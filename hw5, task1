package ru.gb.jcore.hw_5;

import java.io.File;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

import static java.nio.file.StandardCopyOption.REPLACE_EXISTING;

public class Backup {
    public static void createBackup(String sourcePath, String targetPath) throws IOException {
        File root = new File(sourcePath);
        File[] directoryFiles = root.listFiles();

        if (directoryFiles != null) {
            for (File file : directoryFiles) {
                if (file.isDirectory()) {
                    Path newDerictory = Paths.get(targetPath).resolve(file.getName());
                    Files.createDirectories(newDerictory);
                    createBackup(file.getPath(), String.valueOf(newDerictory));
                } else {
                    Files.copy(file.toPath(), Paths.get(targetPath).resolve(file.getName()), REPLACE_EXISTING);
                }
            }
        }
    }
}

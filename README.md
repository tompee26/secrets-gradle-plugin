# Secrets Gradle Plugin for Android

A fork of Google's [secrets-gradle-plugin](https://github.com/google/secrets-gradle-plugin) with the following changes:
1. Support for inline secrets in the `build.gradle` file.

For instructions on how to use, see the original [README](https://github.com/google/secrets-gradle-plugin/blob/main/README.md).

## Installation

1. In your `settings.gradle.kts` file:
```
pluginManagement {
    repositories {
        maven {
            url = uri("https://maven.pkg.github.com/tompee26/secrets-gradle-plugin")
            credentials {
                username = <username>
                password = <token with packages scope>
            }
        }
    }
}
```
1. In your version catalog file:
```
secrets = { id = "com.tompee.secrets-gradle-plugin", version.ref = "secretsversion" }
```
1. In your project's root `build.gradle.kts` file:
```
plugins {
    alias(libs.plugins.secrets) apply false
}
```
1. In your app-level `build.gradle.kts` file:
```
plugins {
    alias(libs.plugins.secrets)
}

secrets {
    inlineProperties += mapOf("key" to "value")
}
```

## License
Apache 2.0. See [LICENSE](LICENSE) for more information.

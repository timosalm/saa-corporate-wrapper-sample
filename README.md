# SAA Corporate Starter Sample

This project contains a Spring Boot wrapper example for [Spring Application Advisor](https://enterprise.spring.io/spring-application-advisor).

## Publishing to GitHub Packages

To publish the wrapper artifact to GitHub Packages, follow these steps:

### Prerequisites
- Ensure you have Maven installed or use the provided Maven wrapper (`./mvnw`).
- Create a GitHub Personal Access Token (PAT) with the following permissions:
  - `repo` (full control of private repositories)
  - `packages:write` (write packages)

### Configure Maven Settings
1. Edit your `~/.m2/settings.xml` file (create it if it doesn't exist).
2. Add the following server configuration:

```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                              https://maven.apache.org/xsd/settings-1.0.0.xsd">
  <servers>
    <server>
      <id>github</id>
      <username>YOUR_GITHUB_USERNAME</username>
      <password>YOUR_GITHUB_TOKEN</password>
    </server>
  </servers>
</settings>
```

Replace `YOUR_GITHUB_USERNAME` with your GitHub username and `YOUR_GITHUB_TOKEN` with your PAT.

### Publish the Artifact
To publish the wrapper:
   ```bash
   ./mvnw -f wrapper/pom.xml clean deploy
   ```

This will build and deploy each artifact to GitHub Packages under the repository `timosalm/saa-corporate-wrapper-sample`.

### Notes
- The `distributionManagement` section in the `pom.xml` files is already configured to point to GitHub Packages.
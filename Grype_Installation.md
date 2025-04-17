# Grype 

Grype is a vulnerability scanner for container images and filesystems. 

## Grype Installation

```bash
sudo curl -sSfL https://raw.githubusercontent.com/anchore/grype/main/install.sh | sudo sh -s -- -b /usr/local/bin
```
# Syft

Grype Works with `Syft`,which is a powerful SBOM (software bill of materials) tool for container images and filesystems.Before scanning image or files we need to install syft.

## syft Installation

```bash
sudo curl -sSfL https://raw.githubusercontent.com/anchore/syft/main/install.sh | sudo sh -s -- -b /usr/local/bin
```

after installation, using syft create SBOM for particular docker image or file. Use following command to create SBOM in json format and store it in file with any name e.g `syft-sbom.json`.

```bash
syft <image_name or file_name> -o syft-json > syft-sbom.json
```
 After this clone grype repo for templates to generate report in different formats that you want. for clone the repo use following command.

```bash
git clone https://github.com/anchore/grype.git ~/.grype
```

then for generating report in html format use following command and store report in file. e.g `report.html`

```bash
grype -o template -t ~/.grype/templates/html.tmpl sbom:./syft-json.json > report.html
```
 After run this command you get report of vulnerabilities in image or file.

 For reference/more info use following links:
 
 Grype
 ```href
 https://github.com/anchore/grype.git
 ```
 Syft
 ```href
 https://github.com/anchore/syft
 ```

@Library('jenkins-shared-library@v1.0') _

def moduleName = "auth"
def helmFile = "staging-helm"
def baseImageTag = "1.19.2_v1.19"

deployGolangStaging {
    env = [
        project: "fulfillment",
        module: "ffm-${moduleName}",
        gitUrl: "git@bitbucket.org:hasaki-tech/fulfillment_${moduleName}.git"
    ]
    test = [
        enable: true
    ]
    build = [
        baseImage: "ffm-harbor.inshasaki.com/base-images/fulfillment/base-golang:${baseImageTag}",
    ]
    deploy = [
        web: [
            helmRepoRev: "go-helm",
            helmFile: "helmfile/${helmFile}.yaml"
        ],
    ]
}

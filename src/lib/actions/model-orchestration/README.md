# Entity Update Orchestration Github Action

This action checks for updates to entity model definition files located in the `entities/` 
directory. Entity model definition files are Typescript files that follow a `*entity-name*.model.ts`
file naming convention.

## Inputs

## `srclaunch-project-id`

**Required** The ID of the SrcLaunch project associated with the entities.

## `srclaunch-project-pipeline-secret`

**Required** Secret token required to authenticate the SrcLaunch integration.

## Outputs

## `error_message`

A string indicating the cause for an entity update failure.

## `failed`

Boolean value indicating whether entity changes failed to complete.

## `not_updated`

A boolean value indicating whether or not entity updates have been detected, and 
update orchestration has been skipped.

## `update_success`

Boolean value indicating whether entities were updated succesfully.

## Example usage

```
uses: actions/entity-update-orchestration-github-action@v1.1
with:
    github-token: ${{ secrets.GITHUB_TOKEN }}
    srclaunch-project-id: ${{ secrets.SRCLAUNCH_PROJECT_ID }}
    srclaunch-project-pipeline-secret: ${{ secrets.SRCLAUNCH_PROJECT_PIPELINE_SECRET }}
```
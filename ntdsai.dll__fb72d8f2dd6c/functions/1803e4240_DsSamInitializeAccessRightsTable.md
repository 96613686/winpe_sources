# DsSamInitializeAccessRightsTable

- ea: `0x1803e4240`
- end: `0x1803e440a`
- name: `DsSamInitializeAccessRightsTable`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180400bc0`

## callees

- `0x18001ea60`
- `0x1803e3630`
- `0x1803e4240`
- `0x1803e6708`

## import_xrefs

- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1803e4266`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1803e4266`
- `SAMSRV!SampSetErrorInfo` at `0x1803e43fc`
- `SAMSRV!SampSetErrorInfo` at `0x1803e43fc`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e428d`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e42d1`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e4319`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e4361`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e43a6`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e43eb`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e428d`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e42d1`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e4319`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e4361`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e43a6`
- `SAMSRV!SampSetCheckpointInfo` at `0x1803e43eb`

## string_xrefs

- `0x1803e4286`: `DsSamInitializeAclConversionCache`
- `0x1803e43f3`: `DsSamInitializeAclConversionCache`
- `0x1803e42be`: `SampComputeReverseAccessRights`
- `0x1803e42ca`: `SampComputeReverseAccessRights`
- `0x1803e4396`: `SampComputeReverseAccessRights(AliasAccessRightMappingTable)`
- `0x1803e439f`: `SampComputeReverseAccessRights(AliasAccessRightMappingTable)`
- `0x1803e43db`: `SampComputeReverseAccessRights(UserAccessRightMappingTable)`
- `0x1803e43e4`: `SampComputeReverseAccessRights(UserAccessRightMappingTable)`
- `0x1803e4306`: `SampComputeReverseAccessRights(DomainAccessRightMappingTable)`
- `0x1803e4312`: `SampComputeReverseAccessRights(DomainAccessRightMappingTable)`
- `0x1803e434e`: `SampComputeReverseAccessRights(GroupAccessRightMappingTable)`
- `0x1803e435a`: `SampComputeReverseAccessRights(GroupAccessRightMappingTable)`

## pseudocode

```c

```

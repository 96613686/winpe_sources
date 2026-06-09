# SampDsValidateDomainControllerCreation

- ea: `0x180412080`
- end: `0x1804122f9`
- name: `SampDsValidateDomainControllerCreation`
- size: `633`
- prototype: `__int64 __fastcall(PVOID HandleId)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001e090`
- `0x1803af8f0`
- `0x1803e00d0`
- `0x1803e6ee4`
- `0x180412080`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1804121ff`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1804121ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804122ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804122ac`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x18041227d`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x18041227d`
- `ntdll!RtlFreeHeap` at `0x1804122ca`
- `ntdll!RtlFreeHeap` at `0x1804122ca`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180412163`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180412163`
- `SAMSRV!SampGetObjectTypeNameFromIndex` at `0x18041220c`
- `SAMSRV!SampGetObjectTypeNameFromIndex` at `0x18041220c`
- `SAMSRV!SampImpersonateClient` at `0x1804121e0`
- `SAMSRV!SampImpersonateClient` at `0x1804121e0`
- `SAMSRV!SampGetSamSubsystemName` at `0x180412215`
- `SAMSRV!SampGetSamSubsystemName` at `0x180412215`
- `SAMSRV!SampRevertToSelf` at `0x180412288`
- `SAMSRV!SampRevertToSelf` at `0x180412288`

## pseudocode

```c

```

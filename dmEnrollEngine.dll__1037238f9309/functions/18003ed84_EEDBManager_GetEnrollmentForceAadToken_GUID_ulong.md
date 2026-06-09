# EEDBManager::GetEnrollmentForceAadToken(_GUID,ulong *)

- ea: `0x18003ed84`
- end: `0x18003ee4c`
- name: `?GetEnrollmentForceAadToken@EEDBManager@@SAJU_GUID@@PEAK@Z`
- size: `200`
- prototype: `static int(struct _GUID *__struct_ptr, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180040850`

## callees

- `0x180005cf0`
- `0x1800071c0`
- `0x18003ed84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ee11`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ee11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ede0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ede0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee39`

## string_xrefs

- `0x18003edfa`: `ForceAadToken`

## pseudocode

```c

```

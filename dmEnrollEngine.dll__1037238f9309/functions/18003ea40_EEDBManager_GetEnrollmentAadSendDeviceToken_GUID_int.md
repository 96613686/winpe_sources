# EEDBManager::GetEnrollmentAadSendDeviceToken(_GUID,int *)

- ea: `0x18003ea40`
- end: `0x18003eb08`
- name: `?GetEnrollmentAadSendDeviceToken@EEDBManager@@SAJU_GUID@@PEAH@Z`
- size: `200`
- prototype: `static int(struct _GUID *__struct_ptr, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180040700`

## callees

- `0x180005cf0`
- `0x1800071c0`
- `0x18003ea40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003eacd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003eacd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ea9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eaf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ea9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eaf5`

## string_xrefs

- `0x18003eab6`: `AADSendDeviceToken`

## pseudocode

```c

```

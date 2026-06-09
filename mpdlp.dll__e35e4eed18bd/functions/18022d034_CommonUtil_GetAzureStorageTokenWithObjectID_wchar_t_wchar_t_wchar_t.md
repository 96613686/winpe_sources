# CommonUtil::GetAzureStorageTokenWithObjectID(wchar_t * *,wchar_t * *,wchar_t * *)

- ea: `0x18022d034`
- end: `0x18022d2ee`
- name: `?GetAzureStorageTokenWithObjectID@CommonUtil@@YAJPEAPEA_W00@Z`
- size: `698`
- prototype: `int(CommonUtil *__hidden this, wchar_t **, wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180208c60`

## callees

- `0x1800809d0`
- `0x1800b7f88`
- `0x180106620`
- `0x180106cc4`
- `0x180107188`
- `0x18010cb40`
- `0x18010ce3c`
- `0x180145e30`
- `0x18022d034`
- `0x180231a50`
- `0x180232080`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18022d0a6`
- `KERNEL32!CloseHandle` at `0x18022d11b`
- `KERNEL32!CloseHandle` at `0x18022d12a`
- `KERNEL32!CloseHandle` at `0x18022d198`
- `KERNEL32!CloseHandle` at `0x18022d1a7`
- `KERNEL32!CloseHandle` at `0x18022d289`
- `KERNEL32!CloseHandle` at `0x18022d298`
- `KERNEL32!CloseHandle` at `0x18022d2b9`
- `KERNEL32!CloseHandle` at `0x18022d2c8`
- `KERNEL32!CloseHandle` at `0x18022d0a6`
- `KERNEL32!CloseHandle` at `0x18022d11b`
- `KERNEL32!CloseHandle` at `0x18022d12a`
- `KERNEL32!CloseHandle` at `0x18022d198`
- `KERNEL32!CloseHandle` at `0x18022d1a7`
- `KERNEL32!CloseHandle` at `0x18022d289`
- `KERNEL32!CloseHandle` at `0x18022d298`
- `KERNEL32!CloseHandle` at `0x18022d2b9`
- `KERNEL32!CloseHandle` at `0x18022d2c8`
- `ADVAPI32!RevertToSelf` at `0x18022d229`
- `ADVAPI32!RevertToSelf` at `0x18022d229`

## string_xrefs

- `0x18022d160`: `CommonUtil::GetAzureStorageTokenWithObjectID`
- `0x18022d17a`: `Failed to duplicate impersonation token Error_`
- `0x18022d0fc`: `Failed to duplicate token Error_`

## pseudocode

```c

```

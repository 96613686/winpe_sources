# AddACLToObjectSecurityDescriptor(void *,_SE_OBJECT_TYPE)

- ea: `0x1804ac38c`
- end: `0x1804ac758`
- name: `?AddACLToObjectSecurityDescriptor@@YAHPEAXW4_SE_OBJECT_TYPE@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(void *, enum _SE_OBJECT_TYPE)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1804acc58`

## callees

- `0x1804ac38c`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1804ac405`
- `KERNEL32!LoadLibraryW` at `0x1804ac405`
- `KERNEL32!OutputDebugStringW` at `0x1804ac66d`
- `KERNEL32!OutputDebugStringW` at `0x1804ac66d`
- `KERNEL32!LocalFree` at `0x1804ac71c`
- `KERNEL32!LocalFree` at `0x1804ac71c`
- `KERNEL32!GetProcAddress` at `0x1804ac426`
- `KERNEL32!GetProcAddress` at `0x1804ac442`
- `KERNEL32!GetProcAddress` at `0x1804ac658`
- `KERNEL32!GetProcAddress` at `0x1804ac6af`
- `KERNEL32!GetProcAddress` at `0x1804ac426`
- `KERNEL32!GetProcAddress` at `0x1804ac442`
- `KERNEL32!GetProcAddress` at `0x1804ac658`
- `KERNEL32!GetProcAddress` at `0x1804ac6af`
- `KERNEL32!FreeLibrary` at `0x1804ac725`
- `KERNEL32!FreeLibrary` at `0x1804ac725`

## string_xrefs

- `0x1804ac3ce`: `advapi32.dll`
- `0x1804ac6a5`: `FreeSid`
- `0x1804ac666`: `AddSidToObjectsSecurityDescriptor: Can't get proc SetSecurityInfo`
- `0x1804ac64e`: `SetSecurityInfo`
- `0x1804ac438`: `SetEntriesInAclW`
- `0x1804ac417`: `AllocateAndInitializeSid`

## pseudocode

```c

```

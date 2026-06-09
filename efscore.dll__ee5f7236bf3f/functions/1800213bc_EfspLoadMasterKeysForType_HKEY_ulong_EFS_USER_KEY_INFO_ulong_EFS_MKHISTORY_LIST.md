# EfspLoadMasterKeysForType(HKEY__ *,ulong,_EFS_USER_KEY_INFO *,ulong,_EFS_MKHISTORY_LIST *)

- ea: `0x1800213bc`
- end: `0x180021b72`
- name: `?EfspLoadMasterKeysForType@@YAKPEAUHKEY__@@KPEAU_EFS_USER_KEY_INFO@@KPEAU_EFS_MKHISTORY_LIST@@@Z`
- size: `1974`
- prototype: `unsigned int __usercall@<eax>(HKEY hkey@<rcx>, unsigned int@<edx>, struct _EFS_USER_KEY_INFO *@<r8>, unsigned int@<r9d>, struct _EFS_MKHISTORY_LIST *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800211ac`

## callees

- `0x18000efb8`
- `0x180010bf0`
- `0x180020138`
- `0x1800205e0`
- `0x180020cd0`
- `0x1800213bc`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180063a0c`
- `0x1800d87ac`
- `0x1800dca3c`
- `0x1800dddb6`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b3f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800218b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800218b8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002173a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002173a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800214e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800214e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021460`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021460`

## pseudocode

```c

```

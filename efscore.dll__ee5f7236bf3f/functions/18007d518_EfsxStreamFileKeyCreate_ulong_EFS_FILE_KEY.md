# EfsxStreamFileKeyCreate(ulong,_EFS_FILE_KEY * *)

- ea: `0x18007d518`
- end: `0x18007d796`
- name: `?EfsxStreamFileKeyCreate@@YAKKPEAPEAU_EFS_FILE_KEY@@@Z`
- size: `638`
- prototype: `unsigned int __fastcall(unsigned int, struct _EFS_FILE_KEY **)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180074220`
- `0x180076630`

## callees

- `0x180004f86`
- `0x180005045`
- `0x18004a89c`
- `0x180063698`
- `0x180069c6c`
- `0x180070410`
- `0x18007d518`
- `0x1800dddf0`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18007d664`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18007d664`
- `bcrypt!BCryptDestroyKey` at `0x18007d761`
- `bcrypt!BCryptDestroyKey` at `0x18007d761`
- `bcrypt!BCryptGenRandom` at `0x18007d5b6`
- `bcrypt!BCryptGenRandom` at `0x18007d5b6`
- `ntdll!RtlNtStatusToDosError` at `0x18007d5c2`
- `ntdll!RtlNtStatusToDosError` at `0x18007d670`
- `ntdll!RtlNtStatusToDosError` at `0x18007d5c2`
- `ntdll!RtlNtStatusToDosError` at `0x18007d670`

## pseudocode

```c

```

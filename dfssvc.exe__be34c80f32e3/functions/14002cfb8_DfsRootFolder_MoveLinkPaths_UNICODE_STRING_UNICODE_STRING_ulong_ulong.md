# DfsRootFolder::MoveLinkPaths(_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *)

- ea: `0x14002cfb8`
- end: `0x14002d32d`
- name: `?MoveLinkPaths@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@0KPEAK@Z`
- size: `885`
- prototype: `unsigned int __usercall@<eax>(DfsRootFolder *__hidden this@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400117e4`

## callees

- `0x140005a94`
- `0x14000a354`
- `0x1400177fc`
- `0x14002cfb8`
- `0x1400582e4`
- `0x14005e010`

## import_xrefs

- `msvcrt!wcscspn` at `0x14002d100`
- `msvcrt!wcscspn` at `0x14002d100`
- `ntdll!RtlEqualUnicodeString` at `0x14002d143`
- `ntdll!RtlEqualUnicodeString` at `0x14002d143`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002d282`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002d282`

## pseudocode

```c

```

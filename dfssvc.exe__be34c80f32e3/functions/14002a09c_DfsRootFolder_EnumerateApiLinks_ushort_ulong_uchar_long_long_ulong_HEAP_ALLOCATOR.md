# DfsRootFolder::EnumerateApiLinks(ushort *,ulong,uchar * *,long *,long *,ulong *,_HEAP_ALLOCATOR *)

- ea: `0x14002a09c`
- end: `0x14002a254`
- name: `?EnumerateApiLinks@DfsRootFolder@@QEAAKPEAGKPEAPEAEPEAJ2PEAKPEAU_HEAP_ALLOCATOR@@@Z`
- size: `440`
- prototype: `unsigned int __usercall@<eax>(DfsRootFolder *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int8 **@<r9>, int *, int *, unsigned int *, struct _HEAP_ALLOCATOR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140010f9c`

## callees

- `0x14000a354`
- `0x14002a09c`
- `0x14002b5d0`
- `0x140058db8`
- `0x14005e010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14002a0e4`
- `ntdll!RtlInitUnicodeString` at `0x14002a0e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002a22d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002a22d`

## pseudocode

```c

```

# CPersistentWorkStorage::UpdateWorkItemEntry(IRdlsDBConnection *,WORKITEM_OPERATION,uchar *,ulong,ulong,ulong,ulong,uchar *,ulong)

- ea: `0x18004c26c`
- end: `0x18004c549`
- name: `?UpdateWorkItemEntry@CPersistentWorkStorage@@AEAAHPEAVIRdlsDBConnection@@W4WORKITEM_OPERATION@@PEAEKKKK2K@Z`
- size: `733`
- prototype: `int __high(struct IRdlsDBConnection *, enum WORKITEM_OPERATION, unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18004ad70`
- `0x18004af00`
- `0x18004b0c4`
- `0x18004ba6c`

## callees

- `0x180031f3c`
- `0x1800320d0`
- `0x18004b630`
- `0x18004bd54`
- `0x18004c26c`
- `0x180066320`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004c2ee`
- `KERNEL32!GetLastError` at `0x18004c2ee`
- `KERNEL32!LocalFree` at `0x18004c39b`
- `KERNEL32!LocalFree` at `0x18004c39b`
- `KERNEL32!SetLastError` at `0x18004c36b`
- `KERNEL32!SetLastError` at `0x18004c36b`

## pseudocode

```c

```

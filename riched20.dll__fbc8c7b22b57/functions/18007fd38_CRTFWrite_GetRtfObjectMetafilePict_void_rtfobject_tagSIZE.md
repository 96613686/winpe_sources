# CRTFWrite::GetRtfObjectMetafilePict(void *,_rtfobject &,tagSIZE &)

- ea: `0x18007fd38`
- end: `0x18007fe49`
- name: `?GetRtfObjectMetafilePict@CRTFWrite@@AEAAHPEAXAEAU_rtfobject@@AEAUtagSIZE@@@Z`
- size: `273`
- prototype: `int(CRTFWrite *__hidden this, void *, struct _rtfobject *, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007fbac`

## callees

- `0x180039990`
- `0x18004bac8`
- `0x18007fd38`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18007fdcb`
- `KERNEL32!GlobalAlloc` at `0x18007fdcb`
- `KERNEL32!GlobalLock` at `0x18007fd53`
- `KERNEL32!GlobalLock` at `0x18007fde2`
- `KERNEL32!GlobalLock` at `0x18007fd53`
- `KERNEL32!GlobalLock` at `0x18007fde2`
- `KERNEL32!GlobalUnlock` at `0x18007fe2d`
- `KERNEL32!GlobalUnlock` at `0x18007fe2d`
- `GDI32!GetMetaFileBitsEx` at `0x18007fdb2`
- `GDI32!GetMetaFileBitsEx` at `0x18007fe0b`
- `GDI32!GetMetaFileBitsEx` at `0x18007fdb2`
- `GDI32!GetMetaFileBitsEx` at `0x18007fe0b`

## pseudocode

```c

```

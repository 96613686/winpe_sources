# CFtpDrop::_CopyHglobal(IStream *,ulong,ulong,ulong,void *,_ULARGE_INTEGER *)

- ea: `0x1800141f0`
- end: `0x180014298`
- name: `?_CopyHglobal@CFtpDrop@@SAJPEAUIStream@@KKKPEAXPEAT_ULARGE_INTEGER@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(struct IStream *, unsigned int, unsigned int, unsigned int, HGLOBAL hMem, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800141f0`
- `0x180028010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180014222`
- `KERNEL32!GlobalLock` at `0x180014222`
- `KERNEL32!GlobalUnlock` at `0x18001427a`
- `KERNEL32!GlobalUnlock` at `0x18001427a`
- `KERNEL32!GlobalSize` at `0x180014238`
- `KERNEL32!GlobalSize` at `0x180014238`

## pseudocode

```c

```

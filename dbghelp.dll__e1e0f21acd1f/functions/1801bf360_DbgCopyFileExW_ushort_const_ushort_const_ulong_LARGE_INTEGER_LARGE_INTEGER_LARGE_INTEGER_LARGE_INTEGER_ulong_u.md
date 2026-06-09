# DbgCopyFileExW(ushort const *,ushort const *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,int *,ulong)

- ea: `0x1801bf360`
- end: `0x1801bf401`
- name: `?DbgCopyFileExW@@YAHPEBG0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z2PEAHK@Z`
- size: `161`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *, int *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a820`
- `0x1801a16d0`

## callees

- `0x1800084a0`
- `0x1801bf360`
- `0x1801bf4a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bf3ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bf3ee`

## pseudocode

```c

```

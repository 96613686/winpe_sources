# HashComputeMemoryHashMultiple(void *,ulong,_HASHLIB_BLOB *,uchar *,ulong *)

- ea: `0x18010d3d4`
- end: `0x18010d49c`
- name: `?HashComputeMemoryHashMultiple@@YAJPEAXKPEAU_HASHLIB_BLOB@@PEAEPEAK@Z`
- size: `200`
- prototype: `int(void *, unsigned int, struct _HASHLIB_BLOB *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180063444`

## callees

- `0x180005e40`
- `0x18010d3d4`
- `0x18010d4a4`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18010d447`
- `bcrypt!BCryptHashData` at `0x18010d447`
- `bcrypt!BCryptDestroyHash` at `0x18010d471`
- `bcrypt!BCryptDestroyHash` at `0x18010d471`
- `bcrypt!BCryptFinishHash` at `0x18010d466`
- `bcrypt!BCryptFinishHash` at `0x18010d466`

## pseudocode

```c

```

# ReadDbEntry

- ea: `0x180017fbc`
- end: `0x1800182cc`
- name: `ReadDbEntry`
- size: `784`
- prototype: `__int64 __fastcall(JET_SESID sesid, char *, char *, unsigned int cbData)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180017ad0`

## callees

- `0x18000f144`
- `0x180017fbc`
- `0x1800cc982`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x1800180ba`
- `ESENT!JetRetrieveColumns` at `0x1800180ba`
- `ESENT!JetRetrieveColumn` at `0x18001818e`
- `ESENT!JetRetrieveColumn` at `0x180018238`
- `ESENT!JetRetrieveColumn` at `0x18001818e`
- `ESENT!JetRetrieveColumn` at `0x180018238`
- `KERNEL32!HeapAlloc` at `0x180018034`
- `KERNEL32!HeapAlloc` at `0x180018034`
- `KERNEL32!HeapFree` at `0x18001826b`
- `KERNEL32!HeapFree` at `0x18001826b`

## string_xrefs

- `0x1800180c8`: `ReadDBEntry:JetRetrieveColumns()`
- `0x18001819c`: `C:ReadDbEntry`
- `0x180018246`: `C:ReadDbEntry`

## pseudocode

```c

```

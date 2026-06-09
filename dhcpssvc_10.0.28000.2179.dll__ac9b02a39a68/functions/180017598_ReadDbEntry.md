# ReadDbEntry

- ea: `0x180017598`
- end: `0x1800178a2`
- name: `ReadDbEntry`
- size: `778`
- prototype: `__int64 __fastcall(JET_SESID sesid, void *, void *, unsigned int cbData)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001709c`

## callees

- `0x18000e814`
- `0x180017598`
- `0x1800cda62`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x18001769c`
- `ESENT!JetRetrieveColumns` at `0x18001769c`
- `ESENT!JetRetrieveColumn` at `0x180017772`
- `ESENT!JetRetrieveColumn` at `0x180017815`
- `ESENT!JetRetrieveColumn` at `0x180017772`
- `ESENT!JetRetrieveColumn` at `0x180017815`
- `KERNEL32!HeapAlloc` at `0x180017617`
- `KERNEL32!HeapAlloc` at `0x180017617`
- `KERNEL32!HeapFree` at `0x180017848`
- `KERNEL32!HeapFree` at `0x180017848`

## string_xrefs

- `0x1800176aa`: `ReadDBEntry:JetRetrieveColumns()`
- `0x180017780`: `C:ReadDbEntry`
- `0x180017823`: `C:ReadDbEntry`

## pseudocode

```c

```

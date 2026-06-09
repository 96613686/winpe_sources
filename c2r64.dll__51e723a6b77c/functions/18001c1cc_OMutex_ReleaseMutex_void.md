# OMutex::ReleaseMutex(void)

- ea: `0x18001c1cc`
- end: `0x18001c265`
- name: `?ReleaseMutex@OMutex@@QEAAXXZ`
- size: `153`
- prototype: `void __fastcall(OMutex *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001bdc8`

## callees

- `0x18001c1cc`
- `0x18003e690`
- `0x1800409e0`
- `0x180043dd0`
- `0x18013292c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c20b`
- `KERNEL32!GetLastError` at `0x18001c20b`
- `KERNEL32!ReleaseMutex` at `0x18001c1e9`
- `KERNEL32!ReleaseMutex` at `0x18001c1e9`

## string_xrefs

- `0x18001c226`: `Current thread doesn't own this mutex`

## pseudocode

```c

```

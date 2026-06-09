# UIComposition::GetSelection(IMCLock &,long *,long *)

- ea: `0x18005221c`
- end: `0x180052531`
- name: `?GetSelection@UIComposition@@QEAAJAEAVIMCLock@@PEAJ1@Z`
- size: `789`
- prototype: `__int64 __fastcall(UIComposition *__hidden this, struct IMCLock *, int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180049234`

## callees

- `0x1800185f0`
- `0x180018640`
- `0x18001cc80`
- `0x18005221c`
- `0x180052608`
- `0x180074c50`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800523a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800523a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800522f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800522f8`
- `IMM32!ImmLockIMCC` at `0x180052271`
- `IMM32!ImmLockIMCC` at `0x180052271`
- `IMM32!ImmUnlockIMCC` at `0x18005234d`
- `IMM32!ImmUnlockIMCC` at `0x180052396`
- `IMM32!ImmUnlockIMCC` at `0x18005234d`
- `IMM32!ImmUnlockIMCC` at `0x180052396`

## string_xrefs

- `0x18005237d`: `UIComposition::OnSetCursor. imc_ctfime==NULL`
- `0x1800524a2`: `UIComposition::OnSetCursor. _pCicContext==NULL`

## pseudocode

```c

```

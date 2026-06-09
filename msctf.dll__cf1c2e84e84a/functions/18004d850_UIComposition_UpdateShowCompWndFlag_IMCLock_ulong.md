# UIComposition::UpdateShowCompWndFlag(IMCLock &,ulong *)

- ea: `0x18004d850`
- end: `0x18004da4e`
- name: `?UpdateShowCompWndFlag@UIComposition@@AEAAJAEAVIMCLock@@PEAK@Z`
- size: `510`
- prototype: `__int64 __fastcall(UIComposition *__hidden this, struct IMCLock *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180048298`
- `0x180049234`
- `0x1800e381c`

## callees

- `0x1800185f0`
- `0x18001cc80`
- `0x18004d850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d9a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d9a7`
- `USER32!IsWindow` at `0x18004d882`
- `USER32!IsWindow` at `0x18004d882`
- `IMM32!ImmLockIMCC` at `0x18004d8c6`
- `IMM32!ImmLockIMCC` at `0x18004d926`
- `IMM32!ImmLockIMCC` at `0x18004d8c6`
- `IMM32!ImmLockIMCC` at `0x18004d926`
- `IMM32!ImmUnlockIMCC` at `0x18004d94a`
- `IMM32!ImmUnlockIMCC` at `0x18004d985`
- `IMM32!ImmUnlockIMCC` at `0x18004d99d`
- `IMM32!ImmUnlockIMCC` at `0x18004d94a`
- `IMM32!ImmUnlockIMCC` at `0x18004d985`
- `IMM32!ImmUnlockIMCC` at `0x18004d99d`

## string_xrefs

- `0x18004d931`: `UIComposition::UpdateShowCompWndFlag. comp==NULL`
- `0x18004d9d7`: `UIComposition::UpdateShowCompWndFlag. imc->hWNd==NULL`
- `0x18004d9fc`: `UIComposition::UpdateCompWndFlag. imc_ctfime==NULL`
- `0x18004da08`: `UIComposition::UpdateCompWndFlag. _pCicContext==NULL`
- `0x18004da2c`: `UIComposition::UpdateShowCompWndFlag. imc==NULL`

## pseudocode

```c

```

# UIComposition::OnPrivateGetContextFlag(IMCLock &,int,IME_UIWND_STATE *)

- ea: `0x180060178`
- end: `0x18006030d`
- name: `?OnPrivateGetContextFlag@UIComposition@@QEAAJAEAVIMCLock@@HPEAW4IME_UIWND_STATE@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(UIComposition *__hidden this, struct IMCLock *, int, enum IME_UIWND_STATE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a9e0`

## callees

- `0x1800185f0`
- `0x18001cc80`
- `0x180060178`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060276`
- `USER32!IsWindowVisible` at `0x1800602ad`
- `USER32!IsWindowVisible` at `0x1800602e8`
- `USER32!IsWindowVisible` at `0x1800602ad`
- `USER32!IsWindowVisible` at `0x1800602e8`
- `USER32!IsWindow` at `0x1800601ae`
- `USER32!IsWindow` at `0x1800601d2`
- `USER32!IsWindow` at `0x1800601ae`
- `USER32!IsWindow` at `0x1800601d2`
- `IMM32!ImmLockIMCC` at `0x18006021d`
- `IMM32!ImmLockIMCC` at `0x18006021d`
- `IMM32!ImmUnlockIMCC` at `0x18006026c`
- `IMM32!ImmUnlockIMCC` at `0x18006026c`

## string_xrefs

- `0x180060253`: `UIComposition::OnPrivateGetContextFlag. imc_ctfime==NULL`
- `0x180060286`: `UIComposition::OnPrivateGetContextFlag. _pCicContext==NULL`

## pseudocode

```c

```

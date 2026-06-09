# CicInputContext::InquireIMECharPosition(ushort,CicInputContext::IME_QUERY_POS *)

- ea: `0x180061a6c`
- end: `0x180061b9d`
- name: `?InquireIMECharPosition@CicInputContext@@QEAAJGPEAW4IME_QUERY_POS@1@@Z`
- size: `305`
- prototype: `__int64 __fastcall(CicInputContext *__hidden this, unsigned __int16, enum CicInputContext::IME_QUERY_POS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a9e0`

## callees

- `0x18001cc80`
- `0x180061a6c`
- `0x180106a60`

## import_xrefs

- `USER32!SendMessageW` at `0x180061b4b`
- `USER32!SendMessageW` at `0x180061b4b`
- `IMM32!ImmLockIMC` at `0x180061b23`
- `IMM32!ImmLockIMC` at `0x180061b23`
- `IMM32!ImmRequestMessageW` at `0x180061b61`
- `IMM32!ImmRequestMessageW` at `0x180061b61`
- `IMM32!ImmUnlockIMC` at `0x180061b6f`
- `IMM32!ImmUnlockIMC` at `0x180061b85`
- `IMM32!ImmUnlockIMC` at `0x180061b6f`
- `IMM32!ImmUnlockIMC` at `0x180061b85`
- `IMM32!ImmGetAppCompatFlags` at `0x180061ae5`
- `IMM32!ImmGetAppCompatFlags` at `0x180061ae5`

## pseudocode

```c

```

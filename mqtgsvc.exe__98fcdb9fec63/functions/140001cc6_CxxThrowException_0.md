# _CxxThrowException_0

- ea: `0x140001cc6`
- end: `0x140001ccc`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `73`
- callee_count: `0`
- tags: ``

## callers

- `0x1400014d4`
- `0x140001530`
- `0x140003958`
- `0x140004868`
- `0x1400049d0`
- `0x140004a00`
- `0x140004a40`
- `0x140004a80`
- `0x140004c24`
- `0x1400053dc`
- `0x140005ad8`
- `0x140006960`
- `0x140006b54`
- `0x140006d34`
- `0x140007034`
- `0x1400076a8`
- `0x14000858c`
- `0x140008c44`
- `0x140008f50`
- `0x14000a6dc`
- `0x14000afa0`
- `0x14000b180`
- `0x14000bdc0`
- `0x14000cac4`
- `0x14000cd44`
- `0x14000d00c`
- `0x14000d110`
- `0x14000d75c`
- `0x14000e570`
- `0x14000e768`
- `0x14000eb04`
- `0x14000ecd0`
- `0x14000ed70`
- `0x14000eda0`
- `0x14000f0a4`
- `0x14000f61c`
- `0x14000f6e0`
- `0x14001050c`
- `0x1400105cc`
- `0x14001068c`
- `0x1400115c8`
- `0x140011d38`
- `0x140012630`
- `0x140012670`
- `0x140013200`
- `0x140013bf8`
- `0x1400149f4`
- `0x140015220`
- `0x140016b38`
- `0x14001a320`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x140001cc6`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException_0(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x140001cc6  jmp     cs:__imp__CxxThrowException
```

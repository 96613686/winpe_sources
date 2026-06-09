# _CxxThrowException_0

- ea: `0x18000df14`
- end: `0x18000df1a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004c60`
- `0x180005560`
- `0x18000d6a0`
- `0x18000d6e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x18000df14`

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
0x18000df14  jmp     cs:__imp__CxxThrowException
```

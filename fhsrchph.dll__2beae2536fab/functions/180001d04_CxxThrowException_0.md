# _CxxThrowException_0

- ea: `0x180001d04`
- end: `0x180001d0a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011c4`
- `0x1800012b8`
- `0x1800012e4`
- `0x18000278c`
- `0x180006418`
- `0x180007a40`
- `0x180009604`
- `0x1800099e4`
- `0x18000a77c`
- `0x18000b23e`
- `0x18000b26c`
- `0x18000b61c`
- `0x18000b642`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001d04`

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
0x180001d04  jmp     cs:__imp__CxxThrowException
```

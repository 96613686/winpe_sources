# _CxxThrowException_0

- ea: `0x18000265c`
- end: `0x180002662`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001518`
- `0x180001558`
- `0x180001584`
- `0x18000418c`
- `0x18000e067`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000265c`

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
0x18000265c  jmp     cs:__imp__CxxThrowException
```

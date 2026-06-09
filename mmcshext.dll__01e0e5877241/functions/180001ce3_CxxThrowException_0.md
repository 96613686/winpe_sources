# _CxxThrowException_0

- ea: `0x180001ce3`
- end: `0x180001ce9`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001348`
- `0x180001370`
- `0x18000139c`
- `0x18000a360`
- `0x18000a9cf`
- `0x18000ae41`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001ce3`

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
0x180001ce3  jmp     cs:__imp__CxxThrowException
```

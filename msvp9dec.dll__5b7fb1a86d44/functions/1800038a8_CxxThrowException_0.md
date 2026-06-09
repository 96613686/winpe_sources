# _CxxThrowException_0

- ea: `0x1800038a8`
- end: `0x1800038ae`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800036e4`
- `0x18000370c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800038a8`

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
0x1800038a8  jmp     cs:__imp__CxxThrowException
```

# _CxxThrowException_0

- ea: `0x180002068`
- end: `0x18000206e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f90`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180002068`

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
0x180002068  jmp     cs:__imp__CxxThrowException
```

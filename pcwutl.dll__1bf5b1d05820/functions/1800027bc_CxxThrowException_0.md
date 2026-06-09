# _CxxThrowException_0

- ea: `0x1800027bc`
- end: `0x1800027c2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001858`
- `0x180001898`
- `0x1800018c4`
- `0x180019347`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800027bc`

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
0x1800027bc  jmp     cs:__imp__CxxThrowException
```

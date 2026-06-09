# _CxxThrowException_0

- ea: `0x180001d18`
- end: `0x180001d1e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011d8`
- `0x1800012d8`
- `0x180001304`
- `0x1800030b4`
- `0x180008b58`
- `0x1800098e0`
- `0x180009faa`
- `0x180009fd8`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001d18`

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
0x180001d18  jmp     cs:__imp__CxxThrowException
```

# _CxxThrowException_0

- ea: `0x1800026cc`
- end: `0x1800026d2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001588`
- `0x1800015c8`
- `0x1800015f4`
- `0x180004048`
- `0x180011497`
- `0x1800119bf`
- `0x1800119e5`
- `0x180011be5`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800026cc`

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
0x1800026cc  jmp     cs:__imp__CxxThrowException
```

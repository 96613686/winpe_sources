# _CxxThrowException_0

- ea: `0x140001909`
- end: `0x14000190f`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400018e0`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x140001909`

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
0x140001909  jmp     cs:__imp__CxxThrowException
```

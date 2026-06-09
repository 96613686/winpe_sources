# _CxxThrowException_0

- ea: `0x1800027ec`
- end: `0x1800027f2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x1800020e8`
- `0x180002128`
- `0x180002154`
- `0x18000818c`
- `0x180008350`
- `0x1800084a0`
- `0x180008b80`
- `0x180009d6b`
- `0x180009d96`
- `0x180009dbc`
- `0x180009de2`
- `0x18000a1da`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800027ec`

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
0x1800027ec  jmp     cs:__imp__CxxThrowException
```

# _CxxThrowException_0

- ea: `0x18000cb69`
- end: `0x18000cb6f`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a54`
- `0x180004d60`
- `0x180004eb0`
- `0x1800057b0`
- `0x18000d4a7`
- `0x18000d526`
- `0x18000d54c`
- `0x18000d73d`
- `0x18000da3e`
- `0x18000dab6`
- `0x18000dc6e`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000cb69`

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
0x18000cb69  jmp     cs:__imp__CxxThrowException
```

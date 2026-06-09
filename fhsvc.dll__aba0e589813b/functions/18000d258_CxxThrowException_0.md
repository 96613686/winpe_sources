# _CxxThrowException_0

- ea: `0x18000d258`
- end: `0x18000d25e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b48c`
- `0x18000cadc`
- `0x180011b00`
- `0x180011f0f`
- `0x180011f2c`
- `0x18001204f`
- `0x180012500`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000d258`

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
0x18000d258  jmp     cs:__imp__CxxThrowException
```

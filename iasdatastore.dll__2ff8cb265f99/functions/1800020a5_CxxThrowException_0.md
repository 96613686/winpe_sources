# _CxxThrowException_0

- ea: `0x1800020a5`
- end: `0x1800020ab`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180002028`
- `0x180002050`
- `0x18000207c`
- `0x180002310`
- `0x1800039a4`
- `0x18000d94c`
- `0x18000dc14`
- `0x18000ecaa`
- `0x18000ed55`
- `0x18000edb8`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800020a5`

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
0x1800020a5  jmp     cs:__imp__CxxThrowException
```

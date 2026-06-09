# _CxxThrowException_0

- ea: `0x180001e0e`
- end: `0x180001e14`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x180001238`
- `0x180001260`
- `0x18000128c`
- `0x180002280`
- `0x18000236c`
- `0x18000d98c`
- `0x18000f208`
- `0x1800137c0`
- `0x1800189fa`
- `0x180018a72`
- `0x180018b19`
- `0x180018b3f`
- `0x180018b7a`
- `0x180018ba0`
- `0x180018bd8`
- `0x180018c32`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001e0e`

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
0x180001e0e  jmp     cs:__imp__CxxThrowException
```

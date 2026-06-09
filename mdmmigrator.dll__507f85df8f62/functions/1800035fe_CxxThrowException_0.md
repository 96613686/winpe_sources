# _CxxThrowException_0

- ea: `0x1800035fe`
- end: `0x180003604`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800035b4`
- `0x180005f4c`
- `0x180006110`
- `0x180006260`
- `0x180006d50`
- `0x18000970c`
- `0x1800118f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800035fe`

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
0x1800035fe  jmp     cs:__imp__CxxThrowException
```

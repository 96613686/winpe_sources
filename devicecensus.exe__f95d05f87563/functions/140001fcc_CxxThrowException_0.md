# _CxxThrowException_0

- ea: `0x140001fcc`
- end: `0x140001fd2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400016b8`
- `0x1400016e0`
- `0x14000170c`
- `0x14001180b`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x140001fcc`

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
0x140001fcc  jmp     cs:__imp__CxxThrowException
```

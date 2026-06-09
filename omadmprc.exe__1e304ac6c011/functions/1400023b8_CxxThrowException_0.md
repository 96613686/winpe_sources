# _CxxThrowException_0

- ea: `0x1400023b8`
- end: `0x1400023be`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140001e38`
- `0x140001e60`
- `0x140001e8c`
- `0x140006f30`
- `0x140008380`
- `0x1400084d0`
- `0x140009400`
- `0x140015bbf`
- `0x140015f7b`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1400023b8`

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
0x1400023b8  jmp     cs:__imp__CxxThrowException
```

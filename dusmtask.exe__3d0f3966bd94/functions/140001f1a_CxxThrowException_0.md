# _CxxThrowException_0

- ea: `0x140001f1a`
- end: `0x140001f20`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140001aa8`
- `0x1400055d4`
- `0x140005820`
- `0x140005970`
- `0x1400068f0`
- `0x140006d54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140001f1a`

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
0x140001f1a  jmp     cs:__imp__CxxThrowException
```

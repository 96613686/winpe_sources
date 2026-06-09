# _CxxThrowException_0

- ea: `0x1400020dc`
- end: `0x1400020e2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140001ef4`
- `0x140005b80`
- `0x140006b60`
- `0x140006cb0`
- `0x140007b80`
- `0x140014548`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1400020dc`

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
0x1400020dc  jmp     cs:__imp__CxxThrowException
```

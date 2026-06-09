# _CxxThrowException_0

- ea: `0x180002990`
- end: `0x180002996`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180002824`
- `0x18000559c`
- `0x1800057e0`
- `0x180005930`
- `0x1800063a0`
- `0x180009ab8`
- `0x18000a938`
- `0x18000a960`
- `0x18000a9bc`
- `0x18000a9fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002990`

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
0x180002990  jmp     cs:__imp__CxxThrowException
```

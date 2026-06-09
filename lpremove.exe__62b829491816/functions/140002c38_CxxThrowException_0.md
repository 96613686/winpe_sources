# _CxxThrowException_0

- ea: `0x140002c38`
- end: `0x140002c3e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1400027b8`
- `0x14000944c`
- `0x14000a770`
- `0x14000a8c0`
- `0x14000c000`
- `0x14000ce78`
- `0x1400104a0`
- `0x14001053a`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140002c38`

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
0x140002c38  jmp     cs:__imp__CxxThrowException
```

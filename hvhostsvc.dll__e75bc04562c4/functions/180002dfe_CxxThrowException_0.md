# _CxxThrowException_0

- ea: `0x180002dfe`
- end: `0x180002e04`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018c0`
- `0x180002da4`
- `0x180002dcc`
- `0x1800051a4`
- `0x180005360`
- `0x1800054f0`
- `0x180005c70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002dfe`

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
0x180002dfe  jmp     cs:__imp__CxxThrowException
```

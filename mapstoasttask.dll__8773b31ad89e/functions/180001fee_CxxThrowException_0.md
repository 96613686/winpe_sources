# _CxxThrowException_0

- ea: `0x180001fee`
- end: `0x180001ff4`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001bf8`
- `0x180004af4`
- `0x180004be0`
- `0x180004d30`
- `0x180005dd0`
- `0x1800063b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180001fee`

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
0x180001fee  jmp     cs:__imp__CxxThrowException
```

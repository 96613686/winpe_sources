# _CxxThrowException_0

- ea: `0x180001faa`
- end: `0x180001fb0`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e50`
- `0x18000462c`
- `0x180004870`
- `0x1800049c0`
- `0x180005430`
- `0x180006ca8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180001faa`

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
0x180001faa  jmp     cs:__imp__CxxThrowException
```

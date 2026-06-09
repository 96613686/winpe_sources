# _CxxThrowException_0

- ea: `0x180014e74`
- end: `0x180014e7a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180006c24`
- `0x1800080f0`
- `0x180008240`
- `0x180009170`
- `0x18000d360`
- `0x18000db80`
- `0x18000dc0c`
- `0x18000dc54`
- `0x18000f77c`
- `0x18001064c`
- `0x1800148c4`
- `0x180015362`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180014e74`

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
0x180014e74  jmp     cs:__imp__CxxThrowException
```

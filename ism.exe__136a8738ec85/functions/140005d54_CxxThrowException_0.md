# _CxxThrowException_0

- ea: `0x140005d54`
- end: `0x140005d5a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400048e0`
- `0x140005390`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140005d54`

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
0x140005d54  jmp     cs:__imp__CxxThrowException
```

# _CxxThrowException_0

- ea: `0x14000280e`
- end: `0x140002814`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400025d0`
- `0x140003580`
- `0x14000c69b`
- `0x14000c70f`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x14000280e`

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
0x14000280e  jmp     cs:__imp__CxxThrowException
```

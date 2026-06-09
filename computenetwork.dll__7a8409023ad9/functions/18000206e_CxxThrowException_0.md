# _CxxThrowException_0

- ea: `0x18000206e`
- end: `0x180002074`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f20`
- `0x18000662c`
- `0x1800068b0`
- `0x180006a00`
- `0x180007490`
- `0x18000b520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x18000206e`

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
0x18000206e  jmp     cs:__imp__CxxThrowException
```

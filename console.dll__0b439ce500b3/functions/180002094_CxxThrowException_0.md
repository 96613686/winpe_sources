# _CxxThrowException_0

- ea: `0x180002094`
- end: `0x18000209a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f00`
- `0x180001f28`
- `0x1800054f4`
- `0x1800056d0`
- `0x180005870`
- `0x180005fe0`
- `0x18000d9d4`
- `0x18000eaf0`
- `0x180014ee4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002094`

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
0x180002094  jmp     cs:__imp__CxxThrowException
```

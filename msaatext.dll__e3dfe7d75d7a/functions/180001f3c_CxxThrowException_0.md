# _CxxThrowException_0

- ea: `0x180001f3c`
- end: `0x180001f42`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180001518`
- `0x180001540`
- `0x18000156c`
- `0x180012f48`
- `0x180012fc0`
- `0x180013044`
- `0x18001306a`
- `0x180013093`
- `0x1800130b0`
- `0x180013102`
- `0x180013854`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001f3c`

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
0x180001f3c  jmp     cs:__imp__CxxThrowException
```

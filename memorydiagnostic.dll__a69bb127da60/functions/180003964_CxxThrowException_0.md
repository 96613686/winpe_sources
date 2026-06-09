# _CxxThrowException_0

- ea: `0x180003964`
- end: `0x18000396a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800037c0`
- `0x18000ef48`
- `0x180010830`
- `0x180010980`
- `0x180013970`
- `0x1800156a0`
- `0x18001f650`
- `0x18001f680`
- `0x18001ff50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180003964`

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
0x180003964  jmp     cs:__imp__CxxThrowException
```

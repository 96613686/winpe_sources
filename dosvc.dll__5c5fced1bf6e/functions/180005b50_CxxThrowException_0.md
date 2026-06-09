# _CxxThrowException_0

- ea: `0x180005b50`
- end: `0x180005b56`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012a0`
- `0x180001380`
- `0x180004488`
- `0x1800059d4`
- `0x1800059fc`
- `0x1800079f0`
- `0x1800080e0`
- `0x180009f40`
- `0x18000a0cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180005b50`

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
0x180005b50  jmp     cs:__imp__CxxThrowException
```

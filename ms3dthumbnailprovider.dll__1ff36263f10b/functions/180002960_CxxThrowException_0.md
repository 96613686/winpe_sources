# _CxxThrowException_0

- ea: `0x180002960`
- end: `0x180002966`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800027d8`
- `0x180008350`
- `0x180009500`
- `0x1800099d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002960`

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
0x180002960  jmp     cs:__imp__CxxThrowException
```

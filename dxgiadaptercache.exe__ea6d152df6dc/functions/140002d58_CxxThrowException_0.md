# _CxxThrowException_0

- ea: `0x140002d58`
- end: `0x140002d5e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1400028c8`
- `0x14000b174`
- `0x14000c730`
- `0x14000c880`
- `0x14000de20`
- `0x1400103f0`
- `0x140010418`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140002d58`

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
0x140002d58  jmp     cs:__imp__CxxThrowException
```

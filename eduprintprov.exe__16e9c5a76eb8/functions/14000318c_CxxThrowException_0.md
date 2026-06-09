# _CxxThrowException_0

- ea: `0x14000318c`
- end: `0x140003192`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140002f88`
- `0x1400096f0`
- `0x14000a660`
- `0x14000b940`
- `0x14000f304`
- `0x140012ff8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x14000318c`

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
0x14000318c  jmp     cs:__imp__CxxThrowException
```

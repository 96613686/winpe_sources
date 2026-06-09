# _CxxThrowException_0

- ea: `0x1400027bc`
- end: `0x1400027c2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x140002228`
- `0x140002250`
- `0x14000227c`
- `0x14000b050`
- `0x14000b9c0`
- `0x14001995b`
- `0x140019981`
- `0x140019a0b`
- `0x140019a31`
- `0x140019a72`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1400027bc`

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
0x1400027bc  jmp     cs:__imp__CxxThrowException
```

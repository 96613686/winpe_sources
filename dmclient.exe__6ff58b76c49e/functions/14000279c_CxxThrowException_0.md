# _CxxThrowException_0

- ea: `0x14000279c`
- end: `0x1400027a2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x140002208`
- `0x140002230`
- `0x14000225c`
- `0x14000ad60`
- `0x14000b670`
- `0x140018b2a`
- `0x140018b50`
- `0x140018bda`
- `0x140018c00`
- `0x140018c41`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x14000279c`

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
0x14000279c  jmp     cs:__imp__CxxThrowException
```

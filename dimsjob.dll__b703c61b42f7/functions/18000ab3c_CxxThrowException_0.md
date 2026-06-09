# _CxxThrowException_0

- ea: `0x18000ab3c`
- end: `0x18000ab42`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180001190`
- `0x180001b20`
- `0x180001c10`
- `0x180002670`
- `0x180002860`
- `0x180003c8c`
- `0x180003e88`
- `0x180003f10`
- `0x18000408c`
- `0x18000412c`
- `0x180008760`
- `0x1800092a0`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000ab3c`

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
0x18000ab3c  jmp     cs:__imp__CxxThrowException
```

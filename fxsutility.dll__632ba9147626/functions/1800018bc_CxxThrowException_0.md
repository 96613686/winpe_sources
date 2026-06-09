# _CxxThrowException_0

- ea: `0x1800018bc`
- end: `0x1800018c2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001284`
- `0x180001330`
- `0x18000bba0`
- `0x18000c6e0`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800018bc`

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
0x1800018bc  jmp     cs:__imp__CxxThrowException
```

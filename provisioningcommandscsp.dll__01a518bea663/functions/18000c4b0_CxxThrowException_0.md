# _CxxThrowException_0

- ea: `0x18000c4b0`
- end: `0x18000c4b6`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800049a0`
- `0x180004c20`
- `0x180004d70`
- `0x180005620`
- `0x18000cde7`
- `0x18000ce60`
- `0x18000ce86`
- `0x18000d077`
- `0x18000d372`
- `0x18000d3ea`
- `0x18000d59e`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000c4b0`

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
0x18000c4b0  jmp     cs:__imp__CxxThrowException
```

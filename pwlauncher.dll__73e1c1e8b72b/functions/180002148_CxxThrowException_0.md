# _CxxThrowException_0

- ea: `0x180002148`
- end: `0x18000214e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016e4`
- `0x18000374c`
- `0x180008e20`
- `0x18000946c`
- `0x180009f4c`
- `0x18000b180`
- `0x18000b3ac`
- `0x18000b5d8`
- `0x18000c60c`
- `0x18000c6bc`
- `0x18000cd50`
- `0x18000d130`
- `0x18000d2c0`
- `0x18000d3d0`
- `0x18000e948`
- `0x18000ec5c`
- `0x18000ee48`
- `0x18000ef8c`
- `0x18000f288`
- `0x18000f658`
- `0x18000f880`
- `0x18000fa50`
- `0x18000fb3c`
- `0x18001086f`
- `0x1800108a6`
- `0x180010917`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180002148`

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
0x180002148  jmp     cs:__imp__CxxThrowException
```

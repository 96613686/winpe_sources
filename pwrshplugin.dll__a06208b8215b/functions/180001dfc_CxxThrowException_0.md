# _CxxThrowException_0

- ea: `0x180001dfc`
- end: `0x180001e02`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180001238`
- `0x180001260`
- `0x18000128c`
- `0x180002170`
- `0x180002fac`
- `0x180003158`
- `0x180003a68`
- `0x180003f0c`
- `0x180004370`
- `0x1800063f0`
- `0x1800093d4`
- `0x180009abe`
- `0x180009b45`
- `0x180009dc8`
- `0x180009f24`
- `0x180009fba`
- `0x18000a014`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001dfc`

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
0x180001dfc  jmp     cs:__imp__CxxThrowException
```

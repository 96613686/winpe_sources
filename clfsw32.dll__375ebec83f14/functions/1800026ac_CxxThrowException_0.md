# _CxxThrowException_0

- ea: `0x1800026ac`
- end: `0x1800026b2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002028`
- `0x180002068`
- `0x180002094`
- `0x18001525a`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800026ac`

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
0x1800026ac  jmp     cs:__imp__CxxThrowException
```

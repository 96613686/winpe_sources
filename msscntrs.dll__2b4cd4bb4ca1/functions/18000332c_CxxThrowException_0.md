# _CxxThrowException_0

- ea: `0x18000332c`
- end: `0x180003332`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f18`
- `0x1800077ac`
- `0x1800089a0`
- `0x180008af0`
- `0x180008b60`
- `0x180009ae0`
- `0x18000a410`
- `0x18000a78c`
- `0x18000c434`
- `0x180012268`
- `0x180012394`
- `0x1800123f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x18000332c`

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
0x18000332c  jmp     cs:__imp__CxxThrowException
```

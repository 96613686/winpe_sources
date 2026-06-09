# _CxxThrowException_0

- ea: `0x180003380`
- end: `0x180003386`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180003024`
- `0x18000f820`
- `0x180011250`
- `0x180011350`
- `0x180014570`
- `0x1800163ac`
- `0x180020b80`
- `0x180020bb0`
- `0x180021680`
- `0x180022147`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180003380`

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
0x180003380  jmp     cs:__imp__CxxThrowException
```

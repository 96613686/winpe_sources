# _CxxThrowException_0

- ea: `0x18001ce34`
- end: `0x18001ce3a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `43`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a50`
- `0x180005510`
- `0x180006ec0`
- `0x180007b58`
- `0x180008aac`
- `0x180009b34`
- `0x18000b52c`
- `0x18000c8c4`
- `0x18000d800`
- `0x18000fc54`
- `0x18000ff40`
- `0x18001003c`
- `0x180010c70`
- `0x180010f20`
- `0x180011208`
- `0x180011c9c`
- `0x180011d08`
- `0x180011ed4`
- `0x180011f58`
- `0x180011fdc`
- `0x180012064`
- `0x1800121a4`
- `0x18001270c`
- `0x180014850`
- `0x180014980`
- `0x180014b80`
- `0x1800151c0`
- `0x180015440`
- `0x180015694`
- `0x18001a09c`
- `0x18001a1f4`
- `0x18001a30c`
- `0x18001a49c`
- `0x18001a888`
- `0x18001b8fc`
- `0x18001d4aa`
- `0x18001d4d4`
- `0x18001d510`
- `0x18001d75c`
- `0x18001d79f`
- `0x18001d7de`
- `0x18001d88e`
- `0x18001e18e`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x18001ce34`

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
0x18001ce34  jmp     cs:__imp__CxxThrowException
```

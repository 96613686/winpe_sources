# SetIsSideloadingEnabled

- ea: `0x180007550`
- end: `0x180007556`
- name: `SetIsSideloadingEnabled`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!SetIsSideloadingEnabled` at `0x180007550`

## pseudocode

```c
// attributes: thunk
__int64 SetIsSideloadingEnabled()
{
  return __imp_SetIsSideloadingEnabled();
}

```

## disassembly

```asm
0x180007550  jmp     cs:__imp_SetIsSideloadingEnabled
```

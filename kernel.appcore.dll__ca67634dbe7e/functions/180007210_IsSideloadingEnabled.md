# IsSideloadingEnabled

- ea: `0x180007210`
- end: `0x180007216`
- name: `IsSideloadingEnabled`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!IsSideloadingEnabled` at `0x180007210`

## pseudocode

```c
// attributes: thunk
__int64 IsSideloadingEnabled()
{
  return __imp_IsSideloadingEnabled();
}

```

## disassembly

```asm
0x180007210  jmp     cs:__imp_IsSideloadingEnabled
```

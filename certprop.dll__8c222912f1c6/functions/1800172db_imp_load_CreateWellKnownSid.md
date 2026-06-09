# __imp_load_CreateWellKnownSid

- ea: `0x1800172db`
- end: `0x1800172e7`
- name: `__imp_load_CreateWellKnownSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180017196`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x1800172db`

## pseudocode

```c
__int64 load_CreateWellKnownSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800172db  lea     rax, __imp_CreateWellKnownSid
0x1800172e2  jmp     __tailMerge_advapi32_dll
```

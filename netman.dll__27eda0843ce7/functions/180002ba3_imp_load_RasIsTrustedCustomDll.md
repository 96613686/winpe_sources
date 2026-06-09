# __imp_load_RasIsTrustedCustomDll

- ea: `0x180002ba3`
- end: `0x180002baf`
- name: `__imp_load_RasIsTrustedCustomDll`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b12`

## import_xrefs

- `rasman!RasIsTrustedCustomDll` at `0x180002ba3`

## pseudocode

```c
__int64 load_RasIsTrustedCustomDll()
{
  return _tailMerge_rasman_dll();
}

```

## disassembly

```asm
0x180002ba3  lea     rax, __imp_RasIsTrustedCustomDll
0x180002baa  jmp     __tailMerge_rasman_dll
```

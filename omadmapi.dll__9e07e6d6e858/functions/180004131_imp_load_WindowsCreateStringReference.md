# __imp_load_WindowsCreateStringReference

- ea: `0x180004131`
- end: `0x18000413d`
- name: `__imp_load_WindowsCreateStringReference`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000408e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004131`

## pseudocode

```c
__int64 load_WindowsCreateStringReference()
{
  return _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll();
}

```

## disassembly

```asm
0x180004131  lea     rax, __imp_WindowsCreateStringReference
0x180004138  jmp     __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll
```

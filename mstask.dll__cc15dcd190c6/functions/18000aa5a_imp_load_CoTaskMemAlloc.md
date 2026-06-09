# __imp_load_CoTaskMemAlloc

- ea: `0x18000aa5a`
- end: `0x18000aa66`
- name: `__imp_load_CoTaskMemAlloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a9db`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aa5a`

## pseudocode

```c
__int64 load_CoTaskMemAlloc()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000aa5a  lea     rax, __imp_CoTaskMemAlloc
0x18000aa61  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```

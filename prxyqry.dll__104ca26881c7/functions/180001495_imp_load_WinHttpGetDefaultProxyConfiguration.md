# __imp_load_WinHttpGetDefaultProxyConfiguration

- ea: `0x180001495`
- end: `0x1800014a1`
- name: `__imp_load_WinHttpGetDefaultProxyConfiguration`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180001331`

## import_xrefs

- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180001495`

## pseudocode

```c
__int64 load_WinHttpGetDefaultProxyConfiguration()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001495  lea     rax, __imp_WinHttpGetDefaultProxyConfiguration
0x18000149c  jmp     __tailMerge_winhttp_dll
```

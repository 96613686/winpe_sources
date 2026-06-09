# __imp_load_CreateDXGIFactory1

- ea: `0x140002e31`
- end: `0x140002e3d`
- name: `__imp_load_CreateDXGIFactory1`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002db2`

## import_xrefs

- `dxgi!CreateDXGIFactory1` at `0x140002e31`

## pseudocode

```c
__int64 load_CreateDXGIFactory1()
{
  return _tailMerge_dxgi_dll();
}

```

## disassembly

```asm
0x140002e31  lea     rax, __imp_CreateDXGIFactory1
0x140002e38  jmp     __tailMerge_dxgi_dll
```

# __imp_load_D3D12CreateDevice

- ea: `0x140002f47`
- end: `0x140002f53`
- name: `__imp_load_D3D12CreateDevice`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002ec8`

## import_xrefs

- `d3d12!__imp_D3D12CreateDevice` at `0x140002f47`

## pseudocode

```c
__int64 load_D3D12CreateDevice()
{
  return _tailMerge_d3d12_dll();
}

```

## disassembly

```asm
0x140002f47  lea     rax, __imp_D3D12CreateDevice
0x140002f4e  jmp     __tailMerge_d3d12_dll
```

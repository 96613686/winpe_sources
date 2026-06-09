# __imp_load_D3D11CreateDevice

- ea: `0x14000311e`
- end: `0x14000312a`
- name: `__imp_load_D3D11CreateDevice`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000309f`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x14000311e`

## pseudocode

```c
__int64 load_D3D11CreateDevice()
{
  return _tailMerge_d3d11_dll();
}

```

## disassembly

```asm
0x14000311e  lea     rax, __imp_D3D11CreateDevice
0x140003125  jmp     __tailMerge_d3d11_dll
```

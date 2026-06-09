# __imp_load_D3DKMTOpenAdapterFromLuid

- ea: `0x140003081`
- end: `0x14000308d`
- name: `__imp_load_D3DKMTOpenAdapterFromLuid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003002`

## import_xrefs

- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTOpenAdapterFromLuid` at `0x140003081`

## pseudocode

```c
__int64 load_D3DKMTOpenAdapterFromLuid()
{
  return _tailMerge_api_ms_win_dx_d3dkmt_l1_1_1_dll();
}

```

## disassembly

```asm
0x140003081  lea     rax, __imp_D3DKMTOpenAdapterFromLuid
0x140003088  jmp     __tailMerge_api_ms_win_dx_d3dkmt_l1_1_1_dll
```

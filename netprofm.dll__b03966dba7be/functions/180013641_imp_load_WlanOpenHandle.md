# __imp_load_WlanOpenHandle

- ea: `0x180013641`
- end: `0x18001364d`
- name: `__imp_load_WlanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001358c`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x180013641`

## pseudocode

```c
__int64 load_WlanOpenHandle()
{
  return _tailMerge_ext_ms_win_networking_wlanapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x180013641  lea     rax, __imp_WlanOpenHandle
0x180013648  jmp     __tailMerge_ext_ms_win_networking_wlanapi_l1_1_0_dll
```

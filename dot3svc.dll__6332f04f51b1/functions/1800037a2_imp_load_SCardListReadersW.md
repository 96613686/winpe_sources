# __imp_load_SCardListReadersW

- ea: `0x1800037a2`
- end: `0x1800037ae`
- name: `__imp_load_SCardListReadersW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003723`

## import_xrefs

- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x1800037a2`

## pseudocode

```c
__int64 load_SCardListReadersW()
{
  return _tailMerge_ext_ms_win_wlan_scard_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800037a2  lea     rax, __imp_SCardListReadersW
0x1800037a9  jmp     __tailMerge_ext_ms_win_wlan_scard_l1_1_0_dll
```

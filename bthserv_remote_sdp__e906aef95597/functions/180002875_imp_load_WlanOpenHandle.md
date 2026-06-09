# __imp_load_WlanOpenHandle

- ea: `0x180002875`
- end: `0x180002881`
- name: `__imp_load_WlanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800027f6`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x180002875`

## pseudocode

```c
__int64 load_WlanOpenHandle()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x180002875  lea     rax, __imp_WlanOpenHandle
0x18000287c  jmp     __tailMerge_wlanapi_dll
```

# __imp_load_WlanOpenHandle

- ea: `0x1800038fd`
- end: `0x180003909`
- name: `__imp_load_WlanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003848`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x1800038fd`

## pseudocode

```c
__int64 load_WlanOpenHandle()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x1800038fd  lea     rax, __imp_WlanOpenHandle
0x180003904  jmp     __tailMerge_wlanapi_dll
```

# __imp_load_WlanOpenHandle

- ea: `0x180008ad7`
- end: `0x180008ae3`
- name: `__imp_load_WlanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008a58`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x180008ad7`

## pseudocode

```c
__int64 load_WlanOpenHandle()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x180008ad7  lea     rax, __imp_WlanOpenHandle
0x180008ade  jmp     __tailMerge_wlanapi_dll
```

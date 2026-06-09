# MupGetUncCacheHostPrefixTable

- ea: `0x1400024ec`
- end: `0x1400024f4`
- name: `MupGetUncCacheHostPrefixTable`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14001dacc`
- `0x14001dca0`

## pseudocode

```c
PVOID *MupGetUncCacheHostPrefixTable()
{
  return &WPP_MAIN_CB.Reserved + 1;
}

```

## disassembly

```asm
0x1400024ec  lea     rax, WPP_MAIN_CB+148h
0x1400024f3  retn
```

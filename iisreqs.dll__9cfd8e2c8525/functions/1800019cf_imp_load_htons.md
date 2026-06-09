# __imp_load_htons

- ea: `0x1800019cf`
- end: `0x1800019db`
- name: `__imp_load_htons`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001950`

## import_xrefs

- `WS2_32!__imp_htons` at `0x1800019cf`

## pseudocode

```c
__int64 __fastcall load_htons(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_ws2_32_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800019cf  lea     rax, __imp_htons
0x1800019d6  jmp     __tailMerge_ws2_32_dll
```

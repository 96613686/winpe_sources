# __imp_load_getnameinfo

- ea: `0x1800019e1`
- end: `0x1800019ed`
- name: `__imp_load_getnameinfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001950`

## import_xrefs

- `WS2_32!getnameinfo` at `0x1800019e1`

## pseudocode

```c
__int64 __fastcall load_getnameinfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_ws2_32_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800019e1  lea     rax, __imp_getnameinfo
0x1800019e8  jmp     __tailMerge_ws2_32_dll
```

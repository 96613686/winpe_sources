# __imp_load_WinHttpOpen

- ea: `0x180001483`
- end: `0x18000148f`
- name: `__imp_load_WinHttpOpen`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001331`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x180001483`

## pseudocode

```c
__int64 __fastcall load_WinHttpOpen(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_winhttp_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001483  lea     rax, __imp_WinHttpOpen
0x18000148a  jmp     __tailMerge_winhttp_dll
```

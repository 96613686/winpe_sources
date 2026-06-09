# __imp_load_WinHttpCloseHandle

- ea: `0x1800013d4`
- end: `0x1800013e0`
- name: `__imp_load_WinHttpCloseHandle`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001331`

## import_xrefs

- `WINHTTP!WinHttpCloseHandle` at `0x1800013d4`

## pseudocode

```c
__int64 __fastcall load_WinHttpCloseHandle(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_winhttp_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800013d4  lea     rax, __imp_WinHttpCloseHandle
0x1800013db  jmp     __tailMerge_winhttp_dll
```

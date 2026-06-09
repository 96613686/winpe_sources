# __imp_load_WinHttpOpenRequest

- ea: `0x18001c41f`
- end: `0x18001c42b`
- name: `__imp_load_WinHttpOpenRequest`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c2fe`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x18001c41f`

## pseudocode

```c
__int64 load_WinHttpOpenRequest()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x18001c41f  lea     rax, __imp_WinHttpOpenRequest
0x18001c426  jmp     __tailMerge_winhttp_dll
```

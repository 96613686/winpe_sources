# __imp_load_WinHttpOpenRequest

- ea: `0x18000aee0`
- end: `0x18000aeec`
- name: `__imp_load_WinHttpOpenRequest`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ad9b`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x18000aee0`

## pseudocode

```c
__int64 load_WinHttpOpenRequest()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x18000aee0  lea     rax, __imp_WinHttpOpenRequest
0x18000aee7  jmp     __tailMerge_winhttp_dll
```

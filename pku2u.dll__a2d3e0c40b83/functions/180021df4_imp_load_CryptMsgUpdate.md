# __imp_load_CryptMsgUpdate

- ea: `0x180021df4`
- end: `0x180021e00`
- name: `__imp_load_CryptMsgUpdate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180021af7`

## import_xrefs

- `CRYPT32!CryptMsgUpdate` at `0x180021df4`

## pseudocode

```c
__int64 load_CryptMsgUpdate()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180021df4  lea     rax, __imp_CryptMsgUpdate
0x180021dfb  jmp     __tailMerge_crypt32_dll
```

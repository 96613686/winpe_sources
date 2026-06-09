# sub_1800CDE3A

- ea: `0x1800cde3a`
- end: `0x1800cde46`
- name: `sub_1800CDE3A`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800cd43e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cde3a`

## pseudocode

```c
__int64 sub_1800CDE3A()
{
  return sub_1800CD43E();
}

```

## disassembly

```asm
0x1800cde3a  lea     rax, CoTaskMemFree
0x1800cde41  jmp     sub_1800CD43E
```

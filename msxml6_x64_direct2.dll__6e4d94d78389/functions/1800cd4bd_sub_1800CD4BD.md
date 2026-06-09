# sub_1800CD4BD

- ea: `0x1800cd4bd`
- end: `0x1800cd4c9`
- name: `sub_1800CD4BD`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800cd43e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cd4bd`

## pseudocode

```c
__int64 sub_1800CD4BD()
{
  return sub_1800CD43E();
}

```

## disassembly

```asm
0x1800cd4bd  lea     rax, CoTaskMemAlloc
0x1800cd4c4  jmp     sub_1800CD43E
```

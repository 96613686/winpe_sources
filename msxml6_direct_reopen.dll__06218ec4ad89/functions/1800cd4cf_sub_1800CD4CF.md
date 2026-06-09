# sub_1800CD4CF

- ea: `0x1800cd4cf`
- end: `0x1800cd4db`
- name: `sub_1800CD4CF`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800cd43e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800cd4cf`

## pseudocode

```c
__int64 sub_1800CD4CF()
{
  return sub_1800CD43E();
}

```

## disassembly

```asm
0x1800cd4cf  lea     rax, CoCreateFreeThreadedMarshaler
0x1800cd4d6  jmp     sub_1800CD43E
```

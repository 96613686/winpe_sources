# __scrt_initialize_type_info(void)

- ea: `0x1400016f4`
- end: `0x140001702`
- name: `?__scrt_initialize_type_info@@YAXXZ`
- size: `14`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010e0`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x1400016fb`

## pseudocode

```c
void __scrt_initialize_type_info(void)
{
  InitializeSListHead(&__type_info_root_node);
}

```

## disassembly

```asm
0x1400016f4  lea     rcx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x1400016fb  jmp     cs:__imp_InitializeSListHead
```

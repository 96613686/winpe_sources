# __scrt_initialize_type_info(void)

- ea: `0x1400016b4`
- end: `0x1400016c2`
- name: `?__scrt_initialize_type_info@@YAXXZ`
- size: `14`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001090`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x1400016bb`

## pseudocode

```c
void __scrt_initialize_type_info(void)
{
  InitializeSListHead((PSLIST_HEADER)&__type_info_root_node);
}

```

## disassembly

```asm
0x1400016b4  lea     rcx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x1400016bb  jmp     cs:__imp_InitializeSListHead
```

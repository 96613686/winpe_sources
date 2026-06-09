# _dynamic_atexit_destructor_for__g_LibraryCache__

- ea: `0x18004b800`
- end: `0x18004b80e`
- name: `_dynamic_atexit_destructor_for__g_LibraryCache__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b807`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_LibraryCache__()
{
  DeleteCriticalSection(&g_LibraryCache);
}

```

## disassembly

```asm
0x18004b800  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; LibraryCache g_LibraryCache
0x18004b807  jmp     cs:__imp_DeleteCriticalSection
```

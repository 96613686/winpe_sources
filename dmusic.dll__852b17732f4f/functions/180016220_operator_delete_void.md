# operator delete(void *)

- ea: `0x180016220`
- end: `0x180016227`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800012c4`
- `0x180001aa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016220`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180016220  jmp     cs:__imp_free
```

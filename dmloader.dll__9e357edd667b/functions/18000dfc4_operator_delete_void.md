# operator delete(void *)

- ea: `0x18000dfc4`
- end: `0x18000dfcb`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800019a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dfc4`

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
0x18000dfc4  jmp     cs:__imp_free
```

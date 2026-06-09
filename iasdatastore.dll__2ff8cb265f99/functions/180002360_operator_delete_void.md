# operator delete(void *)

- ea: `0x180002360`
- end: `0x180002367`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800016a0`
- `0x180001ff0`
- `0x18000e1cc`
- `0x18000e1de`
- `0x18000e1f0`
- `0x18000e684`
- `0x18000e696`
- `0x18000e6a8`
- `0x18000e764`
- `0x18000eaa5`

## import_xrefs

- `msvcrt!free` at `0x180002360`

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
0x180002360  jmp     cs:__imp_free
```

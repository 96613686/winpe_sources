# operator delete(void *)

- ea: `0x1800021c0`
- end: `0x1800021c5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002120`
- `0x18000214c`
- `0x180006594`
- `0x18001df18`

## callees

- `0x180001f54`

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
0x1800021c0  jmp     free
```

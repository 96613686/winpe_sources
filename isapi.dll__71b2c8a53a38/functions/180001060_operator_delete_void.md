# operator delete(void *)

- ea: `0x180001060`
- end: `0x180001065`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001960`
- `0x180001d60`
- `0x180001d8c`
- `0x1800032b0`
- `0x1800032c0`
- `0x1800050d4`
- `0x18000c490`
- `0x18000c5e8`
- `0x180010770`
- `0x180010b10`
- `0x180012150`

## callees

- `0x180001726`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001060  jmp     free_0
```

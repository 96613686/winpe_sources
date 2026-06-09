# operator delete(void *)

- ea: `0x18000b3f4`
- end: `0x18000b3f9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800026a0`
- `0x180004af0`
- `0x180008ff0`
- `0x18000b7e0`
- `0x18000b7f0`

## callees

- `0x18000be54`

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
0x18000b3f4  jmp     free
```

# operator delete(void *)

- ea: `0x180001f38`
- end: `0x180001f3d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001f44`
- `0x180002810`
- `0x180002b98`
- `0x180002e80`

## callees

- `0x180002924`

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
0x180001f38  jmp     free
```

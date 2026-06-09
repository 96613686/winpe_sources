# operator delete(void *)

- ea: `0x1800019e0`
- end: `0x1800019e5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001980`
- `0x180001990`

## callees

- `0x180002064`

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
0x1800019e0  jmp     free
```

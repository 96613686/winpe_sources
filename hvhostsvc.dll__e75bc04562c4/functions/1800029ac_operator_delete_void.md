# operator delete(void *)

- ea: `0x1800029ac`
- end: `0x1800029b1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800024d0`
- `0x1800024e0`

## callees

- `0x180002ac4`

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
0x1800029ac  jmp     free
```

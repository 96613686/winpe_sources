# operator delete(void *)

- ea: `0x1800026cc`
- end: `0x1800026d1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a350`

## callees

- `0x1800025f2`

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
0x1800026cc  jmp     free
```

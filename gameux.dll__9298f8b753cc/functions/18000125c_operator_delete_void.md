# operator delete(void *)

- ea: `0x18000125c`
- end: `0x180001261`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ce0`
- `0x180001d20`
- `0x180001d58`
- `0x180002690`
- `0x1800026d0`
- `0x180002710`
- `0x180002ce0`
- `0x180002d44`

## callees

- `0x180001855`

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
0x18000125c  jmp     free_0
```

# operator delete[](void *)

- ea: `0x1800019bc`
- end: `0x1800019c1`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800056c8`
- `0x18000678c`
- `0x180009970`
- `0x18000a9e8`
- `0x18000bae8`
- `0x18000c33c`
- `0x18000e104`

## callees

- `0x1800019b0`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1800019bc  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

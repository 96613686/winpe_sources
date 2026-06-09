# operator delete(void *)

- ea: `0x1400012d0`
- end: `0x1400012d5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001ef0`
- `0x140002010`
- `0x140004cfc`
- `0x1400053f0`
- `0x140005430`
- `0x140005a4c`
- `0x140005d0c`
- `0x140005fd0`
- `0x14000712c`

## callees

- `0x1400016a6`

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
0x1400012d0  jmp     free_0
```

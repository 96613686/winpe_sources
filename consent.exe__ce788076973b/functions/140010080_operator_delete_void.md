# operator delete(void *)

- ea: `0x140010080`
- end: `0x140010085`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140009280`
- `0x14000a7b0`
- `0x14000cfdc`
- `0x14000de20`
- `0x14000f7b0`
- `0x14000fb20`
- `0x140010570`
- `0x1400119c0`
- `0x140011a00`
- `0x140013cec`
- `0x140013fe0`
- `0x140019b34`

## callees

- `0x1400107c9`

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
0x140010080  jmp     free_0
```

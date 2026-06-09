# operator delete(void *,unsigned __int64)

- ea: `0x18000b7e0`
- end: `0x18000b7e5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800025f0`
- `0x1800028d0`
- `0x180002a60`
- `0x180005de4`
- `0x180006e2c`
- `0x180008b98`
- `0x18000aa60`
- `0x18000c8c0`
- `0x18000c900`
- `0x18000c940`
- `0x18000c980`
- `0x18000e800`
- `0x18000e840`
- `0x18000fd20`
- `0x18000fd50`

## callees

- `0x18000b3f4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18000b7e0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

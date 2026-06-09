# operator delete(void *)

- ea: `0x180001144`
- end: `0x180001149`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `30`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001150`
- `0x180001a50`
- `0x1800020e0`
- `0x180002140`
- `0x180002d30`
- `0x180004270`
- `0x180004714`
- `0x180004784`
- `0x180004970`
- `0x1800049d0`
- `0x180007f70`
- `0x180007ff0`
- `0x180008030`
- `0x1800092d0`
- `0x18000b400`
- `0x18000d660`
- `0x18000e958`
- `0x1800107a0`
- `0x1800108a8`
- `0x1800109d0`
- `0x180010db8`
- `0x180010e98`
- `0x1800110a8`
- `0x180011970`
- `0x1800119b0`
- `0x180011a00`
- `0x1800150f8`
- `0x1800151a0`
- `0x180015260`
- `0x1800170f0`

## callees

- `0x180001a3c`

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
0x180001144  jmp     free_0
```

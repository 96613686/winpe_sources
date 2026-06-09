# operator delete(void *)

- ea: `0x1800012d0`
- end: `0x1800012d5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800018e0`
- `0x180002058`
- `0x18000212c`
- `0x180002b80`
- `0x180002c50`
- `0x180004360`
- `0x1800043c0`
- `0x180004500`
- `0x180004bf0`
- `0x1800087c0`
- `0x1800087f0`
- `0x18000dc34`
- `0x18000fb20`
- `0x18000fb70`
- `0x18000fbd0`
- `0x18000fc10`
- `0x18000fc3c`
- `0x180010600`
- `0x180010650`
- `0x180013b00`

## callees

- `0x18000184c`

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
0x1800012d0  jmp     free_0
```

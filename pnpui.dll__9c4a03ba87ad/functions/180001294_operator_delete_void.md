# operator delete(void *)

- ea: `0x180001294`
- end: `0x180001299`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800025cc`
- `0x180002620`
- `0x180002dd0`
- `0x180004cf0`
- `0x180005fd4`
- `0x180006700`
- `0x180007630`
- `0x18000b300`
- `0x18000b340`

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
0x180001294  jmp     free_0
```

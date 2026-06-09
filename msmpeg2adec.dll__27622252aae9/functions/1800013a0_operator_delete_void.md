# operator delete(void *)

- ea: `0x1800013a0`
- end: `0x1800013a5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `21`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001b80`
- `0x180001b90`
- `0x18000a140`
- `0x18000aa40`
- `0x18000aed0`
- `0x18000b900`
- `0x1800110a0`
- `0x180018b70`
- `0x18001d6e0`
- `0x1800261f4`
- `0x180026238`
- `0x180027270`
- `0x180033080`
- `0x180059f00`
- `0x18005a530`
- `0x18005c430`
- `0x18005eaa0`
- `0x180060ca0`
- `0x180064740`
- `0x180066d20`
- `0x180088cf0`

## callees

- `0x180002160`

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
0x1800013a0  jmp     free
```

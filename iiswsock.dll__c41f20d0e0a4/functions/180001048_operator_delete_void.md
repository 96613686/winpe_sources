# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002de0`
- `0x1800032c0`
- `0x180003300`
- `0x180003370`
- `0x1800035b0`
- `0x180003d60`
- `0x180003f00`
- `0x180004140`
- `0x180004170`
- `0x18000477c`
- `0x180004ad4`
- `0x180004bac`
- `0x180004ebc`
- `0x180005070`
- `0x1800051c0`
- `0x1800052d0`
- `0x180005394`
- `0x180005568`
- `0x1800059f0`
- `0x1800079a0`
- `0x1800079b0`
- `0x180007e70`
- `0x180008080`

## callees

- `0x180001532`

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
0x180001048  jmp     free_0
```

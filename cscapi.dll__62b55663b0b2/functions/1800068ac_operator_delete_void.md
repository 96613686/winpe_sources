# operator delete(void *)

- ea: `0x1800068ac`
- end: `0x1800068b1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005ed0`
- `0x180006d90`
- `0x1800082e0`
- `0x180008c00`

## callees

- `0x180006dde`

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
0x1800068ac  jmp     free_0
```

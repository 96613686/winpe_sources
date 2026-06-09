# operator delete(void *)

- ea: `0x180001008`
- end: `0x18000100d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800069b0`
- `0x180006ac0`
- `0x180006bc0`
- `0x180006cd0`
- `0x180006dd0`
- `0x180006ed0`
- `0x180006fd0`
- `0x1800072d0`
- `0x180007370`
- `0x180007410`
- `0x1800074b0`
- `0x180007550`
- `0x1800075f0`
- `0x180007690`

## callees

- `0x180001548`

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
0x180001008  jmp     free_0
```

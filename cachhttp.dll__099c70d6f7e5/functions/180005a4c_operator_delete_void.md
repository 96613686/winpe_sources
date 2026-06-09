# operator delete(void *)

- ea: `0x180005a4c`
- end: `0x180005a51`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001010`
- `0x1800011b8`
- `0x180002670`
- `0x1800039d0`
- `0x1800052b4`
- `0x180006390`
- `0x1800063bc`
- `0x18000657c`
- `0x1800065c8`
- `0x1800072a0`
- `0x1800072b0`
- `0x180007620`
- `0x1800078b4`
- `0x1800078e0`

## callees

- `0x180005f26`

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
0x180005a4c  jmp     free_0
```

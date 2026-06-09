# operator delete(void *,unsigned __int64)

- ea: `0x180001a94`
- end: `0x180001a99`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002a9c`
- `0x180002fd0`
- `0x18000300c`
- `0x180003050`
- `0x180003098`
- `0x180003608`
- `0x180003e90`
- `0x180004bec`
- `0x180004e80`
- `0x180007de0`
- `0x180007e20`
- `0x180007e60`
- `0x180007e9c`
- `0x18000f680`
- `0x18000f810`
- `0x180010450`
- `0x180011510`

## callees

- `0x180001a54`

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
0x180001a94  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

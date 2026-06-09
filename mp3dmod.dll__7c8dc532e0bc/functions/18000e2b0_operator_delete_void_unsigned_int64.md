# operator delete(void *,unsigned __int64)

- ea: `0x18000e2b0`
- end: `0x18000e2b5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ae90`
- `0x18000be3c`
- `0x18000f060`
- `0x18000fb80`

## callees

- `0x18000e308`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18000e2b0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

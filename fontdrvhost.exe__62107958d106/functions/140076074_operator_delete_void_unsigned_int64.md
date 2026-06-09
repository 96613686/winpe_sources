# operator delete(void *,unsigned __int64)

- ea: `0x140076074`
- end: `0x140076079`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400743ac`
- `0x140077f80`
- `0x140077fc0`
- `0x140078000`
- `0x140078040`
- `0x14009273c`
- `0x140093150`
- `0x140093190`

## callees

- `0x140076620`

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
0x140076074  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

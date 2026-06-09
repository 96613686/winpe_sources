# operator delete(void *,unsigned __int64)

- ea: `0x1800017c4`
- end: `0x1800017c9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `62`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002960`
- `0x1800029a0`
- `0x180003c80`
- `0x180003cc0`
- `0x180003cfc`
- `0x180003d30`
- `0x180003d70`
- `0x180003db0`
- `0x180006370`
- `0x1800063b0`
- `0x1800063f0`
- `0x180006430`
- `0x180006470`
- `0x1800064c0`
- `0x18000ef60`
- `0x18000efa0`
- `0x180010eb0`
- `0x180011290`
- `0x1800112d0`
- `0x180011ff0`
- `0x1800121b0`
- `0x180012910`
- `0x180012950`
- `0x180012990`
- `0x180013c20`
- `0x180013cb0`
- `0x180013ce0`
- `0x180015160`
- `0x1800159b8`
- `0x180016a7c`
- `0x180016ca0`
- `0x180017d80`
- `0x18001e870`
- `0x180020548`
- `0x180021be0`
- `0x18002278c`
- `0x180023190`
- `0x1800231d0`
- `0x180023210`
- `0x1800258a0`
- `0x1800258e0`
- `0x180028050`
- `0x180028090`
- `0x1800296c0`
- `0x18002b8a0`
- `0x18002f634`
- `0x18002f6a1`
- `0x1800313e1`
- `0x180031404`
- `0x1800314a9`

## callees

- `0x180003c3c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x1800017c4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

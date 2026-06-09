# operator delete(void *,unsigned __int64)

- ea: `0x1400029c4`
- end: `0x1400029c9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400041b0`
- `0x1400041f0`
- `0x1400058e0`
- `0x1400071c0`
- `0x140007200`
- `0x140007234`
- `0x14000b990`
- `0x14000b9d0`
- `0x140015fc8`
- `0x1400177e4`

## callees

- `0x1400070e8`

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
0x1400029c4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

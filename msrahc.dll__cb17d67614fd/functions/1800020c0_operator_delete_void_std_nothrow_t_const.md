# operator delete[](void *,std::nothrow_t const &)

- ea: `0x1800020c0`
- end: `0x1800020c5`
- name: `??_V@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001ac99`
- `0x18001acd0`

## callees

- `0x180001b16`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *a1, const struct std::nothrow_t *a2)
{
  ??_V@YAXPEAX@Z_0(a1);
}

```

## disassembly

```asm
0x1800020c0  jmp     ??_V@YAXPEAX@Z_0; operator delete[](void *)
```

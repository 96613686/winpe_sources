# operator delete[](void *,unsigned __int64)

- ea: `0x180024de0`
- end: `0x180024de5`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003e5ec`
- `0x180048a84`
- `0x18004e4a4`
- `0x18006f22a`

## callees

- `0x1800245f0`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *a1, const struct std::nothrow_t *a2)
{
  operator delete(a1, a2);
}

```

## disassembly

```asm
0x180024de0  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```

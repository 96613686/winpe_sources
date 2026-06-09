# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001f5c`
- end: `0x180001f61`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180013dd1`

## callees

- `0x180001a46`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z_0(a1);
}

```

## disassembly

```asm
0x180001f5c  jmp     ??3@YAXPEAX@Z_0; operator delete(void *)
```

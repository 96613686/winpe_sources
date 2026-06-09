# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x1800018a4`
- end: `0x1800018a9`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180009630`
- `0x180009d40`
- `0x180009fe0`
- `0x18000cba0`
- `0x180010bdc`
- `0x1800136a0`

## callees

- `0x18000187c`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](size_t a1, const struct std::nothrow_t *a2)
{
  return operator new(a1, a2);
}

```

## disassembly

```asm
0x1800018a4  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```

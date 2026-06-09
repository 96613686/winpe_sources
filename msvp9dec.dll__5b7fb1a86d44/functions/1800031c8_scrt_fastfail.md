# __scrt_fastfail

- ea: `0x1800031c8`
- end: `0x1800031cc`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002998`
- `0x180002a98`
- `0x180002eb4`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800031c8  mov     ecx, ecx
0x1800031ca  int     29h; Win8: RtlFailFast(ecx)
```

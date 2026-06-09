# __scrt_fastfail

- ea: `0x140001880`
- end: `0x140001884`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011b0`
- `0x1400012a0`
- `0x14000153c`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x140001880  mov     ecx, ecx
0x140001882  int     29h; Win8: RtlFailFast(ecx)
```

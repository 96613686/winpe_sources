# __scrt_fastfail

- ea: `0x180002144`
- end: `0x180002148`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018c8`
- `0x1800019c8`
- `0x180001e04`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180002144  mov     ecx, ecx
0x180002146  int     29h; Win8: RtlFailFast(ecx)
```

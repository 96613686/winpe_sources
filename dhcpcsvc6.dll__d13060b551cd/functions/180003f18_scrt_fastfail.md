# __scrt_fastfail

- ea: `0x180003f18`
- end: `0x180003f1c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003778`
- `0x180003878`
- `0x180003d78`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180003f18  mov     ecx, ecx
0x180003f1a  int     29h; Win8: RtlFailFast(ecx)
```

# __scrt_fastfail

- ea: `0x180015274`
- end: `0x180015278`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180014aa8`
- `0x180014ba8`
- `0x1800150d4`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180015274  mov     ecx, ecx
0x180015276  int     29h; Win8: RtlFailFast(ecx)
```

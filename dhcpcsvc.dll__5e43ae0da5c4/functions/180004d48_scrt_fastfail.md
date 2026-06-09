# __scrt_fastfail

- ea: `0x180004d48`
- end: `0x180004d4c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800045a8`
- `0x1800046a8`
- `0x180004ba8`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180004d48  mov     ecx, ecx
0x180004d4a  int     29h; Win8: RtlFailFast(ecx)
```

# __scrt_fastfail

- ea: `0x180007768`
- end: `0x18000776c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006fc8`
- `0x1800070c8`
- `0x1800075c8`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180007768  mov     ecx, ecx
0x18000776a  int     29h; Win8: RtlFailFast(ecx)
```

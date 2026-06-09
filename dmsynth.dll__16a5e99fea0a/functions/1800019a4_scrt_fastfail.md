# __scrt_fastfail

- ea: `0x1800019a4`
- end: `0x1800019a8`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011d8`
- `0x1800012d8`
- `0x180001804`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800019a4  mov     ecx, ecx
0x1800019a6  int     29h; Win8: RtlFailFast(ecx)
```

# RtlFailFast

- ea: `0x1800018d0`
- end: `0x1800018d4`
- name: `RtlFailFast`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010e8`
- `0x1800011e8`
- `0x180001730`

## pseudocode

```c
void __fastcall __noreturn RtlFailFast(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800018d0  mov     ecx, ecx
0x1800018d2  int     29h; Win8: RtlFailFast(ecx)
```

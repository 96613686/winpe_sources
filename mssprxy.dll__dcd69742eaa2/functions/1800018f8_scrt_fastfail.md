# __scrt_fastfail

- ea: `0x1800018f8`
- end: `0x1800018fc`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001158`
- `0x180001258`
- `0x180001758`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800018f8  mov     ecx, ecx
0x1800018fa  int     29h; Win8: RtlFailFast(ecx)
```

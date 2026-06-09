# __scrt_fastfail

- ea: `0x180001aa4`
- end: `0x180001aa8`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011f8`
- `0x1800012f8`
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
0x180001aa4  mov     ecx, ecx
0x180001aa6  int     29h; Win8: RtlFailFast(ecx)
```

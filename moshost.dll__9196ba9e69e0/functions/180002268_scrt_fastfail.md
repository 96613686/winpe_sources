# __scrt_fastfail

- ea: `0x180002268`
- end: `0x18000226c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019d8`
- `0x180001ad8`
- `0x180001eec`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180002268  mov     ecx, ecx
0x18000226a  int     29h; Win8: RtlFailFast(ecx)
```

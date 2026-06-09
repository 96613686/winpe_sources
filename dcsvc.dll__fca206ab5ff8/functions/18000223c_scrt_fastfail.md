# __scrt_fastfail

- ea: `0x18000223c`
- end: `0x180002240`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019c8`
- `0x180001ac8`
- `0x180001f08`
- `0x180002790`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x18000223c  mov     ecx, ecx
0x18000223e  int     29h; Win8: RtlFailFast(ecx)
```

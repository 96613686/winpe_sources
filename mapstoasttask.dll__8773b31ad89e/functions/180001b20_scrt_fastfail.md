# __scrt_fastfail

- ea: `0x180001b20`
- end: `0x180001b24`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001298`
- `0x180001398`
- `0x180001920`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001b20  mov     ecx, ecx
0x180001b22  int     29h; Win8: RtlFailFast(ecx)
```

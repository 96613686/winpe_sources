# __scrt_fastfail

- ea: `0x180002498`
- end: `0x18000249c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001888`
- `0x180001988`
- `0x180001d80`
- `0x180002000`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180002498  mov     ecx, ecx
0x18000249a  int     29h; Win8: RtlFailFast(ecx)
```

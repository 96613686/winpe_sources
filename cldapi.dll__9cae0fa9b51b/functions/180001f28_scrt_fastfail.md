# __scrt_fastfail

- ea: `0x180001f28`
- end: `0x180001f2c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001788`
- `0x180001888`
- `0x180001d88`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001f28  mov     ecx, ecx
0x180001f2a  int     29h; Win8: RtlFailFast(ecx)
```

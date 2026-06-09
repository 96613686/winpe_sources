# __scrt_fastfail

- ea: `0x1400019c0`
- end: `0x1400019c4`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001260`
- `0x140001350`
- `0x1400015a4`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1400019c0  mov     ecx, ecx
0x1400019c2  int     29h; Win8: RtlFailFast(ecx)
```

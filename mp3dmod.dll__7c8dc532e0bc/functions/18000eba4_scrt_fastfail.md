# __scrt_fastfail

- ea: `0x18000eba4`
- end: `0x18000eba8`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e428`
- `0x18000e528`
- `0x18000ea04`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x18000eba4  mov     ecx, ecx
0x18000eba6  int     29h; Win8: RtlFailFast(ecx)
```

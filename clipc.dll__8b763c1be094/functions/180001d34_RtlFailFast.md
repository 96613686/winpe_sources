# RtlFailFast

- ea: `0x180001d34`
- end: `0x180001d38`
- name: `RtlFailFast`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800014d8`
- `0x1800015d8`
- `0x1800019d0`

## pseudocode

```c
void __fastcall __noreturn RtlFailFast(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001d34  mov     ecx, ecx
0x180001d36  int     29h; Win8: RtlFailFast(ecx)
```

# __scrt_fastfail

- ea: `0x180002414`
- end: `0x180002418`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001bd8`
- `0x180001cd8`
- `0x18000210c`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180002414  mov     ecx, ecx
0x180002416  int     29h; Win8: RtlFailFast(ecx)
```

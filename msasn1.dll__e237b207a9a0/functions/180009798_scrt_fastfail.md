# __scrt_fastfail

- ea: `0x180009798`
- end: `0x18000979c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180008ff8`
- `0x1800090f8`
- `0x1800095f8`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180009798  mov     ecx, ecx
0x18000979a  int     29h; Win8: RtlFailFast(ecx)
```

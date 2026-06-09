# __scrt_fastfail

- ea: `0x1800050c8`
- end: `0x1800050cc`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004928`
- `0x180004a28`
- `0x180004f28`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800050c8  mov     ecx, ecx
0x1800050ca  int     29h; Win8: RtlFailFast(ecx)
```

# __scrt_fastfail

- ea: `0x14000261c`
- end: `0x140002620`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d00`
- `0x140001df0`
- `0x140002050`
- `0x140002240`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x14000261c  mov     ecx, ecx
0x14000261e  int     29h; Win8: RtlFailFast(ecx)
```

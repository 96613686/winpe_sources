# ___scrt_fastfail

- ea: `0x10012f93`
- end: `0x10012f9d`
- name: `___scrt_fastfail`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1001280b`
- `0x1001291b`
- `0x10012e06`

## pseudocode

```c
void __cdecl __noreturn __scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x10012f93  mov     edi, edi
0x10012f95  push    ebp
0x10012f96  mov     ebp, esp
0x10012f98  mov     ecx, [ebp+arg_0]
0x10012f9b  int     29h; Win8: RtlFailFast(ecx)
```

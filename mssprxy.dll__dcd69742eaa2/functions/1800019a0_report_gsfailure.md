# __report_gsfailure

- ea: `0x1800019a0`
- end: `0x1800019a7`
- name: `__report_gsfailure`
- size: `7`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001470`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  __fastfail(2u);
}

```

## disassembly

```asm
0x1800019a0  mov     ecx, 2
0x1800019a5  int     29h; Win8: RtlFailFast(ecx)
```

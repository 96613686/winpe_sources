# __report_gsfailure

- ea: `0x140001010`
- end: `0x140001017`
- name: `__report_gsfailure`
- size: `7`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140003510`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  __fastfail(2u);
}

```

## disassembly

```asm
0x140001010  mov     ecx, 2
0x140001015  int     29h; Win8: RtlFailFast(ecx)
```

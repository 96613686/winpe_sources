# __security_check_cookie

- ea: `0x140006480`
- end: `0x14000649e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400023f4`
- `0x140003c50`
- `0x140005b00`
- `0x1400063dc`
- `0x140012020`
- `0x1400125e0`
- `0x1400154a0`
- `0x140015830`
- `0x140018900`
- `0x14001b210`
- `0x14001b6c8`
- `0x14001d698`
- `0x14001dd70`
- `0x14001e10c`
- `0x14001e3f0`
- `0x14001e694`
- `0x14001ec90`
- `0x14001f710`
- `0x140020880`
- `0x140020ab0`
- `0x140020c38`
- `0x140021af0`
- `0x14002269c`
- `0x140025c40`
- `0x140026f90`
- `0x140029174`
- `0x140029228`
- `0x1400294a0`
- `0x140029aa8`
- `0x14002a540`
- `0x14002baa0`
- `0x14002e078`
- `0x14002e960`

## callees

- `0x140003010`
- `0x140006480`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x140006480  cmp     rcx, cs:__security_cookie
0x140006487  jnz     short ReportFailure
0x140006489  rol     rcx, 10h
0x14000648d  test    cx, 0FFFFh
0x140006492  jnz     short RestoreRcx
0x140006494  retn
0x140006495  ror     rcx, 10h; StackCookie
0x140006499  jmp     __report_gsfailure
```

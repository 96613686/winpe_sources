# __security_check_cookie

- ea: `0x180008bf0`
- end: `0x180008c0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001dd0`
- `0x1800020d0`
- `0x180002f20`
- `0x18000338c`
- `0x180003d10`
- `0x180003fe0`
- `0x180004778`
- `0x180004bfc`
- `0x180004d90`
- `0x18000534c`
- `0x1800054e8`
- `0x180005840`
- `0x1800080a8`
- `0x18000838c`
- `0x1800088d8`
- `0x1800089f0`
- `0x180008b34`

## callees

- `0x180006190`
- `0x180008bf0`

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
0x180008bf0  cmp     rcx, cs:__security_cookie
0x180008bf7  jnz     short ReportFailure
0x180008bf9  rol     rcx, 10h
0x180008bfd  test    cx, 0FFFFh
0x180008c02  jnz     short RestoreRcx
0x180008c04  retn
0x180008c05  ror     rcx, 10h
0x180008c09  jmp     __report_gsfailure
```

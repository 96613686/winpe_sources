# __security_check_cookie

- ea: `0x140005bf0`
- end: `0x140005c0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400014a0`
- `0x1400028b0`
- `0x140003410`
- `0x140003cb0`
- `0x140003d30`
- `0x140003dd8`
- `0x140003ecc`
- `0x140003f78`
- `0x140004624`
- `0x140005aac`
- `0x14000f198`
- `0x1400111d0`
- `0x140011438`
- `0x1400115e0`
- `0x140011ee0`
- `0x1400120f0`
- `0x140012210`
- `0x1400125d0`
- `0x140012810`
- `0x140014200`
- `0x140014f00`
- `0x140015350`
- `0x140015760`
- `0x140017078`

## callees

- `0x140003700`
- `0x140005bf0`

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
0x140005bf0  cmp     rcx, cs:__security_cookie
0x140005bf7  jnz     short ReportFailure
0x140005bf9  rol     rcx, 10h
0x140005bfd  test    cx, 0FFFFh
0x140005c02  jnz     short RestoreRcx
0x140005c04  retn
0x140005c05  ror     rcx, 10h; StackCookie
0x140005c09  jmp     __report_gsfailure
```

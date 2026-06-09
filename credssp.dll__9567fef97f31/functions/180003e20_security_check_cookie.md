# __security_check_cookie

- ea: `0x180003e20`
- end: `0x180003e3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b50`
- `0x1800020d0`
- `0x180002560`
- `0x1800035b4`
- `0x1800039e4`
- `0x180003d70`

## callees

- `0x180001700`
- `0x180003e20`

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
0x180003e20  cmp     rcx, cs:__security_cookie
0x180003e27  jnz     short ReportFailure
0x180003e29  rol     rcx, 10h
0x180003e2d  test    cx, 0FFFFh
0x180003e32  jnz     short RestoreRcx
0x180003e34  retn
0x180003e35  ror     rcx, 10h
0x180003e39  jmp     __report_gsfailure
```

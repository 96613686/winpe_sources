# __security_check_cookie

- ea: `0x180014e00`
- end: `0x180014e1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002dcc`
- `0x18000307c`
- `0x1800037f4`
- `0x180003ba0`
- `0x180003f78`
- `0x180004934`
- `0x180004ccc`
- `0x1800059d0`
- `0x180005c48`
- `0x18000658c`
- `0x180007608`
- `0x1800080bc`
- `0x180008b00`
- `0x180008bfc`
- `0x180008ca0`
- `0x180009378`
- `0x18000ab74`
- `0x18000aec0`
- `0x18000be70`
- `0x18000ca00`
- `0x18000d610`
- `0x180010920`
- `0x180010bdc`
- `0x1800136a0`
- `0x180013cc0`
- `0x180014cd8`

## callees

- `0x180001ad0`
- `0x180014e00`

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
0x180014e00  cmp     rcx, cs:__security_cookie
0x180014e07  jnz     short ReportFailure
0x180014e09  rol     rcx, 10h
0x180014e0d  test    cx, 0FFFFh
0x180014e12  jnz     short RestoreRcx
0x180014e14  retn
0x180014e15  ror     rcx, 10h
0x180014e19  jmp     __report_gsfailure
```

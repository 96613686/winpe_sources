# __security_check_cookie

- ea: `0x180003430`
- end: `0x18000344e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800019a4`
- `0x180001c90`
- `0x180002238`
- `0x1800026bc`
- `0x180002c20`
- `0x18000339c`

## callees

- `0x180001790`
- `0x180003430`

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
0x180003430  cmp     rcx, cs:__security_cookie
0x180003437  jnz     short ReportFailure
0x180003439  rol     rcx, 10h
0x18000343d  test    cx, 0FFFFh
0x180003442  jnz     short RestoreRcx
0x180003444  retn
0x180003445  ror     rcx, 10h
0x180003449  jmp     __report_gsfailure
```

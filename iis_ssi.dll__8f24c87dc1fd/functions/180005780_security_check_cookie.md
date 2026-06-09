# __security_check_cookie

- ea: `0x180005780`
- end: `0x18000579e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002170`
- `0x180002dc0`
- `0x180003678`
- `0x180003a34`
- `0x180003d8c`
- `0x180003e9c`
- `0x180003fac`
- `0x1800040ec`
- `0x1800042fc`
- `0x18000474c`
- `0x180004afc`
- `0x18000559c`
- `0x1800056b8`

## callees

- `0x180001570`
- `0x180005780`

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
0x180005780  cmp     rcx, cs:__security_cookie
0x180005787  jnz     short ReportFailure
0x180005789  rol     rcx, 10h
0x18000578d  test    cx, 0FFFFh
0x180005792  jnz     short RestoreRcx
0x180005794  retn
0x180005795  ror     rcx, 10h
0x180005799  jmp     __report_gsfailure
```

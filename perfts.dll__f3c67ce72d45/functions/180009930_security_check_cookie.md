# __security_check_cookie

- ea: `0x180009930`
- end: `0x18000994e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001098`
- `0x180001140`
- `0x180002990`
- `0x1800034c8`
- `0x180003604`
- `0x1800038b0`
- `0x180003a40`
- `0x180003c74`
- `0x1800040c4`
- `0x180004e40`
- `0x180005378`
- `0x1800058b8`
- `0x180005d24`
- `0x180006068`
- `0x180006598`
- `0x180006784`
- `0x180006f98`
- `0x180007668`
- `0x180008074`
- `0x1800096e0`
- `0x180009814`

## callees

- `0x180001910`
- `0x180009930`

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
0x180009930  cmp     rcx, cs:__security_cookie
0x180009937  jnz     short ReportFailure
0x180009939  rol     rcx, 10h
0x18000993d  test    cx, 0FFFFh
0x180009942  jnz     short RestoreRcx
0x180009944  retn
0x180009945  ror     rcx, 10h
0x180009949  jmp     __report_gsfailure
```

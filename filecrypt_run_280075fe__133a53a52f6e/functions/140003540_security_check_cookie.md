# __security_check_cookie

- ea: `0x140003540`
- end: `0x14000355e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400015c4`
- `0x14000213c`
- `0x140002fd0`
- `0x140003028`
- `0x140003098`
- `0x140003134`
- `0x14000320c`
- `0x140003358`
- `0x14000d7a8`
- `0x14000e858`
- `0x14000ecd4`
- `0x14000f044`
- `0x140011810`
- `0x140011d50`
- `0x1400127b0`
- `0x140012a40`
- `0x140013160`
- `0x140014010`

## callees

- `0x140001420`
- `0x140003540`

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
0x140003540  cmp     rcx, cs:__security_cookie
0x140003547  jnz     short ReportFailure
0x140003549  rol     rcx, 10h
0x14000354d  test    cx, 0FFFFh
0x140003552  jnz     short RestoreRcx
0x140003554  retn
0x140003555  ror     rcx, 10h; StackCookie
0x140003559  jmp     __report_gsfailure
```

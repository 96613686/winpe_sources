# __security_check_cookie

- ea: `0x180009310`
- end: `0x18000932e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800044d0`
- `0x1800067c0`
- `0x1800069f8`
- `0x180006b00`
- `0x18000aa5c`

## callees

- `0x180009310`
- `0x180009840`

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
0x180009310  cmp     rcx, cs:__security_cookie
0x180009317  jnz     short ReportFailure
0x180009319  rol     rcx, 10h
0x18000931d  test    cx, 0FFFFh
0x180009322  jnz     short RestoreRcx
0x180009324  retn
0x180009325  ror     rcx, 10h; StackCookie
0x180009329  jmp     __report_gsfailure
```

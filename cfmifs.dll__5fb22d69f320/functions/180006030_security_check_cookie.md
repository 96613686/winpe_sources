# __security_check_cookie

- ea: `0x180006030`
- end: `0x18000604e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c2c`
- `0x180001d7c`
- `0x180002d44`
- `0x1800034c0`
- `0x18000420c`
- `0x180004538`
- `0x180004688`
- `0x180004818`
- `0x1800049dc`
- `0x1800052b4`
- `0x18000547c`
- `0x18000579c`

## callees

- `0x180001620`
- `0x180006030`

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
0x180006030  cmp     rcx, cs:__security_cookie
0x180006037  jnz     short ReportFailure
0x180006039  rol     rcx, 10h
0x18000603d  test    cx, 0FFFFh
0x180006042  jnz     short RestoreRcx
0x180006044  retn
0x180006045  ror     rcx, 10h
0x180006049  jmp     __report_gsfailure
```

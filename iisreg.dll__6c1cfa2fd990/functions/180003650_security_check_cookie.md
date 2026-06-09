# __security_check_cookie

- ea: `0x180003650`
- end: `0x18000366e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b90`
- `0x180001d7c`
- `0x18000200c`
- `0x180002330`
- `0x18000260c`
- `0x18000283c`
- `0x1800029c4`
- `0x180002b90`
- `0x180002d14`
- `0x180002e64`
- `0x180002ec8`
- `0x180003328`
- `0x18000359c`

## callees

- `0x180001710`
- `0x180003650`

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
0x180003650  cmp     rcx, cs:__security_cookie
0x180003657  jnz     short ReportFailure
0x180003659  rol     rcx, 10h
0x18000365d  test    cx, 0FFFFh
0x180003662  jnz     short RestoreRcx
0x180003664  retn
0x180003665  ror     rcx, 10h
0x180003669  jmp     __report_gsfailure
```

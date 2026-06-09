# __security_check_cookie

- ea: `0x180003a90`
- end: `0x180003aae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180002070`
- `0x180002880`
- `0x180002ec0`
- `0x180003240`
- `0x1800077b8`

## callees

- `0x180003a90`
- `0x180003fc0`

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
0x180003a90  cmp     rcx, cs:__security_cookie
0x180003a97  jnz     short ReportFailure
0x180003a99  rol     rcx, 10h
0x180003a9d  test    cx, 0FFFFh
0x180003aa2  jnz     short RestoreRcx
0x180003aa4  retn
0x180003aa5  ror     rcx, 10h; StackCookie
0x180003aa9  jmp     __report_gsfailure
```

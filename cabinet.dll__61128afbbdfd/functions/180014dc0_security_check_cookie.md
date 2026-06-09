# __security_check_cookie

- ea: `0x180014dc0`
- end: `0x180014dde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001bd8`
- `0x180002b44`
- `0x180002f0c`
- `0x180003340`
- `0x1800039b8`
- `0x1800059b0`
- `0x180006910`
- `0x180007260`
- `0x1800078e0`
- `0x180009158`
- `0x180009650`
- `0x18000e150`
- `0x18000e684`
- `0x18000f21c`
- `0x18000f2a8`
- `0x18000fe40`
- `0x1800117c0`
- `0x180012760`
- `0x180012a40`
- `0x180013004`
- `0x180014140`
- `0x1800156e0`
- `0x180015900`
- `0x1800159f0`
- `0x18001b5b0`

## callees

- `0x180014dc0`
- `0x180014df0`

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
0x180014dc0  cmp     rcx, cs:__security_cookie
0x180014dc7  jnz     short ReportFailure
0x180014dc9  rol     rcx, 10h
0x180014dcd  test    cx, 0FFFFh
0x180014dd2  jnz     short RestoreRcx
0x180014dd4  retn
0x180014dd5  ror     rcx, 10h; StackCookie
0x180014dd9  jmp     __report_gsfailure
```

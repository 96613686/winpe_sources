# __security_check_cookie

- ea: `0x18000ee10`
- end: `0x18000ee2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b78`
- `0x180002620`
- `0x180002ad0`
- `0x180003ad4`
- `0x180003eb0`
- `0x18000401c`
- `0x1800042f0`
- `0x1800045e0`
- `0x180004c24`
- `0x180005294`
- `0x180006d40`
- `0x1800075f0`
- `0x180007e1c`
- `0x180008850`
- `0x180009414`
- `0x180009d74`
- `0x18000a028`
- `0x18000a8b8`
- `0x18000abfc`
- `0x18000b564`
- `0x18000bb5c`
- `0x18000bea0`
- `0x18000c390`
- `0x18000cb30`
- `0x18000d370`
- `0x18000dc5c`
- `0x18000ddec`
- `0x18000e448`
- `0x18000ed50`

## callees

- `0x1800017a0`
- `0x18000ee10`

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
0x18000ee10  cmp     rcx, cs:__security_cookie
0x18000ee17  jnz     short ReportFailure
0x18000ee19  rol     rcx, 10h
0x18000ee1d  test    cx, 0FFFFh
0x18000ee22  jnz     short RestoreRcx
0x18000ee24  retn
0x18000ee25  ror     rcx, 10h
0x18000ee29  jmp     __report_gsfailure
```

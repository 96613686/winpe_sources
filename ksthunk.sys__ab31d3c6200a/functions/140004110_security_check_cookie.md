# __security_check_cookie

- ea: `0x140004110`
- end: `0x14000412e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001990`
- `0x14000272c`
- `0x14000280c`
- `0x14000408c`
- `0x14000bac0`
- `0x14000e2c4`

## callees

- `0x140001010`
- `0x140004110`

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
0x140004110  cmp     rcx, cs:__security_cookie
0x140004117  jnz     short ReportFailure
0x140004119  rol     rcx, 10h
0x14000411d  test    cx, 0FFFFh
0x140004122  jnz     short RestoreRcx
0x140004124  retn
0x140004125  ror     rcx, 10h; StackCookie
0x140004129  jmp     __report_gsfailure
```

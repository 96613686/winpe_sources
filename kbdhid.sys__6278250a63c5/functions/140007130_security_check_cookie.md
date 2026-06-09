# __security_check_cookie

- ea: `0x140007130`
- end: `0x14000714e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400026a0`
- `0x140003040`
- `0x140004f80`
- `0x1400062e4`
- `0x14000649c`
- `0x1400067e4`
- `0x140006ffc`
- `0x14000f7fc`
- `0x14000ff70`
- `0x140011010`
- `0x140011660`
- `0x14001187c`

## callees

- `0x1400057e0`
- `0x140007130`

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
0x140007130  cmp     rcx, cs:__security_cookie
0x140007137  jnz     short ReportFailure
0x140007139  rol     rcx, 10h
0x14000713d  test    cx, 0FFFFh
0x140007142  jnz     short RestoreRcx
0x140007144  retn
0x140007145  ror     rcx, 10h; StackCookie
0x140007149  jmp     __report_gsfailure
```

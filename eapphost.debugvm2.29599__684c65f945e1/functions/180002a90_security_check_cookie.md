# __security_check_cookie

- ea: `0x180002a90`
- end: `0x180002aae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `147`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001118`
- `0x180001300`
- `0x180001524`
- `0x1800015f0`
- `0x1800016dc`
- `0x1800017a4`
- `0x18000186c`
- `0x1800019cc`
- `0x180001c80`
- `0x180001f78`
- `0x1800044dc`
- `0x180004778`
- `0x180005158`
- `0x1800053d0`
- `0x18000556c`
- `0x180005b30`
- `0x1800074e4`
- `0x180007898`
- `0x180007e88`
- `0x18000926c`
- `0x180009990`
- `0x180009bec`
- `0x180009d00`
- `0x18000abf4`
- `0x18000c0e4`
- `0x18000c768`
- `0x18000cf70`
- `0x18000d79c`
- `0x18000dea4`
- `0x18000e190`
- `0x18000e89c`
- `0x18000f7e0`
- `0x18000fa68`
- `0x18000fb7c`
- `0x18000fcf0`
- `0x18000fea0`
- `0x1800104d4`
- `0x1800106d4`
- `0x180010acc`
- `0x180010eb4`
- `0x180011064`
- `0x1800113a0`
- `0x1800115e8`
- `0x180011958`
- `0x1800119d4`
- `0x1800123f0`
- `0x180012900`
- `0x180012fc0`
- `0x1800131c0`

## callees

- `0x180002a90`
- `0x180002ea0`

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
0x180002a90  cmp     rcx, cs:__security_cookie
0x180002a97  jnz     short ReportFailure
0x180002a99  rol     rcx, 10h
0x180002a9d  test    cx, 0FFFFh
0x180002aa2  jnz     short RestoreRcx
0x180002aa4  retn
0x180002aa5  ror     rcx, 10h; StackCookie
0x180002aa9  jmp     __report_gsfailure
```

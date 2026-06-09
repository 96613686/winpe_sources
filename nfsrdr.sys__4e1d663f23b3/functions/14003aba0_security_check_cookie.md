# __security_check_cookie

- ea: `0x14003aba0`
- end: `0x14003abbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `55`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400029d0`
- `0x140004530`
- `0x140005de0`
- `0x14000adb0`
- `0x14000df64`
- `0x140012c40`
- `0x140015674`
- `0x140016cb8`
- `0x14001a950`
- `0x14001add0`
- `0x14001b3e0`
- `0x14001d6b0`
- `0x14001e69c`
- `0x140020fa8`
- `0x1400219e8`
- `0x14002246c`
- `0x140022c5c`
- `0x140023000`
- `0x1400231c0`
- `0x140023388`
- `0x14002372c`
- `0x140023dd0`
- `0x140024720`
- `0x140024c60`
- `0x140025be0`
- `0x1400273f0`
- `0x140027d74`
- `0x140027eec`
- `0x140028870`
- `0x140028ac8`
- `0x140028d14`
- `0x1400293c4`
- `0x140029b24`
- `0x140029f20`
- `0x14002a518`
- `0x14002a5f0`
- `0x14002a9e0`
- `0x14002bc4c`
- `0x14002bf9c`
- `0x14002c2e0`
- `0x14002c4c4`
- `0x14002c854`
- `0x14002cfc8`
- `0x14002d428`
- `0x14002e330`
- `0x14002e5a8`
- `0x14002e7fc`
- `0x1400316d0`
- `0x140036fd0`
- `0x1400372e8`

## callees

- `0x1400150d0`
- `0x14003aba0`

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
0x14003aba0  cmp     rcx, cs:__security_cookie
0x14003aba7  jnz     short ReportFailure
0x14003aba9  rol     rcx, 10h
0x14003abad  test    cx, 0FFFFh
0x14003abb2  jnz     short RestoreRcx
0x14003abb4  retn
0x14003abb5  ror     rcx, 10h; StackCookie
0x14003abb9  jmp     __report_gsfailure
```

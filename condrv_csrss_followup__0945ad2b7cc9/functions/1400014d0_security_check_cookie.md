# __security_check_cookie

- ea: `0x1400014d0`
- end: `0x1400014ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400013dc`
- `0x140008aa0`
- `0x140008f04`
- `0x140009af0`
- `0x14000ac50`
- `0x14000ce70`
- `0x14000d6b0`

## callees

- `0x140001120`
- `0x1400014d0`

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
0x1400014d0  cmp     rcx, cs:__security_cookie
0x1400014d7  jnz     short ReportFailure
0x1400014d9  rol     rcx, 10h
0x1400014dd  test    cx, 0FFFFh
0x1400014e2  jnz     short RestoreRcx
0x1400014e4  retn
0x1400014e5  ror     rcx, 10h; StackCookie
0x1400014e9  jmp     __report_gsfailure
```

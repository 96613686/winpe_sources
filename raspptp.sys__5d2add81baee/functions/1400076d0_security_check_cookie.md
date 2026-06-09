# __security_check_cookie

- ea: `0x1400076d0`
- end: `0x1400076ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001c10`
- `0x140005ee0`
- `0x140006efc`
- `0x140007274`
- `0x14000759c`
- `0x14000f224`
- `0x14000f588`
- `0x14000f8d8`
- `0x14000fbac`
- `0x1400102fc`
- `0x140010c14`
- `0x1400114c8`
- `0x140011d04`
- `0x1400122b0`
- `0x140012798`
- `0x140012ac0`
- `0x140012da4`
- `0x1400137ac`
- `0x140013954`
- `0x140014fd8`
- `0x140015270`
- `0x140015338`
- `0x1400154b8`
- `0x140015da8`
- `0x1400162f0`
- `0x140016db0`
- `0x140017b50`
- `0x14001a010`
- `0x14001af90`
- `0x14001ded0`

## callees

- `0x140002b00`
- `0x1400076d0`

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
0x1400076d0  cmp     rcx, cs:__security_cookie
0x1400076d7  jnz     short ReportFailure
0x1400076d9  rol     rcx, 10h
0x1400076dd  test    cx, 0FFFFh
0x1400076e2  jnz     short RestoreRcx
0x1400076e4  retn
0x1400076e5  ror     rcx, 10h; StackCookie
0x1400076e9  jmp     __report_gsfailure
```

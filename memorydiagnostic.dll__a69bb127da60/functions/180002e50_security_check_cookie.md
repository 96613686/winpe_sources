# __security_check_cookie

- ea: `0x180002e50`
- end: `0x180002e6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `56`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001098`
- `0x180001174`
- `0x180001220`
- `0x1800012cc`
- `0x180001394`
- `0x180001648`
- `0x180001940`
- `0x180001b1c`
- `0x180002230`
- `0x180002540`
- `0x180002740`
- `0x1800028b0`
- `0x1800032fc`
- `0x18000425c`
- `0x180004db0`
- `0x180004ef4`
- `0x180005454`
- `0x180005aa4`
- `0x180005d50`
- `0x1800063d8`
- `0x180008cc8`
- `0x180009098`
- `0x1800094d4`
- `0x180009fc0`
- `0x18000a294`
- `0x18000b238`
- `0x18000cd54`
- `0x18000d174`
- `0x18000dcdc`
- `0x18000e168`
- `0x18000ef90`
- `0x18000f09c`
- `0x18000faac`
- `0x180011760`
- `0x1800139d0`
- `0x180014570`
- `0x180015928`
- `0x180015a4c`
- `0x180015f9c`
- `0x18001625c`
- `0x180017480`
- `0x180018680`
- `0x180018844`
- `0x180018a48`
- `0x180018c48`
- `0x180018fa0`
- `0x1800190c8`
- `0x180019780`
- `0x18001a3e4`

## callees

- `0x180002e50`
- `0x1800037b0`

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
0x180002e50  cmp     rcx, cs:__security_cookie
0x180002e57  jnz     short ReportFailure
0x180002e59  rol     rcx, 10h
0x180002e5d  test    cx, 0FFFFh
0x180002e62  jnz     short RestoreRcx
0x180002e64  retn
0x180002e65  ror     rcx, 10h; StackCookie
0x180002e69  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x14001fc30`
- end: `0x14001fc4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001044`
- `0x140002ec8`
- `0x140005378`
- `0x140006bc0`
- `0x1400074d0`
- `0x14000a5f0`
- `0x14000d740`
- `0x14000d83c`
- `0x14001b5b0`
- `0x14001fa68`
- `0x1400326f8`
- `0x140033530`
- `0x140034a80`
- `0x140034e38`
- `0x140035ab8`
- `0x14003751c`

## callees

- `0x140001010`
- `0x14001fc30`

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
0x14001fc30  cmp     rcx, cs:__security_cookie
0x14001fc37  jnz     short ReportFailure
0x14001fc39  rol     rcx, 10h
0x14001fc3d  test    cx, 0FFFFh
0x14001fc42  jnz     short RestoreRcx
0x14001fc44  retn
0x14001fc45  ror     rcx, 10h; StackCookie
0x14001fc49  jmp     __report_gsfailure
```

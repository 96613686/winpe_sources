# __security_check_cookie

- ea: `0x140002df0`
- end: `0x140002e0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002c4c`
- `0x14000b684`
- `0x14000c8b4`
- `0x14000dc38`
- `0x14000f27c`
- `0x14000f618`
- `0x140011744`
- `0x1400135d0`
- `0x1400142d8`
- `0x140015090`
- `0x14001617c`
- `0x1400163f0`
- `0x140018bec`
- `0x14001b0d8`
- `0x14001c500`

## callees

- `0x1400010c0`
- `0x140002df0`

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
0x140002df0  cmp     rcx, cs:__security_cookie
0x140002df7  jnz     short ReportFailure
0x140002df9  rol     rcx, 10h
0x140002dfd  test    cx, 0FFFFh
0x140002e02  jnz     short RestoreRcx
0x140002e04  retn
0x140002e05  ror     rcx, 10h; StackCookie
0x140002e09  jmp     __report_gsfailure
```

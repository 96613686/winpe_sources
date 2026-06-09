# __security_check_cookie

- ea: `0x180003100`
- end: `0x18000311e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800026f8`
- `0x1800029a0`
- `0x18000306c`

## callees

- `0x180001880`
- `0x180003100`

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
0x180003100  cmp     rcx, cs:__security_cookie
0x180003107  jnz     short ReportFailure
0x180003109  rol     rcx, 10h
0x18000310d  test    cx, 0FFFFh
0x180003112  jnz     short RestoreRcx
0x180003114  retn
0x180003115  ror     rcx, 10h
0x180003119  jmp     __report_gsfailure
```

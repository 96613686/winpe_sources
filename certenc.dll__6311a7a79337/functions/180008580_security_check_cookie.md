# __security_check_cookie

- ea: `0x180008580`
- end: `0x18000859e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800045d4`
- `0x180004788`
- `0x18000550c`
- `0x180005c48`
- `0x180006468`
- `0x1800084d0`

## callees

- `0x1800015a0`
- `0x180008580`

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
0x180008580  cmp     rcx, cs:__security_cookie
0x180008587  jnz     short ReportFailure
0x180008589  rol     rcx, 10h
0x18000858d  test    cx, 0FFFFh
0x180008592  jnz     short RestoreRcx
0x180008594  retn
0x180008595  ror     rcx, 10h
0x180008599  jmp     __report_gsfailure
```

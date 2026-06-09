# __security_check_cookie

- ea: `0x140004dd0`
- end: `0x140004dee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400044bc`
- `0x140004c9c`
- `0x14000baf0`

## callees

- `0x140001010`
- `0x140004dd0`

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
0x140004dd0  cmp     rcx, cs:__security_cookie
0x140004dd7  jnz     short ReportFailure
0x140004dd9  rol     rcx, 10h
0x140004ddd  test    cx, 0FFFFh
0x140004de2  jnz     short RestoreRcx
0x140004de4  retn
0x140004de5  ror     rcx, 10h; StackCookie
0x140004de9  jmp     __report_gsfailure
```

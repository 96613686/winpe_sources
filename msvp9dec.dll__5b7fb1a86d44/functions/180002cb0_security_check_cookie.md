# __security_check_cookie

- ea: `0x180002cb0`
- end: `0x180002cce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001440`
- `0x180003ad0`
- `0x1800048ec`
- `0x180004fc4`

## callees

- `0x180002cb0`
- `0x180003270`

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
0x180002cb0  cmp     rcx, cs:__security_cookie
0x180002cb7  jnz     short ReportFailure
0x180002cb9  rol     rcx, 10h
0x180002cbd  test    cx, 0FFFFh
0x180002cc2  jnz     short RestoreRcx
0x180002cc4  retn
0x180002cc5  ror     rcx, 10h; StackCookie
0x180002cc9  jmp     __report_gsfailure
```

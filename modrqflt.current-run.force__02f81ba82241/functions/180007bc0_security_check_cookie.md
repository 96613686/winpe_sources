# __security_check_cookie

- ea: `0x180007bc0`
- end: `0x180007bde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010c0`
- `0x180003080`
- `0x1800071f8`
- `0x1800077f8`
- `0x180007988`
- `0x180007b3c`

## callees

- `0x180005fe0`
- `0x180007bc0`

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
0x180007bc0  cmp     rcx, cs:__security_cookie
0x180007bc7  jnz     short ReportFailure
0x180007bc9  rol     rcx, 10h
0x180007bcd  test    cx, 0FFFFh
0x180007bd2  jnz     short RestoreRcx
0x180007bd4  retn
0x180007bd5  ror     rcx, 10h
0x180007bd9  jmp     __report_gsfailure
```

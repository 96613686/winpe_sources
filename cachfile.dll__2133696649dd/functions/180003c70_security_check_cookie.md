# __security_check_cookie

- ea: `0x180003c70`
- end: `0x180003c8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001630`
- `0x180001d40`
- `0x180002030`
- `0x180003534`
- `0x180003840`
- `0x180003bbc`

## callees

- `0x180003060`
- `0x180003c70`

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
0x180003c70  cmp     rcx, cs:__security_cookie
0x180003c77  jnz     short ReportFailure
0x180003c79  rol     rcx, 10h
0x180003c7d  test    cx, 0FFFFh
0x180003c82  jnz     short RestoreRcx
0x180003c84  retn
0x180003c85  ror     rcx, 10h
0x180003c89  jmp     __report_gsfailure
```

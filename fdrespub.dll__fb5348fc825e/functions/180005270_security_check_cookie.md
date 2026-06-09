# __security_check_cookie

- ea: `0x180005270`
- end: `0x18000528e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800022b4`
- `0x180003404`
- `0x18000356c`
- `0x180003ae8`
- `0x1800051d0`

## callees

- `0x180001790`
- `0x180005270`

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
0x180005270  cmp     rcx, cs:__security_cookie
0x180005277  jnz     short ReportFailure
0x180005279  rol     rcx, 10h
0x18000527d  test    cx, 0FFFFh
0x180005282  jnz     short RestoreRcx
0x180005284  retn
0x180005285  ror     rcx, 10h
0x180005289  jmp     __report_gsfailure
```

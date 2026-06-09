# __security_check_cookie

- ea: `0x180003a40`
- end: `0x180003a5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000243c`
- `0x180002968`
- `0x180003994`

## callees

- `0x180001790`
- `0x180003a40`

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
0x180003a40  cmp     rcx, cs:__security_cookie
0x180003a47  jnz     short ReportFailure
0x180003a49  rol     rcx, 10h
0x180003a4d  test    cx, 0FFFFh
0x180003a52  jnz     short RestoreRcx
0x180003a54  retn
0x180003a55  ror     rcx, 10h
0x180003a59  jmp     __report_gsfailure
```

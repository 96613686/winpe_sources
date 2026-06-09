# __security_check_cookie

- ea: `0x180002620`
- end: `0x18000263e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001280`
- `0x180002598`

## callees

- `0x180001d30`
- `0x180002620`

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
0x180002620  cmp     rcx, cs:__security_cookie
0x180002627  jnz     short ReportFailure
0x180002629  rol     rcx, 10h
0x18000262d  test    cx, 0FFFFh
0x180002632  jnz     short RestoreRcx
0x180002634  retn
0x180002635  ror     rcx, 10h
0x180002639  jmp     __report_gsfailure
```

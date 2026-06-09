# __security_check_cookie

- ea: `0x180004920`
- end: `0x18000493e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b1c`
- `0x180002fc4`
- `0x18000388c`
- `0x180004604`

## callees

- `0x180001920`
- `0x180004920`

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
0x180004920  cmp     rcx, cs:__security_cookie
0x180004927  jnz     short ReportFailure
0x180004929  rol     rcx, 10h
0x18000492d  test    cx, 0FFFFh
0x180004932  jnz     short RestoreRcx
0x180004934  retn
0x180004935  ror     rcx, 10h
0x180004939  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x180002760`
- end: `0x18000277e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800016b0`
- `0x180001ab0`
- `0x1800026cc`
- `0x180003aa4`
- `0x180004230`

## callees

- `0x180002500`
- `0x180002760`

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
0x180002760  cmp     rcx, cs:__security_cookie
0x180002767  jnz     short ReportFailure
0x180002769  rol     rcx, 10h
0x18000276d  test    cx, 0FFFFh
0x180002772  jnz     short RestoreRcx
0x180002774  retn
0x180002775  ror     rcx, 10h
0x180002779  jmp     __report_gsfailure
```

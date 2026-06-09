# __security_check_cookie

- ea: `0x180001580`
- end: `0x18000159e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003678`
- `0x1800041dc`
- `0x18000440c`
- `0x180004fc0`
- `0x180005340`
- `0x1800057a0`
- `0x180005fbc`
- `0x180008358`
- `0x180016a30`
- `0x18001a330`
- `0x18001ac40`
- `0x18001af58`
- `0x18001c404`
- `0x18001d2f4`

## callees

- `0x180001580`
- `0x180001b10`

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
0x180001580  cmp     rcx, cs:__security_cookie
0x180001587  jnz     short ReportFailure
0x180001589  rol     rcx, 10h
0x18000158d  test    cx, 0FFFFh
0x180001592  jnz     short RestoreRcx
0x180001594  retn
0x180001595  ror     rcx, 10h; StackCookie
0x180001599  jmp     __report_gsfailure
```

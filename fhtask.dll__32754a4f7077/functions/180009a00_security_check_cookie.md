# __security_check_cookie

- ea: `0x180009a00`
- end: `0x180009a1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f2c`
- `0x18000207c`
- `0x18000296c`
- `0x180003cec`
- `0x180004148`
- `0x180004298`
- `0x180004428`
- `0x18000460c`
- `0x180004f84`
- `0x180005074`
- `0x1800054a0`
- `0x180007110`
- `0x1800071fc`
- `0x1800075c4`
- `0x1800077ec`
- `0x180007ba0`
- `0x180008900`
- `0x1800093c8`

## callees

- `0x180001870`
- `0x180009a00`

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
0x180009a00  cmp     rcx, cs:__security_cookie
0x180009a07  jnz     short ReportFailure
0x180009a09  rol     rcx, 10h
0x180009a0d  test    cx, 0FFFFh
0x180009a12  jnz     short RestoreRcx
0x180009a14  retn
0x180009a15  ror     rcx, 10h
0x180009a19  jmp     __report_gsfailure
```

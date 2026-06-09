# __security_check_cookie

- ea: `0x180001be0`
- end: `0x180001bfe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180002d24`
- `0x180002fc0`
- `0x1800033e8`
- `0x1800037d4`
- `0x180003bb4`
- `0x180004020`
- `0x180004534`
- `0x1800048b0`
- `0x1800065c4`
- `0x180006bfc`
- `0x180006ee4`
- `0x180007004`
- `0x1800072f0`
- `0x1800076d0`
- `0x180007900`
- `0x180007d90`

## callees

- `0x180001be0`
- `0x1800021e0`

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
0x180001be0  cmp     rcx, cs:__security_cookie
0x180001be7  jnz     short ReportFailure
0x180001be9  rol     rcx, 10h
0x180001bed  test    cx, 0FFFFh
0x180001bf2  jnz     short RestoreRcx
0x180001bf4  retn
0x180001bf5  ror     rcx, 10h; StackCookie
0x180001bf9  jmp     __report_gsfailure
```

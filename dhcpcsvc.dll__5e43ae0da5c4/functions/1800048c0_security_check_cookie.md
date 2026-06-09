# __security_check_cookie

- ea: `0x1800048c0`
- end: `0x1800048de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001240`
- `0x1800021a0`
- `0x1800026a0`
- `0x180003b3c`
- `0x180003e70`
- `0x180006000`
- `0x180007dd0`
- `0x1800088d0`
- `0x180008aa0`
- `0x180009060`
- `0x180009920`
- `0x180009d40`
- `0x18000a4d0`
- `0x18000b9d0`
- `0x18000c990`
- `0x18000cc10`
- `0x18000cfe0`
- `0x18000dd30`
- `0x18000e04c`
- `0x18000e1e0`
- `0x18000f090`
- `0x18000f2a0`
- `0x18000fdc4`
- `0x180010958`

## callees

- `0x1800048c0`
- `0x180004df0`

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
0x1800048c0  cmp     rcx, cs:__security_cookie
0x1800048c7  jnz     short ReportFailure
0x1800048c9  rol     rcx, 10h
0x1800048cd  test    cx, 0FFFFh
0x1800048d2  jnz     short RestoreRcx
0x1800048d4  retn
0x1800048d5  ror     rcx, 10h; StackCookie
0x1800048d9  jmp     __report_gsfailure
```

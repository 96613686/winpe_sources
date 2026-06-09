# __security_check_cookie

- ea: `0x180004420`
- end: `0x18000443e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001bb0`
- `0x1800029c0`
- `0x1800034d0`
- `0x180003800`
- `0x1800040c8`
- `0x18000431c`

## callees

- `0x180001780`
- `0x180004420`

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
0x180004420  cmp     rcx, cs:__security_cookie
0x180004427  jnz     short ReportFailure
0x180004429  rol     rcx, 10h
0x18000442d  test    cx, 0FFFFh
0x180004432  jnz     short RestoreRcx
0x180004434  retn
0x180004435  ror     rcx, 10h
0x180004439  jmp     __report_gsfailure
```

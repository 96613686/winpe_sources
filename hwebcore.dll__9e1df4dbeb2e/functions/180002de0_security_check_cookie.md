# __security_check_cookie

- ea: `0x180002de0`
- end: `0x180002dfe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a3c`
- `0x180001ab0`
- `0x18000244c`
- `0x180002600`
- `0x180002714`
- `0x180002d20`

## callees

- `0x180001780`
- `0x180002de0`

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
0x180002de0  cmp     rcx, cs:__security_cookie
0x180002de7  jnz     short ReportFailure
0x180002de9  rol     rcx, 10h
0x180002ded  test    cx, 0FFFFh
0x180002df2  jnz     short RestoreRcx
0x180002df4  retn
0x180002df5  ror     rcx, 10h
0x180002df9  jmp     __report_gsfailure
```

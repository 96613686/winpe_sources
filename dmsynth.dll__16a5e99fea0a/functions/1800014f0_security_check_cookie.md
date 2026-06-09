# __security_check_cookie

- ea: `0x1800014f0`
- end: `0x18000150e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bb20`
- `0x18000c710`
- `0x18000e930`
- `0x18000f010`
- `0x18000f910`
- `0x1800101c0`
- `0x180010cc0`
- `0x180010da0`
- `0x180010fc0`
- `0x1800112a0`
- `0x1800133b0`
- `0x180013710`
- `0x180013ae0`
- `0x180013fb0`
- `0x180014380`
- `0x180014850`

## callees

- `0x1800014f0`
- `0x180001530`

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
0x1800014f0  cmp     rcx, cs:__security_cookie
0x1800014f7  jnz     short ReportFailure
0x1800014f9  rol     rcx, 10h
0x1800014fd  test    cx, 0FFFFh
0x180001502  jnz     short RestoreRcx
0x180001504  retn
0x180001505  ror     rcx, 10h; StackCookie
0x180001509  jmp     __report_gsfailure
```

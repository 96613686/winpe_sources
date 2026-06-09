# __security_check_cookie

- ea: `0x180004c10`
- end: `0x180004c2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001220`
- `0x180001eb0`
- `0x1800024d0`
- `0x180002f20`
- `0x180004b5c`
- `0x1800069c4`

## callees

- `0x180004990`
- `0x180004c10`

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
0x180004c10  cmp     rcx, cs:__security_cookie
0x180004c17  jnz     short ReportFailure
0x180004c19  rol     rcx, 10h
0x180004c1d  test    cx, 0FFFFh
0x180004c22  jnz     short RestoreRcx
0x180004c24  retn
0x180004c25  ror     rcx, 10h
0x180004c29  jmp     __report_gsfailure
```

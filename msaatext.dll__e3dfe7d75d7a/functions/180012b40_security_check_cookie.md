# __security_check_cookie

- ea: `0x180012b40`
- end: `0x180012b5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800026d0`
- `0x180002994`
- `0x180004544`
- `0x180004af0`
- `0x180004b50`
- `0x1800066a0`
- `0x180007810`
- `0x180008930`
- `0x18000ab80`
- `0x18000d38c`
- `0x18000dab0`
- `0x18000dba0`
- `0x18000df20`
- `0x18000e3f4`
- `0x18000ecfc`
- `0x18000ee8c`
- `0x18000f150`
- `0x18001036c`
- `0x180010ae8`
- `0x180010dd4`
- `0x180011038`
- `0x180012314`
- `0x1800124b0`
- `0x180012528`
- `0x1800129b4`

## callees

- `0x180001b30`
- `0x180012b40`

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
0x180012b40  cmp     rcx, cs:__security_cookie
0x180012b47  jnz     short ReportFailure
0x180012b49  rol     rcx, 10h
0x180012b4d  test    cx, 0FFFFh
0x180012b52  jnz     short RestoreRcx
0x180012b54  retn
0x180012b55  ror     rcx, 10h
0x180012b59  jmp     __report_gsfailure
```

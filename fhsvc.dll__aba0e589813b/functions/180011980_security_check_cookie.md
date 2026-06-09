# __security_check_cookie

- ea: `0x180011980`
- end: `0x18001199e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800029e0`
- `0x180003190`
- `0x180003390`
- `0x180004e80`
- `0x180006dd0`
- `0x180008f90`
- `0x18000a360`
- `0x18000d650`
- `0x18000d79c`
- `0x1800100b8`
- `0x180010158`
- `0x1800101e0`
- `0x180010b08`
- `0x180010bac`
- `0x180010c84`
- `0x180010d28`
- `0x180010ed4`

## callees

- `0x18000d490`
- `0x180011980`

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
0x180011980  cmp     rcx, cs:__security_cookie
0x180011987  jnz     short ReportFailure
0x180011989  rol     rcx, 10h
0x18001198d  test    cx, 0FFFFh
0x180011992  jnz     short RestoreRcx
0x180011994  retn
0x180011995  ror     rcx, 10h
0x180011999  jmp     __report_gsfailure
```

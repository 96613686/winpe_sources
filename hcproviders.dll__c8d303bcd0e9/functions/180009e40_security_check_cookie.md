# __security_check_cookie

- ea: `0x180009e40`
- end: `0x180009e5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800018c0`
- `0x180002650`
- `0x180004b10`
- `0x180005f74`
- `0x180006224`
- `0x1800066b8`
- `0x18000692c`
- `0x180006cd4`
- `0x180007004`
- `0x180008098`
- `0x180008410`
- `0x180008dc4`
- `0x180009da8`

## callees

- `0x1800057f0`
- `0x180009e40`

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
0x180009e40  cmp     rcx, cs:__security_cookie
0x180009e47  jnz     short ReportFailure
0x180009e49  rol     rcx, 10h
0x180009e4d  test    cx, 0FFFFh
0x180009e52  jnz     short RestoreRcx
0x180009e54  retn
0x180009e55  ror     rcx, 10h
0x180009e59  jmp     __report_gsfailure
```

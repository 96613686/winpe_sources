# __security_check_cookie

- ea: `0x140001b40`
- end: `0x140001b5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400015f0`
- `0x140001a0c`
- `0x140009410`
- `0x14000b080`

## callees

- `0x1400018e0`
- `0x140001b40`

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
0x140001b40  cmp     rcx, cs:__security_cookie
0x140001b47  jnz     short ReportFailure
0x140001b49  rol     rcx, 10h
0x140001b4d  test    cx, 0FFFFh
0x140001b52  jnz     short RestoreRcx
0x140001b54  retn
0x140001b55  ror     rcx, 10h; StackCookie
0x140001b59  jmp     __report_gsfailure
```

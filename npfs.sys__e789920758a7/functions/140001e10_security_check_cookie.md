# __security_check_cookie

- ea: `0x140001e10`
- end: `0x140001e2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140001cfc`
- `0x14000b15c`
- `0x14000b354`
- `0x140011f60`
- `0x140012180`
- `0x140014ed4`

## callees

- `0x140001aa0`
- `0x140001e10`

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
0x140001e10  cmp     rcx, cs:__security_cookie
0x140001e17  jnz     short ReportFailure
0x140001e19  rol     rcx, 10h
0x140001e1d  test    cx, 0FFFFh
0x140001e22  jnz     short RestoreRcx
0x140001e24  retn
0x140001e25  ror     rcx, 10h; StackCookie
0x140001e29  jmp     __report_gsfailure
```

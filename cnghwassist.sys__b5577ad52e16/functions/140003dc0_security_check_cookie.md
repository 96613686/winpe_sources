# __security_check_cookie

- ea: `0x140003dc0`
- end: `0x140003dde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001430`
- `0x140002270`
- `0x140003c0c`
- `0x14000ab10`
- `0x14000ae34`
- `0x14000b1c0`

## callees

- `0x140001010`
- `0x140003dc0`

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
0x140003dc0  cmp     rcx, cs:__security_cookie
0x140003dc7  jnz     short ReportFailure
0x140003dc9  rol     rcx, 10h
0x140003dcd  test    cx, 0FFFFh
0x140003dd2  jnz     short RestoreRcx
0x140003dd4  retn
0x140003dd5  ror     rcx, 10h; StackCookie
0x140003dd9  jmp     __report_gsfailure
```

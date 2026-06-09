# __security_check_cookie

- ea: `0x1800029d0`
- end: `0x1800029ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ca4`
- `0x1800024b0`
- `0x180002658`
- `0x1800027c0`
- `0x180002938`

## callees

- `0x180001780`
- `0x1800029d0`

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
0x1800029d0  cmp     rcx, cs:__security_cookie
0x1800029d7  jnz     short ReportFailure
0x1800029d9  rol     rcx, 10h
0x1800029dd  test    cx, 0FFFFh
0x1800029e2  jnz     short RestoreRcx
0x1800029e4  retn
0x1800029e5  ror     rcx, 10h
0x1800029e9  jmp     __report_gsfailure
```

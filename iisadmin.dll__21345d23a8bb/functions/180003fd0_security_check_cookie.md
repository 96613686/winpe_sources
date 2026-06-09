# __security_check_cookie

- ea: `0x180003fd0`
- end: `0x180003fee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003118`
- `0x180003f44`

## callees

- `0x180001790`
- `0x180003fd0`

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
0x180003fd0  cmp     rcx, cs:__security_cookie
0x180003fd7  jnz     short ReportFailure
0x180003fd9  rol     rcx, 10h
0x180003fdd  test    cx, 0FFFFh
0x180003fe2  jnz     short RestoreRcx
0x180003fe4  retn
0x180003fe5  ror     rcx, 10h
0x180003fe9  jmp     __report_gsfailure
```

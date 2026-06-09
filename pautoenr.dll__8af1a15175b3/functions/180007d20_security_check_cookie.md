# __security_check_cookie

- ea: `0x180007d20`
- end: `0x180007d3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001100`
- `0x1800015d0`
- `0x180001a60`
- `0x180001d90`
- `0x1800027e0`
- `0x180002bc0`
- `0x180003d10`
- `0x180004270`
- `0x180004720`
- `0x180004fb0`
- `0x180006f94`
- `0x1800070e4`
- `0x180007358`
- `0x1800074b0`
- `0x180007994`
- `0x180007c04`

## callees

- `0x180005860`
- `0x180007d20`

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
0x180007d20  cmp     rcx, cs:__security_cookie
0x180007d27  jnz     short ReportFailure
0x180007d29  rol     rcx, 10h
0x180007d2d  test    cx, 0FFFFh
0x180007d32  jnz     short RestoreRcx
0x180007d34  retn
0x180007d35  ror     rcx, 10h
0x180007d39  jmp     __report_gsfailure
```

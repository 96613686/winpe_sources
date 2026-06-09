# __security_check_cookie

- ea: `0x140002d70`
- end: `0x140002d8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002c3c`
- `0x14000adf0`
- `0x14000ba94`
- `0x14000bb40`
- `0x14000f680`
- `0x14000fcc0`
- `0x1400119a0`
- `0x140018060`
- `0x1400195d0`
- `0x140019af0`
- `0x14001a3d0`

## callees

- `0x140001b70`
- `0x140002d70`

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
0x140002d70  cmp     rcx, cs:__security_cookie
0x140002d77  jnz     short ReportFailure
0x140002d79  rol     rcx, 10h
0x140002d7d  test    cx, 0FFFFh
0x140002d82  jnz     short RestoreRcx
0x140002d84  retn
0x140002d85  ror     rcx, 10h; StackCookie
0x140002d89  jmp     __report_gsfailure
```

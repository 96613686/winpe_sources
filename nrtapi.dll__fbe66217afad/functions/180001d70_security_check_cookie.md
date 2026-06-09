# __security_check_cookie

- ea: `0x180001d70`
- end: `0x180001d8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001120`
- `0x180001d70`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x180001d70  cmp     rcx, cs:__security_cookie
0x180001d77  jnz     short loc_180001D89
0x180001d79  rol     rcx, 10h
0x180001d7d  test    cx, 0FFFFh
0x180001d82  jnz     short loc_180001D85
0x180001d84  retn
0x180001d85  ror     rcx, 10h
0x180001d89  jmp     __report_gsfailure
```

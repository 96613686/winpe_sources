# __security_check_cookie

- ea: `0x180003220`
- end: `0x18000323e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001db0`
- `0x180002660`
- `0x18000318c`

## callees

- `0x180001120`
- `0x180003220`

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
0x180003220  cmp     rcx, cs:__security_cookie
0x180003227  jnz     short loc_180003239
0x180003229  rol     rcx, 10h
0x18000322d  test    cx, 0FFFFh
0x180003232  jnz     short loc_180003235
0x180003234  retn
0x180003235  ror     rcx, 10h
0x180003239  jmp     __report_gsfailure
```

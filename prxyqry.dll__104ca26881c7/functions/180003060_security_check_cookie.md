# __security_check_cookie

- ea: `0x180003060`
- end: `0x18000307e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001d60`
- `0x180002560`
- `0x180002fcc`

## callees

- `0x180001120`
- `0x180003060`

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
0x180003060  cmp     rcx, cs:__security_cookie
0x180003067  jnz     short loc_180003079
0x180003069  rol     rcx, 10h
0x18000306d  test    cx, 0FFFFh
0x180003072  jnz     short loc_180003075
0x180003074  retn
0x180003075  ror     rcx, 10h
0x180003079  jmp     __report_gsfailure
```

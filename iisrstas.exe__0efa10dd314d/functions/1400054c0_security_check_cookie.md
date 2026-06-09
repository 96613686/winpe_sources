# __security_check_cookie

- ea: `0x1400054c0`
- end: `0x1400054de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002a40`
- `0x140002ec0`
- `0x140003110`
- `0x1400031d0`
- `0x1400032a0`
- `0x140003384`
- `0x140003674`
- `0x140003dc4`
- `0x140004114`
- `0x1400042d8`
- `0x140004628`
- `0x1400048b0`
- `0x1400049b0`
- `0x140005074`
- `0x140005168`
- `0x14000540c`

## callees

- `0x1400016c0`
- `0x1400054c0`

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
0x1400054c0  cmp     rcx, cs:__security_cookie
0x1400054c7  jnz     short loc_1400054D9
0x1400054c9  rol     rcx, 10h
0x1400054cd  test    cx, 0FFFFh
0x1400054d2  jnz     short loc_1400054D5
0x1400054d4  retn
0x1400054d5  ror     rcx, 10h
0x1400054d9  jmp     __report_gsfailure
```

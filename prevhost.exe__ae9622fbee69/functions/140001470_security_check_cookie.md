# __security_check_cookie

- ea: `0x140001470`
- end: `0x14000148e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400023cc`
- `0x140002668`
- `0x140002b44`
- `0x140002f74`
- `0x1400036a4`
- `0x140003a1c`
- `0x140005140`
- `0x140005298`
- `0x14000568c`
- `0x140005a80`

## callees

- `0x140001470`
- `0x140001a40`

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
0x140001470  cmp     rcx, cs:__security_cookie
0x140001477  jnz     short loc_140001489
0x140001479  rol     rcx, 10h
0x14000147d  test    cx, 0FFFFh
0x140001482  jnz     short loc_140001485
0x140001484  retn
0x140001485  ror     rcx, 10h; StackCookie
0x140001489  jmp     __report_gsfailure
```

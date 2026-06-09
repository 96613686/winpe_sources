# __security_check_cookie

- ea: `0x140001460`
- end: `0x14000147e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002164`
- `0x140002568`
- `0x140002804`
- `0x140002e78`
- `0x14000321c`
- `0x140003784`
- `0x140003b00`
- `0x1400053bc`
- `0x1400058c0`
- `0x140005c1c`

## callees

- `0x140001460`
- `0x140001a10`

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
0x140001460  cmp     rcx, cs:__security_cookie
0x140001467  jnz     short loc_140001479
0x140001469  rol     rcx, 10h
0x14000146d  test    cx, 0FFFFh
0x140001472  jnz     short loc_140001475
0x140001474  retn
0x140001475  ror     rcx, 10h; StackCookie
0x140001479  jmp     __report_gsfailure
```

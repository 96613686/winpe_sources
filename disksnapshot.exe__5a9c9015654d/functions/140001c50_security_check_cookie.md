# __security_check_cookie

- ea: `0x140001c50`
- end: `0x140001c6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001460`
- `0x1400016e0`
- `0x140001d68`
- `0x140003154`
- `0x1400032c4`
- `0x140005444`
- `0x140006060`
- `0x140006120`
- `0x140006198`
- `0x140006424`
- `0x140006b20`
- `0x140006c30`
- `0x140007534`
- `0x1400079b0`
- `0x140007c84`
- `0x140008590`
- `0x140008a38`
- `0x14000a400`
- `0x14000a604`
- `0x14000a854`
- `0x14000ac0c`
- `0x14000b144`
- `0x14000b7dc`
- `0x14000ba74`

## callees

- `0x140001c50`
- `0x140001d00`

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
0x140001c50  cmp     rcx, cs:__security_cookie
0x140001c57  jnz     short loc_140001C69
0x140001c59  rol     rcx, 10h
0x140001c5d  test    cx, 0FFFFh
0x140001c62  jnz     short loc_140001C65
0x140001c64  retn
0x140001c65  ror     rcx, 10h; StackCookie
0x140001c69  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x1400020c0`
- end: `0x1400020de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001720`
- `0x140002b00`
- `0x140002d30`
- `0x1400038cc`
- `0x140003e9c`
- `0x1400041f0`
- `0x140004324`
- `0x14000481c`
- `0x1400049c8`
- `0x140005220`

## callees

- `0x1400020c0`
- `0x140002620`

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
0x1400020c0  cmp     rcx, cs:__security_cookie
0x1400020c7  jnz     short loc_1400020D9
0x1400020c9  rol     rcx, 10h
0x1400020cd  test    cx, 0FFFFh
0x1400020d2  jnz     short loc_1400020D5
0x1400020d4  retn
0x1400020d5  ror     rcx, 10h; StackCookie
0x1400020d9  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x1400187e0`
- end: `0x1400187fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001098`
- `0x140001414`
- `0x140001538`
- `0x1400015fc`
- `0x1400016f4`
- `0x1400018cc`
- `0x140001990`
- `0x140001a84`
- `0x140001b9c`
- `0x140001c44`
- `0x140001d68`
- `0x140003adc`
- `0x140003d70`
- `0x140004bd0`
- `0x140005600`
- `0x140005b34`
- `0x140006c94`
- `0x140007064`
- `0x1400076e4`
- `0x140007ff8`
- `0x14000a19c`
- `0x14000aa08`
- `0x14000b69c`
- `0x14000c360`
- `0x14000c47c`
- `0x14000dab4`
- `0x14000dd30`
- `0x14000e924`
- `0x14000f65c`
- `0x140010050`
- `0x140010470`
- `0x1400105d8`
- `0x140010e70`
- `0x14001150c`
- `0x140011fec`
- `0x14001248c`
- `0x140013330`
- `0x140013b84`
- `0x1400144a4`
- `0x140014a8c`
- `0x140014d0c`
- `0x14001556c`
- `0x140015e78`
- `0x140016230`
- `0x140016c98`
- `0x140017a80`
- `0x140017b80`
- `0x140017e70`
- `0x14001841c`

## callees

- `0x140002b10`
- `0x1400187e0`

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
0x1400187e0  cmp     rcx, cs:__security_cookie
0x1400187e7  jnz     short loc_1400187F9
0x1400187e9  rol     rcx, 10h
0x1400187ed  test    cx, 0FFFFh
0x1400187f2  jnz     short loc_1400187F5
0x1400187f4  retn
0x1400187f5  ror     rcx, 10h
0x1400187f9  jmp     __report_gsfailure
```

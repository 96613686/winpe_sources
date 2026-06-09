# __security_check_cookie

- ea: `0x140009820`
- end: `0x14000983e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400011e4`
- `0x140003ce4`
- `0x140003e10`
- `0x140003ea0`
- `0x140004444`
- `0x140004768`
- `0x1400049a4`
- `0x140004ca8`
- `0x140005084`
- `0x1400052a0`
- `0x140005490`
- `0x14000580c`
- `0x1400064f0`
- `0x140006e10`
- `0x140007110`
- `0x140007568`
- `0x1400078f0`
- `0x140008280`
- `0x140008300`
- `0x140008b10`
- `0x1400094c4`
- `0x140009700`

## callees

- `0x140003200`
- `0x140009820`

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
0x140009820  cmp     rcx, cs:__security_cookie
0x140009827  jnz     short loc_140009839
0x140009829  rol     rcx, 10h
0x14000982d  test    cx, 0FFFFh
0x140009832  jnz     short loc_140009835
0x140009834  retn
0x140009835  ror     rcx, 10h
0x140009839  jmp     __report_gsfailure
```

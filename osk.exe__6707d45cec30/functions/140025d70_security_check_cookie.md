# __security_check_cookie

- ea: `0x140025d70`
- end: `0x140025d8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `101`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400010c0`
- `0x140001368`
- `0x140001640`
- `0x140001714`
- `0x1400017d8`
- `0x140001a8c`
- `0x140002e3c`
- `0x140003c6c`
- `0x140003f00`
- `0x140005730`
- `0x14000589c`
- `0x140005d5c`
- `0x1400065b4`
- `0x1400069f4`
- `0x140007f54`
- `0x140008a1c`
- `0x140008c0c`
- `0x1400092e8`
- `0x14000a77c`
- `0x14000b574`
- `0x14000b8cc`
- `0x14000bd74`
- `0x14000d1bc`
- `0x14000d390`
- `0x14000d650`
- `0x14000d838`
- `0x14000e16c`
- `0x14000e6a0`
- `0x14000e990`
- `0x14000edf0`
- `0x14000eeb4`
- `0x14000f75c`
- `0x14000fa10`
- `0x14001025c`
- `0x140010468`
- `0x140010968`
- `0x140010a40`
- `0x140010c78`
- `0x140010ed8`
- `0x140011178`
- `0x140011368`
- `0x1400118d0`
- `0x140011d2c`
- `0x140013004`
- `0x1400138fc`
- `0x140013b1c`
- `0x140013eac`
- `0x1400144fc`
- `0x140014634`

## callees

- `0x1400028e0`
- `0x140025d70`

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
0x140025d70  cmp     rcx, cs:__security_cookie
0x140025d77  jnz     short loc_140025D89
0x140025d79  rol     rcx, 10h
0x140025d7d  test    cx, 0FFFFh
0x140025d82  jnz     short loc_140025D85
0x140025d84  retn
0x140025d85  ror     rcx, 10h
0x140025d89  jmp     __report_gsfailure
```

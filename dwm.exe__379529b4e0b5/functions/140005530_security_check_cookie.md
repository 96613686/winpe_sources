# __security_check_cookie

- ea: `0x140005530`
- end: `0x14000554e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012e0`
- `0x1400013b4`
- `0x140001478`
- `0x14000172c`
- `0x140001a24`
- `0x140001c28`
- `0x140001cac`
- `0x1400023dc`
- `0x1400031e0`
- `0x140003350`
- `0x140003ab0`
- `0x1400068f0`
- `0x140006f40`
- `0x1400071d4`
- `0x140007adc`
- `0x140007c48`
- `0x140007e14`
- `0x140008a44`
- `0x140008d5c`
- `0x140009dac`
- `0x14000a1b0`
- `0x14000b060`
- `0x14000bcec`
- `0x14000bf74`
- `0x14000c260`
- `0x14000cc90`
- `0x14000ce0c`
- `0x14000d534`
- `0x14000d87c`
- `0x14000e1f4`
- `0x14000e324`
- `0x14000e7e4`
- `0x14000e994`
- `0x14000ed0c`
- `0x14000ee44`
- `0x14000ef18`
- `0x14000f500`
- `0x14000f724`

## callees

- `0x140005530`
- `0x140005810`

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
0x140005530  cmp     rcx, cs:__security_cookie
0x140005537  jnz     short loc_140005549
0x140005539  rol     rcx, 10h
0x14000553d  test    cx, 0FFFFh
0x140005542  jnz     short loc_140005545
0x140005544  retn
0x140005545  ror     rcx, 10h; StackCookie
0x140005549  jmp     __report_gsfailure
```

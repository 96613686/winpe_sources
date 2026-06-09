# __security_check_cookie

- ea: `0x14001e050`
- end: `0x14001e06e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x1400015b4`
- `0x14000188c`
- `0x140001b48`
- `0x140001e44`
- `0x140002124`
- `0x1400026a0`
- `0x1400029e0`
- `0x140003660`
- `0x140003e40`
- `0x1400042e0`
- `0x140004660`
- `0x140004ab0`
- `0x140006070`
- `0x1400061a0`
- `0x140006d00`
- `0x140006fd0`
- `0x140007250`
- `0x140007ce0`
- `0x140008280`
- `0x140009070`
- `0x1400098a0`
- `0x140009ca0`
- `0x140009f30`
- `0x14000a0c0`
- `0x14000a310`
- `0x14000a7b0`
- `0x14000ad90`
- `0x14000af70`
- `0x14000b820`
- `0x14000c350`
- `0x14000cfdc`
- `0x14000d7c0`
- `0x14000e1e0`
- `0x14000e354`
- `0x14000e5e4`
- `0x14000f200`
- `0x14000f4b8`
- `0x140011258`
- `0x1400114ec`
- `0x140011a6c`
- `0x140011e14`
- `0x14001212c`
- `0x1400137f0`
- `0x140013950`
- `0x1400140c8`
- `0x1400143a0`
- `0x140014764`
- `0x140014a18`

## callees

- `0x1400105f0`
- `0x14001e050`

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
0x14001e050  cmp     rcx, cs:__security_cookie
0x14001e057  jnz     short loc_14001E069
0x14001e059  rol     rcx, 10h
0x14001e05d  test    cx, 0FFFFh
0x14001e062  jnz     short loc_14001E065
0x14001e064  retn
0x14001e065  ror     rcx, 10h
0x14001e069  jmp     __report_gsfailure
```

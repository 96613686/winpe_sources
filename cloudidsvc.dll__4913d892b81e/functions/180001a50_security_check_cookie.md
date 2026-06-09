# __security_check_cookie

- ea: `0x180001a50`
- end: `0x180001a6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000110c`
- `0x180001348`
- `0x180002708`
- `0x180003394`
- `0x18000342c`
- `0x18000399c`
- `0x180003c48`
- `0x180004d28`
- `0x180004ffc`
- `0x180005680`
- `0x180005ac0`
- `0x180006e94`
- `0x1800078c8`
- `0x180008250`
- `0x1800085d0`
- `0x180009e80`
- `0x18000adb8`
- `0x18000b1d0`
- `0x18000b67c`
- `0x18000ba60`
- `0x18000ce9c`
- `0x18000e0b0`
- `0x18000e4b0`
- `0x18000e668`
- `0x18000e8e8`
- `0x18000eaf4`
- `0x18000ed90`
- `0x18000f4ac`
- `0x18000f7cc`
- `0x18000ff0c`
- `0x18000ff78`
- `0x18001063c`

## callees

- `0x180001a50`
- `0x180002060`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180001a50  cmp     rcx, cs:__security_cookie
0x180001a57  jnz     short ReportFailure
0x180001a59  rol     rcx, 10h
0x180001a5d  test    cx, 0FFFFh
0x180001a62  jnz     short RestoreRcx
0x180001a64  retn
0x180001a65  ror     rcx, 10h; StackCookie
0x180001a69  jmp     __report_gsfailure
```

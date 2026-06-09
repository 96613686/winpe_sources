# __security_check_cookie

- ea: `0x18001a5e0`
- end: `0x18001a5fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `46`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002400`
- `0x18000252c`
- `0x180002a24`
- `0x180002cb8`
- `0x1800038d0`
- `0x180003a3c`
- `0x180003c08`
- `0x1800042f4`
- `0x1800046a8`
- `0x180005738`
- `0x180005920`
- `0x180005fc0`
- `0x180006fb4`
- `0x180008110`
- `0x1800082f8`
- `0x180008efc`
- `0x18000980c`
- `0x1800099a8`
- `0x180009cec`
- `0x18000ac58`
- `0x18000af48`
- `0x18000b05c`
- `0x18000b1f4`
- `0x18000b44c`
- `0x18000bbbc`
- `0x18000bfac`
- `0x18000c224`
- `0x18000f7c8`
- `0x180010718`
- `0x180010adc`
- `0x180010eac`
- `0x180011424`
- `0x180011a04`
- `0x18001317c`
- `0x1800140c4`
- `0x180014660`
- `0x180014814`
- `0x1800148c4`
- `0x1800149bc`
- `0x18001505c`
- `0x18001692c`
- `0x180016c38`
- `0x180017078`
- `0x1800171dc`
- `0x18001762c`
- `0x1800177d4`

## callees

- `0x180001de0`
- `0x18001a5e0`

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
0x18001a5e0  cmp     rcx, cs:__security_cookie
0x18001a5e7  jnz     short ReportFailure
0x18001a5e9  rol     rcx, 10h
0x18001a5ed  test    cx, 0FFFFh
0x18001a5f2  jnz     short RestoreRcx
0x18001a5f4  retn
0x18001a5f5  ror     rcx, 10h
0x18001a5f9  jmp     __report_gsfailure
```

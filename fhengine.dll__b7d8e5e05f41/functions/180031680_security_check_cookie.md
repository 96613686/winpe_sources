# __security_check_cookie

- ea: `0x180031680`
- end: `0x18003169e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `58`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001540`
- `0x180002830`
- `0x18000298c`
- `0x180003aec`
- `0x1800051d4`
- `0x180005658`
- `0x18000576c`
- `0x1800058e0`
- `0x180005a90`
- `0x1800064f0`
- `0x180006664`
- `0x180006b44`
- `0x180009d70`
- `0x18000cafc`
- `0x18000d348`
- `0x18000f55c`
- `0x18000fde8`
- `0x180012b44`
- `0x180016c44`
- `0x180016da0`
- `0x18001768c`
- `0x180018ee0`
- `0x180019dd0`
- `0x18001cb74`
- `0x18001eaf0`
- `0x18001fee4`
- `0x180021240`
- `0x180021bc0`
- `0x1800220a4`
- `0x180022124`
- `0x1800221c0`
- `0x180023330`
- `0x1800236d0`
- `0x180024dd0`
- `0x1800256d0`
- `0x180025a40`
- `0x180025db0`
- `0x180026f64`
- `0x180027200`
- `0x180027f50`
- `0x1800280b8`
- `0x180028848`
- `0x18002a094`
- `0x18002a4a4`
- `0x18002b9ec`
- `0x18002bcb4`
- `0x18002c3d4`
- `0x18002db00`
- `0x18002e7f0`

## callees

- `0x180002000`
- `0x180031680`

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
0x180031680  cmp     rcx, cs:__security_cookie
0x180031687  jnz     short ReportFailure
0x180031689  rol     rcx, 10h
0x18003168d  test    cx, 0FFFFh
0x180031692  jnz     short RestoreRcx
0x180031694  retn
0x180031695  ror     rcx, 10h
0x180031699  jmp     __report_gsfailure
```

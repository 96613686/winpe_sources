# __security_check_cookie

- ea: `0x18002b960`
- end: `0x18002b97e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `90`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010f8`
- `0x180001188`
- `0x180001290`
- `0x180001368`
- `0x180001474`
- `0x180001564`
- `0x18000160c`
- `0x180001724`
- `0x180001868`
- `0x18000192c`
- `0x1800019fc`
- `0x180001b3c`
- `0x180001bfc`
- `0x180001ca4`
- `0x180001d68`
- `0x180001f98`
- `0x1800020bc`
- `0x1800021f0`
- `0x1800022b0`
- `0x180002374`
- `0x180002444`
- `0x18000251c`
- `0x180002630`
- `0x180002720`
- `0x180002844`
- `0x180002914`
- `0x180002a04`
- `0x180002b04`
- `0x180002cbc`
- `0x180002dfc`
- `0x180002e4c`
- `0x180002f18`
- `0x180002fc8`
- `0x18000304c`
- `0x180004850`
- `0x1800049a4`
- `0x180004cbc`
- `0x1800052d0`
- `0x180005504`
- `0x180006240`
- `0x180006950`
- `0x180006a40`
- `0x180006db4`
- `0x180007230`
- `0x1800074cc`
- `0x1800079a8`
- `0x180007b44`
- `0x180008a5c`
- `0x180008fa4`

## callees

- `0x180003b00`
- `0x18002b960`

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
0x18002b960  cmp     rcx, cs:__security_cookie
0x18002b967  jnz     short ReportFailure
0x18002b969  rol     rcx, 10h
0x18002b96d  test    cx, 0FFFFh
0x18002b972  jnz     short RestoreRcx
0x18002b974  retn
0x18002b975  ror     rcx, 10h
0x18002b979  jmp     __report_gsfailure
```

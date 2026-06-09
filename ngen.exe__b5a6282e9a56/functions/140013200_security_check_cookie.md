# __security_check_cookie

- ea: `0x140013200`
- end: `0x14001321e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001374`
- `0x1400016f4`
- `0x140001950`
- `0x140001bac`
- `0x140001e08`
- `0x140002168`
- `0x140004694`
- `0x140004b08`
- `0x140006188`
- `0x1400068ec`
- `0x140006a5c`
- `0x140006ee4`
- `0x140006fb8`
- `0x140007100`
- `0x140007388`
- `0x14000793c`
- `0x140007bac`
- `0x140008548`
- `0x140009104`
- `0x140009a78`
- `0x14000a2ac`
- `0x14000a3bc`
- `0x14000a610`
- `0x14000aa04`
- `0x14000b010`
- `0x14000b124`
- `0x14000b578`
- `0x14000b898`
- `0x14000bf84`
- `0x14000c044`
- `0x14000cef0`
- `0x14000f1b8`
- `0x14000f8e0`
- `0x14000fad4`
- `0x140010938`
- `0x140010c68`
- `0x140010e48`
- `0x14001281c`
- `0x140012c84`
- `0x140013dc0`

## callees

- `0x140013200`
- `0x140013260`

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
0x140013200  cmp     rcx, cs:__security_cookie
0x140013207  jnz     short ReportFailure
0x140013209  rol     rcx, 10h
0x14001320d  test    cx, 0FFFFh
0x140013212  jnz     short RestoreRcx
0x140013214  retn
0x140013215  ror     rcx, 10h
0x140013219  jmp     __report_gsfailure
```

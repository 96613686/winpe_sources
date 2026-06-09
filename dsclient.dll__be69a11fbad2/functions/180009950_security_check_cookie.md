# __security_check_cookie

- ea: `0x180009950`
- end: `0x18000996e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cf0`
- `0x180002350`
- `0x18000384c`
- `0x1800038d4`
- `0x1800040f8`
- `0x180004394`
- `0x180004ce0`
- `0x180004e48`
- `0x180005074`
- `0x180005814`
- `0x180005b2c`
- `0x180006bb0`
- `0x180006e04`
- `0x180007520`
- `0x180007820`
- `0x180008358`
- `0x180008f68`
- `0x180009144`
- `0x180009430`
- `0x1800095e8`
- `0x1800097dc`
- `0x1800098a8`

## callees

- `0x180002f50`
- `0x180009950`

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
0x180009950  cmp     rcx, cs:__security_cookie
0x180009957  jnz     short ReportFailure
0x180009959  rol     rcx, 10h
0x18000995d  test    cx, 0FFFFh
0x180009962  jnz     short RestoreRcx
0x180009964  retn
0x180009965  ror     rcx, 10h
0x180009969  jmp     __report_gsfailure
```

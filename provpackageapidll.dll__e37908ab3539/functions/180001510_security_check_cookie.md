# __security_check_cookie

- ea: `0x180001510`
- end: `0x18000152e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000283c`
- `0x180002ad0`
- `0x180003068`
- `0x180003438`
- `0x1800039a4`
- `0x180003d20`
- `0x18000555c`
- `0x180005a40`
- `0x180007040`
- `0x1800078e8`
- `0x180007f78`
- `0x18000a040`
- `0x18000b7b0`
- `0x18000d350`
- `0x18000d708`
- `0x18000e1cc`
- `0x18000e948`
- `0x18000fc8c`
- `0x180012b94`
- `0x180014870`
- `0x180016050`
- `0x180016710`
- `0x180017898`
- `0x180018300`

## callees

- `0x180001510`
- `0x180001aa0`

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
0x180001510  cmp     rcx, cs:__security_cookie
0x180001517  jnz     short ReportFailure
0x180001519  rol     rcx, 10h
0x18000151d  test    cx, 0FFFFh
0x180001522  jnz     short RestoreRcx
0x180001524  retn
0x180001525  ror     rcx, 10h; StackCookie
0x180001529  jmp     __report_gsfailure
```

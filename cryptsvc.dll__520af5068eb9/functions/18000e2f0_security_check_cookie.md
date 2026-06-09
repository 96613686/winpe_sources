# __security_check_cookie

- ea: `0x18000e2f0`
- end: `0x18000e30e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800028f0`
- `0x180003f00`
- `0x180004c90`
- `0x180005bd0`
- `0x180006db0`
- `0x180007370`
- `0x180007af0`
- `0x180007dc0`
- `0x1800090b0`
- `0x180009854`
- `0x18000ae70`
- `0x18000b02c`
- `0x18000b4a4`
- `0x18000c18c`
- `0x18000ca64`
- `0x18000cb10`
- `0x18000d3fc`
- `0x18000f51c`
- `0x18000f6c4`
- `0x18001065c`
- `0x180011258`
- `0x180011390`
- `0x180011458`
- `0x180011a04`
- `0x180011ca0`
- `0x18001217c`
- `0x1800122e4`
- `0x1800124ac`
- `0x180012f24`
- `0x1800132d8`
- `0x1800144bc`
- `0x180015048`
- `0x180015a7c`
- `0x180015c74`
- `0x180016320`
- `0x1800167c0`
- `0x180016cf4`
- `0x180017020`
- `0x180017410`

## callees

- `0x18000e2f0`
- `0x18000e880`

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
0x18000e2f0  cmp     rcx, cs:__security_cookie
0x18000e2f7  jnz     short ReportFailure
0x18000e2f9  rol     rcx, 10h
0x18000e2fd  test    cx, 0FFFFh
0x18000e302  jnz     short RestoreRcx
0x18000e304  retn
0x18000e305  ror     rcx, 10h; StackCookie
0x18000e309  jmp     __report_gsfailure
```

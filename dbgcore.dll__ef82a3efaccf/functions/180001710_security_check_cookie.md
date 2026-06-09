# __security_check_cookie

- ea: `0x180001710`
- end: `0x18000172e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `97`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002210`
- `0x18000335c`
- `0x180003af8`
- `0x180003da0`
- `0x180004c68`
- `0x18000500c`
- `0x1800058d0`
- `0x180005ea8`
- `0x1800062f4`
- `0x180007470`
- `0x18000825c`
- `0x180008738`
- `0x180008f7c`
- `0x1800098a8`
- `0x18000b27c`
- `0x18000bd54`
- `0x18000c19c`
- `0x18000c54c`
- `0x18000c67c`
- `0x18000d228`
- `0x18000d6f4`
- `0x18000dc78`
- `0x18000df34`
- `0x18000e11c`
- `0x18000e438`
- `0x18000e6cc`
- `0x18000e898`
- `0x18000ea58`
- `0x18000eb24`
- `0x18000ec70`
- `0x18000efb4`
- `0x18000f180`
- `0x18000f580`
- `0x18000f6a8`
- `0x18000f8e8`
- `0x1800100f0`
- `0x1800106fc`
- `0x180010974`
- `0x180010a7c`
- `0x180010bbc`
- `0x180011430`
- `0x180011e08`
- `0x180012214`
- `0x1800125a4`
- `0x180012780`
- `0x180012e20`
- `0x180013020`
- `0x1800132b0`
- `0x180013340`
- `0x180013510`

## callees

- `0x180001710`
- `0x180001b60`

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
0x180001710  cmp     rcx, cs:__security_cookie
0x180001717  jnz     short ReportFailure
0x180001719  rol     rcx, 10h
0x18000171d  test    cx, 0FFFFh
0x180001722  jnz     short RestoreRcx
0x180001724  retn
0x180001725  ror     rcx, 10h; StackCookie
0x180001729  jmp     __report_gsfailure
```

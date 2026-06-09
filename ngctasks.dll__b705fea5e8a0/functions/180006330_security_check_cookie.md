# __security_check_cookie

- ea: `0x180006330`
- end: `0x18000634e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `59`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800012cc`
- `0x180001310`
- `0x1800013bc`
- `0x1800016a8`
- `0x1800019bc`
- `0x180001a4c`
- `0x180001b0c`
- `0x180001bec`
- `0x180001e90`
- `0x180002188`
- `0x18000224c`
- `0x180002320`
- `0x180002548`
- `0x180002a08`
- `0x180002e70`
- `0x180002ec8`
- `0x1800031b0`
- `0x180003f10`
- `0x1800072dc`
- `0x180007b54`
- `0x180007de8`
- `0x180009508`
- `0x18000976c`
- `0x180009e70`
- `0x18000a3b8`
- `0x18000a884`
- `0x18000b06c`
- `0x18000c23c`
- `0x18000e11c`
- `0x18000e57c`
- `0x18000e750`
- `0x18000f0f4`
- `0x18000f8c0`
- `0x180010a84`
- `0x180010b28`
- `0x180011ee0`
- `0x1800120cc`
- `0x1800126e4`
- `0x1800149c0`
- `0x180014ea4`
- `0x1800151a0`
- `0x180015748`
- `0x180016b24`
- `0x180017cfc`
- `0x1800180d4`
- `0x1800189d4`
- `0x1800194b0`
- `0x180019b5c`
- `0x18001ada0`

## callees

- `0x180006330`
- `0x180006a30`

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
0x180006330  cmp     rcx, cs:__security_cookie
0x180006337  jnz     short ReportFailure
0x180006339  rol     rcx, 10h
0x18000633d  test    cx, 0FFFFh
0x180006342  jnz     short RestoreRcx
0x180006344  retn
0x180006345  ror     rcx, 10h; StackCookie
0x180006349  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x180001770`
- end: `0x18000178e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `52`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800022c0`
- `0x1800025b0`
- `0x180002930`
- `0x180002de0`
- `0x180002e70`
- `0x1800032fc`
- `0x180003938`
- `0x180003be4`
- `0x180004528`
- `0x18000495c`
- `0x180005054`
- `0x1800053d0`
- `0x180006f7c`
- `0x1800074d0`
- `0x1800077f8`
- `0x180007878`
- `0x180007920`
- `0x1800082f0`
- `0x1800083e8`
- `0x180008500`
- `0x180008a70`
- `0x180008f2c`
- `0x1800090f0`
- `0x180009300`
- `0x1800097f8`
- `0x180009f30`
- `0x18000a068`
- `0x18000a4b8`
- `0x18000b3b0`
- `0x18000c574`
- `0x18000c8ec`
- `0x18000d4d8`
- `0x18000e100`
- `0x18000efe0`
- `0x18000f1ac`
- `0x18000f814`
- `0x18000fe14`
- `0x180011a28`
- `0x180011cc0`
- `0x1800125f4`
- `0x180012770`
- `0x180012890`
- `0x180012b44`
- `0x180012e44`
- `0x180013220`
- `0x180013438`
- `0x180013954`
- `0x180013a88`
- `0x180013c00`
- `0x180013d28`

## callees

- `0x180001770`
- `0x180001da0`

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
0x180001770  cmp     rcx, cs:__security_cookie
0x180001777  jnz     short ReportFailure
0x180001779  rol     rcx, 10h
0x18000177d  test    cx, 0FFFFh
0x180001782  jnz     short RestoreRcx
0x180001784  retn
0x180001785  ror     rcx, 10h; StackCookie
0x180001789  jmp     __report_gsfailure
```

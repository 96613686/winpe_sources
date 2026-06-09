# __security_check_cookie

- ea: `0x18001b340`
- end: `0x18001b35e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `63`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010dc`
- `0x180001390`
- `0x180001688`
- `0x1800018b8`
- `0x180001bcc`
- `0x180003cd8`
- `0x180003f6c`
- `0x180004548`
- `0x1800046dc`
- `0x180004b24`
- `0x180004f20`
- `0x180006070`
- `0x1800067b4`
- `0x1800081bc`
- `0x180009220`
- `0x18000949c`
- `0x180009b04`
- `0x18000aae0`
- `0x18000ae48`
- `0x18000b500`
- `0x18000bf80`
- `0x18000c040`
- `0x18000c158`
- `0x18000c3e4`
- `0x18000c46c`
- `0x18000c680`
- `0x18000d68c`
- `0x18000da68`
- `0x18000dd00`
- `0x18000e364`
- `0x18000e91c`
- `0x18000eacc`
- `0x18000ed70`
- `0x18000f740`
- `0x18000fe6c`
- `0x180011450`
- `0x18001182c`
- `0x180011914`
- `0x180011b38`
- `0x180011bdc`
- `0x180013400`
- `0x180013978`
- `0x180014050`
- `0x1800143c4`
- `0x1800145dc`
- `0x180014a18`
- `0x1800180f8`
- `0x180018420`
- `0x1800184ec`

## callees

- `0x180002df0`
- `0x18001b340`

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
0x18001b340  cmp     rcx, cs:__security_cookie
0x18001b347  jnz     short ReportFailure
0x18001b349  rol     rcx, 10h
0x18001b34d  test    cx, 0FFFFh
0x18001b352  jnz     short RestoreRcx
0x18001b354  retn
0x18001b355  ror     rcx, 10h
0x18001b359  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x180001bb0`
- end: `0x180001bce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `87`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x18000116c`
- `0x1800011d0`
- `0x180001318`
- `0x180001394`
- `0x180001478`
- `0x180001544`
- `0x1800033a8`
- `0x180003db4`
- `0x180003ea8`
- `0x180004d28`
- `0x180004e90`
- `0x1800050d0`
- `0x180005200`
- `0x180005850`
- `0x180005bf0`
- `0x180005dd0`
- `0x180005eb0`
- `0x180005fd0`
- `0x180006250`
- `0x1800064a0`
- `0x1800066d0`
- `0x180006a10`
- `0x180006ac0`
- `0x180006c30`
- `0x180006df0`
- `0x180007210`
- `0x180007360`
- `0x180007b00`
- `0x180007e20`
- `0x180008bd4`
- `0x180008f38`
- `0x180009768`
- `0x18000a6e8`
- `0x18000ae3c`
- `0x18000bffc`
- `0x18000d0a4`
- `0x18000d248`
- `0x18000d358`
- `0x18000d4c0`
- `0x18000db90`
- `0x18000dd98`
- `0x18000e4e0`
- `0x18000e778`
- `0x18000ea70`
- `0x18000ebc0`
- `0x18000ecfc`
- `0x18000ef68`
- `0x18000f830`
- `0x18000fbc0`

## callees

- `0x180001bb0`
- `0x180001be0`

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
0x180001bb0  cmp     rcx, cs:__security_cookie
0x180001bb7  jnz     short ReportFailure
0x180001bb9  rol     rcx, 10h
0x180001bbd  test    cx, 0FFFFh
0x180001bc2  jnz     short RestoreRcx
0x180001bc4  retn
0x180001bc5  ror     rcx, 10h; StackCookie
0x180001bc9  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x180018500`
- end: `0x18001851e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e4c`
- `0x180001f9c`
- `0x180002454`
- `0x18000326c`
- `0x180003598`
- `0x1800036e8`
- `0x180003878`
- `0x180003a3c`
- `0x180004304`
- `0x1800043dc`
- `0x180004d50`
- `0x180005e5c`
- `0x1800064e0`
- `0x18000689c`
- `0x1800082ac`
- `0x180008aa0`
- `0x180008bb0`
- `0x180008cc0`
- `0x180008e7c`
- `0x1800093cc`
- `0x18000b1a4`
- `0x18000ce60`
- `0x18000e958`
- `0x18000f520`
- `0x180012068`
- `0x180012408`
- `0x180013f44`
- `0x180015260`
- `0x180015bd8`
- `0x180015fa0`
- `0x180016224`
- `0x180017178`

## callees

- `0x1800016f0`
- `0x180018500`

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
0x180018500  cmp     rcx, cs:__security_cookie
0x180018507  jnz     short ReportFailure
0x180018509  rol     rcx, 10h
0x18001850d  test    cx, 0FFFFh
0x180018512  jnz     short RestoreRcx
0x180018514  retn
0x180018515  ror     rcx, 10h
0x180018519  jmp     __report_gsfailure
```

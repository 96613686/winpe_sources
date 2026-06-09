# __security_check_cookie

- ea: `0x18001f690`
- end: `0x18001f6ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `68`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800011dc`
- `0x180002910`
- `0x180002a3c`
- `0x180002f94`
- `0x180003250`
- `0x180003f40`
- `0x1800046ec`
- `0x180004e34`
- `0x180004fdc`
- `0x1800054a4`
- `0x180005ae4`
- `0x180005de8`
- `0x180005f38`
- `0x1800060c8`
- `0x1800062ac`
- `0x180006a5c`
- `0x180006c60`
- `0x180007dbc`
- `0x180008cb8`
- `0x180009060`
- `0x180009600`
- `0x1800098b0`
- `0x18000a200`
- `0x18000a310`
- `0x18000a470`
- `0x18000a730`
- `0x18000a9e0`
- `0x18000adc0`
- `0x18000afb0`
- `0x18000b0e0`
- `0x18000b240`
- `0x18000b3c0`
- `0x18000c440`
- `0x18000d22c`
- `0x18000d8f0`
- `0x18000e2d4`
- `0x18000ec70`
- `0x18000f8b8`
- `0x18000fa40`
- `0x18000fdb8`
- `0x180010320`
- `0x18001084c`
- `0x1800131d8`
- `0x180014340`
- `0x1800151b0`
- `0x180015358`
- `0x180015590`
- `0x180016290`
- `0x1800165c0`

## callees

- `0x1800022e0`
- `0x18001f690`

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
0x18001f690  cmp     rcx, cs:__security_cookie
0x18001f697  jnz     short ReportFailure
0x18001f699  rol     rcx, 10h
0x18001f69d  test    cx, 0FFFFh
0x18001f6a2  jnz     short RestoreRcx
0x18001f6a4  retn
0x18001f6a5  ror     rcx, 10h
0x18001f6a9  jmp     __report_gsfailure
```

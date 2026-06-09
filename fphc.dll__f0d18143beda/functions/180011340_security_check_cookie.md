# __security_check_cookie

- ea: `0x180011340`
- end: `0x18001135e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800028fc`
- `0x180002a4c`
- `0x1800030ac`
- `0x1800037f4`
- `0x18000399c`
- `0x180003e64`
- `0x1800044a4`
- `0x1800047a8`
- `0x1800048f8`
- `0x180004a88`
- `0x180004c68`
- `0x18000541c`
- `0x180005620`
- `0x180006970`
- `0x180008b74`
- `0x180009110`
- `0x1800098b0`
- `0x18000b23c`
- `0x18000b498`
- `0x18000c154`
- `0x18000ca08`
- `0x18000f0b4`
- `0x18000f124`
- `0x18000f2d8`
- `0x18000f7f0`
- `0x18000fb38`
- `0x1800107e8`
- `0x180010830`
- `0x180010c94`

## callees

- `0x180002260`
- `0x180011340`

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
0x180011340  cmp     rcx, cs:__security_cookie
0x180011347  jnz     short ReportFailure
0x180011349  rol     rcx, 10h
0x18001134d  test    cx, 0FFFFh
0x180011352  jnz     short RestoreRcx
0x180011354  retn
0x180011355  ror     rcx, 10h
0x180011359  jmp     __report_gsfailure
```

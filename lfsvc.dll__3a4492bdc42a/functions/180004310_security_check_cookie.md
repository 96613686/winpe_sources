# __security_check_cookie

- ea: `0x180004310`
- end: `0x18000432e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001158`
- `0x1800012f0`
- `0x1800013ac`
- `0x180001a20`
- `0x180001e20`
- `0x1800022e0`
- `0x18000301c`
- `0x18000330c`
- `0x180003494`
- `0x1800035a4`
- `0x180003de8`
- `0x1800051d8`
- `0x1800053b4`
- `0x180005670`
- `0x180006308`
- `0x180006498`
- `0x180006698`
- `0x180006954`
- `0x180006d54`
- `0x18000706c`
- `0x180007374`
- `0x180007528`
- `0x180007b60`
- `0x180007bcc`
- `0x180007f50`
- `0x180008208`
- `0x180008274`
- `0x18000837c`
- `0x1800085ac`
- `0x180008600`
- `0x180008658`
- `0x1800086dc`
- `0x180009200`
- `0x18000935c`
- `0x1800097f4`
- `0x18000a1a0`
- `0x18000a3a8`
- `0x18000a62c`
- `0x18000b274`

## callees

- `0x180004310`
- `0x180004910`

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
0x180004310  cmp     rcx, cs:__security_cookie
0x180004317  jnz     short ReportFailure
0x180004319  rol     rcx, 10h
0x18000431d  test    cx, 0FFFFh
0x180004322  jnz     short RestoreRcx
0x180004324  retn
0x180004325  ror     rcx, 10h; StackCookie
0x180004329  jmp     __report_gsfailure
```

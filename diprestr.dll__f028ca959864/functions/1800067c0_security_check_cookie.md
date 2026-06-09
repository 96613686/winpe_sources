# __security_check_cookie

- ea: `0x1800067c0`
- end: `0x1800067de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001af4`
- `0x180001cd4`
- `0x180001dc8`
- `0x180002604`
- `0x180002dd0`
- `0x1800047a4`
- `0x180004f8c`
- `0x1800057cc`
- `0x180005ab8`
- `0x1800061c0`
- `0x180006700`

## callees

- `0x180001780`
- `0x1800067c0`

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
0x1800067c0  cmp     rcx, cs:__security_cookie
0x1800067c7  jnz     short ReportFailure
0x1800067c9  rol     rcx, 10h
0x1800067cd  test    cx, 0FFFFh
0x1800067d2  jnz     short RestoreRcx
0x1800067d4  retn
0x1800067d5  ror     rcx, 10h
0x1800067d9  jmp     __report_gsfailure
```

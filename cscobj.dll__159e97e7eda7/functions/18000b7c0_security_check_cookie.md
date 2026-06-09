# __security_check_cookie

- ea: `0x18000b7c0`
- end: `0x18000b7de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800020a0`
- `0x180003ca0`
- `0x180004028`
- `0x180004270`
- `0x180004cf0`
- `0x1800061a0`
- `0x180006e70`
- `0x1800076e0`
- `0x18000df30`
- `0x180010400`
- `0x18001057c`
- `0x180010834`
- `0x180010934`
- `0x180010ae8`
- `0x180010c64`
- `0x180012638`
- `0x18001f22c`
- `0x18002273c`
- `0x180022b4c`
- `0x180022cdc`
- `0x180022f6c`
- `0x180024650`
- `0x180025fe4`
- `0x180026470`
- `0x1800281bc`
- `0x18002aaec`

## callees

- `0x18000b7c0`
- `0x18000bd80`

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
0x18000b7c0  cmp     rcx, cs:__security_cookie
0x18000b7c7  jnz     short ReportFailure
0x18000b7c9  rol     rcx, 10h
0x18000b7cd  test    cx, 0FFFFh
0x18000b7d2  jnz     short RestoreRcx
0x18000b7d4  retn
0x18000b7d5  ror     rcx, 10h; StackCookie
0x18000b7d9  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x1800067e0`
- end: `0x1800067fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010e4`
- `0x180001700`
- `0x180001d38`
- `0x180001e04`
- `0x180002348`
- `0x180002444`
- `0x180002888`
- `0x180002e70`
- `0x180002ef4`
- `0x1800030b4`
- `0x1800031a0`
- `0x18000325c`
- `0x180003370`
- `0x1800036a0`
- `0x1800037ac`
- `0x180003a4c`
- `0x180003d00`
- `0x180003e20`
- `0x180004280`
- `0x180004368`
- `0x180004594`
- `0x1800046ec`
- `0x1800047d0`
- `0x1800049c4`
- `0x180005020`
- `0x180005250`
- `0x180006558`
- `0x180006680`

## callees

- `0x180001010`
- `0x1800067e0`

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
0x1800067e0  cmp     rcx, cs:__security_cookie
0x1800067e7  jnz     short ReportFailure
0x1800067e9  rol     rcx, 10h
0x1800067ed  test    cx, 0FFFFh
0x1800067f2  jnz     short RestoreRcx
0x1800067f4  retn
0x1800067f5  ror     rcx, 10h; StackCookie
0x1800067f9  jmp     __report_gsfailure
```

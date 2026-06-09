# __security_check_cookie

- ea: `0x1800108a0`
- end: `0x1800108be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180002a84`
- `0x180003574`
- `0x18000368c`
- `0x180003a54`
- `0x180003c38`
- `0x180003e20`
- `0x180004c74`
- `0x1800076a0`
- `0x18000ad04`
- `0x18000ae18`
- `0x18000af24`
- `0x18000b048`
- `0x18000b184`
- `0x18000b860`
- `0x18000efe0`
- `0x18001023c`
- `0x18001078c`
- `0x18001f870`
- `0x18001fd20`
- `0x18001ff10`
- `0x180021740`
- `0x1800218c0`
- `0x180022850`
- `0x180022c20`
- `0x180022f50`
- `0x180023320`
- `0x180023a78`
- `0x180024130`
- `0x180024330`
- `0x180024910`
- `0x180025e00`
- `0x180027470`
- `0x180027d78`
- `0x18002b078`
- `0x18002b7ac`

## callees

- `0x180007a30`
- `0x1800108a0`

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
0x1800108a0  cmp     rcx, cs:__security_cookie
0x1800108a7  jnz     short ReportFailure
0x1800108a9  rol     rcx, 10h
0x1800108ad  test    cx, 0FFFFh
0x1800108b2  jnz     short RestoreRcx
0x1800108b4  retn
0x1800108b5  ror     rcx, 10h; StackCookie
0x1800108b9  jmp     __report_gsfailure
```

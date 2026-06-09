# __security_check_cookie

- ea: `0x18002f0e0`
- end: `0x18002f0fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800031e4`
- `0x180003c70`
- `0x180005264`
- `0x180008360`
- `0x180008518`
- `0x180008798`
- `0x18000cbc8`
- `0x18000d1fc`
- `0x18000e86c`
- `0x18000eeb0`
- `0x18000f2e0`
- `0x18000fbbc`
- `0x180010564`
- `0x180010658`
- `0x180010ee0`
- `0x180011fac`
- `0x180015988`
- `0x180016b60`
- `0x180016eac`
- `0x180019408`
- `0x1800198f4`
- `0x180019fbc`
- `0x18001a0fc`
- `0x18001a9ac`
- `0x18001acc4`
- `0x18001c688`
- `0x18001cd30`
- `0x18001d42c`
- `0x18001dd70`
- `0x18001e2ec`
- `0x18001eb10`
- `0x18001f7c8`
- `0x18001fff8`
- `0x180020bec`
- `0x180021128`
- `0x180021d10`
- `0x180023784`
- `0x1800248d8`
- `0x180028148`
- `0x18002a250`
- `0x18002a540`
- `0x18002a730`
- `0x18002ac38`
- `0x18002cee0`
- `0x18002dcc4`
- `0x18002e554`
- `0x18002efb0`

## callees

- `0x1800016b0`
- `0x18002f0e0`

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
0x18002f0e0  cmp     rcx, cs:__security_cookie
0x18002f0e7  jnz     short ReportFailure
0x18002f0e9  rol     rcx, 10h
0x18002f0ed  test    cx, 0FFFFh
0x18002f0f2  jnz     short RestoreRcx
0x18002f0f4  retn
0x18002f0f5  ror     rcx, 10h
0x18002f0f9  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x18002f0e0`
- end: `0x18002f0fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `60`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ec0`
- `0x180003458`
- `0x180004870`
- `0x180005144`
- `0x1800053e0`
- `0x180006108`
- `0x180006270`
- `0x180006438`
- `0x180006b34`
- `0x180006f44`
- `0x180007390`
- `0x180008280`
- `0x180008b70`
- `0x180008dd4`
- `0x180009474`
- `0x18000a600`
- `0x18000b0d0`
- `0x18000b2c0`
- `0x18000bb80`
- `0x18000d890`
- `0x18000dde0`
- `0x18000e530`
- `0x18000e65c`
- `0x18000e9c4`
- `0x18000ef44`
- `0x1800108f0`
- `0x180010ba0`
- `0x180011218`
- `0x180011bd8`
- `0x180011dfc`
- `0x180012158`
- `0x18001231c`
- `0x180012b94`
- `0x180013b18`
- `0x18001513c`
- `0x180015580`
- `0x1800159a0`
- `0x180017430`
- `0x180017730`
- `0x180017fd0`
- `0x180018530`
- `0x180018b40`
- `0x180019b94`
- `0x180019da0`
- `0x18001d480`
- `0x18001eb24`
- `0x18001fa40`
- `0x18002036c`
- `0x1800209a8`
- `0x180020fe0`

## callees

- `0x180003120`
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

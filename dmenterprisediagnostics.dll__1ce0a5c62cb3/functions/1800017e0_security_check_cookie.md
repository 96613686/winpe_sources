# __security_check_cookie

- ea: `0x1800017e0`
- end: `0x1800017fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `59`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002934`
- `0x180002a98`
- `0x180002f08`
- `0x1800031b4`
- `0x180003d18`
- `0x180003ec8`
- `0x1800041bc`
- `0x1800045b4`
- `0x180004968`
- `0x180005f0c`
- `0x1800064dc`
- `0x180006e88`
- `0x1800074c0`
- `0x180007ce4`
- `0x180008274`
- `0x180008448`
- `0x18000aa44`
- `0x18000b240`
- `0x18000ba80`
- `0x18000c484`
- `0x18000f0d0`
- `0x180010e80`
- `0x180011bfc`
- `0x180011e80`
- `0x180011fec`
- `0x1800121e8`
- `0x180013844`
- `0x180013974`
- `0x180013e6c`
- `0x1800149f0`
- `0x180014f08`
- `0x180015d78`
- `0x1800176b0`
- `0x180018bac`
- `0x18001964c`
- `0x180019b50`
- `0x18001a684`
- `0x18001a6dc`
- `0x18001a75c`
- `0x18001a7fc`
- `0x18001a8b4`
- `0x18001aabc`
- `0x18001ab88`
- `0x18001accc`
- `0x18001b2d4`
- `0x18001ce64`
- `0x18001d360`
- `0x18001e9f0`
- `0x18001f160`
- `0x18001f3a4`

## callees

- `0x1800017e0`
- `0x180001ee0`

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
0x1800017e0  cmp     rcx, cs:__security_cookie
0x1800017e7  jnz     short ReportFailure
0x1800017e9  rol     rcx, 10h
0x1800017ed  test    cx, 0FFFFh
0x1800017f2  jnz     short RestoreRcx
0x1800017f4  retn
0x1800017f5  ror     rcx, 10h; StackCookie
0x1800017f9  jmp     __report_gsfailure
```

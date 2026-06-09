# __security_check_cookie

- ea: `0x180001cf0`
- end: `0x180001d0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000113c`
- `0x180001284`
- `0x18000132c`
- `0x180003424`
- `0x1800036b8`
- `0x180004418`
- `0x1800047e8`
- `0x180004be0`
- `0x180005744`
- `0x180005ac0`
- `0x1800060b0`
- `0x180006c9c`
- `0x180006da8`
- `0x1800077bc`
- `0x180007b9c`
- `0x1800082c0`
- `0x180008390`
- `0x18000947c`
- `0x18000969c`
- `0x18000993c`
- `0x18000a350`
- `0x18000a478`
- `0x18000a944`
- `0x18000c568`
- `0x18000c6b0`
- `0x18000c990`
- `0x18000dce4`
- `0x18000dfa8`
- `0x18000ead8`
- `0x18000ec04`
- `0x18000ed9c`
- `0x18000fcfc`
- `0x18000fff8`
- `0x180010098`
- `0x180010a14`
- `0x180010af0`
- `0x180011b20`

## callees

- `0x180001cf0`
- `0x1800022e0`

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
0x180001cf0  cmp     rcx, cs:__security_cookie
0x180001cf7  jnz     short ReportFailure
0x180001cf9  rol     rcx, 10h
0x180001cfd  test    cx, 0FFFFh
0x180001d02  jnz     short RestoreRcx
0x180001d04  retn
0x180001d05  ror     rcx, 10h; StackCookie
0x180001d09  jmp     __report_gsfailure
```

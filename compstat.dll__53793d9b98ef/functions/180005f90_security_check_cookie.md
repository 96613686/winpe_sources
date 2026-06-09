# __security_check_cookie

- ea: `0x180005f90`
- end: `0x180005fae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001310`
- `0x180001b00`
- `0x180001d80`
- `0x180002000`
- `0x180002090`
- `0x180002670`
- `0x1800028a0`
- `0x180004180`
- `0x180004d70`
- `0x180005ed0`
- `0x180008120`
- `0x180008c90`
- `0x180008eb0`

## callees

- `0x180005be0`
- `0x180005f90`

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
0x180005f90  cmp     rcx, cs:__security_cookie
0x180005f97  jnz     short ReportFailure
0x180005f99  rol     rcx, 10h
0x180005f9d  test    cx, 0FFFFh
0x180005fa2  jnz     short RestoreRcx
0x180005fa4  retn
0x180005fa5  ror     rcx, 10h
0x180005fa9  jmp     __report_gsfailure
```

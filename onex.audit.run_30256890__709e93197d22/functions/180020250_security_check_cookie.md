# __security_check_cookie

- ea: `0x180020250`
- end: `0x18002026e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004660`
- `0x180004710`
- `0x180004f40`
- `0x180004fa0`
- `0x180006160`
- `0x180006bd0`
- `0x18000d6d0`
- `0x18000dd40`
- `0x18000e888`
- `0x1800127a0`
- `0x180013ee0`
- `0x180014190`
- `0x18001aeb4`
- `0x18001ba00`
- `0x18001bbd8`
- `0x18001c6c0`
- `0x18001d108`
- `0x18001dd84`
- `0x18001f690`
- `0x180021e70`
- `0x180021f5c`
- `0x180022384`
- `0x18002275c`
- `0x180022c30`
- `0x1800235a4`
- `0x1800258c8`
- `0x180027d10`
- `0x180027dec`
- `0x18002a22c`
- `0x18002aa00`
- `0x18002f690`

## callees

- `0x180020250`
- `0x180020280`

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
0x180020250  cmp     rcx, cs:__security_cookie
0x180020257  jnz     short ReportFailure
0x180020259  rol     rcx, 10h
0x18002025d  test    cx, 0FFFFh
0x180020262  jnz     short RestoreRcx
0x180020264  retn
0x180020265  ror     rcx, 10h; StackCookie
0x180020269  jmp     __report_gsfailure
```

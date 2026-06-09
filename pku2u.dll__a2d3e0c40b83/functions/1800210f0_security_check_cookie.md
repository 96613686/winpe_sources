# __security_check_cookie

- ea: `0x1800210f0`
- end: `0x18002110e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `78`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000115c`
- `0x180001410`
- `0x180001bf0`
- `0x180002e40`
- `0x180003700`
- `0x180003bc0`
- `0x1800044f0`
- `0x180004830`
- `0x180005840`
- `0x1800071a0`
- `0x1800075d0`
- `0x180007800`
- `0x180007b18`
- `0x180007f40`
- `0x180009070`
- `0x18000a370`
- `0x18000b000`
- `0x18000d220`
- `0x18000ed70`
- `0x18000fc70`
- `0x180010ea4`
- `0x180011060`
- `0x180011de0`
- `0x180014fe0`
- `0x180015fa0`
- `0x180016600`
- `0x180016a10`
- `0x180017df0`
- `0x180018124`
- `0x180018ca8`
- `0x180018ff8`
- `0x180019928`
- `0x18001a940`
- `0x18001b080`
- `0x18001b324`
- `0x18001cc90`
- `0x18001e090`
- `0x18001e368`
- `0x18001e510`
- `0x18001ed80`
- `0x180022794`
- `0x180022e2c`
- `0x180024f34`
- `0x1800254c8`
- `0x180025660`
- `0x1800258c4`
- `0x180025bdc`
- `0x180026c2c`
- `0x180027060`

## callees

- `0x1800210f0`
- `0x180021680`

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
0x1800210f0  cmp     rcx, cs:__security_cookie
0x1800210f7  jnz     short ReportFailure
0x1800210f9  rol     rcx, 10h
0x1800210fd  test    cx, 0FFFFh
0x180021102  jnz     short RestoreRcx
0x180021104  retn
0x180021105  ror     rcx, 10h; StackCookie
0x180021109  jmp     __report_gsfailure
```

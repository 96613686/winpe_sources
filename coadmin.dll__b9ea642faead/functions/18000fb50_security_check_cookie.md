# __security_check_cookie

- ea: `0x18000fb50`
- end: `0x18000fb6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000238c`
- `0x180003590`
- `0x1800046a4`
- `0x180004dd0`
- `0x180006198`
- `0x1800063c0`
- `0x180006c0c`
- `0x180007394`
- `0x1800087f0`
- `0x180008ae0`
- `0x180009ac4`
- `0x180009bd8`
- `0x180009f60`
- `0x18000a0b0`
- `0x18000b08c`
- `0x18000b2d4`
- `0x18000b988`
- `0x18000c020`
- `0x18000de90`
- `0x18000e978`
- `0x18000ea44`
- `0x18000eb50`
- `0x18000eeb8`
- `0x18000f468`
- `0x18000f730`
- `0x18000f998`
- `0x18000fa94`

## callees

- `0x180001690`
- `0x18000fb50`

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
0x18000fb50  cmp     rcx, cs:__security_cookie
0x18000fb57  jnz     short ReportFailure
0x18000fb59  rol     rcx, 10h
0x18000fb5d  test    cx, 0FFFFh
0x18000fb62  jnz     short RestoreRcx
0x18000fb64  retn
0x18000fb65  ror     rcx, 10h
0x18000fb69  jmp     __report_gsfailure
```

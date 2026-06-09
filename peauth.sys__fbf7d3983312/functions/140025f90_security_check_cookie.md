# __security_check_cookie

- ea: `0x140025f90`
- end: `0x140025fae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `58`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010e8`
- `0x140005b6c`
- `0x140005cb0`
- `0x14000704c`
- `0x140007550`
- `0x14000762c`
- `0x140007bcc`
- `0x140008e98`
- `0x14000a2bc`
- `0x14000b370`
- `0x14000bb9c`
- `0x14000c6ac`
- `0x14000cd44`
- `0x14000d3c8`
- `0x14000d68c`
- `0x14000e020`
- `0x14000e124`
- `0x14000e26c`
- `0x14000e304`
- `0x14000f930`
- `0x14000fa4c`
- `0x140011310`
- `0x140011420`
- `0x140011d54`
- `0x1400120d4`
- `0x140012274`
- `0x1400134c0`
- `0x140013d10`
- `0x140014810`
- `0x140016770`
- `0x1400168b0`
- `0x140016a44`
- `0x140017180`
- `0x140025e3c`
- `0x140044830`
- `0x1400448b8`
- `0x1400451f4`
- `0x140045734`
- `0x140045850`
- `0x140045980`
- `0x140045a5c`
- `0x140045f14`
- `0x1400461c8`
- `0x140046878`
- `0x1400469f0`
- `0x14004704c`
- `0x140047304`
- `0x14004748c`
- `0x14004759c`
- `0x1400477e4`

## callees

- `0x14001c5b0`
- `0x140025f90`

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
0x140025f90  cmp     rcx, cs:__security_cookie
0x140025f97  jnz     short ReportFailure
0x140025f99  rol     rcx, 10h
0x140025f9d  test    cx, 0FFFFh
0x140025fa2  jnz     short RestoreRcx
0x140025fa4  retn
0x140025fa5  ror     rcx, 10h; StackCookie
0x140025fa9  jmp     __report_gsfailure
```

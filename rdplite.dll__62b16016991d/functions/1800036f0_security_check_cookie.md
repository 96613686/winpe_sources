# __security_check_cookie

- ea: `0x1800036f0`
- end: `0x18000370e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `77`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001178`
- `0x1800012bc`
- `0x1800014e8`
- `0x180001574`
- `0x1800016a0`
- `0x1800017dc`
- `0x180001a90`
- `0x180001d88`
- `0x180001ecc`
- `0x180001fe4`
- `0x18000208c`
- `0x180002198`
- `0x1800022b0`
- `0x1800023fc`
- `0x180002508`
- `0x18000260c`
- `0x18000275c`
- `0x1800028d4`
- `0x180002a98`
- `0x180002d44`
- `0x180002f68`
- `0x180003080`
- `0x18000464c`
- `0x180004748`
- `0x180005338`
- `0x180005514`
- `0x180005864`
- `0x180005bbc`
- `0x180007228`
- `0x180007770`
- `0x18000799c`
- `0x180007c68`
- `0x180007e30`
- `0x180008f9c`
- `0x1800091c8`
- `0x18000a00c`
- `0x18000a3f4`
- `0x18000a4d8`
- `0x18000ad3c`
- `0x18000b578`
- `0x18000c410`
- `0x18000d098`
- `0x18000d98c`
- `0x18000e270`
- `0x18000e314`
- `0x18000e3b8`
- `0x18000e45c`
- `0x18000e5fc`
- `0x18000e794`

## callees

- `0x1800036f0`
- `0x180003d00`

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
0x1800036f0  cmp     rcx, cs:__security_cookie
0x1800036f7  jnz     short ReportFailure
0x1800036f9  rol     rcx, 10h
0x1800036fd  test    cx, 0FFFFh
0x180003702  jnz     short RestoreRcx
0x180003704  retn
0x180003705  ror     rcx, 10h; StackCookie
0x180003709  jmp     __report_gsfailure
```

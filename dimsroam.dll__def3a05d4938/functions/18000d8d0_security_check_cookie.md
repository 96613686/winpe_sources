# __security_check_cookie

- ea: `0x18000d8d0`
- end: `0x18000d8ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001fcc`
- `0x1800024e4`
- `0x1800025d8`
- `0x1800027d8`
- `0x180002f60`
- `0x180003300`
- `0x1800036c8`
- `0x180003ad0`
- `0x180003fb4`
- `0x1800045f4`
- `0x18000542c`
- `0x18000556c`
- `0x180005c00`
- `0x180006230`
- `0x1800071d0`
- `0x180007c38`
- `0x180007ed4`
- `0x18000870c`
- `0x180008ab0`
- `0x180008e80`
- `0x1800098e4`
- `0x180009c5c`
- `0x18000a89c`
- `0x18000ab1c`
- `0x18000b3e8`
- `0x18000c268`
- `0x18000cba8`
- `0x18000cebc`
- `0x18000d1f0`
- `0x18000d450`
- `0x18000d810`

## callees

- `0x1800019a0`
- `0x18000d8d0`

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
0x18000d8d0  cmp     rcx, cs:__security_cookie
0x18000d8d7  jnz     short ReportFailure
0x18000d8d9  rol     rcx, 10h
0x18000d8dd  test    cx, 0FFFFh
0x18000d8e2  jnz     short RestoreRcx
0x18000d8e4  retn
0x18000d8e5  ror     rcx, 10h
0x18000d8e9  jmp     __report_gsfailure
```

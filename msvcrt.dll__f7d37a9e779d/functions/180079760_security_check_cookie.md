# __security_check_cookie

- ea: `0x180079760`
- end: `0x18007977e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `184`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001180`
- `0x180001e10`
- `0x180001f00`
- `0x180002000`
- `0x180002460`
- `0x180002550`
- `0x180002640`
- `0x180002770`
- `0x180003f80`
- `0x180004dc0`
- `0x18000568c`
- `0x180005da0`
- `0x180006564`
- `0x180006760`
- `0x180006900`
- `0x180006c90`
- `0x180006e00`
- `0x180006f90`
- `0x1800070b0`
- `0x180007220`
- `0x1800073ac`
- `0x180007454`
- `0x1800075b4`
- `0x180007718`
- `0x180007878`
- `0x180007c78`
- `0x180008140`
- `0x180008330`
- `0x180008678`
- `0x180008960`
- `0x180008f30`
- `0x180009318`
- `0x180009844`
- `0x18000990c`
- `0x180009b10`
- `0x18000a0d8`
- `0x18000a574`
- `0x18000a768`
- `0x18000d080`
- `0x18000d928`
- `0x18000e58c`
- `0x18000e638`
- `0x180013c5c`
- `0x180013ec0`
- `0x180014bb0`
- `0x1800158cc`
- `0x180015eb4`
- `0x180016c34`
- `0x180018568`
- `0x180018800`

## callees

- `0x180035e40`
- `0x180079760`

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
0x180079760  cmp     rcx, cs:__security_cookie
0x180079767  jnz     short ReportFailure
0x180079769  rol     rcx, 10h
0x18007976d  test    cx, 0FFFFh
0x180079772  jnz     short RestoreRcx
0x180079774  retn
0x180079775  ror     rcx, 10h
0x180079779  jmp     __report_gsfailure
```

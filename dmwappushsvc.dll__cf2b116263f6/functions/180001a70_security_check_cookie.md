# __security_check_cookie

- ea: `0x180001a70`
- end: `0x180001a8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010f4`
- `0x1800011f8`
- `0x180002764`
- `0x1800030e4`
- `0x180003ae0`
- `0x180003e90`
- `0x1800049c0`
- `0x180004a18`
- `0x180005020`
- `0x1800052dc`
- `0x180005bec`
- `0x180005d00`
- `0x180005ea0`
- `0x180006240`
- `0x18000650c`
- `0x1800067a0`
- `0x180006ca4`
- `0x180006d94`
- `0x180007ee0`
- `0x18000804c`
- `0x180008218`
- `0x180008c6c`
- `0x18000a2c8`
- `0x18000aaec`
- `0x18000b2c0`
- `0x18000bb38`
- `0x18000c234`
- `0x18000c7d0`
- `0x18000cf40`
- `0x18000d20c`
- `0x18000d574`
- `0x18000db88`
- `0x18000ddd0`
- `0x18000df4c`
- `0x18000e994`
- `0x18000eb50`
- `0x18000eccc`
- `0x18000f0ec`
- `0x18000f6d0`
- `0x18000f860`
- `0x18000faf0`
- `0x18000fe10`
- `0x18000ffa0`
- `0x180010770`
- `0x180010934`
- `0x180010b0c`
- `0x180010c20`

## callees

- `0x180001a70`
- `0x1800020f0`

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
0x180001a70  cmp     rcx, cs:__security_cookie
0x180001a77  jnz     short ReportFailure
0x180001a79  rol     rcx, 10h
0x180001a7d  test    cx, 0FFFFh
0x180001a82  jnz     short RestoreRcx
0x180001a84  retn
0x180001a85  ror     rcx, 10h; StackCookie
0x180001a89  jmp     __report_gsfailure
```

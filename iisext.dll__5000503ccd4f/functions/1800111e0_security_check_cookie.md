# __security_check_cookie

- ea: `0x1800111e0`
- end: `0x1800111fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b10`
- `0x180003fdc`
- `0x18000449c`
- `0x180004628`
- `0x180004790`
- `0x180005800`
- `0x180005e50`
- `0x180006ab0`
- `0x18000ac50`
- `0x18000b22c`
- `0x18000b6b0`
- `0x18000b7a8`
- `0x18000bb84`
- `0x18000bd80`
- `0x18000c0ac`
- `0x18000cba0`
- `0x18000cdd8`
- `0x18000d4c0`
- `0x18000d5dc`
- `0x18000d81c`
- `0x18000d930`
- `0x180010638`
- `0x180010b44`
- `0x1800110b4`

## callees

- `0x180001580`
- `0x1800111e0`

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
0x1800111e0  cmp     rcx, cs:__security_cookie
0x1800111e7  jnz     short ReportFailure
0x1800111e9  rol     rcx, 10h
0x1800111ed  test    cx, 0FFFFh
0x1800111f2  jnz     short RestoreRcx
0x1800111f4  retn
0x1800111f5  ror     rcx, 10h
0x1800111f9  jmp     __report_gsfailure
```

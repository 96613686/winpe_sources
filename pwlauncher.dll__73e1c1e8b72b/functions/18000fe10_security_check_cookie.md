# __security_check_cookie

- ea: `0x18000fe10`
- end: `0x18000fe2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000235c`
- `0x1800024ac`
- `0x180002b3c`
- `0x180003284`
- `0x180003cc4`
- `0x180003fc8`
- `0x180004118`
- `0x1800042a8`
- `0x18000448c`
- `0x180004c3c`
- `0x180004d04`
- `0x180005638`
- `0x180005a68`
- `0x180005c98`
- `0x180006e44`
- `0x1800070ec`
- `0x1800075fc`
- `0x1800077f8`
- `0x180007e74`
- `0x18000810c`
- `0x180008488`
- `0x180008720`
- `0x18000c6bc`
- `0x18000c8f4`
- `0x18000d038`
- `0x18000de18`
- `0x18000e948`

## callees

- `0x180001cb0`
- `0x18000fe10`

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
0x18000fe10  cmp     rcx, cs:__security_cookie
0x18000fe17  jnz     short ReportFailure
0x18000fe19  rol     rcx, 10h
0x18000fe1d  test    cx, 0FFFFh
0x18000fe22  jnz     short RestoreRcx
0x18000fe24  retn
0x18000fe25  ror     rcx, 10h
0x18000fe29  jmp     __report_gsfailure
```

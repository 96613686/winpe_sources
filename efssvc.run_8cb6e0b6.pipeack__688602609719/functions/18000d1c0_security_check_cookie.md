# __security_check_cookie

- ea: `0x18000d1c0`
- end: `0x18000d1de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180002a34`
- `0x180003714`
- `0x1800037b8`
- `0x180004900`
- `0x180007f38`
- `0x180008db0`
- `0x18000945c`
- `0x18000970c`
- `0x180009a10`
- `0x18000a03c`
- `0x18000ac68`
- `0x18000b04c`
- `0x18000b9d0`
- `0x18000d03c`
- `0x18000d114`

## callees

- `0x1800020a0`
- `0x18000d1c0`

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
0x18000d1c0  cmp     rcx, cs:__security_cookie
0x18000d1c7  jnz     short ReportFailure
0x18000d1c9  rol     rcx, 10h
0x18000d1cd  test    cx, 0FFFFh
0x18000d1d2  jnz     short RestoreRcx
0x18000d1d4  retn
0x18000d1d5  ror     rcx, 10h
0x18000d1d9  jmp     __report_gsfailure
```

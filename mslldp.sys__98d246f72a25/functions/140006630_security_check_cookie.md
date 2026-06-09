# __security_check_cookie

- ea: `0x140006630`
- end: `0x14000664e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000458c`
- `0x140004860`
- `0x140004c4c`
- `0x1400059ac`
- `0x140005d78`
- `0x140005dd0`
- `0x140005e4c`
- `0x140005ef8`
- `0x1400064fc`
- `0x14000e008`
- `0x14000ead0`
- `0x14000eb88`
- `0x14000f3b8`
- `0x14000f83c`
- `0x14000fa94`
- `0x14000fb2c`
- `0x140010ca0`
- `0x140013588`

## callees

- `0x140004af0`
- `0x140006630`

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
0x140006630  cmp     rcx, cs:__security_cookie
0x140006637  jnz     short ReportFailure
0x140006639  rol     rcx, 10h
0x14000663d  test    cx, 0FFFFh
0x140006642  jnz     short RestoreRcx
0x140006644  retn
0x140006645  ror     rcx, 10h; StackCookie
0x140006649  jmp     __report_gsfailure
```

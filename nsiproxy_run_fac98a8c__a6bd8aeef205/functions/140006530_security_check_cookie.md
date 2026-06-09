# __security_check_cookie

- ea: `0x140006530`
- end: `0x14000654e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005320`
- `0x1400055c0`
- `0x1400064ac`
- `0x14000de48`
- `0x14000e9f4`

## callees

- `0x1400056b0`
- `0x140006530`

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
0x140006530  cmp     rcx, cs:__security_cookie
0x140006537  jnz     short ReportFailure
0x140006539  rol     rcx, 10h
0x14000653d  test    cx, 0FFFFh
0x140006542  jnz     short RestoreRcx
0x140006544  retn
0x140006545  ror     rcx, 10h; StackCookie
0x140006549  jmp     __report_gsfailure
```

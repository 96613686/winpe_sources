# __security_check_cookie

- ea: `0x180006b00`
- end: `0x180006b1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003930`
- `0x180003a60`
- `0x1800040d0`
- `0x180004220`
- `0x180004c30`
- `0x180005cf8`
- `0x180006a60`

## callees

- `0x1800054e0`
- `0x180006b00`

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
0x180006b00  cmp     rcx, cs:__security_cookie
0x180006b07  jnz     short ReportFailure
0x180006b09  rol     rcx, 10h
0x180006b0d  test    cx, 0FFFFh
0x180006b12  jnz     short RestoreRcx
0x180006b14  retn
0x180006b15  ror     rcx, 10h
0x180006b19  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x18000bbf0`
- end: `0x18000bc0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002b08`
- `0x180003638`
- `0x1800038d4`
- `0x18000410c`
- `0x1800044b0`
- `0x180004880`
- `0x1800052e4`
- `0x18000565c`
- `0x18000629c`
- `0x18000651c`
- `0x180006de8`
- `0x180007c68`
- `0x1800085a8`
- `0x180009aa0`
- `0x18000aa10`
- `0x18000afc0`
- `0x18000b460`
- `0x18000bad0`

## callees

- `0x180001ab0`
- `0x18000bbf0`

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
0x18000bbf0  cmp     rcx, cs:__security_cookie
0x18000bbf7  jnz     short ReportFailure
0x18000bbf9  rol     rcx, 10h
0x18000bbfd  test    cx, 0FFFFh
0x18000bc02  jnz     short RestoreRcx
0x18000bc04  retn
0x18000bc05  ror     rcx, 10h
0x18000bc09  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x1800054f0`
- end: `0x18000550e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800037bc`
- `0x180003fe4`
- `0x180004108`
- `0x1800042ec`
- `0x1800050b0`
- `0x1800052c0`
- `0x180005424`

## callees

- `0x1800017a0`
- `0x1800054f0`

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
0x1800054f0  cmp     rcx, cs:__security_cookie
0x1800054f7  jnz     short ReportFailure
0x1800054f9  rol     rcx, 10h
0x1800054fd  test    cx, 0FFFFh
0x180005502  jnz     short RestoreRcx
0x180005504  retn
0x180005505  ror     rcx, 10h
0x180005509  jmp     __report_gsfailure
```

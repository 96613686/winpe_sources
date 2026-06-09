# __security_check_cookie

- ea: `0x1800035f0`
- end: `0x18000360e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800021ec`
- `0x180002758`
- `0x180002bc4`
- `0x18000355c`

## callees

- `0x180001790`
- `0x1800035f0`

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
0x1800035f0  cmp     rcx, cs:__security_cookie
0x1800035f7  jnz     short ReportFailure
0x1800035f9  rol     rcx, 10h
0x1800035fd  test    cx, 0FFFFh
0x180003602  jnz     short RestoreRcx
0x180003604  retn
0x180003605  ror     rcx, 10h
0x180003609  jmp     __report_gsfailure
```

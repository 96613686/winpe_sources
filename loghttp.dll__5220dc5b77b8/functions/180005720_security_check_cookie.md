# __security_check_cookie

- ea: `0x180005720`
- end: `0x18000573e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001080`
- `0x180001cd0`
- `0x180003318`
- `0x180003510`
- `0x180003a10`
- `0x1800047f8`
- `0x1800048ec`
- `0x180004d14`
- `0x180004f40`
- `0x1800051c8`
- `0x180005670`

## callees

- `0x180002de0`
- `0x180005720`

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
0x180005720  cmp     rcx, cs:__security_cookie
0x180005727  jnz     short ReportFailure
0x180005729  rol     rcx, 10h
0x18000572d  test    cx, 0FFFFh
0x180005732  jnz     short RestoreRcx
0x180005734  retn
0x180005735  ror     rcx, 10h
0x180005739  jmp     __report_gsfailure
```

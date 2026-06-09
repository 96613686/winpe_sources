# __security_check_cookie

- ea: `0x180002dd0`
- end: `0x180002dee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ac8`
- `0x180001cb4`
- `0x180002ca0`

## callees

- `0x180001570`
- `0x180002dd0`

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
0x180002dd0  cmp     rcx, cs:__security_cookie
0x180002dd7  jnz     short ReportFailure
0x180002dd9  rol     rcx, 10h
0x180002ddd  test    cx, 0FFFFh
0x180002de2  jnz     short RestoreRcx
0x180002de4  retn
0x180002de5  ror     rcx, 10h
0x180002de9  jmp     __report_gsfailure
```

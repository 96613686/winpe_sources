# __security_check_cookie

- ea: `0x180004ad0`
- end: `0x180004aee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b5c`
- `0x1800028b0`
- `0x1800034fc`
- `0x18000369c`
- `0x180003ce8`
- `0x180003df4`
- `0x180004290`
- `0x180004a38`

## callees

- `0x1800018c0`
- `0x180004ad0`

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
0x180004ad0  cmp     rcx, cs:__security_cookie
0x180004ad7  jnz     short ReportFailure
0x180004ad9  rol     rcx, 10h
0x180004add  test    cx, 0FFFFh
0x180004ae2  jnz     short RestoreRcx
0x180004ae4  retn
0x180004ae5  ror     rcx, 10h
0x180004ae9  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x180001600`
- end: `0x18000161e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800030e4`
- `0x180003a3c`
- `0x180003ce8`
- `0x1800044f8`
- `0x1800048c8`
- `0x180004e44`
- `0x1800051c0`
- `0x1800074e4`
- `0x1800079f0`
- `0x180009e58`
- `0x18000a558`
- `0x18000b8c4`
- `0x18000bef4`
- `0x18000cda4`

## callees

- `0x180001600`
- `0x180001c30`

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
0x180001600  cmp     rcx, cs:__security_cookie
0x180001607  jnz     short ReportFailure
0x180001609  rol     rcx, 10h
0x18000160d  test    cx, 0FFFFh
0x180001612  jnz     short RestoreRcx
0x180001614  retn
0x180001615  ror     rcx, 10h; StackCookie
0x180001619  jmp     __report_gsfailure
```

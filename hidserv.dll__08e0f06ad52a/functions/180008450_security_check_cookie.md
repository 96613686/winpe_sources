# __security_check_cookie

- ea: `0x180008450`
- end: `0x18000846e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000142c`
- `0x180002910`
- `0x180003594`
- `0x180004000`
- `0x180005708`
- `0x180006460`
- `0x18000674c`
- `0x180006a64`
- `0x180006b9c`
- `0x180006cb4`
- `0x180007988`
- `0x180008390`

## callees

- `0x180001cf0`
- `0x180008450`

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
0x180008450  cmp     rcx, cs:__security_cookie
0x180008457  jnz     short ReportFailure
0x180008459  rol     rcx, 10h
0x18000845d  test    cx, 0FFFFh
0x180008462  jnz     short RestoreRcx
0x180008464  retn
0x180008465  ror     rcx, 10h
0x180008469  jmp     __report_gsfailure
```

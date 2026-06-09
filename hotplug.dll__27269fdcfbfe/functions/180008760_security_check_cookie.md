# __security_check_cookie

- ea: `0x180008760`
- end: `0x18000877e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002824`
- `0x180002e58`
- `0x18000312c`
- `0x180003a14`
- `0x180004664`
- `0x180004c20`
- `0x180004e60`
- `0x180005528`
- `0x180005610`
- `0x180005724`
- `0x180005c80`
- `0x180006124`
- `0x180006338`
- `0x18000672c`
- `0x180006a68`
- `0x180006bd0`
- `0x18000712c`
- `0x1800073b0`
- `0x180007558`
- `0x180007888`
- `0x180007c20`
- `0x180007f1c`
- `0x180008660`

## callees

- `0x180001f10`
- `0x180008760`

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
0x180008760  cmp     rcx, cs:__security_cookie
0x180008767  jnz     short ReportFailure
0x180008769  rol     rcx, 10h
0x18000876d  test    cx, 0FFFFh
0x180008772  jnz     short RestoreRcx
0x180008774  retn
0x180008775  ror     rcx, 10h
0x180008779  jmp     __report_gsfailure
```

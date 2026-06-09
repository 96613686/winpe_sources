# __security_check_cookie

- ea: `0x180007870`
- end: `0x18000788e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800012c0`
- `0x180001d3c`
- `0x1800038d0`
- `0x180004504`
- `0x180004968`
- `0x180004d9c`
- `0x18000518c`
- `0x1800053e0`
- `0x180005988`
- `0x1800065f0`
- `0x1800077c4`

## callees

- `0x180002770`
- `0x180007870`

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
0x180007870  cmp     rcx, cs:__security_cookie
0x180007877  jnz     short ReportFailure
0x180007879  rol     rcx, 10h
0x18000787d  test    cx, 0FFFFh
0x180007882  jnz     short RestoreRcx
0x180007884  retn
0x180007885  ror     rcx, 10h
0x180007889  jmp     __report_gsfailure
```

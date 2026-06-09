# __security_check_cookie

- ea: `0x180001400`
- end: `0x18000141e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002334`
- `0x180002f40`
- `0x180003cc4`
- `0x1800041b4`
- `0x1800044f0`
- `0x180004a10`
- `0x180004f60`
- `0x180005350`
- `0x180005920`
- `0x180006410`

## callees

- `0x180001400`
- `0x180001430`

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
0x180001400  cmp     rcx, cs:__security_cookie
0x180001407  jnz     short ReportFailure
0x180001409  rol     rcx, 10h
0x18000140d  test    cx, 0FFFFh
0x180001412  jnz     short RestoreRcx
0x180001414  retn
0x180001415  ror     rcx, 10h; StackCookie
0x180001419  jmp     __report_gsfailure
```

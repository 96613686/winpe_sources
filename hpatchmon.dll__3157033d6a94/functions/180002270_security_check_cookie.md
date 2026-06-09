# __security_check_cookie

- ea: `0x180002270`
- end: `0x18000228e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `45`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001098`
- `0x18000126c`
- `0x18000132c`
- `0x180001408`
- `0x1800014d8`
- `0x180001580`
- `0x180001624`
- `0x1800016d8`
- `0x1800017d4`
- `0x180001ca0`
- `0x180002fb0`
- `0x18000385c`
- `0x180003af8`
- `0x1800048f8`
- `0x180004c9c`
- `0x180005070`
- `0x1800051d8`
- `0x180005570`
- `0x1800067f4`
- `0x180006b70`
- `0x180006f90`
- `0x180007400`
- `0x1800075a0`
- `0x18000841c`
- `0x180008528`
- `0x180008f3c`
- `0x180009a80`
- `0x18000b294`
- `0x18000baf0`
- `0x18000bccc`
- `0x18000c8f0`
- `0x18000ca18`
- `0x18000ce60`
- `0x18000df40`
- `0x18000eca0`
- `0x18000ed44`
- `0x18000fa50`
- `0x18000ffe0`
- `0x180010710`
- `0x180011414`
- `0x1800114a4`
- `0x1800115c0`
- `0x180011770`
- `0x180013f10`

## callees

- `0x180002270`
- `0x180002800`

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
0x180002270  cmp     rcx, cs:__security_cookie
0x180002277  jnz     short ReportFailure
0x180002279  rol     rcx, 10h
0x18000227d  test    cx, 0FFFFh
0x180002282  jnz     short RestoreRcx
0x180002284  retn
0x180002285  ror     rcx, 10h; StackCookie
0x180002289  jmp     __report_gsfailure
```

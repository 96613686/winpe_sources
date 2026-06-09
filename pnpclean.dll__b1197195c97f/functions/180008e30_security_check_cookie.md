# __security_check_cookie

- ea: `0x180008e30`
- end: `0x180008e4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b8c`
- `0x180002304`
- `0x180003140`
- `0x1800034b0`
- `0x180004460`
- `0x180004a04`
- `0x180004e0c`
- `0x180004e74`
- `0x1800058a0`
- `0x180005bd0`
- `0x180006644`
- `0x18000684c`
- `0x180006c9c`
- `0x180006dc4`
- `0x180007370`
- `0x180007498`
- `0x180007560`
- `0x180007680`
- `0x180007c00`
- `0x180007f48`
- `0x180007fbc`
- `0x180008438`
- `0x18000880c`
- `0x180008990`
- `0x180008a30`

## callees

- `0x1800016c0`
- `0x180008e30`

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
0x180008e30  cmp     rcx, cs:__security_cookie
0x180008e37  jnz     short ReportFailure
0x180008e39  rol     rcx, 10h
0x180008e3d  test    cx, 0FFFFh
0x180008e42  jnz     short RestoreRcx
0x180008e44  retn
0x180008e45  ror     rcx, 10h
0x180008e49  jmp     __report_gsfailure
```

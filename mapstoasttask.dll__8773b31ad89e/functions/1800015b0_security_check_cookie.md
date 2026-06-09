# __security_check_cookie

- ea: `0x1800015b0`
- end: `0x1800015ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ed4`
- `0x180003560`
- `0x18000374c`
- `0x1800038e4`
- `0x180003b44`
- `0x180003e00`
- `0x1800040f0`
- `0x1800044a8`
- `0x1800053e0`
- `0x18000574c`
- `0x180005e60`
- `0x180006b00`
- `0x180006d30`
- `0x18000730c`
- `0x180007c24`
- `0x180008010`
- `0x1800083b4`
- `0x18000914c`
- `0x180009400`

## callees

- `0x1800015b0`
- `0x180001bc0`

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
0x1800015b0  cmp     rcx, cs:__security_cookie
0x1800015b7  jnz     short ReportFailure
0x1800015b9  rol     rcx, 10h
0x1800015bd  test    cx, 0FFFFh
0x1800015c2  jnz     short RestoreRcx
0x1800015c4  retn
0x1800015c5  ror     rcx, 10h; StackCookie
0x1800015c9  jmp     __report_gsfailure
```

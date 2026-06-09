# __security_check_cookie

- ea: `0x18000a800`
- end: `0x18000a81e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001970`
- `0x180002b10`
- `0x180003750`
- `0x180003c90`
- `0x180004790`
- `0x180006f84`
- `0x180007940`
- `0x180007a60`
- `0x180007b38`
- `0x180007bcc`
- `0x180007ce4`
- `0x180007e24`
- `0x180008174`
- `0x180008430`
- `0x180008f38`
- `0x18000a484`
- `0x18000a740`

## callees

- `0x1800069e0`
- `0x18000a800`

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
0x18000a800  cmp     rcx, cs:__security_cookie
0x18000a807  jnz     short ReportFailure
0x18000a809  rol     rcx, 10h
0x18000a80d  test    cx, 0FFFFh
0x18000a812  jnz     short RestoreRcx
0x18000a814  retn
0x18000a815  ror     rcx, 10h
0x18000a819  jmp     __report_gsfailure
```

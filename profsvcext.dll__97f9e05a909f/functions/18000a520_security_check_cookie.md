# __security_check_cookie

- ea: `0x18000a520`
- end: `0x18000a53e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `62`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800029d0`
- `0x180002f6c`
- `0x180003300`
- `0x180003410`
- `0x1800038e0`
- `0x180003da0`
- `0x180004130`
- `0x180004250`
- `0x180004a50`
- `0x180004b00`
- `0x180005130`
- `0x1800056e8`
- `0x180005b54`
- `0x18000637c`
- `0x18000671c`
- `0x180006c1c`
- `0x1800075d8`
- `0x180007bd0`
- `0x180008258`
- `0x180008818`
- `0x180008b54`
- `0x180009588`
- `0x18000bf5c`
- `0x18000c208`
- `0x18000c928`
- `0x18000cac0`
- `0x18000cea4`
- `0x18000d1e4`
- `0x18000e8bc`
- `0x18000ee40`
- `0x18000f4b0`
- `0x18000f530`
- `0x180010df0`
- `0x180011880`
- `0x180012314`
- `0x180012b94`
- `0x180012f28`
- `0x180014158`
- `0x1800145c8`
- `0x180014cb8`
- `0x180015dbc`
- `0x180016a1c`
- `0x180016b68`
- `0x180017508`
- `0x1800176e4`
- `0x180017d90`
- `0x1800180c8`
- `0x180018a3c`

## callees

- `0x18000a520`
- `0x18000aae0`

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
0x18000a520  cmp     rcx, cs:__security_cookie
0x18000a527  jnz     short ReportFailure
0x18000a529  rol     rcx, 10h
0x18000a52d  test    cx, 0FFFFh
0x18000a532  jnz     short RestoreRcx
0x18000a534  retn
0x18000a535  ror     rcx, 10h; StackCookie
0x18000a539  jmp     __report_gsfailure
```

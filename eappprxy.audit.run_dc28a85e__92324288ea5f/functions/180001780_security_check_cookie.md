# __security_check_cookie

- ea: `0x180001780`
- end: `0x18000179e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002820`
- `0x180002ad0`
- `0x18000327c`
- `0x1800037d4`
- `0x180003b70`
- `0x1800045a0`
- `0x180005590`
- `0x180005714`
- `0x180005f40`
- `0x180006100`
- `0x1800069e0`
- `0x180006d20`
- `0x180007090`
- `0x180007330`
- `0x1800075c0`
- `0x180007a80`
- `0x180007d40`
- `0x1800080c0`
- `0x180008850`
- `0x180008cf0`
- `0x180009230`
- `0x1800096e0`
- `0x180009b90`
- `0x180009e10`
- `0x18000a1b0`
- `0x18000a550`
- `0x18000a8f0`
- `0x18000bac0`
- `0x18000bd30`
- `0x18000bef4`
- `0x18000c500`
- `0x18000ddd8`

## callees

- `0x180001780`
- `0x180001d40`

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
0x180001780  cmp     rcx, cs:__security_cookie
0x180001787  jnz     short ReportFailure
0x180001789  rol     rcx, 10h
0x18000178d  test    cx, 0FFFFh
0x180001792  jnz     short RestoreRcx
0x180001794  retn
0x180001795  ror     rcx, 10h; StackCookie
0x180001799  jmp     __report_gsfailure
```

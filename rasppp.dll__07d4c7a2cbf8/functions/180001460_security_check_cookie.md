# __security_check_cookie

- ea: `0x180001460`
- end: `0x18000147e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `199`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e00`
- `0x1800023a8`
- `0x180003110`
- `0x180003308`
- `0x1800034d4`
- `0x180003660`
- `0x180003770`
- `0x18000419c`
- `0x180004388`
- `0x180004630`
- `0x1800048e8`
- `0x180004eac`
- `0x1800051a0`
- `0x1800053c0`
- `0x1800054a8`
- `0x180005704`
- `0x180006118`
- `0x1800066d0`
- `0x180006d70`
- `0x180006f40`
- `0x180007850`
- `0x1800078e0`
- `0x180008320`
- `0x180008910`
- `0x1800089b0`
- `0x180009400`
- `0x180009560`
- `0x1800096e8`
- `0x180009900`
- `0x180009c00`
- `0x180009eb0`
- `0x18000a0f0`
- `0x18000a310`
- `0x18000a3c0`
- `0x18000a4f0`
- `0x18000a610`
- `0x18000aed4`
- `0x18000b170`
- `0x18000b310`
- `0x18000b834`
- `0x18000ba40`
- `0x18000bc28`
- `0x18000be0c`
- `0x18000bfc0`
- `0x18000c4ac`
- `0x18000c854`
- `0x18000c9a0`
- `0x18000cb10`
- `0x18000d020`
- `0x18000d284`

## callees

- `0x180001460`
- `0x180001490`

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
0x180001460  cmp     rcx, cs:__security_cookie
0x180001467  jnz     short ReportFailure
0x180001469  rol     rcx, 10h
0x18000146d  test    cx, 0FFFFh
0x180001472  jnz     short RestoreRcx
0x180001474  retn
0x180001475  ror     rcx, 10h; StackCookie
0x180001479  jmp     __report_gsfailure
```

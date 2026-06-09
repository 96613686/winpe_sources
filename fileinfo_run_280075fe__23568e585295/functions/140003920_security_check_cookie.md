# __security_check_cookie

- ea: `0x140003920`
- end: `0x14000393e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001130`
- `0x140001570`
- `0x140001644`
- `0x1400018d0`
- `0x140001ab0`
- `0x140001c60`
- `0x140001dd0`
- `0x140001f60`
- `0x1400020b0`
- `0x140002708`
- `0x1400028c8`
- `0x140002a80`
- `0x14000374c`
- `0x14000382c`
- `0x14000d5cc`
- `0x14000d8cc`
- `0x14000e8d8`
- `0x14000ec10`
- `0x14000f0b0`
- `0x14000f290`
- `0x14000f3f0`
- `0x14000f510`
- `0x14000f9b8`
- `0x140010350`
- `0x140011b98`
- `0x140012744`
- `0x140012850`
- `0x140012a90`
- `0x140013fb0`
- `0x1400149e0`
- `0x140014bf0`
- `0x140014e00`
- `0x140014f30`
- `0x140015a48`
- `0x140015d3c`
- `0x14001606c`
- `0x140016fa0`
- `0x140017284`
- `0x140017700`
- `0x140018078`

## callees

- `0x140002fa0`
- `0x140003920`

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
0x140003920  cmp     rcx, cs:__security_cookie
0x140003927  jnz     short ReportFailure
0x140003929  rol     rcx, 10h
0x14000392d  test    cx, 0FFFFh
0x140003932  jnz     short RestoreRcx
0x140003934  retn
0x140003935  ror     rcx, 10h; StackCookie
0x140003939  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x14000da60`
- end: `0x14000da7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400095b8`
- `0x140009a30`
- `0x140009aac`
- `0x140009b28`
- `0x140009ba4`
- `0x140009c64`
- `0x140009f9c`
- `0x14000a018`
- `0x14000a154`
- `0x14000a394`
- `0x14000a410`
- `0x14000a48c`
- `0x14000a508`
- `0x14000a584`
- `0x14000a600`
- `0x14000afe8`
- `0x14000b23c`
- `0x14000b2b8`
- `0x14000bb7c`
- `0x14000bbf8`
- `0x14000bc74`
- `0x14000bcf0`
- `0x14000cbe0`
- `0x14000d92c`
- `0x140017504`
- `0x140017ee0`
- `0x140018bf0`
- `0x140019490`
- `0x140019cfc`
- `0x14001b924`
- `0x140021a98`

## callees

- `0x140008f60`
- `0x14000da60`

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
0x14000da60  cmp     rcx, cs:__security_cookie
0x14000da67  jnz     short ReportFailure
0x14000da69  rol     rcx, 10h
0x14000da6d  test    cx, 0FFFFh
0x14000da72  jnz     short RestoreRcx
0x14000da74  retn
0x14000da75  ror     rcx, 10h; StackCookie
0x14000da79  jmp     __report_gsfailure
```

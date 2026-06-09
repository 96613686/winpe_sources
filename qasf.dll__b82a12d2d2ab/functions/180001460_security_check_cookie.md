# __security_check_cookie

- ea: `0x180001460`
- end: `0x18000147e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `120`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ee0`
- `0x1800020b0`
- `0x18000222c`
- `0x180002500`
- `0x1800026d4`
- `0x18000277c`
- `0x1800028b0`
- `0x180002ba4`
- `0x180002eb4`
- `0x180002f3c`
- `0x180004430`
- `0x1800050d0`
- `0x1800069f0`
- `0x1800083d0`
- `0x1800085e0`
- `0x1800087d8`
- `0x180008980`
- `0x180008b9c`
- `0x180008cc0`
- `0x180008ef0`
- `0x180009140`
- `0x180009474`
- `0x180009838`
- `0x1800098f0`
- `0x180009b40`
- `0x180009c50`
- `0x180009d70`
- `0x18000a190`
- `0x18000a250`
- `0x18000a508`
- `0x18000a740`
- `0x18000ab04`
- `0x18000b970`
- `0x18000bdd0`
- `0x18000ce10`
- `0x18000d150`
- `0x18000d1e0`
- `0x18000d5d0`
- `0x18000d6b0`
- `0x18000d7d0`
- `0x18000dc60`
- `0x18000e444`
- `0x18000e9a0`
- `0x18000ea00`
- `0x18000eff0`
- `0x18000f150`
- `0x18000f2d0`
- `0x18000f414`
- `0x18000f970`
- `0x18000fc80`

## callees

- `0x180001460`
- `0x180001990`

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

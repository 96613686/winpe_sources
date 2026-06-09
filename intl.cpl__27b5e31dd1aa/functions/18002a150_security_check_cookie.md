# __security_check_cookie

- ea: `0x18002a150`
- end: `0x18002a16e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `142`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010f4`
- `0x1800013a8`
- `0x1800016a0`
- `0x1800018c8`
- `0x180001910`
- `0x180001c24`
- `0x180001c94`
- `0x180001d24`
- `0x180001e20`
- `0x1800020c4`
- `0x180002400`
- `0x180003780`
- `0x1800038ac`
- `0x180003d40`
- `0x180003fdc`
- `0x180004660`
- `0x1800047f4`
- `0x180004ba4`
- `0x180004fa0`
- `0x1800064e4`
- `0x180007130`
- `0x18000739c`
- `0x180007520`
- `0x180007684`
- `0x18000793c`
- `0x180007b70`
- `0x180007cec`
- `0x18000849c`
- `0x1800085b8`
- `0x180009218`
- `0x1800096fc`
- `0x180009b5c`
- `0x18000a0f4`
- `0x18000a73c`
- `0x18000ad4c`
- `0x18000b000`
- `0x18000b8c8`
- `0x18000ba98`
- `0x18000c1e8`
- `0x18000c454`
- `0x18000c870`
- `0x18000dce0`
- `0x18000fbd4`
- `0x180010024`
- `0x180010408`
- `0x180010c48`
- `0x180011040`
- `0x1800112a0`
- `0x1800116f8`

## callees

- `0x1800031c0`
- `0x18002a150`

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
0x18002a150  cmp     rcx, cs:__security_cookie
0x18002a157  jnz     short ReportFailure
0x18002a159  rol     rcx, 10h
0x18002a15d  test    cx, 0FFFFh
0x18002a162  jnz     short RestoreRcx
0x18002a164  retn
0x18002a165  ror     rcx, 10h
0x18002a169  jmp     __report_gsfailure
```

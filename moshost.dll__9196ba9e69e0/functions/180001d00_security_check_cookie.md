# __security_check_cookie

- ea: `0x180001d00`
- end: `0x180001d1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180002ef8`
- `0x180003194`
- `0x180003734`
- `0x180003ad8`
- `0x180004034`
- `0x1800043b0`
- `0x180005cdc`
- `0x180006190`
- `0x18000642c`
- `0x18000668c`
- `0x180006750`
- `0x180007550`
- `0x180007680`
- `0x180007930`
- `0x1800079e0`
- `0x180008690`
- `0x180008898`
- `0x180009540`
- `0x180009660`
- `0x180009a80`
- `0x18000a480`
- `0x18000a6a4`
- `0x18000ac7c`
- `0x18000af38`
- `0x18000b30c`
- `0x18000b38c`
- `0x18000bef4`
- `0x18000bf98`
- `0x18000c5e0`

## callees

- `0x180001d00`
- `0x180002310`

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
0x180001d00  cmp     rcx, cs:__security_cookie
0x180001d07  jnz     short ReportFailure
0x180001d09  rol     rcx, 10h
0x180001d0d  test    cx, 0FFFFh
0x180001d12  jnz     short RestoreRcx
0x180001d14  retn
0x180001d15  ror     rcx, 10h; StackCookie
0x180001d19  jmp     __report_gsfailure
```

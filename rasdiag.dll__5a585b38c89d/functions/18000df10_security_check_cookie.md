# __security_check_cookie

- ea: `0x18000df10`
- end: `0x18000df2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000288c`
- `0x1800029fc`
- `0x1800030ec`
- `0x18000387c`
- `0x180003a50`
- `0x180003f80`
- `0x180004694`
- `0x1800049dc`
- `0x180004b4c`
- `0x180004cf0`
- `0x180004ef8`
- `0x18000574c`
- `0x18000596c`
- `0x1800086b0`
- `0x180009924`
- `0x180009e60`
- `0x18000a918`
- `0x18000ad60`
- `0x18000b864`
- `0x18000c310`
- `0x18000ca8c`

## callees

- `0x1800021f0`
- `0x18000df10`

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
0x18000df10  cmp     rcx, cs:__security_cookie
0x18000df17  jnz     short ReportFailure
0x18000df19  rol     rcx, 10h
0x18000df1d  test    cx, 0FFFFh
0x18000df22  jnz     short RestoreRcx
0x18000df24  retn
0x18000df25  ror     rcx, 10h
0x18000df29  jmp     __report_gsfailure
```

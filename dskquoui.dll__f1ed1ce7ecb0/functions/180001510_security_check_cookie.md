# __security_check_cookie

- ea: `0x180001510`
- end: `0x18000152e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `70`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000288c`
- `0x180002b28`
- `0x1800030c8`
- `0x18000346c`
- `0x1800039b4`
- `0x180003d30`
- `0x18000553c`
- `0x1800059f0`
- `0x180005ebc`
- `0x1800064cc`
- `0x180006c54`
- `0x180008150`
- `0x1800081ec`
- `0x180008510`
- `0x180008640`
- `0x180008720`
- `0x180008c30`
- `0x180008f80`
- `0x1800092f4`
- `0x18000946c`
- `0x18000a07c`
- `0x18000a510`
- `0x18000abe4`
- `0x18000ad00`
- `0x18000b52c`
- `0x18000b8fc`
- `0x18000bd88`
- `0x18000c674`
- `0x18000d138`
- `0x18000d4d0`
- `0x18000da5c`
- `0x18000dc40`
- `0x18000dd24`
- `0x18000de10`
- `0x18000e190`
- `0x18000e4fc`
- `0x18000ed94`
- `0x18000f620`
- `0x18000fc54`
- `0x18001058c`
- `0x180010758`
- `0x180010960`
- `0x180011790`
- `0x18001230c`
- `0x180012e94`
- `0x18001387c`
- `0x180013a48`
- `0x1800151c0`
- `0x180015cf0`
- `0x180015dc0`

## callees

- `0x180001510`
- `0x1800019f0`

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
0x180001510  cmp     rcx, cs:__security_cookie
0x180001517  jnz     short ReportFailure
0x180001519  rol     rcx, 10h
0x18000151d  test    cx, 0FFFFh
0x180001522  jnz     short RestoreRcx
0x180001524  retn
0x180001525  ror     rcx, 10h; StackCookie
0x180001529  jmp     __report_gsfailure
```

# __security_check_cookie

- ea: `0x180018a80`
- end: `0x180018a9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `59`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010f8`
- `0x1800013ac`
- `0x18000141c`
- `0x1800014ac`
- `0x180001750`
- `0x180001a48`
- `0x180001bd8`
- `0x180001eb0`
- `0x180001f84`
- `0x180002f7c`
- `0x18000309c`
- `0x18000427c`
- `0x180004518`
- `0x1800049e0`
- `0x180004b74`
- `0x180004f24`
- `0x180005320`
- `0x18000658c`
- `0x180007418`
- `0x1800076f0`
- `0x180009de8`
- `0x18000a9c0`
- `0x18000abc8`
- `0x18000b1e4`
- `0x18000b47c`
- `0x18000ba1c`
- `0x18000c0c8`
- `0x18000d0cc`
- `0x18000d348`
- `0x18000d45c`
- `0x18000d5d0`
- `0x18000d764`
- `0x18000ddbc`
- `0x18000dfcc`
- `0x18000e224`
- `0x18000eca0`
- `0x18000fac8`
- `0x1800102ec`
- `0x180011164`
- `0x180011348`
- `0x180011974`
- `0x1800126d0`
- `0x180014f30`
- `0x18001510c`
- `0x1800151fc`
- `0x180015324`
- `0x1800154e8`
- `0x18001568c`
- `0x180015858`

## callees

- `0x180002a80`
- `0x180018a80`

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
0x180018a80  cmp     rcx, cs:__security_cookie
0x180018a87  jnz     short ReportFailure
0x180018a89  rol     rcx, 10h
0x180018a8d  test    cx, 0FFFFh
0x180018a92  jnz     short RestoreRcx
0x180018a94  retn
0x180018a95  ror     rcx, 10h
0x180018a99  jmp     __report_gsfailure
```

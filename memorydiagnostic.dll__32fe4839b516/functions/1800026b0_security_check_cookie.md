# __security_check_cookie

- ea: `0x1800026b0`
- end: `0x1800026ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001098`
- `0x180001178`
- `0x180001224`
- `0x1800012d0`
- `0x180001398`
- `0x180001650`
- `0x180001950`
- `0x180001b30`
- `0x180003ca8`
- `0x18000487c`
- `0x1800049c4`
- `0x180004f4c`
- `0x1800055b0`
- `0x180005870`
- `0x180006140`
- `0x180006300`
- `0x180006a0c`
- `0x180008cc4`
- `0x1800090b8`
- `0x180009504`
- `0x18000a1a8`
- `0x18000a490`
- `0x18000b3e0`
- `0x18000d474`
- `0x18000d8c0`
- `0x18000e790`
- `0x18000e964`
- `0x18000f86c`
- `0x18000f97c`
- `0x1800103c4`
- `0x1800121a0`
- `0x1800145d0`
- `0x1800152b8`
- `0x180016694`
- `0x180016740`
- `0x180016b34`
- `0x180016dfc`
- `0x1800172f4`
- `0x1800180cc`
- `0x180019660`
- `0x180019820`
- `0x180019a18`
- `0x180019e40`
- `0x180019f6c`
- `0x18001a748`
- `0x18001b364`
- `0x18001d310`
- `0x18001e018`
- `0x18001ead0`

## callees

- `0x1800026b0`
- `0x180002ec0`

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
0x1800026b0  cmp     rcx, cs:__security_cookie
0x1800026b7  jnz     short ReportFailure
0x1800026b9  rol     rcx, 10h
0x1800026bd  test    cx, 0FFFFh
0x1800026c2  jnz     short RestoreRcx
0x1800026c4  retn
0x1800026c5  ror     rcx, 10h
0x1800026c9  jmp     __report_gsfailure
```

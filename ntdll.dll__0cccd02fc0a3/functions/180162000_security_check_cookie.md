# __security_check_cookie

- ea: `0x180162000`
- end: `0x18016201e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `552`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010fc`
- `0x1800012e0`
- `0x1800015ac`
- `0x180001690`
- `0x180001a50`
- `0x180002120`
- `0x1800028a0`
- `0x180002ce0`
- `0x1800034a0`
- `0x1800090b0`
- `0x1800094d0`
- `0x180009d60`
- `0x18000a070`
- `0x18000b730`
- `0x18000be70`
- `0x18000d3e0`
- `0x18000e7c0`
- `0x18000f570`
- `0x18000f610`
- `0x180010870`
- `0x180012664`
- `0x180012c8c`
- `0x180012eb0`
- `0x180013370`
- `0x180013540`
- `0x180013820`
- `0x180013ed0`
- `0x1800145b0`
- `0x180014f80`
- `0x1800152b0`
- `0x180015710`
- `0x1800159b0`
- `0x180015d00`
- `0x180016fa0`
- `0x180018640`
- `0x180018bc0`
- `0x1800195a0`
- `0x180019d50`
- `0x18001a0d0`
- `0x18001a420`
- `0x18001a590`
- `0x18001aa40`
- `0x18001ae70`
- `0x18001b9b0`
- `0x18001bcb0`
- `0x18001c520`
- `0x18001d4b0`
- `0x18001eb80`
- `0x18001faf0`

## callees

- `0x1801257f0`
- `0x180162000`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x180162000  cmp     rcx, cs:__security_cookie
0x180162007  jnz     short loc_180162019
0x180162009  rol     rcx, 10h
0x18016200d  test    cx, 0FFFFh
0x180162012  jnz     short loc_180162015
0x180162014  retn
0x180162015  ror     rcx, 10h
0x180162019  jmp     __report_gsfailure
```

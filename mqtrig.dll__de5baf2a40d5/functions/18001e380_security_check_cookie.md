# __security_check_cookie

- ea: `0x18001e380`
- end: `0x18001e39e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800018b8`
- `0x180001d24`
- `0x180003460`
- `0x180003640`
- `0x180003e5c`
- `0x180004608`
- `0x180004e84`
- `0x180008d68`
- `0x18000995c`
- `0x18000a300`
- `0x18000aa80`
- `0x18000aea0`
- `0x18000b760`
- `0x18000bd0c`
- `0x18000bda0`
- `0x18000c720`
- `0x18000d520`
- `0x180010590`
- `0x18001108c`
- `0x180011778`
- `0x1800124f0`
- `0x180012770`
- `0x180012bf8`
- `0x180013524`
- `0x1800137ec`
- `0x1800141cc`
- `0x180014d30`
- `0x1800151dc`
- `0x180015440`
- `0x1800158cc`
- `0x180015af8`
- `0x180015f38`
- `0x180016024`
- `0x1800161a8`
- `0x180016270`
- `0x1800164c8`
- `0x180016944`
- `0x180016d90`
- `0x1800174d4`
- `0x1800175dc`
- `0x1800176ec`
- `0x180019230`
- `0x1800199a0`
- `0x18001a15c`
- `0x18001a968`
- `0x18001ab60`
- `0x18001b110`
- `0x18001b1d4`
- `0x18001b27c`
- `0x18001b5a0`

## callees

- `0x180001b40`
- `0x18001e380`

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
0x18001e380  cmp     rcx, cs:__security_cookie
0x18001e387  jnz     short ReportFailure
0x18001e389  rol     rcx, 10h
0x18001e38d  test    cx, 0FFFFh
0x18001e392  jnz     short RestoreRcx
0x18001e394  retn
0x18001e395  ror     rcx, 10h
0x18001e399  jmp     __report_gsfailure
```

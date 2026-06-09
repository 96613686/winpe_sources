# __security_check_cookie

- ea: `0x180031040`
- end: `0x18003105e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019dcc`
- `0x18001a1e0`
- `0x18001ba78`
- `0x18001bd28`
- `0x18001c684`
- `0x18001ca7c`
- `0x18001ce90`
- `0x18001d9d4`
- `0x18001dd60`
- `0x18001eb40`
- `0x18001f048`
- `0x18001f390`
- `0x18001f5ec`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x180021828`
- `0x180021b10`
- `0x1800235e0`
- `0x180023964`
- `0x180023a74`
- `0x180024484`
- `0x180025aac`
- `0x1800266fc`
- `0x1800268f0`
- `0x180026ed4`
- `0x1800291e4`
- `0x18002b7cc`
- `0x18002b894`
- `0x18002b94c`
- `0x18002ba2c`
- `0x18002c99c`
- `0x18002ccd0`
- `0x18002cf60`
- `0x18002dd00`
- `0x18002e330`
- `0x18002ed24`
- `0x18002f194`
- `0x1800304c4`
- `0x180030f88`

## callees

- `0x180001a40`
- `0x180031040`

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
0x180031040  cmp     rcx, cs:__security_cookie
0x180031047  jnz     short ReportFailure
0x180031049  rol     rcx, 10h
0x18003104d  test    cx, 0FFFFh
0x180031052  jnz     short RestoreRcx
0x180031054  retn
0x180031055  ror     rcx, 10h
0x180031059  jmp     __report_gsfailure
```

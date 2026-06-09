# __security_check_cookie

- ea: `0x180010840`
- end: `0x18001085e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180002a84`
- `0x180003574`
- `0x18000368c`
- `0x180003a54`
- `0x180003c38`
- `0x180003e20`
- `0x180004c74`
- `0x1800076a0`
- `0x18000ad04`
- `0x18000ae18`
- `0x18000af24`
- `0x18000b048`
- `0x18000b184`
- `0x18000b860`
- `0x18000ef40`
- `0x1800101dc`
- `0x18001072c`
- `0x18001f870`
- `0x18001fd20`
- `0x18001ff10`
- `0x1800216f0`
- `0x180021870`
- `0x180022800`
- `0x180022bd0`
- `0x180022f00`
- `0x1800232d0`
- `0x180023a28`
- `0x1800240e0`
- `0x1800242e0`
- `0x1800248c0`
- `0x180025db0`
- `0x180027420`
- `0x180027d28`
- `0x18002b078`
- `0x18002b7ac`

## callees

- `0x180007a30`
- `0x180010840`

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
0x180010840  cmp     rcx, cs:__security_cookie
0x180010847  jnz     short ReportFailure
0x180010849  rol     rcx, 10h
0x18001084d  test    cx, 0FFFFh
0x180010852  jnz     short RestoreRcx
0x180010854  retn
0x180010855  ror     rcx, 10h; StackCookie
0x180010859  jmp     __report_gsfailure
```

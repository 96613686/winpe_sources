# __security_check_cookie

- ea: `0x18001cef0`
- end: `0x18001cf0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `140`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001e90`
- `0x1800026fc`
- `0x1800032b8`
- `0x180003544`
- `0x180003ea0`
- `0x1800042b8`
- `0x1800044cc`
- `0x180005f28`
- `0x180006bd0`
- `0x1800079e4`
- `0x180008240`
- `0x1800083b8`
- `0x180008740`
- `0x1800089f8`
- `0x180008b04`
- `0x180008c5c`
- `0x180008ce8`
- `0x180008d58`
- `0x180008e6c`
- `0x180008ed0`
- `0x180008f98`
- `0x180009038`
- `0x180009090`
- `0x180009108`
- `0x180009174`
- `0x180009264`
- `0x180009310`
- `0x1800093ac`
- `0x18000941c`
- `0x1800094f0`
- `0x1800095d8`
- `0x18000a194`
- `0x18000ac74`
- `0x18000b650`
- `0x18000b82c`
- `0x18000bc40`
- `0x18000c090`
- `0x18000c7dc`
- `0x18000cc70`
- `0x18000cf2c`
- `0x18000d364`
- `0x18000e77c`
- `0x18000e930`
- `0x18000ef2c`
- `0x18000f51c`
- `0x1800104e4`
- `0x1800106e8`
- `0x18001098c`
- `0x180010b44`

## callees

- `0x18001cef0`
- `0x18001cf20`

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
0x18001cef0  cmp     rcx, cs:__security_cookie
0x18001cef7  jnz     short ReportFailure
0x18001cef9  rol     rcx, 10h
0x18001cefd  test    cx, 0FFFFh
0x18001cf02  jnz     short RestoreRcx
0x18001cf04  retn
0x18001cf05  ror     rcx, 10h; StackCookie
0x18001cf09  jmp     __report_gsfailure
```

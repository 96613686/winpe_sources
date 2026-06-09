# __security_check_cookie

- ea: `0x18001ca70`
- end: `0x18001ca8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `58`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180002978`
- `0x180002c14`
- `0x1800037a8`
- `0x180003b4c`
- `0x180003f1c`
- `0x1800048b4`
- `0x180004c30`
- `0x18000587c`
- `0x180005afc`
- `0x1800063d0`
- `0x18000770c`
- `0x180008110`
- `0x180008220`
- `0x180008ac0`
- `0x180009660`
- `0x18000a428`
- `0x18000a810`
- `0x18000af40`
- `0x18000bc20`
- `0x18000bd70`
- `0x18000c020`
- `0x18000c584`
- `0x18000c6e4`
- `0x18000d658`
- `0x18000d9b4`
- `0x18000dcd0`
- `0x18000e344`
- `0x18000e5a4`
- `0x18000e7d0`
- `0x18000ebd4`
- `0x18000ee64`
- `0x18000f3ec`
- `0x18001084c`
- `0x180011550`
- `0x180011d84`
- `0x1800123fc`
- `0x180012860`
- `0x180012ddc`
- `0x1800147d4`
- `0x180014e20`
- `0x1800151b8`
- `0x180015460`
- `0x1800165a4`
- `0x180017510`
- `0x180018540`
- `0x180018be0`
- `0x180019260`
- `0x1800195cc`
- `0x18001a9e0`

## callees

- `0x180001c20`
- `0x18001ca70`

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
0x18001ca70  cmp     rcx, cs:__security_cookie
0x18001ca77  jnz     short ReportFailure
0x18001ca79  rol     rcx, 10h
0x18001ca7d  test    cx, 0FFFFh
0x18001ca82  jnz     short RestoreRcx
0x18001ca84  retn
0x18001ca85  ror     rcx, 10h
0x18001ca89  jmp     __report_gsfailure
```

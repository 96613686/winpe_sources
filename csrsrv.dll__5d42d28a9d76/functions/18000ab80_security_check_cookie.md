# __security_check_cookie

- ea: `0x18000ab80`
- end: `0x18000ab9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001140`
- `0x180001c50`
- `0x180002a00`
- `0x180002c90`
- `0x1800035c0`
- `0x180003ea0`
- `0x180003f20`
- `0x1800042b0`
- `0x1800050c0`
- `0x180005180`
- `0x1800058b0`
- `0x1800064b0`
- `0x180006700`
- `0x180006820`
- `0x180006a80`
- `0x180006d20`
- `0x180006df0`
- `0x180007060`
- `0x180007b70`
- `0x180007ee0`
- `0x180008540`
- `0x180008ca4`
- `0x180008f00`
- `0x180009370`
- `0x1800095c0`
- `0x1800097f0`
- `0x18000a070`
- `0x18000a2b0`
- `0x18000aa7c`

## callees

- `0x1800089d0`
- `0x18000ab80`

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
0x18000ab80  cmp     rcx, cs:__security_cookie
0x18000ab87  jnz     short loc_18000AB99
0x18000ab89  rol     rcx, 10h
0x18000ab8d  test    cx, 0FFFFh
0x18000ab92  jnz     short loc_18000AB95
0x18000ab94  retn
0x18000ab95  ror     rcx, 10h
0x18000ab99  jmp     __report_gsfailure
```

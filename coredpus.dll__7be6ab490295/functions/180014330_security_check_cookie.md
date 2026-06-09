# __security_check_cookie

- ea: `0x180014330`
- end: `0x18001434e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `103`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001190`
- `0x1800011d4`
- `0x1800012b0`
- `0x180001390`
- `0x180001488`
- `0x180001584`
- `0x18000169c`
- `0x1800017e8`
- `0x180001878`
- `0x180001950`
- `0x180001a44`
- `0x180001ae0`
- `0x180001bd0`
- `0x180001c78`
- `0x180002380`
- `0x180002860`
- `0x180002dd0`
- `0x1800034d0`
- `0x180003a50`
- `0x180003b60`
- `0x180003f70`
- `0x180004b00`
- `0x180004f00`
- `0x180005370`
- `0x180005bd0`
- `0x1800060a0`
- `0x1800070a0`
- `0x180007820`
- `0x180007e80`
- `0x180008620`
- `0x180008d30`
- `0x180009380`
- `0x180009560`
- `0x180009760`
- `0x180009c70`
- `0x18000a0d0`
- `0x18000a760`
- `0x18000ab90`
- `0x18000adf0`
- `0x18000b560`
- `0x18000bc70`
- `0x18000bf60`
- `0x18000c600`
- `0x18000cfb0`
- `0x18000d510`
- `0x18000e020`
- `0x18000e1a0`
- `0x18000e490`
- `0x18000e940`

## callees

- `0x180014330`
- `0x180014c50`

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
0x180014330  cmp     rcx, cs:__security_cookie
0x180014337  jnz     short ReportFailure
0x180014339  rol     rcx, 10h
0x18001433d  test    cx, 0FFFFh
0x180014342  jnz     short RestoreRcx
0x180014344  retn
0x180014345  ror     rcx, 10h; StackCookie
0x180014349  jmp     __report_gsfailure
```

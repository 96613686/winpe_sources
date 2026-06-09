# __security_check_cookie

- ea: `0x1800cbde0`
- end: `0x1800cbdfe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `183`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010c0`
- `0x1800011a0`
- `0x180001420`
- `0x1800014e0`
- `0x180001594`
- `0x180002090`
- `0x180002690`
- `0x180003070`
- `0x180003db0`
- `0x1800051d0`
- `0x1800062f0`
- `0x180007b20`
- `0x180008500`
- `0x1800090d0`
- `0x1800095a0`
- `0x18000a400`
- `0x18000b150`
- `0x18000c180`
- `0x18000c6d0`
- `0x18000ccf0`
- `0x18000db40`
- `0x18000f8e0`
- `0x180010890`
- `0x180011d00`
- `0x1800128b0`
- `0x180013190`
- `0x180014a30`
- `0x180014d70`
- `0x1800152d0`
- `0x180016c50`
- `0x180018ba0`
- `0x180018ce0`
- `0x18001a280`
- `0x18001ae10`
- `0x18001b260`
- `0x18001b5a0`
- `0x18001b920`
- `0x18001c860`
- `0x18001cc30`
- `0x18001d0f0`
- `0x18001eed0`
- `0x18001ffc0`
- `0x180020100`
- `0x180020270`
- `0x1800243d0`
- `0x1800247e0`
- `0x180024e90`
- `0x180025680`
- `0x180025968`
- `0x18002635c`

## callees

- `0x1800cbde0`
- `0x1800cc6f0`

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
0x1800cbde0  cmp     rcx, cs:__security_cookie
0x1800cbde7  jnz     short ReportFailure
0x1800cbde9  rol     rcx, 10h
0x1800cbded  test    cx, 0FFFFh
0x1800cbdf2  jnz     short RestoreRcx
0x1800cbdf4  retn
0x1800cbdf5  ror     rcx, 10h; StackCookie
0x1800cbdf9  jmp     __report_gsfailure
```

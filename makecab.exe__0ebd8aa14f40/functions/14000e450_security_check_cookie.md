# __security_check_cookie

- ea: `0x14000e450`
- end: `0x14000e46e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001de0`
- `0x140002c80`
- `0x1400034e4`
- `0x140003a30`
- `0x14000488c`
- `0x1400052b0`
- `0x140005c80`
- `0x140006a6c`
- `0x140007934`
- `0x140007e18`
- `0x140008244`
- `0x14000836c`
- `0x14000895c`
- `0x140008a78`
- `0x140008b90`
- `0x14000907c`
- `0x140009454`
- `0x140009938`
- `0x140009b38`
- `0x140009c24`
- `0x14000a000`
- `0x14000aa6c`
- `0x14000b128`
- `0x14000b2d8`
- `0x14000b890`
- `0x14000c2bc`
- `0x14000c6d4`
- `0x14000cb80`
- `0x14000cec0`
- `0x14000d528`
- `0x14000d70c`
- `0x14000d9c8`
- `0x14000dcf8`
- `0x14000e0c4`
- `0x14000e1f4`
- `0x14000e394`

## callees

- `0x140001360`
- `0x14000e450`

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
0x14000e450  cmp     rcx, cs:__security_cookie
0x14000e457  jnz     short loc_14000E469
0x14000e459  rol     rcx, 10h
0x14000e45d  test    cx, 0FFFFh
0x14000e462  jnz     short loc_14000E465
0x14000e464  retn
0x14000e465  ror     rcx, 10h
0x14000e469  jmp     __report_gsfailure
```

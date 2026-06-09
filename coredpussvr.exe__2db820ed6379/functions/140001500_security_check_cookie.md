# __security_check_cookie

- ea: `0x140001500`
- end: `0x14000151e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002788`
- `0x140002a38`
- `0x14000308c`
- `0x1400035e4`
- `0x140003980`
- `0x140004340`
- `0x1400052dc`
- `0x1400058a0`
- `0x1400061bc`
- `0x140007110`
- `0x14000756c`
- `0x1400076dc`
- `0x140007880`
- `0x140007a88`
- `0x14000836c`
- `0x140008460`
- `0x14000878c`
- `0x140008f48`

## callees

- `0x140001500`
- `0x1400017e0`

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
0x140001500  cmp     rcx, cs:__security_cookie
0x140001507  jnz     short loc_140001519
0x140001509  rol     rcx, 10h
0x14000150d  test    cx, 0FFFFh
0x140001512  jnz     short loc_140001515
0x140001514  retn
0x140001515  ror     rcx, 10h; StackCookie
0x140001519  jmp     __report_gsfailure
```

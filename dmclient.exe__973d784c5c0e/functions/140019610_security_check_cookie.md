# __security_check_cookie

- ea: `0x140019610`
- end: `0x14001962e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001098`
- `0x140001418`
- `0x14000153c`
- `0x140001604`
- `0x1400016fc`
- `0x1400018e4`
- `0x1400019a8`
- `0x140001a9c`
- `0x140001bb4`
- `0x140001c5c`
- `0x140001d80`
- `0x140003b48`
- `0x140003df0`
- `0x140004ce4`
- `0x140005740`
- `0x140005bd4`
- `0x140006d84`
- `0x140007174`
- `0x14000784c`
- `0x1400081c4`
- `0x14000a3c4`
- `0x14000ac6c`
- `0x14000b9ec`
- `0x14000c800`
- `0x14000c928`
- `0x14000dff4`
- `0x14000e290`
- `0x14000ee98`
- `0x14000fbf8`
- `0x140010638`
- `0x140010acc`
- `0x140010c40`
- `0x140011580`
- `0x140011cd0`
- `0x140012928`
- `0x140012e10`
- `0x1400135d4`
- `0x140013ebc`
- `0x140014774`
- `0x140014a40`
- `0x140015fb4`
- `0x140016818`
- `0x14001691c`
- `0x140016d68`
- `0x140016fe4`
- `0x1400178ac`
- `0x140018700`
- `0x140018b0c`
- `0x14001920c`

## callees

- `0x140002b30`
- `0x140019610`

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
0x140019610  cmp     rcx, cs:__security_cookie
0x140019617  jnz     short loc_140019629
0x140019619  rol     rcx, 10h
0x14001961d  test    cx, 0FFFFh
0x140019622  jnz     short loc_140019625
0x140019624  retn
0x140019625  ror     rcx, 10h
0x140019629  jmp     __report_gsfailure
```

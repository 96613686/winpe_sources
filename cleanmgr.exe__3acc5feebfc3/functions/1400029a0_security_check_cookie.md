# __security_check_cookie

- ea: `0x1400029a0`
- end: `0x1400029be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `62`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400012b8`
- `0x14000156c`
- `0x140001864`
- `0x140001a88`
- `0x140001ad0`
- `0x140001b94`
- `0x140001cb8`
- `0x140001fb4`
- `0x1400020ec`
- `0x1400022a0`
- `0x140002330`
- `0x140003868`
- `0x140003b04`
- `0x140004238`
- `0x1400043e4`
- `0x140004794`
- `0x140004b90`
- `0x1400061a0`
- `0x1400067a0`
- `0x140007260`
- `0x1400076d0`
- `0x140007b00`
- `0x1400080a8`
- `0x1400083c8`
- `0x140008750`
- `0x140008908`
- `0x140008ff8`
- `0x140009d34`
- `0x14000a534`
- `0x14000a8c8`
- `0x14000ad18`
- `0x14000b3d0`
- `0x14000b5bc`
- `0x14000b6dc`
- `0x14000b780`
- `0x14000bae4`
- `0x14000bd24`
- `0x14000c1f4`
- `0x14000c538`
- `0x14000c678`
- `0x14000de50`
- `0x14000eae4`
- `0x14000fa20`
- `0x140010a00`
- `0x140010be4`
- `0x1400124b8`
- `0x140012a7c`
- `0x140013530`
- `0x140014fe0`

## callees

- `0x1400029a0`
- `0x140002c70`

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
0x1400029a0  cmp     rcx, cs:__security_cookie
0x1400029a7  jnz     short loc_1400029B9
0x1400029a9  rol     rcx, 10h
0x1400029ad  test    cx, 0FFFFh
0x1400029b2  jnz     short loc_1400029B5
0x1400029b4  retn
0x1400029b5  ror     rcx, 10h; StackCookie
0x1400029b9  jmp     __report_gsfailure
```

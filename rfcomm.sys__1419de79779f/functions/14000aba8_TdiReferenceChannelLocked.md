# TdiReferenceChannelLocked

- ea: `0x14000aba8`
- end: `0x14000abdc`
- name: `TdiReferenceChannelLocked`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000280c`
- `0x140002ac8`
- `0x140003970`
- `0x140006a04`
- `0x140008ac0`
- `0x1400097f4`
- `0x14000a5f0`
- `0x14000aca0`

## callees

- `0x14000aba8`
- `0x14001e74c`

## string_xrefs

- `0x14000abc0`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiReferenceChannelLocked(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a1 + 272);
  if ( v2 )
    RefObj_AddRefEx(v2 + 24, a2, 4443, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  return v2;
}

```

## disassembly

```asm
0x14000aba8  push    rbx
0x14000abaa  sub     rsp, 20h
0x14000abae  mov     rbx, [rcx+110h]
0x14000abb5  test    rbx, rbx
0x14000abb8  jz      short loc_14000ABD2
0x14000abba  mov     edx, edx
0x14000abbc  lea     rcx, [rbx+18h]
0x14000abc0  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000abc7  mov     r8d, 115Bh
0x14000abcd  call    RefObj_AddRefEx
0x14000abd2  mov     rax, rbx
0x14000abd5  add     rsp, 20h
0x14000abd9  pop     rbx
0x14000abda  retn
```

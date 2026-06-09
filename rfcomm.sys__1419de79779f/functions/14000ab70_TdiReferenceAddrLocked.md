# TdiReferenceAddrLocked

- ea: `0x14000ab70`
- end: `0x14000aba1`
- name: `TdiReferenceAddrLocked`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400079c0`
- `0x140007b60`
- `0x1400085a0`
- `0x14000877c`
- `0x1400097f4`
- `0x14000a5f0`
- `0x14001190c`
- `0x140014eb4`
- `0x140018330`
- `0x1400186b4`
- `0x140018e9c`

## callees

- `0x14000ab70`
- `0x14001e74c`

## string_xrefs

- `0x14000ab85`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiReferenceAddrLocked(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a1 + 104);
  if ( v2 )
    RefObj_AddRefEx(v2 + 24, a2, 4409, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  return v2;
}

```

## disassembly

```asm
0x14000ab70  push    rbx
0x14000ab72  sub     rsp, 20h
0x14000ab76  mov     rbx, [rcx+68h]
0x14000ab7a  test    rbx, rbx
0x14000ab7d  jz      short loc_14000AB97
0x14000ab7f  mov     edx, edx
0x14000ab81  lea     rcx, [rbx+18h]
0x14000ab85  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000ab8c  mov     r8d, 1139h
0x14000ab92  call    RefObj_AddRefEx
0x14000ab97  mov     rax, rbx
0x14000ab9a  add     rsp, 20h
0x14000ab9e  pop     rbx
0x14000ab9f  retn
```

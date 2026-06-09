# ChannelReferenceConnLocked

- ea: `0x14001a12c`
- end: `0x14001a15d`
- name: `ChannelReferenceConnLocked`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010810`
- `0x140011634`
- `0x14001190c`
- `0x14001204c`
- `0x1400121d4`
- `0x140012c60`
- `0x1400197ec`

## callees

- `0x14001a12c`
- `0x14001e74c`

## string_xrefs

- `0x14001a141`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`

## pseudocode

```c
__int64 __fastcall ChannelReferenceConnLocked(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a1 + 64);
  if ( v2 )
    RefObj_AddRefEx(v2 + 24, a2, 1043, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
  return v2;
}

```

## disassembly

```asm
0x14001a12c  push    rbx
0x14001a12e  sub     rsp, 20h
0x14001a132  mov     rbx, [rcx+40h]
0x14001a136  test    rbx, rbx
0x14001a139  jz      short loc_14001A153
0x14001a13b  mov     edx, edx
0x14001a13d  lea     rcx, [rbx+18h]
0x14001a141  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001a148  mov     r8d, 413h
0x14001a14e  call    RefObj_AddRefEx
0x14001a153  mov     rax, rbx
0x14001a156  add     rsp, 20h
0x14001a15a  pop     rbx
0x14001a15b  retn
```

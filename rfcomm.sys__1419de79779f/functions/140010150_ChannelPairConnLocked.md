# ChannelPairConnLocked

- ea: `0x140010150`
- end: `0x14001025a`
- name: `ChannelPairConnLocked`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fc00`
- `0x140018e9c`

## callees

- `0x140003bf4`
- `0x140004e58`
- `0x140010150`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010217`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010217`
- `ntoskrnl!ObfReferenceObject` at `0x140010204`
- `ntoskrnl!ObfReferenceObject` at `0x140010204`

## string_xrefs

- `0x1400101bd`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x1400101db`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
void __fastcall ChannelPairConnLocked(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  int v5; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      168,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a2,
      a1);
  *(_BYTE *)(a2 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 48));
  RefObj_AddRefEx(a1 + 24, 1313754947, 5927, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  RefObj_AddRefEx(a2 + 24, 1111705667, 5928, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  *(_QWORD *)(a2 + 272) = a1;
  v4 = *(_QWORD *)(a1 + 56);
  *(_QWORD *)(a1 + 64) = a2;
  ObfReferenceObject(*(PVOID *)(*(_QWORD *)(v4 + 72) + 80LL));
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 48), *(_BYTE *)(a2 + 56));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      169,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
}

```

## disassembly

```asm
0x140010150  push    rbx
0x140010152  push    rsi
0x140010153  push    rdi
0x140010154  push    r14
0x140010156  push    r15
0x140010158  sub     rsp, 40h
0x14001015c  mov     rdi, rdx
0x14001015f  mov     rsi, rcx
0x140010162  lea     r15, WPP_RECORDER_INITIALIZED
0x140010169  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140010170  lea     r14, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140010177  jz      short loc_1400101A4
0x140010179  mov     [rsp+68h+var_38], rcx
0x14001017e  mov     r9d, 0A8h
0x140010184  mov     rcx, cs:WPP_GLOBAL_Control
0x14001018b  mov     r8d, 3
0x140010191  mov     [rsp+68h+var_40], rdx
0x140010196  mov     [rsp+68h+var_48], r14
0x14001019b  mov     rcx, [rcx+40h]
0x14001019f  call    WPP_RECORDER_SF_qq
0x1400101a4  lea     rcx, [rdi+30h]; SpinLock
0x1400101a8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400101af  nop     dword ptr [rax+rax+00h]
0x1400101b4  lea     rcx, [rsi+18h]
0x1400101b8  mov     edx, 4E4E4F43h
0x1400101bd  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400101c4  mov     [rdi+38h], al
0x1400101c7  mov     r8d, 1727h
0x1400101cd  call    RefObj_AddRefEx
0x1400101d2  lea     rcx, [rdi+18h]
0x1400101d6  mov     edx, 42434843h
0x1400101db  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400101e2  mov     r8d, 1728h
0x1400101e8  call    RefObj_AddRefEx
0x1400101ed  mov     [rdi+110h], rsi
0x1400101f4  mov     rax, [rsi+38h]
0x1400101f8  mov     [rsi+40h], rdi
0x1400101fc  mov     rcx, [rax+48h]
0x140010200  mov     rcx, [rcx+50h]; Object
0x140010204  call    cs:__imp_ObfReferenceObject
0x14001020b  nop     dword ptr [rax+rax+00h]
0x140010210  mov     dl, [rdi+38h]; NewIrql
0x140010213  lea     rcx, [rdi+30h]; SpinLock
0x140010217  call    cs:__imp_KeReleaseSpinLock
0x14001021e  nop     dword ptr [rax+rax+00h]
0x140010223  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001022a  jz      short loc_14001024D
0x14001022c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010233  mov     r9d, 0A9h
0x140010239  mov     r8d, 3
0x14001023f  mov     [rsp+68h+var_48], r14
0x140010244  mov     rcx, [rcx+40h]
0x140010248  call    WPP_RECORDER_SF_
0x14001024d  add     rsp, 40h
0x140010251  pop     r15
0x140010253  pop     r14
0x140010255  pop     rdi
0x140010256  pop     rsi
0x140010257  pop     rbx
0x140010258  retn
```

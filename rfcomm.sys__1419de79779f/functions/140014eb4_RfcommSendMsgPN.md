# RfcommSendMsgPN

- ea: `0x140014eb4`
- end: `0x140015134`
- name: `RfcommSendMsgPN`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018e9c`

## callees

- `0x140003818`
- `0x140003cb4`
- `0x140004a68`
- `0x14000ab70`
- `0x140010080`
- `0x1400135cc`
- `0x140013abc`
- `0x140013bf8`
- `0x140014eb4`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014f1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014f55`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014f1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014f55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014f45`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001507e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014f45`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001507e`

## string_xrefs

- `0x140015099`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x1400150cf`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall RfcommSendMsgPN(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // r15
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // r10
  unsigned int v10; // ebx
  bool v11; // cf
  char v12; // al
  unsigned __int16 v13; // ax
  __int64 v14; // rdx
  __int64 v15; // r10
  unsigned __int16 v16; // r11
  __int64 NextCmdLocked; // r14
  int v18; // edx
  unsigned int v20; // [rsp+80h] [rbp+8h] BYREF

  v20 = 10;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      65,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a2);
  v6 = *(_QWORD *)(a1 + 72);
  *(_BYTE *)(a3 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 48));
  v7 = TdiReferenceAddrLocked(a3, 1313754947);
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 48), *(_BYTE *)(a3 + 56));
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v8 = RfcommFrameAllocLockedEx(a1, (__int64 *)a2, 239, 32, 0, 0, &v20, a2 + 152, 0);
  v9 = v8;
  if ( v8 )
  {
    *(_WORD *)(v8 + 155) = 4483;
    v10 = 259;
    *(_BYTE *)(v8 + 157) = *(_BYTE *)(a2 + 184);
    v11 = *(_BYTE *)(v6 + 265) != 0;
    *(_BYTE *)(v8 + 158) = v11 ? 0xF0 : 0;
    *(_BYTE *)(v8 + 164) = v11 ? 7 : 0;
    v12 = *(_BYTE *)(a2 + 184);
    if ( v12 )
      v12 = (v12 & 0xF8) + 7;
    *(_BYTE *)(v9 + 159) = v12;
    *(_BYTE *)(v9 + 160) = 0;
    v13 = ChannelMaxMTULocked(a1, v7);
    if ( v16 >= v13 )
      v16 = ChannelMaxMTULocked(a1, v14);
    *(_WORD *)(v15 + 161) = v16;
    *(_BYTE *)(v15 + 163) = 0;
  }
  else
  {
    v10 = -1073741670;
  }
  NextCmdLocked = RfcommGetNextCmdLocked(a1, a2);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  RefObj_ReleaseEx(a2 + 24, 1313754947, 3053, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  if ( NextCmdLocked )
  {
    RfcommStartTimer(*(_QWORD *)(a1 + 72));
    RfcommFrameWrite(a1, NextCmdLocked);
  }
  if ( v7 )
    RefObj_ReleaseEx(v7 + 24, 1313754947, 3069, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      3,
      66,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v10);
  return v10;
}

```

## disassembly

```asm
0x140014eb4  mov     r11, rsp
0x140014eb7  mov     [r11+10h], rbx
0x140014ebb  mov     [r11+18h], rbp
0x140014ebf  push    rsi
0x140014ec0  push    rdi
0x140014ec1  push    r12
0x140014ec3  push    r14
0x140014ec5  push    r15
0x140014ec7  sub     rsp, 50h
0x140014ecb  mov     r14, r8
0x140014ece  mov     dword ptr [r11+8], 0Ah
0x140014ed6  mov     rbp, rdx
0x140014ed9  mov     rsi, rcx
0x140014edc  lea     rax, WPP_RECORDER_INITIALIZED
0x140014ee3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014eea  lea     rcx, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140014ef1  jz      short loc_140014F15
0x140014ef3  mov     [r11-50h], rdx
0x140014ef7  mov     r9d, 41h ; 'A'
0x140014efd  mov     [r11-58h], rcx
0x140014f01  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f08  lea     r8d, [r9-3Eh]
0x140014f0c  mov     rcx, [rcx+40h]
0x140014f10  call    WPP_RECORDER_SF_q
0x140014f15  mov     r15, [rsi+48h]
0x140014f19  lea     rcx, [r14+30h]; SpinLock
0x140014f1d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014f24  nop     dword ptr [rax+rax+00h]
0x140014f29  mov     edx, 4E4E4F43h
0x140014f2e  mov     rcx, r14
0x140014f31  mov     [r14+38h], al
0x140014f35  call    TdiReferenceAddrLocked
0x140014f3a  mov     dl, [r14+38h]; NewIrql
0x140014f3e  lea     rcx, [r14+30h]; SpinLock
0x140014f42  mov     rdi, rax
0x140014f45  call    cs:__imp_KeReleaseSpinLock
0x140014f4c  nop     dword ptr [rax+rax+00h]
0x140014f51  lea     rcx, [rsi+38h]; SpinLock
0x140014f55  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014f5c  nop     dword ptr [rax+rax+00h]
0x140014f61  mov     [rsp+78h+var_38], 0
0x140014f66  lea     rcx, [rbp+98h]
0x140014f6d  mov     [rsp+78h+var_40], rcx
0x140014f72  mov     r9b, 20h ; ' '
0x140014f75  mov     [rsi+40h], al
0x140014f78  mov     r8b, 0EFh
0x140014f7b  lea     rax, [rsp+78h+arg_0]
0x140014f83  mov     rdx, rbp
0x140014f86  mov     [rsp+78h+var_48], rax
0x140014f8b  mov     rcx, rsi
0x140014f8e  mov     [rsp+78h+var_50], 0
0x140014f96  mov     byte ptr [rsp+78h+var_58], 0
0x140014f9b  call    RfcommFrameAllocLockedEx
0x140014fa0  mov     r10, rax
0x140014fa3  test    rax, rax
0x140014fa6  jnz     short loc_140014FB2
0x140014fa8  mov     ebx, 0C000009Ah
0x140014fad  jmp     loc_140015069
0x140014fb2  mov     word ptr [rax+9Bh], 1183h
0x140014fbb  mov     ebx, 103h
0x140014fc0  mov     al, [rbp+0B8h]
0x140014fc6  mov     [r10+9Dh], al
0x140014fcd  mov     dl, [r15+109h]
0x140014fd4  mov     al, dl
0x140014fd6  neg     al
0x140014fd8  sbb     cl, cl
0x140014fda  and     cl, 0F0h
0x140014fdd  neg     dl
0x140014fdf  mov     [r10+9Eh], cl
0x140014fe6  sbb     al, al
0x140014fe8  and     al, 7
0x140014fea  mov     [r10+0A4h], al
0x140014ff1  mov     al, [rbp+0B8h]
0x140014ff7  test    al, al
0x140014ff9  jz      short loc_140014FFF
0x140014ffb  and     al, 0F8h
0x140014ffd  add     al, 7
0x140014fff  mov     [r10+9Fh], al
0x140015006  mov     r11d, 3F3h
0x14001500c  mov     byte ptr [r10+0A0h], 0
0x140015014  test    rdi, rdi
0x140015017  jz      short loc_14001503C
0x140015019  cmp     dword ptr [rdi+0C8h], 0
0x140015020  jbe     short loc_14001502C
0x140015022  movzx   r11d, word ptr [rdi+0C8h]
0x14001502a  jmp     short loc_14001503C
0x14001502c  mov     eax, [rdi+0CCh]
0x140015032  test    al, 2
0x140015034  jz      short loc_14001503C
0x140015036  mov     r11d, 3F0h
0x14001503c  mov     rdx, rdi
0x14001503f  mov     rcx, rsi
0x140015042  call    ChannelMaxMTULocked
0x140015047  cmp     r11w, ax
0x14001504b  jb      short loc_140015059
0x14001504d  mov     rcx, rsi
0x140015050  call    ChannelMaxMTULocked
0x140015055  movzx   r11d, ax
0x140015059  mov     [r10+0A1h], r11w
0x140015061  mov     byte ptr [r10+0A3h], 0
0x140015069  mov     rdx, rbp
0x14001506c  mov     rcx, rsi
0x14001506f  call    RfcommGetNextCmdLocked
0x140015074  mov     dl, [rsi+40h]; NewIrql
0x140015077  lea     rcx, [rsi+38h]; SpinLock
0x14001507b  mov     r14, rax
0x14001507e  call    cs:__imp_KeReleaseSpinLock
0x140015085  nop     dword ptr [rax+rax+00h]
0x14001508a  lea     rcx, [rbp+18h]
0x14001508e  mov     r8d, 0BEDh
0x140015094  mov     ebp, 4E4E4F43h
0x140015099  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400150a0  mov     edx, ebp
0x1400150a2  call    RefObj_ReleaseEx
0x1400150a7  test    r14, r14
0x1400150aa  jz      short loc_1400150C0
0x1400150ac  mov     rcx, [rsi+48h]
0x1400150b0  call    RfcommStartTimer
0x1400150b5  mov     rdx, r14
0x1400150b8  mov     rcx, rsi
0x1400150bb  call    RfcommFrameWrite
0x1400150c0  test    rdi, rdi
0x1400150c3  jz      short loc_1400150DE
0x1400150c5  lea     rcx, [rdi+18h]
0x1400150c9  mov     r8d, 0BFDh
0x1400150cf  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400150d6  mov     rdx, rbp
0x1400150d9  call    RefObj_ReleaseEx
0x1400150de  lea     rax, WPP_RECORDER_INITIALIZED
0x1400150e5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400150ec  jz      short loc_140015118
0x1400150ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400150f5  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400150fc  mov     r9d, 42h ; 'B'
0x140015102  mov     [rsp+78h+var_50], ebx
0x140015106  mov     [rsp+78h+var_58], rax
0x14001510b  mov     rcx, [rcx+40h]
0x14001510f  lea     r8d, [r9-3Fh]
0x140015113  call    WPP_RECORDER_SF_d
0x140015118  lea     r11, [rsp+78h+var_28]
0x14001511d  mov     eax, ebx
0x14001511f  mov     rbx, [r11+38h]
0x140015123  mov     rbp, [r11+40h]
0x140015127  mov     rsp, r11
0x14001512a  pop     r15
0x14001512c  pop     r14
0x14001512e  pop     r12
0x140015130  pop     rdi
0x140015131  pop     rsi
0x140015132  retn
```

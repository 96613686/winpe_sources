# HandleMsgRPN

- ea: `0x1400121d4`
- end: `0x140012588`
- name: `HandleMsgRPN`
- size: `948`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012c60`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140003d98`
- `0x140005c38`
- `0x1400121d4`
- `0x140014b10`
- `0x1400195d0`
- `0x140019e5c`
- `0x14001a12c`
- `0x14001e74c`
- `0x14001ea34`
- `0x14001ebd8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400122ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400122ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012336`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012384`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012336`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012384`
- `ntoskrnl!ExAllocatePool2` at `0x14001246e`
- `ntoskrnl!ExAllocatePool2` at `0x14001246e`

## string_xrefs

- `0x140012350`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x1400124f5`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140012515`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x1400123df`: `COMMAND`

## pseudocode

```c
char __fastcall HandleMsgRPN(__int64 a1, __int64 a2, __int64 a3, __int64 *a4, __int64 *a5)
{
  __int64 v5; // r13
  char v10; // si
  int v11; // ecx
  __int64 v12; // rdx
  __int64 Locked; // rbx
  _BYTE *v14; // r14
  char v15; // r15
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // edx
  __int64 v20; // r13
  __int64 v21; // rax
  IRP *v22; // r13
  __int64 v23; // rdi
  const wchar_t *v24; // rax
  __int64 Pool2; // rax
  char v26; // di
  char v28; // [rsp+80h] [rbp+18h]
  __int64 v30; // [rsp+90h] [rbp+28h]

  v5 = 0;
  v28 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      117,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  v10 = 1;
  *a4 = 0;
  v11 = *(unsigned __int8 *)(a2 + 1) >> 1;
  *a5 = 0;
  v12 = (unsigned int)(v11 - 1);
  if ( v11 == 1 )
  {
    v15 = 1;
  }
  else
  {
    if ( v11 != 8 )
    {
      Locked = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          3,
          118,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
          v11);
      v14 = (_BYTE *)(a2 + 2);
      goto LABEL_30;
    }
    v15 = 0;
  }
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v14 = (_BYTE *)(a2 + 2);
  LOBYTE(v16) = 1;
  LOBYTE(v17) = *(_BYTE *)(a2 + 2) >> 2;
  Locked = ChannelFindLocked(a1, v17, v16);
  if ( !Locked )
  {
    v18 = ChannelCreateLocked(a1, (unsigned __int8)*v14 >> 3, 0);
    Locked = v18;
    if ( !v18 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          1,
          119,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
      goto LABEL_30;
    }
    RefObj_AddRefEx(v18 + 24, 1145981254, 4305, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  v20 = ChannelReferenceConnLocked(Locked, 1145981254);
  v30 = v20;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  *a4 = Locked;
  if ( v20 )
  {
    v21 = IrpList_Dequeue(v20 + 736);
    v22 = (IRP *)v21;
    if ( v21 )
    {
      v23 = *(_QWORD *)(v21 + 24);
      *(_QWORD *)v23 = 0;
      *(_WORD *)(v23 + 8) = 0;
      *(_BYTE *)(v23 + 10) = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v24 = L"REQUEST";
        if ( !v15 )
          v24 = L"COMMAND";
        WPP_RECORDER_SF_S(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          3,
          120,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
          (__int64)v24);
      }
      if ( v15 )
      {
        *(_DWORD *)v23 = 4;
      }
      else
      {
        *(_DWORD *)v23 = 3;
        *(_DWORD *)(v23 + 4) = *(_DWORD *)(a2 + 3);
        *(_WORD *)(v23 + 8) = *(_WORD *)(a2 + 7);
        *(_BYTE *)(v23 + 10) = *(_BYTE *)(a2 + 9);
      }
      RfcommCompleteTdiIrp(v22);
      v28 = 1;
      goto LABEL_32;
    }
  }
  if ( !v15 )
  {
    _InterlockedExchange((volatile __int32 *)(Locked + 216), 1);
    goto LABEL_32;
  }
  Pool2 = ExAllocatePool2(64, 10, 1095001682);
  *a5 = Pool2;
  if ( Pool2 )
  {
    *(_WORD *)Pool2 = 4497;
    *(_BYTE *)(Pool2 + 2) = *v14;
    *(_DWORD *)(Pool2 + 3) = 285213444;
    *(_WORD *)(Pool2 + 7) = 19;
    *(_BYTE *)(Pool2 + 9) = 0;
    _InterlockedExchange((volatile __int32 *)(Locked + 212), 1);
LABEL_32:
    v26 = 1;
    v5 = v30;
    goto LABEL_33;
  }
  v5 = v30;
LABEL_30:
  v26 = 0;
  LOBYTE(v12) = *v14 >> 2;
  RfcommSendDMEx(a1, v12, 0);
LABEL_33:
  if ( Locked && !*a4 )
    RefObj_ReleaseEx(Locked + 24, 1145981254, 4407, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  if ( v5 )
    RefObj_ReleaseEx(v5 + 24, 1145981254, 4411, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      3,
      121,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  if ( !v26 || v28 )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x1400121d4  mov     rax, rsp
0x1400121d7  mov     [rax+8], rbx
0x1400121db  mov     [rax+20h], r9
0x1400121df  mov     [rax+18h], r8d
0x1400121e3  push    rbp
0x1400121e4  push    rsi
0x1400121e5  push    rdi
0x1400121e6  push    r12
0x1400121e8  push    r13
0x1400121ea  push    r14
0x1400121ec  push    r15
0x1400121ee  sub     rsp, 30h
0x1400121f2  xor     r13d, r13d
0x1400121f5  mov     rbx, r9
0x1400121f8  mov     [rsp+68h+arg_10], r13b
0x140012200  mov     rbp, rdx
0x140012203  mov     r12, rcx
0x140012206  lea     r8, WPP_RECORDER_INITIALIZED
0x14001220d  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140012214  lea     r10, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001221b  jz      short loc_140012247
0x14001221d  mov     rcx, cs:WPP_GLOBAL_Control
0x140012224  lea     r9d, [r13+75h]
0x140012228  lea     r8d, [r13+3]
0x14001222c  mov     [rax-48h], r10
0x140012230  mov     rcx, [rcx+40h]
0x140012234  call    WPP_RECORDER_SF_
0x140012239  lea     r8, WPP_RECORDER_INITIALIZED
0x140012240  lea     r10, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140012247  mov     rdi, [rsp+68h+arg_20]
0x14001224f  mov     esi, 1
0x140012254  mov     [rbx], r13
0x140012257  movzx   ecx, byte ptr [rbp+1]
0x14001225b  shr     ecx, 1
0x14001225d  mov     edx, ecx
0x14001225f  mov     [rdi], r13
0x140012262  sub     edx, esi
0x140012264  jz      short loc_1400122A5
0x140012266  cmp     edx, 7
0x140012269  jz      short loc_1400122A0
0x14001226b  xor     ebx, ebx
0x14001226d  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140012274  jz      short loc_140012297
0x140012276  mov     dword ptr [rsp+68h+var_40], ecx
0x14001227a  lea     r9d, [rsi+75h]
0x14001227e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012285  lea     r8d, [rsi+2]
0x140012289  mov     [rsp+68h+var_48], r10
0x14001228e  mov     rcx, [rcx+40h]
0x140012292  call    WPP_RECORDER_SF_d
0x140012297  lea     r14, [rbp+2]
0x14001229b  jmp     loc_1400124B0
0x1400122a0  xor     r15b, r15b
0x1400122a3  jmp     short loc_1400122A8
0x1400122a5  mov     r15b, sil
0x1400122a8  lea     rcx, [r12+38h]; SpinLock
0x1400122ad  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400122b4  nop     dword ptr [rax+rax+00h]
0x1400122b9  mov     [r12+40h], al
0x1400122be  lea     r14, [rbp+2]
0x1400122c2  mov     dl, [r14]
0x1400122c5  mov     r8b, sil
0x1400122c8  shr     dl, 2
0x1400122cb  mov     rcx, r12
0x1400122ce  call    ChannelFindLocked
0x1400122d3  mov     rbx, rax
0x1400122d6  test    rax, rax
0x1400122d9  jnz     loc_140012362
0x1400122df  movzx   edx, byte ptr [r14]
0x1400122e3  xor     r8d, r8d
0x1400122e6  shr     edx, 3
0x1400122e9  mov     rcx, r12
0x1400122ec  call    ChannelCreateLocked
0x1400122f1  mov     rbx, rax
0x1400122f4  test    rax, rax
0x1400122f7  jnz     short loc_140012347
0x1400122f9  lea     rax, WPP_RECORDER_INITIALIZED
0x140012300  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140012307  jz      short loc_14001232C
0x140012309  mov     rcx, cs:WPP_GLOBAL_Control
0x140012310  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140012317  lea     r9d, [rbx+77h]
0x14001231b  mov     [rsp+68h+var_48], rax
0x140012320  mov     r8d, esi
0x140012323  mov     rcx, [rcx+40h]
0x140012327  call    WPP_RECORDER_SF_
0x14001232c  mov     dl, [r12+40h]; NewIrql
0x140012331  lea     rcx, [r12+38h]; SpinLock
0x140012336  call    cs:__imp_KeReleaseSpinLock
0x14001233d  nop     dword ptr [rax+rax+00h]
0x140012342  jmp     loc_1400124B0
0x140012347  lea     rcx, [rax+18h]
0x14001234b  mov     edx, 444E4946h
0x140012350  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140012357  mov     r8d, 10D1h
0x14001235d  call    RefObj_AddRefEx
0x140012362  mov     edx, 444E4946h
0x140012367  mov     rcx, rbx
0x14001236a  call    ChannelReferenceConnLocked
0x14001236f  mov     dl, [r12+40h]; NewIrql
0x140012374  lea     rcx, [r12+38h]; SpinLock
0x140012379  mov     r13, rax
0x14001237c  mov     [rsp+68h+arg_20], rax
0x140012384  call    cs:__imp_KeReleaseSpinLock
0x14001238b  nop     dword ptr [rax+rax+00h]
0x140012390  mov     rax, [rsp+68h+arg_18]
0x140012398  mov     [rax], rbx
0x14001239b  test    r13, r13
0x14001239e  jz      loc_14001245B
0x1400123a4  lea     rcx, [r13+2E0h]
0x1400123ab  call    IrpList_Dequeue
0x1400123b0  mov     r13, rax
0x1400123b3  test    rax, rax
0x1400123b6  jz      loc_14001245B
0x1400123bc  mov     rdi, [rax+18h]
0x1400123c0  xor     eax, eax
0x1400123c2  mov     [rdi], rax
0x1400123c5  mov     [rdi+8], ax
0x1400123c9  mov     [rdi+0Ah], al
0x1400123cc  lea     rax, WPP_RECORDER_INITIALIZED
0x1400123d3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400123da  jz      short loc_14001241C
0x1400123dc  test    r15b, r15b
0x1400123df  lea     rcx, aCommand_0; "COMMAND"
0x1400123e6  mov     r9d, 78h ; 'x'
0x1400123ec  lea     rax, aRequest; "REQUEST"
0x1400123f3  cmovz   rax, rcx
0x1400123f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400123fe  mov     [rsp+68h+var_40], rax
0x140012403  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001240a  mov     [rsp+68h+var_48], rax
0x14001240f  lea     r8d, [r9-75h]
0x140012413  mov     rcx, [rcx+40h]
0x140012417  call    WPP_RECORDER_SF_S
0x14001241c  test    r15b, r15b
0x14001241f  jz      short loc_140012429
0x140012421  mov     dword ptr [rdi], 4
0x140012427  jmp     short loc_140012443
0x140012429  mov     dword ptr [rdi], 3
0x14001242f  mov     eax, [rbp+3]
0x140012432  mov     [rdi+4], eax
0x140012435  movzx   eax, word ptr [rbp+7]
0x140012439  mov     [rdi+8], ax
0x14001243d  mov     al, [rbp+9]
0x140012440  mov     [rdi+0Ah], al
0x140012443  xor     edx, edx
0x140012445  mov     rcx, r13; Irp
0x140012448  lea     r8d, [rdx+0Bh]
0x14001244c  call    RfcommCompleteTdiIrp
0x140012451  mov     [rsp+68h+arg_10], sil
0x140012459  jmp     short loc_1400124CE
0x14001245b  test    r15b, r15b
0x14001245e  jz      short loc_1400124C6
0x140012460  mov     edx, 0Ah
0x140012465  mov     r8d, 41446652h
0x14001246b  lea     ecx, [rdx+36h]
0x14001246e  call    cs:__imp_ExAllocatePool2
0x140012475  nop     dword ptr [rax+rax+00h]
0x14001247a  mov     [rdi], rax
0x14001247d  test    rax, rax
0x140012480  jz      short loc_1400124A8
0x140012482  mov     word ptr [rax], 1191h
0x140012487  mov     cl, [r14]
0x14001248a  mov     [rax+2], cl
0x14001248d  mov     dword ptr [rax+3], 11000304h
0x140012494  mov     word ptr [rax+7], 13h
0x14001249a  mov     byte ptr [rax+9], 0
0x14001249e  mov     eax, esi
0x1400124a0  xchg    eax, [rbx+0D4h]
0x1400124a6  jmp     short loc_1400124CE
0x1400124a8  mov     r13, [rsp+68h+arg_20]
0x1400124b0  mov     dl, [r14]
0x1400124b3  xor     dil, dil
0x1400124b6  shr     dl, 2
0x1400124b9  xor     r8d, r8d
0x1400124bc  mov     rcx, r12
0x1400124bf  call    RfcommSendDMEx
0x1400124c4  jmp     short loc_1400124D9
0x1400124c6  mov     eax, esi
0x1400124c8  xchg    eax, [rbx+0D8h]
0x1400124ce  mov     dil, sil
0x1400124d1  mov     r13, [rsp+68h+arg_20]
0x1400124d9  test    rbx, rbx
0x1400124dc  jz      short loc_140012507
0x1400124de  mov     rax, [rsp+68h+arg_18]
0x1400124e6  cmp     qword ptr [rax], 0
0x1400124ea  jnz     short loc_140012507
0x1400124ec  lea     rcx, [rbx+18h]
0x1400124f0  mov     edx, 444E4946h
0x1400124f5  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400124fc  mov     r8d, 1137h
0x140012502  call    RefObj_ReleaseEx
0x140012507  test    r13, r13
0x14001250a  jz      short loc_140012527
0x14001250c  lea     rcx, [r13+18h]
0x140012510  mov     edx, 444E4946h
0x140012515  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001251c  mov     r8d, 113Bh
0x140012522  call    RefObj_ReleaseEx
0x140012527  lea     rax, WPP_RECORDER_INITIALIZED
0x14001252e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140012535  jz      short loc_14001255D
0x140012537  mov     rcx, cs:WPP_GLOBAL_Control
0x14001253e  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140012545  mov     r9d, 79h ; 'y'
0x14001254b  mov     [rsp+68h+var_48], rax
0x140012550  mov     rcx, [rcx+40h]
0x140012554  lea     r8d, [r9-76h]
0x140012558  call    WPP_RECORDER_SF_
0x14001255d  test    dil, dil
0x140012560  jz      short loc_14001256C
0x140012562  cmp     [rsp+68h+arg_10], 0
0x14001256a  jz      short loc_14001256F
0x14001256c  xor     sil, sil
0x14001256f  mov     rbx, [rsp+68h+arg_0]
0x140012574  mov     al, sil
0x140012577  add     rsp, 30h
0x14001257b  pop     r15
0x14001257d  pop     r14
0x14001257f  pop     r13
0x140012581  pop     r12
0x140012583  pop     rdi
0x140012584  pop     rsi
0x140012585  pop     rbp
0x140012586  retn
```

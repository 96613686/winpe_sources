# SetupVcAsynchronously

- ea: `0x140011518`
- end: `0x140011f96`
- name: `SetupVcAsynchronously`
- size: `2686`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400130b8`

## callees

- `0x1400013f0`
- `0x140001850`
- `0x140001990`
- `0x140001b70`
- `0x140001ce0`
- `0x140001fc0`
- `0x1400021c0`
- `0x140003050`
- `0x1400030c4`
- `0x140003230`
- `0x1400032f0`
- `0x140010388`
- `0x14001070c`
- `0x140011070`
- `0x1400110d0`
- `0x140011518`
- `0x140011f9c`
- `0x14001ac30`
- `0x14001c050`
- `0x14001c390`
- `0x14001c400`
- `0x14001c860`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140011750`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011750`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011bd3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011be6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011eb2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011f03`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011bd3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011be6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011eb2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011f03`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b2b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011e7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b2b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011e7e`
- `NDIS!NdisFreeNetBufferList` at `0x140011590`
- `NDIS!NdisFreeNetBufferList` at `0x14001173e`
- `NDIS!NdisFreeNetBufferList` at `0x140011c12`
- `NDIS!NdisFreeNetBufferList` at `0x140011590`
- `NDIS!NdisFreeNetBufferList` at `0x14001173e`
- `NDIS!NdisFreeNetBufferList` at `0x140011c12`
- `NDIS!NdisCmDispatchIncomingCall` at `0x140011edb`
- `NDIS!NdisCmDispatchIncomingCall` at `0x140011edb`
- `NDIS!NdisMCmCreateVc` at `0x140011d1f`
- `NDIS!NdisMCmCreateVc` at `0x140011d1f`
- `NDIS!NdisMCmActivateVc` at `0x140011d91`
- `NDIS!NdisMCmActivateVc` at `0x140011d91`

## pseudocode

```c
void __fastcall SetupVcAsynchronously(__int64 a1, struct _NET_BUFFER_LIST *a2, __int64 a3)
{
  __int64 v3; // rsi
  struct _NET_BUFFER_LIST *v5; // r12
  __int64 v6; // rbx
  struct _NET_BUFFER_LIST **v7; // rax
  struct _NET_BUFFER_LIST **v8; // rdi
  _OWORD *v9; // rax
  _OWORD *v10; // rcx
  __int64 v11; // rdx
  __int128 v12; // xmm1
  char *v13; // r13
  _OWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  KIRQL v17; // al
  bool v18; // zf
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  _WORD *v22; // rax
  _BYTE *v23; // rax
  _DWORD *v24; // rax
  __int64 v25; // r12
  NDIS_STATUS Vc; // eax
  __int64 v27; // r8
  NDIS_STATUS v28; // eax
  __int64 v29; // r8
  __int64 v30; // rcx
  char v31; // al
  KIRQL v32; // al
  NDIS_STATUS v33; // eax
  unsigned int v34; // ebx
  NDIS_HANDLE MiniportVcContext; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-68h]
  PDEVICE_OBJECT v37; // [rsp+B8h] [rbp-60h]
  struct _NET_BUFFER_LIST **v38; // [rsp+C0h] [rbp-58h]
  char v40; // [rsp+120h] [rbp+8h]

  v3 = *(_QWORD *)(a1 + 24);
  v5 = a2;
  v36 = v3;
  v6 = a1;
  MiniportVcContext = 0;
  if ( (unsigned int)LcmCmCreateVc(v3, 0, &MiniportVcContext) )
  {
LABEL_2:
    ScheduleTunnelWork(v6, 0, (unsigned int)FsmCloseTunnel, 2, 4);
    NdisFreeNetBufferList(v5);
    return;
  }
  v7 = (struct _NET_BUFFER_LIST **)ALLOC_NONPAGED(1216, 1750348364);
  v38 = v7;
  v8 = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
    }
    LcmCmDeleteVc(MiniportVcContext);
    goto LABEL_2;
  }
  *v7 = v5;
  v9 = v7 + 8;
  v10 = (_OWORD *)a3;
  v11 = 2;
  do
  {
    *v9 = *v10;
    v9[1] = v10[1];
    v9[2] = v10[2];
    v9[3] = v10[3];
    v9[4] = v10[4];
    v9[5] = v10[5];
    v9[6] = v10[6];
    v12 = v10[7];
    v10 += 8;
    v9[7] = v12;
    v9 += 8;
    --v11;
  }
  while ( v11 );
  v13 = (char *)MiniportVcContext;
  *v9 = *v10;
  v9[1] = v10[1];
  v9[2] = v10[2];
  v9[3] = v10[3];
  if ( (int)BuildCallParametersShell(
              v3,
              (int)v6 + 80,
              (int)v6 + 48,
              (int)v8 + 392,
              v8 + 49,
              (__int64)(v13 + 144),
              (__int64)(v13 + 152),
              (__int64)(v13 + 192)) >= 0 )
  {
    v14 = *(_OWORD **)(a3 + 288);
    if ( v14 )
    {
      *((_OWORD *)v13 + 13) = *v14;
      v13[224] = 0;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_DDDDDDDDDDDDDDDD(
            v37->AttachedDevice,
            44,
            (unsigned int)WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids,
            *((unsigned __int8 *)MiniportVcContext + 208),
            *((_BYTE *)MiniportVcContext + 209),
            *((_BYTE *)MiniportVcContext + 210),
            v13[211],
            v13[212],
            v13[213],
            v13[214],
            v13[215],
            v13[216],
            v13[217],
            v13[218],
            v13[219],
            v13[220],
            v13[221],
            v13[222],
            v13[223]);
          v13 = (char *)MiniportVcContext;
        }
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_DDDDDDDDDDDDDDDD(
              v37->AttachedDevice,
              45,
              (unsigned int)WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids,
              *((unsigned __int8 *)MiniportVcContext + 211),
              *((_BYTE *)MiniportVcContext + 210),
              *((_BYTE *)MiniportVcContext + 209),
              v13[208],
              v13[213],
              v13[212],
              v13[215],
              v13[214],
              v13[216],
              v13[217],
              v13[218],
              v13[219],
              v13[220],
              v13[221],
              v13[222],
              v13[223]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
          }
          v13 = (char *)MiniportVcContext;
        }
      }
      v6 = a1;
      v5 = a2;
      *(_OWORD *)(*((_QWORD *)v13 + 24) + 20LL) = *((_OWORD *)v13 + 13);
      *(_DWORD *)(*((_QWORD *)v13 + 24) + 8LL) |= 8u;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
    }
    SetFlags(v13 + 60, 0x40000);
    v16 = 4144;
    *((_QWORD *)v13 + 17) = v38;
    *((_DWORD *)v13 + 50) = 0;
    if ( **(_WORD **)(a3 + 8) != 10 )
      v16 = 4128;
    SetFlags(v15, v16);
    ReferenceTunnel(v6, 0);
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 32));
    v18 = (*(_DWORD *)(v6 + 120) & 0x100) == 0;
    *(_BYTE *)(v6 + 40) = v17;
    if ( v18 )
    {
      *(_BYTE *)(v6 + 368) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 360));
      *((_QWORD *)v13 + 4) = v6;
      ReferenceVc(v13);
      v19 = *(_QWORD **)(v6 + 352);
      if ( *v19 != v6 + 344 )
        __fastfail(3u);
      *((_QWORD *)v13 + 1) = v19;
      *(_QWORD *)v13 = v6 + 344;
      *v19 = v13;
      v40 = 0;
      *(_QWORD *)(v6 + 352) = v13;
      SetFlags(v13 + 60, 0x2000000);
      SetFlags(v20, 0x80000);
      ReferenceVc(v13);
      KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 360), *(_BYTE *)(v6 + 368));
    }
    else
    {
      v40 = 1;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 32), *(_BYTE *)(v6 + 40));
    if ( v40 )
    {
      CallSetupComplete(v13);
      LcmCmDeleteVc(v13);
      NdisFreeNetBufferList(v5);
      DereferenceTunnel(v6);
      return;
    }
    v21 = a3;
    v22 = *(_WORD **)(a3 + 120);
    if ( !v22 || !*v22 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
      }
      *((_DWORD *)v13 + 50) = 327682;
      goto LABEL_93;
    }
    if ( (*((_DWORD *)v13 + 15) & 0x10) == 0 )
    {
      v23 = *(_BYTE **)(a3 + 160);
      if ( !v23 || (*v23 & 1) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
          v21 = a3;
        }
        if ( (*(_DWORD *)(v36 + 8) & 2) == 0 )
          goto LABEL_55;
      }
      v24 = *(_DWORD **)(v21 + 152);
      if ( v24 && *v24 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
        }
LABEL_55:
        *((_DWORD *)v13 + 50) = 5;
        goto LABEL_93;
      }
    }
    v25 = v36;
    Vc = NdisMCmCreateVc(*(NDIS_HANDLE *)(v36 + 328), *(NDIS_HANDLE *)(v36 + 352), v13, (PNDIS_HANDLE)v13 + 38);
    if ( !Vc )
    {
      SetFlags(v13 + 60, 256);
      v28 = NdisMCmActivateVc(*((NDIS_HANDLE *)v13 + 38), (PCO_CALL_PARAMETERS)(*((_QWORD *)v13 + 17) + 392LL));
      if ( v28 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 52, v29, v13, v28);
        }
        *((_DWORD *)v13 + 50) = 262146;
        v30 = v6;
      }
      else
      {
        SetFlags(v13 + 60, 518);
        ReferenceCall(v13);
        v31 = ReferenceSap(v25);
        v30 = v6;
        if ( v31 )
        {
          ReferenceTunnel(v6, 0);
          ReferenceCall(v13);
          SetFlags(v13 + 60, 0x100000);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
          }
          ReferenceVc(v13);
          v32 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 32));
          v18 = (*(_DWORD *)(v6 + 120) & 0x100) == 0;
          *(_BYTE *)(v6 + 40) = v32;
          if ( v18 )
          {
            SetFlags(v13 + 60, 1024);
            KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 32), *(_BYTE *)(v6 + 40));
            v33 = NdisCmDispatchIncomingCall(
                    *(NDIS_HANDLE *)(v25 + 336),
                    *((NDIS_HANDLE *)v13 + 38),
                    (PCO_CALL_PARAMETERS)(*((_QWORD *)v13 + 17) + 392LL));
            v34 = v33;
            if ( v33 && v33 != 259 )
              ClearFlags(v13 + 60, 1024);
          }
          else
          {
            KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 32), v32);
            v34 = -1073741823;
          }
          DereferenceSap(v25);
          if ( v34 != 259 )
            LcmCmIncomingCallComplete(v34, v13, 0);
          goto LABEL_94;
        }
        *((_DWORD *)v13 + 50) = 4;
      }
      SetupVcComplete(v30, v13);
LABEL_94:
      DereferenceVc(v13);
      return;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 51, v27, v13, Vc);
    }
    *((_DWORD *)v13 + 50) = 262146;
LABEL_93:
    SetupVcComplete(v6, v13);
    LcmCmDeleteVc(v13);
    goto LABEL_94;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
  }
  LcmCmDeleteVc(v13);
  ScheduleTunnelWork(v6, 0, (unsigned int)FsmCloseTunnel, 2, 3);
  NdisFreeNetBufferList(v5);
  ExFreePoolWithTag(v8 - 2, 0);
}

```

## disassembly

```asm
0x140011518  mov     rax, rsp
0x14001151b  mov     [rax+18h], r8
0x14001151f  mov     [rax+10h], rdx
0x140011523  mov     [rax+8], rcx
0x140011527  push    rbx
0x140011528  push    rbp
0x140011529  push    rsi
0x14001152a  push    rdi
0x14001152b  push    r12
0x14001152d  push    r13
0x14001152f  push    r14
0x140011531  push    r15
0x140011533  sub     rsp, 0D8h
0x14001153a  mov     rsi, [rcx+18h]
0x14001153e  mov     rbp, r8
0x140011541  mov     r12, rdx
0x140011544  mov     [rsp+118h+var_68], rsi
0x14001154c  mov     rbx, rcx
0x14001154f  lea     r8, [rax-70h]
0x140011553  xor     r15d, r15d
0x140011556  mov     rcx, rsi
0x140011559  xor     edx, edx
0x14001155b  mov     [rax-70h], r15
0x14001155f  call    LcmCmCreateVc
0x140011564  test    eax, eax
0x140011566  jz      short loc_1400115A1
0x140011568  mov     byte ptr [rsp+118h+var_E0], r15b
0x14001156d  lea     r8, FsmCloseTunnel
0x140011574  mov     r9d, 2
0x14001157a  mov     [rsp+118h+var_F8], 4
0x140011583  xor     edx, edx
0x140011585  mov     rcx, rbx
0x140011588  call    ScheduleTunnelWork
0x14001158d  mov     rcx, r12; NetBufferList
0x140011590  call    cs:__imp_NdisFreeNetBufferList
0x140011597  nop     dword ptr [rax+rax+00h]
0x14001159c  jmp     loc_140011F81
0x1400115a1  mov     edx, 6854324Ch
0x1400115a6  mov     ecx, 4C0h
0x1400115ab  call    ALLOC_NONPAGED
0x1400115b0  mov     [rsp+118h+var_58], rax
0x1400115b8  mov     rdi, rax
0x1400115bb  test    rax, rax
0x1400115be  jnz     short loc_140011609
0x1400115c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115c7  lea     rax, WPP_GLOBAL_Control
0x1400115ce  cmp     rcx, rax
0x1400115d1  jz      short loc_1400115F7
0x1400115d3  mov     eax, [rcx+2Ch]
0x1400115d6  mov     sil, 1
0x1400115d9  test    sil, al
0x1400115dc  jz      short loc_1400115F7
0x1400115de  cmp     [rcx+29h], sil
0x1400115e2  jb      short loc_1400115F7
0x1400115e4  mov     rcx, [rcx+18h]
0x1400115e8  lea     edx, [rdi+2Ah]
0x1400115eb  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x1400115f2  call    WPP_SF_
0x1400115f7  mov     rcx, [rsp+118h+MiniportVcContext]
0x1400115ff  call    LcmCmDeleteVc
0x140011604  jmp     loc_140011568
0x140011609  mov     r14d, 2
0x14001160f  mov     [rax], r12
0x140011612  add     rax, 40h ; '@'
0x140011616  mov     rcx, rbp
0x140011619  mov     edx, r14d
0x14001161c  lea     r8d, [r14+7Eh]
0x140011620  movups  xmm0, xmmword ptr [rcx]
0x140011623  movups  xmmword ptr [rax], xmm0
0x140011626  movups  xmm1, xmmword ptr [rcx+10h]
0x14001162a  movups  xmmword ptr [rax+10h], xmm1
0x14001162e  movups  xmm0, xmmword ptr [rcx+20h]
0x140011632  movups  xmmword ptr [rax+20h], xmm0
0x140011636  movups  xmm1, xmmword ptr [rcx+30h]
0x14001163a  movups  xmmword ptr [rax+30h], xmm1
0x14001163e  movups  xmm0, xmmword ptr [rcx+40h]
0x140011642  movups  xmmword ptr [rax+40h], xmm0
0x140011646  movups  xmm1, xmmword ptr [rcx+50h]
0x14001164a  movups  xmmword ptr [rax+50h], xmm1
0x14001164e  movups  xmm0, xmmword ptr [rcx+60h]
0x140011652  movups  xmmword ptr [rax+60h], xmm0
0x140011656  movups  xmm1, xmmword ptr [rcx+70h]
0x14001165a  add     rcx, r8
0x14001165d  movups  xmmword ptr [rax+70h], xmm1
0x140011661  add     rax, r8
0x140011664  sub     rdx, 1
0x140011668  jnz     short loc_140011620
0x14001166a  movups  xmm0, xmmword ptr [rcx]
0x14001166d  mov     r13, [rsp+118h+MiniportVcContext]
0x140011675  lea     r9, [rdi+188h]; int
0x14001167c  lea     r8, [rbx+30h]; int
0x140011680  movups  xmmword ptr [rax], xmm0
0x140011683  lea     rdx, [rbx+50h]; int
0x140011687  movups  xmm1, xmmword ptr [rcx+10h]
0x14001168b  lea     r10, [r13+0C0h]
0x140011692  mov     [rsp+118h+var_E0], r10; __int64
0x140011697  movups  xmmword ptr [rax+10h], xmm1
0x14001169b  movups  xmm0, xmmword ptr [rcx+20h]
0x14001169f  movups  xmmword ptr [rax+20h], xmm0
0x1400116a3  movups  xmm1, xmmword ptr [rcx+30h]
0x1400116a7  lea     rcx, [r13+90h]
0x1400116ae  movups  xmmword ptr [rax+30h], xmm1
0x1400116b2  lea     rax, [r13+98h]
0x1400116b9  mov     [rsp+118h+var_E8], rax; __int64
0x1400116be  mov     [rsp+118h+var_F0], rcx; __int64
0x1400116c3  mov     rcx, rsi; int
0x1400116c6  mov     [rsp+118h+var_F8], r9; void *
0x1400116cb  call    BuildCallParametersShell
0x1400116d0  test    eax, eax
0x1400116d2  jns     loc_140011761
0x1400116d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116df  lea     rax, WPP_GLOBAL_Control
0x1400116e6  cmp     rcx, rax
0x1400116e9  jz      short loc_140011711
0x1400116eb  mov     eax, [rcx+2Ch]
0x1400116ee  mov     sil, 1
0x1400116f1  test    sil, al
0x1400116f4  jz      short loc_140011711
0x1400116f6  cmp     [rcx+29h], sil
0x1400116fa  jb      short loc_140011711
0x1400116fc  mov     rcx, [rcx+18h]
0x140011700  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140011707  mov     edx, 2Bh ; '+'
0x14001170c  call    WPP_SF_
0x140011711  mov     rcx, r13
0x140011714  call    LcmCmDeleteVc
0x140011719  mov     r9, r14
0x14001171c  mov     byte ptr [rsp+118h+var_E0], r15b
0x140011721  lea     r8, FsmCloseTunnel
0x140011728  mov     [rsp+118h+var_F8], 3
0x140011731  xor     edx, edx
0x140011733  mov     rcx, rbx
0x140011736  call    ScheduleTunnelWork
0x14001173b  mov     rcx, r12; NetBufferList
0x14001173e  call    cs:__imp_NdisFreeNetBufferList
0x140011745  nop     dword ptr [rax+rax+00h]
0x14001174a  lea     rcx, [rdi-10h]; P
0x14001174e  xor     edx, edx; Tag
0x140011750  call    cs:__imp_ExFreePoolWithTag
0x140011757  nop     dword ptr [rax+rax+00h]
0x14001175c  jmp     loc_140011F81
0x140011761  mov     rax, [rbp+120h]
0x140011768  lea     r15, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x14001176f  xor     esi, esi
0x140011771  mov     ebp, 4
0x140011776  test    rax, rax
0x140011779  jz      loc_140011AA1
0x14001177f  movups  xmm0, xmmword ptr [rax]
0x140011782  movdqu  xmmword ptr [r13+0D0h], xmm0
0x14001178b  mov     [r13+0E0h], sil
0x140011792  mov     rcx, cs:WPP_GLOBAL_Control
0x140011799  lea     rdi, WPP_GLOBAL_Control
0x1400117a0  mov     [rsp+118h+var_60], rcx
0x1400117a8  cmp     rcx, rdi
0x1400117ab  jz      loc_140011A71
0x1400117b1  mov     eax, [rcx+2Ch]
0x1400117b4  test    bpl, al
0x1400117b7  jz      loc_1400118EF
0x1400117bd  cmp     [rcx+29h], r14b
0x1400117c1  jb      loc_1400118EF
0x1400117c7  movzx   eax, byte ptr [r13+0DFh]
0x1400117cf  movzx   ecx, byte ptr [r13+0DEh]
0x1400117d7  movzx   r8d, byte ptr [r13+0DDh]
0x1400117df  mov     r9, [rsp+118h+MiniportVcContext]
0x1400117e7  movzx   r15d, byte ptr [r13+0D5h]
0x1400117ef  movzx   r10d, byte ptr [r13+0DCh]
0x1400117f7  movzx   r11d, byte ptr [r13+0DBh]
0x1400117ff  movzx   edx, byte ptr [r9+0D2h]
0x140011807  movzx   ebx, byte ptr [r13+0DAh]
0x14001180f  movzx   edi, byte ptr [r13+0D9h]
0x140011817  movzx   esi, byte ptr [r13+0D8h]
0x14001181f  movzx   ebp, byte ptr [r13+0D7h]
0x140011827  movzx   r14d, byte ptr [r13+0D6h]
0x14001182f  movzx   r12d, byte ptr [r13+0D4h]
0x140011837  movzx   r13d, byte ptr [r13+0D3h]
0x14001183f  mov     [rsp+118h+var_88], eax
0x140011846  mov     [rsp+118h+var_90], ecx
0x14001184d  mov     rcx, [rsp+118h+var_60]
0x140011855  mov     [rsp+118h+var_98], r8d
0x14001185d  mov     [rsp+118h+var_A0], r10d
0x140011862  mov     [rsp+118h+var_A8], r11d
0x140011867  mov     rcx, [rcx+18h]
0x14001186b  mov     [rsp+118h+var_B0], ebx
0x14001186f  mov     [rsp+118h+var_B8], edi
0x140011873  mov     [rsp+118h+var_C0], esi
0x140011877  mov     [rsp+118h+var_C8], ebp
0x14001187b  mov     [rsp+118h+var_D0], r14d
0x140011880  mov     [rsp+118h+var_D8], r15d
0x140011885  lea     r15, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x14001188c  mov     [rsp+118h+arg_18], edx
0x140011893  mov     r8, r15
0x140011896  movzx   edx, byte ptr [r9+0D1h]
0x14001189e  mov     eax, [rsp+118h+arg_18]
0x1400118a5  movzx   r9d, byte ptr [r9+0D0h]
0x1400118ad  mov     dword ptr [rsp+118h+var_E0], r12d
0x1400118b2  mov     [rsp+118h+var_78], edx
0x1400118b9  mov     edx, 2Ch ; ','
0x1400118be  mov     dword ptr [rsp+118h+var_E8], r13d
0x1400118c3  mov     dword ptr [rsp+118h+var_F0], eax
0x1400118c7  mov     eax, [rsp+118h+var_78]
0x1400118ce  mov     dword ptr [rsp+118h+var_F8], eax
0x1400118d2  call    WPP_SF_DDDDDDDDDDDDDDDD
0x1400118d7  mov     r13, [rsp+118h+MiniportVcContext]
0x1400118df  lea     rdi, WPP_GLOBAL_Control
0x1400118e6  mov     ebp, 4
0x1400118eb  lea     r14d, [rbp-2]
0x1400118ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118f6  mov     [rsp+118h+var_60], rcx
0x1400118fe  cmp     rcx, rdi
0x140011901  jz      loc_140011A71
0x140011907  mov     eax, [rcx+2Ch]
0x14001190a  test    bpl, al
0x14001190d  jz      loc_140011A39
0x140011913  cmp     [rcx+29h], r14b
0x140011917  jb      loc_140011A39
0x14001191d  movzx   eax, byte ptr [r13+0DFh]
0x140011925  movzx   ecx, byte ptr [r13+0DEh]
0x14001192d  movzx   r8d, byte ptr [r13+0DDh]
0x140011935  mov     r9, [rsp+118h+MiniportVcContext]
0x14001193d  movzx   r15d, byte ptr [r13+0D4h]
0x140011945  movzx   r10d, byte ptr [r13+0DCh]
0x14001194d  movzx   r11d, byte ptr [r13+0DBh]
0x140011955  movzx   edx, byte ptr [r9+0D1h]
0x14001195d  movzx   ebx, byte ptr [r13+0DAh]
0x140011965  movzx   edi, byte ptr [r13+0D9h]
0x14001196d  movzx   esi, byte ptr [r13+0D8h]
0x140011975  movzx   ebp, byte ptr [r13+0D6h]
0x14001197d  movzx   r14d, byte ptr [r13+0D7h]
0x140011985  movzx   r12d, byte ptr [r13+0D5h]
0x14001198d  movzx   r13d, byte ptr [r13+0D0h]
0x140011995  mov     [rsp+118h+var_88], eax
0x14001199c  mov     [rsp+118h+var_90], ecx
0x1400119a3  mov     rcx, [rsp+118h+var_60]
0x1400119ab  mov     [rsp+118h+var_98], r8d
0x1400119b3  mov     [rsp+118h+var_A0], r10d
0x1400119b8  mov     [rsp+118h+var_A8], r11d
0x1400119bd  mov     rcx, [rcx+18h]
0x1400119c1  mov     [rsp+118h+var_B0], ebx
0x1400119c5  mov     [rsp+118h+var_B8], edi
0x1400119c9  mov     [rsp+118h+var_C0], esi
0x1400119cd  mov     [rsp+118h+var_C8], ebp
0x1400119d1  mov     [rsp+118h+var_D0], r14d
0x1400119d6  mov     [rsp+118h+var_D8], r15d
0x1400119db  lea     r15, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x1400119e2  mov     [rsp+118h+arg_18], edx
0x1400119e9  mov     r8, r15
0x1400119ec  movzx   edx, byte ptr [r9+0D2h]
0x1400119f4  mov     eax, [rsp+118h+arg_18]
0x1400119fb  movzx   r9d, byte ptr [r9+0D3h]
0x140011a03  mov     dword ptr [rsp+118h+var_E0], r12d
0x140011a08  mov     [rsp+118h+var_78], edx
0x140011a0f  mov     edx, 2Dh ; '-'
0x140011a14  mov     dword ptr [rsp+118h+var_E8], r13d
0x140011a19  mov     dword ptr [rsp+118h+var_F0], eax
0x140011a1d  mov     eax, [rsp+118h+var_78]
0x140011a24  mov     dword ptr [rsp+118h+var_F8], eax
0x140011a28  call    WPP_SF_DDDDDDDDDDDDDDDD
0x140011a2d  lea     rdi, WPP_GLOBAL_Control
0x140011a34  mov     ebp, 4
0x140011a39  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a40  mov     r14d, 2
0x140011a46  cmp     rcx, rdi
0x140011a49  jz      short loc_140011A69
0x140011a4b  mov     eax, [rcx+2Ch]
0x140011a4e  test    bpl, al
0x140011a51  jz      short loc_140011A69
0x140011a53  cmp     [rcx+29h], r14b
0x140011a57  jb      short loc_140011A69
0x140011a59  mov     rcx, [rcx+18h]
0x140011a5d  lea     edx, [r14+2Ch]
0x140011a61  mov     r8, r15
0x140011a64  call    WPP_SF_
0x140011a69  mov     r13, [rsp+118h+MiniportVcContext]
0x140011a71  movups  xmm0, xmmword ptr [r13+0D0h]
0x140011a79  mov     rbx, [rsp+118h+arg_0]
0x140011a81  lea     rcx, [r13+0C0h]
0x140011a88  mov     rax, [rcx]
0x140011a8b  mov     r12, [rsp+118h+NetBufferList]
0x140011a93  movdqu  xmmword ptr [rax+14h], xmm0
0x140011a98  mov     rax, [rcx]
0x140011a9b  or      dword ptr [rax+8], 8
0x140011a9f  jmp     short loc_140011AD3
0x140011aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140011aa8  lea     rdi, WPP_GLOBAL_Control
0x140011aaf  cmp     rcx, rdi
0x140011ab2  jz      short loc_140011AD3
0x140011ab4  mov     eax, [rcx+2Ch]
0x140011ab7  test    bpl, al
0x140011aba  jz      short loc_140011AD3
0x140011abc  cmp     [rcx+29h], r14b
0x140011ac0  jb      short loc_140011AD3
0x140011ac2  mov     rcx, [rcx+18h]
0x140011ac6  mov     edx, 2Fh ; '/'
0x140011acb  mov     r8, r15
0x140011ace  call    WPP_SF_
0x140011ad3  lea     rcx, [r13+3Ch]
0x140011ad7  mov     edx, 40000h
0x140011adc  call    SetFlags
0x140011ae1  mov     rax, [rsp+118h+var_58]
0x140011ae9  mov     edx, 1030h
  ... truncated ...
```

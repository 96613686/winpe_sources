# SetCompressionInfo

- ea: `0x14002aa40`
- end: `0x14002b17a`
- name: `SetCompressionInfo`
- size: `1850`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x140002cc0`
- `0x1400048c0`
- `0x140005494`
- `0x14000550c`
- `0x1400084d8`
- `0x1400085b0`
- `0x14000a290`
- `0x14000a5f4`
- `0x14000a648`
- `0x1400161f0`
- `0x140016700`
- `0x140024874`
- `0x140024a80`
- `0x140024d68`
- `0x140024e48`
- `0x14002a8e0`
- `0x14002aa40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002af66`
- `ntoskrnl!KeInitializeEvent` at `0x14002af66`
- `ntoskrnl!KeSetTimerEx` at `0x14002b0af`
- `ntoskrnl!KeSetTimerEx` at `0x14002b0af`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002af48`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002afd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b0c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b0fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b140`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002af48`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002afd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b0c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b0fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b140`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002abe6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002afaf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002afe5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b027`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b119`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002abe6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002afaf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002afe5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b027`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b119`

## pseudocode

```c
__int64 __fastcall SetCompressionInfo(_QWORD *a1, unsigned int a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  int CCP; // r14d
  int v8; // eax
  __int64 v9; // rcx
  _QWORD *v10; // rsi
  char *v11; // rbx
  KSPIN_LOCK *v12; // r15
  __int64 v13; // r13
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r9
  _OWORD *v17; // rcx
  _OWORD *v18; // rax
  __int128 v19; // xmm1
  _OWORD *v20; // rcx
  _OWORD *v21; // rax
  __int128 v22; // xmm1
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  KIRQL v28; // al
  bool v29; // zf
  KIRQL v30; // al
  _QWORD *v31; // rcx
  KIRQL v32; // al
  PVOID v34; // [rsp+30h] [rbp-D0h] BYREF
  PVOID Entry; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v36[21]; // [rsp+40h] [rbp-C0h] BYREF

  v34 = 0;
  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  *a5 = 0;
  if ( a2 < 0x2E8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a2, 744);
    }
    *a5 = 744;
    return (unsigned int)-1073741820;
  }
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v8 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v8 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
  v9 = *a1;
  if ( v8 )
  {
    CCP = ValidateLinkAndBundle(v9, 1, &v34, &Entry);
    if ( CCP < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, *a1);
      }
      goto LABEL_26;
    }
LABEL_27:
    v11 = (char *)Entry;
    v10 = v34;
    v12 = (KSPIN_LOCK *)((char *)Entry + 1768);
    v13 = *((_QWORD *)v34 + 9);
    v11[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 221);
    v15 = 2;
    *((_DWORD *)v11 + 128) = *((_DWORD *)a1 + 28);
    *((_DWORD *)v11 + 222) = *((_DWORD *)a1 + 120);
    v16 = 128;
    if ( (a1[14] & 4) != 0 )
    {
      v17 = a1 + 15;
      *((_DWORD *)v11 + 117) = *((_DWORD *)a1 + 17);
      v14 = 2;
      *((_QWORD *)v11 + 51) = a1[1];
      *((_OWORD *)v11 + 26) = *((_OWORD *)a1 + 1);
      *((_QWORD *)v11 + 54) = a1[4];
      v18 = v11 + 520;
      *(_OWORD *)(v11 + 440) = *(_OWORD *)(a1 + 5);
      *((_QWORD *)v11 + 57) = a1[7];
      do
      {
        *v18 = *v17;
        v18[1] = v17[1];
        v18[2] = v17[2];
        v18[3] = v17[3];
        v18[4] = v17[4];
        v18[5] = v17[5];
        v18[6] = v17[6];
        v19 = v17[7];
        v17 += 8;
        v18[7] = v19;
        v18 += 8;
        --v14;
      }
      while ( v14 );
    }
    if ( (a1[60] & 4) != 0 )
    {
      v20 = a1 + 61;
      *((_DWORD *)v11 + 211) = *((_DWORD *)a1 + 109);
      *((_QWORD *)v11 + 98) = a1[47];
      *(_OWORD *)(v11 + 792) = *((_OWORD *)a1 + 24);
      *((_QWORD *)v11 + 101) = a1[50];
      v21 = v11 + 896;
      *((_OWORD *)v11 + 51) = *(_OWORD *)(a1 + 51);
      *((_QWORD *)v11 + 104) = a1[53];
      do
      {
        *v21 = *v20;
        v21[1] = v20[1];
        v21[2] = v20[2];
        v21[3] = v20[3];
        v21[4] = v20[4];
        v21[5] = v20[5];
        v21[6] = v20[6];
        v22 = v20[7];
        v20 += 8;
        v21[7] = v22;
        v21 += 8;
        --v15;
      }
      while ( v15 );
    }
    v23 = 0x4000;
    if ( (a1[14] & 8) != 0 )
    {
      *((_DWORD *)v11 + 116) = *((_DWORD *)a1 + 16);
      if ( (*((_DWORD *)v11 + 4) & 0x4000) == 0 )
      {
        *((_WORD *)v11 + 660) = 0;
        LOBYTE(v14) = 1;
        *((_DWORD *)v11 + 4) |= 0x4000u;
        CCP = WanAllocateCCP(v11, v11 + 408, v14, 128);
        if ( CCP )
          goto LABEL_45;
      }
      if ( (*((_DWORD *)v11 + 4) & 0x10000) == 0 )
      {
        *((_WORD *)v11 + 660) = 0;
        *((_DWORD *)v11 + 4) |= 0x10000u;
        LOBYTE(v16) = 1;
        CCP = WanAllocateECP((__int64)v11, (_DWORD *)v11 + 102, (__int64)(v11 + 1160), v16);
      }
      if ( CCP )
        goto LABEL_45;
    }
    if ( (a1[60] & 8) != 0 )
    {
      *((_DWORD *)v11 + 210) = *((_DWORD *)a1 + 108);
      if ( (*((_DWORD *)v11 + 4) & 0x8000) == 0 )
      {
        *((_WORD *)v11 + 662) = 0;
        *((_WORD *)v11 + 664) = 0;
        *((_DWORD *)v11 + 333) = 0;
        *((_DWORD *)v11 + 4) |= 0x8000u;
        CCP = WanAllocateCCP(v11, v11 + 784, 0, v16);
        if ( CCP )
          goto LABEL_45;
      }
      v23 = 0x20000;
      if ( (*((_DWORD *)v11 + 4) & 0x20000) == 0 )
      {
        *((_WORD *)v11 + 662) = 0;
        *((_WORD *)v11 + 664) = 0;
        *((_DWORD *)v11 + 333) = 0;
        *((_DWORD *)v11 + 4) |= 0x20000u;
        CCP = WanAllocateECP((__int64)v11, (_DWORD *)v11 + 196, (__int64)(v11 + 1240), 0);
      }
    }
    if ( !CCP )
    {
LABEL_53:
      if ( *(_DWORD *)(v13 + 124) == 13 )
      {
        memset(v36, 0, 0x148u);
        ++*((_DWORD *)v11 + 6);
        KeReleaseSpinLock(v12, v11[1776]);
        *(_QWORD *)&v36[1] = 1;
        KeInitializeEvent((PRKEVENT)&v36[19], NotificationEvent, 0);
        *((_QWORD *)&v36[1] + 1) = v13;
        *(_QWORD *)&v36[3] = 0x100EC0196LL;
        LODWORD(v36[5]) = 67175041;
        *((_QWORD *)&v36[5] + 1) = a1;
        LODWORD(v36[6]) = a2;
        *((_QWORD *)&v36[2] + 1) = v10[7];
        NdisWanSubmitNdisRequest(v13, v36);
        v28 = KeAcquireSpinLockRaiseToDpc(v12);
        v11[1776] = v28;
        v29 = (*((_DWORD *)v11 + 6))-- == 1;
        if ( v29 )
          DoDerefBundleCBWork(v11);
        else
          KeReleaseSpinLock(v12, v28);
        v11[1776] = KeAcquireSpinLockRaiseToDpc(v12);
      }
      if ( (a1[14] & 1) != 0 )
      {
        *((_DWORD *)v11 + 4) |= 0x2000u;
      }
      else
      {
        *((_DWORD *)v11 + 4) &= ~0x2000u;
        if ( (*((_DWORD *)v11 + 4) & 0x80u) == 0 )
        {
          ++*((_DWORD *)v11 + 6);
          *((_DWORD *)v11 + 4) |= 0x80u;
          v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
          v31 = *(_QWORD **)&WPP_MAIN_CB.DeviceQueue.Type;
          LOBYTE(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) = v30;
          if ( **(struct _DEVICE_OBJECT ***)&WPP_MAIN_CB.DeviceQueue.Type != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.AlignmentRequirement )
            __fastfail(3u);
          *((_QWORD *)v11 + 167) = &WPP_MAIN_CB.AlignmentRequirement;
          *((_QWORD *)v11 + 168) = v31;
          *v31 = v11 + 1336;
          *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = v11 + 1336;
          if ( ++LODWORD(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) > HIDWORD(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) )
            HIDWORD(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) = WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
          if ( !LOBYTE(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink) )
          {
            LOBYTE(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink) = 1;
            KeSetTimerEx(
              (PKTIMER)&WPP_MAIN_CB.Dpc.DeferredContext,
              (LARGE_INTEGER)-150000LL,
              0,
              (PKDPC)&WPP_MAIN_CB.DeviceQueue.DeviceListHead);
          }
          KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject, (KIRQL)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
        }
      }
      SetBundleFlags(v11, v15, v14, v16);
      goto LABEL_69;
    }
LABEL_45:
    v24 = *((_DWORD *)v11 + 4);
    if ( (v24 & 0x4000) != 0 )
    {
      LOBYTE(v14) = 1;
      *((_DWORD *)v11 + 4) = v24 & 0xFFFFBFFF;
      WanDeallocateCCP(v11, v11 + 408, v14);
    }
    v25 = *((_DWORD *)v11 + 4);
    if ( (v25 & 0x8000) != 0 )
    {
      *((_DWORD *)v11 + 4) = v25 & 0xFFFF7FFF;
      WanDeallocateCCP(v11, v11 + 784, 0);
    }
    v26 = *((_DWORD *)v11 + 4);
    if ( (v26 & 0x10000) != 0 )
    {
      *((_DWORD *)v11 + 4) = v26 & 0xFFFEFFFF;
      WanDeallocateECP(v23, (__int64)(v11 + 408), (_QWORD *)v11 + 145);
    }
    v27 = *((_DWORD *)v11 + 4);
    if ( (v27 & 0x20000) != 0 )
    {
      *((_DWORD *)v11 + 4) = v27 & 0xFFFDFFFF;
      WanDeallocateECP(v23, (__int64)(v11 + 784), (_QWORD *)v11 + 155);
    }
    goto LABEL_53;
  }
  CCP = 0;
  if ( (unsigned __int8)AreLinkAndBundleValid(v9, 1, &v34, &Entry) )
    goto LABEL_27;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, *a1);
  }
  CCP = 601;
LABEL_26:
  v10 = v34;
  v11 = (char *)Entry;
LABEL_69:
  if ( v11 )
  {
    v29 = (*((_DWORD *)v11 + 6))-- == 1;
    if ( v29 )
      DoDerefBundleCBWork(v11);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v11 + 221, v11[1776]);
  }
  if ( v10 )
  {
    v32 = KeAcquireSpinLockRaiseToDpc(v10 + 92);
    *((_BYTE *)v10 + 744) = v32;
    v29 = (*((_DWORD *)v10 + 7))-- == 1;
    if ( v29 )
      DoDerefLinkCBWork(v10);
    else
      KeReleaseSpinLock(v10 + 92, v32);
  }
  return (unsigned int)CCP;
}

```

## disassembly

```asm
0x14002aa40  mov     [rsp-8+arg_10], rbx
0x14002aa45  push    rbp
0x14002aa46  push    rsi
0x14002aa47  push    rdi
0x14002aa48  push    r12
0x14002aa4a  push    r13
0x14002aa4c  push    r14
0x14002aa4e  push    r15
0x14002aa50  lea     rbp, [rsp-0A0h]
0x14002aa58  sub     rsp, 1A0h
0x14002aa5f  mov     rax, cs:__security_cookie
0x14002aa66  xor     rax, rsp
0x14002aa69  mov     [rbp+0D0h+var_40], rax
0x14002aa70  mov     rbx, [rbp+0D0h+arg_20]
0x14002aa77  mov     r12d, edx
0x14002aa7a  mov     rdi, rcx
0x14002aa7d  mov     [rsp+1D0h+var_1A0], 0
0x14002aa86  mov     [rsp+1D0h+Entry], 0
0x14002aa8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa96  lea     r15, WPP_GLOBAL_Control
0x14002aa9d  lea     r13, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002aaa4  mov     sil, 20h ; ' '
0x14002aaa7  cmp     rcx, r15
0x14002aaaa  jz      short loc_14002AACB
0x14002aaac  mov     eax, [rcx+2Ch]
0x14002aaaf  test    sil, al
0x14002aab2  jz      short loc_14002AACB
0x14002aab4  cmp     byte ptr [rcx+29h], 5
0x14002aab8  jb      short loc_14002AACB
0x14002aaba  mov     rcx, [rcx+18h]
0x14002aabe  mov     edx, 4Dh ; 'M'
0x14002aac3  mov     r8, r13
0x14002aac6  call    WPP_SF_
0x14002aacb  mov     r14d, 2E8h
0x14002aad1  mov     dword ptr [rbx], 0
0x14002aad7  cmp     r12d, r14d
0x14002aada  jnb     short loc_14002AB1D
0x14002aadc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aae3  cmp     rcx, r15
0x14002aae6  jz      short loc_14002AB0F
0x14002aae8  mov     eax, [rcx+2Ch]
0x14002aaeb  test    sil, al
0x14002aaee  jz      short loc_14002AB0F
0x14002aaf0  cmp     byte ptr [rcx+29h], 3
0x14002aaf4  jb      short loc_14002AB0F
0x14002aaf6  mov     rcx, [rcx+18h]
0x14002aafa  mov     edx, 4Eh ; 'N'
0x14002aaff  mov     r9d, r12d
0x14002ab02  mov     [rsp+1D0h+var_1B0], r14d
0x14002ab07  mov     r8, r13
0x14002ab0a  call    WPP_SF_dd
0x14002ab0f  mov     [rbx], r14d
0x14002ab12  mov     r14d, 0C0000004h
0x14002ab18  jmp     loc_14002B14C
0x14002ab1d  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x14002ab23  test    al, 10h
0x14002ab25  jz      short loc_14002AB2C
0x14002ab27  and     eax, 1
0x14002ab2a  jmp     short loc_14002AB31
0x14002ab2c  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x14002ab31  mov     rcx, [rdi]
0x14002ab34  lea     r9, [rsp+1D0h+Entry]
0x14002ab39  lea     r8, [rsp+1D0h+var_1A0]
0x14002ab3e  mov     dl, 1
0x14002ab40  test    eax, eax
0x14002ab42  jnz     short loc_14002AB85
0x14002ab44  xor     r14d, r14d
0x14002ab47  call    AreLinkAndBundleValid
0x14002ab4c  test    al, al
0x14002ab4e  jnz     short loc_14002ABCE
0x14002ab50  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab57  cmp     rcx, r15
0x14002ab5a  jz      short loc_14002AB7D
0x14002ab5c  mov     eax, [rcx+2Ch]
0x14002ab5f  test    sil, al
0x14002ab62  jz      short loc_14002AB7D
0x14002ab64  cmp     byte ptr [rcx+29h], 3
0x14002ab68  jb      short loc_14002AB7D
0x14002ab6a  mov     r9, [rdi]
0x14002ab6d  lea     edx, [r14+50h]
0x14002ab71  mov     rcx, [rcx+18h]
0x14002ab75  mov     r8, r13
0x14002ab78  call    WPP_SF_q
0x14002ab7d  mov     r14d, 259h
0x14002ab83  jmp     short loc_14002ABBF
0x14002ab85  call    ValidateLinkAndBundle
0x14002ab8a  mov     r14d, eax
0x14002ab8d  test    eax, eax
0x14002ab8f  jns     short loc_14002ABCE
0x14002ab91  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab98  cmp     rcx, r15
0x14002ab9b  jz      short loc_14002ABBF
0x14002ab9d  mov     edx, [rcx+2Ch]
0x14002aba0  test    sil, dl
0x14002aba3  jz      short loc_14002ABBF
0x14002aba5  cmp     byte ptr [rcx+29h], 3
0x14002aba9  jb      short loc_14002ABBF
0x14002abab  mov     r9, [rdi]
0x14002abae  mov     edx, 4Fh ; 'O'
0x14002abb3  mov     rcx, [rcx+18h]
0x14002abb7  mov     r8, r13
0x14002abba  call    WPP_SF_q
0x14002abbf  mov     rsi, [rsp+1D0h+var_1A0]
0x14002abc4  mov     rbx, [rsp+1D0h+Entry]
0x14002abc9  jmp     loc_14002B0DC
0x14002abce  mov     rbx, [rsp+1D0h+Entry]
0x14002abd3  mov     rsi, [rsp+1D0h+var_1A0]
0x14002abd8  lea     r15, [rbx+6E8h]
0x14002abdf  mov     r13, [rsi+48h]
0x14002abe3  mov     rcx, r15; SpinLock
0x14002abe6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002abed  nop     dword ptr [rax+rax+00h]
0x14002abf2  mov     [rbx+6F0h], al
0x14002abf8  mov     edx, 2
0x14002abfd  mov     eax, [rdi+70h]
0x14002ac00  mov     [rbx+200h], eax
0x14002ac06  mov     eax, [rdi+1E0h]
0x14002ac0c  mov     [rbx+378h], eax
0x14002ac12  lea     r9d, [rdx+7Eh]
0x14002ac16  mov     eax, [rdi+70h]
0x14002ac19  test    al, 4
0x14002ac1b  jz      loc_14002ACBC
0x14002ac21  mov     eax, [rdi+44h]
0x14002ac24  lea     rcx, [rdi+78h]
0x14002ac28  mov     [rbx+1D4h], eax
0x14002ac2e  mov     r8d, edx
0x14002ac31  mov     rax, [rdi+8]
0x14002ac35  mov     [rbx+198h], rax
0x14002ac3c  movups  xmm0, xmmword ptr [rdi+10h]
0x14002ac40  movdqu  xmmword ptr [rbx+1A0h], xmm0
0x14002ac48  mov     rax, [rdi+20h]
0x14002ac4c  mov     [rbx+1B0h], rax
0x14002ac53  lea     rax, [rbx+208h]
0x14002ac5a  movups  xmm0, xmmword ptr [rdi+28h]
0x14002ac5e  movups  xmmword ptr [rbx+1B8h], xmm0
0x14002ac65  movsd   xmm1, qword ptr [rdi+38h]
0x14002ac6a  movsd   qword ptr [rbx+1C8h], xmm1
0x14002ac72  movups  xmm0, xmmword ptr [rcx]
0x14002ac75  movups  xmmword ptr [rax], xmm0
0x14002ac78  movups  xmm1, xmmword ptr [rcx+10h]
0x14002ac7c  movups  xmmword ptr [rax+10h], xmm1
0x14002ac80  movups  xmm0, xmmword ptr [rcx+20h]
0x14002ac84  movups  xmmword ptr [rax+20h], xmm0
0x14002ac88  movups  xmm1, xmmword ptr [rcx+30h]
0x14002ac8c  movups  xmmword ptr [rax+30h], xmm1
0x14002ac90  movups  xmm0, xmmword ptr [rcx+40h]
0x14002ac94  movups  xmmword ptr [rax+40h], xmm0
0x14002ac98  movups  xmm1, xmmword ptr [rcx+50h]
0x14002ac9c  movups  xmmword ptr [rax+50h], xmm1
0x14002aca0  movups  xmm0, xmmword ptr [rcx+60h]
0x14002aca4  movups  xmmword ptr [rax+60h], xmm0
0x14002aca8  movups  xmm1, xmmword ptr [rcx+70h]
0x14002acac  add     rcx, r9
0x14002acaf  movups  xmmword ptr [rax+70h], xmm1
0x14002acb3  add     rax, r9
0x14002acb6  sub     r8, 1
0x14002acba  jnz     short loc_14002AC72
0x14002acbc  mov     eax, [rdi+1E0h]
0x14002acc2  test    al, 4
0x14002acc4  jz      loc_14002AD77
0x14002acca  mov     eax, [rdi+1B4h]
0x14002acd0  lea     rcx, [rdi+1E8h]
0x14002acd7  mov     [rbx+34Ch], eax
0x14002acdd  mov     rax, [rdi+178h]
0x14002ace4  mov     [rbx+310h], rax
0x14002aceb  movups  xmm0, xmmword ptr [rdi+180h]
0x14002acf2  movdqu  xmmword ptr [rbx+318h], xmm0
0x14002acfa  mov     rax, [rdi+190h]
0x14002ad01  mov     [rbx+328h], rax
0x14002ad08  lea     rax, [rbx+380h]
0x14002ad0f  movups  xmm0, xmmword ptr [rdi+198h]
0x14002ad16  movups  xmmword ptr [rbx+330h], xmm0
0x14002ad1d  movsd   xmm1, qword ptr [rdi+1A8h]
0x14002ad25  movsd   qword ptr [rbx+340h], xmm1
0x14002ad2d  movups  xmm0, xmmword ptr [rcx]
0x14002ad30  movups  xmmword ptr [rax], xmm0
0x14002ad33  movups  xmm1, xmmword ptr [rcx+10h]
0x14002ad37  movups  xmmword ptr [rax+10h], xmm1
0x14002ad3b  movups  xmm0, xmmword ptr [rcx+20h]
0x14002ad3f  movups  xmmword ptr [rax+20h], xmm0
0x14002ad43  movups  xmm1, xmmword ptr [rcx+30h]
0x14002ad47  movups  xmmword ptr [rax+30h], xmm1
0x14002ad4b  movups  xmm0, xmmword ptr [rcx+40h]
0x14002ad4f  movups  xmmword ptr [rax+40h], xmm0
0x14002ad53  movups  xmm1, xmmword ptr [rcx+50h]
0x14002ad57  movups  xmmword ptr [rax+50h], xmm1
0x14002ad5b  movups  xmm0, xmmword ptr [rcx+60h]
0x14002ad5f  movups  xmmword ptr [rax+60h], xmm0
0x14002ad63  movups  xmm1, xmmword ptr [rcx+70h]
0x14002ad67  add     rcx, r9
0x14002ad6a  movups  xmmword ptr [rax+70h], xmm1
0x14002ad6e  add     rax, r9
0x14002ad71  sub     rdx, 1
0x14002ad75  jnz     short loc_14002AD2D
0x14002ad77  mov     eax, [rdi+70h]
0x14002ad7a  mov     ecx, 4000h
0x14002ad7f  test    al, 8
0x14002ad81  jz      short loc_14002ADF6
0x14002ad83  mov     eax, [rdi+40h]
0x14002ad86  mov     [rbx+1D0h], eax
0x14002ad8c  test    [rbx+10h], ecx
0x14002ad8f  jnz     short loc_14002ADBA
0x14002ad91  xor     eax, eax
0x14002ad93  lea     rdx, [rbx+198h]
0x14002ad9a  mov     [rbx+528h], ax
0x14002ada1  mov     r8b, 1
0x14002ada4  or      [rbx+10h], ecx
0x14002ada7  mov     rcx, rbx
0x14002adaa  call    WanAllocateCCP
0x14002adaf  mov     r14d, eax
0x14002adb2  test    eax, eax
0x14002adb4  jnz     loc_14002AE95
0x14002adba  test    dword ptr [rbx+10h], 10000h
0x14002adc1  jnz     short loc_14002ADED
0x14002adc3  xor     eax, eax
0x14002adc5  lea     r8, [rbx+488h]
0x14002adcc  mov     [rbx+528h], ax
0x14002add3  lea     rdx, [rbx+198h]
0x14002adda  bts     dword ptr [rbx+10h], 10h
0x14002addf  mov     r9b, 1
0x14002ade2  mov     rcx, rbx
0x14002ade5  call    WanAllocateECP
0x14002adea  mov     r14d, eax
0x14002aded  test    r14d, r14d
0x14002adf0  jnz     loc_14002AE95
0x14002adf6  mov     eax, [rdi+1E0h]
0x14002adfc  test    al, 8
0x14002adfe  jz      loc_14002AE8C
0x14002ae04  mov     eax, [rdi+1B0h]
0x14002ae0a  mov     [rbx+348h], eax
0x14002ae10  test    dword ptr [rbx+10h], 8000h
0x14002ae17  jnz     short loc_14002AE4D
0x14002ae19  xor     eax, eax
0x14002ae1b  lea     rdx, [rbx+310h]
0x14002ae22  mov     [rbx+52Ch], ax
0x14002ae29  xor     r8d, r8d
0x14002ae2c  mov     [rbx+530h], ax
0x14002ae33  mov     rcx, rbx
0x14002ae36  mov     [rbx+534h], eax
0x14002ae3c  bts     dword ptr [rbx+10h], 0Fh
0x14002ae41  call    WanAllocateCCP
0x14002ae46  mov     r14d, eax
0x14002ae49  test    eax, eax
0x14002ae4b  jnz     short loc_14002AE95
0x14002ae4d  mov     ecx, 20000h
0x14002ae52  test    [rbx+10h], ecx
0x14002ae55  jnz     short loc_14002AE8C
0x14002ae57  xor     eax, eax
0x14002ae59  lea     r8, [rbx+4D8h]
0x14002ae60  mov     [rbx+52Ch], ax
0x14002ae67  lea     rdx, [rbx+310h]
0x14002ae6e  mov     [rbx+530h], ax
0x14002ae75  xor     r9d, r9d
0x14002ae78  mov     [rbx+534h], eax
0x14002ae7e  or      [rbx+10h], ecx
0x14002ae81  mov     rcx, rbx
0x14002ae84  call    WanAllocateECP
0x14002ae89  mov     r14d, eax
0x14002ae8c  test    r14d, r14d
0x14002ae8f  jz      loc_14002AF1F
0x14002ae95  mov     eax, [rbx+10h]
0x14002ae98  bt      eax, 0Eh
0x14002ae9c  jnb     short loc_14002AEB7
0x14002ae9e  btr     eax, 0Eh
0x14002aea2  lea     rdx, [rbx+198h]
0x14002aea9  mov     r8b, 1
0x14002aeac  mov     [rbx+10h], eax
0x14002aeaf  mov     rcx, rbx
0x14002aeb2  call    WanDeallocateCCP
0x14002aeb7  mov     eax, [rbx+10h]
0x14002aeba  bt      eax, 0Fh
0x14002aebe  jnb     short loc_14002AED9
0x14002aec0  btr     eax, 0Fh
0x14002aec4  lea     rdx, [rbx+310h]
0x14002aecb  xor     r8d, r8d
0x14002aece  mov     [rbx+10h], eax
0x14002aed1  mov     rcx, rbx
0x14002aed4  call    WanDeallocateCCP
0x14002aed9  mov     eax, [rbx+10h]
0x14002aedc  bt      eax, 10h
0x14002aee0  jnb     short loc_14002AEFC
0x14002aee2  btr     eax, 10h
0x14002aee6  lea     r8, [rbx+488h]
0x14002aeed  lea     rdx, [rbx+198h]
0x14002aef4  mov     [rbx+10h], eax
0x14002aef7  call    WanDeallocateECP
0x14002aefc  mov     eax, [rbx+10h]
0x14002aeff  bt      eax, 11h
0x14002af03  jnb     short loc_14002AF1F
0x14002af05  btr     eax, 11h
0x14002af09  lea     r8, [rbx+4D8h]
0x14002af10  lea     rdx, [rbx+310h]
0x14002af17  mov     [rbx+10h], eax
0x14002af1a  call    WanDeallocateECP
0x14002af1f  cmp     dword ptr [r13+7Ch], 0Dh
0x14002af24  jnz     loc_14002AFF7
0x14002af2a  xor     edx, edx; Val
0x14002af2c  lea     rcx, [rsp+1D0h+var_190]; void *
0x14002af31  mov     r8d, 148h; Size
0x14002af37  call    memset
  ... truncated ...
```

# ClIncomingCallWork

- ea: `0x140007fb0`
- end: `0x1400084d1`
- name: `ClIncomingCallWork`
- size: `1313`
- prototype: `NDIS_IO_WORKITEM_FUNCTION`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002cc0`
- `0x140005494`
- `0x14000550c`
- `0x140007364`
- `0x140007fb0`
- `0x1400084d8`
- `0x1400085b0`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a5f4`
- `0x14000a6e0`
- `0x14000a744`

## import_xrefs

- `ntoskrnl!MmLockPagableDataSection` at `0x140008050`
- `ntoskrnl!MmLockPagableDataSection` at `0x140008050`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400080d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000842e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008463`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400080d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000842e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008463`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400080af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400080ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000843d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400080af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400080ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000843d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008025`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008025`
- `NDIS!NdisFreeIoWorkItem` at `0x140008034`
- `NDIS!NdisFreeIoWorkItem` at `0x140008034`
- `NDIS!NdisClIncomingCallComplete` at `0x14000847f`
- `NDIS!NdisClIncomingCallComplete` at `0x14000847f`

## pseudocode

```c
void __fastcall ClIncomingCallWork(__int64 *WorkItemContext, NDIS_HANDLE NdisIoWorkItemHandle)
{
  __int64 v2; // r9
  char v3; // r15
  __int64 v4; // rdi
  struct _CO_CALL_PARAMETERS *v6; // r14
  __int64 v8; // rbp
  __int64 v9; // rdx
  int v10; // eax
  NDIS_STATUS v11; // esi
  unsigned int *v12; // rbx
  KSPIN_LOCK *v13; // r12
  KIRQL v14; // al
  _BYTE *v15; // rdi
  KSPIN_LOCK *v16; // r13
  __int64 v17; // rdx
  __int64 v18; // r8
  _OWORD *p_TokenRate; // rax
  PCO_CALL_MANAGER_PARAMETERS CallMgrParameters; // rax
  int v21; // eax
  PCO_MEDIA_PARAMETERS MediaParameters; // rcx
  __int64 Length; // r9
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  char *v26; // rax
  __int64 v27; // rcx
  bool v28; // zf
  KIRQL v29; // al
  PVOID v30; // [rsp+70h] [rbp+8h] BYREF
  PVOID Entry; // [rsp+80h] [rbp+18h] BYREF

  v2 = *WorkItemContext;
  v3 = 0;
  v4 = WorkItemContext[1];
  v6 = (struct _CO_CALL_PARAMETERS *)WorkItemContext[2];
  v30 = 0;
  v8 = *(_QWORD *)(v2 + 32);
  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, v2, v4);
  }
  ExFreePoolWithTag(WorkItemContext, 0);
  NdisFreeIoWorkItem(NdisIoWorkItemHandle);
  if ( !g_fPagesLocked )
  {
    MmLockPagableDataSection(WanAllocateECP);
    g_fPagesLocked = 1;
  }
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v10 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v10 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
  LOBYTE(v9) = 1;
  if ( v10 )
  {
    v11 = ValidateLinkAndBundle(v4, 1, &v30, &Entry);
    if ( v11 >= 0 )
      goto LABEL_12;
  }
  else
  {
    v11 = 0;
    if ( (unsigned __int8)AreLinkAndBundleValid(v4, v9, &v30, &Entry) )
    {
LABEL_12:
      v12 = (unsigned int *)v30;
      v13 = (KSPIN_LOCK *)((char *)v30 + 736);
      v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v30 + 92);
      *((_BYTE *)v12 + 744) = v14;
      v12[6] = 2;
      v12[9] &= ~4u;
      KeReleaseSpinLock(v13, v14);
      v15 = Entry;
      v16 = (KSPIN_LOCK *)((char *)Entry + 1768);
      v15[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 221);
      p_TokenRate = &v6->CallMgrParameters->Transmit.TokenRate;
      *((_OWORD *)v12 + 8) = *p_TokenRate;
      *((_OWORD *)v12 + 9) = p_TokenRate[1];
      CallMgrParameters = v6->CallMgrParameters;
      *((_OWORD *)v12 + 10) = *(_OWORD *)&CallMgrParameters->Receive.TokenRate;
      *((_OWORD *)v12 + 11) = *(_OWORD *)&CallMgrParameters->Receive.DelayVariation;
      v21 = v12[34];
      if ( !v21 )
      {
        v21 = 3600;
        v12[34] = 3600;
      }
      if ( !v12[42] )
        v12[42] = v21;
      v12[73] = 256;
      v12[72] = 256;
      *((_QWORD *)v12 + 15) = ReceivePPP;
      if ( *(_DWORD *)(v8 + 120) == 12 && *(_DWORD *)(v8 + 124) == 12 )
      {
        v3 = 1;
        *((_QWORD *)v12 + 15) = DetectBroadbandFraming;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
        }
      }
      if ( (unsigned int)(*(_DWORD *)(v8 + 124) - 14) <= 1 )
      {
        v12[73] = 0x10000000;
        v12[72] = 0x10000000;
        *((_QWORD *)v12 + 15) = ReceivePassThrough;
        *((_DWORD *)v15 + 4) |= 0x80000u;
      }
      if ( v3 )
      {
        v12[72] |= 0x200u;
        v12[73] |= 0x200u;
        v18 = v12[72];
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_33;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_qdd(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids,
            v12,
            v18,
            v12[73]);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          37,
          WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids,
          v12[34],
          v12[52]);
      }
LABEL_33:
      if ( (v6->Flags & 1) != 0 )
        *((_DWORD *)v15 + 4) |= 0x100u;
      if ( (v6->Flags & 4) != 0 )
        *((_QWORD *)v12 + 8) = v6[5].MediaParameters;
      MediaParameters = v6->MediaParameters;
      Length = MediaParameters->MediaSpecific.Length;
      if ( (unsigned int)Length >= 0x30 )
      {
        v17 = *(unsigned __int16 *)MediaParameters[1].MediaSpecific.Parameters;
        if ( (unsigned int)v17 >= 0x70 )
        {
          if ( (MediaParameters[1].Flags & 1) == 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
            }
            goto LABEL_63;
          }
          v26 = (char *)MediaParameters + *(_QWORD *)&MediaParameters[2].Flags;
          Length = *((unsigned int *)v26 + 40);
          if ( (unsigned int)Length >= 8 )
          {
            v27 = *((unsigned int *)v26 + 41);
            if ( *(_DWORD *)&v26[v27 + 56] == 1396789842 )
              *((_DWORD *)v15 + 447) = *(_DWORD *)&v26[v27 + 60];
            goto LABEL_63;
          }
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            v25 = 41;
            goto LABEL_42;
          }
        }
        else
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            Length = (unsigned int)v17;
            v25 = 39;
            goto LABEL_42;
          }
        }
      }
      else
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v25 = 38;
LABEL_42:
          WPP_SF_d(v24->AttachedDevice, v25, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, Length);
        }
      }
LABEL_63:
      *((_DWORD *)v15 + 17) = 256;
      *((_DWORD *)v15 + 18) = 256;
      UpdateBundleInfo(v15, v17, v18);
      v28 = (*((_DWORD *)v15 + 6))-- == 1;
      if ( v28 )
        DoDerefBundleCBWork(v15);
      else
        KeReleaseSpinLock(v16, v15[1776]);
      v29 = KeAcquireSpinLockRaiseToDpc(v13);
      *((_BYTE *)v12 + 744) = v29;
      v28 = v12[7]-- == 1;
      if ( v28 )
        DoDerefLinkCBWork(v12);
      else
        KeReleaseSpinLock(v13, v29);
      goto LABEL_69;
    }
    v11 = -1073741823;
  }
  v12 = (unsigned int *)v30;
LABEL_69:
  NdisClIncomingCallComplete(v11, *((NDIS_HANDLE *)v12 + 7), v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
}

```

## disassembly

```asm
0x140007fb0  mov     rax, rsp
0x140007fb3  mov     [rax+10h], rbx
0x140007fb7  push    rbp
0x140007fb8  push    rsi
0x140007fb9  push    rdi
0x140007fba  push    r12
0x140007fbc  push    r13
0x140007fbe  push    r14
0x140007fc0  push    r15
0x140007fc2  sub     rsp, 30h
0x140007fc6  mov     r9, [rcx]
0x140007fc9  xor     r15d, r15d
0x140007fcc  mov     rdi, [rcx+8]
0x140007fd0  mov     rsi, rdx
0x140007fd3  mov     r14, [rcx+10h]
0x140007fd7  mov     rbx, rcx
0x140007fda  mov     [rax+8], r15
0x140007fde  mov     rbp, [r9+20h]
0x140007fe2  mov     [rax+18h], r15
0x140007fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x140007fed  lea     r12, WPP_GLOBAL_Control
0x140007ff4  cmp     rcx, r12
0x140007ff7  jz      short loc_140008020
0x140007ff9  test    dword ptr [rcx+2Ch], 8000h
0x140008000  jz      short loc_140008020
0x140008002  cmp     byte ptr [rcx+29h], 5
0x140008006  jb      short loc_140008020
0x140008008  mov     rcx, [rcx+18h]
0x14000800c  lea     edx, [r15+22h]
0x140008010  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140008017  mov     [rax-48h], rdi
0x14000801b  call    WPP_SF_qq
0x140008020  xor     edx, edx; Tag
0x140008022  mov     rcx, rbx; P
0x140008025  call    cs:__imp_ExFreePoolWithTag
0x14000802c  nop     dword ptr [rax+rax+00h]
0x140008031  mov     rcx, rsi; NdisIoWorkItemHandle
0x140008034  call    cs:__imp_NdisFreeIoWorkItem
0x14000803b  nop     dword ptr [rax+rax+00h]
0x140008040  cmp     cs:g_fPagesLocked, r15b
0x140008047  jnz     short loc_140008063
0x140008049  lea     rcx, WanAllocateECP; AddressWithinSection
0x140008050  call    cs:__imp_MmLockPagableDataSection
0x140008057  nop     dword ptr [rax+rax+00h]
0x14000805c  mov     cs:g_fPagesLocked, 1
0x140008063  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x140008069  test    al, 10h
0x14000806b  jz      short loc_140008072
0x14000806d  and     eax, 1
0x140008070  jmp     short loc_140008077
0x140008072  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x140008077  lea     r9, [rsp+68h+Entry]
0x14000807f  mov     dl, 1
0x140008081  lea     r8, [rsp+68h+arg_0]
0x140008086  mov     rcx, rdi
0x140008089  test    eax, eax
0x14000808b  jz      loc_140008319
0x140008091  call    ValidateLinkAndBundle
0x140008096  mov     esi, eax
0x140008098  test    eax, eax
0x14000809a  js      loc_14000832E
0x1400080a0  mov     rbx, [rsp+68h+arg_0]
0x1400080a5  lea     r12, [rbx+2E0h]
0x1400080ac  mov     rcx, r12; SpinLock
0x1400080af  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400080b6  nop     dword ptr [rax+rax+00h]
0x1400080bb  mov     [rbx+2E8h], al
0x1400080c1  mov     dl, al; NewIrql
0x1400080c3  mov     dword ptr [rbx+18h], 2
0x1400080ca  mov     rcx, r12; SpinLock
0x1400080cd  and     dword ptr [rbx+24h], 0FFFFFFFBh
0x1400080d1  call    cs:__imp_KeReleaseSpinLock
0x1400080d8  nop     dword ptr [rax+rax+00h]
0x1400080dd  mov     rdi, [rsp+68h+Entry]
0x1400080e5  lea     r13, [rdi+6E8h]
0x1400080ec  mov     rcx, r13; SpinLock
0x1400080ef  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400080f6  nop     dword ptr [rax+rax+00h]
0x1400080fb  mov     [rdi+6F0h], al
0x140008101  mov     rax, [r14+8]
0x140008105  movups  xmm0, xmmword ptr [rax]
0x140008108  movups  xmmword ptr [rbx+80h], xmm0
0x14000810f  movups  xmm1, xmmword ptr [rax+10h]
0x140008113  movups  xmmword ptr [rbx+90h], xmm1
0x14000811a  mov     rax, [r14+8]
0x14000811e  movups  xmm0, xmmword ptr [rax+20h]
0x140008122  movups  xmmword ptr [rbx+0A0h], xmm0
0x140008129  movups  xmm1, xmmword ptr [rax+30h]
0x14000812d  movups  xmmword ptr [rbx+0B0h], xmm1
0x140008134  mov     eax, [rbx+88h]
0x14000813a  test    eax, eax
0x14000813c  jnz     short loc_140008149
0x14000813e  mov     eax, 0E10h
0x140008143  mov     [rbx+88h], eax
0x140008149  cmp     [rbx+0A8h], r15d
0x140008150  jnz     short loc_140008158
0x140008152  mov     [rbx+0A8h], eax
0x140008158  mov     eax, 100h
0x14000815d  mov     [rbx+124h], eax
0x140008163  mov     [rbx+120h], eax
0x140008169  lea     rax, ReceivePPP
0x140008170  mov     [rbx+78h], rax
0x140008174  cmp     dword ptr [rbp+78h], 0Ch
0x140008178  jnz     short loc_1400081C5
0x14000817a  cmp     dword ptr [rbp+7Ch], 0Ch
0x14000817e  jnz     short loc_1400081C5
0x140008180  lea     rax, DetectBroadbandFraming
0x140008187  mov     r15b, 1
0x14000818a  mov     [rbx+78h], rax
0x14000818e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008195  lea     r10, WPP_GLOBAL_Control
0x14000819c  cmp     rcx, r10
0x14000819f  jz      short loc_1400081CC
0x1400081a1  test    dword ptr [rcx+2Ch], 8000h
0x1400081a8  jz      short loc_1400081CC
0x1400081aa  cmp     byte ptr [rcx+29h], 5
0x1400081ae  jb      short loc_1400081CC
0x1400081b0  mov     rcx, [rcx+18h]
0x1400081b4  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x1400081bb  mov     edx, 23h ; '#'
0x1400081c0  call    WPP_SF_
0x1400081c5  lea     r10, WPP_GLOBAL_Control
0x1400081cc  mov     eax, [rbp+7Ch]
0x1400081cf  sub     eax, 0Eh
0x1400081d2  cmp     eax, 1
0x1400081d5  ja      short loc_1400081F8
0x1400081d7  mov     eax, 10000000h
0x1400081dc  mov     [rbx+124h], eax
0x1400081e2  mov     [rbx+120h], eax
0x1400081e8  lea     rax, ReceivePassThrough
0x1400081ef  mov     [rbx+78h], rax
0x1400081f3  bts     dword ptr [rdi+10h], 13h
0x1400081f8  test    r15b, r15b
0x1400081fb  jz      short loc_140008264
0x1400081fd  mov     eax, 200h
0x140008202  or      [rbx+120h], eax
0x140008208  or      [rbx+124h], eax
0x14000820e  mov     r9d, [rbx+124h]
0x140008215  mov     r8d, [rbx+120h]
0x14000821c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008223  cmp     rcx, r10
0x140008226  jz      loc_1400082AC
0x14000822c  test    dword ptr [rcx+2Ch], 8000h
0x140008233  jz      short loc_140008264
0x140008235  cmp     byte ptr [rcx+29h], 5
0x140008239  jb      short loc_140008264
0x14000823b  mov     rcx, [rcx+18h]
0x14000823f  mov     edx, 24h ; '$'
0x140008244  mov     [rsp+68h+var_40], r9d
0x140008249  mov     r9, rbx
0x14000824c  mov     [rsp+68h+var_48], r8d
0x140008251  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140008258  call    WPP_SF_qdd
0x14000825d  lea     r10, WPP_GLOBAL_Control
0x140008264  mov     rcx, cs:WPP_GLOBAL_Control
0x14000826b  cmp     rcx, r10
0x14000826e  jz      short loc_1400082AC
0x140008270  test    dword ptr [rcx+2Ch], 8000h
0x140008277  jz      short loc_1400082AC
0x140008279  cmp     byte ptr [rcx+29h], 5
0x14000827d  jb      short loc_1400082AC
0x14000827f  mov     eax, [rbx+0D0h]
0x140008285  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14000828c  mov     r9d, [rbx+88h]
0x140008293  mov     edx, 25h ; '%'
0x140008298  mov     rcx, [rcx+18h]
0x14000829c  mov     [rsp+68h+var_48], eax
0x1400082a0  call    WPP_SF_dd
0x1400082a5  lea     r10, WPP_GLOBAL_Control
0x1400082ac  mov     eax, [r14]
0x1400082af  test    al, 1
0x1400082b1  jz      short loc_1400082B8
0x1400082b3  bts     dword ptr [rdi+10h], 8
0x1400082b8  mov     eax, [r14]
0x1400082bb  test    al, 4
0x1400082bd  jz      short loc_1400082CA
0x1400082bf  mov     rax, [r14+88h]
0x1400082c6  mov     [rbx+40h], rax
0x1400082ca  mov     rcx, [r14+10h]
0x1400082ce  mov     r9d, [rcx+14h]
0x1400082d2  cmp     r9d, 30h ; '0'
0x1400082d6  jnb     short loc_140008338
0x1400082d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400082df  cmp     rcx, r10
0x1400082e2  jz      loc_1400083FD
0x1400082e8  test    dword ptr [rcx+2Ch], 8000h
0x1400082ef  jz      loc_1400083FD
0x1400082f5  cmp     byte ptr [rcx+29h], 5
0x1400082f9  jb      loc_1400083FD
0x1400082ff  mov     edx, 26h ; '&'
0x140008304  mov     rcx, [rcx+18h]
0x140008308  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14000830f  call    WPP_SF_d
0x140008314  jmp     loc_1400083FD
0x140008319  mov     esi, r15d
0x14000831c  call    AreLinkAndBundleValid
0x140008321  test    al, al
0x140008323  jnz     loc_1400080A0
0x140008329  mov     esi, 0C0000001h
0x14000832e  mov     rbx, [rsp+68h+arg_0]
0x140008333  jmp     loc_140008476
0x140008338  movzx   edx, word ptr [rcx+38h]
0x14000833c  cmp     edx, 70h ; 'p'
0x14000833f  jnb     short loc_140008372
0x140008341  mov     rcx, cs:WPP_GLOBAL_Control
0x140008348  cmp     rcx, r10
0x14000834b  jz      loc_1400083FD
0x140008351  test    dword ptr [rcx+2Ch], 8000h
0x140008358  jz      loc_1400083FD
0x14000835e  cmp     byte ptr [rcx+29h], 5
0x140008362  jb      loc_1400083FD
0x140008368  mov     r9d, edx
0x14000836b  mov     edx, 27h ; '''
0x140008370  jmp     short loc_140008304
0x140008372  test    byte ptr [rcx+20h], 1
0x140008376  jnz     short loc_1400083AA
0x140008378  mov     rcx, cs:WPP_GLOBAL_Control
0x14000837f  cmp     rcx, r10
0x140008382  jz      short loc_1400083FD
0x140008384  test    dword ptr [rcx+2Ch], 8000h
0x14000838b  jz      short loc_1400083FD
0x14000838d  cmp     byte ptr [rcx+29h], 5
0x140008391  jb      short loc_1400083FD
0x140008393  mov     rcx, [rcx+18h]
0x140008397  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14000839e  mov     edx, 28h ; '('
0x1400083a3  call    WPP_SF_
0x1400083a8  jmp     short loc_1400083FD
0x1400083aa  mov     rax, [rcx+40h]
0x1400083ae  add     rax, rcx
0x1400083b1  mov     r9d, [rax+0A0h]
0x1400083b8  cmp     r9d, 8
0x1400083bc  jnb     short loc_1400083E3
0x1400083be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400083c5  cmp     rcx, r10
0x1400083c8  jz      short loc_1400083FD
0x1400083ca  test    dword ptr [rcx+2Ch], 8000h
0x1400083d1  jz      short loc_1400083FD
0x1400083d3  cmp     byte ptr [rcx+29h], 5
0x1400083d7  jb      short loc_1400083FD
0x1400083d9  mov     edx, 29h ; ')'
0x1400083de  jmp     loc_140008304
0x1400083e3  mov     ecx, [rax+0A4h]
0x1400083e9  cmp     dword ptr [rcx+rax+38h], 53415252h
0x1400083f1  jnz     short loc_1400083FD
0x1400083f3  mov     eax, [rcx+rax+3Ch]
0x1400083f7  mov     [rdi+6FCh], eax
0x1400083fd  mov     dword ptr [rdi+44h], 100h
0x140008404  mov     rcx, rdi
0x140008407  mov     dword ptr [rdi+48h], 100h
0x14000840e  call    UpdateBundleInfo
0x140008413  or      ebp, 0FFFFFFFFh
0x140008416  add     [rdi+18h], ebp
0x140008419  jnz     short loc_140008425
0x14000841b  mov     rcx, rdi; Entry
0x14000841e  call    DoDerefBundleCBWork
0x140008423  jmp     short loc_14000843A
0x140008425  mov     dl, [rdi+6F0h]; NewIrql
0x14000842b  mov     rcx, r13; SpinLock
0x14000842e  call    cs:__imp_KeReleaseSpinLock
0x140008435  nop     dword ptr [rax+rax+00h]
0x14000843a  mov     rcx, r12; SpinLock
0x14000843d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008444  nop     dword ptr [rax+rax+00h]
0x140008449  mov     [rbx+2E8h], al
0x14000844f  add     [rbx+1Ch], ebp
0x140008452  jnz     short loc_14000845E
0x140008454  mov     rcx, rbx; Entry
0x140008457  call    DoDerefLinkCBWork
0x14000845c  jmp     short loc_14000846F
0x14000845e  mov     dl, al; NewIrql
0x140008460  mov     rcx, r12; SpinLock
0x140008463  call    cs:__imp_KeReleaseSpinLock
0x14000846a  nop     dword ptr [rax+rax+00h]
0x14000846f  lea     r12, WPP_GLOBAL_Control
0x140008476  mov     rdx, [rbx+38h]; NdisVcHandle
0x14000847a  mov     r8, r14; CallParameters
0x14000847d  mov     ecx, esi; Status
0x14000847f  call    cs:__imp_NdisClIncomingCallComplete
0x140008486  nop     dword ptr [rax+rax+00h]
0x14000848b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008492  cmp     rcx, r12
0x140008495  jz      short loc_1400084BB
0x140008497  test    dword ptr [rcx+2Ch], 8000h
0x14000849e  jz      short loc_1400084BB
0x1400084a0  cmp     byte ptr [rcx+29h], 5
0x1400084a4  jb      short loc_1400084BB
0x1400084a6  mov     rcx, [rcx+18h]
0x1400084aa  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x1400084b1  mov     edx, 2Ah ; '*'
0x1400084b6  call    WPP_SF_
0x1400084bb  mov     rbx, [rsp+68h+arg_8]
0x1400084c0  add     rsp, 30h
0x1400084c4  pop     r15
0x1400084c6  pop     r14
0x1400084c8  pop     r13
0x1400084ca  pop     r12
0x1400084cc  pop     rdi
0x1400084cd  pop     rsi
0x1400084ce  pop     rbp
  ... truncated ...
```

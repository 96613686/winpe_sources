# WFDDeviceHandleReceivedGONResponse(_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_RESPONSE_PARAMETERS *)

- ea: `0x140084b5c`
- end: `0x1400860fc`
- name: `?WFDDeviceHandleReceivedGONResponse@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_RESPONSE_PARAMETERS@@@Z`
- size: `5536`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_GO_NEGOTIATION_RESPONSE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007df60`

## callees

- `0x14000170c`
- `0x14000d21c`
- `0x14000d2b0`
- `0x140020dc0`
- `0x140020f20`
- `0x14002f44c`
- `0x140030b7c`
- `0x140031038`
- `0x14003b04c`
- `0x14003da34`
- `0x14007b8bc`
- `0x140080a84`
- `0x140080bb4`
- `0x140080dd0`
- `0x140080dfc`
- `0x140080e3c`
- `0x140080f6c`
- `0x140084b5c`
- `0x14008aef8`
- `0x14008bfb0`
- `0x14008c694`
- `0x14008c788`
- `0x14008c88c`
- `0x14008d3c0`
- `0x14008d978`
- `0x14008de3c`
- `0x14008dfa8`
- `0x14008edc0`
- `0x140098fac`
- `0x14009bbb0`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140084c31`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008594b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140084c31`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008594b`
- `ntoskrnl!ExAllocatePool2` at `0x140085963`
- `ntoskrnl!ExAllocatePool2` at `0x140085963`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400857ff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140085ff8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086038`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400857ff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140085ff8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086038`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085ab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086009`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086049`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085ab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086009`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086049`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085ba9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085d13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085d7e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085ba9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085d13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085d7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140084fa7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140085c29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140084fa7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140085c29`
- `NDIS!NdisReleaseRWLock` at `0x1400857d4`
- `NDIS!NdisReleaseRWLock` at `0x140085ad2`
- `NDIS!NdisReleaseRWLock` at `0x1400857d4`
- `NDIS!NdisReleaseRWLock` at `0x140085ad2`
- `NDIS!NdisAcquireRWLockRead` at `0x140085779`
- `NDIS!NdisAcquireRWLockRead` at `0x140085779`

## pseudocode

```c
void __fastcall WFDDeviceHandleReceivedGONResponse(
        struct _WFD_ROLE *a1,
        unsigned int a2,
        struct _DOT11_RECEIVED_GO_NEGOTIATION_RESPONSE_PARAMETERS *a3)
{
  struct _WFD_PEER_DEVICE *v3; // r15
  struct _WFD_ROLE *v6; // rdx
  unsigned int v7; // r12d
  __int64 v8; // rbx
  struct _WFD_DEVICE_ROLE *pRoleExt; // rax
  char *v10; // rax
  int v11; // r8d
  char *v12; // r12
  unsigned int PeerByMAC; // edi
  unsigned __int8 v14; // bl
  char *v15; // r15
  unsigned __int8 *v16; // rbx
  char *v17; // rdi
  const char *v18; // rax
  int v19; // r8d
  int v20; // r9d
  bool v21; // zf
  const char *v22; // rdi
  const char *v23; // rbx
  const char *v24; // r11
  const char *v25; // r10
  const char *v26; // r8
  const char *v27; // rdx
  const char *v28; // rcx
  unsigned __int8 *v29; // rbx
  _DEVICE_OBJECT *AttachedDevice; // rcx
  struct _WFD_DEVICE_ROLE *v31; // rdi
  unsigned __int8 v32; // r9
  unsigned __int8 *v33; // r13
  __int64 v34; // r8
  unsigned __int8 *v35; // r8
  char *v36; // r9
  __int64 v37; // r8
  __int64 v38; // r9
  int v39; // edx
  int v40; // r8d
  PDEVICE_OBJECT v41; // rcx
  __int64 v42; // rdx
  bool v43; // cl
  __int64 v44; // r9
  __int64 v45; // rdx
  _DEVICE_OBJECT *v46; // rcx
  bool v47; // bl
  unsigned __int8 v48; // al
  char v49; // r12
  PDEVICE_OBJECT v50; // rcx
  __int64 v51; // rdx
  unsigned __int8 v52; // cl
  const char *v53; // r8
  unsigned __int8 *v54; // rdi
  const char *v55; // r9
  const char *v56; // rax
  unsigned __int64 v57; // rcx
  void *v58; // rdx
  size_t v59; // r13
  _OWORD *v60; // r14
  struct _WFD_ROLE *v61; // rdi
  char *v62; // rsi
  char v63; // bl
  PDEVICE_OBJECT v64; // rcx
  __int64 v65; // rdx
  PNDIS_RW_LOCK_EX *v66; // r12
  unsigned int v67; // ebx
  unsigned int v68; // eax
  unsigned int v69; // r12d
  unsigned int v70; // ecx
  unsigned int v71; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  _DWORD *Pool2; // rax
  size_t v74; // r8
  char *v75; // rbx
  unsigned __int8 *v76; // rdx
  char *v77; // rbx
  _DWORD *v78; // rcx
  unsigned __int8 *v79; // r14
  const char *v80; // r11
  const char *v81; // rcx
  struct _WFD_DEVICE_ROLE *v82; // r13
  PKSPIN_LOCK v83; // r14
  int v84; // eax
  KIRQL v85; // al
  unsigned int v86; // edx
  char v87; // al
  __int64 v88; // rsi
  char *v89; // rbx
  char v90; // r14
  __int16 v91; // ax
  struct _WFD_ROLE *v92; // rsi
  char v93; // [rsp+90h] [rbp-80h]
  unsigned __int8 v94; // [rsp+91h] [rbp-7Fh] BYREF
  char v95; // [rsp+92h] [rbp-7Eh]
  char v96; // [rsp+93h] [rbp-7Dh]
  char v97; // [rsp+94h] [rbp-7Ch]
  PKSPIN_LOCK SpinLock; // [rsp+98h] [rbp-78h]
  unsigned int v99; // [rsp+A0h] [rbp-70h]
  int Size[3]; // [rsp+A4h] [rbp-6Ch] BYREF
  char v101; // [rsp+B0h] [rbp-60h]
  unsigned __int8 *v102; // [rsp+B8h] [rbp-58h]
  struct _LOCK_STATE_EX LockState; // [rsp+C0h] [rbp-50h] BYREF
  void *v104; // [rsp+C8h] [rbp-48h]
  char *v105; // [rsp+D0h] [rbp-40h]
  unsigned int v106; // [rsp+D8h] [rbp-38h] BYREF
  struct _DOT11_RECEIVED_GO_NEGOTIATION_RESPONSE_PARAMETERS *v107; // [rsp+E0h] [rbp-30h]
  unsigned int v108; // [rsp+E8h] [rbp-28h]
  struct _WFD_PEER_DEVICE *v109; // [rsp+F0h] [rbp-20h] BYREF
  void *Src; // [rsp+F8h] [rbp-18h]
  struct _WFD_DEVICE_ROLE *v111; // [rsp+100h] [rbp-10h]
  _QWORD v112[2]; // [rsp+110h] [rbp+0h] BYREF
  char *v113; // [rsp+120h] [rbp+10h]
  _DWORD *v114; // [rsp+128h] [rbp+18h]
  void *v115; // [rsp+130h] [rbp+20h]
  _QWORD v116[12]; // [rsp+140h] [rbp+30h] BYREF

  v3 = 0;
  v107 = a3;
  v109 = 0;
  v94 = 0;
  v6 = a1;
  *(_QWORD *)&Size[1] = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    v6 = *(struct _WFD_ROLE **)&Size[1];
  }
  v7 = *((_DWORD *)a3 + 7);
  v8 = *((unsigned int *)a3 + 6);
  if ( (!v7 || (unsigned int)v8 >= 0x20) && v7 + (unsigned int)v8 >= (unsigned int)v8 && v7 + (unsigned int)v8 <= a2 )
  {
    pRoleExt = (struct _WFD_DEVICE_ROLE *)v6->pRoleExt;
    v93 = 5;
    v108 = 0;
    v115 = 0;
    v97 = 0;
    v95 = 0;
    v96 = 0;
    v104 = 0;
    v99 = 0;
    v111 = pRoleExt;
    v10 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
    if ( !v10 )
    {
      v12 = 0;
      PeerByMAC = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 144, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      v14 = 5;
      goto LABEL_11;
    }
    v16 = (unsigned __int8 *)v107 + v8;
    *(_QWORD *)v10 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    v17 = v10 + 16;
    *((_DWORD *)v10 + 2) = 808679286;
    v105 = v10 + 16;
    v102 = v16;
    memset(v10 + 16, 0, 0xBCu);
    if ( !(unsigned __int8)WFDValidateIncomingGONegotiationResponseIEs(v16, v7, v17) )
    {
      PeerByMAC = -1073676267;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 145, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      }
      v12 = v105;
      goto LABEL_288;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      v18 = "Y";
      if ( (v17[184] & 2) == 0 )
        v18 = "N";
      WPP_SF__MAC_DcDDDD_MAC_H_WPSDEVICENAME_hs_MAC__SSID_(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v105,
        (_DWORD)v17 + 63,
        (_DWORD)v107 + 4,
        *((_BYTE *)v107 + 10),
        *v105,
        (unsigned __int8)v17[60] >> 1,
        v17[60] & 1,
        v17[61],
        v17[62],
        (__int64)(v17 + 63),
        *((_WORD *)v105 + 41),
        (__int64)(v17 + 92),
        *((_WORD *)v105 + 64),
        (__int64)v18,
        (__int64)(v17 + 140),
        (__int64)(v17 + 148));
      v17 = v105;
    }
    if ( (unsigned int)dword_1400B1050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400B1050, 0x200000000000LL) )
    {
      Size[0] = (unsigned __int8)*v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1400B1050,
        (unsigned int)byte_1400A76A9,
        v19,
        v20,
        (__int64)Size);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      v21 = *((_DWORD *)v17 + 13) == 0;
      v22 = "Y";
      v23 = "Y";
      v24 = "Y";
      if ( v21 )
        v22 = "N";
      v25 = "Y";
      v26 = "Y";
      if ( !*((_DWORD *)v105 + 12) )
        v23 = "N";
      v27 = "Y";
      if ( !*((_DWORD *)v105 + 11) )
        v24 = "N";
      if ( !*((_DWORD *)v105 + 10) )
        v25 = "N";
      if ( !*((_DWORD *)v105 + 9) )
        v26 = "N";
      v28 = "Y";
      if ( !*((_DWORD *)v105 + 8) )
        v27 = "N";
      if ( !*((_DWORD *)v105 + 7) )
        v28 = "N";
      WPP_SF__MAC_sssssss(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v27,
        (_DWORD)v26,
        (_DWORD)v107 + 4,
        (__int64)v28,
        (__int64)v27,
        (__int64)v26,
        (__int64)v25,
        (__int64)v24,
        (__int64)v23,
        (__int64)v22);
    }
    if ( !v7 || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v29 = v102;
    }
    else
    {
      v29 = v102;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v112[0] = (unsigned __int16)v7;
        v112[1] = v102;
        WPP_SF__HEX_(AttachedDevice, 148, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v112);
      }
    }
    v31 = v111;
    SpinLock = (PKSPIN_LOCK)((char *)v111 + 1192);
    *((_BYTE *)v31 + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v111 + 149);
    v32 = *((_BYTE *)v107 + 10);
    v33 = (unsigned __int8 *)v107 + 4;
    v102 = (unsigned __int8 *)v107 + 4;
    if ( (int)WFDDeviceCheckDuplicateTransmission(
                v31,
                (unsigned __int8 (*)[6])((char *)v107 + 4),
                WfdReceivedPacketTypeGONResponse,
                v32,
                &v94) < 0
      || v94 )
    {
      v94 = 1;
      PeerByMAC = -1073676267;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0 )
      {
        goto LABEL_249;
      }
      v45 = 149;
      v46 = WPP_GLOBAL_Control->AttachedDevice;
      v44 = *((unsigned __int8 *)v107 + 10);
      goto LABEL_248;
    }
    v94 = 0;
    PeerByMAC = WFDDeviceFindPeerByMAC(v31, (unsigned __int8 (*)[6])v33, &v109);
    if ( PeerByMAC )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 150, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v33);
      v3 = v109;
      goto LABEL_249;
    }
    v3 = v109;
    if ( *((_BYTE *)v107 + 10) != *((_BYTE *)v109 + 40) )
    {
      PeerByMAC = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          151,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          *((unsigned __int8 *)v107 + 10),
          *((unsigned __int8 *)v109 + 40));
      goto LABEL_249;
    }
    v108 = *((_DWORD *)v109 + 14);
    if ( !(unsigned __int8)WFDPeerDeviceSetState(v109, 21) )
    {
      PeerByMAC = -1073741436;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          152,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          *((unsigned int *)v3 + 9));
      }
      goto LABEL_249;
    }
    if ( !(unsigned int)WFDPeerDeviceCancelTimer(v3) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer)
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF__MAC_q(WPP_GLOBAL_Control->AttachedDevice, 153, v34, (char *)v3 + 24, v3);
      }
      goto LABEL_249;
    }
    v35 = (unsigned __int8 *)v3 + 320;
    v36 = v105;
    v115 = (void *)*((_QWORD *)v3 + 6);
    v97 = 1;
    v96 = 1;
    *((_BYTE *)v3 + 374) = *v105;
    *((_BYTE *)v3 + 380) |= 2u;
    v113 = (char *)v3 + 320;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        154,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        *((unsigned __int8 *)v3 + 374));
      v36 = v105;
      v35 = (unsigned __int8 *)v3 + 320;
    }
    if ( *((_BYTE *)v3 + 374) )
    {
      if ( *((_BYTE *)v3 + 374) == 1 )
      {
        if ( (unsigned __int8)WFDPeerDeviceSetState(v3, 22) )
        {
          WFDPeerDeviceQueueTimer(v3, 0x1D4C0u, 0x2EE0u);
          v97 = 0;
          v94 = 1;
          v95 = 1;
          goto LABEL_249;
        }
        PeerByMAC = -1073741436;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer)
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        }
        v95 = 1;
        goto LABEL_97;
      }
      v96 = 0;
      PeerByMAC = -1073741811;
    }
    v95 = 1;
    if ( PeerByMAC )
    {
LABEL_97:
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_249;
      v42 = 161;
      goto LABEL_90;
    }
    WFDDeviceUpdateGroupCaps(v35 + 44, (struct _WFD_GROUP_CAPABILITY *)(v36 + 28));
    *((_BYTE *)v3 + 380) = *((_BYTE *)v3 + 380) & 0xFE | ((*(_BYTE *)(v38 + 184) & 2) != 0);
    if ( (*(_BYTE *)(v38 + 184) & 2) != 0 )
    {
      *(_OWORD *)v37 = *(_OWORD *)(v38 + 140);
      *(_OWORD *)(v37 + 16) = *(_OWORD *)(v38 + 156);
      *(_OWORD *)(v37 + 28) = *(_OWORD *)(v38 + 168);
    }
    *(_DWORD *)((char *)v3 + 365) = *(_DWORD *)(v38 + 63);
    *(_WORD *)((char *)v3 + 369) = *(_WORD *)(v38 + 67);
    *(_WORD *)((char *)v3 + 371) = *(_WORD *)(v38 + 61);
    *((_BYTE *)v3 + 380) ^= (*((_BYTE *)v3 + 380) ^ (4 * *(_BYTE *)(v38 + 184))) & 4;
    if ( (*(_BYTE *)(v38 + 184) & 1) != 0 )
    {
      *(_DWORD *)((char *)v3 + 375) = *(_DWORD *)(v38 + 132);
      *((_BYTE *)v3 + 379) = *(_BYTE *)(v38 + 136);
    }
    *((_BYTE *)v3 + 373) = *(_BYTE *)(v38 + 60);
    PeerByMAC = WFDDeviceGetChannelListBlob(v7, v29, (unsigned int *)(v37 + 108), (unsigned __int8 **)(v37 + 112));
    if ( PeerByMAC )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v42 = 156;
LABEL_90:
        WPP_SF_(v41->AttachedDevice, v42, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      }
LABEL_249:
      v83 = SpinLock;
      goto LABEL_250;
    }
    v43 = (*((_BYTE *)v3 + 253) & 1) == 0;
    if ( (*((_BYTE *)v3 + 373) & 1) != v43 )
    {
      PeerByMAC = -1073676267;
      v93 = 4;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_249;
      v44 = v43;
      v45 = 157;
      v46 = WPP_GLOBAL_Control->AttachedDevice;
LABEL_248:
      WPP_SF_d(v46, v45, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v44);
      goto LABEL_249;
    }
    v47 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    v48 = *((_BYTE *)v3 + 373) >> 1;
    if ( v48 <= 0xFu )
    {
      v49 = 0;
      v52 = *((_BYTE *)v3 + 253) >> 1;
      v93 = 0;
      if ( v48 < v52 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        }
        v47 = 1;
        goto LABEL_124;
      }
      if ( v48 != v52 )
        goto LABEL_124;
      if ( v48 != 15 )
      {
        v47 = (*((_BYTE *)v3 + 373) & 1) == 0;
        goto LABEL_124;
      }
      v49 = 9;
      v93 = 9;
      v50 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          v51 = 112;
          goto LABEL_110;
        }
LABEL_124:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          v53 = "Y";
          if ( !v47 )
            v53 = "N";
          WPP_SF_DDDDDs(
            WPP_GLOBAL_Control->AttachedDevice,
            *((_BYTE *)v3 + 373) & 1,
            (_DWORD)v53,
            *((unsigned __int8 *)v3 + 253) >> 1,
            *((_BYTE *)v3 + 253) & 1,
            *((_BYTE *)v3 + 373) >> 1,
            *((_BYTE *)v3 + 373) & 1,
            v49,
            (__int64)v53);
        }
      }
    }
    else
    {
      v49 = 4;
      v93 = 4;
      v50 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          v51 = 110;
LABEL_110:
          WPP_SF_(v50->AttachedDevice, v51, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
          goto LABEL_124;
        }
        goto LABEL_124;
      }
    }
    if ( v49 )
    {
      PeerByMAC = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_249;
    }
    *((_BYTE *)v3 + 192) = v47;
    if ( v47 )
      goto LABEL_148;
    LOBYTE(v40) = *((_BYTE *)v3 + 364) & 2;
    LOBYTE(v39) = *((_BYTE *)v3 + 244) & 2;
    if ( ((_BYTE)v39 != 0) != ((_BYTE)v40 != 0) )
    {
      v93 = 2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v54 = v102;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          v55 = "PERSISTENT";
          v56 = "PERSISTENT";
          if ( !(_BYTE)v40 )
            v56 = "TRANSIENT";
          if ( !(_BYTE)v39 )
            v55 = "TRANSIENT";
          WPP_SF_ss_MAC_(WPP_GLOBAL_Control->AttachedDevice, v39, v40, (_DWORD)v55, (__int64)v56, (__int64)v102);
        }
LABEL_149:
        if ( v47 )
        {
          v57 = (unsigned __int64)v3 + 200;
          v113 = (char *)v3 + 200;
        }
        else
        {
          v57 = (unsigned __int64)v3 + 320;
        }
        v21 = *((_BYTE *)v3 + 440) == 0;
        v58 = (void *)*((_QWORD *)v3 + 37);
        v59 = *((unsigned int *)v3 + 76);
        Src = v58;
        if ( v21 )
          v114 = 0;
        else
          v114 = (_DWORD *)((char *)v3 + 441);
        v106 = 0;
        LockState.OldIrql = 0;
        v60 = (_OWORD *)(v57 & -(__int64)v47);
        v112[0] = *((_QWORD *)v107 + 2);
        v101 = *((_BYTE *)v107 + 10);
        *(_WORD *)&LockState.LockState = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
          v58 = Src;
        }
        if ( !v54 )
          goto LABEL_160;
        if ( v58 )
        {
          if ( !(_DWORD)v59 )
            goto LABEL_160;
        }
        else if ( (_DWORD)v59 )
        {
LABEL_160:
          PeerByMAC = -1073741811;
          goto LABEL_161;
        }
        v61 = *(struct _WFD_ROLE **)&Size[1];
        v62 = 0;
        v63 = 0;
        NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)&Size[1] + 32LL), &LockState, 0);
        PeerByMAC = WFDRoleGetCachedFrameIEs(v61, MANAGEMENT_FRAME_TYPE_GO_NEGOTIATION_CONFIRMATION, &v106, 0);
        if ( PeerByMAC )
        {
          v64 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
LABEL_168:
            v66 = *(PNDIS_RW_LOCK_EX **)&Size[1];
            goto LABEL_169;
          }
          v65 = 72;
LABEL_167:
          WPP_SF_(v64->AttachedDevice, v65, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
          goto LABEL_168;
        }
        v68 = v59 + 96;
        if ( (unsigned int)v59 >= 0xFFFFFFA0 )
        {
          PeerByMAC = -1073741675;
          v64 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_168;
          v65 = 73;
          goto LABEL_167;
        }
        v69 = v106;
        v70 = v106 + v68;
        Size[0] = v106 + v68;
        if ( v106 + v68 < v68 )
        {
          PeerByMAC = -1073741675;
          v64 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_168;
          v65 = 74;
          goto LABEL_167;
        }
        v71 = v70 + 16;
        if ( v70 >= 0xFFFFFFF0 )
        {
LABEL_201:
          PeerByMAC = -1073741670;
          v64 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_168;
          v65 = 76;
          goto LABEL_167;
        }
        if ( v71 > 0x40 )
        {
          if ( v71 > 0x100 )
          {
            if ( v71 > 0x400 )
            {
              if ( v71 > 0x800 )
              {
                p_WaitListHead = 0;
                Pool2 = (_DWORD *)ExAllocatePool2(64, v71, 808679286);
LABEL_200:
                if ( Pool2 )
                {
                  v74 = (unsigned int)Size[0];
                  v62 = (char *)(Pool2 + 4);
                  v75 = v113;
                  *(_QWORD *)Pool2 = p_WaitListHead;
                  Pool2[2] = 808679286;
                  PeerByMAC = 0;
                  memset(Pool2 + 4, 0, v74);
                  v76 = v102;
                  *(_DWORD *)v62 = 6292096;
                  *((_DWORD *)v62 + 1) = *(_DWORD *)v76;
                  *((_WORD *)v62 + 4) = *((_WORD *)v76 + 2);
                  v62[10] = v101;
                  *((_QWORD *)v62 + 2) = v112[0];
                  *((_DWORD *)v62 + 6) = 1000;
                  v62[28] = 0;
                  v77 = v75 + 44;
                  if ( v77 )
                    v62[29] = *v77;
                  if ( v60 )
                  {
                    *((_OWORD *)v62 + 2) = *v60;
                    *((_OWORD *)v62 + 3) = v60[1];
                    *(_OWORD *)(v62 + 60) = *(_OWORD *)((char *)v60 + 28);
                    v62[76] = 1;
                  }
                  v78 = v114;
                  if ( v114 )
                  {
                    *((_DWORD *)v62 + 22) = *v114;
                    v62[92] = *((_BYTE *)v78 + 4);
                    v62[93] = 1;
                  }
                  *((_DWORD *)v62 + 20) = 96;
                  *((_DWORD *)v62 + 21) = v69 + v59;
                  v79 = (unsigned __int8 *)(v62 + 96);
                  if ( Src )
                  {
                    memmove(v62 + 96, Src, v59);
                    v79 += v59;
                  }
                  v21 = v69 == 0;
                  v66 = *(PNDIS_RW_LOCK_EX **)&Size[1];
                  if ( v21
                    || (PeerByMAC = WFDRoleGetCachedFrameIEs(
                                      *(struct _WFD_ROLE **)&Size[1],
                                      MANAGEMENT_FRAME_TYPE_GO_NEGOTIATION_CONFIRMATION,
                                      &v106,
                                      v79)) == 0 )
                  {
                    NdisReleaseRWLock(v66[4], &LockState);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                    {
                      v80 = "Y";
                      v81 = "Y";
                      if ( !Src )
                        v81 = "N";
                      if ( !v62[76] )
                        v80 = "N";
                      WPP_SF__MAC_DqDcCs_MAC__SSID_DDs(
                        WPP_GLOBAL_Control->AttachedDevice,
                        (_DWORD)v62 + 40,
                        (unsigned __int8)v62[10],
                        (_DWORD)v62 + 4,
                        v62[10],
                        *((_QWORD *)v62 + 2),
                        *((_DWORD *)v62 + 6),
                        v62[28],
                        v62[29],
                        (__int64)v80,
                        (__int64)(v62 + 32),
                        (__int64)(v62 + 40),
                        *((_DWORD *)v62 + 20),
                        *((_DWORD *)v62 + 21),
                        (__int64)v81);
                    }
                    v67 = Size[0];
LABEL_174:
                    v99 = v67;
                    v104 = v62;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        79,
                        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                        PeerByMAC);
                    if ( !PeerByMAC )
                    {
                      if ( (unsigned __int8)WFDPeerDeviceSetState(v3, 29) )
                      {
                        v82 = v111;
                        v83 = SpinLock;
                        KeReleaseSpinLock(SpinLock, *((_BYTE *)v111 + 1200));
                        v84 = NwifiSetDirectOidRequestAsync(*((struct _ADAPT **)*v66 + 2), 0xE05010Cu, v62, v67);
                        if ( v84 == 1076035585 )
                          v84 = 0;
                        Size[0] = v84;
                        MapPendingDirectOidStatus(Size);
                        PeerByMAC = Size[0];
                        if ( Size[0] )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              164,
                              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                              (unsigned int)Size[0]);
                          v104 = v62;
                          v99 = v67;
LABEL_251:
                          v12 = v105;
                          v87 = v93;
                          if ( !v93 )
                            v87 = 5;
                          v14 = v87;
                          v93 = v87;
LABEL_11:
                          if ( !PeerByMAC )
                            PeerByMAC = -1073741823;
                          if ( v96 )
                          {
                            memset(v116, 0, sizeof(v116));
                            if ( v3 && *((_BYTE *)v3 + 440) )
                              v15 = (char *)v3 + 441;
                            else
                              v15 = 0;
                            if ( v14 )
                            {
                              LOBYTE(v106) = 0;
                              v88 = *((_QWORD *)v107 + 2);
                              v89 = (char *)v107 + 4;
                              v90 = *((_BYTE *)v107 + 10);
                              *(_WORD *)((char *)&v106 + 1) = 0;
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                WPP_SF_(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  71,
                                  WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                              if ( v89 )
                              {
                                memset(v116, 0, sizeof(v116));
                                HIDWORD(v116[0]) = *(_DWORD *)v89;
                                v91 = *((_WORD *)v89 + 2);
                                v14 = v93;
                                BYTE4(v116[3]) = v93;
                                LODWORD(v116[0]) = 6292096;
                                LOWORD(v116[1]) = v91;
                                BYTE2(v116[1]) = v90;
                                v116[2] = v88;
                                LODWORD(v116[3]) = 1000;
                                if ( v15 )
                                {
                                  LODWORD(v116[11]) = *(_DWORD *)v15;
                                  BYTE4(v116[11]) = v15[4];
                                  BYTE5(v116[11]) = 1;
                                }
                                v116[10] = 96;
                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                                {
                                  WPP_SF__MAC_DqDcCs_MAC__SSID_DDs(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    (unsigned int)&v116[4],
                                    0,
                                    (unsigned int)v116 + 4,
                                    v90,
                                    v88,
                                    232,
                                    v93,
                                    0,
                                    (__int64)"N",
                                    (__int64)&v116[4],
                                    (__int64)&v116[5],
                                    96,
                                    0,
                                    (__int64)"N");
                                }
                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                  WPP_SF_d(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    79,
                                    WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                                    0);
                                v92 = *(struct _WFD_ROLE **)&Size[1];
                                Size[0] = NwifiSetDirectOidRequestAsync(
                                            *(struct _ADAPT **)(**(_QWORD **)&Size[1] + 16LL),
                                            0xE05010Cu,
                                            v116,
                                            v99);
                                MapPendingDirectOidStatus(Size);
                                if ( Size[0]
                                  && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  && BYTE1(WPP_GLOBAL_Control->Timer)
                                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                                {
                                  WPP_SF_(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    167,
                                    WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                                }
                                goto LABEL_278;
                              }
                              v14 = v93;
                            }
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && BYTE1(WPP_GLOBAL_Control->Timer)
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                            {
                              WPP_SF_(
                                WPP_GLOBAL_Control->AttachedDevice,
                                168,
                                WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                            }
                          }
                          v92 = *(struct _WFD_ROLE **)&Size[1];
LABEL_278:
                          if ( v95 )
                            WFDDeviceGONegotiationSendUpcallFailure(v92, v115, v11, PeerByMAC, v14);
                          goto LABEL_281;
                        }
                        v85 = KeAcquireSpinLockRaiseToDpc(v83);
                        v86 = v108;
                        *((_BYTE *)v82 + 1200) = v85;
                        if ( (unsigned int)WFDDeviceFindPeerByID(v82, v86, &v109) )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                          {
                            WPP_SF_(
                              WPP_GLOBAL_Control->AttachedDevice,
                              165,
                              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                          }
                          v3 = v109;
                          v95 = 1;
                        }
                        else
                        {
                          v3 = v109;
                          if ( (unsigned __int8)WFDPeerDeviceSetState(v109, 30) )
                          {
                            WFDPeerDeviceQueueTimer(v3, 0x3E8u, 0x64u);
                            KeReleaseSpinLock(v83, *((_BYTE *)v82 + 1200));
                            v12 = v105;
LABEL_284:
                            if ( v62 )
                            {
                              if ( *((_QWORD *)v62 - 2) )
                                ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v62 - 2), v62 - 16);
                              else
                                ExFreePoolWithTag(v62 - 16, *((_DWORD *)v62 - 2));
                            }
LABEL_288:
                            if ( v12 )
                            {
                              if ( *((_QWORD *)v12 - 2) )
                                ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 16);
                              else
                                ExFreePoolWithTag(v12 - 16, *((_DWORD *)v12 - 2));
                            }
                            goto LABEL_296;
                          }
                          PeerByMAC = -1073741436;
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              166,
                              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                              *((unsigned int *)v3 + 9));
                          }
                        }
                        v104 = v62;
                        v99 = v67;
LABEL_250:
                        KeReleaseSpinLock(v83, *((_BYTE *)v83 + 8));
                        if ( v94 )
                        {
                          v12 = v105;
LABEL_281:
                          if ( v97 )
                            WFDDeviceCleanupPeerByID(v111, v108);
                          v62 = (char *)v104;
                          goto LABEL_284;
                        }
                        goto LABEL_251;
                      }
                      PeerByMAC = -1073741436;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          163,
                          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                          *((unsigned int *)v3 + 9));
                      }
                      v104 = v62;
                      v99 = v67;
                      goto LABEL_249;
                    }
LABEL_161:
                    v41 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_249;
                    v42 = 162;
                    goto LABEL_90;
                  }
                  v63 = 1;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_169:
                  NdisReleaseRWLock(v66[4], &LockState);
                  if ( v62 && v63 )
                  {
                    if ( *((_QWORD *)v62 - 2) )
                      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v62 - 2), v62 - 16);
                    else
                      ExFreePoolWithTag(v62 - 16, *((_DWORD *)v62 - 2));
                  }
                  v62 = (char *)v104;
                  v67 = (unsigned int)v104;
                  goto LABEL_174;
                }
                goto LABEL_201;
              }
              p_WaitListHead = &stru_1400B31C0;
            }
            else
            {
              p_WaitListHead = &Lookaside;
            }
          }
          else
          {
            p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
          }
        }
        else
        {
          p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
        }
        Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
        goto LABEL_200;
      }
LABEL_148:
      v54 = v102;
      goto LABEL_149;
    }
    if ( (*((_BYTE *)v3 + 380) & 5) == 5 )
      goto LABEL_148;
    v93 = 4;
    PeerByMAC = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_249;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    goto LABEL_97;
  }
  PeerByMAC = -1073676267;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer)
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
  {
    WPP_SF_DDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      143,
      WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
      (unsigned int)v8,
      v7,
      v7 + v8,
      a2);
  }
LABEL_296:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 169, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, PeerByMAC);
}

```

## disassembly

```asm
0x140084b5c  mov     [rsp-8+arg_8], rbx
0x140084b61  push    rbp
0x140084b62  push    rsi
0x140084b63  push    rdi
0x140084b64  push    r12
0x140084b66  push    r13
0x140084b68  push    r14
0x140084b6a  push    r15
0x140084b6c  lea     rbp, [rsp-0A0h]
0x140084b74  sub     rsp, 1B0h
0x140084b7b  mov     rax, cs:__security_cookie
0x140084b82  xor     rax, rsp
0x140084b85  mov     [rbp+0D0h+var_40], rax
0x140084b8c  xor     r15d, r15d
0x140084b8f  mov     [rbp+0D0h+var_100], r8
0x140084b93  mov     esi, edx
0x140084b95  mov     [rbp+0D0h+var_F0], r15
0x140084b99  mov     [rbp+0D0h+var_14F], r15b
0x140084b9d  mov     rdi, r8
0x140084ba0  mov     rdx, rcx
0x140084ba3  mov     qword ptr [rbp+0D0h+Size+4], rcx
0x140084ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x140084bae  lea     rax, WPP_GLOBAL_Control
0x140084bb5  cmp     rcx, rax
0x140084bb8  jz      short loc_140084BD3
0x140084bba  mov     rcx, [rcx+18h]
0x140084bbe  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140084bc5  mov     edx, 8Eh
0x140084bca  call    WPP_SF_
0x140084bcf  mov     rdx, qword ptr [rbp+0D0h+Size+4]
0x140084bd3  mov     r12d, [rdi+1Ch]
0x140084bd7  mov     ebx, [rdi+18h]
0x140084bda  test    r12d, r12d
0x140084bdd  jz      short loc_140084BE8
0x140084bdf  cmp     ebx, 20h ; ' '
0x140084be2  jb      loc_140086057
0x140084be8  lea     eax, [r12+rbx]
0x140084bec  cmp     eax, ebx
0x140084bee  jb      loc_140086057
0x140084bf4  cmp     eax, esi
0x140084bf6  ja      loc_140086057
0x140084bfc  mov     rax, [rdx+0B8h]
0x140084c03  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140084c0a  mov     rcx, rdi; Lookaside
0x140084c0d  mov     [rbp+0D0h+var_150], 5
0x140084c11  mov     [rbp+0D0h+var_F8], r15d
0x140084c15  mov     [rbp+0D0h+var_B0], r15
0x140084c19  mov     [rbp+0D0h+var_14C], r15b
0x140084c1d  mov     [rbp+0D0h+var_14E], r15b
0x140084c21  mov     [rbp+0D0h+var_14D], r15b
0x140084c25  mov     [rbp+0D0h+var_118], r15
0x140084c29  mov     [rbp+0D0h+var_140], r15d
0x140084c2d  mov     [rbp+0D0h+var_E0], rax
0x140084c31  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140084c38  nop     dword ptr [rax+rax+00h]
0x140084c3d  mov     r14d, 200000h
0x140084c43  mov     r13d, 1
0x140084c49  test    rax, rax
0x140084c4c  jnz     short loc_140084CCB
0x140084c4e  xor     r12d, r12d
0x140084c51  mov     edi, 0C000009Ah
0x140084c56  mov     rcx, cs:WPP_GLOBAL_Control
0x140084c5d  lea     rbx, WPP_GLOBAL_Control
0x140084c64  cmp     rcx, rbx
0x140084c67  jz      short loc_140084C7E
0x140084c69  mov     rcx, [rcx+18h]
0x140084c6d  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140084c74  mov     edx, 90h
0x140084c79  call    WPP_SF_
0x140084c7e  mov     bl, [rbp+0D0h+var_150]
0x140084c81  mov     esi, 0C0000001h
0x140084c86  test    edi, edi
0x140084c88  cmovz   edi, esi
0x140084c8b  cmp     [rbp+0D0h+var_14D], 0
0x140084c8f  jz      loc_140085FA8
0x140084c95  xor     edx, edx; Val
0x140084c97  mov     byte ptr [rbp+0D0h+var_A0], 0
0x140084c9b  lea     rcx, [rbp+0D0h+var_A0+1]; void *
0x140084c9f  lea     r8d, [rdx+5Fh]; Size
0x140084ca3  call    memset
0x140084ca8  test    r15, r15
0x140084cab  jz      loc_140085DB6
0x140084cb1  cmp     byte ptr [r15+1B8h], 0
0x140084cb9  jz      loc_140085DB6
0x140084cbf  add     r15, 1B9h
0x140084cc6  jmp     loc_140085DB9
0x140084ccb  add     rbx, [rbp+0D0h+var_100]
0x140084ccf  xor     edx, edx; Val
0x140084cd1  mov     [rax], rdi
0x140084cd4  mov     r8d, 0BCh; Size
0x140084cda  lea     rdi, [rax+10h]
0x140084cde  mov     dword ptr [rax+8], 30337776h
0x140084ce5  mov     rcx, rdi; void *
0x140084ce8  mov     [rbp+0D0h+var_110], rdi
0x140084cec  mov     [rbp+0D0h+var_128], rbx
0x140084cf0  call    memset
0x140084cf5  mov     r8, rdi; void *
0x140084cf8  mov     edx, r12d; unsigned int
0x140084cfb  mov     rcx, rbx; unsigned __int8 *
0x140084cfe  call    WFDValidateIncomingGONegotiationResponseIEs
0x140084d03  test    al, al
0x140084d05  jnz     short loc_140084D4C
0x140084d07  mov     edi, 0C0010015h
0x140084d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140084d13  lea     r14, WPP_GLOBAL_Control
0x140084d1a  cmp     rcx, r14
0x140084d1d  jz      short loc_140084D43
0x140084d1f  cmp     byte ptr [rcx+29h], 2
0x140084d23  jb      short loc_140084D43
0x140084d25  test    dword ptr [rcx+2Ch], 200000h
0x140084d2c  jz      short loc_140084D43
0x140084d2e  mov     rcx, [rcx+18h]
0x140084d32  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140084d39  mov     edx, 91h
0x140084d3e  call    WPP_SF_
0x140084d43  mov     r12, [rbp+0D0h+var_110]
0x140084d47  jmp     loc_14008601C
0x140084d4c  mov     r13, cs:WPP_GLOBAL_Control
0x140084d53  lea     rbx, WPP_GLOBAL_Control
0x140084d5a  cmp     r13, rbx
0x140084d5d  jz      loc_140084E35
0x140084d63  cmp     byte ptr [r13+29h], 4
0x140084d68  jb      loc_140084E35
0x140084d6e  test    [r13+2Ch], r14d
0x140084d72  jz      loc_140084E35
0x140084d78  movzx   r14d, byte ptr [rdi+3Ch]
0x140084d7d  lea     rsi, [rdi+8Ch]
0x140084d84  test    byte ptr [rdi+0B8h], 2
0x140084d8b  lea     r8, [rdi+3Fh]
0x140084d8f  movzx   r10d, byte ptr [rdi+3Eh]
0x140084d94  lea     rdx, [rsi+8]
0x140084d98  movzx   r11d, byte ptr [rdi+3Dh]
0x140084d9d  lea     rcx, aN; "N"
0x140084da4  mov     r9, [rbp+0D0h+var_100]
0x140084da8  lea     rax, aY; "Y"
0x140084daf  mov     [rsp+1E0h+var_160], rdx
0x140084db7  cmovz   rax, rcx
0x140084dbb  mov     rdx, [rbp+0D0h+var_110]
0x140084dbf  lea     rcx, [rdi+5Ch]
0x140084dc3  mov     [rsp+1E0h+var_168], rsi
0x140084dc8  mov     ebx, r14d
0x140084dcb  movzx   edi, byte ptr [r9+0Ah]
0x140084dd0  and     ebx, 1
0x140084dd3  mov     [rsp+1E0h+var_170], rax
0x140084dd8  add     r9, 4
0x140084ddc  movzx   eax, word ptr [rdx+80h]
0x140084de3  mov     word ptr [rsp+1E0h+var_178], ax
0x140084de8  movzx   eax, word ptr [rdx+52h]
0x140084dec  mov     [rsp+1E0h+var_180], rcx
0x140084df1  mov     rcx, [r13+18h]
0x140084df5  mov     word ptr [rsp+1E0h+var_188], ax
0x140084dfa  mov     al, [rdx]
0x140084dfc  mov     [rsp+1E0h+var_190], r8
0x140084e01  mov     dword ptr [rsp+1E0h+var_198], r10d
0x140084e06  mov     dword ptr [rsp+1E0h+var_1A0], r11d
0x140084e0b  mov     dword ptr [rsp+1E0h+var_1A8], ebx
0x140084e0f  shr     r14d, 1
0x140084e12  mov     dword ptr [rsp+1E0h+var_1B0], r14d
0x140084e17  mov     byte ptr [rsp+1E0h+var_1B8], al
0x140084e1b  mov     dword ptr [rsp+1E0h+var_1C0], edi
0x140084e1f  call    WPP_SF__MAC_DcDDDD_MAC_H_WPSDEVICENAME_hs_MAC__SSID_
0x140084e24  mov     rdi, [rbp+0D0h+var_110]
0x140084e28  lea     rbx, WPP_GLOBAL_Control
0x140084e2f  mov     r14d, 200000h
0x140084e35  mov     eax, cs:dword_1400B1050
0x140084e3b  cmp     eax, 5
0x140084e3e  jbe     short loc_140084E7C
0x140084e40  mov     rdx, 200000000000h
0x140084e4a  lea     rcx, dword_1400B1050
0x140084e51  call    _tlgKeywordOn
0x140084e56  test    al, al
0x140084e58  jz      short loc_140084E7C
0x140084e5a  movzx   eax, byte ptr [rdi]
0x140084e5d  lea     rdx, byte_1400A76A9
0x140084e64  mov     dword ptr [rbp+0D0h+Size], eax
0x140084e67  lea     rcx, dword_1400B1050
0x140084e6e  lea     rax, [rbp+0D0h+Size]
0x140084e72  mov     [rsp+1E0h+var_1C0], rax
0x140084e77  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140084e7c  mov     rsi, cs:WPP_GLOBAL_Control
0x140084e83  cmp     rsi, rbx
0x140084e86  jz      loc_140084F3C
0x140084e8c  cmp     byte ptr [rsi+29h], 4
0x140084e90  jb      loc_140084F3C
0x140084e96  test    [rsi+2Ch], r14d
0x140084e9a  jz      loc_140084F3C
0x140084ea0  mov     rcx, [rbp+0D0h+var_110]
0x140084ea4  lea     r9, aY; "Y"
0x140084eab  mov     eax, [rdi+34h]
0x140084eae  lea     r13, aN; "N"
0x140084eb5  test    eax, eax
0x140084eb7  mov     rdi, r9
0x140084eba  mov     rbx, r9
0x140084ebd  mov     r11, r9
0x140084ec0  mov     eax, [rcx+1Ch]
0x140084ec3  cmovz   rdi, r13
0x140084ec7  cmp     [rcx+30h], r15d
0x140084ecb  mov     r10, r9
0x140084ece  mov     [rsp+1E0h+var_190], rdi
0x140084ed3  mov     r8, r9
0x140084ed6  cmovz   rbx, r13
0x140084eda  mov     rdx, r9
0x140084edd  cmp     [rcx+2Ch], r15d
0x140084ee1  mov     [rsp+1E0h+var_198], rbx
0x140084ee6  cmovz   r11, r13
0x140084eea  cmp     [rcx+28h], r15d
0x140084eee  mov     [rsp+1E0h+var_1A0], r11
0x140084ef3  cmovz   r10, r13
0x140084ef7  cmp     [rcx+24h], r15d
0x140084efb  mov     [rsp+1E0h+var_1A8], r10
0x140084f00  cmovz   r8, r13
0x140084f04  cmp     [rcx+20h], r15d
0x140084f08  mov     rcx, r9
0x140084f0b  mov     [rsp+1E0h+var_1B0], r8
0x140084f10  mov     r9, [rbp+0D0h+var_100]
0x140084f14  cmovz   rdx, r13
0x140084f18  test    eax, eax
0x140084f1a  mov     [rsp+1E0h+var_1B8], rdx
0x140084f1f  cmovz   rcx, r13
0x140084f23  add     r9, 4
0x140084f27  mov     [rsp+1E0h+var_1C0], rcx
0x140084f2c  mov     rcx, [rsi+18h]
0x140084f30  call    WPP_SF__MAC_sssssss
0x140084f35  lea     rbx, WPP_GLOBAL_Control
0x140084f3c  test    r12d, r12d
0x140084f3f  jz      short loc_140084F91
0x140084f41  mov     rcx, cs:WPP_GLOBAL_Control
0x140084f48  cmp     rcx, rbx
0x140084f4b  jz      short loc_140084F91
0x140084f4d  cmp     byte ptr [rcx+29h], 4
0x140084f51  jb      short loc_140084F91
0x140084f53  mov     rbx, [rbp+0D0h+var_128]
0x140084f57  test    [rcx+2Ch], r14d
0x140084f5b  jz      short loc_140084F95
0x140084f5d  mov     rcx, [rcx+18h]
0x140084f61  lea     r9, [rbp+0D0h+var_D0]
0x140084f65  xorps   xmm0, xmm0
0x140084f68  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140084f6f  movups  [rbp+0D0h+var_D0], xmm0
0x140084f73  mov     word ptr [rbp+0D0h+var_D0], r12w
0x140084f78  mov     edx, 94h
0x140084f7d  mov     qword ptr [rbp+0D0h+var_D0+8], rbx
0x140084f81  movaps  xmm0, [rbp+0D0h+var_D0]
0x140084f85  movdqa  [rbp+0D0h+var_D0], xmm0
0x140084f8a  call    WPP_SF__HEX_
0x140084f8f  jmp     short loc_140084F95
0x140084f91  mov     rbx, [rbp+0D0h+var_128]
0x140084f95  mov     rdi, [rbp+0D0h+var_E0]
0x140084f99  lea     rax, [rdi+4A8h]
0x140084fa0  mov     rcx, rax; SpinLock
0x140084fa3  mov     [rbp+0D0h+SpinLock], rax
0x140084fa7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140084fae  nop     dword ptr [rax+rax+00h]
0x140084fb3  mov     [rdi+4B0h], al
0x140084fb9  lea     rcx, [rbp+0D0h+var_14F]
0x140084fbd  mov     rax, [rbp+0D0h+var_100]
0x140084fc1  mov     esi, 1
0x140084fc6  mov     [rsp+1E0h+var_1C0], rcx; unsigned __int8 *
0x140084fcb  mov     r8d, esi; enum _WFD_RECEIVED_PACKET_TYPE
0x140084fce  mov     rcx, rdi; struct _WFD_DEVICE_ROLE *
0x140084fd1  mov     r9b, [rax+0Ah]; unsigned __int8
0x140084fd5  lea     r13, [rax+4]
0x140084fd9  mov     rdx, r13; unsigned __int8 (*)[6]
0x140084fdc  mov     [rbp+0D0h+var_128], r13
0x140084fe0  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x140084fe5  test    eax, eax
0x140084fe7  js      loc_140085D28
0x140084fed  cmp     [rbp+0D0h+var_14F], r15b
0x140084ff1  jnz     loc_140085D28
0x140084ff7  lea     r8, [rbp+0D0h+var_F0]; struct _WFD_PEER_DEVICE **
0x140084ffb  mov     [rbp+0D0h+var_14F], r15b
0x140084fff  mov     rdx, r13; unsigned __int8 (*)[6]
0x140085002  mov     rcx, rdi; struct _WFD_DEVICE_ROLE *
0x140085005  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x14008500a  mov     edi, eax
0x14008500c  test    eax, eax
0x14008500e  jz      short loc_140085044
0x140085010  mov     rcx, cs:WPP_GLOBAL_Control
0x140085017  lea     rbx, WPP_GLOBAL_Control
0x14008501e  cmp     rcx, rbx
0x140085021  jz      short loc_14008503B
0x140085023  mov     rcx, [rcx+18h]
0x140085027  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008502e  mov     edx, 96h
0x140085033  mov     r9, r13
0x140085036  call    WPP_SF__MAC_
0x14008503b  mov     r15, [rbp+0D0h+var_F0]
0x14008503f  jmp     loc_140085D6E
0x140085044  mov     r15, [rbp+0D0h+var_F0]
0x140085048  mov     rdx, [rbp+0D0h+var_100]
0x14008504c  movzx   eax, byte ptr [r15+28h]
0x140085051  movzx   edx, byte ptr [rdx+0Ah]
0x140085055  cmp     dl, al
0x140085057  jz      short loc_140085096
0x140085059  mov     edi, 0C000000Dh
0x14008505e  mov     rcx, cs:WPP_GLOBAL_Control
0x140085065  lea     rbx, WPP_GLOBAL_Control
0x14008506c  cmp     rcx, rbx
0x14008506f  jz      loc_140085D6E
0x140085075  mov     rcx, [rcx+18h]
  ... truncated ...
```

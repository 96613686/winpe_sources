# WFDDeviceHandleReceivedGONResponse(_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_RESPONSE_PARAMETERS *)

- ea: `0x14008332c`
- end: `0x1400848cc`
- name: `?WFDDeviceHandleReceivedGONResponse@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_RESPONSE_PARAMETERS@@@Z`
- size: `5536`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_GO_NEGOTIATION_RESPONSE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007c730`

## callees

- `0x14000170c`
- `0x14000d22c`
- `0x14000d2c0`
- `0x140020dc0`
- `0x140020f20`
- `0x14002f1bc`
- `0x1400308ec`
- `0x140030da8`
- `0x14003ae2c`
- `0x14003d814`
- `0x14007a08c`
- `0x14007f254`
- `0x14007f384`
- `0x14007f5a0`
- `0x14007f5cc`
- `0x14007f60c`
- `0x14007f73c`
- `0x14008332c`
- `0x1400896c8`
- `0x14008a780`
- `0x14008ae64`
- `0x14008af58`
- `0x14008b05c`
- `0x14008bb90`
- `0x14008c148`
- `0x14008c60c`
- `0x14008c778`
- `0x14008d590`
- `0x1400977cc`
- `0x14009a3d0`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140083401`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008411b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140083401`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008411b`
- `ntoskrnl!ExAllocatePool2` at `0x140084133`
- `ntoskrnl!ExAllocatePool2` at `0x140084133`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140083fcf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400847c8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084808`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140083fcf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400847c8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084808`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084288`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400847d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084819`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084288`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400847d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084819`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084379`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400844e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008454e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084379`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400844e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008454e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140083777`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400843f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140083777`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400843f9`
- `NDIS!NdisReleaseRWLock` at `0x140083fa4`
- `NDIS!NdisReleaseRWLock` at `0x1400842a2`
- `NDIS!NdisReleaseRWLock` at `0x140083fa4`
- `NDIS!NdisReleaseRWLock` at `0x1400842a2`
- `NDIS!NdisAcquireRWLockRead` at `0x140083f49`
- `NDIS!NdisAcquireRWLockRead` at `0x140083f49`

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
  char v32; // r9
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
  __int64 v64; // r9
  PDEVICE_OBJECT v65; // rcx
  __int64 v66; // rdx
  PNDIS_RW_LOCK_EX *v67; // r12
  unsigned int v68; // ebx
  unsigned int v69; // eax
  unsigned int v70; // r12d
  unsigned int v71; // ecx
  unsigned int v72; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  _DWORD *Pool2; // rax
  size_t v75; // r8
  char *v76; // rbx
  unsigned __int8 *v77; // rdx
  char *v78; // rbx
  _DWORD *v79; // rcx
  unsigned __int8 *v80; // r14
  const char *v81; // r11
  const char *v82; // rcx
  struct _WFD_DEVICE_ROLE *v83; // r13
  PKSPIN_LOCK v84; // r14
  int v85; // eax
  KIRQL v86; // al
  unsigned int v87; // edx
  char v88; // al
  __int64 v89; // rsi
  char *v90; // rbx
  char v91; // r14
  __int16 v92; // ax
  struct _WFD_ROLE *v93; // rsi
  char v94; // [rsp+90h] [rbp-80h]
  unsigned __int8 v95; // [rsp+91h] [rbp-7Fh] BYREF
  char v96; // [rsp+92h] [rbp-7Eh]
  char v97; // [rsp+93h] [rbp-7Dh]
  char v98; // [rsp+94h] [rbp-7Ch]
  PKSPIN_LOCK SpinLock; // [rsp+98h] [rbp-78h]
  unsigned int v100; // [rsp+A0h] [rbp-70h]
  int Size[3]; // [rsp+A4h] [rbp-6Ch] BYREF
  char v102; // [rsp+B0h] [rbp-60h]
  unsigned __int8 *v103; // [rsp+B8h] [rbp-58h]
  struct _LOCK_STATE_EX LockState; // [rsp+C0h] [rbp-50h] BYREF
  void *v105; // [rsp+C8h] [rbp-48h]
  char *v106; // [rsp+D0h] [rbp-40h]
  unsigned int v107; // [rsp+D8h] [rbp-38h] BYREF
  struct _DOT11_RECEIVED_GO_NEGOTIATION_RESPONSE_PARAMETERS *v108; // [rsp+E0h] [rbp-30h]
  unsigned int v109; // [rsp+E8h] [rbp-28h]
  struct _WFD_PEER_DEVICE *v110; // [rsp+F0h] [rbp-20h] BYREF
  void *Src; // [rsp+F8h] [rbp-18h]
  struct _WFD_DEVICE_ROLE *v112; // [rsp+100h] [rbp-10h]
  _QWORD v113[2]; // [rsp+110h] [rbp+0h] BYREF
  char *v114; // [rsp+120h] [rbp+10h]
  _DWORD *v115; // [rsp+128h] [rbp+18h]
  void *v116; // [rsp+130h] [rbp+20h]
  _QWORD v117[12]; // [rsp+140h] [rbp+30h] BYREF

  v3 = 0;
  v108 = a3;
  v110 = 0;
  v95 = 0;
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
    v94 = 5;
    v109 = 0;
    v116 = 0;
    v98 = 0;
    v96 = 0;
    v97 = 0;
    v105 = 0;
    v100 = 0;
    v112 = pRoleExt;
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
    v16 = (unsigned __int8 *)v108 + v8;
    *(_QWORD *)v10 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    v17 = v10 + 16;
    *((_DWORD *)v10 + 2) = 808679286;
    v106 = v10 + 16;
    v103 = v16;
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
      v12 = v106;
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
        (_DWORD)v106,
        (_DWORD)v17 + 63,
        (_DWORD)v108 + 4,
        *((_BYTE *)v108 + 10),
        *v106,
        (unsigned __int8)v17[60] >> 1,
        v17[60] & 1,
        v17[61],
        v17[62],
        (__int64)(v17 + 63),
        *((_WORD *)v106 + 41),
        (__int64)(v17 + 92),
        *((_WORD *)v106 + 64),
        (__int64)v18,
        (__int64)(v17 + 140),
        (__int64)(v17 + 148));
      v17 = v106;
    }
    if ( (unsigned int)dword_1400AE050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400AE050, 0x200000000000LL) )
    {
      Size[0] = (unsigned __int8)*v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1400AE050,
        (unsigned int)byte_1400A55A9,
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
      if ( !*((_DWORD *)v106 + 12) )
        v23 = "N";
      v27 = "Y";
      if ( !*((_DWORD *)v106 + 11) )
        v24 = "N";
      if ( !*((_DWORD *)v106 + 10) )
        v25 = "N";
      if ( !*((_DWORD *)v106 + 9) )
        v26 = "N";
      v28 = "Y";
      if ( !*((_DWORD *)v106 + 8) )
        v27 = "N";
      if ( !*((_DWORD *)v106 + 7) )
        v28 = "N";
      WPP_SF__MAC_sssssss(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v27,
        (_DWORD)v26,
        (_DWORD)v108 + 4,
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
      v29 = v103;
    }
    else
    {
      v29 = v103;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v113[0] = (unsigned __int16)v7;
        v113[1] = v103;
        WPP_SF__HEX_(AttachedDevice, 148, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v113);
      }
    }
    v31 = v112;
    SpinLock = (PKSPIN_LOCK)((char *)v112 + 1192);
    *((_BYTE *)v31 + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v112 + 149);
    v32 = *((_BYTE *)v108 + 10);
    v33 = (unsigned __int8 *)v108 + 4;
    v103 = (unsigned __int8 *)v108 + 4;
    if ( (int)WFDDeviceCheckDuplicateTransmission(v31, (unsigned __int8 (*)[6])((char *)v108 + 4), 1, v32, &v95) < 0
      || v95 )
    {
      v95 = 1;
      PeerByMAC = -1073676267;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0 )
      {
        goto LABEL_249;
      }
      v45 = 149;
      v46 = WPP_GLOBAL_Control->AttachedDevice;
      v44 = *((unsigned __int8 *)v108 + 10);
      goto LABEL_248;
    }
    v95 = 0;
    PeerByMAC = WFDDeviceFindPeerByMAC(v31, (unsigned __int8 (*)[6])v33, &v110);
    if ( PeerByMAC )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 150, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v33);
      v3 = v110;
      goto LABEL_249;
    }
    v3 = v110;
    if ( *((_BYTE *)v108 + 10) != *((_BYTE *)v110 + 40) )
    {
      PeerByMAC = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          151,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          *((unsigned __int8 *)v108 + 10),
          *((unsigned __int8 *)v110 + 40));
      goto LABEL_249;
    }
    v109 = *((_DWORD *)v110 + 14);
    if ( !(unsigned __int8)WFDPeerDeviceSetState(v110, 21) )
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
    v36 = v106;
    v116 = (void *)*((_QWORD *)v3 + 6);
    v98 = 1;
    v97 = 1;
    *((_BYTE *)v3 + 374) = *v106;
    *((_BYTE *)v3 + 380) |= 2u;
    v114 = (char *)v3 + 320;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        154,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        *((unsigned __int8 *)v3 + 374));
      v36 = v106;
      v35 = (unsigned __int8 *)v3 + 320;
    }
    if ( *((_BYTE *)v3 + 374) )
    {
      if ( *((_BYTE *)v3 + 374) == 1 )
      {
        if ( (unsigned __int8)WFDPeerDeviceSetState(v3, 22) )
        {
          WFDPeerDeviceQueueTimer(v3, 0x1D4C0u, 0x2EE0u);
          v98 = 0;
          v95 = 1;
          v96 = 1;
          goto LABEL_249;
        }
        PeerByMAC = -1073741436;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer)
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        }
        v96 = 1;
        goto LABEL_97;
      }
      v97 = 0;
      PeerByMAC = -1073741811;
    }
    v96 = 1;
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
      v84 = SpinLock;
      goto LABEL_250;
    }
    v43 = (*((_BYTE *)v3 + 253) & 1) == 0;
    if ( (*((_BYTE *)v3 + 373) & 1) != v43 )
    {
      PeerByMAC = -1073676267;
      v94 = 4;
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
      v94 = 0;
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
      v94 = 9;
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
      v94 = 4;
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
      v94 = 2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v54 = v103;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          v55 = "PERSISTENT";
          v56 = "PERSISTENT";
          if ( !(_BYTE)v40 )
            v56 = "TRANSIENT";
          if ( !(_BYTE)v39 )
            v55 = "TRANSIENT";
          WPP_SF_ss_MAC_(WPP_GLOBAL_Control->AttachedDevice, v39, v40, (_DWORD)v55, (__int64)v56, (__int64)v103);
        }
LABEL_149:
        if ( v47 )
        {
          v57 = (unsigned __int64)v3 + 200;
          v114 = (char *)v3 + 200;
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
          v115 = 0;
        else
          v115 = (_DWORD *)((char *)v3 + 441);
        v107 = 0;
        LockState.OldIrql = 0;
        v60 = (_OWORD *)(v57 & -(__int64)v47);
        v113[0] = *((_QWORD *)v108 + 2);
        v102 = *((_BYTE *)v108 + 10);
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
        PeerByMAC = WFDRoleGetCachedFrameIEs(v61, 7u, &v107, 0);
        if ( PeerByMAC )
        {
          v65 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
LABEL_168:
            v67 = *(PNDIS_RW_LOCK_EX **)&Size[1];
            goto LABEL_169;
          }
          v66 = 72;
LABEL_167:
          WPP_SF_(v65->AttachedDevice, v66, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
          goto LABEL_168;
        }
        v69 = v59 + 96;
        if ( (unsigned int)v59 >= 0xFFFFFFA0 )
        {
          PeerByMAC = -1073741675;
          v65 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_168;
          v66 = 73;
          goto LABEL_167;
        }
        v70 = v107;
        v71 = v107 + v69;
        Size[0] = v107 + v69;
        if ( v107 + v69 < v69 )
        {
          PeerByMAC = -1073741675;
          v65 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_168;
          v66 = 74;
          goto LABEL_167;
        }
        v72 = v71 + 16;
        if ( v71 >= 0xFFFFFFF0 )
        {
LABEL_201:
          PeerByMAC = -1073741670;
          v65 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_168;
          v66 = 76;
          goto LABEL_167;
        }
        if ( v72 > 0x40 )
        {
          if ( v72 > 0x100 )
          {
            if ( v72 > 0x400 )
            {
              if ( v72 > 0x800 )
              {
                p_WaitListHead = 0;
                Pool2 = (_DWORD *)ExAllocatePool2(64, v72, 808679286, v64);
LABEL_200:
                if ( Pool2 )
                {
                  v75 = (unsigned int)Size[0];
                  v62 = (char *)(Pool2 + 4);
                  v76 = v114;
                  *(_QWORD *)Pool2 = p_WaitListHead;
                  Pool2[2] = 808679286;
                  PeerByMAC = 0;
                  memset(Pool2 + 4, 0, v75);
                  v77 = v103;
                  *(_DWORD *)v62 = 6292096;
                  *((_DWORD *)v62 + 1) = *(_DWORD *)v77;
                  *((_WORD *)v62 + 4) = *((_WORD *)v77 + 2);
                  v62[10] = v102;
                  *((_QWORD *)v62 + 2) = v113[0];
                  *((_DWORD *)v62 + 6) = 1000;
                  v62[28] = 0;
                  v78 = v76 + 44;
                  if ( v78 )
                    v62[29] = *v78;
                  if ( v60 )
                  {
                    *((_OWORD *)v62 + 2) = *v60;
                    *((_OWORD *)v62 + 3) = v60[1];
                    *(_OWORD *)(v62 + 60) = *(_OWORD *)((char *)v60 + 28);
                    v62[76] = 1;
                  }
                  v79 = v115;
                  if ( v115 )
                  {
                    *((_DWORD *)v62 + 22) = *v115;
                    v62[92] = *((_BYTE *)v79 + 4);
                    v62[93] = 1;
                  }
                  *((_DWORD *)v62 + 20) = 96;
                  *((_DWORD *)v62 + 21) = v70 + v59;
                  v80 = (unsigned __int8 *)(v62 + 96);
                  if ( Src )
                  {
                    memmove(v62 + 96, Src, v59);
                    v80 += v59;
                  }
                  v21 = v70 == 0;
                  v67 = *(PNDIS_RW_LOCK_EX **)&Size[1];
                  if ( v21
                    || (PeerByMAC = WFDRoleGetCachedFrameIEs(*(struct _WFD_ROLE **)&Size[1], 7u, &v107, v80)) == 0 )
                  {
                    NdisReleaseRWLock(v67[4], &LockState);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                    {
                      v81 = "Y";
                      v82 = "Y";
                      if ( !Src )
                        v82 = "N";
                      if ( !v62[76] )
                        v81 = "N";
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
                        (__int64)v81,
                        (__int64)(v62 + 32),
                        (__int64)(v62 + 40),
                        *((_DWORD *)v62 + 20),
                        *((_DWORD *)v62 + 21),
                        (__int64)v82);
                    }
                    v68 = Size[0];
LABEL_174:
                    v100 = v68;
                    v105 = v62;
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
                        v83 = v112;
                        v84 = SpinLock;
                        KeReleaseSpinLock(SpinLock, *((_BYTE *)v112 + 1200));
                        v85 = NwifiSetDirectOidRequestAsync(*((struct _ADAPT **)*v67 + 2), 235208972, v62, v68);
                        if ( v85 == 1076035585 )
                          v85 = 0;
                        Size[0] = v85;
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
                          v105 = v62;
                          v100 = v68;
LABEL_251:
                          v12 = v106;
                          v88 = v94;
                          if ( !v94 )
                            v88 = 5;
                          v14 = v88;
                          v94 = v88;
LABEL_11:
                          if ( !PeerByMAC )
                            PeerByMAC = -1073741823;
                          if ( v97 )
                          {
                            memset(v117, 0, sizeof(v117));
                            if ( v3 && *((_BYTE *)v3 + 440) )
                              v15 = (char *)v3 + 441;
                            else
                              v15 = 0;
                            if ( v14 )
                            {
                              LOBYTE(v107) = 0;
                              v89 = *((_QWORD *)v108 + 2);
                              v90 = (char *)v108 + 4;
                              v91 = *((_BYTE *)v108 + 10);
                              *(_WORD *)((char *)&v107 + 1) = 0;
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                WPP_SF_(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  71,
                                  WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                              if ( v90 )
                              {
                                memset(v117, 0, sizeof(v117));
                                HIDWORD(v117[0]) = *(_DWORD *)v90;
                                v92 = *((_WORD *)v90 + 2);
                                v14 = v94;
                                BYTE4(v117[3]) = v94;
                                LODWORD(v117[0]) = 6292096;
                                LOWORD(v117[1]) = v92;
                                BYTE2(v117[1]) = v91;
                                v117[2] = v89;
                                LODWORD(v117[3]) = 1000;
                                if ( v15 )
                                {
                                  LODWORD(v117[11]) = *(_DWORD *)v15;
                                  BYTE4(v117[11]) = v15[4];
                                  BYTE5(v117[11]) = 1;
                                }
                                v117[10] = 96;
                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                                {
                                  WPP_SF__MAC_DqDcCs_MAC__SSID_DDs(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    (unsigned int)&v117[4],
                                    0,
                                    (unsigned int)v117 + 4,
                                    v91,
                                    v89,
                                    232,
                                    v94,
                                    0,
                                    (__int64)"N",
                                    (__int64)&v117[4],
                                    (__int64)&v117[5],
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
                                v93 = *(struct _WFD_ROLE **)&Size[1];
                                Size[0] = NwifiSetDirectOidRequestAsync(
                                            *(struct _ADAPT **)(**(_QWORD **)&Size[1] + 16LL),
                                            235208972,
                                            v117,
                                            v100);
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
                              v14 = v94;
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
                          v93 = *(struct _WFD_ROLE **)&Size[1];
LABEL_278:
                          if ( v96 )
                            WFDDeviceGONegotiationSendUpcallFailure(v93, v116, v11, PeerByMAC, v14);
                          goto LABEL_281;
                        }
                        v86 = KeAcquireSpinLockRaiseToDpc(v84);
                        v87 = v109;
                        *((_BYTE *)v83 + 1200) = v86;
                        if ( (unsigned int)WFDDeviceFindPeerByID(v83, v87, &v110) )
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
                          v3 = v110;
                          v96 = 1;
                        }
                        else
                        {
                          v3 = v110;
                          if ( (unsigned __int8)WFDPeerDeviceSetState(v110, 30) )
                          {
                            WFDPeerDeviceQueueTimer(v3, 0x3E8u, 0x64u);
                            KeReleaseSpinLock(v84, *((_BYTE *)v83 + 1200));
                            v12 = v106;
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
                        v105 = v62;
                        v100 = v68;
LABEL_250:
                        KeReleaseSpinLock(v84, *((_BYTE *)v84 + 8));
                        if ( v95 )
                        {
                          v12 = v106;
LABEL_281:
                          if ( v98 )
                            WFDDeviceCleanupPeerByID(v112, v109);
                          v62 = (char *)v105;
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
                      v105 = v62;
                      v100 = v68;
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
                  NdisReleaseRWLock(v67[4], &LockState);
                  if ( v62 && v63 )
                  {
                    if ( *((_QWORD *)v62 - 2) )
                      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v62 - 2), v62 - 16);
                    else
                      ExFreePoolWithTag(v62 - 16, *((_DWORD *)v62 - 2));
                  }
                  v62 = (char *)v105;
                  v68 = (unsigned int)v105;
                  goto LABEL_174;
                }
                goto LABEL_201;
              }
              p_WaitListHead = &stru_1400B0180;
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
      v54 = v103;
      goto LABEL_149;
    }
    if ( (*((_BYTE *)v3 + 380) & 5) == 5 )
      goto LABEL_148;
    v94 = 4;
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
0x14008332c  mov     [rsp-8+arg_8], rbx
0x140083331  push    rbp
0x140083332  push    rsi
0x140083333  push    rdi
0x140083334  push    r12
0x140083336  push    r13
0x140083338  push    r14
0x14008333a  push    r15
0x14008333c  lea     rbp, [rsp-0A0h]
0x140083344  sub     rsp, 1B0h
0x14008334b  mov     rax, cs:__security_cookie
0x140083352  xor     rax, rsp
0x140083355  mov     [rbp+0D0h+var_40], rax
0x14008335c  xor     r15d, r15d
0x14008335f  mov     [rbp+0D0h+var_100], r8
0x140083363  mov     esi, edx
0x140083365  mov     [rbp+0D0h+var_F0], r15
0x140083369  mov     [rbp+0D0h+var_14F], r15b
0x14008336d  mov     rdi, r8
0x140083370  mov     rdx, rcx
0x140083373  mov     qword ptr [rbp+0D0h+Size+4], rcx
0x140083377  mov     rcx, cs:WPP_GLOBAL_Control
0x14008337e  lea     rax, WPP_GLOBAL_Control
0x140083385  cmp     rcx, rax
0x140083388  jz      short loc_1400833A3
0x14008338a  mov     rcx, [rcx+18h]
0x14008338e  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140083395  mov     edx, 8Eh
0x14008339a  call    WPP_SF_
0x14008339f  mov     rdx, qword ptr [rbp+0D0h+Size+4]
0x1400833a3  mov     r12d, [rdi+1Ch]
0x1400833a7  mov     ebx, [rdi+18h]
0x1400833aa  test    r12d, r12d
0x1400833ad  jz      short loc_1400833B8
0x1400833af  cmp     ebx, 20h ; ' '
0x1400833b2  jb      loc_140084827
0x1400833b8  lea     eax, [r12+rbx]
0x1400833bc  cmp     eax, ebx
0x1400833be  jb      loc_140084827
0x1400833c4  cmp     eax, esi
0x1400833c6  ja      loc_140084827
0x1400833cc  mov     rax, [rdx+0B8h]
0x1400833d3  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400833da  mov     rcx, rdi; Lookaside
0x1400833dd  mov     [rbp+0D0h+var_150], 5
0x1400833e1  mov     [rbp+0D0h+var_F8], r15d
0x1400833e5  mov     [rbp+0D0h+var_B0], r15
0x1400833e9  mov     [rbp+0D0h+var_14C], r15b
0x1400833ed  mov     [rbp+0D0h+var_14E], r15b
0x1400833f1  mov     [rbp+0D0h+var_14D], r15b
0x1400833f5  mov     [rbp+0D0h+var_118], r15
0x1400833f9  mov     [rbp+0D0h+var_140], r15d
0x1400833fd  mov     [rbp+0D0h+var_E0], rax
0x140083401  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140083408  nop     dword ptr [rax+rax+00h]
0x14008340d  mov     r14d, 200000h
0x140083413  mov     r13d, 1
0x140083419  test    rax, rax
0x14008341c  jnz     short loc_14008349B
0x14008341e  xor     r12d, r12d
0x140083421  mov     edi, 0C000009Ah
0x140083426  mov     rcx, cs:WPP_GLOBAL_Control
0x14008342d  lea     rbx, WPP_GLOBAL_Control
0x140083434  cmp     rcx, rbx
0x140083437  jz      short loc_14008344E
0x140083439  mov     rcx, [rcx+18h]
0x14008343d  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140083444  mov     edx, 90h
0x140083449  call    WPP_SF_
0x14008344e  mov     bl, [rbp+0D0h+var_150]
0x140083451  mov     esi, 0C0000001h
0x140083456  test    edi, edi
0x140083458  cmovz   edi, esi
0x14008345b  cmp     [rbp+0D0h+var_14D], 0
0x14008345f  jz      loc_140084778
0x140083465  xor     edx, edx; Val
0x140083467  mov     byte ptr [rbp+0D0h+var_A0], 0
0x14008346b  lea     rcx, [rbp+0D0h+var_A0+1]; void *
0x14008346f  lea     r8d, [rdx+5Fh]; Size
0x140083473  call    memset
0x140083478  test    r15, r15
0x14008347b  jz      loc_140084586
0x140083481  cmp     byte ptr [r15+1B8h], 0
0x140083489  jz      loc_140084586
0x14008348f  add     r15, 1B9h
0x140083496  jmp     loc_140084589
0x14008349b  add     rbx, [rbp+0D0h+var_100]
0x14008349f  xor     edx, edx; Val
0x1400834a1  mov     [rax], rdi
0x1400834a4  mov     r8d, 0BCh; Size
0x1400834aa  lea     rdi, [rax+10h]
0x1400834ae  mov     dword ptr [rax+8], 30337776h
0x1400834b5  mov     rcx, rdi; void *
0x1400834b8  mov     [rbp+0D0h+var_110], rdi
0x1400834bc  mov     [rbp+0D0h+var_128], rbx
0x1400834c0  call    memset
0x1400834c5  mov     r8, rdi; void *
0x1400834c8  mov     edx, r12d; unsigned int
0x1400834cb  mov     rcx, rbx; unsigned __int8 *
0x1400834ce  call    WFDValidateIncomingGONegotiationResponseIEs
0x1400834d3  test    al, al
0x1400834d5  jnz     short loc_14008351C
0x1400834d7  mov     edi, 0C0010015h
0x1400834dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400834e3  lea     r14, WPP_GLOBAL_Control
0x1400834ea  cmp     rcx, r14
0x1400834ed  jz      short loc_140083513
0x1400834ef  cmp     byte ptr [rcx+29h], 2
0x1400834f3  jb      short loc_140083513
0x1400834f5  test    dword ptr [rcx+2Ch], 200000h
0x1400834fc  jz      short loc_140083513
0x1400834fe  mov     rcx, [rcx+18h]
0x140083502  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140083509  mov     edx, 91h
0x14008350e  call    WPP_SF_
0x140083513  mov     r12, [rbp+0D0h+var_110]
0x140083517  jmp     loc_1400847EC
0x14008351c  mov     r13, cs:WPP_GLOBAL_Control
0x140083523  lea     rbx, WPP_GLOBAL_Control
0x14008352a  cmp     r13, rbx
0x14008352d  jz      loc_140083605
0x140083533  cmp     byte ptr [r13+29h], 4
0x140083538  jb      loc_140083605
0x14008353e  test    [r13+2Ch], r14d
0x140083542  jz      loc_140083605
0x140083548  movzx   r14d, byte ptr [rdi+3Ch]
0x14008354d  lea     rsi, [rdi+8Ch]
0x140083554  test    byte ptr [rdi+0B8h], 2
0x14008355b  lea     r8, [rdi+3Fh]
0x14008355f  movzx   r10d, byte ptr [rdi+3Eh]
0x140083564  lea     rdx, [rsi+8]
0x140083568  movzx   r11d, byte ptr [rdi+3Dh]
0x14008356d  lea     rcx, aN; "N"
0x140083574  mov     r9, [rbp+0D0h+var_100]
0x140083578  lea     rax, aY; "Y"
0x14008357f  mov     [rsp+1E0h+var_160], rdx
0x140083587  cmovz   rax, rcx
0x14008358b  mov     rdx, [rbp+0D0h+var_110]
0x14008358f  lea     rcx, [rdi+5Ch]
0x140083593  mov     [rsp+1E0h+var_168], rsi
0x140083598  mov     ebx, r14d
0x14008359b  movzx   edi, byte ptr [r9+0Ah]
0x1400835a0  and     ebx, 1
0x1400835a3  mov     [rsp+1E0h+var_170], rax
0x1400835a8  add     r9, 4
0x1400835ac  movzx   eax, word ptr [rdx+80h]
0x1400835b3  mov     word ptr [rsp+1E0h+var_178], ax
0x1400835b8  movzx   eax, word ptr [rdx+52h]
0x1400835bc  mov     [rsp+1E0h+var_180], rcx
0x1400835c1  mov     rcx, [r13+18h]
0x1400835c5  mov     word ptr [rsp+1E0h+var_188], ax
0x1400835ca  mov     al, [rdx]
0x1400835cc  mov     [rsp+1E0h+var_190], r8
0x1400835d1  mov     dword ptr [rsp+1E0h+var_198], r10d
0x1400835d6  mov     dword ptr [rsp+1E0h+var_1A0], r11d
0x1400835db  mov     dword ptr [rsp+1E0h+var_1A8], ebx
0x1400835df  shr     r14d, 1
0x1400835e2  mov     dword ptr [rsp+1E0h+var_1B0], r14d
0x1400835e7  mov     byte ptr [rsp+1E0h+var_1B8], al
0x1400835eb  mov     dword ptr [rsp+1E0h+var_1C0], edi
0x1400835ef  call    WPP_SF__MAC_DcDDDD_MAC_H_WPSDEVICENAME_hs_MAC__SSID_
0x1400835f4  mov     rdi, [rbp+0D0h+var_110]
0x1400835f8  lea     rbx, WPP_GLOBAL_Control
0x1400835ff  mov     r14d, 200000h
0x140083605  mov     eax, cs:dword_1400AE050
0x14008360b  cmp     eax, 5
0x14008360e  jbe     short loc_14008364C
0x140083610  mov     rdx, 200000000000h
0x14008361a  lea     rcx, dword_1400AE050
0x140083621  call    _tlgKeywordOn
0x140083626  test    al, al
0x140083628  jz      short loc_14008364C
0x14008362a  movzx   eax, byte ptr [rdi]
0x14008362d  lea     rdx, byte_1400A55A9
0x140083634  mov     dword ptr [rbp+0D0h+Size], eax
0x140083637  lea     rcx, dword_1400AE050
0x14008363e  lea     rax, [rbp+0D0h+Size]
0x140083642  mov     [rsp+1E0h+var_1C0], rax
0x140083647  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x14008364c  mov     rsi, cs:WPP_GLOBAL_Control
0x140083653  cmp     rsi, rbx
0x140083656  jz      loc_14008370C
0x14008365c  cmp     byte ptr [rsi+29h], 4
0x140083660  jb      loc_14008370C
0x140083666  test    [rsi+2Ch], r14d
0x14008366a  jz      loc_14008370C
0x140083670  mov     rcx, [rbp+0D0h+var_110]
0x140083674  lea     r9, aY; "Y"
0x14008367b  mov     eax, [rdi+34h]
0x14008367e  lea     r13, aN; "N"
0x140083685  test    eax, eax
0x140083687  mov     rdi, r9
0x14008368a  mov     rbx, r9
0x14008368d  mov     r11, r9
0x140083690  mov     eax, [rcx+1Ch]
0x140083693  cmovz   rdi, r13
0x140083697  cmp     [rcx+30h], r15d
0x14008369b  mov     r10, r9
0x14008369e  mov     [rsp+1E0h+var_190], rdi
0x1400836a3  mov     r8, r9
0x1400836a6  cmovz   rbx, r13
0x1400836aa  mov     rdx, r9
0x1400836ad  cmp     [rcx+2Ch], r15d
0x1400836b1  mov     [rsp+1E0h+var_198], rbx
0x1400836b6  cmovz   r11, r13
0x1400836ba  cmp     [rcx+28h], r15d
0x1400836be  mov     [rsp+1E0h+var_1A0], r11
0x1400836c3  cmovz   r10, r13
0x1400836c7  cmp     [rcx+24h], r15d
0x1400836cb  mov     [rsp+1E0h+var_1A8], r10
0x1400836d0  cmovz   r8, r13
0x1400836d4  cmp     [rcx+20h], r15d
0x1400836d8  mov     rcx, r9
0x1400836db  mov     [rsp+1E0h+var_1B0], r8
0x1400836e0  mov     r9, [rbp+0D0h+var_100]
0x1400836e4  cmovz   rdx, r13
0x1400836e8  test    eax, eax
0x1400836ea  mov     [rsp+1E0h+var_1B8], rdx
0x1400836ef  cmovz   rcx, r13
0x1400836f3  add     r9, 4
0x1400836f7  mov     [rsp+1E0h+var_1C0], rcx
0x1400836fc  mov     rcx, [rsi+18h]
0x140083700  call    WPP_SF__MAC_sssssss
0x140083705  lea     rbx, WPP_GLOBAL_Control
0x14008370c  test    r12d, r12d
0x14008370f  jz      short loc_140083761
0x140083711  mov     rcx, cs:WPP_GLOBAL_Control
0x140083718  cmp     rcx, rbx
0x14008371b  jz      short loc_140083761
0x14008371d  cmp     byte ptr [rcx+29h], 4
0x140083721  jb      short loc_140083761
0x140083723  mov     rbx, [rbp+0D0h+var_128]
0x140083727  test    [rcx+2Ch], r14d
0x14008372b  jz      short loc_140083765
0x14008372d  mov     rcx, [rcx+18h]
0x140083731  lea     r9, [rbp+0D0h+var_D0]
0x140083735  xorps   xmm0, xmm0
0x140083738  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008373f  movups  [rbp+0D0h+var_D0], xmm0
0x140083743  mov     word ptr [rbp+0D0h+var_D0], r12w
0x140083748  mov     edx, 94h
0x14008374d  mov     qword ptr [rbp+0D0h+var_D0+8], rbx
0x140083751  movaps  xmm0, [rbp+0D0h+var_D0]
0x140083755  movdqa  [rbp+0D0h+var_D0], xmm0
0x14008375a  call    WPP_SF__HEX_
0x14008375f  jmp     short loc_140083765
0x140083761  mov     rbx, [rbp+0D0h+var_128]
0x140083765  mov     rdi, [rbp+0D0h+var_E0]
0x140083769  lea     rax, [rdi+4A8h]
0x140083770  mov     rcx, rax; SpinLock
0x140083773  mov     [rbp+0D0h+SpinLock], rax
0x140083777  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008377e  nop     dword ptr [rax+rax+00h]
0x140083783  mov     [rdi+4B0h], al
0x140083789  lea     rcx, [rbp+0D0h+var_14F]
0x14008378d  mov     rax, [rbp+0D0h+var_100]
0x140083791  mov     esi, 1
0x140083796  mov     [rsp+1E0h+var_1C0], rcx; unsigned __int8 *
0x14008379b  mov     r8d, esi; enum _WFD_RECEIVED_PACKET_TYPE
0x14008379e  mov     rcx, rdi; struct _WFD_DEVICE_ROLE *
0x1400837a1  mov     r9b, [rax+0Ah]; unsigned __int8
0x1400837a5  lea     r13, [rax+4]
0x1400837a9  mov     rdx, r13; unsigned __int8 (*)[6]
0x1400837ac  mov     [rbp+0D0h+var_128], r13
0x1400837b0  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x1400837b5  test    eax, eax
0x1400837b7  js      loc_1400844F8
0x1400837bd  cmp     [rbp+0D0h+var_14F], r15b
0x1400837c1  jnz     loc_1400844F8
0x1400837c7  lea     r8, [rbp+0D0h+var_F0]; struct _WFD_PEER_DEVICE **
0x1400837cb  mov     [rbp+0D0h+var_14F], r15b
0x1400837cf  mov     rdx, r13; unsigned __int8 (*)[6]
0x1400837d2  mov     rcx, rdi; struct _WFD_DEVICE_ROLE *
0x1400837d5  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x1400837da  mov     edi, eax
0x1400837dc  test    eax, eax
0x1400837de  jz      short loc_140083814
0x1400837e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400837e7  lea     rbx, WPP_GLOBAL_Control
0x1400837ee  cmp     rcx, rbx
0x1400837f1  jz      short loc_14008380B
0x1400837f3  mov     rcx, [rcx+18h]
0x1400837f7  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400837fe  mov     edx, 96h
0x140083803  mov     r9, r13
0x140083806  call    WPP_SF__MAC_
0x14008380b  mov     r15, [rbp+0D0h+var_F0]
0x14008380f  jmp     loc_14008453E
0x140083814  mov     r15, [rbp+0D0h+var_F0]
0x140083818  mov     rdx, [rbp+0D0h+var_100]
0x14008381c  movzx   eax, byte ptr [r15+28h]
0x140083821  movzx   edx, byte ptr [rdx+0Ah]
0x140083825  cmp     dl, al
0x140083827  jz      short loc_140083866
0x140083829  mov     edi, 0C000000Dh
0x14008382e  mov     rcx, cs:WPP_GLOBAL_Control
0x140083835  lea     rbx, WPP_GLOBAL_Control
0x14008383c  cmp     rcx, rbx
0x14008383f  jz      loc_14008453E
0x140083845  mov     rcx, [rcx+18h]
  ... truncated ...
```

# WFDDeviceHandleGONRequestForExistingPeer(ulong,_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *,_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *,ulong,uchar *,uchar *)

- ea: `0x140081d8c`
- end: `0x140082dc4`
- name: `?WFDDeviceHandleGONRequestForExistingPeer@@YAEKPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS@@PEAU_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES@@KPEAE3@Z`
- size: `4152`
- prototype: `unsigned __int8 __fastcall(unsigned int, struct _WFD_ROLE *, int, struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *, struct _WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *, unsigned int, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140084210`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x140030b7c`
- `0x140031038`
- `0x140034c84`
- `0x14007b8bc`
- `0x140080bb4`
- `0x140080dd0`
- `0x140080e3c`
- `0x140080f6c`
- `0x1400811dc`
- `0x140081d8c`
- `0x14008aef8`
- `0x14008bfb0`
- `0x14008c694`
- `0x14008c788`
- `0x14008c88c`
- `0x14008db38`
- `0x14008de3c`
- `0x14008de90`
- `0x14008e1d4`
- `0x14009a7dc`
- `0x14009bcc0`
- `0x14009bfc0`
- `0x14009c4e0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008255c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140082598`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140082804`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008255c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140082598`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140082804`
- `ntoskrnl!ExAllocatePool2` at `0x14008281f`
- `ntoskrnl!ExAllocatePool2` at `0x14008281f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400825f8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140082724`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140082b4b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140082c9f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400825f8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140082724`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140082b4b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140082c9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400829c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082d83`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400829c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082d83`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081e8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140082be1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081e8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140082be1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140081e20`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140082cb8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140081e20`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140082cb8`
- `NDIS!NdisReleaseRWLock` at `0x1400826f9`
- `NDIS!NdisReleaseRWLock` at `0x1400829e1`
- `NDIS!NdisReleaseRWLock` at `0x1400826f9`
- `NDIS!NdisReleaseRWLock` at `0x1400829e1`
- `NDIS!NdisAcquireRWLockRead` at `0x14008269e`
- `NDIS!NdisAcquireRWLockRead` at `0x14008269e`

## pseudocode

```c
unsigned __int8 __fastcall WFDDeviceHandleGONRequestForExistingPeer(
        unsigned int a1,
        struct _WFD_ROLE *a2,
        int a3,
        struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *a4,
        struct _WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned __int8 *a8)
{
  _VELAN *pGenVElan; // rax
  void *pRoleExt; // r15
  unsigned __int8 v10; // bl
  unsigned int ChannelListBlob; // esi
  unsigned __int8 v14; // r12
  PNPAGED_LOOKASIDE_LIST *v15; // r14
  struct _WFD_ROLE *v16; // r13
  void *v17; // rdi
  int v18; // r8d
  struct _WFD_PEER_DEVICE *v19; // rbx
  int v20; // edi
  __int64 v21; // r8
  struct _WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *v22; // r13
  unsigned __int8 *v23; // rdx
  unsigned int v24; // ecx
  char v25; // cl
  _BYTE *v26; // r8
  char v27; // al
  bool v28; // di
  unsigned __int8 v29; // dl
  const char *v30; // r10
  unsigned __int8 v31; // al
  unsigned __int8 v32; // r14
  PDEVICE_OBJECT v33; // rcx
  __int64 v34; // rdx
  unsigned __int8 v35; // cl
  __int64 v36; // rdx
  __int64 v37; // r8
  struct _DEVICE_OBJECT *v38; // r9
  char v39; // r13
  char v40; // si
  void *v41; // rdx
  int v42; // r13d
  int v43; // esi
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  _DWORD *v47; // rax
  _DWORD *v48; // rax
  PNPAGED_LOOKASIDE_LIST *v49; // rbx
  void *v50; // r8
  _DWORD *v51; // rcx
  struct _WFD_ROLE *v52; // rsi
  char *v53; // r14
  PDEVICE_OBJECT v54; // rcx
  __int64 v55; // rdx
  char v56; // bl
  unsigned int v57; // eax
  unsigned int v58; // ecx
  unsigned int v59; // eax
  _DWORD *Pool2; // rax
  size_t v61; // r8
  _WORD *v62; // r13
  char *v63; // rdi
  char *v64; // rbx
  char *v65; // rdx
  char *v66; // rax
  _OWORD *v67; // rax
  __int64 v68; // r13
  void *v69; // rdx
  unsigned __int8 *v70; // rdi
  int v71; // ebx
  const char *v72; // r9
  int v73; // eax
  struct _WFD_PEER_DEVICE *v74; // rbx
  char v75; // cl
  unsigned __int8 result; // al
  int v77; // [rsp+28h] [rbp-E0h]
  char v78; // [rsp+7Ah] [rbp-8Eh]
  PNPAGED_LOOKASIDE_LIST *v79; // [rsp+80h] [rbp-88h]
  char v80; // [rsp+90h] [rbp-78h]
  unsigned int Size; // [rsp+94h] [rbp-74h] BYREF
  struct _LOCK_STATE_EX Size_4; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v83; // [rsp+9Ch] [rbp-6Ch] BYREF
  _DWORD *v84; // [rsp+A0h] [rbp-68h]
  unsigned int v85; // [rsp+A8h] [rbp-60h]
  unsigned int v86; // [rsp+ACh] [rbp-5Ch]
  struct _WFD_PEER_DEVICE *v87; // [rsp+B0h] [rbp-58h] BYREF
  size_t v88; // [rsp+B8h] [rbp-50h]
  void *Src; // [rsp+C0h] [rbp-48h]
  void *v90; // [rsp+C8h] [rbp-40h]
  void *v91; // [rsp+D0h] [rbp-38h]
  char *v92; // [rsp+D8h] [rbp-30h]
  __int64 v93; // [rsp+E0h] [rbp-28h]
  char *v94; // [rsp+E8h] [rbp-20h]
  _OWORD *v95; // [rsp+F0h] [rbp-18h]
  PVOID Entry; // [rsp+F8h] [rbp-10h]
  void *pVElanExt; // [rsp+100h] [rbp-8h]
  struct _WFD_ROLE *v99; // [rsp+160h] [rbp+58h] BYREF
  int v100; // [rsp+168h] [rbp+60h]
  struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *v101; // [rsp+170h] [rbp+68h]

  v101 = a4;
  v100 = a3;
  v99 = a2;
  pGenVElan = a2->pGenVElan;
  pRoleExt = a2->pRoleExt;
  v10 = 0;
  v87 = 0;
  v79 = 0;
  ChannelListBlob = 0;
  pVElanExt = pGenVElan->pVElanExt;
  LOBYTE(v100) = 0;
  v78 = 0;
  v91 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
  *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
  if ( (unsigned int)WFDDeviceFindPeerByID((struct _WFD_DEVICE_ROLE *)pRoleExt, a1, &v87) )
  {
    ChannelListBlob = -1073741436;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, a1);
LABEL_6:
    v14 = v10;
LABEL_7:
    v15 = 0;
LABEL_8:
    v16 = v99;
LABEL_9:
    v17 = pRoleExt;
    goto LABEL_10;
  }
  v19 = v87;
  v20 = *((_DWORD *)v87 + 9);
  if ( !(unsigned __int8)WFDPeerDeviceSetState(v87, 23) )
  {
    ChannelListBlob = -1073741436;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        116,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        *((unsigned int *)v19 + 9));
    }
    v10 = 0;
    goto LABEL_6;
  }
  if ( !(unsigned int)WFDPeerDeviceCancelTimer(v19) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF__MAC_q(WPP_GLOBAL_Control->AttachedDevice, 117, v21, (char *)v19 + 24, v19);
    }
    v14 = 0;
    goto LABEL_24;
  }
  v14 = 1;
  v91 = (void *)*((_QWORD *)v19 + 6);
  v78 = 1;
  if ( (unsigned int)(v20 - 17) <= 3 && memcmp((char *)v19 + 200, (char *)v19 + 24, 6u) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    }
    if ( !(unsigned __int8)WFDPeerDeviceSetState(v19, 20) )
    {
      ChannelListBlob = -1073741436;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, 20);
      v10 = 0;
      goto LABEL_7;
    }
    WFDPeerDeviceQueueTimer(v19, 0x3E8u, 0x64u);
    v78 = 0;
LABEL_24:
    v10 = 0;
    v15 = 0;
    goto LABEL_8;
  }
  v22 = a5;
  *((_BYTE *)v19 + 40) = *((_BYTE *)a4 + 10);
  WFDDeviceUpdateGroupCaps(
    (unsigned __int8 *)v19 + 364,
    (struct _WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *)((char *)v22 + 24));
  v23 = a7;
  v24 = a6;
  *(_DWORD *)((char *)v19 + 365) = *((_DWORD *)v22 + 16);
  *(_WORD *)((char *)v19 + 369) = *((_WORD *)v22 + 34);
  *(_WORD *)((char *)v19 + 371) = *(_WORD *)((char *)v22 + 57);
  *(_DWORD *)((char *)v19 + 375) = *((_DWORD *)v22 + 32);
  *((_BYTE *)v19 + 379) = *((_BYTE *)v22 + 132);
  *((_BYTE *)v19 + 380) |= 4u;
  *((_BYTE *)v19 + 373) = *((_BYTE *)v22 + 56);
  ChannelListBlob = WFDDeviceGetChannelListBlob(v24, v23, (unsigned int *)v19 + 107, (unsigned __int8 **)v19 + 54);
  if ( ChannelListBlob )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    v10 = v100;
    goto LABEL_6;
  }
  v25 = *((_BYTE *)v19 + 253);
  v26 = (char *)v19 + 253;
  v27 = ~*((_BYTE *)v19 + 373);
  v94 = (char *)v19 + 253;
  *((_BYTE *)v19 + 253) = v25 ^ (v25 ^ v27) & 1;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    v26 = (char *)v19 + 253;
  }
  v29 = *((_BYTE *)v19 + 373);
  v30 = "Y";
  v31 = v29 >> 1;
  if ( (unsigned __int8)(v29 >> 1) > 0xFu )
  {
    v32 = 4;
    LOBYTE(v100) = 4;
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_68;
    if ( !BYTE1(WPP_GLOBAL_Control->Timer) || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      goto LABEL_62;
    v34 = 110;
LABEL_59:
    WPP_SF_(v33->AttachedDevice, v34, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    goto LABEL_61;
  }
  v32 = 0;
  v35 = *v26 >> 1;
  LOBYTE(v100) = 0;
  if ( v31 < v35 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    }
    v28 = 1;
    goto LABEL_61;
  }
  if ( v31 == v35 )
  {
    if ( v31 != 15 )
    {
      v28 = (v29 & 1) == 0;
      goto LABEL_61;
    }
    v32 = 9;
    LOBYTE(v100) = 9;
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_68;
    if ( !BYTE1(WPP_GLOBAL_Control->Timer) || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      goto LABEL_61;
    v34 = 112;
    goto LABEL_59;
  }
LABEL_61:
  v30 = "Y";
LABEL_62:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
  {
    if ( !v28 )
      v30 = "N";
    WPP_SF_DDDDDs(
      WPP_GLOBAL_Control->AttachedDevice,
      v32,
      *((_BYTE *)v19 + 373) & 1,
      *((unsigned __int8 *)v19 + 253) >> 1,
      *((_BYTE *)v19 + 253) & 1,
      *((_BYTE *)v19 + 373) >> 1,
      *((_BYTE *)v19 + 373) & 1,
      v32,
      (__int64)v30);
  }
LABEL_68:
  if ( v32 )
  {
    ChannelListBlob = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_71:
    v10 = v100;
LABEL_72:
    v14 = 0;
    goto LABEL_7;
  }
  *((_BYTE *)v19 + 192) = v28;
  if ( *((_DWORD *)v22 + 34) != (unsigned int)WFDDeviceGetDevicePasswordIDComplement(*((unsigned int *)v19 + 49)) )
  {
    LOBYTE(v100) = 4;
    ChannelListBlob = -1073741823;
  }
  if ( ChannelListBlob )
  {
    if ( WPP_GLOBAL_Control != v38 )
    {
      LOWORD(v77) = *((_WORD *)v19 + 98);
      WPP_SF_hh(WPP_GLOBAL_Control->AttachedDevice, v36, v37, *((unsigned __int16 *)v22 + 68), v77);
    }
    goto LABEL_71;
  }
  if ( v28 )
  {
    v39 = *((_BYTE *)v19 + 244);
    v40 = *((_BYTE *)v19 + 364) & 2;
    if ( WPP_GLOBAL_Control != v38
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        123,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        *((unsigned __int8 *)v19 + 244),
        *((unsigned __int8 *)v19 + 364));
      v38 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
    }
    if ( v40 && (v39 & 2) == 0 )
    {
      v10 = 2;
      if ( WPP_GLOBAL_Control != v38
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      {
        WPP_SF_ss(
          WPP_GLOBAL_Control->AttachedDevice,
          124,
          (unsigned int)WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          (unsigned int)"TRANSIENT",
          (__int64)"PERSISTENT");
      }
      ChannelListBlob = -1073741823;
      goto LABEL_72;
    }
  }
  if ( !(unsigned __int8)WFDPeerDeviceSetState(v19, 24) )
  {
    ChannelListBlob = -1073741436;
    v10 = 5;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, 24);
    }
    goto LABEL_72;
  }
  v41 = (void *)*((_QWORD *)v19 + 35);
  v42 = *((_DWORD *)v19 + 68);
  v43 = *((_DWORD *)v19 + 49);
  v86 = 0;
  LODWORD(v88) = v42;
  v95 = (_OWORD *)(((unsigned __int64)v19 + 200) & -(__int64)v28);
  v90 = v41;
  v92 = (char *)v19 + 24;
  Size = 0;
  v93 = *((_QWORD *)v101 + 2);
  v80 = *((_BYTE *)v19 + 40);
  *(_WORD *)&Size_4.LockState = 0;
  v83 = 0;
  Size_4.OldIrql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    v41 = v90;
  }
  if ( v19 != (struct _WFD_PEER_DEVICE *)-24LL )
  {
    if ( !v41 )
    {
      if ( v42 )
        goto LABEL_100;
LABEL_106:
      p_WaitListHead = &Lookaside;
      Size = 256;
      v47 = ExAllocateFromNPagedLookasideList(&Lookaside);
      Entry = v47;
      if ( !v47 )
      {
        ChannelListBlob = -1073741670;
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v45 = 58;
          goto LABEL_102;
        }
LABEL_186:
        v16 = v99;
        goto LABEL_187;
      }
      *(_QWORD *)v47 = &Lookaside;
      v47[2] = 808679286;
      Src = v47 + 4;
      memset(v47 + 4, 0, Size);
      v48 = ExAllocateFromNPagedLookasideList(&Lookaside);
      if ( !v48 )
      {
        v49 = 0;
        ChannelListBlob = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_110:
        v16 = v99;
LABEL_111:
        if ( Src )
        {
          if ( *(_QWORD *)Entry )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)Entry, Entry);
          else
            ExFreePoolWithTag(Entry, *((_DWORD *)Entry + 2));
        }
        if ( v49 )
        {
          if ( *(v49 - 2) )
            ExFreeToNPagedLookasideList(*(v49 - 2), v49 - 2);
          else
            ExFreePoolWithTag(v49 - 2, *((_DWORD *)v49 - 2));
        }
        goto LABEL_103;
      }
      *(_QWORD *)v48 = &Lookaside;
      v84 = v48 + 4;
      v48[2] = 808679286;
      memset(v48 + 4, 0, 0x208u);
      v50 = Src;
      v51 = v84;
      *v84 = 1;
      v51[2] = v43;
      v51[1] = 524416;
      v51[3] |= 1u;
      v51[4] = 32;
      if ( !(unsigned __int8)WcnGenerateWpsIe(v51, &Size, v50) )
      {
        ChannelListBlob = -1073741823;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        v49 = (PNPAGED_LOOKASIDE_LIST *)v84;
        goto LABEL_110;
      }
      v52 = v99;
      v53 = 0;
      NdisAcquireRWLockRead(v99->pRWLock, &Size_4, 0);
      ChannelListBlob = WFDRoleGetCachedFrameIEs(v52, 6u, &v83, 0);
      if ( ChannelListBlob )
      {
        v54 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_122:
          v16 = v99;
          v56 = 0;
          goto LABEL_123;
        }
        v55 = 61;
LABEL_121:
        WPP_SF_(v54->AttachedDevice, v55, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        goto LABEL_122;
      }
      v57 = Size + 96;
      if ( Size >= 0xFFFFFFA0 )
      {
        ChannelListBlob = -1073741675;
        v54 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v55 = 62;
        goto LABEL_121;
      }
      v58 = v57 + v42;
      if ( v57 + v42 < v57 )
      {
        ChannelListBlob = -1073741675;
        v54 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v55 = 63;
        goto LABEL_121;
      }
      v85 = v58 + v83;
      if ( v58 + v83 < v58 )
      {
        ChannelListBlob = -1073741675;
        v54 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v55 = 64;
        goto LABEL_121;
      }
      v59 = v58 + v83 + 16;
      if ( v59 < 0x10 )
      {
LABEL_148:
        ChannelListBlob = -1073741670;
        v54 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v55 = 66;
        goto LABEL_121;
      }
      if ( v59 > 0x40 )
      {
        if ( v59 > 0x100 )
        {
          if ( v59 > 0x400 )
          {
            if ( v59 > 0x800 )
            {
              p_WaitListHead = 0;
              Pool2 = (_DWORD *)ExAllocatePool2(64, v59, 808679286);
LABEL_147:
              if ( Pool2 )
              {
                v61 = v85;
                v53 = (char *)(Pool2 + 4);
                *(_QWORD *)Pool2 = p_WaitListHead;
                v62 = (_WORD *)((char *)v19 + 251);
                Pool2[2] = 808679286;
                v63 = (char *)v19 + 244;
                ChannelListBlob = 0;
                v64 = (char *)v19 + 245;
                memset(Pool2 + 4, 0, v61);
                v65 = v92;
                *(_DWORD *)v53 = 6291840;
                *((_DWORD *)v53 + 1) = *(_DWORD *)v65;
                *((_WORD *)v53 + 4) = *((_WORD *)v65 + 2);
                v53[10] = v80;
                *((_QWORD *)v53 + 2) = v93;
                v66 = v94;
                *((_DWORD *)v53 + 6) = 10000;
                v53[28] = 0;
                if ( v66 )
                  v53[29] = *v66;
                if ( v64 )
                {
                  *((_DWORD *)v53 + 8) = *(_DWORD *)v64;
                  *((_WORD *)v53 + 18) = *((_WORD *)v64 + 2);
                }
                if ( v63 )
                  v53[38] = *v63;
                v67 = v95;
                if ( v95 )
                {
                  *(_OWORD *)(v53 + 40) = *v95;
                  *(_OWORD *)(v53 + 56) = v67[1];
                  *(_OWORD *)(v53 + 68) = *(_OWORD *)((char *)v67 + 28);
                  v53[84] = 1;
                }
                if ( v62 )
                  *((_WORD *)v53 + 15) = *v62;
                v68 = (unsigned int)v88;
                v69 = Src;
                *((_DWORD *)v53 + 22) = 96;
                *((_DWORD *)v53 + 23) = v68 + Size + v83;
                memmove(v53 + 96, v69, Size);
                v70 = (unsigned __int8 *)&v53[Size + 96];
                if ( v90 )
                {
                  memmove(&v53[Size + 96], v90, (unsigned int)v68);
                  v70 += v68;
                }
                v16 = v99;
                if ( !v83 || (ChannelListBlob = WFDRoleGetCachedFrameIEs(v99, 6u, &v83, v70)) == 0 )
                {
                  NdisReleaseRWLock(v16->pRWLock, &Size_4);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                    {
                      v71 = (_DWORD)v53 + 4;
                      WPP_SF__MAC_DqDcDDDD_MAC_C(
                        WPP_GLOBAL_Control->AttachedDevice,
                        68,
                        (unsigned int)WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                        (_DWORD)v53 + 4,
                        v53[10],
                        *((_QWORD *)v53 + 2),
                        *((_DWORD *)v53 + 6),
                        v53[28],
                        (unsigned __int8)v53[29] >> 1,
                        v53[29] & 1,
                        v53[30],
                        v53[31],
                        (__int64)(v53 + 32));
                    }
                    else
                    {
                      v71 = (_DWORD)v53 + 4;
                    }
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                    {
                      v72 = "Y";
                      if ( !v53[84] )
                        v72 = "N";
                      WPP_SF__MAC_s_MAC__SSID_DD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        69,
                        (unsigned int)WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                        v71,
                        (__int64)v72,
                        (__int64)(v53 + 40),
                        (__int64)(v53 + 48),
                        *((_DWORD *)v53 + 22),
                        *((_DWORD *)v53 + 23));
                    }
                  }
                  v86 = v85;
                  v79 = (PNPAGED_LOOKASIDE_LIST *)v53;
                  goto LABEL_127;
                }
                v56 = 1;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_123:
                NdisReleaseRWLock(v16->pRWLock, &Size_4);
                if ( v53 && v56 )
                {
                  if ( *((_QWORD *)v53 - 2) )
                    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v53 - 2), v53 - 16);
                  else
                    ExFreePoolWithTag(v53 - 16, *((_DWORD *)v53 - 2));
                }
LABEL_127:
                v49 = (PNPAGED_LOOKASIDE_LIST *)v84;
                goto LABEL_111;
              }
              goto LABEL_148;
            }
            p_WaitListHead = &stru_1400B31C0;
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
      goto LABEL_147;
    }
    if ( v42 )
      goto LABEL_106;
  }
LABEL_100:
  ChannelListBlob = -1073741811;
  v44 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_186;
  v45 = 57;
LABEL_102:
  WPP_SF_(v44->AttachedDevice, v45, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
  v16 = v99;
LABEL_103:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, ChannelListBlob);
LABEL_187:
  if ( ChannelListBlob )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 126, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    v10 = v100;
    v14 = 0;
    v15 = v79;
    goto LABEL_9;
  }
  v17 = pRoleExt;
  KeReleaseSpinLock((PKSPIN_LOCK)pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
  v15 = v79;
  v73 = NwifiSetDirectOidRequestAsync(*(struct _ADAPT **)(*(_QWORD *)pVElanExt + 16LL), 0xE05010Bu, v79, v86);
  if ( v73 == 1076035585 )
    v73 = 0;
  LODWORD(v99) = v73;
  MapPendingDirectOidStatus((int *)&v99);
  ChannelListBlob = (unsigned int)v99;
  if ( !(_DWORD)v99 )
  {
    v78 = 0;
    *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
    if ( (unsigned int)WFDDeviceFindPeerByID((struct _WFD_DEVICE_ROLE *)pRoleExt, a1, &v87) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      }
    }
    else
    {
      v74 = v87;
      if ( (unsigned __int8)WFDPeerDeviceSetState(v87, 25) )
      {
        WFDPeerDeviceQueueTimer(v74, 0x2710u, 0x3E8u);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
             && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          129,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          *((unsigned int *)v74 + 9));
      }
    }
    v10 = v100;
LABEL_10:
    KeReleaseSpinLock((PKSPIN_LOCK)v17 + 149, *((_BYTE *)v17 + 1200));
    if ( !v78 )
      goto LABEL_198;
    goto LABEL_197;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      127,
      WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
      (unsigned int)v99);
  v14 = 0;
  v10 = v100;
LABEL_197:
  WFDDeviceGONegotiationSendUpcallFailure(v16, v91, v18, ChannelListBlob, v10);
  WFDDeviceCleanupPeerByID((struct _WFD_DEVICE_ROLE *)v17, a1);
LABEL_198:
  if ( v15 )
  {
    if ( *(v15 - 2) )
      ExFreeToNPagedLookasideList(*(v15 - 2), v15 - 2);
    else
      ExFreePoolWithTag(v15 - 2, *((_DWORD *)v15 - 2));
  }
  if ( !v14 )
  {
    v75 = v10;
    if ( !v10 )
      v75 = 5;
    v10 = v75;
  }
  result = v14;
  *a8 = v10;
  return result;
}

```

## disassembly

```asm
0x140081d8c  mov     rax, rsp
0x140081d8f  mov     [rax+20h], r9
0x140081d93  mov     [rax+18h], r8d
0x140081d97  mov     [rax+10h], rdx
0x140081d9b  mov     [rax+8], ecx
0x140081d9e  push    rbp
0x140081d9f  push    rbx
0x140081da0  push    rsi
0x140081da1  push    rdi
0x140081da2  push    r12
0x140081da4  push    r13
0x140081da6  push    r14
0x140081da8  push    r15
0x140081daa  lea     rbp, [rax-48h]
0x140081dae  sub     rsp, 108h
0x140081db5  mov     rax, [rdx]
0x140081db8  xor     r13d, r13d
0x140081dbb  mov     r15, [rdx+0B8h]
0x140081dc2  mov     bl, r13b
0x140081dc5  mov     r14, r9
0x140081dc8  mov     [rbp+40h+var_98], r13
0x140081dcc  mov     edi, ecx
0x140081dce  mov     [rsp+78h], r13
0x140081dd3  mov     rax, [rax+1F68h]
0x140081dda  mov     esi, r13d
0x140081ddd  mov     [rbp+40h+var_48], rax
0x140081de1  mov     byte ptr [rbp+40h+arg_10], bl
0x140081de4  mov     byte ptr [rsp+140h+var_D0], r13b
0x140081de9  mov     byte ptr [rsp+140h+var_D0+2], r13b
0x140081dee  mov     [rbp+40h+var_78], r13
0x140081df2  mov     rcx, cs:WPP_GLOBAL_Control
0x140081df9  lea     r12, WPP_GLOBAL_Control
0x140081e00  cmp     rcx, r12
0x140081e03  jz      short loc_140081E19
0x140081e05  mov     rcx, [rcx+18h]
0x140081e09  lea     edx, [r13+72h]
0x140081e0d  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140081e14  call    WPP_SF_
0x140081e19  lea     rcx, [r15+4A8h]; SpinLock
0x140081e20  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140081e27  nop     dword ptr [rax+rax+00h]
0x140081e2c  lea     r8, [rbp+40h+var_98]; struct _WFD_PEER_DEVICE **
0x140081e30  mov     edx, edi; unsigned int
0x140081e32  mov     rcx, r15; struct _WFD_DEVICE_ROLE *
0x140081e35  mov     [r15+4B0h], al
0x140081e3c  call    ?WFDDeviceFindPeerByID@@YAHPEAU_WFD_DEVICE_ROLE@@KPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByID(_WFD_DEVICE_ROLE *,ulong,_WFD_PEER_DEVICE * *)
0x140081e41  test    eax, eax
0x140081e43  jz      short loc_140081EA6
0x140081e45  mov     esi, 0C0000184h
0x140081e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140081e51  cmp     rcx, r12
0x140081e54  jz      short loc_140081E6E
0x140081e56  mov     rcx, [rcx+18h]
0x140081e5a  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140081e61  mov     edx, 73h ; 's'
0x140081e66  mov     r9d, edi
0x140081e69  call    WPP_SF_d
0x140081e6e  mov     r12b, bl
0x140081e71  mov     r14, [rsp+78h]
0x140081e76  mov     r13, [rbp+40h+arg_8]
0x140081e7a  mov     rdi, r15
0x140081e7d  mov     dl, [rdi+4B0h]; NewIrql
0x140081e83  lea     rcx, [rdi+4A8h]; SpinLock
0x140081e8a  call    cs:__imp_KeReleaseSpinLock
0x140081e91  nop     dword ptr [rax+rax+00h]
0x140081e96  cmp     byte ptr [rsp+140h+var_D0+2], 0
0x140081e9b  jz      loc_140082C80
0x140081ea1  jmp     loc_140082C62
0x140081ea6  mov     rbx, [rbp+40h+var_98]
0x140081eaa  mov     edx, 17h
0x140081eaf  mov     rcx, rbx
0x140081eb2  mov     edi, [rbx+24h]
0x140081eb5  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x140081eba  test    al, al
0x140081ebc  jnz     short loc_140081EFD
0x140081ebe  mov     esi, 0C0000184h
0x140081ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x140081eca  cmp     rcx, r12
0x140081ecd  jz      short loc_140081EF5
0x140081ecf  cmp     byte ptr [rcx+29h], 3
0x140081ed3  jb      short loc_140081EF5
0x140081ed5  bt      dword ptr [rcx+2Ch], 15h
0x140081eda  jnb     short loc_140081EF5
0x140081edc  mov     r9d, [rbx+24h]
0x140081ee0  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140081ee7  mov     rcx, [rcx+18h]
0x140081eeb  mov     edx, 74h ; 't'
0x140081ef0  call    WPP_SF_d
0x140081ef5  mov     bl, r13b
0x140081ef8  jmp     loc_140081E6E
0x140081efd  mov     rcx, rbx; struct _WFD_PEER_DEVICE *
0x140081f00  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCancelTimer(_WFD_PEER_DEVICE *)
0x140081f05  test    eax, eax
0x140081f07  jnz     short loc_140081F49
0x140081f09  mov     rcx, cs:WPP_GLOBAL_Control
0x140081f10  cmp     rcx, r12
0x140081f13  jz      short loc_140081F3B
0x140081f15  lea     r12d, [rax+1]
0x140081f19  cmp     [rcx+29h], r12b
0x140081f1d  jb      short loc_140081F3B
0x140081f1f  bt      dword ptr [rcx+2Ch], 15h
0x140081f24  jnb     short loc_140081F3B
0x140081f26  mov     rcx, [rcx+18h]
0x140081f2a  lea     r9, [rbx+18h]
0x140081f2e  lea     edx, [rax+75h]
0x140081f31  mov     qword ptr [rsp+140h+var_120], rbx
0x140081f36  call    WPP_SF__MAC_q
0x140081f3b  mov     r12b, sil
0x140081f3e  mov     bl, sil
0x140081f41  mov     r14, rsi
0x140081f44  jmp     loc_140081E76
0x140081f49  mov     rax, [rbx+30h]
0x140081f4d  mov     r12d, 1
0x140081f53  mov     [rbp+40h+var_78], rax
0x140081f57  lea     eax, [rdi-11h]
0x140081f5a  mov     byte ptr [rsp+140h+var_D0+2], r12b
0x140081f5f  cmp     eax, 3
0x140081f62  ja      loc_14008201C
0x140081f68  lea     rdx, [rbx+18h]; Buf2
0x140081f6c  lea     rcx, [rbx+0C8h]; Buf1
0x140081f73  lea     r8d, [r12+5]; Size
0x140081f78  call    memcmp
0x140081f7d  test    eax, eax
0x140081f7f  jns     loc_14008201C
0x140081f85  mov     rcx, cs:WPP_GLOBAL_Control
0x140081f8c  lea     rdi, WPP_GLOBAL_Control
0x140081f93  cmp     rcx, rdi
0x140081f96  jz      short loc_140081FBA
0x140081f98  cmp     byte ptr [rcx+29h], 3
0x140081f9c  jb      short loc_140081FBA
0x140081f9e  bt      dword ptr [rcx+2Ch], 15h
0x140081fa3  jnb     short loc_140081FBA
0x140081fa5  mov     rcx, [rcx+18h]
0x140081fa9  lea     edx, [r12+75h]
0x140081fae  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140081fb5  call    WPP_SF_
0x140081fba  mov     r14d, 14h
0x140081fc0  mov     rcx, rbx
0x140081fc3  mov     edx, r14d
0x140081fc6  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x140081fcb  test    al, al
0x140081fcd  jnz     short loc_140081FFF
0x140081fcf  mov     esi, 0C0000184h
0x140081fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140081fdb  cmp     rcx, rdi
0x140081fde  jz      short loc_140081FF7
0x140081fe0  mov     rcx, [rcx+18h]
0x140081fe4  lea     edx, [r14+63h]
0x140081fe8  mov     r9d, r14d
0x140081feb  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140081ff2  call    WPP_SF_d
0x140081ff7  mov     bl, r13b
0x140081ffa  jmp     loc_140081E71
0x140081fff  mov     edx, 3E8h; unsigned int
0x140082004  mov     r8d, 64h ; 'd'; unsigned int
0x14008200a  mov     rcx, rbx; struct _WFD_PEER_DEVICE *
0x14008200d  call    ?WFDPeerDeviceQueueTimer@@YAXPEAU_WFD_PEER_DEVICE@@KK@Z; WFDPeerDeviceQueueTimer(_WFD_PEER_DEVICE *,ulong,ulong)
0x140082012  mov     byte ptr [rsp+140h+var_D0+2], r13b
0x140082017  jmp     loc_140081F3E
0x14008201c  mov     al, [r14+0Ah]
0x140082020  lea     rcx, [rbx+16Ch]; unsigned __int8 *
0x140082027  mov     r13, [rbp+40h+arg_20]
0x14008202b  mov     [rbx+28h], al
0x14008202e  lea     rdx, [r13+18h]; struct _WFD_GROUP_CAPABILITY *
0x140082032  call    ?WFDDeviceUpdateGroupCaps@@YAXPEAEPEAU_WFD_GROUP_CAPABILITY@@@Z; WFDDeviceUpdateGroupCaps(uchar *,_WFD_GROUP_CAPABILITY *)
0x140082037  mov     eax, [r13+40h]
0x14008203b  lea     r9, [rbx+1B0h]; unsigned __int8 **
0x140082042  mov     rdx, [rbp+40h+arg_30]; unsigned __int8 *
0x140082049  lea     r8, [rbx+1ACh]; unsigned int *
0x140082050  mov     ecx, [rbp+40h+arg_28]; unsigned int
0x140082053  mov     [rbx+16Dh], eax
0x140082059  movzx   eax, word ptr [r13+44h]
0x14008205e  mov     [rbx+171h], ax
0x140082065  movzx   eax, word ptr [r13+39h]
0x14008206a  mov     [rbx+173h], ax
0x140082071  mov     eax, [r13+80h]
0x140082078  mov     [rbx+177h], eax
0x14008207e  mov     al, [r13+84h]
0x140082085  mov     [rbx+17Bh], al
0x14008208b  or      byte ptr [rbx+17Ch], 4
0x140082092  mov     al, [r13+38h]
0x140082096  mov     [rbx+175h], al
0x14008209c  call    ?WFDDeviceGetChannelListBlob@@YAJKPEAEPEAKPEAPEAE@Z; WFDDeviceGetChannelListBlob(ulong,uchar *,ulong *,uchar * *)
0x1400820a1  mov     esi, eax
0x1400820a3  test    eax, eax
0x1400820a5  jz      short loc_1400820D7
0x1400820a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400820ae  lea     rax, WPP_GLOBAL_Control
0x1400820b5  cmp     rcx, rax
0x1400820b8  jz      short loc_1400820CF
0x1400820ba  mov     rcx, [rcx+18h]
0x1400820be  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400820c5  mov     edx, 78h ; 'x'
0x1400820ca  call    WPP_SF_
0x1400820cf  mov     bl, byte ptr [rbp+40h+arg_10]
0x1400820d2  jmp     loc_140081E6E
0x1400820d7  mov     cl, [rbx+0FDh]
0x1400820dd  lea     r8, [rbx+0FDh]
0x1400820e4  mov     al, [rbx+175h]
0x1400820ea  not     al
0x1400820ec  mov     [rbp+40h+var_60], r8
0x1400820f0  xor     al, cl
0x1400820f2  and     al, r12b
0x1400820f5  xor     al, cl
0x1400820f7  mov     [r8], al
0x1400820fa  xor     dil, dil
0x1400820fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140082104  lea     r9, WPP_GLOBAL_Control
0x14008210b  cmp     rcx, r9
0x14008210e  jz      short loc_140082133
0x140082110  mov     rcx, [rcx+18h]
0x140082114  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008211b  mov     edx, 6Dh ; 'm'
0x140082120  call    WPP_SF_
0x140082125  lea     r8, [rbx+0FDh]
0x14008212c  lea     r9, WPP_GLOBAL_Control
0x140082133  mov     dl, [rbx+175h]
0x140082139  lea     r10, aY; "Y"
0x140082140  mov     al, dl
0x140082142  shr     al, 1
0x140082144  cmp     al, 0Fh
0x140082146  jbe     short loc_14008217B
0x140082148  mov     r14b, 4
0x14008214b  mov     byte ptr [rbp+40h+arg_10], r14b
0x14008214f  mov     rcx, cs:WPP_GLOBAL_Control
0x140082156  cmp     rcx, r9
0x140082159  jz      loc_14008228C
0x14008215f  cmp     [rcx+29h], r12b
0x140082163  jb      loc_140082218
0x140082169  bt      dword ptr [rcx+2Ch], 15h
0x14008216e  jnb     loc_140082218
0x140082174  mov     edx, 6Eh ; 'n'
0x140082179  jmp     short loc_1400821ED
0x14008217b  mov     cl, [r8]
0x14008217e  xor     r14b, r14b
0x140082181  shr     cl, 1
0x140082183  mov     byte ptr [rbp+40h+arg_10], r14b
0x140082187  cmp     al, cl
0x140082189  jnb     short loc_1400821BE
0x14008218b  mov     rcx, cs:WPP_GLOBAL_Control
0x140082192  cmp     rcx, r9
0x140082195  jz      short loc_1400821B9
0x140082197  cmp     byte ptr [rcx+29h], 3
0x14008219b  jb      short loc_1400821B9
0x14008219d  bt      dword ptr [rcx+2Ch], 15h
0x1400821a2  jnb     short loc_1400821B9
0x1400821a4  mov     rcx, [rcx+18h]
0x1400821a8  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400821af  mov     edx, 6Fh ; 'o'
0x1400821b4  call    WPP_SF_
0x1400821b9  mov     dil, r12b
0x1400821bc  jmp     short loc_14008220A
0x1400821be  jnz     short loc_14008220A
0x1400821c0  cmp     al, 0Fh
0x1400821c2  jnz     short loc_1400821FF
0x1400821c4  mov     r14b, 9
0x1400821c7  mov     byte ptr [rbp+40h+arg_10], r14b
0x1400821cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400821d2  cmp     rcx, r9
0x1400821d5  jz      loc_14008228C
0x1400821db  cmp     [rcx+29h], r12b
0x1400821df  jb      short loc_14008220A
0x1400821e1  bt      dword ptr [rcx+2Ch], 15h
0x1400821e6  jnb     short loc_14008220A
0x1400821e8  mov     edx, 70h ; 'p'
0x1400821ed  mov     rcx, [rcx+18h]
0x1400821f1  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400821f8  call    WPP_SF_
0x1400821fd  jmp     short loc_14008220A
0x1400821ff  test    r12b, dl
0x140082202  movzx   edi, dil
0x140082206  cmovz   edi, r12d
0x14008220a  lea     r9, WPP_GLOBAL_Control
0x140082211  lea     r10, aY; "Y"
0x140082218  mov     rcx, cs:WPP_GLOBAL_Control
0x14008221f  cmp     rcx, r9
0x140082222  jz      short loc_14008228C
0x140082224  cmp     byte ptr [rcx+29h], 3
0x140082228  jb      short loc_14008228C
0x14008222a  bt      dword ptr [rcx+2Ch], 15h
0x14008222f  jnb     short loc_14008228C
0x140082231  movzx   r11d, byte ptr [rbx+175h]
0x140082239  lea     rax, aN; "N"
0x140082240  movzx   r9d, byte ptr [rbx+0FDh]
0x140082248  mov     r8d, r11d
0x14008224b  mov     rcx, [rcx+18h]
0x14008224f  test    dil, dil
0x140082252  movzx   edx, r14b
0x140082256  cmovz   r10, rax
0x14008225a  mov     eax, r9d
0x14008225d  mov     qword ptr [rsp+140h+var_100], r10
0x140082262  and     r8d, r12d
0x140082265  mov     dword ptr [rsp+140h+var_108], edx
0x140082269  and     eax, r12d
0x14008226c  mov     [rsp+140h+var_110], r8d
0x140082271  shr     r11d, 1
0x140082274  mov     dword ptr [rsp+140h+var_118], r11d
0x140082279  shr     r9d, 1
0x14008227c  mov     dword ptr [rsp+140h+var_120], eax
0x140082280  call    WPP_SF_DDDDDs
  ... truncated ...
```

# WFDDeviceHandleGONRequestForExistingPeer(ulong,_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *,_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *,ulong,uchar *,uchar *)

- ea: `0x14008055c`
- end: `0x140081594`
- name: `?WFDDeviceHandleGONRequestForExistingPeer@@YAEKPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS@@PEAU_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES@@KPEAE3@Z`
- size: `4152`
- prototype: `unsigned __int8 __usercall@<al>(unsigned int@<ecx>, struct _WFD_ROLE *@<rdx>, unsigned int@<r8d>, struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *@<r9>, struct _WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *, unsigned int, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400829e0`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x1400308ec`
- `0x140030da8`
- `0x140034a64`
- `0x14007a08c`
- `0x14007f384`
- `0x14007f5a0`
- `0x14007f60c`
- `0x14007f73c`
- `0x14007f9ac`
- `0x14008055c`
- `0x1400896c8`
- `0x14008a780`
- `0x14008ae64`
- `0x14008af58`
- `0x14008b05c`
- `0x14008c308`
- `0x14008c60c`
- `0x14008c660`
- `0x14008c9a4`
- `0x140098ffc`
- `0x14009a4c0`
- `0x14009a7c0`
- `0x14009ace0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080d2c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080d68`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080fd4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080d2c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080d68`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080fd4`
- `ntoskrnl!ExAllocatePool2` at `0x140080fef`
- `ntoskrnl!ExAllocatePool2` at `0x140080fef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140080dc8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140080ef4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008131b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008146f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140080dc8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140080ef4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008131b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008146f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081198`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400812f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008132f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081553`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081198`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400812f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008132f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081553`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008065a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400813b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008065a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400813b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400805f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140081488`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400805f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140081488`
- `NDIS!NdisReleaseRWLock` at `0x140080ec9`
- `NDIS!NdisReleaseRWLock` at `0x1400811b1`
- `NDIS!NdisReleaseRWLock` at `0x140080ec9`
- `NDIS!NdisReleaseRWLock` at `0x1400811b1`
- `NDIS!NdisAcquireRWLockRead` at `0x140080e6e`
- `NDIS!NdisAcquireRWLockRead` at `0x140080e6e`

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
  int *v49; // rbx
  _BYTE *v50; // r8
  int *v51; // rcx
  struct _WFD_ROLE *v52; // rsi
  char *v53; // r14
  __int64 v54; // r9
  PDEVICE_OBJECT v55; // rcx
  __int64 v56; // rdx
  char v57; // bl
  unsigned int v58; // eax
  unsigned int v59; // ecx
  unsigned int v60; // eax
  _DWORD *Pool2; // rax
  size_t v62; // r8
  _WORD *v63; // r13
  char *v64; // rdi
  char *v65; // rbx
  char *v66; // rdx
  char *v67; // rax
  _OWORD *v68; // rax
  __int64 v69; // r13
  void *v70; // rdx
  unsigned __int8 *v71; // rdi
  int v72; // ebx
  const char *v73; // r9
  int v74; // eax
  struct _WFD_PEER_DEVICE *v75; // rbx
  char v76; // cl
  unsigned __int8 result; // al
  int v78; // [rsp+28h] [rbp-E0h]
  char v79; // [rsp+7Ah] [rbp-8Eh]
  PNPAGED_LOOKASIDE_LIST *v80; // [rsp+80h] [rbp-88h]
  char v81; // [rsp+90h] [rbp-78h]
  unsigned int Size; // [rsp+94h] [rbp-74h] BYREF
  struct _LOCK_STATE_EX Size_4; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v84; // [rsp+9Ch] [rbp-6Ch] BYREF
  int *v85; // [rsp+A0h] [rbp-68h]
  unsigned int v86; // [rsp+A8h] [rbp-60h]
  unsigned int v87; // [rsp+ACh] [rbp-5Ch]
  struct _WFD_PEER_DEVICE *v88; // [rsp+B0h] [rbp-58h] BYREF
  size_t v89; // [rsp+B8h] [rbp-50h]
  void *Src; // [rsp+C0h] [rbp-48h]
  void *v91; // [rsp+C8h] [rbp-40h]
  void *v92; // [rsp+D0h] [rbp-38h]
  char *v93; // [rsp+D8h] [rbp-30h]
  __int64 v94; // [rsp+E0h] [rbp-28h]
  char *v95; // [rsp+E8h] [rbp-20h]
  _OWORD *v96; // [rsp+F0h] [rbp-18h]
  PVOID Entry; // [rsp+F8h] [rbp-10h]
  void *pVElanExt; // [rsp+100h] [rbp-8h]
  struct _WFD_ROLE *v100; // [rsp+160h] [rbp+58h] BYREF
  int v101; // [rsp+168h] [rbp+60h]
  struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *v102; // [rsp+170h] [rbp+68h]

  v102 = a4;
  v101 = a3;
  v100 = a2;
  pGenVElan = a2->pGenVElan;
  pRoleExt = a2->pRoleExt;
  v10 = 0;
  v88 = 0;
  v80 = 0;
  ChannelListBlob = 0;
  pVElanExt = pGenVElan->pVElanExt;
  LOBYTE(v101) = 0;
  v79 = 0;
  v92 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
  *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
  if ( (unsigned int)WFDDeviceFindPeerByID((struct _WFD_DEVICE_ROLE *)pRoleExt, a1, &v88) )
  {
    ChannelListBlob = -1073741436;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, a1);
LABEL_6:
    v14 = v10;
LABEL_7:
    v15 = 0;
LABEL_8:
    v16 = v100;
LABEL_9:
    v17 = pRoleExt;
    goto LABEL_10;
  }
  v19 = v88;
  v20 = *((_DWORD *)v88 + 9);
  if ( !(unsigned __int8)WFDPeerDeviceSetState(v88, 23) )
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
  v92 = (void *)*((_QWORD *)v19 + 6);
  v79 = 1;
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
    v79 = 0;
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
    v10 = v101;
    goto LABEL_6;
  }
  v25 = *((_BYTE *)v19 + 253);
  v26 = (char *)v19 + 253;
  v27 = ~*((_BYTE *)v19 + 373);
  v95 = (char *)v19 + 253;
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
    LOBYTE(v101) = 4;
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
  LOBYTE(v101) = 0;
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
    LOBYTE(v101) = 9;
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
    v10 = v101;
LABEL_72:
    v14 = 0;
    goto LABEL_7;
  }
  *((_BYTE *)v19 + 192) = v28;
  if ( *((_DWORD *)v22 + 34) != (unsigned int)WFDDeviceGetDevicePasswordIDComplement(*((unsigned int *)v19 + 49)) )
  {
    LOBYTE(v101) = 4;
    ChannelListBlob = -1073741823;
  }
  if ( ChannelListBlob )
  {
    if ( WPP_GLOBAL_Control != v38 )
    {
      LOWORD(v78) = *((_WORD *)v19 + 98);
      WPP_SF_hh(WPP_GLOBAL_Control->AttachedDevice, v36, v37, *((unsigned __int16 *)v22 + 68), v78);
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
  v87 = 0;
  LODWORD(v89) = v42;
  v96 = (_OWORD *)(((unsigned __int64)v19 + 200) & -(__int64)v28);
  v91 = v41;
  v93 = (char *)v19 + 24;
  Size = 0;
  v94 = *((_QWORD *)v102 + 2);
  v81 = *((_BYTE *)v19 + 40);
  *(_WORD *)&Size_4.LockState = 0;
  v84 = 0;
  Size_4.OldIrql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    v41 = v91;
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
        v16 = v100;
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
        v16 = v100;
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
          if ( *((_QWORD *)v49 - 2) )
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v49 - 2), v49 - 4);
          else
            ExFreePoolWithTag(v49 - 4, *(v49 - 2));
        }
        goto LABEL_103;
      }
      *(_QWORD *)v48 = &Lookaside;
      v85 = v48 + 4;
      v48[2] = 808679286;
      memset(v48 + 4, 0, 0x208u);
      v50 = Src;
      v51 = v85;
      *v85 = 1;
      v51[2] = v43;
      v51[1] = 524416;
      v51[3] |= 1u;
      v51[4] = 32;
      if ( !WcnGenerateWpsIe(v51, &Size, v50) )
      {
        ChannelListBlob = -1073741823;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        v49 = v85;
        goto LABEL_110;
      }
      v52 = v100;
      v53 = 0;
      NdisAcquireRWLockRead(v100->pRWLock, &Size_4, 0);
      ChannelListBlob = WFDRoleGetCachedFrameIEs(v52, 6u, &v84, 0);
      if ( ChannelListBlob )
      {
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_122:
          v16 = v100;
          v57 = 0;
          goto LABEL_123;
        }
        v56 = 61;
LABEL_121:
        WPP_SF_(v55->AttachedDevice, v56, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        goto LABEL_122;
      }
      v58 = Size + 96;
      if ( Size >= 0xFFFFFFA0 )
      {
        ChannelListBlob = -1073741675;
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v56 = 62;
        goto LABEL_121;
      }
      v59 = v58 + v42;
      if ( v58 + v42 < v58 )
      {
        ChannelListBlob = -1073741675;
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v56 = 63;
        goto LABEL_121;
      }
      v86 = v59 + v84;
      if ( v59 + v84 < v59 )
      {
        ChannelListBlob = -1073741675;
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v56 = 64;
        goto LABEL_121;
      }
      v60 = v59 + v84 + 16;
      if ( v60 < 0x10 )
      {
LABEL_148:
        ChannelListBlob = -1073741670;
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v56 = 66;
        goto LABEL_121;
      }
      if ( v60 > 0x40 )
      {
        if ( v60 > 0x100 )
        {
          if ( v60 > 0x400 )
          {
            if ( v60 > 0x800 )
            {
              p_WaitListHead = 0;
              Pool2 = (_DWORD *)ExAllocatePool2(64, v60, 808679286, v54);
LABEL_147:
              if ( Pool2 )
              {
                v62 = v86;
                v53 = (char *)(Pool2 + 4);
                *(_QWORD *)Pool2 = p_WaitListHead;
                v63 = (_WORD *)((char *)v19 + 251);
                Pool2[2] = 808679286;
                v64 = (char *)v19 + 244;
                ChannelListBlob = 0;
                v65 = (char *)v19 + 245;
                memset(Pool2 + 4, 0, v62);
                v66 = v93;
                *(_DWORD *)v53 = 6291840;
                *((_DWORD *)v53 + 1) = *(_DWORD *)v66;
                *((_WORD *)v53 + 4) = *((_WORD *)v66 + 2);
                v53[10] = v81;
                *((_QWORD *)v53 + 2) = v94;
                v67 = v95;
                *((_DWORD *)v53 + 6) = 10000;
                v53[28] = 0;
                if ( v67 )
                  v53[29] = *v67;
                if ( v65 )
                {
                  *((_DWORD *)v53 + 8) = *(_DWORD *)v65;
                  *((_WORD *)v53 + 18) = *((_WORD *)v65 + 2);
                }
                if ( v64 )
                  v53[38] = *v64;
                v68 = v96;
                if ( v96 )
                {
                  *(_OWORD *)(v53 + 40) = *v96;
                  *(_OWORD *)(v53 + 56) = v68[1];
                  *(_OWORD *)(v53 + 68) = *(_OWORD *)((char *)v68 + 28);
                  v53[84] = 1;
                }
                if ( v63 )
                  *((_WORD *)v53 + 15) = *v63;
                v69 = (unsigned int)v89;
                v70 = Src;
                *((_DWORD *)v53 + 22) = 96;
                *((_DWORD *)v53 + 23) = v69 + Size + v84;
                memmove(v53 + 96, v70, Size);
                v71 = (unsigned __int8 *)&v53[Size + 96];
                if ( v91 )
                {
                  memmove(&v53[Size + 96], v91, (unsigned int)v69);
                  v71 += v69;
                }
                v16 = v100;
                if ( !v84 || (ChannelListBlob = WFDRoleGetCachedFrameIEs(v100, 6u, &v84, v71)) == 0 )
                {
                  NdisReleaseRWLock(v16->pRWLock, &Size_4);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                    {
                      v72 = (_DWORD)v53 + 4;
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
                      v72 = (_DWORD)v53 + 4;
                    }
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                    {
                      v73 = "Y";
                      if ( !v53[84] )
                        v73 = "N";
                      WPP_SF__MAC_s_MAC__SSID_DD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        69,
                        (unsigned int)WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                        v72,
                        (__int64)v73,
                        (__int64)(v53 + 40),
                        (__int64)(v53 + 48),
                        *((_DWORD *)v53 + 22),
                        *((_DWORD *)v53 + 23));
                    }
                  }
                  v87 = v86;
                  v80 = (PNPAGED_LOOKASIDE_LIST *)v53;
                  goto LABEL_127;
                }
                v57 = 1;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_123:
                NdisReleaseRWLock(v16->pRWLock, &Size_4);
                if ( v53 && v57 )
                {
                  if ( *((_QWORD *)v53 - 2) )
                    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v53 - 2), v53 - 16);
                  else
                    ExFreePoolWithTag(v53 - 16, *((_DWORD *)v53 - 2));
                }
LABEL_127:
                v49 = v85;
                goto LABEL_111;
              }
              goto LABEL_148;
            }
            p_WaitListHead = &stru_1400B0180;
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
  v16 = v100;
LABEL_103:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, ChannelListBlob);
LABEL_187:
  if ( ChannelListBlob )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 126, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    v10 = v101;
    v14 = 0;
    v15 = v80;
    goto LABEL_9;
  }
  v17 = pRoleExt;
  KeReleaseSpinLock((PKSPIN_LOCK)pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
  v15 = v80;
  v74 = NwifiSetDirectOidRequestAsync(*(struct _ADAPT **)(*(_QWORD *)pVElanExt + 16LL), 235208971, v80, v87);
  if ( v74 == 1076035585 )
    v74 = 0;
  LODWORD(v100) = v74;
  MapPendingDirectOidStatus((int *)&v100);
  ChannelListBlob = (unsigned int)v100;
  if ( !(_DWORD)v100 )
  {
    v79 = 0;
    *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
    if ( (unsigned int)WFDDeviceFindPeerByID((struct _WFD_DEVICE_ROLE *)pRoleExt, a1, &v88) )
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
      v75 = v88;
      if ( (unsigned __int8)WFDPeerDeviceSetState(v88, 25) )
      {
        WFDPeerDeviceQueueTimer(v75, 0x2710u, 0x3E8u);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
             && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          129,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          *((unsigned int *)v75 + 9));
      }
    }
    v10 = v101;
LABEL_10:
    KeReleaseSpinLock((PKSPIN_LOCK)v17 + 149, *((_BYTE *)v17 + 1200));
    if ( !v79 )
      goto LABEL_198;
    goto LABEL_197;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      127,
      WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
      (unsigned int)v100);
  v14 = 0;
  v10 = v101;
LABEL_197:
  WFDDeviceGONegotiationSendUpcallFailure(v16, v92, v18, ChannelListBlob, v10);
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
    v76 = v10;
    if ( !v10 )
      v76 = 5;
    v10 = v76;
  }
  result = v14;
  *a8 = v10;
  return result;
}

```

## disassembly

```asm
0x14008055c  mov     rax, rsp
0x14008055f  mov     [rax+20h], r9
0x140080563  mov     [rax+18h], r8d
0x140080567  mov     [rax+10h], rdx
0x14008056b  mov     [rax+8], ecx
0x14008056e  push    rbp
0x14008056f  push    rbx
0x140080570  push    rsi
0x140080571  push    rdi
0x140080572  push    r12
0x140080574  push    r13
0x140080576  push    r14
0x140080578  push    r15
0x14008057a  lea     rbp, [rax-48h]
0x14008057e  sub     rsp, 108h
0x140080585  mov     rax, [rdx]
0x140080588  xor     r13d, r13d
0x14008058b  mov     r15, [rdx+0B8h]
0x140080592  mov     bl, r13b
0x140080595  mov     r14, r9
0x140080598  mov     [rbp+40h+var_98], r13
0x14008059c  mov     edi, ecx
0x14008059e  mov     [rsp+78h], r13
0x1400805a3  mov     rax, [rax+1F68h]
0x1400805aa  mov     esi, r13d
0x1400805ad  mov     [rbp+40h+var_48], rax
0x1400805b1  mov     byte ptr [rbp+40h+arg_10], bl
0x1400805b4  mov     byte ptr [rsp+140h+var_D0], r13b
0x1400805b9  mov     byte ptr [rsp+140h+var_D0+2], r13b
0x1400805be  mov     [rbp+40h+var_78], r13
0x1400805c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400805c9  lea     r12, WPP_GLOBAL_Control
0x1400805d0  cmp     rcx, r12
0x1400805d3  jz      short loc_1400805E9
0x1400805d5  mov     rcx, [rcx+18h]
0x1400805d9  lea     edx, [r13+72h]
0x1400805dd  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400805e4  call    WPP_SF_
0x1400805e9  lea     rcx, [r15+4A8h]; SpinLock
0x1400805f0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400805f7  nop     dword ptr [rax+rax+00h]
0x1400805fc  lea     r8, [rbp+40h+var_98]; struct _WFD_PEER_DEVICE **
0x140080600  mov     edx, edi; unsigned int
0x140080602  mov     rcx, r15; struct _WFD_DEVICE_ROLE *
0x140080605  mov     [r15+4B0h], al
0x14008060c  call    ?WFDDeviceFindPeerByID@@YAHPEAU_WFD_DEVICE_ROLE@@KPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByID(_WFD_DEVICE_ROLE *,ulong,_WFD_PEER_DEVICE * *)
0x140080611  test    eax, eax
0x140080613  jz      short loc_140080676
0x140080615  mov     esi, 0C0000184h
0x14008061a  mov     rcx, cs:WPP_GLOBAL_Control
0x140080621  cmp     rcx, r12
0x140080624  jz      short loc_14008063E
0x140080626  mov     rcx, [rcx+18h]
0x14008062a  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140080631  mov     edx, 73h ; 's'
0x140080636  mov     r9d, edi
0x140080639  call    WPP_SF_d
0x14008063e  mov     r12b, bl
0x140080641  mov     r14, [rsp+78h]
0x140080646  mov     r13, [rbp+40h+arg_8]
0x14008064a  mov     rdi, r15
0x14008064d  mov     dl, [rdi+4B0h]; NewIrql
0x140080653  lea     rcx, [rdi+4A8h]; SpinLock
0x14008065a  call    cs:__imp_KeReleaseSpinLock
0x140080661  nop     dword ptr [rax+rax+00h]
0x140080666  cmp     byte ptr [rsp+140h+var_D0+2], 0
0x14008066b  jz      loc_140081450
0x140080671  jmp     loc_140081432
0x140080676  mov     rbx, [rbp+40h+var_98]
0x14008067a  mov     edx, 17h
0x14008067f  mov     rcx, rbx
0x140080682  mov     edi, [rbx+24h]
0x140080685  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x14008068a  test    al, al
0x14008068c  jnz     short loc_1400806CD
0x14008068e  mov     esi, 0C0000184h
0x140080693  mov     rcx, cs:WPP_GLOBAL_Control
0x14008069a  cmp     rcx, r12
0x14008069d  jz      short loc_1400806C5
0x14008069f  cmp     byte ptr [rcx+29h], 3
0x1400806a3  jb      short loc_1400806C5
0x1400806a5  bt      dword ptr [rcx+2Ch], 15h
0x1400806aa  jnb     short loc_1400806C5
0x1400806ac  mov     r9d, [rbx+24h]
0x1400806b0  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400806b7  mov     rcx, [rcx+18h]
0x1400806bb  mov     edx, 74h ; 't'
0x1400806c0  call    WPP_SF_d
0x1400806c5  mov     bl, r13b
0x1400806c8  jmp     loc_14008063E
0x1400806cd  mov     rcx, rbx; struct _WFD_PEER_DEVICE *
0x1400806d0  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCancelTimer(_WFD_PEER_DEVICE *)
0x1400806d5  test    eax, eax
0x1400806d7  jnz     short loc_140080719
0x1400806d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400806e0  cmp     rcx, r12
0x1400806e3  jz      short loc_14008070B
0x1400806e5  lea     r12d, [rax+1]
0x1400806e9  cmp     [rcx+29h], r12b
0x1400806ed  jb      short loc_14008070B
0x1400806ef  bt      dword ptr [rcx+2Ch], 15h
0x1400806f4  jnb     short loc_14008070B
0x1400806f6  mov     rcx, [rcx+18h]
0x1400806fa  lea     r9, [rbx+18h]
0x1400806fe  lea     edx, [rax+75h]
0x140080701  mov     qword ptr [rsp+140h+var_120], rbx
0x140080706  call    WPP_SF__MAC_q
0x14008070b  mov     r12b, sil
0x14008070e  mov     bl, sil
0x140080711  mov     r14, rsi
0x140080714  jmp     loc_140080646
0x140080719  mov     rax, [rbx+30h]
0x14008071d  mov     r12d, 1
0x140080723  mov     [rbp+40h+var_78], rax
0x140080727  lea     eax, [rdi-11h]
0x14008072a  mov     byte ptr [rsp+140h+var_D0+2], r12b
0x14008072f  cmp     eax, 3
0x140080732  ja      loc_1400807EC
0x140080738  lea     rdx, [rbx+18h]; Buf2
0x14008073c  lea     rcx, [rbx+0C8h]; Buf1
0x140080743  lea     r8d, [r12+5]; Size
0x140080748  call    memcmp
0x14008074d  test    eax, eax
0x14008074f  jns     loc_1400807EC
0x140080755  mov     rcx, cs:WPP_GLOBAL_Control
0x14008075c  lea     rdi, WPP_GLOBAL_Control
0x140080763  cmp     rcx, rdi
0x140080766  jz      short loc_14008078A
0x140080768  cmp     byte ptr [rcx+29h], 3
0x14008076c  jb      short loc_14008078A
0x14008076e  bt      dword ptr [rcx+2Ch], 15h
0x140080773  jnb     short loc_14008078A
0x140080775  mov     rcx, [rcx+18h]
0x140080779  lea     edx, [r12+75h]
0x14008077e  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140080785  call    WPP_SF_
0x14008078a  mov     r14d, 14h
0x140080790  mov     rcx, rbx
0x140080793  mov     edx, r14d
0x140080796  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x14008079b  test    al, al
0x14008079d  jnz     short loc_1400807CF
0x14008079f  mov     esi, 0C0000184h
0x1400807a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400807ab  cmp     rcx, rdi
0x1400807ae  jz      short loc_1400807C7
0x1400807b0  mov     rcx, [rcx+18h]
0x1400807b4  lea     edx, [r14+63h]
0x1400807b8  mov     r9d, r14d
0x1400807bb  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400807c2  call    WPP_SF_d
0x1400807c7  mov     bl, r13b
0x1400807ca  jmp     loc_140080641
0x1400807cf  mov     edx, 3E8h; unsigned int
0x1400807d4  mov     r8d, 64h ; 'd'; unsigned int
0x1400807da  mov     rcx, rbx; struct _WFD_PEER_DEVICE *
0x1400807dd  call    ?WFDPeerDeviceQueueTimer@@YAXPEAU_WFD_PEER_DEVICE@@KK@Z; WFDPeerDeviceQueueTimer(_WFD_PEER_DEVICE *,ulong,ulong)
0x1400807e2  mov     byte ptr [rsp+140h+var_D0+2], r13b
0x1400807e7  jmp     loc_14008070E
0x1400807ec  mov     al, [r14+0Ah]
0x1400807f0  lea     rcx, [rbx+16Ch]; unsigned __int8 *
0x1400807f7  mov     r13, [rbp+40h+arg_20]
0x1400807fb  mov     [rbx+28h], al
0x1400807fe  lea     rdx, [r13+18h]; struct _WFD_GROUP_CAPABILITY *
0x140080802  call    ?WFDDeviceUpdateGroupCaps@@YAXPEAEPEAU_WFD_GROUP_CAPABILITY@@@Z; WFDDeviceUpdateGroupCaps(uchar *,_WFD_GROUP_CAPABILITY *)
0x140080807  mov     eax, [r13+40h]
0x14008080b  lea     r9, [rbx+1B0h]; unsigned __int8 **
0x140080812  mov     rdx, [rbp+40h+arg_30]; unsigned __int8 *
0x140080819  lea     r8, [rbx+1ACh]; unsigned int *
0x140080820  mov     ecx, [rbp+40h+arg_28]; unsigned int
0x140080823  mov     [rbx+16Dh], eax
0x140080829  movzx   eax, word ptr [r13+44h]
0x14008082e  mov     [rbx+171h], ax
0x140080835  movzx   eax, word ptr [r13+39h]
0x14008083a  mov     [rbx+173h], ax
0x140080841  mov     eax, [r13+80h]
0x140080848  mov     [rbx+177h], eax
0x14008084e  mov     al, [r13+84h]
0x140080855  mov     [rbx+17Bh], al
0x14008085b  or      byte ptr [rbx+17Ch], 4
0x140080862  mov     al, [r13+38h]
0x140080866  mov     [rbx+175h], al
0x14008086c  call    ?WFDDeviceGetChannelListBlob@@YAJKPEAEPEAKPEAPEAE@Z; WFDDeviceGetChannelListBlob(ulong,uchar *,ulong *,uchar * *)
0x140080871  mov     esi, eax
0x140080873  test    eax, eax
0x140080875  jz      short loc_1400808A7
0x140080877  mov     rcx, cs:WPP_GLOBAL_Control
0x14008087e  lea     rax, WPP_GLOBAL_Control
0x140080885  cmp     rcx, rax
0x140080888  jz      short loc_14008089F
0x14008088a  mov     rcx, [rcx+18h]
0x14008088e  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140080895  mov     edx, 78h ; 'x'
0x14008089a  call    WPP_SF_
0x14008089f  mov     bl, byte ptr [rbp+40h+arg_10]
0x1400808a2  jmp     loc_14008063E
0x1400808a7  mov     cl, [rbx+0FDh]
0x1400808ad  lea     r8, [rbx+0FDh]
0x1400808b4  mov     al, [rbx+175h]
0x1400808ba  not     al
0x1400808bc  mov     [rbp+40h+var_60], r8
0x1400808c0  xor     al, cl
0x1400808c2  and     al, r12b
0x1400808c5  xor     al, cl
0x1400808c7  mov     [r8], al
0x1400808ca  xor     dil, dil
0x1400808cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400808d4  lea     r9, WPP_GLOBAL_Control
0x1400808db  cmp     rcx, r9
0x1400808de  jz      short loc_140080903
0x1400808e0  mov     rcx, [rcx+18h]
0x1400808e4  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400808eb  mov     edx, 6Dh ; 'm'
0x1400808f0  call    WPP_SF_
0x1400808f5  lea     r8, [rbx+0FDh]
0x1400808fc  lea     r9, WPP_GLOBAL_Control
0x140080903  mov     dl, [rbx+175h]
0x140080909  lea     r10, aY; "Y"
0x140080910  mov     al, dl
0x140080912  shr     al, 1
0x140080914  cmp     al, 0Fh
0x140080916  jbe     short loc_14008094B
0x140080918  mov     r14b, 4
0x14008091b  mov     byte ptr [rbp+40h+arg_10], r14b
0x14008091f  mov     rcx, cs:WPP_GLOBAL_Control
0x140080926  cmp     rcx, r9
0x140080929  jz      loc_140080A5C
0x14008092f  cmp     [rcx+29h], r12b
0x140080933  jb      loc_1400809E8
0x140080939  bt      dword ptr [rcx+2Ch], 15h
0x14008093e  jnb     loc_1400809E8
0x140080944  mov     edx, 6Eh ; 'n'
0x140080949  jmp     short loc_1400809BD
0x14008094b  mov     cl, [r8]
0x14008094e  xor     r14b, r14b
0x140080951  shr     cl, 1
0x140080953  mov     byte ptr [rbp+40h+arg_10], r14b
0x140080957  cmp     al, cl
0x140080959  jnb     short loc_14008098E
0x14008095b  mov     rcx, cs:WPP_GLOBAL_Control
0x140080962  cmp     rcx, r9
0x140080965  jz      short loc_140080989
0x140080967  cmp     byte ptr [rcx+29h], 3
0x14008096b  jb      short loc_140080989
0x14008096d  bt      dword ptr [rcx+2Ch], 15h
0x140080972  jnb     short loc_140080989
0x140080974  mov     rcx, [rcx+18h]
0x140080978  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008097f  mov     edx, 6Fh ; 'o'
0x140080984  call    WPP_SF_
0x140080989  mov     dil, r12b
0x14008098c  jmp     short loc_1400809DA
0x14008098e  jnz     short loc_1400809DA
0x140080990  cmp     al, 0Fh
0x140080992  jnz     short loc_1400809CF
0x140080994  mov     r14b, 9
0x140080997  mov     byte ptr [rbp+40h+arg_10], r14b
0x14008099b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400809a2  cmp     rcx, r9
0x1400809a5  jz      loc_140080A5C
0x1400809ab  cmp     [rcx+29h], r12b
0x1400809af  jb      short loc_1400809DA
0x1400809b1  bt      dword ptr [rcx+2Ch], 15h
0x1400809b6  jnb     short loc_1400809DA
0x1400809b8  mov     edx, 70h ; 'p'
0x1400809bd  mov     rcx, [rcx+18h]
0x1400809c1  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400809c8  call    WPP_SF_
0x1400809cd  jmp     short loc_1400809DA
0x1400809cf  test    r12b, dl
0x1400809d2  movzx   edi, dil
0x1400809d6  cmovz   edi, r12d
0x1400809da  lea     r9, WPP_GLOBAL_Control
0x1400809e1  lea     r10, aY; "Y"
0x1400809e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400809ef  cmp     rcx, r9
0x1400809f2  jz      short loc_140080A5C
0x1400809f4  cmp     byte ptr [rcx+29h], 3
0x1400809f8  jb      short loc_140080A5C
0x1400809fa  bt      dword ptr [rcx+2Ch], 15h
0x1400809ff  jnb     short loc_140080A5C
0x140080a01  movzx   r11d, byte ptr [rbx+175h]
0x140080a09  lea     rax, aN; "N"
0x140080a10  movzx   r9d, byte ptr [rbx+0FDh]
0x140080a18  mov     r8d, r11d
0x140080a1b  mov     rcx, [rcx+18h]
0x140080a1f  test    dil, dil
0x140080a22  movzx   edx, r14b
0x140080a26  cmovz   r10, rax
0x140080a2a  mov     eax, r9d
0x140080a2d  mov     qword ptr [rsp+140h+var_100], r10
0x140080a32  and     r8d, r12d
0x140080a35  mov     dword ptr [rsp+140h+var_108], edx
0x140080a39  and     eax, r12d
0x140080a3c  mov     [rsp+140h+var_110], r8d
0x140080a41  shr     r11d, 1
0x140080a44  mov     dword ptr [rsp+140h+var_118], r11d
0x140080a49  shr     r9d, 1
0x140080a4c  mov     dword ptr [rsp+140h+var_120], eax
0x140080a50  call    WPP_SF_DDDDDs
  ... truncated ...
```

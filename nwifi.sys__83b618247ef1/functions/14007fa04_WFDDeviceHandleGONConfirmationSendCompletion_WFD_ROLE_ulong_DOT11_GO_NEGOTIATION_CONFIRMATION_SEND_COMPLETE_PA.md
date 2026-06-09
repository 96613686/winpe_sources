# WFDDeviceHandleGONConfirmationSendCompletion(_WFD_ROLE *,ulong,_DOT11_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE_PARAMETERS *)

- ea: `0x14007fa04`
- end: `0x140080553`
- name: `?WFDDeviceHandleGONConfirmationSendCompletion@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE_PARAMETERS@@@Z`
- size: `2895`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007c000`

## callees

- `0x14000170c`
- `0x14000d22c`
- `0x14000d2c0`
- `0x140020dc0`
- `0x140020f20`
- `0x140022f08`
- `0x14003ae2c`
- `0x14003d814`
- `0x14007f5cc`
- `0x14007f60c`
- `0x14007fa04`
- `0x140089588`
- `0x14008a780`
- `0x14008af58`
- `0x14008bd7c`
- `0x14008c0e8`
- `0x14008c5a8`
- `0x14008c60c`
- `0x14008d3c0`
- `0x140097438`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007fb34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080121`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007fb34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080121`
- `ntoskrnl!ExAllocatePool2` at `0x140080139`
- `ntoskrnl!ExAllocatePool2` at `0x140080139`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008043d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008047a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008043d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008047a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008044e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080492`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008044e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080492`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400803d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400803d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007fd72`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007fd72`

## pseudocode

```c
void __fastcall WFDDeviceHandleGONConfirmationSendCompletion(
        struct _WFD_ROLE *a1,
        unsigned int a2,
        struct _DOT11_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE_PARAMETERS *a3)
{
  struct _DOT11_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE_PARAMETERS *v3; // rdi
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // r14d
  __int64 v9; // rsi
  char *pRoleExt; // r13
  _DWORD *v11; // rax
  PNPAGED_LOOKASIDE_LIST *v12; // r15
  char *v13; // rbx
  char *v14; // r12
  int PeerByMAC; // ebx
  char *v16; // r15
  const char *v17; // r8
  int v18; // eax
  const char *v19; // r13
  const char *v20; // r14
  char v21; // r15
  const char *v22; // rbp
  char v23; // r12
  const char *v24; // rsi
  const char *v25; // rdi
  const char *v26; // r11
  bool v27; // zf
  const char *v28; // rbx
  PDEVICE_OBJECT v29; // r14
  size_t v30; // r13
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r8
  size_t v34; // r14
  size_t v35; // rsi
  unsigned int v36; // eax
  unsigned int v37; // edi
  unsigned int v38; // r8d
  int v39; // edi
  PDEVICE_OBJECT v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r9
  unsigned int v43; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  char *v46; // rbx
  char *v47; // rbx
  void *v48; // rdx
  void *v49; // rdx
  unsigned int v50; // eax
  const char *v51; // r12
  int v52; // r8d
  __int64 v53; // [rsp+88h] [rbp-90h]
  unsigned int Size; // [rsp+90h] [rbp-88h]
  size_t v55; // [rsp+98h] [rbp-80h] BYREF
  unsigned int v56; // [rsp+A0h] [rbp-78h]
  PDEVICE_OBJECT v57; // [rsp+A8h] [rbp-70h]
  char *v58; // [rsp+B0h] [rbp-68h]
  void *v59; // [rsp+B8h] [rbp-60h]
  PNPAGED_LOOKASIDE_LIST *v60; // [rsp+C0h] [rbp-58h]
  void *v61; // [rsp+C8h] [rbp-50h]
  void *Src; // [rsp+D0h] [rbp-48h]
  char v65; // [rsp+130h] [rbp+18h]
  int v66; // [rsp+138h] [rbp+20h] BYREF

  v3 = a3;
  v55 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 170, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF__MAC_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        171,
        *((unsigned __int8 *)v3 + 10),
        (char *)v3 + 4,
        *((unsigned __int8 *)v3 + 10),
        *((_DWORD *)v3 + 3));
    }
  }
  if ( (unsigned int)dword_1400AE050 >= 6 && (unsigned __int8)tlgKeywordOn(&dword_1400AE050, 0x200000000000LL) )
  {
    v66 = *((_DWORD *)v3 + 3);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1400AE050,
      (unsigned int)byte_1400A5571,
      v6,
      v7,
      (__int64)&v66);
  }
  v8 = *((_DWORD *)v3 + 5);
  v9 = *((unsigned int *)v3 + 4);
  if ( v8 && (unsigned int)v9 < 0x18 || v8 + (unsigned int)v9 < (unsigned int)v9 || v8 + (unsigned int)v9 > a2 )
  {
    PeerByMAC = -1073676267;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        172,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        (unsigned int)v9,
        v8,
        v8 + v9,
        a2);
    }
    goto LABEL_142;
  }
  pRoleExt = (char *)a1->pRoleExt;
  v61 = pRoleExt;
  v11 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  v60 = (PNPAGED_LOOKASIDE_LIST *)v11;
  v12 = (PNPAGED_LOOKASIDE_LIST *)v11;
  if ( v11 )
  {
    *(_QWORD *)v11 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    v13 = (char *)(v11 + 4);
    v11[2] = 808679286;
    v14 = (char *)v3 + v9;
    v58 = (char *)(v11 + 4);
    Src = (char *)v3 + v9;
    memset(v11 + 4, 0, 0x74u);
    if ( !WFDValidateIncomingGONegotiationConfirmationIEs((unsigned __int8 *)v3 + v9, v8, v13) )
    {
      PeerByMAC = -1073676267;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 174, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      }
LABEL_132:
      if ( v12 != (PNPAGED_LOOKASIDE_LIST *)-16LL )
      {
        if ( *v12 )
          ExFreeToNPagedLookasideList(*v12, v12);
        else
          ExFreePoolWithTag(v12, *((_DWORD *)v12 + 2));
      }
      goto LABEL_142;
    }
    v16 = 0;
    LOBYTE(v66) = 0;
    v59 = 0;
    v56 = 0;
    v17 = "Y";
    v57 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      v18 = *((_DWORD *)v13 + 9);
      v19 = "Y";
      if ( (v13[112] & 1) == 0 )
        v19 = "N";
      v20 = "Y";
      v21 = v13[64];
      v22 = "Y";
      v23 = v13[63];
      if ( !*((_DWORD *)v13 + 13) )
        v20 = "N";
      v24 = "Y";
      v53 = (__int64)(v13 + 76);
      v25 = "Y";
      if ( !*((_DWORD *)v13 + 12) )
        v22 = "N";
      v26 = "Y";
      if ( !*((_DWORD *)v13 + 11) )
        v24 = "N";
      v27 = *((_DWORD *)v13 + 10) == 0;
      v28 = "Y";
      if ( v27 )
        v25 = "N";
      if ( !v18 )
        v28 = "N";
      if ( !*((_DWORD *)v58 + 8) )
        v26 = "N";
      if ( !*((_DWORD *)v58 + 7) )
        v17 = "N";
      WPP_SF__MAC_DcsssssssDDs_MAC__SSID_(
        v57->AttachedDevice,
        175,
        (_DWORD)v17,
        (_DWORD)a3 + 4,
        *((_BYTE *)a3 + 10),
        *v58,
        (__int64)v17,
        (__int64)v26,
        (__int64)v28,
        (__int64)v25,
        (__int64)v24,
        (__int64)v22,
        (__int64)v20,
        v23,
        v21,
        (__int64)v19,
        (__int64)(v58 + 68),
        v53);
      v16 = 0;
      v3 = a3;
      pRoleExt = (char *)v61;
      v14 = (char *)Src;
    }
    v29 = (PDEVICE_OBJECT)(pRoleExt + 1192);
    v57 = (PDEVICE_OBJECT)(pRoleExt + 1192);
    pRoleExt[1200] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
    PeerByMAC = WFDDeviceFindPeerByMAC(
                  (struct _WFD_DEVICE_ROLE *)pRoleExt,
                  (unsigned __int8 (*)[6])((char *)v3 + 4),
                  (struct _WFD_PEER_DEVICE **)&v55);
    if ( PeerByMAC )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_(
          WPP_GLOBAL_Control->AttachedDevice,
          176,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          (char *)v3 + 4);
      goto LABEL_123;
    }
    v30 = v55;
    if ( *(_BYTE *)(v55 + 40) != *((_BYTE *)v3 + 10) )
    {
      PeerByMAC = -1073741436;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          177,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          *(unsigned __int8 *)(v55 + 40),
          *((unsigned __int8 *)v3 + 10));
      goto LABEL_123;
    }
    if ( !(unsigned __int8)WFDPeerDeviceSetState(v55, 31) )
    {
      PeerByMAC = -1073741436;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 178, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, 19);
      }
      goto LABEL_123;
    }
    if ( !(unsigned int)WFDPeerDeviceCancelTimer((struct _WFD_PEER_DEVICE *)v30) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer)
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF__MAC_q(WPP_GLOBAL_Control->AttachedDevice, 179, v31, v30 + 24, v30);
      }
      goto LABEL_123;
    }
    v33 = *((unsigned int *)v3 + 3);
    v59 = *(void **)(v30 + 48);
    LOBYTE(v66) = 1;
    if ( (_DWORD)v33 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer)
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF__MAC_dq(WPP_GLOBAL_Control->AttachedDevice, 180, v33, (char *)v3 + 4, v33, v30);
      }
      PeerByMAC = *((_DWORD *)v3 + 3);
      if ( PeerByMAC < 0 )
      {
LABEL_122:
        WFDPeerDeviceDestroy((struct _WFD_PEER_DEVICE *)v30);
LABEL_123:
        KeReleaseSpinLock((PKSPIN_LOCK)v29, (KIRQL)v29->DriverObject);
        if ( (_BYTE)v66 )
        {
          if ( PeerByMAC )
            WFDDeviceGONegotiationSendUpcallFailure(a1, v59, v52, PeerByMAC, 0);
          else
            WFDDeviceSendUpCallRequest(a1->pGenVElan->pVElanExt, 20, v16);
        }
        if ( v16 )
        {
          if ( *((_QWORD *)v16 - 2) )
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v16 - 2), v16 - 16);
          else
            ExFreePoolWithTag(v16 - 16, *((_DWORD *)v16 - 2));
        }
        v12 = v60;
        goto LABEL_132;
      }
    }
    if ( *v58 )
    {
      PeerByMAC = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 181, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_122;
    }
    v34 = v30 + 200;
    v65 = *(_BYTE *)(v30 + 192);
    if ( !v65 )
      v34 = v30 + 320;
    v35 = *((unsigned int *)v3 + 5);
    v61 = *(void **)(v30 + 432);
    v36 = *(_DWORD *)(v30 + 428);
    LODWORD(v55) = v36;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      v36 = v55;
    }
    if ( v14 )
    {
      if ( (_DWORD)v35 )
      {
        v37 = v35 + 96;
        if ( (unsigned int)v35 >= 0xFFFFFFA0 )
        {
          PeerByMAC = -1073741675;
          v39 = -1073741675;
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v41 = 82;
            v42 = (unsigned int)v35;
            goto LABEL_80;
          }
LABEL_96:
          PeerByMAC = v39;
LABEL_97:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 182, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_121:
          v29 = v57;
          goto LABEL_122;
        }
LABEL_71:
        v38 = v37 + v36;
        Size = v37 + v36;
        if ( v37 + v36 < v37 )
        {
          PeerByMAC = -1073741675;
          v39 = -1073741675;
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v41 = 83;
            v42 = v36;
LABEL_80:
            WPP_SF_Dd(v40->AttachedDevice, v41, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v42, -1);
            goto LABEL_97;
          }
          goto LABEL_96;
        }
        v43 = v38 + 16;
        if ( v38 >= 0xFFFFFFF0 )
        {
LABEL_94:
          v39 = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              85,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              v38,
              -1073741670);
          goto LABEL_96;
        }
        if ( v43 > 0x40 )
        {
          if ( v43 > 0x100 )
          {
            if ( v43 > 0x400 )
            {
              if ( v43 > 0x800 )
              {
                p_WaitListHead = 0;
                Pool2 = (_DWORD *)ExAllocatePool2(64, v43, 808679286, v32);
                goto LABEL_92;
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
LABEL_92:
        if ( Pool2 )
        {
          v16 = (char *)(Pool2 + 4);
          *(_QWORD *)Pool2 = p_WaitListHead;
          v46 = v58;
          Pool2[2] = 808679286;
          v47 = v46 + 60;
          memset(Pool2 + 4, 0, Size);
          *(_QWORD *)v16 = v59;
          *((_QWORD *)v16 + 1) = 0;
          v16[17] = (v65 != 0) + 1;
          v16[16] = 0;
          if ( v30 != -365 )
          {
            *((_DWORD *)v16 + 16) = *(_DWORD *)(v30 + 365);
            *((_WORD *)v16 + 34) = *(_WORD *)(v30 + 369);
          }
          if ( v47 )
          {
            *(_WORD *)(v16 + 71) = *(_WORD *)v47;
            v16[73] = v47[2];
            v16[74] = v47[3];
            v16[75] = v47[4];
            v16[76] |= 1u;
          }
          if ( v34 )
          {
            *(_OWORD *)(v16 + 20) = *(_OWORD *)v34;
            *(_OWORD *)(v16 + 36) = *(_OWORD *)(v34 + 16);
            *((_OWORD *)v16 + 3) = *(_OWORD *)(v34 + 28);
          }
          if ( v30 != -371 )
            *(_WORD *)(v16 + 77) = *(_WORD *)(v30 + 371);
          if ( v34 != -44 )
            v16[70] = *(_BYTE *)(v34 + 44);
          v48 = Src;
          *((_DWORD *)v16 + 20) = 96;
          *((_DWORD *)v16 + 21) = v35;
          if ( v48 )
            memmove(v16 + 96, v48, v35);
          v49 = v61;
          if ( v61 )
          {
            v50 = v55;
            if ( (_DWORD)v55 )
            {
              *((_DWORD *)v16 + 22) = v37;
              *((_DWORD *)v16 + 23) = v50;
              memmove(&v16[v37], v49, v50);
            }
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
          {
            v51 = "Y";
            if ( !*((_DWORD *)v16 + 2) )
              v51 = "N";
            WPP_SF_qsdDD_MAC__SSID__MAC_DDDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              (unsigned __int8)v16[78],
              (unsigned __int8)v16[77],
              *(_QWORD *)v16,
              (__int64)v51,
              *((_DWORD *)v16 + 3),
              v16[16],
              v16[17],
              (__int64)(v16 + 20),
              (__int64)(v16 + 28),
              (__int64)(v16 + 64),
              v16[70],
              v16[74],
              v16[75],
              v16[77],
              v16[78]);
          }
          v56 = Size;
          PeerByMAC = 0;
          goto LABEL_121;
        }
        v38 = Size;
        goto LABEL_94;
      }
    }
    else if ( !(_DWORD)v35 )
    {
      v37 = 96;
      goto LABEL_71;
    }
    PeerByMAC = -1073741811;
    v39 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_97;
    }
    goto LABEL_96;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return;
  PeerByMAC = -1073741670;
  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 173, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_142:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      183,
      WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
      (unsigned int)PeerByMAC);
}

```

## disassembly

```asm
0x14007fa04  mov     rax, rsp
0x14007fa07  mov     [rax+10h], rbx
0x14007fa0b  mov     [rax+18h], r8
0x14007fa0f  mov     [rax+8], rcx
0x14007fa13  push    rbp
0x14007fa14  push    rsi
0x14007fa15  push    rdi
0x14007fa16  push    r12
0x14007fa18  push    r13
0x14007fa1a  push    r14
0x14007fa1c  push    r15
0x14007fa1e  sub     rsp, 0E0h
0x14007fa25  mov     rdi, r8
0x14007fa28  mov     qword ptr [rax-80h], 0
0x14007fa30  mov     ebp, edx
0x14007fa32  mov     rbx, rcx
0x14007fa35  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fa3c  lea     r12, WPP_GLOBAL_Control
0x14007fa43  cmp     rcx, r12
0x14007fa46  jz      short loc_14007FA99
0x14007fa48  mov     rcx, [rcx+18h]
0x14007fa4c  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007fa53  mov     edx, 0AAh
0x14007fa58  call    WPP_SF_
0x14007fa5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fa64  cmp     rcx, r12
0x14007fa67  jz      short loc_14007FA99
0x14007fa69  cmp     byte ptr [rcx+29h], 3
0x14007fa6d  jb      short loc_14007FA99
0x14007fa6f  bt      dword ptr [rcx+2Ch], 15h
0x14007fa74  jnb     short loc_14007FA99
0x14007fa76  movzx   r8d, byte ptr [rdi+0Ah]
0x14007fa7b  lea     r9, [rdi+4]
0x14007fa7f  mov     eax, [rdi+0Ch]
0x14007fa82  mov     edx, 0ABh
0x14007fa87  mov     rcx, [rcx+18h]
0x14007fa8b  mov     dword ptr [rsp+118h+var_F0], eax
0x14007fa8f  mov     dword ptr [rsp+118h+var_F8], r8d
0x14007fa94  call    WPP_SF__MAC_Dd
0x14007fa99  mov     eax, cs:dword_1400AE050
0x14007fa9f  test    eax, eax
0x14007faa1  jz      short loc_14007FAF2
0x14007faa3  mov     eax, cs:dword_1400AE050
0x14007faa9  cmp     eax, 5
0x14007faac  jbe     short loc_14007FAF2
0x14007faae  mov     rdx, 200000000000h
0x14007fab8  lea     rcx, dword_1400AE050
0x14007fabf  call    _tlgKeywordOn
0x14007fac4  test    al, al
0x14007fac6  jz      short loc_14007FAF2
0x14007fac8  mov     eax, [rdi+0Ch]
0x14007facb  lea     rdx, byte_1400A5571
0x14007fad2  mov     [rsp+118h+arg_18], eax
0x14007fad9  lea     rcx, dword_1400AE050
0x14007fae0  lea     rax, [rsp+118h+arg_18]
0x14007fae8  mov     qword ptr [rsp+118h+var_F8], rax
0x14007faed  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x14007faf2  mov     r14d, [rdi+14h]
0x14007faf6  mov     esi, [rdi+10h]
0x14007faf9  test    r14d, r14d
0x14007fafc  jz      short loc_14007FB07
0x14007fafe  cmp     esi, 18h
0x14007fb01  jb      loc_1400804CC
0x14007fb07  lea     eax, [r14+rsi]
0x14007fb0b  cmp     eax, esi
0x14007fb0d  jb      loc_1400804CC
0x14007fb13  cmp     eax, ebp
0x14007fb15  ja      loc_1400804CC
0x14007fb1b  mov     r13, [rbx+0B8h]
0x14007fb22  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007fb29  mov     rcx, rbx; Lookaside
0x14007fb2c  mov     [rsp+118h+var_50], r13
0x14007fb34  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007fb3b  nop     dword ptr [rax+rax+00h]
0x14007fb40  mov     [rsp+118h+var_58], rax
0x14007fb48  mov     r15, rax
0x14007fb4b  test    rax, rax
0x14007fb4e  jz      loc_1400804A0
0x14007fb54  xor     edx, edx; Val
0x14007fb56  mov     [rax], rbx
0x14007fb59  lea     rbx, [rax+10h]
0x14007fb5d  mov     dword ptr [rax+8], 30337776h
0x14007fb64  lea     r12, [rdi+rsi]
0x14007fb68  mov     [rsp+118h+var_68], rbx
0x14007fb70  mov     rcx, rbx; void *
0x14007fb73  mov     [rsp+118h+Src], r12
0x14007fb7b  lea     r8d, [rdx+74h]; Size
0x14007fb7f  call    memset
0x14007fb84  mov     r8, rbx; void *
0x14007fb87  mov     edx, r14d; unsigned int
0x14007fb8a  mov     rcx, r12; unsigned __int8 *
0x14007fb8d  call    WFDValidateIncomingGONegotiationConfirmationIEs
0x14007fb92  test    al, al
0x14007fb94  jnz     short loc_14007FBE3
0x14007fb96  mov     ebx, 0C0010015h
0x14007fb9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fba2  lea     r12, WPP_GLOBAL_Control
0x14007fba9  cmp     rcx, r12
0x14007fbac  jz      loc_140080462
0x14007fbb2  cmp     byte ptr [rcx+29h], 2
0x14007fbb6  jb      loc_140080462
0x14007fbbc  test    dword ptr [rcx+2Ch], 200000h
0x14007fbc3  jz      loc_140080462
0x14007fbc9  mov     rcx, [rcx+18h]
0x14007fbcd  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007fbd4  mov     edx, 0AEh
0x14007fbd9  call    WPP_SF_
0x14007fbde  jmp     loc_140080462
0x14007fbe3  mov     rax, cs:WPP_GLOBAL_Control
0x14007fbea  lea     rcx, WPP_GLOBAL_Control
0x14007fbf1  xor     r15d, r15d
0x14007fbf4  mov     byte ptr [rsp+118h+arg_18], 0
0x14007fbfc  mov     [rsp+118h+var_60], 0
0x14007fc08  mov     bpl, 1
0x14007fc0b  mov     [rsp+118h+Size], r15
0x14007fc13  lea     r9, aN; "N"
0x14007fc1a  mov     [rsp+118h+var_78], r15d
0x14007fc22  lea     r8, aY; "Y"
0x14007fc29  mov     [rsp+118h+var_70], rax
0x14007fc31  cmp     rax, rcx
0x14007fc34  jz      loc_14007FD60
0x14007fc3a  cmp     byte ptr [rax+29h], 4
0x14007fc3e  jb      loc_14007FD60
0x14007fc44  test    dword ptr [rax+2Ch], 200000h
0x14007fc4b  jz      loc_14007FD60
0x14007fc51  test    [rbx+70h], bpl
0x14007fc55  lea     rcx, [rbx+4Ch]
0x14007fc59  mov     eax, [rbx+24h]
0x14007fc5c  mov     r13, r8
0x14007fc5f  mov     rdx, [rsp+118h+var_68]
0x14007fc67  cmovz   r13, r9
0x14007fc6b  cmp     dword ptr [rbx+34h], 0
0x14007fc6f  mov     r14, r8
0x14007fc72  movzx   r15d, byte ptr [rbx+40h]
0x14007fc77  mov     rbp, r8
0x14007fc7a  movzx   r12d, byte ptr [rbx+3Fh]
0x14007fc7f  cmovz   r14, r9
0x14007fc83  cmp     dword ptr [rbx+30h], 0
0x14007fc87  mov     rsi, r8
0x14007fc8a  mov     [rsp+118h+var_90], rcx
0x14007fc92  mov     rdi, r8
0x14007fc95  mov     rcx, [rsp+118h+var_68]
0x14007fc9d  cmovz   rbp, r9
0x14007fca1  cmp     dword ptr [rbx+2Ch], 0
0x14007fca5  mov     r11, r8
0x14007fca8  cmovz   rsi, r9
0x14007fcac  cmp     dword ptr [rbx+28h], 0
0x14007fcb0  mov     rbx, r8
0x14007fcb3  cmovz   rdi, r9
0x14007fcb7  test    eax, eax
0x14007fcb9  lea     rax, [rcx+44h]
0x14007fcbd  mov     [rsp+118h+var_98], rax
0x14007fcc5  cmovz   rbx, r9
0x14007fcc9  cmp     dword ptr [rdx+20h], 0
0x14007fccd  mov     al, [rcx]
0x14007fccf  mov     rcx, [rsp+118h+var_70]
0x14007fcd7  cmovz   r11, r9
0x14007fcdb  cmp     dword ptr [rdx+1Ch], 0
0x14007fcdf  mov     edx, 0AFh
0x14007fce4  mov     [rsp+118h+var_A0], r13
0x14007fce9  mov     [rsp+118h+var_A8], r15d
0x14007fcee  cmovz   r8, r9
0x14007fcf2  mov     r9, [rsp+118h+arg_10]
0x14007fcfa  mov     rcx, [rcx+18h]
0x14007fcfe  mov     [rsp+118h+var_B0], r12d
0x14007fd03  mov     [rsp+118h+var_B8], r14
0x14007fd08  movzx   r10d, byte ptr [r9+0Ah]
0x14007fd0d  add     r9, 4
0x14007fd11  mov     [rsp+118h+var_C0], rbp
0x14007fd16  mov     [rsp+118h+var_C8], rsi
0x14007fd1b  mov     [rsp+118h+var_D0], rdi
0x14007fd20  mov     [rsp+118h+var_D8], rbx
0x14007fd25  mov     [rsp+118h+var_E0], r11
0x14007fd2a  mov     [rsp+118h+var_E8], r8
0x14007fd2f  mov     byte ptr [rsp+118h+var_F0], al
0x14007fd33  mov     dword ptr [rsp+118h+var_F8], r10d
0x14007fd38  call    WPP_SF__MAC_DcsssssssDDs_MAC__SSID_
0x14007fd3d  mov     r15, [rsp+118h+Size]
0x14007fd45  mov     bpl, 1
0x14007fd48  mov     rdi, [rsp+118h+arg_10]
0x14007fd50  mov     r13, [rsp+118h+var_50]
0x14007fd58  mov     r12, [rsp+118h+Src]
0x14007fd60  lea     r14, [r13+4A8h]
0x14007fd67  mov     rcx, r14; SpinLock
0x14007fd6a  mov     [rsp+118h+var_70], r14
0x14007fd72  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007fd79  nop     dword ptr [rax+rax+00h]
0x14007fd7e  lea     rsi, [rdi+4]
0x14007fd82  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x14007fd85  lea     r8, [rsp+118h+var_80]; struct _WFD_PEER_DEVICE **
0x14007fd8d  mov     [r13+4B0h], al
0x14007fd94  mov     rdx, rsi; unsigned __int8 (*)[6]
0x14007fd97  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x14007fd9c  mov     ebx, eax
0x14007fd9e  test    eax, eax
0x14007fda0  jz      short loc_14007FDD6
0x14007fda2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fda9  lea     r12, WPP_GLOBAL_Control
0x14007fdb0  cmp     rcx, r12
0x14007fdb3  jz      loc_1400803C9
0x14007fdb9  mov     rcx, [rcx+18h]
0x14007fdbd  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007fdc4  mov     edx, 0B0h
0x14007fdc9  mov     r9, rsi
0x14007fdcc  call    WPP_SF__MAC_
0x14007fdd1  jmp     loc_1400803C9
0x14007fdd6  mov     r13, [rsp+118h+var_80]
0x14007fdde  movzx   eax, byte ptr [rdi+0Ah]
0x14007fde2  movzx   edx, byte ptr [r13+28h]
0x14007fde7  cmp     dl, al
0x14007fde9  jz      short loc_14007FE28
0x14007fdeb  mov     ebx, 0C0000184h
0x14007fdf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fdf7  lea     r12, WPP_GLOBAL_Control
0x14007fdfe  cmp     rcx, r12
0x14007fe01  jz      loc_1400803C9
0x14007fe07  mov     rcx, [rcx+18h]
0x14007fe0b  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007fe12  mov     r9d, edx
0x14007fe15  mov     dword ptr [rsp+118h+var_F8], eax
0x14007fe19  mov     edx, 0B1h
0x14007fe1e  call    WPP_SF_Dd
0x14007fe23  jmp     loc_1400803C9
0x14007fe28  mov     edx, 1Fh
0x14007fe2d  mov     rcx, r13
0x14007fe30  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x14007fe35  test    al, al
0x14007fe37  jnz     short loc_14007FE8C
0x14007fe39  mov     ebx, 0C0000184h
0x14007fe3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fe45  lea     r12, WPP_GLOBAL_Control
0x14007fe4c  cmp     rcx, r12
0x14007fe4f  jz      loc_1400803C9
0x14007fe55  cmp     byte ptr [rcx+29h], 3
0x14007fe59  jb      loc_1400803C9
0x14007fe5f  test    dword ptr [rcx+2Ch], 200000h
0x14007fe66  jz      loc_1400803C9
0x14007fe6c  mov     rcx, [rcx+18h]
0x14007fe70  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007fe77  mov     edx, 0B2h
0x14007fe7c  mov     r9d, 13h
0x14007fe82  call    WPP_SF_d
0x14007fe87  jmp     loc_1400803C9
0x14007fe8c  mov     rcx, r13; struct _WFD_PEER_DEVICE *
0x14007fe8f  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCancelTimer(_WFD_PEER_DEVICE *)
0x14007fe94  test    eax, eax
0x14007fe96  jnz     short loc_14007FEE2
0x14007fe98  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fe9f  lea     r12, WPP_GLOBAL_Control
0x14007fea6  cmp     rcx, r12
0x14007fea9  jz      loc_1400803C9
0x14007feaf  cmp     [rcx+29h], bpl
0x14007feb3  jb      loc_1400803C9
0x14007feb9  test    dword ptr [rcx+2Ch], 200000h
0x14007fec0  jz      loc_1400803C9
0x14007fec6  mov     rcx, [rcx+18h]
0x14007feca  lea     r9, [r13+18h]
0x14007fece  mov     edx, 0B3h
0x14007fed3  mov     qword ptr [rsp+118h+var_F8], r13
0x14007fed8  call    WPP_SF__MAC_q
0x14007fedd  jmp     loc_1400803C9
0x14007fee2  mov     rax, [r13+30h]
0x14007fee6  mov     r8d, [rdi+0Ch]
0x14007feea  mov     [rsp+118h+var_60], rax
0x14007fef2  mov     byte ptr [rsp+118h+arg_18], bpl
0x14007fefa  test    r8d, r8d
0x14007fefd  jz      short loc_14007FF4F
0x14007feff  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ff06  lea     rax, WPP_GLOBAL_Control
0x14007ff0d  cmp     rcx, rax
0x14007ff10  jz      short loc_14007FF3C
0x14007ff12  cmp     [rcx+29h], bpl
0x14007ff16  jb      short loc_14007FF3C
0x14007ff18  test    dword ptr [rcx+2Ch], 200000h
0x14007ff1f  jz      short loc_14007FF3C
0x14007ff21  mov     rcx, [rcx+18h]
0x14007ff25  mov     edx, 0B4h
0x14007ff2a  mov     [rsp+118h+var_F0], r13
0x14007ff2f  mov     r9, rsi
0x14007ff32  mov     dword ptr [rsp+118h+var_F8], r8d
0x14007ff37  call    WPP_SF__MAC_dq
0x14007ff3c  mov     ebx, [rdi+0Ch]
0x14007ff3f  test    ebx, ebx
0x14007ff41  jns     short loc_14007FF4F
0x14007ff43  lea     r12, WPP_GLOBAL_Control
0x14007ff4a  jmp     loc_1400803C1
0x14007ff4f  mov     rax, [rsp+118h+var_68]
0x14007ff57  cmp     byte ptr [rax], 0
0x14007ff5a  jz      short loc_14007FF92
0x14007ff5c  mov     ebx, 0C000000Dh
0x14007ff61  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ff68  lea     r12, WPP_GLOBAL_Control
0x14007ff6f  cmp     rcx, r12
0x14007ff72  jz      loc_1400803C1
0x14007ff78  mov     rcx, [rcx+18h]
0x14007ff7c  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007ff83  mov     edx, 0B5h
0x14007ff88  call    WPP_SF_
0x14007ff8d  jmp     loc_1400803C1
0x14007ff92  mov     al, [r13+0C0h]
  ... truncated ...
```

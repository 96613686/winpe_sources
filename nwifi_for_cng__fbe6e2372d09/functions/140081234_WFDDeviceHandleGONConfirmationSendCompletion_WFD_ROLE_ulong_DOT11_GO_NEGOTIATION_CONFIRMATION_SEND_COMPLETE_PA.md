# WFDDeviceHandleGONConfirmationSendCompletion(_WFD_ROLE *,ulong,_DOT11_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE_PARAMETERS *)

- ea: `0x140081234`
- end: `0x140081d83`
- name: `?WFDDeviceHandleGONConfirmationSendCompletion@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE_PARAMETERS@@@Z`
- size: `2895`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_GO_NEGOTIATION_CONFIRMATION_SEND_COMPLETE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007d830`

## callees

- `0x14000170c`
- `0x14000d21c`
- `0x14000d2b0`
- `0x140020dc0`
- `0x140020f20`
- `0x140022f08`
- `0x14003b04c`
- `0x14003da34`
- `0x140080dfc`
- `0x140080e3c`
- `0x140081234`
- `0x14008adb8`
- `0x14008bfb0`
- `0x14008c788`
- `0x14008d5ac`
- `0x14008d918`
- `0x14008ddd8`
- `0x14008de3c`
- `0x14008ebf0`
- `0x140098c18`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140081364`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140081951`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140081364`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140081951`
- `ntoskrnl!ExAllocatePool2` at `0x140081969`
- `ntoskrnl!ExAllocatePool2` at `0x140081969`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140081c6d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140081caa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140081c6d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140081caa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081c7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081cc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081c7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081cc2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081c00`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081c00`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400815a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400815a2`

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
  __int64 v32; // r8
  size_t v33; // r14
  size_t v34; // rsi
  unsigned int v35; // eax
  unsigned int v36; // edi
  unsigned int v37; // r8d
  int v38; // edi
  PDEVICE_OBJECT v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r9
  unsigned int v42; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  char *v45; // rbx
  char *v46; // rbx
  void *v47; // rdx
  void *v48; // rdx
  unsigned int v49; // eax
  const char *v50; // r12
  int v51; // r8d
  __int64 v52; // [rsp+88h] [rbp-90h]
  unsigned int Size; // [rsp+90h] [rbp-88h]
  size_t v54; // [rsp+98h] [rbp-80h] BYREF
  unsigned int v55; // [rsp+A0h] [rbp-78h]
  PDEVICE_OBJECT v56; // [rsp+A8h] [rbp-70h]
  char *v57; // [rsp+B0h] [rbp-68h]
  void *v58; // [rsp+B8h] [rbp-60h]
  PNPAGED_LOOKASIDE_LIST *v59; // [rsp+C0h] [rbp-58h]
  void *v60; // [rsp+C8h] [rbp-50h]
  void *Src; // [rsp+D0h] [rbp-48h]
  char v64; // [rsp+130h] [rbp+18h]
  int v65; // [rsp+138h] [rbp+20h] BYREF

  v3 = a3;
  v54 = 0;
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
  if ( (unsigned int)dword_1400B1050 >= 6 && (unsigned __int8)tlgKeywordOn(&dword_1400B1050, 0x200000000000LL) )
  {
    v65 = *((_DWORD *)v3 + 3);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1400B1050,
      (unsigned int)byte_1400A7671,
      v6,
      v7,
      (__int64)&v65);
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
  v60 = pRoleExt;
  v11 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  v59 = (PNPAGED_LOOKASIDE_LIST *)v11;
  v12 = (PNPAGED_LOOKASIDE_LIST *)v11;
  if ( v11 )
  {
    *(_QWORD *)v11 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    v13 = (char *)(v11 + 4);
    v11[2] = 808679286;
    v14 = (char *)v3 + v9;
    v57 = (char *)(v11 + 4);
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
    LOBYTE(v65) = 0;
    v58 = 0;
    v55 = 0;
    v17 = "Y";
    v56 = WPP_GLOBAL_Control;
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
      v52 = (__int64)(v13 + 76);
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
      if ( !*((_DWORD *)v57 + 8) )
        v26 = "N";
      if ( !*((_DWORD *)v57 + 7) )
        v17 = "N";
      WPP_SF__MAC_DcsssssssDDs_MAC__SSID_(
        v56->AttachedDevice,
        175,
        (_DWORD)v17,
        (_DWORD)a3 + 4,
        *((_BYTE *)a3 + 10),
        *v57,
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
        (__int64)(v57 + 68),
        v52);
      v16 = 0;
      v3 = a3;
      pRoleExt = (char *)v60;
      v14 = (char *)Src;
    }
    v29 = (PDEVICE_OBJECT)(pRoleExt + 1192);
    v56 = (PDEVICE_OBJECT)(pRoleExt + 1192);
    pRoleExt[1200] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
    PeerByMAC = WFDDeviceFindPeerByMAC(
                  (struct _WFD_DEVICE_ROLE *)pRoleExt,
                  (unsigned __int8 (*)[6])((char *)v3 + 4),
                  (struct _WFD_PEER_DEVICE **)&v54);
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
    v30 = v54;
    if ( *(_BYTE *)(v54 + 40) != *((_BYTE *)v3 + 10) )
    {
      PeerByMAC = -1073741436;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          177,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          *(unsigned __int8 *)(v54 + 40),
          *((unsigned __int8 *)v3 + 10));
      goto LABEL_123;
    }
    if ( !(unsigned __int8)WFDPeerDeviceSetState(v54, 31) )
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
    v32 = *((unsigned int *)v3 + 3);
    v58 = *(void **)(v30 + 48);
    LOBYTE(v65) = 1;
    if ( (_DWORD)v32 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer)
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF__MAC_dq(WPP_GLOBAL_Control->AttachedDevice, 180, v32, (char *)v3 + 4, v32, v30);
      }
      PeerByMAC = *((_DWORD *)v3 + 3);
      if ( PeerByMAC < 0 )
      {
LABEL_122:
        WFDPeerDeviceDestroy((struct _WFD_PEER_DEVICE *)v30);
LABEL_123:
        KeReleaseSpinLock((PKSPIN_LOCK)v29, (KIRQL)v29->DriverObject);
        if ( (_BYTE)v65 )
        {
          if ( PeerByMAC )
            WFDDeviceGONegotiationSendUpcallFailure(a1, v58, v51, PeerByMAC, 0);
          else
            WFDDeviceSendUpCallRequest(a1->pGenVElan->pVElanExt, 20, v16, v55);
        }
        if ( v16 )
        {
          if ( *((_QWORD *)v16 - 2) )
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v16 - 2), v16 - 16);
          else
            ExFreePoolWithTag(v16 - 16, *((_DWORD *)v16 - 2));
        }
        v12 = v59;
        goto LABEL_132;
      }
    }
    if ( *v57 )
    {
      PeerByMAC = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 181, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_122;
    }
    v33 = v30 + 200;
    v64 = *(_BYTE *)(v30 + 192);
    if ( !v64 )
      v33 = v30 + 320;
    v34 = *((unsigned int *)v3 + 5);
    v60 = *(void **)(v30 + 432);
    v35 = *(_DWORD *)(v30 + 428);
    LODWORD(v54) = v35;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      v35 = v54;
    }
    if ( v14 )
    {
      if ( (_DWORD)v34 )
      {
        v36 = v34 + 96;
        if ( (unsigned int)v34 >= 0xFFFFFFA0 )
        {
          PeerByMAC = -1073741675;
          v38 = -1073741675;
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v40 = 82;
            v41 = (unsigned int)v34;
            goto LABEL_80;
          }
LABEL_96:
          PeerByMAC = v38;
LABEL_97:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 182, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_121:
          v29 = v56;
          goto LABEL_122;
        }
LABEL_71:
        v37 = v36 + v35;
        Size = v36 + v35;
        if ( v36 + v35 < v36 )
        {
          PeerByMAC = -1073741675;
          v38 = -1073741675;
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v40 = 83;
            v41 = v35;
LABEL_80:
            WPP_SF_Dd(v39->AttachedDevice, v40, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v41, -1);
            goto LABEL_97;
          }
          goto LABEL_96;
        }
        v42 = v37 + 16;
        if ( v37 >= 0xFFFFFFF0 )
        {
LABEL_94:
          v38 = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              85,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              v37,
              -1073741670);
          goto LABEL_96;
        }
        if ( v42 > 0x40 )
        {
          if ( v42 > 0x100 )
          {
            if ( v42 > 0x400 )
            {
              if ( v42 > 0x800 )
              {
                p_WaitListHead = 0;
                Pool2 = (_DWORD *)ExAllocatePool2(64, v42, 808679286);
                goto LABEL_92;
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
LABEL_92:
        if ( Pool2 )
        {
          v16 = (char *)(Pool2 + 4);
          *(_QWORD *)Pool2 = p_WaitListHead;
          v45 = v57;
          Pool2[2] = 808679286;
          v46 = v45 + 60;
          memset(Pool2 + 4, 0, Size);
          *(_QWORD *)v16 = v58;
          *((_QWORD *)v16 + 1) = 0;
          v16[17] = (v64 != 0) + 1;
          v16[16] = 0;
          if ( v30 != -365 )
          {
            *((_DWORD *)v16 + 16) = *(_DWORD *)(v30 + 365);
            *((_WORD *)v16 + 34) = *(_WORD *)(v30 + 369);
          }
          if ( v46 )
          {
            *(_WORD *)(v16 + 71) = *(_WORD *)v46;
            v16[73] = v46[2];
            v16[74] = v46[3];
            v16[75] = v46[4];
            v16[76] |= 1u;
          }
          if ( v33 )
          {
            *(_OWORD *)(v16 + 20) = *(_OWORD *)v33;
            *(_OWORD *)(v16 + 36) = *(_OWORD *)(v33 + 16);
            *((_OWORD *)v16 + 3) = *(_OWORD *)(v33 + 28);
          }
          if ( v30 != -371 )
            *(_WORD *)(v16 + 77) = *(_WORD *)(v30 + 371);
          if ( v33 != -44 )
            v16[70] = *(_BYTE *)(v33 + 44);
          v47 = Src;
          *((_DWORD *)v16 + 20) = 96;
          *((_DWORD *)v16 + 21) = v34;
          if ( v47 )
            memmove(v16 + 96, v47, v34);
          v48 = v60;
          if ( v60 )
          {
            v49 = v54;
            if ( (_DWORD)v54 )
            {
              *((_DWORD *)v16 + 22) = v36;
              *((_DWORD *)v16 + 23) = v49;
              memmove(&v16[v36], v48, v49);
            }
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
          {
            v50 = "Y";
            if ( !*((_DWORD *)v16 + 2) )
              v50 = "N";
            WPP_SF_qsdDD_MAC__SSID__MAC_DDDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              (unsigned __int8)v16[78],
              (unsigned __int8)v16[77],
              *(_QWORD *)v16,
              (__int64)v50,
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
          v55 = Size;
          PeerByMAC = 0;
          goto LABEL_121;
        }
        v37 = Size;
        goto LABEL_94;
      }
    }
    else if ( !(_DWORD)v34 )
    {
      v36 = 96;
      goto LABEL_71;
    }
    PeerByMAC = -1073741811;
    v38 = -1073741811;
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
0x140081234  mov     rax, rsp
0x140081237  mov     [rax+10h], rbx
0x14008123b  mov     [rax+18h], r8
0x14008123f  mov     [rax+8], rcx
0x140081243  push    rbp
0x140081244  push    rsi
0x140081245  push    rdi
0x140081246  push    r12
0x140081248  push    r13
0x14008124a  push    r14
0x14008124c  push    r15
0x14008124e  sub     rsp, 0E0h
0x140081255  mov     rdi, r8
0x140081258  mov     qword ptr [rax-80h], 0
0x140081260  mov     ebp, edx
0x140081262  mov     rbx, rcx
0x140081265  mov     rcx, cs:WPP_GLOBAL_Control
0x14008126c  lea     r12, WPP_GLOBAL_Control
0x140081273  cmp     rcx, r12
0x140081276  jz      short loc_1400812C9
0x140081278  mov     rcx, [rcx+18h]
0x14008127c  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140081283  mov     edx, 0AAh
0x140081288  call    WPP_SF_
0x14008128d  mov     rcx, cs:WPP_GLOBAL_Control
0x140081294  cmp     rcx, r12
0x140081297  jz      short loc_1400812C9
0x140081299  cmp     byte ptr [rcx+29h], 3
0x14008129d  jb      short loc_1400812C9
0x14008129f  bt      dword ptr [rcx+2Ch], 15h
0x1400812a4  jnb     short loc_1400812C9
0x1400812a6  movzx   r8d, byte ptr [rdi+0Ah]
0x1400812ab  lea     r9, [rdi+4]
0x1400812af  mov     eax, [rdi+0Ch]
0x1400812b2  mov     edx, 0ABh
0x1400812b7  mov     rcx, [rcx+18h]
0x1400812bb  mov     dword ptr [rsp+118h+var_F0], eax
0x1400812bf  mov     dword ptr [rsp+118h+var_F8], r8d
0x1400812c4  call    WPP_SF__MAC_Dd
0x1400812c9  mov     eax, cs:dword_1400B1050
0x1400812cf  test    eax, eax
0x1400812d1  jz      short loc_140081322
0x1400812d3  mov     eax, cs:dword_1400B1050
0x1400812d9  cmp     eax, 5
0x1400812dc  jbe     short loc_140081322
0x1400812de  mov     rdx, 200000000000h
0x1400812e8  lea     rcx, dword_1400B1050
0x1400812ef  call    _tlgKeywordOn
0x1400812f4  test    al, al
0x1400812f6  jz      short loc_140081322
0x1400812f8  mov     eax, [rdi+0Ch]
0x1400812fb  lea     rdx, byte_1400A7671
0x140081302  mov     [rsp+118h+arg_18], eax
0x140081309  lea     rcx, dword_1400B1050
0x140081310  lea     rax, [rsp+118h+arg_18]
0x140081318  mov     qword ptr [rsp+118h+var_F8], rax
0x14008131d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140081322  mov     r14d, [rdi+14h]
0x140081326  mov     esi, [rdi+10h]
0x140081329  test    r14d, r14d
0x14008132c  jz      short loc_140081337
0x14008132e  cmp     esi, 18h
0x140081331  jb      loc_140081CFC
0x140081337  lea     eax, [r14+rsi]
0x14008133b  cmp     eax, esi
0x14008133d  jb      loc_140081CFC
0x140081343  cmp     eax, ebp
0x140081345  ja      loc_140081CFC
0x14008134b  mov     r13, [rbx+0B8h]
0x140081352  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140081359  mov     rcx, rbx; Lookaside
0x14008135c  mov     [rsp+118h+var_50], r13
0x140081364  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008136b  nop     dword ptr [rax+rax+00h]
0x140081370  mov     [rsp+118h+var_58], rax
0x140081378  mov     r15, rax
0x14008137b  test    rax, rax
0x14008137e  jz      loc_140081CD0
0x140081384  xor     edx, edx; Val
0x140081386  mov     [rax], rbx
0x140081389  lea     rbx, [rax+10h]
0x14008138d  mov     dword ptr [rax+8], 30337776h
0x140081394  lea     r12, [rdi+rsi]
0x140081398  mov     [rsp+118h+var_68], rbx
0x1400813a0  mov     rcx, rbx; void *
0x1400813a3  mov     [rsp+118h+Src], r12
0x1400813ab  lea     r8d, [rdx+74h]; Size
0x1400813af  call    memset
0x1400813b4  mov     r8, rbx; void *
0x1400813b7  mov     edx, r14d; unsigned int
0x1400813ba  mov     rcx, r12; unsigned __int8 *
0x1400813bd  call    WFDValidateIncomingGONegotiationConfirmationIEs
0x1400813c2  test    al, al
0x1400813c4  jnz     short loc_140081413
0x1400813c6  mov     ebx, 0C0010015h
0x1400813cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400813d2  lea     r12, WPP_GLOBAL_Control
0x1400813d9  cmp     rcx, r12
0x1400813dc  jz      loc_140081C92
0x1400813e2  cmp     byte ptr [rcx+29h], 2
0x1400813e6  jb      loc_140081C92
0x1400813ec  test    dword ptr [rcx+2Ch], 200000h
0x1400813f3  jz      loc_140081C92
0x1400813f9  mov     rcx, [rcx+18h]
0x1400813fd  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140081404  mov     edx, 0AEh
0x140081409  call    WPP_SF_
0x14008140e  jmp     loc_140081C92
0x140081413  mov     rax, cs:WPP_GLOBAL_Control
0x14008141a  lea     rcx, WPP_GLOBAL_Control
0x140081421  xor     r15d, r15d
0x140081424  mov     byte ptr [rsp+118h+arg_18], 0
0x14008142c  mov     [rsp+118h+var_60], 0
0x140081438  mov     bpl, 1
0x14008143b  mov     [rsp+118h+Size], r15
0x140081443  lea     r9, aN; "N"
0x14008144a  mov     [rsp+118h+var_78], r15d
0x140081452  lea     r8, aY; "Y"
0x140081459  mov     [rsp+118h+var_70], rax
0x140081461  cmp     rax, rcx
0x140081464  jz      loc_140081590
0x14008146a  cmp     byte ptr [rax+29h], 4
0x14008146e  jb      loc_140081590
0x140081474  test    dword ptr [rax+2Ch], 200000h
0x14008147b  jz      loc_140081590
0x140081481  test    [rbx+70h], bpl
0x140081485  lea     rcx, [rbx+4Ch]
0x140081489  mov     eax, [rbx+24h]
0x14008148c  mov     r13, r8
0x14008148f  mov     rdx, [rsp+118h+var_68]
0x140081497  cmovz   r13, r9
0x14008149b  cmp     dword ptr [rbx+34h], 0
0x14008149f  mov     r14, r8
0x1400814a2  movzx   r15d, byte ptr [rbx+40h]
0x1400814a7  mov     rbp, r8
0x1400814aa  movzx   r12d, byte ptr [rbx+3Fh]
0x1400814af  cmovz   r14, r9
0x1400814b3  cmp     dword ptr [rbx+30h], 0
0x1400814b7  mov     rsi, r8
0x1400814ba  mov     [rsp+118h+var_90], rcx
0x1400814c2  mov     rdi, r8
0x1400814c5  mov     rcx, [rsp+118h+var_68]
0x1400814cd  cmovz   rbp, r9
0x1400814d1  cmp     dword ptr [rbx+2Ch], 0
0x1400814d5  mov     r11, r8
0x1400814d8  cmovz   rsi, r9
0x1400814dc  cmp     dword ptr [rbx+28h], 0
0x1400814e0  mov     rbx, r8
0x1400814e3  cmovz   rdi, r9
0x1400814e7  test    eax, eax
0x1400814e9  lea     rax, [rcx+44h]
0x1400814ed  mov     [rsp+118h+var_98], rax
0x1400814f5  cmovz   rbx, r9
0x1400814f9  cmp     dword ptr [rdx+20h], 0
0x1400814fd  mov     al, [rcx]
0x1400814ff  mov     rcx, [rsp+118h+var_70]
0x140081507  cmovz   r11, r9
0x14008150b  cmp     dword ptr [rdx+1Ch], 0
0x14008150f  mov     edx, 0AFh
0x140081514  mov     [rsp+118h+var_A0], r13
0x140081519  mov     [rsp+118h+var_A8], r15d
0x14008151e  cmovz   r8, r9
0x140081522  mov     r9, [rsp+118h+arg_10]
0x14008152a  mov     rcx, [rcx+18h]
0x14008152e  mov     [rsp+118h+var_B0], r12d
0x140081533  mov     [rsp+118h+var_B8], r14
0x140081538  movzx   r10d, byte ptr [r9+0Ah]
0x14008153d  add     r9, 4
0x140081541  mov     [rsp+118h+var_C0], rbp
0x140081546  mov     [rsp+118h+var_C8], rsi
0x14008154b  mov     [rsp+118h+var_D0], rdi
0x140081550  mov     [rsp+118h+var_D8], rbx
0x140081555  mov     [rsp+118h+var_E0], r11
0x14008155a  mov     [rsp+118h+var_E8], r8
0x14008155f  mov     byte ptr [rsp+118h+var_F0], al
0x140081563  mov     dword ptr [rsp+118h+var_F8], r10d
0x140081568  call    WPP_SF__MAC_DcsssssssDDs_MAC__SSID_
0x14008156d  mov     r15, [rsp+118h+Size]
0x140081575  mov     bpl, 1
0x140081578  mov     rdi, [rsp+118h+arg_10]
0x140081580  mov     r13, [rsp+118h+var_50]
0x140081588  mov     r12, [rsp+118h+Src]
0x140081590  lea     r14, [r13+4A8h]
0x140081597  mov     rcx, r14; SpinLock
0x14008159a  mov     [rsp+118h+var_70], r14
0x1400815a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400815a9  nop     dword ptr [rax+rax+00h]
0x1400815ae  lea     rsi, [rdi+4]
0x1400815b2  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x1400815b5  lea     r8, [rsp+118h+var_80]; struct _WFD_PEER_DEVICE **
0x1400815bd  mov     [r13+4B0h], al
0x1400815c4  mov     rdx, rsi; unsigned __int8 (*)[6]
0x1400815c7  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x1400815cc  mov     ebx, eax
0x1400815ce  test    eax, eax
0x1400815d0  jz      short loc_140081606
0x1400815d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400815d9  lea     r12, WPP_GLOBAL_Control
0x1400815e0  cmp     rcx, r12
0x1400815e3  jz      loc_140081BF9
0x1400815e9  mov     rcx, [rcx+18h]
0x1400815ed  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400815f4  mov     edx, 0B0h
0x1400815f9  mov     r9, rsi
0x1400815fc  call    WPP_SF__MAC_
0x140081601  jmp     loc_140081BF9
0x140081606  mov     r13, [rsp+118h+var_80]
0x14008160e  movzx   eax, byte ptr [rdi+0Ah]
0x140081612  movzx   edx, byte ptr [r13+28h]
0x140081617  cmp     dl, al
0x140081619  jz      short loc_140081658
0x14008161b  mov     ebx, 0C0000184h
0x140081620  mov     rcx, cs:WPP_GLOBAL_Control
0x140081627  lea     r12, WPP_GLOBAL_Control
0x14008162e  cmp     rcx, r12
0x140081631  jz      loc_140081BF9
0x140081637  mov     rcx, [rcx+18h]
0x14008163b  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140081642  mov     r9d, edx
0x140081645  mov     dword ptr [rsp+118h+var_F8], eax
0x140081649  mov     edx, 0B1h
0x14008164e  call    WPP_SF_Dd
0x140081653  jmp     loc_140081BF9
0x140081658  mov     edx, 1Fh
0x14008165d  mov     rcx, r13
0x140081660  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x140081665  test    al, al
0x140081667  jnz     short loc_1400816BC
0x140081669  mov     ebx, 0C0000184h
0x14008166e  mov     rcx, cs:WPP_GLOBAL_Control
0x140081675  lea     r12, WPP_GLOBAL_Control
0x14008167c  cmp     rcx, r12
0x14008167f  jz      loc_140081BF9
0x140081685  cmp     byte ptr [rcx+29h], 3
0x140081689  jb      loc_140081BF9
0x14008168f  test    dword ptr [rcx+2Ch], 200000h
0x140081696  jz      loc_140081BF9
0x14008169c  mov     rcx, [rcx+18h]
0x1400816a0  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400816a7  mov     edx, 0B2h
0x1400816ac  mov     r9d, 13h
0x1400816b2  call    WPP_SF_d
0x1400816b7  jmp     loc_140081BF9
0x1400816bc  mov     rcx, r13; struct _WFD_PEER_DEVICE *
0x1400816bf  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCancelTimer(_WFD_PEER_DEVICE *)
0x1400816c4  test    eax, eax
0x1400816c6  jnz     short loc_140081712
0x1400816c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400816cf  lea     r12, WPP_GLOBAL_Control
0x1400816d6  cmp     rcx, r12
0x1400816d9  jz      loc_140081BF9
0x1400816df  cmp     [rcx+29h], bpl
0x1400816e3  jb      loc_140081BF9
0x1400816e9  test    dword ptr [rcx+2Ch], 200000h
0x1400816f0  jz      loc_140081BF9
0x1400816f6  mov     rcx, [rcx+18h]
0x1400816fa  lea     r9, [r13+18h]
0x1400816fe  mov     edx, 0B3h
0x140081703  mov     qword ptr [rsp+118h+var_F8], r13
0x140081708  call    WPP_SF__MAC_q
0x14008170d  jmp     loc_140081BF9
0x140081712  mov     rax, [r13+30h]
0x140081716  mov     r8d, [rdi+0Ch]
0x14008171a  mov     [rsp+118h+var_60], rax
0x140081722  mov     byte ptr [rsp+118h+arg_18], bpl
0x14008172a  test    r8d, r8d
0x14008172d  jz      short loc_14008177F
0x14008172f  mov     rcx, cs:WPP_GLOBAL_Control
0x140081736  lea     rax, WPP_GLOBAL_Control
0x14008173d  cmp     rcx, rax
0x140081740  jz      short loc_14008176C
0x140081742  cmp     [rcx+29h], bpl
0x140081746  jb      short loc_14008176C
0x140081748  test    dword ptr [rcx+2Ch], 200000h
0x14008174f  jz      short loc_14008176C
0x140081751  mov     rcx, [rcx+18h]
0x140081755  mov     edx, 0B4h
0x14008175a  mov     [rsp+118h+var_F0], r13
0x14008175f  mov     r9, rsi
0x140081762  mov     dword ptr [rsp+118h+var_F8], r8d
0x140081767  call    WPP_SF__MAC_dq
0x14008176c  mov     ebx, [rdi+0Ch]
0x14008176f  test    ebx, ebx
0x140081771  jns     short loc_14008177F
0x140081773  lea     r12, WPP_GLOBAL_Control
0x14008177a  jmp     loc_140081BF1
0x14008177f  mov     rax, [rsp+118h+var_68]
0x140081787  cmp     byte ptr [rax], 0
0x14008178a  jz      short loc_1400817C2
0x14008178c  mov     ebx, 0C000000Dh
0x140081791  mov     rcx, cs:WPP_GLOBAL_Control
0x140081798  lea     r12, WPP_GLOBAL_Control
0x14008179f  cmp     rcx, r12
0x1400817a2  jz      loc_140081BF1
0x1400817a8  mov     rcx, [rcx+18h]
0x1400817ac  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400817b3  mov     edx, 0B5h
0x1400817b8  call    WPP_SF_
0x1400817bd  jmp     loc_140081BF1
0x1400817c2  mov     al, [r13+0C0h]
  ... truncated ...
```

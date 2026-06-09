# WFDDeviceHandleReceivedGONConfirmation(_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS *)

- ea: `0x140083660`
- end: `0x14008420a`
- name: `?WFDDeviceHandleReceivedGONConfirmation@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS@@@Z`
- size: `2986`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007de60`

## callees

- `0x14000170c`
- `0x14000d21c`
- `0x14000d2b0`
- `0x140020dc0`
- `0x140020f20`
- `0x140022f08`
- `0x14002f44c`
- `0x14003b04c`
- `0x14003da34`
- `0x140080a84`
- `0x140080dfc`
- `0x140080e3c`
- `0x140083660`
- `0x14008adb8`
- `0x14008aef8`
- `0x14008bfb0`
- `0x14008c788`
- `0x14008d5ac`
- `0x14008de3c`
- `0x14008ebf0`
- `0x140098c18`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140083708`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140083dba`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140083708`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140083dba`
- `ntoskrnl!ExAllocatePool2` at `0x140083dd3`
- `ntoskrnl!ExAllocatePool2` at `0x140083dd3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008409c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084162`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008409c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084162`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400840b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084173`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400840b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084173`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008406b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008410f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008406b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008410f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400839d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400839d4`

## pseudocode

```c
void __fastcall WFDDeviceHandleReceivedGONConfirmation(
        struct _WFD_ROLE *a1,
        unsigned int a2,
        struct _DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS *a3)
{
  struct _WFD_ROLE *v4; // rdx
  struct _DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS *v5; // r15
  unsigned int v6; // r14d
  __int64 v7; // rsi
  char *pRoleExt; // r13
  char *v9; // rax
  unsigned int v10; // ebx
  unsigned __int8 *v11; // rdi
  char *v12; // rbx
  char v13; // r12
  char *v14; // rcx
  int v15; // eax
  const char *v16; // r15
  char v17; // r12
  const char *v18; // r14
  char v19; // r13
  const char *v20; // rsi
  const char *v21; // rbx
  const char *v22; // r11
  const char *v23; // r8
  bool v24; // zf
  const char *v25; // rdi
  int v26; // r8d
  int v27; // r9d
  _DEVICE_OBJECT *AttachedDevice; // rcx
  struct _WFD_PEER_DEVICE *v29; // r13
  __int64 v30; // r8
  unsigned __int8 v31; // si
  char *v32; // r14
  unsigned int v33; // r8d
  size_t v34; // r15
  unsigned int v35; // eax
  __int64 v36; // r9
  unsigned int v37; // esi
  PDEVICE_OBJECT v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r9
  unsigned int v41; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // r12
  char *Pool2; // rax
  struct _WFD_PEER_DEVICE *v44; // rbx
  size_t v45; // r8
  char *v46; // r12
  void *v47; // rdx
  void *v48; // rdx
  unsigned int v49; // ecx
  const char *v50; // rax
  int v51; // r8d
  __int64 v52; // [rsp+50h] [rbp-91h]
  char v53; // [rsp+98h] [rbp-49h]
  unsigned __int8 v54[3]; // [rsp+99h] [rbp-48h] BYREF
  unsigned int Size; // [rsp+9Ch] [rbp-45h]
  unsigned int Size_4; // [rsp+A0h] [rbp-41h]
  char *v57; // [rsp+A8h] [rbp-39h]
  struct _WFD_PEER_DEVICE *v58; // [rsp+B0h] [rbp-31h] BYREF
  PKSPIN_LOCK SpinLock; // [rsp+B8h] [rbp-29h]
  PDEVICE_OBJECT v60; // [rsp+C0h] [rbp-21h]
  _QWORD v61[2]; // [rsp+C8h] [rbp-19h] BYREF
  void *Src; // [rsp+D8h] [rbp-9h]
  KIRQL *v63; // [rsp+E0h] [rbp-1h]
  void *v64; // [rsp+E8h] [rbp+7h]
  void *v65; // [rsp+F0h] [rbp+Fh]
  const char *v66; // [rsp+F8h] [rbp+17h]
  struct _DOT11_RECEIVED_GO_NEGOTIATION_CONFIRMATION_PARAMETERS *v68; // [rsp+158h] [rbp+77h] BYREF
  unsigned __int8 v69; // [rsp+160h] [rbp+7Fh]

  v68 = a3;
  v58 = 0;
  v4 = a1;
  v54[0] = 0;
  v5 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 184, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    v4 = a1;
  }
  v6 = *((_DWORD *)v5 + 4);
  v7 = *((unsigned int *)v5 + 3);
  Size = v6;
  if ( (!v6 || (unsigned int)v7 >= 0x14) && v6 + (unsigned int)v7 >= (unsigned int)v7 && v6 + (unsigned int)v7 <= a2 )
  {
    pRoleExt = (char *)v4->pRoleExt;
    v63 = (KIRQL *)pRoleExt;
    v9 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
    if ( !v9 )
    {
      v10 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 186, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_151;
    }
    v11 = (unsigned __int8 *)(v9 + 16);
    *(_QWORD *)v9 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    *((_DWORD *)v9 + 2) = 808679286;
    v12 = (char *)v5 + v7;
    v57 = v9 + 16;
    Src = (char *)v5 + v7;
    memset(v9 + 16, 0, 0x74u);
    if ( !(unsigned __int8)WFDValidateIncomingGONegotiationConfirmationIEs((unsigned __int8 *)v5 + v7, v6, v11) )
    {
      v10 = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 187, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      }
LABEL_143:
      if ( v11 )
      {
        if ( *((_QWORD *)v11 - 2) )
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v11 - 2), v11 - 16);
        else
          ExFreePoolWithTag(v11 - 16, *((_DWORD *)v11 - 2));
      }
      goto LABEL_151;
    }
    v13 = 0;
    v69 = 0;
    v64 = 0;
    v66 = "N";
    v60 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      v14 = "Y";
      v15 = *((_DWORD *)v11 + 10);
      v16 = "Y";
      v17 = v11[64];
      if ( (v11[112] & 1) == 0 )
        v14 = "N";
      v18 = "Y";
      v19 = v11[63];
      v20 = "Y";
      if ( !*((_DWORD *)v11 + 13) )
        v16 = "N";
      SpinLock = (PKSPIN_LOCK)v14;
      v21 = "Y";
      v22 = "Y";
      if ( !*((_DWORD *)v11 + 12) )
        v18 = "N";
      v23 = "Y";
      v24 = *((_DWORD *)v11 + 11) == 0;
      v25 = "Y";
      if ( v24 )
        v20 = "N";
      if ( !v15 )
        v25 = "N";
      if ( !*((_DWORD *)v57 + 9) )
        v21 = "N";
      if ( !*((_DWORD *)v57 + 8) )
        v22 = "N";
      if ( !*((_DWORD *)v57 + 7) )
        v23 = "N";
      v52 = (__int64)v25;
      v11 = (unsigned __int8 *)v57;
      WPP_SF__MAC_DcsssssssDDs_MAC__SSID_(
        v60->AttachedDevice,
        188,
        (_DWORD)v23,
        (_DWORD)v68 + 4,
        *((_BYTE *)v68 + 10),
        *v57,
        (__int64)v23,
        (__int64)v22,
        (__int64)v21,
        v52,
        (__int64)v20,
        (__int64)v18,
        (__int64)v16,
        v19,
        v17,
        (__int64)SpinLock,
        (__int64)(v57 + 68),
        (__int64)(v57 + 76));
      v6 = Size;
      v5 = v68;
      v13 = 0;
      v12 = (char *)Src;
      pRoleExt = (char *)v63;
    }
    if ( (unsigned int)dword_1400B1050 >= 6 && (unsigned __int8)tlgKeywordOn(&dword_1400B1050, 0x200000000000LL) )
    {
      LODWORD(v68) = *v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1400B1050,
        (unsigned int)byte_1400A7635,
        v26,
        v27,
        (__int64)&v68);
    }
    if ( v6
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v61[0] = (unsigned __int16)v6;
      v61[1] = v12;
      WPP_SF__HEX_(AttachedDevice, 189, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v61);
    }
    SpinLock = (PKSPIN_LOCK)(pRoleExt + 1192);
    pRoleExt[1200] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
    if ( (int)WFDDeviceCheckDuplicateTransmission(
                (struct _WFD_DEVICE_ROLE *)pRoleExt,
                (unsigned __int8 (*)[6])((char *)v5 + 4),
                WfdReceivedPacketTypeGONConfirm,
                *((_BYTE *)v5 + 10),
                v54) < 0
      || v54[0] )
    {
      v10 = -1073676267;
      LOBYTE(v68) = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          190,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          *((unsigned __int8 *)v5 + 10));
      }
      goto LABEL_137;
    }
    LOBYTE(v68) = 0;
    if ( (unsigned int)WFDDeviceFindPeerByMAC(
                         (struct _WFD_DEVICE_ROLE *)pRoleExt,
                         (unsigned __int8 (*)[6])((char *)v5 + 4),
                         &v58) )
    {
      v10 = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_(
          WPP_GLOBAL_Control->AttachedDevice,
          191,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          (char *)v5 + 4);
LABEL_137:
      v31 = v69;
LABEL_138:
      KeReleaseSpinLock(SpinLock, *((_BYTE *)SpinLock + 8));
      if ( !(_BYTE)v68 )
      {
        if ( !v10 )
          v10 = -1073741823;
        if ( v13 )
          WFDDeviceGONegotiationSendUpcallFailure(a1, v64, v51, v10, v31);
      }
      goto LABEL_143;
    }
    v29 = v58;
    if ( *((_BYTE *)v58 + 40) != *((_BYTE *)v5 + 10) )
    {
      v10 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 192, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_137;
    }
    v61[0] = a1->pGenVElan->pVElanExt;
    if ( !(unsigned __int8)WFDPeerDeviceSetState(v58, 28) )
    {
      v10 = -1073741436;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          193,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          *((unsigned int *)v29 + 9));
      }
      goto LABEL_137;
    }
    if ( !(unsigned int)WFDPeerDeviceCancelTimer(v29) )
    {
      v10 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer)
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF__MAC_q(WPP_GLOBAL_Control->AttachedDevice, 194, v30, (char *)v29 + 24, v29);
      }
      v31 = 0;
      goto LABEL_138;
    }
    v64 = (void *)*((_QWORD *)v29 + 6);
    if ( *v11 )
    {
      v31 = *v11;
      v10 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 195, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, *v11);
      goto LABEL_106;
    }
    v32 = (char *)v29 + 320;
    *((_BYTE *)v29 + 380) |= 4u;
    *(_DWORD *)((char *)v29 + 375) = *((_DWORD *)v11 + 15);
    *((_BYTE *)v29 + 379) = v11[64];
    WFDDeviceUpdateGroupCaps((unsigned __int8 *)v29 + 364, (struct _WFD_GROUP_CAPABILITY *)(v11 + 28));
    if ( !*((_BYTE *)v29 + 192) )
    {
      if ( (v11[112] & 1) == 0 )
      {
        v10 = -1073676267;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 196, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_105:
        v31 = v69;
LABEL_106:
        v13 = 1;
        WFDPeerDeviceDestroy(v29);
        goto LABEL_138;
      }
      *((_BYTE *)v29 + 380) |= 1u;
      *(_OWORD *)v32 = *(_OWORD *)(v11 + 68);
      *((_OWORD *)v29 + 21) = *(_OWORD *)(v11 + 84);
      *(_OWORD *)((char *)v29 + 348) = *((_OWORD *)v11 + 6);
    }
    v53 = *((_BYTE *)v29 + 192);
    if ( v53 )
      v32 = (char *)v29 + 200;
    v33 = *((_DWORD *)v29 + 107);
    v34 = *((unsigned int *)v5 + 4);
    v65 = (void *)*((_QWORD *)v29 + 54);
    v60 = (PDEVICE_OBJECT)*((_QWORD *)v29 + 6);
    Size_4 = v33;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      v33 = Size_4;
    }
    if ( v12 )
    {
      if ( (_DWORD)v34 )
      {
        v35 = v34 + 96;
        if ( (unsigned int)v34 >= 0xFFFFFFA0 )
        {
          v10 = -1073741675;
          v37 = -1073741675;
          v38 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v39 = 82;
            v40 = (unsigned int)v34;
            goto LABEL_86;
          }
LABEL_102:
          v10 = v37;
LABEL_103:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 197, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v37);
          goto LABEL_105;
        }
LABEL_77:
        v36 = v35 + v33;
        Size = v36;
        if ( (unsigned int)v36 < v35 )
        {
          v10 = -1073741675;
          v37 = -1073741675;
          v38 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v39 = 83;
            v40 = v33;
LABEL_86:
            WPP_SF_Dd(v38->AttachedDevice, v39, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v40, -1);
            goto LABEL_103;
          }
          goto LABEL_102;
        }
        v41 = v36 + 16;
        if ( (unsigned int)v36 >= 0xFFFFFFF0 )
        {
LABEL_100:
          v37 = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              85,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              v36,
              -1073741670);
          goto LABEL_102;
        }
        if ( v41 > 0x40 )
        {
          if ( v41 > 0x100 )
          {
            if ( v41 > 0x400 )
            {
              if ( v41 > 0x800 )
              {
                p_WaitListHead = 0;
                Pool2 = (char *)ExAllocatePool2(64, v41, 808679286);
                goto LABEL_98;
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
        Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_98:
        v58 = (struct _WFD_PEER_DEVICE *)Pool2;
        v44 = (struct _WFD_PEER_DEVICE *)Pool2;
        if ( Pool2 )
        {
          v45 = Size;
          *(_QWORD *)Pool2 = p_WaitListHead;
          v46 = Pool2 + 16;
          *((_DWORD *)Pool2 + 2) = 808679286;
          memset(Pool2 + 16, 0, v45);
          *(_QWORD *)v46 = v60;
          *((_QWORD *)v44 + 3) = 0;
          *((_BYTE *)v44 + 33) = (v53 != 0) + 1;
          *((_BYTE *)v44 + 32) = 0;
          if ( v29 != (struct _WFD_PEER_DEVICE *)-365LL )
          {
            *((_DWORD *)v44 + 20) = *(_DWORD *)((char *)v29 + 365);
            *((_WORD *)v44 + 42) = *(_WORD *)((char *)v29 + 369);
          }
          if ( v29 != (struct _WFD_PEER_DEVICE *)-375LL )
          {
            *(_WORD *)((char *)v44 + 87) = *(_WORD *)((char *)v29 + 375);
            *((_BYTE *)v44 + 89) = *((_BYTE *)v29 + 377);
            *((_BYTE *)v44 + 90) = *((_BYTE *)v29 + 378);
            *((_BYTE *)v44 + 91) = *((_BYTE *)v29 + 379);
            *((_BYTE *)v44 + 92) |= 1u;
          }
          if ( v32 )
          {
            *(_OWORD *)((char *)v44 + 36) = *(_OWORD *)v32;
            *(_OWORD *)((char *)v44 + 52) = *((_OWORD *)v32 + 1);
            *((_OWORD *)v44 + 4) = *(_OWORD *)(v32 + 28);
          }
          if ( v29 != (struct _WFD_PEER_DEVICE *)-371LL )
            *(_WORD *)((char *)v44 + 93) = *(_WORD *)((char *)v29 + 371);
          if ( v32 != (char *)-44LL )
            *((_BYTE *)v44 + 86) = v32[44];
          v47 = Src;
          *((_DWORD *)v44 + 24) = 96;
          *((_DWORD *)v44 + 25) = v34;
          if ( v47 )
            memmove((char *)v44 + 112, v47, v34);
          v48 = v65;
          if ( v65 )
          {
            v49 = Size_4;
            if ( Size_4 )
            {
              *((_DWORD *)v44 + 26) = v34 + 96;
              *((_DWORD *)v44 + 27) = v49;
              memmove(&v46[(unsigned int)(v34 + 96)], v48, v49);
            }
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
          {
            v50 = "Y";
            if ( !*((_DWORD *)v46 + 2) )
              v50 = v66;
            WPP_SF_qsdDD_MAC__SSID__MAC_DDDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              *((unsigned __int8 *)v44 + 94),
              (unsigned __int8)v46[77],
              *(_QWORD *)v46,
              (__int64)v50,
              *((_DWORD *)v46 + 3),
              v46[16],
              v46[17],
              (__int64)(v46 + 20),
              (__int64)(v46 + 28),
              (__int64)(v46 + 64),
              v46[70],
              v46[74],
              *((_BYTE *)v44 + 91),
              v46[77],
              v46[78]);
            v11 = (unsigned __int8 *)v57;
            v44 = v58;
          }
          WFDPeerDeviceDestroy(v29);
          KeReleaseSpinLock(SpinLock, v63[1200]);
          WFDDeviceSendUpCallRequest(v61[0], 20, v46, Size);
          if ( v46 )
          {
            if ( *(_QWORD *)v44 )
              ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v44, v44);
            else
              ExFreePoolWithTag(v44, *((_DWORD *)v44 + 2));
          }
          v10 = 0;
          goto LABEL_143;
        }
        v36 = Size;
        goto LABEL_100;
      }
    }
    else if ( !(_DWORD)v34 )
    {
      v35 = 96;
      goto LABEL_77;
    }
    v10 = -1073741811;
    v37 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_103;
    }
    goto LABEL_102;
  }
  v10 = -1073676267;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer)
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
  {
    WPP_SF_DDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      185,
      WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
      (unsigned int)v7,
      v6,
      v6 + v7,
      a2);
  }
LABEL_151:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 198, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v10);
}

```

## disassembly

```asm
0x140083660  mov     rax, rsp
0x140083663  mov     [rax+10h], rbx
0x140083667  mov     [rax+18h], r8
0x14008366b  mov     [rax+8], rcx
0x14008366f  push    rbp
0x140083670  push    rsi
0x140083671  push    rdi
0x140083672  push    r12
0x140083674  push    r13
0x140083676  push    r14
0x140083678  push    r15
0x14008367a  lea     rbp, [rax-5Fh]
0x14008367e  sub     rsp, 100h
0x140083685  mov     edi, edx
0x140083687  mov     [rbp+57h+var_88], 0
0x14008368f  mov     rdx, rcx
0x140083692  mov     [rbp+57h+var_9F], 0
0x140083696  mov     r15, r8
0x140083699  mov     rcx, cs:WPP_GLOBAL_Control
0x1400836a0  lea     r12, WPP_GLOBAL_Control
0x1400836a7  cmp     rcx, r12
0x1400836aa  jz      short loc_1400836C5
0x1400836ac  mov     rcx, [rcx+18h]
0x1400836b0  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400836b7  mov     edx, 0B8h
0x1400836bc  call    WPP_SF_
0x1400836c1  mov     rdx, [rbp+57h+arg_0]
0x1400836c5  mov     r14d, [r15+10h]
0x1400836c9  mov     esi, [r15+0Ch]
0x1400836cd  mov     dword ptr [rbp+57h+Size], r14d
0x1400836d1  test    r14d, r14d
0x1400836d4  jz      short loc_1400836DF
0x1400836d6  cmp     esi, 14h
0x1400836d9  jb      loc_140084181
0x1400836df  lea     eax, [r14+rsi]
0x1400836e3  cmp     eax, esi
0x1400836e5  jb      loc_140084181
0x1400836eb  cmp     eax, edi
0x1400836ed  ja      loc_140084181
0x1400836f3  mov     r13, [rdx+0B8h]
0x1400836fa  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140083701  mov     rcx, rbx; Lookaside
0x140083704  mov     [rbp+57h+var_58], r13
0x140083708  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008370f  nop     dword ptr [rax+rax+00h]
0x140083714  test    rax, rax
0x140083717  jnz     short loc_140083748
0x140083719  mov     ebx, 0C000009Ah
0x14008371e  mov     rcx, cs:WPP_GLOBAL_Control
0x140083725  cmp     rcx, r12
0x140083728  jz      loc_1400841CA
0x14008372e  mov     rcx, [rcx+18h]
0x140083732  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140083739  mov     edx, 0BAh
0x14008373e  call    WPP_SF_
0x140083743  jmp     loc_1400841CA
0x140083748  lea     rdi, [rax+10h]
0x14008374c  mov     [rax], rbx
0x14008374f  xor     edx, edx; Val
0x140083751  mov     dword ptr [rax+8], 30337776h
0x140083758  lea     rbx, [r15+rsi]
0x14008375c  mov     [rbp+57h+var_90], rdi
0x140083760  mov     rcx, rdi; void *
0x140083763  mov     [rbp+57h+Src], rbx
0x140083767  lea     r8d, [rdx+74h]; Size
0x14008376b  call    memset
0x140083770  mov     r8, rdi; void *
0x140083773  mov     edx, r14d; unsigned int
0x140083776  mov     rcx, rbx; unsigned __int8 *
0x140083779  call    WFDValidateIncomingGONegotiationConfirmationIEs
0x14008377e  test    al, al
0x140083780  jnz     short loc_1400837C8
0x140083782  mov     ebx, 0C000000Dh
0x140083787  mov     rcx, cs:WPP_GLOBAL_Control
0x14008378e  cmp     rcx, r12
0x140083791  jz      loc_14008414B
0x140083797  cmp     byte ptr [rcx+29h], 2
0x14008379b  jb      loc_14008414B
0x1400837a1  test    dword ptr [rcx+2Ch], 200000h
0x1400837a8  jz      loc_14008414B
0x1400837ae  mov     rcx, [rcx+18h]
0x1400837b2  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400837b9  mov     edx, 0BBh
0x1400837be  call    WPP_SF_
0x1400837c3  jmp     loc_14008414B
0x1400837c8  mov     rax, cs:WPP_GLOBAL_Control
0x1400837cf  lea     rcx, WPP_GLOBAL_Control
0x1400837d6  xor     r12b, r12b
0x1400837d9  mov     [rbp+57h+arg_18], 0
0x1400837dd  mov     [rbp+57h+var_A0], r12b
0x1400837e1  lea     r9, aN; "N"
0x1400837e8  mov     [rbp+57h+var_50], 0
0x1400837f0  mov     esi, 200000h
0x1400837f5  mov     [rbp+57h+var_40], r9
0x1400837f9  lea     rdx, aY; "Y"
0x140083800  mov     [rbp+57h+var_78], rax
0x140083804  cmp     rax, rcx
0x140083807  jz      loc_140083920
0x14008380d  cmp     byte ptr [rax+29h], 4
0x140083811  jb      loc_140083920
0x140083817  test    [rax+2Ch], esi
0x14008381a  jz      loc_140083920
0x140083820  test    byte ptr [rdi+70h], 1
0x140083824  mov     rcx, rdx
0x140083827  mov     eax, [rdi+28h]
0x14008382a  mov     r15, rdx
0x14008382d  movzx   r12d, byte ptr [rdi+40h]
0x140083832  cmovz   rcx, r9
0x140083836  cmp     dword ptr [rdi+34h], 0
0x14008383a  mov     r14, rdx
0x14008383d  movzx   r13d, byte ptr [rdi+3Fh]
0x140083842  mov     rsi, rdx
0x140083845  cmovz   r15, r9
0x140083849  mov     [rbp+57h+SpinLock], rcx
0x14008384d  cmp     dword ptr [rdi+30h], 0
0x140083851  mov     rbx, rdx
0x140083854  mov     rcx, [rbp+57h+var_90]
0x140083858  mov     r11, rdx
0x14008385b  cmovz   r14, r9
0x14008385f  mov     r8, rdx
0x140083862  cmp     dword ptr [rdi+2Ch], 0
0x140083866  mov     rdi, rdx
0x140083869  mov     edx, 0BCh
0x14008386e  cmovz   rsi, r9
0x140083872  test    eax, eax
0x140083874  lea     rax, [rcx+4Ch]
0x140083878  mov     [rsp+88h], rax
0x140083880  cmovz   rdi, r9
0x140083884  cmp     dword ptr [rcx+24h], 0
0x140083888  lea     rax, [rcx+44h]
0x14008388c  mov     [rsp+130h+var_B0], rax
0x140083894  cmovz   rbx, r9
0x140083898  cmp     dword ptr [rcx+20h], 0
0x14008389c  cmovz   r11, r9
0x1400838a0  cmp     dword ptr [rcx+1Ch], 0
0x1400838a4  mov     rcx, [rbp+57h+SpinLock]
0x1400838a8  mov     [rsp+130h+var_B8], rcx
0x1400838ad  cmovz   r8, r9
0x1400838b1  mov     r9, [rbp+57h+arg_10]
0x1400838b5  mov     rcx, [rbp+57h+var_78]
0x1400838b9  mov     dword ptr [rsp+130h+var_C0], r12d
0x1400838be  mov     [rsp+130h+var_C8], r13d
0x1400838c3  movzx   r10d, byte ptr [r9+0Ah]
0x1400838c8  add     r9, 4
0x1400838cc  mov     rcx, [rcx+18h]
0x1400838d0  mov     qword ptr [rsp+130h+var_D0], r15
0x1400838d5  mov     [rsp+130h+var_D8], r14
0x1400838da  mov     [rsp+130h+var_E0], rsi
0x1400838df  mov     [rsp+130h+var_E8], rdi
0x1400838e4  mov     rdi, [rbp+57h+var_90]
0x1400838e8  mov     [rsp+130h+var_F0], rbx
0x1400838ed  mov     [rsp+130h+var_F8], r11
0x1400838f2  mov     [rsp+130h+var_100], r8
0x1400838f7  mov     al, [rdi]
0x1400838f9  mov     byte ptr [rsp+130h+var_108], al
0x1400838fd  mov     dword ptr [rsp+130h+var_110], r10d
0x140083902  call    WPP_SF__MAC_DcsssssssDDs_MAC__SSID_
0x140083907  mov     r14d, dword ptr [rbp+57h+Size]
0x14008390b  mov     esi, 200000h
0x140083910  mov     r15, [rbp+57h+arg_10]
0x140083914  mov     r12b, [rbp+57h+var_A0]
0x140083918  mov     rbx, [rbp+57h+Src]
0x14008391c  mov     r13, [rbp+57h+var_58]
0x140083920  mov     eax, cs:dword_1400B1050
0x140083926  test    eax, eax
0x140083928  jz      short loc_140083971
0x14008392a  mov     eax, cs:dword_1400B1050
0x140083930  cmp     eax, 5
0x140083933  jbe     short loc_140083971
0x140083935  mov     rdx, 200000000000h
0x14008393f  lea     rcx, dword_1400B1050
0x140083946  call    _tlgKeywordOn
0x14008394b  test    al, al
0x14008394d  jz      short loc_140083971
0x14008394f  movzx   eax, byte ptr [rdi]
0x140083952  lea     rdx, byte_1400A7635
0x140083959  mov     dword ptr [rbp+57h+arg_10], eax
0x14008395c  lea     rcx, dword_1400B1050
0x140083963  lea     rax, [rbp+57h+arg_10]
0x140083967  mov     [rsp+130h+var_110], rax
0x14008396c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140083971  test    r14d, r14d
0x140083974  jz      short loc_1400839C6
0x140083976  mov     rcx, cs:WPP_GLOBAL_Control
0x14008397d  lea     rax, WPP_GLOBAL_Control
0x140083984  cmp     rcx, rax
0x140083987  jz      short loc_1400839C6
0x140083989  cmp     byte ptr [rcx+29h], 4
0x14008398d  jb      short loc_1400839C6
0x14008398f  test    [rcx+2Ch], esi
0x140083992  jz      short loc_1400839C6
0x140083994  mov     rcx, [rcx+18h]
0x140083998  lea     r9, [rbp+57h+var_70]
0x14008399c  xorps   xmm0, xmm0
0x14008399f  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400839a6  movups  [rbp+57h+var_70], xmm0
0x1400839aa  mov     word ptr [rbp+57h+var_70], r14w
0x1400839af  mov     edx, 0BDh
0x1400839b4  mov     qword ptr [rbp+57h+var_70+8], rbx
0x1400839b8  movaps  xmm0, [rbp+57h+var_70]
0x1400839bc  movdqa  [rbp+57h+var_70], xmm0
0x1400839c1  call    WPP_SF__HEX_
0x1400839c6  lea     rax, [r13+4A8h]
0x1400839cd  mov     rcx, rax; SpinLock
0x1400839d0  mov     [rbp+57h+SpinLock], rax
0x1400839d4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400839db  nop     dword ptr [rax+rax+00h]
0x1400839e0  mov     [r13+4B0h], al
0x1400839e7  lea     r14, [r15+4]
0x1400839eb  mov     r9b, [r15+0Ah]; unsigned __int8
0x1400839ef  mov     r8d, 2; enum _WFD_RECEIVED_PACKET_TYPE
0x1400839f5  lea     rax, [rbp+57h+var_9F]
0x1400839f9  mov     rdx, r14; unsigned __int8 (*)[6]
0x1400839fc  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x1400839ff  mov     [rsp+130h+var_110], rax; unsigned __int8 *
0x140083a04  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x140083a09  test    eax, eax
0x140083a0b  js      loc_1400840C3
0x140083a11  cmp     [rbp+57h+var_9F], 0
0x140083a15  jnz     loc_1400840C3
0x140083a1b  lea     r8, [rbp+57h+var_88]; struct _WFD_PEER_DEVICE **
0x140083a1f  mov     byte ptr [rbp+57h+arg_10], 0
0x140083a23  mov     rdx, r14; unsigned __int8 (*)[6]
0x140083a26  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x140083a29  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x140083a2e  test    eax, eax
0x140083a30  jz      short loc_140083A6B
0x140083a32  mov     ebx, 0C000000Dh
0x140083a37  mov     rcx, cs:WPP_GLOBAL_Control
0x140083a3e  lea     rax, WPP_GLOBAL_Control
0x140083a45  cmp     rcx, rax
0x140083a48  jz      loc_140084104
0x140083a4e  mov     rcx, [rcx+18h]
0x140083a52  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140083a59  mov     edx, 0BFh
0x140083a5e  mov     r9, r14
0x140083a61  call    WPP_SF__MAC_
0x140083a66  jmp     loc_140084104
0x140083a6b  mov     r13, [rbp+57h+var_88]
0x140083a6f  mov     al, [r15+0Ah]
0x140083a73  cmp     [r13+28h], al
0x140083a77  jz      short loc_140083AAF
0x140083a79  mov     ebx, 0C0000001h
0x140083a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140083a85  lea     rax, WPP_GLOBAL_Control
0x140083a8c  cmp     rcx, rax
0x140083a8f  jz      loc_140084104
0x140083a95  mov     rcx, [rcx+18h]
0x140083a99  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140083aa0  mov     edx, 0C0h
0x140083aa5  call    WPP_SF_
0x140083aaa  jmp     loc_140084104
0x140083aaf  mov     rax, [rbp+57h+arg_0]
0x140083ab3  mov     edx, 1Ch
0x140083ab8  mov     rcx, r13
0x140083abb  mov     rax, [rax]
0x140083abe  mov     rax, [rax+1F68h]
0x140083ac5  mov     qword ptr [rbp+57h+var_70], rax
0x140083ac9  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x140083ace  test    al, al
0x140083ad0  jnz     short loc_140083B1F
0x140083ad2  mov     ebx, 0C0000184h
0x140083ad7  mov     rcx, cs:WPP_GLOBAL_Control
0x140083ade  lea     rax, WPP_GLOBAL_Control
0x140083ae5  cmp     rcx, rax
0x140083ae8  jz      loc_140084104
0x140083aee  cmp     byte ptr [rcx+29h], 3
0x140083af2  jb      loc_140084104
0x140083af8  test    [rcx+2Ch], esi
0x140083afb  jz      loc_140084104
0x140083b01  mov     r9d, [r13+24h]
0x140083b05  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140083b0c  mov     rcx, [rcx+18h]
0x140083b10  mov     edx, 0C1h
0x140083b15  call    WPP_SF_d
0x140083b1a  jmp     loc_140084104
0x140083b1f  mov     rcx, r13; struct _WFD_PEER_DEVICE *
0x140083b22  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCancelTimer(_WFD_PEER_DEVICE *)
0x140083b27  test    eax, eax
0x140083b29  jnz     short loc_140083B6A
0x140083b2b  xor     ebx, ebx
0x140083b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140083b34  lea     rax, WPP_GLOBAL_Control
0x140083b3b  cmp     rcx, rax
0x140083b3e  jz      short loc_140083B62
0x140083b40  cmp     byte ptr [rcx+29h], 1
0x140083b44  jb      short loc_140083B62
0x140083b46  test    [rcx+2Ch], esi
0x140083b49  jz      short loc_140083B62
0x140083b4b  mov     rcx, [rcx+18h]
0x140083b4f  lea     r9, [r13+18h]
0x140083b53  mov     edx, 0C2h
0x140083b58  mov     [rsp+130h+var_110], r13
0x140083b5d  call    WPP_SF__MAC_q
0x140083b62  mov     sil, bl
0x140083b65  jmp     loc_140084108
0x140083b6a  mov     rax, [r13+30h]
0x140083b6e  mov     [rbp+57h+var_50], rax
0x140083b72  movzx   eax, byte ptr [rdi]
0x140083b75  test    al, al
  ... truncated ...
```

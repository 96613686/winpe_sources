# WFDDeviceHandleReceivedGONRequest(_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *)

- ea: `0x1400829e0`
- end: `0x140083325`
- name: `?WFDDeviceHandleReceivedGONRequest@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS@@@Z`
- size: `2373`
- prototype: `void(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007c6b0`

## callees

- `0x140001ecc`
- `0x14000d22c`
- `0x14000d2c0`
- `0x140020dc0`
- `0x140020f20`
- `0x14002f1bc`
- `0x1400308ec`
- `0x140030da8`
- `0x14003d814`
- `0x14007a08c`
- `0x14007f254`
- `0x14007f5cc`
- `0x14008055c`
- `0x1400829e0`
- `0x1400863ec`
- `0x14008b744`
- `0x14008c308`
- `0x14008c660`
- `0x140097550`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140082aad`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140082aad`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140083271`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140083271`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083282`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083282`
- `ntoskrnl!KeReleaseSpinLock` at `0x140082e20`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008323e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140082e20`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008323e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140082db3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140082db3`

## pseudocode

```c
void __fastcall WFDDeviceHandleReceivedGONRequest(
        struct _WFD_ROLE *a1,
        unsigned int a2,
        struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *a3)
{
  struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *v3; // rbx
  unsigned int v6; // r15d
  __int64 v7; // r14
  void *pRoleExt; // r13
  _DWORD *v9; // rax
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  unsigned __int8 *v12; // r14
  __int64 v13; // rdi
  unsigned int v14; // r9d
  int v15; // eax
  __int64 v16; // rcx
  char v17; // bl
  const char *v18; // rdx
  const char *v19; // r13
  bool v20; // zf
  const char *v21; // r12
  const char *v22; // r15
  const char *v23; // r14
  const char *v24; // rsi
  const char *v25; // rdi
  int v26; // r8d
  int v27; // r9d
  _DEVICE_OBJECT *AttachedDevice; // rcx
  unsigned int v29; // r12d
  unsigned int v30; // edx
  struct _WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *v31; // r9
  unsigned __int8 v32; // al
  unsigned int v33; // r15d
  char v34; // r12
  unsigned __int8 *v35; // rax
  unsigned int v36; // r14d
  char v37; // r13
  char *v38; // rbx
  unsigned int CachedFrameIEs; // edi
  PDEVICE_OBJECT v40; // rcx
  __int64 v41; // rdx
  unsigned int v42; // r14d
  char v43; // r15
  const char *v44; // r8
  int v45; // eax
  unsigned int v46; // edi
  ULONG *v47; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v48; // rax
  unsigned __int8 v49; // [rsp+A0h] [rbp-80h] BYREF
  unsigned __int8 v50[3]; // [rsp+A1h] [rbp-7Fh] BYREF
  unsigned int v51; // [rsp+A4h] [rbp-7Ch] BYREF
  int v52; // [rsp+A8h] [rbp-78h] BYREF
  struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *v53; // [rsp+B0h] [rbp-70h] BYREF
  PDEVICE_OBJECT v54; // [rsp+B8h] [rbp-68h] BYREF
  char *v55; // [rsp+C0h] [rbp-60h]
  unsigned __int8 *v56; // [rsp+C8h] [rbp-58h]
  struct _WFD_ROLE *v57; // [rsp+D0h] [rbp-50h]
  const char *v58; // [rsp+D8h] [rbp-48h] BYREF
  unsigned int v59; // [rsp+E0h] [rbp-40h]
  unsigned int v60; // [rsp+E4h] [rbp-3Ch]
  _QWORD v61[2]; // [rsp+F0h] [rbp-30h] BYREF
  struct _WFD_PEER_DEVICE *v62; // [rsp+100h] [rbp-20h] BYREF
  _QWORD v63[12]; // [rsp+110h] [rbp-10h] BYREF
  unsigned __int8 v64[64]; // [rsp+170h] [rbp+50h] BYREF

  v3 = a3;
  v59 = a2;
  v57 = a1;
  v53 = a3;
  v62 = 0;
  v50[0] = 0;
  v49 = 5;
  memset(v63, 0, sizeof(v63));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 132, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
  v6 = *((_DWORD *)v3 + 7);
  v7 = *((unsigned int *)v3 + 6);
  v51 = v6;
  if ( (!v6 || (unsigned int)v7 >= 0x20) && v6 + (unsigned int)v7 >= (unsigned int)v7 && v6 + (unsigned int)v7 <= a2 )
  {
    pRoleExt = a1->pRoleExt;
    v61[0] = pRoleExt;
    v9 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
    if ( !v9 )
    {
      v55 = 0;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_50;
      v11 = 134;
      goto LABEL_10;
    }
    *(_QWORD *)v9 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    v12 = (unsigned __int8 *)v3 + v7;
    v13 = (__int64)(v9 + 4);
    v9[2] = 808679286;
    v55 = (char *)(v9 + 4);
    v60 = 0;
    v56 = v12;
    memset(v9 + 4, 0, 0x8Cu);
    if ( WFDValidateIncomingGONegotiationRequestIEs(v12, v6, v13) )
    {
      v54 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        v14 = *(unsigned __int8 *)(v13 + 56);
        v15 = *(_DWORD *)(v13 + 24);
        v16 = v13 + 92;
        v17 = *(_BYTE *)(v13 + 56);
        v18 = "Y";
        if ( !*(_DWORD *)(v13 + 48) )
          v18 = "N";
        v19 = "Y";
        v20 = *(_DWORD *)(v13 + 44) == 0;
        v21 = "Y";
        v22 = "Y";
        v58 = v18;
        if ( v20 )
          v19 = "N";
        v23 = "Y";
        v24 = "Y";
        if ( !*(_DWORD *)(v13 + 40) )
          v21 = "N";
        if ( !*(_DWORD *)(v13 + 36) )
          v22 = "N";
        if ( !*(_DWORD *)(v13 + 32) )
          v23 = "N";
        v20 = *(_DWORD *)(v13 + 28) == 0;
        v25 = "Y";
        if ( v20 )
          v24 = "N";
        if ( !v15 )
          v25 = "N";
        v52 = v14 >> 1;
        WPP_SF__MAC_DDDDD_MAC_sssssssH_WPSDEVICENAME_h(
          v54->AttachedDevice,
          *((unsigned __int8 *)v53 + 10),
          (_DWORD)v55 + 64,
          (_DWORD)v53 + 4,
          *((_BYTE *)v53 + 10),
          v14 >> 1,
          v17 & 1,
          v55[57],
          v55[58],
          (__int64)(v55 + 64),
          (__int64)v25,
          (__int64)v24,
          (__int64)v23,
          (__int64)v22,
          (__int64)v21,
          (__int64)v19,
          (__int64)v58,
          *((_WORD *)v55 + 41),
          v16,
          *((_WORD *)v55 + 68));
        v3 = v53;
        v6 = v51;
        v13 = (__int64)v55;
        pRoleExt = (void *)v61[0];
        v12 = v56;
      }
      if ( (unsigned int)dword_1400AE050 >= 6 && (unsigned __int8)tlgKeywordOn(&dword_1400AE050, 0x200000000000LL) )
      {
        v52 = *(unsigned __int8 *)(v13 + 58);
        v51 = *(unsigned __int8 *)(v13 + 57);
        LODWORD(v54) = *(_BYTE *)(v13 + 56) & 1;
        LODWORD(v58) = *(unsigned __int8 *)(v13 + 56) >> 1;
        LODWORD(v53) = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1400AE050,
          (unsigned int)byte_1400A55E1,
          v26,
          v27,
          (__int64)&v53,
          (__int64)&v58,
          (__int64)&v54,
          (__int64)&v51,
          (__int64)&v52);
      }
      if ( v6
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v61[0] = (unsigned __int16)v6;
        v61[1] = v12;
        WPP_SF__HEX_(AttachedDevice, 137, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v61);
      }
      *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
      if ( (int)WFDDeviceCheckDuplicateTransmission(
                  (struct _WFD_DEVICE_ROLE *)pRoleExt,
                  (unsigned __int8 (*)[6])((char *)v3 + 4),
                  0,
                  *((_BYTE *)v3 + 10),
                  v50) < 0
        || v50[0] )
      {
        v46 = -1073676267;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            138,
            WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
            *((unsigned __int8 *)v3 + 10));
        }
        KeReleaseSpinLock((PKSPIN_LOCK)pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
        goto LABEL_101;
      }
      v29 = 0;
      LODWORD(v53) = WFDDeviceFindPeerByMAC(
                       (struct _WFD_DEVICE_ROLE *)pRoleExt,
                       (unsigned __int8 (*)[6])((char *)v3 + 4),
                       &v62);
      if ( !(_DWORD)v53 )
        v29 = *((_DWORD *)v62 + 14);
      KeReleaseSpinLock((PKSPIN_LOCK)pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
      if ( (_DWORD)v53 )
        v32 = WFDDeviceHandleUnsolicitedGONRequest(v57, v30, v3, v31, &v49);
      else
        v32 = WFDDeviceHandleGONRequestForExistingPeer(
                v29,
                v57,
                v59,
                v3,
                (struct _WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *)v13,
                v6,
                v56,
                &v49);
      if ( v32 )
      {
        v46 = v60;
LABEL_101:
        if ( v55 )
        {
          v47 = (ULONG *)(v55 - 16);
          v48 = (struct _NPAGED_LOOKASIDE_LIST *)*((_QWORD *)v55 - 2);
          if ( v48 )
            ExFreeToNPagedLookasideList(v48, v47);
          else
            ExFreePoolWithTag(v47, v47[2]);
        }
        goto LABEL_109;
      }
    }
    else
    {
      v49 = 4;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        v11 = 135;
LABEL_10:
        WPP_SF_(v10->AttachedDevice, v11, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      }
    }
LABEL_50:
    v33 = 96;
    if ( !v49 )
      v49 = 5;
    v34 = v49;
    v35 = (unsigned __int8 *)*((_QWORD *)v3 + 2);
    v36 = 0;
    v37 = *((_BYTE *)v3 + 10);
    v38 = (char *)v3 + 4;
    v56 = v35;
    *(_WORD *)((char *)&v54 + 1) = 0;
    v51 = 0;
    LOBYTE(v54) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      v36 = v51;
    }
    if ( v38 )
    {
      v42 = v36 + 96;
      if ( v42 >= 0x60 )
      {
        if ( v42 > 0x60 )
        {
          CachedFrameIEs = -2147483643;
          v33 = v42;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v42, v42);
LABEL_81:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                70,
                WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                CachedFrameIEs);
            goto LABEL_83;
          }
          goto LABEL_83;
        }
        CachedFrameIEs = 0;
        memset(v63, 0, v42);
        HIDWORD(v63[0]) = *(_DWORD *)v38;
        LOWORD(v63[1]) = *((_WORD *)v38 + 2);
        v63[2] = v56;
        LODWORD(v63[0]) = 6291840;
        BYTE2(v63[1]) = v37;
        LODWORD(v63[3]) = 10000;
        BYTE4(v63[3]) = v34;
        LODWORD(v63[11]) = 96;
        HIDWORD(v63[11]) = v51;
        if ( v51 )
        {
          CachedFrameIEs = WFDRoleGetCachedFrameIEs(v57, 6u, &v51, v64);
          if ( CachedFrameIEs )
          {
            v40 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              v41 = 67;
              goto LABEL_57;
            }
            goto LABEL_83;
          }
          v34 = BYTE4(v63[3]);
          v43 = v63[2];
          v37 = BYTE2(v63[1]);
        }
        else
        {
          v43 = (char)v56;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
            WPP_SF__MAC_DqDcDDDD_MAC_C(
              WPP_GLOBAL_Control->AttachedDevice,
              68,
              (unsigned int)WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              (unsigned int)v63 + 4,
              v37,
              v43,
              v63[3],
              v34,
              BYTE5(v63[3]) >> 1,
              BYTE5(v63[3]) & 1,
              SBYTE6(v63[3]),
              SHIBYTE(v63[3]),
              (__int64)&v63[4]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
          {
            v44 = "Y";
            if ( !BYTE4(v63[10]) )
              v44 = "N";
            WPP_SF__MAC_s_MAC__SSID_DD(
              WPP_GLOBAL_Control->AttachedDevice,
              69,
              (unsigned int)WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              (unsigned int)v63 + 4,
              (__int64)v44,
              (__int64)&v63[5],
              (__int64)&v63[6],
              v63[11],
              SBYTE4(v63[11]));
          }
        }
        v33 = v42;
        goto LABEL_81;
      }
      CachedFrameIEs = -1073741675;
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v41 = 64;
        goto LABEL_57;
      }
    }
    else
    {
      CachedFrameIEs = -1073741811;
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v41 = 57;
LABEL_57:
        WPP_SF_(v40->AttachedDevice, v41, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        goto LABEL_81;
      }
    }
LABEL_83:
    if ( CachedFrameIEs
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, CachedFrameIEs);
    }
    v45 = NwifiSetDirectOidRequestAsync(v57->pGenVElan->pAdapt, 235208971, v63, v33);
    if ( v45 == 1076035585 )
      v45 = 0;
    v52 = v45;
    MapPendingDirectOidStatus(&v52);
    v46 = v52;
    if ( v52
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        140,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        (unsigned int)v52);
    }
    goto LABEL_101;
  }
  v46 = -1073676267;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer)
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
  {
    WPP_SF_DDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      133,
      WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
      (unsigned int)v7,
      v6,
      v6 + v7,
      a2);
  }
LABEL_109:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v46);
}

```

## disassembly

```asm
0x1400829e0  mov     [rsp-8+arg_18], rbx
0x1400829e5  push    rbp
0x1400829e6  push    rsi
0x1400829e7  push    rdi
0x1400829e8  push    r12
0x1400829ea  push    r13
0x1400829ec  push    r14
0x1400829ee  push    r15
0x1400829f0  lea     rbp, [rsp-60h]
0x1400829f5  sub     rsp, 180h
0x1400829fc  mov     rax, cs:__security_cookie
0x140082a03  xor     rax, rsp
0x140082a06  mov     qword ptr [rbp+90h+var_40], rax
0x140082a0a  mov     rbx, r8
0x140082a0d  mov     [rbp+90h+var_D0], edx
0x140082a10  mov     esi, edx
0x140082a12  mov     [rbp+90h+var_E0], rcx
0x140082a16  xor     edx, edx; Val
0x140082a18  mov     [rbp+90h+var_100], rbx
0x140082a1c  mov     rdi, rcx
0x140082a1f  mov     [rbp+90h+var_B0], 0
0x140082a27  lea     rcx, [rbp+90h+var_A0+1]; void *
0x140082a2b  mov     [rbp+90h+var_10F], 0
0x140082a2f  mov     [rbp+90h+var_110], 5
0x140082a33  lea     r8d, [rdx+5Fh]; Size
0x140082a37  mov     byte ptr [rbp+90h+var_A0], 0
0x140082a3b  call    memset
0x140082a40  mov     rcx, cs:WPP_GLOBAL_Control
0x140082a47  lea     r12, WPP_GLOBAL_Control
0x140082a4e  cmp     rcx, r12
0x140082a51  jz      short loc_140082A68
0x140082a53  mov     rcx, [rcx+18h]
0x140082a57  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140082a5e  mov     edx, 84h
0x140082a63  call    WPP_SF_
0x140082a68  mov     r15d, [rbx+1Ch]
0x140082a6c  mov     r14d, [rbx+18h]
0x140082a70  mov     [rbp+90h+var_10C], r15d
0x140082a74  test    r15d, r15d
0x140082a77  jz      short loc_140082A83
0x140082a79  cmp     r14d, 20h ; ' '
0x140082a7d  jb      loc_140083290
0x140082a83  lea     eax, [r15+r14]
0x140082a87  cmp     eax, r14d
0x140082a8a  jb      loc_140083290
0x140082a90  cmp     eax, esi
0x140082a92  ja      loc_140083290
0x140082a98  mov     r13, [rdi+0B8h]
0x140082a9f  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140082aa6  mov     rcx, rdi; Lookaside
0x140082aa9  mov     qword ptr [rbp+90h+var_C0], r13
0x140082aad  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140082ab4  nop     dword ptr [rax+rax+00h]
0x140082ab9  mov     esi, 200000h
0x140082abe  test    rax, rax
0x140082ac1  jnz     short loc_140082AF1
0x140082ac3  mov     [rbp+90h+var_F0], rax
0x140082ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x140082ace  cmp     rcx, r12
0x140082ad1  jz      loc_140082E7C
0x140082ad7  mov     edx, 86h
0x140082adc  mov     rcx, [rcx+18h]
0x140082ae0  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140082ae7  call    WPP_SF_
0x140082aec  jmp     loc_140082E7C
0x140082af1  mov     [rax], rdi
0x140082af4  add     r14, rbx
0x140082af7  lea     rdi, [rax+10h]
0x140082afb  mov     dword ptr [rax+8], 30337776h
0x140082b02  mov     rcx, rdi; void *
0x140082b05  mov     [rbp+90h+var_F0], rdi
0x140082b09  xor     edx, edx; Val
0x140082b0b  mov     [rbp+90h+var_CC], 0
0x140082b12  mov     r8d, 8Ch; Size
0x140082b18  mov     [rbp+90h+var_E8], r14
0x140082b1c  call    memset
0x140082b21  mov     r8, rdi
0x140082b24  mov     edx, r15d; unsigned int
0x140082b27  mov     rcx, r14; unsigned __int8 *
0x140082b2a  call    WFDValidateIncomingGONegotiationRequestIEs
0x140082b2f  test    al, al
0x140082b31  jnz     short loc_140082B64
0x140082b33  mov     [rbp+90h+var_110], 4
0x140082b37  mov     rcx, cs:WPP_GLOBAL_Control
0x140082b3e  cmp     rcx, r12
0x140082b41  jz      loc_140082E7C
0x140082b47  cmp     byte ptr [rcx+29h], 2
0x140082b4b  jb      loc_140082E7C
0x140082b51  test    [rcx+2Ch], esi
0x140082b54  jz      loc_140082E7C
0x140082b5a  mov     edx, 87h
0x140082b5f  jmp     loc_140082ADC
0x140082b64  mov     rax, cs:WPP_GLOBAL_Control
0x140082b6b  mov     [rbp+90h+var_F8], rax
0x140082b6f  cmp     rax, r12
0x140082b72  jz      loc_140082CBC
0x140082b78  cmp     byte ptr [rax+29h], 4
0x140082b7c  jb      loc_140082CBC
0x140082b82  test    [rax+2Ch], esi
0x140082b85  jz      loc_140082CBC
0x140082b8b  cmp     dword ptr [rdi+30h], 0
0x140082b8f  lea     r10, aN; "N"
0x140082b96  movzx   r9d, byte ptr [rdi+38h]
0x140082b9b  lea     r8, aY; "Y"
0x140082ba2  mov     eax, [rdi+18h]
0x140082ba5  lea     rcx, [rdi+5Ch]
0x140082ba9  mov     ebx, r9d
0x140082bac  mov     rdx, r8
0x140082baf  cmovz   rdx, r10
0x140082bb3  mov     r13, r8
0x140082bb6  cmp     dword ptr [rdi+2Ch], 0
0x140082bba  mov     r12, r8
0x140082bbd  mov     r15, r8
0x140082bc0  mov     [rbp+90h+var_D8], rdx
0x140082bc4  cmovz   r13, r10
0x140082bc8  mov     r14, r8
0x140082bcb  cmp     dword ptr [rdi+28h], 0
0x140082bcf  mov     rsi, r8
0x140082bd2  cmovz   r12, r10
0x140082bd6  cmp     dword ptr [rdi+24h], 0
0x140082bda  cmovz   r15, r10
0x140082bde  cmp     dword ptr [rdi+20h], 0
0x140082be2  cmovz   r14, r10
0x140082be6  cmp     dword ptr [rdi+1Ch], 0
0x140082bea  mov     rdi, r8
0x140082bed  cmovz   rsi, r10
0x140082bf1  test    eax, eax
0x140082bf3  mov     rax, [rbp+90h+var_F0]
0x140082bf7  cmovz   rdi, r10
0x140082bfb  and     ebx, 1
0x140082bfe  shr     r9d, 1
0x140082c01  mov     [rbp+90h+var_108], r9d
0x140082c05  movzx   r10d, byte ptr [rax+3Ah]
0x140082c0a  lea     r8, [rax+40h]
0x140082c0e  movzx   r11d, byte ptr [rax+39h]
0x140082c13  movzx   eax, word ptr [rax+88h]
0x140082c1a  mov     r9, [rbp+90h+var_100]
0x140082c1e  mov     [rsp+1B0h+var_118], ax
0x140082c26  mov     rax, [rbp+90h+var_F0]
0x140082c2a  mov     [rsp+1B0h+var_120], rcx
0x140082c32  movzx   edx, byte ptr [r9+0Ah]
0x140082c37  add     r9, 4
0x140082c3b  mov     rcx, [rbp+90h+var_F8]
0x140082c3f  movzx   eax, word ptr [rax+52h]
0x140082c43  mov     [rsp+1B0h+var_128], ax
0x140082c4b  mov     rax, [rbp+90h+var_D8]
0x140082c4f  mov     rcx, [rcx+18h]
0x140082c53  mov     [rsp+1B0h+var_130], rax
0x140082c5b  mov     eax, [rbp+90h+var_108]
0x140082c5e  mov     [rsp+1B0h+var_138], r13
0x140082c63  mov     [rsp+1B0h+var_140], r12
0x140082c68  mov     [rsp+1B0h+var_148], r15
0x140082c6d  mov     [rsp+1B0h+var_150], r14
0x140082c72  mov     [rsp+1B0h+var_158], rsi
0x140082c77  mov     [rsp+1B0h+var_160], rdi
0x140082c7c  mov     [rsp+1B0h+var_168], r8
0x140082c81  mov     dword ptr [rsp+1B0h+var_170], r10d
0x140082c86  mov     dword ptr [rsp+1B0h+var_178], r11d
0x140082c8b  mov     dword ptr [rsp+1B0h+var_180], ebx
0x140082c8f  mov     [rsp+1B0h+var_188], eax
0x140082c93  mov     dword ptr [rsp+1B0h+var_190], edx
0x140082c97  call    WPP_SF__MAC_DDDDD_MAC_sssssssH_WPSDEVICENAME_h
0x140082c9c  mov     rbx, [rbp+90h+var_100]
0x140082ca0  lea     r12, WPP_GLOBAL_Control
0x140082ca7  mov     r15d, [rbp+90h+var_10C]
0x140082cab  mov     esi, 200000h
0x140082cb0  mov     rdi, [rbp+90h+var_F0]
0x140082cb4  mov     r13, qword ptr [rbp+90h+var_C0]
0x140082cb8  mov     r14, [rbp+90h+var_E8]
0x140082cbc  mov     eax, cs:dword_1400AE050
0x140082cc2  test    eax, eax
0x140082cc4  jz      loc_140082D5B
0x140082cca  mov     eax, cs:dword_1400AE050
0x140082cd0  cmp     eax, 5
0x140082cd3  jbe     loc_140082D5B
0x140082cd9  mov     rdx, 200000000000h
0x140082ce3  lea     rcx, dword_1400AE050
0x140082cea  call    _tlgKeywordOn
0x140082cef  test    al, al
0x140082cf1  jz      short loc_140082D5B
0x140082cf3  movzx   eax, byte ptr [rdi+3Ah]
0x140082cf7  lea     rdx, byte_1400A55E1
0x140082cfe  mov     [rbp+90h+var_108], eax
0x140082d01  lea     rcx, dword_1400AE050
0x140082d08  movzx   eax, byte ptr [rdi+39h]
0x140082d0c  mov     [rbp+90h+var_10C], eax
0x140082d0f  movzx   eax, byte ptr [rdi+38h]
0x140082d13  and     eax, 1
0x140082d16  mov     dword ptr [rbp+90h+var_F8], eax
0x140082d19  movzx   eax, byte ptr [rdi+38h]
0x140082d1d  shr     eax, 1
0x140082d1f  mov     dword ptr [rbp+90h+var_D8], eax
0x140082d22  lea     rax, [rbp+90h+var_108]
0x140082d26  mov     [rsp+1B0h+var_170], rax
0x140082d2b  lea     rax, [rbp+90h+var_10C]
0x140082d2f  mov     [rsp+1B0h+var_178], rax
0x140082d34  lea     rax, [rbp+90h+var_F8]
0x140082d38  mov     [rsp+1B0h+var_180], rax
0x140082d3d  lea     rax, [rbp+90h+var_D8]
0x140082d41  mov     qword ptr [rsp+1B0h+var_188], rax
0x140082d46  lea     rax, [rbp+90h+var_100]
0x140082d4a  mov     [rsp+1B0h+var_190], rax
0x140082d4f  mov     dword ptr [rbp+90h+var_100], 0
0x140082d56  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140082d5b  test    r15d, r15d
0x140082d5e  jz      short loc_140082DA9
0x140082d60  mov     rcx, cs:WPP_GLOBAL_Control
0x140082d67  cmp     rcx, r12
0x140082d6a  jz      short loc_140082DA9
0x140082d6c  cmp     byte ptr [rcx+29h], 4
0x140082d70  jb      short loc_140082DA9
0x140082d72  test    [rcx+2Ch], esi
0x140082d75  jz      short loc_140082DA9
0x140082d77  mov     rcx, [rcx+18h]
0x140082d7b  lea     r9, [rbp+90h+var_C0]
0x140082d7f  xorps   xmm0, xmm0
0x140082d82  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140082d89  movups  [rbp+90h+var_C0], xmm0
0x140082d8d  mov     word ptr [rbp+90h+var_C0], r15w
0x140082d92  mov     edx, 89h
0x140082d97  mov     qword ptr [rbp+90h+var_C0+8], r14
0x140082d9b  movaps  xmm0, [rbp+90h+var_C0]
0x140082d9f  movdqa  [rbp+90h+var_C0], xmm0
0x140082da4  call    WPP_SF__HEX_
0x140082da9  lea     r14, [r13+4A8h]
0x140082db0  mov     rcx, r14; SpinLock
0x140082db3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140082dba  nop     dword ptr [rax+rax+00h]
0x140082dbf  lea     rcx, [rbp+90h+var_10F]
0x140082dc3  mov     [r13+4B0h], al
0x140082dca  mov     r9b, [rbx+0Ah]; unsigned __int8
0x140082dce  xor     r8d, r8d; enum _WFD_RECEIVED_PACKET_TYPE
0x140082dd1  mov     [rsp+1B0h+var_190], rcx; unsigned __int8 *
0x140082dd6  lea     rdx, [rbx+4]; unsigned __int8 (*)[6]
0x140082dda  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x140082ddd  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x140082de2  test    eax, eax
0x140082de4  js      loc_140083201
0x140082dea  cmp     [rbp+90h+var_10F], 0
0x140082dee  jnz     loc_140083201
0x140082df4  lea     r8, [rbp+90h+var_B0]; struct _WFD_PEER_DEVICE **
0x140082df8  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x140082dfb  lea     rdx, [rbx+4]; unsigned __int8 (*)[6]
0x140082dff  xor     r12d, r12d
0x140082e02  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x140082e07  mov     dword ptr [rbp+90h+var_100], eax
0x140082e0a  test    eax, eax
0x140082e0c  jnz     short loc_140082E16
0x140082e0e  mov     rdx, [rbp+90h+var_B0]
0x140082e12  mov     r12d, [rdx+38h]
0x140082e16  mov     dl, [r13+4B0h]; NewIrql
0x140082e1d  mov     rcx, r14; SpinLock
0x140082e20  call    cs:__imp_KeReleaseSpinLock
0x140082e27  nop     dword ptr [rax+rax+00h]
0x140082e2c  cmp     dword ptr [rbp+90h+var_100], 0
0x140082e30  lea     rax, [rbp+90h+var_110]
0x140082e34  jnz     short loc_140082E63
0x140082e36  mov     r8d, [rbp+90h+var_D0]; unsigned int
0x140082e3a  mov     r9, rbx; struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *
0x140082e3d  mov     rdx, [rbp+90h+var_E0]; struct _WFD_ROLE *
0x140082e41  mov     ecx, r12d; unsigned int
0x140082e44  mov     [rsp+1B0h+var_178], rax; unsigned __int8 *
0x140082e49  mov     rax, [rbp+90h+var_E8]
0x140082e4d  mov     [rsp+1B0h+var_180], rax; unsigned __int8 *
0x140082e52  mov     [rsp+1B0h+var_188], r15d; unsigned int
0x140082e57  mov     [rsp+1B0h+var_190], rdi; struct _WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *
0x140082e5c  call    ?WFDDeviceHandleGONRequestForExistingPeer@@YAEKPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS@@PEAU_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES@@KPEAE3@Z; WFDDeviceHandleGONRequestForExistingPeer(ulong,_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *,_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *,ulong,uchar *,uchar *)
0x140082e61  jmp     short loc_140082E74
0x140082e63  mov     rcx, [rbp+90h+var_E0]; struct _WFD_ROLE *
0x140082e67  mov     r8, rbx; struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *
0x140082e6a  mov     [rsp+1B0h+var_190], rax; unsigned __int8 *
0x140082e6f  call    ?WFDDeviceHandleUnsolicitedGONRequest@@YAEPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS@@PEAU_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES@@PEAE@Z; WFDDeviceHandleUnsolicitedGONRequest(_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *,_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *,uchar *)
0x140082e74  test    al, al
0x140082e76  jnz     loc_14008324C
0x140082e7c  cmp     [rbp+90h+var_110], 0
0x140082e80  mov     r15d, 60h ; '`'
0x140082e86  jnz     short loc_140082E8C
0x140082e88  mov     [rbp+90h+var_110], 5
0x140082e8c  mov     r12b, [rbp+90h+var_110]
0x140082e90  test    r12b, r12b
0x140082e93  jnz     short loc_140082EA6
0x140082e95  mov     edi, 0C000000Dh
0x140082e9a  lea     r12, WPP_GLOBAL_Control
0x140082ea1  jmp     loc_140083164
0x140082ea6  mov     rax, [rbx+10h]
0x140082eaa  xor     r14d, r14d
0x140082ead  mov     r13b, [rbx+0Ah]
0x140082eb1  add     rbx, 4
0x140082eb5  mov     [rbp+90h+var_E8], rax
0x140082eb9  xor     eax, eax
0x140082ebb  mov     word ptr [rbp+90h+var_F8+1], ax
0x140082ebf  mov     [rbp+90h+var_10C], r14d
0x140082ec3  mov     byte ptr [rbp+90h+var_F8], r14b
0x140082ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x140082ece  lea     rax, WPP_GLOBAL_Control
0x140082ed5  cmp     rcx, rax
0x140082ed8  jz      short loc_140082EF2
0x140082eda  mov     rcx, [rcx+18h]
0x140082ede  lea     edx, [r14+38h]
0x140082ee2  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
  ... truncated ...
```

# WFDDeviceHandleReceivedGONRequest(_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *)

- ea: `0x140084210`
- end: `0x140084b55`
- name: `?WFDDeviceHandleReceivedGONRequest@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS@@@Z`
- size: `2373`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007dee0`

## callees

- `0x140001ecc`
- `0x14000d21c`
- `0x14000d2b0`
- `0x140020dc0`
- `0x140020f20`
- `0x14002f44c`
- `0x140030b7c`
- `0x140031038`
- `0x14003da34`
- `0x14007b8bc`
- `0x140080a84`
- `0x140080dfc`
- `0x140081d8c`
- `0x140084210`
- `0x140087c1c`
- `0x14008cf74`
- `0x14008db38`
- `0x14008de90`
- `0x140098d30`
- `0x14009bbb0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400842dd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400842dd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084aa1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084aa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084ab2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084ab2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084650`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084a6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084650`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084a6e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400845e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400845e3`

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
  char *v13; // rdi
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
    v13 = (char *)(v9 + 4);
    v9[2] = 808679286;
    v55 = (char *)(v9 + 4);
    v60 = 0;
    v56 = v12;
    memset(v9 + 4, 0, 0x8Cu);
    if ( (unsigned __int8)WFDValidateIncomingGONegotiationRequestIEs(v12, v6) )
    {
      v54 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        v14 = (unsigned __int8)v13[56];
        v15 = *((_DWORD *)v13 + 6);
        v16 = (__int64)(v13 + 92);
        v17 = v13[56];
        v18 = "Y";
        if ( !*((_DWORD *)v13 + 12) )
          v18 = "N";
        v19 = "Y";
        v20 = *((_DWORD *)v13 + 11) == 0;
        v21 = "Y";
        v22 = "Y";
        v58 = v18;
        if ( v20 )
          v19 = "N";
        v23 = "Y";
        v24 = "Y";
        if ( !*((_DWORD *)v13 + 10) )
          v21 = "N";
        if ( !*((_DWORD *)v13 + 9) )
          v22 = "N";
        if ( !*((_DWORD *)v13 + 8) )
          v23 = "N";
        v20 = *((_DWORD *)v13 + 7) == 0;
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
        v13 = v55;
        pRoleExt = (void *)v61[0];
        v12 = v56;
      }
      if ( (unsigned int)dword_1400B1050 >= 6 && (unsigned __int8)tlgKeywordOn(&dword_1400B1050, 0x200000000000LL) )
      {
        v52 = (unsigned __int8)v13[58];
        v51 = (unsigned __int8)v13[57];
        LODWORD(v54) = v13[56] & 1;
        LODWORD(v58) = (unsigned __int8)v13[56] >> 1;
        LODWORD(v53) = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1400B1050,
          (unsigned int)byte_1400A76E1,
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
                  WfdReceivedPacketTypeGONRequest,
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
          CachedFrameIEs = WFDRoleGetCachedFrameIEs(v57, MANAGEMENT_FRAME_TYPE_GO_NEGOTIATION_RESPONSE, &v51, v64);
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
    v45 = NwifiSetDirectOidRequestAsync(v57->pGenVElan->pAdapt, 0xE05010Bu, v63, v33);
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
0x140084210  mov     [rsp-8+arg_18], rbx
0x140084215  push    rbp
0x140084216  push    rsi
0x140084217  push    rdi
0x140084218  push    r12
0x14008421a  push    r13
0x14008421c  push    r14
0x14008421e  push    r15
0x140084220  lea     rbp, [rsp-60h]
0x140084225  sub     rsp, 180h
0x14008422c  mov     rax, cs:__security_cookie
0x140084233  xor     rax, rsp
0x140084236  mov     qword ptr [rbp+90h+var_40], rax
0x14008423a  mov     rbx, r8
0x14008423d  mov     [rbp+90h+var_D0], edx
0x140084240  mov     esi, edx
0x140084242  mov     [rbp+90h+var_E0], rcx
0x140084246  xor     edx, edx; Val
0x140084248  mov     [rbp+90h+var_100], rbx
0x14008424c  mov     rdi, rcx
0x14008424f  mov     [rbp+90h+var_B0], 0
0x140084257  lea     rcx, [rbp+90h+var_A0+1]; void *
0x14008425b  mov     [rbp+90h+var_10F], 0
0x14008425f  mov     [rbp+90h+var_110], 5
0x140084263  lea     r8d, [rdx+5Fh]; Size
0x140084267  mov     byte ptr [rbp+90h+var_A0], 0
0x14008426b  call    memset
0x140084270  mov     rcx, cs:WPP_GLOBAL_Control
0x140084277  lea     r12, WPP_GLOBAL_Control
0x14008427e  cmp     rcx, r12
0x140084281  jz      short loc_140084298
0x140084283  mov     rcx, [rcx+18h]
0x140084287  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008428e  mov     edx, 84h
0x140084293  call    WPP_SF_
0x140084298  mov     r15d, [rbx+1Ch]
0x14008429c  mov     r14d, [rbx+18h]
0x1400842a0  mov     [rbp+90h+var_10C], r15d
0x1400842a4  test    r15d, r15d
0x1400842a7  jz      short loc_1400842B3
0x1400842a9  cmp     r14d, 20h ; ' '
0x1400842ad  jb      loc_140084AC0
0x1400842b3  lea     eax, [r15+r14]
0x1400842b7  cmp     eax, r14d
0x1400842ba  jb      loc_140084AC0
0x1400842c0  cmp     eax, esi
0x1400842c2  ja      loc_140084AC0
0x1400842c8  mov     r13, [rdi+0B8h]
0x1400842cf  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400842d6  mov     rcx, rdi; Lookaside
0x1400842d9  mov     qword ptr [rbp+90h+var_C0], r13
0x1400842dd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400842e4  nop     dword ptr [rax+rax+00h]
0x1400842e9  mov     esi, 200000h
0x1400842ee  test    rax, rax
0x1400842f1  jnz     short loc_140084321
0x1400842f3  mov     [rbp+90h+var_F0], rax
0x1400842f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400842fe  cmp     rcx, r12
0x140084301  jz      loc_1400846AC
0x140084307  mov     edx, 86h
0x14008430c  mov     rcx, [rcx+18h]
0x140084310  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140084317  call    WPP_SF_
0x14008431c  jmp     loc_1400846AC
0x140084321  mov     [rax], rdi
0x140084324  add     r14, rbx
0x140084327  lea     rdi, [rax+10h]
0x14008432b  mov     dword ptr [rax+8], 30337776h
0x140084332  mov     rcx, rdi; void *
0x140084335  mov     [rbp+90h+var_F0], rdi
0x140084339  xor     edx, edx; Val
0x14008433b  mov     [rbp+90h+var_CC], 0
0x140084342  mov     r8d, 8Ch; Size
0x140084348  mov     [rbp+90h+var_E8], r14
0x14008434c  call    memset
0x140084351  mov     r8, rdi
0x140084354  mov     edx, r15d; unsigned int
0x140084357  mov     rcx, r14; unsigned __int8 *
0x14008435a  call    WFDValidateIncomingGONegotiationRequestIEs
0x14008435f  test    al, al
0x140084361  jnz     short loc_140084394
0x140084363  mov     [rbp+90h+var_110], 4
0x140084367  mov     rcx, cs:WPP_GLOBAL_Control
0x14008436e  cmp     rcx, r12
0x140084371  jz      loc_1400846AC
0x140084377  cmp     byte ptr [rcx+29h], 2
0x14008437b  jb      loc_1400846AC
0x140084381  test    [rcx+2Ch], esi
0x140084384  jz      loc_1400846AC
0x14008438a  mov     edx, 87h
0x14008438f  jmp     loc_14008430C
0x140084394  mov     rax, cs:WPP_GLOBAL_Control
0x14008439b  mov     [rbp+90h+var_F8], rax
0x14008439f  cmp     rax, r12
0x1400843a2  jz      loc_1400844EC
0x1400843a8  cmp     byte ptr [rax+29h], 4
0x1400843ac  jb      loc_1400844EC
0x1400843b2  test    [rax+2Ch], esi
0x1400843b5  jz      loc_1400844EC
0x1400843bb  cmp     dword ptr [rdi+30h], 0
0x1400843bf  lea     r10, aN; "N"
0x1400843c6  movzx   r9d, byte ptr [rdi+38h]
0x1400843cb  lea     r8, aY; "Y"
0x1400843d2  mov     eax, [rdi+18h]
0x1400843d5  lea     rcx, [rdi+5Ch]
0x1400843d9  mov     ebx, r9d
0x1400843dc  mov     rdx, r8
0x1400843df  cmovz   rdx, r10
0x1400843e3  mov     r13, r8
0x1400843e6  cmp     dword ptr [rdi+2Ch], 0
0x1400843ea  mov     r12, r8
0x1400843ed  mov     r15, r8
0x1400843f0  mov     [rbp+90h+var_D8], rdx
0x1400843f4  cmovz   r13, r10
0x1400843f8  mov     r14, r8
0x1400843fb  cmp     dword ptr [rdi+28h], 0
0x1400843ff  mov     rsi, r8
0x140084402  cmovz   r12, r10
0x140084406  cmp     dword ptr [rdi+24h], 0
0x14008440a  cmovz   r15, r10
0x14008440e  cmp     dword ptr [rdi+20h], 0
0x140084412  cmovz   r14, r10
0x140084416  cmp     dword ptr [rdi+1Ch], 0
0x14008441a  mov     rdi, r8
0x14008441d  cmovz   rsi, r10
0x140084421  test    eax, eax
0x140084423  mov     rax, [rbp+90h+var_F0]
0x140084427  cmovz   rdi, r10
0x14008442b  and     ebx, 1
0x14008442e  shr     r9d, 1
0x140084431  mov     [rbp+90h+var_108], r9d
0x140084435  movzx   r10d, byte ptr [rax+3Ah]
0x14008443a  lea     r8, [rax+40h]
0x14008443e  movzx   r11d, byte ptr [rax+39h]
0x140084443  movzx   eax, word ptr [rax+88h]
0x14008444a  mov     r9, [rbp+90h+var_100]
0x14008444e  mov     [rsp+1B0h+var_118], ax
0x140084456  mov     rax, [rbp+90h+var_F0]
0x14008445a  mov     [rsp+1B0h+var_120], rcx
0x140084462  movzx   edx, byte ptr [r9+0Ah]
0x140084467  add     r9, 4
0x14008446b  mov     rcx, [rbp+90h+var_F8]
0x14008446f  movzx   eax, word ptr [rax+52h]
0x140084473  mov     [rsp+1B0h+var_128], ax
0x14008447b  mov     rax, [rbp+90h+var_D8]
0x14008447f  mov     rcx, [rcx+18h]
0x140084483  mov     [rsp+1B0h+var_130], rax
0x14008448b  mov     eax, [rbp+90h+var_108]
0x14008448e  mov     [rsp+1B0h+var_138], r13
0x140084493  mov     [rsp+1B0h+var_140], r12
0x140084498  mov     [rsp+1B0h+var_148], r15
0x14008449d  mov     [rsp+1B0h+var_150], r14
0x1400844a2  mov     [rsp+1B0h+var_158], rsi
0x1400844a7  mov     [rsp+1B0h+var_160], rdi
0x1400844ac  mov     [rsp+1B0h+var_168], r8
0x1400844b1  mov     dword ptr [rsp+1B0h+var_170], r10d
0x1400844b6  mov     dword ptr [rsp+1B0h+var_178], r11d
0x1400844bb  mov     dword ptr [rsp+1B0h+var_180], ebx
0x1400844bf  mov     [rsp+1B0h+var_188], eax
0x1400844c3  mov     dword ptr [rsp+1B0h+var_190], edx
0x1400844c7  call    WPP_SF__MAC_DDDDD_MAC_sssssssH_WPSDEVICENAME_h
0x1400844cc  mov     rbx, [rbp+90h+var_100]
0x1400844d0  lea     r12, WPP_GLOBAL_Control
0x1400844d7  mov     r15d, [rbp+90h+var_10C]
0x1400844db  mov     esi, 200000h
0x1400844e0  mov     rdi, [rbp+90h+var_F0]
0x1400844e4  mov     r13, qword ptr [rbp+90h+var_C0]
0x1400844e8  mov     r14, [rbp+90h+var_E8]
0x1400844ec  mov     eax, cs:dword_1400B1050
0x1400844f2  test    eax, eax
0x1400844f4  jz      loc_14008458B
0x1400844fa  mov     eax, cs:dword_1400B1050
0x140084500  cmp     eax, 5
0x140084503  jbe     loc_14008458B
0x140084509  mov     rdx, 200000000000h
0x140084513  lea     rcx, dword_1400B1050
0x14008451a  call    _tlgKeywordOn
0x14008451f  test    al, al
0x140084521  jz      short loc_14008458B
0x140084523  movzx   eax, byte ptr [rdi+3Ah]
0x140084527  lea     rdx, byte_1400A76E1
0x14008452e  mov     [rbp+90h+var_108], eax
0x140084531  lea     rcx, dword_1400B1050
0x140084538  movzx   eax, byte ptr [rdi+39h]
0x14008453c  mov     [rbp+90h+var_10C], eax
0x14008453f  movzx   eax, byte ptr [rdi+38h]
0x140084543  and     eax, 1
0x140084546  mov     dword ptr [rbp+90h+var_F8], eax
0x140084549  movzx   eax, byte ptr [rdi+38h]
0x14008454d  shr     eax, 1
0x14008454f  mov     dword ptr [rbp+90h+var_D8], eax
0x140084552  lea     rax, [rbp+90h+var_108]
0x140084556  mov     [rsp+1B0h+var_170], rax
0x14008455b  lea     rax, [rbp+90h+var_10C]
0x14008455f  mov     [rsp+1B0h+var_178], rax
0x140084564  lea     rax, [rbp+90h+var_F8]
0x140084568  mov     [rsp+1B0h+var_180], rax
0x14008456d  lea     rax, [rbp+90h+var_D8]
0x140084571  mov     qword ptr [rsp+1B0h+var_188], rax
0x140084576  lea     rax, [rbp+90h+var_100]
0x14008457a  mov     [rsp+1B0h+var_190], rax
0x14008457f  mov     dword ptr [rbp+90h+var_100], 0
0x140084586  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14008458b  test    r15d, r15d
0x14008458e  jz      short loc_1400845D9
0x140084590  mov     rcx, cs:WPP_GLOBAL_Control
0x140084597  cmp     rcx, r12
0x14008459a  jz      short loc_1400845D9
0x14008459c  cmp     byte ptr [rcx+29h], 4
0x1400845a0  jb      short loc_1400845D9
0x1400845a2  test    [rcx+2Ch], esi
0x1400845a5  jz      short loc_1400845D9
0x1400845a7  mov     rcx, [rcx+18h]
0x1400845ab  lea     r9, [rbp+90h+var_C0]
0x1400845af  xorps   xmm0, xmm0
0x1400845b2  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400845b9  movups  [rbp+90h+var_C0], xmm0
0x1400845bd  mov     word ptr [rbp+90h+var_C0], r15w
0x1400845c2  mov     edx, 89h
0x1400845c7  mov     qword ptr [rbp+90h+var_C0+8], r14
0x1400845cb  movaps  xmm0, [rbp+90h+var_C0]
0x1400845cf  movdqa  [rbp+90h+var_C0], xmm0
0x1400845d4  call    WPP_SF__HEX_
0x1400845d9  lea     r14, [r13+4A8h]
0x1400845e0  mov     rcx, r14; SpinLock
0x1400845e3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400845ea  nop     dword ptr [rax+rax+00h]
0x1400845ef  lea     rcx, [rbp+90h+var_10F]
0x1400845f3  mov     [r13+4B0h], al
0x1400845fa  mov     r9b, [rbx+0Ah]; unsigned __int8
0x1400845fe  xor     r8d, r8d; enum _WFD_RECEIVED_PACKET_TYPE
0x140084601  mov     [rsp+1B0h+var_190], rcx; unsigned __int8 *
0x140084606  lea     rdx, [rbx+4]; unsigned __int8 (*)[6]
0x14008460a  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x14008460d  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x140084612  test    eax, eax
0x140084614  js      loc_140084A31
0x14008461a  cmp     [rbp+90h+var_10F], 0
0x14008461e  jnz     loc_140084A31
0x140084624  lea     r8, [rbp+90h+var_B0]; struct _WFD_PEER_DEVICE **
0x140084628  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x14008462b  lea     rdx, [rbx+4]; unsigned __int8 (*)[6]
0x14008462f  xor     r12d, r12d
0x140084632  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x140084637  mov     dword ptr [rbp+90h+var_100], eax
0x14008463a  test    eax, eax
0x14008463c  jnz     short loc_140084646
0x14008463e  mov     rdx, [rbp+90h+var_B0]
0x140084642  mov     r12d, [rdx+38h]
0x140084646  mov     dl, [r13+4B0h]; NewIrql
0x14008464d  mov     rcx, r14; SpinLock
0x140084650  call    cs:__imp_KeReleaseSpinLock
0x140084657  nop     dword ptr [rax+rax+00h]
0x14008465c  cmp     dword ptr [rbp+90h+var_100], 0
0x140084660  lea     rax, [rbp+90h+var_110]
0x140084664  jnz     short loc_140084693
0x140084666  mov     r8d, [rbp+90h+var_D0]; unsigned int
0x14008466a  mov     r9, rbx; struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *
0x14008466d  mov     rdx, [rbp+90h+var_E0]; struct _WFD_ROLE *
0x140084671  mov     ecx, r12d; unsigned int
0x140084674  mov     [rsp+1B0h+var_178], rax; unsigned __int8 *
0x140084679  mov     rax, [rbp+90h+var_E8]
0x14008467d  mov     [rsp+1B0h+var_180], rax; unsigned __int8 *
0x140084682  mov     [rsp+1B0h+var_188], r15d; unsigned int
0x140084687  mov     [rsp+1B0h+var_190], rdi; struct _WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *
0x14008468c  call    ?WFDDeviceHandleGONRequestForExistingPeer@@YAEKPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS@@PEAU_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES@@KPEAE3@Z; WFDDeviceHandleGONRequestForExistingPeer(ulong,_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *,_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *,ulong,uchar *,uchar *)
0x140084691  jmp     short loc_1400846A4
0x140084693  mov     rcx, [rbp+90h+var_E0]; struct _WFD_ROLE *
0x140084697  mov     r8, rbx; struct _DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *
0x14008469a  mov     [rsp+1B0h+var_190], rax; unsigned __int8 *
0x14008469f  call    ?WFDDeviceHandleUnsolicitedGONRequest@@YAEPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS@@PEAU_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES@@PEAE@Z; WFDDeviceHandleUnsolicitedGONRequest(_WFD_ROLE *,ulong,_DOT11_RECEIVED_GO_NEGOTIATION_REQUEST_PARAMETERS *,_WFD_GO_NEGOTIATION_REQUEST_ATTRIBUTES *,uchar *)
0x1400846a4  test    al, al
0x1400846a6  jnz     loc_140084A7C
0x1400846ac  cmp     [rbp+90h+var_110], 0
0x1400846b0  mov     r15d, 60h ; '`'
0x1400846b6  jnz     short loc_1400846BC
0x1400846b8  mov     [rbp+90h+var_110], 5
0x1400846bc  mov     r12b, [rbp+90h+var_110]
0x1400846c0  test    r12b, r12b
0x1400846c3  jnz     short loc_1400846D6
0x1400846c5  mov     edi, 0C000000Dh
0x1400846ca  lea     r12, WPP_GLOBAL_Control
0x1400846d1  jmp     loc_140084994
0x1400846d6  mov     rax, [rbx+10h]
0x1400846da  xor     r14d, r14d
0x1400846dd  mov     r13b, [rbx+0Ah]
0x1400846e1  add     rbx, 4
0x1400846e5  mov     [rbp+90h+var_E8], rax
0x1400846e9  xor     eax, eax
0x1400846eb  mov     word ptr [rbp+90h+var_F8+1], ax
0x1400846ef  mov     [rbp+90h+var_10C], r14d
0x1400846f3  mov     byte ptr [rbp+90h+var_F8], r14b
0x1400846f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400846fe  lea     rax, WPP_GLOBAL_Control
0x140084705  cmp     rcx, rax
0x140084708  jz      short loc_140084722
0x14008470a  mov     rcx, [rcx+18h]
0x14008470e  lea     edx, [r14+38h]
0x140084712  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
  ... truncated ...
```

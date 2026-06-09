# HandleIncomingProvisionDiscoveryRequestForExistingPeer(_WFD_PEER_DEVICE *,_WFD_DEVICE_ROLE *,_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *,_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar *)

- ea: `0x14007e374`
- end: `0x14007eb4b`
- name: `?HandleIncomingProvisionDiscoveryRequestForExistingPeer@@YAEPEAU_WFD_PEER_DEVICE@@PEAU_WFD_DEVICE_ROLE@@PEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS@@PEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@PEAE@Z`
- size: `2007`
- prototype: `char __fastcall(struct _WFD_PEER_DEVICE *, struct _WFD_DEVICE_ROLE *, struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *, struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008538c`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x140022f08`
- `0x14002ffb4`
- `0x14003ae2c`
- `0x140063578`
- `0x14007e374`
- `0x14007ec58`
- `0x140088d48`
- `0x14008942c`
- `0x140089588`
- `0x14008a780`
- `0x14008af58`
- `0x14008b44c`
- `0x14008c60c`
- `0x14008cb24`
- `0x140097400`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007eb09`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007eb09`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eb1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eb1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007e7ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007e7ac`

## pseudocode

```c
char __fastcall HandleIncomingProvisionDiscoveryRequestForExistingPeer(
        struct _WFD_PEER_DEVICE *a1,
        struct _WFD_DEVICE_ROLE *a2,
        struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *a3,
        struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *a4,
        unsigned __int8 *a5)
{
  struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *v7; // r15
  int v8; // r9d
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  char v11; // r12
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // r10d
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  unsigned int v18; // ecx
  char v19; // dl
  __int64 v20; // r9
  char v21; // r14
  char v22; // al
  int v23; // r8d
  bool v24; // zf
  unsigned __int8 v25; // si
  __int64 v26; // r9
  char *v27; // r14
  unsigned int v28; // eax
  struct _WFD_ROLE *v29; // rcx
  unsigned int v30; // esi
  unsigned int v31; // eax
  __int64 v32; // rcx
  unsigned int v33; // esi
  int v34; // eax
  char v35; // r8
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  int v39; // eax
  int v40; // eax
  unsigned __int8 v42; // [rsp+20h] [rbp-E0h]
  char v43; // [rsp+70h] [rbp-90h]
  unsigned __int8 v44; // [rsp+71h] [rbp-8Fh]
  char v45; // [rsp+72h] [rbp-8Eh]
  enum _DOT11_WPS_CONFIG_METHOD v46[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _WFD_DEVICE_ROLE *v47; // [rsp+80h] [rbp-80h]
  struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *v48; // [rsp+88h] [rbp-78h] BYREF
  struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *v49; // [rsp+90h] [rbp-70h]
  _OWORD v50[9]; // [rsp+A0h] [rbp-60h] BYREF

  v49 = a3;
  v47 = a2;
  *(_QWORD *)v46 = a5;
  v43 = 0;
  memset(v50, 0, 0x88u);
  v7 = 0;
  *a5 = 1;
  v44 = 0;
  v48 = 0;
  if ( !*((_BYTE *)a1 + 616) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF__MAC_(
        WPP_GLOBAL_Control->AttachedDevice,
        320,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        (char *)a1 + 24);
    }
    v11 = 0;
    v45 = 0;
    goto LABEL_72;
  }
  v8 = *((_DWORD *)a4 + 16);
  v45 = 0;
  if ( !v8 )
    goto LABEL_123;
  v9 = *(_QWORD *)((char *)a1 + 676) - *(_QWORD *)((char *)a4 + 68);
  if ( !v9 )
    v9 = *((unsigned int *)a1 + 171) - (unsigned __int64)*((unsigned int *)a4 + 19);
  if ( v9 )
    goto LABEL_123;
  v10 = *((_QWORD *)a1 + 86) - *((_QWORD *)a4 + 10);
  if ( !v10 )
    v10 = *((unsigned int *)a1 + 174) - (unsigned __int64)*((unsigned int *)a4 + 22);
  if ( v10 )
  {
LABEL_123:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_lDD_MAC__MAC_DD_MAC__MAC_D(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)a4 + 84,
        (_DWORD)a1 + 692,
        v8,
        *((_DWORD *)a1 + 169),
        *((_DWORD *)a4 + 17),
        (__int64)a1 + 680,
        (__int64)a4 + 72,
        *((_DWORD *)a1 + 172),
        *((_DWORD *)a4 + 20),
        (__int64)a1 + 692,
        (__int64)a4 + 84);
    }
    v11 = 0;
    goto LABEL_72;
  }
  if ( !(unsigned __int8)WFDPeerDeviceSetState(a1, 16) )
  {
    v11 = 0;
LABEL_72:
    v21 = 1;
    v25 = 0;
    goto LABEL_73;
  }
  if ( !(unsigned int)WFDPeerDeviceCancelTimer(a1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF__MAC_q(WPP_GLOBAL_Control->AttachedDevice, 321, v13, (char *)a1 + 24, a1);
    }
    goto LABEL_116;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
  {
    v42 = *((_BYTE *)a4 + 60);
    WPP_SF__MAC_D(WPP_GLOBAL_Control->AttachedDevice, v12, v13, (char *)a1 + 24);
  }
  v14 = *((_DWORD *)a1 + 134);
  *(_QWORD *)&v50[0] = *((_QWORD *)a1 + 6);
  DWORD2(v50[0]) = 0;
  v15 = v14 & 0x1000 | 0x80;
  if ( (v14 & 0x80u) == 0 )
    v15 = v14 & 0x1000;
  v16 = v15 | 0x100;
  if ( (v14 & 8) == 0 )
    v16 = v15;
  v17 = v16 | 8;
  if ( (v14 & 0x100) == 0 )
    v17 = v16;
  v18 = v17 | 0x40;
  if ( (v14 & 0x40) == 0 )
    v18 = v17;
  v19 = *((_BYTE *)a4 + 60);
  v20 = v18 | 0x40;
  if ( (v14 & 0x20) == 0 )
    v20 = v18;
  if ( !v19 || v19 == 12 )
  {
    v23 = *((_DWORD *)a4 + 2);
    if ( v23 )
    {
      if ( v23 == (_DWORD)v20 )
      {
        v21 = 0;
        if ( !v19
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 326, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        }
        v24 = *((_DWORD *)a4 + 37) == 0;
        BYTE12(v50[0]) = *((_BYTE *)a4 + 60);
        LODWORD(v50[1]) = *((_DWORD *)a4 + 2);
        DWORD1(v50[1]) = *((_DWORD *)a4 + 35);
        BYTE8(v50[1]) = *((_BYTE *)a4 + 144);
        WORD5(v50[1]) = *((_WORD *)a4 + 84);
        v44 = *((_BYTE *)a1 + 856);
        v22 = 1;
        v45 = 1;
        BYTE9(v50[1]) = BYTE9(v50[1]) & 0xFE | !v24;
        goto LABEL_56;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      {
        WPP_SF_lll(
          WPP_GLOBAL_Control->AttachedDevice,
          325,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          v20,
          v14,
          v23);
      }
      DWORD2(v50[0]) = -1073741629;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 324, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      }
      DWORD2(v50[0]) = -1073741616;
    }
    v11 = 0;
    v21 = 1;
    v22 = 0;
    goto LABEL_57;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      323,
      WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
      *((unsigned __int8 *)a4 + 60));
  }
  v21 = 0;
  BYTE12(v50[0]) = *((_BYTE *)a4 + 60);
  v22 = 1;
  v45 = 0;
LABEL_56:
  v11 = 1;
LABEL_57:
  v43 = v22;
  WFDPeerDeviceDestroy(a1);
  if ( !v21 && !v45 && !v43 )
    return v43;
  v25 = v44;
LABEL_73:
  KeReleaseSpinLock((PKSPIN_LOCK)v47 + 149, *((_BYTE *)v47 + 1200));
  **(_BYTE **)v46 = 0;
  if ( v45 )
  {
    v26 = *((unsigned int *)a4 + 2);
    if ( (v26 & 0x11E8) != 0 )
    {
      LODWORD(v7) = *((_DWORD *)a4 + 2);
      v46[0] = (int)v7;
    }
    else
    {
      v46[0] = DOT11_WPS_CONFIG_METHOD_NULL;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_84:
        v27 = (char *)v49 + 4;
        v28 = WFDDeviceBuildProvisionDiscoveryResponseParams(
                *(struct _WFD_ROLE **)v47,
                *((_BYTE *)v49 + 16),
                *((void **)v49 + 3),
                (unsigned __int8 (*)[6])((char *)v49 + 4),
                (enum _DOT11_WPS_CONFIG_METHOD)v7,
                v25,
                a4,
                1,
                &v48);
        v30 = v28;
        if ( v28 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer)
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 329, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v28);
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF__MAC_L(
              WPP_GLOBAL_Control->AttachedDevice,
              330,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              v27,
              v30);
          v7 = v48;
          goto LABEL_116;
        }
        v7 = v48;
        v31 = WFDDeviceSendProvisionDiscoveryResponse(v29, *(struct _ADAPT **)(**(_QWORD **)v47 + 16LL), v46[0], v48);
        v33 = v31;
        if ( v31 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer)
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 331, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v31);
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF__MAC_L(
              WPP_GLOBAL_Control->AttachedDevice,
              332,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              v27,
              v33);
          goto LABEL_116;
        }
        v43 = 1;
        if ( !v11 )
        {
LABEL_116:
          if ( v7 )
          {
            if ( *((_QWORD *)v7 - 2) )
              ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v7 - 2), (char *)v7 - 16);
            else
              ExFreePoolWithTag((char *)v7 - 16, *((_DWORD *)v7 - 2));
          }
          return v43;
        }
        BYTE12(v50[1]) |= 1u;
        LOBYTE(v32) = *((_BYTE *)v7 + 92);
        LOWORD(v46[0]) = 0;
        BYTE2(v46[0]) = 0;
        v34 = WFDUtilConvertConnectionCapabilityFromUChar(v32, v46);
        if ( v34 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              333,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              (unsigned int)v34);
          goto LABEL_116;
        }
        v24 = *((_DWORD *)a4 + 14) == 0;
        HIBYTE(v50[1]) = BYTE1(v46[0]);
        BYTE13(v50[1]) = v46[0];
        BYTE14(v50[1]) = BYTE2(v46[0]);
        if ( !v24 )
        {
          v36 = *(_OWORD *)((char *)a4 + 12);
          LOBYTE(v50[2]) |= v35;
          v37 = *(_OWORD *)((char *)a4 + 28);
          *(_OWORD *)((char *)&v50[2] + 4) = v36;
          v38 = *(_OWORD *)((char *)a4 + 40);
          *(_OWORD *)((char *)&v50[3] + 4) = v37;
          v50[4] = v38;
        }
        if ( *((_BYTE *)v7 + 44) )
        {
          LOBYTE(v50[5]) |= v35;
          *(_OWORD *)((char *)&v50[5] + 4) = *((_OWORD *)v7 + 3);
          *(_OWORD *)((char *)&v50[6] + 4) = *((_OWORD *)v7 + 4);
          v50[7] = *(_OWORD *)((char *)v7 + 76);
        }
        if ( *((_DWORD *)a4 + 45) )
        {
          v39 = *((_DWORD *)a4 + 46);
          LOBYTE(v50[8]) |= v35;
          *(_DWORD *)((char *)&v50[8] + 1) = v39;
          *(_WORD *)((char *)&v50[8] + 5) = *((_WORD *)a4 + 94);
        }
LABEL_115:
        WFDDeviceSendUpCallRequest(*(_QWORD *)(**(_QWORD **)v47 + 8040LL), 25, v50);
        goto LABEL_116;
      }
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 327, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v26, 4584);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        328,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        v25,
        *(unsigned __int8 *)(*(_QWORD *)v47 + 124LL));
    }
    goto LABEL_84;
  }
  if ( !v21 )
  {
LABEL_114:
    if ( !v11 )
      goto LABEL_116;
    goto LABEL_115;
  }
  v40 = WFDDeviceSendProvisionDiscoveryFailureResponse(
          *(struct _ADAPT **)(**(_QWORD **)v47 + 16LL),
          *((_BYTE *)v49 + 16),
          *((void **)v49 + 3),
          (unsigned __int8 (*)[6])((char *)v49 + 4),
          v42);
  if ( !v40 )
  {
    v43 = 1;
    goto LABEL_114;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF__MAC_L(
      WPP_GLOBAL_Control->AttachedDevice,
      335,
      WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
      (char *)v49 + 4,
      v40);
  return v43;
}

```

## disassembly

```asm
0x14007e374  push    rbp
0x14007e376  push    rbx
0x14007e377  push    rsi
0x14007e378  push    rdi
0x14007e379  push    r12
0x14007e37b  push    r13
0x14007e37d  push    r14
0x14007e37f  push    r15
0x14007e381  lea     rbp, [rsp-48h]
0x14007e386  sub     rsp, 148h
0x14007e38d  mov     rax, cs:__security_cookie
0x14007e394  xor     rax, rsp
0x14007e397  mov     [rbp+80h+var_50], rax
0x14007e39b  mov     rdi, [rbp+80h+arg_20]
0x14007e3a2  mov     rsi, rcx
0x14007e3a5  mov     [rbp+80h+var_F0], r8
0x14007e3a9  lea     rcx, [rbp+80h+var_E0]; void *
0x14007e3ad  mov     [rbp+80h+var_100], rdx
0x14007e3b1  mov     r8d, 88h; Size
0x14007e3b7  xor     edx, edx; Val
0x14007e3b9  mov     qword ptr [rsp+180h+var_108], rdi
0x14007e3be  mov     rbx, r9
0x14007e3c1  mov     [rsp+180h+var_110], 0
0x14007e3c6  call    memset
0x14007e3cb  xor     r15d, r15d
0x14007e3ce  mov     byte ptr [rdi], 1
0x14007e3d1  lea     rdi, WPP_GLOBAL_Control
0x14007e3d8  mov     [rsp+180h+var_10F], 0
0x14007e3dd  lea     r12, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007e3e4  mov     [rbp+80h+var_F8], r15
0x14007e3e8  mov     r14b, 3
0x14007e3eb  cmp     [rsi+268h], r15b
0x14007e3f2  jz      loc_14007E762
0x14007e3f8  mov     r9d, [rbx+40h]
0x14007e3fc  mov     [rsp+180h+var_10E], r15b
0x14007e401  test    r9d, r9d
0x14007e404  jz      loc_14007E6E7
0x14007e40a  mov     rcx, [rsi+2A4h]
0x14007e411  sub     rcx, [rbx+44h]
0x14007e415  jnz     short loc_14007E423
0x14007e417  mov     ecx, [rsi+2ACh]
0x14007e41d  mov     eax, [rbx+4Ch]
0x14007e420  sub     rcx, rax
0x14007e423  test    rcx, rcx
0x14007e426  jnz     loc_14007E6E7
0x14007e42c  mov     rcx, [rsi+2B0h]
0x14007e433  sub     rcx, [rbx+50h]
0x14007e437  jnz     short loc_14007E445
0x14007e439  mov     ecx, [rsi+2B8h]
0x14007e43f  mov     eax, [rbx+58h]
0x14007e442  sub     rcx, rax
0x14007e445  test    rcx, rcx
0x14007e448  jnz     loc_14007E6E7
0x14007e44e  lea     edx, [rcx+10h]
0x14007e451  mov     rcx, rsi
0x14007e454  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x14007e459  test    al, al
0x14007e45b  jnz     short loc_14007E465
0x14007e45d  xor     r12d, r12d
0x14007e460  jmp     loc_14007E798
0x14007e465  mov     rcx, rsi; struct _WFD_PEER_DEVICE *
0x14007e468  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCancelTimer(_WFD_PEER_DEVICE *)
0x14007e46d  test    eax, eax
0x14007e46f  jnz     short loc_14007E4B9
0x14007e471  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e478  lea     rdi, WPP_GLOBAL_Control
0x14007e47f  cmp     rcx, rdi
0x14007e482  jz      loc_14007EAF2
0x14007e488  cmp     byte ptr [rcx+29h], 1
0x14007e48c  jb      loc_14007EAF2
0x14007e492  bt      dword ptr [rcx+2Ch], 15h
0x14007e497  jnb     loc_14007EAF2
0x14007e49d  mov     rcx, [rcx+18h]
0x14007e4a1  lea     r9, [rsi+18h]
0x14007e4a5  mov     edx, 141h
0x14007e4aa  mov     qword ptr [rsp+180h+var_160], rsi
0x14007e4af  call    WPP_SF__MAC_q
0x14007e4b4  jmp     loc_14007EAF2
0x14007e4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e4c0  cmp     rcx, rdi
0x14007e4c3  jz      short loc_14007E4E7
0x14007e4c5  cmp     [rcx+29h], r14b
0x14007e4c9  jb      short loc_14007E4E7
0x14007e4cb  bt      dword ptr [rcx+2Ch], 15h
0x14007e4d0  jnb     short loc_14007E4E7
0x14007e4d2  movzx   eax, byte ptr [rbx+3Ch]
0x14007e4d6  lea     r9, [rsi+18h]
0x14007e4da  mov     rcx, [rcx+18h]
0x14007e4de  mov     [rsp+180h+var_160], eax
0x14007e4e2  call    WPP_SF__MAC_D
0x14007e4e7  mov     r10d, [rsi+218h]
0x14007e4ee  mov     r8d, 100h
0x14007e4f4  mov     rax, [rsi+30h]
0x14007e4f8  mov     ecx, r10d
0x14007e4fb  and     ecx, 1000h
0x14007e501  mov     [rbp+80h+var_E0], rax
0x14007e505  mov     edx, ecx
0x14007e507  mov     [rbp+80h+var_D8], r15d
0x14007e50b  bts     edx, 7
0x14007e50f  test    r10b, 80h
0x14007e513  cmovz   edx, ecx
0x14007e516  mov     ecx, edx
0x14007e518  or      ecx, r8d
0x14007e51b  test    r10b, 8
0x14007e51f  cmovz   ecx, edx
0x14007e522  mov     edx, ecx
0x14007e524  or      edx, 8
0x14007e527  test    r8d, r10d
0x14007e52a  cmovz   edx, ecx
0x14007e52d  mov     ecx, edx
0x14007e52f  or      ecx, 40h
0x14007e532  test    r10b, 40h
0x14007e536  cmovz   ecx, edx
0x14007e539  movzx   edx, byte ptr [rbx+3Ch]
0x14007e53d  mov     r9d, ecx
0x14007e540  or      r9d, 40h
0x14007e544  test    r10b, 20h
0x14007e548  cmovz   r9d, ecx
0x14007e54c  test    dl, dl
0x14007e54e  jz      short loc_14007E596
0x14007e550  cmp     dl, 0Ch
0x14007e553  jz      short loc_14007E596
0x14007e555  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e55c  cmp     rcx, rdi
0x14007e55f  jz      short loc_14007E581
0x14007e561  cmp     [rcx+29h], r14b
0x14007e565  jb      short loc_14007E581
0x14007e567  bt      dword ptr [rcx+2Ch], 15h
0x14007e56c  jnb     short loc_14007E581
0x14007e56e  mov     rcx, [rcx+18h]
0x14007e572  mov     r9d, edx
0x14007e575  lea     edx, [r8+43h]
0x14007e579  mov     r8, r12
0x14007e57c  call    WPP_SF_d
0x14007e581  mov     al, [rbx+3Ch]
0x14007e584  xor     r14b, r14b
0x14007e587  mov     [rbp+80h+var_D4], al
0x14007e58a  mov     al, 1
0x14007e58c  mov     [rsp+180h+var_10E], r14b
0x14007e591  jmp     loc_14007E69E
0x14007e596  mov     r8d, [rbx+8]
0x14007e59a  test    r8d, r8d
0x14007e59d  jnz     short loc_14007E5DE
0x14007e59f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e5a6  cmp     rcx, rdi
0x14007e5a9  jz      short loc_14007E5C9
0x14007e5ab  cmp     [rcx+29h], r14b
0x14007e5af  jb      short loc_14007E5C9
0x14007e5b1  bt      dword ptr [rcx+2Ch], 15h
0x14007e5b6  jnb     short loc_14007E5C9
0x14007e5b8  mov     rcx, [rcx+18h]
0x14007e5bc  mov     edx, 144h
0x14007e5c1  mov     r8, r12
0x14007e5c4  call    WPP_SF_
0x14007e5c9  mov     [rbp+80h+var_D8], 0C00000D0h
0x14007e5d0  xor     r12b, r12b
0x14007e5d3  mov     r14b, 1
0x14007e5d6  mov     al, r12b
0x14007e5d9  jmp     loc_14007E6A1
0x14007e5de  cmp     r8d, r9d
0x14007e5e1  jz      short loc_14007E620
0x14007e5e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e5ea  cmp     rcx, rdi
0x14007e5ed  jz      short loc_14007E617
0x14007e5ef  cmp     [rcx+29h], r14b
0x14007e5f3  jb      short loc_14007E617
0x14007e5f5  bt      dword ptr [rcx+2Ch], 15h
0x14007e5fa  jnb     short loc_14007E617
0x14007e5fc  mov     rcx, [rcx+18h]
0x14007e600  mov     edx, 145h
0x14007e605  mov     dword ptr [rsp+180h+var_158], r8d
0x14007e60a  mov     r8, r12
0x14007e60d  mov     [rsp+180h+var_160], r10d
0x14007e612  call    WPP_SF_lll
0x14007e617  mov     [rbp+80h+var_D8], 0C00000C3h
0x14007e61e  jmp     short loc_14007E5D0
0x14007e620  xor     r14b, r14b
0x14007e623  test    dl, dl
0x14007e625  jnz     short loc_14007E651
0x14007e627  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e62e  cmp     rcx, rdi
0x14007e631  jz      short loc_14007E651
0x14007e633  cmp     byte ptr [rcx+29h], 2
0x14007e637  jb      short loc_14007E651
0x14007e639  bt      dword ptr [rcx+2Ch], 15h
0x14007e63e  jnb     short loc_14007E651
0x14007e640  mov     rcx, [rcx+18h]
0x14007e644  mov     edx, 146h
0x14007e649  mov     r8, r12
0x14007e64c  call    WPP_SF_
0x14007e651  mov     al, [rbx+3Ch]
0x14007e654  cmp     [rbx+94h], r15d
0x14007e65b  mov     [rbp+80h+var_D4], al
0x14007e65e  mov     eax, [rbx+8]
0x14007e661  setnz   dl
0x14007e664  mov     [rbp+80h+var_D0], eax
0x14007e667  mov     eax, [rbx+8Ch]
0x14007e66d  mov     [rbp+80h+var_CC], eax
0x14007e670  mov     al, [rbx+90h]
0x14007e676  mov     [rbp+80h+var_C8], al
0x14007e679  mov     al, [rbp+80h+var_C7]
0x14007e67c  and     al, 0FEh
0x14007e67e  or      dl, al
0x14007e680  movzx   eax, word ptr [rbx+0A8h]
0x14007e687  mov     [rbp+80h+var_C6], ax
0x14007e68b  mov     al, [rsi+358h]
0x14007e691  mov     [rsp+180h+var_10F], al
0x14007e695  mov     al, 1
0x14007e697  mov     [rsp+180h+var_10E], al
0x14007e69b  mov     [rbp+80h+var_C7], dl
0x14007e69e  mov     r12b, al
0x14007e6a1  mov     cl, [rsp+180h+var_10F]
0x14007e6a5  mov     [rsp+180h+var_10F], cl
0x14007e6a9  mov     rcx, rsi; struct _WFD_PEER_DEVICE *
0x14007e6ac  mov     [rsp+180h+var_110], al
0x14007e6b0  call    ?WFDPeerDeviceDestroy@@YAXPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceDestroy(_WFD_PEER_DEVICE *)
0x14007e6b5  mov     al, [rsp+180h+var_10E]
0x14007e6b9  mov     [rsp+180h+var_10E], al
0x14007e6bd  test    r14b, r14b
0x14007e6c0  jnz     short loc_14007E6DB
0x14007e6c2  test    al, al
0x14007e6c4  jnz     short loc_14007E6DB
0x14007e6c6  cmp     [rsp+180h+var_110], r15b
0x14007e6cb  jz      loc_14007EB26
0x14007e6d1  mov     sil, [rsp+180h+var_10F]
0x14007e6d6  jmp     loc_14007E79E
0x14007e6db  mov     sil, [rsp+180h+var_110]
0x14007e6e0  mov     [rsp+180h+var_110], sil
0x14007e6e5  jmp     short loc_14007E6D1
0x14007e6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e6ee  cmp     rcx, rdi
0x14007e6f1  jz      short loc_14007E75D
0x14007e6f3  cmp     [rcx+29h], r14b
0x14007e6f7  jb      short loc_14007E75D
0x14007e6f9  bt      dword ptr [rcx+2Ch], 15h
0x14007e6fe  jnb     short loc_14007E75D
0x14007e700  movzx   eax, byte ptr [rbx+3Ch]
0x14007e704  lea     rdx, [rbx+54h]
0x14007e708  mov     rcx, [rcx+18h]
0x14007e70c  lea     r8, [rsi+2B4h]
0x14007e713  mov     [rsp+180h+var_120], eax
0x14007e717  lea     r10, [rbx+48h]
0x14007e71b  mov     eax, [rbx+50h]
0x14007e71e  lea     r11, [rsi+2A8h]
0x14007e725  mov     [rsp+180h+var_128], rdx
0x14007e72a  mov     [rsp+180h+var_130], r8
0x14007e72f  mov     [rsp+180h+var_138], eax
0x14007e733  mov     eax, [rsi+2B0h]
0x14007e739  mov     dword ptr [rsp+180h+var_140], eax
0x14007e73d  mov     eax, [rbx+44h]
0x14007e740  mov     qword ptr [rsp+180h+var_148], r10
0x14007e745  mov     [rsp+180h+var_150], r11
0x14007e74a  mov     dword ptr [rsp+180h+var_158], eax
0x14007e74e  mov     eax, [rsi+2A4h]
0x14007e754  mov     [rsp+180h+var_160], eax
0x14007e758  call    WPP_SF_lDD_MAC__MAC_DD_MAC__MAC_D
0x14007e75d  xor     r12b, r12b
0x14007e760  jmp     short loc_14007E798
0x14007e762  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e769  cmp     rcx, rdi
0x14007e76c  jz      short loc_14007E790
0x14007e76e  cmp     [rcx+29h], r14b
0x14007e772  jb      short loc_14007E790
0x14007e774  bt      dword ptr [rcx+2Ch], 15h
0x14007e779  jnb     short loc_14007E790
0x14007e77b  mov     rcx, [rcx+18h]
0x14007e77f  lea     r9, [rsi+18h]
0x14007e783  mov     edx, 140h
0x14007e788  mov     r8, r12
0x14007e78b  call    WPP_SF__MAC_
0x14007e790  xor     r12b, r12b
0x14007e793  mov     [rsp+180h+var_10E], r12b
0x14007e798  mov     r14b, 1
0x14007e79b  mov     sil, r12b
0x14007e79e  mov     rcx, [rbp+80h+var_100]
0x14007e7a2  add     rcx, 4A8h; SpinLock
0x14007e7a9  mov     dl, [rcx+8]; NewIrql
0x14007e7ac  call    cs:__imp_KeReleaseSpinLock
0x14007e7b3  nop     dword ptr [rax+rax+00h]
0x14007e7b8  mov     rax, qword ptr [rsp+180h+var_108]
0x14007e7bd  mov     [rax], r15b
0x14007e7c0  cmp     [rsp+180h+var_10E], r15b
0x14007e7c5  jz      loc_14007EA68
0x14007e7cb  mov     r9d, [rbx+8]
0x14007e7cf  mov     r8d, 11E8h
0x14007e7d5  test    r8d, r9d
0x14007e7d8  jz      short loc_14007E7E4
0x14007e7da  mov     r15d, r9d
0x14007e7dd  mov     [rsp+180h+var_108], r9d
0x14007e7e2  jmp     short loc_14007E81C
0x14007e7e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e7eb  mov     [rsp+180h+var_108], r15d
0x14007e7f0  cmp     rcx, rdi
0x14007e7f3  jz      short loc_14007E85F
0x14007e7f5  cmp     byte ptr [rcx+29h], 3
0x14007e7f9  jb      short loc_14007E81C
0x14007e7fb  bt      dword ptr [rcx+2Ch], 15h
0x14007e800  jnb     short loc_14007E81C
0x14007e802  mov     rcx, [rcx+18h]
0x14007e806  mov     edx, 147h
  ... truncated ...
```

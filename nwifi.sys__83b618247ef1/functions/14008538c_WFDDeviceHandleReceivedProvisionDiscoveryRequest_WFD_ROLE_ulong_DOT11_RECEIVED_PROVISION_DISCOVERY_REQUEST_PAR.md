# WFDDeviceHandleReceivedProvisionDiscoveryRequest(_WFD_ROLE *,ulong,_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *)

- ea: `0x14008538c`
- end: `0x1400859f6`
- name: `?WFDDeviceHandleReceivedProvisionDiscoveryRequest@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS@@@Z`
- size: `1642`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14007c8b0`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x140024058`
- `0x14002f1bc`
- `0x14002ffb4`
- `0x14007e374`
- `0x14007ec58`
- `0x14007f254`
- `0x14007f5cc`
- `0x14008538c`
- `0x1400888a8`
- `0x140088d48`
- `0x14008942c`
- `0x14008970c`
- `0x14008b4a4`
- `0x14008d078`
- `0x140097e38`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400854c2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400854c2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140085904`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008593c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140085904`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008593c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085915`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085950`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085915`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085950`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400856b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400856b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140085574`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140085574`

## pseudocode

```c
void __fastcall WFDDeviceHandleReceivedProvisionDiscoveryRequest(
        struct _WFD_ROLE *a1,
        unsigned int a2,
        struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *a3)
{
  __int64 v3; // r13
  __int64 v5; // r8
  struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *v7; // r15
  int v8; // r11d
  unsigned int v9; // ecx
  int v10; // edx
  __int64 v11; // rax
  _DEVICE_OBJECT *AttachedDevice; // rcx
  unsigned __int8 v13; // r12
  _DWORD *v14; // rax
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  KIRQL v17; // al
  struct _WFD_DEVICE_ROLE *v18; // rcx
  unsigned __int8 v19; // r9
  unsigned __int8 *v20; // rdx
  enum _DOT11_WPS_CONFIG_METHOD v21; // r12d
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // eax
  void *v25; // r8
  unsigned int v26; // eax
  __int64 v27; // r9
  unsigned int v28; // eax
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  unsigned __int8 v31; // [rsp+20h] [rbp-60h]
  char v32; // [rsp+50h] [rbp-30h]
  unsigned __int8 v33[7]; // [rsp+51h] [rbp-2Fh] BYREF
  struct _WFD_DEVICE_ROLE *pRoleExt; // [rsp+58h] [rbp-28h]
  struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *v35; // [rsp+60h] [rbp-20h] BYREF
  struct _WFD_PEER_DEVICE *v36; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v37[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int8 v39; // [rsp+D0h] [rbp+50h] BYREF
  char v40; // [rsp+D8h] [rbp+58h]

  v3 = 0;
  v36 = 0;
  v5 = a2;
  v33[0] = 0;
  v39 = 0;
  v7 = 0;
  v35 = 0;
  if ( a3 && (unsigned int)v5 >= 0x28 )
  {
    v8 = *((_DWORD *)a3 + 9);
    if ( !v8 || (v9 = *((_DWORD *)a3 + 8), v9 >= 0x28) )
    {
      v9 = *((_DWORD *)a3 + 8);
      if ( v9 + v8 >= v9 && v9 + v8 <= (unsigned int)v5 )
      {
        pRoleExt = (struct _WFD_DEVICE_ROLE *)a1->pRoleExt;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          v31 = *((_BYTE *)a3 + 16);
          WPP_SF__MAC_DDD(WPP_GLOBAL_Control->AttachedDevice, 338, WPP_GLOBAL_Control, (char *)a3 + 4);
        }
        v10 = *((_DWORD *)a3 + 9);
        if ( v10
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          v11 = *((unsigned int *)a3 + 8);
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          v37[0] = (unsigned __int16)v10;
          v37[1] = (char *)a3 + v11;
          WPP_SF__HEX_(AttachedDevice, 339, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v37);
        }
        v32 = 0;
        v13 = 0;
        v14 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
        if ( v14 )
        {
          v14[2] = 808679286;
          v3 = (__int64)(v14 + 4);
          *(_QWORD *)v14 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
          memset(v14 + 4, 0, 0xC0u);
          if ( WFDValidateIncomingProvisionDiscoveryRequestIEs(
                 (__int64)a3 + 4,
                 (unsigned __int8 *)a3 + *((unsigned int *)a3 + 8),
                 *((_DWORD *)a3 + 9),
                 v3) )
          {
            v40 = 1;
            v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
            v18 = pRoleExt;
            *((_BYTE *)pRoleExt + 1200) = v17;
            v19 = *((_BYTE *)a3 + 16);
            v39 = 1;
            if ( (int)WFDDeviceCheckDuplicateTransmission(
                        v18,
                        (unsigned __int8 (*)[6])((char *)a3 + 4),
                        WfdReceivedPacketTypeProvisionDiscoveryRequest,
                        v19,
                        v33) < 0
              || v33[0] )
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  342,
                  WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                  *((unsigned __int8 *)a3 + 16));
              }
              v13 = 1;
            }
            else
            {
              if ( !(unsigned int)WFDDeviceFindPeerByMAC(pRoleExt, (unsigned __int8 (*)[6])((char *)a3 + 4), &v36) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                  && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 343, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                  v20 = (unsigned __int8 *)a3 + 4;
                }
                v13 = 1;
              }
              if ( !WFDDeviceValidateProvisionDiscoveryRequestAttributes(
                      (struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *)v3,
                      (unsigned __int8 (*)[6])v20,
                      0,
                      v13,
                      0) )
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                  && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 344, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                }
              }
              if ( v13 )
              {
                v13 = HandleIncomingProvisionDiscoveryRequestForExistingPeer(
                        v36,
                        pRoleExt,
                        a3,
                        (struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *)v3,
                        &v39);
              }
              else
              {
                v32 = 1;
                v13 = 0;
              }
            }
LABEL_49:
            if ( v39 )
            {
              KeReleaseSpinLock((PKSPIN_LOCK)pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
              v39 = 0;
            }
            if ( v13 )
              goto LABEL_94;
            v21 = DOT11_WPS_CONFIG_METHOD_NULL;
            v22 = 4584;
            if ( v32 )
            {
              v23 = *(unsigned int *)(v3 + 8);
              if ( (v23 & 0x11E8) != 0 )
              {
                v21 = *(_DWORD *)(v3 + 8);
              }
              else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                     && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                WPP_SF_Dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  345,
                  WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                  v23,
                  4584);
              }
              v24 = WFDDeviceBuildProvisionDiscoveryResponseParams(
                      a1,
                      *((_BYTE *)a3 + 16),
                      *((void **)a3 + 3),
                      (unsigned __int8 (*)[6])((char *)a3 + 4),
                      v21,
                      a1->ConnectionCapability,
                      (struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *)v3,
                      0,
                      &v35);
              if ( v24 )
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control->Timer)
                  && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    346,
                    WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                    v24);
                }
              }
              v7 = v35;
            }
            if ( v40 )
            {
              if ( (unsigned __int8)WFDDeviceIsIncomingPacketTypeFiltered(a1, 4, v22) )
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                  && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 348, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                }
              }
              else
              {
                v26 = WFDDeviceIndicateIncomingProvisionDiscoveryRequest(
                        (struct _WFD_VELAN *)a1->pGenVElan->pVElanExt,
                        a3,
                        v25,
                        v7);
                if ( v26 )
                {
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer)
                    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      347,
                      WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                      v26);
                  }
                }
              }
            }
            if ( v32 )
            {
              v27 = *(unsigned int *)(v3 + 8);
              if ( (v27 & 0x11E8) != 0 )
              {
                v21 = *(_DWORD *)(v3 + 8);
              }
              else
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                  && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                {
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    349,
                    WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                    v27,
                    4584);
                }
              }
              v28 = WFDDeviceSendProvisionDiscoveryResponse((struct _WFD_ROLE *)v15, a1->pGenVElan->pAdapt, v21, v7);
              if ( !v28 )
                goto LABEL_94;
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || !BYTE1(WPP_GLOBAL_Control->Timer)
                || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                goto LABEL_94;
              }
              v30 = 350;
            }
            else
            {
              v28 = WFDDeviceSendProvisionDiscoveryFailureResponse(
                      *(struct _ADAPT **)(**(_QWORD **)pRoleExt + 16LL),
                      *((_BYTE *)a3 + 16),
                      *((void **)a3 + 3),
                      (unsigned __int8 (*)[6])((char *)a3 + 4),
                      v31);
              if ( !v28 )
                goto LABEL_94;
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || !BYTE1(WPP_GLOBAL_Control->Timer)
                || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                goto LABEL_94;
              }
              v30 = 351;
            }
            WPP_SF_d(v29->AttachedDevice, v30, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v28);
LABEL_94:
            if ( v3 )
            {
              if ( *(_QWORD *)(v3 - 16) )
                ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 - 16), (PVOID)(v3 - 16));
              else
                ExFreePoolWithTag((PVOID)(v3 - 16), *(_DWORD *)(v3 - 16 + 8));
            }
            if ( v7 )
            {
              if ( *((_QWORD *)v7 - 2) )
                ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v7 - 2), (char *)v7 - 16);
              else
                ExFreePoolWithTag((char *)v7 - 16, *((_DWORD *)v7 - 2));
            }
            return;
          }
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u
            || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
LABEL_22:
            v40 = 0;
            goto LABEL_49;
          }
          v16 = 341;
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u
            || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            goto LABEL_22;
          }
          v16 = 340;
        }
        WPP_SF_(v15->AttachedDevice, v16, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        goto LABEL_22;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 337, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v9, v8, v5);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && BYTE1(WPP_GLOBAL_Control->Timer)
         && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
  {
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 336, v5, a3);
  }
}

```

## disassembly

```asm
0x14008538c  mov     [rsp-38h+arg_8], rbx
0x140085391  mov     [rsp-38h+arg_0], rcx
0x140085396  push    rbp
0x140085397  push    rsi
0x140085398  push    rdi
0x140085399  push    r12
0x14008539b  push    r13
0x14008539d  push    r14
0x14008539f  push    r15
0x1400853a1  mov     rbp, rsp
0x1400853a4  sub     rsp, 80h
0x1400853ab  xor     r13d, r13d
0x1400853ae  mov     rsi, r8
0x1400853b1  mov     [rbp+var_18], r13
0x1400853b5  mov     r8d, edx
0x1400853b8  mov     [rbp+var_2F], r13b
0x1400853bc  mov     rdx, rcx
0x1400853bf  mov     [rbp+arg_10], r13b
0x1400853c3  mov     r15d, r13d
0x1400853c6  mov     [rbp+var_20], r13
0x1400853ca  test    rsi, rsi
0x1400853cd  jz      loc_1400859A4
0x1400853d3  cmp     r8d, 28h ; '('
0x1400853d7  jb      loc_1400859A4
0x1400853dd  mov     r11d, [rsi+24h]
0x1400853e1  test    r11d, r11d
0x1400853e4  jz      short loc_1400853F2
0x1400853e6  mov     ecx, [rsi+20h]
0x1400853e9  cmp     ecx, 28h ; '('
0x1400853ec  jb      loc_14008595E
0x1400853f2  mov     ecx, [rsi+20h]
0x1400853f5  lea     eax, [rcx+r11]
0x1400853f9  cmp     eax, ecx
0x1400853fb  jb      loc_14008595E
0x140085401  cmp     eax, r8d
0x140085404  ja      loc_14008595E
0x14008540a  mov     rax, [rdx+0B8h]
0x140085411  mov     [rbp+var_28], rax
0x140085415  mov     r8, cs:WPP_GLOBAL_Control
0x14008541c  lea     rdi, WPP_GLOBAL_Control
0x140085423  cmp     r8, rdi
0x140085426  jz      short loc_14008545A
0x140085428  cmp     byte ptr [r8+29h], 3
0x14008542d  jb      short loc_14008545A
0x14008542f  bt      dword ptr [r8+2Ch], 15h
0x140085435  jnb     short loc_14008545A
0x140085437  movzx   eax, byte ptr [rsi+10h]
0x14008543b  lea     r9, [rsi+4]
0x14008543f  mov     dword ptr [rsp+80h+var_50], r11d
0x140085444  mov     edx, 152h
0x140085449  mov     dword ptr [rsp+80h+var_58], ecx
0x14008544d  mov     rcx, [r8+18h]
0x140085451  mov     [rsp+80h+var_60], eax
0x140085455  call    WPP_SF__MAC_DDD
0x14008545a  mov     edx, [rsi+24h]
0x14008545d  lea     r14, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140085464  test    edx, edx
0x140085466  jz      short loc_1400854B4
0x140085468  mov     rcx, cs:WPP_GLOBAL_Control
0x14008546f  cmp     rcx, rdi
0x140085472  jz      short loc_1400854B4
0x140085474  cmp     byte ptr [rcx+29h], 3
0x140085478  jb      short loc_1400854B4
0x14008547a  bt      dword ptr [rcx+2Ch], 15h
0x14008547f  jnb     short loc_1400854B4
0x140085481  mov     eax, [rsi+20h]
0x140085484  lea     r9, [rbp+var_10]
0x140085488  mov     rcx, [rcx+18h]
0x14008548c  xorps   xmm0, xmm0
0x14008548f  movups  [rbp+var_10], xmm0
0x140085493  mov     word ptr [rbp+var_10], dx
0x140085497  add     rax, rsi
0x14008549a  mov     qword ptr [rbp+var_10+8], rax
0x14008549e  mov     edx, 153h
0x1400854a3  movaps  xmm0, [rbp+var_10]
0x1400854a7  mov     r8, r14
0x1400854aa  movdqa  [rbp+var_10], xmm0
0x1400854af  call    WPP_SF__HEX_
0x1400854b4  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Lookaside
0x1400854bb  mov     [rbp+var_30], r13b
0x1400854bf  mov     r12b, r13b
0x1400854c2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400854c9  nop     dword ptr [rax+rax+00h]
0x1400854ce  test    rax, rax
0x1400854d1  jnz     short loc_140085506
0x1400854d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400854da  cmp     rcx, rdi
0x1400854dd  jz      short loc_1400854FD
0x1400854df  cmp     byte ptr [rcx+29h], 3
0x1400854e3  jb      short loc_1400854FD
0x1400854e5  bt      dword ptr [rcx+2Ch], 15h
0x1400854ea  jnb     short loc_1400854FD
0x1400854ec  mov     edx, 154h
0x1400854f1  mov     rcx, [rcx+18h]
0x1400854f5  mov     r8, r14
0x1400854f8  call    WPP_SF_
0x1400854fd  mov     [rbp+arg_18], r12b
0x140085501  jmp     loc_1400856A4
0x140085506  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14008550d  mov     dword ptr [rax+8], 30337776h
0x140085514  lea     r13, [rax+10h]
0x140085518  mov     [rax], rcx
0x14008551b  mov     rcx, r13; void *
0x14008551e  xor     edx, edx; Val
0x140085520  mov     r8d, 0C0h; Size
0x140085526  call    memset
0x14008552b  mov     edx, [rsi+20h]
0x14008552e  lea     rcx, [rsi+4]
0x140085532  mov     r8d, [rsi+24h]
0x140085536  add     rdx, rsi
0x140085539  mov     r9, r13
0x14008553c  call    WFDValidateIncomingProvisionDiscoveryRequestIEs
0x140085541  test    al, al
0x140085543  jnz     short loc_140085565
0x140085545  mov     rcx, cs:WPP_GLOBAL_Control
0x14008554c  cmp     rcx, rdi
0x14008554f  jz      short loc_1400854FD
0x140085551  cmp     byte ptr [rcx+29h], 3
0x140085555  jb      short loc_1400854FD
0x140085557  bt      dword ptr [rcx+2Ch], 15h
0x14008555c  jnb     short loc_1400854FD
0x14008555e  mov     edx, 155h
0x140085563  jmp     short loc_1400854F1
0x140085565  mov     rcx, [rbp+var_28]
0x140085569  add     rcx, 4A8h; SpinLock
0x140085570  mov     [rbp+arg_18], 1
0x140085574  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008557b  nop     dword ptr [rax+rax+00h]
0x140085580  mov     rcx, [rbp+var_28]; struct _WFD_DEVICE_ROLE *
0x140085584  lea     rdx, [rsi+4]; unsigned __int8 (*)[6]
0x140085588  mov     r8d, 5; enum _WFD_RECEIVED_PACKET_TYPE
0x14008558e  mov     [rcx+4B0h], al
0x140085594  lea     rax, [rbp+var_2F]
0x140085598  mov     r9b, [rsi+10h]; unsigned __int8
0x14008559c  mov     qword ptr [rsp+80h+var_60], rax; unsigned __int8 *
0x1400855a1  mov     [rbp+arg_10], 1
0x1400855a5  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x1400855aa  test    eax, eax
0x1400855ac  js      loc_140085672
0x1400855b2  cmp     [rbp+var_2F], r12b
0x1400855b6  jnz     loc_140085672
0x1400855bc  mov     rcx, [rbp+var_28]; struct _WFD_DEVICE_ROLE *
0x1400855c0  lea     r8, [rbp+var_18]; struct _WFD_PEER_DEVICE **
0x1400855c4  lea     rdx, [rsi+4]; unsigned __int8 (*)[6]
0x1400855c8  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x1400855cd  test    eax, eax
0x1400855cf  jnz     short loc_140085602
0x1400855d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400855d8  cmp     rcx, rdi
0x1400855db  jz      short loc_1400855FF
0x1400855dd  cmp     byte ptr [rcx+29h], 3
0x1400855e1  jb      short loc_1400855FF
0x1400855e3  bt      dword ptr [rcx+2Ch], 15h
0x1400855e8  jnb     short loc_1400855FF
0x1400855ea  mov     rcx, [rcx+18h]
0x1400855ee  mov     edx, 157h
0x1400855f3  mov     r8, r14
0x1400855f6  call    WPP_SF_
0x1400855fb  lea     rdx, [rsi+4]; unsigned __int8 (*)[6]
0x1400855ff  mov     r12b, 1
0x140085602  mov     r9b, r12b; unsigned __int8
0x140085605  mov     byte ptr [rsp+80h+var_60], r15b; char
0x14008560a  xor     r8d, r8d; unsigned __int8
0x14008560d  mov     rcx, r13; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x140085610  call    ?WFDDeviceValidateProvisionDiscoveryRequestAttributes@@YAEPEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@PEAY05EEEE@Z; WFDDeviceValidateProvisionDiscoveryRequestAttributes(_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar (*)[6],uchar,uchar,uchar)
0x140085615  test    al, al
0x140085617  jnz     short loc_140085643
0x140085619  mov     rcx, cs:WPP_GLOBAL_Control
0x140085620  cmp     rcx, rdi
0x140085623  jz      short loc_140085643
0x140085625  cmp     byte ptr [rcx+29h], 2
0x140085629  jb      short loc_140085643
0x14008562b  bt      dword ptr [rcx+2Ch], 15h
0x140085630  jnb     short loc_140085643
0x140085632  mov     rcx, [rcx+18h]
0x140085636  mov     edx, 158h
0x14008563b  mov     r8, r14
0x14008563e  call    WPP_SF_
0x140085643  test    r12b, r12b
0x140085646  jz      short loc_140085669
0x140085648  mov     rdx, [rbp+var_28]; struct _WFD_DEVICE_ROLE *
0x14008564c  lea     rax, [rbp+arg_10]
0x140085650  mov     rcx, [rbp+var_18]; struct _WFD_PEER_DEVICE *
0x140085654  mov     r9, r13; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x140085657  mov     r8, rsi; struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *
0x14008565a  mov     qword ptr [rsp+80h+var_60], rax; unsigned __int8 *
0x14008565f  call    ?HandleIncomingProvisionDiscoveryRequestForExistingPeer@@YAEPEAU_WFD_PEER_DEVICE@@PEAU_WFD_DEVICE_ROLE@@PEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS@@PEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@PEAE@Z; HandleIncomingProvisionDiscoveryRequestForExistingPeer(_WFD_PEER_DEVICE *,_WFD_DEVICE_ROLE *,_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *,_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar *)
0x140085664  mov     r12b, al
0x140085667  jmp     short loc_1400856A4
0x140085669  mov     [rbp+var_30], 1
0x14008566d  mov     r12b, r15b
0x140085670  jmp     short loc_1400856A4
0x140085672  mov     rcx, cs:WPP_GLOBAL_Control
0x140085679  cmp     rcx, rdi
0x14008567c  jz      short loc_1400856A1
0x14008567e  cmp     byte ptr [rcx+29h], 3
0x140085682  jb      short loc_1400856A1
0x140085684  bt      dword ptr [rcx+2Ch], 15h
0x140085689  jnb     short loc_1400856A1
0x14008568b  movzx   r9d, byte ptr [rsi+10h]
0x140085690  mov     edx, 156h
0x140085695  mov     rcx, [rcx+18h]
0x140085699  mov     r8, r14
0x14008569c  call    WPP_SF_d
0x1400856a1  mov     r12b, 1
0x1400856a4  cmp     [rbp+arg_10], r15b
0x1400856a8  jz      short loc_1400856C8
0x1400856aa  mov     rcx, [rbp+var_28]
0x1400856ae  add     rcx, 4A8h; SpinLock
0x1400856b5  mov     dl, [rcx+8]; NewIrql
0x1400856b8  call    cs:__imp_KeReleaseSpinLock
0x1400856bf  nop     dword ptr [rax+rax+00h]
0x1400856c4  mov     [rbp+arg_10], r15b
0x1400856c8  test    r12b, r12b
0x1400856cb  jnz     loc_1400858ED
0x1400856d1  xor     r12d, r12d
0x1400856d4  mov     r8d, 11E8h
0x1400856da  cmp     [rbp+var_30], r12b
0x1400856de  jz      loc_140085789
0x1400856e4  mov     r9d, [r13+8]
0x1400856e8  test    r8d, r9d
0x1400856eb  jz      short loc_1400856F2
0x1400856ed  mov     r12d, r9d
0x1400856f0  jmp     short loc_140085721
0x1400856f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400856f9  cmp     rcx, rdi
0x1400856fc  jz      short loc_140085721
0x1400856fe  cmp     byte ptr [rcx+29h], 3
0x140085702  jb      short loc_140085721
0x140085704  bt      dword ptr [rcx+2Ch], 15h
0x140085709  jnb     short loc_140085721
0x14008570b  mov     rcx, [rcx+18h]
0x14008570f  mov     edx, 159h
0x140085714  mov     [rsp+80h+var_60], r8d
0x140085719  mov     r8, r14
0x14008571c  call    WPP_SF_Dd
0x140085721  mov     rcx, [rbp+arg_0]; struct _WFD_ROLE *
0x140085725  lea     rax, [rbp+var_20]
0x140085729  mov     r8, [rsi+18h]; void *
0x14008572d  lea     r9, [rsi+4]; unsigned __int8 (*)[6]
0x140085731  mov     dl, [rsi+10h]; unsigned __int8
0x140085734  mov     [rsp+80h+var_40], rax; struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 **
0x140085739  mov     al, [rcx+7Ch]
0x14008573c  mov     [rsp+80h+var_48], r15b; unsigned __int8
0x140085741  mov     [rsp+80h+var_50], r13; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x140085746  mov     [rsp+80h+var_58], al; unsigned __int8
0x14008574a  mov     [rsp+80h+var_60], r12d; unsigned __int8
0x14008574f  call    ?WFDDeviceBuildProvisionDiscoveryResponseParams@@YAHPEAU_WFD_ROLE@@EPEAXPEAY05EW4_DOT11_WPS_CONFIG_METHOD@@EPEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@EPEAPEAU_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2@@@Z; WFDDeviceBuildProvisionDiscoveryResponseParams(_WFD_ROLE *,uchar,void *,uchar (*)[6],_DOT11_WPS_CONFIG_METHOD,uchar,_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar,_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 * *)
0x140085754  test    eax, eax
0x140085756  jz      short loc_140085785
0x140085758  mov     rcx, cs:WPP_GLOBAL_Control
0x14008575f  cmp     rcx, rdi
0x140085762  jz      short loc_140085785
0x140085764  cmp     byte ptr [rcx+29h], 1
0x140085768  jb      short loc_140085785
0x14008576a  bt      dword ptr [rcx+2Ch], 15h
0x14008576f  jnb     short loc_140085785
0x140085771  mov     rcx, [rcx+18h]
0x140085775  mov     edx, 15Ah
0x14008577a  mov     r9d, eax
0x14008577d  mov     r8, r14
0x140085780  call    WPP_SF_d
0x140085785  mov     r15, [rbp+var_20]
0x140085789  cmp     [rbp+arg_18], 0
0x14008578d  jz      loc_14008581B
0x140085793  mov     rcx, [rbp+arg_0]
0x140085797  mov     edx, 4
0x14008579c  call    ?WFDDeviceIsIncomingPacketTypeFiltered@@YAEPEAU_WFD_ROLE@@W4_WFD_INCOMING_PACKET_TYPE@@@Z; WFDDeviceIsIncomingPacketTypeFiltered(_WFD_ROLE *,_WFD_INCOMING_PACKET_TYPE)
0x1400857a1  test    al, al
0x1400857a3  jnz     short loc_1400857F1
0x1400857a5  mov     rax, [rbp+arg_0]
0x1400857a9  mov     r9, r15; struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *
0x1400857ac  mov     rdx, rsi; struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *
0x1400857af  mov     rcx, [rax]
0x1400857b2  mov     rcx, [rcx+1F68h]; struct _WFD_VELAN *
0x1400857b9  call    ?WFDDeviceIndicateIncomingProvisionDiscoveryRequest@@YAJPEAU_WFD_VELAN@@PEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS@@PEAXPEAU_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2@@@Z; WFDDeviceIndicateIncomingProvisionDiscoveryRequest(_WFD_VELAN *,_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *,void *,_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *)
0x1400857be  test    eax, eax
0x1400857c0  jz      short loc_14008581B
0x1400857c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400857c9  cmp     rcx, rdi
0x1400857cc  jz      short loc_14008581B
0x1400857ce  cmp     byte ptr [rcx+29h], 1
0x1400857d2  jb      short loc_14008581B
0x1400857d4  bt      dword ptr [rcx+2Ch], 15h
0x1400857d9  jnb     short loc_14008581B
0x1400857db  mov     rcx, [rcx+18h]
0x1400857df  mov     edx, 15Bh
0x1400857e4  mov     r9d, eax
0x1400857e7  mov     r8, r14
0x1400857ea  call    WPP_SF_d
0x1400857ef  jmp     short loc_14008581B
0x1400857f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400857f8  cmp     rcx, rdi
0x1400857fb  jz      short loc_14008581B
0x1400857fd  cmp     byte ptr [rcx+29h], 3
0x140085801  jb      short loc_14008581B
0x140085803  bt      dword ptr [rcx+2Ch], 15h
0x140085808  jnb     short loc_14008581B
0x14008580a  mov     rcx, [rcx+18h]
0x14008580e  mov     edx, 15Ch
  ... truncated ...
```

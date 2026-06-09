# WFDDeviceHandleReceivedProvisionDiscoveryRequest(_WFD_ROLE *,ulong,_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *)

- ea: `0x140086bbc`
- end: `0x140087226`
- name: `?WFDDeviceHandleReceivedProvisionDiscoveryRequest@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS@@@Z`
- size: `1642`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14007e0e0`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x140024058`
- `0x14002f44c`
- `0x140030244`
- `0x14007fba4`
- `0x140080488`
- `0x140080a84`
- `0x140080dfc`
- `0x140086bbc`
- `0x14008a0d8`
- `0x14008a578`
- `0x14008ac5c`
- `0x14008af3c`
- `0x14008ccd4`
- `0x14008e8a8`
- `0x140099618`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140086cf2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140086cf2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087134`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008716c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087134`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008716c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087145`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087180`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087145`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087180`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086ee8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086ee8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140086da4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140086da4`

## pseudocode

```c
void __fastcall WFDDeviceHandleReceivedProvisionDiscoveryRequest(
        struct _WFD_ROLE *a1,
        unsigned int a2,
        struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *a3)
{
  char *v3; // r13
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
  __int64 v22; // r9
  unsigned int v23; // eax
  void *v24; // r8
  unsigned int v25; // eax
  __int64 v26; // r9
  unsigned int v27; // eax
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  unsigned __int8 v30; // [rsp+20h] [rbp-60h]
  char v31; // [rsp+50h] [rbp-30h]
  unsigned __int8 v32[7]; // [rsp+51h] [rbp-2Fh] BYREF
  struct _WFD_DEVICE_ROLE *pRoleExt; // [rsp+58h] [rbp-28h]
  struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *v34; // [rsp+60h] [rbp-20h] BYREF
  struct _WFD_PEER_DEVICE *v35; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v36[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int8 v38; // [rsp+D0h] [rbp+50h] BYREF
  char v39; // [rsp+D8h] [rbp+58h]

  v3 = 0;
  v35 = 0;
  v5 = a2;
  v32[0] = 0;
  v38 = 0;
  v7 = 0;
  v34 = 0;
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
          WPP_SF__MAC_DDD(
            WPP_GLOBAL_Control->AttachedDevice,
            338,
            WPP_GLOBAL_Control,
            (char *)a3 + 4,
            *((unsigned __int8 *)a3 + 16),
            v9,
            v8);
        }
        v10 = *((_DWORD *)a3 + 9);
        if ( v10
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          v11 = *((unsigned int *)a3 + 8);
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          v36[0] = (unsigned __int16)v10;
          v36[1] = (char *)a3 + v11;
          WPP_SF__HEX_(AttachedDevice, 339, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v36);
        }
        v31 = 0;
        v13 = 0;
        v14 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
        if ( v14 )
        {
          v14[2] = 808679286;
          v3 = (char *)(v14 + 4);
          *(_QWORD *)v14 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
          memset(v14 + 4, 0, 0xC0u);
          if ( (unsigned __int8)WFDValidateIncomingProvisionDiscoveryRequestIEs(
                                  (char *)a3 + 4,
                                  (char *)a3 + *((unsigned int *)a3 + 8),
                                  *((unsigned int *)a3 + 9),
                                  v3) )
          {
            v39 = 1;
            v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
            v18 = pRoleExt;
            *((_BYTE *)pRoleExt + 1200) = v17;
            v19 = *((_BYTE *)a3 + 16);
            v38 = 1;
            if ( (int)WFDDeviceCheckDuplicateTransmission(
                        v18,
                        (unsigned __int8 (*)[6])((char *)a3 + 4),
                        WfdReceivedPacketTypeProvisionDiscoveryRequest,
                        v19,
                        v32) < 0
              || v32[0] )
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
              if ( !(unsigned int)WFDDeviceFindPeerByMAC(pRoleExt, (unsigned __int8 (*)[6])((char *)a3 + 4), &v35) )
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
                        v35,
                        pRoleExt,
                        a3,
                        (struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *)v3,
                        &v38);
              }
              else
              {
                v31 = 1;
                v13 = 0;
              }
            }
LABEL_49:
            if ( v38 )
            {
              KeReleaseSpinLock((PKSPIN_LOCK)pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
              v38 = 0;
            }
            if ( v13 )
              goto LABEL_94;
            v21 = DOT11_WPS_CONFIG_METHOD_NULL;
            if ( v31 )
            {
              v22 = *((unsigned int *)v3 + 2);
              if ( (v22 & 0x11E8) != 0 )
              {
                v21 = *((_DWORD *)v3 + 2);
              }
              else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                     && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                WPP_SF_Dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  345,
                  WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                  v22,
                  4584);
              }
              v23 = WFDDeviceBuildProvisionDiscoveryResponseParams(
                      a1,
                      *((_BYTE *)a3 + 16),
                      *((void **)a3 + 3),
                      (unsigned __int8 (*)[6])((char *)a3 + 4),
                      v21,
                      a1->ConnectionCapability,
                      (struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *)v3,
                      0,
                      &v34);
              if ( v23 )
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
                    v23);
                }
              }
              v7 = v34;
            }
            if ( v39 )
            {
              if ( (unsigned __int8)WFDDeviceIsIncomingPacketTypeFiltered(a1, 4) )
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
                v25 = WFDDeviceIndicateIncomingProvisionDiscoveryRequest(
                        (struct _WFD_VELAN *)a1->pGenVElan->pVElanExt,
                        a3,
                        v24,
                        v7);
                if ( v25 )
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
                      v25);
                  }
                }
              }
            }
            if ( v31 )
            {
              v26 = *((unsigned int *)v3 + 2);
              if ( (v26 & 0x11E8) != 0 )
              {
                v21 = *((_DWORD *)v3 + 2);
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
                    v26,
                    4584);
                }
              }
              v27 = WFDDeviceSendProvisionDiscoveryResponse((struct _WFD_ROLE *)v15, a1->pGenVElan->pAdapt, v21, v7);
              if ( !v27 )
                goto LABEL_94;
              v28 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || !BYTE1(WPP_GLOBAL_Control->Timer)
                || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                goto LABEL_94;
              }
              v29 = 350;
            }
            else
            {
              v27 = WFDDeviceSendProvisionDiscoveryFailureResponse(
                      *(struct _ADAPT **)(**(_QWORD **)pRoleExt + 16LL),
                      *((_BYTE *)a3 + 16),
                      *((void **)a3 + 3),
                      (unsigned __int8 (*)[6])((char *)a3 + 4),
                      v30);
              if ( !v27 )
                goto LABEL_94;
              v28 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || !BYTE1(WPP_GLOBAL_Control->Timer)
                || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                goto LABEL_94;
              }
              v29 = 351;
            }
            WPP_SF_d(v28->AttachedDevice, v29, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v27);
LABEL_94:
            if ( v3 )
            {
              if ( *((_QWORD *)v3 - 2) )
                ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v3 - 2), v3 - 16);
              else
                ExFreePoolWithTag(v3 - 16, *((_DWORD *)v3 - 2));
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
            v39 = 0;
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
0x140086bbc  mov     [rsp-38h+arg_8], rbx
0x140086bc1  mov     [rsp-38h+arg_0], rcx
0x140086bc6  push    rbp
0x140086bc7  push    rsi
0x140086bc8  push    rdi
0x140086bc9  push    r12
0x140086bcb  push    r13
0x140086bcd  push    r14
0x140086bcf  push    r15
0x140086bd1  mov     rbp, rsp
0x140086bd4  sub     rsp, 80h
0x140086bdb  xor     r13d, r13d
0x140086bde  mov     rsi, r8
0x140086be1  mov     [rbp+var_18], r13
0x140086be5  mov     r8d, edx
0x140086be8  mov     [rbp+var_2F], r13b
0x140086bec  mov     rdx, rcx
0x140086bef  mov     [rbp+arg_10], r13b
0x140086bf3  mov     r15d, r13d
0x140086bf6  mov     [rbp+var_20], r13
0x140086bfa  test    rsi, rsi
0x140086bfd  jz      loc_1400871D4
0x140086c03  cmp     r8d, 28h ; '('
0x140086c07  jb      loc_1400871D4
0x140086c0d  mov     r11d, [rsi+24h]
0x140086c11  test    r11d, r11d
0x140086c14  jz      short loc_140086C22
0x140086c16  mov     ecx, [rsi+20h]
0x140086c19  cmp     ecx, 28h ; '('
0x140086c1c  jb      loc_14008718E
0x140086c22  mov     ecx, [rsi+20h]
0x140086c25  lea     eax, [rcx+r11]
0x140086c29  cmp     eax, ecx
0x140086c2b  jb      loc_14008718E
0x140086c31  cmp     eax, r8d
0x140086c34  ja      loc_14008718E
0x140086c3a  mov     rax, [rdx+0B8h]
0x140086c41  mov     [rbp+var_28], rax
0x140086c45  mov     r8, cs:WPP_GLOBAL_Control
0x140086c4c  lea     rdi, WPP_GLOBAL_Control
0x140086c53  cmp     r8, rdi
0x140086c56  jz      short loc_140086C8A
0x140086c58  cmp     byte ptr [r8+29h], 3
0x140086c5d  jb      short loc_140086C8A
0x140086c5f  bt      dword ptr [r8+2Ch], 15h
0x140086c65  jnb     short loc_140086C8A
0x140086c67  movzx   eax, byte ptr [rsi+10h]
0x140086c6b  lea     r9, [rsi+4]
0x140086c6f  mov     dword ptr [rsp+80h+var_50], r11d
0x140086c74  mov     edx, 152h
0x140086c79  mov     dword ptr [rsp+80h+var_58], ecx
0x140086c7d  mov     rcx, [r8+18h]
0x140086c81  mov     [rsp+80h+var_60], eax
0x140086c85  call    WPP_SF__MAC_DDD
0x140086c8a  mov     edx, [rsi+24h]
0x140086c8d  lea     r14, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140086c94  test    edx, edx
0x140086c96  jz      short loc_140086CE4
0x140086c98  mov     rcx, cs:WPP_GLOBAL_Control
0x140086c9f  cmp     rcx, rdi
0x140086ca2  jz      short loc_140086CE4
0x140086ca4  cmp     byte ptr [rcx+29h], 3
0x140086ca8  jb      short loc_140086CE4
0x140086caa  bt      dword ptr [rcx+2Ch], 15h
0x140086caf  jnb     short loc_140086CE4
0x140086cb1  mov     eax, [rsi+20h]
0x140086cb4  lea     r9, [rbp+var_10]
0x140086cb8  mov     rcx, [rcx+18h]
0x140086cbc  xorps   xmm0, xmm0
0x140086cbf  movups  [rbp+var_10], xmm0
0x140086cc3  mov     word ptr [rbp+var_10], dx
0x140086cc7  add     rax, rsi
0x140086cca  mov     qword ptr [rbp+var_10+8], rax
0x140086cce  mov     edx, 153h
0x140086cd3  movaps  xmm0, [rbp+var_10]
0x140086cd7  mov     r8, r14
0x140086cda  movdqa  [rbp+var_10], xmm0
0x140086cdf  call    WPP_SF__HEX_
0x140086ce4  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Lookaside
0x140086ceb  mov     [rbp+var_30], r13b
0x140086cef  mov     r12b, r13b
0x140086cf2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140086cf9  nop     dword ptr [rax+rax+00h]
0x140086cfe  test    rax, rax
0x140086d01  jnz     short loc_140086D36
0x140086d03  mov     rcx, cs:WPP_GLOBAL_Control
0x140086d0a  cmp     rcx, rdi
0x140086d0d  jz      short loc_140086D2D
0x140086d0f  cmp     byte ptr [rcx+29h], 3
0x140086d13  jb      short loc_140086D2D
0x140086d15  bt      dword ptr [rcx+2Ch], 15h
0x140086d1a  jnb     short loc_140086D2D
0x140086d1c  mov     edx, 154h
0x140086d21  mov     rcx, [rcx+18h]
0x140086d25  mov     r8, r14
0x140086d28  call    WPP_SF_
0x140086d2d  mov     [rbp+arg_18], r12b
0x140086d31  jmp     loc_140086ED4
0x140086d36  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140086d3d  mov     dword ptr [rax+8], 30337776h
0x140086d44  lea     r13, [rax+10h]
0x140086d48  mov     [rax], rcx
0x140086d4b  mov     rcx, r13; void *
0x140086d4e  xor     edx, edx; Val
0x140086d50  mov     r8d, 0C0h; Size
0x140086d56  call    memset
0x140086d5b  mov     edx, [rsi+20h]
0x140086d5e  lea     rcx, [rsi+4]
0x140086d62  mov     r8d, [rsi+24h]
0x140086d66  add     rdx, rsi
0x140086d69  mov     r9, r13
0x140086d6c  call    WFDValidateIncomingProvisionDiscoveryRequestIEs
0x140086d71  test    al, al
0x140086d73  jnz     short loc_140086D95
0x140086d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140086d7c  cmp     rcx, rdi
0x140086d7f  jz      short loc_140086D2D
0x140086d81  cmp     byte ptr [rcx+29h], 3
0x140086d85  jb      short loc_140086D2D
0x140086d87  bt      dword ptr [rcx+2Ch], 15h
0x140086d8c  jnb     short loc_140086D2D
0x140086d8e  mov     edx, 155h
0x140086d93  jmp     short loc_140086D21
0x140086d95  mov     rcx, [rbp+var_28]
0x140086d99  add     rcx, 4A8h; SpinLock
0x140086da0  mov     [rbp+arg_18], 1
0x140086da4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140086dab  nop     dword ptr [rax+rax+00h]
0x140086db0  mov     rcx, [rbp+var_28]; struct _WFD_DEVICE_ROLE *
0x140086db4  lea     rdx, [rsi+4]; unsigned __int8 (*)[6]
0x140086db8  mov     r8d, 5; enum _WFD_RECEIVED_PACKET_TYPE
0x140086dbe  mov     [rcx+4B0h], al
0x140086dc4  lea     rax, [rbp+var_2F]
0x140086dc8  mov     r9b, [rsi+10h]; unsigned __int8
0x140086dcc  mov     qword ptr [rsp+80h+var_60], rax; unsigned __int8 *
0x140086dd1  mov     [rbp+arg_10], 1
0x140086dd5  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x140086dda  test    eax, eax
0x140086ddc  js      loc_140086EA2
0x140086de2  cmp     [rbp+var_2F], r12b
0x140086de6  jnz     loc_140086EA2
0x140086dec  mov     rcx, [rbp+var_28]; struct _WFD_DEVICE_ROLE *
0x140086df0  lea     r8, [rbp+var_18]; struct _WFD_PEER_DEVICE **
0x140086df4  lea     rdx, [rsi+4]; unsigned __int8 (*)[6]
0x140086df8  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x140086dfd  test    eax, eax
0x140086dff  jnz     short loc_140086E32
0x140086e01  mov     rcx, cs:WPP_GLOBAL_Control
0x140086e08  cmp     rcx, rdi
0x140086e0b  jz      short loc_140086E2F
0x140086e0d  cmp     byte ptr [rcx+29h], 3
0x140086e11  jb      short loc_140086E2F
0x140086e13  bt      dword ptr [rcx+2Ch], 15h
0x140086e18  jnb     short loc_140086E2F
0x140086e1a  mov     rcx, [rcx+18h]
0x140086e1e  mov     edx, 157h
0x140086e23  mov     r8, r14
0x140086e26  call    WPP_SF_
0x140086e2b  lea     rdx, [rsi+4]; unsigned __int8 (*)[6]
0x140086e2f  mov     r12b, 1
0x140086e32  mov     r9b, r12b; unsigned __int8
0x140086e35  mov     byte ptr [rsp+80h+var_60], r15b; char
0x140086e3a  xor     r8d, r8d; unsigned __int8
0x140086e3d  mov     rcx, r13; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x140086e40  call    ?WFDDeviceValidateProvisionDiscoveryRequestAttributes@@YAEPEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@PEAY05EEEE@Z; WFDDeviceValidateProvisionDiscoveryRequestAttributes(_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar (*)[6],uchar,uchar,uchar)
0x140086e45  test    al, al
0x140086e47  jnz     short loc_140086E73
0x140086e49  mov     rcx, cs:WPP_GLOBAL_Control
0x140086e50  cmp     rcx, rdi
0x140086e53  jz      short loc_140086E73
0x140086e55  cmp     byte ptr [rcx+29h], 2
0x140086e59  jb      short loc_140086E73
0x140086e5b  bt      dword ptr [rcx+2Ch], 15h
0x140086e60  jnb     short loc_140086E73
0x140086e62  mov     rcx, [rcx+18h]
0x140086e66  mov     edx, 158h
0x140086e6b  mov     r8, r14
0x140086e6e  call    WPP_SF_
0x140086e73  test    r12b, r12b
0x140086e76  jz      short loc_140086E99
0x140086e78  mov     rdx, [rbp+var_28]; struct _WFD_DEVICE_ROLE *
0x140086e7c  lea     rax, [rbp+arg_10]
0x140086e80  mov     rcx, [rbp+var_18]; struct _WFD_PEER_DEVICE *
0x140086e84  mov     r9, r13; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x140086e87  mov     r8, rsi; struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *
0x140086e8a  mov     qword ptr [rsp+80h+var_60], rax; unsigned __int8 *
0x140086e8f  call    ?HandleIncomingProvisionDiscoveryRequestForExistingPeer@@YAEPEAU_WFD_PEER_DEVICE@@PEAU_WFD_DEVICE_ROLE@@PEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS@@PEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@PEAE@Z; HandleIncomingProvisionDiscoveryRequestForExistingPeer(_WFD_PEER_DEVICE *,_WFD_DEVICE_ROLE *,_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *,_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar *)
0x140086e94  mov     r12b, al
0x140086e97  jmp     short loc_140086ED4
0x140086e99  mov     [rbp+var_30], 1
0x140086e9d  mov     r12b, r15b
0x140086ea0  jmp     short loc_140086ED4
0x140086ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x140086ea9  cmp     rcx, rdi
0x140086eac  jz      short loc_140086ED1
0x140086eae  cmp     byte ptr [rcx+29h], 3
0x140086eb2  jb      short loc_140086ED1
0x140086eb4  bt      dword ptr [rcx+2Ch], 15h
0x140086eb9  jnb     short loc_140086ED1
0x140086ebb  movzx   r9d, byte ptr [rsi+10h]
0x140086ec0  mov     edx, 156h
0x140086ec5  mov     rcx, [rcx+18h]
0x140086ec9  mov     r8, r14
0x140086ecc  call    WPP_SF_d
0x140086ed1  mov     r12b, 1
0x140086ed4  cmp     [rbp+arg_10], r15b
0x140086ed8  jz      short loc_140086EF8
0x140086eda  mov     rcx, [rbp+var_28]
0x140086ede  add     rcx, 4A8h; SpinLock
0x140086ee5  mov     dl, [rcx+8]; NewIrql
0x140086ee8  call    cs:__imp_KeReleaseSpinLock
0x140086eef  nop     dword ptr [rax+rax+00h]
0x140086ef4  mov     [rbp+arg_10], r15b
0x140086ef8  test    r12b, r12b
0x140086efb  jnz     loc_14008711D
0x140086f01  xor     r12d, r12d
0x140086f04  mov     r8d, 11E8h
0x140086f0a  cmp     [rbp+var_30], r12b
0x140086f0e  jz      loc_140086FB9
0x140086f14  mov     r9d, [r13+8]
0x140086f18  test    r8d, r9d
0x140086f1b  jz      short loc_140086F22
0x140086f1d  mov     r12d, r9d
0x140086f20  jmp     short loc_140086F51
0x140086f22  mov     rcx, cs:WPP_GLOBAL_Control
0x140086f29  cmp     rcx, rdi
0x140086f2c  jz      short loc_140086F51
0x140086f2e  cmp     byte ptr [rcx+29h], 3
0x140086f32  jb      short loc_140086F51
0x140086f34  bt      dword ptr [rcx+2Ch], 15h
0x140086f39  jnb     short loc_140086F51
0x140086f3b  mov     rcx, [rcx+18h]
0x140086f3f  mov     edx, 159h
0x140086f44  mov     [rsp+80h+var_60], r8d
0x140086f49  mov     r8, r14
0x140086f4c  call    WPP_SF_Dd
0x140086f51  mov     rcx, [rbp+arg_0]; struct _WFD_ROLE *
0x140086f55  lea     rax, [rbp+var_20]
0x140086f59  mov     r8, [rsi+18h]; void *
0x140086f5d  lea     r9, [rsi+4]; unsigned __int8 (*)[6]
0x140086f61  mov     dl, [rsi+10h]; unsigned __int8
0x140086f64  mov     [rsp+80h+var_40], rax; struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 **
0x140086f69  mov     al, [rcx+7Ch]
0x140086f6c  mov     [rsp+80h+var_48], r15b; unsigned __int8
0x140086f71  mov     [rsp+80h+var_50], r13; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x140086f76  mov     [rsp+80h+var_58], al; unsigned __int8
0x140086f7a  mov     [rsp+80h+var_60], r12d; unsigned __int8
0x140086f7f  call    ?WFDDeviceBuildProvisionDiscoveryResponseParams@@YAHPEAU_WFD_ROLE@@EPEAXPEAY05EW4_DOT11_WPS_CONFIG_METHOD@@EPEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@EPEAPEAU_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2@@@Z; WFDDeviceBuildProvisionDiscoveryResponseParams(_WFD_ROLE *,uchar,void *,uchar (*)[6],_DOT11_WPS_CONFIG_METHOD,uchar,_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar,_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 * *)
0x140086f84  test    eax, eax
0x140086f86  jz      short loc_140086FB5
0x140086f88  mov     rcx, cs:WPP_GLOBAL_Control
0x140086f8f  cmp     rcx, rdi
0x140086f92  jz      short loc_140086FB5
0x140086f94  cmp     byte ptr [rcx+29h], 1
0x140086f98  jb      short loc_140086FB5
0x140086f9a  bt      dword ptr [rcx+2Ch], 15h
0x140086f9f  jnb     short loc_140086FB5
0x140086fa1  mov     rcx, [rcx+18h]
0x140086fa5  mov     edx, 15Ah
0x140086faa  mov     r9d, eax
0x140086fad  mov     r8, r14
0x140086fb0  call    WPP_SF_d
0x140086fb5  mov     r15, [rbp+var_20]
0x140086fb9  cmp     [rbp+arg_18], 0
0x140086fbd  jz      loc_14008704B
0x140086fc3  mov     rcx, [rbp+arg_0]
0x140086fc7  mov     edx, 4
0x140086fcc  call    ?WFDDeviceIsIncomingPacketTypeFiltered@@YAEPEAU_WFD_ROLE@@W4_WFD_INCOMING_PACKET_TYPE@@@Z; WFDDeviceIsIncomingPacketTypeFiltered(_WFD_ROLE *,_WFD_INCOMING_PACKET_TYPE)
0x140086fd1  test    al, al
0x140086fd3  jnz     short loc_140087021
0x140086fd5  mov     rax, [rbp+arg_0]
0x140086fd9  mov     r9, r15; struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *
0x140086fdc  mov     rdx, rsi; struct _DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *
0x140086fdf  mov     rcx, [rax]
0x140086fe2  mov     rcx, [rcx+1F68h]; struct _WFD_VELAN *
0x140086fe9  call    ?WFDDeviceIndicateIncomingProvisionDiscoveryRequest@@YAJPEAU_WFD_VELAN@@PEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS@@PEAXPEAU_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2@@@Z; WFDDeviceIndicateIncomingProvisionDiscoveryRequest(_WFD_VELAN *,_DOT11_RECEIVED_PROVISION_DISCOVERY_REQUEST_PARAMETERS *,void *,_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *)
0x140086fee  test    eax, eax
0x140086ff0  jz      short loc_14008704B
0x140086ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x140086ff9  cmp     rcx, rdi
0x140086ffc  jz      short loc_14008704B
0x140086ffe  cmp     byte ptr [rcx+29h], 1
0x140087002  jb      short loc_14008704B
0x140087004  bt      dword ptr [rcx+2Ch], 15h
0x140087009  jnb     short loc_14008704B
0x14008700b  mov     rcx, [rcx+18h]
0x14008700f  mov     edx, 15Bh
0x140087014  mov     r9d, eax
0x140087017  mov     r8, r14
0x14008701a  call    WPP_SF_d
0x14008701f  jmp     short loc_14008704B
0x140087021  mov     rcx, cs:WPP_GLOBAL_Control
0x140087028  cmp     rcx, rdi
0x14008702b  jz      short loc_14008704B
0x14008702d  cmp     byte ptr [rcx+29h], 3
0x140087031  jb      short loc_14008704B
0x140087033  bt      dword ptr [rcx+2Ch], 15h
0x140087038  jnb     short loc_14008704B
0x14008703a  mov     rcx, [rcx+18h]
0x14008703e  mov     edx, 15Ch
  ... truncated ...
```

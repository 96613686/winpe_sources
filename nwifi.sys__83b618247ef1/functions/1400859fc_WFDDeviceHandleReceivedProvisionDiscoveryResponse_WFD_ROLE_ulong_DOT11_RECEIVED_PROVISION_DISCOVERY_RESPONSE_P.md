# WFDDeviceHandleReceivedProvisionDiscoveryResponse(_WFD_ROLE *,ulong,_DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS *)

- ea: `0x1400859fc`
- end: `0x1400863e6`
- name: `?WFDDeviceHandleReceivedProvisionDiscoveryResponse@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS@@@Z`
- size: `2538`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007c930`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x140022f08`
- `0x14002f1bc`
- `0x14002ffb4`
- `0x14003ae2c`
- `0x14007f254`
- `0x14007f5cc`
- `0x1400859fc`
- `0x140089588`
- `0x140089cdc`
- `0x14008a780`
- `0x14008ae64`
- `0x14008af58`
- `0x14008b4a4`
- `0x14008c60c`
- `0x14008ca00`
- `0x14008cc3c`
- `0x1400980fc`
- `0x14009a3d0`
- `0x14009a7c0`
- `0x14009ace0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140085bd7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140085bd7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086321`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086321`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086335`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086335`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086273`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400862fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086273`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400862fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140085b64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140085b64`

## pseudocode

```c
void __fastcall WFDDeviceHandleReceivedProvisionDiscoveryResponse(
        struct _WFD_ROLE *a1,
        unsigned int a2,
        struct _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS *a3)
{
  char *pRoleExt; // rsi
  int v7; // r8d
  __int64 v8; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  PKSPIN_LOCK v10; // r13
  unsigned __int8 *v11; // r12
  char *v12; // rsi
  _DWORD *v13; // rax
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  int v16; // edx
  struct _WFD_PEER_DEVICE *v17; // r15
  __int64 v18; // r8
  int v19; // r12d
  int v20; // eax
  int v21; // ecx
  int v22; // r12d
  char v23; // bl
  int v24; // r8d
  __int64 v25; // r9
  _QWORD *v26; // r8
  unsigned __int8 v27[16]; // [rsp+90h] [rbp-80h] BYREF
  PKSPIN_LOCK SpinLock[2]; // [rsp+A0h] [rbp-70h] BYREF
  struct _WFD_PEER_DEVICE *v29; // [rsp+B0h] [rbp-60h] BYREF
  struct _WFD_DEVICE_ROLE *v30; // [rsp+B8h] [rbp-58h]
  struct _WFD_ROLE *v31; // [rsp+C0h] [rbp-50h]
  _OWORD v32[9]; // [rsp+D0h] [rbp-40h] BYREF
  _QWORD v33[30]; // [rsp+160h] [rbp+50h] BYREF

  v31 = a1;
  v29 = 0;
  memset(v32, 0, 0x88u);
  memset(v33, 0, 0xE8u);
  v27[0] = 0;
  if ( a3 && a2 >= 0x1C )
  {
    pRoleExt = (char *)a1->pRoleExt;
    v30 = (struct _WFD_DEVICE_ROLE *)pRoleExt;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF__MAC_DDD(WPP_GLOBAL_Control->AttachedDevice, 299, *((unsigned __int8 *)a3 + 16), (char *)a3 + 4);
    }
    v7 = *((_DWORD *)a3 + 6);
    if ( !v7 || (v8 = *((unsigned int *)a3 + 5), (unsigned int)v8 >= 0x1C) )
    {
      v8 = *((unsigned int *)a3 + 5);
      if ( (int)v8 + v7 >= (unsigned int)v8 && (int)v8 + v7 <= a2 )
      {
        if ( v7
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          SpinLock[0] = (PKSPIN_LOCK)(unsigned __int16)v7;
          SpinLock[1] = (PKSPIN_LOCK)((char *)a3 + v8);
          WPP_SF__HEX_(AttachedDevice, 301, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, SpinLock);
        }
        v10 = (PKSPIN_LOCK)(pRoleExt + 1192);
        SpinLock[0] = (PKSPIN_LOCK)(pRoleExt + 1192);
        v11 = (unsigned __int8 *)a3 + 4;
        pRoleExt[1200] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
        if ( (unsigned int)WFDDeviceFindPeerByMAC(
                             (struct _WFD_DEVICE_ROLE *)pRoleExt,
                             (unsigned __int8 (*)[6])((char *)a3 + 4),
                             &v29) )
        {
          v12 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            WPP_SF__MAC_(
              WPP_GLOBAL_Control->AttachedDevice,
              302,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              (char *)a3 + 4);
          }
          goto LABEL_100;
        }
        v13 = ExAllocateFromNPagedLookasideList(&Lookaside);
        if ( !v13 )
        {
          v12 = 0;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control->Timer)
            || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            goto LABEL_100;
          }
          v15 = 303;
          goto LABEL_26;
        }
        *(_QWORD *)v13 = &Lookaside;
        v12 = (char *)(v13 + 4);
        v13[2] = 808679286;
        memset(v13 + 4, 0, 0x13Cu);
        if ( !WFDValidateIncomingProvisionDiscoveryResponseIEs(
                (unsigned __int8 *)a3 + *((unsigned int *)a3 + 5),
                *((_DWORD *)a3 + 6),
                v12) )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control->Timer)
            || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            goto LABEL_100;
          }
          v15 = 304;
LABEL_26:
          WPP_SF_(v14->AttachedDevice, v15, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
          goto LABEL_100;
        }
        if ( (int)WFDDeviceCheckDuplicateTransmission(
                    v30,
                    (unsigned __int8 (*)[6])((char *)a3 + 4),
                    6,
                    *((_BYTE *)a3 + 16),
                    v27) < 0
          || v27[0] )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              305,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              *((unsigned __int8 *)a3 + 16));
          }
          goto LABEL_100;
        }
        v16 = *((unsigned __int8 *)a3 + 16);
        v17 = v29;
        if ( *((_BYTE *)v29 + 40) != (_BYTE)v16 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              306,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              *((unsigned __int8 *)v29 + 40),
              v16);
          }
          goto LABEL_100;
        }
        if ( !(unsigned __int8)WFDPeerDeviceSetState(v29, 13) )
        {
LABEL_100:
          KeReleaseSpinLock(v10, *((_BYTE *)v10 + 8));
LABEL_101:
          if ( v12 )
          {
            if ( *((_QWORD *)v12 - 2) )
              ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 16);
            else
              ExFreePoolWithTag(v12 - 16, *((_DWORD *)v12 - 2));
          }
          return;
        }
        if ( !(unsigned int)WFDPeerDeviceCancelTimer(v17) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer)
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            WPP_SF__MAC_q(WPP_GLOBAL_Control->AttachedDevice, 307, v18, (char *)v17 + 24, v17);
          }
          goto LABEL_100;
        }
        if ( !WFDDeviceValidateProvisionDiscoveryResponseAttributes(
                (struct _WFD_PROVISION_DISCOVERY_RESPONSE_ATTRIBUTES *)v12,
                (unsigned __int8 (*)[6])v11,
                0,
                *((_BYTE *)v17 + 848),
                0)
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 308, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        }
        memset(v32, 0, 0x88u);
        memset(v33, 0, 0xE8u);
        *(_QWORD *)&v32[0] = *((_QWORD *)v17 + 6);
        DWORD2(v32[0]) = 0;
        if ( *((_BYTE *)v17 + 616) )
        {
          v19 = *((_DWORD *)v12 + 1);
          if ( !v19
            || memcmp((char *)v17 + 676, v12 + 8, 0xCu)
            || (v20 = memcmp((char *)v17 + 688, v12 + 20, 0xCu), v21 = 0, v20) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_lDD_MAC__MAC_DD_MAC__MAC_llllD(
                WPP_GLOBAL_Control->AttachedDevice,
                (unsigned __int8)v12[301],
                (unsigned __int8)v12[300],
                v19,
                *((_DWORD *)v17 + 169),
                *((_DWORD *)v12 + 2),
                (__int64)v17 + 680,
                (__int64)(v12 + 12),
                *((_DWORD *)v17 + 172),
                *((_DWORD *)v12 + 5),
                (__int64)v17 + 692,
                (__int64)(v12 + 24),
                *((_DWORD *)v12 + 74),
                v12[300],
                v12[301],
                v12[302],
                *((_WORD *)v12 + 74));
            }
            v21 = -1073741629;
            DWORD2(v32[0]) = -1073741629;
          }
          if ( v21 )
            goto LABEL_83;
        }
        else
        {
          v24 = *(_DWORD *)v12;
          if ( !*(_DWORD *)v12 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 310, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
            }
            DWORD2(v32[0]) = -1073741616;
            goto LABEL_83;
          }
          v25 = *((unsigned int *)v17 + 134);
          if ( v24 != (_DWORD)v25 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_Dd(
                WPP_GLOBAL_Control->AttachedDevice,
                311,
                WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                v25,
                v24);
            }
            DWORD2(v32[0]) = -1073741629;
            goto LABEL_83;
          }
        }
        if ( *((_BYTE *)v17 + 616) )
        {
          v22 = *((_DWORD *)v12 + 1);
          if ( v22 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_lDDD_MAC__MAC_DD_MAC__MAC_llllD(
                WPP_GLOBAL_Control->AttachedDevice,
                (unsigned __int8)v12[301],
                (unsigned __int8)v12[300],
                v22,
                v12[128],
                *((_DWORD *)v17 + 169),
                *((_DWORD *)v12 + 2),
                (__int64)v17 + 680,
                (__int64)(v12 + 12),
                *((_DWORD *)v17 + 172),
                *((_DWORD *)v12 + 5),
                (__int64)v17 + 692,
                (__int64)(v12 + 24),
                *((_DWORD *)v12 + 74),
                v12[300],
                v12[301],
                v12[302],
                *((_WORD *)v12 + 74));
            }
            if ( v12[128] == 1 )
            {
              if ( !(unsigned __int8)WFDPeerDeviceSetState(v17, 14) )
              {
                v10 = SpinLock[0];
                goto LABEL_100;
              }
              WFDPeerDeviceQueueTimer(v17, 0x1D4C0u, 0x2EE0u);
              v33[0] = *((_QWORD *)v17 + 6);
              LODWORD(v33[1]) = 0;
              *(_QWORD *)((char *)&v33[1] + 4) = *((_QWORD *)v12 + 1);
              HIDWORD(v33[2]) = *((_DWORD *)v12 + 4);
              v33[3] = *(_QWORD *)(v12 + 20);
              LODWORD(v33[4]) = *((_DWORD *)v12 + 7);
              *(_OWORD *)((char *)&v33[4] + 4) = *(_OWORD *)(v12 + 148);
              *(_OWORD *)((char *)&v33[6] + 4) = *(_OWORD *)(v12 + 164);
              *(_OWORD *)((char *)&v33[8] + 4) = *(_OWORD *)(v12 + 180);
              *(_OWORD *)((char *)&v33[10] + 4) = *(_OWORD *)(v12 + 196);
              *(_OWORD *)((char *)&v33[12] + 4) = *(_OWORD *)(v12 + 212);
              *(_OWORD *)((char *)&v33[14] + 4) = *(_OWORD *)(v12 + 228);
              *(_OWORD *)((char *)&v33[16] + 4) = *(_OWORD *)(v12 + 244);
              *(_OWORD *)((char *)&v33[18] + 4) = *(_OWORD *)(v12 + 260);
              *(_OWORD *)((char *)&v33[20] + 4) = *(_OWORD *)(v12 + 276);
              WORD2(v33[22]) = *((_WORD *)v12 + 146);
              if ( *((_DWORD *)v12 + 31) )
              {
                BYTE6(v33[22]) |= 1u;
                *(_OWORD *)&v33[23] = *((_OWORD *)v12 + 5);
                *(_OWORD *)&v33[25] = *((_OWORD *)v12 + 6);
                *(_OWORD *)((char *)&v33[26] + 4) = *(_OWORD *)(v12 + 108);
              }
              v23 = 1;
LABEL_92:
              KeReleaseSpinLock(SpinLock[0], *((_BYTE *)v30 + 1200));
              v26 = v33;
              if ( !v23 )
                v26 = v32;
              WFDDeviceSendUpCallRequest(v31->pGenVElan->pVElanExt, v23 != 0 ? 36 : 25, v26);
              goto LABEL_101;
            }
          }
        }
LABEL_83:
        v23 = 0;
        BYTE12(v32[0]) = v12[128];
        LODWORD(v32[1]) = *(_DWORD *)v12;
        DWORD1(v32[1]) = *(_DWORD *)(v12 + 138);
        BYTE8(v32[1]) = v12[142];
        BYTE9(v32[1]) = BYTE9(v32[1]) & 0xFE | (*((_DWORD *)v12 + 36) != 0);
        WORD5(v32[1]) = *((_WORD *)v12 + 68);
        if ( *((_DWORD *)v12 + 74) )
        {
          BYTE12(v32[1]) |= 1u;
          *(_WORD *)((char *)&v32[1] + 13) = *((_WORD *)v12 + 150);
          HIBYTE(v32[1]) = v12[302];
        }
        if ( *((_DWORD *)v12 + 19) )
        {
          LOBYTE(v32[2]) |= 1u;
          *(_OWORD *)((char *)&v32[2] + 4) = *((_OWORD *)v12 + 2);
          *(_OWORD *)((char *)&v32[3] + 4) = *((_OWORD *)v12 + 3);
          v32[4] = *(_OWORD *)(v12 + 60);
        }
        if ( *((_DWORD *)v12 + 31) )
        {
          LOBYTE(v32[5]) |= 1u;
          *(_OWORD *)((char *)&v32[5] + 4) = *((_OWORD *)v12 + 5);
          *(_OWORD *)((char *)&v32[6] + 4) = *((_OWORD *)v12 + 6);
          v32[7] = *(_OWORD *)(v12 + 108);
        }
        if ( *((_DWORD *)v12 + 76) )
        {
          LOBYTE(v32[8]) |= 1u;
          *(_DWORD *)((char *)&v32[8] + 1) = *((_DWORD *)v12 + 77);
          *(_WORD *)((char *)&v32[8] + 5) = *((_WORD *)v12 + 156);
        }
        WFDPeerDeviceDestroy(v17);
        goto LABEL_92;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 300, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v8, v7, a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && BYTE1(WPP_GLOBAL_Control->Timer)
         && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 298, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, 28, a2);
  }
}

```

## disassembly

```asm
0x1400859fc  mov     [rsp-8+arg_8], rbx
0x140085a01  push    rbp
0x140085a02  push    rsi
0x140085a03  push    rdi
0x140085a04  push    r12
0x140085a06  push    r13
0x140085a08  push    r14
0x140085a0a  push    r15
0x140085a0c  lea     rbp, [rsp-150h]
0x140085a14  sub     rsp, 260h
0x140085a1b  mov     rax, cs:__security_cookie
0x140085a22  xor     rax, rsp
0x140085a25  mov     [rbp+180h+var_40], rax
0x140085a2c  mov     r15, r8
0x140085a2f  mov     [rbp+180h+var_1D0], rcx
0x140085a33  mov     ebx, edx
0x140085a35  mov     [rbp+180h+var_1E0], 0
0x140085a3d  mov     rdi, rcx
0x140085a40  xor     edx, edx; Val
0x140085a42  mov     r8d, 88h; Size
0x140085a48  lea     rcx, [rbp+180h+var_1C0]; void *
0x140085a4c  call    memset
0x140085a51  xor     edx, edx; Val
0x140085a53  lea     rcx, [rbp+180h+var_130]; void *
0x140085a57  mov     r8d, 0E8h; Size
0x140085a5d  call    memset
0x140085a62  mov     [rbp+180h+var_200], 0
0x140085a66  test    r15, r15
0x140085a69  jz      loc_14008637C
0x140085a6f  cmp     ebx, 1Ch
0x140085a72  jb      loc_14008637C
0x140085a78  mov     rsi, [rdi+0B8h]
0x140085a7f  mov     [rbp+180h+var_1D8], rsi
0x140085a83  mov     rcx, cs:WPP_GLOBAL_Control
0x140085a8a  lea     rdi, WPP_GLOBAL_Control
0x140085a91  cmp     rcx, rdi
0x140085a94  jz      short loc_140085ACF
0x140085a96  cmp     byte ptr [rcx+29h], 3
0x140085a9a  jb      short loc_140085ACF
0x140085a9c  bt      dword ptr [rcx+2Ch], 15h
0x140085aa1  jnb     short loc_140085ACF
0x140085aa3  mov     eax, [r15+18h]
0x140085aa7  lea     r9, [r15+4]
0x140085aab  movzx   r8d, byte ptr [r15+10h]
0x140085ab0  mov     edx, 12Bh
0x140085ab5  mov     rcx, [rcx+18h]
0x140085ab9  mov     dword ptr [rsp+290h+var_260], eax
0x140085abd  mov     eax, [r15+14h]
0x140085ac1  mov     [rsp+290h+var_268], eax
0x140085ac5  mov     dword ptr [rsp+290h+var_270], r8d
0x140085aca  call    WPP_SF__MAC_DDD
0x140085acf  mov     r8d, [r15+18h]
0x140085ad3  test    r8d, r8d
0x140085ad6  jz      short loc_140085AE6
0x140085ad8  mov     r9d, [r15+14h]
0x140085adc  cmp     r9d, 1Ch
0x140085ae0  jb      loc_140086343
0x140085ae6  mov     r9d, [r15+14h]
0x140085aea  lea     eax, [r9+r8]
0x140085aee  cmp     eax, r9d
0x140085af1  jb      loc_140086343
0x140085af7  cmp     eax, ebx
0x140085af9  ja      loc_140086343
0x140085aff  lea     rbx, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140085b06  test    r8d, r8d
0x140085b09  jz      short loc_140085B56
0x140085b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140085b12  cmp     rcx, rdi
0x140085b15  jz      short loc_140085B56
0x140085b17  cmp     byte ptr [rcx+29h], 3
0x140085b1b  jb      short loc_140085B56
0x140085b1d  bt      dword ptr [rcx+2Ch], 15h
0x140085b22  jnb     short loc_140085B56
0x140085b24  mov     rcx, [rcx+18h]
0x140085b28  lea     rax, [r15+r9]
0x140085b2c  xorps   xmm0, xmm0
0x140085b2f  lea     r9, [rbp+180h+SpinLock]
0x140085b33  movups  xmmword ptr [rbp+180h+SpinLock], xmm0
0x140085b37  mov     word ptr [rbp+180h+SpinLock], r8w
0x140085b3c  mov     edx, 12Dh
0x140085b41  mov     [rbp+180h+SpinLock+8], rax
0x140085b45  mov     r8, rbx
0x140085b48  movaps  xmm0, xmmword ptr [rbp+180h+SpinLock]
0x140085b4c  movdqa  xmmword ptr [rbp+180h+SpinLock], xmm0
0x140085b51  call    WPP_SF__HEX_
0x140085b56  lea     r13, [rsi+4A8h]
0x140085b5d  mov     rcx, r13; SpinLock
0x140085b60  mov     [rbp+180h+SpinLock], r13
0x140085b64  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140085b6b  nop     dword ptr [rax+rax+00h]
0x140085b70  lea     r12, [r15+4]
0x140085b74  mov     rcx, rsi; struct _WFD_DEVICE_ROLE *
0x140085b77  lea     r8, [rbp+180h+var_1E0]; struct _WFD_PEER_DEVICE **
0x140085b7b  mov     [rsi+4B0h], al
0x140085b81  mov     rdx, r12; unsigned __int8 (*)[6]
0x140085b84  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x140085b89  test    eax, eax
0x140085b8b  jz      short loc_140085BCD
0x140085b8d  xor     esi, esi
0x140085b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140085b96  cmp     rcx, rdi
0x140085b99  jz      loc_1400862F3
0x140085b9f  cmp     byte ptr [rcx+29h], 3
0x140085ba3  jb      loc_1400862F3
0x140085ba9  bt      dword ptr [rcx+2Ch], 15h
0x140085bae  jnb     loc_1400862F3
0x140085bb4  mov     rcx, [rcx+18h]
0x140085bb8  mov     edx, 12Eh
0x140085bbd  mov     r9, r12
0x140085bc0  mov     r8, rbx
0x140085bc3  call    WPP_SF__MAC_
0x140085bc8  jmp     loc_1400862F3
0x140085bcd  lea     rsi, Lookaside
0x140085bd4  mov     rcx, rsi; Lookaside
0x140085bd7  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140085bde  nop     dword ptr [rax+rax+00h]
0x140085be3  test    rax, rax
0x140085be6  jnz     short loc_140085C25
0x140085be8  xor     esi, esi
0x140085bea  mov     rcx, cs:WPP_GLOBAL_Control
0x140085bf1  cmp     rcx, rdi
0x140085bf4  jz      loc_1400862F3
0x140085bfa  cmp     byte ptr [rcx+29h], 1
0x140085bfe  jb      loc_1400862F3
0x140085c04  bt      dword ptr [rcx+2Ch], 15h
0x140085c09  jnb     loc_1400862F3
0x140085c0f  mov     edx, 12Fh
0x140085c14  mov     rcx, [rcx+18h]
0x140085c18  mov     r8, rbx
0x140085c1b  call    WPP_SF_
0x140085c20  jmp     loc_1400862F3
0x140085c25  mov     [rax], rsi
0x140085c28  xor     edx, edx; Val
0x140085c2a  lea     rsi, [rax+10h]
0x140085c2e  mov     dword ptr [rax+8], 30337776h
0x140085c35  mov     rcx, rsi; void *
0x140085c38  mov     r8d, 13Ch; Size
0x140085c3e  call    memset
0x140085c43  mov     ecx, [r15+14h]
0x140085c47  mov     r8, rsi; void *
0x140085c4a  mov     edx, [r15+18h]; unsigned int
0x140085c4e  add     rcx, r15; unsigned __int8 *
0x140085c51  call    WFDValidateIncomingProvisionDiscoveryResponseIEs
0x140085c56  test    al, al
0x140085c58  jnz     short loc_140085C86
0x140085c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140085c61  cmp     rcx, rdi
0x140085c64  jz      loc_1400862F3
0x140085c6a  cmp     byte ptr [rcx+29h], 1
0x140085c6e  jb      loc_1400862F3
0x140085c74  bt      dword ptr [rcx+2Ch], 15h
0x140085c79  jnb     loc_1400862F3
0x140085c7f  mov     edx, 130h
0x140085c84  jmp     short loc_140085C14
0x140085c86  mov     r9b, [r15+10h]; unsigned __int8
0x140085c8a  lea     rax, [rbp+180h+var_200]
0x140085c8e  mov     rcx, [rbp+180h+var_1D8]; struct _WFD_DEVICE_ROLE *
0x140085c92  mov     r8d, 6; enum _WFD_RECEIVED_PACKET_TYPE
0x140085c98  mov     rdx, r12; unsigned __int8 (*)[6]
0x140085c9b  mov     [rsp+290h+var_270], rax; unsigned __int8 *
0x140085ca0  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x140085ca5  test    eax, eax
0x140085ca7  js      loc_1400862BE
0x140085cad  cmp     [rbp+180h+var_200], 0
0x140085cb1  jnz     loc_1400862BE
0x140085cb7  movzx   edx, byte ptr [r15+10h]
0x140085cbc  mov     r15, [rbp+180h+var_1E0]
0x140085cc0  movzx   r8d, byte ptr [r15+28h]
0x140085cc5  cmp     r8b, dl
0x140085cc8  jz      short loc_140085D0E
0x140085cca  mov     rcx, cs:WPP_GLOBAL_Control
0x140085cd1  cmp     rcx, rdi
0x140085cd4  jz      loc_1400862F3
0x140085cda  cmp     byte ptr [rcx+29h], 3
0x140085cde  jb      loc_1400862F3
0x140085ce4  bt      dword ptr [rcx+2Ch], 15h
0x140085ce9  jnb     loc_1400862F3
0x140085cef  mov     rcx, [rcx+18h]
0x140085cf3  mov     eax, edx
0x140085cf5  mov     r9d, r8d
0x140085cf8  mov     dword ptr [rsp+290h+var_270], eax
0x140085cfc  mov     edx, 132h
0x140085d01  mov     r8, rbx
0x140085d04  call    WPP_SF_Dd
0x140085d09  jmp     loc_1400862F3
0x140085d0e  mov     edx, 0Dh
0x140085d13  mov     rcx, r15
0x140085d16  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x140085d1b  test    al, al
0x140085d1d  jz      loc_1400862F3
0x140085d23  mov     rcx, r15; struct _WFD_PEER_DEVICE *
0x140085d26  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCancelTimer(_WFD_PEER_DEVICE *)
0x140085d2b  test    eax, eax
0x140085d2d  jnz     short loc_140085D70
0x140085d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140085d36  cmp     rcx, rdi
0x140085d39  jz      loc_1400862F3
0x140085d3f  cmp     byte ptr [rcx+29h], 1
0x140085d43  jb      loc_1400862F3
0x140085d49  bt      dword ptr [rcx+2Ch], 15h
0x140085d4e  jnb     loc_1400862F3
0x140085d54  mov     rcx, [rcx+18h]
0x140085d58  lea     r9, [r15+18h]
0x140085d5c  mov     edx, 133h
0x140085d61  mov     [rsp+290h+var_270], r15
0x140085d66  call    WPP_SF__MAC_q
0x140085d6b  jmp     loc_1400862F3
0x140085d70  mov     r9b, [r15+350h]; unsigned __int8
0x140085d77  xor     r13d, r13d
0x140085d7a  xor     r8d, r8d; unsigned __int8
0x140085d7d  mov     byte ptr [rsp+290h+var_270], r13b; unsigned __int8
0x140085d82  mov     rdx, r12; unsigned __int8 (*)[6]
0x140085d85  mov     rcx, rsi; struct _WFD_PROVISION_DISCOVERY_RESPONSE_ATTRIBUTES *
0x140085d88  call    ?WFDDeviceValidateProvisionDiscoveryResponseAttributes@@YAEPEAU_WFD_PROVISION_DISCOVERY_RESPONSE_ATTRIBUTES@@PEAY05EEEE@Z; WFDDeviceValidateProvisionDiscoveryResponseAttributes(_WFD_PROVISION_DISCOVERY_RESPONSE_ATTRIBUTES *,uchar (*)[6],uchar,uchar,uchar)
0x140085d8d  test    al, al
0x140085d8f  jnz     short loc_140085DBB
0x140085d91  mov     rcx, cs:WPP_GLOBAL_Control
0x140085d98  cmp     rcx, rdi
0x140085d9b  jz      short loc_140085DBB
0x140085d9d  cmp     byte ptr [rcx+29h], 2
0x140085da1  jb      short loc_140085DBB
0x140085da3  bt      dword ptr [rcx+2Ch], 15h
0x140085da8  jnb     short loc_140085DBB
0x140085daa  mov     rcx, [rcx+18h]
0x140085dae  mov     edx, 134h
0x140085db3  mov     r8, rbx
0x140085db6  call    WPP_SF_
0x140085dbb  xor     edx, edx; Val
0x140085dbd  lea     rcx, [rbp+180h+var_1C0]; void *
0x140085dc1  mov     r8d, 88h; Size
0x140085dc7  call    memset
0x140085dcc  xor     edx, edx; Val
0x140085dce  lea     rcx, [rbp+180h+var_130]; void *
0x140085dd2  mov     r8d, 0E8h; Size
0x140085dd8  call    memset
0x140085ddd  mov     rax, [r15+30h]
0x140085de1  mov     [rbp+180h+var_1C0], rax
0x140085de5  mov     [rbp+180h+var_1B8], r13d
0x140085de9  cmp     [r15+268h], r13b
0x140085df0  jz      loc_14008610E
0x140085df6  mov     r12d, [rsi+4]
0x140085dfa  test    r12d, r12d
0x140085dfd  jz      short loc_140085E39
0x140085dff  mov     ebx, 0Ch
0x140085e04  lea     rdx, [rsi+8]; Buf2
0x140085e08  mov     r8d, ebx; Size
0x140085e0b  lea     rcx, [r15+2A4h]; Buf1
0x140085e12  call    memcmp
0x140085e17  test    eax, eax
0x140085e19  jnz     short loc_140085E39
0x140085e1b  lea     rdx, [rsi+14h]; Buf2
0x140085e1f  mov     r8d, ebx; Size
0x140085e22  lea     rcx, [r15+2B0h]; Buf1
0x140085e29  call    memcmp
0x140085e2e  mov     ecx, r13d
0x140085e31  test    eax, eax
0x140085e33  jz      loc_140085F00
0x140085e39  mov     r13, cs:WPP_GLOBAL_Control
0x140085e40  cmp     r13, rdi
0x140085e43  jz      loc_140085EF5
0x140085e49  cmp     byte ptr [r13+29h], 3
0x140085e4e  jb      loc_140085EF5
0x140085e54  bt      dword ptr [r13+2Ch], 15h
0x140085e5a  jnb     loc_140085EF5
0x140085e60  movzx   eax, word ptr [rsi+94h]
0x140085e67  lea     r9, [rsi+18h]
0x140085e6b  movzx   ecx, byte ptr [rsi+12Eh]
0x140085e72  lea     r10, [r15+2B4h]
0x140085e79  movzx   edx, byte ptr [rsi+12Dh]
0x140085e80  lea     r11, [rsi+0Ch]
0x140085e84  movzx   r8d, byte ptr [rsi+12Ch]
0x140085e8c  lea     rbx, [r15+2A8h]
0x140085e93  mov     [rsp+290h+var_210], eax
0x140085e9a  mov     eax, [rsi+128h]
0x140085ea0  mov     [rsp+290h+var_218], ecx
0x140085ea4  mov     rcx, [r13+18h]
0x140085ea8  mov     [rsp+290h+var_220], edx
0x140085eac  mov     [rsp+290h+var_228], r8d
0x140085eb1  mov     dword ptr [rsp+290h+var_230], eax
0x140085eb5  mov     eax, [rsi+14h]
0x140085eb8  mov     [rsp+290h+var_238], r9
0x140085ebd  mov     r9d, r12d
0x140085ec0  mov     [rsp+290h+var_240], r10
0x140085ec5  mov     [rsp+290h+var_248], eax
0x140085ec9  mov     eax, [r15+2B0h]
0x140085ed0  mov     dword ptr [rsp+290h+var_250], eax
0x140085ed4  mov     eax, [rsi+8]
0x140085ed7  mov     [rsp+290h+var_258], r11
0x140085edc  mov     [rsp+290h+var_260], rbx
0x140085ee1  mov     [rsp+290h+var_268], eax
0x140085ee5  mov     eax, [r15+2A4h]
0x140085eec  mov     dword ptr [rsp+290h+var_270], eax
0x140085ef0  call    WPP_SF_lDD_MAC__MAC_DD_MAC__MAC_llllD
0x140085ef5  mov     ecx, 0C00000C3h
0x140085efa  xor     r13d, r13d
0x140085efd  mov     [rbp+180h+var_1B8], ecx
0x140085f00  test    ecx, ecx
0x140085f02  jnz     loc_140086195
0x140085f08  cmp     [r15+268h], r13b
0x140085f0f  jz      loc_140086195
  ... truncated ...
```

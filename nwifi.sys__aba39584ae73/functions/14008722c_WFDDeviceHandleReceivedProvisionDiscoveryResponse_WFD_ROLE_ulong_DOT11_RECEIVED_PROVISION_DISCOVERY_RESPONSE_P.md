# WFDDeviceHandleReceivedProvisionDiscoveryResponse(_WFD_ROLE *,ulong,_DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS *)

- ea: `0x14008722c`
- end: `0x140087c16`
- name: `?WFDDeviceHandleReceivedProvisionDiscoveryResponse@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS@@@Z`
- size: `2538`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007e160`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x140022f08`
- `0x14002f44c`
- `0x140030244`
- `0x14003b04c`
- `0x140080a84`
- `0x140080dfc`
- `0x14008722c`
- `0x14008adb8`
- `0x14008b50c`
- `0x14008bfb0`
- `0x14008c694`
- `0x14008c788`
- `0x14008ccd4`
- `0x14008de3c`
- `0x14008e230`
- `0x14008e46c`
- `0x1400998dc`
- `0x14009bbb0`
- `0x14009bfc0`
- `0x14009c4e0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140087407`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140087407`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087b51`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087b51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087b65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087b65`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087aa3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087b2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087aa3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087b2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140087394`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140087394`

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
  _DWORD *v12; // rsi
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
      WPP_SF__MAC_DDD(
        WPP_GLOBAL_Control->AttachedDevice,
        299,
        *((unsigned __int8 *)a3 + 16),
        (char *)a3 + 4,
        *((unsigned __int8 *)a3 + 16),
        *((_DWORD *)a3 + 5),
        *((_DWORD *)a3 + 6));
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
        v12 = v13 + 4;
        v13[2] = 808679286;
        memset(v13 + 4, 0, 0x13Cu);
        if ( !(unsigned __int8)WFDValidateIncomingProvisionDiscoveryResponseIEs(
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
                    WfdReceivedPacketTypeProvisionDiscoveryResponse,
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
              ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 4);
            else
              ExFreePoolWithTag(v12 - 4, *(v12 - 2));
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
          v19 = v12[1];
          if ( !v19
            || memcmp((char *)v17 + 676, v12 + 2, 0xCu)
            || (v20 = memcmp((char *)v17 + 688, v12 + 5, 0xCu), v21 = 0, v20) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_lDD_MAC__MAC_DD_MAC__MAC_llllD(
                WPP_GLOBAL_Control->AttachedDevice,
                *((unsigned __int8 *)v12 + 301),
                *((unsigned __int8 *)v12 + 300),
                v19,
                *((_DWORD *)v17 + 169),
                v12[2],
                (__int64)v17 + 680,
                (__int64)(v12 + 3),
                *((_DWORD *)v17 + 172),
                v12[5],
                (__int64)v17 + 692,
                (__int64)(v12 + 6),
                v12[74],
                *((_BYTE *)v12 + 300),
                *((_BYTE *)v12 + 301),
                *((_BYTE *)v12 + 302),
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
          v24 = *v12;
          if ( !*v12 )
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
          v22 = v12[1];
          if ( v22 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_lDDD_MAC__MAC_DD_MAC__MAC_llllD(
                WPP_GLOBAL_Control->AttachedDevice,
                *((unsigned __int8 *)v12 + 301),
                *((unsigned __int8 *)v12 + 300),
                v22,
                *((_BYTE *)v12 + 128),
                *((_DWORD *)v17 + 169),
                v12[2],
                (__int64)v17 + 680,
                (__int64)(v12 + 3),
                *((_DWORD *)v17 + 172),
                v12[5],
                (__int64)v17 + 692,
                (__int64)(v12 + 6),
                v12[74],
                *((_BYTE *)v12 + 300),
                *((_BYTE *)v12 + 301),
                *((_BYTE *)v12 + 302),
                *((_WORD *)v12 + 74));
            }
            if ( *((_BYTE *)v12 + 128) == 1 )
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
              HIDWORD(v33[2]) = v12[4];
              v33[3] = *(_QWORD *)(v12 + 5);
              LODWORD(v33[4]) = v12[7];
              *(_OWORD *)((char *)&v33[4] + 4) = *(_OWORD *)(v12 + 37);
              *(_OWORD *)((char *)&v33[6] + 4) = *(_OWORD *)(v12 + 41);
              *(_OWORD *)((char *)&v33[8] + 4) = *(_OWORD *)(v12 + 45);
              *(_OWORD *)((char *)&v33[10] + 4) = *(_OWORD *)(v12 + 49);
              *(_OWORD *)((char *)&v33[12] + 4) = *(_OWORD *)(v12 + 53);
              *(_OWORD *)((char *)&v33[14] + 4) = *(_OWORD *)(v12 + 57);
              *(_OWORD *)((char *)&v33[16] + 4) = *(_OWORD *)(v12 + 61);
              *(_OWORD *)((char *)&v33[18] + 4) = *(_OWORD *)(v12 + 65);
              *(_OWORD *)((char *)&v33[20] + 4) = *(_OWORD *)(v12 + 69);
              WORD2(v33[22]) = *((_WORD *)v12 + 146);
              if ( v12[31] )
              {
                BYTE6(v33[22]) |= 1u;
                *(_OWORD *)&v33[23] = *((_OWORD *)v12 + 5);
                *(_OWORD *)&v33[25] = *((_OWORD *)v12 + 6);
                *(_OWORD *)((char *)&v33[26] + 4) = *(_OWORD *)(v12 + 27);
              }
              v23 = 1;
LABEL_92:
              KeReleaseSpinLock(SpinLock[0], *((_BYTE *)v30 + 1200));
              v26 = v33;
              if ( !v23 )
                v26 = v32;
              WFDDeviceSendUpCallRequest(v31->pGenVElan->pVElanExt, v23 != 0 ? 36 : 25, v26, v23 != 0 ? 232 : 136);
              goto LABEL_101;
            }
          }
        }
LABEL_83:
        v23 = 0;
        BYTE12(v32[0]) = *((_BYTE *)v12 + 128);
        LODWORD(v32[1]) = *v12;
        DWORD1(v32[1]) = *(_DWORD *)((char *)v12 + 138);
        BYTE8(v32[1]) = *((_BYTE *)v12 + 142);
        BYTE9(v32[1]) = BYTE9(v32[1]) & 0xFE | (v12[36] != 0);
        WORD5(v32[1]) = *((_WORD *)v12 + 68);
        if ( v12[74] )
        {
          BYTE12(v32[1]) |= 1u;
          *(_WORD *)((char *)&v32[1] + 13) = *((_WORD *)v12 + 150);
          HIBYTE(v32[1]) = *((_BYTE *)v12 + 302);
        }
        if ( v12[19] )
        {
          LOBYTE(v32[2]) |= 1u;
          *(_OWORD *)((char *)&v32[2] + 4) = *((_OWORD *)v12 + 2);
          *(_OWORD *)((char *)&v32[3] + 4) = *((_OWORD *)v12 + 3);
          v32[4] = *(_OWORD *)(v12 + 15);
        }
        if ( v12[31] )
        {
          LOBYTE(v32[5]) |= 1u;
          *(_OWORD *)((char *)&v32[5] + 4) = *((_OWORD *)v12 + 5);
          *(_OWORD *)((char *)&v32[6] + 4) = *((_OWORD *)v12 + 6);
          v32[7] = *(_OWORD *)(v12 + 27);
        }
        if ( v12[76] )
        {
          LOBYTE(v32[8]) |= 1u;
          *(_DWORD *)((char *)&v32[8] + 1) = v12[77];
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
0x14008722c  mov     [rsp-8+arg_8], rbx
0x140087231  push    rbp
0x140087232  push    rsi
0x140087233  push    rdi
0x140087234  push    r12
0x140087236  push    r13
0x140087238  push    r14
0x14008723a  push    r15
0x14008723c  lea     rbp, [rsp-150h]
0x140087244  sub     rsp, 260h
0x14008724b  mov     rax, cs:__security_cookie
0x140087252  xor     rax, rsp
0x140087255  mov     [rbp+180h+var_40], rax
0x14008725c  mov     r15, r8
0x14008725f  mov     [rbp+180h+var_1D0], rcx
0x140087263  mov     ebx, edx
0x140087265  mov     [rbp+180h+var_1E0], 0
0x14008726d  mov     rdi, rcx
0x140087270  xor     edx, edx; Val
0x140087272  mov     r8d, 88h; Size
0x140087278  lea     rcx, [rbp+180h+var_1C0]; void *
0x14008727c  call    memset
0x140087281  xor     edx, edx; Val
0x140087283  lea     rcx, [rbp+180h+var_130]; void *
0x140087287  mov     r8d, 0E8h; Size
0x14008728d  call    memset
0x140087292  mov     [rbp+180h+var_200], 0
0x140087296  test    r15, r15
0x140087299  jz      loc_140087BAC
0x14008729f  cmp     ebx, 1Ch
0x1400872a2  jb      loc_140087BAC
0x1400872a8  mov     rsi, [rdi+0B8h]
0x1400872af  mov     [rbp+180h+var_1D8], rsi
0x1400872b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400872ba  lea     rdi, WPP_GLOBAL_Control
0x1400872c1  cmp     rcx, rdi
0x1400872c4  jz      short loc_1400872FF
0x1400872c6  cmp     byte ptr [rcx+29h], 3
0x1400872ca  jb      short loc_1400872FF
0x1400872cc  bt      dword ptr [rcx+2Ch], 15h
0x1400872d1  jnb     short loc_1400872FF
0x1400872d3  mov     eax, [r15+18h]
0x1400872d7  lea     r9, [r15+4]
0x1400872db  movzx   r8d, byte ptr [r15+10h]
0x1400872e0  mov     edx, 12Bh
0x1400872e5  mov     rcx, [rcx+18h]
0x1400872e9  mov     dword ptr [rsp+290h+var_260], eax
0x1400872ed  mov     eax, [r15+14h]
0x1400872f1  mov     [rsp+290h+var_268], eax
0x1400872f5  mov     dword ptr [rsp+290h+var_270], r8d
0x1400872fa  call    WPP_SF__MAC_DDD
0x1400872ff  mov     r8d, [r15+18h]
0x140087303  test    r8d, r8d
0x140087306  jz      short loc_140087316
0x140087308  mov     r9d, [r15+14h]
0x14008730c  cmp     r9d, 1Ch
0x140087310  jb      loc_140087B73
0x140087316  mov     r9d, [r15+14h]
0x14008731a  lea     eax, [r9+r8]
0x14008731e  cmp     eax, r9d
0x140087321  jb      loc_140087B73
0x140087327  cmp     eax, ebx
0x140087329  ja      loc_140087B73
0x14008732f  lea     rbx, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140087336  test    r8d, r8d
0x140087339  jz      short loc_140087386
0x14008733b  mov     rcx, cs:WPP_GLOBAL_Control
0x140087342  cmp     rcx, rdi
0x140087345  jz      short loc_140087386
0x140087347  cmp     byte ptr [rcx+29h], 3
0x14008734b  jb      short loc_140087386
0x14008734d  bt      dword ptr [rcx+2Ch], 15h
0x140087352  jnb     short loc_140087386
0x140087354  mov     rcx, [rcx+18h]
0x140087358  lea     rax, [r15+r9]
0x14008735c  xorps   xmm0, xmm0
0x14008735f  lea     r9, [rbp+180h+SpinLock]
0x140087363  movups  xmmword ptr [rbp+180h+SpinLock], xmm0
0x140087367  mov     word ptr [rbp+180h+SpinLock], r8w
0x14008736c  mov     edx, 12Dh
0x140087371  mov     [rbp+180h+SpinLock+8], rax
0x140087375  mov     r8, rbx
0x140087378  movaps  xmm0, xmmword ptr [rbp+180h+SpinLock]
0x14008737c  movdqa  xmmword ptr [rbp+180h+SpinLock], xmm0
0x140087381  call    WPP_SF__HEX_
0x140087386  lea     r13, [rsi+4A8h]
0x14008738d  mov     rcx, r13; SpinLock
0x140087390  mov     [rbp+180h+SpinLock], r13
0x140087394  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008739b  nop     dword ptr [rax+rax+00h]
0x1400873a0  lea     r12, [r15+4]
0x1400873a4  mov     rcx, rsi; struct _WFD_DEVICE_ROLE *
0x1400873a7  lea     r8, [rbp+180h+var_1E0]; struct _WFD_PEER_DEVICE **
0x1400873ab  mov     [rsi+4B0h], al
0x1400873b1  mov     rdx, r12; unsigned __int8 (*)[6]
0x1400873b4  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x1400873b9  test    eax, eax
0x1400873bb  jz      short loc_1400873FD
0x1400873bd  xor     esi, esi
0x1400873bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400873c6  cmp     rcx, rdi
0x1400873c9  jz      loc_140087B23
0x1400873cf  cmp     byte ptr [rcx+29h], 3
0x1400873d3  jb      loc_140087B23
0x1400873d9  bt      dword ptr [rcx+2Ch], 15h
0x1400873de  jnb     loc_140087B23
0x1400873e4  mov     rcx, [rcx+18h]
0x1400873e8  mov     edx, 12Eh
0x1400873ed  mov     r9, r12
0x1400873f0  mov     r8, rbx
0x1400873f3  call    WPP_SF__MAC_
0x1400873f8  jmp     loc_140087B23
0x1400873fd  lea     rsi, Lookaside
0x140087404  mov     rcx, rsi; Lookaside
0x140087407  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008740e  nop     dword ptr [rax+rax+00h]
0x140087413  test    rax, rax
0x140087416  jnz     short loc_140087455
0x140087418  xor     esi, esi
0x14008741a  mov     rcx, cs:WPP_GLOBAL_Control
0x140087421  cmp     rcx, rdi
0x140087424  jz      loc_140087B23
0x14008742a  cmp     byte ptr [rcx+29h], 1
0x14008742e  jb      loc_140087B23
0x140087434  bt      dword ptr [rcx+2Ch], 15h
0x140087439  jnb     loc_140087B23
0x14008743f  mov     edx, 12Fh
0x140087444  mov     rcx, [rcx+18h]
0x140087448  mov     r8, rbx
0x14008744b  call    WPP_SF_
0x140087450  jmp     loc_140087B23
0x140087455  mov     [rax], rsi
0x140087458  xor     edx, edx; Val
0x14008745a  lea     rsi, [rax+10h]
0x14008745e  mov     dword ptr [rax+8], 30337776h
0x140087465  mov     rcx, rsi; void *
0x140087468  mov     r8d, 13Ch; Size
0x14008746e  call    memset
0x140087473  mov     ecx, [r15+14h]
0x140087477  mov     r8, rsi; void *
0x14008747a  mov     edx, [r15+18h]; unsigned int
0x14008747e  add     rcx, r15; unsigned __int8 *
0x140087481  call    WFDValidateIncomingProvisionDiscoveryResponseIEs
0x140087486  test    al, al
0x140087488  jnz     short loc_1400874B6
0x14008748a  mov     rcx, cs:WPP_GLOBAL_Control
0x140087491  cmp     rcx, rdi
0x140087494  jz      loc_140087B23
0x14008749a  cmp     byte ptr [rcx+29h], 1
0x14008749e  jb      loc_140087B23
0x1400874a4  bt      dword ptr [rcx+2Ch], 15h
0x1400874a9  jnb     loc_140087B23
0x1400874af  mov     edx, 130h
0x1400874b4  jmp     short loc_140087444
0x1400874b6  mov     r9b, [r15+10h]; unsigned __int8
0x1400874ba  lea     rax, [rbp+180h+var_200]
0x1400874be  mov     rcx, [rbp+180h+var_1D8]; struct _WFD_DEVICE_ROLE *
0x1400874c2  mov     r8d, 6; enum _WFD_RECEIVED_PACKET_TYPE
0x1400874c8  mov     rdx, r12; unsigned __int8 (*)[6]
0x1400874cb  mov     [rsp+290h+var_270], rax; unsigned __int8 *
0x1400874d0  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x1400874d5  test    eax, eax
0x1400874d7  js      loc_140087AEE
0x1400874dd  cmp     [rbp+180h+var_200], 0
0x1400874e1  jnz     loc_140087AEE
0x1400874e7  movzx   edx, byte ptr [r15+10h]
0x1400874ec  mov     r15, [rbp+180h+var_1E0]
0x1400874f0  movzx   r8d, byte ptr [r15+28h]
0x1400874f5  cmp     r8b, dl
0x1400874f8  jz      short loc_14008753E
0x1400874fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140087501  cmp     rcx, rdi
0x140087504  jz      loc_140087B23
0x14008750a  cmp     byte ptr [rcx+29h], 3
0x14008750e  jb      loc_140087B23
0x140087514  bt      dword ptr [rcx+2Ch], 15h
0x140087519  jnb     loc_140087B23
0x14008751f  mov     rcx, [rcx+18h]
0x140087523  mov     eax, edx
0x140087525  mov     r9d, r8d
0x140087528  mov     dword ptr [rsp+290h+var_270], eax
0x14008752c  mov     edx, 132h
0x140087531  mov     r8, rbx
0x140087534  call    WPP_SF_Dd
0x140087539  jmp     loc_140087B23
0x14008753e  mov     edx, 0Dh
0x140087543  mov     rcx, r15
0x140087546  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x14008754b  test    al, al
0x14008754d  jz      loc_140087B23
0x140087553  mov     rcx, r15; struct _WFD_PEER_DEVICE *
0x140087556  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCancelTimer(_WFD_PEER_DEVICE *)
0x14008755b  test    eax, eax
0x14008755d  jnz     short loc_1400875A0
0x14008755f  mov     rcx, cs:WPP_GLOBAL_Control
0x140087566  cmp     rcx, rdi
0x140087569  jz      loc_140087B23
0x14008756f  cmp     byte ptr [rcx+29h], 1
0x140087573  jb      loc_140087B23
0x140087579  bt      dword ptr [rcx+2Ch], 15h
0x14008757e  jnb     loc_140087B23
0x140087584  mov     rcx, [rcx+18h]
0x140087588  lea     r9, [r15+18h]
0x14008758c  mov     edx, 133h
0x140087591  mov     [rsp+290h+var_270], r15
0x140087596  call    WPP_SF__MAC_q
0x14008759b  jmp     loc_140087B23
0x1400875a0  mov     r9b, [r15+350h]; unsigned __int8
0x1400875a7  xor     r13d, r13d
0x1400875aa  xor     r8d, r8d; unsigned __int8
0x1400875ad  mov     byte ptr [rsp+290h+var_270], r13b; unsigned __int8
0x1400875b2  mov     rdx, r12; unsigned __int8 (*)[6]
0x1400875b5  mov     rcx, rsi; struct _WFD_PROVISION_DISCOVERY_RESPONSE_ATTRIBUTES *
0x1400875b8  call    ?WFDDeviceValidateProvisionDiscoveryResponseAttributes@@YAEPEAU_WFD_PROVISION_DISCOVERY_RESPONSE_ATTRIBUTES@@PEAY05EEEE@Z; WFDDeviceValidateProvisionDiscoveryResponseAttributes(_WFD_PROVISION_DISCOVERY_RESPONSE_ATTRIBUTES *,uchar (*)[6],uchar,uchar,uchar)
0x1400875bd  test    al, al
0x1400875bf  jnz     short loc_1400875EB
0x1400875c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400875c8  cmp     rcx, rdi
0x1400875cb  jz      short loc_1400875EB
0x1400875cd  cmp     byte ptr [rcx+29h], 2
0x1400875d1  jb      short loc_1400875EB
0x1400875d3  bt      dword ptr [rcx+2Ch], 15h
0x1400875d8  jnb     short loc_1400875EB
0x1400875da  mov     rcx, [rcx+18h]
0x1400875de  mov     edx, 134h
0x1400875e3  mov     r8, rbx
0x1400875e6  call    WPP_SF_
0x1400875eb  xor     edx, edx; Val
0x1400875ed  lea     rcx, [rbp+180h+var_1C0]; void *
0x1400875f1  mov     r8d, 88h; Size
0x1400875f7  call    memset
0x1400875fc  xor     edx, edx; Val
0x1400875fe  lea     rcx, [rbp+180h+var_130]; void *
0x140087602  mov     r8d, 0E8h; Size
0x140087608  call    memset
0x14008760d  mov     rax, [r15+30h]
0x140087611  mov     [rbp+180h+var_1C0], rax
0x140087615  mov     [rbp+180h+var_1B8], r13d
0x140087619  cmp     [r15+268h], r13b
0x140087620  jz      loc_14008793E
0x140087626  mov     r12d, [rsi+4]
0x14008762a  test    r12d, r12d
0x14008762d  jz      short loc_140087669
0x14008762f  mov     ebx, 0Ch
0x140087634  lea     rdx, [rsi+8]; Buf2
0x140087638  mov     r8d, ebx; Size
0x14008763b  lea     rcx, [r15+2A4h]; Buf1
0x140087642  call    memcmp
0x140087647  test    eax, eax
0x140087649  jnz     short loc_140087669
0x14008764b  lea     rdx, [rsi+14h]; Buf2
0x14008764f  mov     r8d, ebx; Size
0x140087652  lea     rcx, [r15+2B0h]; Buf1
0x140087659  call    memcmp
0x14008765e  mov     ecx, r13d
0x140087661  test    eax, eax
0x140087663  jz      loc_140087730
0x140087669  mov     r13, cs:WPP_GLOBAL_Control
0x140087670  cmp     r13, rdi
0x140087673  jz      loc_140087725
0x140087679  cmp     byte ptr [r13+29h], 3
0x14008767e  jb      loc_140087725
0x140087684  bt      dword ptr [r13+2Ch], 15h
0x14008768a  jnb     loc_140087725
0x140087690  movzx   eax, word ptr [rsi+94h]
0x140087697  lea     r9, [rsi+18h]
0x14008769b  movzx   ecx, byte ptr [rsi+12Eh]
0x1400876a2  lea     r10, [r15+2B4h]
0x1400876a9  movzx   edx, byte ptr [rsi+12Dh]
0x1400876b0  lea     r11, [rsi+0Ch]
0x1400876b4  movzx   r8d, byte ptr [rsi+12Ch]
0x1400876bc  lea     rbx, [r15+2A8h]
0x1400876c3  mov     [rsp+290h+var_210], eax
0x1400876ca  mov     eax, [rsi+128h]
0x1400876d0  mov     [rsp+290h+var_218], ecx
0x1400876d4  mov     rcx, [r13+18h]
0x1400876d8  mov     [rsp+290h+var_220], edx
0x1400876dc  mov     [rsp+290h+var_228], r8d
0x1400876e1  mov     dword ptr [rsp+290h+var_230], eax
0x1400876e5  mov     eax, [rsi+14h]
0x1400876e8  mov     [rsp+290h+var_238], r9
0x1400876ed  mov     r9d, r12d
0x1400876f0  mov     [rsp+290h+var_240], r10
0x1400876f5  mov     [rsp+290h+var_248], eax
0x1400876f9  mov     eax, [r15+2B0h]
0x140087700  mov     dword ptr [rsp+290h+var_250], eax
0x140087704  mov     eax, [rsi+8]
0x140087707  mov     [rsp+290h+var_258], r11
0x14008770c  mov     [rsp+290h+var_260], rbx
0x140087711  mov     [rsp+290h+var_268], eax
0x140087715  mov     eax, [r15+2A4h]
0x14008771c  mov     dword ptr [rsp+290h+var_270], eax
0x140087720  call    WPP_SF_lDD_MAC__MAC_DD_MAC__MAC_llllD
0x140087725  mov     ecx, 0C00000C3h
0x14008772a  xor     r13d, r13d
0x14008772d  mov     [rbp+180h+var_1B8], ecx
0x140087730  test    ecx, ecx
0x140087732  jnz     loc_1400879C5
0x140087738  cmp     [r15+268h], r13b
0x14008773f  jz      loc_1400879C5
  ... truncated ...
```

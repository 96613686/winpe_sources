# WFDDeviceHandleReceivedInvitationResponse(_WFD_ROLE *,ulong,_DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS *)

- ea: `0x140084de4`
- end: `0x140085386`
- name: `?WFDDeviceHandleReceivedInvitationResponse@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS@@@Z`
- size: `1442`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007c830`

## callees

- `0x14000170c`
- `0x14000d22c`
- `0x14000d2c0`
- `0x140020dc0`
- `0x140020f20`
- `0x140022f08`
- `0x14002f1bc`
- `0x14002ffb4`
- `0x14003ae2c`
- `0x14007f254`
- `0x14007f5cc`
- `0x140084de4`
- `0x140089588`
- `0x14008a780`
- `0x14008ae64`
- `0x14008af58`
- `0x14008b4a4`
- `0x14008c60c`
- `0x140097d08`
- `0x14009a3d0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140084fdd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140084fdd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400852c4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400852c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400852d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400852d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085231`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008529d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140085231`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008529d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140084f67`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140084f67`

## pseudocode

```c
void __fastcall WFDDeviceHandleReceivedInvitationResponse(
        struct _WFD_ROLE *a1,
        unsigned int a2,
        struct _DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS *a3)
{
  void *pRoleExt; // r13
  int v6; // r8d
  __int64 v7; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  int v9; // r8d
  int v10; // r9d
  KIRQL v11; // al
  struct _WFD_DEVICE_ROLE *v12; // rcx
  char *v13; // rbx
  _DWORD *v14; // rax
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  struct _WFD_PEER_DEVICE *v17; // rdi
  int v18; // edx
  __int64 v19; // r8
  __int16 v20; // ax
  char v21; // al
  unsigned __int8 v22[8]; // [rsp+40h] [rbp-39h] BYREF
  struct _WFD_DEVICE_ROLE *v23; // [rsp+48h] [rbp-31h]
  int v24; // [rsp+50h] [rbp-29h] BYREF
  struct _WFD_PEER_DEVICE *v25; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v26[2]; // [rsp+60h] [rbp-19h] BYREF
  struct _WFD_ROLE *v27; // [rsp+70h] [rbp-9h]
  _OWORD v28[2]; // [rsp+78h] [rbp-1h] BYREF

  v27 = a1;
  v25 = 0;
  v22[0] = 0;
  memset(v28, 0, sizeof(v28));
  if ( a3 && a2 >= 0x1C )
  {
    pRoleExt = a1->pRoleExt;
    v23 = (struct _WFD_DEVICE_ROLE *)pRoleExt;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF__MAC_DDD(WPP_GLOBAL_Control->AttachedDevice, 216, *((unsigned __int8 *)a3 + 16), (char *)a3 + 4);
    }
    v6 = *((_DWORD *)a3 + 6);
    if ( !v6 || (v7 = *((unsigned int *)a3 + 5), (unsigned int)v7 >= 0x1C) )
    {
      v7 = *((unsigned int *)a3 + 5);
      if ( (int)v7 + v6 >= (unsigned int)v7 && (int)v7 + v6 <= a2 )
      {
        if ( v6
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          v26[0] = (unsigned __int16)v6;
          v26[1] = (char *)a3 + v7;
          WPP_SF__HEX_(AttachedDevice, 218, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v26);
        }
        if ( (unsigned int)dword_1400AE050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400AE050, 0x200000000000LL) )
        {
          v24 = 0;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1400AE050,
            (unsigned int)&dword_1400A5504,
            v9,
            v10,
            (__int64)&v24);
        }
        v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
        v12 = v23;
        *((_BYTE *)pRoleExt + 1200) = v11;
        if ( (unsigned int)WFDDeviceFindPeerByMAC(v12, (unsigned __int8 (*)[6])((char *)a3 + 4), &v25) )
        {
          v13 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            WPP_SF__MAC_(
              WPP_GLOBAL_Control->AttachedDevice,
              219,
              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
              (char *)a3 + 4);
          }
          goto LABEL_63;
        }
        v14 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
        if ( v14 )
        {
          v17 = v25;
          *(_QWORD *)v14 = &WPP_MAIN_CB.DeviceQueue;
          v13 = (char *)(v14 + 4);
          v14[2] = 808679286;
          *((_QWORD *)v14 + 2) = 0;
          v14[6] = 0;
          *((_WORD *)v14 + 14) = 0;
          *((_BYTE *)v14 + 30) = 0;
          if ( (unsigned __int8)WFDValidateIncomingInvitationResponseIEs(
                                  (unsigned __int8 *)a3 + *((unsigned int *)a3 + 5),
                                  *((_DWORD *)a3 + 6)) )
          {
            if ( (int)WFDDeviceCheckDuplicateTransmission(
                        v23,
                        (unsigned __int8 (*)[6])((char *)a3 + 4),
                        4,
                        *((_BYTE *)a3 + 16),
                        v22) < 0
              || v22[0] )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  222,
                  WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                  *((unsigned __int8 *)a3 + 16));
              }
            }
            else
            {
              v18 = *((unsigned __int8 *)a3 + 16);
              if ( *((_BYTE *)v17 + 40) == (_BYTE)v18 )
              {
                if ( (unsigned __int8)WFDPeerDeviceSetState(v17, 5) )
                {
                  if ( (unsigned int)WFDPeerDeviceCancelTimer(v17) )
                  {
                    if ( *v13 != 1 || (*((_BYTE *)v17 + 466) & 1) == 0 )
                    {
                      *(_QWORD *)&v28[0] = *((_QWORD *)v17 + 6);
                      DWORD2(v28[0]) = 0;
                      BYTE12(v28[0]) = *v13;
                      if ( !*v13 )
                      {
                        if ( (v13[14] & 1) != 0 )
                        {
                          *(_DWORD *)((char *)v28 + 13) = *((_DWORD *)v13 + 2);
                          v20 = *((_WORD *)v13 + 6);
                        }
                        else
                        {
                          *(_DWORD *)((char *)v28 + 13) = *(_DWORD *)((char *)v17 + 467);
                          v20 = *(_WORD *)((char *)v17 + 471);
                        }
                        *(_WORD *)((char *)&v28[1] + 1) = v20;
                        *(_WORD *)((char *)&v28[1] + 9) = *(_WORD *)(v13 + 1);
                        if ( (v13[14] & 2) != 0 )
                        {
                          *(_DWORD *)((char *)&v28[1] + 3) = *(_DWORD *)(v13 + 3);
                          v21 = v13[7];
                          BYTE8(v28[1]) |= 1u;
                          BYTE7(v28[1]) = v21;
                        }
                      }
                      WFDPeerDeviceDestroy(v17);
                      KeReleaseSpinLock((PKSPIN_LOCK)v23 + 149, *((_BYTE *)v23 + 1200));
                      WFDDeviceSendUpCallRequest(v27->pGenVElan->pVElanExt, 21, v28);
                      goto LABEL_64;
                    }
                    if ( (unsigned __int8)WFDPeerDeviceSetState(v17, 6) )
                      WFDPeerDeviceQueueTimer(v17, 0x1D4C0u, 0x2EE0u);
                  }
                  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                         && BYTE1(WPP_GLOBAL_Control->Timer)
                         && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
                  {
                    WPP_SF__MAC_q(WPP_GLOBAL_Control->AttachedDevice, 224, v19, (char *)v17 + 24, v17);
                  }
                }
              }
              else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                     && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                WPP_SF_Dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  223,
                  WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                  *((unsigned __int8 *)v17 + 40),
                  v18);
              }
            }
LABEL_63:
            KeReleaseSpinLock((PKSPIN_LOCK)v23 + 149, *((_BYTE *)v23 + 1200));
LABEL_64:
            if ( v13 )
            {
              if ( *((_QWORD *)v13 - 2) )
                ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 - 2), v13 - 16);
              else
                ExFreePoolWithTag(v13 - 16, *((_DWORD *)v13 - 2));
            }
            return;
          }
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control->Timer)
            || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            goto LABEL_63;
          }
          v16 = 221;
        }
        else
        {
          v13 = 0;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control->Timer)
            || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            goto LABEL_63;
          }
          v16 = 220;
        }
        WPP_SF_(v15->AttachedDevice, v16, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        goto LABEL_63;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 217, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v7, v6, a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && BYTE1(WPP_GLOBAL_Control->Timer)
         && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 215, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, 28, a2);
  }
}

```

## disassembly

```asm
0x140084de4  mov     [rsp-8+arg_8], rbx
0x140084de9  push    rbp
0x140084dea  push    rsi
0x140084deb  push    rdi
0x140084dec  push    r12
0x140084dee  push    r13
0x140084df0  push    r14
0x140084df2  push    r15
0x140084df4  lea     rbp, [rsp-27h]
0x140084df9  sub     rsp, 0A0h
0x140084e00  mov     rax, cs:__security_cookie
0x140084e07  xor     rax, rsp
0x140084e0a  mov     [rbp+57h+var_38], rax
0x140084e0e  xor     edi, edi
0x140084e10  mov     [rbp+57h+var_60], rcx
0x140084e14  mov     [rbp+57h+var_78], rdi
0x140084e18  xorps   xmm0, xmm0
0x140084e1b  mov     [rbp+57h+var_90], dil
0x140084e1f  mov     r15, r8
0x140084e22  mov     ebx, edx
0x140084e24  movups  [rbp+57h+var_58], xmm0
0x140084e28  movups  [rbp+57h+var_48], xmm0
0x140084e2c  test    r8, r8
0x140084e2f  jz      loc_14008531F
0x140084e35  cmp     edx, 1Ch
0x140084e38  jb      loc_14008531F
0x140084e3e  mov     r13, [rcx+0B8h]
0x140084e45  mov     [rbp+57h+var_88], r13
0x140084e49  mov     rcx, cs:WPP_GLOBAL_Control
0x140084e50  lea     rsi, WPP_GLOBAL_Control
0x140084e57  cmp     rcx, rsi
0x140084e5a  jz      short loc_140084E95
0x140084e5c  cmp     byte ptr [rcx+29h], 3
0x140084e60  jb      short loc_140084E95
0x140084e62  bt      dword ptr [rcx+2Ch], 15h
0x140084e67  jnb     short loc_140084E95
0x140084e69  mov     eax, [r15+18h]
0x140084e6d  lea     r9, [r15+4]
0x140084e71  movzx   r8d, byte ptr [r8+10h]
0x140084e76  mov     edx, 0D8h
0x140084e7b  mov     rcx, [rcx+18h]
0x140084e7f  mov     [rsp+0D0h+var_A0], eax
0x140084e83  mov     eax, [r15+14h]
0x140084e87  mov     [rsp+0D0h+var_A8], eax
0x140084e8b  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x140084e90  call    WPP_SF__MAC_DDD
0x140084e95  mov     r8d, [r15+18h]
0x140084e99  test    r8d, r8d
0x140084e9c  jz      short loc_140084EAC
0x140084e9e  mov     r9d, [r15+14h]
0x140084ea2  cmp     r9d, 1Ch
0x140084ea6  jb      loc_1400852E6
0x140084eac  mov     r9d, [r15+14h]
0x140084eb0  lea     eax, [r9+r8]
0x140084eb4  cmp     eax, r9d
0x140084eb7  jb      loc_1400852E6
0x140084ebd  cmp     eax, ebx
0x140084ebf  ja      loc_1400852E6
0x140084ec5  lea     r12, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140084ecc  test    r8d, r8d
0x140084ecf  jz      short loc_140084F1C
0x140084ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x140084ed8  cmp     rcx, rsi
0x140084edb  jz      short loc_140084F1C
0x140084edd  cmp     byte ptr [rcx+29h], 3
0x140084ee1  jb      short loc_140084F1C
0x140084ee3  bt      dword ptr [rcx+2Ch], 15h
0x140084ee8  jnb     short loc_140084F1C
0x140084eea  mov     rcx, [rcx+18h]
0x140084eee  lea     rax, [r15+r9]
0x140084ef2  xorps   xmm0, xmm0
0x140084ef5  lea     r9, [rbp+57h+var_70]
0x140084ef9  movups  [rbp+57h+var_70], xmm0
0x140084efd  mov     word ptr [rbp+57h+var_70], r8w
0x140084f02  mov     edx, 0DAh
0x140084f07  mov     qword ptr [rbp+57h+var_70+8], rax
0x140084f0b  mov     r8, r12
0x140084f0e  movaps  xmm0, [rbp+57h+var_70]
0x140084f12  movdqa  [rbp+57h+var_70], xmm0
0x140084f17  call    WPP_SF__HEX_
0x140084f1c  mov     eax, cs:dword_1400AE050
0x140084f22  cmp     eax, 5
0x140084f25  jbe     short loc_140084F60
0x140084f27  mov     rdx, 200000000000h
0x140084f31  lea     rcx, dword_1400AE050
0x140084f38  call    _tlgKeywordOn
0x140084f3d  test    al, al
0x140084f3f  jz      short loc_140084F60
0x140084f41  lea     rax, [rbp+57h+var_80]
0x140084f45  mov     [rbp+57h+var_80], edi
0x140084f48  lea     rdx, dword_1400A5504
0x140084f4f  mov     [rsp+0D0h+var_B0], rax
0x140084f54  lea     rcx, dword_1400AE050
0x140084f5b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z
0x140084f60  lea     rcx, [r13+4A8h]; SpinLock
0x140084f67  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140084f6e  nop     dword ptr [rax+rax+00h]
0x140084f73  mov     rcx, [rbp+57h+var_88]; struct _WFD_DEVICE_ROLE *
0x140084f77  lea     r8, [rbp+57h+var_78]; struct _WFD_PEER_DEVICE **
0x140084f7b  mov     [r13+4B0h], al
0x140084f82  lea     r13, [r15+4]
0x140084f86  mov     rdx, r13; unsigned __int8 (*)[6]
0x140084f89  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z
0x140084f8e  test    eax, eax
0x140084f90  jz      short loc_140084FD3
0x140084f92  mov     rbx, rdi
0x140084f95  mov     rcx, cs:WPP_GLOBAL_Control
0x140084f9c  cmp     rcx, rsi
0x140084f9f  jz      loc_14008528F
0x140084fa5  cmp     byte ptr [rcx+29h], 3
0x140084fa9  jb      loc_14008528F
0x140084faf  bt      dword ptr [rcx+2Ch], 15h
0x140084fb4  jnb     loc_14008528F
0x140084fba  mov     rcx, [rcx+18h]
0x140084fbe  mov     edx, 0DBh
0x140084fc3  mov     r9, r13
0x140084fc6  mov     r8, r12
0x140084fc9  call    WPP_SF__MAC_
0x140084fce  jmp     loc_14008528F
0x140084fd3  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140084fda  mov     rcx, rbx; Lookaside
0x140084fdd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140084fe4  nop     dword ptr [rax+rax+00h]
0x140084fe9  test    rax, rax
0x140084fec  jnz     short loc_14008502C
0x140084fee  mov     rbx, rdi
0x140084ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x140084ff8  cmp     rcx, rsi
0x140084ffb  jz      loc_14008528F
0x140085001  cmp     byte ptr [rcx+29h], 1
0x140085005  jb      loc_14008528F
0x14008500b  bt      dword ptr [rcx+2Ch], 15h
0x140085010  jnb     loc_14008528F
0x140085016  mov     edx, 0DCh
0x14008501b  mov     rcx, [rcx+18h]
0x14008501f  mov     r8, r12
0x140085022  call    WPP_SF_
0x140085027  jmp     loc_14008528F
0x14008502c  mov     rdi, [rbp+57h+var_78]
0x140085030  mov     [rax], rbx
0x140085033  lea     rbx, [rax+10h]
0x140085037  mov     dword ptr [rax+8], 30337776h
0x14008503e  mov     r9, rbx
0x140085041  xor     eax, eax
0x140085043  mov     [rbx], rax
0x140085046  mov     [rbx+8], eax
0x140085049  mov     [rbx+0Ch], ax
0x14008504d  mov     [rbx+0Eh], al
0x140085050  cmp     [rdi+20Ch], al
0x140085056  mov     ecx, [r15+14h]
0x14008505a  mov     edx, [r15+18h]; unsigned int
0x14008505e  setz    r8b
0x140085062  add     rcx, r15; unsigned __int8 *
0x140085065  call    WFDValidateIncomingInvitationResponseIEs
0x14008506a  test    al, al
0x14008506c  jnz     short loc_14008509A
0x14008506e  mov     rcx, cs:WPP_GLOBAL_Control
0x140085075  cmp     rcx, rsi
0x140085078  jz      loc_14008528F
0x14008507e  cmp     byte ptr [rcx+29h], 1
0x140085082  jb      loc_14008528F
0x140085088  bt      dword ptr [rcx+2Ch], 15h
0x14008508d  jnb     loc_14008528F
0x140085093  mov     edx, 0DDh
0x140085098  jmp     short loc_14008501B
0x14008509a  mov     r9b, [r15+10h]; unsigned __int8
0x14008509e  lea     rax, [rbp+57h+var_90]
0x1400850a2  mov     rcx, [rbp+57h+var_88]; struct _WFD_DEVICE_ROLE *
0x1400850a6  mov     r8d, 4; enum _WFD_RECEIVED_PACKET_TYPE
0x1400850ac  mov     rdx, r13; unsigned __int8 (*)[6]
0x1400850af  mov     [rsp+0D0h+var_B0], rax; unsigned __int8 *
0x1400850b4  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z
0x1400850b9  test    eax, eax
0x1400850bb  js      loc_140085260
0x1400850c1  cmp     [rbp+57h+var_90], 0
0x1400850c5  jnz     loc_140085260
0x1400850cb  movzx   edx, byte ptr [r15+10h]
0x1400850d0  movzx   r8d, byte ptr [rdi+28h]
0x1400850d5  cmp     r8b, dl
0x1400850d8  jz      short loc_14008511E
0x1400850da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400850e1  cmp     rcx, rsi
0x1400850e4  jz      loc_14008528F
0x1400850ea  cmp     byte ptr [rcx+29h], 3
0x1400850ee  jb      loc_14008528F
0x1400850f4  bt      dword ptr [rcx+2Ch], 15h
0x1400850f9  jnb     loc_14008528F
0x1400850ff  mov     rcx, [rcx+18h]
0x140085103  mov     eax, edx
0x140085105  mov     r9d, r8d
0x140085108  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14008510c  mov     edx, 0DFh
0x140085111  mov     r8, r12
0x140085114  call    WPP_SF_Dd
0x140085119  jmp     loc_14008528F
0x14008511e  mov     edx, 5
0x140085123  mov     rcx, rdi
0x140085126  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z
0x14008512b  test    al, al
0x14008512d  jz      loc_14008528F
0x140085133  mov     rcx, rdi; struct _WFD_PEER_DEVICE *
0x140085136  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z
0x14008513b  test    eax, eax
0x14008513d  jnz     short loc_140085180
0x14008513f  mov     rcx, cs:WPP_GLOBAL_Control
0x140085146  cmp     rcx, rsi
0x140085149  jz      loc_14008528F
0x14008514f  cmp     byte ptr [rcx+29h], 1
0x140085153  jb      loc_14008528F
0x140085159  bt      dword ptr [rcx+2Ch], 15h
0x14008515e  jnb     loc_14008528F
0x140085164  mov     rcx, [rcx+18h]
0x140085168  lea     r9, [rdi+18h]
0x14008516c  mov     edx, 0E0h
0x140085171  mov     [rsp+0D0h+var_B0], rdi
0x140085176  call    WPP_SF__MAC_q
0x14008517b  jmp     loc_14008528F
0x140085180  cmp     byte ptr [rbx], 1
0x140085183  jnz     short loc_1400851BB
0x140085185  test    byte ptr [rdi+1D2h], 1
0x14008518c  jz      short loc_1400851BB
0x14008518e  mov     edx, 6
0x140085193  mov     rcx, rdi
0x140085196  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z
0x14008519b  test    al, al
0x14008519d  jz      loc_14008528F
0x1400851a3  mov     edx, 1D4C0h; unsigned int
0x1400851a8  mov     r8d, 2EE0h; unsigned int
0x1400851ae  mov     rcx, rdi; struct _WFD_PEER_DEVICE *
0x1400851b1  call    ?WFDPeerDeviceQueueTimer@@YAXPEAU_WFD_PEER_DEVICE@@KK@Z
0x1400851b6  jmp     loc_14008528F
0x1400851bb  mov     rax, [rdi+30h]
0x1400851bf  mov     qword ptr [rbp+57h+var_58], rax
0x1400851c3  mov     dword ptr [rbp+57h+var_58+8], 0
0x1400851ca  mov     al, [rbx]
0x1400851cc  mov     byte ptr [rbp+57h+var_58+0Ch], al
0x1400851cf  cmp     byte ptr [rbx], 0
0x1400851d2  jnz     short loc_140085218
0x1400851d4  test    byte ptr [rbx+0Eh], 1
0x1400851d8  jz      short loc_1400851E6
0x1400851da  mov     eax, [rbx+8]
0x1400851dd  mov     dword ptr [rbp+57h+var_58+0Dh], eax
0x1400851e0  movzx   eax, word ptr [rbx+0Ch]
0x1400851e4  jmp     short loc_1400851F6
0x1400851e6  mov     eax, [rdi+1D3h]
0x1400851ec  mov     dword ptr [rbp+57h+var_58+0Dh], eax
0x1400851ef  movzx   eax, word ptr [rdi+1D7h]
0x1400851f6  mov     word ptr [rbp+57h+var_48+1], ax
0x1400851fa  movzx   eax, word ptr [rbx+1]
0x1400851fe  mov     word ptr [rbp+57h+var_48+9], ax
0x140085202  test    byte ptr [rbx+0Eh], 2
0x140085206  jz      short loc_140085218
0x140085208  mov     eax, [rbx+3]
0x14008520b  mov     dword ptr [rbp+57h+var_48+3], eax
0x14008520e  mov     al, [rbx+7]
0x140085211  or      byte ptr [rbp+57h+var_48+8], 1
0x140085215  mov     byte ptr [rbp+57h+var_48+7], al
0x140085218  mov     rcx, rdi; struct _WFD_PEER_DEVICE *
0x14008521b  call    ?WFDPeerDeviceDestroy@@YAXPEAU_WFD_PEER_DEVICE@@@Z
0x140085220  mov     rax, [rbp+57h+var_88]
0x140085224  mov     dl, [rax+4B0h]; NewIrql
0x14008522a  lea     rcx, [rax+4A8h]; SpinLock
0x140085231  call    cs:__imp_KeReleaseSpinLock
0x140085238  nop     dword ptr [rax+rax+00h]
0x14008523d  mov     rax, [rbp+57h+var_60]
0x140085241  lea     r8, [rbp+57h+var_58]
0x140085245  mov     r9d, 20h ; ' '
0x14008524b  mov     rcx, [rax]
0x14008524e  lea     edx, [r9-0Bh]
0x140085252  mov     rcx, [rcx+1F68h]
0x140085259  call    ?WFDDeviceSendUpCallRequest@@YAXPEAU_WFD_VELAN@@W4DOT11_AUTH_UPCALL_TYPE@@PEAXK@Z
0x14008525e  jmp     short loc_1400852A9
0x140085260  mov     rcx, cs:WPP_GLOBAL_Control
0x140085267  cmp     rcx, rsi
0x14008526a  jz      short loc_14008528F
0x14008526c  cmp     byte ptr [rcx+29h], 3
0x140085270  jb      short loc_14008528F
0x140085272  bt      dword ptr [rcx+2Ch], 15h
0x140085277  jnb     short loc_14008528F
0x140085279  movzx   r9d, byte ptr [r15+10h]
0x14008527e  mov     edx, 0DEh
0x140085283  mov     rcx, [rcx+18h]
0x140085287  mov     r8, r12
0x14008528a  call    WPP_SF_d
0x14008528f  mov     rcx, [rbp+57h+var_88]
0x140085293  add     rcx, 4A8h; SpinLock
0x14008529a  mov     dl, [rcx+8]; NewIrql
0x14008529d  call    cs:__imp_KeReleaseSpinLock
0x1400852a4  nop     dword ptr [rax+rax+00h]
0x1400852a9  test    rbx, rbx
0x1400852ac  jz      loc_14008535E
0x1400852b2  lea     rcx, [rbx-10h]; P
0x1400852b6  mov     rax, [rcx]
0x1400852b9  test    rax, rax
0x1400852bc  jz      short loc_1400852D5
0x1400852be  mov     rdx, rcx; Entry
0x1400852c1  mov     rcx, rax; Lookaside
0x1400852c4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400852cb  nop     dword ptr [rax+rax+00h]
0x1400852d0  jmp     loc_14008535E
  ... truncated ...
```

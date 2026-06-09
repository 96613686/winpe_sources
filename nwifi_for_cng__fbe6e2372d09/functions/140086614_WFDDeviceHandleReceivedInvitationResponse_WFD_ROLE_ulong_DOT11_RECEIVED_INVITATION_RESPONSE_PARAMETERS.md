# WFDDeviceHandleReceivedInvitationResponse(_WFD_ROLE *,ulong,_DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS *)

- ea: `0x140086614`
- end: `0x140086bb6`
- name: `?WFDDeviceHandleReceivedInvitationResponse@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS@@@Z`
- size: `1442`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007e060`

## callees

- `0x14000170c`
- `0x14000d21c`
- `0x14000d2b0`
- `0x140020dc0`
- `0x140020f20`
- `0x140022f08`
- `0x14002f44c`
- `0x140030244`
- `0x14003b04c`
- `0x140080a84`
- `0x140080dfc`
- `0x140086614`
- `0x14008adb8`
- `0x14008bfb0`
- `0x14008c694`
- `0x14008c788`
- `0x14008ccd4`
- `0x14008de3c`
- `0x1400994e8`
- `0x14009bbb0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008680d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008680d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086af4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086b08`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086a61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086acd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086a61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140086acd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140086797`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140086797`

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
      WPP_SF__MAC_DDD(
        WPP_GLOBAL_Control->AttachedDevice,
        216,
        *((unsigned __int8 *)a3 + 16),
        (char *)a3 + 4,
        *((unsigned __int8 *)a3 + 16),
        *((_DWORD *)a3 + 5),
        *((_DWORD *)a3 + 6));
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
        if ( (unsigned int)dword_1400B1050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400B1050, 0x200000000000LL) )
        {
          v24 = 0;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1400B1050,
            (unsigned int)&dword_1400A7604,
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
                        WfdReceivedPacketTypeInviteResponse,
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
                      WFDDeviceSendUpCallRequest(v27->pGenVElan->pVElanExt, 21, v28, 32);
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
0x140086614  mov     [rsp-8+arg_8], rbx
0x140086619  push    rbp
0x14008661a  push    rsi
0x14008661b  push    rdi
0x14008661c  push    r12
0x14008661e  push    r13
0x140086620  push    r14
0x140086622  push    r15
0x140086624  lea     rbp, [rsp-27h]
0x140086629  sub     rsp, 0A0h
0x140086630  mov     rax, cs:__security_cookie
0x140086637  xor     rax, rsp
0x14008663a  mov     [rbp+57h+var_38], rax
0x14008663e  xor     edi, edi
0x140086640  mov     [rbp+57h+var_60], rcx
0x140086644  mov     [rbp+57h+var_78], rdi
0x140086648  xorps   xmm0, xmm0
0x14008664b  mov     [rbp+57h+var_90], dil
0x14008664f  mov     r15, r8
0x140086652  mov     ebx, edx
0x140086654  movups  [rbp+57h+var_58], xmm0
0x140086658  movups  [rbp+57h+var_48], xmm0
0x14008665c  test    r8, r8
0x14008665f  jz      loc_140086B4F
0x140086665  cmp     edx, 1Ch
0x140086668  jb      loc_140086B4F
0x14008666e  mov     r13, [rcx+0B8h]
0x140086675  mov     [rbp+57h+var_88], r13
0x140086679  mov     rcx, cs:WPP_GLOBAL_Control
0x140086680  lea     rsi, WPP_GLOBAL_Control
0x140086687  cmp     rcx, rsi
0x14008668a  jz      short loc_1400866C5
0x14008668c  cmp     byte ptr [rcx+29h], 3
0x140086690  jb      short loc_1400866C5
0x140086692  bt      dword ptr [rcx+2Ch], 15h
0x140086697  jnb     short loc_1400866C5
0x140086699  mov     eax, [r15+18h]
0x14008669d  lea     r9, [r15+4]
0x1400866a1  movzx   r8d, byte ptr [r8+10h]
0x1400866a6  mov     edx, 0D8h
0x1400866ab  mov     rcx, [rcx+18h]
0x1400866af  mov     [rsp+0D0h+var_A0], eax
0x1400866b3  mov     eax, [r15+14h]
0x1400866b7  mov     [rsp+0D0h+var_A8], eax
0x1400866bb  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x1400866c0  call    WPP_SF__MAC_DDD
0x1400866c5  mov     r8d, [r15+18h]
0x1400866c9  test    r8d, r8d
0x1400866cc  jz      short loc_1400866DC
0x1400866ce  mov     r9d, [r15+14h]
0x1400866d2  cmp     r9d, 1Ch
0x1400866d6  jb      loc_140086B16
0x1400866dc  mov     r9d, [r15+14h]
0x1400866e0  lea     eax, [r9+r8]
0x1400866e4  cmp     eax, r9d
0x1400866e7  jb      loc_140086B16
0x1400866ed  cmp     eax, ebx
0x1400866ef  ja      loc_140086B16
0x1400866f5  lea     r12, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400866fc  test    r8d, r8d
0x1400866ff  jz      short loc_14008674C
0x140086701  mov     rcx, cs:WPP_GLOBAL_Control
0x140086708  cmp     rcx, rsi
0x14008670b  jz      short loc_14008674C
0x14008670d  cmp     byte ptr [rcx+29h], 3
0x140086711  jb      short loc_14008674C
0x140086713  bt      dword ptr [rcx+2Ch], 15h
0x140086718  jnb     short loc_14008674C
0x14008671a  mov     rcx, [rcx+18h]
0x14008671e  lea     rax, [r15+r9]
0x140086722  xorps   xmm0, xmm0
0x140086725  lea     r9, [rbp+57h+var_70]
0x140086729  movups  [rbp+57h+var_70], xmm0
0x14008672d  mov     word ptr [rbp+57h+var_70], r8w
0x140086732  mov     edx, 0DAh
0x140086737  mov     qword ptr [rbp+57h+var_70+8], rax
0x14008673b  mov     r8, r12
0x14008673e  movaps  xmm0, [rbp+57h+var_70]
0x140086742  movdqa  [rbp+57h+var_70], xmm0
0x140086747  call    WPP_SF__HEX_
0x14008674c  mov     eax, cs:dword_1400B1050
0x140086752  cmp     eax, 5
0x140086755  jbe     short loc_140086790
0x140086757  mov     rdx, 200000000000h
0x140086761  lea     rcx, dword_1400B1050
0x140086768  call    _tlgKeywordOn
0x14008676d  test    al, al
0x14008676f  jz      short loc_140086790
0x140086771  lea     rax, [rbp+57h+var_80]
0x140086775  mov     [rbp+57h+var_80], edi
0x140086778  lea     rdx, dword_1400A7604
0x14008677f  mov     [rsp+0D0h+var_B0], rax
0x140086784  lea     rcx, dword_1400B1050
0x14008678b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z
0x140086790  lea     rcx, [r13+4A8h]; SpinLock
0x140086797  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008679e  nop     dword ptr [rax+rax+00h]
0x1400867a3  mov     rcx, [rbp+57h+var_88]; struct _WFD_DEVICE_ROLE *
0x1400867a7  lea     r8, [rbp+57h+var_78]; struct _WFD_PEER_DEVICE **
0x1400867ab  mov     [r13+4B0h], al
0x1400867b2  lea     r13, [r15+4]
0x1400867b6  mov     rdx, r13; unsigned __int8 (*)[6]
0x1400867b9  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z
0x1400867be  test    eax, eax
0x1400867c0  jz      short loc_140086803
0x1400867c2  mov     rbx, rdi
0x1400867c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400867cc  cmp     rcx, rsi
0x1400867cf  jz      loc_140086ABF
0x1400867d5  cmp     byte ptr [rcx+29h], 3
0x1400867d9  jb      loc_140086ABF
0x1400867df  bt      dword ptr [rcx+2Ch], 15h
0x1400867e4  jnb     loc_140086ABF
0x1400867ea  mov     rcx, [rcx+18h]
0x1400867ee  mov     edx, 0DBh
0x1400867f3  mov     r9, r13
0x1400867f6  mov     r8, r12
0x1400867f9  call    WPP_SF__MAC_
0x1400867fe  jmp     loc_140086ABF
0x140086803  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14008680a  mov     rcx, rbx; Lookaside
0x14008680d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140086814  nop     dword ptr [rax+rax+00h]
0x140086819  test    rax, rax
0x14008681c  jnz     short loc_14008685C
0x14008681e  mov     rbx, rdi
0x140086821  mov     rcx, cs:WPP_GLOBAL_Control
0x140086828  cmp     rcx, rsi
0x14008682b  jz      loc_140086ABF
0x140086831  cmp     byte ptr [rcx+29h], 1
0x140086835  jb      loc_140086ABF
0x14008683b  bt      dword ptr [rcx+2Ch], 15h
0x140086840  jnb     loc_140086ABF
0x140086846  mov     edx, 0DCh
0x14008684b  mov     rcx, [rcx+18h]
0x14008684f  mov     r8, r12
0x140086852  call    WPP_SF_
0x140086857  jmp     loc_140086ABF
0x14008685c  mov     rdi, [rbp+57h+var_78]
0x140086860  mov     [rax], rbx
0x140086863  lea     rbx, [rax+10h]
0x140086867  mov     dword ptr [rax+8], 30337776h
0x14008686e  mov     r9, rbx
0x140086871  xor     eax, eax
0x140086873  mov     [rbx], rax
0x140086876  mov     [rbx+8], eax
0x140086879  mov     [rbx+0Ch], ax
0x14008687d  mov     [rbx+0Eh], al
0x140086880  cmp     [rdi+20Ch], al
0x140086886  mov     ecx, [r15+14h]
0x14008688a  mov     edx, [r15+18h]; unsigned int
0x14008688e  setz    r8b
0x140086892  add     rcx, r15; unsigned __int8 *
0x140086895  call    WFDValidateIncomingInvitationResponseIEs
0x14008689a  test    al, al
0x14008689c  jnz     short loc_1400868CA
0x14008689e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400868a5  cmp     rcx, rsi
0x1400868a8  jz      loc_140086ABF
0x1400868ae  cmp     byte ptr [rcx+29h], 1
0x1400868b2  jb      loc_140086ABF
0x1400868b8  bt      dword ptr [rcx+2Ch], 15h
0x1400868bd  jnb     loc_140086ABF
0x1400868c3  mov     edx, 0DDh
0x1400868c8  jmp     short loc_14008684B
0x1400868ca  mov     r9b, [r15+10h]; unsigned __int8
0x1400868ce  lea     rax, [rbp+57h+var_90]
0x1400868d2  mov     rcx, [rbp+57h+var_88]; struct _WFD_DEVICE_ROLE *
0x1400868d6  mov     r8d, 4; enum _WFD_RECEIVED_PACKET_TYPE
0x1400868dc  mov     rdx, r13; unsigned __int8 (*)[6]
0x1400868df  mov     [rsp+0D0h+var_B0], rax; unsigned __int8 *
0x1400868e4  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z
0x1400868e9  test    eax, eax
0x1400868eb  js      loc_140086A90
0x1400868f1  cmp     [rbp+57h+var_90], 0
0x1400868f5  jnz     loc_140086A90
0x1400868fb  movzx   edx, byte ptr [r15+10h]
0x140086900  movzx   r8d, byte ptr [rdi+28h]
0x140086905  cmp     r8b, dl
0x140086908  jz      short loc_14008694E
0x14008690a  mov     rcx, cs:WPP_GLOBAL_Control
0x140086911  cmp     rcx, rsi
0x140086914  jz      loc_140086ABF
0x14008691a  cmp     byte ptr [rcx+29h], 3
0x14008691e  jb      loc_140086ABF
0x140086924  bt      dword ptr [rcx+2Ch], 15h
0x140086929  jnb     loc_140086ABF
0x14008692f  mov     rcx, [rcx+18h]
0x140086933  mov     eax, edx
0x140086935  mov     r9d, r8d
0x140086938  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14008693c  mov     edx, 0DFh
0x140086941  mov     r8, r12
0x140086944  call    WPP_SF_Dd
0x140086949  jmp     loc_140086ABF
0x14008694e  mov     edx, 5
0x140086953  mov     rcx, rdi
0x140086956  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z
0x14008695b  test    al, al
0x14008695d  jz      loc_140086ABF
0x140086963  mov     rcx, rdi; struct _WFD_PEER_DEVICE *
0x140086966  call    ?WFDPeerDeviceCancelTimer@@YAHPEAU_WFD_PEER_DEVICE@@@Z
0x14008696b  test    eax, eax
0x14008696d  jnz     short loc_1400869B0
0x14008696f  mov     rcx, cs:WPP_GLOBAL_Control
0x140086976  cmp     rcx, rsi
0x140086979  jz      loc_140086ABF
0x14008697f  cmp     byte ptr [rcx+29h], 1
0x140086983  jb      loc_140086ABF
0x140086989  bt      dword ptr [rcx+2Ch], 15h
0x14008698e  jnb     loc_140086ABF
0x140086994  mov     rcx, [rcx+18h]
0x140086998  lea     r9, [rdi+18h]
0x14008699c  mov     edx, 0E0h
0x1400869a1  mov     [rsp+0D0h+var_B0], rdi
0x1400869a6  call    WPP_SF__MAC_q
0x1400869ab  jmp     loc_140086ABF
0x1400869b0  cmp     byte ptr [rbx], 1
0x1400869b3  jnz     short loc_1400869EB
0x1400869b5  test    byte ptr [rdi+1D2h], 1
0x1400869bc  jz      short loc_1400869EB
0x1400869be  mov     edx, 6
0x1400869c3  mov     rcx, rdi
0x1400869c6  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z
0x1400869cb  test    al, al
0x1400869cd  jz      loc_140086ABF
0x1400869d3  mov     edx, 1D4C0h; unsigned int
0x1400869d8  mov     r8d, 2EE0h; unsigned int
0x1400869de  mov     rcx, rdi; struct _WFD_PEER_DEVICE *
0x1400869e1  call    ?WFDPeerDeviceQueueTimer@@YAXPEAU_WFD_PEER_DEVICE@@KK@Z
0x1400869e6  jmp     loc_140086ABF
0x1400869eb  mov     rax, [rdi+30h]
0x1400869ef  mov     qword ptr [rbp+57h+var_58], rax
0x1400869f3  mov     dword ptr [rbp+57h+var_58+8], 0
0x1400869fa  mov     al, [rbx]
0x1400869fc  mov     byte ptr [rbp+57h+var_58+0Ch], al
0x1400869ff  cmp     byte ptr [rbx], 0
0x140086a02  jnz     short loc_140086A48
0x140086a04  test    byte ptr [rbx+0Eh], 1
0x140086a08  jz      short loc_140086A16
0x140086a0a  mov     eax, [rbx+8]
0x140086a0d  mov     dword ptr [rbp+57h+var_58+0Dh], eax
0x140086a10  movzx   eax, word ptr [rbx+0Ch]
0x140086a14  jmp     short loc_140086A26
0x140086a16  mov     eax, [rdi+1D3h]
0x140086a1c  mov     dword ptr [rbp+57h+var_58+0Dh], eax
0x140086a1f  movzx   eax, word ptr [rdi+1D7h]
0x140086a26  mov     word ptr [rbp+57h+var_48+1], ax
0x140086a2a  movzx   eax, word ptr [rbx+1]
0x140086a2e  mov     word ptr [rbp+57h+var_48+9], ax
0x140086a32  test    byte ptr [rbx+0Eh], 2
0x140086a36  jz      short loc_140086A48
0x140086a38  mov     eax, [rbx+3]
0x140086a3b  mov     dword ptr [rbp+57h+var_48+3], eax
0x140086a3e  mov     al, [rbx+7]
0x140086a41  or      byte ptr [rbp+57h+var_48+8], 1
0x140086a45  mov     byte ptr [rbp+57h+var_48+7], al
0x140086a48  mov     rcx, rdi; struct _WFD_PEER_DEVICE *
0x140086a4b  call    ?WFDPeerDeviceDestroy@@YAXPEAU_WFD_PEER_DEVICE@@@Z
0x140086a50  mov     rax, [rbp+57h+var_88]
0x140086a54  mov     dl, [rax+4B0h]; NewIrql
0x140086a5a  lea     rcx, [rax+4A8h]; SpinLock
0x140086a61  call    cs:__imp_KeReleaseSpinLock
0x140086a68  nop     dword ptr [rax+rax+00h]
0x140086a6d  mov     rax, [rbp+57h+var_60]
0x140086a71  lea     r8, [rbp+57h+var_58]
0x140086a75  mov     r9d, 20h ; ' '
0x140086a7b  mov     rcx, [rax]
0x140086a7e  lea     edx, [r9-0Bh]
0x140086a82  mov     rcx, [rcx+1F68h]
0x140086a89  call    ?WFDDeviceSendUpCallRequest@@YAXPEAU_WFD_VELAN@@W4DOT11_AUTH_UPCALL_TYPE@@PEAXK@Z
0x140086a8e  jmp     short loc_140086AD9
0x140086a90  mov     rcx, cs:WPP_GLOBAL_Control
0x140086a97  cmp     rcx, rsi
0x140086a9a  jz      short loc_140086ABF
0x140086a9c  cmp     byte ptr [rcx+29h], 3
0x140086aa0  jb      short loc_140086ABF
0x140086aa2  bt      dword ptr [rcx+2Ch], 15h
0x140086aa7  jnb     short loc_140086ABF
0x140086aa9  movzx   r9d, byte ptr [r15+10h]
0x140086aae  mov     edx, 0DEh
0x140086ab3  mov     rcx, [rcx+18h]
0x140086ab7  mov     r8, r12
0x140086aba  call    WPP_SF_d
0x140086abf  mov     rcx, [rbp+57h+var_88]
0x140086ac3  add     rcx, 4A8h; SpinLock
0x140086aca  mov     dl, [rcx+8]; NewIrql
0x140086acd  call    cs:__imp_KeReleaseSpinLock
0x140086ad4  nop     dword ptr [rax+rax+00h]
0x140086ad9  test    rbx, rbx
0x140086adc  jz      loc_140086B8E
0x140086ae2  lea     rcx, [rbx-10h]; P
0x140086ae6  mov     rax, [rcx]
0x140086ae9  test    rax, rax
0x140086aec  jz      short loc_140086B05
0x140086aee  mov     rdx, rcx; Entry
0x140086af1  mov     rcx, rax; Lookaside
0x140086af4  call    cs:__imp_ExFreeToNPagedLookasideList
0x140086afb  nop     dword ptr [rax+rax+00h]
0x140086b00  jmp     loc_140086B8E
  ... truncated ...
```

# WFDDeviceHandleReceivedInvitationRequest(_WFD_ROLE *,ulong,_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *)

- ea: `0x1400848d4`
- end: `0x140084ddd`
- name: `?WFDDeviceHandleReceivedInvitationRequest@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS@@@Z`
- size: `1289`
- prototype: `void(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007c7b0`

## callees

- `0x140001d94`
- `0x14000d22c`
- `0x14000d2c0`
- `0x140020dc0`
- `0x140024370`
- `0x14002f1bc`
- `0x14002ffb4`
- `0x14007b560`
- `0x14007de4c`
- `0x14007f254`
- `0x14007f5cc`
- `0x1400848d4`
- `0x1400888a8`
- `0x14008890c`
- `0x14008b4a4`
- `0x14008d078`
- `0x140097abc`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140084a5e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140084a5e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084d26`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084d26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084d3a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084c0b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084c0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140084a38`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140084a38`

## pseudocode

```c
void __fastcall WFDDeviceHandleReceivedInvitationRequest(
        struct _WFD_ROLE *a1,
        unsigned int a2,
        struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *a3)
{
  char *v3; // r13
  __int64 v5; // r8
  int v7; // r11d
  unsigned int v8; // ecx
  void *pRoleExt; // r12
  int v10; // edx
  __int64 v11; // rax
  _DEVICE_OBJECT *AttachedDevice; // rcx
  unsigned __int8 v13; // r15
  _DWORD *v14; // rax
  __int64 v15; // r8
  char v16; // r12
  const unsigned __int8 *v17; // rdx
  struct _WFD_DEVICE_ROLE *v18; // r11
  unsigned __int8 v19; // al
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned __int8 v22[8]; // [rsp+40h] [rbp-30h] BYREF
  struct _WFD_DEVICE_ROLE *v23; // [rsp+48h] [rbp-28h]
  struct _WFD_PEER_DEVICE *v24; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 v27; // [rsp+C0h] [rbp+50h]
  unsigned __int8 v28; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  v28 = 0;
  v5 = a2;
  v24 = 0;
  v22[0] = 0;
  if ( a3 && (unsigned int)v5 >= 0x28 )
  {
    v7 = *((_DWORD *)a3 + 9);
    if ( !v7 || (v8 = *((_DWORD *)a3 + 8), v8 >= 0x28) )
    {
      v8 = *((_DWORD *)a3 + 8);
      if ( v8 + v7 >= v8 && v8 + v7 <= (unsigned int)v5 )
      {
        pRoleExt = a1->pRoleExt;
        v23 = (struct _WFD_DEVICE_ROLE *)pRoleExt;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          WPP_SF__MAC_DDD(WPP_GLOBAL_Control->AttachedDevice, 247, WPP_GLOBAL_Control, (char *)a3 + 4);
        }
        v10 = *((_DWORD *)a3 + 9);
        if ( v10
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          v11 = *((unsigned int *)a3 + 8);
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          v25[0] = (unsigned __int16)v10;
          v25[1] = (char *)a3 + v11;
          WPP_SF__HEX_(AttachedDevice, 248, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v25);
        }
        v13 = 5;
        if ( (unsigned int)dword_1400AE050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400AE050, 0x200000000000LL) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1400AE050,
            word_1400A54B2);
        *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
        v28 = 1;
        v27 = 0;
        v14 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
        if ( v14 )
        {
          v3 = (char *)(v14 + 4);
          *(_QWORD *)v14 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
          v14[2] = 808679286;
          memset(v14 + 4, 0, 0xB0u);
          if ( (unsigned __int8)WFDValidateIncomingInvitationRequestIEs(
                                  (unsigned __int8 *)a3 + *((unsigned int *)a3 + 8),
                                  *((_DWORD *)a3 + 9)) )
          {
            v16 = 1;
            if ( (int)WFDDeviceCheckDuplicateTransmission(
                        v23,
                        (unsigned __int8 (*)[6])((char *)a3 + 4),
                        3,
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
                  251,
                  WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                  *((unsigned __int8 *)a3 + 16));
              }
              v27 = 1;
              goto LABEL_48;
            }
            if ( !(unsigned int)WFDDeviceFindPeerByMAC(v23, (unsigned __int8 (*)[6])((char *)a3 + 4), &v24) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 252, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                v18 = v23;
              }
              v27 = HandleIncomingInvitationRequestForExistingPeer(
                      v24,
                      v18,
                      a3,
                      (struct _WFD_INVITATION_REQUEST_ATTRIBUTES *)v3,
                      &v28);
              goto LABEL_48;
            }
            if ( (v3[2] & 1) == 0
              || WFDRoleLookupPersistentGroupIdListForDevice(
                   *(struct _WFD_ROLE **)v18,
                   (const unsigned __int8 (*)[6])v17,
                   (const struct _DOT11_WFD_GROUP_ID *)(v3 + 16)) )
            {
              v13 = 1;
              goto LABEL_48;
            }
            v13 = 8;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 250, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
            }
            v13 = 4;
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
               && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 249, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        }
        v16 = 0;
LABEL_48:
        if ( v28 )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)v23 + 149, *((_BYTE *)v23 + 1200));
          v28 = 0;
        }
        v19 = v27;
        if ( !v27 )
        {
          v20 = WFDDeviceSendInvitationFailureResponse(
                  a1->pGenVElan->pAdapt,
                  *((_BYTE *)a3 + 16),
                  *((void **)a3 + 3),
                  (unsigned __int8 (*)[6])((char *)a3 + 4),
                  v13);
          if ( v20
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer)
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 253, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v20);
          }
          v19 = 0;
        }
        if ( v16 && !v19 )
        {
          if ( (unsigned __int8)WFDDeviceIsIncomingPacketTypeFiltered(a1, 2, v15) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 255, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
            }
          }
          else
          {
            v21 = WFDDeviceIndicateIncomingInvitationRequest((struct _WFD_VELAN *)a1->pGenVElan->pVElanExt, a3);
            if ( v21
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer)
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 254, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v21);
            }
          }
        }
        if ( v3 )
        {
          if ( *((_QWORD *)v3 - 2) )
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v3 - 2), v3 - 16);
          else
            ExFreePoolWithTag(v3 - 16, *((_DWORD *)v3 - 2));
        }
        return;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 246, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v8, v7, v5);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && BYTE1(WPP_GLOBAL_Control->Timer)
         && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
  {
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 245, v5, a3);
  }
}

```

## disassembly

```asm
0x1400848d4  mov     [rsp-38h+arg_8], rbx
0x1400848d9  mov     [rsp-38h+arg_0], rcx
0x1400848de  push    rbp
0x1400848df  push    rsi
0x1400848e0  push    rdi
0x1400848e1  push    r12
0x1400848e3  push    r13
0x1400848e5  push    r14
0x1400848e7  push    r15
0x1400848e9  mov     rbp, rsp
0x1400848ec  sub     rsp, 70h
0x1400848f0  xor     r13d, r13d
0x1400848f3  mov     rbx, r8
0x1400848f6  mov     [rbp+arg_18], r13b
0x1400848fa  mov     r8d, edx
0x1400848fd  mov     [rbp+var_20], r13
0x140084901  mov     rdx, rcx
0x140084904  mov     [rbp+var_30], r13b
0x140084908  test    rbx, rbx
0x14008490b  jz      loc_140084D8E
0x140084911  cmp     r8d, 28h ; '('
0x140084915  jb      loc_140084D8E
0x14008491b  mov     r11d, [rbx+24h]
0x14008491f  test    r11d, r11d
0x140084922  jz      short loc_140084930
0x140084924  mov     ecx, [rbx+20h]
0x140084927  cmp     ecx, 28h ; '('
0x14008492a  jb      loc_140084D48
0x140084930  mov     ecx, [rbx+20h]
0x140084933  lea     eax, [rcx+r11]
0x140084937  cmp     eax, ecx
0x140084939  jb      loc_140084D48
0x14008493f  cmp     eax, r8d
0x140084942  ja      loc_140084D48
0x140084948  mov     r12, [rdx+0B8h]
0x14008494f  mov     [rbp+var_28], r12
0x140084953  mov     r8, cs:WPP_GLOBAL_Control
0x14008495a  lea     rsi, WPP_GLOBAL_Control
0x140084961  cmp     r8, rsi
0x140084964  jz      short loc_140084998
0x140084966  cmp     byte ptr [r8+29h], 3
0x14008496b  jb      short loc_140084998
0x14008496d  bt      dword ptr [r8+2Ch], 15h
0x140084973  jnb     short loc_140084998
0x140084975  movzx   eax, byte ptr [rbx+10h]
0x140084979  lea     r9, [rbx+4]
0x14008497d  mov     [rsp+70h+var_40], r11d
0x140084982  mov     edx, 0F7h
0x140084987  mov     [rsp+70h+var_48], ecx
0x14008498b  mov     rcx, [r8+18h]
0x14008498f  mov     dword ptr [rsp+70h+var_50], eax
0x140084993  call    WPP_SF__MAC_DDD
0x140084998  mov     edx, [rbx+24h]
0x14008499b  lea     r14, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400849a2  test    edx, edx
0x1400849a4  jz      short loc_1400849F2
0x1400849a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400849ad  cmp     rcx, rsi
0x1400849b0  jz      short loc_1400849F2
0x1400849b2  cmp     byte ptr [rcx+29h], 3
0x1400849b6  jb      short loc_1400849F2
0x1400849b8  bt      dword ptr [rcx+2Ch], 15h
0x1400849bd  jnb     short loc_1400849F2
0x1400849bf  mov     eax, [rbx+20h]
0x1400849c2  lea     r9, [rbp+var_10]
0x1400849c6  mov     rcx, [rcx+18h]
0x1400849ca  xorps   xmm0, xmm0
0x1400849cd  movups  [rbp+var_10], xmm0
0x1400849d1  mov     word ptr [rbp+var_10], dx
0x1400849d5  add     rax, rbx
0x1400849d8  mov     qword ptr [rbp+var_10+8], rax
0x1400849dc  mov     edx, 0F8h
0x1400849e1  movaps  xmm0, [rbp+var_10]
0x1400849e5  mov     r8, r14
0x1400849e8  movdqa  [rbp+var_10], xmm0
0x1400849ed  call    WPP_SF__HEX_
0x1400849f2  mov     eax, cs:dword_1400AE050
0x1400849f8  mov     r15d, 5
0x1400849fe  cmp     eax, r15d
0x140084a01  jbe     short loc_140084A30
0x140084a03  mov     rdx, 200000000000h
0x140084a0d  lea     rcx, dword_1400AE050
0x140084a14  call    _tlgKeywordOn
0x140084a19  test    al, al
0x140084a1b  jz      short loc_140084A30
0x140084a1d  lea     rdx, word_1400A54B2
0x140084a24  lea     rcx, dword_1400AE050
0x140084a2b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x140084a30  lea     rcx, [r12+4A8h]; SpinLock
0x140084a38  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140084a3f  nop     dword ptr [rax+rax+00h]
0x140084a44  mov     [r12+4B0h], al
0x140084a4c  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140084a53  mov     rcx, r12; Lookaside
0x140084a56  mov     [rbp+arg_18], 1
0x140084a5a  mov     [rbp+arg_10], r13b
0x140084a5e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140084a65  nop     dword ptr [rax+rax+00h]
0x140084a6a  test    rax, rax
0x140084a6d  jnz     short loc_140084AA1
0x140084a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140084a76  cmp     rcx, rsi
0x140084a79  jz      short loc_140084A99
0x140084a7b  cmp     byte ptr [rcx+29h], 3
0x140084a7f  jb      short loc_140084A99
0x140084a81  bt      dword ptr [rcx+2Ch], 15h
0x140084a86  jnb     short loc_140084A99
0x140084a88  mov     rcx, [rcx+18h]
0x140084a8c  mov     edx, 0F9h
0x140084a91  mov     r8, r14
0x140084a94  call    WPP_SF_
0x140084a99  xor     r12b, r12b
0x140084a9c  jmp     loc_140084BF4
0x140084aa1  lea     r13, [rax+10h]
0x140084aa5  mov     [rax], r12
0x140084aa8  mov     rcx, r13; void *
0x140084aab  mov     dword ptr [rax+8], 30337776h
0x140084ab2  xor     edx, edx; Val
0x140084ab4  mov     r8d, 0B0h; Size
0x140084aba  call    memset
0x140084abf  mov     ecx, [rbx+20h]
0x140084ac2  mov     r8, r13
0x140084ac5  mov     edx, [rbx+24h]; unsigned int
0x140084ac8  add     rcx, rbx; unsigned __int8 *
0x140084acb  call    WFDValidateIncomingInvitationRequestIEs
0x140084ad0  test    al, al
0x140084ad2  jnz     short loc_140084B03
0x140084ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x140084adb  cmp     rcx, rsi
0x140084ade  jz      short loc_140084AFE
0x140084ae0  cmp     byte ptr [rcx+29h], 3
0x140084ae4  jb      short loc_140084AFE
0x140084ae6  bt      dword ptr [rcx+2Ch], 15h
0x140084aeb  jnb     short loc_140084AFE
0x140084aed  mov     rcx, [rcx+18h]
0x140084af1  mov     edx, 0FAh
0x140084af6  mov     r8, r14
0x140084af9  call    WPP_SF_
0x140084afe  mov     r15b, 4
0x140084b01  jmp     short loc_140084A99
0x140084b03  mov     r9b, [rbx+10h]; unsigned __int8
0x140084b07  lea     rcx, [rbp+var_30]
0x140084b0b  mov     [rsp+70h+var_50], rcx; unsigned __int8 *
0x140084b10  lea     rdx, [rbx+4]; unsigned __int8 (*)[6]
0x140084b14  mov     rcx, [rbp+var_28]; struct _WFD_DEVICE_ROLE *
0x140084b18  mov     r8d, 3; enum _WFD_RECEIVED_PACKET_TYPE
0x140084b1e  mov     r12b, 1
0x140084b21  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x140084b26  test    eax, eax
0x140084b28  js      loc_140084BC1
0x140084b2e  cmp     [rbp+var_30], 0
0x140084b32  jnz     loc_140084BC1
0x140084b38  mov     r11, [rbp+var_28]
0x140084b3c  lea     r8, [rbp+var_20]; struct _WFD_PEER_DEVICE **
0x140084b40  mov     rcx, r11; struct _WFD_DEVICE_ROLE *
0x140084b43  lea     rdx, [rbx+4]; unsigned __int8 (*)[6]
0x140084b47  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x140084b4c  test    eax, eax
0x140084b4e  jnz     short loc_140084B9E
0x140084b50  mov     rcx, cs:WPP_GLOBAL_Control
0x140084b57  cmp     rcx, rsi
0x140084b5a  jz      short loc_140084B7E
0x140084b5c  cmp     byte ptr [rcx+29h], 3
0x140084b60  jb      short loc_140084B7E
0x140084b62  bt      dword ptr [rcx+2Ch], 15h
0x140084b67  jnb     short loc_140084B7E
0x140084b69  mov     rcx, [rcx+18h]
0x140084b6d  mov     edx, 0FCh
0x140084b72  mov     r8, r14
0x140084b75  call    WPP_SF_
0x140084b7a  mov     r11, [rbp+var_28]
0x140084b7e  mov     rcx, [rbp+var_20]; struct _WFD_PEER_DEVICE *
0x140084b82  lea     rax, [rbp+arg_18]
0x140084b86  mov     r9, r13; struct _WFD_INVITATION_REQUEST_ATTRIBUTES *
0x140084b89  mov     [rsp+70h+var_50], rax; unsigned __int8 *
0x140084b8e  mov     r8, rbx; struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *
0x140084b91  mov     rdx, r11; struct _WFD_DEVICE_ROLE *
0x140084b94  call    ?HandleIncomingInvitationRequestForExistingPeer@@YAEPEAU_WFD_PEER_DEVICE@@PEAU_WFD_DEVICE_ROLE@@PEAU_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS@@PEAU_WFD_INVITATION_REQUEST_ATTRIBUTES@@PEAE@Z; HandleIncomingInvitationRequestForExistingPeer(_WFD_PEER_DEVICE *,_WFD_DEVICE_ROLE *,_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *,_WFD_INVITATION_REQUEST_ATTRIBUTES *,uchar *)
0x140084b99  mov     [rbp+arg_10], al
0x140084b9c  jmp     short loc_140084BF4
0x140084b9e  test    [r13+2], r12b
0x140084ba2  jz      short loc_140084BBC
0x140084ba4  mov     rcx, [r11]; struct _WFD_ROLE *
0x140084ba7  lea     r8, [r13+10h]; struct _DOT11_WFD_GROUP_ID *
0x140084bab  call    ?WFDRoleLookupPersistentGroupIdListForDevice@@YAEPEAU_WFD_ROLE@@PEAY05$$CBEPEBU_DOT11_WFD_GROUP_ID@@@Z; WFDRoleLookupPersistentGroupIdListForDevice(_WFD_ROLE *,uchar const (*)[6],_DOT11_WFD_GROUP_ID const *)
0x140084bb0  test    al, al
0x140084bb2  jnz     short loc_140084BBC
0x140084bb4  mov     r15b, 8
0x140084bb7  jmp     loc_140084A99
0x140084bbc  mov     r15b, r12b
0x140084bbf  jmp     short loc_140084BF4
0x140084bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140084bc8  cmp     rcx, rsi
0x140084bcb  jz      short loc_140084BF0
0x140084bcd  cmp     byte ptr [rcx+29h], 3
0x140084bd1  jb      short loc_140084BF0
0x140084bd3  bt      dword ptr [rcx+2Ch], 15h
0x140084bd8  jnb     short loc_140084BF0
0x140084bda  movzx   r9d, byte ptr [rbx+10h]
0x140084bdf  mov     edx, 0FBh
0x140084be4  mov     rcx, [rcx+18h]
0x140084be8  mov     r8, r14
0x140084beb  call    WPP_SF_d
0x140084bf0  mov     [rbp+arg_10], r12b
0x140084bf4  cmp     [rbp+arg_18], 0
0x140084bf8  jz      short loc_140084C1B
0x140084bfa  mov     rax, [rbp+var_28]
0x140084bfe  mov     dl, [rax+4B0h]; NewIrql
0x140084c04  lea     rcx, [rax+4A8h]; SpinLock
0x140084c0b  call    cs:__imp_KeReleaseSpinLock
0x140084c12  nop     dword ptr [rax+rax+00h]
0x140084c17  mov     [rbp+arg_18], 0
0x140084c1b  mov     al, [rbp+arg_10]
0x140084c1e  test    al, al
0x140084c20  jnz     short loc_140084C76
0x140084c22  mov     rcx, [rbp+arg_0]
0x140084c26  lea     r9, [rbx+4]; unsigned __int8 (*)[6]
0x140084c2a  mov     r8, [rbx+18h]; void *
0x140084c2e  mov     dl, [rbx+10h]; unsigned __int8
0x140084c31  mov     byte ptr [rsp+70h+var_50], r15b; unsigned __int8
0x140084c36  mov     rcx, [rcx]
0x140084c39  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140084c3d  call    ?WFDDeviceSendInvitationFailureResponse@@YAHPEAU_ADAPT@@EPEAXPEAY05EE@Z; WFDDeviceSendInvitationFailureResponse(_ADAPT *,uchar,void *,uchar (*)[6],uchar)
0x140084c42  test    eax, eax
0x140084c44  jz      short loc_140084C73
0x140084c46  mov     rcx, cs:WPP_GLOBAL_Control
0x140084c4d  cmp     rcx, rsi
0x140084c50  jz      short loc_140084C73
0x140084c52  cmp     byte ptr [rcx+29h], 1
0x140084c56  jb      short loc_140084C73
0x140084c58  bt      dword ptr [rcx+2Ch], 15h
0x140084c5d  jnb     short loc_140084C73
0x140084c5f  mov     rcx, [rcx+18h]
0x140084c63  mov     edx, 0FDh
0x140084c68  mov     r9d, eax
0x140084c6b  mov     r8, r14
0x140084c6e  call    WPP_SF_d
0x140084c73  mov     al, [rbp+arg_10]
0x140084c76  test    r12b, r12b
0x140084c79  jz      loc_140084D0B
0x140084c7f  test    al, al
0x140084c81  jnz     loc_140084D0B
0x140084c87  mov     r15, [rbp+arg_0]
0x140084c8b  mov     edx, 2
0x140084c90  mov     rcx, r15
0x140084c93  call    ?WFDDeviceIsIncomingPacketTypeFiltered@@YAEPEAU_WFD_ROLE@@W4_WFD_INCOMING_PACKET_TYPE@@@Z; WFDDeviceIsIncomingPacketTypeFiltered(_WFD_ROLE *,_WFD_INCOMING_PACKET_TYPE)
0x140084c98  test    al, al
0x140084c9a  jnz     short loc_140084CE1
0x140084c9c  mov     rcx, [r15]
0x140084c9f  mov     rdx, rbx; struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *
0x140084ca2  mov     rcx, [rcx+1F68h]; struct _WFD_VELAN *
0x140084ca9  call    ?WFDDeviceIndicateIncomingInvitationRequest@@YAJPEAU_WFD_VELAN@@PEAU_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS@@@Z; WFDDeviceIndicateIncomingInvitationRequest(_WFD_VELAN *,_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *)
0x140084cae  test    eax, eax
0x140084cb0  jz      short loc_140084D0B
0x140084cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140084cb9  cmp     rcx, rsi
0x140084cbc  jz      short loc_140084D0B
0x140084cbe  cmp     byte ptr [rcx+29h], 1
0x140084cc2  jb      short loc_140084D0B
0x140084cc4  bt      dword ptr [rcx+2Ch], 15h
0x140084cc9  jnb     short loc_140084D0B
0x140084ccb  mov     rcx, [rcx+18h]
0x140084ccf  mov     edx, 0FEh
0x140084cd4  mov     r9d, eax
0x140084cd7  mov     r8, r14
0x140084cda  call    WPP_SF_d
0x140084cdf  jmp     short loc_140084D0B
0x140084ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x140084ce8  cmp     rcx, rsi
0x140084ceb  jz      short loc_140084D0B
0x140084ced  cmp     byte ptr [rcx+29h], 3
0x140084cf1  jb      short loc_140084D0B
0x140084cf3  bt      dword ptr [rcx+2Ch], 15h
0x140084cf8  jnb     short loc_140084D0B
0x140084cfa  mov     rcx, [rcx+18h]
0x140084cfe  mov     edx, 0FFh
0x140084d03  mov     r8, r14
0x140084d06  call    WPP_SF_
0x140084d0b  test    r13, r13
0x140084d0e  jz      loc_140084DC4
0x140084d14  lea     rcx, [r13-10h]; P
0x140084d18  mov     rax, [rcx]
0x140084d1b  test    rax, rax
0x140084d1e  jz      short loc_140084D37
0x140084d20  mov     rdx, rcx; Entry
0x140084d23  mov     rcx, rax; Lookaside
0x140084d26  call    cs:__imp_ExFreeToNPagedLookasideList
0x140084d2d  nop     dword ptr [rax+rax+00h]
0x140084d32  jmp     loc_140084DC4
0x140084d37  mov     edx, [rcx+8]; Tag
0x140084d3a  call    cs:__imp_ExFreePoolWithTag
0x140084d41  nop     dword ptr [rax+rax+00h]
0x140084d46  jmp     short loc_140084DC4
0x140084d48  mov     r10, cs:WPP_GLOBAL_Control
0x140084d4f  lea     rsi, WPP_GLOBAL_Control
0x140084d56  cmp     r10, rsi
0x140084d59  jz      short loc_140084DC4
0x140084d5b  cmp     byte ptr [r10+29h], 1
0x140084d60  jb      short loc_140084DC4
0x140084d62  bt      dword ptr [r10+2Ch], 15h
  ... truncated ...
```

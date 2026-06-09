# WFDDeviceHandleReceivedInvitationRequest(_WFD_ROLE *,ulong,_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *)

- ea: `0x140086104`
- end: `0x14008660d`
- name: `?WFDDeviceHandleReceivedInvitationRequest@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS@@@Z`
- size: `1289`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007dfe0`

## callees

- `0x140001d94`
- `0x14000d21c`
- `0x14000d2b0`
- `0x140020dc0`
- `0x140024370`
- `0x14002f44c`
- `0x140030244`
- `0x14007cd90`
- `0x14007f67c`
- `0x140080a84`
- `0x140080dfc`
- `0x140086104`
- `0x14008a0d8`
- `0x14008a13c`
- `0x14008ccd4`
- `0x14008e8a8`
- `0x14009929c`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008628e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008628e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086556`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086556`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008656a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008656a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008643b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008643b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140086268`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140086268`

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
  char v15; // r12
  const unsigned __int8 *v16; // rdx
  struct _WFD_DEVICE_ROLE *v17; // r11
  unsigned __int8 v18; // al
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned __int8 v21[8]; // [rsp+40h] [rbp-30h] BYREF
  struct _WFD_DEVICE_ROLE *v22; // [rsp+48h] [rbp-28h]
  struct _WFD_PEER_DEVICE *v23; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v24[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 v26; // [rsp+C0h] [rbp+50h]
  unsigned __int8 v27; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  v27 = 0;
  v5 = a2;
  v23 = 0;
  v21[0] = 0;
  if ( a3 && (unsigned int)v5 >= 0x28 )
  {
    v7 = *((_DWORD *)a3 + 9);
    if ( !v7 || (v8 = *((_DWORD *)a3 + 8), v8 >= 0x28) )
    {
      v8 = *((_DWORD *)a3 + 8);
      if ( v8 + v7 >= v8 && v8 + v7 <= (unsigned int)v5 )
      {
        pRoleExt = a1->pRoleExt;
        v22 = (struct _WFD_DEVICE_ROLE *)pRoleExt;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          WPP_SF__MAC_DDD(
            WPP_GLOBAL_Control->AttachedDevice,
            247,
            WPP_GLOBAL_Control,
            (char *)a3 + 4,
            *((unsigned __int8 *)a3 + 16),
            v8,
            v7);
        }
        v10 = *((_DWORD *)a3 + 9);
        if ( v10
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          v11 = *((unsigned int *)a3 + 8);
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          v24[0] = (unsigned __int16)v10;
          v24[1] = (char *)a3 + v11;
          WPP_SF__HEX_(AttachedDevice, 248, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v24);
        }
        v13 = 5;
        if ( (unsigned int)dword_1400B1050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400B1050, 0x200000000000LL) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1400B1050,
            word_1400A75B2);
        *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
        v27 = 1;
        v26 = 0;
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
            v15 = 1;
            if ( (int)WFDDeviceCheckDuplicateTransmission(
                        v22,
                        (unsigned __int8 (*)[6])((char *)a3 + 4),
                        WfdReceivedPacketTypeInviteRequest,
                        *((_BYTE *)a3 + 16),
                        v21) < 0
              || v21[0] )
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
              v26 = 1;
              goto LABEL_48;
            }
            if ( !(unsigned int)WFDDeviceFindPeerByMAC(v22, (unsigned __int8 (*)[6])((char *)a3 + 4), &v23) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 252, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                v17 = v22;
              }
              v26 = HandleIncomingInvitationRequestForExistingPeer(
                      v23,
                      v17,
                      a3,
                      (struct _WFD_INVITATION_REQUEST_ATTRIBUTES *)v3,
                      &v27);
              goto LABEL_48;
            }
            if ( (v3[2] & 1) == 0
              || WFDRoleLookupPersistentGroupIdListForDevice(
                   *(struct _WFD_ROLE **)v17,
                   (const unsigned __int8 (*)[6])v16,
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
        v15 = 0;
LABEL_48:
        if ( v27 )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)v22 + 149, *((_BYTE *)v22 + 1200));
          v27 = 0;
        }
        v18 = v26;
        if ( !v26 )
        {
          v19 = WFDDeviceSendInvitationFailureResponse(
                  a1->pGenVElan->pAdapt,
                  *((_BYTE *)a3 + 16),
                  *((void **)a3 + 3),
                  (unsigned __int8 (*)[6])((char *)a3 + 4),
                  v13);
          if ( v19
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer)
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 253, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v19);
          }
          v18 = 0;
        }
        if ( v15 && !v18 )
        {
          if ( (unsigned __int8)WFDDeviceIsIncomingPacketTypeFiltered(a1, 2) )
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
            v20 = WFDDeviceIndicateIncomingInvitationRequest((struct _WFD_VELAN *)a1->pGenVElan->pVElanExt, a3);
            if ( v20
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer)
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 254, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v20);
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
0x140086104  mov     [rsp-38h+arg_8], rbx
0x140086109  mov     [rsp-38h+arg_0], rcx
0x14008610e  push    rbp
0x14008610f  push    rsi
0x140086110  push    rdi
0x140086111  push    r12
0x140086113  push    r13
0x140086115  push    r14
0x140086117  push    r15
0x140086119  mov     rbp, rsp
0x14008611c  sub     rsp, 70h
0x140086120  xor     r13d, r13d
0x140086123  mov     rbx, r8
0x140086126  mov     [rbp+arg_18], r13b
0x14008612a  mov     r8d, edx
0x14008612d  mov     [rbp+var_20], r13
0x140086131  mov     rdx, rcx
0x140086134  mov     [rbp+var_30], r13b
0x140086138  test    rbx, rbx
0x14008613b  jz      loc_1400865BE
0x140086141  cmp     r8d, 28h ; '('
0x140086145  jb      loc_1400865BE
0x14008614b  mov     r11d, [rbx+24h]
0x14008614f  test    r11d, r11d
0x140086152  jz      short loc_140086160
0x140086154  mov     ecx, [rbx+20h]
0x140086157  cmp     ecx, 28h ; '('
0x14008615a  jb      loc_140086578
0x140086160  mov     ecx, [rbx+20h]
0x140086163  lea     eax, [rcx+r11]
0x140086167  cmp     eax, ecx
0x140086169  jb      loc_140086578
0x14008616f  cmp     eax, r8d
0x140086172  ja      loc_140086578
0x140086178  mov     r12, [rdx+0B8h]
0x14008617f  mov     [rbp+var_28], r12
0x140086183  mov     r8, cs:WPP_GLOBAL_Control
0x14008618a  lea     rsi, WPP_GLOBAL_Control
0x140086191  cmp     r8, rsi
0x140086194  jz      short loc_1400861C8
0x140086196  cmp     byte ptr [r8+29h], 3
0x14008619b  jb      short loc_1400861C8
0x14008619d  bt      dword ptr [r8+2Ch], 15h
0x1400861a3  jnb     short loc_1400861C8
0x1400861a5  movzx   eax, byte ptr [rbx+10h]
0x1400861a9  lea     r9, [rbx+4]
0x1400861ad  mov     [rsp+70h+var_40], r11d
0x1400861b2  mov     edx, 0F7h
0x1400861b7  mov     [rsp+70h+var_48], ecx
0x1400861bb  mov     rcx, [r8+18h]
0x1400861bf  mov     dword ptr [rsp+70h+var_50], eax
0x1400861c3  call    WPP_SF__MAC_DDD
0x1400861c8  mov     edx, [rbx+24h]
0x1400861cb  lea     r14, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400861d2  test    edx, edx
0x1400861d4  jz      short loc_140086222
0x1400861d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400861dd  cmp     rcx, rsi
0x1400861e0  jz      short loc_140086222
0x1400861e2  cmp     byte ptr [rcx+29h], 3
0x1400861e6  jb      short loc_140086222
0x1400861e8  bt      dword ptr [rcx+2Ch], 15h
0x1400861ed  jnb     short loc_140086222
0x1400861ef  mov     eax, [rbx+20h]
0x1400861f2  lea     r9, [rbp+var_10]
0x1400861f6  mov     rcx, [rcx+18h]
0x1400861fa  xorps   xmm0, xmm0
0x1400861fd  movups  [rbp+var_10], xmm0
0x140086201  mov     word ptr [rbp+var_10], dx
0x140086205  add     rax, rbx
0x140086208  mov     qword ptr [rbp+var_10+8], rax
0x14008620c  mov     edx, 0F8h
0x140086211  movaps  xmm0, [rbp+var_10]
0x140086215  mov     r8, r14
0x140086218  movdqa  [rbp+var_10], xmm0
0x14008621d  call    WPP_SF__HEX_
0x140086222  mov     eax, cs:dword_1400B1050
0x140086228  mov     r15d, 5
0x14008622e  cmp     eax, r15d
0x140086231  jbe     short loc_140086260
0x140086233  mov     rdx, 200000000000h
0x14008623d  lea     rcx, dword_1400B1050
0x140086244  call    _tlgKeywordOn
0x140086249  test    al, al
0x14008624b  jz      short loc_140086260
0x14008624d  lea     rdx, word_1400A75B2
0x140086254  lea     rcx, dword_1400B1050
0x14008625b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x140086260  lea     rcx, [r12+4A8h]; SpinLock
0x140086268  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008626f  nop     dword ptr [rax+rax+00h]
0x140086274  mov     [r12+4B0h], al
0x14008627c  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140086283  mov     rcx, r12; Lookaside
0x140086286  mov     [rbp+arg_18], 1
0x14008628a  mov     [rbp+arg_10], r13b
0x14008628e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140086295  nop     dword ptr [rax+rax+00h]
0x14008629a  test    rax, rax
0x14008629d  jnz     short loc_1400862D1
0x14008629f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400862a6  cmp     rcx, rsi
0x1400862a9  jz      short loc_1400862C9
0x1400862ab  cmp     byte ptr [rcx+29h], 3
0x1400862af  jb      short loc_1400862C9
0x1400862b1  bt      dword ptr [rcx+2Ch], 15h
0x1400862b6  jnb     short loc_1400862C9
0x1400862b8  mov     rcx, [rcx+18h]
0x1400862bc  mov     edx, 0F9h
0x1400862c1  mov     r8, r14
0x1400862c4  call    WPP_SF_
0x1400862c9  xor     r12b, r12b
0x1400862cc  jmp     loc_140086424
0x1400862d1  lea     r13, [rax+10h]
0x1400862d5  mov     [rax], r12
0x1400862d8  mov     rcx, r13; void *
0x1400862db  mov     dword ptr [rax+8], 30337776h
0x1400862e2  xor     edx, edx; Val
0x1400862e4  mov     r8d, 0B0h; Size
0x1400862ea  call    memset
0x1400862ef  mov     ecx, [rbx+20h]
0x1400862f2  mov     r8, r13
0x1400862f5  mov     edx, [rbx+24h]; unsigned int
0x1400862f8  add     rcx, rbx; unsigned __int8 *
0x1400862fb  call    WFDValidateIncomingInvitationRequestIEs
0x140086300  test    al, al
0x140086302  jnz     short loc_140086333
0x140086304  mov     rcx, cs:WPP_GLOBAL_Control
0x14008630b  cmp     rcx, rsi
0x14008630e  jz      short loc_14008632E
0x140086310  cmp     byte ptr [rcx+29h], 3
0x140086314  jb      short loc_14008632E
0x140086316  bt      dword ptr [rcx+2Ch], 15h
0x14008631b  jnb     short loc_14008632E
0x14008631d  mov     rcx, [rcx+18h]
0x140086321  mov     edx, 0FAh
0x140086326  mov     r8, r14
0x140086329  call    WPP_SF_
0x14008632e  mov     r15b, 4
0x140086331  jmp     short loc_1400862C9
0x140086333  mov     r9b, [rbx+10h]; unsigned __int8
0x140086337  lea     rcx, [rbp+var_30]
0x14008633b  mov     [rsp+70h+var_50], rcx; unsigned __int8 *
0x140086340  lea     rdx, [rbx+4]; unsigned __int8 (*)[6]
0x140086344  mov     rcx, [rbp+var_28]; struct _WFD_DEVICE_ROLE *
0x140086348  mov     r8d, 3; enum _WFD_RECEIVED_PACKET_TYPE
0x14008634e  mov     r12b, 1
0x140086351  call    ?WFDDeviceCheckDuplicateTransmission@@YAJPEAU_WFD_DEVICE_ROLE@@PEAY05EW4_WFD_RECEIVED_PACKET_TYPE@@EPEAE@Z; WFDDeviceCheckDuplicateTransmission(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_RECEIVED_PACKET_TYPE,uchar,uchar *)
0x140086356  test    eax, eax
0x140086358  js      loc_1400863F1
0x14008635e  cmp     [rbp+var_30], 0
0x140086362  jnz     loc_1400863F1
0x140086368  mov     r11, [rbp+var_28]
0x14008636c  lea     r8, [rbp+var_20]; struct _WFD_PEER_DEVICE **
0x140086370  mov     rcx, r11; struct _WFD_DEVICE_ROLE *
0x140086373  lea     rdx, [rbx+4]; unsigned __int8 (*)[6]
0x140086377  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x14008637c  test    eax, eax
0x14008637e  jnz     short loc_1400863CE
0x140086380  mov     rcx, cs:WPP_GLOBAL_Control
0x140086387  cmp     rcx, rsi
0x14008638a  jz      short loc_1400863AE
0x14008638c  cmp     byte ptr [rcx+29h], 3
0x140086390  jb      short loc_1400863AE
0x140086392  bt      dword ptr [rcx+2Ch], 15h
0x140086397  jnb     short loc_1400863AE
0x140086399  mov     rcx, [rcx+18h]
0x14008639d  mov     edx, 0FCh
0x1400863a2  mov     r8, r14
0x1400863a5  call    WPP_SF_
0x1400863aa  mov     r11, [rbp+var_28]
0x1400863ae  mov     rcx, [rbp+var_20]; struct _WFD_PEER_DEVICE *
0x1400863b2  lea     rax, [rbp+arg_18]
0x1400863b6  mov     r9, r13; struct _WFD_INVITATION_REQUEST_ATTRIBUTES *
0x1400863b9  mov     [rsp+70h+var_50], rax; unsigned __int8 *
0x1400863be  mov     r8, rbx; struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *
0x1400863c1  mov     rdx, r11; struct _WFD_DEVICE_ROLE *
0x1400863c4  call    ?HandleIncomingInvitationRequestForExistingPeer@@YAEPEAU_WFD_PEER_DEVICE@@PEAU_WFD_DEVICE_ROLE@@PEAU_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS@@PEAU_WFD_INVITATION_REQUEST_ATTRIBUTES@@PEAE@Z; HandleIncomingInvitationRequestForExistingPeer(_WFD_PEER_DEVICE *,_WFD_DEVICE_ROLE *,_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *,_WFD_INVITATION_REQUEST_ATTRIBUTES *,uchar *)
0x1400863c9  mov     [rbp+arg_10], al
0x1400863cc  jmp     short loc_140086424
0x1400863ce  test    [r13+2], r12b
0x1400863d2  jz      short loc_1400863EC
0x1400863d4  mov     rcx, [r11]; struct _WFD_ROLE *
0x1400863d7  lea     r8, [r13+10h]; struct _DOT11_WFD_GROUP_ID *
0x1400863db  call    ?WFDRoleLookupPersistentGroupIdListForDevice@@YAEPEAU_WFD_ROLE@@PEAY05$$CBEPEBU_DOT11_WFD_GROUP_ID@@@Z; WFDRoleLookupPersistentGroupIdListForDevice(_WFD_ROLE *,uchar const (*)[6],_DOT11_WFD_GROUP_ID const *)
0x1400863e0  test    al, al
0x1400863e2  jnz     short loc_1400863EC
0x1400863e4  mov     r15b, 8
0x1400863e7  jmp     loc_1400862C9
0x1400863ec  mov     r15b, r12b
0x1400863ef  jmp     short loc_140086424
0x1400863f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400863f8  cmp     rcx, rsi
0x1400863fb  jz      short loc_140086420
0x1400863fd  cmp     byte ptr [rcx+29h], 3
0x140086401  jb      short loc_140086420
0x140086403  bt      dword ptr [rcx+2Ch], 15h
0x140086408  jnb     short loc_140086420
0x14008640a  movzx   r9d, byte ptr [rbx+10h]
0x14008640f  mov     edx, 0FBh
0x140086414  mov     rcx, [rcx+18h]
0x140086418  mov     r8, r14
0x14008641b  call    WPP_SF_d
0x140086420  mov     [rbp+arg_10], r12b
0x140086424  cmp     [rbp+arg_18], 0
0x140086428  jz      short loc_14008644B
0x14008642a  mov     rax, [rbp+var_28]
0x14008642e  mov     dl, [rax+4B0h]; NewIrql
0x140086434  lea     rcx, [rax+4A8h]; SpinLock
0x14008643b  call    cs:__imp_KeReleaseSpinLock
0x140086442  nop     dword ptr [rax+rax+00h]
0x140086447  mov     [rbp+arg_18], 0
0x14008644b  mov     al, [rbp+arg_10]
0x14008644e  test    al, al
0x140086450  jnz     short loc_1400864A6
0x140086452  mov     rcx, [rbp+arg_0]
0x140086456  lea     r9, [rbx+4]; unsigned __int8 (*)[6]
0x14008645a  mov     r8, [rbx+18h]; void *
0x14008645e  mov     dl, [rbx+10h]; unsigned __int8
0x140086461  mov     byte ptr [rsp+70h+var_50], r15b; unsigned __int8
0x140086466  mov     rcx, [rcx]
0x140086469  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14008646d  call    ?WFDDeviceSendInvitationFailureResponse@@YAHPEAU_ADAPT@@EPEAXPEAY05EE@Z; WFDDeviceSendInvitationFailureResponse(_ADAPT *,uchar,void *,uchar (*)[6],uchar)
0x140086472  test    eax, eax
0x140086474  jz      short loc_1400864A3
0x140086476  mov     rcx, cs:WPP_GLOBAL_Control
0x14008647d  cmp     rcx, rsi
0x140086480  jz      short loc_1400864A3
0x140086482  cmp     byte ptr [rcx+29h], 1
0x140086486  jb      short loc_1400864A3
0x140086488  bt      dword ptr [rcx+2Ch], 15h
0x14008648d  jnb     short loc_1400864A3
0x14008648f  mov     rcx, [rcx+18h]
0x140086493  mov     edx, 0FDh
0x140086498  mov     r9d, eax
0x14008649b  mov     r8, r14
0x14008649e  call    WPP_SF_d
0x1400864a3  mov     al, [rbp+arg_10]
0x1400864a6  test    r12b, r12b
0x1400864a9  jz      loc_14008653B
0x1400864af  test    al, al
0x1400864b1  jnz     loc_14008653B
0x1400864b7  mov     r15, [rbp+arg_0]
0x1400864bb  mov     edx, 2
0x1400864c0  mov     rcx, r15
0x1400864c3  call    ?WFDDeviceIsIncomingPacketTypeFiltered@@YAEPEAU_WFD_ROLE@@W4_WFD_INCOMING_PACKET_TYPE@@@Z; WFDDeviceIsIncomingPacketTypeFiltered(_WFD_ROLE *,_WFD_INCOMING_PACKET_TYPE)
0x1400864c8  test    al, al
0x1400864ca  jnz     short loc_140086511
0x1400864cc  mov     rcx, [r15]
0x1400864cf  mov     rdx, rbx; struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *
0x1400864d2  mov     rcx, [rcx+1F68h]; struct _WFD_VELAN *
0x1400864d9  call    ?WFDDeviceIndicateIncomingInvitationRequest@@YAJPEAU_WFD_VELAN@@PEAU_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS@@@Z; WFDDeviceIndicateIncomingInvitationRequest(_WFD_VELAN *,_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS *)
0x1400864de  test    eax, eax
0x1400864e0  jz      short loc_14008653B
0x1400864e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400864e9  cmp     rcx, rsi
0x1400864ec  jz      short loc_14008653B
0x1400864ee  cmp     byte ptr [rcx+29h], 1
0x1400864f2  jb      short loc_14008653B
0x1400864f4  bt      dword ptr [rcx+2Ch], 15h
0x1400864f9  jnb     short loc_14008653B
0x1400864fb  mov     rcx, [rcx+18h]
0x1400864ff  mov     edx, 0FEh
0x140086504  mov     r9d, eax
0x140086507  mov     r8, r14
0x14008650a  call    WPP_SF_d
0x14008650f  jmp     short loc_14008653B
0x140086511  mov     rcx, cs:WPP_GLOBAL_Control
0x140086518  cmp     rcx, rsi
0x14008651b  jz      short loc_14008653B
0x14008651d  cmp     byte ptr [rcx+29h], 3
0x140086521  jb      short loc_14008653B
0x140086523  bt      dword ptr [rcx+2Ch], 15h
0x140086528  jnb     short loc_14008653B
0x14008652a  mov     rcx, [rcx+18h]
0x14008652e  mov     edx, 0FFh
0x140086533  mov     r8, r14
0x140086536  call    WPP_SF_
0x14008653b  test    r13, r13
0x14008653e  jz      loc_1400865F4
0x140086544  lea     rcx, [r13-10h]; P
0x140086548  mov     rax, [rcx]
0x14008654b  test    rax, rax
0x14008654e  jz      short loc_140086567
0x140086550  mov     rdx, rcx; Entry
0x140086553  mov     rcx, rax; Lookaside
0x140086556  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008655d  nop     dword ptr [rax+rax+00h]
0x140086562  jmp     loc_1400865F4
0x140086567  mov     edx, [rcx+8]; Tag
0x14008656a  call    cs:__imp_ExFreePoolWithTag
0x140086571  nop     dword ptr [rax+rax+00h]
0x140086576  jmp     short loc_1400865F4
0x140086578  mov     r10, cs:WPP_GLOBAL_Control
0x14008657f  lea     rsi, WPP_GLOBAL_Control
0x140086586  cmp     r10, rsi
0x140086589  jz      short loc_1400865F4
0x14008658b  cmp     byte ptr [r10+29h], 1
0x140086590  jb      short loc_1400865F4
0x140086592  bt      dword ptr [r10+2Ch], 15h
  ... truncated ...
```

# WFDRoleDeInitialize(_WFD_ROLE *)

- ea: `0x14007b664`
- end: `0x14007b8b4`
- name: `?WFDRoleDeInitialize@@YAXPEAU_WFD_ROLE@@@Z`
- size: `592`
- prototype: `void __fastcall(struct _WFD_ROLE *)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1400210c8`
- `0x140066160`
- `0x140072280`
- `0x14007c194`
- `0x14007f588`

## callees

- `0x14000d21c`
- `0x140022dd4`
- `0x14003af50`
- `0x140046494`
- `0x14007b664`
- `0x14008efe4`
- `0x14008f14c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b76e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b7b4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b7f3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b832`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b865`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b76e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b7b4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b7f3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b832`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b865`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b77f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b7c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b804`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b843`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b876`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b77f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b7c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b804`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b843`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b876`
- `NDIS!NdisFreeRWLock` at `0x14007b73a`
- `NDIS!NdisFreeRWLock` at `0x14007b73a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007b6c5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007b6c5`
- `NDIS!NdisReleaseRWLock` at `0x14007b6ed`
- `NDIS!NdisReleaseRWLock` at `0x14007b6ed`

## pseudocode

```c
void __fastcall WFDRoleDeInitialize(struct _WFD_ROLE *a1)
{
  struct _WFD_DEVICE_ROLE *pRoleExt; // rcx
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  _DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *pFrameIEList; // rcx
  _DOT11_WFD_MANAGEMENT_FRAME_IE *v6; // rcx
  _WFDSVC_SERVICE_ADVERTISEMENT_ENTRY *pCachedServiceAdvertisementList; // rcx
  _DOT11_WFD_MANAGEMENT_FRAME_IE *v8; // rcx
  ULONG *v9; // rcx
  _DOT11_WFD_PERSISTENT_GROUP_ID_LIST *pCachedPersistentGroupIdList; // rcx
  ULONG *v11; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
  if ( a1 )
  {
    NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
    Dot11RsnaConfigureAddressRequestKDE(a1->pGenVElan, 0, 0);
    NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
    pRoleExt = (struct _WFD_DEVICE_ROLE *)a1->pRoleExt;
    if ( pRoleExt )
    {
      switch ( a1->RoleType )
      {
        case WFD_ROLE_TYPE_DEVICE:
          WFDDeviceDeInitialize(pRoleExt);
          break;
        case WFD_ROLE_TYPE_GROUP_OWNER:
          WFDGODeInitialize(pRoleExt);
          break;
        case WFD_ROLE_TYPE_CLIENT:
          WFDClientDeInitialize(pRoleExt);
          break;
      }
      a1->pRoleExt = 0;
    }
    pRWLock = a1->pRWLock;
    if ( pRWLock )
    {
      NdisFreeRWLock(pRWLock);
      a1->pRWLock = 0;
    }
    IsEnabledDeviceUsageNoInline = Feature_57277348__private_IsEnabledDeviceUsageNoInline();
    pFrameIEList = a1->pFrameIEList;
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( pFrameIEList )
      {
        v6 = &pFrameIEList[-1].Frames[10];
        if ( *v6 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, v6);
        else
          ExFreePoolWithTag(v6, v6[1].uIEsOffset);
        a1->pFrameIEList = 0;
      }
      a1->cbFrameIEList = 0;
      pCachedServiceAdvertisementList = a1->pCachedServiceAdvertisementList;
      if ( !pCachedServiceAdvertisementList )
        goto LABEL_32;
    }
    else
    {
      if ( pFrameIEList )
      {
        v8 = &pFrameIEList[-1].Frames[10];
        if ( *v8 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v8, v8);
        else
          ExFreePoolWithTag(v8, v8[1].uIEsOffset);
        a1->pFrameIEList = 0;
        a1->cbFrameIEList = 0;
      }
      pCachedServiceAdvertisementList = a1->pCachedServiceAdvertisementList;
      if ( !pCachedServiceAdvertisementList )
        goto LABEL_33;
    }
    v9 = (ULONG *)&pCachedServiceAdvertisementList[-1].SessionInfo.ucSessionInfo[128];
    if ( *(_QWORD *)v9 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v9, v9);
    else
      ExFreePoolWithTag(v9, v9[2]);
    a1->pCachedServiceAdvertisementList = 0;
LABEL_32:
    a1->uCachedServiceAdvertisementCount = 0;
LABEL_33:
    pCachedPersistentGroupIdList = a1->pCachedPersistentGroupIdList;
    if ( pCachedPersistentGroupIdList )
    {
      v11 = (ULONG *)&pCachedPersistentGroupIdList[-1].GroupList[0].GroupId.SSID.ucSSID[16];
      if ( *(_QWORD *)v11 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v11, v11);
      else
        ExFreePoolWithTag(v11, v11[2]);
      a1->pCachedPersistentGroupIdList = 0;
    }
    if ( *(_QWORD *)&a1[-1].GOGroupID.SSID.ucSSID[24] )
      ExFreeToNPagedLookasideList(
        *(PNPAGED_LOOKASIDE_LIST *)&a1[-1].GOGroupID.SSID.ucSSID[24],
        &a1[-1].GOGroupID.SSID.ucSSID[24]);
    else
      ExFreePoolWithTag(&a1[-1].GOGroupID.SSID.ucSSID[24], (ULONG)a1[-1].pRoleExt);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
}

```

## disassembly

```asm
0x14007b664  mov     [rsp+arg_8], rbx
0x14007b669  mov     [rsp+arg_10], rsi
0x14007b66e  push    rdi
0x14007b66f  sub     rsp, 20h
0x14007b673  xor     edi, edi
0x14007b675  mov     rbx, rcx
0x14007b678  xor     eax, eax
0x14007b67a  mov     [rsp+28h+LockState.OldIrql], dil
0x14007b67f  mov     word ptr [rsp+28h+LockState.LockState], ax
0x14007b684  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b68b  lea     rsi, WPP_GLOBAL_Control
0x14007b692  cmp     rcx, rsi
0x14007b695  jz      short loc_14007B6AA
0x14007b697  mov     rcx, [rcx+18h]
0x14007b69b  lea     edx, [rdi+0Eh]
0x14007b69e  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007b6a5  call    WPP_SF_
0x14007b6aa  test    rbx, rbx
0x14007b6ad  jz      loc_14007B882
0x14007b6b3  mov     rcx, [rbx]
0x14007b6b6  lea     rdx, [rsp+28h+LockState]; LockState
0x14007b6bb  xor     r8d, r8d; Flags
0x14007b6be  mov     rcx, [rcx+90h]; Lock
0x14007b6c5  call    cs:__imp_NdisAcquireRWLockWrite
0x14007b6cc  nop     dword ptr [rax+rax+00h]
0x14007b6d1  mov     rcx, [rbx]; struct _VELAN *
0x14007b6d4  xor     r8d, r8d; void (*)(void *, struct _DOT11_WFD_ADDRESS_RESPONSE_KDE_DATA *)
0x14007b6d7  xor     edx, edx; void *
0x14007b6d9  call    ?Dot11RsnaConfigureAddressRequestKDE@@YAXPEAU_VELAN@@PEAXP6AX1PEAU_DOT11_WFD_ADDRESS_RESPONSE_KDE_DATA@@@Z@Z; Dot11RsnaConfigureAddressRequestKDE(_VELAN *,void *,void (*)(void *,_DOT11_WFD_ADDRESS_RESPONSE_KDE_DATA *))
0x14007b6de  mov     rcx, [rbx]
0x14007b6e1  lea     rdx, [rsp+28h+LockState]; LockState
0x14007b6e6  mov     rcx, [rcx+90h]; Lock
0x14007b6ed  call    cs:__imp_NdisReleaseRWLock
0x14007b6f4  nop     dword ptr [rax+rax+00h]
0x14007b6f9  mov     rcx, [rbx+0B8h]; struct _WFD_DEVICE_ROLE *
0x14007b700  test    rcx, rcx
0x14007b703  jz      short loc_14007B731
0x14007b705  mov     edx, [rbx+10h]
0x14007b708  sub     edx, 1
0x14007b70b  jz      short loc_14007B725
0x14007b70d  sub     edx, 1
0x14007b710  jz      short loc_14007B71E
0x14007b712  cmp     edx, 2
0x14007b715  jnz     short loc_14007B72A
0x14007b717  call    ?WFDClientDeInitialize@@YAXPEAU_WFD_CLIENT_ROLE@@@Z; WFDClientDeInitialize(_WFD_CLIENT_ROLE *)
0x14007b71c  jmp     short loc_14007B72A
0x14007b71e  call    ?WFDGODeInitialize@@YAXPEAU_WFD_GO_ROLE@@@Z; WFDGODeInitialize(_WFD_GO_ROLE *)
0x14007b723  jmp     short loc_14007B72A
0x14007b725  call    ?WFDDeviceDeInitialize@@YAXPEAU_WFD_DEVICE_ROLE@@@Z; WFDDeviceDeInitialize(_WFD_DEVICE_ROLE *)
0x14007b72a  mov     [rbx+0B8h], rdi
0x14007b731  mov     rcx, [rbx+20h]; Lock
0x14007b735  test    rcx, rcx
0x14007b738  jz      short loc_14007B74A
0x14007b73a  call    cs:__imp_NdisFreeRWLock
0x14007b741  nop     dword ptr [rax+rax+00h]
0x14007b746  mov     [rbx+20h], rdi
0x14007b74a  call    Feature_57277348__private_IsEnabledDeviceUsageNoInline
0x14007b74f  mov     rcx, [rbx+30h]
0x14007b753  test    eax, eax
0x14007b755  jz      short loc_14007B79D
0x14007b757  test    rcx, rcx
0x14007b75a  jz      short loc_14007B78F
0x14007b75c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14007b760  mov     rax, [rcx]
0x14007b763  test    rax, rax
0x14007b766  jz      short loc_14007B77C
0x14007b768  mov     rdx, rcx; Entry
0x14007b76b  mov     rcx, rax; Lookaside
0x14007b76e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007b775  nop     dword ptr [rax+rax+00h]
0x14007b77a  jmp     short loc_14007B78B
0x14007b77c  mov     edx, [rcx+8]; Tag
0x14007b77f  call    cs:__imp_ExFreePoolWithTag
0x14007b786  nop     dword ptr [rax+rax+00h]
0x14007b78b  mov     [rbx+30h], rdi
0x14007b78f  mov     [rbx+28h], edi
0x14007b792  mov     rcx, [rbx+38h]
0x14007b796  test    rcx, rcx
0x14007b799  jz      short loc_14007B814
0x14007b79b  jmp     short loc_14007B7E1
0x14007b79d  test    rcx, rcx
0x14007b7a0  jz      short loc_14007B7D8
0x14007b7a2  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14007b7a6  mov     rax, [rcx]
0x14007b7a9  test    rax, rax
0x14007b7ac  jz      short loc_14007B7C2
0x14007b7ae  mov     rdx, rcx; Entry
0x14007b7b1  mov     rcx, rax; Lookaside
0x14007b7b4  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007b7bb  nop     dword ptr [rax+rax+00h]
0x14007b7c0  jmp     short loc_14007B7D1
0x14007b7c2  mov     edx, [rcx+8]; Tag
0x14007b7c5  call    cs:__imp_ExFreePoolWithTag
0x14007b7cc  nop     dword ptr [rax+rax+00h]
0x14007b7d1  mov     [rbx+30h], rdi
0x14007b7d5  mov     [rbx+28h], edi
0x14007b7d8  mov     rcx, [rbx+38h]
0x14007b7dc  test    rcx, rcx
0x14007b7df  jz      short loc_14007B817
0x14007b7e1  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14007b7e5  mov     rax, [rcx]
0x14007b7e8  test    rax, rax
0x14007b7eb  jz      short loc_14007B801
0x14007b7ed  mov     rdx, rcx; Entry
0x14007b7f0  mov     rcx, rax; Lookaside
0x14007b7f3  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007b7fa  nop     dword ptr [rax+rax+00h]
0x14007b7ff  jmp     short loc_14007B810
0x14007b801  mov     edx, [rcx+8]; Tag
0x14007b804  call    cs:__imp_ExFreePoolWithTag
0x14007b80b  nop     dword ptr [rax+rax+00h]
0x14007b810  mov     [rbx+38h], rdi
0x14007b814  mov     [rbx+40h], edi
0x14007b817  mov     rcx, [rbx+48h]
0x14007b81b  test    rcx, rcx
0x14007b81e  jz      short loc_14007B853
0x14007b820  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14007b824  mov     rax, [rcx]
0x14007b827  test    rax, rax
0x14007b82a  jz      short loc_14007B840
0x14007b82c  mov     rdx, rcx; Entry
0x14007b82f  mov     rcx, rax; Lookaside
0x14007b832  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007b839  nop     dword ptr [rax+rax+00h]
0x14007b83e  jmp     short loc_14007B84F
0x14007b840  mov     edx, [rcx+8]; Tag
0x14007b843  call    cs:__imp_ExFreePoolWithTag
0x14007b84a  nop     dword ptr [rax+rax+00h]
0x14007b84f  mov     [rbx+48h], rdi
0x14007b853  lea     rcx, [rbx-10h]; P
0x14007b857  mov     rax, [rcx]
0x14007b85a  test    rax, rax
0x14007b85d  jz      short loc_14007B873
0x14007b85f  mov     rdx, rcx; Entry
0x14007b862  mov     rcx, rax; Lookaside
0x14007b865  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007b86c  nop     dword ptr [rax+rax+00h]
0x14007b871  jmp     short loc_14007B882
0x14007b873  mov     edx, [rcx+8]; Tag
0x14007b876  call    cs:__imp_ExFreePoolWithTag
0x14007b87d  nop     dword ptr [rax+rax+00h]
0x14007b882  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b889  cmp     rcx, rsi
0x14007b88c  jz      short loc_14007B8A3
0x14007b88e  mov     rcx, [rcx+18h]
0x14007b892  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007b899  mov     edx, 0Fh
0x14007b89e  call    WPP_SF_
0x14007b8a3  mov     rbx, [rsp+28h+arg_8]
0x14007b8a8  mov     rsi, [rsp+28h+arg_10]
0x14007b8ad  add     rsp, 20h
0x14007b8b1  pop     rdi
0x14007b8b2  retn
```

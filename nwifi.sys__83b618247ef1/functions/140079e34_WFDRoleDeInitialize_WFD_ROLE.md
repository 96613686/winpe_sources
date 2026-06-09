# WFDRoleDeInitialize(_WFD_ROLE *)

- ea: `0x140079e34`
- end: `0x14007a084`
- name: `?WFDRoleDeInitialize@@YAXPEAU_WFD_ROLE@@@Z`
- size: `592`
- prototype: `void __fastcall(struct _WFD_ROLE *)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1400210c8`
- `0x140064930`
- `0x140070a50`
- `0x14007a964`
- `0x14007dd58`

## callees

- `0x14000d22c`
- `0x140022dd4`
- `0x14003ad30`
- `0x140045914`
- `0x140079e34`
- `0x14008d7b4`
- `0x14008d91c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079f3e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079f84`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079fc3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007a002`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007a035`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079f3e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079f84`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079fc3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007a002`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007a035`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079f4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079f95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079fd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a013`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a046`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079f4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079f95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079fd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a013`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a046`
- `NDIS!NdisFreeRWLock` at `0x140079f0a`
- `NDIS!NdisFreeRWLock` at `0x140079f0a`
- `NDIS!NdisAcquireRWLockWrite` at `0x140079e95`
- `NDIS!NdisAcquireRWLockWrite` at `0x140079e95`
- `NDIS!NdisReleaseRWLock` at `0x140079ebd`
- `NDIS!NdisReleaseRWLock` at `0x140079ebd`

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
0x140079e34  mov     [rsp+arg_8], rbx
0x140079e39  mov     [rsp+arg_10], rsi
0x140079e3e  push    rdi
0x140079e3f  sub     rsp, 20h
0x140079e43  xor     edi, edi
0x140079e45  mov     rbx, rcx
0x140079e48  xor     eax, eax
0x140079e4a  mov     [rsp+28h+LockState.OldIrql], dil
0x140079e4f  mov     word ptr [rsp+28h+LockState.LockState], ax
0x140079e54  mov     rcx, cs:WPP_GLOBAL_Control
0x140079e5b  lea     rsi, WPP_GLOBAL_Control
0x140079e62  cmp     rcx, rsi
0x140079e65  jz      short loc_140079E7A
0x140079e67  mov     rcx, [rcx+18h]
0x140079e6b  lea     edx, [rdi+0Eh]
0x140079e6e  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079e75  call    WPP_SF_
0x140079e7a  test    rbx, rbx
0x140079e7d  jz      loc_14007A052
0x140079e83  mov     rcx, [rbx]
0x140079e86  lea     rdx, [rsp+28h+LockState]; LockState
0x140079e8b  xor     r8d, r8d; Flags
0x140079e8e  mov     rcx, [rcx+90h]; Lock
0x140079e95  call    cs:__imp_NdisAcquireRWLockWrite
0x140079e9c  nop     dword ptr [rax+rax+00h]
0x140079ea1  mov     rcx, [rbx]; struct _VELAN *
0x140079ea4  xor     r8d, r8d; void (*)(void *, struct _DOT11_WFD_ADDRESS_RESPONSE_KDE_DATA *)
0x140079ea7  xor     edx, edx; void *
0x140079ea9  call    ?Dot11RsnaConfigureAddressRequestKDE@@YAXPEAU_VELAN@@PEAXP6AX1PEAU_DOT11_WFD_ADDRESS_RESPONSE_KDE_DATA@@@Z@Z; Dot11RsnaConfigureAddressRequestKDE(_VELAN *,void *,void (*)(void *,_DOT11_WFD_ADDRESS_RESPONSE_KDE_DATA *))
0x140079eae  mov     rcx, [rbx]
0x140079eb1  lea     rdx, [rsp+28h+LockState]; LockState
0x140079eb6  mov     rcx, [rcx+90h]; Lock
0x140079ebd  call    cs:__imp_NdisReleaseRWLock
0x140079ec4  nop     dword ptr [rax+rax+00h]
0x140079ec9  mov     rcx, [rbx+0B8h]; struct _WFD_DEVICE_ROLE *
0x140079ed0  test    rcx, rcx
0x140079ed3  jz      short loc_140079F01
0x140079ed5  mov     edx, [rbx+10h]
0x140079ed8  sub     edx, 1
0x140079edb  jz      short loc_140079EF5
0x140079edd  sub     edx, 1
0x140079ee0  jz      short loc_140079EEE
0x140079ee2  cmp     edx, 2
0x140079ee5  jnz     short loc_140079EFA
0x140079ee7  call    ?WFDClientDeInitialize@@YAXPEAU_WFD_CLIENT_ROLE@@@Z; WFDClientDeInitialize(_WFD_CLIENT_ROLE *)
0x140079eec  jmp     short loc_140079EFA
0x140079eee  call    ?WFDGODeInitialize@@YAXPEAU_WFD_GO_ROLE@@@Z; WFDGODeInitialize(_WFD_GO_ROLE *)
0x140079ef3  jmp     short loc_140079EFA
0x140079ef5  call    ?WFDDeviceDeInitialize@@YAXPEAU_WFD_DEVICE_ROLE@@@Z; WFDDeviceDeInitialize(_WFD_DEVICE_ROLE *)
0x140079efa  mov     [rbx+0B8h], rdi
0x140079f01  mov     rcx, [rbx+20h]; Lock
0x140079f05  test    rcx, rcx
0x140079f08  jz      short loc_140079F1A
0x140079f0a  call    cs:__imp_NdisFreeRWLock
0x140079f11  nop     dword ptr [rax+rax+00h]
0x140079f16  mov     [rbx+20h], rdi
0x140079f1a  call    Feature_57277348__private_IsEnabledDeviceUsageNoInline
0x140079f1f  mov     rcx, [rbx+30h]
0x140079f23  test    eax, eax
0x140079f25  jz      short loc_140079F6D
0x140079f27  test    rcx, rcx
0x140079f2a  jz      short loc_140079F5F
0x140079f2c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140079f30  mov     rax, [rcx]
0x140079f33  test    rax, rax
0x140079f36  jz      short loc_140079F4C
0x140079f38  mov     rdx, rcx; Entry
0x140079f3b  mov     rcx, rax; Lookaside
0x140079f3e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140079f45  nop     dword ptr [rax+rax+00h]
0x140079f4a  jmp     short loc_140079F5B
0x140079f4c  mov     edx, [rcx+8]; Tag
0x140079f4f  call    cs:__imp_ExFreePoolWithTag
0x140079f56  nop     dword ptr [rax+rax+00h]
0x140079f5b  mov     [rbx+30h], rdi
0x140079f5f  mov     [rbx+28h], edi
0x140079f62  mov     rcx, [rbx+38h]
0x140079f66  test    rcx, rcx
0x140079f69  jz      short loc_140079FE4
0x140079f6b  jmp     short loc_140079FB1
0x140079f6d  test    rcx, rcx
0x140079f70  jz      short loc_140079FA8
0x140079f72  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140079f76  mov     rax, [rcx]
0x140079f79  test    rax, rax
0x140079f7c  jz      short loc_140079F92
0x140079f7e  mov     rdx, rcx; Entry
0x140079f81  mov     rcx, rax; Lookaside
0x140079f84  call    cs:__imp_ExFreeToNPagedLookasideList
0x140079f8b  nop     dword ptr [rax+rax+00h]
0x140079f90  jmp     short loc_140079FA1
0x140079f92  mov     edx, [rcx+8]; Tag
0x140079f95  call    cs:__imp_ExFreePoolWithTag
0x140079f9c  nop     dword ptr [rax+rax+00h]
0x140079fa1  mov     [rbx+30h], rdi
0x140079fa5  mov     [rbx+28h], edi
0x140079fa8  mov     rcx, [rbx+38h]
0x140079fac  test    rcx, rcx
0x140079faf  jz      short loc_140079FE7
0x140079fb1  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140079fb5  mov     rax, [rcx]
0x140079fb8  test    rax, rax
0x140079fbb  jz      short loc_140079FD1
0x140079fbd  mov     rdx, rcx; Entry
0x140079fc0  mov     rcx, rax; Lookaside
0x140079fc3  call    cs:__imp_ExFreeToNPagedLookasideList
0x140079fca  nop     dword ptr [rax+rax+00h]
0x140079fcf  jmp     short loc_140079FE0
0x140079fd1  mov     edx, [rcx+8]; Tag
0x140079fd4  call    cs:__imp_ExFreePoolWithTag
0x140079fdb  nop     dword ptr [rax+rax+00h]
0x140079fe0  mov     [rbx+38h], rdi
0x140079fe4  mov     [rbx+40h], edi
0x140079fe7  mov     rcx, [rbx+48h]
0x140079feb  test    rcx, rcx
0x140079fee  jz      short loc_14007A023
0x140079ff0  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140079ff4  mov     rax, [rcx]
0x140079ff7  test    rax, rax
0x140079ffa  jz      short loc_14007A010
0x140079ffc  mov     rdx, rcx; Entry
0x140079fff  mov     rcx, rax; Lookaside
0x14007a002  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007a009  nop     dword ptr [rax+rax+00h]
0x14007a00e  jmp     short loc_14007A01F
0x14007a010  mov     edx, [rcx+8]; Tag
0x14007a013  call    cs:__imp_ExFreePoolWithTag
0x14007a01a  nop     dword ptr [rax+rax+00h]
0x14007a01f  mov     [rbx+48h], rdi
0x14007a023  lea     rcx, [rbx-10h]; P
0x14007a027  mov     rax, [rcx]
0x14007a02a  test    rax, rax
0x14007a02d  jz      short loc_14007A043
0x14007a02f  mov     rdx, rcx; Entry
0x14007a032  mov     rcx, rax; Lookaside
0x14007a035  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007a03c  nop     dword ptr [rax+rax+00h]
0x14007a041  jmp     short loc_14007A052
0x14007a043  mov     edx, [rcx+8]; Tag
0x14007a046  call    cs:__imp_ExFreePoolWithTag
0x14007a04d  nop     dword ptr [rax+rax+00h]
0x14007a052  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a059  cmp     rcx, rsi
0x14007a05c  jz      short loc_14007A073
0x14007a05e  mov     rcx, [rcx+18h]
0x14007a062  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007a069  mov     edx, 0Fh
0x14007a06e  call    WPP_SF_
0x14007a073  mov     rbx, [rsp+28h+arg_8]
0x14007a078  mov     rsi, [rsp+28h+arg_10]
0x14007a07d  add     rsp, 20h
0x14007a081  pop     rdi
0x14007a082  retn
```

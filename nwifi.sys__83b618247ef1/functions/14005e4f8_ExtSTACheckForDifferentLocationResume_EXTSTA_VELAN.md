# ExtSTACheckForDifferentLocationResume(EXTSTA_VELAN *)

- ea: `0x14005e4f8`
- end: `0x14005e68b`
- name: `?ExtSTACheckForDifferentLocationResume@@YAHPEAUEXTSTA_VELAN@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14001e830`

## callees

- `0x14000d22c`
- `0x14005e42c`
- `0x14005e4f8`
- `0x14005f9d4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005e627`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005e65b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005e627`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005e65b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e638`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e66c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e638`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e66c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e52e`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e52e`
- `NDIS!NdisReleaseRWLock` at `0x14005e567`
- `NDIS!NdisReleaseRWLock` at `0x14005e567`

## pseudocode

```c
__int64 __fastcall ExtSTACheckForDifferentLocationResume(struct EXTSTA_VELAN *a1)
{
  _VELAN *pGenVElan; // rcx
  struct EXTSTA_BSS_LIST *pPreSleepBSSList; // rsi
  unsigned int v4; // edx
  struct EXTSTA_BSS_LIST *v5; // rbx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  struct EXTSTA_BSS_LIST *BSSList; // rax
  unsigned int v9; // edi
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  pGenVElan = a1->pGenVElan;
  *(_WORD *)&LockState.LockState = 0;
  pPreSleepBSSList = 0;
  LockState.OldIrql = 0;
  NdisAcquireRWLockWrite(pGenVElan->pRWLock, &LockState, 0);
  if ( a1->AssocMgr.pPreSleepBSSList )
  {
    pPreSleepBSSList = a1->AssocMgr.pPreSleepBSSList;
    a1->AssocMgr.pPreSleepBSSList = 0;
  }
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( !pPreSleepBSSList )
  {
    v5 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_10;
    v7 = 155;
    goto LABEL_9;
  }
  BSSList = ExtSTAInternalQueryBSSList(a1, v4);
  v5 = BSSList;
  if ( !BSSList )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_10;
    v7 = 156;
LABEL_9:
    WPP_SF_(v6->AttachedDevice, v7, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
LABEL_10:
    v9 = 0;
    if ( !pPreSleepBSSList )
      goto LABEL_19;
    goto LABEL_16;
  }
  v9 = 1;
  if ( (unsigned int)ExtSTACheckBSSListForDifferentLocation(pPreSleepBSSList, BSSList) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
  }
  else
  {
    v9 = 0;
  }
LABEL_16:
  if ( *(_QWORD *)&pPreSleepBSSList[-1].BSSIDList[253][2] )
    ExFreeToNPagedLookasideList(
      *(PNPAGED_LOOKASIDE_LIST *)&pPreSleepBSSList[-1].BSSIDList[253][2],
      &pPreSleepBSSList[-1].BSSIDList[253][2]);
  else
    ExFreePoolWithTag(&pPreSleepBSSList[-1].BSSIDList[253][2], *(_DWORD *)&pPreSleepBSSList[-1].BSSIDList[254][4]);
LABEL_19:
  if ( v5 )
  {
    if ( *(_QWORD *)&v5[-1].BSSIDList[253][2] )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v5[-1].BSSIDList[253][2], &v5[-1].BSSIDList[253][2]);
    else
      ExFreePoolWithTag(&v5[-1].BSSIDList[253][2], *(_DWORD *)&v5[-1].BSSIDList[254][4]);
  }
  return v9;
}

```

## disassembly

```asm
0x14005e4f8  mov     [rsp+arg_8], rbx
0x14005e4fd  mov     [rsp+arg_10], rsi
0x14005e502  push    rdi
0x14005e503  sub     rsp, 20h
0x14005e507  mov     rbx, rcx
0x14005e50a  lea     rdx, [rsp+28h+LockState]; LockState
0x14005e50f  mov     rcx, [rcx+0A38h]
0x14005e516  xor     eax, eax
0x14005e518  mov     word ptr [rsp+28h+LockState.LockState], ax
0x14005e51d  xor     esi, esi
0x14005e51f  mov     [rsp+28h+LockState.OldIrql], sil
0x14005e524  xor     r8d, r8d; Flags
0x14005e527  mov     rcx, [rcx+90h]; Lock
0x14005e52e  call    cs:__imp_NdisAcquireRWLockWrite
0x14005e535  nop     dword ptr [rax+rax+00h]
0x14005e53a  mov     rax, [rbx+2F0h]
0x14005e541  test    rax, rax
0x14005e544  jz      short loc_14005E554
0x14005e546  mov     rsi, rax
0x14005e549  mov     qword ptr [rbx+2F0h], 0
0x14005e554  mov     rcx, [rbx+0A38h]
0x14005e55b  lea     rdx, [rsp+28h+LockState]; LockState
0x14005e560  mov     rcx, [rcx+90h]; Lock
0x14005e567  call    cs:__imp_NdisReleaseRWLock
0x14005e56e  nop     dword ptr [rax+rax+00h]
0x14005e573  test    rsi, rsi
0x14005e576  jnz     short loc_14005E594
0x14005e578  xor     ebx, ebx
0x14005e57a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e581  lea     rax, WPP_GLOBAL_Control
0x14005e588  cmp     rcx, rax
0x14005e58b  jz      short loc_14005E5CC
0x14005e58d  mov     edx, 9Bh
0x14005e592  jmp     short loc_14005E5BC
0x14005e594  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14005e597  call    ?ExtSTAInternalQueryBSSList@@YAPEAUEXTSTA_BSS_LIST@@PEAUEXTSTA_VELAN@@@Z; ExtSTAInternalQueryBSSList(EXTSTA_VELAN *)
0x14005e59c  mov     rbx, rax
0x14005e59f  test    rax, rax
0x14005e5a2  jnz     short loc_14005E5D5
0x14005e5a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e5ab  lea     rax, WPP_GLOBAL_Control
0x14005e5b2  cmp     rcx, rax
0x14005e5b5  jz      short loc_14005E5CC
0x14005e5b7  mov     edx, 9Ch
0x14005e5bc  mov     rcx, [rcx+18h]
0x14005e5c0  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005e5c7  call    WPP_SF_
0x14005e5cc  xor     edi, edi
0x14005e5ce  test    rsi, rsi
0x14005e5d1  jz      short loc_14005E644
0x14005e5d3  jmp     short loc_14005E615
0x14005e5d5  mov     rdx, rax; struct EXTSTA_BSS_LIST *
0x14005e5d8  mov     rcx, rsi; struct EXTSTA_BSS_LIST *
0x14005e5db  call    ?ExtSTACheckBSSListForDifferentLocation@@YAHPEAUEXTSTA_BSS_LIST@@0@Z; ExtSTACheckBSSListForDifferentLocation(EXTSTA_BSS_LIST *,EXTSTA_BSS_LIST *)
0x14005e5e0  mov     edi, 1
0x14005e5e5  cmp     eax, edi
0x14005e5e7  jnz     short loc_14005E613
0x14005e5e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e5f0  lea     rax, WPP_GLOBAL_Control
0x14005e5f7  cmp     rcx, rax
0x14005e5fa  jz      short loc_14005E615
0x14005e5fc  mov     rcx, [rcx+18h]
0x14005e600  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005e607  mov     edx, 9Dh
0x14005e60c  call    WPP_SF_
0x14005e611  jmp     short loc_14005E615
0x14005e613  xor     edi, edi
0x14005e615  lea     rcx, [rsi-10h]; P
0x14005e619  mov     rax, [rcx]
0x14005e61c  test    rax, rax
0x14005e61f  jz      short loc_14005E635
0x14005e621  mov     rdx, rcx; Entry
0x14005e624  mov     rcx, rax; Lookaside
0x14005e627  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005e62e  nop     dword ptr [rax+rax+00h]
0x14005e633  jmp     short loc_14005E644
0x14005e635  mov     edx, [rcx+8]; Tag
0x14005e638  call    cs:__imp_ExFreePoolWithTag
0x14005e63f  nop     dword ptr [rax+rax+00h]
0x14005e644  test    rbx, rbx
0x14005e647  jz      short loc_14005E678
0x14005e649  lea     rcx, [rbx-10h]; P
0x14005e64d  mov     rax, [rcx]
0x14005e650  test    rax, rax
0x14005e653  jz      short loc_14005E669
0x14005e655  mov     rdx, rcx; Entry
0x14005e658  mov     rcx, rax; Lookaside
0x14005e65b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005e662  nop     dword ptr [rax+rax+00h]
0x14005e667  jmp     short loc_14005E678
0x14005e669  mov     edx, [rcx+8]; Tag
0x14005e66c  call    cs:__imp_ExFreePoolWithTag
0x14005e673  nop     dword ptr [rax+rax+00h]
0x14005e678  mov     rbx, [rsp+28h+arg_8]
0x14005e67d  mov     eax, edi
0x14005e67f  mov     rsi, [rsp+28h+arg_10]
0x14005e684  add     rsp, 20h
0x14005e688  pop     rdi
0x14005e689  retn
```

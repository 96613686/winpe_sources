# ExtSTACheckForDifferentLocationResume(EXTSTA_VELAN *)

- ea: `0x14005fd28`
- end: `0x14005febb`
- name: `?ExtSTACheckForDifferentLocationResume@@YAHPEAUEXTSTA_VELAN@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14001e830`

## callees

- `0x14000d21c`
- `0x14005fc5c`
- `0x14005fd28`
- `0x140061204`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005fe57`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005fe8b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005fe57`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005fe8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fe68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fe9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fe68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fe9c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005fd5e`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005fd5e`
- `NDIS!NdisReleaseRWLock` at `0x14005fd97`
- `NDIS!NdisReleaseRWLock` at `0x14005fd97`

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
    v7 = 154;
    goto LABEL_9;
  }
  BSSList = ExtSTAInternalQueryBSSList(a1, v4);
  v5 = BSSList;
  if ( !BSSList )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_10;
    v7 = 155;
LABEL_9:
    WPP_SF_(v6->AttachedDevice, v7, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
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
0x14005fd28  mov     [rsp+arg_8], rbx
0x14005fd2d  mov     [rsp+arg_10], rsi
0x14005fd32  push    rdi
0x14005fd33  sub     rsp, 20h
0x14005fd37  mov     rbx, rcx
0x14005fd3a  lea     rdx, [rsp+28h+LockState]; LockState
0x14005fd3f  mov     rcx, [rcx+0A38h]
0x14005fd46  xor     eax, eax
0x14005fd48  mov     word ptr [rsp+28h+LockState.LockState], ax
0x14005fd4d  xor     esi, esi
0x14005fd4f  mov     [rsp+28h+LockState.OldIrql], sil
0x14005fd54  xor     r8d, r8d; Flags
0x14005fd57  mov     rcx, [rcx+90h]; Lock
0x14005fd5e  call    cs:__imp_NdisAcquireRWLockWrite
0x14005fd65  nop     dword ptr [rax+rax+00h]
0x14005fd6a  mov     rax, [rbx+2F0h]
0x14005fd71  test    rax, rax
0x14005fd74  jz      short loc_14005FD84
0x14005fd76  mov     rsi, rax
0x14005fd79  mov     qword ptr [rbx+2F0h], 0
0x14005fd84  mov     rcx, [rbx+0A38h]
0x14005fd8b  lea     rdx, [rsp+28h+LockState]; LockState
0x14005fd90  mov     rcx, [rcx+90h]; Lock
0x14005fd97  call    cs:__imp_NdisReleaseRWLock
0x14005fd9e  nop     dword ptr [rax+rax+00h]
0x14005fda3  test    rsi, rsi
0x14005fda6  jnz     short loc_14005FDC4
0x14005fda8  xor     ebx, ebx
0x14005fdaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fdb1  lea     rax, WPP_GLOBAL_Control
0x14005fdb8  cmp     rcx, rax
0x14005fdbb  jz      short loc_14005FDFC
0x14005fdbd  mov     edx, 9Ah
0x14005fdc2  jmp     short loc_14005FDEC
0x14005fdc4  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14005fdc7  call    ?ExtSTAInternalQueryBSSList@@YAPEAUEXTSTA_BSS_LIST@@PEAUEXTSTA_VELAN@@@Z; ExtSTAInternalQueryBSSList(EXTSTA_VELAN *)
0x14005fdcc  mov     rbx, rax
0x14005fdcf  test    rax, rax
0x14005fdd2  jnz     short loc_14005FE05
0x14005fdd4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fddb  lea     rax, WPP_GLOBAL_Control
0x14005fde2  cmp     rcx, rax
0x14005fde5  jz      short loc_14005FDFC
0x14005fde7  mov     edx, 9Bh
0x14005fdec  mov     rcx, [rcx+18h]
0x14005fdf0  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14005fdf7  call    WPP_SF_
0x14005fdfc  xor     edi, edi
0x14005fdfe  test    rsi, rsi
0x14005fe01  jz      short loc_14005FE74
0x14005fe03  jmp     short loc_14005FE45
0x14005fe05  mov     rdx, rax; struct EXTSTA_BSS_LIST *
0x14005fe08  mov     rcx, rsi; struct EXTSTA_BSS_LIST *
0x14005fe0b  call    ?ExtSTACheckBSSListForDifferentLocation@@YAHPEAUEXTSTA_BSS_LIST@@0@Z; ExtSTACheckBSSListForDifferentLocation(EXTSTA_BSS_LIST *,EXTSTA_BSS_LIST *)
0x14005fe10  mov     edi, 1
0x14005fe15  cmp     eax, edi
0x14005fe17  jnz     short loc_14005FE43
0x14005fe19  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fe20  lea     rax, WPP_GLOBAL_Control
0x14005fe27  cmp     rcx, rax
0x14005fe2a  jz      short loc_14005FE45
0x14005fe2c  mov     rcx, [rcx+18h]
0x14005fe30  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14005fe37  mov     edx, 9Ch
0x14005fe3c  call    WPP_SF_
0x14005fe41  jmp     short loc_14005FE45
0x14005fe43  xor     edi, edi
0x14005fe45  lea     rcx, [rsi-10h]; P
0x14005fe49  mov     rax, [rcx]
0x14005fe4c  test    rax, rax
0x14005fe4f  jz      short loc_14005FE65
0x14005fe51  mov     rdx, rcx; Entry
0x14005fe54  mov     rcx, rax; Lookaside
0x14005fe57  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005fe5e  nop     dword ptr [rax+rax+00h]
0x14005fe63  jmp     short loc_14005FE74
0x14005fe65  mov     edx, [rcx+8]; Tag
0x14005fe68  call    cs:__imp_ExFreePoolWithTag
0x14005fe6f  nop     dword ptr [rax+rax+00h]
0x14005fe74  test    rbx, rbx
0x14005fe77  jz      short loc_14005FEA8
0x14005fe79  lea     rcx, [rbx-10h]; P
0x14005fe7d  mov     rax, [rcx]
0x14005fe80  test    rax, rax
0x14005fe83  jz      short loc_14005FE99
0x14005fe85  mov     rdx, rcx; Entry
0x14005fe88  mov     rcx, rax; Lookaside
0x14005fe8b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005fe92  nop     dword ptr [rax+rax+00h]
0x14005fe97  jmp     short loc_14005FEA8
0x14005fe99  mov     edx, [rcx+8]; Tag
0x14005fe9c  call    cs:__imp_ExFreePoolWithTag
0x14005fea3  nop     dword ptr [rax+rax+00h]
0x14005fea8  mov     rbx, [rsp+28h+arg_8]
0x14005fead  mov     eax, edi
0x14005feaf  mov     rsi, [rsp+28h+arg_10]
0x14005feb4  add     rsp, 20h
0x14005feb8  pop     rdi
0x14005feb9  retn
```

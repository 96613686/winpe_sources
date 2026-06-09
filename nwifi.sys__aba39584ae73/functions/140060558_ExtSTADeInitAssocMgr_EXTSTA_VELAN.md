# ExtSTADeInitAssocMgr(EXTSTA_VELAN *)

- ea: `0x140060558`
- end: `0x140060752`
- name: `?ExtSTADeInitAssocMgr@@YAXPEAUEXTSTA_VELAN@@@Z`
- size: `506`
- prototype: `void __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006533c`

## callees

- `0x14000d21c`
- `0x14001f1e4`
- `0x140025590`
- `0x14005f8f4`
- `0x14005f97c`
- `0x14005fec4`
- `0x140060558`
- `0x140064a18`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006062e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006062e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006063f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006063f`
- `NDIS!NdisFreeTimerObject` at `0x140060711`
- `NDIS!NdisFreeTimerObject` at `0x140060711`
- `NDIS!NdisMSleep` at `0x14006067a`
- `NDIS!NdisMSleep` at `0x140060692`
- `NDIS!NdisMSleep` at `0x14006067a`
- `NDIS!NdisMSleep` at `0x140060692`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400605c4`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400606bf`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400605c4`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400606bf`
- `NDIS!NdisReleaseRWLock` at `0x140060665`
- `NDIS!NdisReleaseRWLock` at `0x1400606fd`
- `NDIS!NdisReleaseRWLock` at `0x140060665`
- `NDIS!NdisReleaseRWLock` at `0x1400606fd`

## pseudocode

```c
void __fastcall ExtSTADeInitAssocMgr(struct EXTSTA_VELAN *a1)
{
  int v2; // edx
  struct _IRP *pIrp; // rdx
  EXTSTA_BSS_LIST *pPreSleepBSSList; // rcx
  ULONG *v5; // rcx
  void *hConnRoamingTimer; // rdi
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
  *(_DWORD *)&a1->AssocMgr |= 8u;
  ExtSTACancelConnRoamingTimerSync(a1);
  *(_DWORD *)&a1->AssocMgr &= 0xFFFFFFFC;
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
  Dot11LeaveRoamingAndAbortRoamingPacketEx(a1->pGenVElan, v2);
  ExtSTAFlushAssocTable(a1, 0, qword_1400A3E90);
  pIrp = a1->AssocMgr.pIrp;
  a1->AssocMgr.pIrp = 0;
  if ( pIrp )
    ExtSTACompleteConnection(a1, pIrp, -1073741248);
  ExtSTAUpcallDisconnect(a1);
  pPreSleepBSSList = a1->AssocMgr.pPreSleepBSSList;
  if ( pPreSleepBSSList )
  {
    v5 = (ULONG *)&pPreSleepBSSList[-1].BSSIDList[253][2];
    if ( *(_QWORD *)v5 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v5, v5);
    else
      ExFreePoolWithTag(v5, v5[2]);
    a1->AssocMgr.pPreSleepBSSList = 0;
  }
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  while ( a1->AssocMgr.bResetInProgress )
    NdisMSleep(0x30D40u);
  while ( a1->AssocMgr.ConnectIoctlRef )
    NdisMSleep(0x30D40u);
  hConnRoamingTimer = 0;
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
  if ( a1->AssocMgr.hConnRoamingTimer )
  {
    ExtSTACancelConnRoamingTimer(a1);
    hConnRoamingTimer = a1->AssocMgr.hConnRoamingTimer;
    a1->AssocMgr.hConnRoamingTimer = 0;
  }
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( hConnRoamingTimer )
    NdisFreeTimerObject(hConnRoamingTimer);
  *(_QWORD *)&a1->AssocMgr.uNumPendingAssoc = 0;
  a1->AssocMgr.uNumOpenPort = 0;
  a1->AssocMgr.uLastAssocStatusCode = 0;
  a1->AssocMgr.uAssocComebackTime = 0;
  *(_DWORD *)&a1->RoD &= ~4u;
  *(_DWORD *)&a1->AssocMgr &= ~8u;
}

```

## disassembly

```asm
0x140060558  mov     [rsp+arg_8], rbx
0x14006055d  mov     [rsp+arg_10], rsi
0x140060562  push    rdi
0x140060563  sub     rsp, 20h
0x140060567  xor     esi, esi
0x140060569  mov     rbx, rcx
0x14006056c  xor     eax, eax
0x14006056e  mov     [rsp+28h+LockState.OldIrql], sil
0x140060573  mov     word ptr [rsp+28h+LockState.LockState], ax
0x140060578  mov     rcx, cs:WPP_GLOBAL_Control
0x14006057f  lea     rax, WPP_GLOBAL_Control
0x140060586  cmp     rcx, rax
0x140060589  jz      short loc_14006059E
0x14006058b  mov     rcx, [rcx+18h]
0x14006058f  lea     edx, [rsi+0Ch]
0x140060592  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x140060599  call    WPP_SF_
0x14006059e  or      dword ptr [rbx+8], 8
0x1400605a2  mov     rcx, rbx; struct EXTSTA_VELAN *
0x1400605a5  call    ExtSTACancelConnRoamingTimerSync
0x1400605aa  and     dword ptr [rbx+8], 0FFFFFFFCh
0x1400605ae  lea     rdx, [rsp+28h+LockState]; LockState
0x1400605b3  mov     rcx, [rbx+0A38h]
0x1400605ba  xor     r8d, r8d; Flags
0x1400605bd  mov     rcx, [rcx+90h]; Lock
0x1400605c4  call    cs:__imp_NdisAcquireRWLockWrite
0x1400605cb  nop     dword ptr [rax+rax+00h]
0x1400605d0  mov     rcx, [rbx+0A38h]; struct _VELAN *
0x1400605d7  call    ?Dot11LeaveRoamingAndAbortRoamingPacketEx@@YAXPEAU_VELAN@@H@Z; Dot11LeaveRoamingAndAbortRoamingPacketEx(_VELAN *,int)
0x1400605dc  lea     r8, qword_1400A3E90
0x1400605e3  xor     edx, edx
0x1400605e5  mov     rcx, rbx
0x1400605e8  call    ExtSTAFlushAssocTable
0x1400605ed  mov     rdx, [rbx+10h]; struct _IRP *
0x1400605f1  mov     [rbx+10h], rsi
0x1400605f5  test    rdx, rdx
0x1400605f8  jz      short loc_140060608
0x1400605fa  mov     r8d, 0C0000240h; int
0x140060600  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140060603  call    ?ExtSTACompleteConnection@@YAXPEAUEXTSTA_VELAN@@PEAU_IRP@@J@Z; ExtSTACompleteConnection(EXTSTA_VELAN *,_IRP *,long)
0x140060608  mov     rcx, rbx
0x14006060b  call    ExtSTAUpcallDisconnect
0x140060610  mov     rcx, [rbx+2F0h]
0x140060617  test    rcx, rcx
0x14006061a  jz      short loc_140060652
0x14006061c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140060620  mov     rax, [rcx]
0x140060623  test    rax, rax
0x140060626  jz      short loc_14006063C
0x140060628  mov     rdx, rcx; Entry
0x14006062b  mov     rcx, rax; Lookaside
0x14006062e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140060635  nop     dword ptr [rax+rax+00h]
0x14006063a  jmp     short loc_14006064B
0x14006063c  mov     edx, [rcx+8]; Tag
0x14006063f  call    cs:__imp_ExFreePoolWithTag
0x140060646  nop     dword ptr [rax+rax+00h]
0x14006064b  mov     [rbx+2F0h], rsi
0x140060652  mov     rcx, [rbx+0A38h]
0x140060659  lea     rdx, [rsp+28h+LockState]; LockState
0x14006065e  mov     rcx, [rcx+90h]; Lock
0x140060665  call    cs:__imp_NdisReleaseRWLock
0x14006066c  nop     dword ptr [rax+rax+00h]
0x140060671  mov     edi, 30D40h
0x140060676  jmp     short loc_140060686
0x140060678  mov     ecx, edi; MicrosecondsToSleep
0x14006067a  call    cs:__imp_NdisMSleep
0x140060681  nop     dword ptr [rax+rax+00h]
0x140060686  cmp     [rbx+2ECh], esi
0x14006068c  jnz     short loc_140060678
0x14006068e  jmp     short loc_14006069E
0x140060690  mov     ecx, edi; MicrosecondsToSleep
0x140060692  call    cs:__imp_NdisMSleep
0x140060699  nop     dword ptr [rax+rax+00h]
0x14006069e  cmp     [rbx+330h], esi
0x1400606a4  jnz     short loc_140060690
0x1400606a6  mov     rcx, [rbx+0A38h]
0x1400606ad  lea     rdx, [rsp+28h+LockState]; LockState
0x1400606b2  xor     r8d, r8d; Flags
0x1400606b5  mov     rdi, rsi
0x1400606b8  mov     rcx, [rcx+90h]; Lock
0x1400606bf  call    cs:__imp_NdisAcquireRWLockWrite
0x1400606c6  nop     dword ptr [rax+rax+00h]
0x1400606cb  cmp     [rbx+2F8h], rsi
0x1400606d2  jz      short loc_1400606EA
0x1400606d4  mov     rcx, rbx; struct EXTSTA_VELAN *
0x1400606d7  call    ?ExtSTACancelConnRoamingTimer@@YAEPEAUEXTSTA_VELAN@@@Z; ExtSTACancelConnRoamingTimer(EXTSTA_VELAN *)
0x1400606dc  mov     rdi, [rbx+2F8h]
0x1400606e3  mov     [rbx+2F8h], rsi
0x1400606ea  mov     rcx, [rbx+0A38h]
0x1400606f1  lea     rdx, [rsp+28h+LockState]; LockState
0x1400606f6  mov     rcx, [rcx+90h]; Lock
0x1400606fd  call    cs:__imp_NdisReleaseRWLock
0x140060704  nop     dword ptr [rax+rax+00h]
0x140060709  test    rdi, rdi
0x14006070c  jz      short loc_14006071D
0x14006070e  mov     rcx, rdi; TimerObject
0x140060711  call    cs:__imp_NdisFreeTimerObject
0x140060718  nop     dword ptr [rax+rax+00h]
0x14006071d  mov     [rbx+148h], rsi
0x140060724  mov     [rbx+150h], esi
0x14006072a  mov     [rbx+194h], esi
0x140060730  mov     [rbx+19Ch], esi
0x140060736  and     dword ptr [rbx+610h], 0FFFFFFFBh
0x14006073d  and     dword ptr [rbx+8], 0FFFFFFF7h
0x140060741  mov     rbx, [rsp+28h+arg_8]
0x140060746  mov     rsi, [rsp+28h+arg_10]
0x14006074b  add     rsp, 20h
0x14006074f  pop     rdi
0x140060750  retn
```

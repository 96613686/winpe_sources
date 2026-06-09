# ExtSTADeInitAssocMgr(EXTSTA_VELAN *)

- ea: `0x14005ed28`
- end: `0x14005ef22`
- name: `?ExtSTADeInitAssocMgr@@YAXPEAUEXTSTA_VELAN@@@Z`
- size: `506`
- prototype: `void __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140063b0c`

## callees

- `0x14000d22c`
- `0x14001f1e4`
- `0x14002530c`
- `0x14005e0c4`
- `0x14005e14c`
- `0x14005e694`
- `0x14005ed28`
- `0x1400631e8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005edfe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005edfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ee0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ee0f`
- `NDIS!NdisFreeTimerObject` at `0x14005eee1`
- `NDIS!NdisFreeTimerObject` at `0x14005eee1`
- `NDIS!NdisMSleep` at `0x14005ee4a`
- `NDIS!NdisMSleep` at `0x14005ee62`
- `NDIS!NdisMSleep` at `0x14005ee4a`
- `NDIS!NdisMSleep` at `0x14005ee62`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ed94`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ee8f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ed94`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005ee8f`
- `NDIS!NdisReleaseRWLock` at `0x14005ee35`
- `NDIS!NdisReleaseRWLock` at `0x14005eecd`
- `NDIS!NdisReleaseRWLock` at `0x14005ee35`
- `NDIS!NdisReleaseRWLock` at `0x14005eecd`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
  *(_DWORD *)&a1->AssocMgr |= 8u;
  ExtSTACancelConnRoamingTimerSync(a1);
  *(_DWORD *)&a1->AssocMgr &= 0xFFFFFFFC;
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
  Dot11LeaveRoamingAndAbortRoamingPacketEx(a1->pGenVElan, v2);
  ExtSTAFlushAssocTable(a1, 0, qword_1400A1D50);
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
0x14005ed28  mov     [rsp+arg_8], rbx
0x14005ed2d  mov     [rsp+arg_10], rsi
0x14005ed32  push    rdi
0x14005ed33  sub     rsp, 20h
0x14005ed37  xor     esi, esi
0x14005ed39  mov     rbx, rcx
0x14005ed3c  xor     eax, eax
0x14005ed3e  mov     [rsp+28h+LockState.OldIrql], sil
0x14005ed43  mov     word ptr [rsp+28h+LockState.LockState], ax
0x14005ed48  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ed4f  lea     rax, WPP_GLOBAL_Control
0x14005ed56  cmp     rcx, rax
0x14005ed59  jz      short loc_14005ED6E
0x14005ed5b  mov     rcx, [rcx+18h]
0x14005ed5f  lea     edx, [rsi+0Ch]
0x14005ed62  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005ed69  call    WPP_SF_
0x14005ed6e  or      dword ptr [rbx+8], 8
0x14005ed72  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14005ed75  call    ExtSTACancelConnRoamingTimerSync
0x14005ed7a  and     dword ptr [rbx+8], 0FFFFFFFCh
0x14005ed7e  lea     rdx, [rsp+28h+LockState]; LockState
0x14005ed83  mov     rcx, [rbx+0A38h]
0x14005ed8a  xor     r8d, r8d; Flags
0x14005ed8d  mov     rcx, [rcx+90h]; Lock
0x14005ed94  call    cs:__imp_NdisAcquireRWLockWrite
0x14005ed9b  nop     dword ptr [rax+rax+00h]
0x14005eda0  mov     rcx, [rbx+0A38h]; struct _VELAN *
0x14005eda7  call    ?Dot11LeaveRoamingAndAbortRoamingPacketEx@@YAXPEAU_VELAN@@H@Z; Dot11LeaveRoamingAndAbortRoamingPacketEx(_VELAN *,int)
0x14005edac  lea     r8, qword_1400A1D50
0x14005edb3  xor     edx, edx
0x14005edb5  mov     rcx, rbx
0x14005edb8  call    ExtSTAFlushAssocTable
0x14005edbd  mov     rdx, [rbx+10h]; struct _IRP *
0x14005edc1  mov     [rbx+10h], rsi
0x14005edc5  test    rdx, rdx
0x14005edc8  jz      short loc_14005EDD8
0x14005edca  mov     r8d, 0C0000240h; int
0x14005edd0  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14005edd3  call    ?ExtSTACompleteConnection@@YAXPEAUEXTSTA_VELAN@@PEAU_IRP@@J@Z; ExtSTACompleteConnection(EXTSTA_VELAN *,_IRP *,long)
0x14005edd8  mov     rcx, rbx
0x14005eddb  call    ExtSTAUpcallDisconnect
0x14005ede0  mov     rcx, [rbx+2F0h]
0x14005ede7  test    rcx, rcx
0x14005edea  jz      short loc_14005EE22
0x14005edec  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14005edf0  mov     rax, [rcx]
0x14005edf3  test    rax, rax
0x14005edf6  jz      short loc_14005EE0C
0x14005edf8  mov     rdx, rcx; Entry
0x14005edfb  mov     rcx, rax; Lookaside
0x14005edfe  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005ee05  nop     dword ptr [rax+rax+00h]
0x14005ee0a  jmp     short loc_14005EE1B
0x14005ee0c  mov     edx, [rcx+8]; Tag
0x14005ee0f  call    cs:__imp_ExFreePoolWithTag
0x14005ee16  nop     dword ptr [rax+rax+00h]
0x14005ee1b  mov     [rbx+2F0h], rsi
0x14005ee22  mov     rcx, [rbx+0A38h]
0x14005ee29  lea     rdx, [rsp+28h+LockState]; LockState
0x14005ee2e  mov     rcx, [rcx+90h]; Lock
0x14005ee35  call    cs:__imp_NdisReleaseRWLock
0x14005ee3c  nop     dword ptr [rax+rax+00h]
0x14005ee41  mov     edi, 30D40h
0x14005ee46  jmp     short loc_14005EE56
0x14005ee48  mov     ecx, edi; MicrosecondsToSleep
0x14005ee4a  call    cs:__imp_NdisMSleep
0x14005ee51  nop     dword ptr [rax+rax+00h]
0x14005ee56  cmp     [rbx+2ECh], esi
0x14005ee5c  jnz     short loc_14005EE48
0x14005ee5e  jmp     short loc_14005EE6E
0x14005ee60  mov     ecx, edi; MicrosecondsToSleep
0x14005ee62  call    cs:__imp_NdisMSleep
0x14005ee69  nop     dword ptr [rax+rax+00h]
0x14005ee6e  cmp     [rbx+330h], esi
0x14005ee74  jnz     short loc_14005EE60
0x14005ee76  mov     rcx, [rbx+0A38h]
0x14005ee7d  lea     rdx, [rsp+28h+LockState]; LockState
0x14005ee82  xor     r8d, r8d; Flags
0x14005ee85  mov     rdi, rsi
0x14005ee88  mov     rcx, [rcx+90h]; Lock
0x14005ee8f  call    cs:__imp_NdisAcquireRWLockWrite
0x14005ee96  nop     dword ptr [rax+rax+00h]
0x14005ee9b  cmp     [rbx+2F8h], rsi
0x14005eea2  jz      short loc_14005EEBA
0x14005eea4  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14005eea7  call    ?ExtSTACancelConnRoamingTimer@@YAEPEAUEXTSTA_VELAN@@@Z; ExtSTACancelConnRoamingTimer(EXTSTA_VELAN *)
0x14005eeac  mov     rdi, [rbx+2F8h]
0x14005eeb3  mov     [rbx+2F8h], rsi
0x14005eeba  mov     rcx, [rbx+0A38h]
0x14005eec1  lea     rdx, [rsp+28h+LockState]; LockState
0x14005eec6  mov     rcx, [rcx+90h]; Lock
0x14005eecd  call    cs:__imp_NdisReleaseRWLock
0x14005eed4  nop     dword ptr [rax+rax+00h]
0x14005eed9  test    rdi, rdi
0x14005eedc  jz      short loc_14005EEED
0x14005eede  mov     rcx, rdi; TimerObject
0x14005eee1  call    cs:__imp_NdisFreeTimerObject
0x14005eee8  nop     dword ptr [rax+rax+00h]
0x14005eeed  mov     [rbx+148h], rsi
0x14005eef4  mov     [rbx+150h], esi
0x14005eefa  mov     [rbx+194h], esi
0x14005ef00  mov     [rbx+19Ch], esi
0x14005ef06  and     dword ptr [rbx+610h], 0FFFFFFFBh
0x14005ef0d  and     dword ptr [rbx+8], 0FFFFFFF7h
0x14005ef11  mov     rbx, [rsp+28h+arg_8]
0x14005ef16  mov     rsi, [rsp+28h+arg_10]
0x14005ef1b  add     rsp, 20h
0x14005ef1f  pop     rdi
0x14005ef20  retn
```

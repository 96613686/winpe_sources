# PtDeallocateVElan(_VELAN *)

- ea: `0x140024944`
- end: `0x140024bad`
- name: `?PtDeallocateVElan@@YAXPEAU_VELAN@@@Z`
- size: `617`
- prototype: `void __fastcall(struct _VELAN *)`
- caller_count: `13`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14001f28c`
- `0x140020b98`
- `0x140033374`
- `0x1400353c0`
- `0x140036000`
- `0x140037a10`
- `0x140037d30`
- `0x140037eac`
- `0x14003c2a0`
- `0x14003d934`
- `0x14003eb90`
- `0x140056e70`
- `0x14005d660`

## callees

- `0x14000d21c`
- `0x140020fbc`
- `0x140024944`
- `0x140024bb4`
- `0x140025704`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024b0b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024b68`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024b0b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024b68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b79`
- `NDIS!NdisFreeRWLock` at `0x140024b3f`
- `NDIS!NdisFreeRWLock` at `0x140024b3f`
- `NDIS!NdisFreeTimerObject` at `0x1400249aa`
- `NDIS!NdisFreeTimerObject` at `0x1400249aa`
- `NDIS!NdisFreeNetBufferPool` at `0x140024a72`
- `NDIS!NdisFreeNetBufferPool` at `0x140024a9c`
- `NDIS!NdisFreeNetBufferPool` at `0x140024a72`
- `NDIS!NdisFreeNetBufferPool` at `0x140024a9c`
- `NDIS!NdisFreeNetBufferListPool` at `0x140024a5d`
- `NDIS!NdisFreeNetBufferListPool` at `0x140024a87`
- `NDIS!NdisFreeNetBufferListPool` at `0x140024a5d`
- `NDIS!NdisFreeNetBufferListPool` at `0x140024a87`
- `NDIS!NdisMSleep` at `0x140024a38`
- `NDIS!NdisMSleep` at `0x140024ab6`
- `NDIS!NdisMSleep` at `0x140024a38`
- `NDIS!NdisMSleep` at `0x140024ab6`

## pseudocode

```c
void __fastcall PtDeallocateVElan(struct _VELAN *a1, unsigned int a2)
{
  DOT11_MAC_STATE_ENTRY *pDefaultMacState; // rax
  void *hSendNetBufferListPool; // rcx
  void *hSendNetBufferPool; // rcx
  void *hRecvNetBufferListPool; // rcx
  void *hRecvNetBufferPool; // rcx
  struct SAE_CONNECTION_CONTEXT *pSaeConnection; // rdi
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids);
  if ( a1->hRoamingNBLTimer )
  {
    if ( a1->bRoamingMode && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids);
    NdisFreeTimerObject(a1->hRoamingNBLTimer);
    a1->hRoamingNBLTimer = 0;
  }
  pDefaultMacState = a1->pDefaultMacState;
  if ( pDefaultMacState )
  {
    if ( (pDefaultMacState->uObjCnt != 1 || pDefaultMacState->uRefCnt != 1)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids);
    }
    if ( (a1->ModuleStatus.uValue & 2) == 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids);
    Dot11DecObjCnt(&a1->pDefaultMacState, a2);
  }
  if ( (a1->ModuleStatus.uValue & 2) != 0 )
  {
    while ( a1->MacStateTable.uNumPendingDeletingEntries )
      NdisMSleep(0x4E20u);
    a1->ModuleStatus.uValue &= ~2u;
  }
  hSendNetBufferListPool = a1->hSendNetBufferListPool;
  if ( hSendNetBufferListPool )
    NdisFreeNetBufferListPool(hSendNetBufferListPool);
  hSendNetBufferPool = a1->hSendNetBufferPool;
  if ( hSendNetBufferPool )
    NdisFreeNetBufferPool(hSendNetBufferPool);
  hRecvNetBufferListPool = a1->hRecvNetBufferListPool;
  if ( hRecvNetBufferListPool )
    NdisFreeNetBufferListPool(hRecvNetBufferListPool);
  hRecvNetBufferPool = a1->hRecvNetBufferPool;
  if ( hRecvNetBufferPool )
    NdisFreeNetBufferPool(hRecvNetBufferPool);
  if ( (a1->ModuleStatus.uValue & 1) != 0 )
  {
    while ( a1->IoctlModule.bWorkItemQueued )
      NdisMSleep(0x4E20u);
    a1->ModuleStatus.uValue &= ~1u;
  }
  if ( a1->pOWEContext )
    Dot11DeallocateOWEContext(&a1->pOWEContext);
  pSaeConnection = a1->pSaeConnection;
  if ( pSaeConnection )
  {
    SaeAuthContextManager::~SaeAuthContextManager((struct SAE_CONNECTION_CONTEXT *)((char *)pSaeConnection + 16));
    if ( *((_QWORD *)pSaeConnection - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)pSaeConnection - 2), (char *)pSaeConnection - 16);
    else
      ExFreePoolWithTag((char *)pSaeConnection - 16, *((_DWORD *)pSaeConnection - 2));
    a1->pSaeConnection = 0;
  }
  pRWLock = a1->pRWLock;
  if ( pRWLock )
  {
    NdisFreeRWLock(pRWLock);
    a1->pRWLock = 0;
  }
  if ( a1[-1].pOWEContext )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)a1[-1].pOWEContext, &a1[-1].pOWEContext);
  else
    ExFreePoolWithTag(&a1[-1].pOWEContext, (ULONG)a1[-1].pSaeConnection);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids);
}

```

## disassembly

```asm
0x140024944  push    rbx
0x140024946  push    rbp
0x140024947  push    rdi
0x140024948  push    r14
0x14002494a  sub     rsp, 28h
0x14002494e  mov     rbx, rcx
0x140024951  mov     rcx, cs:WPP_GLOBAL_Control
0x140024958  lea     rbp, WPP_GLOBAL_Control
0x14002495f  lea     r14, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x140024966  cmp     rcx, rbp
0x140024969  jz      short loc_14002497C
0x14002496b  mov     rcx, [rcx+18h]
0x14002496f  mov     edx, 2Bh ; '+'
0x140024974  mov     r8, r14
0x140024977  call    WPP_SF_
0x14002497c  cmp     qword ptr [rbx+78h], 0
0x140024981  jz      short loc_1400249BE
0x140024983  cmp     dword ptr [rbx+50h], 0
0x140024987  jz      short loc_1400249A6
0x140024989  mov     rcx, cs:WPP_GLOBAL_Control
0x140024990  cmp     rcx, rbp
0x140024993  jz      short loc_1400249A6
0x140024995  mov     rcx, [rcx+18h]
0x140024999  mov     edx, 2Ch ; ','
0x14002499e  mov     r8, r14
0x1400249a1  call    WPP_SF_
0x1400249a6  mov     rcx, [rbx+78h]; TimerObject
0x1400249aa  call    cs:__imp_NdisFreeTimerObject
0x1400249b1  nop     dword ptr [rax+rax+00h]
0x1400249b6  mov     qword ptr [rbx+78h], 0
0x1400249be  lea     rdi, [rbx+10D0h]
0x1400249c5  mov     rax, [rdi]
0x1400249c8  test    rax, rax
0x1400249cb  jz      short loc_140024A25
0x1400249cd  cmp     dword ptr [rax+20h], 1
0x1400249d1  jnz     short loc_1400249D9
0x1400249d3  cmp     dword ptr [rax+24h], 1
0x1400249d7  jz      short loc_1400249F6
0x1400249d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400249e0  cmp     rcx, rbp
0x1400249e3  jz      short loc_1400249F6
0x1400249e5  mov     rcx, [rcx+18h]
0x1400249e9  mov     edx, 2Dh ; '-'
0x1400249ee  mov     r8, r14
0x1400249f1  call    WPP_SF_
0x1400249f6  mov     eax, [rbx+1538h]
0x1400249fc  test    al, 2
0x1400249fe  jnz     short loc_140024A1D
0x140024a00  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a07  cmp     rcx, rbp
0x140024a0a  jz      short loc_140024A1D
0x140024a0c  mov     rcx, [rcx+18h]
0x140024a10  mov     edx, 2Eh ; '.'
0x140024a15  mov     r8, r14
0x140024a18  call    WPP_SF_
0x140024a1d  mov     rcx, rdi; struct DOT11_MAC_STATE_ENTRY **
0x140024a20  call    ?Dot11DecObjCnt@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@K@Z; Dot11DecObjCnt(DOT11_MAC_STATE_ENTRY * *,ulong)
0x140024a25  mov     eax, [rbx+1538h]
0x140024a2b  mov     edi, 4E20h
0x140024a30  test    al, 2
0x140024a32  jz      short loc_140024A54
0x140024a34  jmp     short loc_140024A44
0x140024a36  mov     ecx, edi; MicrosecondsToSleep
0x140024a38  call    cs:__imp_NdisMSleep
0x140024a3f  nop     dword ptr [rax+rax+00h]
0x140024a44  cmp     dword ptr [rbx+10C8h], 0
0x140024a4b  jnz     short loc_140024A36
0x140024a4d  and     dword ptr [rbx+1538h], 0FFFFFFFDh
0x140024a54  mov     rcx, [rbx+30h]; PoolHandle
0x140024a58  test    rcx, rcx
0x140024a5b  jz      short loc_140024A69
0x140024a5d  call    cs:__imp_NdisFreeNetBufferListPool
0x140024a64  nop     dword ptr [rax+rax+00h]
0x140024a69  mov     rcx, [rbx+38h]; PoolHandle
0x140024a6d  test    rcx, rcx
0x140024a70  jz      short loc_140024A7E
0x140024a72  call    cs:__imp_NdisFreeNetBufferPool
0x140024a79  nop     dword ptr [rax+rax+00h]
0x140024a7e  mov     rcx, [rbx+40h]; PoolHandle
0x140024a82  test    rcx, rcx
0x140024a85  jz      short loc_140024A93
0x140024a87  call    cs:__imp_NdisFreeNetBufferListPool
0x140024a8e  nop     dword ptr [rax+rax+00h]
0x140024a93  mov     rcx, [rbx+48h]; PoolHandle
0x140024a97  test    rcx, rcx
0x140024a9a  jz      short loc_140024AA8
0x140024a9c  call    cs:__imp_NdisFreeNetBufferPool
0x140024aa3  nop     dword ptr [rax+rax+00h]
0x140024aa8  mov     eax, [rbx+1538h]
0x140024aae  test    al, 1
0x140024ab0  jz      short loc_140024AD2
0x140024ab2  jmp     short loc_140024AC2
0x140024ab4  mov     ecx, edi; MicrosecondsToSleep
0x140024ab6  call    cs:__imp_NdisMSleep
0x140024abd  nop     dword ptr [rax+rax+00h]
0x140024ac2  cmp     dword ptr [rbx+15BCh], 0
0x140024ac9  jnz     short loc_140024AB4
0x140024acb  and     dword ptr [rbx+1538h], 0FFFFFFFEh
0x140024ad2  lea     rcx, [rbx+2170h]; struct _OWE_CONTEXT **
0x140024ad9  cmp     qword ptr [rcx], 0
0x140024add  jz      short loc_140024AE4
0x140024adf  call    ?Dot11DeallocateOWEContext@@YAXPEAPEAU_OWE_CONTEXT@@@Z; Dot11DeallocateOWEContext(_OWE_CONTEXT * *)
0x140024ae4  mov     rdi, [rbx+2178h]
0x140024aeb  test    rdi, rdi
0x140024aee  jz      short loc_140024B33
0x140024af0  lea     rcx, [rdi+10h]; this
0x140024af4  call    ??1SaeAuthContextManager@@QEAA@XZ; SaeAuthContextManager::~SaeAuthContextManager(void)
0x140024af9  lea     rcx, [rdi-10h]; P
0x140024afd  mov     rax, [rcx]
0x140024b00  test    rax, rax
0x140024b03  jz      short loc_140024B19
0x140024b05  mov     rdx, rcx; Entry
0x140024b08  mov     rcx, rax; Lookaside
0x140024b0b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140024b12  nop     dword ptr [rax+rax+00h]
0x140024b17  jmp     short loc_140024B28
0x140024b19  mov     edx, [rcx+8]; Tag
0x140024b1c  call    cs:__imp_ExFreePoolWithTag
0x140024b23  nop     dword ptr [rax+rax+00h]
0x140024b28  mov     qword ptr [rbx+2178h], 0
0x140024b33  mov     rcx, [rbx+90h]; Lock
0x140024b3a  test    rcx, rcx
0x140024b3d  jz      short loc_140024B56
0x140024b3f  call    cs:__imp_NdisFreeRWLock
0x140024b46  nop     dword ptr [rax+rax+00h]
0x140024b4b  mov     qword ptr [rbx+90h], 0
0x140024b56  lea     rcx, [rbx-10h]; P
0x140024b5a  mov     rax, [rcx]
0x140024b5d  test    rax, rax
0x140024b60  jz      short loc_140024B76
0x140024b62  mov     rdx, rcx; Entry
0x140024b65  mov     rcx, rax; Lookaside
0x140024b68  call    cs:__imp_ExFreeToNPagedLookasideList
0x140024b6f  nop     dword ptr [rax+rax+00h]
0x140024b74  jmp     short loc_140024B85
0x140024b76  mov     edx, [rcx+8]; Tag
0x140024b79  call    cs:__imp_ExFreePoolWithTag
0x140024b80  nop     dword ptr [rax+rax+00h]
0x140024b85  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b8c  cmp     rcx, rbp
0x140024b8f  jz      short loc_140024BA2
0x140024b91  mov     rcx, [rcx+18h]
0x140024b95  mov     edx, 2Fh ; '/'
0x140024b9a  mov     r8, r14
0x140024b9d  call    WPP_SF_
0x140024ba2  add     rsp, 28h
0x140024ba6  pop     r14
0x140024ba8  pop     rdi
0x140024ba9  pop     rbp
0x140024baa  pop     rbx
0x140024bab  retn
```

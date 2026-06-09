# MRxDAVOuterStop

- ea: `0x140010168`
- end: `0x140010452`
- name: `MRxDAVOuterStop`
- size: `746`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000f120`

## callees

- `0x140001188`
- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140005554`
- `0x140010168`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140010199`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400101d5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010213`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001031b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010385`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400103c1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010412`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010199`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400101d5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010213`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001031b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010385`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400103c1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010412`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400102ed`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400102ed`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400103f0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140028e5c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400103f0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140028e5c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010258`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010258`
- `ntoskrnl!KeReadStateTimer` at `0x14001027f`
- `ntoskrnl!KeReadStateTimer` at `0x14001027f`
- `ntoskrnl!KeSetTimerEx` at `0x14001029e`
- `ntoskrnl!KeSetTimerEx` at `0x14001029e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400102b1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400102da`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400102b1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400102da`
- `rdbss!RxStopMinirdr` at `0x140010353`
- `rdbss!RxStopMinirdr` at `0x140010353`

## pseudocode

```c
__int64 __fastcall MRxDAVOuterStop(PRX_CONTEXT RxContext)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  int RdbssDbgExtension; // eax
  PNON_PAGED_FCB NonPagedFcb; // rbx
  __int64 v10; // rbx
  HANDLE v11; // rax
  unsigned int v12; // edi
  __int64 v13; // rbx
  HANDLE v14; // rax
  __int64 v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // rbx
  HANDLE v18; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v2, 34, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, CurrentThreadId);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v5 = PsGetCurrentThreadId();
    WPP_SF_qq(v4, 35, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v5, RxContext);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v7 = PsGetCurrentThreadId();
    WPP_SF_q(v6, 36, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v7);
  }
  RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
  if ( (RdbssDbgExtension & 0x200) != 0 )
  {
    if ( (RdbssDbgExtension & 2) == 0 )
      __int2c();
    NonPagedFcb = RxContext->NonPagedFcb;
    ExAcquireResourceExclusiveLite(&MRxDAVTimerThreadLock, 1u);
    if ( TimerThreadShutDown )
    {
      ExReleaseResourceLite(&MRxDAVTimerThreadLock);
    }
    else
    {
      TimerThreadShutDown = 1;
      if ( !KeReadStateTimer(&DavTimerObject) )
        KeSetTimerEx(&DavTimerObject, 0, 0, 0);
      ExReleaseResourceLite(&MRxDAVTimerThreadLock);
      MRxDAVCleanUpTheLockConflictList(1);
      MRxDAVTimeOutTheContexts(1);
    }
    ExAcquireFastMutexUnsafe(&MRxDAVSerializationMutex);
    if ( LOBYTE(NonPagedFcb[3].PagingIoResource.Reserved2) )
    {
      v12 = RxStopMinirdr(RxContext, (PBOOLEAN)&RxContext->RealDevice + 3);
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v16 = PsGetCurrentThreadId();
          WPP_SF_qD(v15, 39, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v16, v12);
        }
      }
      else
      {
        LOBYTE(NonPagedFcb[3].PagingIoResource.Reserved2) = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v14 = PsGetCurrentThreadId();
          WPP_SF_q(v13, 38, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v14);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v11 = PsGetCurrentThreadId();
        WPP_SF_q(v10, 37, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v11);
      }
      v12 = -1073741573;
    }
    ExReleaseFastMutexUnsafe(&MRxDAVSerializationMutex);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v18 = PsGetCurrentThreadId();
      WPP_SF_qD(v17, 40, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v18, v12);
    }
    return v12;
  }
  else
  {
    BYTE3(RxContext->RealDevice) = 1;
    return 3225485315LL;
  }
}

```

## disassembly

```asm
0x140010168  push    rbx
0x14001016a  push    rdi
0x14001016b  push    r14
0x14001016d  push    r15
0x14001016f  sub     rsp, 48h
0x140010173  mov     rdi, rcx
0x140010176  lea     r15, WPP_GLOBAL_Control
0x14001017d  mov     rbx, cs:WPP_GLOBAL_Control
0x140010184  mov     r14d, 4000h
0x14001018a  cmp     rbx, r15
0x14001018d  jz      short loc_1400101BC
0x14001018f  test    [rbx+2Ch], r14d
0x140010193  jz      short loc_1400101BC
0x140010195  mov     rbx, [rbx+18h]
0x140010199  call    cs:__imp_PsGetCurrentThreadId
0x1400101a0  nop     dword ptr [rax+rax+00h]
0x1400101a5  mov     r9, rax
0x1400101a8  mov     edx, 22h ; '"'
0x1400101ad  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x1400101b4  mov     rcx, rbx
0x1400101b7  call    WPP_SF_q
0x1400101bc  mov     rbx, cs:WPP_GLOBAL_Control
0x1400101c3  cmp     rbx, r15
0x1400101c6  jz      short loc_1400101FD
0x1400101c8  test    dword ptr [rbx+2Ch], 2000h
0x1400101cf  jz      short loc_1400101FD
0x1400101d1  mov     rbx, [rbx+18h]
0x1400101d5  call    cs:__imp_PsGetCurrentThreadId
0x1400101dc  nop     dword ptr [rax+rax+00h]
0x1400101e1  mov     r9, rax
0x1400101e4  mov     edx, 23h ; '#'
0x1400101e9  mov     [rsp+68h+var_48], rdi
0x1400101ee  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x1400101f5  mov     rcx, rbx
0x1400101f8  call    WPP_SF_qq
0x1400101fd  mov     rbx, cs:WPP_GLOBAL_Control
0x140010204  cmp     rbx, r15
0x140010207  jz      short loc_140010236
0x140010209  test    [rbx+2Ch], r14d
0x14001020d  jz      short loc_140010236
0x14001020f  mov     rbx, [rbx+18h]
0x140010213  call    cs:__imp_PsGetCurrentThreadId
0x14001021a  nop     dword ptr [rax+rax+00h]
0x14001021f  mov     r9, rax
0x140010222  mov     edx, 24h ; '$'
0x140010227  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14001022e  mov     rcx, rbx
0x140010231  call    WPP_SF_q
0x140010236  mov     eax, [rdi+78h]
0x140010239  bt      eax, 9
0x14001023d  jnb     loc_14001043D
0x140010243  bt      eax, 1
0x140010247  jb      short loc_14001024B
0x140010249  int     2Ch; Windows NT - assertion failure
0x14001024b  mov     rbx, [rdi+50h]
0x14001024f  mov     dl, 1; Wait
0x140010251  lea     rcx, MRxDAVTimerThreadLock; Resource
0x140010258  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001025f  nop     dword ptr [rax+rax+00h]
0x140010264  mov     eax, cs:TimerThreadShutDown
0x14001026a  test    eax, eax
0x14001026c  jnz     short loc_1400102D3
0x14001026e  mov     cs:TimerThreadShutDown, 1
0x140010278  lea     rcx, DavTimerObject; Timer
0x14001027f  call    cs:__imp_KeReadStateTimer
0x140010286  nop     dword ptr [rax+rax+00h]
0x14001028b  test    al, al
0x14001028d  jnz     short loc_1400102AA
0x14001028f  xor     edx, edx; DueTime
0x140010291  xor     r9d, r9d; Dpc
0x140010294  xor     r8d, r8d; Period
0x140010297  lea     rcx, DavTimerObject; Timer
0x14001029e  call    cs:__imp_KeSetTimerEx
0x1400102a5  nop     dword ptr [rax+rax+00h]
0x1400102aa  lea     rcx, MRxDAVTimerThreadLock; Resource
0x1400102b1  call    cs:__imp_ExReleaseResourceLite
0x1400102b8  nop     dword ptr [rax+rax+00h]
0x1400102bd  mov     ecx, 1
0x1400102c2  call    MRxDAVCleanUpTheLockConflictList
0x1400102c7  mov     ecx, 1
0x1400102cc  call    MRxDAVTimeOutTheContexts
0x1400102d1  jmp     short loc_1400102E6
0x1400102d3  lea     rcx, MRxDAVTimerThreadLock; Resource
0x1400102da  call    cs:__imp_ExReleaseResourceLite
0x1400102e1  nop     dword ptr [rax+rax+00h]
0x1400102e6  lea     rcx, MRxDAVSerializationMutex; FastMutex
0x1400102ed  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400102f4  nop     dword ptr [rax+rax+00h]
0x1400102f9  nop
0x1400102fa  cmp     byte ptr [rbx+660h], 0
0x140010301  jnz     short loc_14001034C
0x140010303  mov     rbx, cs:WPP_GLOBAL_Control
0x14001030a  cmp     rbx, r15
0x14001030d  jz      short loc_14001033E
0x14001030f  mov     eax, [rbx+2Ch]
0x140010312  test    r14d, eax
0x140010315  jz      short loc_14001033E
0x140010317  mov     rbx, [rbx+18h]
0x14001031b  call    cs:__imp_PsGetCurrentThreadId
0x140010322  nop     dword ptr [rax+rax+00h]
0x140010327  mov     r9, rax
0x14001032a  mov     edx, 25h ; '%'
0x14001032f  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x140010336  mov     rcx, rbx
0x140010339  call    WPP_SF_q
0x14001033e  mov     edi, 0C00000FBh
0x140010343  mov     [rsp+68h+var_38], edi
0x140010347  jmp     loc_1400103E9
0x14001034c  lea     rdx, [rdi+23h]; PostToFsp
0x140010350  mov     rcx, rdi; RxContext
0x140010353  call    cs:__imp_RxStopMinirdr
0x14001035a  nop     dword ptr [rax+rax+00h]
0x14001035f  mov     edi, eax
0x140010361  mov     [rsp+68h+var_38], eax
0x140010365  test    eax, eax
0x140010367  jnz     short loc_1400103A8
0x140010369  mov     [rbx+660h], al
0x14001036f  mov     rbx, cs:WPP_GLOBAL_Control
0x140010376  cmp     rbx, r15
0x140010379  jz      short loc_1400103E9
0x14001037b  test    [rbx+2Ch], r14d
0x14001037f  jz      short loc_1400103E9
0x140010381  mov     rbx, [rbx+18h]
0x140010385  call    cs:__imp_PsGetCurrentThreadId
0x14001038c  nop     dword ptr [rax+rax+00h]
0x140010391  mov     r9, rax
0x140010394  lea     edx, [rdi+26h]
0x140010397  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14001039e  mov     rcx, rbx
0x1400103a1  call    WPP_SF_q
0x1400103a6  jmp     short loc_1400103E9
0x1400103a8  mov     rbx, cs:WPP_GLOBAL_Control
0x1400103af  cmp     rbx, r15
0x1400103b2  jz      short loc_1400103E9
0x1400103b4  mov     eax, [rbx+2Ch]
0x1400103b7  bt      eax, 0Dh
0x1400103bb  jnb     short loc_1400103E9
0x1400103bd  mov     rbx, [rbx+18h]
0x1400103c1  call    cs:__imp_PsGetCurrentThreadId
0x1400103c8  nop     dword ptr [rax+rax+00h]
0x1400103cd  mov     r9, rax
0x1400103d0  mov     edx, 27h ; '''
0x1400103d5  mov     dword ptr [rsp+68h+var_48], edi
0x1400103d9  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x1400103e0  mov     rcx, rbx
0x1400103e3  call    WPP_SF_qD
0x1400103e8  nop
0x1400103e9  lea     rcx, MRxDAVSerializationMutex; FastMutex
0x1400103f0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400103f7  nop     dword ptr [rax+rax+00h]
0x1400103fc  mov     rbx, cs:WPP_GLOBAL_Control
0x140010403  cmp     rbx, r15
0x140010406  jz      short loc_140010439
0x140010408  test    [rbx+2Ch], r14d
0x14001040c  jz      short loc_140010439
0x14001040e  mov     rbx, [rbx+18h]
0x140010412  call    cs:__imp_PsGetCurrentThreadId
0x140010419  nop     dword ptr [rax+rax+00h]
0x14001041e  mov     r9, rax
0x140010421  mov     edx, 28h ; '('
0x140010426  mov     dword ptr [rsp+68h+var_48], edi
0x14001042a  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x140010431  mov     rcx, rbx
0x140010434  call    WPP_SF_qD
0x140010439  mov     eax, edi
0x14001043b  jmp     short loc_140010446
0x14001043d  mov     byte ptr [rdi+23h], 1
0x140010441  mov     eax, 0C0410003h
0x140010446  add     rsp, 48h
0x14001044a  pop     r15
0x14001044c  pop     r14
0x14001044e  pop     rdi
0x14001044f  pop     rbx
0x140010450  retn
0x140028e4c  push    rbp
0x140028e4e  sub     rsp, 30h
0x140028e52  mov     rbp, rdx
0x140028e55  lea     rcx, MRxDAVSerializationMutex; FastMutex
0x140028e5c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140028e63  nop     dword ptr [rax+rax+00h]
0x140028e68  nop
0x140028e69  add     rsp, 30h
0x140028e6d  pop     rbp
0x140028e6e  retn
```

# VidSchTerminateAdapter

- ea: `0x1400ac500`
- end: `0x1400acb06`
- name: `VidSchTerminateAdapter`
- size: `1542`
- prototype: `__int64 __fastcall(_VIDSCH_GLOBAL *this)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400af270`
- `0x1400dd584`

## callees

- `0x140004d60`
- `0x140009790`
- `0x1400098c0`
- `0x14002ee90`
- `0x14002ef70`
- `0x140030ae0`
- `0x140030e28`
- `0x140032898`
- `0x14003e9d8`
- `0x140042b8c`
- `0x1400aada0`
- `0x1400aba50`
- `0x1400ac500`
- `0x1400b0b74`
- `0x1400d97e0`
- `0x1401149e0`
- `0x14011c9a0`
- `0x14011ef14`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400aca4d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400aca95`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400aca4d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400aca95`
- `ntoskrnl!ObfReferenceObject` at `0x1400ac5ad`
- `ntoskrnl!ObfReferenceObject` at `0x1400ac5ad`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ac5e8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400acad0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ac5e8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400acad0`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400ac65e`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400ac65e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ac685`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ac685`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400ac9d2`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400ac9e5`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400ac9f8`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400aca0b`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400aca1e`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400aca31`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400ac9d2`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400ac9e5`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400ac9f8`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400aca0b`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400aca1e`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400aca31`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400acade`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400acade`
- `ntoskrnl!ExDeleteTimer` at `0x1400ac865`
- `ntoskrnl!ExDeleteTimer` at `0x1400ac865`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ac5d9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400aca79`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ac5d9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400aca79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac6ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac71b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac768`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac7b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac967`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac988`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac9ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400acabc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac6ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac71b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac768`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac7b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac967`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac988`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ac9ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400acabc`

## pseudocode

```c
__int64 __fastcall VidSchTerminateAdapter(_VIDSCH_GLOBAL *this)
{
  _QWORD *v2; // rbx
  __int64 v3; // rcx
  _QWORD *v4; // rax
  int v5; // r14d
  __int64 v6; // rdx
  void *v7; // rbx
  unsigned int i; // ebx
  unsigned int j; // ebx
  struct _VIDSCH_CONTEXT *v10; // rcx
  unsigned int k; // ebx
  struct _VIDSCH_CONTEXT *v12; // rcx
  unsigned int m; // ebx
  struct VIDSCH_HW_QUEUE *v14; // rcx
  unsigned int n; // ebx
  void *v16; // rcx
  void *v17; // rcx
  unsigned int ii; // ebx
  __int64 *v19; // rsi
  __int64 v20; // rsi
  struct _VIDSCH_CONTEXT *v21; // rcx
  struct _VIDSCH_CONTEXT *v22; // rcx
  void *v23; // rcx
  __int64 v24; // rcx
  unsigned int jj; // ebx
  PVOID *v26; // rax
  _QWORD *v27; // rcx
  unsigned int v28; // ebp
  char *v29; // rcx
  char *v30; // rbx
  unsigned int kk; // ebx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rbx
  _BYTE v36[32]; // [rsp+30h] [rbp-48h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+80h] [rbp+8h] BYREF

  if ( this )
  {
    v2 = (_QWORD *)((char *)this + 3888);
    if ( *((_QWORD *)this + 486) )
    {
      DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(
        (DXGAUTOEXPUSHLOCKEXCLUSIVE *)v36,
        (struct _EX_PUSH_LOCK *const)&gAdapterListLock);
      v3 = *v2;
      if ( *(_QWORD **)(*v2 + 8LL) != v2 || (v4 = (_QWORD *)v2[1], (_QWORD *)*v4 != v2) )
        __fastfail(3u);
      *v4 = v3;
      *(_QWORD *)(v3 + 8) = v4;
      *(_OWORD *)v2 = 0;
      DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v36);
    }
    v5 = 0;
    if ( (unsigned __int8)VidSchiAcceptsIncomingWork(this) )
    {
      if ( !(unsigned __int8)VidSchIsWorkerThread() )
      {
        VidSchFlushAdapter(this);
        v7 = (void *)*((_QWORD *)this + 22);
        ObfReferenceObject(v7);
        VidSchiRequestSchedulerStatus(this, 2, 0);
        KeWaitForSingleObject(v7, Executive, 0, 0, 0);
        ObfDereferenceObject(v7);
        return 0;
      }
      VidSchFlushAdapter(this);
      for ( i = 0; i < *((_DWORD *)this + 12); ++i )
      {
        if ( *((_DWORD *)this + i + 548) )
        {
          *((_DWORD *)this + i + 548) = 1;
          VidSchControlVSyncAdapter(this);
        }
      }
      VidSchiBlockDriverCallback(this);
      while ( *((_DWORD *)this + 658) )
      {
        Interval.QuadPart = -1000000;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      if ( (*((_DWORD *)this + 726) & 2) != 0 )
        ExReleaseResourceLite((PERESOURCE)((char *)this + 1232));
      v5 = 1;
    }
    if ( *((_QWORD *)this + 44) )
    {
      for ( j = 0; j < *((_DWORD *)this + 21); ++j )
      {
        v10 = *(struct _VIDSCH_CONTEXT **)(*((_QWORD *)this + 44) + 8LL * j);
        if ( v10 )
          VidSchTerminateContext(v10);
      }
      ExFreePoolWithTag(*((PVOID *)this + 44), 0);
      *((_QWORD *)this + 44) = 0;
    }
    if ( *((_QWORD *)this + 41) )
    {
      for ( k = 0; k < *((_DWORD *)this + 21); ++k )
      {
        v12 = *(struct _VIDSCH_CONTEXT **)(*((_QWORD *)this + 41) + 8LL * k);
        if ( v12 )
          VidSchTerminateContext(v12);
      }
      ExFreePoolWithTag(*((PVOID *)this + 41), 0);
      *((_QWORD *)this + 41) = 0;
    }
    if ( *((_QWORD *)this + 43) )
    {
      for ( m = 0; m < *((_DWORD *)this + 21); ++m )
      {
        v14 = *(struct VIDSCH_HW_QUEUE **)(*((_QWORD *)this + 43) + 8LL * m);
        if ( v14 )
          VidSchTerminateHwQueue(v14);
      }
      ExFreePoolWithTag(*((PVOID *)this + 43), 0);
      *((_QWORD *)this + 43) = 0;
    }
    if ( *((_QWORD *)this + 42) )
    {
      for ( n = 0; n < *((_DWORD *)this + 21); ++n )
      {
        v16 = *(void **)(*((_QWORD *)this + 42) + 8LL * n);
        if ( v16 )
          VidSchTerminateHwContext(v16);
      }
      ExFreePoolWithTag(*((PVOID *)this + 42), 0);
      *((_QWORD *)this + 42) = 0;
    }
    v17 = (void *)*((_QWORD *)this + 40);
    if ( v17 )
    {
      VidSchTerminateDevice(v17);
      *((_QWORD *)this + 40) = 0;
    }
    for ( ii = 0; ii < *((_DWORD *)this + 22); ++ii )
    {
      v19 = (__int64 *)*((_QWORD *)this + 97);
      if ( ii < *((_DWORD *)this + 212) )
        v19 += ii;
      v20 = *v19;
      if ( v20 )
      {
        v21 = *(struct _VIDSCH_CONTEXT **)(v20 + 32);
        if ( v21 )
        {
          VidSchTerminateContext(v21);
          *(_QWORD *)(v20 + 32) = 0;
        }
      }
    }
    v22 = (struct _VIDSCH_CONTEXT *)*((_QWORD *)this + 34);
    if ( v22 )
    {
      VidSchTerminateContext(v22);
      *((_QWORD *)this + 34) = 0;
    }
    v23 = (void *)*((_QWORD *)this + 33);
    if ( v23 )
    {
      VidSchTerminateDevice(v23);
      *((_QWORD *)this + 33) = 0;
    }
    v24 = *((_QWORD *)this + 25);
    if ( v24 )
    {
      LOBYTE(v6) = 1;
      ExDeleteTimer(v24, v6, 0, 0);
    }
    for ( jj = 0; jj < *((_DWORD *)this + 23); ++jj )
    {
      v26 = (PVOID *)*((_QWORD *)this + 97);
      if ( jj < *((_DWORD *)this + 212) )
        v26 += jj;
      if ( *v26 )
      {
        VidSchiTerminateNode(*v26);
        v27 = (_QWORD *)(*((_QWORD *)this + 97) + 8LL * jj);
        if ( jj >= *((_DWORD *)this + 212) )
          v27 = (_QWORD *)*((_QWORD *)this + 97);
        *v27 = 0;
      }
    }
    v28 = 0;
    for ( *((_DWORD *)this + 114) = 2; v28 < *((_DWORD *)this + 12); ++v28 )
    {
      if ( *((_QWORD *)this + v28 + 441) )
      {
        VidSchiClearPeriodicFrameNotifications(this, v28);
        v29 = *(char **)(*((_QWORD *)this + v28 + 441) + 136LL);
        if ( v29 )
        {
          v30 = v29 - 8;
          `vector destructor iterator'(
            v29,
            0x70u,
            *((_QWORD *)v29 - 1),
            (void (*)(void *))VIDSCH_FLIP_QUEUE_HISTORY_ENTRY::~VIDSCH_FLIP_QUEUE_HISTORY_ENTRY);
          operator delete(v30);
        }
        operator delete(*(void **)(*((_QWORD *)this + v28 + 441) + 44408LL));
        if ( !*((_BYTE *)this + 67) )
        {
          for ( kk = 0; kk < *((_DWORD *)this + 40); ++kk )
          {
            v32 = *(void **)(304LL * kk + *((_QWORD *)this + v28 + 441) + 432);
            if ( v32 )
              ExFreePoolWithTag(v32, 0);
          }
        }
        ExFreePoolWithTag(*((PVOID *)this + v28 + 441), 0);
        *((_QWORD *)this + v28 + 441) = 0;
      }
      v33 = (void *)*((_QWORD *)this + v28 + 948);
      if ( v33 )
      {
        ExFreePoolWithTag(v33, 0);
        *((_QWORD *)this + v28 + 948) = 0;
      }
    }
    ExDeleteResourceLite((PERESOURCE)((char *)this + 3208));
    ExDeleteResourceLite((PERESOURCE)((char *)this + 464));
    ExDeleteResourceLite((PERESOURCE)((char *)this + 1440));
    ExDeleteResourceLite((PERESOURCE)((char *)this + 1232));
    ExDeleteResourceLite((PERESOURCE)((char *)this + 1128));
    ExDeleteResourceLite((PERESOURCE)((char *)this + 1336));
    if ( *((_BYTE *)this + 7928) )
    {
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)this + 7808));
      if ( *((_VIDSCH_GLOBAL **)this + 972) != (_VIDSCH_GLOBAL *)((char *)this + 7776) )
        KeWaitForSingleObject((char *)this + 7904, Executive, 0, 0, 0);
    }
    if ( *((_BYTE *)this + 1120) )
    {
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)this + 1024));
      *((_BYTE *)this + 1120) = 0;
    }
    v34 = (void *)*((_QWORD *)this + 22);
    _VIDSCH_GLOBAL::~_VIDSCH_GLOBAL(this);
    ExFreePoolWithTag(this, 0);
    if ( v5 )
    {
      ObfDereferenceObject(v34);
      PsTerminateSystemThread(0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400ac500  mov     [rsp+arg_8], rbx
0x1400ac505  mov     [rsp+arg_10], rbp
0x1400ac50a  push    rsi
0x1400ac50b  push    rdi
0x1400ac50c  push    r12
0x1400ac50e  push    r14
0x1400ac510  push    r15
0x1400ac512  sub     rsp, 50h
0x1400ac516  xor     r15d, r15d
0x1400ac519  mov     rdi, rcx
0x1400ac51c  test    rcx, rcx
0x1400ac51f  jz      loc_1400ACAEA
0x1400ac525  lea     rbx, [rcx+0F30h]
0x1400ac52c  cmp     [rbx], r15
0x1400ac52f  jz      short loc_1400AC574
0x1400ac531  lea     rdx, gAdapterListLock; struct _EX_PUSH_LOCK *
0x1400ac538  lea     rcx, [rsp+78h+var_48]; this
0x1400ac53d  call    ??0DXGAUTOEXPUSHLOCKEXCLUSIVE@@QEAA@QEAU_EX_PUSH_LOCK@@@Z; DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(_EX_PUSH_LOCK * const)
0x1400ac542  mov     rcx, [rbx]
0x1400ac545  cmp     [rcx+8], rbx
0x1400ac549  jnz     loc_1400AC5F9
0x1400ac54f  mov     rax, [rbx+8]
0x1400ac553  cmp     [rax], rbx
0x1400ac556  jnz     loc_1400AC5F9
0x1400ac55c  mov     [rax], rcx
0x1400ac55f  xorps   xmm0, xmm0
0x1400ac562  mov     [rcx+8], rax
0x1400ac566  lea     rcx, [rsp+78h+var_48]; this
0x1400ac56b  movdqu  xmmword ptr [rbx], xmm0
0x1400ac56f  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x1400ac574  mov     rcx, rdi
0x1400ac577  mov     r14d, r15d
0x1400ac57a  call    VidSchiAcceptsIncomingWork
0x1400ac57f  mov     r12d, 1
0x1400ac585  test    al, al
0x1400ac587  jz      loc_1400AC694
0x1400ac58d  call    VidSchIsWorkerThread
0x1400ac592  lea     edx, [r12+10h]
0x1400ac597  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x1400ac59a  test    al, al
0x1400ac59c  jnz     short loc_1400AC600
0x1400ac59e  call    VidSchFlushAdapter
0x1400ac5a3  mov     rbx, [rdi+0B0h]
0x1400ac5aa  mov     rcx, rbx; Object
0x1400ac5ad  call    cs:__imp_ObfReferenceObject
0x1400ac5b4  nop     dword ptr [rax+rax+00h]
0x1400ac5b9  xor     r8d, r8d
0x1400ac5bc  lea     edx, [r12+1]
0x1400ac5c1  mov     rcx, rdi
0x1400ac5c4  call    VidSchiRequestSchedulerStatus
0x1400ac5c9  xor     r9d, r9d; Alertable
0x1400ac5cc  mov     [rsp+78h+Timeout], r15; Timeout
0x1400ac5d1  xor     r8d, r8d; WaitMode
0x1400ac5d4  xor     edx, edx; WaitReason
0x1400ac5d6  mov     rcx, rbx; Object
0x1400ac5d9  call    cs:__imp_KeWaitForSingleObject
0x1400ac5e0  nop     dword ptr [rax+rax+00h]
0x1400ac5e5  mov     rcx, rbx; Object
0x1400ac5e8  call    cs:__imp_ObfDereferenceObject
0x1400ac5ef  nop     dword ptr [rax+rax+00h]
0x1400ac5f4  jmp     loc_1400ACAEA
0x1400ac5f9  mov     ecx, 3
0x1400ac5fe  int     29h; Win8: RtlFailFast(ecx)
0x1400ac600  call    VidSchFlushAdapter
0x1400ac605  mov     ebx, r15d
0x1400ac608  cmp     [rdi+30h], r15d
0x1400ac60c  jbe     short loc_1400AC63C
0x1400ac60e  mov     eax, ebx
0x1400ac610  cmp     [rdi+rax*4+890h], r15d
0x1400ac618  jz      short loc_1400AC634
0x1400ac61a  xor     r8d, r8d
0x1400ac61d  mov     [rdi+rax*4+890h], r12d
0x1400ac625  mov     r9d, ebx
0x1400ac628  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x1400ac62b  lea     edx, [r8+5]
0x1400ac62f  call    VidSchControlVSyncAdapter
0x1400ac634  add     ebx, r12d
0x1400ac637  cmp     ebx, [rdi+30h]
0x1400ac63a  jb      short loc_1400AC60E
0x1400ac63c  mov     rcx, rdi
0x1400ac63f  call    VidSchiBlockDriverCallback
0x1400ac644  jmp     short loc_1400AC66A
0x1400ac646  lea     r8, [rsp+78h+Interval]; Interval
0x1400ac64e  mov     qword ptr [rsp+78h+Interval], 0FFFFFFFFFFF0BDC0h
0x1400ac65a  xor     edx, edx; Alertable
0x1400ac65c  xor     ecx, ecx; WaitMode
0x1400ac65e  call    cs:__imp_KeDelayExecutionThread
0x1400ac665  nop     dword ptr [rax+rax+00h]
0x1400ac66a  mov     eax, [rdi+0A48h]
0x1400ac670  test    eax, eax
0x1400ac672  jnz     short loc_1400AC646
0x1400ac674  mov     eax, [rdi+0B58h]
0x1400ac67a  test    al, 2
0x1400ac67c  jz      short loc_1400AC691
0x1400ac67e  lea     rcx, [rdi+4D0h]; Resource
0x1400ac685  call    cs:__imp_ExReleaseResourceLite
0x1400ac68c  nop     dword ptr [rax+rax+00h]
0x1400ac691  mov     r14d, r12d
0x1400ac694  cmp     [rdi+160h], r15
0x1400ac69b  jz      short loc_1400AC6E1
0x1400ac69d  mov     ebx, r15d
0x1400ac6a0  cmp     [rdi+54h], r15d
0x1400ac6a4  jbe     short loc_1400AC6C5
0x1400ac6a6  mov     rax, [rdi+160h]
0x1400ac6ad  mov     ecx, ebx
0x1400ac6af  mov     rcx, [rax+rcx*8]; struct _VIDSCH_CONTEXT *
0x1400ac6b3  test    rcx, rcx
0x1400ac6b6  jz      short loc_1400AC6BD
0x1400ac6b8  call    VidSchTerminateContext
0x1400ac6bd  add     ebx, r12d
0x1400ac6c0  cmp     ebx, [rdi+54h]
0x1400ac6c3  jb      short loc_1400AC6A6
0x1400ac6c5  mov     rcx, [rdi+160h]; P
0x1400ac6cc  xor     edx, edx; Tag
0x1400ac6ce  call    cs:__imp_ExFreePoolWithTag
0x1400ac6d5  nop     dword ptr [rax+rax+00h]
0x1400ac6da  mov     [rdi+160h], r15
0x1400ac6e1  cmp     [rdi+148h], r15
0x1400ac6e8  jz      short loc_1400AC72E
0x1400ac6ea  mov     ebx, r15d
0x1400ac6ed  cmp     [rdi+54h], r15d
0x1400ac6f1  jbe     short loc_1400AC712
0x1400ac6f3  mov     rax, [rdi+148h]
0x1400ac6fa  mov     ecx, ebx
0x1400ac6fc  mov     rcx, [rax+rcx*8]; struct _VIDSCH_CONTEXT *
0x1400ac700  test    rcx, rcx
0x1400ac703  jz      short loc_1400AC70A
0x1400ac705  call    VidSchTerminateContext
0x1400ac70a  add     ebx, r12d
0x1400ac70d  cmp     ebx, [rdi+54h]
0x1400ac710  jb      short loc_1400AC6F3
0x1400ac712  mov     rcx, [rdi+148h]; P
0x1400ac719  xor     edx, edx; Tag
0x1400ac71b  call    cs:__imp_ExFreePoolWithTag
0x1400ac722  nop     dword ptr [rax+rax+00h]
0x1400ac727  mov     [rdi+148h], r15
0x1400ac72e  cmp     [rdi+158h], r15
0x1400ac735  jz      short loc_1400AC77B
0x1400ac737  mov     ebx, r15d
0x1400ac73a  cmp     [rdi+54h], r15d
0x1400ac73e  jbe     short loc_1400AC75F
0x1400ac740  mov     rax, [rdi+158h]
0x1400ac747  mov     ecx, ebx
0x1400ac749  mov     rcx, [rax+rcx*8]; struct VIDSCH_HW_QUEUE *
0x1400ac74d  test    rcx, rcx
0x1400ac750  jz      short loc_1400AC757
0x1400ac752  call    VidSchTerminateHwQueue
0x1400ac757  add     ebx, r12d
0x1400ac75a  cmp     ebx, [rdi+54h]
0x1400ac75d  jb      short loc_1400AC740
0x1400ac75f  mov     rcx, [rdi+158h]; P
0x1400ac766  xor     edx, edx; Tag
0x1400ac768  call    cs:__imp_ExFreePoolWithTag
0x1400ac76f  nop     dword ptr [rax+rax+00h]
0x1400ac774  mov     [rdi+158h], r15
0x1400ac77b  cmp     [rdi+150h], r15
0x1400ac782  jz      short loc_1400AC7C8
0x1400ac784  mov     ebx, r15d
0x1400ac787  cmp     [rdi+54h], r15d
0x1400ac78b  jbe     short loc_1400AC7AC
0x1400ac78d  mov     rax, [rdi+150h]
0x1400ac794  mov     ecx, ebx
0x1400ac796  mov     rcx, [rax+rcx*8]; P
0x1400ac79a  test    rcx, rcx
0x1400ac79d  jz      short loc_1400AC7A4
0x1400ac79f  call    VidSchTerminateHwContext
0x1400ac7a4  add     ebx, r12d
0x1400ac7a7  cmp     ebx, [rdi+54h]
0x1400ac7aa  jb      short loc_1400AC78D
0x1400ac7ac  mov     rcx, [rdi+150h]; P
0x1400ac7b3  xor     edx, edx; Tag
0x1400ac7b5  call    cs:__imp_ExFreePoolWithTag
0x1400ac7bc  nop     dword ptr [rax+rax+00h]
0x1400ac7c1  mov     [rdi+150h], r15
0x1400ac7c8  mov     rcx, [rdi+140h]; P
0x1400ac7cf  test    rcx, rcx
0x1400ac7d2  jz      short loc_1400AC7E0
0x1400ac7d4  call    VidSchTerminateDevice
0x1400ac7d9  mov     [rdi+140h], r15
0x1400ac7e0  mov     ebx, r15d
0x1400ac7e3  cmp     [rdi+58h], r15d
0x1400ac7e7  jbe     short loc_1400AC820
0x1400ac7e9  mov     rsi, [rdi+308h]
0x1400ac7f0  cmp     ebx, [rdi+350h]
0x1400ac7f6  jnb     short loc_1400AC7FE
0x1400ac7f8  mov     eax, ebx
0x1400ac7fa  lea     rsi, [rsi+rax*8]
0x1400ac7fe  mov     rsi, [rsi]
0x1400ac801  test    rsi, rsi
0x1400ac804  jz      short loc_1400AC818
0x1400ac806  mov     rcx, [rsi+20h]; struct _VIDSCH_CONTEXT *
0x1400ac80a  test    rcx, rcx
0x1400ac80d  jz      short loc_1400AC818
0x1400ac80f  call    VidSchTerminateContext
0x1400ac814  mov     [rsi+20h], r15
0x1400ac818  add     ebx, r12d
0x1400ac81b  cmp     ebx, [rdi+58h]
0x1400ac81e  jb      short loc_1400AC7E9
0x1400ac820  mov     rcx, [rdi+110h]; struct _VIDSCH_CONTEXT *
0x1400ac827  test    rcx, rcx
0x1400ac82a  jz      short loc_1400AC838
0x1400ac82c  call    VidSchTerminateContext
0x1400ac831  mov     [rdi+110h], r15
0x1400ac838  mov     rcx, [rdi+108h]; P
0x1400ac83f  test    rcx, rcx
0x1400ac842  jz      short loc_1400AC850
0x1400ac844  call    VidSchTerminateDevice
0x1400ac849  mov     [rdi+108h], r15
0x1400ac850  mov     rcx, [rdi+0C8h]
0x1400ac857  test    rcx, rcx
0x1400ac85a  jz      short loc_1400AC871
0x1400ac85c  xor     r9d, r9d
0x1400ac85f  xor     r8d, r8d
0x1400ac862  mov     dl, r12b
0x1400ac865  call    cs:__imp_ExDeleteTimer
0x1400ac86c  nop     dword ptr [rax+rax+00h]
0x1400ac871  mov     ebx, r15d
0x1400ac874  cmp     [rdi+5Ch], r15d
0x1400ac878  jbe     short loc_1400AC8BC
0x1400ac87a  mov     rax, [rdi+308h]
0x1400ac881  mov     esi, ebx
0x1400ac883  cmp     ebx, [rdi+350h]
0x1400ac889  jnb     short loc_1400AC88F
0x1400ac88b  lea     rax, [rax+rsi*8]
0x1400ac88f  mov     rcx, [rax]; P
0x1400ac892  test    rcx, rcx
0x1400ac895  jz      short loc_1400AC8B4
0x1400ac897  call    VidSchiTerminateNode
0x1400ac89c  mov     rdx, [rdi+308h]
0x1400ac8a3  cmp     ebx, [rdi+350h]
0x1400ac8a9  lea     rcx, [rdx+rsi*8]
0x1400ac8ad  cmovnb  rcx, rdx
0x1400ac8b1  mov     [rcx], r15
0x1400ac8b4  add     ebx, r12d
0x1400ac8b7  cmp     ebx, [rdi+5Ch]
0x1400ac8ba  jb      short loc_1400AC87A
0x1400ac8bc  mov     ebp, r15d
0x1400ac8bf  mov     dword ptr [rdi+1C8h], 2
0x1400ac8c9  cmp     [rdi+30h], r15d
0x1400ac8cd  jbe     loc_1400AC9CB
0x1400ac8d3  mov     esi, ebp
0x1400ac8d5  cmp     [rdi+rsi*8+0DC8h], r15
0x1400ac8dd  jz      loc_1400AC99C
0x1400ac8e3  mov     edx, ebp
0x1400ac8e5  mov     rcx, rdi
0x1400ac8e8  call    VidSchiClearPeriodicFrameNotifications
0x1400ac8ed  mov     rax, [rdi+rsi*8+0DC8h]
0x1400ac8f5  mov     rcx, [rax+88h]; void *
0x1400ac8fc  test    rcx, rcx
0x1400ac8ff  jz      short loc_1400AC921
0x1400ac901  lea     rbx, [rcx-8]
0x1400ac905  mov     edx, 70h ; 'p'; unsigned __int64
0x1400ac90a  mov     r8, [rbx]; unsigned __int64
0x1400ac90d  lea     r9, ??1VIDSCH_FLIP_QUEUE_HISTORY_ENTRY@@QEAA@XZ; void (*)(void *)
0x1400ac914  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400ac919  mov     rcx, rbx; void *
0x1400ac91c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400ac921  mov     rcx, [rdi+rsi*8+0DC8h]
0x1400ac929  mov     rcx, [rcx+0AD78h]; void *
0x1400ac930  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400ac935  cmp     [rdi+43h], r15b
0x1400ac939  jnz     short loc_1400AC97E
0x1400ac93b  mov     ebx, r15d
0x1400ac93e  cmp     [rdi+0A0h], r15d
0x1400ac945  jbe     short loc_1400AC97E
0x1400ac947  mov     eax, ebx
0x1400ac949  imul    rcx, rax, 130h
0x1400ac950  mov     rax, [rdi+rsi*8+0DC8h]
0x1400ac958  mov     rcx, [rcx+rax+1B0h]; P
0x1400ac960  test    rcx, rcx
0x1400ac963  jz      short loc_1400AC973
0x1400ac965  xor     edx, edx; Tag
0x1400ac967  call    cs:__imp_ExFreePoolWithTag
0x1400ac96e  nop     dword ptr [rax+rax+00h]
0x1400ac973  add     ebx, r12d
0x1400ac976  cmp     ebx, [rdi+0A0h]
0x1400ac97c  jb      short loc_1400AC947
0x1400ac97e  mov     rcx, [rdi+rsi*8+0DC8h]; P
0x1400ac986  xor     edx, edx; Tag
0x1400ac988  call    cs:__imp_ExFreePoolWithTag
0x1400ac98f  nop     dword ptr [rax+rax+00h]
0x1400ac994  mov     [rdi+rsi*8+0DC8h], r15
0x1400ac99c  mov     rcx, [rdi+rsi*8+1DA0h]; P
0x1400ac9a4  test    rcx, rcx
0x1400ac9a7  jz      short loc_1400AC9BF
0x1400ac9a9  xor     edx, edx; Tag
0x1400ac9ab  call    cs:__imp_ExFreePoolWithTag
0x1400ac9b2  nop     dword ptr [rax+rax+00h]
0x1400ac9b7  mov     [rdi+rsi*8+1DA0h], r15
0x1400ac9bf  add     ebp, r12d
0x1400ac9c2  cmp     ebp, [rdi+30h]
0x1400ac9c5  jb      loc_1400AC8D3
0x1400ac9cb  lea     rcx, [rdi+0C88h]; Resource
0x1400ac9d2  call    cs:__imp_ExDeleteResourceLite
0x1400ac9d9  nop     dword ptr [rax+rax+00h]
0x1400ac9de  lea     rcx, [rdi+1D0h]; Resource
0x1400ac9e5  call    cs:__imp_ExDeleteResourceLite
0x1400ac9ec  nop     dword ptr [rax+rax+00h]
0x1400ac9f1  lea     rcx, [rdi+5A0h]; Resource
0x1400ac9f8  call    cs:__imp_ExDeleteResourceLite
  ... truncated ...
```

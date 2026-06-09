# VidSchTerminateAdapter

- ea: `0x1400ad8b0`
- end: `0x1400adeb6`
- name: `VidSchTerminateAdapter`
- size: `1542`
- prototype: `__int64 __fastcall(_VIDSCH_GLOBAL *this)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400b07c0`
- `0x1400e59e4`

## callees

- `0x1400049e0`
- `0x140009420`
- `0x140009550`
- `0x14002bf50`
- `0x14002c030`
- `0x14002e6c0`
- `0x14002ea08`
- `0x1400306e8`
- `0x14003d398`
- `0x140042cfc`
- `0x1400abee0`
- `0x1400ace00`
- `0x1400ad8b0`
- `0x1400b20c4`
- `0x1400e1c40`
- `0x1401185a0`
- `0x1401202b0`
- `0x1401226f4`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400addfd`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400ade45`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400addfd`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400ade45`
- `ntoskrnl!ObfReferenceObject` at `0x1400ad95d`
- `ntoskrnl!ObfReferenceObject` at `0x1400ad95d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ad998`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ade80`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ad998`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ade80`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400ada0e`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400ada0e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ada35`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ada35`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400add82`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400add95`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400adda8`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400addbb`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400addce`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400adde1`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400add82`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400add95`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400adda8`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400addbb`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400addce`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400adde1`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400ade8e`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400ade8e`
- `ntoskrnl!ExDeleteTimer` at `0x1400adc15`
- `ntoskrnl!ExDeleteTimer` at `0x1400adc15`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ad989`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ade29`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ad989`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ade29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ada7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400adacb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400adb18`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400adb65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400add17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400add38`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400add5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ade6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ada7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400adacb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400adb18`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400adb65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400add17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400add38`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400add5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ade6c`

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
0x1400ad8b0  mov     [rsp+arg_8], rbx
0x1400ad8b5  mov     [rsp+arg_10], rbp
0x1400ad8ba  push    rsi
0x1400ad8bb  push    rdi
0x1400ad8bc  push    r12
0x1400ad8be  push    r14
0x1400ad8c0  push    r15
0x1400ad8c2  sub     rsp, 50h
0x1400ad8c6  xor     r15d, r15d
0x1400ad8c9  mov     rdi, rcx
0x1400ad8cc  test    rcx, rcx
0x1400ad8cf  jz      loc_1400ADE9A
0x1400ad8d5  lea     rbx, [rcx+0F30h]
0x1400ad8dc  cmp     [rbx], r15
0x1400ad8df  jz      short loc_1400AD924
0x1400ad8e1  lea     rdx, gAdapterListLock; struct _EX_PUSH_LOCK *
0x1400ad8e8  lea     rcx, [rsp+78h+var_48]; this
0x1400ad8ed  call    ??0DXGAUTOEXPUSHLOCKEXCLUSIVE@@QEAA@QEAU_EX_PUSH_LOCK@@@Z; DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(_EX_PUSH_LOCK * const)
0x1400ad8f2  mov     rcx, [rbx]
0x1400ad8f5  cmp     [rcx+8], rbx
0x1400ad8f9  jnz     loc_1400AD9A9
0x1400ad8ff  mov     rax, [rbx+8]
0x1400ad903  cmp     [rax], rbx
0x1400ad906  jnz     loc_1400AD9A9
0x1400ad90c  mov     [rax], rcx
0x1400ad90f  xorps   xmm0, xmm0
0x1400ad912  mov     [rcx+8], rax
0x1400ad916  lea     rcx, [rsp+78h+var_48]; this
0x1400ad91b  movdqu  xmmword ptr [rbx], xmm0
0x1400ad91f  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x1400ad924  mov     rcx, rdi
0x1400ad927  mov     r14d, r15d
0x1400ad92a  call    VidSchiAcceptsIncomingWork
0x1400ad92f  mov     r12d, 1
0x1400ad935  test    al, al
0x1400ad937  jz      loc_1400ADA44
0x1400ad93d  call    VidSchIsWorkerThread
0x1400ad942  lea     edx, [r12+10h]
0x1400ad947  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x1400ad94a  test    al, al
0x1400ad94c  jnz     short loc_1400AD9B0
0x1400ad94e  call    VidSchFlushAdapter
0x1400ad953  mov     rbx, [rdi+0B0h]
0x1400ad95a  mov     rcx, rbx; Object
0x1400ad95d  call    cs:__imp_ObfReferenceObject
0x1400ad964  nop     dword ptr [rax+rax+00h]
0x1400ad969  xor     r8d, r8d
0x1400ad96c  lea     edx, [r12+1]
0x1400ad971  mov     rcx, rdi
0x1400ad974  call    VidSchiRequestSchedulerStatus
0x1400ad979  xor     r9d, r9d; Alertable
0x1400ad97c  mov     [rsp+78h+Timeout], r15; Timeout
0x1400ad981  xor     r8d, r8d; WaitMode
0x1400ad984  xor     edx, edx; WaitReason
0x1400ad986  mov     rcx, rbx; Object
0x1400ad989  call    cs:__imp_KeWaitForSingleObject
0x1400ad990  nop     dword ptr [rax+rax+00h]
0x1400ad995  mov     rcx, rbx; Object
0x1400ad998  call    cs:__imp_ObfDereferenceObject
0x1400ad99f  nop     dword ptr [rax+rax+00h]
0x1400ad9a4  jmp     loc_1400ADE9A
0x1400ad9a9  mov     ecx, 3
0x1400ad9ae  int     29h; Win8: RtlFailFast(ecx)
0x1400ad9b0  call    VidSchFlushAdapter
0x1400ad9b5  mov     ebx, r15d
0x1400ad9b8  cmp     [rdi+30h], r15d
0x1400ad9bc  jbe     short loc_1400AD9EC
0x1400ad9be  mov     eax, ebx
0x1400ad9c0  cmp     [rdi+rax*4+890h], r15d
0x1400ad9c8  jz      short loc_1400AD9E4
0x1400ad9ca  xor     r8d, r8d
0x1400ad9cd  mov     [rdi+rax*4+890h], r12d
0x1400ad9d5  mov     r9d, ebx
0x1400ad9d8  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x1400ad9db  lea     edx, [r8+5]
0x1400ad9df  call    VidSchControlVSyncAdapter
0x1400ad9e4  add     ebx, r12d
0x1400ad9e7  cmp     ebx, [rdi+30h]
0x1400ad9ea  jb      short loc_1400AD9BE
0x1400ad9ec  mov     rcx, rdi
0x1400ad9ef  call    VidSchiBlockDriverCallback
0x1400ad9f4  jmp     short loc_1400ADA1A
0x1400ad9f6  lea     r8, [rsp+78h+Interval]; Interval
0x1400ad9fe  mov     qword ptr [rsp+78h+Interval], 0FFFFFFFFFFF0BDC0h
0x1400ada0a  xor     edx, edx; Alertable
0x1400ada0c  xor     ecx, ecx; WaitMode
0x1400ada0e  call    cs:__imp_KeDelayExecutionThread
0x1400ada15  nop     dword ptr [rax+rax+00h]
0x1400ada1a  mov     eax, [rdi+0A48h]
0x1400ada20  test    eax, eax
0x1400ada22  jnz     short loc_1400AD9F6
0x1400ada24  mov     eax, [rdi+0B58h]
0x1400ada2a  test    al, 2
0x1400ada2c  jz      short loc_1400ADA41
0x1400ada2e  lea     rcx, [rdi+4D0h]; Resource
0x1400ada35  call    cs:__imp_ExReleaseResourceLite
0x1400ada3c  nop     dword ptr [rax+rax+00h]
0x1400ada41  mov     r14d, r12d
0x1400ada44  cmp     [rdi+160h], r15
0x1400ada4b  jz      short loc_1400ADA91
0x1400ada4d  mov     ebx, r15d
0x1400ada50  cmp     [rdi+54h], r15d
0x1400ada54  jbe     short loc_1400ADA75
0x1400ada56  mov     rax, [rdi+160h]
0x1400ada5d  mov     ecx, ebx
0x1400ada5f  mov     rcx, [rax+rcx*8]; struct _VIDSCH_CONTEXT *
0x1400ada63  test    rcx, rcx
0x1400ada66  jz      short loc_1400ADA6D
0x1400ada68  call    VidSchTerminateContext
0x1400ada6d  add     ebx, r12d
0x1400ada70  cmp     ebx, [rdi+54h]
0x1400ada73  jb      short loc_1400ADA56
0x1400ada75  mov     rcx, [rdi+160h]; P
0x1400ada7c  xor     edx, edx; Tag
0x1400ada7e  call    cs:__imp_ExFreePoolWithTag
0x1400ada85  nop     dword ptr [rax+rax+00h]
0x1400ada8a  mov     [rdi+160h], r15
0x1400ada91  cmp     [rdi+148h], r15
0x1400ada98  jz      short loc_1400ADADE
0x1400ada9a  mov     ebx, r15d
0x1400ada9d  cmp     [rdi+54h], r15d
0x1400adaa1  jbe     short loc_1400ADAC2
0x1400adaa3  mov     rax, [rdi+148h]
0x1400adaaa  mov     ecx, ebx
0x1400adaac  mov     rcx, [rax+rcx*8]; struct _VIDSCH_CONTEXT *
0x1400adab0  test    rcx, rcx
0x1400adab3  jz      short loc_1400ADABA
0x1400adab5  call    VidSchTerminateContext
0x1400adaba  add     ebx, r12d
0x1400adabd  cmp     ebx, [rdi+54h]
0x1400adac0  jb      short loc_1400ADAA3
0x1400adac2  mov     rcx, [rdi+148h]; P
0x1400adac9  xor     edx, edx; Tag
0x1400adacb  call    cs:__imp_ExFreePoolWithTag
0x1400adad2  nop     dword ptr [rax+rax+00h]
0x1400adad7  mov     [rdi+148h], r15
0x1400adade  cmp     [rdi+158h], r15
0x1400adae5  jz      short loc_1400ADB2B
0x1400adae7  mov     ebx, r15d
0x1400adaea  cmp     [rdi+54h], r15d
0x1400adaee  jbe     short loc_1400ADB0F
0x1400adaf0  mov     rax, [rdi+158h]
0x1400adaf7  mov     ecx, ebx
0x1400adaf9  mov     rcx, [rax+rcx*8]; struct VIDSCH_HW_QUEUE *
0x1400adafd  test    rcx, rcx
0x1400adb00  jz      short loc_1400ADB07
0x1400adb02  call    VidSchTerminateHwQueue
0x1400adb07  add     ebx, r12d
0x1400adb0a  cmp     ebx, [rdi+54h]
0x1400adb0d  jb      short loc_1400ADAF0
0x1400adb0f  mov     rcx, [rdi+158h]; P
0x1400adb16  xor     edx, edx; Tag
0x1400adb18  call    cs:__imp_ExFreePoolWithTag
0x1400adb1f  nop     dword ptr [rax+rax+00h]
0x1400adb24  mov     [rdi+158h], r15
0x1400adb2b  cmp     [rdi+150h], r15
0x1400adb32  jz      short loc_1400ADB78
0x1400adb34  mov     ebx, r15d
0x1400adb37  cmp     [rdi+54h], r15d
0x1400adb3b  jbe     short loc_1400ADB5C
0x1400adb3d  mov     rax, [rdi+150h]
0x1400adb44  mov     ecx, ebx
0x1400adb46  mov     rcx, [rax+rcx*8]; P
0x1400adb4a  test    rcx, rcx
0x1400adb4d  jz      short loc_1400ADB54
0x1400adb4f  call    VidSchTerminateHwContext
0x1400adb54  add     ebx, r12d
0x1400adb57  cmp     ebx, [rdi+54h]
0x1400adb5a  jb      short loc_1400ADB3D
0x1400adb5c  mov     rcx, [rdi+150h]; P
0x1400adb63  xor     edx, edx; Tag
0x1400adb65  call    cs:__imp_ExFreePoolWithTag
0x1400adb6c  nop     dword ptr [rax+rax+00h]
0x1400adb71  mov     [rdi+150h], r15
0x1400adb78  mov     rcx, [rdi+140h]; P
0x1400adb7f  test    rcx, rcx
0x1400adb82  jz      short loc_1400ADB90
0x1400adb84  call    VidSchTerminateDevice
0x1400adb89  mov     [rdi+140h], r15
0x1400adb90  mov     ebx, r15d
0x1400adb93  cmp     [rdi+58h], r15d
0x1400adb97  jbe     short loc_1400ADBD0
0x1400adb99  mov     rsi, [rdi+308h]
0x1400adba0  cmp     ebx, [rdi+350h]
0x1400adba6  jnb     short loc_1400ADBAE
0x1400adba8  mov     eax, ebx
0x1400adbaa  lea     rsi, [rsi+rax*8]
0x1400adbae  mov     rsi, [rsi]
0x1400adbb1  test    rsi, rsi
0x1400adbb4  jz      short loc_1400ADBC8
0x1400adbb6  mov     rcx, [rsi+20h]; struct _VIDSCH_CONTEXT *
0x1400adbba  test    rcx, rcx
0x1400adbbd  jz      short loc_1400ADBC8
0x1400adbbf  call    VidSchTerminateContext
0x1400adbc4  mov     [rsi+20h], r15
0x1400adbc8  add     ebx, r12d
0x1400adbcb  cmp     ebx, [rdi+58h]
0x1400adbce  jb      short loc_1400ADB99
0x1400adbd0  mov     rcx, [rdi+110h]; struct _VIDSCH_CONTEXT *
0x1400adbd7  test    rcx, rcx
0x1400adbda  jz      short loc_1400ADBE8
0x1400adbdc  call    VidSchTerminateContext
0x1400adbe1  mov     [rdi+110h], r15
0x1400adbe8  mov     rcx, [rdi+108h]; P
0x1400adbef  test    rcx, rcx
0x1400adbf2  jz      short loc_1400ADC00
0x1400adbf4  call    VidSchTerminateDevice
0x1400adbf9  mov     [rdi+108h], r15
0x1400adc00  mov     rcx, [rdi+0C8h]
0x1400adc07  test    rcx, rcx
0x1400adc0a  jz      short loc_1400ADC21
0x1400adc0c  xor     r9d, r9d
0x1400adc0f  xor     r8d, r8d
0x1400adc12  mov     dl, r12b
0x1400adc15  call    cs:__imp_ExDeleteTimer
0x1400adc1c  nop     dword ptr [rax+rax+00h]
0x1400adc21  mov     ebx, r15d
0x1400adc24  cmp     [rdi+5Ch], r15d
0x1400adc28  jbe     short loc_1400ADC6C
0x1400adc2a  mov     rax, [rdi+308h]
0x1400adc31  mov     esi, ebx
0x1400adc33  cmp     ebx, [rdi+350h]
0x1400adc39  jnb     short loc_1400ADC3F
0x1400adc3b  lea     rax, [rax+rsi*8]
0x1400adc3f  mov     rcx, [rax]; P
0x1400adc42  test    rcx, rcx
0x1400adc45  jz      short loc_1400ADC64
0x1400adc47  call    VidSchiTerminateNode
0x1400adc4c  mov     rdx, [rdi+308h]
0x1400adc53  cmp     ebx, [rdi+350h]
0x1400adc59  lea     rcx, [rdx+rsi*8]
0x1400adc5d  cmovnb  rcx, rdx
0x1400adc61  mov     [rcx], r15
0x1400adc64  add     ebx, r12d
0x1400adc67  cmp     ebx, [rdi+5Ch]
0x1400adc6a  jb      short loc_1400ADC2A
0x1400adc6c  mov     ebp, r15d
0x1400adc6f  mov     dword ptr [rdi+1C8h], 2
0x1400adc79  cmp     [rdi+30h], r15d
0x1400adc7d  jbe     loc_1400ADD7B
0x1400adc83  mov     esi, ebp
0x1400adc85  cmp     [rdi+rsi*8+0DC8h], r15
0x1400adc8d  jz      loc_1400ADD4C
0x1400adc93  mov     edx, ebp
0x1400adc95  mov     rcx, rdi
0x1400adc98  call    VidSchiClearPeriodicFrameNotifications
0x1400adc9d  mov     rax, [rdi+rsi*8+0DC8h]
0x1400adca5  mov     rcx, [rax+88h]; void *
0x1400adcac  test    rcx, rcx
0x1400adcaf  jz      short loc_1400ADCD1
0x1400adcb1  lea     rbx, [rcx-8]
0x1400adcb5  mov     edx, 70h ; 'p'; unsigned __int64
0x1400adcba  mov     r8, [rbx]; unsigned __int64
0x1400adcbd  lea     r9, ??1VIDSCH_FLIP_QUEUE_HISTORY_ENTRY@@QEAA@XZ; void (*)(void *)
0x1400adcc4  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400adcc9  mov     rcx, rbx; void *
0x1400adccc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400adcd1  mov     rcx, [rdi+rsi*8+0DC8h]
0x1400adcd9  mov     rcx, [rcx+0AD78h]; void *
0x1400adce0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400adce5  cmp     [rdi+43h], r15b
0x1400adce9  jnz     short loc_1400ADD2E
0x1400adceb  mov     ebx, r15d
0x1400adcee  cmp     [rdi+0A0h], r15d
0x1400adcf5  jbe     short loc_1400ADD2E
0x1400adcf7  mov     eax, ebx
0x1400adcf9  imul    rcx, rax, 130h
0x1400add00  mov     rax, [rdi+rsi*8+0DC8h]
0x1400add08  mov     rcx, [rcx+rax+1B0h]; P
0x1400add10  test    rcx, rcx
0x1400add13  jz      short loc_1400ADD23
0x1400add15  xor     edx, edx; Tag
0x1400add17  call    cs:__imp_ExFreePoolWithTag
0x1400add1e  nop     dword ptr [rax+rax+00h]
0x1400add23  add     ebx, r12d
0x1400add26  cmp     ebx, [rdi+0A0h]
0x1400add2c  jb      short loc_1400ADCF7
0x1400add2e  mov     rcx, [rdi+rsi*8+0DC8h]; P
0x1400add36  xor     edx, edx; Tag
0x1400add38  call    cs:__imp_ExFreePoolWithTag
0x1400add3f  nop     dword ptr [rax+rax+00h]
0x1400add44  mov     [rdi+rsi*8+0DC8h], r15
0x1400add4c  mov     rcx, [rdi+rsi*8+1DA0h]; P
0x1400add54  test    rcx, rcx
0x1400add57  jz      short loc_1400ADD6F
0x1400add59  xor     edx, edx; Tag
0x1400add5b  call    cs:__imp_ExFreePoolWithTag
0x1400add62  nop     dword ptr [rax+rax+00h]
0x1400add67  mov     [rdi+rsi*8+1DA0h], r15
0x1400add6f  add     ebp, r12d
0x1400add72  cmp     ebp, [rdi+30h]
0x1400add75  jb      loc_1400ADC83
0x1400add7b  lea     rcx, [rdi+0C88h]; Resource
0x1400add82  call    cs:__imp_ExDeleteResourceLite
0x1400add89  nop     dword ptr [rax+rax+00h]
0x1400add8e  lea     rcx, [rdi+1D0h]; Resource
0x1400add95  call    cs:__imp_ExDeleteResourceLite
0x1400add9c  nop     dword ptr [rax+rax+00h]
0x1400adda1  lea     rcx, [rdi+5A0h]; Resource
0x1400adda8  call    cs:__imp_ExDeleteResourceLite
  ... truncated ...
```

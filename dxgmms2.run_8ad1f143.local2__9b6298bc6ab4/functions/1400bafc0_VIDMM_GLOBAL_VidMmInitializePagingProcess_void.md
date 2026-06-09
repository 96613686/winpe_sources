# VIDMM_GLOBAL::VidMmInitializePagingProcess(void)

- ea: `0x1400bafc0`
- end: `0x1400bb359`
- name: `?VidMmInitializePagingProcess@VIDMM_GLOBAL@@QEAAJXZ`
- size: `921`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140046f20`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140054148`
- `0x140058680`
- `0x140058760`
- `0x14009b2a8`
- `0x1400b3698`
- `0x1400bafc0`
- `0x1400bf1f0`
- `0x1400c2ab8`
- `0x1400c4720`
- `0x1400d931c`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400bb013`
- `ntoskrnl!KeStackAttachProcess` at `0x1400bb013`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400bb32a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400bb32a`
- `ntoskrnl!PsInitialSystemProcess` at `0x1400baffa`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400bb10a`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400bb10a`
- `watchdog!WdLogSingleEntry0` at `0x1400bb03a`
- `watchdog!WdLogSingleEntry0` at `0x1400bb094`
- `watchdog!WdLogSingleEntry0` at `0x1400bb12f`
- `watchdog!WdLogSingleEntry0` at `0x1400bb17c`
- `watchdog!WdLogSingleEntry0` at `0x1400bb1aa`
- `watchdog!WdLogSingleEntry0` at `0x1400bb03a`
- `watchdog!WdLogSingleEntry0` at `0x1400bb094`
- `watchdog!WdLogSingleEntry0` at `0x1400bb12f`
- `watchdog!WdLogSingleEntry0` at `0x1400bb17c`
- `watchdog!WdLogSingleEntry0` at `0x1400bb1aa`
- `watchdog!WdLogSingleEntry1` at `0x1400bb1f4`
- `watchdog!WdLogSingleEntry1` at `0x1400bb2a9`
- `watchdog!WdLogSingleEntry1` at `0x1400bb1f4`
- `watchdog!WdLogSingleEntry1` at `0x1400bb2a9`

## string_xrefs

- `0x1400bb0a5`: `Failed to create scheduler system devices`
- `0x1400bb1bb`: `Failed to create paging fence objects`
- `0x1400bb2ba`: `Failed to create scheduling logs. ntStatus=0x%.8x`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::VidMmInitializePagingProcess(VIDMM_GLOBAL *this)
{
  __int64 v2; // rdi
  int v3; // ecx
  int v4; // r8d
  __int64 v5; // rax
  const wchar_t *v6; // r9
  __int64 v7; // rax
  struct VIDMM_PAGING *v8; // rbx
  int v9; // ecx
  int v10; // r8d
  unsigned int i; // ebx
  int inited; // eax
  __int64 v13; // rax
  __int64 v14; // rbp
  unsigned int j; // ebx
  struct _VIDSCH_NODE **v16; // r8
  unsigned int v17; // edx
  struct _VIDSCH_NODE **v18; // rax
  int NodeSchedulingLog; // eax
  unsigned int k; // ebx
  _DWORD *v21; // rcx
  __int64 v23; // [rsp+20h] [rbp-A8h]
  struct _KAPC_STATE ApcState; // [rsp+50h] [rbp-78h] BYREF

  *((_BYTE *)this + 37229) = 1;
  memset(&ApcState, 0, sizeof(ApcState));
  KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
  LODWORD(v2) = VIDMM_PAGING_PROCESS::InitPagingProcess((VIDMM_GLOBAL *)((char *)this + 36672), this);
  if ( (int)v2 < 0 )
  {
    WdLogSingleEntry0(1);
    v5 = 24993;
    v6 = L"Failed to initialize paging process";
    goto LABEL_3;
  }
  LODWORD(v2) = VidSchCreateSystemDevices(*(struct _VIDSCH_GLOBAL **)(*((_QWORD *)this + 2) + 744LL));
  if ( (int)v2 < 0 )
  {
    WdLogSingleEntry0(1);
    v5 = 25004;
    v6 = L"Failed to create scheduler system devices";
    goto LABEL_3;
  }
  LODWORD(v2) = VIDMM_DEVICE::CreatePagingProcessPagingQueues(*((VIDMM_DEVICE **)this + 4585));
  if ( (int)v2 < 0 )
    goto LABEL_35;
  v7 = operator new(184, 1833789782, 64);
  v8 = (struct VIDMM_PAGING *)v7;
  if ( v7 )
  {
    *(_QWORD *)v7 = this;
    *(_QWORD *)(v7 + 8) = *(_QWORD *)this;
    *(_QWORD *)(v7 + 48) = v7;
    *(_QWORD *)(v7 + 56) = 0;
    *(_QWORD *)(v7 + 64) = 0;
    *(_DWORD *)(v7 + 80) = 0;
    *(_QWORD *)(v7 + 176) = 1;
    KeInitializeSemaphore((PRKSEMAPHORE)(v7 + 16), 1, 1);
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 6) = v8;
  if ( !v8 )
  {
    _InterlockedAdd(&dword_1400868CC, 1u);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 25022;
    DxgkLogInternalTriageEvent(
      v9,
      262145,
      v10,
      (unsigned int)L"Failed to allocate memory for VIDMM_PAGING structure",
      25022,
      0,
      0,
      0);
    goto LABEL_35;
  }
  LODWORD(v2) = VidMmInitializePaging(v8);
  if ( (int)v2 < 0 )
  {
    WdLogSingleEntry0(1);
    v5 = 25031;
    v6 = L"Failed to init paging structure and DMA pools.\n";
    goto LABEL_3;
  }
  LODWORD(v2) = VIDMM_GLOBAL::CreatePagingFenceObjects(this);
  if ( (int)v2 < 0 )
  {
    WdLogSingleEntry0(1);
    v5 = 25042;
    v6 = L"Failed to create paging fence objects";
LABEL_3:
    v23 = v5;
    WdLogGlobalForLineNumber = v5;
LABEL_4:
    DxgkLogInternalTriageEvent(v3, 0x40000, v4, (_DWORD)v6, v23, 0, 0, 0);
    goto LABEL_35;
  }
  for ( i = 0; i < *((_DWORD *)this + 778); ++i )
  {
    inited = VIDMM_GLOBAL::InitPagingProcessVaSpace(this, 0, i, 0);
    v2 = inited;
    if ( inited < 0 )
    {
      WdLogSingleEntry1(1, inited);
      v6 = L"Failed to initialize paging process VA space. ntStatus=0x%.8x";
      v23 = v2;
      WdLogGlobalForLineNumber = 25058;
      goto LABEL_4;
    }
  }
  v13 = *((_QWORD *)this + 2);
  *((_BYTE *)this + 37229) = 1;
  v14 = *(_QWORD *)(v13 + 744);
  if ( *(int *)(*(_QWORD *)(v14 + 16) + 3116LL) >= 2500 )
  {
    for ( j = 0; j < *(_DWORD *)(v14 + 88); ++j )
    {
      v16 = *(struct _VIDSCH_NODE ***)(v14 + 776);
      v17 = *(_DWORD *)(v14 + 848);
      v18 = &v16[j];
      if ( j >= v17 )
        v18 = *(struct _VIDSCH_NODE ***)(v14 + 776);
      if ( (*((_DWORD *)*v18 + 3) & 2) != 0 )
      {
        if ( j < v17 )
          v16 += j;
        NodeSchedulingLog = VidSchiCreateNodeSchedulingLog(*v16, 0x800u);
        v2 = NodeSchedulingLog;
        if ( NodeSchedulingLog < 0 )
        {
          WdLogSingleEntry1(1, NodeSchedulingLog);
          v6 = L"Failed to create scheduling logs. ntStatus=0x%.8x";
          v23 = v2;
          WdLogGlobalForLineNumber = 25076;
          goto LABEL_4;
        }
      }
    }
  }
  LODWORD(v2) = 0;
LABEL_35:
  for ( k = 0; k < *((_DWORD *)this + 778); ++k )
  {
    v21 = *(_DWORD **)(*((_QWORD *)this + 4560) + 8LL * k);
    if ( v21[269] == 1 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v21 + 344LL))(v21);
  }
  *((_BYTE *)this + 37229) = 0;
  KeUnstackDetachProcess(&ApcState);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400bafc0  push    rbx
0x1400bafc2  push    rbp
0x1400bafc3  push    rsi
0x1400bafc4  push    rdi
0x1400bafc5  push    r14
0x1400bafc7  push    r15
0x1400bafc9  sub     rsp, 98h
0x1400bafd0  mov     rax, cs:__security_cookie
0x1400bafd7  xor     rax, rsp
0x1400bafda  mov     [rsp+0C8h+var_48], rax
0x1400bafe2  xorps   xmm0, xmm0
0x1400bafe5  lea     rdx, [rsp+0C8h+ApcState]; ApcState
0x1400bafea  mov     rsi, rcx
0x1400bafed  mov     r15d, 1
0x1400baff3  mov     [rcx+916Dh], r15b
0x1400baffa  mov     rcx, cs:__imp_PsInitialSystemProcess
0x1400bb001  movups  xmmword ptr [rsp+0C8h+ApcState.ApcListHead.Flink], xmm0
0x1400bb006  movups  xmmword ptr [rsp+0C8h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400bb00b  mov     rcx, [rcx]; PROCESS
0x1400bb00e  movups  xmmword ptr [rsp+0C8h+ApcState.Process], xmm0
0x1400bb013  call    cs:__imp_KeStackAttachProcess
0x1400bb01a  nop     dword ptr [rax+rax+00h]
0x1400bb01f  lea     rcx, [rsi+8F40h]; this
0x1400bb026  mov     rdx, rsi; struct VIDMM_GLOBAL *
0x1400bb029  call    ?InitPagingProcess@VIDMM_PAGING_PROCESS@@QEAAJPEAVVIDMM_GLOBAL@@@Z; VIDMM_PAGING_PROCESS::InitPagingProcess(VIDMM_GLOBAL *)
0x1400bb02e  xor     r14d, r14d
0x1400bb031  mov     edi, eax
0x1400bb033  test    eax, eax
0x1400bb035  jns     short loc_1400BB07B
0x1400bb037  mov     ecx, r15d
0x1400bb03a  call    cs:__imp_WdLogSingleEntry0
0x1400bb041  nop     dword ptr [rax+rax+00h]
0x1400bb046  mov     eax, 61A1h
0x1400bb04b  lea     r9, aFailedToInitia_20; "Failed to initialize paging process"
0x1400bb052  mov     [rsp+0C8h+var_90], r14
0x1400bb057  mov     [rsp+0C8h+var_98], r14
0x1400bb05c  mov     [rsp+0C8h+var_A0], r14
0x1400bb061  mov     [rsp+0C8h+var_A8], rax
0x1400bb066  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bb06c  mov     edx, 40000h
0x1400bb071  call    DxgkLogInternalTriageEvent
0x1400bb076  jmp     loc_1400BB2E2
0x1400bb07b  mov     rcx, [rsi+10h]
0x1400bb07f  mov     rcx, [rcx+2E8h]
0x1400bb086  call    VidSchCreateSystemDevices
0x1400bb08b  mov     edi, eax
0x1400bb08d  test    eax, eax
0x1400bb08f  jns     short loc_1400BB0AE
0x1400bb091  mov     ecx, r15d
0x1400bb094  call    cs:__imp_WdLogSingleEntry0
0x1400bb09b  nop     dword ptr [rax+rax+00h]
0x1400bb0a0  mov     eax, 61ACh
0x1400bb0a5  lea     r9, aFailedToCreate_2; "Failed to create scheduler system devic"...
0x1400bb0ac  jmp     short loc_1400BB052
0x1400bb0ae  mov     rcx, [rsi+8F48h]; this
0x1400bb0b5  call    ?CreatePagingProcessPagingQueues@VIDMM_DEVICE@@QEAAJXZ; VIDMM_DEVICE::CreatePagingProcessPagingQueues(void)
0x1400bb0ba  mov     edi, eax
0x1400bb0bc  test    eax, eax
0x1400bb0be  js      loc_1400BB2E2
0x1400bb0c4  mov     ecx, 0B8h
0x1400bb0c9  mov     edx, 6D4D6956h
0x1400bb0ce  lea     r8d, [rcx-78h]
0x1400bb0d2  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400bb0d7  mov     rbx, rax
0x1400bb0da  test    rax, rax
0x1400bb0dd  jz      short loc_1400BB118
0x1400bb0df  mov     [rax], rsi
0x1400bb0e2  lea     rcx, [rbx+10h]; Semaphore
0x1400bb0e6  mov     rax, [rsi]
0x1400bb0e9  mov     r8d, r15d; Limit
0x1400bb0ec  mov     [rbx+8], rax
0x1400bb0f0  mov     edx, r15d; Count
0x1400bb0f3  mov     [rbx+30h], rbx
0x1400bb0f7  mov     [rbx+38h], r14
0x1400bb0fb  mov     [rbx+40h], r14
0x1400bb0ff  mov     [rbx+50h], r14d
0x1400bb103  mov     [rbx+0B0h], r15
0x1400bb10a  call    cs:__imp_KeInitializeSemaphore
0x1400bb111  nop     dword ptr [rax+rax+00h]
0x1400bb116  jmp     short loc_1400BB11B
0x1400bb118  mov     rbx, r14
0x1400bb11b  mov     [rsi+30h], rbx
0x1400bb11f  test    rbx, rbx
0x1400bb122  jnz     short loc_1400BB16B
0x1400bb124  lock add cs:dword_1400868CC, r15d
0x1400bb12c  lea     ecx, [rbx+6]
0x1400bb12f  call    cs:__imp_WdLogSingleEntry0
0x1400bb136  nop     dword ptr [rax+rax+00h]
0x1400bb13b  mov     [rsp+0C8h+var_90], r14
0x1400bb140  lea     r9, aFailedToAlloca_71; "Failed to allocate memory for VIDMM_PAG"...
0x1400bb147  mov     eax, 61BEh
0x1400bb14c  mov     [rsp+0C8h+var_98], r14
0x1400bb151  mov     [rsp+0C8h+var_A0], r14
0x1400bb156  mov     edx, 40001h
0x1400bb15b  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bb161  mov     [rsp+0C8h+var_A8], rax
0x1400bb166  jmp     loc_1400BB071
0x1400bb16b  mov     rcx, rbx; struct VIDMM_PAGING *
0x1400bb16e  call    ?VidMmInitializePaging@@YAJPEAUVIDMM_PAGING@@@Z; VidMmInitializePaging(VIDMM_PAGING *)
0x1400bb173  mov     edi, eax
0x1400bb175  test    eax, eax
0x1400bb177  jns     short loc_1400BB199
0x1400bb179  mov     ecx, r15d
0x1400bb17c  call    cs:__imp_WdLogSingleEntry0
0x1400bb183  nop     dword ptr [rax+rax+00h]
0x1400bb188  mov     eax, 61C7h
0x1400bb18d  lea     r9, aFailedToInitPa; "Failed to init paging structure and DMA"...
0x1400bb194  jmp     loc_1400BB052
0x1400bb199  mov     rcx, rsi; this
0x1400bb19c  call    ?CreatePagingFenceObjects@VIDMM_GLOBAL@@QEAAJXZ; VIDMM_GLOBAL::CreatePagingFenceObjects(void)
0x1400bb1a1  mov     edi, eax
0x1400bb1a3  test    eax, eax
0x1400bb1a5  jns     short loc_1400BB1C7
0x1400bb1a7  mov     ecx, r15d
0x1400bb1aa  call    cs:__imp_WdLogSingleEntry0
0x1400bb1b1  nop     dword ptr [rax+rax+00h]
0x1400bb1b6  mov     eax, 61D2h
0x1400bb1bb  lea     r9, aFailedToCreate_6; "Failed to create paging fence objects"
0x1400bb1c2  jmp     loc_1400BB052
0x1400bb1c7  mov     ebx, r14d
0x1400bb1ca  cmp     ebx, [rsi+0C28h]
0x1400bb1d0  jnb     short loc_1400BB22A
0x1400bb1d2  xor     r9d, r9d; bool
0x1400bb1d5  mov     r8d, ebx; unsigned int
0x1400bb1d8  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400bb1da  mov     rcx, rsi; this
0x1400bb1dd  call    ?InitPagingProcessVaSpace@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_N@Z; VIDMM_GLOBAL::InitPagingProcessVaSpace(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,bool)
0x1400bb1e2  movsxd  rdi, eax
0x1400bb1e5  test    eax, eax
0x1400bb1e7  js      short loc_1400BB1EE
0x1400bb1e9  add     ebx, r15d
0x1400bb1ec  jmp     short loc_1400BB1CA
0x1400bb1ee  mov     rdx, rdi
0x1400bb1f1  mov     ecx, r15d
0x1400bb1f4  call    cs:__imp_WdLogSingleEntry1
0x1400bb1fb  nop     dword ptr [rax+rax+00h]
0x1400bb200  mov     [rsp+0C8h+var_90], r14
0x1400bb205  lea     r9, aFailedToInitia_7; "Failed to initialize paging process VA "...
0x1400bb20c  mov     [rsp+0C8h+var_98], r14
0x1400bb211  mov     [rsp+0C8h+var_A0], r14
0x1400bb216  mov     [rsp+0C8h+var_A8], rdi
0x1400bb21b  mov     cs:WdLogGlobalForLineNumber, 61E2h
0x1400bb225  jmp     loc_1400BB06C
0x1400bb22a  mov     rax, [rsi+10h]
0x1400bb22e  mov     [rsi+916Dh], r15b
0x1400bb235  mov     rbp, [rax+2E8h]
0x1400bb23c  mov     rax, [rbp+10h]
0x1400bb240  cmp     dword ptr [rax+0C2Ch], 9C4h
0x1400bb24a  jl      loc_1400BB2DF
0x1400bb250  mov     ebx, r14d
0x1400bb253  cmp     ebx, [rbp+58h]
0x1400bb256  jnb     loc_1400BB2DF
0x1400bb25c  mov     r8, [rbp+308h]
0x1400bb263  mov     edx, [rbp+350h]
0x1400bb269  mov     r9d, ebx
0x1400bb26c  lea     rax, [r8+r9*8]
0x1400bb270  cmp     ebx, edx
0x1400bb272  jb      short loc_1400BB277
0x1400bb274  mov     rax, r8
0x1400bb277  mov     rax, [rax]
0x1400bb27a  mov     ecx, [rax+0Ch]
0x1400bb27d  test    cl, 2
0x1400bb280  jz      short loc_1400BB29E
0x1400bb282  cmp     ebx, edx
0x1400bb284  jnb     short loc_1400BB28A
0x1400bb286  lea     r8, [r8+r9*8]
0x1400bb28a  mov     rcx, [r8]; struct _VIDSCH_NODE *
0x1400bb28d  mov     edx, 800h
0x1400bb292  call    VidSchiCreateNodeSchedulingLog
0x1400bb297  movsxd  rdi, eax
0x1400bb29a  test    eax, eax
0x1400bb29c  js      short loc_1400BB2A3
0x1400bb29e  add     ebx, r15d
0x1400bb2a1  jmp     short loc_1400BB253
0x1400bb2a3  mov     rdx, rdi
0x1400bb2a6  mov     ecx, r15d
0x1400bb2a9  call    cs:__imp_WdLogSingleEntry1
0x1400bb2b0  nop     dword ptr [rax+rax+00h]
0x1400bb2b5  mov     [rsp+0C8h+var_90], r14
0x1400bb2ba  lea     r9, aFailedToCreate_11; "Failed to create scheduling logs. ntSta"...
0x1400bb2c1  mov     [rsp+0C8h+var_98], r14
0x1400bb2c6  mov     [rsp+0C8h+var_A0], r14
0x1400bb2cb  mov     [rsp+0C8h+var_A8], rdi
0x1400bb2d0  mov     cs:WdLogGlobalForLineNumber, 61F4h
0x1400bb2da  jmp     loc_1400BB06C
0x1400bb2df  mov     edi, r14d
0x1400bb2e2  mov     ebx, r14d
0x1400bb2e5  cmp     [rsi+0C28h], r14d
0x1400bb2ec  jbe     short loc_1400BB31E
0x1400bb2ee  mov     rax, [rsi+8E80h]
0x1400bb2f5  mov     ecx, ebx
0x1400bb2f7  mov     rcx, [rax+rcx*8]
0x1400bb2fb  cmp     [rcx+434h], r15d
0x1400bb302  jnz     short loc_1400BB313
0x1400bb304  mov     rax, [rcx]
0x1400bb307  mov     rax, [rax+158h]
0x1400bb30e  call    _guard_dispatch_icall
0x1400bb313  add     ebx, r15d
0x1400bb316  cmp     ebx, [rsi+0C28h]
0x1400bb31c  jb      short loc_1400BB2EE
0x1400bb31e  lea     rcx, [rsp+0C8h+ApcState]; ApcState
0x1400bb323  mov     [rsi+916Dh], r14b
0x1400bb32a  call    cs:__imp_KeUnstackDetachProcess
0x1400bb331  nop     dword ptr [rax+rax+00h]
0x1400bb336  mov     eax, edi
0x1400bb338  mov     rcx, [rsp+0C8h+var_48]
0x1400bb340  xor     rcx, rsp; StackCookie
0x1400bb343  call    __security_check_cookie
0x1400bb348  add     rsp, 98h
0x1400bb34f  pop     r15
0x1400bb351  pop     r14
0x1400bb353  pop     rdi
0x1400bb354  pop     rsi
0x1400bb355  pop     rbp
0x1400bb356  pop     rbx
0x1400bb357  retn
```

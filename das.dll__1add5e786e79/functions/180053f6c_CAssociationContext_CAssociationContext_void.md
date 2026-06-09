# CAssociationContext::~CAssociationContext(void)

- ea: `0x180053f6c`
- end: `0x180054331`
- name: `??1CAssociationContext@@IEAA@XZ`
- size: `965`
- prototype: `void __fastcall(CAssociationContext *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180056c50`

## callees

- `0x180007500`
- `0x180009590`
- `0x180016d20`
- `0x180024294`
- `0x18002d764`
- `0x180053f6c`
- `0x180054778`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180054078`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180054078`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053f9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053f9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053faa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053faa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054121`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054145`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800541e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054121`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054145`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800541e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005412f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054153`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800541f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005412f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054153`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800541f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054092`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800540dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800540dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180054000`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800541cc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180054000`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800541cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800541c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800541c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800541b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800541b7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800540cf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800540cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053fee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005404b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005421a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054233`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005424e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053fee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005404b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005421a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054233`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005424e`
- `RPCRT4!RpcAsyncAbortCall` at `0x180053fdc`
- `RPCRT4!RpcAsyncAbortCall` at `0x180053fdc`

## pseudocode

```c
void __fastcall CAssociationContext::~CAssociationContext(CAssociationContext *this)
{
  __int64 v1; // rbp
  int v3; // esi
  void *v4; // rcx
  struct _TP_WAIT *v5; // rcx
  void *v6; // rdx
  struct _DEVPROPERTY *v7; // rcx
  void *v8; // rcx
  char LastError; // al
  int v10; // edx
  int v11; // r8d
  CHostContext *v12; // rcx
  struct _DEVPROPERTY *v13; // rcx
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  void *v16; // rbx
  HANDLE v17; // rax
  unsigned int i; // ebx
  wil::details *v19; // rcx
  PTP_WAIT *v20; // rbp
  PTP_WAIT *j; // rsi
  struct _TP_WAIT *v22; // rbx
  void *v23; // rbx
  HANDLE v24; // rax
  void *v25; // rcx
  void *v26; // rcx
  HANDLE *v27; // rsi
  HANDLE *k; // rbx
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx

  v1 = *((_QWORD *)this + 73);
  *(_QWORD *)this = &CAssociationContext::`vftable';
  v3 = 0;
  if ( v1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 112));
    *(_DWORD *)(v1 + 104) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 112));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 73) + 16LL))(*((_QWORD *)this + 73));
    *((_QWORD *)this + 73) = 0;
  }
  if ( !*((_DWORD *)this + 9) )
    RpcAsyncAbortCall(*((PRPC_ASYNC_STATE *)this + 25), 0x71Au);
  v4 = (void *)*((_QWORD *)this + 79);
  if ( v4 )
    CloseHandle(v4);
  v5 = (struct _TP_WAIT *)*((_QWORD *)this + 80);
  if ( v5 )
    CloseThreadpoolWait(v5);
  if ( !*((_DWORD *)this + 11) && (unsigned int)(*((_DWORD *)this + 7) - 6) > 3 )
    v3 = 1;
  CAssociationContext::CleanupRemoteAssociationContext(this, v3);
  v7 = (struct _DEVPROPERTY *)*((_QWORD *)this + 12);
  if ( v7 )
  {
    MidlFreeDevProperties(v7, *((_DWORD *)this + 22));
    *((_QWORD *)this + 12) = 0;
    *((_DWORD *)this + 22) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 7);
  if ( v8 )
    CloseHandle(v8);
  if ( *((_QWORD *)this + 76) )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)g_cProviderObjectCleanup) == 1
      && !ResetEvent(g_hProviderObjectCleanupCompleteEvent)
      && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LastError = GetLastError();
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v10,
        v11,
        10,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        LastError);
    }
    *(_DWORD *)(*((_QWORD *)this + 46) + 8LL) = v3;
    SubmitThreadpoolWork(*((PTP_WORK *)this + 76));
    CloseThreadpoolWork(*((PTP_WORK *)this + 76));
    *((_QWORD *)this + 76) = 0;
  }
  v12 = (CHostContext *)*((_QWORD *)this + 75);
  if ( v12 )
    CHostContext::Release(v12);
  v13 = (struct _DEVPROPERTY *)*((_QWORD *)this + 42);
  if ( v13 )
  {
    MidlFreeDevProperties(v13, *((_DWORD *)this + 83));
    *((_DWORD *)this + 83) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 2);
  if ( v14 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v14);
    *((_QWORD *)this + 2) = 0;
  }
  v16 = (void *)*((_QWORD *)this + 48);
  if ( v16 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
  }
  if ( *((_QWORD *)this + 51) )
  {
    for ( i = 0; i < *((_DWORD *)this + 100); ++i )
    {
      v19 = *(wil::details **)(*((_QWORD *)this + 51) + 8LL * i);
      if ( v19 )
        wil::details::FreeProcessHeap(v19, v6);
    }
    wil::details::FreeProcessHeap(*((wil::details **)this + 51), v6);
  }
  v20 = (PTP_WAIT *)*((_QWORD *)this + 69);
  for ( j = (PTP_WAIT *)*((_QWORD *)this + 68); j != v20; ++j )
  {
    v22 = *j;
    SetThreadpoolWait(*j, 0, 0);
    WaitForThreadpoolWaitCallbacks(v22, 1);
    CloseThreadpoolWait(v22);
  }
  v23 = (void *)*((_QWORD *)this + 1);
  if ( v23 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
    *((_QWORD *)this + 1) = 0;
  }
  v25 = (void *)*((_QWORD *)this + 56);
  if ( v25 )
    CloseHandle(v25);
  v26 = (void *)*((_QWORD *)this + 55);
  if ( v26 )
    CloseHandle(v26);
  v27 = (HANDLE *)*((_QWORD *)this + 58);
  for ( k = (HANDLE *)*((_QWORD *)this + 57); k != v27; ++k )
    CloseHandle(*k);
  v29 = (void *)*((_QWORD *)this + 54);
  if ( v29 )
    CloseHandle(v29);
  v30 = (void *)*((_QWORD *)this + 68);
  if ( v30 )
  {
    std::_Deallocate<16>(v30, (*((_QWORD *)this + 70) - (_QWORD)v30) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 68) = 0;
    *((_QWORD *)this + 69) = 0;
    *((_QWORD *)this + 70) = 0;
  }
  v31 = (void *)*((_QWORD *)this + 65);
  if ( v31 )
  {
    std::_Deallocate<16>(v31, (*((_QWORD *)this + 67) - (_QWORD)v31) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 65) = 0;
    *((_QWORD *)this + 66) = 0;
    *((_QWORD *)this + 67) = 0;
  }
  v32 = (void *)*((_QWORD *)this + 62);
  if ( v32 )
  {
    std::_Deallocate<16>(v32, (*((_QWORD *)this + 64) - (_QWORD)v32) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 62) = 0;
    *((_QWORD *)this + 63) = 0;
    *((_QWORD *)this + 64) = 0;
  }
  v33 = (void *)*((_QWORD *)this + 57);
  if ( v33 )
  {
    std::_Deallocate<16>(v33, (*((_QWORD *)this + 59) - (_QWORD)v33) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 57) = 0;
    *((_QWORD *)this + 58) = 0;
    *((_QWORD *)this + 59) = 0;
  }
}

```

## disassembly

```asm
0x180053f6c  push    rbx
0x180053f6e  push    rbp
0x180053f6f  push    rsi
0x180053f70  push    rdi
0x180053f71  push    r14
0x180053f73  push    r15
0x180053f75  sub     rsp, 38h
0x180053f79  mov     rbp, [rcx+248h]
0x180053f80  lea     rax, ??_7CAssociationContext@@6B@; const CAssociationContext::`vftable'
0x180053f87  xor     r14d, r14d
0x180053f8a  mov     [rcx], rax
0x180053f8d  mov     rdi, rcx
0x180053f90  mov     esi, r14d
0x180053f93  test    rbp, rbp
0x180053f96  jz      short loc_180053FCA
0x180053f98  lea     rcx, [rbp+70h]; lpCriticalSection
0x180053f9c  call    cs:__imp_EnterCriticalSection
0x180053fa2  lea     rcx, [rbp+70h]; lpCriticalSection
0x180053fa6  mov     [rbp+68h], r14d
0x180053faa  call    cs:__imp_LeaveCriticalSection
0x180053fb0  mov     rcx, [rdi+248h]
0x180053fb7  mov     rax, [rcx]
0x180053fba  mov     rax, [rax+10h]
0x180053fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fc3  mov     [rdi+248h], r14
0x180053fca  cmp     [rdi+24h], r14d
0x180053fce  jnz     short loc_180053FE2
0x180053fd0  mov     rcx, [rdi+0C8h]; pAsync
0x180053fd7  mov     edx, 71Ah; ExceptionCode
0x180053fdc  call    cs:__imp_RpcAsyncAbortCall
0x180053fe2  mov     rcx, [rdi+278h]; hObject
0x180053fe9  test    rcx, rcx
0x180053fec  jz      short loc_180053FF4
0x180053fee  call    cs:__imp_CloseHandle
0x180053ff4  mov     rcx, [rdi+280h]; pwa
0x180053ffb  test    rcx, rcx
0x180053ffe  jz      short loc_180054006
0x180054000  call    cs:__imp_CloseThreadpoolWait
0x180054006  mov     r15d, 1
0x18005400c  cmp     [rdi+2Ch], r14d
0x180054010  jnz     short loc_18005401F
0x180054012  mov     eax, [rdi+1Ch]
0x180054015  sub     eax, 6
0x180054018  cmp     eax, 3
0x18005401b  cmova   esi, r15d
0x18005401f  mov     edx, esi; int
0x180054021  mov     rcx, rdi; this
0x180054024  call    ?CleanupRemoteAssociationContext@CAssociationContext@@IEAAXH@Z; CAssociationContext::CleanupRemoteAssociationContext(int)
0x180054029  mov     rcx, [rdi+60h]; this
0x18005402d  test    rcx, rcx
0x180054030  jz      short loc_180054042
0x180054032  mov     edx, [rdi+58h]; unsigned int
0x180054035  call    ?MidlFreeDevProperties@@YAXPEAU_DEVPROPERTY@@K@Z; MidlFreeDevProperties(_DEVPROPERTY *,ulong)
0x18005403a  mov     [rdi+60h], r14
0x18005403e  mov     [rdi+58h], r14d
0x180054042  mov     rcx, [rdi+38h]; hObject
0x180054046  test    rcx, rcx
0x180054049  jz      short loc_180054051
0x18005404b  call    cs:__imp_CloseHandle
0x180054051  cmp     [rdi+260h], r14
0x180054058  jz      loc_1800540E9
0x18005405e  mov     eax, r15d
0x180054061  lock xadd cs:?g_cProviderObjectCleanup@@3KC, eax; ulong volatile g_cProviderObjectCleanup
0x180054069  add     eax, r15d
0x18005406c  cmp     eax, r15d
0x18005406f  jnz     short loc_1800540BE
0x180054071  mov     rcx, cs:?g_hProviderObjectCleanupCompleteEvent@@3PEAXEA; hEvent
0x180054078  call    cs:__imp_ResetEvent
0x18005407e  test    eax, eax
0x180054080  jnz     short loc_1800540BE
0x180054082  lea     rax, WPP_RECORDER_INITIALIZED
0x180054089  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180054090  jz      short loc_1800540BE
0x180054092  call    cs:__imp_GetLastError
0x180054098  mov     rcx, cs:WPP_GLOBAL_Control
0x18005409f  mov     r9d, 0Ah; int
0x1800540a5  mov     dword ptr [rsp+68h+var_40], eax; char
0x1800540a9  lea     rax, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x1800540b0  mov     [rsp+68h+MessageGuid], rax; MessageGuid
0x1800540b5  mov     rcx, [rcx+28h]; int
0x1800540b9  call    WPP_RECORDER_SF_D
0x1800540be  mov     rax, [rdi+170h]
0x1800540c5  mov     [rax+8], esi
0x1800540c8  mov     rcx, [rdi+260h]; pwk
0x1800540cf  call    cs:__imp_SubmitThreadpoolWork
0x1800540d5  mov     rcx, [rdi+260h]; pwk
0x1800540dc  call    cs:__imp_CloseThreadpoolWork
0x1800540e2  mov     [rdi+260h], r14
0x1800540e9  mov     rcx, [rdi+258h]; this
0x1800540f0  test    rcx, rcx
0x1800540f3  jz      short loc_1800540FA
0x1800540f5  call    ?Release@CHostContext@@QEAAKXZ; CHostContext::Release(void)
0x1800540fa  mov     rcx, [rdi+150h]; this
0x180054101  test    rcx, rcx
0x180054104  jz      short loc_180054118
0x180054106  mov     edx, [rdi+14Ch]; unsigned int
0x18005410c  call    ?MidlFreeDevProperties@@YAXPEAU_DEVPROPERTY@@K@Z; MidlFreeDevProperties(_DEVPROPERTY *,ulong)
0x180054111  mov     [rdi+14Ch], r14d
0x180054118  mov     rbx, [rdi+10h]
0x18005411c  test    rbx, rbx
0x18005411f  jz      short loc_180054139
0x180054121  call    cs:__imp_GetProcessHeap
0x180054127  mov     r8, rbx; lpMem
0x18005412a  xor     edx, edx; dwFlags
0x18005412c  mov     rcx, rax; hHeap
0x18005412f  call    cs:__imp_HeapFree
0x180054135  mov     [rdi+10h], r14
0x180054139  mov     rbx, [rdi+180h]
0x180054140  test    rbx, rbx
0x180054143  jz      short loc_180054159
0x180054145  call    cs:__imp_GetProcessHeap
0x18005414b  mov     r8, rbx; lpMem
0x18005414e  xor     edx, edx; dwFlags
0x180054150  mov     rcx, rax; hHeap
0x180054153  call    cs:__imp_HeapFree
0x180054159  cmp     [rdi+198h], r14
0x180054160  jz      short loc_18005419C
0x180054162  mov     ebx, r14d
0x180054165  cmp     [rdi+190h], r14d
0x18005416c  jbe     short loc_180054190
0x18005416e  mov     rax, [rdi+198h]
0x180054175  mov     ecx, ebx
0x180054177  mov     rcx, [rax+rcx*8]; this
0x18005417b  test    rcx, rcx
0x18005417e  jz      short loc_180054185
0x180054180  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180054185  add     ebx, r15d
0x180054188  cmp     ebx, [rdi+190h]
0x18005418e  jb      short loc_18005416E
0x180054190  mov     rcx, [rdi+198h]; this
0x180054197  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18005419c  mov     rbp, [rdi+228h]
0x1800541a3  mov     rsi, [rdi+220h]
0x1800541aa  jmp     short loc_1800541D6
0x1800541ac  mov     rbx, [rsi]
0x1800541af  xor     r8d, r8d; pftTimeout
0x1800541b2  mov     rcx, rbx; pwa
0x1800541b5  xor     edx, edx; h
0x1800541b7  call    cs:__imp_SetThreadpoolWait
0x1800541bd  mov     edx, r15d; fCancelPendingCallbacks
0x1800541c0  mov     rcx, rbx; pwa
0x1800541c3  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800541c9  mov     rcx, rbx; pwa
0x1800541cc  call    cs:__imp_CloseThreadpoolWait
0x1800541d2  add     rsi, 8
0x1800541d6  cmp     rsi, rbp
0x1800541d9  jnz     short loc_1800541AC
0x1800541db  mov     rbx, [rdi+8]
0x1800541df  test    rbx, rbx
0x1800541e2  jz      short loc_1800541FC
0x1800541e4  call    cs:__imp_GetProcessHeap
0x1800541ea  mov     r8, rbx; lpMem
0x1800541ed  xor     edx, edx; dwFlags
0x1800541ef  mov     rcx, rax; hHeap
0x1800541f2  call    cs:__imp_HeapFree
0x1800541f8  mov     [rdi+8], r14
0x1800541fc  mov     rcx, [rdi+1C0h]; hObject
0x180054203  test    rcx, rcx
0x180054206  jz      short loc_18005420E
0x180054208  call    cs:__imp_CloseHandle
0x18005420e  mov     rcx, [rdi+1B8h]; hObject
0x180054215  test    rcx, rcx
0x180054218  jz      short loc_180054220
0x18005421a  call    cs:__imp_CloseHandle
0x180054220  mov     rsi, [rdi+1D0h]
0x180054227  mov     rbx, [rdi+1C8h]
0x18005422e  jmp     short loc_18005423D
0x180054230  mov     rcx, [rbx]; hObject
0x180054233  call    cs:__imp_CloseHandle
0x180054239  add     rbx, 8
0x18005423d  cmp     rbx, rsi
0x180054240  jnz     short loc_180054230
0x180054242  mov     rcx, [rdi+1B0h]; hObject
0x180054249  test    rcx, rcx
0x18005424c  jz      short loc_180054254
0x18005424e  call    cs:__imp_CloseHandle
0x180054254  mov     rcx, [rdi+220h]
0x18005425b  test    rcx, rcx
0x18005425e  jz      short loc_180054288
0x180054260  mov     rdx, [rdi+230h]
0x180054267  sub     rdx, rcx
0x18005426a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005426e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180054273  mov     [rdi+220h], r14
0x18005427a  mov     [rdi+228h], r14
0x180054281  mov     [rdi+230h], r14
0x180054288  mov     rcx, [rdi+208h]
0x18005428f  test    rcx, rcx
0x180054292  jz      short loc_1800542BC
0x180054294  mov     rdx, [rdi+218h]
0x18005429b  sub     rdx, rcx
0x18005429e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800542a2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800542a7  mov     [rdi+208h], r14
0x1800542ae  mov     [rdi+210h], r14
0x1800542b5  mov     [rdi+218h], r14
0x1800542bc  mov     rcx, [rdi+1F0h]
0x1800542c3  test    rcx, rcx
0x1800542c6  jz      short loc_1800542F0
0x1800542c8  mov     rdx, [rdi+200h]
0x1800542cf  sub     rdx, rcx
0x1800542d2  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800542d6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800542db  mov     [rdi+1F0h], r14
0x1800542e2  mov     [rdi+1F8h], r14
0x1800542e9  mov     [rdi+200h], r14
0x1800542f0  mov     rcx, [rdi+1C8h]
0x1800542f7  test    rcx, rcx
0x1800542fa  jz      short loc_180054324
0x1800542fc  mov     rdx, [rdi+1D8h]
0x180054303  sub     rdx, rcx
0x180054306  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005430a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005430f  mov     [rdi+1C8h], r14
0x180054316  mov     [rdi+1D0h], r14
0x18005431d  mov     [rdi+1D8h], r14
0x180054324  add     rsp, 38h
0x180054328  pop     r15
0x18005432a  pop     r14
0x18005432c  pop     rdi
0x18005432d  pop     rsi
0x18005432e  pop     rbp
0x18005432f  pop     rbx
0x180054330  retn
```

# Hns::Client::Notifications::NotificationCallbacks::RegisterCallback(void *,void *,void (*)(ulong,void *,long,ushort const *))

- ea: `0x18000a608`
- end: `0x18000aa97`
- name: `?RegisterCallback@NotificationCallbacks@Notifications@Client@Hns@@QEAAPEAXPEAX0P6AXK0JPEBG@Z@Z`
- size: `1167`
- prototype: `void *__fastcall(Hns::Client::Notifications::NotificationCallbacks *__hidden this, void *, void *, void (*)(unsigned int, void *, int, const unsigned __int16 *))`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180005e30`
- `0x180009690`
- `0x180009730`

## callees

- `0x1800019d0`
- `0x180001a0c`
- `0x1800027a8`
- `0x180004240`
- `0x180007904`
- `0x18000a190`
- `0x18000a608`
- `0x18000ad08`
- `0x18000b298`
- `0x18000b4c8`
- `0x18000b548`
- `0x18000b8c4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000a6ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000a718`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000a6ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000a718`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a6d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a73d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a9fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000aa13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a6d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a73d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a9fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000aa13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a6e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a749`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a6e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a749`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a6e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a752`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a6e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a752`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a79e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a79e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000a781`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000a781`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a903`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a903`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a9e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a9e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a877`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a877`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a849`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a849`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a75a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a7a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a7ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a820`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a75a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a7a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a7ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a80d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a818`

## string_xrefs

- `0x18000a8d9`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`
- `0x18000aa5e`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char **__fastcall Hns::Client::Notifications::NotificationCallbacks::RegisterCallback(
        RTL_SRWLOCK *this,
        char *a2,
        char *a3,
        void (*a4)(unsigned int, void *, int, const unsigned __int16 *))
{
  char **v7; // rsi
  void **v8; // r12
  unsigned int v9; // r8d
  const char *v10; // r9
  PTP_WAIT ThreadpoolWait; // r15
  struct _TP_WAIT *v12; // rdi
  char v13; // r14
  DWORD LastError; // ebx
  unsigned int v15; // r8d
  const char *v16; // r9
  PTP_WAIT v17; // r15
  PTP_WAIT *v18; // rax
  struct _TP_WAIT *v19; // rdi
  DWORD v20; // ebx
  PTP_WORK ThreadpoolWork; // rdi
  unsigned int v22; // r8d
  const char *v23; // r9
  struct _TP_WORK *v24; // r15
  DWORD v25; // ebx
  void *v26; // rdi
  DWORD v27; // ebx
  HANDLE *v28; // r15
  HANDLE v29; // rdi
  DWORD v30; // ebx
  RTL_SRWLOCK v31; // rbx
  RTL_SRWLOCK *v32; // rdi
  int v33; // ecx
  unsigned int v34; // r15d
  volatile signed __int32 *v35; // rbx
  RTL_SRWLOCK *v36; // r15
  RTL_SRWLOCK *v37; // rdi
  _QWORD *Ptr; // rcx
  HANDLE *v39; // rax
  int v40; // r12d
  HANDLE *v41; // r13
  PVOID v42; // rbx
  _QWORD *v43; // rax
  int v45; // [rsp+20h] [rbp-69h]
  char *v46; // [rsp+30h] [rbp-59h]
  char **v47; // [rsp+38h] [rbp-51h]
  HANDLE *v48; // [rsp+40h] [rbp-49h] BYREF
  int v49; // [rsp+48h] [rbp-41h]
  int v50; // [rsp+4Ch] [rbp-3Dh]
  _QWORD *v51; // [rsp+50h] [rbp-39h] BYREF
  char **v52; // [rsp+58h] [rbp-31h]
  HANDLE *v53; // [rsp+60h] [rbp-29h]
  RTL_SRWLOCK *v54; // [rsp+68h] [rbp-21h]
  RTL_SRWLOCK *v55; // [rsp+70h] [rbp-19h] BYREF
  volatile signed __int32 *v56; // [rsp+78h] [rbp-11h]
  _QWORD v57[2]; // [rsp+80h] [rbp-9h] BYREF
  __int16 v58; // [rsp+90h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  PTP_WAIT *v60; // [rsp+F0h] [rbp+67h]
  char *v61; // [rsp+F8h] [rbp+6Fh] BYREF
  HANDLE *v62; // [rsp+100h] [rbp+77h]
  PTP_WAIT *v63; // [rsp+108h] [rbp+7Fh]

  v61 = a2;
  v7 = (char **)operator new(0x60u);
  *(_WORD *)((char *)v7 + 61) = 0;
  *((_BYTE *)v7 + 63) = 0;
  v62 = (HANDLE *)(v7 + 3);
  v7[3] = 0;
  v63 = (PTP_WAIT *)(v7 + 4);
  v7[4] = 0;
  v8 = (void **)(v7 + 5);
  v53 = (HANDLE *)(v7 + 5);
  v7[5] = 0;
  v60 = (PTP_WAIT *)(v7 + 6);
  v7[6] = 0;
  *((_DWORD *)v7 + 14) = 0;
  *((_BYTE *)v7 + 60) = 0;
  v7[8] = 0;
  v7[9] = 0;
  v7[10] = 0;
  v52 = v7;
  *v7 = v61;
  v7[1] = (char *)a4;
  v7[2] = a3;
  v7[11] = (char *)this;
  ThreadpoolWait = CreateThreadpoolWait(Hns::Client::Notifications::NotificationCallbacks::WaitCallback, v7, 0);
  v12 = (struct _TP_WAIT *)v7[4];
  v13 = 1;
  if ( v12 )
  {
    LastError = GetLastError();
    SetThreadpoolWait(v12, 0, 0);
    WaitForThreadpoolWaitCallbacks(v12, 1);
    CloseThreadpoolWait(v12);
    SetLastError(LastError);
  }
  *v63 = ThreadpoolWait;
  if ( !ThreadpoolWait )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x49, v9, v10);
  v17 = CreateThreadpoolWait(Hns::Client::Notifications::NotificationCallbacks::WaitCallback, v7, 0);
  v18 = (PTP_WAIT *)(v7 + 6);
  v19 = *v60;
  if ( *v60 )
  {
    v20 = GetLastError();
    SetThreadpoolWait(v19, 0, 0);
    WaitForThreadpoolWaitCallbacks(v19, 1);
    CloseThreadpoolWait(v19);
    SetLastError(v20);
    v18 = (PTP_WAIT *)(v7 + 6);
  }
  *v18 = v17;
  if ( !v17 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x4D, v15, v16);
  ThreadpoolWork = CreateThreadpoolWork(Hns::Client::Notifications::NotificationCallbacks::CleanupCallback, v7, 0);
  v24 = (struct _TP_WORK *)v7[10];
  if ( v24 )
  {
    v25 = GetLastError();
    CloseThreadpoolWork(v24);
    SetLastError(v25);
  }
  v7[10] = (char *)ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x52, v22, v23);
  v47 = v7;
  v46 = v61;
  v26 = *v8;
  if ( (char *)*v8 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v27 = GetLastError();
    CloseHandle(v26);
    SetLastError(v27);
  }
  *v8 = 0;
  v51 = v7 + 5;
  v28 = v62;
  v29 = *v62;
  if ( (char *)*v62 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v30 = GetLastError();
    CloseHandle(v29);
    SetLastError(v30);
  }
  *v28 = 0;
  v48 = v28;
  v31.Ptr = this->Ptr;
  v32 = (RTL_SRWLOCK *)(*Hns::Client::RpcHelper::GetRpcClient(&v55) + 8LL);
  AcquireSRWLockShared(v32);
  v54 = v32;
  v34 = Rpc::RpcClient::InvokeRpcFunctionInternal<long (*)(void *,unsigned short const *,unsigned short * *),void * &,unsigned short const * &,unsigned short * *>(
          v33,
          v31.Ptr,
          (unsigned int)&v61,
          (unsigned int)&v48,
          (__int64)&v51);
  if ( v32 )
    ReleaseSRWLockShared(v32);
  v35 = v56;
  if ( v56 )
  {
    if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
      if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
    }
  }
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x5B,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
    (const char *)v34,
    (int)"Failed to register notifications for handle %p",
    v46);
  v57[0] = this;
  v57[1] = &v61;
  v58 = 257;
  v36 = this + 5;
  AcquireSRWLockExclusive(this + 5);
  v54 = this + 5;
  v37 = this + 3;
  Ptr = this[3].Ptr;
  v39 = (HANDLE *)Ptr[1];
  v40 = 0;
  if ( *((_BYTE *)v39 + 25) )
  {
    v41 = (HANDLE *)Ptr[1];
  }
  else
  {
    do
    {
      v41 = v39;
      if ( v39[4] >= v61 )
      {
        v40 = 1;
        Ptr = v39;
        v39 = (HANDLE *)*v39;
      }
      else
      {
        v40 = 0;
        v39 = (HANDLE *)v39[2];
      }
    }
    while ( !*((_BYTE *)v39 + 25) );
  }
  if ( *((_BYTE *)Ptr + 25) || (unsigned __int64)v61 < Ptr[4] )
  {
    if ( v37[1].Ptr == (PVOID)0x555555555555555LL )
      std::_Throw_tree_length_error();
    v42 = v37->Ptr;
    v55 = v37;
    v56 = 0;
    v43 = operator new(0x30u);
    v43[4] = v61;
    v7 = 0;
    v52 = 0;
    v43[5] = v47;
    *v43 = v42;
    v43[1] = v42;
    v43[2] = v42;
    *((_WORD *)v43 + 12) = 0;
    v48 = v41;
    v49 = v40;
    v50 = 0;
    std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Insert_node(
      v37,
      &v48,
      v43);
  }
  else
  {
    v13 = 0;
  }
  if ( !v13 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
      (const char *)0x800700B7LL,
      v45);
  if ( v36 )
    ReleaseSRWLockExclusive(v36);
  SetThreadpoolWait(*v63, *v62, 0);
  SetThreadpoolWait(*v60, *v53, 0);
  HIBYTE(v58) = 0;
  wil::details::ScopeExitFnGuard__lambda_ce4f58e6acb0bd507de9c422b318be30___::operator()(v57);
  if ( v7 )
  {
    Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext((Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)v7);
    operator delete(v7, 0x60u);
  }
  return v47;
}

```

## disassembly

```asm
0x18000a608  mov     [rsp-8+arg_8], rdx
0x18000a60d  push    rbp
0x18000a60e  push    rbx
0x18000a60f  push    rsi
0x18000a610  push    rdi
0x18000a611  push    r12
0x18000a613  push    r13
0x18000a615  push    r14
0x18000a617  push    r15
0x18000a619  lea     rbp, [rsp-1Fh]
0x18000a61e  sub     rsp, 0A8h
0x18000a625  mov     rbx, r9
0x18000a628  mov     rdi, r8
0x18000a62b  mov     r13, rcx
0x18000a62e  xor     r15d, r15d
0x18000a631  lea     ecx, [r15+60h]; Size
0x18000a635  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a63a  mov     rsi, rax
0x18000a63d  xor     eax, eax
0x18000a63f  mov     [rsi+3Dh], ax
0x18000a643  mov     [rsi+3Fh], al
0x18000a646  lea     rax, [rsi+18h]
0x18000a64a  mov     [rbp+57h+arg_10], rax
0x18000a64e  mov     [rax], r15
0x18000a651  lea     r14, [rsi+20h]
0x18000a655  mov     [rbp+57h+arg_18], r14
0x18000a659  mov     [r14], r15
0x18000a65c  lea     r12, [rsi+28h]
0x18000a660  mov     [rbp+57h+var_80], r12
0x18000a664  mov     [r12], r15
0x18000a668  lea     rax, [rsi+30h]
0x18000a66c  mov     [rbp+57h+arg_0], rax
0x18000a670  mov     [rax], r15
0x18000a673  mov     [rsi+38h], r15d
0x18000a677  mov     [rsi+3Ch], r15b
0x18000a67b  xor     eax, eax
0x18000a67d  mov     [rsi+40h], rax
0x18000a681  mov     [rsi+48h], rax
0x18000a685  mov     [rsi+50h], r15
0x18000a689  mov     [rbp+57h+var_88], rsi
0x18000a68d  mov     rax, [rbp+57h+arg_8]
0x18000a691  mov     [rsi], rax
0x18000a694  mov     [rsi+8], rbx
0x18000a698  mov     [rsi+10h], rdi
0x18000a69c  mov     [rsi+58h], r13
0x18000a6a0  xor     r8d, r8d; pcbe
0x18000a6a3  mov     rdx, rsi; pv
0x18000a6a6  lea     rcx, ?WaitCallback@NotificationCallbacks@Notifications@Client@Hns@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18000a6ad  call    cs:__imp_CreateThreadpoolWait
0x18000a6b3  mov     r15, rax
0x18000a6b6  mov     rdi, [r14]
0x18000a6b9  mov     r14d, 1
0x18000a6bf  test    rdi, rdi
0x18000a6c2  jz      short loc_18000A6F7
0x18000a6c4  call    cs:__imp_GetLastError
0x18000a6ca  mov     ebx, eax
0x18000a6cc  xor     r8d, r8d; pftTimeout
0x18000a6cf  xor     edx, edx; h
0x18000a6d1  mov     rcx, rdi; pwa
0x18000a6d4  call    cs:__imp_SetThreadpoolWait
0x18000a6da  mov     edx, r14d; fCancelPendingCallbacks
0x18000a6dd  mov     rcx, rdi; pwa
0x18000a6e0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000a6e6  mov     rcx, rdi; pwa
0x18000a6e9  call    cs:__imp_CloseThreadpoolWait
0x18000a6ef  mov     ecx, ebx; dwErrCode
0x18000a6f1  call    cs:__imp_SetLastError
0x18000a6f7  mov     rax, [rbp+57h+arg_18]
0x18000a6fb  mov     [rax], r15
0x18000a6fe  mov     rcx, [rbp+5Fh]; this
0x18000a702  test    r15, r15
0x18000a705  jz      loc_18000AA70
0x18000a70b  xor     r8d, r8d; pcbe
0x18000a70e  mov     rdx, rsi; pv
0x18000a711  lea     rcx, ?WaitCallback@NotificationCallbacks@Notifications@Client@Hns@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18000a718  call    cs:__imp_CreateThreadpoolWait
0x18000a71e  mov     r15, rax
0x18000a721  mov     rax, [rbp+57h+arg_0]
0x18000a725  mov     rdi, [rax]
0x18000a728  test    rdi, rdi
0x18000a72b  jz      short loc_18000A764
0x18000a72d  call    cs:__imp_GetLastError
0x18000a733  mov     ebx, eax
0x18000a735  xor     r8d, r8d; pftTimeout
0x18000a738  xor     edx, edx; h
0x18000a73a  mov     rcx, rdi; pwa
0x18000a73d  call    cs:__imp_SetThreadpoolWait
0x18000a743  mov     edx, r14d; fCancelPendingCallbacks
0x18000a746  mov     rcx, rdi; pwa
0x18000a749  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000a74f  mov     rcx, rdi; pwa
0x18000a752  call    cs:__imp_CloseThreadpoolWait
0x18000a758  mov     ecx, ebx; dwErrCode
0x18000a75a  call    cs:__imp_SetLastError
0x18000a760  mov     rax, [rbp+57h+arg_0]
0x18000a764  mov     [rax], r15
0x18000a767  mov     rcx, [rbp+5Fh]; this
0x18000a76b  test    r15, r15
0x18000a76e  jz      loc_18000AA7B
0x18000a774  xor     r8d, r8d; pcbe
0x18000a777  mov     rdx, rsi; pv
0x18000a77a  lea     rcx, ?CleanupCallback@NotificationCallbacks@Notifications@Client@Hns@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000a781  call    cs:__imp_CreateThreadpoolWork
0x18000a787  mov     rdi, rax
0x18000a78a  mov     r15, [rsi+50h]
0x18000a78e  test    r15, r15
0x18000a791  jz      short loc_18000A7AC
0x18000a793  call    cs:__imp_GetLastError
0x18000a799  mov     ebx, eax
0x18000a79b  mov     rcx, r15; pwk
0x18000a79e  call    cs:__imp_CloseThreadpoolWork
0x18000a7a4  mov     ecx, ebx; dwErrCode
0x18000a7a6  call    cs:__imp_SetLastError
0x18000a7ac  mov     [rsi+50h], rdi
0x18000a7b0  mov     rcx, [rbp+5Fh]; this
0x18000a7b4  test    rdi, rdi
0x18000a7b7  jz      loc_18000AA86
0x18000a7bd  mov     [rbp+57h+var_A8], rsi
0x18000a7c1  mov     rax, [rbp+57h+arg_8]
0x18000a7c5  mov     [rbp+57h+var_B0], rax
0x18000a7c9  mov     rdi, [r12]
0x18000a7cd  lea     rax, [rdi-1]
0x18000a7d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a7d5  ja      short loc_18000A7F0
0x18000a7d7  call    cs:__imp_GetLastError
0x18000a7dd  mov     ebx, eax
0x18000a7df  mov     rcx, rdi; hObject
0x18000a7e2  call    cs:__imp_CloseHandle
0x18000a7e8  mov     ecx, ebx; dwErrCode
0x18000a7ea  call    cs:__imp_SetLastError
0x18000a7f0  mov     qword ptr [r12], 0
0x18000a7f8  mov     [rbp+57h+var_90], r12
0x18000a7fc  mov     r15, [rbp+57h+arg_10]
0x18000a800  mov     rdi, [r15]
0x18000a803  lea     rax, [rdi-1]
0x18000a807  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a80b  ja      short loc_18000A826
0x18000a80d  call    cs:__imp_GetLastError
0x18000a813  mov     ebx, eax
0x18000a815  mov     rcx, rdi; hObject
0x18000a818  call    cs:__imp_CloseHandle
0x18000a81e  mov     ecx, ebx; dwErrCode
0x18000a820  call    cs:__imp_SetLastError
0x18000a826  mov     qword ptr [r15], 0
0x18000a82d  mov     [rbp+57h+var_A0], r15
0x18000a831  mov     rbx, [r13+0]
0x18000a835  lea     rcx, [rbp+57h+var_70]
0x18000a839  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x18000a83e  nop
0x18000a83f  mov     rdi, [rax]
0x18000a842  add     rdi, 8
0x18000a846  mov     rcx, rdi; SRWLock
0x18000a849  call    cs:__imp_AcquireSRWLockShared
0x18000a84f  mov     [rbp+57h+var_78], rdi
0x18000a853  lea     rax, [rbp+57h+var_90]
0x18000a857  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18000a85c  lea     r9, [rbp+57h+var_A0]
0x18000a860  lea     r8, [rbp+57h+arg_8]
0x18000a864  mov     rdx, rbx
0x18000a867  call    ??$InvokeRpcFunctionInternal@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcClient@Rpc@@AEAA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z
0x18000a86c  mov     r15d, eax
0x18000a86f  test    rdi, rdi
0x18000a872  jz      short loc_18000A87E
0x18000a874  mov     rcx, rdi; SRWLock
0x18000a877  call    cs:__imp_ReleaseSRWLockShared
0x18000a87d  nop
0x18000a87e  mov     rbx, [rbp+57h+var_68]
0x18000a882  test    rbx, rbx
0x18000a885  jz      short loc_18000A8BD
0x18000a887  or      edi, 0FFFFFFFFh
0x18000a88a  mov     eax, edi
0x18000a88c  lock xadd [rbx+8], eax
0x18000a891  add     eax, edi
0x18000a893  jnz     short loc_18000A8BD
0x18000a895  mov     rax, [rbx]
0x18000a898  mov     rcx, rbx
0x18000a89b  mov     rax, [rax]
0x18000a89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8a3  mov     eax, edi
0x18000a8a5  lock xadd [rbx+0Ch], eax
0x18000a8aa  add     eax, edi
0x18000a8ac  jnz     short loc_18000A8BD
0x18000a8ae  mov     rax, [rbx]
0x18000a8b1  mov     rcx, rbx
0x18000a8b4  mov     rax, [rax+8]
0x18000a8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8bd  mov     rcx, [rbp+5Fh]; this
0x18000a8c1  mov     rax, [rbp+57h+var_B0]
0x18000a8c5  mov     [rsp+0E0h+var_B8], rax; char *
0x18000a8ca  lea     rax, aFailedToRegist; "Failed to register notifications for ha"...
0x18000a8d1  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18000a8d6  mov     r9d, r15d; char *
0x18000a8d9  lea     r8, aOnecoreVmDvNet_1; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x18000a8e0  mov     edx, 5Bh ; '['; void *
0x18000a8e5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000a8ea  mov     [rbp+57h+var_60], r13
0x18000a8ee  lea     rax, [rbp+57h+arg_8]
0x18000a8f2  mov     [rbp+57h+var_58], rax
0x18000a8f6  mov     [rbp+57h+var_50], 101h
0x18000a8fc  lea     r15, [r13+28h]
0x18000a900  mov     rcx, r15; SRWLock
0x18000a903  call    cs:__imp_AcquireSRWLockExclusive
0x18000a909  mov     [rbp+57h+var_78], r15
0x18000a90d  lea     rdi, [r13+18h]
0x18000a911  mov     rcx, [rdi]
0x18000a914  mov     rax, [rcx+8]
0x18000a918  xor     ebx, ebx
0x18000a91a  mov     r12d, ebx
0x18000a91d  xor     edx, edx
0x18000a91f  mov     [rbp+57h+var_B0], rdx
0x18000a923  mov     rdx, [rbp+57h+arg_8]
0x18000a927  cmp     [rax+19h], bl
0x18000a92a  jnz     short loc_18000A94E
0x18000a92c  mov     r13, rax
0x18000a92f  cmp     [rax+20h], rdx
0x18000a933  jnb     short loc_18000A93E
0x18000a935  mov     r12d, ebx
0x18000a938  mov     rax, [rax+10h]
0x18000a93c  jmp     short loc_18000A947
0x18000a93e  mov     r12d, r14d
0x18000a941  mov     rcx, rax
0x18000a944  mov     rax, [rax]
0x18000a947  cmp     [rax+19h], bl
0x18000a94a  jz      short loc_18000A92C
0x18000a94c  jmp     short loc_18000A951
0x18000a94e  mov     r13, rax
0x18000a951  cmp     [rcx+19h], bl
0x18000a954  jnz     short loc_18000A961
0x18000a956  cmp     rdx, [rcx+20h]
0x18000a95a  jb      short loc_18000A961
0x18000a95c  mov     r14b, bl
0x18000a95f  jmp     short loc_18000A9D4
0x18000a961  mov     rax, 555555555555555h
0x18000a96b  cmp     [rdi+8], rax
0x18000a96f  jz      loc_18000AA91
0x18000a975  mov     rbx, [rdi]
0x18000a978  mov     [rbp+57h+var_70], rdi
0x18000a97c  mov     [rbp+57h+var_68], 0
0x18000a984  mov     ecx, 30h ; '0'; Size
0x18000a989  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a98e  nop
0x18000a98f  mov     rcx, [rbp+57h+arg_8]
0x18000a993  mov     [rax+20h], rcx
0x18000a997  xor     esi, esi
0x18000a999  mov     [rbp+57h+var_88], rsi
0x18000a99d  mov     rcx, [rbp+57h+var_A8]
0x18000a9a1  mov     [rax+28h], rcx
0x18000a9a5  mov     [rax], rbx
0x18000a9a8  mov     [rax+8], rbx
0x18000a9ac  mov     [rax+10h], rbx
0x18000a9b0  xor     ebx, ebx
0x18000a9b2  mov     [rax+18h], bx
0x18000a9b6  mov     [rbp+57h+var_A0], r13
0x18000a9ba  mov     [rbp+57h+var_98], r12d
0x18000a9be  mov     rcx, [rbp+57h+var_B0]
0x18000a9c2  mov     [rbp+57h+var_94], ecx
0x18000a9c5  mov     r8, rax
0x18000a9c8  lea     rdx, [rbp+57h+var_A0]
0x18000a9cc  mov     rcx, rdi
0x18000a9cf  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *> *>,std::_Tree_node<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>,void *> * const)
0x18000a9d4  mov     rcx, [rbp+5Fh]; this
0x18000a9d8  test    r14b, r14b
0x18000a9db  jz      short loc_18000AA58
0x18000a9dd  test    r15, r15
0x18000a9e0  jz      short loc_18000A9EB
0x18000a9e2  mov     rcx, r15; SRWLock
0x18000a9e5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a9eb  xor     r8d, r8d; pftTimeout
0x18000a9ee  mov     rdx, [rbp+57h+arg_10]
0x18000a9f2  mov     rdx, [rdx]; h
0x18000a9f5  mov     rax, [rbp+57h+arg_18]
0x18000a9f9  mov     rcx, [rax]; pwa
0x18000a9fc  call    cs:__imp_SetThreadpoolWait
0x18000aa02  xor     r8d, r8d; pftTimeout
0x18000aa05  mov     rdx, [rbp+57h+var_80]
0x18000aa09  mov     rdx, [rdx]; h
0x18000aa0c  mov     rax, [rbp+57h+arg_0]
0x18000aa10  mov     rcx, [rax]; pwa
0x18000aa13  call    cs:__imp_SetThreadpoolWait
0x18000aa19  mov     byte ptr [rbp+57h+var_50+1], bl
0x18000aa1c  lea     rcx, [rbp+57h+var_60]
0x18000aa20  call    wil__details__ScopeExitFnGuard__lambda_ce4f58e6acb0bd507de9c422b318be30_____operator__
0x18000aa25  nop
0x18000aa26  test    rsi, rsi
0x18000aa29  jz      short loc_18000AA40
0x18000aa2b  mov     rcx, rsi; this
0x18000aa2e  call    ??1NotificationContext@NotificationCallbacks@Notifications@Client@Hns@@QEAA@XZ; Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x18000aa33  mov     edx, 60h ; '`'; unsigned __int64
0x18000aa38  mov     rcx, rsi; void *
0x18000aa3b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aa40  mov     rax, [rbp+57h+var_A8]
0x18000aa44  add     rsp, 0A8h
0x18000aa4b  pop     r15
0x18000aa4d  pop     r14
0x18000aa4f  pop     r13
0x18000aa51  pop     r12
0x18000aa53  pop     rdi
0x18000aa54  pop     rsi
0x18000aa55  pop     rbx
0x18000aa56  pop     rbp
  ... truncated ...
```

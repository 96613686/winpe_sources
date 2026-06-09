# RealtimeProtection::CThreadPoolIoFilterRequest::DoCompletion(CommonUtil::IMpThreadPoolOverlapped::CInfo const &)

- ea: `0x180053170`
- end: `0x180053869`
- name: `?DoCompletion@CThreadPoolIoFilterRequest@RealtimeProtection@@EEAAJAEBUCInfo@IMpThreadPoolOverlapped@CommonUtil@@@Z`
- size: `1785`
- prototype: `__int64 __fastcall(RealtimeProtection::CThreadPoolIoFilterRequest *__hidden this, const struct CommonUtil::IMpThreadPoolOverlapped::CInfo *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180053170`
- `0x180053870`
- `0x180080760`
- `0x1800809d0`
- `0x18009351c`
- `0x18009f730`
- `0x1800a2020`
- `0x1800b51d0`
- `0x180101af8`
- `0x180105db0`
- `0x180105e54`
- `0x180105f50`
- `0x18010cb40`
- `0x1801d2010`
- `0x18023a290`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18005321f`
- `KERNEL32!GetCurrentThread` at `0x1800532af`
- `KERNEL32!GetCurrentThread` at `0x180053705`
- `KERNEL32!GetCurrentThread` at `0x18005321f`
- `KERNEL32!GetCurrentThread` at `0x1800532af`
- `KERNEL32!GetCurrentThread` at `0x180053705`
- `KERNEL32!GetThreadPriority` at `0x18005370e`
- `KERNEL32!GetThreadPriority` at `0x18005370e`
- `KERNEL32!GetCurrentThreadId` at `0x1800531ce`
- `KERNEL32!GetCurrentThreadId` at `0x1800531ce`
- `FLTLIB!FilterReplyMessage` at `0x1800534eb`
- `FLTLIB!FilterReplyMessage` at `0x1800534eb`

## string_xrefs

- `0x1800532fa`: `AsyncWorkerUpdate`
- `0x1800536bc`: `GetThreadInformation`
- `0x18005377c`: `GetThreadInformation`
- `0x1800536e2`: `SetThreadInformation`
- `0x1800537a1`: `SetThreadInformation`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::CThreadPoolIoFilterRequest::DoCompletion(
        RealtimeProtection::CThreadPoolIoFilterRequest *this,
        const struct CommonUtil::IMpThreadPoolOverlapped::CInfo *a2)
{
  unsigned int v4; // r14d
  RealtimeProtection::CThreadPoolIoPortHandlerBase *v5; // rdi
  __int64 v6; // rbx
  int v7; // edx
  RealtimeProtection *v8; // rcx
  const char *v9; // r8
  bool v10; // r9
  unsigned int (__fastcall *v11)(HANDLE, __int64, int *, __int64); // rbx
  HANDLE CurrentThread; // rax
  int LoadedKernel32ProcAddress; // r14d
  int v14; // ebx
  const char *v15; // r8
  bool v16; // r9
  unsigned int (__fastcall *v17)(HANDLE, __int64, int *, __int64); // rsi
  HANDLE v18; // rax
  int v19; // esi
  __int64 v20; // rcx
  __int64 v21; // r8
  char v22; // al
  __int64 v23; // rdx
  __int64 v24; // rcx
  char v25; // si
  PVOID v26; // rcx
  __int64 v27; // r14
  __int64 v29; // r14
  void (__fastcall *v30)(__int64, _QWORD); // rsi
  __int64 v31; // rax
  int v32; // eax
  DWORD v33; // esi
  struct _FILTER_REPLY_HEADER *v34; // rax
  int v35; // edx
  HRESULT v36; // esi
  __int64 v37; // r10
  int v38; // eax
  int v39; // ecx
  char v40; // al
  HANDLE v41; // rax
  int ThreadPriority; // esi
  unsigned int LastFailure; // eax
  int v44; // eax
  int v45; // ecx
  int IsVistaOrGreater; // eax
  unsigned int v47; // [rsp+30h] [rbp-69h]
  __int64 v48; // [rsp+38h] [rbp-61h]
  int v49; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v50; // [rsp+48h] [rbp-51h] BYREF
  int v51; // [rsp+50h] [rbp-49h] BYREF
  const wchar_t *v52; // [rsp+70h] [rbp-29h]
  __int64 v53; // [rsp+78h] [rbp-21h]
  int *v54; // [rsp+80h] [rbp-19h]
  __int64 v55; // [rsp+88h] [rbp-11h]
  unsigned int *v56; // [rsp+90h] [rbp-9h]
  __int64 v57; // [rsp+98h] [rbp-1h]
  int *v58; // [rsp+A0h] [rbp+7h]
  __int64 v59; // [rsp+A8h] [rbp+Fh]

  if ( *((_BYTE *)a2 + 24) )
    return 2147500036LL;
  v4 = *((_DWORD *)a2 + 4);
  v47 = v4;
  v48 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 24LL))(*(_QWORD *)a2);
  v5 = *(RealtimeProtection::CThreadPoolIoPortHandlerBase **)(v48 + 16);
  v6 = *((_QWORD *)this + 12);
  *(_DWORD *)(*((_QWORD *)v5 + 5) + 16 * v6 + 8) = GetCurrentThreadId();
  v8 = (RealtimeProtection *)*((unsigned int *)a2 + 2);
  if ( (int)v8 < 0 )
  {
    if ( !(unsigned int)RealtimeProtection::IsFilterUnloadError(v8, v7) )
    {
      if ( v39 != -2147024774 && v39 != -1073741789 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_478311733890348080e50cbded8c9165_Traceguids,
            *((_QWORD *)v5 + 3),
            v39);
        RealtimeProtection::CThreadPoolIoPortHandlerBase::PrivateSetPenddingRequestForHealthCheck(v5, this, 0);
        return 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v40 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 24LL))(*((_QWORD *)this + 10));
        WPP_SF_SLd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_478311733890348080e50cbded8c9165_Traceguids,
          *((_QWORD *)v5 + 3),
          v40,
          v4);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 40LL))(*((_QWORD *)this + 10), v4);
LABEL_23:
      *(_DWORD *)(*((_QWORD *)v5 + 5) + 16LL * *((_QWORD *)this + 12) + 8) = 0;
      return 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_478311733890348080e50cbded8c9165_Traceguids,
        *((_QWORD *)v5 + 3),
        v39);
    *(_DWORD *)(*((_QWORD *)v5 + 5) + 16LL * *((_QWORD *)this + 12) + 8) = 0;
    return 2147500036LL;
  }
  if ( (unsigned int)MpIsWindows8OrGreater() )
  {
    if ( qword_1803135B0
      || (LOBYTE(v9) = 1,
          LoadedKernel32ProcAddress = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                                        (CommonUtil *)&qword_1803135B0,
                                        (__int64 (**)(void))"GetThreadInformation",
                                        v9,
                                        v10),
          LoadedKernel32ProcAddress >= 0) )
    {
      if ( qword_1803135A8
        || (LOBYTE(v9) = 1,
            LoadedKernel32ProcAddress = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                                          (CommonUtil *)&qword_1803135A8,
                                          (__int64 (**)(void))"SetThreadInformation",
                                          v9,
                                          v10),
            LoadedKernel32ProcAddress >= 0) )
      {
        v49 = 0;
        v11 = (unsigned int (__fastcall *)(HANDLE, __int64, int *, __int64))qword_1803135B0;
        CurrentThread = GetCurrentThread();
        if ( v11(CurrentThread, 1, &v49, 4) )
          LoadedKernel32ProcAddress = v49;
        else
          LoadedKernel32ProcAddress = 0;
      }
    }
  }
  else
  {
    LoadedKernel32ProcAddress = 0;
  }
  v14 = 0x7FFFFFFF;
  if ( ((*(__int64 (__fastcall **)(RealtimeProtection::CThreadPoolIoPortHandlerBase *))(*(_QWORD *)v5 + 8LL))(v5) & 2) != 0 )
  {
    v41 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v41);
    if ( ThreadPriority == 0x7FFFFFFF )
    {
      LastFailure = HrGetLastFailure();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_478311733890348080e50cbded8c9165_Traceguids, LastFailure);
    }
    else
    {
      v44 = ((__int64 (*)(void))MpIsVistaOrGreater)();
      v45 = 0x10000;
      if ( !v44 )
        v45 = -2;
      if ( (int)RealtimeProtection::CAutoLowThreadPriority::UtilSetCurrentThreadPriority(v45) >= 0 )
        v14 = ThreadPriority;
    }
  }
  if ( (Microsoft_Antimalware_RTPEnableBits & 1) != 0 )
  {
    if ( (unsigned int)MpIsWindows8OrGreater() )
    {
      if ( qword_1803135B0
        || (LOBYTE(v15) = 1,
            v19 = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                    (CommonUtil *)&qword_1803135B0,
                    (__int64 (**)(void))"GetThreadInformation",
                    v15,
                    v16),
            v19 >= 0) )
      {
        if ( qword_1803135A8
          || (LOBYTE(v15) = 1,
              v19 = CommonUtil::UtilRawGetLoadedKernel32ProcAddress(
                      (CommonUtil *)&qword_1803135A8,
                      (__int64 (**)(void))"SetThreadInformation",
                      v15,
                      v16),
              v19 >= 0) )
        {
          v49 = 0;
          v17 = (unsigned int (__fastcall *)(HANDLE, __int64, int *, __int64))qword_1803135B0;
          v18 = GetCurrentThread();
          if ( v17(v18, 1, &v49, 4) )
            v19 = v49;
          else
            v19 = 0;
        }
      }
    }
    else
    {
      v19 = 0;
    }
    v50 = ((*(unsigned int (__fastcall **)(RealtimeProtection::CThreadPoolIoPortHandlerBase *))(*(_QWORD *)v5 + 8LL))(v5) >> 1)
        & 1;
    v51 = v19;
    v49 = LoadedKernel32ProcAddress;
    v52 = L"AsyncWorkerUpdate";
    v53 = 36;
    v54 = &v49;
    v55 = 4;
    v56 = &v50;
    v57 = 4;
    v58 = &v51;
    v59 = 4;
    McGenEventWrite_EventWriteTransfer(v20, RTPPriorityEvent, v21, 5);
  }
  v22 = (*(__int64 (__fastcall **)(RealtimeProtection::CThreadPoolIoPortHandlerBase *))(*(_QWORD *)v5 + 8LL))(v5);
  v23 = v47;
  v24 = *((_QWORD *)this + 10);
  if ( (v22 & 1) != 0 )
  {
    v25 = 0;
    LODWORD(v27) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 48LL))(v24, v47);
  }
  else
  {
    if ( v47 >= 0x10 )
    {
      v29 = *((_QWORD *)this + 11);
      v30 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 24LL);
      v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v30(v29, *(_QWORD *)(v31 + 8));
      v24 = *((_QWORD *)this + 10);
      v23 = v47;
    }
    v25 = 1;
    v27 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 48LL))(v24, v23);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 11) + 8LL))(*((_QWORD *)this + 11), v27);
  }
  if ( (int)v27 >= 0 )
  {
    v32 = (*(__int64 (__fastcall **)(RealtimeProtection::CThreadPoolIoPortHandlerBase *, _QWORD, _QWORD))(*(_QWORD *)v5 + 16LL))(
            v5,
            *((_QWORD *)this + 10),
            *((_QWORD *)this + 11));
    if ( v32 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_478311733890348080e50cbded8c9165_Traceguids,
          *((_QWORD *)v5 + 3),
          v32);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_478311733890348080e50cbded8c9165_Traceguids,
      *((_QWORD *)v5 + 3),
      v27);
  }
  if ( !v25 )
    goto LABEL_21;
  v33 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
  v34 = (struct _FILTER_REPLY_HEADER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
  v36 = FilterReplyMessage(*(HANDLE *)(v48 + 24), v34, v33);
  if ( v36 < 0
    && (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 16LL))(*((_QWORD *)this + 11)) >= 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)WPP_478311733890348080e50cbded8c9165_Traceguids,
      *((_QWORD *)v5 + 3),
      v36);
  }
  if ( !(unsigned int)RealtimeProtection::IsFilterUnloadError((RealtimeProtection *)(unsigned int)v36, v35) )
  {
LABEL_21:
    if ( v14 != 0x7FFFFFFF )
    {
      IsVistaOrGreater = MpIsVistaOrGreater(v26);
      RealtimeProtection::CAutoLowThreadPriority::UtilSetCurrentThreadPriority(IsVistaOrGreater != 0 ? 0x20000 : 0);
    }
    goto LABEL_23;
  }
  if ( (PVOID *)v37 != &WPP_GLOBAL_Control && (*(_BYTE *)(v37 + 28) & 2) != 0 )
    WPP_SF_Sd(
      *(_QWORD *)(v37 + 16),
      25,
      (unsigned int)WPP_478311733890348080e50cbded8c9165_Traceguids,
      *((_QWORD *)v5 + 3),
      v36);
  if ( v14 != 0x7FFFFFFF )
  {
    v38 = MpIsVistaOrGreater(v26);
    RealtimeProtection::CAutoLowThreadPriority::UtilSetCurrentThreadPriority(v38 != 0 ? 0x20000 : 0);
  }
  RealtimeProtection::CThreadPoolIoPortHandlerBase::PrivateSetPenddingRequestForHealthCheck(v5, this, 0);
  return 2147500036LL;
}

```

## disassembly

```asm
0x180053170  mov     [rsp-8+arg_10], rbx
0x180053175  push    rbp
0x180053176  push    rsi
0x180053177  push    rdi
0x180053178  push    r12
0x18005317a  push    r13
0x18005317c  push    r14
0x18005317e  push    r15
0x180053180  lea     rbp, [rsp-27h]
0x180053185  sub     rsp, 0C0h
0x18005318c  mov     rax, cs:__security_cookie
0x180053193  xor     rax, rsp
0x180053196  mov     [rbp+57h+var_40], rax
0x18005319a  mov     rsi, rdx
0x18005319d  mov     r13, rcx
0x1800531a0  cmp     byte ptr [rdx+18h], 0
0x1800531a4  jnz     loc_1800535EC
0x1800531aa  mov     r14d, [rdx+10h]
0x1800531ae  mov     [rbp+57h+var_C0], r14d
0x1800531b2  mov     rcx, [rdx]
0x1800531b5  mov     rax, [rcx]
0x1800531b8  mov     rax, [rax+18h]
0x1800531bc  call    cs:__guard_dispatch_icall_fptr
0x1800531c2  mov     [rbp+57h+var_B8], rax
0x1800531c6  mov     rdi, [rax+10h]
0x1800531ca  mov     rbx, [r13+60h]
0x1800531ce  call    cs:__imp_GetCurrentThreadId
0x1800531d4  add     rbx, rbx
0x1800531d7  mov     rcx, [rdi+28h]
0x1800531db  mov     [rcx+rbx*8+8], eax
0x1800531df  mov     ecx, [rsi+8]; this
0x1800531e2  test    ecx, ecx
0x1800531e4  js      loc_180053576
0x1800531ea  call    MpIsWindows8OrGreater
0x1800531ef  xor     r15d, r15d
0x1800531f2  test    eax, eax
0x1800531f4  jz      loc_18005344D
0x1800531fa  cmp     cs:qword_1803135B0, r15
0x180053201  jz      loc_1800536B9
0x180053207  cmp     cs:qword_1803135A8, r15
0x18005320e  jz      loc_1800536DF
0x180053214  mov     [rbp+57h+var_B0], r15d
0x180053218  mov     rbx, cs:qword_1803135B0
0x18005321f  call    cs:__imp_GetCurrentThread
0x180053225  mov     rcx, rax
0x180053228  mov     r9d, 4
0x18005322e  lea     r8, [rbp+57h+var_B0]
0x180053232  mov     edx, 1
0x180053237  mov     rax, rbx
0x18005323a  call    cs:__guard_dispatch_icall_fptr
0x180053240  test    eax, eax
0x180053242  jz      loc_18005356E
0x180053248  mov     r14d, [rbp+57h+var_B0]
0x18005324c  mov     rax, [rdi]
0x18005324f  mov     rcx, rdi
0x180053252  mov     rax, [rax+8]
0x180053256  call    cs:__guard_dispatch_icall_fptr
0x18005325c  lea     r12, WPP_GLOBAL_Control
0x180053263  mov     ebx, 7FFFFFFFh
0x180053268  test    al, 2
0x18005326a  jnz     loc_180053705
0x180053270  test    cs:Microsoft_Antimalware_RTPEnableBits, 1
0x180053277  jz      loc_180053358
0x18005327d  call    MpIsWindows8OrGreater
0x180053282  test    eax, eax
0x180053284  jz      loc_180053455
0x18005328a  cmp     cs:qword_1803135B0, r15
0x180053291  jz      loc_180053779
0x180053297  cmp     cs:qword_1803135A8, r15
0x18005329e  jz      loc_18005379E
0x1800532a4  mov     [rbp+57h+var_B0], r15d
0x1800532a8  mov     rsi, cs:qword_1803135B0
0x1800532af  call    cs:__imp_GetCurrentThread
0x1800532b5  mov     rcx, rax
0x1800532b8  mov     r9d, 4
0x1800532be  lea     r8, [rbp+57h+var_B0]
0x1800532c2  mov     edx, 1
0x1800532c7  mov     rax, rsi
0x1800532ca  call    cs:__guard_dispatch_icall_fptr
0x1800532d0  test    eax, eax
0x1800532d2  jz      loc_1800535BE
0x1800532d8  mov     esi, [rbp+57h+var_B0]
0x1800532db  mov     rax, [rdi]
0x1800532de  mov     rcx, rdi
0x1800532e1  mov     rax, [rax+8]
0x1800532e5  call    cs:__guard_dispatch_icall_fptr
0x1800532eb  shr     eax, 1
0x1800532ed  and     eax, 1
0x1800532f0  mov     [rbp+57h+var_A8], eax
0x1800532f3  mov     [rbp+57h+var_A0], esi
0x1800532f6  mov     [rbp+57h+var_B0], r14d
0x1800532fa  lea     rax, aAsyncworkerupd; "AsyncWorkerUpdate"
0x180053301  mov     [rbp+57h+var_80], rax
0x180053305  mov     [rbp+57h+var_78], 24h ; '$'
0x18005330d  lea     rax, [rbp+57h+var_B0]
0x180053311  mov     [rbp+57h+var_70], rax
0x180053315  mov     [rbp+57h+var_68], 4
0x18005331d  lea     rax, [rbp+57h+var_A8]
0x180053321  mov     [rbp+57h+var_60], rax
0x180053325  mov     [rbp+57h+var_58], 4
0x18005332d  lea     rax, [rbp+57h+var_A0]
0x180053331  mov     [rbp+57h+var_50], rax
0x180053335  mov     [rbp+57h+var_48], 4
0x18005333d  lea     rax, [rbp+57h+var_90]
0x180053341  mov     [rsp+0F0h+var_D0], rax
0x180053346  mov     r9d, 5
0x18005334c  lea     rdx, RTPPriorityEvent
0x180053353  call    McGenEventWrite_EventWriteTransfer
0x180053358  mov     rax, [rdi]
0x18005335b  mov     rcx, rdi
0x18005335e  mov     rax, [rax+8]
0x180053362  call    cs:__guard_dispatch_icall_fptr
0x180053368  mov     edx, [rbp+57h+var_C0]
0x18005336b  mov     rcx, [r13+50h]
0x18005336f  test    al, 1
0x180053371  jz      short loc_1800533ED
0x180053373  xor     sil, sil
0x180053376  mov     rax, [rcx]
0x180053379  mov     rax, [rax+30h]
0x18005337d  call    cs:__guard_dispatch_icall_fptr
0x180053383  mov     r14d, eax
0x180053386  test    r14d, r14d
0x180053389  jns     loc_18005345D
0x18005338f  mov     rax, cs:WPP_GLOBAL_Control
0x180053396  cmp     rax, r12
0x180053399  jnz     loc_1800537C3
0x18005339f  test    sil, sil
0x1800533a2  jnz     loc_1800534B9
0x1800533a8  cmp     ebx, 7FFFFFFFh
0x1800533ae  jnz     loc_180053850
0x1800533b4  mov     rcx, [r13+60h]
0x1800533b8  mov     rax, [rdi+28h]
0x1800533bc  add     rcx, rcx
0x1800533bf  mov     [rax+rcx*8+8], r15d
0x1800533c4  xor     eax, eax
0x1800533c6  mov     rcx, [rbp+57h+var_40]
0x1800533ca  xor     rcx, rsp; StackCookie
0x1800533cd  call    __security_check_cookie
0x1800533d2  mov     rbx, [rsp+0F0h+arg_10]
0x1800533da  add     rsp, 0C0h
0x1800533e1  pop     r15
0x1800533e3  pop     r14
0x1800533e5  pop     r13
0x1800533e7  pop     r12
0x1800533e9  pop     rdi
0x1800533ea  pop     rsi
0x1800533eb  pop     rbp
0x1800533ec  retn
0x1800533ed  cmp     edx, 10h
0x1800533f0  jb      short loc_180053421
0x1800533f2  mov     r14, [r13+58h]
0x1800533f6  mov     rax, [r14]
0x1800533f9  mov     rsi, [rax+18h]
0x1800533fd  mov     rdx, [rcx]
0x180053400  mov     rax, [rdx+10h]
0x180053404  call    cs:__guard_dispatch_icall_fptr
0x18005340a  mov     rdx, [rax+8]
0x18005340e  mov     rcx, r14
0x180053411  mov     rax, rsi
0x180053414  call    cs:__guard_dispatch_icall_fptr
0x18005341a  mov     rcx, [r13+50h]
0x18005341e  mov     edx, [rbp+57h+var_C0]
0x180053421  mov     rax, [rcx]
0x180053424  mov     rax, [rax+30h]
0x180053428  call    cs:__guard_dispatch_icall_fptr
0x18005342e  mov     sil, 1
0x180053431  mov     r14d, eax
0x180053434  mov     rcx, [r13+58h]
0x180053438  mov     rax, [rcx]
0x18005343b  mov     edx, r14d
0x18005343e  mov     rax, [rax+8]
0x180053442  call    cs:__guard_dispatch_icall_fptr
0x180053448  jmp     loc_180053386
0x18005344d  mov     r14d, r15d
0x180053450  jmp     loc_18005324C
0x180053455  mov     esi, r15d
0x180053458  jmp     loc_1800532DB
0x18005345d  mov     rax, [rdi]
0x180053460  mov     r8, [r13+58h]
0x180053464  mov     rdx, [r13+50h]
0x180053468  mov     rcx, rdi
0x18005346b  mov     rax, [rax+10h]
0x18005346f  call    cs:__guard_dispatch_icall_fptr
0x180053475  test    eax, eax
0x180053477  jns     loc_18005339F
0x18005347d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053484  cmp     rcx, r12
0x180053487  jz      loc_18005339F
0x18005348d  test    byte ptr [rcx+1Ch], 1
0x180053491  jz      loc_18005339F
0x180053497  mov     edx, 16h
0x18005349c  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800534a0  mov     r9, [rdi+18h]
0x1800534a4  lea     r8, WPP_478311733890348080e50cbded8c9165_Traceguids
0x1800534ab  mov     rcx, [rcx+10h]
0x1800534af  call    WPP_SF_Sd
0x1800534b4  jmp     loc_18005339F
0x1800534b9  mov     rcx, [r13+58h]
0x1800534bd  mov     rax, [rcx]
0x1800534c0  mov     rax, [rax+28h]
0x1800534c4  call    cs:__guard_dispatch_icall_fptr
0x1800534ca  mov     esi, eax
0x1800534cc  mov     rcx, [r13+58h]
0x1800534d0  mov     rdx, [rcx]
0x1800534d3  mov     rax, [rdx+20h]
0x1800534d7  call    cs:__guard_dispatch_icall_fptr
0x1800534dd  mov     r8d, esi; dwReplyBufferSize
0x1800534e0  mov     rdx, rax; lpReplyBuffer
0x1800534e3  mov     rcx, [rbp+57h+var_B8]
0x1800534e7  mov     rcx, [rcx+18h]; hPort
0x1800534eb  call    cs:__imp_FilterReplyMessage
0x1800534f1  mov     esi, eax
0x1800534f3  test    eax, eax
0x1800534f5  js      loc_1800537FA
0x1800534fb  mov     r10, cs:WPP_GLOBAL_Control
0x180053502  mov     ecx, esi; this
0x180053504  call    ?IsFilterUnloadError@RealtimeProtection@@YAHJ@Z; RealtimeProtection::IsFilterUnloadError(long)
0x180053509  test    eax, eax
0x18005350b  jz      loc_1800533A8
0x180053511  cmp     r10, r12
0x180053514  jz      short loc_18005353A
0x180053516  test    byte ptr [r10+1Ch], 2
0x18005351b  jz      short loc_18005353A
0x18005351d  mov     edx, 19h
0x180053522  mov     dword ptr [rsp+0F0h+var_D0], esi
0x180053526  mov     r9, [rdi+18h]
0x18005352a  lea     r8, WPP_478311733890348080e50cbded8c9165_Traceguids
0x180053531  mov     rcx, [r10+10h]
0x180053535  call    WPP_SF_Sd
0x18005353a  cmp     ebx, 7FFFFFFFh
0x180053540  jz      short loc_180053556
0x180053542  call    MpIsVistaOrGreater
0x180053547  neg     eax
0x180053549  sbb     ecx, ecx
0x18005354b  and     ecx, 20000h; nPriority
0x180053551  call    ?UtilSetCurrentThreadPriority@CAutoLowThreadPriority@RealtimeProtection@@CAJH@Z; RealtimeProtection::CAutoLowThreadPriority::UtilSetCurrentThreadPriority(int)
0x180053556  xor     r8d, r8d; bool
0x180053559  mov     rdx, r13; struct RealtimeProtection::CThreadPoolIoFilterRequest *
0x18005355c  mov     rcx, rdi; this
0x18005355f  call    ?PrivateSetPenddingRequestForHealthCheck@CThreadPoolIoPortHandlerBase@RealtimeProtection@@QEAAXPEAVCThreadPoolIoFilterRequest@2@_N@Z; RealtimeProtection::CThreadPoolIoPortHandlerBase::PrivateSetPenddingRequestForHealthCheck(RealtimeProtection::CThreadPoolIoFilterRequest *,bool)
0x180053564  mov     eax, 80004004h
0x180053569  jmp     loc_1800533C6
0x18005356e  mov     r14d, r15d
0x180053571  jmp     loc_18005324C
0x180053576  call    ?IsFilterUnloadError@RealtimeProtection@@YAHJ@Z; RealtimeProtection::IsFilterUnloadError(long)
0x18005357b  test    eax, eax
0x18005357d  jnz     short loc_1800535C6
0x18005357f  cmp     ecx, 8007007Ah
0x180053585  jnz     loc_18005361B
0x18005358b  lea     r12, WPP_GLOBAL_Control
0x180053592  mov     rax, cs:WPP_GLOBAL_Control
0x180053599  cmp     rax, r12
0x18005359c  jnz     loc_180053670
0x1800535a2  mov     rcx, [r13+50h]
0x1800535a6  mov     rax, [rcx]
0x1800535a9  mov     edx, r14d
0x1800535ac  mov     rax, [rax+28h]
0x1800535b0  call    cs:__guard_dispatch_icall_fptr
0x1800535b6  xor     r15d, r15d
0x1800535b9  jmp     loc_1800533B4
0x1800535be  mov     esi, r15d
0x1800535c1  jmp     loc_1800532DB
0x1800535c6  lea     r12, WPP_GLOBAL_Control
0x1800535cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800535d4  cmp     rax, r12
0x1800535d7  jnz     short loc_1800535F6
0x1800535d9  mov     rcx, [r13+60h]
0x1800535dd  add     rcx, rcx
0x1800535e0  mov     rax, [rdi+28h]
0x1800535e4  xor     r15d, r15d
0x1800535e7  mov     [rax+rcx*8+8], r15d
0x1800535ec  mov     eax, 80004004h
0x1800535f1  jmp     loc_1800533C6
0x1800535f6  test    byte ptr [rax+1Ch], 2
0x1800535fa  jz      short loc_1800535D9
0x1800535fc  mov     edx, 0Dh
0x180053601  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x180053605  mov     r9, [rdi+18h]
0x180053609  lea     r8, WPP_478311733890348080e50cbded8c9165_Traceguids
0x180053610  mov     rcx, [rax+10h]
0x180053614  call    WPP_SF_Sd
0x180053619  jmp     short loc_1800535D9
0x18005361b  cmp     ecx, 0C0000023h
0x180053621  jz      loc_18005358B
0x180053627  lea     r12, WPP_GLOBAL_Control
0x18005362e  mov     rax, cs:WPP_GLOBAL_Control
0x180053635  cmp     rax, r12
0x180053638  jz      short loc_18005365D
0x18005363a  test    byte ptr [rax+1Ch], 1
0x18005363e  jz      short loc_18005365D
0x180053640  mov     edx, 0Fh
0x180053645  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x180053649  mov     r9, [rdi+18h]
0x18005364d  lea     r8, WPP_478311733890348080e50cbded8c9165_Traceguids
0x180053654  mov     rcx, [rax+10h]
0x180053658  call    WPP_SF_Sd
0x18005365d  xor     r8d, r8d; bool
0x180053660  mov     rdx, r13; struct RealtimeProtection::CThreadPoolIoFilterRequest *
0x180053663  mov     rcx, rdi; this
0x180053666  call    ?PrivateSetPenddingRequestForHealthCheck@CThreadPoolIoPortHandlerBase@RealtimeProtection@@QEAAXPEAVCThreadPoolIoFilterRequest@2@_N@Z; RealtimeProtection::CThreadPoolIoPortHandlerBase::PrivateSetPenddingRequestForHealthCheck(RealtimeProtection::CThreadPoolIoFilterRequest *,bool)
  ... truncated ...
```

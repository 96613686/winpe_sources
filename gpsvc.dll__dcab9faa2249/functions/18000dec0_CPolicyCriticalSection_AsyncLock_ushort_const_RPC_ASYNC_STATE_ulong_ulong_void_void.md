# CPolicyCriticalSection::AsyncLock(ushort const *,_RPC_ASYNC_STATE *,ulong,ulong,void *,void * *)

- ea: `0x18000dec0`
- end: `0x18000e5e9`
- name: `?AsyncLock@CPolicyCriticalSection@@AEAAKPEBGPEAU_RPC_ASYNC_STATE@@KKPEAXPEAPEAX@Z`
- size: `1833`
- prototype: `__int64 __fastcall(CPolicyCriticalSection *this, const unsigned __int16 *, struct _RPC_ASYNC_STATE *, __int64, unsigned int, void *, void **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, installer_update`

## callers

- `0x18000e5f0`

## callees

- `0x180007b38`
- `0x180008380`
- `0x18000844c`
- `0x18000a910`
- `0x18000bbe0`
- `0x18000dec0`
- `0x180049d10`
- `0x18004b498`
- `0x180075ec0`
- `0x18007d304`
- `0x18007d320`
- `0x18007d6f0`
- `0x18007d770`
- `0x18007de08`
- `0x180093234`
- `0x1800935d0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e0cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e16e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e0cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e16e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000e280`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000e280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e34e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e412`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e34e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e412`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e3ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e3ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e140`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e181`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e57f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e57f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e3b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e3e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e484`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e591`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e3b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e3e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e484`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e591`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e024`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e041`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e024`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e041`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000df97`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000df97`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000e000`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000e000`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000e0ec`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000e0ec`

## string_xrefs

- `0x18000e0bb`: `OpenProcessFailed`
- `0x18000e075`: `AsyncLock: OpenProcess failed for PID:0x%x - Error 0x%x`
- `0x18000e0aa`: `AsyncLock: OpenProcess failed for PID:0x%x - Error 0x%x`
- `0x18000e523`: `Calling DoWriterUnlock for %d.`
- `0x18000e551`: `Calling DoWriterUnlock for %d.`
- `0x18000e4bc`: `Calling WakeupReaders.`
- `0x18000e4ec`: `Calling WakeupReaders.`

## pseudocode

```c
__int64 __fastcall CPolicyCriticalSection::AsyncLock(
        CPolicyCriticalSection *this,
        const unsigned __int16 *a2,
        struct _RPC_ASYNC_STATE *a3,
        __int64 a4,
        unsigned int a5,
        void *a6,
        void **a7)
{
  HLOCAL *v10; // rax
  HLOCAL *v11; // rbx
  unsigned int v12; // eax
  DWORD v13; // r8d
  HANDLE v14; // rdi
  void (*v15)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v16; // eax
  DWORD v17; // eax
  void (*v18)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD LastError; // eax
  DWORD v20; // eax
  unsigned int PolicySectionContext; // r15d
  _QWORD *v22; // rax
  void *v23; // r8
  _DWORD *v24; // rdx
  char IsEnabled; // al
  __int64 v26; // rdi
  __int64 v27; // rbp
  struct _RTL_CRITICAL_SECTION *v28; // rdi
  _DWORD *v29; // rax
  __int64 v30; // r9
  _QWORD *j; // rcx
  _QWORD *v32; // r14
  void *v33; // rcx
  _QWORD *v34; // rax
  void *v35; // rcx
  __int64 v36; // r9
  _QWORD *i; // rcx
  _QWORD *v38; // r14
  void *v39; // rcx
  __int64 v40; // rax
  _QWORD *v41; // rax
  void *v42; // rcx
  unsigned int v44; // [rsp+20h] [rbp-108h]
  DWORD dwSize[2]; // [rsp+30h] [rbp-F8h] BYREF
  DWORD pSessionId; // [rsp+38h] [rbp-F0h] BYREF
  HLOCAL *v47; // [rsp+40h] [rbp-E8h]
  _DWORD RpcCallAttributes[2]; // [rsp+50h] [rbp-D8h] BYREF
  __int128 v49; // [rsp+58h] [rbp-D0h]
  __int128 v50; // [rsp+68h] [rbp-C0h]
  __int128 v51; // [rsp+78h] [rbp-B0h]
  DWORD dwProcessId[4]; // [rsp+88h] [rbp-A0h]
  __int128 v53; // [rsp+98h] [rbp-90h]
  __int128 v54; // [rsp+A8h] [rbp-80h]
  __int128 v55; // [rsp+B8h] [rbp-70h]

  *a7 = 0;
  v10 = (HLOCAL *)operator new(0x258u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
  {
    operator delete(0);
    PolicySectionContext = 14;
    goto LABEL_98;
  }
  v10[2] = 0;
  v10[3] = 0;
  v10[7] = 0;
  v10[8] = 0;
  *((_DWORD *)v10 + 18) = 0;
  memset_0((char *)v10 + 76, 0, 0x208u);
  *((_DWORD *)v11 + 149) = 0;
  operator delete(0);
  v47 = v11;
  *v11 = a3;
  v11[1] = (HLOCAL)a2;
  v11[2] = 0;
  v11[6] = this;
  *((_DWORD *)v11 + 8) = a5;
  v11[7] = a6;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::GetImpl'::`2'::impl) )
  {
    GetSystemTimeAsFileTime((LPFILETIME)v11 + 8);
    *((_DWORD *)v11 + 18) = 0;
    *((_WORD *)v11 + 38) = 0;
    *((_DWORD *)v11 + 149) = 0;
    if ( (a5 & 0x20000000) != 0 )
    {
      v49 = 0;
      v50 = 0;
      v51 = 0;
      *(_OWORD *)dwProcessId = 0;
      v53 = 0;
      v54 = 0;
      v55 = 0;
      RpcCallAttributes[1] = 16;
      RpcCallAttributes[0] = 3;
      v12 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
      if ( v12 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"AsyncLock: RpcServerInqCallAttributes failed: 0x%x", v12);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"AsyncLock: RpcServerInqCallAttributes failed: 0x%x", v12);
          }
        }
      }
      else
      {
        v13 = dwProcessId[2];
        *((_DWORD *)v11 + 18) = dwProcessId[2];
        v14 = OpenProcess(0x400u, 0, v13);
        if ( v14 || (v14 = OpenProcess(0x1000u, 0, *((_DWORD *)v11 + 18))) != 0 )
        {
          dwSize[0] = 260;
          if ( !QueryFullProcessImageNameW(v14, 0, (LPWSTR)v11 + 38, dwSize) )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v18 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                LastError = GetLastError();
                v18(
                  4u,
                  L"AsyncLock: QueryFullProcessImageName failed for PID:0x%x - Error 0x%x",
                  *((unsigned int *)v11 + 18),
                  LastError);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                v20 = GetLastError();
                RedirectDebugMsg(
                  4u,
                  L"AsyncLock: QueryFullProcessImageName failed for PID:0x%x - Error 0x%x",
                  *((unsigned int *)v11 + 18),
                  v20);
              }
            }
            _o_wcscpy_s((char *)v11 + 76, 260, L"QueryProcessNameFailed");
          }
          pSessionId = 0;
          if ( ProcessIdToSessionId(*((_DWORD *)v11 + 18), &pSessionId) )
            *((_DWORD *)v11 + 149) = pSessionId;
          CloseHandle(v14);
        }
        else
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v15 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v16 = GetLastError();
              v15(2u, L"AsyncLock: OpenProcess failed for PID:0x%x - Error 0x%x", *((unsigned int *)v11 + 18), v16);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v17 = GetLastError();
              RedirectDebugMsg(
                2u,
                L"AsyncLock: OpenProcess failed for PID:0x%x - Error 0x%x",
                *((unsigned int *)v11 + 18),
                v17);
            }
          }
          _o_wcscpy_s((char *)v11 + 76, 260, L"OpenProcessFailed");
        }
      }
    }
  }
  PolicySectionContext = CRWLock::Lock(*(_QWORD *)this, 0, v11 + 5);
  if ( PolicySectionContext )
    goto LABEL_99;
  v22 = v11[5];
  v23 = (void *)v22[1];
  if ( !v23 )
  {
    *(_QWORD *)dwSize = 0;
    PolicySectionContext = CPolicyCriticalSection::CreatePolicySectionContext(
                             v11[1],
                             *((unsigned int *)v11 + 8),
                             v22,
                             0,
                             0,
                             dwSize);
    if ( !PolicySectionContext )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::GetImpl'::`2'::impl);
      v26 = *(_QWORD *)dwSize;
      if ( IsEnabled && *(_QWORD *)dwSize && ((_DWORD)v11[4] & 0x20000000) != 0 )
      {
        *(_DWORD *)(*(_QWORD *)dwSize + 48LL) = *((_DWORD *)v11 + 18);
        _o_wcsncpy_s(v26 + 52, 260, (char *)v11 + 76, 260);
        *(_DWORD *)(v26 + 572) = *((_DWORD *)v11 + 149);
        *(_QWORD *)(v26 + 32) = v11[8];
      }
      PolicySectionContext = CPolicyCriticalSection::AddReaderToList(this, (struct _POLICY_SECTION_CONTEXT *)v26);
      if ( !PolicySectionContext )
      {
        *a7 = (void *)v26;
        goto LABEL_99;
      }
      CPolicyCriticalSection::DeletePolicySectionContext((HLOCAL)v26);
    }
    goto LABEL_48;
  }
  PolicySectionContext = CPolicyCriticalSection::RegisterWaitForLockNotificationOrClientCancellation(
                           this,
                           (struct CPolicyCriticalSection::CLockCallbackContext *)v11,
                           v23,
                           a6,
                           v44);
  if ( !PolicySectionContext )
  {
LABEL_98:
    v11 = 0;
    goto LABEL_99;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"RegisterWaitForLockNotificationOrClientCancellation failed with 0x%x", PolicySectionContext);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(
        2u,
        L"RegisterWaitForLockNotificationOrClientCancellation failed with 0x%x",
        PolicySectionContext);
    }
  }
LABEL_48:
  v27 = *(_QWORD *)this;
  v28 = *(struct _RTL_CRITICAL_SECTION **)(v27 + 72);
  v29 = v11[5];
  *(_QWORD *)dwSize = v28;
  if ( v29[4] )
  {
    if ( v28 )
      EnterCriticalSection(v28);
    v36 = *(_QWORD *)(v27 + 24);
    if ( v36 )
    {
      for ( i = **(_QWORD ***)v36; i != *(_QWORD **)v36; i = (_QWORD *)*i )
      {
        v38 = (_QWORD *)i[2];
        v24 = v11[5];
        if ( *v24 == *(_DWORD *)v38 )
        {
          *(_QWORD *)i[1] = *i;
          *(_QWORD *)(*i + 8LL) = i[1];
          --*(_QWORD *)(v36 + 8);
          operator delete(i);
          v39 = (void *)v38[1];
          if ( v39 )
            CloseHandle(v39);
          v38[1] = 0;
          LocalFree(v38);
          v40 = *(_QWORD *)(v27 + 24);
          if ( (!v40 || !*(_QWORD *)(v40 + 8)) && *(_DWORD *)(v27 + 12) != 2 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"Calling WakeupReaders.");
                CRWLock::WakeupWaitingReaders((CRWLock *)v27);
                goto LABEL_92;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                RedirectDebugMsg(4u, L"Calling WakeupReaders.");
            }
            CRWLock::WakeupWaitingReaders((CRWLock *)v27);
          }
          goto LABEL_92;
        }
      }
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Calling DoWriterUnlock for %d.", *(unsigned int *)v11[5]);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Calling DoWriterUnlock for %d.", *(unsigned int *)v11[5]);
      }
    }
    CRWLock::DoWriterUnLock((CRWLock *)v27, (unsigned int)v24);
LABEL_92:
    v41 = v11[5];
    if ( v41 )
    {
      v42 = (void *)v41[1];
      if ( v42 )
        CloseHandle(v42);
      *((_QWORD *)v11[5] + 1) = 0;
      LocalFree(v11[5]);
      v11[5] = 0;
    }
  }
  else
  {
    if ( v28 )
      EnterCriticalSection(v28);
    v30 = *(_QWORD *)(v27 + 16);
    if ( v30 )
    {
      for ( j = **(_QWORD ***)v30; j != *(_QWORD **)v30; j = (_QWORD *)*j )
      {
        v32 = (_QWORD *)j[2];
        v24 = v11[5];
        if ( *v24 == *(_DWORD *)v32 )
        {
          *(_QWORD *)j[1] = *j;
          *(_QWORD *)(*j + 8LL) = j[1];
          --*(_QWORD *)(v30 + 8);
          operator delete(j);
          v33 = (void *)v32[1];
          if ( v33 )
            CloseHandle(v33);
          v32[1] = 0;
          LocalFree(v32);
          goto LABEL_60;
        }
      }
    }
    CRWLock::DoReaderUnLock((CRWLock *)v27, (unsigned int)v24);
LABEL_60:
    v34 = v11[5];
    if ( v34 )
    {
      v35 = (void *)v34[1];
      if ( v35 )
        CloseHandle(v35);
      *((_QWORD *)v11[5] + 1) = 0;
      LocalFree(v11[5]);
      v11[5] = 0;
    }
  }
  if ( v28 )
    LeaveCriticalSection(v28);
LABEL_99:
  operator delete(v11);
  return PolicySectionContext;
}

```

## disassembly

```asm
0x18000dec0  push    rbx
0x18000dec2  push    rbp
0x18000dec3  push    rsi
0x18000dec4  push    rdi
0x18000dec5  push    r12
0x18000dec7  push    r13
0x18000dec9  push    r14
0x18000decb  push    r15
0x18000decd  sub     rsp, 0E8h
0x18000ded4  mov     rax, cs:__security_cookie
0x18000dedb  xor     rax, rsp
0x18000dede  mov     [rsp+128h+var_58], rax
0x18000dee6  mov     rdi, r8
0x18000dee9  mov     rsi, rdx
0x18000deec  mov     rbp, rcx
0x18000deef  mov     r13, [rsp+128h+arg_28]
0x18000def7  mov     r12, [rsp+128h+arg_30]
0x18000deff  xor     r14d, r14d
0x18000df02  mov     [r12], r14
0x18000df06  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000df0d  mov     ecx, 258h; unsigned __int64
0x18000df12  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000df17  mov     rbx, rax
0x18000df1a  test    rax, rax
0x18000df1d  jz      loc_18000E5A0
0x18000df23  mov     [rax+10h], r14
0x18000df27  mov     [rax+18h], r14
0x18000df2b  mov     [rax+38h], r14
0x18000df2f  xor     eax, eax
0x18000df31  mov     [rbx+40h], rax
0x18000df35  mov     [rbx+48h], r14d
0x18000df39  lea     rcx, [rbx+4Ch]; void *
0x18000df3d  xor     edx, edx; Val
0x18000df3f  mov     r8d, 208h; Size
0x18000df45  call    memset_0
0x18000df4a  mov     [rbx+254h], r14d
0x18000df51  mov     edx, 258h
0x18000df56  xor     ecx, ecx; Block
0x18000df58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000df5d  mov     [rsp+128h+var_E8], rbx
0x18000df62  mov     [rbx], rdi
0x18000df65  mov     [rbx+8], rsi
0x18000df69  mov     [rbx+10h], r14
0x18000df6d  mov     [rbx+30h], rbp
0x18000df71  mov     edi, [rsp+128h+arg_20]
0x18000df78  mov     [rbx+20h], edi
0x18000df7b  mov     [rbx+38h], r13
0x18000df7f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::GetImpl(void)'::`2'::impl
0x18000df86  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::__private_IsEnabled(void)
0x18000df8b  test    al, al
0x18000df8d  jz      loc_18000E1EB
0x18000df93  lea     rcx, [rbx+40h]; lpSystemTimeAsFileTime
0x18000df97  call    cs:__imp_GetSystemTimeAsFileTime
0x18000df9d  mov     [rbx+48h], r14d
0x18000dfa1  xor     eax, eax
0x18000dfa3  mov     [rbx+4Ch], ax
0x18000dfa7  mov     [rbx+254h], eax
0x18000dfad  bt      edi, 1Dh
0x18000dfb1  jnb     loc_18000E1EB
0x18000dfb7  xorps   xmm0, xmm0
0x18000dfba  movups  [rsp+128h+var_D0], xmm0
0x18000dfbf  movups  [rsp+128h+var_C0], xmm0
0x18000dfc4  movups  [rsp+128h+var_B0], xmm0
0x18000dfc9  movups  xmmword ptr [rsp+128h+dwProcessId], xmm0
0x18000dfd1  movups  [rsp+128h+var_90], xmm0
0x18000dfd9  movups  [rsp+128h+var_80], xmm0
0x18000dfe1  movups  [rsp+128h+var_70], xmm0
0x18000dfe9  mov     [rsp+128h+var_D4], 10h
0x18000dff1  mov     [rsp+128h+RpcCallAttributes], 3
0x18000dff9  lea     rdx, [rsp+128h+RpcCallAttributes]; RpcCallAttributes
0x18000dffe  xor     ecx, ecx; ClientBinding
0x18000e000  call    cs:__imp_RpcServerInqCallAttributesW
0x18000e006  mov     r8d, eax
0x18000e009  test    eax, eax
0x18000e00b  jnz     loc_18000E1A0
0x18000e011  mov     r8d, [rsp+128h+dwProcessId+8]; dwProcessId
0x18000e019  mov     [rbx+48h], r8d
0x18000e01d  xor     edx, edx; bInheritHandle
0x18000e01f  mov     ecx, 400h; dwDesiredAccess
0x18000e024  call    cs:__imp_OpenProcess
0x18000e02a  mov     rdi, rax
0x18000e02d  test    rax, rax
0x18000e030  jnz     loc_18000E0D6
0x18000e036  mov     r8d, [rbx+48h]; dwProcessId
0x18000e03a  xor     edx, edx; bInheritHandle
0x18000e03c  mov     ecx, 1000h; dwDesiredAccess
0x18000e041  call    cs:__imp_OpenProcess
0x18000e047  mov     rdi, rax
0x18000e04a  test    rax, rax
0x18000e04d  jnz     loc_18000E0D6
0x18000e053  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18000e05a  jz      short loc_18000E0BB
0x18000e05c  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000e063  test    rdi, rdi
0x18000e066  jz      short loc_18000E08B
0x18000e068  call    cs:__imp_GetLastError
0x18000e06e  mov     r9d, eax
0x18000e071  mov     r8d, [rbx+48h]
0x18000e075  lea     rdx, aAsynclockOpenp; "AsyncLock: OpenProcess failed for PID:0"...
0x18000e07c  mov     ecx, 2
0x18000e081  mov     rax, rdi
0x18000e084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e089  jmp     short loc_18000E0BB
0x18000e08b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18000e092  jz      short loc_18000E0BB
0x18000e094  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000e09b  jz      short loc_18000E0BB
0x18000e09d  call    cs:__imp_GetLastError
0x18000e0a3  mov     r9d, eax
0x18000e0a6  mov     r8d, [rbx+48h]
0x18000e0aa  lea     rdx, aAsynclockOpenp; "AsyncLock: OpenProcess failed for PID:0"...
0x18000e0b1  mov     ecx, 2; unsigned int
0x18000e0b6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000e0bb  lea     r8, aOpenprocessfai; "OpenProcessFailed"
0x18000e0c2  mov     edx, 104h
0x18000e0c7  lea     rcx, [rbx+4Ch]
0x18000e0cb  call    cs:__imp__o_wcscpy_s
0x18000e0d1  jmp     loc_18000E1EB
0x18000e0d6  mov     [rsp+128h+dwSize], 104h
0x18000e0de  lea     r9, [rsp+128h+dwSize]; lpdwSize
0x18000e0e3  lea     r8, [rbx+4Ch]; lpExeName
0x18000e0e7  xor     edx, edx; dwFlags
0x18000e0e9  mov     rcx, rdi; hProcess
0x18000e0ec  call    cs:__imp_QueryFullProcessImageNameW
0x18000e0f2  test    eax, eax
0x18000e0f4  jnz     short loc_18000E174
0x18000e0f6  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18000e0fd  jz      short loc_18000E15E
0x18000e0ff  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000e106  test    rsi, rsi
0x18000e109  jz      short loc_18000E12E
0x18000e10b  call    cs:__imp_GetLastError
0x18000e111  mov     r9d, eax
0x18000e114  mov     r8d, [rbx+48h]
0x18000e118  lea     rdx, aAsynclockQuery; "AsyncLock: QueryFullProcessImageName fa"...
0x18000e11f  mov     ecx, 4
0x18000e124  mov     rax, rsi
0x18000e127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e12c  jmp     short loc_18000E15E
0x18000e12e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18000e135  jz      short loc_18000E15E
0x18000e137  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000e13e  jz      short loc_18000E15E
0x18000e140  call    cs:__imp_GetLastError
0x18000e146  mov     r9d, eax
0x18000e149  mov     r8d, [rbx+48h]
0x18000e14d  lea     rdx, aAsynclockQuery; "AsyncLock: QueryFullProcessImageName fa"...
0x18000e154  mov     ecx, 4; unsigned int
0x18000e159  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000e15e  lea     r8, aQueryprocessna; "QueryProcessNameFailed"
0x18000e165  mov     edx, 104h
0x18000e16a  lea     rcx, [rbx+4Ch]
0x18000e16e  call    cs:__imp__o_wcscpy_s
0x18000e174  mov     [rsp+128h+pSessionId], r14d
0x18000e179  lea     rdx, [rsp+128h+pSessionId]; pSessionId
0x18000e17e  mov     ecx, [rbx+48h]; dwProcessId
0x18000e181  call    cs:__imp_ProcessIdToSessionId
0x18000e187  test    eax, eax
0x18000e189  jz      short loc_18000E195
0x18000e18b  mov     eax, [rsp+128h+pSessionId]
0x18000e18f  mov     [rbx+254h], eax
0x18000e195  mov     rcx, rdi; hObject
0x18000e198  call    cs:__imp_CloseHandle
0x18000e19e  jmp     short loc_18000E1EB
0x18000e1a0  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18000e1a7  jz      short loc_18000E1EB
0x18000e1a9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000e1b0  test    rax, rax
0x18000e1b3  jz      short loc_18000E1C8
0x18000e1b5  lea     rdx, aAsynclockRpcse; "AsyncLock: RpcServerInqCallAttributes f"...
0x18000e1bc  mov     ecx, 2
0x18000e1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c6  jmp     short loc_18000E1EB
0x18000e1c8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18000e1cf  jz      short loc_18000E1EB
0x18000e1d1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000e1d8  jz      short loc_18000E1EB
0x18000e1da  lea     rdx, aAsynclockRpcse; "AsyncLock: RpcServerInqCallAttributes f"...
0x18000e1e1  mov     ecx, 2; unsigned int
0x18000e1e6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000e1eb  lea     r8, [rbx+28h]
0x18000e1ef  xor     edx, edx
0x18000e1f1  mov     rcx, [rbp+0]
0x18000e1f5  call    ?Lock@CRWLock@@QEAAKW4LockType@@PEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::Lock(LockType,_RWLOCK_CONTEXT * *)
0x18000e1fa  mov     r15d, eax
0x18000e1fd  test    eax, eax
0x18000e1ff  jnz     loc_18000E5B5
0x18000e205  mov     rax, [rbx+28h]
0x18000e209  mov     r8, [rax+8]; void *
0x18000e20d  test    r8, r8
0x18000e210  jnz     loc_18000E2BF
0x18000e216  mov     qword ptr [rsp+128h+dwSize], r14
0x18000e21b  lea     rcx, [rsp+128h+dwSize]
0x18000e220  mov     [rsp+128h+var_100], rcx
0x18000e225  mov     [rsp+128h+var_108], r14d
0x18000e22a  xor     r9d, r9d
0x18000e22d  mov     r8, rax
0x18000e230  mov     edx, [rbx+20h]
0x18000e233  mov     rcx, [rbx+8]
0x18000e237  call    ?CreatePolicySectionContext@CPolicyCriticalSection@@CAKPEBGKPEAU_RWLOCK_CONTEXT@@HW4LockType@@PEAPEAU_POLICY_SECTION_CONTEXT@@@Z; CPolicyCriticalSection::CreatePolicySectionContext(ushort const *,ulong,_RWLOCK_CONTEXT *,int,LockType,_POLICY_SECTION_CONTEXT * *)
0x18000e23c  mov     r15d, eax
0x18000e23f  test    eax, eax
0x18000e241  jnz     loc_18000E32B
0x18000e247  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::GetImpl(void)'::`2'::impl
0x18000e24e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::__private_IsEnabled(void)
0x18000e253  mov     rdi, qword ptr [rsp+128h+dwSize]
0x18000e258  test    al, al
0x18000e25a  jz      short loc_18000E29A
0x18000e25c  test    rdi, rdi
0x18000e25f  jz      short loc_18000E29A
0x18000e261  test    dword ptr [rbx+20h], 20000000h
0x18000e268  jz      short loc_18000E29A
0x18000e26a  mov     eax, [rbx+48h]
0x18000e26d  mov     [rdi+30h], eax
0x18000e270  lea     r8, [rbx+4Ch]
0x18000e274  lea     rcx, [rdi+34h]
0x18000e278  mov     edx, 104h
0x18000e27d  mov     r9d, edx
0x18000e280  call    cs:__imp__o_wcsncpy_s
0x18000e286  mov     eax, [rbx+254h]
0x18000e28c  mov     [rdi+23Ch], eax
0x18000e292  mov     rax, [rbx+40h]
0x18000e296  mov     [rdi+20h], rax
0x18000e29a  mov     rdx, rdi; struct _POLICY_SECTION_CONTEXT *
0x18000e29d  mov     rcx, rbp; this
0x18000e2a0  call    ?AddReaderToList@CPolicyCriticalSection@@AEAAKPEAU_POLICY_SECTION_CONTEXT@@@Z; CPolicyCriticalSection::AddReaderToList(_POLICY_SECTION_CONTEXT *)
0x18000e2a5  mov     r15d, eax
0x18000e2a8  test    eax, eax
0x18000e2aa  jz      short loc_18000E2B6
0x18000e2ac  mov     rcx, rdi; hMem
0x18000e2af  call    ?DeletePolicySectionContext@CPolicyCriticalSection@@CAXPEAU_POLICY_SECTION_CONTEXT@@@Z; CPolicyCriticalSection::DeletePolicySectionContext(_POLICY_SECTION_CONTEXT *)
0x18000e2b4  jmp     short loc_18000E32B
0x18000e2b6  mov     [r12], rdi
0x18000e2ba  jmp     loc_18000E5B5
0x18000e2bf  mov     r9, r13; void *
0x18000e2c2  mov     rdx, rbx; struct CPolicyCriticalSection::CLockCallbackContext *
0x18000e2c5  mov     rcx, rbp; this
0x18000e2c8  call    ?RegisterWaitForLockNotificationOrClientCancellation@CPolicyCriticalSection@@AEAAKPEAVCLockCallbackContext@1@PEAX1K@Z; CPolicyCriticalSection::RegisterWaitForLockNotificationOrClientCancellation(CPolicyCriticalSection::CLockCallbackContext *,void *,void *,ulong)
0x18000e2cd  mov     r15d, eax
0x18000e2d0  test    eax, eax
0x18000e2d2  jz      loc_18000E5B2
0x18000e2d8  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000e2df  jz      short loc_18000E32B
0x18000e2e1  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000e2e8  test    rax, rax
0x18000e2eb  jz      short loc_18000E303
0x18000e2ed  mov     r8d, r15d
0x18000e2f0  lea     rdx, aRegisterwaitfo; "RegisterWaitForLockNotificationOrClient"...
0x18000e2f7  mov     ecx, 2
0x18000e2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e301  jmp     short loc_18000E32B
0x18000e303  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18000e30b  jz      short loc_18000E32B
0x18000e30d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000e315  jz      short loc_18000E32B
0x18000e317  mov     r8d, r15d
0x18000e31a  lea     rdx, aRegisterwaitfo; "RegisterWaitForLockNotificationOrClient"...
0x18000e321  mov     ecx, 2; unsigned int
0x18000e326  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000e32b  mov     rbp, [rbp+0]
0x18000e32f  mov     rdi, [rbp+48h]
0x18000e333  mov     rax, [rbx+28h]
0x18000e337  mov     qword ptr [rsp+128h+dwSize], rdi
0x18000e33c  cmp     dword ptr [rax+10h], 0
0x18000e340  jnz     loc_18000E40A
0x18000e346  test    rdi, rdi
0x18000e349  jz      short loc_18000E355
0x18000e34b  mov     rcx, rdi; lpCriticalSection
0x18000e34e  call    cs:__imp_EnterCriticalSection
0x18000e354  nop
0x18000e355  mov     r9, [rbp+10h]
0x18000e359  test    r9, r9
0x18000e35c  jz      short loc_18000E3BB
0x18000e35e  mov     r8, [r9]
0x18000e361  mov     rcx, [r8]; Block
0x18000e364  cmp     rcx, r8
0x18000e367  jz      short loc_18000E3BB
0x18000e369  mov     r14, [rcx+10h]
0x18000e36d  mov     rdx, [rbx+28h]
0x18000e371  mov     eax, [r14]
0x18000e374  cmp     [rdx], eax
0x18000e376  jz      short loc_18000E37D
0x18000e378  mov     rcx, [rcx]
0x18000e37b  jmp     short loc_18000E364
0x18000e37d  mov     rdx, [rcx+8]
0x18000e381  mov     rax, [rcx]
0x18000e384  mov     [rdx], rax
0x18000e387  mov     rdx, [rcx]
0x18000e38a  mov     rax, [rcx+8]
0x18000e38e  mov     [rdx+8], rax
0x18000e392  dec     qword ptr [r9+8]
0x18000e396  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e39b  mov     rcx, [r14+8]; hObject
0x18000e39f  test    rcx, rcx
0x18000e3a2  jz      short loc_18000E3AA
0x18000e3a4  call    cs:__imp_CloseHandle
0x18000e3aa  xor     ebp, ebp
0x18000e3ac  mov     [r14+8], rbp
0x18000e3b0  mov     rcx, r14; hMem
0x18000e3b3  call    cs:__imp_LocalFree
  ... truncated ...
```

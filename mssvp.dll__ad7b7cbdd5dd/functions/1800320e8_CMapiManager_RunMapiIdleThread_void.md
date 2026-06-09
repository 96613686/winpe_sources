# CMapiManager::RunMapiIdleThread(void)

- ea: `0x1800320e8`
- end: `0x180032503`
- name: `?RunMapiIdleThread@CMapiManager@@QEAAKXZ`
- size: `1051`
- prototype: `unsigned int __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180031a40`

## callees

- `0x180004850`
- `0x1800048c0`
- `0x18000a56c`
- `0x180013bbc`
- `0x180018758`
- `0x18002d248`
- `0x18002d33c`
- `0x18002d37c`
- `0x18002ef70`
- `0x18002f7f8`
- `0x1800307d4`
- `0x1800308ec`
- `0x180030b78`
- `0x180031620`
- `0x180031954`
- `0x180031b6c`
- `0x180031ce0`
- `0x180031eac`
- `0x1800320e8`
- `0x18003250c`
- `0x1800327ec`
- `0x180033da0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032441`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032441`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032467`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003218f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003218f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003224d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003230e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032396`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032499`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003224d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003230e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032396`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032499`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180032164`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180032164`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800324c8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800324c8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1800321f1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1800321f1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180032215`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180032215`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800321fb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800321fb`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800322c0`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800322c0`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIUninitialize` at `0x1800324ac`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIUninitialize` at `0x1800324ac`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitIdle` at `0x18003217a`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitIdle` at `0x18003217a`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIDeinitIdle` at `0x180032484`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIDeinitIdle` at `0x180032484`

## string_xrefs

- `0x1800324a0`: `   CMapiManager::UninitializeThread() MapiUninitialize() Calling...`
- `0x1800324b2`: `   CMapiManager::UninitializeThread() MapiUninitialize() Completed!`
- `0x1800324d5`: `CMapiManager::RunMapiIdleThread() Exit`
- `0x180032104`: `CMapiManager::RunMapiIdleThread() Enter`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMapiManager::RunMapiIdleThread(CMapiManager *this)
{
  __int64 v2; // rbx
  _QWORD *v3; // rax
  DWORD v4; // edx
  CMapiManager *v5; // rcx
  LONG v6; // eax
  int v7; // ebx
  int v8; // esi
  int v9; // r13d
  HANDLE *v10; // r15
  DWORD v11; // eax
  int v12; // r14d
  HANDLE v13; // r14
  __int64 v14; // rax
  HANDLE **NextValue; // rax
  HANDLE *v16; // rbx
  __int64 v17; // r14
  int i; // ebx
  __int64 v19; // rax
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+30h] [rbp-49h] BYREF
  HANDLE *pHandles; // [rsp+38h] [rbp-41h] BYREF
  DWORD nCount[2]; // [rsp+40h] [rbp-39h]
  __int64 v24; // [rsp+48h] [rbp-31h] BYREF
  __int64 v25; // [rsp+50h] [rbp-29h]
  MSG Msg; // [rsp+58h] [rbp-21h] BYREF
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 StartPosition; // [rsp+F0h] [rbp+77h] BYREF
  struct _RTL_CRITICAL_SECTION *v30; // [rsp+F8h] [rbp+7Fh] BYREF

  CLogger::Info(L"CMapiManager::RunMapiIdleThread() Enter");
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v28);
  v2 = 0xC000000000000LL;
  if ( !(unsigned int)CMapiSupport::GetInstalledOutlookVersion(&v28) )
  {
    v3 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
           &v27,
           &v28);
    v2 = CMapiSupport::ConvertToIntVersion(v3);
  }
  v4 = 2;
  if ( v2 != 0x9000000000000LL )
    v4 = 0;
  CoInitializeEx(0, v4);
  v6 = CMapiManager::InitializeThread(v5);
  v7 = v6;
  LODWORD(v27) = v6;
  if ( v6 >= 0 )
    v6 = MAPIInitIdle(0);
  v8 = v6;
  *((_DWORD *)this + 48) = v6;
  SetEvent(*((HANDLE *)this + 23));
  memset(&Msg, 0, sizeof(Msg));
  if ( v8 >= 0 )
  {
    while ( !*((_DWORD *)this + 33) )
    {
      pHandles = 0;
      *(_QWORD *)nCount = 0;
      if ( !(unsigned int)CMapiManager::PingSessions(this) )
        CMapiManager::SendShutdownNotification(this);
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        if ( Msg.message == 18 )
        {
          *((_DWORD *)this + 33) = 1;
        }
        else
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(&pHandles, (char *)this + 136);
      ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(&pHandles, (char *)this + 272);
      v21 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 352);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
      v9 = *((_DWORD *)this + 72);
      StartPosition = ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition((char *)this + 280);
      while ( StartPosition )
      {
        v30 = **(struct _RTL_CRITICAL_SECTION ***)ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(
                                                    (char *)this + 280,
                                                    &StartPosition);
        ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(&pHandles, &v30);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
      v10 = pHandles;
      v11 = MsgWaitForMultipleObjects(nCount[0], pHandles, 0, 0x7530u, 0x1CFFu);
      if ( v11 )
      {
        if ( v11 == 1 || (v12 = v11 - (v11 >= 0x80 ? 0x80 : 0), v12 - 2 >= v9) )
        {
          CMapiManager::CleanupStoreWatchers(this, 0);
        }
        else
        {
          v24 = 0;
          v25 = 0;
          v30 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 352);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
          if ( v12 < 0 || v12 >= (int)nCount[0] )
          {
            RaiseException(0xC000008C, 1u, 0, 0);
            break;
          }
          v13 = v10[v12];
          v14 = ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition((char *)this + 280);
          StartPosition = v14;
          while ( v14 )
          {
            NextValue = (HANDLE **)ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(
                                     (char *)this + 280,
                                     &StartPosition);
            v16 = *NextValue;
            if ( v13 == **NextValue )
            {
              ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::operator=(
                &v24,
                v16 + 2);
              ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(v16 + 2);
              CMapiManager::CleanupStoreWatchers(this, 0);
              break;
            }
            v14 = StartPosition;
          }
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
          if ( (int)v25 > 0 )
          {
            v30 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
            StartPosition = ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition((char *)this + 16);
            while ( StartPosition )
            {
              v17 = *(_QWORD *)ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(
                                 (char *)this + 16,
                                 &StartPosition);
              if ( v17 )
              {
                for ( i = 0; i < (int)v25; ++i )
                {
                  v19 = ATL::CSimpleArray<HINSTANCE__ *,ATL::CSimpleArrayEqualHelper<HINSTANCE__ *>>::operator[](
                          &v24,
                          (unsigned int)i);
                  CMapiSession::ReleaseStore(v17, v19);
                }
              }
            }
            CMapiManager::ReleaseUnusedSessions(this);
            if ( !*((_QWORD *)this + 3) )
              CMapiManager::SendShutdownNotification(this);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
          }
          ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(&v24);
        }
      }
      else
      {
        *((_DWORD *)this + 33) = 1;
      }
      if ( v10 )
      {
        free(v10);
        pHandles = 0;
      }
      *(_QWORD *)nCount = 0;
    }
    v7 = (int)v27;
  }
  *((_DWORD *)this + 40) = 0;
  CMapiManager::Terminate(this);
  if ( v8 >= 0 )
    MAPIDeinitIdle();
  if ( v7 >= 0 )
  {
    v27 = &CMapiManager::s_csMapiIdleThread;
    EnterCriticalSection(&CMapiManager::s_csMapiIdleThread);
    CLogger::Info(L"   CMapiManager::UninitializeThread() MapiUninitialize() Calling...");
    MAPIUninitialize();
    CLogger::Info(L"   CMapiManager::UninitializeThread() MapiUninitialize() Completed!");
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v27);
  }
  CoUninitialize();
  *((_DWORD *)this + 32) = 0;
  CLogger::Info(v8, L"CMapiManager::RunMapiIdleThread() Exit");
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v28);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800320e8  push    rbp
0x1800320ea  push    rbx
0x1800320eb  push    rsi
0x1800320ec  push    rdi
0x1800320ed  push    r12
0x1800320ef  push    r13
0x1800320f1  push    r14
0x1800320f3  push    r15
0x1800320f5  lea     rbp, [rsp-1Fh]
0x1800320fa  sub     rsp, 98h
0x180032101  mov     rdi, rcx
0x180032104  lea     rcx, aCmapimanagerRu; "CMapiManager::RunMapiIdleThread() Enter"
0x18003210b  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180032110  lea     rcx, [rbp+57h+arg_8]
0x180032114  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180032119  nop
0x18003211a  mov     rbx, 0C000000000000h
0x180032124  lea     rcx, [rbp+57h+arg_8]
0x180032128  call    ?GetInstalledOutlookVersion@CMapiSupport@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::GetInstalledOutlookVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18003212d  xor     r13d, r13d
0x180032130  test    eax, eax
0x180032132  jnz     short loc_18003214C
0x180032134  lea     rdx, [rbp+57h+arg_8]
0x180032138  lea     rcx, [rbp+57h+arg_0]
0x18003213c  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180032141  mov     rcx, rax
0x180032144  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x180032149  mov     rbx, rax
0x18003214c  mov     edx, 2
0x180032151  mov     rax, 9000000000000h
0x18003215b  cmp     rbx, rax
0x18003215e  cmovnz  edx, r13d; dwCoInit
0x180032162  xor     ecx, ecx; pvReserved
0x180032164  call    cs:__imp_CoInitializeEx
0x18003216a  call    ?InitializeThread@CMapiManager@@QEAAJXZ; CMapiManager::InitializeThread(void)
0x18003216f  mov     ebx, eax
0x180032171  mov     dword ptr [rbp+57h+arg_0], eax
0x180032174  test    eax, eax
0x180032176  js      short loc_180032180
0x180032178  xor     ecx, ecx; lpvReserved
0x18003217a  call    cs:__imp_MAPIInitIdle
0x180032180  mov     esi, eax
0x180032182  mov     [rdi+0C0h], eax
0x180032188  mov     rcx, [rdi+0B8h]; hEvent
0x18003218f  call    cs:__imp_SetEvent
0x180032195  xorps   xmm0, xmm0
0x180032198  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18003219c  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x1800321a0  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x1800321a4  test    esi, esi
0x1800321a6  js      loc_180032471
0x1800321ac  cmp     [rdi+84h], r13d
0x1800321b3  jnz     loc_18003246E
0x1800321b9  mov     [rbp+57h+pHandles], r13
0x1800321bd  mov     qword ptr [rbp+57h+nCount], 0
0x1800321c5  mov     rcx, rdi; this
0x1800321c8  call    ?PingSessions@CMapiManager@@QEAAHXZ; CMapiManager::PingSessions(void)
0x1800321cd  test    eax, eax
0x1800321cf  jnz     short loc_180032201
0x1800321d1  mov     rcx, rdi; this
0x1800321d4  call    ?SendShutdownNotification@CMapiManager@@AEAAXXZ; CMapiManager::SendShutdownNotification(void)
0x1800321d9  jmp     short loc_180032201
0x1800321db  cmp     [rbp+57h+Msg.message], 12h
0x1800321df  jnz     short loc_1800321ED
0x1800321e1  mov     dword ptr [rdi+84h], 1
0x1800321eb  jmp     short loc_180032201
0x1800321ed  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800321f1  call    cs:__imp_TranslateMessage
0x1800321f7  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800321fb  call    cs:__imp_DispatchMessageW
0x180032201  mov     [rsp+0D0h+wRemoveMsg], 1; wRemoveMsg
0x180032209  xor     r9d, r9d; wMsgFilterMax
0x18003220c  xor     r8d, r8d; wMsgFilterMin
0x18003220f  xor     edx, edx; hWnd
0x180032211  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180032215  call    cs:__imp_PeekMessageW
0x18003221b  test    eax, eax
0x18003221d  jnz     short loc_1800321DB
0x18003221f  lea     rdx, [rdi+88h]
0x180032226  lea     rcx, [rbp+57h+pHandles]
0x18003222a  call    ?Add@?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAAHAEBQEAX@Z; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(void * const &)
0x18003222f  lea     rdx, [rdi+110h]
0x180032236  lea     rcx, [rbp+57h+pHandles]
0x18003223a  call    ?Add@?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAAHAEBQEAX@Z; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(void * const &)
0x18003223f  lea     rbx, [rdi+160h]
0x180032246  mov     [rbp+57h+var_A0], rbx
0x18003224a  mov     rcx, rbx; lpCriticalSection
0x18003224d  call    cs:__imp_EnterCriticalSection
0x180032253  lea     r12, [rdi+118h]
0x18003225a  mov     r13d, [rdi+120h]
0x180032261  mov     rcx, r12
0x180032264  call    ?GetStartPosition@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition(void)
0x180032269  mov     [rbp+57h+arg_10], rax
0x18003226d  test    rax, rax
0x180032270  jz      short loc_18003229C
0x180032272  lea     rdx, [rbp+57h+arg_10]
0x180032276  mov     rcx, r12
0x180032279  call    ?GetNextValue@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAAEAPEAVCStoreWatcher@CMapiManager@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(__POSITION * &)
0x18003227e  mov     rcx, [rax]
0x180032281  mov     rax, [rcx]
0x180032284  mov     [rbp+57h+arg_18], rax
0x180032288  lea     rdx, [rbp+57h+arg_18]
0x18003228c  lea     rcx, [rbp+57h+pHandles]
0x180032290  call    ?Add@?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAAHAEBQEAX@Z; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(void * const &)
0x180032295  cmp     [rbp+57h+arg_10], 0
0x18003229a  jnz     short loc_180032272
0x18003229c  lea     rcx, [rbp+57h+var_A0]
0x1800322a0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800322a5  mov     [rsp+0D0h+wRemoveMsg], 1CFFh; dwWakeMask
0x1800322ad  mov     r9d, 7530h; dwMilliseconds
0x1800322b3  xor     r8d, r8d; fWaitAll
0x1800322b6  mov     r15, [rbp+57h+pHandles]
0x1800322ba  mov     rdx, r15; pHandles
0x1800322bd  mov     ecx, [rbp+57h+nCount]; nCount
0x1800322c0  call    cs:__imp_MsgWaitForMultipleObjects
0x1800322c6  mov     r14d, eax
0x1800322c9  mov     eax, 80h
0x1800322ce  cmp     r14d, eax
0x1800322d1  sbb     ecx, ecx
0x1800322d3  not     ecx
0x1800322d5  and     ecx, eax
0x1800322d7  mov     eax, r14d
0x1800322da  test    r14d, r14d
0x1800322dd  jz      loc_18003242C
0x1800322e3  cmp     eax, 1
0x1800322e6  jz      loc_18003241C
0x1800322ec  sub     r14d, ecx
0x1800322ef  lea     eax, [r14-2]
0x1800322f3  cmp     eax, r13d
0x1800322f6  jge     loc_18003241C
0x1800322fc  xor     r13d, r13d
0x1800322ff  mov     [rbp+57h+var_88], r13
0x180032303  mov     [rbp+57h+var_80], r13
0x180032307  mov     [rbp+57h+arg_18], rbx
0x18003230b  mov     rcx, rbx; lpCriticalSection
0x18003230e  call    cs:__imp_EnterCriticalSection
0x180032314  nop
0x180032315  test    r14d, r14d
0x180032318  js      loc_180032458
0x18003231e  cmp     r14d, [rbp+57h+nCount]
0x180032322  jge     loc_180032458
0x180032328  movsxd  rax, r14d
0x18003232b  mov     r14, [r15+rax*8]
0x18003232f  mov     rcx, r12
0x180032332  call    ?GetStartPosition@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition(void)
0x180032337  mov     [rbp+57h+arg_10], rax
0x18003233b  test    rax, rax
0x18003233e  jz      short loc_18003237B
0x180032340  lea     rdx, [rbp+57h+arg_10]
0x180032344  mov     rcx, r12
0x180032347  call    ?GetNextValue@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAAEAPEAVCStoreWatcher@CMapiManager@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(__POSITION * &)
0x18003234c  mov     rbx, [rax]
0x18003234f  cmp     r14, [rbx]
0x180032352  jz      short loc_18003235A
0x180032354  mov     rax, [rbp+57h+arg_10]
0x180032358  jmp     short loc_18003233B
0x18003235a  lea     rdx, [rbx+10h]
0x18003235e  lea     rcx, [rbp+57h+var_88]
0x180032362  call    ??4?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::operator=(ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>> const &)
0x180032367  lea     rcx, [rbx+10h]
0x18003236b  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x180032370  xor     edx, edx; int
0x180032372  mov     rcx, rdi; this
0x180032375  call    ?CleanupStoreWatchers@CMapiManager@@AEAAXH@Z; CMapiManager::CleanupStoreWatchers(int)
0x18003237a  nop
0x18003237b  lea     rcx, [rbp+57h+arg_18]
0x18003237f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180032384  cmp     dword ptr [rbp+57h+var_80], r13d
0x180032388  jle     loc_180032411
0x18003238e  lea     rcx, [rdi+58h]; lpCriticalSection
0x180032392  mov     [rbp+57h+arg_18], rcx
0x180032396  call    cs:__imp_EnterCriticalSection
0x18003239c  nop
0x18003239d  lea     rcx, [rdi+10h]
0x1800323a1  call    ?GetStartPosition@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition(void)
0x1800323a6  mov     [rbp+57h+arg_10], rax
0x1800323aa  test    rax, rax
0x1800323ad  jz      short loc_1800323F0
0x1800323af  lea     rdx, [rbp+57h+arg_10]
0x1800323b3  lea     rcx, [rdi+10h]
0x1800323b7  call    ?GetNextValue@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAAEAPEAVCStoreWatcher@CMapiManager@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(__POSITION * &)
0x1800323bc  mov     r14, [rax]
0x1800323bf  test    r14, r14
0x1800323c2  jz      short loc_1800323EA
0x1800323c4  mov     ebx, r13d
0x1800323c7  cmp     dword ptr [rbp+57h+var_80], r13d
0x1800323cb  jle     short loc_1800323EA
0x1800323cd  mov     edx, ebx
0x1800323cf  lea     rcx, [rbp+57h+var_88]
0x1800323d3  call    ??A?$CSimpleArray@PEAUHINSTANCE__@@V?$CSimpleArrayEqualHelper@PEAUHINSTANCE__@@@ATL@@@ATL@@QEAAAEAPEAUHINSTANCE__@@H@Z; ATL::CSimpleArray<HINSTANCE__ *,ATL::CSimpleArrayEqualHelper<HINSTANCE__ *>>::operator[](int)
0x1800323d8  mov     rdx, rax
0x1800323db  mov     rcx, r14
0x1800323de  call    ?ReleaseStore@CMapiSession@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::ReleaseStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800323e3  inc     ebx
0x1800323e5  cmp     ebx, dword ptr [rbp+57h+var_80]
0x1800323e8  jl      short loc_1800323CD
0x1800323ea  cmp     [rbp+57h+arg_10], r13
0x1800323ee  jnz     short loc_1800323AF
0x1800323f0  mov     rcx, rdi; this
0x1800323f3  call    ?ReleaseUnusedSessions@CMapiManager@@QEAAXXZ; CMapiManager::ReleaseUnusedSessions(void)
0x1800323f8  cmp     [rdi+18h], r13
0x1800323fc  jnz     short loc_180032407
0x1800323fe  mov     rcx, rdi; this
0x180032401  call    ?SendShutdownNotification@CMapiManager@@AEAAXXZ; CMapiManager::SendShutdownNotification(void)
0x180032406  nop
0x180032407  lea     rcx, [rbp+57h+arg_18]
0x18003240b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180032410  nop
0x180032411  lea     rcx, [rbp+57h+var_88]
0x180032415  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x18003241a  jmp     short loc_180032439
0x18003241c  xor     edx, edx; int
0x18003241e  mov     rcx, rdi; this
0x180032421  call    ?CleanupStoreWatchers@CMapiManager@@AEAAXH@Z; CMapiManager::CleanupStoreWatchers(int)
0x180032426  nop
0x180032427  xor     r13d, r13d
0x18003242a  jmp     short loc_180032439
0x18003242c  mov     dword ptr [rdi+84h], 1
0x180032436  xor     r13d, r13d
0x180032439  test    r15, r15
0x18003243c  jz      short loc_18003244B
0x18003243e  mov     rcx, r15; Block
0x180032441  call    cs:__imp_free
0x180032447  mov     [rbp+57h+pHandles], r13
0x18003244b  mov     qword ptr [rbp+57h+nCount], 0
0x180032453  jmp     loc_1800321AC
0x180032458  xor     r9d, r9d; lpArguments
0x18003245b  xor     r8d, r8d; nNumberOfArguments
0x18003245e  lea     edx, [r9+1]; dwExceptionFlags
0x180032462  mov     ecx, 0C000008Ch; dwExceptionCode
0x180032467  call    cs:__imp_RaiseException
0x18003246d  nop
0x18003246e  mov     ebx, dword ptr [rbp+57h+arg_0]
0x180032471  mov     [rdi+0A0h], r13d
0x180032478  mov     rcx, rdi; this
0x18003247b  call    ?Terminate@CMapiManager@@AEAAJXZ; CMapiManager::Terminate(void)
0x180032480  test    esi, esi
0x180032482  js      short loc_18003248A
0x180032484  call    cs:__imp_MAPIDeinitIdle
0x18003248a  test    ebx, ebx
0x18003248c  js      short loc_1800324C8
0x18003248e  lea     rcx, ?s_csMapiIdleThread@CMapiManager@@0VCriticalSection@@A; lpCriticalSection
0x180032495  mov     [rbp+57h+arg_0], rcx
0x180032499  call    cs:__imp_EnterCriticalSection
0x18003249f  nop
0x1800324a0  lea     rcx, aCmapimanagerUn_0; "   CMapiManager::UninitializeThread() M"...
0x1800324a7  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x1800324ac  call    cs:__imp_MAPIUninitialize
0x1800324b2  lea     rcx, aCmapimanagerUn; "   CMapiManager::UninitializeThread() M"...
0x1800324b9  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x1800324be  nop
0x1800324bf  lea     rcx, [rbp+57h+arg_0]
0x1800324c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800324c8  call    cs:__imp_CoUninitialize
0x1800324ce  mov     [rdi+80h], r13d
0x1800324d5  lea     rdx, aCmapimanagerRu_0; "CMapiManager::RunMapiIdleThread() Exit"
0x1800324dc  mov     ecx, esi; int
0x1800324de  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x1800324e3  nop
0x1800324e4  lea     rcx, [rbp+57h+arg_8]
0x1800324e8  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x1800324ed  mov     eax, esi
0x1800324ef  add     rsp, 98h
0x1800324f6  pop     r15
0x1800324f8  pop     r14
0x1800324fa  pop     r13
0x1800324fc  pop     r12
0x1800324fe  pop     rdi
0x1800324ff  pop     rsi
0x180032500  pop     rbx
0x180032501  pop     rbp
0x180032502  retn
```

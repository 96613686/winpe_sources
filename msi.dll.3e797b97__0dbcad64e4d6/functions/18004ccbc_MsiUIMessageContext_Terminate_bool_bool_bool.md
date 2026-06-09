# MsiUIMessageContext::Terminate(bool,bool,bool)

- ea: `0x18004ccbc`
- end: `0x18004d63c`
- name: `?Terminate@MsiUIMessageContext@@QEAA_N_N00@Z`
- size: `2432`
- prototype: `bool __fastcall(MsiUIMessageContext *__hidden this, bool, bool, bool)`
- caller_count: `11`
- callee_count: `40`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800075f4`
- `0x180009268`
- `0x18002f750`
- `0x1801318d0`
- `0x18015cb2c`
- `0x18016f43c`
- `0x18019a634`
- `0x18019b520`
- `0x18019b6c0`
- `0x1801a87d8`
- `0x1801d0c00`

## callees

- `0x180005af8`
- `0x18000b8bc`
- `0x18000c4bc`
- `0x18000ca3c`
- `0x18000d6d8`
- `0x180010ac0`
- `0x1800141e0`
- `0x1800202e4`
- `0x18004a014`
- `0x18004bad4`
- `0x18004ccbc`
- `0x18004dc10`
- `0x18004e85c`
- `0x180061c4c`
- `0x1800a5e58`
- `0x1800a614c`
- `0x1800a65d4`
- `0x1800b2e70`
- `0x1800b3314`
- `0x1800b988c`
- `0x180120824`
- `0x180120e0c`
- `0x18012f908`
- `0x180148a30`
- `0x180158c04`
- `0x180159944`
- `0x18015b290`
- `0x18015c49c`
- `0x1801bfadc`
- `0x1801bfb54`
- `0x1801c012c`
- `0x1801c7714`
- `0x1801c8684`
- `0x1801c86ac`
- `0x1801c86d4`
- `0x1801c8ad4`
- `0x1801cb160`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18004ce6e`
- `KERNEL32!DeleteCriticalSection` at `0x18004d376`
- `KERNEL32!DeleteCriticalSection` at `0x18004ce6e`
- `KERNEL32!DeleteCriticalSection` at `0x18004d376`
- `KERNEL32!CloseHandle` at `0x18004cd4c`
- `KERNEL32!CloseHandle` at `0x18004cf40`
- `KERNEL32!CloseHandle` at `0x18004cff5`
- `KERNEL32!CloseHandle` at `0x18004d009`
- `KERNEL32!CloseHandle` at `0x18004d512`
- `KERNEL32!CloseHandle` at `0x18004d525`
- `KERNEL32!CloseHandle` at `0x18004cd4c`
- `KERNEL32!CloseHandle` at `0x18004cf40`
- `KERNEL32!CloseHandle` at `0x18004cff5`
- `KERNEL32!CloseHandle` at `0x18004d009`
- `KERNEL32!CloseHandle` at `0x18004d512`
- `KERNEL32!CloseHandle` at `0x18004d525`
- `KERNEL32!LeaveCriticalSection` at `0x18004d584`
- `KERNEL32!LeaveCriticalSection` at `0x18004d584`
- `KERNEL32!DeleteFileW` at `0x18004d558`
- `KERNEL32!DeleteFileW` at `0x18004d558`
- `KERNEL32!EnterCriticalSection` at `0x18004d39e`
- `KERNEL32!EnterCriticalSection` at `0x18004d39e`
- `KERNEL32!GlobalFree` at `0x18004d4f8`
- `KERNEL32!GlobalFree` at `0x18004d4f8`
- `KERNEL32!FreeLibrary` at `0x18004cfdb`
- `KERNEL32!FreeLibrary` at `0x18004cfdb`
- `KERNEL32!TerminateThread` at `0x18004cd3c`
- `KERNEL32!TerminateThread` at `0x18004cd3c`
- `USER32!DestroyWindow` at `0x18004ce3e`
- `USER32!DestroyWindow` at `0x18004ce3e`

## string_xrefs

- `0x18004d3bd`: `=== MSI `

## pseudocode

```c
char __fastcall MsiUIMessageContext::Terminate(MsiUIMessageContext *this, char a2, char a3, char a4)
{
  CMsiSQMSession *v5; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  struct IUnknown *v10; // r14
  HWND v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  void *v17; // rcx
  HMODULE v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  int v21; // esi
  struct CRestartManagerWrapper * near *v22; // rbx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // edx
  CMsiSystemChange *v26; // rcx
  CMsiSQMSession *v27; // rcx
  CMsiEnvironmentBlock *v28; // rcx
  CMsiEnvironmentBlock *v29; // rcx
  struct IMsiServices *Services; // rbx
  struct IMsiConfigurationManager *ConfigurationManager; // rax
  int v32; // ebx
  const unsigned __int16 *v33; // r8
  __int64 v34; // rbx
  __int64 v35; // rax
  CLogFile *v36; // rcx
  bool v37; // zf
  struct IMsiConfigurationManager *v38; // rax
  struct IMsiConfigurationManager *v41; // [rsp+68h] [rbp-98h] BYREF
  WCHAR String[9]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v43[190]; // [rsp+82h] [rbp-7Eh] BYREF

  v5 = (CMsiSQMSession *)*((_QWORD *)this + 30);
  if ( v5 && g_scServerContext == 2 )
  {
    CMsiSQMSession::`scalar deleting destructor'(v5, a2);
    *((_QWORD *)this + 30) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 12);
  if ( v8 )
  {
    if ( *((_BYTE *)this + 149) )
      MsiUIMessageContext::Invoke(this, 251658549, 0);
    else
      TerminateThread(v8, 0);
    CloseHandle(*((HANDLE *)this + 12));
    *((_QWORD *)this + 12) = 0;
  }
  v9 = *((_QWORD *)this + 35);
  *((_BYTE *)this + 149) = 0;
  *((_BYTE *)this + 227) = 0;
  if ( v9 != -1 )
  {
    if ( v9 )
      SFC::SfcClose();
    *((_QWORD *)this + 35) = -1;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal>::GetImpl'::`2'::impl) )
    Unbind((struct UnbindStruct *)&SFC::rgUnbind, &qword_180314310, &dword_180314308, &byte_180310CEC);
  v10 = CMsiTransaction::m_pMsiTransaction;
  if ( !*((_QWORD *)this + 29) && (!CMsiTransaction::m_pMsiTransaction || a4) )
    MsiUIMessageContext::ClearSaferHandle(this);
  *((_DWORD *)this + 79) = 0;
  CAPITempBuffer<unsigned short,1>::Destroy(&g_rgchBannerText);
  CAPITempBuffer<unsigned short,1>::Destroy(&g_rgchScriptInProgress);
  CAPITempBuffer<unsigned short,1>::Destroy(&g_rgchTimeRemaining);
  CAPITempBuffer<unsigned short,1>::Destroy(&g_rgchFatalOutOfMemory);
  CAPITempBuffer<unsigned short,1>::Destroy(&g_rgchFatalTimedOut);
  CAPITempBuffer<unsigned short,1>::Destroy(&g_rgchFatalException);
  v11 = (HWND)*((_QWORD *)this + 26);
  if ( v11 )
  {
    DestroyWindow(v11);
    *((_QWORD *)this + 26) = 0;
  }
  IsolationAwareUnregisterClassW();
  if ( g_scServerContext == 2 && CProductContextCache::g_fInitialized )
  {
    DeleteCriticalSection(&CProductContextCache::g_csCacheCriticalSection);
    CAPITempBuffer<sProductContext,20>::Destroy(&CProductContextCache::g_rgProductContext);
    CProductContextCache::g_cProductCacheCount = 0;
    CProductContextCache::g_fInitialized = 0;
  }
  if ( a2 )
  {
    *((_QWORD *)this + 7) = 0;
    g_piSharedDllsRegKey = 0;
    g_piSharedDllsRegKey32 = 0;
    goto LABEL_30;
  }
  v13 = *((_QWORD *)this + 7);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)this + 7) = 0;
  }
  v14 = *((_QWORD *)this + 17);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_30:
    *((_QWORD *)this + 17) = 0;
  }
  v15 = *((_QWORD *)this + 34);
  if ( v15 )
  {
    LOBYTE(v12) = a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 56LL))(v15, v12);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 16LL))(*((_QWORD *)this + 34));
    *((_QWORD *)this + 34) = 0;
  }
  v16 = *((_QWORD *)this + 21);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *((_QWORD *)this + 21) = 0;
  }
  v17 = (void *)*((_QWORD *)this + 10);
  if ( v17 )
  {
    CloseHandle(v17);
    *((_QWORD *)this + 10) = 0;
  }
  *((_DWORD *)this + 48) = 0;
  if ( !a4 )
  {
    if ( ((dword_180313928 & 0x2000) == 0
       || !(unsigned int)CMsiAPIMessageRec::Message(g_messageRec, 218103808, &off_18030FDB0))
      && (dword_180313768 & 0x2000) != 0 )
    {
      CMsiAPIMessage::Message(g_message, 218103808, 0);
    }
    if ( g_pEmbeddedUI && (*((_DWORD *)g_pEmbeddedUI + 272) & 0x2000) != 0 )
      CMsiEmbeddedUIManager::Message(v17, 218103808, &off_18030FDB0);
  }
  if ( byte_180310E64 )
    CBasicUI::Terminate((CBasicUI *)v17);
  v18 = (HMODULE)*((_QWORD *)this + 15);
  if ( v18 )
  {
    FreeLibrary(v18);
    *((_QWORD *)this + 15) = 0;
  }
  v19 = (void *)*((_QWORD *)this + 9);
  *((_DWORD *)this + 47) = 0x2000;
  CloseHandle(v19);
  v20 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 9) = 0;
  CloseHandle(v20);
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 13) = 0;
  v21 = 0;
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 29) = -1;
  *((_BYTE *)this + 204) = 0;
  *((_BYTE *)this + 313) = 0;
  *((_WORD *)this + 112) = 0;
  *((_BYTE *)this + 226) = 0;
  do
  {
    v22 = (&CRestartManagerWrapper::m_gpoRestartManagerWrapper)[v21];
    if ( v22 && ((_BYTE)v22[98] & 2) == 0 )
    {
      if ( CRestartManagerWrapper::IsEnabled((CRestartManagerWrapper *)(&CRestartManagerWrapper::m_gpoRestartManagerWrapper)[v21])
        && (*((unsigned int (**)(void))*v22 + 4))()
        && !*((_BYTE *)v22 + 788) )
      {
        v23 = (*((__int64 (__fastcall **)(struct CRestartManagerWrapper * near *))*v22 + 3))(v22);
        if ( v23 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"RESTART MANAGER: Failed while restarting applications. Error: %d",
              (const unsigned __int16 *)v23,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
        }
        else if ( g_dmDiagnosticMode )
        {
          DebugString(
            10,
            0,
            0,
            L"RESTART MANAGER: Previously shut down applications have been restarted.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
      v24 = CRestartManagerWrapper::EndSession((CRestartManagerWrapper *)v22);
      if ( v24 != 1626 )
      {
        if ( v24 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"RESTART MANAGER: Failed while closing session. Error: %d",
              (const unsigned __int16 *)v24,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
        }
        else if ( g_dmDiagnosticMode )
        {
          DebugString(
            10,
            0,
            0,
            L"RESTART MANAGER: Session closed.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
      CRestartManagerWrapper::DestroyInstance((unsigned int)v21);
    }
    ++v21;
  }
  while ( v21 <= 1 );
  FreePolicyTable();
  v26 = qword_180313730;
  if ( qword_180313730 && !qword_1803136D8 && !a4 && (!v10 || SLODWORD(v10[2].lpVtbl) >= 0) )
  {
    if ( *((_DWORD *)qword_180313730 + 4) != 5 && !*((_BYTE *)qword_180313730 + 22) )
    {
      CMsiSystemChange::EndSystemChange(qword_180313730, 0, *((_QWORD *)qword_180313730 + 3));
      v26 = qword_180313730;
    }
    if ( v26 )
      CMsiSystemChange::`scalar deleting destructor'(v26, v25);
    qword_180313730 = 0;
  }
  v27 = (CMsiSQMSession *)*((_QWORD *)this + 30);
  if ( v27 )
  {
    CMsiSQMSession::`scalar deleting destructor'(v27, (unsigned __int8)v25);
    *((_QWORD *)this + 30) = 0;
  }
  if ( a4 )
  {
    v28 = (CMsiEnvironmentBlock *)*((_QWORD *)this + 41);
    if ( v28 )
    {
      CMsiEnvironmentBlock::`scalar deleting destructor'(v28, v25);
      *((_QWORD *)this + 41) = 0;
    }
    v29 = (CMsiEnvironmentBlock *)*((_QWORD *)this + 42);
    if ( v29 )
    {
      CMsiEnvironmentBlock::`scalar deleting destructor'(v29, v25);
      *((_QWORD *)this + 42) = 0;
    }
  }
  if ( a2 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(10, 0, 0, L"fFatalExit=true", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
    *((_BYTE *)this + 248) = 1;
    MsiCloseAllSysHandles();
    FreeMsiMalloc(1);
    ((void (__fastcall *)(_QWORD))KERNEL32::SetThreadExecutionState)(0);
    DestroyMsiVolumeList(1);
    if ( g_piSharedServices )
    {
      g_piSharedServices = 0;
      Services = LoadServices();
      ConfigurationManager = CreateConfigurationManager();
      v41 = ConfigurationManager;
      if ( Services )
      {
        if ( ConfigurationManager )
          (*(void (__fastcall **)(struct IMsiConfigurationManager *, struct IMsiServices *))(*(_QWORD *)ConfigurationManager
                                                                                           + 336LL))(
            ConfigurationManager,
            Services);
        else
          FreeServices();
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v41);
    }
  }
  else if ( *((_QWORD *)this + 27) )
  {
    FreeServices();
    *((_QWORD *)this + 27) = 0;
  }
  if ( *((_QWORD *)this + 4) != -1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    *((_QWORD *)this + 4) = -1;
  }
  if ( *((_QWORD *)this + 22) )
  {
    EnterCriticalSection(&g_csWriteLog);
    if ( *((_DWORD *)this + 67) )
    {
      v32 = g_scServerContext;
      if ( g_scServerContext != 3 )
      {
        wcscpy(String, L"=== MSI ");
        memset_0(v43, 0, 0x8Eu);
        v33 = L"(c)";
        if ( v32 )
          v33 = L"(s)";
        StringCchCatW(String, 0x50u, v33);
        StringCchCatW(String, 0x50u, L" Failed to grab mutex for logging. Some log might be lost. === ");
        *((_DWORD *)this + 66) = 3;
        WriteLogToDisk(String);
      }
    }
    if ( FDiagnosticModeSet(8) && !g_scServerContext )
    {
      String[0] = 0;
      memset_0(&String[1], 0, 0xC6u);
      v34 = ((__int64 (__fastcall *)(void ***))g_MsiStringTime[10])(&g_MsiStringTime);
      v35 = ((__int64 (__fastcall *)(void ***))g_MsiStringDate[10])(&g_MsiStringDate);
      if ( (int)StringCchPrintfW(String, 0x64u, L"=== Verbose logging stopped: %s  %s ===\r\n", v35, v34) >= 0 )
        WriteLog(String);
    }
    v36 = (CLogFile *)*((_QWORD *)this + 37);
    if ( v36 )
    {
      if ( a3 || a2 || (g_dwLogMode & 0x4000) == 0 )
        CLogFile::Flush(v36, 1);
      CLogFile::Destroy(*((CLogFile **)this + 37));
      GlobalFree(*((HGLOBAL *)this + 37));
      *((_QWORD *)this + 37) = 0;
    }
    CloseHandle(*((HANDLE *)this + 22));
    CloseHandle(*((HANDLE *)this + 32));
    v37 = (g_dwLogMode & 0x4000) == 0;
    *((_QWORD *)this + 22) = 0;
    *((_QWORD *)this + 32) = 0;
    if ( !v37 && !a3 && !a2 )
      DeleteFileW(g_rgchLogFile);
    if ( *((_BYTE *)this + 184) )
    {
      g_dwLogMode = 0;
      *g_rgchLogFile = 0;
    }
    LeaveCriticalSection(&g_csWriteLog);
  }
  *((_BYTE *)this + 184) = 0;
  *((_BYTE *)this + 148) = 0;
  CMessageContextState::SetState((MsiUIMessageContext *)((char *)this + 160), 0);
  MsiUIMessageContext::SetUserToken(this, 1);
  if ( *((_BYTE *)this + 312) && g_scServerContext == 2 )
  {
    v38 = CreateConfigurationManager();
    v41 = v38;
    if ( v38 )
      (*(void (__fastcall **)(struct IMsiConfigurationManager *))(*(_QWORD *)v38 + 392LL))(v38);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v41);
  }
  if ( *((_BYTE *)this + 228) == 1 )
  {
    OLE32::CoUninitialize();
    *((_BYTE *)this + 228) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18004ccbc  mov     [rsp-8+arg_10], rbx
0x18004ccc1  push    rbp
0x18004ccc2  push    rsi
0x18004ccc3  push    rdi
0x18004ccc4  push    r12
0x18004ccc6  push    r13
0x18004ccc8  push    r14
0x18004ccca  push    r15
0x18004cccc  lea     rbp, [rsp-50h]
0x18004ccd1  sub     rsp, 150h
0x18004ccd8  mov     rax, cs:__security_cookie
0x18004ccdf  xor     rax, rsp
0x18004cce2  mov     [rbp+80h+var_40], rax
0x18004cce6  mov     rdi, rcx
0x18004cce9  mov     [rsp+180h+var_120], r8b
0x18004ccee  mov     rcx, [rcx+0F0h]; this
0x18004ccf5  xor     ebx, ebx
0x18004ccf7  mov     r15b, r9b
0x18004ccfa  mov     r12b, dl
0x18004ccfd  test    rcx, rcx
0x18004cd00  jz      short loc_18004CD17
0x18004cd02  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18004cd09  jnz     short loc_18004CD17
0x18004cd0b  call    ??_GCMsiSQMSession@@QEAAPEAXI@Z; CMsiSQMSession::`scalar deleting destructor'(uint)
0x18004cd10  mov     [rdi+0F0h], rbx
0x18004cd17  mov     rcx, [rdi+60h]; hThread
0x18004cd1b  test    rcx, rcx
0x18004cd1e  jz      short loc_18004CD5C
0x18004cd20  cmp     [rdi+95h], bl
0x18004cd26  jz      short loc_18004CD3A
0x18004cd28  xor     r8d, r8d
0x18004cd2b  mov     edx, 0F000135h
0x18004cd30  mov     rcx, rdi
0x18004cd33  call    ?Invoke@MsiUIMessageContext@@QEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::Invoke(imtEnum,IMsiRecord *)
0x18004cd38  jmp     short loc_18004CD48
0x18004cd3a  xor     edx, edx; dwExitCode
0x18004cd3c  call    cs:__imp_TerminateThread
0x18004cd43  nop     dword ptr [rax+rax+00h]
0x18004cd48  mov     rcx, [rdi+60h]; hObject
0x18004cd4c  call    cs:__imp_CloseHandle
0x18004cd53  nop     dword ptr [rax+rax+00h]
0x18004cd58  mov     [rdi+60h], rbx
0x18004cd5c  mov     rcx, [rdi+118h]
0x18004cd63  mov     [rdi+95h], bl
0x18004cd69  mov     [rdi+0E3h], bl
0x18004cd6f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004cd73  jz      short loc_18004CD91
0x18004cd75  test    rcx, rcx
0x18004cd78  jz      short loc_18004CD86
0x18004cd7a  mov     rax, cs:?SfcClose@SFC@@3P6AXPEAX@ZEA; void (*SFC::SfcClose)(void *)
0x18004cd81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd86  mov     qword ptr [rdi+118h], 0FFFFFFFFFFFFFFFFh
0x18004cd91  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal>::GetImpl(void)'::`2'::impl
0x18004cd98  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal>::__private_IsEnabled(void)
0x18004cd9d  test    al, al
0x18004cd9f  jnz     short loc_18004CDC2
0x18004cda1  lea     r9, byte_180310CEC; bool *
0x18004cda8  lea     r8, dword_180314308; int *
0x18004cdaf  lea     rdx, qword_180314310; HINSTANCE *
0x18004cdb6  lea     rcx, ?rgUnbind@SFC@@3PAUUnbindStruct@@A; struct UnbindStruct *
0x18004cdbd  call    ?Unbind@@YAXPEAUUnbindStruct@@AEAPEAUHINSTANCE__@@AEAHAEA_N@Z; Unbind(UnbindStruct *,HINSTANCE__ * &,int &,bool &)
0x18004cdc2  mov     r14, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004cdc9  cmp     [rdi+0E8h], rbx
0x18004cdd0  jnz     short loc_18004CDE4
0x18004cdd2  test    r14, r14
0x18004cdd5  jz      short loc_18004CDDC
0x18004cdd7  test    r15b, r15b
0x18004cdda  jz      short loc_18004CDE4
0x18004cddc  mov     rcx, rdi; this
0x18004cddf  call    ?ClearSaferHandle@MsiUIMessageContext@@QEAAXXZ; MsiUIMessageContext::ClearSaferHandle(void)
0x18004cde4  lea     rcx, ?g_rgchBannerText@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchBannerText
0x18004cdeb  mov     [rdi+13Ch], ebx
0x18004cdf1  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18004cdf6  lea     rcx, ?g_rgchScriptInProgress@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchScriptInProgress
0x18004cdfd  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18004ce02  lea     rcx, ?g_rgchTimeRemaining@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchTimeRemaining
0x18004ce09  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18004ce0e  lea     rcx, ?g_rgchFatalOutOfMemory@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchFatalOutOfMemory
0x18004ce15  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18004ce1a  lea     rcx, ?g_rgchFatalTimedOut@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchFatalTimedOut
0x18004ce21  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18004ce26  lea     rcx, ?g_rgchFatalException@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchFatalException
0x18004ce2d  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18004ce32  mov     rcx, [rdi+0D0h]; hWnd
0x18004ce39  test    rcx, rcx
0x18004ce3c  jz      short loc_18004CE51
0x18004ce3e  call    cs:__imp_DestroyWindow
0x18004ce45  nop     dword ptr [rax+rax+00h]
0x18004ce4a  mov     [rdi+0D0h], rbx
0x18004ce51  call    IsolationAwareUnregisterClassW
0x18004ce56  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18004ce5d  jnz     short loc_18004CE92
0x18004ce5f  cmp     cs:?g_fInitialized@CProductContextCache@@2_NA, bl; bool CProductContextCache::g_fInitialized
0x18004ce65  jz      short loc_18004CE92
0x18004ce67  lea     rcx, ?g_csCacheCriticalSection@CProductContextCache@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004ce6e  call    cs:__imp_DeleteCriticalSection
0x18004ce75  nop     dword ptr [rax+rax+00h]
0x18004ce7a  lea     rcx, ?g_rgProductContext@CProductContextCache@@2V?$CAPITempBuffer@UsProductContext@@$0BE@@@A; CAPITempBuffer<sProductContext,20> CProductContextCache::g_rgProductContext
0x18004ce81  call    ?Destroy@?$CAPITempBuffer@UsProductContext@@$0BE@@@QEAAXXZ; CAPITempBuffer<sProductContext,20>::Destroy(void)
0x18004ce86  mov     cs:?g_cProductCacheCount@CProductContextCache@@2HA, ebx; int CProductContextCache::g_cProductCacheCount
0x18004ce8c  mov     cs:?g_fInitialized@CProductContextCache@@2_NA, bl; bool CProductContextCache::g_fInitialized
0x18004ce92  test    r12b, r12b
0x18004ce95  jnz     short loc_18004CECA
0x18004ce97  mov     rcx, [rdi+38h]
0x18004ce9b  test    rcx, rcx
0x18004ce9e  jz      short loc_18004CEB0
0x18004cea0  mov     rax, [rcx]
0x18004cea3  mov     rax, [rax+10h]
0x18004cea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ceac  mov     [rdi+38h], rbx
0x18004ceb0  mov     rcx, [rdi+88h]
0x18004ceb7  test    rcx, rcx
0x18004ceba  jz      short loc_18004CEE3
0x18004cebc  mov     rax, [rcx]
0x18004cebf  mov     rax, [rax+10h]
0x18004cec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cec8  jmp     short loc_18004CEDC
0x18004ceca  mov     [rdi+38h], rbx
0x18004cece  mov     cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA, rbx; IMsiRegKey * g_piSharedDllsRegKey
0x18004ced5  mov     cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA, rbx; IMsiRegKey * g_piSharedDllsRegKey32
0x18004cedc  mov     [rdi+88h], rbx
0x18004cee3  mov     rcx, [rdi+110h]
0x18004ceea  test    rcx, rcx
0x18004ceed  jz      short loc_18004CF18
0x18004ceef  mov     rax, [rcx]
0x18004cef2  mov     dl, r12b
0x18004cef5  mov     rax, [rax+38h]
0x18004cef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cefe  mov     rcx, [rdi+110h]
0x18004cf05  mov     rax, [rcx]
0x18004cf08  mov     rax, [rax+10h]
0x18004cf0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf11  mov     [rdi+110h], rbx
0x18004cf18  mov     rcx, [rdi+0A8h]
0x18004cf1f  test    rcx, rcx
0x18004cf22  jz      short loc_18004CF37
0x18004cf24  mov     rax, [rcx]
0x18004cf27  mov     rax, [rax+10h]
0x18004cf2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf30  mov     [rdi+0A8h], rbx
0x18004cf37  mov     rcx, [rdi+50h]; hObject
0x18004cf3b  test    rcx, rcx
0x18004cf3e  jz      short loc_18004CF50
0x18004cf40  call    cs:__imp_CloseHandle
0x18004cf47  nop     dword ptr [rax+rax+00h]
0x18004cf4c  mov     [rdi+50h], rbx
0x18004cf50  mov     [rdi+0C0h], ebx
0x18004cf56  mov     esi, 2000h
0x18004cf5b  test    r15b, r15b
0x18004cf5e  jnz     short loc_18004CFC5
0x18004cf60  test    cs:dword_180313928, esi
0x18004cf66  jz      short loc_18004CF84
0x18004cf68  lea     r8, off_18030FDB0
0x18004cf6f  mov     edx, 0D000000h
0x18004cf74  lea     rcx, ?g_messageRec@@3VCMsiAPIMessageRec@@A; CMsiAPIMessageRec g_messageRec
0x18004cf7b  call    ?Message@CMsiAPIMessageRec@@QEBA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiAPIMessageRec::Message(imtEnum,IMsiRecord &)
0x18004cf80  test    eax, eax
0x18004cf82  jnz     short loc_18004CFA0
0x18004cf84  test    cs:dword_180313768, esi
0x18004cf8a  jz      short loc_18004CFA0
0x18004cf8c  xor     r8d, r8d
0x18004cf8f  lea     rcx, ?g_message@@3VCMsiAPIMessage@@A; CMsiAPIMessage g_message
0x18004cf96  mov     edx, 0D000000h
0x18004cf9b  call    ?Message@CMsiAPIMessage@@QEBA?AW4imsEnum@@W4imtEnum@@PEBG@Z; CMsiAPIMessage::Message(imtEnum,ushort const *)
0x18004cfa0  mov     rax, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x18004cfa7  test    rax, rax
0x18004cfaa  jz      short loc_18004CFC5
0x18004cfac  test    [rax+440h], esi
0x18004cfb2  jz      short loc_18004CFC5
0x18004cfb4  lea     r8, off_18030FDB0
0x18004cfbb  mov     edx, 0D000000h
0x18004cfc0  call    ?Message@CMsiEmbeddedUIManager@@QEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiEmbeddedUIManager::Message(imtEnum,IMsiRecord &)
0x18004cfc5  cmp     cs:byte_180310E64, bl
0x18004cfcb  jz      short loc_18004CFD2
0x18004cfcd  call    ?Terminate@CBasicUI@@QEAA_NXZ; CBasicUI::Terminate(void)
0x18004cfd2  mov     rcx, [rdi+78h]; hLibModule
0x18004cfd6  test    rcx, rcx
0x18004cfd9  jz      short loc_18004CFEB
0x18004cfdb  call    cs:__imp_FreeLibrary
0x18004cfe2  nop     dword ptr [rax+rax+00h]
0x18004cfe7  mov     [rdi+78h], rbx
0x18004cfeb  mov     rcx, [rdi+48h]; hObject
0x18004cfef  mov     [rdi+0BCh], esi
0x18004cff5  call    cs:__imp_CloseHandle
0x18004cffc  nop     dword ptr [rax+rax+00h]
0x18004d001  mov     rcx, [rdi+58h]; hObject
0x18004d005  mov     [rdi+48h], rbx
0x18004d009  call    cs:__imp_CloseHandle
0x18004d010  nop     dword ptr [rax+rax+00h]
0x18004d015  mov     [rdi+58h], rbx
0x18004d019  lea     r13, aNull; "(NULL)"
0x18004d020  mov     [rdi+68h], rbx
0x18004d024  mov     esi, ebx
0x18004d026  mov     [rdi+70h], ebx
0x18004d029  mov     dword ptr [rdi+74h], 0FFFFFFFFh
0x18004d030  mov     [rdi+0CCh], bl
0x18004d036  mov     [rdi+139h], bl
0x18004d03c  mov     [rdi+0E0h], bx
0x18004d043  mov     [rdi+0E2h], bl
0x18004d049  mov     eax, esi
0x18004d04b  lea     rbx, ?m_gpoRestartManagerWrapper@CRestartManagerWrapper@@1PAPEAV1@A; CRestartManagerWrapper * near * CRestartManagerWrapper::m_gpoRestartManagerWrapper
0x18004d052  mov     rbx, [rbx+rax*8]
0x18004d056  test    rbx, rbx
0x18004d059  jz      loc_18004D1CC
0x18004d05f  test    byte ptr [rbx+310h], 2
0x18004d066  jnz     loc_18004D1CC
0x18004d06c  mov     rcx, rbx; this
0x18004d06f  call    ?IsEnabled@CRestartManagerWrapper@@QEBA_NXZ; CRestartManagerWrapper::IsEnabled(void)
0x18004d074  test    al, al
0x18004d076  jz      loc_18004D12F
0x18004d07c  mov     rax, [rbx]
0x18004d07f  mov     rax, [rax+20h]
0x18004d083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d088  test    eax, eax
0x18004d08a  jz      loc_18004D12F
0x18004d090  cmp     byte ptr [rbx+314h], 0
0x18004d097  jnz     loc_18004D12F
0x18004d09d  mov     rax, [rbx]
0x18004d0a0  mov     rcx, rbx
0x18004d0a3  mov     rax, [rax+18h]
0x18004d0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0ac  xor     ecx, ecx
0x18004d0ae  test    eax, eax
0x18004d0b0  jz      short loc_18004D0EC
0x18004d0b2  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x18004d0b8  jz      short loc_18004D12F
0x18004d0ba  mov     [rsp+180h+var_128], rcx
0x18004d0bf  lea     r9, aRestartManager_10; "RESTART MANAGER: Failed while restartin"...
0x18004d0c6  mov     [rsp+180h+var_130], ecx
0x18004d0ca  mov     [rsp+180h+var_138], r13
0x18004d0cf  mov     [rsp+180h+var_140], r13
0x18004d0d4  mov     [rsp+180h+var_148], r13
0x18004d0d9  mov     [rsp+180h+var_150], r13
0x18004d0de  mov     eax, eax
0x18004d0e0  mov     [rsp+180h+var_158], r13
0x18004d0e5  mov     [rsp+180h+var_160], rax
0x18004d0ea  jmp     short loc_18004D122
0x18004d0ec  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x18004d0f2  jz      short loc_18004D12F
0x18004d0f4  mov     [rsp+180h+var_128], rcx; void *
0x18004d0f9  lea     r9, aRestartManager_17; "RESTART MANAGER: Previously shut down a"...
0x18004d100  mov     [rsp+180h+var_130], ecx; unsigned int
0x18004d104  mov     [rsp+180h+var_138], r13; unsigned __int16 *
0x18004d109  mov     [rsp+180h+var_140], r13; unsigned __int16 *
0x18004d10e  mov     [rsp+180h+var_148], r13; unsigned __int16 *
0x18004d113  mov     [rsp+180h+var_150], r13; unsigned __int16 *
0x18004d118  mov     [rsp+180h+var_158], r13; unsigned __int16 *
0x18004d11d  mov     [rsp+180h+var_160], r13; unsigned __int16 *
0x18004d122  xor     edx, edx; unsigned __int16
0x18004d124  xor     r8d, r8d; int
0x18004d127  lea     ecx, [rdx+0Ah]; int
0x18004d12a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004d12f  mov     rcx, rbx; this
0x18004d132  call    ?EndSession@CRestartManagerWrapper@@QEBAIXZ; CRestartManagerWrapper::EndSession(void)
0x18004d137  cmp     eax, 65Ah
0x18004d13c  jz      loc_18004D1C5
0x18004d142  xor     ecx, ecx
0x18004d144  test    eax, eax
0x18004d146  jz      short loc_18004D182
0x18004d148  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x18004d14e  jz      short loc_18004D1C5
0x18004d150  mov     [rsp+180h+var_128], rcx
0x18004d155  lea     r9, aRestartManager_13; "RESTART MANAGER: Failed while closing s"...
0x18004d15c  mov     [rsp+180h+var_130], ecx
0x18004d160  mov     [rsp+180h+var_138], r13
0x18004d165  mov     [rsp+180h+var_140], r13
0x18004d16a  mov     [rsp+180h+var_148], r13
0x18004d16f  mov     [rsp+180h+var_150], r13
0x18004d174  mov     eax, eax
0x18004d176  mov     [rsp+180h+var_158], r13
0x18004d17b  mov     [rsp+180h+var_160], rax
0x18004d180  jmp     short loc_18004D1B8
0x18004d182  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x18004d188  jz      short loc_18004D1C5
0x18004d18a  mov     [rsp+180h+var_128], rcx; void *
0x18004d18f  lea     r9, aRestartManager_21; "RESTART MANAGER: Session closed."
0x18004d196  mov     [rsp+180h+var_130], ecx; unsigned int
0x18004d19a  mov     [rsp+180h+var_138], r13; unsigned __int16 *
0x18004d19f  mov     [rsp+180h+var_140], r13; unsigned __int16 *
0x18004d1a4  mov     [rsp+180h+var_148], r13; unsigned __int16 *
0x18004d1a9  mov     [rsp+180h+var_150], r13; unsigned __int16 *
0x18004d1ae  mov     [rsp+180h+var_158], r13; unsigned __int16 *
0x18004d1b3  mov     [rsp+180h+var_160], r13; unsigned __int16 *
0x18004d1b8  xor     edx, edx; unsigned __int16
0x18004d1ba  xor     r8d, r8d; int
0x18004d1bd  lea     ecx, [rdx+0Ah]; int
0x18004d1c0  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004d1c5  mov     ecx, esi
0x18004d1c7  call    ?DestroyInstance@CRestartManagerWrapper@@SAXW4ieRMInstallLevel@@@Z; CRestartManagerWrapper::DestroyInstance(ieRMInstallLevel)
0x18004d1cc  inc     esi
0x18004d1ce  cmp     esi, 1
0x18004d1d1  jle     loc_18004D049
0x18004d1d7  call    ?FreePolicyTable@@YAXXZ; FreePolicyTable(void)
0x18004d1dc  mov     rcx, cs:qword_180313730; this
0x18004d1e3  xor     esi, esi
0x18004d1e5  mov     r13b, [rsp+180h+var_120]
0x18004d1ea  test    rcx, rcx
0x18004d1ed  jz      short loc_18004D237
0x18004d1ef  cmp     cs:qword_1803136D8, rsi
0x18004d1f6  jnz     short loc_18004D237
  ... truncated ...
```

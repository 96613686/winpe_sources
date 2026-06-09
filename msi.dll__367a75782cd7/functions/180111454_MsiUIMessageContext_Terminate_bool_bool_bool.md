# MsiUIMessageContext::Terminate(bool,bool,bool)

- ea: `0x180111454`
- end: `0x180111d79`
- name: `?Terminate@MsiUIMessageContext@@QEAA_N_N00@Z`
- size: `2341`
- prototype: `bool __fastcall(MsiUIMessageContext *__hidden this, bool, bool, bool)`
- caller_count: `11`
- callee_count: `40`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800997b8`
- `0x18009b280`
- `0x1800b4680`
- `0x18012be80`
- `0x18015701c`
- `0x18016941c`
- `0x180193a84`
- `0x1801948c0`
- `0x180194a60`
- `0x1801a17b8`
- `0x1801c83dc`

## callees

- `0x18001de18`
- `0x18001e9f8`
- `0x180022120`
- `0x1800255e0`
- `0x180025a18`
- `0x18003ca18`
- `0x18004ac60`
- `0x18004ceb0`
- `0x180066074`
- `0x18009d810`
- `0x18009dadc`
- `0x18009de10`
- `0x18009e200`
- `0x18009e43c`
- `0x1800af0c8`
- `0x1800af818`
- `0x1800da080`
- `0x180111454`
- `0x180112320`
- `0x180112f24`
- `0x18011ada4`
- `0x18011b374`
- `0x18012a5d8`
- `0x180143d60`
- `0x180153278`
- `0x1801532b4`
- `0x180155920`
- `0x180156a38`
- `0x1801b7c2c`
- `0x1801b7c9c`
- `0x1801b822c`
- `0x1801bf344`
- `0x1801c01c8`
- `0x1801c01f0`
- `0x1801c0218`
- `0x1801c0610`
- `0x1801c2abc`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1801115f4`
- `KERNEL32!DeleteCriticalSection` at `0x180111ade`
- `KERNEL32!DeleteCriticalSection` at `0x1801115f4`
- `KERNEL32!DeleteCriticalSection` at `0x180111ade`
- `KERNEL32!CloseHandle` at `0x1801114de`
- `KERNEL32!CloseHandle` at `0x1801116c0`
- `KERNEL32!CloseHandle` at `0x180111769`
- `KERNEL32!CloseHandle` at `0x180111777`
- `KERNEL32!CloseHandle` at `0x180111c68`
- `KERNEL32!CloseHandle` at `0x180111c75`
- `KERNEL32!CloseHandle` at `0x1801114de`
- `KERNEL32!CloseHandle` at `0x1801116c0`
- `KERNEL32!CloseHandle` at `0x180111769`
- `KERNEL32!CloseHandle` at `0x180111777`
- `KERNEL32!CloseHandle` at `0x180111c68`
- `KERNEL32!CloseHandle` at `0x180111c75`
- `KERNEL32!LeaveCriticalSection` at `0x180111cc8`
- `KERNEL32!LeaveCriticalSection` at `0x180111cc8`
- `KERNEL32!DeleteFileW` at `0x180111ca2`
- `KERNEL32!DeleteFileW` at `0x180111ca2`
- `KERNEL32!EnterCriticalSection` at `0x180111b00`
- `KERNEL32!EnterCriticalSection` at `0x180111b00`
- `KERNEL32!GlobalFree` at `0x180111c54`
- `KERNEL32!GlobalFree` at `0x180111c54`
- `KERNEL32!FreeLibrary` at `0x180111755`
- `KERNEL32!FreeLibrary` at `0x180111755`
- `KERNEL32!TerminateThread` at `0x1801114d4`
- `KERNEL32!TerminateThread` at `0x1801114d4`
- `USER32!DestroyWindow` at `0x1801115ca`
- `USER32!DestroyWindow` at `0x1801115ca`

## string_xrefs

- `0x180111b19`: `=== MSI `

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
    Unbind((struct UnbindStruct *)&SFC::rgUnbind, &qword_18030A318, &dword_18030A310, &byte_180306D2C);
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
    if ( ((dword_180309978 & 0x2000) == 0
       || !(unsigned int)CMsiAPIMessageRec::Message(g_messageRec, 218103808, &off_180305DB0))
      && (dword_1803097B8 & 0x2000) != 0 )
    {
      CMsiAPIMessage::Message(g_message, 218103808, 0);
    }
    if ( g_pEmbeddedUI && (*((_DWORD *)g_pEmbeddedUI + 272) & 0x2000) != 0 )
      CMsiEmbeddedUIManager::Message(v17, 218103808, &off_180305DB0);
  }
  if ( byte_180306EA4 )
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
  v26 = qword_180309780;
  if ( qword_180309780 && !qword_180309728 && !a4 && (!v10 || SLODWORD(v10[2].lpVtbl) >= 0) )
  {
    if ( *((_DWORD *)qword_180309780 + 4) != 5 && !*((_BYTE *)qword_180309780 + 22) )
    {
      CMsiSystemChange::EndSystemChange(qword_180309780, 0, *((_QWORD *)qword_180309780 + 3));
      v26 = qword_180309780;
    }
    if ( v26 )
      CMsiSystemChange::`scalar deleting destructor'(v26, v25);
    qword_180309780 = 0;
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
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v41);
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
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v41);
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
0x180111454  mov     [rsp-8+arg_10], rbx
0x180111459  push    rbp
0x18011145a  push    rsi
0x18011145b  push    rdi
0x18011145c  push    r12
0x18011145e  push    r13
0x180111460  push    r14
0x180111462  push    r15
0x180111464  lea     rbp, [rsp-50h]
0x180111469  sub     rsp, 150h
0x180111470  mov     rax, cs:__security_cookie
0x180111477  xor     rax, rsp
0x18011147a  mov     [rbp+80h+var_40], rax
0x18011147e  mov     rdi, rcx
0x180111481  mov     [rsp+180h+var_120], r8b
0x180111486  mov     rcx, [rcx+0F0h]; this
0x18011148d  xor     ebx, ebx
0x18011148f  mov     r15b, r9b
0x180111492  mov     r12b, dl
0x180111495  test    rcx, rcx
0x180111498  jz      short loc_1801114AF
0x18011149a  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1801114a1  jnz     short loc_1801114AF
0x1801114a3  call    ??_GCMsiSQMSession@@QEAAPEAXI@Z; CMsiSQMSession::`scalar deleting destructor'(uint)
0x1801114a8  mov     [rdi+0F0h], rbx
0x1801114af  mov     rcx, [rdi+60h]; hThread
0x1801114b3  test    rcx, rcx
0x1801114b6  jz      short loc_1801114E8
0x1801114b8  cmp     [rdi+95h], bl
0x1801114be  jz      short loc_1801114D2
0x1801114c0  xor     r8d, r8d
0x1801114c3  mov     edx, 0F000135h
0x1801114c8  mov     rcx, rdi
0x1801114cb  call    ?Invoke@MsiUIMessageContext@@QEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::Invoke(imtEnum,IMsiRecord *)
0x1801114d0  jmp     short loc_1801114DA
0x1801114d2  xor     edx, edx; dwExitCode
0x1801114d4  call    cs:__imp_TerminateThread
0x1801114da  mov     rcx, [rdi+60h]; hObject
0x1801114de  call    cs:__imp_CloseHandle
0x1801114e4  mov     [rdi+60h], rbx
0x1801114e8  mov     rcx, [rdi+118h]
0x1801114ef  mov     [rdi+95h], bl
0x1801114f5  mov     [rdi+0E3h], bl
0x1801114fb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801114ff  jz      short loc_18011151D
0x180111501  test    rcx, rcx
0x180111504  jz      short loc_180111512
0x180111506  mov     rax, cs:?SfcClose@SFC@@3P6AXPEAX@ZEA; void (*SFC::SfcClose)(void *)
0x18011150d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111512  mov     qword ptr [rdi+118h], 0FFFFFFFFFFFFFFFFh
0x18011151d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal>::GetImpl(void)'::`2'::impl
0x180111524  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SFC_Unbind_Removal>::__private_IsEnabled(void)
0x180111529  test    al, al
0x18011152b  jnz     short loc_18011154E
0x18011152d  lea     r9, byte_180306D2C; bool *
0x180111534  lea     r8, dword_18030A310; int *
0x18011153b  lea     rdx, qword_18030A318; HINSTANCE *
0x180111542  lea     rcx, ?rgUnbind@SFC@@3PAUUnbindStruct@@A; struct UnbindStruct *
0x180111549  call    ?Unbind@@YAXPEAUUnbindStruct@@AEAPEAUHINSTANCE__@@AEAHAEA_N@Z; Unbind(UnbindStruct *,HINSTANCE__ * &,int &,bool &)
0x18011154e  mov     r14, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x180111555  cmp     [rdi+0E8h], rbx
0x18011155c  jnz     short loc_180111570
0x18011155e  test    r14, r14
0x180111561  jz      short loc_180111568
0x180111563  test    r15b, r15b
0x180111566  jz      short loc_180111570
0x180111568  mov     rcx, rdi; this
0x18011156b  call    ?ClearSaferHandle@MsiUIMessageContext@@QEAAXXZ; MsiUIMessageContext::ClearSaferHandle(void)
0x180111570  lea     rcx, ?g_rgchBannerText@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchBannerText
0x180111577  mov     [rdi+13Ch], ebx
0x18011157d  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x180111582  lea     rcx, ?g_rgchScriptInProgress@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchScriptInProgress
0x180111589  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18011158e  lea     rcx, ?g_rgchTimeRemaining@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchTimeRemaining
0x180111595  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18011159a  lea     rcx, ?g_rgchFatalOutOfMemory@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchFatalOutOfMemory
0x1801115a1  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801115a6  lea     rcx, ?g_rgchFatalTimedOut@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchFatalTimedOut
0x1801115ad  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801115b2  lea     rcx, ?g_rgchFatalException@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchFatalException
0x1801115b9  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x1801115be  mov     rcx, [rdi+0D0h]; hWnd
0x1801115c5  test    rcx, rcx
0x1801115c8  jz      short loc_1801115D7
0x1801115ca  call    cs:__imp_DestroyWindow
0x1801115d0  mov     [rdi+0D0h], rbx
0x1801115d7  call    IsolationAwareUnregisterClassW
0x1801115dc  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1801115e3  jnz     short loc_180111612
0x1801115e5  cmp     cs:?g_fInitialized@CProductContextCache@@2_NA, bl; bool CProductContextCache::g_fInitialized
0x1801115eb  jz      short loc_180111612
0x1801115ed  lea     rcx, ?g_csCacheCriticalSection@CProductContextCache@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801115f4  call    cs:__imp_DeleteCriticalSection
0x1801115fa  lea     rcx, ?g_rgProductContext@CProductContextCache@@2V?$CAPITempBuffer@UsProductContext@@$0BE@@@A; CAPITempBuffer<sProductContext,20> CProductContextCache::g_rgProductContext
0x180111601  call    ?Destroy@?$CAPITempBuffer@UsProductContext@@$0BE@@@QEAAXXZ; CAPITempBuffer<sProductContext,20>::Destroy(void)
0x180111606  mov     cs:?g_cProductCacheCount@CProductContextCache@@2HA, ebx; int CProductContextCache::g_cProductCacheCount
0x18011160c  mov     cs:?g_fInitialized@CProductContextCache@@2_NA, bl; bool CProductContextCache::g_fInitialized
0x180111612  test    r12b, r12b
0x180111615  jnz     short loc_18011164A
0x180111617  mov     rcx, [rdi+38h]
0x18011161b  test    rcx, rcx
0x18011161e  jz      short loc_180111630
0x180111620  mov     rax, [rcx]
0x180111623  mov     rax, [rax+10h]
0x180111627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011162c  mov     [rdi+38h], rbx
0x180111630  mov     rcx, [rdi+88h]
0x180111637  test    rcx, rcx
0x18011163a  jz      short loc_180111663
0x18011163c  mov     rax, [rcx]
0x18011163f  mov     rax, [rax+10h]
0x180111643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111648  jmp     short loc_18011165C
0x18011164a  mov     [rdi+38h], rbx
0x18011164e  mov     cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA, rbx; IMsiRegKey * g_piSharedDllsRegKey
0x180111655  mov     cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA, rbx; IMsiRegKey * g_piSharedDllsRegKey32
0x18011165c  mov     [rdi+88h], rbx
0x180111663  mov     rcx, [rdi+110h]
0x18011166a  test    rcx, rcx
0x18011166d  jz      short loc_180111698
0x18011166f  mov     rax, [rcx]
0x180111672  mov     dl, r12b
0x180111675  mov     rax, [rax+38h]
0x180111679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011167e  mov     rcx, [rdi+110h]
0x180111685  mov     rax, [rcx]
0x180111688  mov     rax, [rax+10h]
0x18011168c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111691  mov     [rdi+110h], rbx
0x180111698  mov     rcx, [rdi+0A8h]
0x18011169f  test    rcx, rcx
0x1801116a2  jz      short loc_1801116B7
0x1801116a4  mov     rax, [rcx]
0x1801116a7  mov     rax, [rax+10h]
0x1801116ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801116b0  mov     [rdi+0A8h], rbx
0x1801116b7  mov     rcx, [rdi+50h]; hObject
0x1801116bb  test    rcx, rcx
0x1801116be  jz      short loc_1801116CA
0x1801116c0  call    cs:__imp_CloseHandle
0x1801116c6  mov     [rdi+50h], rbx
0x1801116ca  mov     [rdi+0C0h], ebx
0x1801116d0  mov     esi, 2000h
0x1801116d5  test    r15b, r15b
0x1801116d8  jnz     short loc_18011173F
0x1801116da  test    cs:dword_180309978, esi
0x1801116e0  jz      short loc_1801116FE
0x1801116e2  lea     r8, off_180305DB0
0x1801116e9  mov     edx, 0D000000h
0x1801116ee  lea     rcx, ?g_messageRec@@3VCMsiAPIMessageRec@@A; CMsiAPIMessageRec g_messageRec
0x1801116f5  call    ?Message@CMsiAPIMessageRec@@QEBA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiAPIMessageRec::Message(imtEnum,IMsiRecord &)
0x1801116fa  test    eax, eax
0x1801116fc  jnz     short loc_18011171A
0x1801116fe  test    cs:dword_1803097B8, esi
0x180111704  jz      short loc_18011171A
0x180111706  xor     r8d, r8d
0x180111709  lea     rcx, ?g_message@@3VCMsiAPIMessage@@A; CMsiAPIMessage g_message
0x180111710  mov     edx, 0D000000h
0x180111715  call    ?Message@CMsiAPIMessage@@QEBA?AW4imsEnum@@W4imtEnum@@PEBG@Z; CMsiAPIMessage::Message(imtEnum,ushort const *)
0x18011171a  mov     rax, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x180111721  test    rax, rax
0x180111724  jz      short loc_18011173F
0x180111726  test    [rax+440h], esi
0x18011172c  jz      short loc_18011173F
0x18011172e  lea     r8, off_180305DB0
0x180111735  mov     edx, 0D000000h
0x18011173a  call    ?Message@CMsiEmbeddedUIManager@@QEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiEmbeddedUIManager::Message(imtEnum,IMsiRecord &)
0x18011173f  cmp     cs:byte_180306EA4, bl
0x180111745  jz      short loc_18011174C
0x180111747  call    ?Terminate@CBasicUI@@QEAA_NXZ; CBasicUI::Terminate(void)
0x18011174c  mov     rcx, [rdi+78h]; hLibModule
0x180111750  test    rcx, rcx
0x180111753  jz      short loc_18011175F
0x180111755  call    cs:__imp_FreeLibrary
0x18011175b  mov     [rdi+78h], rbx
0x18011175f  mov     rcx, [rdi+48h]; hObject
0x180111763  mov     [rdi+0BCh], esi
0x180111769  call    cs:__imp_CloseHandle
0x18011176f  mov     rcx, [rdi+58h]; hObject
0x180111773  mov     [rdi+48h], rbx
0x180111777  call    cs:__imp_CloseHandle
0x18011177d  mov     [rdi+58h], rbx
0x180111781  lea     r13, aNull; "(NULL)"
0x180111788  mov     [rdi+68h], rbx
0x18011178c  mov     esi, ebx
0x18011178e  mov     [rdi+70h], ebx
0x180111791  mov     dword ptr [rdi+74h], 0FFFFFFFFh
0x180111798  mov     [rdi+0CCh], bl
0x18011179e  mov     [rdi+139h], bl
0x1801117a4  mov     [rdi+0E0h], bx
0x1801117ab  mov     [rdi+0E2h], bl
0x1801117b1  mov     eax, esi
0x1801117b3  lea     rbx, ?m_gpoRestartManagerWrapper@CRestartManagerWrapper@@1PAPEAV1@A; CRestartManagerWrapper * near * CRestartManagerWrapper::m_gpoRestartManagerWrapper
0x1801117ba  mov     rbx, [rbx+rax*8]
0x1801117be  test    rbx, rbx
0x1801117c1  jz      loc_180111934
0x1801117c7  test    byte ptr [rbx+310h], 2
0x1801117ce  jnz     loc_180111934
0x1801117d4  mov     rcx, rbx; this
0x1801117d7  call    ?IsEnabled@CRestartManagerWrapper@@QEBA_NXZ; CRestartManagerWrapper::IsEnabled(void)
0x1801117dc  test    al, al
0x1801117de  jz      loc_180111897
0x1801117e4  mov     rax, [rbx]
0x1801117e7  mov     rax, [rax+20h]
0x1801117eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801117f0  test    eax, eax
0x1801117f2  jz      loc_180111897
0x1801117f8  cmp     byte ptr [rbx+314h], 0
0x1801117ff  jnz     loc_180111897
0x180111805  mov     rax, [rbx]
0x180111808  mov     rcx, rbx
0x18011180b  mov     rax, [rax+18h]
0x18011180f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111814  xor     ecx, ecx
0x180111816  test    eax, eax
0x180111818  jz      short loc_180111854
0x18011181a  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x180111820  jz      short loc_180111897
0x180111822  mov     [rsp+180h+var_128], rcx
0x180111827  lea     r9, aRestartManager_10; "RESTART MANAGER: Failed while restartin"...
0x18011182e  mov     [rsp+180h+var_130], ecx
0x180111832  mov     [rsp+180h+var_138], r13
0x180111837  mov     [rsp+180h+var_140], r13
0x18011183c  mov     [rsp+180h+var_148], r13
0x180111841  mov     [rsp+180h+var_150], r13
0x180111846  mov     eax, eax
0x180111848  mov     [rsp+180h+var_158], r13
0x18011184d  mov     [rsp+180h+var_160], rax
0x180111852  jmp     short loc_18011188A
0x180111854  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x18011185a  jz      short loc_180111897
0x18011185c  mov     [rsp+180h+var_128], rcx; void *
0x180111861  lea     r9, aRestartManager_17; "RESTART MANAGER: Previously shut down a"...
0x180111868  mov     [rsp+180h+var_130], ecx; unsigned int
0x18011186c  mov     [rsp+180h+var_138], r13; unsigned __int16 *
0x180111871  mov     [rsp+180h+var_140], r13; unsigned __int16 *
0x180111876  mov     [rsp+180h+var_148], r13; unsigned __int16 *
0x18011187b  mov     [rsp+180h+var_150], r13; unsigned __int16 *
0x180111880  mov     [rsp+180h+var_158], r13; unsigned __int16 *
0x180111885  mov     [rsp+180h+var_160], r13; unsigned __int16 *
0x18011188a  xor     edx, edx; unsigned __int16
0x18011188c  xor     r8d, r8d; int
0x18011188f  lea     ecx, [rdx+0Ah]; int
0x180111892  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180111897  mov     rcx, rbx; this
0x18011189a  call    ?EndSession@CRestartManagerWrapper@@QEBAIXZ; CRestartManagerWrapper::EndSession(void)
0x18011189f  cmp     eax, 65Ah
0x1801118a4  jz      loc_18011192D
0x1801118aa  xor     ecx, ecx
0x1801118ac  test    eax, eax
0x1801118ae  jz      short loc_1801118EA
0x1801118b0  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x1801118b6  jz      short loc_18011192D
0x1801118b8  mov     [rsp+180h+var_128], rcx
0x1801118bd  lea     r9, aRestartManager_13; "RESTART MANAGER: Failed while closing s"...
0x1801118c4  mov     [rsp+180h+var_130], ecx
0x1801118c8  mov     [rsp+180h+var_138], r13
0x1801118cd  mov     [rsp+180h+var_140], r13
0x1801118d2  mov     [rsp+180h+var_148], r13
0x1801118d7  mov     [rsp+180h+var_150], r13
0x1801118dc  mov     eax, eax
0x1801118de  mov     [rsp+180h+var_158], r13
0x1801118e3  mov     [rsp+180h+var_160], rax
0x1801118e8  jmp     short loc_180111920
0x1801118ea  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x1801118f0  jz      short loc_18011192D
0x1801118f2  mov     [rsp+180h+var_128], rcx; void *
0x1801118f7  lea     r9, aRestartManager_21; "RESTART MANAGER: Session closed."
0x1801118fe  mov     [rsp+180h+var_130], ecx; unsigned int
0x180111902  mov     [rsp+180h+var_138], r13; unsigned __int16 *
0x180111907  mov     [rsp+180h+var_140], r13; unsigned __int16 *
0x18011190c  mov     [rsp+180h+var_148], r13; unsigned __int16 *
0x180111911  mov     [rsp+180h+var_150], r13; unsigned __int16 *
0x180111916  mov     [rsp+180h+var_158], r13; unsigned __int16 *
0x18011191b  mov     [rsp+180h+var_160], r13; unsigned __int16 *
0x180111920  xor     edx, edx; unsigned __int16
0x180111922  xor     r8d, r8d; int
0x180111925  lea     ecx, [rdx+0Ah]; int
0x180111928  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18011192d  mov     ecx, esi
0x18011192f  call    ?DestroyInstance@CRestartManagerWrapper@@SAXW4ieRMInstallLevel@@@Z; CRestartManagerWrapper::DestroyInstance(ieRMInstallLevel)
0x180111934  inc     esi
0x180111936  cmp     esi, 1
0x180111939  jle     loc_1801117B1
0x18011193f  call    ?FreePolicyTable@@YAXXZ; FreePolicyTable(void)
0x180111944  mov     rcx, cs:qword_180309780; this
0x18011194b  xor     esi, esi
0x18011194d  mov     r13b, [rsp+180h+var_120]
0x180111952  test    rcx, rcx
0x180111955  jz      short loc_18011199F
0x180111957  cmp     cs:qword_180309728, rsi
0x18011195e  jnz     short loc_18011199F
0x180111960  test    r15b, r15b
0x180111963  jnz     short loc_18011199F
0x180111965  test    r14, r14
0x180111968  jz      short loc_180111970
0x18011196a  cmp     [r14+10h], esi
0x18011196e  jl      short loc_18011199F
0x180111970  cmp     dword ptr [rcx+10h], 5
0x180111974  jz      short loc_18011198E
  ... truncated ...
```

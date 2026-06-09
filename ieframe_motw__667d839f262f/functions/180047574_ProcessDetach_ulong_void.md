# _ProcessDetach(ulong,void *)

- ea: `0x180047574`
- end: `0x180047aa4`
- name: `?_ProcessDetach@@YAXKPEAX@Z`
- size: `1328`
- prototype: `void __fastcall(unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bfc00`

## callees

- `0x1800393a8`
- `0x180047574`
- `0x180047aac`
- `0x180047b50`
- `0x180047b74`
- `0x1800ecc0c`
- `0x180550010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1800479a2`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800479a2`
- `KERNEL32!ReleaseActCtx` at `0x1800477fd`
- `KERNEL32!ReleaseActCtx` at `0x1800477fd`
- `KERNEL32!LocalFree` at `0x1800479fe`
- `KERNEL32!LocalFree` at `0x180047a81`
- `KERNEL32!LocalFree` at `0x1800479fe`
- `KERNEL32!LocalFree` at `0x180047a81`
- `KERNEL32!TlsFree` at `0x180047659`
- `KERNEL32!TlsFree` at `0x180047829`
- `KERNEL32!TlsFree` at `0x180047901`
- `KERNEL32!TlsFree` at `0x180047a14`
- `KERNEL32!TlsFree` at `0x180047659`
- `KERNEL32!TlsFree` at `0x180047829`
- `KERNEL32!TlsFree` at `0x180047901`
- `KERNEL32!TlsFree` at `0x180047a14`
- `KERNEL32!FreeLibrary` at `0x1800478e0`
- `KERNEL32!FreeLibrary` at `0x180047a09`
- `KERNEL32!FreeLibrary` at `0x1800478e0`
- `KERNEL32!FreeLibrary` at `0x180047a09`
- `KERNEL32!DeleteCriticalSection` at `0x18004775e`
- `KERNEL32!DeleteCriticalSection` at `0x18004776b`
- `KERNEL32!DeleteCriticalSection` at `0x180047778`
- `KERNEL32!DeleteCriticalSection` at `0x180047785`
- `KERNEL32!DeleteCriticalSection` at `0x180047792`
- `KERNEL32!DeleteCriticalSection` at `0x18004779f`
- `KERNEL32!DeleteCriticalSection` at `0x1800477ac`
- `KERNEL32!DeleteCriticalSection` at `0x1800477b9`
- `KERNEL32!DeleteCriticalSection` at `0x1800477e7`
- `KERNEL32!DeleteCriticalSection` at `0x18004775e`
- `KERNEL32!DeleteCriticalSection` at `0x18004776b`
- `KERNEL32!DeleteCriticalSection` at `0x180047778`
- `KERNEL32!DeleteCriticalSection` at `0x180047785`
- `KERNEL32!DeleteCriticalSection` at `0x180047792`
- `KERNEL32!DeleteCriticalSection` at `0x18004779f`
- `KERNEL32!DeleteCriticalSection` at `0x1800477ac`
- `KERNEL32!DeleteCriticalSection` at `0x1800477b9`
- `KERNEL32!DeleteCriticalSection` at `0x1800477e7`
- `KERNEL32!CloseHandle` at `0x180047a26`
- `KERNEL32!CloseHandle` at `0x180047a38`
- `KERNEL32!CloseHandle` at `0x180047a26`
- `KERNEL32!CloseHandle` at `0x180047a38`
- `KERNEL32!LeaveCriticalSection` at `0x1800475b2`
- `KERNEL32!LeaveCriticalSection` at `0x1800475e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800476c5`
- `KERNEL32!LeaveCriticalSection` at `0x180047755`
- `KERNEL32!LeaveCriticalSection` at `0x18004785f`
- `KERNEL32!LeaveCriticalSection` at `0x180047896`
- `KERNEL32!LeaveCriticalSection` at `0x1800475b2`
- `KERNEL32!LeaveCriticalSection` at `0x1800475e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800476c5`
- `KERNEL32!LeaveCriticalSection` at `0x180047755`
- `KERNEL32!LeaveCriticalSection` at `0x18004785f`
- `KERNEL32!LeaveCriticalSection` at `0x180047896`
- `KERNEL32!EnterCriticalSection` at `0x180047597`
- `KERNEL32!EnterCriticalSection` at `0x1800475cb`
- `KERNEL32!EnterCriticalSection` at `0x18004769c`
- `KERNEL32!EnterCriticalSection` at `0x18004770c`
- `KERNEL32!EnterCriticalSection` at `0x18004783e`
- `KERNEL32!EnterCriticalSection` at `0x18004787d`
- `KERNEL32!EnterCriticalSection` at `0x180047597`
- `KERNEL32!EnterCriticalSection` at `0x1800475cb`
- `KERNEL32!EnterCriticalSection` at `0x18004769c`
- `KERNEL32!EnterCriticalSection` at `0x18004770c`
- `KERNEL32!EnterCriticalSection` at `0x18004783e`
- `KERNEL32!EnterCriticalSection` at `0x18004787d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180047979`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180047979`
- `GDI32!DeleteObject` at `0x180047913`
- `GDI32!DeleteObject` at `0x1800479da`
- `GDI32!DeleteObject` at `0x180047913`
- `GDI32!DeleteObject` at `0x1800479da`
- `USER32!DestroyIcon` at `0x180047a5e`
- `USER32!DestroyIcon` at `0x180047a5e`
- `USER32!UnregisterClassW` at `0x1800478b1`
- `USER32!UnregisterClassW` at `0x1800478b1`
- `iertutil!__imp_DSA_DeleteAllItems` at `0x1800479c6`
- `iertutil!__imp_DSA_DeleteAllItems` at `0x1800479c6`
- `iertutil!__imp_DSA_Destroy` at `0x1800479cf`
- `iertutil!__imp_DSA_Destroy` at `0x1800479cf`
- `iertutil!__imp_DSA_DestroyCallback` at `0x18004792f`
- `iertutil!__imp_DSA_DestroyCallback` at `0x180047967`
- `iertutil!__imp_DSA_DestroyCallback` at `0x18004792f`
- `iertutil!__imp_DSA_DestroyCallback` at `0x180047967`
- `iertutil!__imp_DPA_DestroyCallback` at `0x18004794b`
- `iertutil!__imp_DPA_DestroyCallback` at `0x18004794b`
- `iertutil!__imp_?IESetThreadRefTLSIndex@@YAXK@Z` at `0x1800478f5`
- `iertutil!__imp_?IESetThreadRefTLSIndex@@YAXK@Z` at `0x1800478f5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180047a99`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180047a99`

## pseudocode

```c
void __fastcall _ProcessDetach(__int64 a1, void *a2)
{
  unsigned int v3; // edx
  unsigned int i; // ebx
  HKEY v5; // rcx
  struct _DSA *v6; // rbx
  unsigned int j; // ebx
  HBITMAP near *v8; // rcx
  HICON *v9; // rbx
  unsigned int m; // ebx
  void *v11; // rcx
  struct ATL::_ATL_MODULE *v12; // rcx
  unsigned int v13; // edx
  HINSTANCE v14; // rdi
  __int64 k; // rbx
  unsigned int v16; // eax
  unsigned int v17; // edi

  g_bDllTerminating = 1;
  EnterCriticalSection(&g_csDll);
  if ( g_cdsaModuleInfoCache )
  {
    DSA_DestroyCallback(g_cdsaModuleInfoCache, ModuleCacheEntryDelete, 0);
    g_cdsaModuleInfoCache = 0;
  }
  LeaveCriticalSection(&g_csDll);
  if ( CDocObjectHost::CDOHBindStatusCallback::s_dpaFTPCredentials )
  {
    DPA_DestroyCallback(
      CDocObjectHost::CDOHBindStatusCallback::s_dpaFTPCredentials,
      CDocObjectHost::CDOHBindStatusCallback::s_FTPCredentialsDPAFree,
      0);
    CDocObjectHost::CDOHBindStatusCallback::s_dpaFTPCredentials = 0;
  }
  EnterCriticalSection(&g_csDll);
  if ( hdsa )
  {
    DSA_DestroyCallback(hdsa, CDefaultOpenDataDSA_DestroyCallback, 0);
    hdsa = 0;
  }
  LeaveCriticalSection(&g_csDll);
  for ( i = 0; i < 7; ++i )
  {
    v5 = (HKEY)qword_18065A040[5 * (int)i];
    if ( v5 )
    {
      RegCloseKey(v5);
      qword_18065A040[5 * (int)i] = 0;
    }
  }
  if ( qword_18065AA38 )
  {
    CPolicyCache::`scalar deleting destructor'(qword_18065AA38, v3);
    qword_18065AA38 = 0;
  }
  TraceLoggingUnregister_EventUnregister(&dword_18065A818);
  if ( g_tlsThreadRef != -1 )
  {
    IESetThreadRefTLSIndex(0xFFFFFFFF);
    TlsFree(g_tlsThreadRef);
    g_tlsThreadRef = -1;
  }
  if ( g_tlsOtherThreadsRef != -1 )
  {
    TlsFree(g_tlsOtherThreadsRef);
    g_tlsOtherThreadsRef = -1;
  }
  if ( TabThreadMinidumpState::_tlsIndex != -1 )
  {
    TlsFree(TabThreadMinidumpState::_tlsIndex);
    TabThreadMinidumpState::_tlsIndex = -1;
  }
  McGenEventUnregister_EventUnregister(BERP_READINGVIEW_Context);
  McGenEventUnregister_EventUnregister(BERP_IEFRAME2_Context);
  McGenEventUnregister_EventUnregister(BERP_IEFRAME_Context);
  McGenEventUnregister_EventUnregister(BERP_MSHTML_Context);
  v6 = 0;
  EnterCriticalSection(&g_csDll);
  if ( g_hFileStoreTimer )
  {
    DeleteTimerQueueTimer(0, g_hFileStoreTimer, 0);
    g_hFileStoreTimer = 0;
  }
  if ( g_dsaFileHandleStore )
  {
    v6 = g_dsaFileHandleStore;
    g_dsaFileHandleStore = 0;
  }
  LeaveCriticalSection(&g_csDll);
  if ( v6 )
  {
    DSA_DeleteAllItems(v6);
    DSA_Destroy(v6);
  }
  for ( j = 0; j < 0x1F; ++j )
  {
    v8 = (&g_rghbmpFavIconBase)[j];
    if ( v8 )
    {
      DeleteObject(v8);
      (&g_rghbmpFavIconBase)[j] = 0;
    }
  }
  if ( !a2 )
  {
    EnterCriticalSection(&g_csDll);
    if ( g_puhUrlHistory )
      (*(void (__fastcall **)(struct IUrlHistoryPriv *))(*(_QWORD *)g_puhUrlHistory + 16LL))(g_puhUrlHistory);
    LeaveCriticalSection(&g_csDll);
    ATL::AtlModuleTerm(v12);
    if ( g_pExtensionRecorder )
    {
      CExtensionRecorder::`scalar deleting destructor'(g_pExtensionRecorder, v13);
      g_pExtensionRecorder = 0;
    }
    EnterCriticalSection(&g_csDll);
    if ( g_pszProtectedModeBuffer )
      LocalFree(g_pszProtectedModeBuffer);
    LeaveCriticalSection(&g_csDll);
    v14 = g_hinst;
    for ( k = 0; k != 55; ++k )
      UnregisterClassW(off_1805571E0[k], v14);
    if ( g_hmodWininet )
      FreeLibrary(g_hmodWininet);
    if ( g_hInstMshtmlMui )
    {
      FreeLibrary(g_hInstMshtmlMui);
      g_hInstMshtmlMui = 0;
    }
  }
  if ( dwTlsIndex != -1 )
  {
    TlsFree(dwTlsIndex);
    dwTlsIndex = -1;
  }
  EnterCriticalSection(&g_csDll);
  if ( g_hpalHalftone )
  {
    DeleteObject(g_hpalHalftone);
    g_hpalHalftone = 0;
  }
  if ( g_hMutexHistory )
  {
    CloseHandle(g_hMutexHistory);
    g_hMutexHistory = 0;
  }
  if ( g_hSemaphoreWindowRevoke )
  {
    CloseHandle(g_hSemaphoreWindowRevoke);
    g_hSemaphoreWindowRevoke = 0;
  }
  v9 = (HICON *)g_pZoneIconNameCache;
  if ( g_pZoneIconNameCache )
  {
    v16 = g_dwZoneCount;
    v17 = 0;
    if ( g_dwZoneCount )
    {
      do
      {
        if ( *v9 )
        {
          DestroyIcon(*v9);
          v16 = g_dwZoneCount;
        }
        v9 += 116;
        ++v17;
      }
      while ( v17 < v16 );
      v9 = (HICON *)g_pZoneIconNameCache;
    }
    LocalFree(v9);
    g_pZoneIconNameCache = 0;
    g_dwZoneCount = 0;
  }
  LeaveCriticalSection(&g_csDll);
  DeleteCriticalSection(&g_csDll);
  DeleteCriticalSection(&g_csThreadHooks);
  DeleteCriticalSection(&g_csThumbnail);
  DeleteCriticalSection(&g_csDownloadManager);
  DeleteCriticalSection(&g_csNewTabPageData);
  DeleteCriticalSection(&g_csLocalRoamedTabTimer);
  DeleteCriticalSection(&g_csNamedWindowList);
  DeleteCriticalSection(&CAsyncStorage::s_csInCallback);
  for ( m = 0; m < 0x20; ++m )
  {
    v11 = (void *)qword_180662158[4 * (int)m];
    if ( v11 )
      CoTaskMemFree(v11);
  }
  DeleteCriticalSection(&stru_180662540);
  if ( g_hActCtx != (HANDLE)-1LL )
  {
    ReleaseActCtx(g_hActCtx);
    g_hActCtx = (HANDLE)-1LL;
  }
  if ( qword_180662700 )
    qword_180662700 = (HMODULE)-1LL;
}

```

## disassembly

```asm
0x180047574  push    rbx
0x180047576  push    rbp
0x180047577  push    rsi
0x180047578  push    rdi
0x180047579  push    r12
0x18004757b  push    r14
0x18004757d  push    r15
0x18004757f  sub     rsp, 20h
0x180047583  lea     r14, g_csDll
0x18004758a  mov     cs:?g_bDllTerminating@@3_NA, 1; bool g_bDllTerminating
0x180047591  mov     rcx, r14; lpCriticalSection
0x180047594  mov     rsi, rdx
0x180047597  call    cs:__imp_EnterCriticalSection
0x18004759d  mov     rcx, cs:?g_cdsaModuleInfoCache@@3V?$CDSA@U_tagModuleInfoCache@@@@A; hdsa
0x1800475a4  xor     ebp, ebp
0x1800475a6  test    rcx, rcx
0x1800475a9  jnz     loc_180047925
0x1800475af  mov     rcx, r14; lpCriticalSection
0x1800475b2  call    cs:__imp_LeaveCriticalSection
0x1800475b8  mov     rcx, cs:?s_dpaFTPCredentials@CDOHBindStatusCallback@CDocObjectHost@@1V?$CDPA@UFTPCredentials@CDOHBindStatusCallback@CDocObjectHost@@@@A; hdpa
0x1800475bf  test    rcx, rcx
0x1800475c2  jnz     loc_180047941
0x1800475c8  mov     rcx, r14; lpCriticalSection
0x1800475cb  call    cs:__imp_EnterCriticalSection
0x1800475d1  mov     rcx, cs:hdsa; hdsa
0x1800475d8  test    rcx, rcx
0x1800475db  jnz     loc_18004795D
0x1800475e1  mov     rcx, r14; lpCriticalSection
0x1800475e4  call    cs:__imp_LeaveCriticalSection
0x1800475ea  mov     ebx, ebp
0x1800475ec  lea     r12, __ImageBase
0x1800475f3  movsxd  rax, ebx
0x1800475f6  lea     rdi, [rax+rax*4]
0x1800475fa  mov     rcx, rva qword_18065A040[r12+rdi*8]; hKey
0x180047602  test    rcx, rcx
0x180047605  jnz     loc_180047979
0x18004760b  inc     ebx
0x18004760d  cmp     ebx, 7
0x180047610  jb      short loc_1800475F3
0x180047612  mov     rcx, cs:qword_18065AA38; this
0x180047619  test    rcx, rcx
0x18004761c  jnz     loc_18004798C
0x180047622  lea     rcx, dword_18065A818
0x180047629  call    TraceLoggingUnregister_EventUnregister
0x18004762e  or      r15d, 0FFFFFFFFh
0x180047632  cmp     cs:g_tlsThreadRef, r15d
0x180047639  jnz     loc_1800478F2
0x18004763f  mov     ecx, cs:g_tlsOtherThreadsRef; dwTlsIndex
0x180047645  cmp     ecx, r15d
0x180047648  jnz     loc_180047829
0x18004764e  mov     ecx, cs:?_tlsIndex@TabThreadMinidumpState@@0KA; dwTlsIndex
0x180047654  cmp     ecx, r15d
0x180047657  jz      short loc_180047666
0x180047659  call    cs:__imp_TlsFree
0x18004765f  mov     cs:?_tlsIndex@TabThreadMinidumpState@@0KA, r15d; ulong TabThreadMinidumpState::_tlsIndex
0x180047666  lea     rcx, BERP_READINGVIEW_Context
0x18004766d  call    McGenEventUnregister_EventUnregister
0x180047672  lea     rcx, BERP_IEFRAME2_Context
0x180047679  call    McGenEventUnregister_EventUnregister
0x18004767e  lea     rcx, BERP_IEFRAME_Context
0x180047685  call    McGenEventUnregister_EventUnregister
0x18004768a  lea     rcx, BERP_MSHTML_Context
0x180047691  call    McGenEventUnregister_EventUnregister
0x180047696  mov     rcx, r14; lpCriticalSection
0x180047699  mov     rbx, rbp
0x18004769c  call    cs:__imp_EnterCriticalSection
0x1800476a2  mov     rdx, cs:?g_hFileStoreTimer@@3PEAXEA; Timer
0x1800476a9  test    rdx, rdx
0x1800476ac  jnz     loc_18004799D
0x1800476b2  mov     rax, cs:?g_dsaFileHandleStore@@3V?$CDSA@USTOREDFILEINFO@@@@A; CDSA<STOREDFILEINFO> g_dsaFileHandleStore
0x1800476b9  test    rax, rax
0x1800476bc  jnz     loc_1800479B4
0x1800476c2  mov     rcx, r14; lpCriticalSection
0x1800476c5  call    cs:__imp_LeaveCriticalSection
0x1800476cb  test    rbx, rbx
0x1800476ce  jnz     loc_1800479C3
0x1800476d4  mov     ebx, ebp
0x1800476d6  movsxd  rdi, ebx
0x1800476d9  mov     rcx, rva ?g_rghbmpFavIconBase@@3PAPEAUHBITMAP__@@A[r12+rdi*8]; ho
0x1800476e1  test    rcx, rcx
0x1800476e4  jnz     loc_1800479DA
0x1800476ea  inc     ebx
0x1800476ec  cmp     ebx, 1Fh
0x1800476ef  jb      short loc_1800476D6
0x1800476f1  test    rsi, rsi
0x1800476f4  jz      loc_18004783B
0x1800476fa  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180047700  cmp     ecx, r15d
0x180047703  jnz     loc_180047A14
0x180047709  mov     rcx, r14; lpCriticalSection
0x18004770c  call    cs:__imp_EnterCriticalSection
0x180047712  mov     rcx, cs:g_hpalHalftone; ho
0x180047719  test    rcx, rcx
0x18004771c  jnz     loc_180047913
0x180047722  mov     rcx, cs:g_hMutexHistory; hObject
0x180047729  test    rcx, rcx
0x18004772c  jnz     loc_180047A26
0x180047732  mov     rcx, cs:g_hSemaphoreWindowRevoke; hObject
0x180047739  test    rcx, rcx
0x18004773c  jnz     loc_180047A38
0x180047742  mov     rbx, cs:?g_pZoneIconNameCache@@3PEAU_ZONESICONNAMECACHE@@EA; _ZONESICONNAMECACHE * g_pZoneIconNameCache
0x180047749  test    rbx, rbx
0x18004774c  jnz     loc_180047A4A
0x180047752  mov     rcx, r14; lpCriticalSection
0x180047755  call    cs:__imp_LeaveCriticalSection
0x18004775b  mov     rcx, r14; lpCriticalSection
0x18004775e  call    cs:__imp_DeleteCriticalSection
0x180047764  lea     rcx, ?g_csThreadHooks@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004776b  call    cs:__imp_DeleteCriticalSection
0x180047771  lea     rcx, ?g_csThumbnail@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180047778  call    cs:__imp_DeleteCriticalSection
0x18004777e  lea     rcx, ?g_csDownloadManager@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180047785  call    cs:__imp_DeleteCriticalSection
0x18004778b  lea     rcx, ?g_csNewTabPageData@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180047792  call    cs:__imp_DeleteCriticalSection
0x180047798  lea     rcx, ?g_csLocalRoamedTabTimer@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004779f  call    cs:__imp_DeleteCriticalSection
0x1800477a5  lea     rcx, ?g_csNamedWindowList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800477ac  call    cs:__imp_DeleteCriticalSection
0x1800477b2  lea     rcx, ?s_csInCallback@CAsyncStorage@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800477b9  call    cs:__imp_DeleteCriticalSection
0x1800477bf  mov     ebx, ebp
0x1800477c1  movsxd  rax, ebx
0x1800477c4  shl     rax, 5
0x1800477c8  mov     rcx, [rax+r12+662158h]; pv
0x1800477d0  test    rcx, rcx
0x1800477d3  jnz     loc_180047A99
0x1800477d9  inc     ebx
0x1800477db  cmp     ebx, 20h ; ' '
0x1800477de  jb      short loc_1800477C1
0x1800477e0  lea     rcx, stru_180662540; lpCriticalSection
0x1800477e7  call    cs:__imp_DeleteCriticalSection
0x1800477ed  mov     rcx, cs:g_hActCtx; hActCtx
0x1800477f4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800477f8  cmp     rcx, rbx
0x1800477fb  jz      short loc_18004780A
0x1800477fd  call    cs:__imp_ReleaseActCtx
0x180047803  mov     cs:g_hActCtx, rbx
0x18004780a  cmp     cs:qword_180662700, rbp
0x180047811  jz      short loc_18004781A
0x180047813  mov     cs:qword_180662700, rbx
0x18004781a  add     rsp, 20h
0x18004781e  pop     r15
0x180047820  pop     r14
0x180047822  pop     r12
0x180047824  pop     rdi
0x180047825  pop     rsi
0x180047826  pop     rbp
0x180047827  pop     rbx
0x180047828  retn
0x180047829  call    cs:__imp_TlsFree
0x18004782f  mov     cs:g_tlsOtherThreadsRef, r15d
0x180047836  jmp     loc_18004764E
0x18004783b  mov     rcx, r14; lpCriticalSection
0x18004783e  call    cs:__imp_EnterCriticalSection
0x180047844  mov     rcx, cs:?g_puhUrlHistory@@3PEAUIUrlHistoryPriv@@EA; IUrlHistoryPriv * g_puhUrlHistory
0x18004784b  test    rcx, rcx
0x18004784e  jz      short loc_18004785C
0x180047850  mov     rax, [rcx]
0x180047853  mov     rax, [rax+10h]
0x180047857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004785c  mov     rcx, r14; lpCriticalSection
0x18004785f  call    cs:__imp_LeaveCriticalSection
0x180047865  call    ?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z; ATL::AtlModuleTerm(ATL::_ATL_MODULE *)
0x18004786a  mov     rcx, cs:?g_pExtensionRecorder@@3PEAVCExtensionRecorder@@EA; this
0x180047871  test    rcx, rcx
0x180047874  jnz     loc_1800479ED
0x18004787a  mov     rcx, r14; lpCriticalSection
0x18004787d  call    cs:__imp_EnterCriticalSection
0x180047883  mov     rcx, cs:?g_pszProtectedModeBuffer@@3PEAGEA; hMem
0x18004788a  test    rcx, rcx
0x18004788d  jnz     loc_1800479FE
0x180047893  mov     rcx, r14; lpCriticalSection
0x180047896  call    cs:__imp_LeaveCriticalSection
0x18004789c  mov     rdi, cs:g_hinst
0x1800478a3  mov     rbx, rbp
0x1800478a6  mov     rcx, ds:rva off_1805571E0[r12+rbx*8]; lpClassName
0x1800478ae  mov     rdx, rdi; hInstance
0x1800478b1  call    cs:__imp_UnregisterClassW
0x1800478b7  inc     rbx
0x1800478ba  cmp     rbx, 37h ; '7'
0x1800478be  jnz     short loc_1800478A6
0x1800478c0  mov     rcx, cs:g_hmodWininet; hLibModule
0x1800478c7  test    rcx, rcx
0x1800478ca  jnz     loc_180047A09
0x1800478d0  mov     rcx, cs:g_hInstMshtmlMui; hLibModule
0x1800478d7  test    rcx, rcx
0x1800478da  jz      loc_1800476FA
0x1800478e0  call    cs:__imp_FreeLibrary
0x1800478e6  mov     cs:g_hInstMshtmlMui, rbp
0x1800478ed  jmp     loc_1800476FA
0x1800478f2  mov     ecx, r15d
0x1800478f5  call    cs:__imp_?IESetThreadRefTLSIndex@@YAXK@Z; IESetThreadRefTLSIndex(ulong)
0x1800478fb  mov     ecx, cs:g_tlsThreadRef; dwTlsIndex
0x180047901  call    cs:__imp_TlsFree
0x180047907  mov     cs:g_tlsThreadRef, r15d
0x18004790e  jmp     loc_18004763F
0x180047913  call    cs:__imp_DeleteObject
0x180047919  mov     cs:g_hpalHalftone, rbp
0x180047920  jmp     loc_180047722
0x180047925  xor     r8d, r8d; pData
0x180047928  lea     rdx, ?ModuleCacheEntryDelete@@YAHPEAU_tagModuleInfoCache@@PEAX@Z; pfnCB
0x18004792f  call    cs:__imp_DSA_DestroyCallback
0x180047935  mov     cs:?g_cdsaModuleInfoCache@@3V?$CDSA@U_tagModuleInfoCache@@@@A, rbp; CDSA<_tagModuleInfoCache> g_cdsaModuleInfoCache
0x18004793c  jmp     loc_1800475AF
0x180047941  xor     r8d, r8d; pData
0x180047944  lea     rdx, ?s_FTPCredentialsDPAFree@CDOHBindStatusCallback@CDocObjectHost@@KAHPEAUFTPCredentials@12@PEAX@Z; pfnCB
0x18004794b  call    cs:__imp_DPA_DestroyCallback
0x180047951  mov     cs:?s_dpaFTPCredentials@CDOHBindStatusCallback@CDocObjectHost@@1V?$CDPA@UFTPCredentials@CDOHBindStatusCallback@CDocObjectHost@@@@A, rbp; CDPA<CDocObjectHost::CDOHBindStatusCallback::FTPCredentials> CDocObjectHost::CDOHBindStatusCallback::s_dpaFTPCredentials
0x180047958  jmp     loc_1800475C8
0x18004795d  xor     r8d, r8d; pData
0x180047960  lea     rdx, ?CDefaultOpenDataDSA_DestroyCallback@@YAHPEAUDefaultOpenData@@PEAX@Z; pfnCB
0x180047967  call    cs:__imp_DSA_DestroyCallback
0x18004796d  mov     cs:hdsa, rbp
0x180047974  jmp     loc_1800475E1
0x180047979  call    cs:__imp_RegCloseKey
0x18004797f  mov     rva qword_18065A040[r12+rdi*8], rbp
0x180047987  jmp     loc_18004760B
0x18004798c  call    ??_GCPolicyCache@@QEAAPEAXI@Z; CPolicyCache::`scalar deleting destructor'(uint)
0x180047991  mov     cs:qword_18065AA38, rbp
0x180047998  jmp     loc_180047622
0x18004799d  xor     r8d, r8d; CompletionEvent
0x1800479a0  xor     ecx, ecx; TimerQueue
0x1800479a2  call    cs:__imp_DeleteTimerQueueTimer
0x1800479a8  mov     cs:?g_hFileStoreTimer@@3PEAXEA, rbp; void * g_hFileStoreTimer
0x1800479af  jmp     loc_1800476B2
0x1800479b4  mov     rbx, rax
0x1800479b7  mov     cs:?g_dsaFileHandleStore@@3V?$CDSA@USTOREDFILEINFO@@@@A, rbp; CDSA<STOREDFILEINFO> g_dsaFileHandleStore
0x1800479be  jmp     loc_1800476C2
0x1800479c3  mov     rcx, rbx; hdsa
0x1800479c6  call    cs:__imp_DSA_DeleteAllItems
0x1800479cc  mov     rcx, rbx; hdsa
0x1800479cf  call    cs:__imp_DSA_Destroy
0x1800479d5  jmp     loc_1800476D4
0x1800479da  call    cs:__imp_DeleteObject
0x1800479e0  mov     rva ?g_rghbmpFavIconBase@@3PAPEAUHBITMAP__@@A[r12+rdi*8], rbp; HBITMAP__ * near * g_rghbmpFavIconBase ...
0x1800479e8  jmp     loc_1800476EA
0x1800479ed  call    ??_GCExtensionRecorder@@QEAAPEAXI@Z; CExtensionRecorder::`scalar deleting destructor'(uint)
0x1800479f2  mov     cs:?g_pExtensionRecorder@@3PEAVCExtensionRecorder@@EA, rbp; CExtensionRecorder * g_pExtensionRecorder
0x1800479f9  jmp     loc_18004787A
0x1800479fe  call    cs:__imp_LocalFree
0x180047a04  jmp     loc_180047893
0x180047a09  call    cs:__imp_FreeLibrary
0x180047a0f  jmp     loc_1800478D0
0x180047a14  call    cs:__imp_TlsFree
0x180047a1a  mov     cs:dwTlsIndex, r15d
0x180047a21  jmp     loc_180047709
0x180047a26  call    cs:__imp_CloseHandle
0x180047a2c  mov     cs:g_hMutexHistory, rbp
0x180047a33  jmp     loc_180047732
0x180047a38  call    cs:__imp_CloseHandle
0x180047a3e  mov     cs:g_hSemaphoreWindowRevoke, rbp
0x180047a45  jmp     loc_180047742
0x180047a4a  mov     eax, cs:?g_dwZoneCount@@3KA; ulong g_dwZoneCount
0x180047a50  mov     edi, ebp
0x180047a52  test    eax, eax
0x180047a54  jz      short loc_180047A7E
0x180047a56  mov     rcx, [rbx]; hIcon
0x180047a59  test    rcx, rcx
0x180047a5c  jz      short loc_180047A6A
0x180047a5e  call    cs:__imp_DestroyIcon
0x180047a64  mov     eax, cs:?g_dwZoneCount@@3KA; ulong g_dwZoneCount
0x180047a6a  add     rbx, 3A0h
0x180047a71  inc     edi
0x180047a73  cmp     edi, eax
0x180047a75  jb      short loc_180047A56
0x180047a77  mov     rbx, cs:?g_pZoneIconNameCache@@3PEAU_ZONESICONNAMECACHE@@EA; _ZONESICONNAMECACHE * g_pZoneIconNameCache
0x180047a7e  mov     rcx, rbx; hMem
0x180047a81  call    cs:__imp_LocalFree
0x180047a87  mov     cs:?g_pZoneIconNameCache@@3PEAU_ZONESICONNAMECACHE@@EA, rbp; _ZONESICONNAMECACHE * g_pZoneIconNameCache
0x180047a8e  mov     cs:?g_dwZoneCount@@3KA, ebp; ulong g_dwZoneCount
0x180047a94  jmp     loc_180047752
0x180047a99  call    cs:__imp_CoTaskMemFree
0x180047a9f  jmp     loc_1800477D9
```

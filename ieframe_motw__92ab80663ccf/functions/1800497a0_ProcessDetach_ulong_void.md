# _ProcessDetach(ulong,void *)

- ea: `0x1800497a0`
- end: `0x180049ddf`
- name: `?_ProcessDetach@@YAXKPEAX@Z`
- size: `1599`
- prototype: `void __fastcall(unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c6a8c`

## callees

- `0x18003afb0`
- `0x1800497a0`
- `0x180049de8`
- `0x180049eac`
- `0x180049ed4`
- `0x1800f6c7c`
- `0x180594010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x180049c95`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180049c95`
- `KERNEL32!ReleaseActCtx` at `0x180049a95`
- `KERNEL32!ReleaseActCtx` at `0x180049a95`
- `KERNEL32!LocalFree` at `0x180049d09`
- `KERNEL32!LocalFree` at `0x180049db0`
- `KERNEL32!LocalFree` at `0x180049d09`
- `KERNEL32!LocalFree` at `0x180049db0`
- `KERNEL32!TlsFree` at `0x18004989d`
- `KERNEL32!TlsFree` at `0x180049ac8`
- `KERNEL32!TlsFree` at `0x180049bd0`
- `KERNEL32!TlsFree` at `0x180049d2b`
- `KERNEL32!TlsFree` at `0x18004989d`
- `KERNEL32!TlsFree` at `0x180049ac8`
- `KERNEL32!TlsFree` at `0x180049bd0`
- `KERNEL32!TlsFree` at `0x180049d2b`
- `KERNEL32!FreeLibrary` at `0x180049ba3`
- `KERNEL32!FreeLibrary` at `0x180049d1a`
- `KERNEL32!FreeLibrary` at `0x180049ba3`
- `KERNEL32!FreeLibrary` at `0x180049d1a`
- `KERNEL32!DeleteCriticalSection` at `0x1800499c0`
- `KERNEL32!DeleteCriticalSection` at `0x1800499d3`
- `KERNEL32!DeleteCriticalSection` at `0x1800499e6`
- `KERNEL32!DeleteCriticalSection` at `0x1800499f9`
- `KERNEL32!DeleteCriticalSection` at `0x180049a0c`
- `KERNEL32!DeleteCriticalSection` at `0x180049a1f`
- `KERNEL32!DeleteCriticalSection` at `0x180049a32`
- `KERNEL32!DeleteCriticalSection` at `0x180049a45`
- `KERNEL32!DeleteCriticalSection` at `0x180049a79`
- `KERNEL32!DeleteCriticalSection` at `0x1800499c0`
- `KERNEL32!DeleteCriticalSection` at `0x1800499d3`
- `KERNEL32!DeleteCriticalSection` at `0x1800499e6`
- `KERNEL32!DeleteCriticalSection` at `0x1800499f9`
- `KERNEL32!DeleteCriticalSection` at `0x180049a0c`
- `KERNEL32!DeleteCriticalSection` at `0x180049a1f`
- `KERNEL32!DeleteCriticalSection` at `0x180049a32`
- `KERNEL32!DeleteCriticalSection` at `0x180049a45`
- `KERNEL32!DeleteCriticalSection` at `0x180049a79`
- `KERNEL32!CloseHandle` at `0x180049d43`
- `KERNEL32!CloseHandle` at `0x180049d5b`
- `KERNEL32!CloseHandle` at `0x180049d43`
- `KERNEL32!CloseHandle` at `0x180049d5b`
- `KERNEL32!LeaveCriticalSection` at `0x1800497e4`
- `KERNEL32!LeaveCriticalSection` at `0x180049822`
- `KERNEL32!LeaveCriticalSection` at `0x180049915`
- `KERNEL32!LeaveCriticalSection` at `0x1800499b1`
- `KERNEL32!LeaveCriticalSection` at `0x180049b0a`
- `KERNEL32!LeaveCriticalSection` at `0x180049b4d`
- `KERNEL32!LeaveCriticalSection` at `0x1800497e4`
- `KERNEL32!LeaveCriticalSection` at `0x180049822`
- `KERNEL32!LeaveCriticalSection` at `0x180049915`
- `KERNEL32!LeaveCriticalSection` at `0x1800499b1`
- `KERNEL32!LeaveCriticalSection` at `0x180049b0a`
- `KERNEL32!LeaveCriticalSection` at `0x180049b4d`
- `KERNEL32!EnterCriticalSection` at `0x1800497c3`
- `KERNEL32!EnterCriticalSection` at `0x180049803`
- `KERNEL32!EnterCriticalSection` at `0x1800498e6`
- `KERNEL32!EnterCriticalSection` at `0x180049962`
- `KERNEL32!EnterCriticalSection` at `0x180049ae3`
- `KERNEL32!EnterCriticalSection` at `0x180049b2e`
- `KERNEL32!EnterCriticalSection` at `0x1800497c3`
- `KERNEL32!EnterCriticalSection` at `0x180049803`
- `KERNEL32!EnterCriticalSection` at `0x1800498e6`
- `KERNEL32!EnterCriticalSection` at `0x180049962`
- `KERNEL32!EnterCriticalSection` at `0x180049ae3`
- `KERNEL32!EnterCriticalSection` at `0x180049b2e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180049c66`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180049c66`
- `GDI32!DeleteObject` at `0x180049be8`
- `GDI32!DeleteObject` at `0x180049cdf`
- `GDI32!DeleteObject` at `0x180049be8`
- `GDI32!DeleteObject` at `0x180049cdf`
- `USER32!DestroyIcon` at `0x180049d87`
- `USER32!DestroyIcon` at `0x180049d87`
- `USER32!UnregisterClassW` at `0x180049b6e`
- `USER32!UnregisterClassW` at `0x180049b6e`
- `iertutil!__imp_DSA_DeleteAllItems` at `0x180049cbf`
- `iertutil!__imp_DSA_DeleteAllItems` at `0x180049cbf`
- `iertutil!__imp_DSA_Destroy` at `0x180049cce`
- `iertutil!__imp_DSA_Destroy` at `0x180049cce`
- `iertutil!__imp_DSA_DestroyCallback` at `0x180049c0a`
- `iertutil!__imp_DSA_DestroyCallback` at `0x180049c4e`
- `iertutil!__imp_DSA_DestroyCallback` at `0x180049c0a`
- `iertutil!__imp_DSA_DestroyCallback` at `0x180049c4e`
- `iertutil!__imp_DPA_DestroyCallback` at `0x180049c2c`
- `iertutil!__imp_DPA_DestroyCallback` at `0x180049c2c`
- `iertutil!__imp_?IESetThreadRefTLSIndex@@YAXK@Z` at `0x180049bbe`
- `iertutil!__imp_?IESetThreadRefTLSIndex@@YAXK@Z` at `0x180049bbe`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180049dce`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180049dce`

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
    v5 = (HKEY)qword_18069E040[5 * (int)i];
    if ( v5 )
    {
      RegCloseKey(v5);
      qword_18069E040[5 * (int)i] = 0;
    }
  }
  if ( qword_18069EA38 )
  {
    CPolicyCache::`scalar deleting destructor'(qword_18069EA38, v3);
    qword_18069EA38 = 0;
  }
  TraceLoggingUnregister_EventUnregister(&dword_18069E818);
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
      UnregisterClassW(off_18059B180[k], v14);
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
    v11 = (void *)qword_1806A6168[4 * (int)m];
    if ( v11 )
      CoTaskMemFree(v11);
  }
  DeleteCriticalSection(&stru_1806A6550);
  if ( g_hActCtx != (HANDLE)-1LL )
  {
    ReleaseActCtx(g_hActCtx);
    g_hActCtx = (HANDLE)-1LL;
  }
  if ( qword_1806A6710 )
    qword_1806A6710 = (HMODULE)-1LL;
}

```

## disassembly

```asm
0x1800497a0  push    rbx
0x1800497a2  push    rbp
0x1800497a3  push    rsi
0x1800497a4  push    rdi
0x1800497a5  push    r12
0x1800497a7  push    r14
0x1800497a9  push    r15
0x1800497ab  sub     rsp, 20h
0x1800497af  lea     r14, g_csDll
0x1800497b6  mov     cs:?g_bDllTerminating@@3_NA, 1; bool g_bDllTerminating
0x1800497bd  mov     rcx, r14; lpCriticalSection
0x1800497c0  mov     rsi, rdx
0x1800497c3  call    cs:__imp_EnterCriticalSection
0x1800497ca  nop     dword ptr [rax+rax+00h]
0x1800497cf  mov     rcx, cs:?g_cdsaModuleInfoCache@@3V?$CDSA@U_tagModuleInfoCache@@@@A; hdsa
0x1800497d6  xor     ebp, ebp
0x1800497d8  test    rcx, rcx
0x1800497db  jnz     loc_180049C00
0x1800497e1  mov     rcx, r14; lpCriticalSection
0x1800497e4  call    cs:__imp_LeaveCriticalSection
0x1800497eb  nop     dword ptr [rax+rax+00h]
0x1800497f0  mov     rcx, cs:?s_dpaFTPCredentials@CDOHBindStatusCallback@CDocObjectHost@@1V?$CDPA@UFTPCredentials@CDOHBindStatusCallback@CDocObjectHost@@@@A; hdpa
0x1800497f7  test    rcx, rcx
0x1800497fa  jnz     loc_180049C22
0x180049800  mov     rcx, r14; lpCriticalSection
0x180049803  call    cs:__imp_EnterCriticalSection
0x18004980a  nop     dword ptr [rax+rax+00h]
0x18004980f  mov     rcx, cs:hdsa; hdsa
0x180049816  test    rcx, rcx
0x180049819  jnz     loc_180049C44
0x18004981f  mov     rcx, r14; lpCriticalSection
0x180049822  call    cs:__imp_LeaveCriticalSection
0x180049829  nop     dword ptr [rax+rax+00h]
0x18004982e  mov     ebx, ebp
0x180049830  lea     r12, __ImageBase
0x180049837  movsxd  rax, ebx
0x18004983a  lea     rdi, [rax+rax*4]
0x18004983e  mov     rcx, rva qword_18069E040[r12+rdi*8]; hKey
0x180049846  test    rcx, rcx
0x180049849  jnz     loc_180049C66
0x18004984f  inc     ebx
0x180049851  cmp     ebx, 7
0x180049854  jb      short loc_180049837
0x180049856  mov     rcx, cs:qword_18069EA38; this
0x18004985d  test    rcx, rcx
0x180049860  jnz     loc_180049C7F
0x180049866  lea     rcx, dword_18069E818
0x18004986d  call    TraceLoggingUnregister_EventUnregister
0x180049872  or      r15d, 0FFFFFFFFh
0x180049876  cmp     cs:g_tlsThreadRef, r15d
0x18004987d  jnz     loc_180049BBB
0x180049883  mov     ecx, cs:g_tlsOtherThreadsRef; dwTlsIndex
0x180049889  cmp     ecx, r15d
0x18004988c  jnz     loc_180049AC8
0x180049892  mov     ecx, cs:?_tlsIndex@TabThreadMinidumpState@@0KA; dwTlsIndex
0x180049898  cmp     ecx, r15d
0x18004989b  jz      short loc_1800498B0
0x18004989d  call    cs:__imp_TlsFree
0x1800498a4  nop     dword ptr [rax+rax+00h]
0x1800498a9  mov     cs:?_tlsIndex@TabThreadMinidumpState@@0KA, r15d; ulong TabThreadMinidumpState::_tlsIndex
0x1800498b0  lea     rcx, BERP_READINGVIEW_Context
0x1800498b7  call    McGenEventUnregister_EventUnregister
0x1800498bc  lea     rcx, BERP_IEFRAME2_Context
0x1800498c3  call    McGenEventUnregister_EventUnregister
0x1800498c8  lea     rcx, BERP_IEFRAME_Context
0x1800498cf  call    McGenEventUnregister_EventUnregister
0x1800498d4  lea     rcx, BERP_MSHTML_Context
0x1800498db  call    McGenEventUnregister_EventUnregister
0x1800498e0  mov     rcx, r14; lpCriticalSection
0x1800498e3  mov     rbx, rbp
0x1800498e6  call    cs:__imp_EnterCriticalSection
0x1800498ed  nop     dword ptr [rax+rax+00h]
0x1800498f2  mov     rdx, cs:?g_hFileStoreTimer@@3PEAXEA; Timer
0x1800498f9  test    rdx, rdx
0x1800498fc  jnz     loc_180049C90
0x180049902  mov     rax, cs:?g_dsaFileHandleStore@@3V?$CDSA@USTOREDFILEINFO@@@@A; CDSA<STOREDFILEINFO> g_dsaFileHandleStore
0x180049909  test    rax, rax
0x18004990c  jnz     loc_180049CAD
0x180049912  mov     rcx, r14; lpCriticalSection
0x180049915  call    cs:__imp_LeaveCriticalSection
0x18004991c  nop     dword ptr [rax+rax+00h]
0x180049921  test    rbx, rbx
0x180049924  jnz     loc_180049CBC
0x18004992a  mov     ebx, ebp
0x18004992c  movsxd  rdi, ebx
0x18004992f  mov     rcx, rva ?g_rghbmpFavIconBase@@3PAPEAUHBITMAP__@@A[r12+rdi*8]; ho
0x180049937  test    rcx, rcx
0x18004993a  jnz     loc_180049CDF
0x180049940  inc     ebx
0x180049942  cmp     ebx, 1Fh
0x180049945  jb      short loc_18004992C
0x180049947  test    rsi, rsi
0x18004994a  jz      loc_180049AE0
0x180049950  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180049956  cmp     ecx, r15d
0x180049959  jnz     loc_180049D2B
0x18004995f  mov     rcx, r14; lpCriticalSection
0x180049962  call    cs:__imp_EnterCriticalSection
0x180049969  nop     dword ptr [rax+rax+00h]
0x18004996e  mov     rcx, cs:g_hpalHalftone; ho
0x180049975  test    rcx, rcx
0x180049978  jnz     loc_180049BE8
0x18004997e  mov     rcx, cs:g_hMutexHistory; hObject
0x180049985  test    rcx, rcx
0x180049988  jnz     loc_180049D43
0x18004998e  mov     rcx, cs:g_hSemaphoreWindowRevoke; hObject
0x180049995  test    rcx, rcx
0x180049998  jnz     loc_180049D5B
0x18004999e  mov     rbx, cs:?g_pZoneIconNameCache@@3PEAU_ZONESICONNAMECACHE@@EA; _ZONESICONNAMECACHE * g_pZoneIconNameCache
0x1800499a5  test    rbx, rbx
0x1800499a8  jnz     loc_180049D73
0x1800499ae  mov     rcx, r14; lpCriticalSection
0x1800499b1  call    cs:__imp_LeaveCriticalSection
0x1800499b8  nop     dword ptr [rax+rax+00h]
0x1800499bd  mov     rcx, r14; lpCriticalSection
0x1800499c0  call    cs:__imp_DeleteCriticalSection
0x1800499c7  nop     dword ptr [rax+rax+00h]
0x1800499cc  lea     rcx, ?g_csThreadHooks@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800499d3  call    cs:__imp_DeleteCriticalSection
0x1800499da  nop     dword ptr [rax+rax+00h]
0x1800499df  lea     rcx, ?g_csThumbnail@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800499e6  call    cs:__imp_DeleteCriticalSection
0x1800499ed  nop     dword ptr [rax+rax+00h]
0x1800499f2  lea     rcx, ?g_csDownloadManager@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800499f9  call    cs:__imp_DeleteCriticalSection
0x180049a00  nop     dword ptr [rax+rax+00h]
0x180049a05  lea     rcx, ?g_csNewTabPageData@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180049a0c  call    cs:__imp_DeleteCriticalSection
0x180049a13  nop     dword ptr [rax+rax+00h]
0x180049a18  lea     rcx, ?g_csLocalRoamedTabTimer@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180049a1f  call    cs:__imp_DeleteCriticalSection
0x180049a26  nop     dword ptr [rax+rax+00h]
0x180049a2b  lea     rcx, ?g_csNamedWindowList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180049a32  call    cs:__imp_DeleteCriticalSection
0x180049a39  nop     dword ptr [rax+rax+00h]
0x180049a3e  lea     rcx, ?s_csInCallback@CAsyncStorage@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180049a45  call    cs:__imp_DeleteCriticalSection
0x180049a4c  nop     dword ptr [rax+rax+00h]
0x180049a51  mov     ebx, ebp
0x180049a53  movsxd  rax, ebx
0x180049a56  shl     rax, 5
0x180049a5a  mov     rcx, [rax+r12+6A6168h]; pv
0x180049a62  test    rcx, rcx
0x180049a65  jnz     loc_180049DCE
0x180049a6b  inc     ebx
0x180049a6d  cmp     ebx, 20h ; ' '
0x180049a70  jb      short loc_180049A53
0x180049a72  lea     rcx, stru_1806A6550; lpCriticalSection
0x180049a79  call    cs:__imp_DeleteCriticalSection
0x180049a80  nop     dword ptr [rax+rax+00h]
0x180049a85  mov     rcx, cs:g_hActCtx; hActCtx
0x180049a8c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180049a90  cmp     rcx, rbx
0x180049a93  jz      short loc_180049AA8
0x180049a95  call    cs:__imp_ReleaseActCtx
0x180049a9c  nop     dword ptr [rax+rax+00h]
0x180049aa1  mov     cs:g_hActCtx, rbx
0x180049aa8  cmp     cs:qword_1806A6710, rbp
0x180049aaf  jz      short loc_180049AB8
0x180049ab1  mov     cs:qword_1806A6710, rbx
0x180049ab8  add     rsp, 20h
0x180049abc  pop     r15
0x180049abe  pop     r14
0x180049ac0  pop     r12
0x180049ac2  pop     rdi
0x180049ac3  pop     rsi
0x180049ac4  pop     rbp
0x180049ac5  pop     rbx
0x180049ac6  retn
0x180049ac8  call    cs:__imp_TlsFree
0x180049acf  nop     dword ptr [rax+rax+00h]
0x180049ad4  mov     cs:g_tlsOtherThreadsRef, r15d
0x180049adb  jmp     loc_180049892
0x180049ae0  mov     rcx, r14; lpCriticalSection
0x180049ae3  call    cs:__imp_EnterCriticalSection
0x180049aea  nop     dword ptr [rax+rax+00h]
0x180049aef  mov     rcx, cs:?g_puhUrlHistory@@3PEAUIUrlHistoryPriv@@EA; IUrlHistoryPriv * g_puhUrlHistory
0x180049af6  test    rcx, rcx
0x180049af9  jz      short loc_180049B07
0x180049afb  mov     rax, [rcx]
0x180049afe  mov     rax, [rax+10h]
0x180049b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b07  mov     rcx, r14; lpCriticalSection
0x180049b0a  call    cs:__imp_LeaveCriticalSection
0x180049b11  nop     dword ptr [rax+rax+00h]
0x180049b16  call    ?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z; ATL::AtlModuleTerm(ATL::_ATL_MODULE *)
0x180049b1b  mov     rcx, cs:?g_pExtensionRecorder@@3PEAVCExtensionRecorder@@EA; this
0x180049b22  test    rcx, rcx
0x180049b25  jnz     loc_180049CF8
0x180049b2b  mov     rcx, r14; lpCriticalSection
0x180049b2e  call    cs:__imp_EnterCriticalSection
0x180049b35  nop     dword ptr [rax+rax+00h]
0x180049b3a  mov     rcx, cs:?g_pszProtectedModeBuffer@@3PEAGEA; hMem
0x180049b41  test    rcx, rcx
0x180049b44  jnz     loc_180049D09
0x180049b4a  mov     rcx, r14; lpCriticalSection
0x180049b4d  call    cs:__imp_LeaveCriticalSection
0x180049b54  nop     dword ptr [rax+rax+00h]
0x180049b59  mov     rdi, cs:g_hinst
0x180049b60  mov     rbx, rbp
0x180049b63  mov     rcx, ds:rva off_18059B180[r12+rbx*8]; lpClassName
0x180049b6b  mov     rdx, rdi; hInstance
0x180049b6e  call    cs:__imp_UnregisterClassW
0x180049b75  nop     dword ptr [rax+rax+00h]
0x180049b7a  inc     rbx
0x180049b7d  cmp     rbx, 37h ; '7'
0x180049b81  jnz     short loc_180049B63
0x180049b83  mov     rcx, cs:g_hmodWininet; hLibModule
0x180049b8a  test    rcx, rcx
0x180049b8d  jnz     loc_180049D1A
0x180049b93  mov     rcx, cs:g_hInstMshtmlMui; hLibModule
0x180049b9a  test    rcx, rcx
0x180049b9d  jz      loc_180049950
0x180049ba3  call    cs:__imp_FreeLibrary
0x180049baa  nop     dword ptr [rax+rax+00h]
0x180049baf  mov     cs:g_hInstMshtmlMui, rbp
0x180049bb6  jmp     loc_180049950
0x180049bbb  mov     ecx, r15d
0x180049bbe  call    cs:__imp_?IESetThreadRefTLSIndex@@YAXK@Z; IESetThreadRefTLSIndex(ulong)
0x180049bc5  nop     dword ptr [rax+rax+00h]
0x180049bca  mov     ecx, cs:g_tlsThreadRef; dwTlsIndex
0x180049bd0  call    cs:__imp_TlsFree
0x180049bd7  nop     dword ptr [rax+rax+00h]
0x180049bdc  mov     cs:g_tlsThreadRef, r15d
0x180049be3  jmp     loc_180049883
0x180049be8  call    cs:__imp_DeleteObject
0x180049bef  nop     dword ptr [rax+rax+00h]
0x180049bf4  mov     cs:g_hpalHalftone, rbp
0x180049bfb  jmp     loc_18004997E
0x180049c00  xor     r8d, r8d; pData
0x180049c03  lea     rdx, ?ModuleCacheEntryDelete@@YAHPEAU_tagModuleInfoCache@@PEAX@Z; pfnCB
0x180049c0a  call    cs:__imp_DSA_DestroyCallback
0x180049c11  nop     dword ptr [rax+rax+00h]
0x180049c16  mov     cs:?g_cdsaModuleInfoCache@@3V?$CDSA@U_tagModuleInfoCache@@@@A, rbp; CDSA<_tagModuleInfoCache> g_cdsaModuleInfoCache
0x180049c1d  jmp     loc_1800497E1
0x180049c22  xor     r8d, r8d; pData
0x180049c25  lea     rdx, ?s_FTPCredentialsDPAFree@CDOHBindStatusCallback@CDocObjectHost@@KAHPEAUFTPCredentials@12@PEAX@Z; pfnCB
0x180049c2c  call    cs:__imp_DPA_DestroyCallback
0x180049c33  nop     dword ptr [rax+rax+00h]
0x180049c38  mov     cs:?s_dpaFTPCredentials@CDOHBindStatusCallback@CDocObjectHost@@1V?$CDPA@UFTPCredentials@CDOHBindStatusCallback@CDocObjectHost@@@@A, rbp; CDPA<CDocObjectHost::CDOHBindStatusCallback::FTPCredentials> CDocObjectHost::CDOHBindStatusCallback::s_dpaFTPCredentials
0x180049c3f  jmp     loc_180049800
0x180049c44  xor     r8d, r8d; pData
0x180049c47  lea     rdx, ?CDefaultOpenDataDSA_DestroyCallback@@YAHPEAUDefaultOpenData@@PEAX@Z; pfnCB
0x180049c4e  call    cs:__imp_DSA_DestroyCallback
0x180049c55  nop     dword ptr [rax+rax+00h]
0x180049c5a  mov     cs:hdsa, rbp
0x180049c61  jmp     loc_18004981F
0x180049c66  call    cs:__imp_RegCloseKey
0x180049c6d  nop     dword ptr [rax+rax+00h]
0x180049c72  mov     rva qword_18069E040[r12+rdi*8], rbp
0x180049c7a  jmp     loc_18004984F
0x180049c7f  call    ??_GCPolicyCache@@QEAAPEAXI@Z; CPolicyCache::`scalar deleting destructor'(uint)
0x180049c84  mov     cs:qword_18069EA38, rbp
0x180049c8b  jmp     loc_180049866
0x180049c90  xor     r8d, r8d; CompletionEvent
0x180049c93  xor     ecx, ecx; TimerQueue
0x180049c95  call    cs:__imp_DeleteTimerQueueTimer
0x180049c9c  nop     dword ptr [rax+rax+00h]
0x180049ca1  mov     cs:?g_hFileStoreTimer@@3PEAXEA, rbp; void * g_hFileStoreTimer
0x180049ca8  jmp     loc_180049902
0x180049cad  mov     rbx, rax
0x180049cb0  mov     cs:?g_dsaFileHandleStore@@3V?$CDSA@USTOREDFILEINFO@@@@A, rbp; CDSA<STOREDFILEINFO> g_dsaFileHandleStore
0x180049cb7  jmp     loc_180049912
0x180049cbc  mov     rcx, rbx; hdsa
0x180049cbf  call    cs:__imp_DSA_DeleteAllItems
0x180049cc6  nop     dword ptr [rax+rax+00h]
0x180049ccb  mov     rcx, rbx; hdsa
0x180049cce  call    cs:__imp_DSA_Destroy
0x180049cd5  nop     dword ptr [rax+rax+00h]
0x180049cda  jmp     loc_18004992A
0x180049cdf  call    cs:__imp_DeleteObject
0x180049ce6  nop     dword ptr [rax+rax+00h]
0x180049ceb  mov     rva ?g_rghbmpFavIconBase@@3PAPEAUHBITMAP__@@A[r12+rdi*8], rbp; HBITMAP__ * near * g_rghbmpFavIconBase ...
0x180049cf3  jmp     loc_180049940
0x180049cf8  call    ??_GCExtensionRecorder@@QEAAPEAXI@Z; CExtensionRecorder::`scalar deleting destructor'(uint)
0x180049cfd  mov     cs:?g_pExtensionRecorder@@3PEAVCExtensionRecorder@@EA, rbp; CExtensionRecorder * g_pExtensionRecorder
0x180049d04  jmp     loc_180049B2B
0x180049d09  call    cs:__imp_LocalFree
0x180049d10  nop     dword ptr [rax+rax+00h]
0x180049d15  jmp     loc_180049B4A
0x180049d1a  call    cs:__imp_FreeLibrary
0x180049d21  nop     dword ptr [rax+rax+00h]
0x180049d26  jmp     loc_180049B93
0x180049d2b  call    cs:__imp_TlsFree
0x180049d32  nop     dword ptr [rax+rax+00h]
0x180049d37  mov     cs:dwTlsIndex, r15d
0x180049d3e  jmp     loc_18004995F
0x180049d43  call    cs:__imp_CloseHandle
0x180049d4a  nop     dword ptr [rax+rax+00h]
0x180049d4f  mov     cs:g_hMutexHistory, rbp
0x180049d56  jmp     loc_18004998E
0x180049d5b  call    cs:__imp_CloseHandle
0x180049d62  nop     dword ptr [rax+rax+00h]
0x180049d67  mov     cs:g_hSemaphoreWindowRevoke, rbp
0x180049d6e  jmp     loc_18004999E
0x180049d73  mov     eax, cs:?g_dwZoneCount@@3KA; ulong g_dwZoneCount
0x180049d79  mov     edi, ebp
0x180049d7b  test    eax, eax
0x180049d7d  jz      short loc_180049DAD
0x180049d7f  mov     rcx, [rbx]; hIcon
  ... truncated ...
```

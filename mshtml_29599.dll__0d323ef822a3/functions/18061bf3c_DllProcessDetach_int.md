# DllProcessDetach(int)

- ea: `0x18061bf3c`
- end: `0x18061c32e`
- name: `?DllProcessDetach@@YAXH@Z`
- size: `1010`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18061ba20`
- `0x180771b84`

## callees

- `0x1800019d8`
- `0x1801c0b08`
- `0x1802a05ac`
- `0x18061be28`
- `0x18061bf3c`
- `0x18068046c`
- `0x180705750`
- `0x18071dea8`
- `0x180759cb0`
- `0x180759edc`
- `0x18077036c`
- `0x180771b58`
- `0x1807ae7e4`
- `0x1807b1a80`
- `0x1807cc8f4`
- `0x180b4787c`
- `0x180f1f6e0`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!FlushViewOfFile` at `0x18061c0db`
- `KERNEL32!FlushViewOfFile` at `0x18061c0db`
- `KERNEL32!FindAtomW` at `0x18061c315`
- `KERNEL32!FindAtomW` at `0x18061c315`
- `KERNEL32!DeleteAtom` at `0x18061c327`
- `KERNEL32!UnmapViewOfFile` at `0x18061c0e8`
- `KERNEL32!UnmapViewOfFile` at `0x18061c25d`
- `KERNEL32!UnmapViewOfFile` at `0x18061c0e8`
- `KERNEL32!UnmapViewOfFile` at `0x18061c25d`
- `KERNEL32!TlsFree` at `0x18061c22f`
- `KERNEL32!TlsFree` at `0x18061c245`
- `KERNEL32!TlsFree` at `0x18061c2ec`
- `KERNEL32!TlsFree` at `0x18061c302`
- `KERNEL32!TlsFree` at `0x18061c22f`
- `KERNEL32!TlsFree` at `0x18061c245`
- `KERNEL32!TlsFree` at `0x18061c2ec`
- `KERNEL32!TlsFree` at `0x18061c302`
- `KERNEL32!FlsFree` at `0x18061c219`
- `KERNEL32!FlsFree` at `0x18061c219`
- `KERNEL32!DeleteCriticalSection` at `0x18061c00d`
- `KERNEL32!DeleteCriticalSection` at `0x18061c01a`
- `KERNEL32!DeleteCriticalSection` at `0x18061c027`
- `KERNEL32!DeleteCriticalSection` at `0x18061c0c4`
- `KERNEL32!DeleteCriticalSection` at `0x18061c185`
- `KERNEL32!DeleteCriticalSection` at `0x18061c1e3`
- `KERNEL32!DeleteCriticalSection` at `0x18061c1ff`
- `KERNEL32!DeleteCriticalSection` at `0x18061c00d`
- `KERNEL32!DeleteCriticalSection` at `0x18061c01a`
- `KERNEL32!DeleteCriticalSection` at `0x18061c027`
- `KERNEL32!DeleteCriticalSection` at `0x18061c0c4`
- `KERNEL32!DeleteCriticalSection` at `0x18061c185`
- `KERNEL32!DeleteCriticalSection` at `0x18061c1e3`
- `KERNEL32!DeleteCriticalSection` at `0x18061c1ff`
- `KERNEL32!LeaveCriticalSection` at `0x18061c0af`
- `KERNEL32!LeaveCriticalSection` at `0x18061c17c`
- `KERNEL32!LeaveCriticalSection` at `0x18061c2e0`
- `KERNEL32!LeaveCriticalSection` at `0x18061c0af`
- `KERNEL32!LeaveCriticalSection` at `0x18061c17c`
- `KERNEL32!LeaveCriticalSection` at `0x18061c2e0`
- `KERNEL32!EnterCriticalSection` at `0x18061c083`
- `KERNEL32!EnterCriticalSection` at `0x18061c149`
- `KERNEL32!EnterCriticalSection` at `0x18061c2b8`
- `KERNEL32!EnterCriticalSection` at `0x18061c083`
- `KERNEL32!EnterCriticalSection` at `0x18061c149`
- `KERNEL32!EnterCriticalSection` at `0x18061c2b8`
- `KERNEL32!CloseHandle` at `0x18061bfed`
- `KERNEL32!CloseHandle` at `0x18061c0fa`
- `KERNEL32!CloseHandle` at `0x18061c26f`
- `KERNEL32!CloseHandle` at `0x18061bfed`
- `KERNEL32!CloseHandle` at `0x18061c0fa`
- `KERNEL32!CloseHandle` at `0x18061c26f`
- `ADVAPI32!CryptReleaseContext` at `0x18061c2cc`
- `ADVAPI32!CryptReleaseContext` at `0x18061c2cc`
- `urlmon!__imp_TrackingProtectionUninitialize` at `0x18061c12d`
- `urlmon!__imp_TrackingProtectionUninitialize` at `0x18061c12d`
- `OLEAUT32!__imp_SysFreeString` at `0x18061c1c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18061c1c7`

## pseudocode

```c
void __fastcall DllProcessDetach(int a1)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v3; // rdi
  CLangUtil *v4; // rax
  void *v5; // r8
  void *v6; // r8
  __int64 v7; // rcx
  void *v8; // r8
  CWebWorkerThreadPool *v9; // rcx
  void *v10; // r8
  struct ATL::_ATL_MODULE *v11; // rcx
  ATOM AtomW; // ax

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  g_processLifetimeActivity = 2;
  v3 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  LODWORD(ThreadLocalStoragePointer) = dword_181559C88;
  *(_BYTE *)(v3 + 33) = 1;
  if ( (unsigned int)ThreadLocalStoragePointer > 5 && (unsigned __int8)tlgKeywordOn(&dword_181559C88, 0x400000000002LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_181559C88,
      &unk_1815187CE,
      &xmmword_18158F768,
      0);
  *(_BYTE *)(v3 + 33) = 0;
  TraceLoggingUnregister_EventUnregister(&dword_181559C88);
  if ( g_pts )
    DllThreadEmergencyDetach(a1);
  v4 = lang();
  CLangUtil::Shutdown(v4);
  if ( CStorageQuotaHelper::s_hQuotaMutex )
    CloseHandle(CStorageQuotaHelper::s_hQuotaMutex);
  CVirtualTabStorage::GlobalUnInit();
  if ( CPersistUserData::s_fInitCS )
  {
    CPersistUserData::DeleteSiteTable();
    DeleteCriticalSection(&CPersistUserData::s_csCacheUrlPrefix);
    DeleteCriticalSection(&CPersistUserData::s_csCacheContainer);
    DeleteCriticalSection(&CPersistUserData::s_csSiteTable);
    CPersistUserData::s_fInitCS = 0;
  }
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)g_tszModuleFileName, v5);
  DeinitInputAcceptLabels();
  if ( CInput::s_pchBrowseButtonCaption )
  {
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, CInput::s_pchBrowseButtonCaption, v6);
    CInput::s_pchBrowseButtonCaption = 0;
  }
  CFontCache::DeInit((CFontCache *)&g_FontCache, a1 != 0);
  EnterCriticalSection(&ColorPaletteInternal::s_csColorPaletteLock);
  if ( qword_18158CAB0 )
  {
    ColorPalette::Release(qword_18158CAB0);
    qword_18158CAB0 = 0;
  }
  byte_18158CAB8 = 0;
  LeaveCriticalSection(&ColorPaletteInternal::s_csColorPaletteLock);
  if ( CRtfToHtmlConverter::_fCSInited )
    DeleteCriticalSection(&CRtfToHtmlConverter::_cs);
  if ( lpBaseAddress )
  {
    FlushViewOfFile(lpBaseAddress, 0xBFE0u);
    UnmapViewOfFile(lpBaseAddress);
  }
  if ( hObject )
    CloseHandle(hObject);
  v7 = qword_181591A98;
  lpBaseAddress = 0;
  hObject = 0;
  if ( qword_181591A98 )
  {
    qword_181591A98 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  TrackingProtectionUninitialize();
  if ( _InterlockedExchange(&CWebWorkerThreadPool::s_fInitialized, 0) )
  {
    EnterCriticalSection(&CWebWorkerThreadPool::s_csWebWorkerThread);
    v9 = CWebWorkerThreadPool::s_pWebWorkerThreadPool;
    if ( CWebWorkerThreadPool::s_pWebWorkerThreadPool )
    {
      if ( a1 )
        *((_QWORD *)CWebWorkerThreadPool::s_pWebWorkerThreadPool + 10) = 0;
      if ( v9 )
        CWebWorkerThreadPool::`vector deleting destructor'(v9, 1u);
      CWebWorkerThreadPool::s_pWebWorkerThreadPool = 0;
    }
    LeaveCriticalSection(&CWebWorkerThreadPool::s_csWebWorkerThread);
    DeleteCriticalSection(&CWebWorkerThreadPool::s_csWebWorkerThread);
  }
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, qword_181591D40, v8);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, qword_181591D38, v10);
  ATL::AtlModuleTerm(v11);
  CGetBlockFmtCommand::Deinit();
  if ( CComposeSettingsCommand::s_bstrLastComposeSettings )
    SysFreeString(CComposeSettingsCommand::s_bstrLastComposeSettings);
  CComposeSettingsCommand::s_bstrLastComposeSettings = 0;
  if ( CComposeSettingsCommand::s_fCSInited )
  {
    DeleteCriticalSection(&CComposeSettingsCommand::s_csLastComposeSettings);
    CComposeSettingsCommand::s_fCSInited = 0;
  }
  if ( byte_181592228 )
  {
    DeleteCriticalSection(&g_csActiveIMM);
    byte_181592228 = 0;
  }
  if ( g_dwFls != -1 )
  {
    FlsFree(g_dwFls);
    g_dwFls = -1;
  }
  if ( g_dwTlsTearoffThunk != -1 )
  {
    TlsFree(g_dwTlsTearoffThunk);
    g_dwTlsTearoffThunk = -1;
  }
  if ( g_dwTlsFlsCallback != -1 )
  {
    TlsFree(g_dwTlsFlsCallback);
    g_dwTlsFlsCallback = -1;
  }
  if ( g_pHtmPerfCtl )
    UnmapViewOfFile(g_pHtmPerfCtl);
  if ( g_hMapHtmPerfCtl )
    CloseHandle(g_hMapHtmPerfCtl);
  McGenEventUnregister_EventUnregister(&BERP_READINGVIEW_Context);
  McGenEventUnregister_EventUnregister(&BERP_JSDUMPHEAP_Context);
  McGenEventUnregister_EventUnregister(&BERP_MSHTML_Context);
  McGenEventUnregister_EventUnregister(&BERP_IE_Context);
  McGenEventUnregister_EventUnregister(&BERP_IEFRAME2_Context);
  EnterCriticalSection(&g_gcsXSSCryptProv);
  if ( g_hXSSCryptProv )
  {
    CryptReleaseContext(g_hXSSCryptProv, 0);
    g_hXSSCryptProv = 0;
  }
  LeaveCriticalSection(&g_gcsXSSCryptProv);
  TlsFree(dwTlsIndex);
  dwTlsIndex = -1;
  if ( CDXRenderLockBase::s_TLSIndex != -1 )
  {
    TlsFree(CDXRenderLockBase::s_TLSIndex);
    CDXRenderLockBase::s_TLSIndex = -1;
  }
  AtomW = FindAtomW(L"{4653C0A4-2B2D-48DE-AB80-93910A28F900}");
  DeleteAtom(AtomW);
}

```

## disassembly

```asm
0x18061bf3c  push    rbx
0x18061bf3e  push    rsi
0x18061bf3f  push    rdi
0x18061bf40  push    r14
0x18061bf42  sub     rsp, 28h
0x18061bf46  mov     rax, gs:58h
0x18061bf4f  xor     esi, esi
0x18061bf51  mov     edx, cs:_tls_index
0x18061bf57  mov     ebx, ecx
0x18061bf59  mov     r14d, 21h ; '!'
0x18061bf5f  mov     cs:?g_processLifetimeActivity@@3V?$TraceLoggingActivity@$1?g_hAsimovProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAC@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, 2; TraceLoggingActivity<&_tlgProvider_t const * const g_hAsimovProvider,70368744177666,5,_TlgReflectorTag_Param0IsHProvider> g_processLifetimeActivity
0x18061bf69  mov     rdi, [rax+rdx*8]
0x18061bf6d  mov     eax, cs:dword_181559C88
0x18061bf73  mov     byte ptr [rdi+r14], 1
0x18061bf78  cmp     eax, 5
0x18061bf7b  jbe     short loc_18061BFB4
0x18061bf7d  mov     rdx, 400000000002h
0x18061bf87  lea     rcx, dword_181559C88
0x18061bf8e  call    _tlgKeywordOn
0x18061bf93  test    al, al
0x18061bf95  jz      short loc_18061BFB4
0x18061bf97  xor     r9d, r9d
0x18061bf9a  lea     r8, xmmword_18158F768
0x18061bfa1  lea     rdx, unk_1815187CE
0x18061bfa8  lea     rcx, dword_181559C88
0x18061bfaf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18061bfb4  lea     rcx, dword_181559C88
0x18061bfbb  mov     [rdi+r14], sil
0x18061bfbf  call    TraceLoggingUnregister_EventUnregister
0x18061bfc4  cmp     cs:?g_pts@@3PEAUTHREADSTATE@@EA, rsi; THREADSTATE * g_pts
0x18061bfcb  jz      short loc_18061BFD4
0x18061bfcd  mov     ecx, ebx; int
0x18061bfcf  call    ?DllThreadEmergencyDetach@@YAXH@Z; DllThreadEmergencyDetach(int)
0x18061bfd4  call    ?lang@@YAAEAVCLangUtil@@XZ; lang(void)
0x18061bfd9  mov     rcx, rax; this
0x18061bfdc  call    ?Shutdown@CLangUtil@@QEAAXXZ; CLangUtil::Shutdown(void)
0x18061bfe1  mov     rcx, cs:?s_hQuotaMutex@CStorageQuotaHelper@@0PEAXEA; hObject
0x18061bfe8  test    rcx, rcx
0x18061bfeb  jz      short loc_18061BFF3
0x18061bfed  call    cs:__imp_CloseHandle
0x18061bff3  call    ?GlobalUnInit@CVirtualTabStorage@@SAXXZ; CVirtualTabStorage::GlobalUnInit(void)
0x18061bff8  cmp     cs:?s_fInitCS@CPersistUserData@@0_NA, sil; bool CPersistUserData::s_fInitCS
0x18061bfff  jz      short loc_18061C034
0x18061c001  call    ?DeleteSiteTable@CPersistUserData@@CAJXZ; CPersistUserData::DeleteSiteTable(void)
0x18061c006  lea     rcx, ?s_csCacheUrlPrefix@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18061c00d  call    cs:__imp_DeleteCriticalSection
0x18061c013  lea     rcx, ?s_csCacheContainer@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18061c01a  call    cs:__imp_DeleteCriticalSection
0x18061c020  lea     rcx, ?s_csSiteTable@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18061c027  call    cs:__imp_DeleteCriticalSection
0x18061c02d  mov     cs:?s_fInitCS@CPersistUserData@@0_NA, sil; bool CPersistUserData::s_fInitCS
0x18061c034  mov     rdx, cs:?g_tszModuleFileName@@3PEAGEA; void *
0x18061c03b  mov     rcx, cs:g_hProcessHeap; this
0x18061c042  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18061c047  call    ?DeinitInputAcceptLabels@@YAXXZ; DeinitInputAcceptLabels(void)
0x18061c04c  mov     rdx, cs:?s_pchBrowseButtonCaption@CInput@@0PEAGEA; void *
0x18061c053  test    rdx, rdx
0x18061c056  jz      short loc_18061C06B
0x18061c058  mov     rcx, cs:g_hProcessHeap; this
0x18061c05f  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18061c064  mov     cs:?s_pchBrowseButtonCaption@CInput@@0PEAGEA, rsi; ushort * CInput::s_pchBrowseButtonCaption
0x18061c06b  test    ebx, ebx
0x18061c06d  lea     rcx, ?g_FontCache@@3VCFontCache@@A; this
0x18061c074  setnz   dl; bool
0x18061c077  call    ?DeInit@CFontCache@@QEAAX_N@Z; CFontCache::DeInit(bool)
0x18061c07c  lea     rcx, ?s_csColorPaletteLock@ColorPaletteInternal@@2VCGlobalCriticalSection@@A; lpCriticalSection
0x18061c083  call    cs:__imp_EnterCriticalSection
0x18061c089  mov     rcx, cs:qword_18158CAB0; this
0x18061c090  test    rcx, rcx
0x18061c093  jz      short loc_18061C0A1
0x18061c095  call    ?Release@ColorPalette@@QEAAXXZ; ColorPalette::Release(void)
0x18061c09a  mov     cs:qword_18158CAB0, rsi
0x18061c0a1  lea     rcx, ?s_csColorPaletteLock@ColorPaletteInternal@@2VCGlobalCriticalSection@@A; lpCriticalSection
0x18061c0a8  mov     cs:byte_18158CAB8, sil
0x18061c0af  call    cs:__imp_LeaveCriticalSection
0x18061c0b5  cmp     cs:?_fCSInited@CRtfToHtmlConverter@@0HA, esi; int CRtfToHtmlConverter::_fCSInited
0x18061c0bb  jz      short loc_18061C0CA
0x18061c0bd  lea     rcx, ?_cs@CRtfToHtmlConverter@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18061c0c4  call    cs:__imp_DeleteCriticalSection
0x18061c0ca  mov     rcx, cs:lpBaseAddress; lpBaseAddress
0x18061c0d1  test    rcx, rcx
0x18061c0d4  jz      short loc_18061C0EE
0x18061c0d6  mov     edx, 0BFE0h; dwNumberOfBytesToFlush
0x18061c0db  call    cs:__imp_FlushViewOfFile
0x18061c0e1  mov     rcx, cs:lpBaseAddress; lpBaseAddress
0x18061c0e8  call    cs:__imp_UnmapViewOfFile
0x18061c0ee  mov     rcx, cs:hObject; hObject
0x18061c0f5  test    rcx, rcx
0x18061c0f8  jz      short loc_18061C100
0x18061c0fa  call    cs:__imp_CloseHandle
0x18061c100  mov     rcx, cs:qword_181591A98
0x18061c107  mov     cs:lpBaseAddress, rsi
0x18061c10e  mov     cs:hObject, rsi
0x18061c115  test    rcx, rcx
0x18061c118  jz      short loc_18061C12D
0x18061c11a  mov     cs:qword_181591A98, rsi
0x18061c121  mov     rax, [rcx]
0x18061c124  mov     rax, [rax+10h]
0x18061c128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18061c12d  call    cs:__imp_TrackingProtectionUninitialize
0x18061c133  mov     eax, esi
0x18061c135  xchg    eax, cs:?s_fInitialized@CWebWorkerThreadPool@@1HA; int CWebWorkerThreadPool::s_fInitialized
0x18061c13b  test    eax, eax
0x18061c13d  jz      short loc_18061C18B
0x18061c13f  lea     rdi, ?s_csWebWorkerThread@CWebWorkerThreadPool@@1U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CWebWorkerThreadPool::s_csWebWorkerThread
0x18061c146  mov     rcx, rdi; lpCriticalSection
0x18061c149  call    cs:__imp_EnterCriticalSection
0x18061c14f  mov     rcx, cs:?s_pWebWorkerThreadPool@CWebWorkerThreadPool@@1PEAV1@EA; this
0x18061c156  test    rcx, rcx
0x18061c159  jz      short loc_18061C179
0x18061c15b  test    ebx, ebx
0x18061c15d  jz      short loc_18061C163
0x18061c15f  mov     [rcx+50h], rsi
0x18061c163  test    rcx, rcx
0x18061c166  jz      short loc_18061C172
0x18061c168  mov     edx, 1; unsigned int
0x18061c16d  call    ??_ECWebWorkerThreadPool@@MEAAPEAXI@Z; CWebWorkerThreadPool::`vector deleting destructor'(uint)
0x18061c172  mov     cs:?s_pWebWorkerThreadPool@CWebWorkerThreadPool@@1PEAV1@EA, rsi; CWebWorkerThreadPool * CWebWorkerThreadPool::s_pWebWorkerThreadPool
0x18061c179  mov     rcx, rdi; lpCriticalSection
0x18061c17c  call    cs:__imp_LeaveCriticalSection
0x18061c182  mov     rcx, rdi; lpCriticalSection
0x18061c185  call    cs:__imp_DeleteCriticalSection
0x18061c18b  mov     rdx, cs:qword_181591D40; void *
0x18061c192  mov     rcx, cs:g_hProcessHeap; this
0x18061c199  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18061c19e  mov     rdx, cs:qword_181591D38; void *
0x18061c1a5  mov     rcx, cs:g_hProcessHeap; this
0x18061c1ac  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18061c1b1  call    ?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z; ATL::AtlModuleTerm(ATL::_ATL_MODULE *)
0x18061c1b6  call    ?Deinit@CGetBlockFmtCommand@@SAXXZ; CGetBlockFmtCommand::Deinit(void)
0x18061c1bb  mov     rcx, cs:?s_bstrLastComposeSettings@CComposeSettingsCommand@@1PEAGEA; bstrString
0x18061c1c2  test    rcx, rcx
0x18061c1c5  jz      short loc_18061C1CD
0x18061c1c7  call    cs:__imp_SysFreeString
0x18061c1cd  cmp     cs:?s_fCSInited@CComposeSettingsCommand@@1HA, esi; int CComposeSettingsCommand::s_fCSInited
0x18061c1d3  mov     cs:?s_bstrLastComposeSettings@CComposeSettingsCommand@@1PEAGEA, rsi; ushort * CComposeSettingsCommand::s_bstrLastComposeSettings
0x18061c1da  jz      short loc_18061C1EF
0x18061c1dc  lea     rcx, ?s_csLastComposeSettings@CComposeSettingsCommand@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18061c1e3  call    cs:__imp_DeleteCriticalSection
0x18061c1e9  mov     cs:?s_fCSInited@CComposeSettingsCommand@@1HA, esi; int CComposeSettingsCommand::s_fCSInited
0x18061c1ef  cmp     cs:byte_181592228, sil
0x18061c1f6  jz      short loc_18061C20C
0x18061c1f8  lea     rcx, ?g_csActiveIMM@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18061c1ff  call    cs:__imp_DeleteCriticalSection
0x18061c205  mov     cs:byte_181592228, sil
0x18061c20c  mov     ecx, cs:?g_dwFls@@3KA; dwFlsIndex
0x18061c212  or      ebx, 0FFFFFFFFh
0x18061c215  cmp     ecx, ebx
0x18061c217  jz      short loc_18061C225
0x18061c219  call    cs:__imp_FlsFree
0x18061c21f  mov     cs:?g_dwFls@@3KA, ebx; ulong g_dwFls
0x18061c225  mov     ecx, cs:g_dwTlsTearoffThunk; dwTlsIndex
0x18061c22b  cmp     ecx, ebx
0x18061c22d  jz      short loc_18061C23B
0x18061c22f  call    cs:__imp_TlsFree
0x18061c235  mov     cs:g_dwTlsTearoffThunk, ebx
0x18061c23b  mov     ecx, cs:?g_dwTlsFlsCallback@@3KA; dwTlsIndex
0x18061c241  cmp     ecx, ebx
0x18061c243  jz      short loc_18061C251
0x18061c245  call    cs:__imp_TlsFree
0x18061c24b  mov     cs:?g_dwTlsFlsCallback@@3KA, ebx; ulong g_dwTlsFlsCallback
0x18061c251  mov     rcx, cs:?g_pHtmPerfCtl@@3PEAUHTMPERFCTL@@EA; lpBaseAddress
0x18061c258  test    rcx, rcx
0x18061c25b  jz      short loc_18061C263
0x18061c25d  call    cs:__imp_UnmapViewOfFile
0x18061c263  mov     rcx, cs:?g_hMapHtmPerfCtl@@3PEAXEA; hObject
0x18061c26a  test    rcx, rcx
0x18061c26d  jz      short loc_18061C275
0x18061c26f  call    cs:__imp_CloseHandle
0x18061c275  lea     rcx, BERP_READINGVIEW_Context
0x18061c27c  call    McGenEventUnregister_EventUnregister
0x18061c281  lea     rcx, BERP_JSDUMPHEAP_Context
0x18061c288  call    McGenEventUnregister_EventUnregister
0x18061c28d  lea     rcx, BERP_MSHTML_Context
0x18061c294  call    McGenEventUnregister_EventUnregister
0x18061c299  lea     rcx, BERP_IE_Context
0x18061c2a0  call    McGenEventUnregister_EventUnregister
0x18061c2a5  lea     rcx, BERP_IEFRAME2_Context
0x18061c2ac  call    McGenEventUnregister_EventUnregister
0x18061c2b1  lea     rcx, ?g_gcsXSSCryptProv@@3VCGlobalCriticalSection@@A; lpCriticalSection
0x18061c2b8  call    cs:__imp_EnterCriticalSection
0x18061c2be  mov     rcx, cs:?g_hXSSCryptProv@@3_KA; hProv
0x18061c2c5  test    rcx, rcx
0x18061c2c8  jz      short loc_18061C2D9
0x18061c2ca  xor     edx, edx; dwFlags
0x18061c2cc  call    cs:__imp_CryptReleaseContext
0x18061c2d2  mov     cs:?g_hXSSCryptProv@@3_KA, rsi; unsigned __int64 g_hXSSCryptProv
0x18061c2d9  lea     rcx, ?g_gcsXSSCryptProv@@3VCGlobalCriticalSection@@A; lpCriticalSection
0x18061c2e0  call    cs:__imp_LeaveCriticalSection
0x18061c2e6  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18061c2ec  call    cs:__imp_TlsFree
0x18061c2f2  mov     ecx, cs:?s_TLSIndex@CDXRenderLockBase@@0KA; dwTlsIndex
0x18061c2f8  mov     cs:dwTlsIndex, ebx
0x18061c2fe  cmp     ecx, ebx
0x18061c300  jz      short loc_18061C30E
0x18061c302  call    cs:__imp_TlsFree
0x18061c308  mov     cs:?s_TLSIndex@CDXRenderLockBase@@0KA, ebx; ulong CDXRenderLockBase::s_TLSIndex
0x18061c30e  lea     rcx, a4653c0a42b2d48; "{4653C0A4-2B2D-48DE-AB80-93910A28F900}"
0x18061c315  call    cs:__imp_FindAtomW
0x18061c31b  movzx   ecx, ax
0x18061c31e  add     rsp, 28h
0x18061c322  pop     r14
0x18061c324  pop     rdi
0x18061c325  pop     rsi
0x18061c326  pop     rbx
0x18061c327  jmp     cs:__imp_DeleteAtom
```

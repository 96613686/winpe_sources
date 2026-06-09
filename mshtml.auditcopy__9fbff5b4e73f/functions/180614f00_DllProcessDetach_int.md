# DllProcessDetach(int)

- ea: `0x180614f00`
- end: `0x1806152d4`
- name: `?DllProcessDetach@@YAXH@Z`
- size: `980`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180614934`
- `0x18077c3a0`

## callees

- `0x1800019e0`
- `0x18005e684`
- `0x180359018`
- `0x180614dc8`
- `0x180614f00`
- `0x18067f594`
- `0x18070ad78`
- `0x180725b14`
- `0x1807618a4`
- `0x180762f20`
- `0x18077c370`
- `0x1807bc2c8`
- `0x1807bd5f8`
- `0x1807d8d74`
- `0x1807eb28c`
- `0x180b602ac`
- `0x181104010`

## import_xrefs

- `KERNEL32!FlushViewOfFile` at `0x1806150c9`
- `KERNEL32!FlushViewOfFile` at `0x1806150c9`
- `KERNEL32!FindAtomW` at `0x1806152b0`
- `KERNEL32!FindAtomW` at `0x1806152b0`
- `KERNEL32!DeleteAtom` at `0x1806152c8`
- `KERNEL32!UnmapViewOfFile` at `0x1806150dc`
- `KERNEL32!UnmapViewOfFile` at `0x1806151ce`
- `KERNEL32!UnmapViewOfFile` at `0x1806150dc`
- `KERNEL32!UnmapViewOfFile` at `0x1806151ce`
- `KERNEL32!TlsFree` at `0x180615194`
- `KERNEL32!TlsFree` at `0x1806151b0`
- `KERNEL32!TlsFree` at `0x18061527b`
- `KERNEL32!TlsFree` at `0x180615297`
- `KERNEL32!TlsFree` at `0x180615194`
- `KERNEL32!TlsFree` at `0x1806151b0`
- `KERNEL32!TlsFree` at `0x18061527b`
- `KERNEL32!TlsFree` at `0x180615297`
- `KERNEL32!FlsFree` at `0x180615178`
- `KERNEL32!FlsFree` at `0x180615178`
- `KERNEL32!DeleteCriticalSection` at `0x180614fd7`
- `KERNEL32!DeleteCriticalSection` at `0x180614fea`
- `KERNEL32!DeleteCriticalSection` at `0x180614ffd`
- `KERNEL32!DeleteCriticalSection` at `0x1806150ac`
- `KERNEL32!DeleteCriticalSection` at `0x180614fd7`
- `KERNEL32!DeleteCriticalSection` at `0x180614fea`
- `KERNEL32!DeleteCriticalSection` at `0x180614ffd`
- `KERNEL32!DeleteCriticalSection` at `0x1806150ac`
- `KERNEL32!LeaveCriticalSection` at `0x180615091`
- `KERNEL32!LeaveCriticalSection` at `0x180615269`
- `KERNEL32!LeaveCriticalSection` at `0x180615091`
- `KERNEL32!LeaveCriticalSection` at `0x180615269`
- `KERNEL32!EnterCriticalSection` at `0x18061505f`
- `KERNEL32!EnterCriticalSection` at `0x180615235`
- `KERNEL32!EnterCriticalSection` at `0x18061505f`
- `KERNEL32!EnterCriticalSection` at `0x180615235`
- `KERNEL32!CloseHandle` at `0x180614fb1`
- `KERNEL32!CloseHandle` at `0x1806150f4`
- `KERNEL32!CloseHandle` at `0x1806151e6`
- `KERNEL32!CloseHandle` at `0x180614fb1`
- `KERNEL32!CloseHandle` at `0x1806150f4`
- `KERNEL32!CloseHandle` at `0x1806151e6`
- `ADVAPI32!CryptReleaseContext` at `0x18061524f`
- `ADVAPI32!CryptReleaseContext` at `0x18061524f`
- `urlmon!__imp_TrackingProtectionUninitialize` at `0x18061512d`
- `urlmon!__imp_TrackingProtectionUninitialize` at `0x18061512d`

## pseudocode

```c
void __fastcall DllProcessDetach(int a1)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v3; // rdi
  CLangUtil *v4; // rcx
  void ***v5; // rax
  void *v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  void *v9; // r8
  void *v10; // r8
  __int64 v11; // rcx
  void *v12; // r8
  void *v13; // r8
  struct ATL::_ATL_MODULE *v14; // rcx
  ATOM AtomW; // ax

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  g_processLifetimeActivity = 2;
  v3 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  LODWORD(ThreadLocalStoragePointer) = dword_18158CCA8;
  *(_BYTE *)(v3 + 33) = 1;
  if ( (unsigned int)ThreadLocalStoragePointer > 5 && tlgKeywordOn((__int64)&dword_18158CCA8, 0x400000000002LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18158CCA8,
      (__int64)&word_18154B82E,
      (__int64)&xmmword_1815C2868,
      0);
  *(_BYTE *)(v3 + 33) = 0;
  TraceLoggingUnregister_EventUnregister((__int64)&dword_18158CCA8);
  if ( g_pts )
    DllThreadEmergencyDetach(a1);
  v5 = lang(v4);
  CLangUtil::Shutdown((CLangUtil *)v5);
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
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)g_tszModuleFileName, v6);
  DeinitInputAcceptLabels(v8, v7, v9);
  if ( CInput::s_pchBrowseButtonCaption )
  {
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, CInput::s_pchBrowseButtonCaption, v10);
    CInput::s_pchBrowseButtonCaption = 0;
  }
  CFontCache::DeInit((struct _RTL_CRITICAL_SECTION *)g_FontCache, a1 != 0);
  EnterCriticalSection(&ColorPaletteInternal::s_csColorPaletteLock);
  if ( qword_1815BFBB0 )
  {
    ColorPalette::Release(qword_1815BFBB0);
    qword_1815BFBB0 = 0;
  }
  byte_1815BFBB8 = 0;
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
  v11 = qword_1815C4B88;
  lpBaseAddress = 0;
  hObject = 0;
  if ( qword_1815C4B88 )
  {
    qword_1815C4B88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  TrackingProtectionUninitialize();
  CWebWorkerThreadPool::GlobalUninit(a1);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, qword_1815C4E40, v12);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, qword_1815C4E48, v13);
  DeinitEditingObjects(v14);
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
  McGenEventUnregister_EventUnregister((REGHANDLE *)BERP_READINGVIEW_Context);
  McGenEventUnregister_EventUnregister(&BERP_JSDUMPHEAP_Context);
  McGenEventUnregister_EventUnregister((REGHANDLE *)BERP_MSHTML_Context);
  McGenEventUnregister_EventUnregister((REGHANDLE *)&BERP_IE_Context);
  McGenEventUnregister_EventUnregister((REGHANDLE *)BERP_IEFRAME2_Context);
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
0x180614f00  push    rbx
0x180614f02  push    rsi
0x180614f03  push    rdi
0x180614f04  push    r14
0x180614f06  sub     rsp, 28h
0x180614f0a  mov     rax, gs:58h
0x180614f13  xor     esi, esi
0x180614f15  mov     edx, cs:_tls_index
0x180614f1b  mov     ebx, ecx
0x180614f1d  mov     r14d, 21h ; '!'
0x180614f23  mov     cs:?g_processLifetimeActivity@@3V?$TraceLoggingActivity@$1?g_hAsimovProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAC@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, 2; TraceLoggingActivity<&_tlgProvider_t const * const g_hAsimovProvider,70368744177666,5,_TlgReflectorTag_Param0IsHProvider> g_processLifetimeActivity
0x180614f2d  mov     rdi, [rax+rdx*8]
0x180614f31  mov     eax, cs:dword_18158CCA8
0x180614f37  mov     byte ptr [rdi+r14], 1
0x180614f3c  cmp     eax, 5
0x180614f3f  jbe     short loc_180614F78
0x180614f41  mov     rdx, 400000000002h
0x180614f4b  lea     rcx, dword_18158CCA8
0x180614f52  call    _tlgKeywordOn
0x180614f57  test    al, al
0x180614f59  jz      short loc_180614F78
0x180614f5b  xor     r9d, r9d
0x180614f5e  lea     r8, xmmword_1815C2868
0x180614f65  lea     rdx, word_18154B82E
0x180614f6c  lea     rcx, dword_18158CCA8
0x180614f73  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180614f78  lea     rcx, dword_18158CCA8
0x180614f7f  mov     [rdi+r14], sil
0x180614f83  call    TraceLoggingUnregister_EventUnregister
0x180614f88  cmp     cs:?g_pts@@3PEAUTHREADSTATE@@EA, rsi; THREADSTATE * g_pts
0x180614f8f  jz      short loc_180614F98
0x180614f91  mov     ecx, ebx; int
0x180614f93  call    ?DllThreadEmergencyDetach@@YAXH@Z; DllThreadEmergencyDetach(int)
0x180614f98  call    ?lang@@YAAEAVCLangUtil@@XZ; lang(void)
0x180614f9d  mov     rcx, rax; this
0x180614fa0  call    ?Shutdown@CLangUtil@@QEAAXXZ; CLangUtil::Shutdown(void)
0x180614fa5  mov     rcx, cs:?s_hQuotaMutex@CStorageQuotaHelper@@0PEAXEA; hObject
0x180614fac  test    rcx, rcx
0x180614faf  jz      short loc_180614FBD
0x180614fb1  call    cs:__imp_CloseHandle
0x180614fb8  nop     dword ptr [rax+rax+00h]
0x180614fbd  call    ?GlobalUnInit@CVirtualTabStorage@@SAXXZ; CVirtualTabStorage::GlobalUnInit(void)
0x180614fc2  cmp     cs:?s_fInitCS@CPersistUserData@@0_NA, sil; bool CPersistUserData::s_fInitCS
0x180614fc9  jz      short loc_180615010
0x180614fcb  call    ?DeleteSiteTable@CPersistUserData@@CAJXZ; CPersistUserData::DeleteSiteTable(void)
0x180614fd0  lea     rcx, ?s_csCacheUrlPrefix@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180614fd7  call    cs:__imp_DeleteCriticalSection
0x180614fde  nop     dword ptr [rax+rax+00h]
0x180614fe3  lea     rcx, ?s_csCacheContainer@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180614fea  call    cs:__imp_DeleteCriticalSection
0x180614ff1  nop     dword ptr [rax+rax+00h]
0x180614ff6  lea     rcx, ?s_csSiteTable@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180614ffd  call    cs:__imp_DeleteCriticalSection
0x180615004  nop     dword ptr [rax+rax+00h]
0x180615009  mov     cs:?s_fInitCS@CPersistUserData@@0_NA, sil; bool CPersistUserData::s_fInitCS
0x180615010  mov     rdx, cs:?g_tszModuleFileName@@3PEAGEA; void *
0x180615017  mov     rcx, cs:g_hProcessHeap; this
0x18061501e  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180615023  call    ?DeinitInputAcceptLabels@@YAXXZ; DeinitInputAcceptLabels(void)
0x180615028  mov     rdx, cs:?s_pchBrowseButtonCaption@CInput@@0PEAGEA; void *
0x18061502f  test    rdx, rdx
0x180615032  jz      short loc_180615047
0x180615034  mov     rcx, cs:g_hProcessHeap; this
0x18061503b  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180615040  mov     cs:?s_pchBrowseButtonCaption@CInput@@0PEAGEA, rsi; ushort * CInput::s_pchBrowseButtonCaption
0x180615047  test    ebx, ebx
0x180615049  lea     rcx, ?g_FontCache@@3VCFontCache@@A; this
0x180615050  setnz   dl; bool
0x180615053  call    ?DeInit@CFontCache@@QEAAX_N@Z; CFontCache::DeInit(bool)
0x180615058  lea     rcx, ?s_csColorPaletteLock@ColorPaletteInternal@@2VCGlobalCriticalSection@@A; lpCriticalSection
0x18061505f  call    cs:__imp_EnterCriticalSection
0x180615066  nop     dword ptr [rax+rax+00h]
0x18061506b  mov     rcx, cs:qword_1815BFBB0; this
0x180615072  test    rcx, rcx
0x180615075  jz      short loc_180615083
0x180615077  call    ?Release@ColorPalette@@QEAAXXZ; ColorPalette::Release(void)
0x18061507c  mov     cs:qword_1815BFBB0, rsi
0x180615083  lea     rcx, ?s_csColorPaletteLock@ColorPaletteInternal@@2VCGlobalCriticalSection@@A; lpCriticalSection
0x18061508a  mov     cs:byte_1815BFBB8, sil
0x180615091  call    cs:__imp_LeaveCriticalSection
0x180615098  nop     dword ptr [rax+rax+00h]
0x18061509d  cmp     cs:?_fCSInited@CRtfToHtmlConverter@@0HA, esi; int CRtfToHtmlConverter::_fCSInited
0x1806150a3  jz      short loc_1806150B8
0x1806150a5  lea     rcx, ?_cs@CRtfToHtmlConverter@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1806150ac  call    cs:__imp_DeleteCriticalSection
0x1806150b3  nop     dword ptr [rax+rax+00h]
0x1806150b8  mov     rcx, cs:lpBaseAddress; lpBaseAddress
0x1806150bf  test    rcx, rcx
0x1806150c2  jz      short loc_1806150E8
0x1806150c4  mov     edx, 0BFE0h; dwNumberOfBytesToFlush
0x1806150c9  call    cs:__imp_FlushViewOfFile
0x1806150d0  nop     dword ptr [rax+rax+00h]
0x1806150d5  mov     rcx, cs:lpBaseAddress; lpBaseAddress
0x1806150dc  call    cs:__imp_UnmapViewOfFile
0x1806150e3  nop     dword ptr [rax+rax+00h]
0x1806150e8  mov     rcx, cs:hObject; hObject
0x1806150ef  test    rcx, rcx
0x1806150f2  jz      short loc_180615100
0x1806150f4  call    cs:__imp_CloseHandle
0x1806150fb  nop     dword ptr [rax+rax+00h]
0x180615100  mov     rcx, cs:qword_1815C4B88
0x180615107  mov     cs:lpBaseAddress, rsi
0x18061510e  mov     cs:hObject, rsi
0x180615115  test    rcx, rcx
0x180615118  jz      short loc_18061512D
0x18061511a  mov     cs:qword_1815C4B88, rsi
0x180615121  mov     rax, [rcx]
0x180615124  mov     rax, [rax+10h]
0x180615128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18061512d  call    cs:__imp_TrackingProtectionUninitialize
0x180615134  nop     dword ptr [rax+rax+00h]
0x180615139  mov     ecx, ebx; int
0x18061513b  call    ?GlobalUninit@CWebWorkerThreadPool@@SAXH@Z; CWebWorkerThreadPool::GlobalUninit(int)
0x180615140  mov     rdx, cs:qword_1815C4E40; void *
0x180615147  mov     rcx, cs:g_hProcessHeap; this
0x18061514e  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180615153  mov     rdx, cs:qword_1815C4E48; void *
0x18061515a  mov     rcx, cs:g_hProcessHeap; this
0x180615161  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180615166  call    ?DeinitEditingObjects@@YAXXZ; DeinitEditingObjects(void)
0x18061516b  mov     ecx, cs:?g_dwFls@@3KA; dwFlsIndex
0x180615171  or      ebx, 0FFFFFFFFh
0x180615174  cmp     ecx, ebx
0x180615176  jz      short loc_18061518A
0x180615178  call    cs:__imp_FlsFree
0x18061517f  nop     dword ptr [rax+rax+00h]
0x180615184  mov     cs:?g_dwFls@@3KA, ebx; ulong g_dwFls
0x18061518a  mov     ecx, cs:g_dwTlsTearoffThunk; dwTlsIndex
0x180615190  cmp     ecx, ebx
0x180615192  jz      short loc_1806151A6
0x180615194  call    cs:__imp_TlsFree
0x18061519b  nop     dword ptr [rax+rax+00h]
0x1806151a0  mov     cs:g_dwTlsTearoffThunk, ebx
0x1806151a6  mov     ecx, cs:?g_dwTlsFlsCallback@@3KA; dwTlsIndex
0x1806151ac  cmp     ecx, ebx
0x1806151ae  jz      short loc_1806151C2
0x1806151b0  call    cs:__imp_TlsFree
0x1806151b7  nop     dword ptr [rax+rax+00h]
0x1806151bc  mov     cs:?g_dwTlsFlsCallback@@3KA, ebx; ulong g_dwTlsFlsCallback
0x1806151c2  mov     rcx, cs:?g_pHtmPerfCtl@@3PEAUHTMPERFCTL@@EA; lpBaseAddress
0x1806151c9  test    rcx, rcx
0x1806151cc  jz      short loc_1806151DA
0x1806151ce  call    cs:__imp_UnmapViewOfFile
0x1806151d5  nop     dword ptr [rax+rax+00h]
0x1806151da  mov     rcx, cs:?g_hMapHtmPerfCtl@@3PEAXEA; hObject
0x1806151e1  test    rcx, rcx
0x1806151e4  jz      short loc_1806151F2
0x1806151e6  call    cs:__imp_CloseHandle
0x1806151ed  nop     dword ptr [rax+rax+00h]
0x1806151f2  lea     rcx, BERP_READINGVIEW_Context
0x1806151f9  call    McGenEventUnregister_EventUnregister
0x1806151fe  lea     rcx, BERP_JSDUMPHEAP_Context
0x180615205  call    McGenEventUnregister_EventUnregister
0x18061520a  lea     rcx, BERP_MSHTML_Context
0x180615211  call    McGenEventUnregister_EventUnregister
0x180615216  lea     rcx, BERP_IE_Context
0x18061521d  call    McGenEventUnregister_EventUnregister
0x180615222  lea     rcx, BERP_IEFRAME2_Context
0x180615229  call    McGenEventUnregister_EventUnregister
0x18061522e  lea     rcx, ?g_gcsXSSCryptProv@@3VCGlobalCriticalSection@@A; lpCriticalSection
0x180615235  call    cs:__imp_EnterCriticalSection
0x18061523c  nop     dword ptr [rax+rax+00h]
0x180615241  mov     rcx, cs:?g_hXSSCryptProv@@3_KA; hProv
0x180615248  test    rcx, rcx
0x18061524b  jz      short loc_180615262
0x18061524d  xor     edx, edx; dwFlags
0x18061524f  call    cs:__imp_CryptReleaseContext
0x180615256  nop     dword ptr [rax+rax+00h]
0x18061525b  mov     cs:?g_hXSSCryptProv@@3_KA, rsi; unsigned __int64 g_hXSSCryptProv
0x180615262  lea     rcx, ?g_gcsXSSCryptProv@@3VCGlobalCriticalSection@@A; lpCriticalSection
0x180615269  call    cs:__imp_LeaveCriticalSection
0x180615270  nop     dword ptr [rax+rax+00h]
0x180615275  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18061527b  call    cs:__imp_TlsFree
0x180615282  nop     dword ptr [rax+rax+00h]
0x180615287  mov     ecx, cs:?s_TLSIndex@CDXRenderLockBase@@0KA; dwTlsIndex
0x18061528d  mov     cs:dwTlsIndex, ebx
0x180615293  cmp     ecx, ebx
0x180615295  jz      short loc_1806152A9
0x180615297  call    cs:__imp_TlsFree
0x18061529e  nop     dword ptr [rax+rax+00h]
0x1806152a3  mov     cs:?s_TLSIndex@CDXRenderLockBase@@0KA, ebx; ulong CDXRenderLockBase::s_TLSIndex
0x1806152a9  lea     rcx, a4653c0a42b2d48; "{4653C0A4-2B2D-48DE-AB80-93910A28F900}"
0x1806152b0  call    cs:__imp_FindAtomW
0x1806152b7  nop     dword ptr [rax+rax+00h]
0x1806152bc  movzx   ecx, ax
0x1806152bf  add     rsp, 28h
0x1806152c3  pop     r14
0x1806152c5  pop     rdi
0x1806152c6  pop     rsi
0x1806152c7  pop     rbx
0x1806152c8  jmp     cs:__imp_DeleteAtom
```

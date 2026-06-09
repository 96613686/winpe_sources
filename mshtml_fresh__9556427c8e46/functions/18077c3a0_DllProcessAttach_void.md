# DllProcessAttach(void)

- ea: `0x18077c3a0`
- end: `0x18077c81b`
- name: `?DllProcessAttach@@YAHXZ`
- size: `1147`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180614934`

## callees

- `0x18027e8e4`
- `0x180402d68`
- `0x18041d5a4`
- `0x180473374`
- `0x1804e4c1c`
- `0x1805fef50`
- `0x180614f00`
- `0x180636de0`
- `0x1806df4e0`
- `0x1806f2d14`
- `0x1807018fc`
- `0x1807048b8`
- `0x180715c00`
- `0x1807228ec`
- `0x180729b34`
- `0x180740244`
- `0x18074c98c`
- `0x18075d28c`
- `0x1807661bc`
- `0x18077c3a0`
- `0x180785ba4`
- `0x180788eac`
- `0x18078f00c`
- `0x1807ce4c8`
- `0x1807e7eec`
- `0x1807e9858`
- `0x180b602ac`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!TlsAlloc` at `0x18077c441`
- `KERNEL32!TlsAlloc` at `0x18077c45e`
- `KERNEL32!TlsAlloc` at `0x18077c7b9`
- `KERNEL32!TlsAlloc` at `0x18077c7f5`
- `KERNEL32!TlsAlloc` at `0x18077c441`
- `KERNEL32!TlsAlloc` at `0x18077c45e`
- `KERNEL32!TlsAlloc` at `0x18077c7b9`
- `KERNEL32!TlsAlloc` at `0x18077c7f5`
- `KERNEL32!InitializeCriticalSection` at `0x18077c4b8`
- `KERNEL32!InitializeCriticalSection` at `0x18077c7d7`
- `KERNEL32!InitializeCriticalSection` at `0x18077c4b8`
- `KERNEL32!InitializeCriticalSection` at `0x18077c7d7`
- `KERNEL32!FlsAlloc` at `0x18077c57a`
- `KERNEL32!FlsAlloc` at `0x18077c57a`
- `KERNEL32!HeapCreate` at `0x18077c5bd`
- `KERNEL32!HeapCreate` at `0x18077c5bd`
- `KERNEL32!GetCurrentProcessId` at `0x18077c69d`
- `KERNEL32!GetCurrentProcessId` at `0x18077c69d`
- `KERNEL32!OpenFileMappingW` at `0x18077c6d3`
- `KERNEL32!OpenFileMappingW` at `0x18077c6d3`
- `KERNEL32!MapViewOfFile` at `0x18077c6fb`
- `KERNEL32!MapViewOfFile` at `0x18077c6fb`
- `KERNEL32!AddAtomW` at `0x18077c40b`
- `KERNEL32!AddAtomW` at `0x18077c40b`
- `KERNEL32!HeapSetInformation` at `0x18077c5ec`
- `KERNEL32!HeapSetInformation` at `0x18077c5ec`
- `KERNEL32!FindAtomW` at `0x18077c3dc`
- `KERNEL32!FindAtomW` at `0x18077c3dc`
- `KERNEL32!RaiseFailFastException` at `0x18077c3c9`
- `KERNEL32!RaiseFailFastException` at `0x18077c3f6`
- `KERNEL32!RaiseFailFastException` at `0x18077c3c9`
- `KERNEL32!RaiseFailFastException` at `0x18077c3f6`
- `KERNEL32!LeaveCriticalSection` at `0x18077c667`
- `KERNEL32!LeaveCriticalSection` at `0x18077c667`
- `KERNEL32!EnterCriticalSection` at `0x18077c635`
- `KERNEL32!EnterCriticalSection` at `0x18077c635`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x18077c42a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x18077c42a`
- `ADVAPI32!EventSetInformation` at `0x18077c752`
- `ADVAPI32!EventSetInformation` at `0x18077c752`

## pseudocode

```c
__int64 DllProcessAttach(void)
{
  CCriticalSection *i; // rbx
  CCriticalSection *j; // rbx
  FeatureControlHelper *v2; // rcx
  GUID v3; // xmm0
  HANDLE v5; // rax
  __int64 *v6; // rax
  HANDLE v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  bool v13; // cl
  DWORD dwNumberOfBytesToMap; // [rsp+20h] [rbp-78h]
  int HeapInformation; // [rsp+30h] [rbp-68h] BYREF
  WCHAR Name[24]; // [rsp+38h] [rbp-60h] BYREF

  if ( (unsigned int)GetBrowserProcess() == 15 )
    RaiseFailFastException(0, 0, 0);
  if ( FindAtomW(L"{4653C0A4-2B2D-48DE-AB80-93910A28F900}") )
    RaiseFailFastException(0, 0, 0);
  else
    AddAtomW(L"{4653C0A4-2B2D-48DE-AB80-93910A28F900}");
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18158CCA8);
  CoCreateGuid(&g_processInstanceGUID);
  g_processInstanceGUID.Data1 |= 1u;
  g_dwTlsFlsCallback = TlsAlloc();
  if ( g_dwTlsFlsCallback == -1 )
    goto LABEL_25;
  g_dwTlsTearoffThunk = TlsAlloc();
  if ( g_dwTlsTearoffThunk == -1 )
    goto LABEL_25;
  InitLockableGlobals();
  for ( i = CGlobalCriticalSection::g_gcsList; i; i = (CCriticalSection *)*((_QWORD *)i + 6) )
    CCriticalSection::Init(i);
  for ( j = CGlobalDwnCrit::g_gdcsList; j; j = (CCriticalSection *)*((_QWORD *)j + 6) )
    CCriticalSection::Init(j);
  InitializeCriticalSection(&CRtfToHtmlConverter::_cs);
  CRtfToHtmlConverter::_fCSInited = 1;
  if ( (g_FeatureControlHelper & 1) == 0 )
  {
    FeatureControlHelper::ReInitializeFeatureControlKeys((FeatureControlHelper *)&g_FeatureControlHelper);
    byte_1815BFC77 &= ~0x80u;
    byte_1815BFC78 &= ~1u;
    g_FeatureControlHelper |= 1u;
  }
  if ( !FeatureControlHelper::UseLegacyJscript(v2) )
  {
    v3 = IID_ITrackerJS9;
    goto LABEL_21;
  }
  g_iid_DynamicTrackingService = IID_ITracker;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::GetImpl'::`2'::impl);
  HeapInformation = 0;
  if ( (int)GetBOOL((__int64 *)SettingStore::IEVALUE_Browser_JScriptReplacement[0], &HeapInformation) >= 0
    && HeapInformation )
  {
    v3 = IID_ITrackerJS9Legacy;
LABEL_21:
    g_iid_DynamicTrackingService = v3;
  }
  if ( !(unsigned int)InitEditingObjects() )
  {
LABEL_25:
    DllProcessDetach(0);
    return 0;
  }
  InitUnicodeWrappers();
  if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_CLEANUP_AT_FLS) )
  {
    g_fDoCleanupAtFls = 0;
  }
  else
  {
    g_fDoCleanupAtFls = 1;
    g_dwFls = FlsAlloc(TridentFlsCallback);
    if ( g_dwFls == -1 )
      goto LABEL_25;
  }
  v5 = HeapCreate(0, 0, 0);
  g_hIsolatedHeap = v5;
  if ( !v5 )
    goto LABEL_25;
  HeapInformation = 2;
  HeapSetInformation(v5, HeapCompatibilityInformation, &HeapInformation, 4u);
  v6 = (__int64 *)&MemoryProtection::g_heapHandles;
  if ( MemoryProtection::g_heapHandles )
    v6 = &qword_1815BE738;
  *v6 = (__int64)g_hIsolatedHeap;
  RegisterClipFormats();
  SetCommonClipFormats(&stru_1815B4A50, 2);
  EnterCriticalSection(&ColorPaletteInternal::s_csColorPaletteLock);
  if ( qword_1815BFBB0 )
  {
    ColorPalette::Release(qword_1815BFBB0);
    qword_1815BFBB0 = 0;
  }
  byte_1815BFBB8 = 0;
  LeaveCriticalSection(&ColorPaletteInternal::s_csColorPaletteLock);
  CLASSINFO::Init((CLASSINFO *)g_ciNull, &GUID_NULL, 0);
  if ( (unsigned int)CFontCache::Init((CFontCache *)g_FontCache) )
    goto LABEL_25;
  dwNumberOfBytesToMap = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x17u, L"%s%08lX", L"#MSHTML#PERF#", dwNumberOfBytesToMap);
  v7 = OpenFileMappingW(2u, 0, Name);
  g_hMapHtmPerfCtl = v7;
  if ( v7 )
    g_pHtmPerfCtl = MapViewOfFile(v7, 2u, 0, 0, 0);
  McGenEventRegister_EventRegister(BERP_MSHTML, v8, BERP_MSHTML_Context, BERP_MSHTML_Context);
  McGenEventRegister_EventRegister(BERP_IE, v9, &BERP_IE_Context, &BERP_IE_Context);
  EventSetInformation(
    BERP_IE_Context,
    2,
    &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
    (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
  McGenEventRegister_EventRegister(BERP_JSDUMPHEAP, v10, &BERP_JSDUMPHEAP_Context, &BERP_JSDUMPHEAP_Context);
  McGenEventRegister_EventRegister(BERP_IEFRAME2, v11, BERP_IEFRAME2_Context, BERP_IEFRAME2_Context);
  McGenEventRegister_EventRegister(BERP_READINGVIEW, v12, BERP_READINGVIEW_Context, BERP_READINGVIEW_Context);
  CheckOutllib();
  CheckForBrowser();
  CStorageQuotaHelper::GlobalInit();
  CVirtualTabStorage::GlobalInit();
  CPersistUserData::GlobalInit();
  dwTlsIndex = TlsAlloc();
  InitPrivacIE();
  InitializeCriticalSection(&CWebWorkerThreadPool::s_csWebWorkerThread);
  CWebWorkerThreadPool::s_fInitialized = 1;
  if ( CDXRenderLockBase::s_TLSIndex != -1 )
    goto LABEL_25;
  CDXRenderLockBase::s_TLSIndex = TlsAlloc();
  if ( CDXRenderLockBase::s_TLSIndex == -1 )
    goto LABEL_25;
  StartProcessTelemetryActivity(v13);
  return 1;
}

```

## disassembly

```asm
0x18077c3a0  push    rbx
0x18077c3a2  push    rbp
0x18077c3a3  push    rsi
0x18077c3a4  push    rdi
0x18077c3a5  sub     rsp, 78h
0x18077c3a9  mov     rax, cs:__security_cookie
0x18077c3b0  xor     rax, rsp
0x18077c3b3  mov     [rsp+98h+var_30], rax
0x18077c3b8  call    GetBrowserProcess
0x18077c3bd  cmp     eax, 0Fh
0x18077c3c0  jnz     short loc_18077C3D5
0x18077c3c2  xor     r8d, r8d; dwFlags
0x18077c3c5  xor     edx, edx; pContextRecord
0x18077c3c7  xor     ecx, ecx; pExceptionRecord
0x18077c3c9  call    cs:__imp_RaiseFailFastException
0x18077c3d0  nop     dword ptr [rax+rax+00h]
0x18077c3d5  lea     rcx, a4653c0a42b2d48; "{4653C0A4-2B2D-48DE-AB80-93910A28F900}"
0x18077c3dc  call    cs:__imp_FindAtomW
0x18077c3e3  nop     dword ptr [rax+rax+00h]
0x18077c3e8  xor     edi, edi
0x18077c3ea  test    ax, ax
0x18077c3ed  jz      short loc_18077C404
0x18077c3ef  xor     r8d, r8d; dwFlags
0x18077c3f2  xor     edx, edx; pContextRecord
0x18077c3f4  xor     ecx, ecx; pExceptionRecord
0x18077c3f6  call    cs:__imp_RaiseFailFastException
0x18077c3fd  nop     dword ptr [rax+rax+00h]
0x18077c402  jmp     short loc_18077C417
0x18077c404  lea     rcx, a4653c0a42b2d48; "{4653C0A4-2B2D-48DE-AB80-93910A28F900}"
0x18077c40b  call    cs:__imp_AddAtomW
0x18077c412  nop     dword ptr [rax+rax+00h]
0x18077c417  lea     rcx, dword_18158CCA8; CallbackContext
0x18077c41e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18077c423  lea     rcx, ?g_processInstanceGUID@@3U_GUID@@A; pguid
0x18077c42a  call    cs:__imp_CoCreateGuid
0x18077c431  nop     dword ptr [rax+rax+00h]
0x18077c436  mov     esi, 1
0x18077c43b  or      cs:?g_processInstanceGUID@@3U_GUID@@A.Data1, esi; _GUID g_processInstanceGUID ...
0x18077c441  call    cs:__imp_TlsAlloc
0x18077c448  nop     dword ptr [rax+rax+00h]
0x18077c44d  or      ebp, 0FFFFFFFFh
0x18077c450  mov     cs:?g_dwTlsFlsCallback@@3KA, eax; ulong g_dwTlsFlsCallback
0x18077c456  cmp     eax, ebp
0x18077c458  jz      loc_18077C590
0x18077c45e  call    cs:__imp_TlsAlloc
0x18077c465  nop     dword ptr [rax+rax+00h]
0x18077c46a  mov     cs:g_dwTlsTearoffThunk, eax
0x18077c470  cmp     eax, ebp
0x18077c472  jz      loc_18077C590
0x18077c478  call    ?InitLockableGlobals@@YAXXZ; InitLockableGlobals(void)
0x18077c47d  mov     rbx, cs:?g_gcsList@CGlobalCriticalSection@@1PEAV1@EA; CGlobalCriticalSection * CGlobalCriticalSection::g_gcsList
0x18077c484  jmp     short loc_18077C492
0x18077c486  mov     rcx, rbx; this
0x18077c489  call    ?Init@CCriticalSection@@QEAAXXZ; CCriticalSection::Init(void)
0x18077c48e  mov     rbx, [rbx+30h]
0x18077c492  test    rbx, rbx
0x18077c495  jnz     short loc_18077C486
0x18077c497  mov     rbx, cs:?g_gdcsList@CGlobalDwnCrit@@1PEAV1@EA; CGlobalDwnCrit * CGlobalDwnCrit::g_gdcsList
0x18077c49e  jmp     short loc_18077C4AC
0x18077c4a0  mov     rcx, rbx; this
0x18077c4a3  call    ?Init@CCriticalSection@@QEAAXXZ; CCriticalSection::Init(void)
0x18077c4a8  mov     rbx, [rbx+30h]
0x18077c4ac  test    rbx, rbx
0x18077c4af  jnz     short loc_18077C4A0
0x18077c4b1  lea     rcx, ?_cs@CRtfToHtmlConverter@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18077c4b8  call    cs:__imp_InitializeCriticalSection
0x18077c4bf  nop     dword ptr [rax+rax+00h]
0x18077c4c4  test    cs:?g_FeatureControlHelper@@3VFeatureControlHelper@@A, sil; FeatureControlHelper g_FeatureControlHelper
0x18077c4cb  mov     cs:?_fCSInited@CRtfToHtmlConverter@@0HA, esi; int CRtfToHtmlConverter::_fCSInited
0x18077c4d1  jnz     short loc_18077C4F4
0x18077c4d3  lea     rcx, ?g_FeatureControlHelper@@3VFeatureControlHelper@@A; this
0x18077c4da  call    ?ReInitializeFeatureControlKeys@FeatureControlHelper@@AEAAXXZ; FeatureControlHelper::ReInitializeFeatureControlKeys(void)
0x18077c4df  and     cs:byte_1815BFC77, 7Fh
0x18077c4e6  and     cs:byte_1815BFC78, 0FEh
0x18077c4ed  or      cs:?g_FeatureControlHelper@@3VFeatureControlHelper@@A, sil; FeatureControlHelper g_FeatureControlHelper
0x18077c4f4  call    ?UseLegacyJscript@FeatureControlHelper@@QEBA_NXZ; FeatureControlHelper::UseLegacyJscript(void)
0x18077c4f9  test    al, al
0x18077c4fb  jz      short loc_18077C540
0x18077c4fd  movups  xmm0, xmmword ptr cs:IID_ITracker.Data1
0x18077c504  movdqu  xmmword ptr cs:?g_iid_DynamicTrackingService@@3U_GUID@@A.Data1, xmm0; _GUID g_iid_DynamicTrackingService ...
0x18077c50c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement> `wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::GetImpl(void)'::`2'::impl
0x18077c513  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18077c518  mov     rcx, cs:?IEVALUE_Browser_JScriptReplacement@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Browser_JScriptReplacement
0x18077c51f  lea     rdx, [rsp+98h+HeapInformation]
0x18077c524  mov     [rsp+98h+HeapInformation], edi
0x18077c528  call    GetBOOL
0x18077c52d  test    eax, eax
0x18077c52f  js      short loc_18077C54F
0x18077c531  cmp     [rsp+98h+HeapInformation], edi
0x18077c535  jz      short loc_18077C54F
0x18077c537  movups  xmm0, xmmword ptr cs:IID_ITrackerJS9Legacy.Data1
0x18077c53e  jmp     short loc_18077C547
0x18077c540  movups  xmm0, xmmword ptr cs:IID_ITrackerJS9.Data1
0x18077c547  movdqu  xmmword ptr cs:?g_iid_DynamicTrackingService@@3U_GUID@@A.Data1, xmm0; _GUID g_iid_DynamicTrackingService ...
0x18077c54f  call    ?InitEditingObjects@@YAHXZ; InitEditingObjects(void)
0x18077c554  test    eax, eax
0x18077c556  jz      short loc_18077C590
0x18077c558  call    ?InitUnicodeWrappers@@YAXXZ; InitUnicodeWrappers(void)
0x18077c55d  lea     rcx, ?FEATURE_CLEANUP_AT_FLS@FCK@@3VCFeatureControlKey@@A; this
0x18077c564  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x18077c569  test    eax, eax
0x18077c56b  jnz     short loc_18077C5B0
0x18077c56d  lea     rcx, ?TridentFlsCallback@@YAXPEAX@Z; lpCallback
0x18077c574  mov     cs:?g_fDoCleanupAtFls@@3HA, esi; int g_fDoCleanupAtFls
0x18077c57a  call    cs:__imp_FlsAlloc
0x18077c581  nop     dword ptr [rax+rax+00h]
0x18077c586  mov     cs:?g_dwFls@@3KA, eax; ulong g_dwFls
0x18077c58c  cmp     eax, ebp
0x18077c58e  jnz     short loc_18077C5B6
0x18077c590  xor     ecx, ecx; int
0x18077c592  call    ?DllProcessDetach@@YAXH@Z; DllProcessDetach(int)
0x18077c597  xor     eax, eax
0x18077c599  mov     rcx, [rsp+98h+var_30]
0x18077c59e  xor     rcx, rsp; StackCookie
0x18077c5a1  call    __security_check_cookie
0x18077c5a6  add     rsp, 78h
0x18077c5aa  pop     rdi
0x18077c5ab  pop     rsi
0x18077c5ac  pop     rbp
0x18077c5ad  pop     rbx
0x18077c5ae  retn
0x18077c5b0  mov     cs:?g_fDoCleanupAtFls@@3HA, edi; int g_fDoCleanupAtFls
0x18077c5b6  xor     r8d, r8d; dwMaximumSize
0x18077c5b9  xor     edx, edx; dwInitialSize
0x18077c5bb  xor     ecx, ecx; flOptions
0x18077c5bd  call    cs:__imp_HeapCreate
0x18077c5c4  nop     dword ptr [rax+rax+00h]
0x18077c5c9  mov     cs:g_hIsolatedHeap, rax
0x18077c5d0  test    rax, rax
0x18077c5d3  jz      short loc_18077C590
0x18077c5d5  mov     ebx, 2
0x18077c5da  lea     r8, [rsp+98h+HeapInformation]; HeapInformation
0x18077c5df  xor     edx, edx; HeapInformationClass
0x18077c5e1  mov     [rsp+98h+HeapInformation], ebx
0x18077c5e5  mov     rcx, rax; HeapHandle
0x18077c5e8  lea     r9d, [rbx+2]; HeapInformationLength
0x18077c5ec  call    cs:__imp_HeapSetInformation
0x18077c5f3  nop     dword ptr [rax+rax+00h]
0x18077c5f8  cmp     cs:?g_heapHandles@MemoryProtection@@3PAPEAXA, rdi; void * near * MemoryProtection::g_heapHandles
0x18077c5ff  lea     rdx, qword_1815BE738
0x18077c606  mov     rcx, cs:g_hIsolatedHeap
0x18077c60d  lea     rax, ?g_heapHandles@MemoryProtection@@3PAPEAXA; void * near * MemoryProtection::g_heapHandles
0x18077c614  cmovnz  rax, rdx
0x18077c618  mov     [rax], rcx
0x18077c61b  call    ?RegisterClipFormats@@YAXXZ; RegisterClipFormats(void)
0x18077c620  mov     edx, ebx; int
0x18077c622  lea     rcx, stru_1815B4A50; struct tagFORMATETC *
0x18077c629  call    ?SetCommonClipFormats@@YAXPEAUtagFORMATETC@@H@Z; SetCommonClipFormats(tagFORMATETC *,int)
0x18077c62e  lea     rcx, ?s_csColorPaletteLock@ColorPaletteInternal@@2VCGlobalCriticalSection@@A; lpCriticalSection
0x18077c635  call    cs:__imp_EnterCriticalSection
0x18077c63c  nop     dword ptr [rax+rax+00h]
0x18077c641  mov     rcx, cs:qword_1815BFBB0; this
0x18077c648  test    rcx, rcx
0x18077c64b  jz      short loc_18077C659
0x18077c64d  call    ?Release@ColorPalette@@QEAAXXZ; ColorPalette::Release(void)
0x18077c652  mov     cs:qword_1815BFBB0, rdi
0x18077c659  lea     rcx, ?s_csColorPaletteLock@ColorPaletteInternal@@2VCGlobalCriticalSection@@A; lpCriticalSection
0x18077c660  mov     cs:byte_1815BFBB8, dil
0x18077c667  call    cs:__imp_LeaveCriticalSection
0x18077c66e  nop     dword ptr [rax+rax+00h]
0x18077c673  xor     r8d, r8d; int
0x18077c676  lea     rdx, GUID_NULL; struct _GUID *
0x18077c67d  lea     rcx, ?g_ciNull@@3UCLASSINFO@@A; this
0x18077c684  call    ?Init@CLASSINFO@@QEAAJAEBU_GUID@@H@Z; CLASSINFO::Init(_GUID const &,int)
0x18077c689  lea     rcx, ?g_FontCache@@3VCFontCache@@A; this
0x18077c690  call    ?Init@CFontCache@@QEAAJXZ; CFontCache::Init(void)
0x18077c695  test    eax, eax
0x18077c697  jnz     loc_18077C590
0x18077c69d  call    cs:__imp_GetCurrentProcessId
0x18077c6a4  nop     dword ptr [rax+rax+00h]
0x18077c6a9  lea     r9, aMshtmlPerf; "#MSHTML#PERF#"
0x18077c6b0  mov     edx, 17h; unsigned __int64
0x18077c6b5  lea     r8, aS08lx; "%s%08lX"
0x18077c6bc  mov     [rsp+98h+dwNumberOfBytesToMap], eax
0x18077c6c0  lea     rcx, [rsp+98h+Name]; unsigned __int16 *
0x18077c6c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18077c6ca  lea     r8, [rsp+98h+Name]; lpName
0x18077c6cf  xor     edx, edx; bInheritHandle
0x18077c6d1  mov     ecx, ebx; dwDesiredAccess
0x18077c6d3  call    cs:__imp_OpenFileMappingW
0x18077c6da  nop     dword ptr [rax+rax+00h]
0x18077c6df  mov     cs:?g_hMapHtmPerfCtl@@3PEAXEA, rax; void * g_hMapHtmPerfCtl
0x18077c6e6  test    rax, rax
0x18077c6e9  jz      short loc_18077C70E
0x18077c6eb  xor     r9d, r9d; dwFileOffsetLow
0x18077c6ee  mov     qword ptr [rsp+98h+dwNumberOfBytesToMap], rdi; dwNumberOfBytesToMap
0x18077c6f3  xor     r8d, r8d; dwFileOffsetHigh
0x18077c6f6  mov     edx, ebx; dwDesiredAccess
0x18077c6f8  mov     rcx, rax; hFileMappingObject
0x18077c6fb  call    cs:__imp_MapViewOfFile
0x18077c702  nop     dword ptr [rax+rax+00h]
0x18077c707  mov     cs:?g_pHtmPerfCtl@@3PEAUHTMPERFCTL@@EA, rax; HTMPERFCTL * g_pHtmPerfCtl
0x18077c70e  lea     r8, BERP_MSHTML_Context
0x18077c715  mov     r9, r8
0x18077c718  lea     rcx, BERP_MSHTML
0x18077c71f  call    McGenEventRegister_EventRegister
0x18077c724  lea     r8, BERP_IE_Context
0x18077c72b  mov     r9, r8
0x18077c72e  lea     rcx, BERP_IE
0x18077c735  call    McGenEventRegister_EventRegister
0x18077c73a  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x18077c742  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x18077c749  mov     rcx, cs:BERP_IE_Context
0x18077c750  mov     edx, ebx
0x18077c752  call    cs:__imp_EventSetInformation
0x18077c759  nop     dword ptr [rax+rax+00h]
0x18077c75e  lea     r8, BERP_JSDUMPHEAP_Context
0x18077c765  mov     r9, r8
0x18077c768  lea     rcx, BERP_JSDUMPHEAP
0x18077c76f  call    McGenEventRegister_EventRegister
0x18077c774  lea     r8, BERP_IEFRAME2_Context
0x18077c77b  mov     r9, r8
0x18077c77e  lea     rcx, BERP_IEFRAME2
0x18077c785  call    McGenEventRegister_EventRegister
0x18077c78a  lea     r8, BERP_READINGVIEW_Context
0x18077c791  mov     r9, r8
0x18077c794  lea     rcx, BERP_READINGVIEW
0x18077c79b  call    McGenEventRegister_EventRegister
0x18077c7a0  call    ?CheckOutllib@@YAXXZ; CheckOutllib(void)
0x18077c7a5  call    ?CheckForBrowser@@YAXXZ; CheckForBrowser(void)
0x18077c7aa  call    ?GlobalInit@CStorageQuotaHelper@@SAJXZ; CStorageQuotaHelper::GlobalInit(void)
0x18077c7af  call    ?GlobalInit@CVirtualTabStorage@@SAJXZ; CVirtualTabStorage::GlobalInit(void)
0x18077c7b4  call    ?GlobalInit@CPersistUserData@@SAHXZ; CPersistUserData::GlobalInit(void)
0x18077c7b9  call    cs:__imp_TlsAlloc
0x18077c7c0  nop     dword ptr [rax+rax+00h]
0x18077c7c5  mov     cs:dwTlsIndex, eax
0x18077c7cb  call    ?InitPrivacIE@@YAXXZ; InitPrivacIE(void)
0x18077c7d0  lea     rcx, ?s_csWebWorkerThread@CWebWorkerThreadPool@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18077c7d7  call    cs:__imp_InitializeCriticalSection
0x18077c7de  nop     dword ptr [rax+rax+00h]
0x18077c7e3  cmp     cs:?s_TLSIndex@CDXRenderLockBase@@0KA, ebp; ulong CDXRenderLockBase::s_TLSIndex
0x18077c7e9  mov     cs:?s_fInitialized@CWebWorkerThreadPool@@1HA, esi; int CWebWorkerThreadPool::s_fInitialized
0x18077c7ef  jnz     loc_18077C590
0x18077c7f5  call    cs:__imp_TlsAlloc
0x18077c7fc  nop     dword ptr [rax+rax+00h]
0x18077c801  mov     cs:?s_TLSIndex@CDXRenderLockBase@@0KA, eax; ulong CDXRenderLockBase::s_TLSIndex
0x18077c807  cmp     eax, ebp
0x18077c809  jz      loc_18077C590
0x18077c80f  call    ?StartProcessTelemetryActivity@@YAX_N@Z; StartProcessTelemetryActivity(bool)
0x18077c814  mov     eax, esi
0x18077c816  jmp     loc_18077C599
```

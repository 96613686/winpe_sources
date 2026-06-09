# DllProcessAttach(void)

- ea: `0x180771b84`
- end: `0x180771f86`
- name: `?DllProcessAttach@@YAHXZ`
- size: `1026`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18061ba20`

## callees

- `0x1800d09f0`
- `0x18028ecdc`
- `0x1802be570`
- `0x18030035c`
- `0x1804a243c`
- `0x180607ae0`
- `0x18061bf3c`
- `0x18063b8a8`
- `0x1806dc8dc`
- `0x1806f1e50`
- `0x1806fd518`
- `0x18070117c`
- `0x18070ef3c`
- `0x180724754`
- `0x180737950`
- `0x18073fcf8`
- `0x180743e94`
- `0x1807558c4`
- `0x18075d3ac`
- `0x180771b84`
- `0x18077a5f0`
- `0x18077d448`
- `0x180784a68`
- `0x1807c13f8`
- `0x1807dc2f8`
- `0x1807dda3c`
- `0x180b4787c`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!TlsAlloc` at `0x180771c07`
- `KERNEL32!TlsAlloc` at `0x180771c1e`
- `KERNEL32!TlsAlloc` at `0x180771f36`
- `KERNEL32!TlsAlloc` at `0x180771f66`
- `KERNEL32!TlsAlloc` at `0x180771c07`
- `KERNEL32!TlsAlloc` at `0x180771c1e`
- `KERNEL32!TlsAlloc` at `0x180771f36`
- `KERNEL32!TlsAlloc` at `0x180771f66`
- `KERNEL32!InitializeCriticalSection` at `0x180771c72`
- `KERNEL32!InitializeCriticalSection` at `0x180771f4e`
- `KERNEL32!InitializeCriticalSection` at `0x180771c72`
- `KERNEL32!InitializeCriticalSection` at `0x180771f4e`
- `KERNEL32!FlsAlloc` at `0x180771d2e`
- `KERNEL32!FlsAlloc` at `0x180771d2e`
- `KERNEL32!HeapCreate` at `0x180771d6a`
- `KERNEL32!HeapCreate` at `0x180771d6a`
- `KERNEL32!GetCurrentProcessId` at `0x180771e32`
- `KERNEL32!GetCurrentProcessId` at `0x180771e32`
- `KERNEL32!OpenFileMappingW` at `0x180771e62`
- `KERNEL32!OpenFileMappingW` at `0x180771e62`
- `KERNEL32!MapViewOfFile` at `0x180771e84`
- `KERNEL32!MapViewOfFile` at `0x180771e84`
- `KERNEL32!AddAtomW` at `0x180771bdd`
- `KERNEL32!AddAtomW` at `0x180771bdd`
- `KERNEL32!HeapSetInformation` at `0x180771d93`
- `KERNEL32!HeapSetInformation` at `0x180771d93`
- `KERNEL32!FindAtomW` at `0x180771bba`
- `KERNEL32!FindAtomW` at `0x180771bba`
- `KERNEL32!RaiseFailFastException` at `0x180771bad`
- `KERNEL32!RaiseFailFastException` at `0x180771bce`
- `KERNEL32!RaiseFailFastException` at `0x180771bad`
- `KERNEL32!RaiseFailFastException` at `0x180771bce`
- `KERNEL32!LeaveCriticalSection` at `0x180771e02`
- `KERNEL32!LeaveCriticalSection` at `0x180771e02`
- `KERNEL32!EnterCriticalSection` at `0x180771dd6`
- `KERNEL32!EnterCriticalSection` at `0x180771dd6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x180771bf6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateGuid` at `0x180771bf6`
- `ADVAPI32!EventSetInformation` at `0x180771ed5`
- `ADVAPI32!EventSetInformation` at `0x180771ed5`

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
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_181559C88);
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
    byte_18158CB77 &= ~0x80u;
    byte_18158CB78 &= ~1u;
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
    v6 = &qword_18158B638;
  *v6 = (__int64)g_hIsolatedHeap;
  RegisterClipFormats();
  SetCommonClipFormats(&stru_181581950, 2);
  EnterCriticalSection(&ColorPaletteInternal::s_csColorPaletteLock);
  if ( qword_18158CAB0 )
  {
    ColorPalette::Release(qword_18158CAB0);
    qword_18158CAB0 = 0;
  }
  byte_18158CAB8 = 0;
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
0x180771b84  push    rbx
0x180771b86  push    rbp
0x180771b87  push    rsi
0x180771b88  push    rdi
0x180771b89  sub     rsp, 78h
0x180771b8d  mov     rax, cs:__security_cookie
0x180771b94  xor     rax, rsp
0x180771b97  mov     [rsp+98h+var_30], rax
0x180771b9c  call    GetBrowserProcess
0x180771ba1  cmp     eax, 0Fh
0x180771ba4  jnz     short loc_180771BB3
0x180771ba6  xor     r8d, r8d; dwFlags
0x180771ba9  xor     edx, edx; pContextRecord
0x180771bab  xor     ecx, ecx; pExceptionRecord
0x180771bad  call    cs:__imp_RaiseFailFastException
0x180771bb3  lea     rcx, a4653c0a42b2d48; "{4653C0A4-2B2D-48DE-AB80-93910A28F900}"
0x180771bba  call    cs:__imp_FindAtomW
0x180771bc0  xor     edi, edi
0x180771bc2  test    ax, ax
0x180771bc5  jz      short loc_180771BD6
0x180771bc7  xor     r8d, r8d; dwFlags
0x180771bca  xor     edx, edx; pContextRecord
0x180771bcc  xor     ecx, ecx; pExceptionRecord
0x180771bce  call    cs:__imp_RaiseFailFastException
0x180771bd4  jmp     short loc_180771BE3
0x180771bd6  lea     rcx, a4653c0a42b2d48; "{4653C0A4-2B2D-48DE-AB80-93910A28F900}"
0x180771bdd  call    cs:__imp_AddAtomW
0x180771be3  lea     rcx, dword_181559C88; CallbackContext
0x180771bea  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180771bef  lea     rcx, ?g_processInstanceGUID@@3U_GUID@@A; pguid
0x180771bf6  call    cs:__imp_CoCreateGuid
0x180771bfc  mov     esi, 1
0x180771c01  or      cs:?g_processInstanceGUID@@3U_GUID@@A.Data1, esi; _GUID g_processInstanceGUID ...
0x180771c07  call    cs:__imp_TlsAlloc
0x180771c0d  or      ebp, 0FFFFFFFFh
0x180771c10  mov     cs:?g_dwTlsFlsCallback@@3KA, eax; ulong g_dwTlsFlsCallback
0x180771c16  cmp     eax, ebp
0x180771c18  jz      loc_180771D3E
0x180771c1e  call    cs:__imp_TlsAlloc
0x180771c24  mov     cs:g_dwTlsTearoffThunk, eax
0x180771c2a  cmp     eax, ebp
0x180771c2c  jz      loc_180771D3E
0x180771c32  call    ?InitLockableGlobals@@YAXXZ; InitLockableGlobals(void)
0x180771c37  mov     rbx, cs:?g_gcsList@CGlobalCriticalSection@@1PEAV1@EA; CGlobalCriticalSection * CGlobalCriticalSection::g_gcsList
0x180771c3e  jmp     short loc_180771C4C
0x180771c40  mov     rcx, rbx; this
0x180771c43  call    ?Init@CCriticalSection@@QEAAXXZ; CCriticalSection::Init(void)
0x180771c48  mov     rbx, [rbx+30h]
0x180771c4c  test    rbx, rbx
0x180771c4f  jnz     short loc_180771C40
0x180771c51  mov     rbx, cs:?g_gdcsList@CGlobalDwnCrit@@1PEAV1@EA; CGlobalDwnCrit * CGlobalDwnCrit::g_gdcsList
0x180771c58  jmp     short loc_180771C66
0x180771c5a  mov     rcx, rbx; this
0x180771c5d  call    ?Init@CCriticalSection@@QEAAXXZ; CCriticalSection::Init(void)
0x180771c62  mov     rbx, [rbx+30h]
0x180771c66  test    rbx, rbx
0x180771c69  jnz     short loc_180771C5A
0x180771c6b  lea     rcx, ?_cs@CRtfToHtmlConverter@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180771c72  call    cs:__imp_InitializeCriticalSection
0x180771c78  test    cs:?g_FeatureControlHelper@@3VFeatureControlHelper@@A, sil; FeatureControlHelper g_FeatureControlHelper
0x180771c7f  mov     cs:?_fCSInited@CRtfToHtmlConverter@@0HA, esi; int CRtfToHtmlConverter::_fCSInited
0x180771c85  jnz     short loc_180771CA8
0x180771c87  lea     rcx, ?g_FeatureControlHelper@@3VFeatureControlHelper@@A; this
0x180771c8e  call    ?ReInitializeFeatureControlKeys@FeatureControlHelper@@AEAAXXZ; FeatureControlHelper::ReInitializeFeatureControlKeys(void)
0x180771c93  and     cs:byte_18158CB77, 7Fh
0x180771c9a  and     cs:byte_18158CB78, 0FEh
0x180771ca1  or      cs:?g_FeatureControlHelper@@3VFeatureControlHelper@@A, sil; FeatureControlHelper g_FeatureControlHelper
0x180771ca8  call    ?UseLegacyJscript@FeatureControlHelper@@QEBA_NXZ; FeatureControlHelper::UseLegacyJscript(void)
0x180771cad  test    al, al
0x180771caf  jz      short loc_180771CF4
0x180771cb1  movups  xmm0, xmmword ptr cs:IID_ITracker.Data1
0x180771cb8  movdqu  xmmword ptr cs:?g_iid_DynamicTrackingService@@3U_GUID@@A.Data1, xmm0; _GUID g_iid_DynamicTrackingService ...
0x180771cc0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement> `wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::GetImpl(void)'::`2'::impl
0x180771cc7  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180771ccc  mov     rcx, cs:?IEVALUE_Browser_JScriptReplacement@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Browser_JScriptReplacement
0x180771cd3  lea     rdx, [rsp+98h+HeapInformation]
0x180771cd8  mov     [rsp+98h+HeapInformation], edi
0x180771cdc  call    GetBOOL
0x180771ce1  test    eax, eax
0x180771ce3  js      short loc_180771D03
0x180771ce5  cmp     [rsp+98h+HeapInformation], edi
0x180771ce9  jz      short loc_180771D03
0x180771ceb  movups  xmm0, xmmword ptr cs:IID_ITrackerJS9Legacy.Data1
0x180771cf2  jmp     short loc_180771CFB
0x180771cf4  movups  xmm0, xmmword ptr cs:IID_ITrackerJS9.Data1
0x180771cfb  movdqu  xmmword ptr cs:?g_iid_DynamicTrackingService@@3U_GUID@@A.Data1, xmm0; _GUID g_iid_DynamicTrackingService ...
0x180771d03  call    ?InitEditingObjects@@YAHXZ; InitEditingObjects(void)
0x180771d08  test    eax, eax
0x180771d0a  jz      short loc_180771D3E
0x180771d0c  call    ?InitUnicodeWrappers@@YAXXZ; InitUnicodeWrappers(void)
0x180771d11  lea     rcx, ?FEATURE_CLEANUP_AT_FLS@FCK@@3VCFeatureControlKey@@A; this
0x180771d18  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180771d1d  test    eax, eax
0x180771d1f  jnz     short loc_180771D5D
0x180771d21  lea     rcx, ?TridentFlsCallback@@YAXPEAX@Z; lpCallback
0x180771d28  mov     cs:?g_fDoCleanupAtFls@@3HA, esi; int g_fDoCleanupAtFls
0x180771d2e  call    cs:__imp_FlsAlloc
0x180771d34  mov     cs:?g_dwFls@@3KA, eax; ulong g_dwFls
0x180771d3a  cmp     eax, ebp
0x180771d3c  jnz     short loc_180771D63
0x180771d3e  xor     ecx, ecx; int
0x180771d40  call    ?DllProcessDetach@@YAXH@Z; DllProcessDetach(int)
0x180771d45  xor     eax, eax
0x180771d47  mov     rcx, [rsp+98h+var_30]
0x180771d4c  xor     rcx, rsp; StackCookie
0x180771d4f  call    __security_check_cookie
0x180771d54  add     rsp, 78h
0x180771d58  pop     rdi
0x180771d59  pop     rsi
0x180771d5a  pop     rbp
0x180771d5b  pop     rbx
0x180771d5c  retn
0x180771d5d  mov     cs:?g_fDoCleanupAtFls@@3HA, edi; int g_fDoCleanupAtFls
0x180771d63  xor     r8d, r8d; dwMaximumSize
0x180771d66  xor     edx, edx; dwInitialSize
0x180771d68  xor     ecx, ecx; flOptions
0x180771d6a  call    cs:__imp_HeapCreate
0x180771d70  mov     cs:g_hIsolatedHeap, rax
0x180771d77  test    rax, rax
0x180771d7a  jz      short loc_180771D3E
0x180771d7c  mov     ebx, 2
0x180771d81  lea     r8, [rsp+98h+HeapInformation]; HeapInformation
0x180771d86  xor     edx, edx; HeapInformationClass
0x180771d88  mov     [rsp+98h+HeapInformation], ebx
0x180771d8c  mov     rcx, rax; HeapHandle
0x180771d8f  lea     r9d, [rbx+2]; HeapInformationLength
0x180771d93  call    cs:__imp_HeapSetInformation
0x180771d99  cmp     cs:?g_heapHandles@MemoryProtection@@3PAPEAXA, rdi; void * near * MemoryProtection::g_heapHandles
0x180771da0  lea     rdx, qword_18158B638
0x180771da7  mov     rcx, cs:g_hIsolatedHeap
0x180771dae  lea     rax, ?g_heapHandles@MemoryProtection@@3PAPEAXA; void * near * MemoryProtection::g_heapHandles
0x180771db5  cmovnz  rax, rdx
0x180771db9  mov     [rax], rcx
0x180771dbc  call    ?RegisterClipFormats@@YAXXZ; RegisterClipFormats(void)
0x180771dc1  mov     edx, ebx; int
0x180771dc3  lea     rcx, stru_181581950; struct tagFORMATETC *
0x180771dca  call    ?SetCommonClipFormats@@YAXPEAUtagFORMATETC@@H@Z; SetCommonClipFormats(tagFORMATETC *,int)
0x180771dcf  lea     rcx, ?s_csColorPaletteLock@ColorPaletteInternal@@2VCGlobalCriticalSection@@A; lpCriticalSection
0x180771dd6  call    cs:__imp_EnterCriticalSection
0x180771ddc  mov     rcx, cs:qword_18158CAB0; this
0x180771de3  test    rcx, rcx
0x180771de6  jz      short loc_180771DF4
0x180771de8  call    ?Release@ColorPalette@@QEAAXXZ; ColorPalette::Release(void)
0x180771ded  mov     cs:qword_18158CAB0, rdi
0x180771df4  lea     rcx, ?s_csColorPaletteLock@ColorPaletteInternal@@2VCGlobalCriticalSection@@A; lpCriticalSection
0x180771dfb  mov     cs:byte_18158CAB8, dil
0x180771e02  call    cs:__imp_LeaveCriticalSection
0x180771e08  xor     r8d, r8d; int
0x180771e0b  lea     rdx, GUID_NULL; struct _GUID *
0x180771e12  lea     rcx, ?g_ciNull@@3UCLASSINFO@@A; this
0x180771e19  call    ?Init@CLASSINFO@@QEAAJAEBU_GUID@@H@Z; CLASSINFO::Init(_GUID const &,int)
0x180771e1e  lea     rcx, ?g_FontCache@@3VCFontCache@@A; this
0x180771e25  call    ?Init@CFontCache@@QEAAJXZ; CFontCache::Init(void)
0x180771e2a  test    eax, eax
0x180771e2c  jnz     loc_180771D3E
0x180771e32  call    cs:__imp_GetCurrentProcessId
0x180771e38  lea     r9, aMshtmlPerf; "#MSHTML#PERF#"
0x180771e3f  mov     edx, 17h; unsigned __int64
0x180771e44  lea     r8, aS08lx; "%s%08lX"
0x180771e4b  mov     [rsp+98h+dwNumberOfBytesToMap], eax
0x180771e4f  lea     rcx, [rsp+98h+Name]; unsigned __int16 *
0x180771e54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180771e59  lea     r8, [rsp+98h+Name]; lpName
0x180771e5e  xor     edx, edx; bInheritHandle
0x180771e60  mov     ecx, ebx; dwDesiredAccess
0x180771e62  call    cs:__imp_OpenFileMappingW
0x180771e68  mov     cs:?g_hMapHtmPerfCtl@@3PEAXEA, rax; void * g_hMapHtmPerfCtl
0x180771e6f  test    rax, rax
0x180771e72  jz      short loc_180771E91
0x180771e74  xor     r9d, r9d; dwFileOffsetLow
0x180771e77  mov     qword ptr [rsp+98h+dwNumberOfBytesToMap], rdi; dwNumberOfBytesToMap
0x180771e7c  xor     r8d, r8d; dwFileOffsetHigh
0x180771e7f  mov     edx, ebx; dwDesiredAccess
0x180771e81  mov     rcx, rax; hFileMappingObject
0x180771e84  call    cs:__imp_MapViewOfFile
0x180771e8a  mov     cs:?g_pHtmPerfCtl@@3PEAUHTMPERFCTL@@EA, rax; HTMPERFCTL * g_pHtmPerfCtl
0x180771e91  lea     r8, BERP_MSHTML_Context
0x180771e98  mov     r9, r8
0x180771e9b  lea     rcx, BERP_MSHTML
0x180771ea2  call    McGenEventRegister_EventRegister
0x180771ea7  lea     r8, BERP_IE_Context
0x180771eae  mov     r9, r8
0x180771eb1  lea     rcx, BERP_IE
0x180771eb8  call    McGenEventRegister_EventRegister
0x180771ebd  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x180771ec5  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x180771ecc  mov     rcx, cs:BERP_IE_Context
0x180771ed3  mov     edx, ebx
0x180771ed5  call    cs:__imp_EventSetInformation
0x180771edb  lea     r8, BERP_JSDUMPHEAP_Context
0x180771ee2  mov     r9, r8
0x180771ee5  lea     rcx, BERP_JSDUMPHEAP
0x180771eec  call    McGenEventRegister_EventRegister
0x180771ef1  lea     r8, BERP_IEFRAME2_Context
0x180771ef8  mov     r9, r8
0x180771efb  lea     rcx, BERP_IEFRAME2
0x180771f02  call    McGenEventRegister_EventRegister
0x180771f07  lea     r8, BERP_READINGVIEW_Context
0x180771f0e  mov     r9, r8
0x180771f11  lea     rcx, BERP_READINGVIEW
0x180771f18  call    McGenEventRegister_EventRegister
0x180771f1d  call    ?CheckOutllib@@YAXXZ; CheckOutllib(void)
0x180771f22  call    ?CheckForBrowser@@YAXXZ; CheckForBrowser(void)
0x180771f27  call    ?GlobalInit@CStorageQuotaHelper@@SAJXZ; CStorageQuotaHelper::GlobalInit(void)
0x180771f2c  call    ?GlobalInit@CVirtualTabStorage@@SAJXZ; CVirtualTabStorage::GlobalInit(void)
0x180771f31  call    ?GlobalInit@CPersistUserData@@SAHXZ; CPersistUserData::GlobalInit(void)
0x180771f36  call    cs:__imp_TlsAlloc
0x180771f3c  mov     cs:dwTlsIndex, eax
0x180771f42  call    ?InitPrivacIE@@YAXXZ; InitPrivacIE(void)
0x180771f47  lea     rcx, ?s_csWebWorkerThread@CWebWorkerThreadPool@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180771f4e  call    cs:__imp_InitializeCriticalSection
0x180771f54  cmp     cs:?s_TLSIndex@CDXRenderLockBase@@0KA, ebp; ulong CDXRenderLockBase::s_TLSIndex
0x180771f5a  mov     cs:?s_fInitialized@CWebWorkerThreadPool@@1HA, esi; int CWebWorkerThreadPool::s_fInitialized
0x180771f60  jnz     loc_180771D3E
0x180771f66  call    cs:__imp_TlsAlloc
0x180771f6c  mov     cs:?s_TLSIndex@CDXRenderLockBase@@0KA, eax; ulong CDXRenderLockBase::s_TLSIndex
0x180771f72  cmp     eax, ebp
0x180771f74  jz      loc_180771D3E
0x180771f7a  call    ?StartProcessTelemetryActivity@@YAX_N@Z; StartProcessTelemetryActivity(bool)
0x180771f7f  mov     eax, esi
0x180771f81  jmp     loc_180771D47
```

# ProcessUninitialize(void)

- ea: `0x1800102e0`
- end: `0x1800105e1`
- name: `?ProcessUninitialize@@YAXXZ`
- size: `769`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d518`
- `0x1800101c8`
- `0x180087d80`

## callees

- `0x180006250`
- `0x180006390`
- `0x1800102e0`
- `0x1800188a0`
- `0x1800859ec`
- `0x18008abdc`
- `0x18008bc34`
- `0x18008bcf0`
- `0x18008bd78`
- `0x18008bdc4`
- `0x1800bd8f8`
- `0x180123284`
- `0x18012dbb8`
- `0x180148ca8`
- `0x1801653d0`
- `0x180179024`
- `0x18018050c`
- `0x180199d80`
- `0x18019bc8c`
- `0x180255010`

## import_xrefs

- `ntdll!RtlDeleteNoSplay` at `0x180010546`
- `ntdll!RtlDeleteNoSplay` at `0x180010546`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010571`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010571`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010502`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001052a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010502`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001052a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800104a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800104a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800105c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800105c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800105b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800105b4`
- `ext-ms-win-com-ole32-l1-1-0!ClipboardProcessUninitialize` at `0x180010328`
- `ext-ms-win-com-ole32-l1-1-0!ClipboardProcessUninitialize` at `0x180010328`
- `ext-ms-win-com-ole32-l1-1-0!DestroyRunningObjectTable` at `0x1800103d1`
- `ext-ms-win-com-ole32-l1-1-0!DestroyRunningObjectTable` at `0x1800103d1`
- `ext-ms-win-com-ole32-l1-1-0!DeletePatternAndExtensionTables` at `0x180010598`
- `ext-ms-win-com-ole32-l1-1-0!DeletePatternAndExtensionTables` at `0x180010598`
- `ext-ms-win-com-ole32-l1-1-0!OleReleaseEnumVerbCache` at `0x18001032e`
- `ext-ms-win-com-ole32-l1-1-0!OleReleaseEnumVerbCache` at `0x18001032e`

## string_xrefs

- `0x18001040f`: `onecore\com\combase\dcomrem\crossctx.cxx`
- `0x1800103ac`: `onecore\com\combase\dcomrem\giptbl.cxx`
- `0x18001033a`: `onecore\com\combase\objact\actvator.cxx`

## pseudocode

```c
void __fastcall ProcessUninitialize(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  tagSOleTlsData *ReservedForOle; // rax
  const char *v5; // r9
  __int64 v6; // rbx
  _RTL_SPLAY_LINKS *pRoot; // rbx
  void *retaddr; // [rsp+28h] [rbp+0h]
  COleTls Tls; // [rsp+30h] [rbp+8h] BYREF

  ReservedForOle = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  Tls._pData = ReservedForOle;
  if ( !ReservedForOle )
  {
    if ( COleTls::TLSAllocData(&Tls) < 0 )
      goto LABEL_7;
    ReservedForOle = Tls._pData;
  }
  if ( SLOBYTE(ReservedForOle->dwFlags) < 0 && IsOle32DllGetClassObjectPresent() )
  {
    ClipboardProcessUninitialize();
    OleReleaseEnumVerbCache();
  }
LABEL_7:
  COleStaticMutexSem::Request(
    &CApartmentHashTable::_mxsAptTblLock,
    "onecore\\com\\combase\\objact\\actvator.cxx",
    0xABAu,
    a4);
  if ( gApartmentTbl._fTableInitialized )
    gApartmentTbl._hashtbl.Cleanup(
      (struct CDWORDHashTable *)&gApartmentTbl,
      (void (__fastcall *)(SHashChain *))CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking);
  COleStaticMutexSem::Release(&CApartmentHashTable::_mxsAptTblLock);
  if ( Windows::Foundation::Diagnostics::CausalityTraceState::gCausality )
  {
    Windows::Foundation::Diagnostics::CausalityTraceState::gCausality->Release(Windows::Foundation::Diagnostics::CausalityTraceState::gCausality);
    Windows::Foundation::Diagnostics::CausalityTraceState::gCausality = 0;
  }
  if ( CGIPTable::_InUseList._first )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0x27Eu, "onecore\\com\\combase\\dcomrem\\giptbl.cxx");
  if ( (g_CleanupFlags & 1) != 0 && IsOle32DllGetClassObjectPresent() )
    DestroyRunningObjectTable();
  if ( g_pMgot )
  {
    CMachineGlobalObjectTable::VerifyEmpty(g_pMgot);
    g_pMgot->Release(g_pMgot);
    g_pMgot = 0;
  }
  COleStaticMutexSem::Request(&gComLock, "onecore\\com\\combase\\dcomrem\\crossctx.cxx", 0x20Fu, v5);
  if ( CStdWrapper::s_fInitialized )
  {
    if ( !CStdWrapper::s_cObjects )
      CStdWrapper::PrivateCleanup();
    CHashTable::Cleanup(
      &CPIDTable::s_PIDHashTbl,
      (void (__fastcall *)(SHashChain *))CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking);
    CPIDTable::s_fInitialized = 0;
    COIDTable::Cleanup();
    CStdWrapper::s_fInitialized = 0;
  }
  COleStaticMutexSem::Release(&gComLock);
  ChannelProcessUninitialize();
  UninitializeSecurity();
  if ( g_bInitialized )
  {
    g_pIMalloc->Release(g_pIMalloc);
    g_bInitialized = 0;
  }
  if ( g_bServerLockInitialized )
  {
    DeleteCriticalSection(&g_ServerLock);
    g_bServerLockInitialized = 0;
  }
  if ( (CClassCache::_dwFlags & 1) != 0 )
    CClassCache::ReleaseCatalogObjects();
  v6 = _InterlockedExchange64((volatile __int64 *)&gpCatalog, 0);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 88LL))(v6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    AcquireSRWLockExclusive(&g_comDependenciesOnPackagesLock.m_lock);
    Tls._pData = (tagSOleTlsData *)&g_comDependenciesOnPackagesLock;
    ObjectLibrary::ReferencedPtr<ComDependenciesOnPackages>::InternalRelease(&g_comDependenciesOnPackages);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > *)&Tls);
  }
  AcquireSRWLockExclusive(&g_unmarshalersTable._lock.SRWLock_);
  pRoot = g_unmarshalersTable._pRoot;
  Tls._pData = (tagSOleTlsData *)g_unmarshalersTable._pRoot;
  while ( pRoot )
  {
    RtlDeleteNoSplay(pRoot, (PRTL_SPLAY_LINKS *)&Tls);
    operator delete(pRoot, 0x30u);
    pRoot = (_RTL_SPLAY_LINKS *)Tls._pData;
  }
  g_unmarshalersTable._pRoot = 0;
  ReleaseSRWLockExclusive(&g_unmarshalersTable._lock.SRWLock_);
  if ( (CClassCache::_dwFlags & 1) != 0 )
    CClassCache::CleanUpDllsForProcess();
  if ( (g_CleanupFlags & 2) != 0 && IsOle32DllGetClassObjectPresent() )
    DeletePatternAndExtensionTables();
  ProcessUninitTlsCleanup();
  if ( gpWorkChannelProcessInitialize )
  {
    WaitForThreadpoolWorkCallbacks(gpWorkChannelProcessInitialize, 1);
    CloseThreadpoolWork(gpWorkChannelProcessInitialize);
    gpWorkChannelProcessInitialize = 0;
  }
  ExitProcessDiagnostics::g_performedAtLeastOneOutofprocActivationUsingClientAsyncRpc._Storage._Value = 0;
}

```

## disassembly

```asm
0x1800102e0  mov     [rsp+arg_8], rbx
0x1800102e5  push    rdi
0x1800102e6  sub     rsp, 20h
0x1800102ea  mov     rax, gs:30h
0x1800102f3  xor     edi, edi
0x1800102f5  mov     rax, [rax+1758h]
0x1800102fc  mov     [rsp+28h+Tls._pData], rax
0x180010301  test    rax, rax
0x180010304  jnz     short loc_180010319
0x180010306  lea     rcx, [rsp+28h+Tls]; this
0x18001030b  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x180010310  test    eax, eax
0x180010312  js      short loc_180010334
0x180010314  mov     rax, [rsp+28h+Tls._pData]
0x180010319  test    byte ptr [rax+14h], 80h
0x18001031d  jz      short loc_180010334
0x18001031f  call    IsOle32DllGetClassObjectPresent
0x180010324  test    al, al
0x180010326  jz      short loc_180010334
0x180010328  call    cs:__imp_ClipboardProcessUninitialize
0x18001032e  call    cs:__imp_OleReleaseEnumVerbCache
0x180010334  mov     r8d, 0ABAh; dwLine
0x18001033a  lea     rdx, aOnecoreComComb_89; "onecore\\com\\combase\\objact\\actvator"...
0x180010341  lea     rcx, ?_mxsAptTblLock@CApartmentHashTable@@0VCOleStaticMutexSem@@A; this
0x180010348  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x18001034d  cmp     cs:?gApartmentTbl@@3VCApartmentHashTable@@A._fTableInitialized, edi; CApartmentHashTable gApartmentTbl ...
0x180010353  jz      short loc_180010373
0x180010355  mov     rax, cs:?gApartmentTbl@@3VCApartmentHashTable@@A._hashtbl.__vftable; CApartmentHashTable gApartmentTbl ...
0x18001035c  lea     rdx, ?DestroyOptionalRanking@?$RankingType@VEffectiveClsctxRanking@CPackagedComCatalog@@@EntryLookup@CPackagedComCatalog@@UEBAXAEAUOptionalRankingGeneric@23@@Z; CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking(CPackagedComCatalog::EntryLookup::OptionalRankingGeneric &)
0x180010363  lea     rcx, ?gApartmentTbl@@3VCApartmentHashTable@@A; CApartmentHashTable gApartmentTbl
0x18001036a  mov     rax, [rax+10h]
0x18001036e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010373  lea     rcx, ?_mxsAptTblLock@CApartmentHashTable@@0VCOleStaticMutexSem@@A; this
0x18001037a  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x18001037f  mov     rcx, cs:?gCausality@CausalityTraceState@Diagnostics@Foundation@Windows@@0PEAV1234@EA; Windows::Foundation::Diagnostics::CausalityTraceState * Windows::Foundation::Diagnostics::CausalityTraceState::gCausality
0x180010386  test    rcx, rcx
0x180010389  jz      short loc_18001039E
0x18001038b  mov     rax, [rcx]
0x18001038e  mov     rax, [rax+10h]
0x180010392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010397  mov     cs:?gCausality@CausalityTraceState@Diagnostics@Foundation@Windows@@0PEAV1234@EA, rdi; Windows::Foundation::Diagnostics::CausalityTraceState * Windows::Foundation::Diagnostics::CausalityTraceState::gCausality
0x18001039e  cmp     cs:?_InUseList@CGIPTable@@0V?$CListBase@$0A@$00@@A._first, rdi; CListBase<0,1> CGIPTable::_InUseList ...
0x1800103a5  jz      short loc_1800103BE
0x1800103a7  mov     rcx, [rsp+28h]; callerReturnAddress
0x1800103ac  lea     r8, aOnecoreComComb_86; "onecore\\com\\combase\\dcomrem\\giptbl."...
0x1800103b3  mov     edx, 27Eh; lineNumber
0x1800103b8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800103be  mov     eax, cs:g_CleanupFlags
0x1800103c4  test    al, 1
0x1800103c6  jz      short loc_1800103D7
0x1800103c8  call    IsOle32DllGetClassObjectPresent
0x1800103cd  test    al, al
0x1800103cf  jz      short loc_1800103D7
0x1800103d1  call    cs:__imp_DestroyRunningObjectTable
0x1800103d7  mov     rax, cs:?g_pMgot@@3REAVCMachineGlobalObjectTable@@EA; CMachineGlobalObjectTable * g_pMgot
0x1800103de  test    rax, rax
0x1800103e1  jz      short loc_180010409
0x1800103e3  mov     rcx, cs:?g_pMgot@@3REAVCMachineGlobalObjectTable@@EA; this
0x1800103ea  call    ?VerifyEmpty@CMachineGlobalObjectTable@@QEAAXXZ; CMachineGlobalObjectTable::VerifyEmpty(void)
0x1800103ef  mov     rcx, cs:?g_pMgot@@3REAVCMachineGlobalObjectTable@@EA; CMachineGlobalObjectTable * g_pMgot
0x1800103f6  mov     rax, [rcx]
0x1800103f9  mov     rax, [rax+10h]
0x1800103fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010402  mov     cs:?g_pMgot@@3REAVCMachineGlobalObjectTable@@EA, rdi; CMachineGlobalObjectTable * g_pMgot
0x180010409  mov     r8d, 20Fh; dwLine
0x18001040f  lea     rdx, aOnecoreComComb_59; "onecore\\com\\combase\\dcomrem\\crossct"...
0x180010416  lea     rcx, ?gComLock@@3VCOleStaticMutexSem@@A; this
0x18001041d  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x180010422  cmp     cs:?s_fInitialized@CStdWrapper@@0HA, edi; int CStdWrapper::s_fInitialized
0x180010428  jz      short loc_18001045B
0x18001042a  cmp     cs:?s_cObjects@CStdWrapper@@0KA, edi; ulong CStdWrapper::s_cObjects
0x180010430  jnz     short loc_180010437
0x180010432  call    ?PrivateCleanup@CStdWrapper@@CAXXZ; CStdWrapper::PrivateCleanup(void)
0x180010437  lea     rdx, ?DestroyOptionalRanking@?$RankingType@VEffectiveClsctxRanking@CPackagedComCatalog@@@EntryLookup@CPackagedComCatalog@@UEBAXAEAUOptionalRankingGeneric@23@@Z; pfnCleanup
0x18001043e  lea     rcx, ?s_PIDHashTbl@CPIDTable@@0VCPIDHashTable@@A; this
0x180010445  call    ?Cleanup@CHashTable@@UEAAXP6AXPEAUSHashChain@@@Z@Z; CHashTable::Cleanup(void (*)(SHashChain *))
0x18001044a  mov     cs:?s_fInitialized@CPIDTable@@0HA, edi; int CPIDTable::s_fInitialized
0x180010450  call    ?Cleanup@COIDTable@@SAXXZ; COIDTable::Cleanup(void)
0x180010455  mov     cs:?s_fInitialized@CStdWrapper@@0HA, edi; int CStdWrapper::s_fInitialized
0x18001045b  lea     rcx, ?gComLock@@3VCOleStaticMutexSem@@A; this
0x180010462  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x180010467  call    ChannelProcessUninitialize
0x18001046c  call    ?UninitializeSecurity@@YAXXZ; UninitializeSecurity(void)
0x180010471  cmp     cs:?g_bInitialized@@3HA, edi; int g_bInitialized
0x180010477  jz      short loc_180010492
0x180010479  mov     rcx, cs:?g_pIMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pIMalloc
0x180010480  mov     rax, [rcx]
0x180010483  mov     rax, [rax+10h]
0x180010487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001048c  mov     cs:?g_bInitialized@@3HA, edi; int g_bInitialized
0x180010492  cmp     cs:?g_bServerLockInitialized@@3HA, edi; int g_bServerLockInitialized
0x180010498  jz      short loc_1800104AD
0x18001049a  lea     rcx, ?g_ServerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800104a1  call    cs:__imp_DeleteCriticalSection
0x1800104a7  mov     cs:?g_bServerLockInitialized@@3HA, edi; int g_bServerLockInitialized
0x1800104ad  test    byte ptr cs:?_dwFlags@CClassCache@@2KA, 1; ulong CClassCache::_dwFlags
0x1800104b4  jz      short loc_1800104BB
0x1800104b6  call    ?ReleaseCatalogObjects@CClassCache@@SAXXZ; CClassCache::ReleaseCatalogObjects(void)
0x1800104bb  mov     rbx, rdi
0x1800104be  xchg    rbx, cs:?gpCatalog@@3PEAUIComCatalog@@EA; IComCatalog * gpCatalog
0x1800104c5  test    rbx, rbx
0x1800104c8  jz      short loc_1800104E8
0x1800104ca  mov     rax, [rbx]
0x1800104cd  mov     rcx, rbx
0x1800104d0  mov     rax, [rax+58h]
0x1800104d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104d9  mov     rax, [rbx]
0x1800104dc  mov     rcx, rbx
0x1800104df  mov     rax, [rax+10h]
0x1800104e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; __annotation("WILSTG:|51593804|Feature_PackagedComElevationSupport|EnabledByDefault")
0x1800104ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800104f4  test    al, al
0x1800104f6  jz      short loc_180010523
0x1800104f8  lea     rbx, ?g_comDependenciesOnPackagesLock@@3Vsrwlock@wil@@A; wil::srwlock g_comDependenciesOnPackagesLock
0x1800104ff  mov     rcx, rbx; SRWLock
0x180010502  call    cs:__imp_AcquireSRWLockExclusive
0x180010508  lea     rcx, ?g_comDependenciesOnPackages@@3V?$ReferencedPtr@VComDependenciesOnPackages@@@ObjectLibrary@@A; this
0x18001050f  mov     [rsp+28h+Tls._pData], rbx
0x180010514  call    ?InternalRelease@?$ReferencedPtr@VComDependenciesOnPackages@@@ObjectLibrary@@AEAAXXZ; ObjectLibrary::ReferencedPtr<ComDependenciesOnPackages>::InternalRelease(void)
0x180010519  lea     rcx, [rsp+28h+Tls]; this
0x18001051e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010523  lea     rcx, ?g_unmarshalersTable@@3VUnmarshalersTable@@A; SRWLock
0x18001052a  call    cs:__imp_AcquireSRWLockExclusive
0x180010530  mov     rbx, cs:?g_unmarshalersTable@@3VUnmarshalersTable@@A._pRoot; UnmarshalersTable g_unmarshalersTable ...
0x180010537  mov     [rsp+28h+Tls._pData], rbx
0x18001053c  jmp     short loc_18001055E
0x18001053e  lea     rdx, [rsp+28h+Tls]; Root
0x180010543  mov     rcx, rbx; Links
0x180010546  call    cs:__imp_RtlDeleteNoSplay
0x18001054c  mov     edx, 30h ; '0'; __formal
0x180010551  mov     rcx, rbx; block
0x180010554  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010559  mov     rbx, [rsp+28h+Tls._pData]
0x18001055e  test    rbx, rbx
0x180010561  jnz     short loc_18001053E
0x180010563  lea     rcx, ?g_unmarshalersTable@@3VUnmarshalersTable@@A; SRWLock
0x18001056a  mov     cs:?g_unmarshalersTable@@3VUnmarshalersTable@@A._pRoot, rdi; UnmarshalersTable g_unmarshalersTable ...
0x180010571  call    cs:__imp_ReleaseSRWLockExclusive
0x180010577  test    byte ptr cs:?_dwFlags@CClassCache@@2KA, 1; ulong CClassCache::_dwFlags
0x18001057e  jz      short loc_180010585
0x180010580  call    ?CleanUpDllsForProcess@CClassCache@@SAJXZ; CClassCache::CleanUpDllsForProcess(void)
0x180010585  mov     eax, cs:g_CleanupFlags
0x18001058b  test    al, 2
0x18001058d  jz      short loc_18001059E
0x18001058f  call    IsOle32DllGetClassObjectPresent
0x180010594  test    al, al
0x180010596  jz      short loc_18001059E
0x180010598  call    cs:__imp_DeletePatternAndExtensionTables
0x18001059e  call    ?ProcessUninitTlsCleanup@@YAXXZ; ProcessUninitTlsCleanup(void)
0x1800105a3  mov     rcx, cs:?gpWorkChannelProcessInitialize@@3PEAU_TP_WORK@@EA; pwk
0x1800105aa  test    rcx, rcx
0x1800105ad  jz      short loc_1800105CE
0x1800105af  mov     edx, 1; fCancelPendingCallbacks
0x1800105b4  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800105ba  mov     rcx, cs:?gpWorkChannelProcessInitialize@@3PEAU_TP_WORK@@EA; pwk
0x1800105c1  call    cs:__imp_CloseThreadpoolWork
0x1800105c7  mov     cs:?gpWorkChannelProcessInitialize@@3PEAU_TP_WORK@@EA, rdi; _TP_WORK * gpWorkChannelProcessInitialize
0x1800105ce  mov     rbx, [rsp+28h+arg_8]
0x1800105d3  mov     eax, edi
0x1800105d5  xchg    al, cs:?g_performedAtLeastOneOutofprocActivationUsingClientAsyncRpc@ExitProcessDiagnostics@@3U?$atomic@_N@std@@A._Storage._Value; std::atomic<bool> ExitProcessDiagnostics::g_performedAtLeastOneOutofprocActivationUsingClientAsyncRpc ...
0x1800105db  add     rsp, 20h
0x1800105df  pop     rdi
0x1800105e0  retn
```

# AddPackageDependency2

- ea: `0x180116430`
- end: `0x180116bd5`
- name: `AddPackageDependency2`
- size: `1957`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180116410`

## callees

- `0x1800025a4`
- `0x18000e3e0`
- `0x18000fb1c`
- `0x1800104b4`
- `0x180010ffc`
- `0x180012c04`
- `0x180014a40`
- `0x1800150f4`
- `0x1800152e0`
- `0x1800154e4`
- `0x18001552c`
- `0x1800192d8`
- `0x180019604`
- `0x18002d7e0`
- `0x180058da8`
- `0x18005997c`
- `0x18005b2c4`
- `0x1800971c0`
- `0x1800a8c88`
- `0x1800e3b8c`
- `0x1800ecbec`
- `0x1800f5220`
- `0x18010d334`
- `0x18010e804`
- `0x180113630`
- `0x1801137f8`
- `0x180116430`
- `0x180156828`
- `0x180156b60`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRAddPackageDependency` at `0x1801164e8`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRAddPackageDependency` at `0x1801164e8`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116589`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18011661f`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116725`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116840`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x1801169d9`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116ae8`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116b70`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116589`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18011661f`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116725`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116840`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x1801169d9`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116ae8`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x180116b70`

## pseudocode

```c
__int64 __fastcall AddPackageDependency2(char *a1, int a2, unsigned int a3, _QWORD *a4, LPWCH *a5)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  LPWCH *v11; // r12
  WCHAR *v12; // rcx
  unsigned __int16 **v13; // r9
  int v14; // eax
  int v15; // eax
  struct _EVENT_DATA_DESCRIPTOR *v16; // rbx
  int v17; // eax
  unsigned int v18; // edi
  int v19; // eax
  struct ARI::DependencyMiniRepository::_HEADER *v20; // rsi
  int v21; // eax
  struct _EVENT_DATA_DESCRIPTOR *v22; // rcx
  ARI::ProcessPackageGraphEntry *v23; // rax
  struct ARI::ProcessPackageGraphEntry *v24; // rax
  struct ARI::ProcessPackageGraphEntry *v25; // rdi
  const unsigned __int16 *v26; // rdx
  int DependencyMiniRepository; // esi
  __int64 v28; // rdx
  int v29; // eax
  WCHAR *v30; // rcx
  ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH *v31; // rsi
  __int64 v32; // rdx
  const struct ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH_NODE *Node; // rax
  const WCHAR *FullName; // rax
  __int64 v35; // rcx
  bool v36; // dl
  int v37; // eax
  WCHAR *v38; // rcx
  int v39; // eax
  struct ARI::ProcessPackageGraphEntry **v40; // rcx
  signed __int32 v41; // esi
  int updated; // eax
  unsigned int v43; // r14d
  int v44; // r8d
  const unsigned __int16 *v45; // r9
  struct ARI::ProcessPackageGraphEntry **v46; // rcx
  int v47; // eax
  int v48; // eax
  WCHAR *v49; // rcx
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  int v53; // eax
  WCHAR *v54; // rcx
  int v55; // eax
  WCHAR *v56; // rcx
  void **bIgnoreCase; // [rsp+28h] [rbp-71h]
  int bIgnoreCasea; // [rsp+28h] [rbp-71h]
  int bIgnoreCaseb; // [rsp+28h] [rbp-71h]
  int bIgnoreCasec; // [rsp+28h] [rbp-71h]
  int bIgnoreCased; // [rsp+28h] [rbp-71h]
  int bIgnoreCasee; // [rsp+28h] [rbp-71h]
  int bIgnoreCasef; // [rsp+28h] [rbp-71h]
  int bIgnoreCaseg; // [rsp+28h] [rbp-71h]
  const void *v65; // [rsp+38h] [rbp-61h]
  LPWCH penv; // [rsp+58h] [rbp-41h] BYREF
  __int64 v67; // [rsp+60h] [rbp-39h] BYREF
  void *v68; // [rsp+68h] [rbp-31h] BYREF
  char v69[8]; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 v70[4]; // [rsp+78h] [rbp-21h] BYREF
  struct ARI::DependencyMiniRepository::_HEADER *Src; // [rsp+80h] [rbp-19h] BYREF
  __int64 v72; // [rsp+88h] [rbp-11h] BYREF
  LPWCH v73; // [rsp+90h] [rbp-9h] BYREF
  int v74[2]; // [rsp+98h] [rbp-1h] BYREF
  LPWCH *p_penv; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v76; // [rsp+A8h] [rbp+Fh] BYREF
  char v77; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+57h]
  PVOID P; // [rsp+F8h] [rbp+5Fh] BYREF
  int v80; // [rsp+100h] [rbp+67h]
  unsigned int v81; // [rsp+108h] [rbp+6Fh]

  v81 = a3;
  v80 = a2;
  if ( !a1 )
  {
    v8 = 680;
LABEL_3:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)0x80070057LL,
      (int)bIgnoreCase);
    return v9;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl'::`2'::impl)
    && !*(_WORD *)a1 )
  {
    v8 = 683;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 685;
    goto LABEL_3;
  }
  v11 = a5;
  *a4 = 0;
  if ( v11 )
    *v11 = 0;
  v67 = 0;
  p_penv = &penv;
  penv = 0;
  v76 = 0;
  v77 = 1;
  v9 = SRAddPackageDependency(a1, a3, &v67, &v76);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>(&p_penv);
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BC,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)v9,
      (int)bIgnoreCase);
LABEL_14:
    v12 = penv;
    penv = 0;
    if ( v12 )
      FreeEnvironmentStringsW(v12);
    return v9;
  }
  wil::AcquireSRWLockExclusive(v69, &ARI::Globals::s_packageInfoLock);
  P = 0;
  v14 = ARI::DependencyMiniRepository::BuildFilenameForPackage(0, penv, (const unsigned __int16 *)&P, v13);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C9,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)v14,
      (int)bIgnoreCase);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(P);
    if ( v67 )
    {
      v15 = SRRemovePackageDependency();
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v15,
          bIgnoreCasea);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v69);
    goto LABEL_14;
  }
  v16 = (struct _EVENT_DATA_DESCRIPTOR *)P;
  *(_QWORD *)v70 = 0;
  Src = 0;
  v68 = (void *)-1LL;
  v17 = ARI::DependencyMiniRepository::Open(
          (struct _EVENT_DATA_DESCRIPTOR *)P,
          v70,
          (unsigned __int64 *)&Src,
          &v68,
          bIgnoreCase);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CD,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)v17,
      bIgnoreCaseb);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v67 )
    {
      v19 = SRRemovePackageDependency();
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v19,
          bIgnoreCasec);
    }
LABEL_93:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v69);
    v56 = penv;
    penv = 0;
    if ( v56 )
      FreeEnvironmentStringsW(v56);
    return v18;
  }
  v20 = Src;
  v21 = ARI::DependencyMiniRepository::_HEADER::Verify(Src, *(unsigned __int64 *)v70);
  v18 = v21;
  if ( v21 < 0 )
  {
    v22 = (struct _EVENT_DATA_DESCRIPTOR *)&stru_18029C360;
    if ( v16 )
      v22 = v16;
    ARI::DependencyMiniRepository::LogDMRCorrupt(
      v22,
      (const unsigned __int16 *)(unsigned int)v21,
      *(int *)v70,
      0,
      0x38495241u,
      (unsigned int)v20,
      v65);
    goto LABEL_90;
  }
  v23 = (ARI::ProcessPackageGraphEntry *)ARI::Allocate<unsigned char>(208);
  if ( !v23
    || (v24 = (struct ARI::ProcessPackageGraphEntry *)ARI::ProcessPackageGraphEntry::ProcessPackageGraphEntry(v23),
        (v25 = v24) == 0) )
  {
    v18 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCaseb);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
LABEL_90:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v67 )
    {
      v55 = SRRemovePackageDependency();
      if ( v55 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v55,
          bIgnoreCased);
    }
    goto LABEL_93;
  }
  v26 = (const unsigned __int16 *)&stru_18029C360;
  if ( v16 )
    v26 = (const unsigned __int16 *)v16;
  DependencyMiniRepository = ARI::Globals::LoadDependencyMiniRepository(v20, v26, v24);
  if ( DependencyMiniRepository < 0 )
  {
    v28 = 728;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)DependencyMiniRepository,
      bIgnoreCaseb);
    goto LABEL_37;
  }
  v31 = (ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH *)*((_QWORD *)v25 + 13);
  if ( !v31 )
  {
    v32 = 731;
    goto LABEL_53;
  }
  Node = ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH::GetNode(
           *((ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH **)v25 + 13),
           0);
  if ( !Node )
  {
    v32 = 733;
    goto LABEL_53;
  }
  FullName = ARI::DependencyMiniRepository::_PACKAGE_IDENTITY::GetFullName((const struct ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH_NODE *)((char *)Node + 8));
  if ( CompareStringOrdinal(FullName, (*(unsigned __int16 *)(v35 + 30) >> 1) - 1, penv, -1, 1) != 2 )
  {
    v32 = 734;
    goto LABEL_53;
  }
  LODWORD(P) = 0;
  DependencyMiniRepository = ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH::CountPackageFamilyInGraphByPackageFullName(
                               v31,
                               penv,
                               (unsigned int *)&P);
  if ( DependencyMiniRepository < 0 )
  {
    v28 = 736;
    goto LABEL_36;
  }
  if ( !(_DWORD)P )
  {
    v32 = 737;
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)0x8000FFFFLL,
      bIgnoreCaseb);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v25);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v67 )
    {
      v37 = SRRemovePackageDependency();
      if ( v37 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v37,
          bIgnoreCasef);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v69);
    v38 = penv;
    penv = 0;
    if ( v38 )
      FreeEnvironmentStringsW(v38);
    return 2147549183LL;
  }
  if ( (a3 & 2) != 0 )
  {
    *((_DWORD *)v25 + 6) = (_DWORD)P;
    ARI::ProcessPackageGraphEntry::SetAlternatePathForLoaderIsFirstPackageFamily(v25, v36);
  }
  v39 = v80;
  *((_DWORD *)v25 + 4) |= 8u;
  *((_DWORD *)v25 + 5) = v39;
  *((_QWORD *)v25 + 4) = v67;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl'::`2'::impl) )
  {
    DependencyMiniRepository = ARI::ProcessPackageGraphEntry::SetDependencyGraphId(v25, (const unsigned __int16 *)a1);
    if ( DependencyMiniRepository < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2F0,
        (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
        (const char *)(unsigned int)DependencyMiniRepository,
        (int)"%ls",
        a1);
LABEL_37:
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v25);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
      if ( v67 )
      {
        v29 = SRRemovePackageDependency();
        if ( v29 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2C3,
            (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
            (const char *)(unsigned int)v29,
            bIgnoreCasee);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v69);
      v30 = penv;
      penv = 0;
      if ( v30 )
        FreeEnvironmentStringsW(v30);
      return (unsigned int)DependencyMiniRepository;
    }
  }
  P = 0;
  DependencyMiniRepository = ARI::ProcessPackageGraphEntry::Insert(
                               v40,
                               v25,
                               a3 & 1,
                               (struct ARI::ProcessPackageGraphEntry **)&P);
  if ( DependencyMiniRepository < 0 )
  {
    v28 = 758;
    goto LABEL_36;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl'::`2'::impl) )
  {
    v41 = _InterlockedIncrement((volatile signed __int32 *)&ARI::Globals::s_generationId);
  }
  else
  {
    v41 = 0;
    _InterlockedAdd((volatile signed __int32 *)&ARI::Globals::s_generationId, 1u);
  }
  updated = ARI::Globals::UpdateLoaderAlternatePath();
  v43 = updated;
  if ( updated >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl'::`2'::impl)
      && (unsigned int)dword_1803A4CD8 > 4 )
    {
      v73 = penv;
      LODWORD(Src) = v81;
      *(_DWORD *)v70 = v80;
      v72 = 0x1000000;
      LODWORD(P) = v41;
      *(_QWORD *)v74 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v50,
        (unsigned int)&byte_180362A9F,
        v51,
        v52,
        (__int64)v74,
        (__int64)v70,
        (__int64)&Src,
        (__int64)&v73,
        (__int64)&P,
        (__int64)&v72);
    }
    *a4 = v67;
    v67 = 0;
    if ( v11 )
    {
      *v11 = penv;
      penv = 0;
    }
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v67 )
    {
      v53 = SRRemovePackageDependency();
      if ( v53 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v53,
          bIgnoreCaseb);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v69);
    v54 = penv;
    penv = 0;
    if ( v54 )
      FreeEnvironmentStringsW(v54);
    return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x305,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)updated,
      bIgnoreCaseb);
    ARI::DependencyMiniRepository::LogDMRRefreshPackageInfoFailed(v16, (const unsigned __int16 *)v43, v44, v45);
    v47 = ARI::ProcessPackageGraphEntry::Remove(v46, v25, (struct ARI::ProcessPackageGraphEntry *)P);
    if ( v47 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x309,
        (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
        (const char *)(unsigned int)v47,
        bIgnoreCaseg);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v68);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v67 )
    {
      v48 = SRRemovePackageDependency();
      if ( v48 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v48,
          bIgnoreCaseg);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v69);
    v49 = penv;
    penv = 0;
    if ( v49 )
      FreeEnvironmentStringsW(v49);
    return v43;
  }
}

```

## disassembly

```asm
0x180116430  mov     rax, rsp
0x180116433  mov     [rax+20h], rbx
0x180116437  mov     [rax+18h], r8d
0x18011643b  mov     [rax+10h], edx
0x18011643e  push    rbp
0x18011643f  push    rsi
0x180116440  push    rdi
0x180116441  push    r12
0x180116443  push    r13
0x180116445  push    r14
0x180116447  push    r15
0x180116449  lea     rbp, [rax-57h]
0x18011644d  sub     rsp, 0B0h
0x180116454  xor     esi, esi
0x180116456  mov     r13, r9
0x180116459  mov     r14d, r8d
0x18011645c  mov     r15, rcx
0x18011645f  test    rcx, rcx
0x180116462  jnz     short loc_180116488
0x180116464  mov     edx, 2A8h; void *
0x180116469  mov     rcx, [rbp+57h]; this
0x18011646d  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x180116474  mov     ebx, 80070057h
0x180116479  mov     r9d, ebx; char *
0x18011647c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116481  mov     eax, ebx
0x180116483  jmp     loc_180116BB9
0x180116488  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2> `wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl(void)'::`2'::impl
0x18011648f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(void)
0x180116494  test    al, al
0x180116496  jz      short loc_1801164A5
0x180116498  cmp     [r15], si
0x18011649c  jnz     short loc_1801164A5
0x18011649e  mov     edx, 2ABh
0x1801164a3  jmp     short loc_180116469
0x1801164a5  test    r13, r13
0x1801164a8  jnz     short loc_1801164B1
0x1801164aa  mov     edx, 2ADh
0x1801164af  jmp     short loc_180116469
0x1801164b1  mov     r12, [rbp+4Fh+arg_20]
0x1801164b5  mov     [r13+0], rsi
0x1801164b9  test    r12, r12
0x1801164bc  jz      short loc_1801164C2
0x1801164be  mov     [r12], rsi
0x1801164c2  lea     rax, [rbp+4Fh+penv]
0x1801164c6  mov     [rbp+4Fh+var_88], rsi
0x1801164ca  lea     r9, [rbp+4Fh+var_40]
0x1801164ce  mov     [rbp+4Fh+var_48], rax
0x1801164d2  lea     r8, [rbp+4Fh+var_88]
0x1801164d6  mov     [rbp+4Fh+penv], rsi
0x1801164da  mov     edx, r14d
0x1801164dd  mov     [rbp+4Fh+var_40], rsi
0x1801164e1  mov     rcx, r15
0x1801164e4  mov     [rbp+4Fh+var_38], 1
0x1801164e8  call    cs:__imp_SRAddPackageDependency
0x1801164ef  nop     dword ptr [rax+rax+00h]
0x1801164f4  lea     rcx, [rbp+4Fh+var_48]
0x1801164f8  mov     ebx, eax
0x1801164fa  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>(void)
0x1801164ff  test    ebx, ebx
0x180116501  jns     short loc_180116536
0x180116503  mov     rcx, [rbp+57h]; this
0x180116507  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18011650e  mov     r9d, ebx; char *
0x180116511  mov     edx, 2BCh; void *
0x180116516  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011651b  mov     rcx, [rbp+4Fh+penv]; penv
0x18011651f  mov     [rbp+4Fh+penv], rsi
0x180116523  test    rcx, rcx
0x180116526  jz      loc_180116481
0x18011652c  call    FreeEnvironmentStringsW
0x180116531  jmp     loc_180116481
0x180116536  lea     rdx, ?s_packageInfoLock@Globals@ARI@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK ARI::Globals::s_packageInfoLock
0x18011653d  lea     rcx, [rbp+4Fh+var_78]
0x180116541  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180116546  mov     rdx, [rbp+4Fh+penv]; void *
0x18011654a  lea     r8, [rbp+4Fh+P]; unsigned __int16 *
0x18011654e  xor     ecx, ecx; this
0x180116550  mov     [rbp+4Fh+P], rsi
0x180116554  call    ?BuildFilenameForPackage@DependencyMiniRepository@ARI@@YAJPEAXPEBGPEAPEAG@Z; ARI::DependencyMiniRepository::BuildFilenameForPackage(void *,ushort const *,ushort * *)
0x180116559  mov     ebx, eax
0x18011655b  test    eax, eax
0x18011655d  jns     short loc_1801165BF
0x18011655f  mov     rcx, [rbp+57h]; this
0x180116563  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18011656a  mov     r9d, eax; char *
0x18011656d  mov     edx, 2C9h; void *
0x180116572  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116577  mov     rcx, [rbp+4Fh+P]; P
0x18011657b  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180116580  mov     rcx, [rbp+4Fh+var_88]
0x180116584  test    rcx, rcx
0x180116587  jz      short loc_1801165B1
0x180116589  call    cs:__imp_SRRemovePackageDependency
0x180116590  nop     dword ptr [rax+rax+00h]
0x180116595  test    eax, eax
0x180116597  jns     short loc_1801165B1
0x180116599  mov     rcx, [rbp+57h]; this
0x18011659d  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x1801165a4  mov     r9d, eax; char *
0x1801165a7  mov     edx, 2C3h; void *
0x1801165ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801165b1  lea     rcx, [rbp+4Fh+var_78]
0x1801165b5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801165ba  jmp     loc_18011651B
0x1801165bf  mov     rbx, [rbp+4Fh+P]
0x1801165c3  lea     r9, [rbp+4Fh+var_80]; void **
0x1801165c7  mov     rcx, rbx; this
0x1801165ca  mov     qword ptr [rbp+4Fh+var_70], rsi
0x1801165ce  lea     r8, [rbp+4Fh+Src]; unsigned __int64 *
0x1801165d2  mov     [rbp+4Fh+Src], rsi
0x1801165d6  lea     rdx, [rbp+4Fh+var_70]; unsigned __int16 *
0x1801165da  mov     [rbp+4Fh+var_80], 0FFFFFFFFFFFFFFFFh
0x1801165e2  call    ?Open@DependencyMiniRepository@ARI@@YAJPEBGPEA_KPEAPEAX2@Z; ARI::DependencyMiniRepository::Open(ushort const *,unsigned __int64 *,void * *,void * *)
0x1801165e7  mov     edi, eax
0x1801165e9  test    eax, eax
0x1801165eb  jns     short loc_18011665D
0x1801165ed  mov     rcx, [rbp+57h]; this
0x1801165f1  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x1801165f8  mov     r9d, eax; char *
0x1801165fb  mov     edx, 2CDh; void *
0x180116600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116605  lea     rcx, [rbp+4Fh+var_80]
0x180116609  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011660e  mov     rcx, rbx; P
0x180116611  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180116616  mov     rcx, [rbp+4Fh+var_88]
0x18011661a  test    rcx, rcx
0x18011661d  jz      short loc_180116647
0x18011661f  call    cs:__imp_SRRemovePackageDependency
0x180116626  nop     dword ptr [rax+rax+00h]
0x18011662b  test    eax, eax
0x18011662d  jns     short loc_180116647
0x18011662f  mov     rcx, [rbp+57h]; this
0x180116633  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18011663a  mov     r9d, eax; char *
0x18011663d  mov     edx, 2C3h; void *
0x180116642  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180116647  lea     rcx, [rbp+4Fh+var_78]
0x18011664b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180116650  mov     rcx, [rbp+4Fh+penv]
0x180116654  mov     [rbp+4Fh+penv], rsi
0x180116658  jmp     loc_180116BAD
0x18011665d  mov     rsi, [rbp+4Fh+Src]
0x180116661  mov     rdx, qword ptr [rbp+4Fh+var_70]; unsigned __int64
0x180116665  mov     rcx, rsi; this
0x180116668  call    ?Verify@_HEADER@DependencyMiniRepository@ARI@@QEBAJ_K@Z; ARI::DependencyMiniRepository::_HEADER::Verify(unsigned __int64)
0x18011666d  mov     edi, eax
0x18011666f  test    eax, eax
0x180116671  jns     short loc_1801166A1
0x180116673  mov     r8, qword ptr [rbp+4Fh+var_70]; int
0x180116677  lea     rcx, stru_18029C360
0x18011667e  test    rbx, rbx
0x180116681  mov     [rsp+0E0h+var_B8], rsi; unsigned int
0x180116686  mov     edx, eax; unsigned __int16 *
0x180116688  mov     [rsp+0E0h+bIgnoreCase], 38495241h; unsigned int
0x180116690  cmovnz  rcx, rbx; this
0x180116694  xor     r9d, r9d; unsigned __int64
0x180116697  call    ?LogDMRCorrupt@DependencyMiniRepository@ARI@@YAXPEBGJ_KIIPEBX@Z; ARI::DependencyMiniRepository::LogDMRCorrupt(ushort const *,long,unsigned __int64,uint,uint,void const *)
0x18011669c  jmp     loc_180116B56
0x1801166a1  mov     ecx, 0D0h
0x1801166a6  call    ??$Allocate@E@ARI@@YAPEAE_K@Z; ARI::Allocate<uchar>(unsigned __int64)
0x1801166ab  test    rax, rax
0x1801166ae  jz      loc_180116B32
0x1801166b4  mov     rcx, rax; this
0x1801166b7  call    ??0ProcessPackageGraphEntry@ARI@@QEAA@XZ; ARI::ProcessPackageGraphEntry::ProcessPackageGraphEntry(void)
0x1801166bc  mov     rdi, rax
0x1801166bf  test    rax, rax
0x1801166c2  jz      loc_180116B32
0x1801166c8  test    rbx, rbx
0x1801166cb  lea     rdx, stru_18029C360
0x1801166d2  mov     r8, rax; struct ARI::ProcessPackageGraphEntry *
0x1801166d5  mov     rcx, rsi; Src
0x1801166d8  cmovnz  rdx, rbx; unsigned __int16 *
0x1801166dc  call    ?LoadDependencyMiniRepository@Globals@ARI@@SAJPEAU_HEADER@DependencyMiniRepository@2@PEBGPEAVProcessPackageGraphEntry@2@@Z; ARI::Globals::LoadDependencyMiniRepository(ARI::DependencyMiniRepository::_HEADER *,ushort const *,ARI::ProcessPackageGraphEntry *)
0x1801166e1  mov     esi, eax
0x1801166e3  test    eax, eax
0x1801166e5  jns     loc_180116773
0x1801166eb  mov     edx, 2D8h; void *
0x1801166f0  mov     rcx, [rbp+57h]; this
0x1801166f4  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x1801166fb  mov     r9d, esi; char *
0x1801166fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116703  mov     rcx, rdi; P
0x180116706  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18011670b  lea     rcx, [rbp+4Fh+var_80]
0x18011670f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180116714  mov     rcx, rbx; P
0x180116717  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18011671c  mov     rcx, [rbp+4Fh+var_88]
0x180116720  test    rcx, rcx
0x180116723  jz      short loc_18011674D
0x180116725  call    cs:__imp_SRRemovePackageDependency
0x18011672c  nop     dword ptr [rax+rax+00h]
0x180116731  test    eax, eax
0x180116733  jns     short loc_18011674D
0x180116735  mov     rcx, [rbp+57h]; this
0x180116739  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x180116740  mov     r9d, eax; char *
0x180116743  mov     edx, 2C3h; void *
0x180116748  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18011674d  lea     rcx, [rbp+4Fh+var_78]
0x180116751  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180116756  mov     rcx, [rbp+4Fh+penv]; penv
0x18011675a  mov     [rbp+4Fh+penv], 0
0x180116762  test    rcx, rcx
0x180116765  jz      short loc_18011676C
0x180116767  call    FreeEnvironmentStringsW
0x18011676c  mov     eax, esi
0x18011676e  jmp     loc_180116BB9
0x180116773  mov     rsi, [rdi+68h]
0x180116777  test    rsi, rsi
0x18011677a  jnz     short loc_180116786
0x18011677c  mov     edx, 2DBh
0x180116781  jmp     loc_180116808
0x180116786  xor     edx, edx; unsigned int
0x180116788  mov     rcx, rsi; this
0x18011678b  call    ?GetNode@_DEPENDENCY_GRAPH@DependencyMiniRepository@ARI@@QEBAPEBU_DEPENDENCY_GRAPH_NODE@23@I@Z; ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH::GetNode(uint)
0x180116790  test    rax, rax
0x180116793  jnz     short loc_18011679C
0x180116795  mov     edx, 2DDh
0x18011679a  jmp     short loc_180116808
0x18011679c  lea     rcx, [rax+8]; this
0x1801167a0  call    ?GetFullName@_PACKAGE_IDENTITY@DependencyMiniRepository@ARI@@QEBAPEBGXZ; ARI::DependencyMiniRepository::_PACKAGE_IDENTITY::GetFullName(void)
0x1801167a5  movzx   edx, word ptr [rcx+1Eh]
0x1801167a9  or      r9d, 0FFFFFFFFh; cchCount2
0x1801167ad  mov     r8, [rbp+4Fh+penv]; lpString2
0x1801167b1  mov     rcx, rax; lpString1
0x1801167b4  shr     edx, 1
0x1801167b6  dec     edx; cchCount1
0x1801167b8  mov     [rsp+0E0h+bIgnoreCase], 1; int
0x1801167c0  call    CompareStringOrdinal
0x1801167c5  cmp     eax, 2
0x1801167c8  jz      short loc_1801167D1
0x1801167ca  mov     edx, 2DEh
0x1801167cf  jmp     short loc_180116808
0x1801167d1  mov     rdx, [rbp+4Fh+penv]; unsigned __int16 *
0x1801167d5  lea     r8, [rbp+4Fh+P]; unsigned int *
0x1801167d9  mov     rcx, rsi; this
0x1801167dc  mov     dword ptr [rbp+4Fh+P], 0
0x1801167e3  call    ?CountPackageFamilyInGraphByPackageFullName@_DEPENDENCY_GRAPH@DependencyMiniRepository@ARI@@QEBAJPEBGAEAI@Z; ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH::CountPackageFamilyInGraphByPackageFullName(ushort const *,uint &)
0x1801167e8  mov     esi, eax
0x1801167ea  test    eax, eax
0x1801167ec  jns     short loc_1801167F8
0x1801167ee  mov     edx, 2E0h
0x1801167f3  jmp     loc_1801166F0
0x1801167f8  mov     eax, dword ptr [rbp+4Fh+P]
0x1801167fb  test    eax, eax
0x1801167fd  jnz     loc_180116891
0x180116803  mov     edx, 2E1h; void *
0x180116808  mov     rcx, [rbp+57h]; this
0x18011680c  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x180116813  mov     r9d, 8000FFFFh; char *
0x180116819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011681e  mov     rcx, rdi; P
0x180116821  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180116826  lea     rcx, [rbp+4Fh+var_80]
0x18011682a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011682f  mov     rcx, rbx; P
0x180116832  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180116837  mov     rcx, [rbp+4Fh+var_88]
0x18011683b  test    rcx, rcx
0x18011683e  jz      short loc_180116868
0x180116840  call    cs:__imp_SRRemovePackageDependency
0x180116847  nop     dword ptr [rax+rax+00h]
0x18011684c  test    eax, eax
0x18011684e  jns     short loc_180116868
0x180116850  mov     rcx, [rbp+57h]; this
0x180116854  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18011685b  mov     r9d, eax; char *
0x18011685e  mov     edx, 2C3h; void *
0x180116863  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180116868  lea     rcx, [rbp+4Fh+var_78]
0x18011686c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180116871  mov     rcx, [rbp+4Fh+penv]; penv
0x180116875  mov     [rbp+4Fh+penv], 0
0x18011687d  test    rcx, rcx
0x180116880  jz      short loc_180116887
0x180116882  call    FreeEnvironmentStringsW
0x180116887  mov     eax, 8000FFFFh
0x18011688c  jmp     loc_180116BB9
0x180116891  test    r14b, 2
0x180116895  jz      short loc_1801168A2
0x180116897  mov     rcx, rdi; this
0x18011689a  mov     [rdi+18h], eax
0x18011689d  call    ?SetAlternatePathForLoaderIsFirstPackageFamily@ProcessPackageGraphEntry@ARI@@QEAAX_N@Z; ARI::ProcessPackageGraphEntry::SetAlternatePathForLoaderIsFirstPackageFamily(bool)
0x1801168a2  mov     eax, [rbp+4Fh+arg_8]
0x1801168a5  or      dword ptr [rdi+10h], 8
0x1801168a9  mov     [rdi+14h], eax
0x1801168ac  mov     rax, [rbp+4Fh+var_88]
0x1801168b0  mov     [rdi+20h], rax
0x1801168b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2> `wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl(void)'::`2'::impl
0x1801168bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(void)
0x1801168c0  test    al, al
0x1801168c2  jz      short loc_180116903
0x1801168c4  mov     rdx, r15; unsigned __int16 *
0x1801168c7  mov     rcx, rdi; this
0x1801168ca  call    ?SetDependencyGraphId@ProcessPackageGraphEntry@ARI@@QEAAJPEBG@Z; ARI::ProcessPackageGraphEntry::SetDependencyGraphId(ushort const *)
0x1801168cf  mov     esi, eax
0x1801168d1  test    eax, eax
  ... truncated ...
```

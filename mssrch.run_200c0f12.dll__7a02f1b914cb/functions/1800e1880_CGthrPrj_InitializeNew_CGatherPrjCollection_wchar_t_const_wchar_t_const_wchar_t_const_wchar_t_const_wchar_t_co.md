# CGthrPrj::InitializeNew(CGatherPrjCollection *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int,CGthrPrj *)

- ea: `0x1800e1880`
- end: `0x1800e236e`
- name: `?InitializeNew@CGthrPrj@@QEAAJPEAVCGatherPrjCollection@@PEB_W1111HHPEAV1@@Z`
- size: `2798`
- prototype: `__int64 __usercall@<rax>(CGthrPrj *__hidden this@<rcx>, struct CGatherPrjCollection *@<rdx>, const wchar_t *@<r8>, const wchar_t *@<r9>, const wchar_t *, const wchar_t *, const wchar_t *, int, int, struct CGthrPrj *)`
- caller_count: `1`
- callee_count: `51`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078ac0`

## callees

- `0x18000a23c`
- `0x18000e628`
- `0x1800252e4`
- `0x1800269b0`
- `0x18002751c`
- `0x18003f938`
- `0x1800495c0`
- `0x1800519a4`
- `0x180052254`
- `0x180052c14`
- `0x180052cac`
- `0x180052fd0`
- `0x18005521c`
- `0x1800555f0`
- `0x18006a040`
- `0x18006a618`
- `0x1800800f4`
- `0x180083e54`
- `0x1800865e8`
- `0x18008668c`
- `0x1800ab934`
- `0x1800abe78`
- `0x1800b2ec0`
- `0x1800b500c`
- `0x1800bac50`
- `0x1800bd828`
- `0x1800bef44`
- `0x1800bfb94`
- `0x1800cc8fc`
- `0x1800cdfe8`
- `0x1800ced0c`
- `0x1800cee20`
- `0x1800ceeac`
- `0x1800ceee8`
- `0x1800e1880`
- `0x1800e2374`
- `0x1800e95f0`
- `0x1800fab20`
- `0x18010042c`
- `0x1801010c4`
- `0x18010af54`
- `0x1801244c0`
- `0x180143b2c`
- `0x18016cb08`
- `0x18016d39c`
- `0x180173ed0`
- `0x180207dd4`
- `0x180207ea8`
- `0x180208368`
- `0x180222fd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1d1a`
- `OLEAUT32!__imp_VariantInit` at `0x1800e1a88`
- `OLEAUT32!__imp_VariantInit` at `0x1800e1a88`
- `OLEAUT32!__imp_VariantClear` at `0x1800e222f`
- `OLEAUT32!__imp_VariantClear` at `0x1800e222f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800e22c1`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800e22c1`

## string_xrefs

- `0x1800e1a29`: `StartAddressConfigURL`
- `0x1800e20c0`: `ActivePlugins`
- `0x1800e20f3`: `ActivePlugins`
- `0x1800e2125`: `Plugins`
- `0x1800e2158`: `Plugins`
- `0x1800e1d07`: `WorkingDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CGthrPrj::InitializeNew(
        CGthrPrj *this,
        struct CGatherPrjCollection *a2,
        wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        const wchar_t *a7,
        int a8,
        int a9,
        struct CGthrPrj *a10)
{
  const struct CLMString *v12; // rbx
  char *v13; // rcx
  const struct CLMString *v14; // rax
  int v15; // ebx
  const struct CLMString *v16; // rax
  int v17; // ebx
  __int128 v18; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  const struct CLMString *v20; // rax
  int v21; // ebx
  int v22; // eax
  int Component; // eax
  int v24; // eax
  int v25; // eax
  const wchar_t *v26; // rdx
  int DirectoryDeepNoThrow; // eax
  const wchar_t *v28; // r9
  signed int LastError; // eax
  int v30; // eax
  int v31; // eax
  CAccessControlImpl *v32; // rbx
  int Blob; // eax
  const wchar_t *v34; // rbx
  __int64 v35; // rcx
  char IsEnabled; // al
  __int64 v37; // rax
  __int64 v38; // rax
  char IsEncryptionAllowedForApplication; // bl
  __int64 v40; // rcx
  struct CGthrPrj *v41; // r12
  __int64 v42; // rax
  __int64 v43; // rcx
  int v44; // ebx
  int v45; // eax
  const char *v46; // r9
  int v47; // eax
  const char *v48; // r9
  int v49; // eax
  unsigned int v50; // ebx
  int v51; // eax
  int v52; // eax
  int v54; // [rsp+20h] [rbp-528h]
  int v55; // [rsp+20h] [rbp-528h]
  int v56; // [rsp+20h] [rbp-528h]
  int v57; // [rsp+20h] [rbp-528h]
  struct CGthrPrj *v58; // [rsp+50h] [rbp-4F8h] BYREF
  const wchar_t *v59; // [rsp+58h] [rbp-4F0h] BYREF
  __int128 v60; // [rsp+60h] [rbp-4E8h] BYREF
  const wchar_t *v61; // [rsp+70h] [rbp-4D8h]
  wchar_t *v62; // [rsp+78h] [rbp-4D0h]
  CGthrPrj *v63; // [rsp+80h] [rbp-4C8h]
  struct CGatherPrjCollection *v64; // [rsp+88h] [rbp-4C0h]
  wchar_t *v65; // [rsp+90h] [rbp-4B8h]
  _DWORD v66[4]; // [rsp+98h] [rbp-4B0h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-4A0h]
  int v68; // [rsp+B0h] [rbp-498h]
  VARIANTARG pvarg; // [rsp+B8h] [rbp-490h] BYREF
  struct tagVARIANT v70; // [rsp+D0h] [rbp-478h] BYREF
  const int *v71; // [rsp+F0h] [rbp-458h] BYREF
  LPCWSTR lpPathName; // [rsp+F8h] [rbp-450h]
  __int64 v73; // [rsp+100h] [rbp-448h]
  __int16 v74; // [rsp+108h] [rbp-440h] BYREF
  _BYTE v75[32]; // [rsp+190h] [rbp-3B8h] BYREF
  _BYTE v76[96]; // [rsp+1B0h] [rbp-398h] BYREF
  _BYTE v77[192]; // [rsp+210h] [rbp-338h] BYREF
  _BYTE v78[528]; // [rsp+2D0h] [rbp-278h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+0h]

  v59 = a4;
  v62 = a3;
  v63 = this;
  v64 = a2;
  v65 = a3;
  v61 = a5;
  v58 = a10;
  lpPathName = (LPCWSTR)&v74;
  v73 = 65;
  v74 = 0;
  v71 = &CCICommonPathString::`vftable';
  v12 = (CGthrPrj *)((char *)this + 1576);
  v13 = (char *)this + 1576;
  try
  {
    CLMString::operator=(v13, a3);
    *((_BYTE *)this + 2428) = a10 != 0;
    TLMString<192,64,32767>::operator=((char *)this + 1672, *((_QWORD *)a2 + 54) + 272LL);
    CLMString::operator+=((char *)this + 1672, 32);
    CLMString::operator+=((char *)this + 1672, v12);
    CLMString::operator=((char *)this + 1000, a6);
    CLMString::operator=((char *)this + 1160, a7);
    CCatalogConfigProps::CCatalogConfigProps(
      (CCatalogConfigProps *)v77,
      (const struct CLMString *)(*((_QWORD *)a2 + 54) + 272LL),
      v12,
      *((_BYTE *)this + 2428));
    v14 = (const struct CLMString *)TLMString<32,32,1024>::TLMString<32,32,1024>(v76, L"CatalogURL");
    v15 = CCatalogConfigProps::SetProperty((CCatalogConfigProps *)v77, v14, (CGthrPrj *)((char *)this + 1000));
    TLMString<32,32,1024>::~TLMString<32,32,1024>(v76);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F0,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v15,
        v54);
    v16 = (const struct CLMString *)TLMString<32,32,1024>::TLMString<32,32,1024>(v76, L"StartAddressConfigURL");
    v17 = CCatalogConfigProps::SetProperty((CCatalogConfigProps *)v77, v16, (CGthrPrj *)((char *)this + 1160));
    TLMString<32,32,1024>::~TLMString<32,32,1024>(v76);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v17,
        v54);
    VariantInit(&pvarg);
    if ( !(*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)a2 + 54) + 288LL))(
            *((_QWORD *)a2 + 54),
            L"indexer:ci:RequestedHitsMultiplier",
            &pvarg) )
    {
      v18 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      v20 = (const struct CLMString *)TLMString<32,32,1024>::TLMString<32,32,1024>(
                                        v76,
                                        L"indexer:ci:RequestedHitsMultiplier");
      *(_OWORD *)&v70.vt = v18;
      v70.pRecInfo = pRecInfo;
      v21 = CCatalogConfigProps::SetProperty((CCatalogConfigProps *)v77, v20, &v70);
      TLMString<32,32,1024>::~TLMString<32,32,1024>(v76);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1F9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
          (const char *)(unsigned int)v21,
          v54);
    }
    v22 = CGthrPrj::SetMD5Calculation(this, (struct CCatalogConfigProps *)v77);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v22,
        v54);
    TComNoUnkPointer<CPlugin>::operator=((char *)this + 2440, a2);
    CCatalogRootNode::CCatalogRootNode(
      (CCatalogRootNode *)v78,
      *(const wchar_t **)(*((_QWORD *)a2 + 54) + 280LL),
      *((const wchar_t **)this + 198),
      *((const wchar_t **)this + 126),
      *((_BYTE *)this + 2428));
    Component = CCatalogRootNode::CreateComponent(
                  (CCatalogRootNode *)v78,
                  L"Gathering Manager",
                  L"Applications",
                  L"Projects");
    if ( Component < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x207,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)Component,
        v55);
    v24 = CCatalogRootNode::OpenComponentInRegistry(
            (CCatalogRootNode *)v78,
            (CGthrPrj *)((char *)this + 984),
            L"Gathering Manager",
            L"Applications",
            L"Projects");
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v24,
        v56);
    v25 = CCatalogRootNode::OpenComponent(
            (CCatalogRootNode *)v78,
            (CGthrPrj *)((char *)this + 72),
            L"Gathering Manager",
            L"Applications",
            L"Projects");
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x210,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v25,
        v57);
    CLMString::operator=(&v71, v59);
    DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(lpPathName, v26);
    if ( DirectoryDeepNoThrow < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x215,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)DirectoryDeepNoThrow,
        v57);
    if ( *((_BYTE *)this + 2428) )
      FSOp::CreateDirectoryWithSecurity((wchar_t *)lpPathName, 0, *(const WCHAR **)(*((_QWORD *)a2 + 54) + 280LL), v28);
    else
      FSOp::CreateDirectoryWithSecurity((wchar_t *)lpPathName, 0, 0, v28);
    TLMString<192,64,32767>::operator=((char *)this + 304, &v71);
    if ( CConfigNode::SetValue((CGthrPrj *)((char *)this + 984), L"WorkingDirectory", (CGthrPrj *)((char *)this + 304)) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError == -2147024890 )
        LastError = -2147218172;
    }
    if ( LastError < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)LastError,
        v57);
    v30 = CGthrPrj::SetCrawlInterval(this, 0);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x225,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v30,
        v57);
    v31 = CAccessControlImpl::Init(
            (CGthrPrj *)((char *)this + 2696),
            *((struct PConfigNode **)this + 9),
            0,
            (CGthrPrj *)((char *)this + 24));
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v31,
        v57);
    v59 = 0;
    v32 = (CAccessControlImpl *)(*((_QWORD *)a2 + 54) + 1368LL);
    (*(void (__fastcall **)(CAccessControlImpl *))(*(_QWORD *)v32 + 8LL))(v32);
    v59 = (const wchar_t *)v32;
    v67 = 0;
    v66[2] = 0;
    v66[0] = 0;
    v68 = 0;
    Blob = CAccessControlImpl::GetBlob(v32, (struct CBlob *)v66);
    if ( Blob >= 0 )
      Blob = CAccessControlImpl::AssignFromBlob((CGthrPrj *)((char *)this + 2696), (struct CBlob *)v66);
    if ( Blob < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)Blob,
        v57);
    *((_QWORD *)this + 326) = (char *)this + 2448;
    *((_QWORD *)this + 323) = (char *)this + 2616;
    *((_QWORD *)this + 324) = (char *)this + 2448;
    *((_DWORD *)this + 650) = 1;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56349604>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56349604>::GetImpl'::`2'::impl) )
      goto LABEL_54;
    v34 = *(const wchar_t **)(*((_QWORD *)a2 + 54) + 280LL);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57872202>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_57872202>::GetImpl'::`2'::impl) )
    {
      v37 = -1;
      do
        ++v37;
      while ( v34[v37] );
      *(_QWORD *)&v60 = v34;
      *((_QWORD *)&v60 + 1) = v37;
      v38 = to_utf8(v75, &v60);
      v60 = *(_OWORD *)std::string::operator std::string_view(v38, &v70);
      IsEncryptionAllowedForApplication = FirstUpgradeEncryptionUtil::IsEncryptionAllowedForApplication(&v60);
      std::string::_Tidy_deallocate(v75);
      if ( IsEncryptionAllowedForApplication )
      {
        LOBYTE(v40) = 2;
        if ( (unsigned __int8)FirstUpgradeEncryptionUtil::IsEncryptionNeededForDBTypes(v40) )
          FirstUpgradeEncryptionUtil::SetEncryptionCompletedForDBTypes();
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_57813162>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_57813162>::GetImpl'::`2'::impl);
        goto LABEL_51;
      }
    }
    else if ( !wcscmp_0(v34, L"Windows") )
    {
      LOBYTE(v35) = 2;
      if ( (unsigned __int8)FirstUpgradeEncryptionUtil::IsEncryptionNeededForDBTypes(v35) )
        FirstUpgradeEncryptionUtil::SetEncryptionCompletedForDBTypes();
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_57813162>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_57813162>::GetImpl'::`2'::impl);
LABEL_51:
      if ( IsEnabled && !FirstUpgradeEncryptionUtil::AreAllPhasesCompletedForProjectDBs() )
        FirstUpgradeEncryptionUtil::SetAllPhasesCompletedForProjectDBs((FirstUpgradeEncryptionUtil *)&`FirstUpgradeEncryptionUtil::Instance'::`2'::instance);
    }
LABEL_54:
    if ( *((_BYTE *)this + 2428) )
    {
      CGthrPrj::InitSchema(this, 0, *(_QWORD *)(*((_QWORD *)a2 + 54) + 280LL));
      v41 = v58;
      CGthrPrj::InitSchemaForPerUserCatalog(this, v58);
    }
    else
    {
      CGthrPrj::InitSchema(this, 1, 0);
      v41 = v58;
    }
    v42 = *((_QWORD *)a2 + 54);
    v58 = 0;
    v43 = *(_QWORD *)(v42 + 1360);
    if ( v43 )
    {
      v57 = 0;
      v44 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v43 + 80LL))(v43, 0, 0, 0);
      if ( v44 >= 0 )
        v44 = (**(__int64 (__fastcall ***)(struct CGthrPrj *, GUID *, char *))v58)(
                v58,
                &GUID_7c5df82a_444a_471e_8d0c_a5aff2ae5062,
                (char *)this + 200);
    }
    else
    {
      v44 = -2147418113;
    }
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v58);
    if ( v44 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x275,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v44,
        v57);
    v45 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, LPCWSTR, const wchar_t *))(**((_QWORD **)this + 25) + 24LL))(
            *((_QWORD *)this + 25),
            v62,
            lpPathName,
            v61);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x27F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v45,
        a8);
    if ( !(unsigned int)CConfigNode::CreateSubKey((CGthrPrj *)((char *)this + 72), L"ActivePlugins") )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x283,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        v46);
    v47 = CPluginCollection::Init((CGthrPrj *)((char *)this + 472), this, L"ActivePlugins", (unsigned int)v46);
    if ( v47 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x287,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v47,
        a8);
    if ( !(unsigned int)CConfigNode::CreateSubKey((CGthrPrj *)((char *)this + 72), L"Plugins") )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x28B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        v48);
    v49 = CPluginCollection::Init((CGthrPrj *)((char *)this + 728), this, L"Plugins", (unsigned int)v48);
    v50 = v49;
    if ( v49 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v49,
        a8);
    *((_DWORD *)this + 606) = 1;
    if ( *((_BYTE *)this + 2428) )
    {
      v51 = lambda_fc0cdd4b4b0ec3c136a94e6ccc34983b_::operator()(retaddr, (char *)v41 + 472, (char *)this + 472);
      if ( v51 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2A7,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
          (const char *)(unsigned int)v51,
          a8);
      v52 = lambda_fc0cdd4b4b0ec3c136a94e6ccc34983b_::operator()(retaddr, (char *)v41 + 728, (char *)this + 728);
      if ( v52 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2A8,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
          (const char *)(unsigned int)v52,
          a8);
    }
    CBlob::Free((CBlob *)v66);
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v59);
    CCatalogRootNode::~CCatalogRootNode((CCatalogRootNode *)v78);
    VariantClear(&pvarg);
    CRegistry::~CRegistry((CRegistry *)v77);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      688,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx");
  }
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v71);
  return v50;
}

```

## disassembly

```asm
0x1800e1880  mov     r11, rsp
0x1800e1883  push    rbx
0x1800e1884  push    rsi
0x1800e1885  push    rdi
0x1800e1886  push    r12
0x1800e1888  push    r13
0x1800e188a  push    r14
0x1800e188c  push    r15
0x1800e188e  sub     rsp, 510h
0x1800e1895  movaps  xmmword ptr [r11-48h], xmm6
0x1800e189a  movaps  xmmword ptr [r11-58h], xmm7
0x1800e189f  mov     rax, cs:__security_cookie
0x1800e18a6  xor     rax, rsp
0x1800e18a9  mov     [rsp+548h+var_68], rax
0x1800e18b1  mov     [rsp+548h+var_4F0], r9
0x1800e18b6  mov     rax, r8
0x1800e18b9  mov     [rsp+548h+var_4D0], rax
0x1800e18be  mov     r15, rdx
0x1800e18c1  mov     rsi, rcx
0x1800e18c4  mov     [rsp+548h+var_4C8], rcx
0x1800e18cc  mov     [rsp+548h+var_4C0], rdx
0x1800e18d4  mov     [rsp+548h+var_4B8], rax
0x1800e18dc  mov     rcx, [rsp+548h+arg_20]
0x1800e18e4  mov     [rsp+548h+var_4D8], rcx
0x1800e18e9  mov     r12, [rsp+548h+arg_28]
0x1800e18f1  mov     r13, [rsp+548h+arg_30]
0x1800e18f9  mov     r14, [rsp+548h+arg_48]
0x1800e1901  mov     [rsp+548h+var_4F8], r14
0x1800e1906  lea     rcx, [r11-440h]
0x1800e190d  mov     [r11-450h], rcx
0x1800e1914  mov     qword ptr [r11-448h], 41h ; 'A'
0x1800e191f  xor     edi, edi
0x1800e1921  mov     [rsp+548h+var_440], di
0x1800e1929  lea     rcx, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1800e1930  mov     [r11-458h], rcx
0x1800e1937  lea     rbx, [rsi+628h]
0x1800e193e  mov     rdx, rax
0x1800e1941  mov     rcx, rbx
0x1800e1944  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800e1949  test    r14, r14
0x1800e194c  setnz   al
0x1800e194f  mov     [rsi+97Ch], al
0x1800e1955  lea     r14, [rsi+688h]
0x1800e195c  mov     rdx, [r15+1B0h]
0x1800e1963  add     rdx, 110h
0x1800e196a  mov     rcx, r14
0x1800e196d  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1800e1972  lea     edx, [rdi+20h]
0x1800e1975  mov     rcx, r14
0x1800e1978  call    ??YCLMString@@QEAAX_W@Z; CLMString::operator+=(wchar_t)
0x1800e197d  mov     rdx, rbx
0x1800e1980  mov     rcx, r14
0x1800e1983  call    ??YCLMString@@QEAAXAEBV0@@Z; CLMString::operator+=(CLMString const &)
0x1800e1988  lea     r14, [rsi+3E8h]
0x1800e198f  mov     rdx, r12
0x1800e1992  mov     rcx, r14
0x1800e1995  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800e199a  lea     r12, [rsi+488h]
0x1800e19a1  mov     rdx, r13
0x1800e19a4  mov     rcx, r12
0x1800e19a7  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800e19ac  mov     rdx, [r15+1B0h]
0x1800e19b3  add     rdx, 110h; struct CLMString *
0x1800e19ba  mov     r9b, [rsi+97Ch]; bool
0x1800e19c1  mov     r8, rbx; struct CLMString *
0x1800e19c4  lea     rcx, [rsp+548h+var_338]; this
0x1800e19cc  call    ??0CCatalogConfigProps@@QEAA@AEBVCLMString@@0_N@Z; CCatalogConfigProps::CCatalogConfigProps(CLMString const &,CLMString const &,bool)
0x1800e19d1  nop
0x1800e19d2  lea     rdx, aCatalogurl; "CatalogURL"
0x1800e19d9  lea     rcx, [rsp+548h+var_398]
0x1800e19e1  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800e19e6  nop
0x1800e19e7  mov     r8, r14; struct CLMString *
0x1800e19ea  mov     rdx, rax; struct CLMString *
0x1800e19ed  lea     rcx, [rsp+548h+var_338]; this
0x1800e19f5  call    ?SetProperty@CCatalogConfigProps@@QEAAJAEBVCLMString@@AEAV2@@Z; CCatalogConfigProps::SetProperty(CLMString const &,CLMString &)
0x1800e19fa  mov     ebx, eax
0x1800e19fc  lea     rcx, [rsp+548h+var_398]
0x1800e1a04  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800e1a09  mov     rcx, [rsp+548h]; this
0x1800e1a11  test    ebx, ebx
0x1800e1a13  jns     short loc_1800E1A29
0x1800e1a15  mov     r9d, ebx; char *
0x1800e1a18  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1a1f  mov     edx, 1F0h; void *
0x1800e1a24  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1a29  lea     rdx, aStartaddressco; "StartAddressConfigURL"
0x1800e1a30  lea     rcx, [rsp+548h+var_398]
0x1800e1a38  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800e1a3d  nop
0x1800e1a3e  mov     r8, r12; struct CLMString *
0x1800e1a41  mov     rdx, rax; struct CLMString *
0x1800e1a44  lea     rcx, [rsp+548h+var_338]; this
0x1800e1a4c  call    ?SetProperty@CCatalogConfigProps@@QEAAJAEBVCLMString@@AEAV2@@Z; CCatalogConfigProps::SetProperty(CLMString const &,CLMString &)
0x1800e1a51  mov     ebx, eax
0x1800e1a53  lea     rcx, [rsp+548h+var_398]
0x1800e1a5b  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800e1a60  mov     rcx, [rsp+548h]; this
0x1800e1a68  test    ebx, ebx
0x1800e1a6a  jns     short loc_1800E1A80
0x1800e1a6c  mov     r9d, ebx; char *
0x1800e1a6f  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1a76  mov     edx, 1F3h; void *
0x1800e1a7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1a80  lea     rcx, [rsp+548h+pvarg]; pvarg
0x1800e1a88  call    cs:__imp_VariantInit
0x1800e1a8e  nop
0x1800e1a8f  mov     rcx, [r15+1B0h]
0x1800e1a96  mov     rax, [rcx]
0x1800e1a99  lea     r8, [rsp+548h+pvarg]
0x1800e1aa1  lea     rdx, aIndexerCiReque; "indexer:ci:RequestedHitsMultiplier"
0x1800e1aa8  mov     rax, [rax+120h]
0x1800e1aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1ab4  test    eax, eax
0x1800e1ab6  jnz     short loc_1800E1B35
0x1800e1ab8  movups  xmm6, xmmword ptr [rsp+548h+pvarg]
0x1800e1ac0  movsd   xmm7, qword ptr [rsp+548h+pvarg+10h]
0x1800e1ac9  lea     rdx, aIndexerCiReque; "indexer:ci:RequestedHitsMultiplier"
0x1800e1ad0  lea     rcx, [rsp+548h+var_398]
0x1800e1ad8  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800e1add  movaps  xmmword ptr [rsp+548h+var_478], xmm6
0x1800e1ae5  movsd   qword ptr [rsp+548h+var_478+10h], xmm7
0x1800e1aee  lea     r8, [rsp+548h+var_478]; struct tagVARIANT
0x1800e1af6  mov     rdx, rax; struct CLMString *
0x1800e1af9  lea     rcx, [rsp+548h+var_338]; this
0x1800e1b01  call    ?SetProperty@CCatalogConfigProps@@QEAAJAEBVCLMString@@UtagVARIANT@@@Z; CCatalogConfigProps::SetProperty(CLMString const &,tagVARIANT)
0x1800e1b06  mov     ebx, eax
0x1800e1b08  lea     rcx, [rsp+548h+var_398]
0x1800e1b10  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800e1b15  mov     rcx, [rsp+548h]; this
0x1800e1b1d  test    ebx, ebx
0x1800e1b1f  jns     short loc_1800E1B35
0x1800e1b21  mov     r9d, ebx; char *
0x1800e1b24  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1b2b  mov     edx, 1F9h; void *
0x1800e1b30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1b35  lea     rdx, [rsp+548h+var_338]; struct CCatalogConfigProps *
0x1800e1b3d  mov     rcx, rsi; this
0x1800e1b40  call    ?SetMD5Calculation@CGthrPrj@@AEAAJAEAVCCatalogConfigProps@@@Z; CGthrPrj::SetMD5Calculation(CCatalogConfigProps &)
0x1800e1b45  mov     rcx, [rsp+548h]; this
0x1800e1b4d  test    eax, eax
0x1800e1b4f  jns     short loc_1800E1B65
0x1800e1b51  mov     r9d, eax; char *
0x1800e1b54  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1b5b  mov     edx, 1FDh; void *
0x1800e1b60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1b65  lea     rcx, [rsi+988h]
0x1800e1b6c  mov     rdx, r15
0x1800e1b6f  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x1800e1b74  mov     rdx, [r15+1B0h]
0x1800e1b7b  mov     al, [rsi+97Ch]
0x1800e1b81  mov     byte ptr [rsp+548h+var_528], al; int
0x1800e1b85  mov     r9, [rsi+3F0h]; wchar_t *
0x1800e1b8c  mov     r8, [rsi+630h]; wchar_t *
0x1800e1b93  mov     rdx, [rdx+118h]; wchar_t *
0x1800e1b9a  lea     rcx, [rsp+548h+var_278]; this
0x1800e1ba2  call    ??0CCatalogRootNode@@QEAA@PEB_W00_N@Z; CCatalogRootNode::CCatalogRootNode(wchar_t const *,wchar_t const *,wchar_t const *,bool)
0x1800e1ba7  nop
0x1800e1ba8  lea     r14, aProjects; "Projects"
0x1800e1baf  mov     r9, r14; wchar_t *
0x1800e1bb2  lea     r8, aApplications_0; "Applications"
0x1800e1bb9  lea     rdx, aGatheringManag_0; "Gathering Manager"
0x1800e1bc0  lea     rcx, [rsp+548h+var_278]; this
0x1800e1bc8  call    ?CreateComponent@CCatalogRootNode@@QEAAJPEB_W00@Z; CCatalogRootNode::CreateComponent(wchar_t const *,wchar_t const *,wchar_t const *)
0x1800e1bcd  mov     rcx, [rsp+548h]; this
0x1800e1bd5  test    eax, eax
0x1800e1bd7  jns     short loc_1800E1BED
0x1800e1bd9  mov     r9d, eax; char *
0x1800e1bdc  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1be3  mov     edx, 207h; void *
0x1800e1be8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1bed  lea     r12, [rsi+3D8h]
0x1800e1bf4  mov     [rsp+548h+var_528], r14; int
0x1800e1bf9  lea     r9, aApplications_0; "Applications"
0x1800e1c00  lea     r8, aGatheringManag_0; "Gathering Manager"
0x1800e1c07  mov     rdx, r12; struct CConfigNode *
0x1800e1c0a  lea     rcx, [rsp+548h+var_278]; this
0x1800e1c12  call    ?OpenComponentInRegistry@CCatalogRootNode@@QEAAJAEAVCConfigNode@@PEB_W11@Z; CCatalogRootNode::OpenComponentInRegistry(CConfigNode &,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800e1c17  mov     rcx, [rsp+548h]; this
0x1800e1c1f  test    eax, eax
0x1800e1c21  jns     short loc_1800E1C37
0x1800e1c23  mov     r9d, eax; char *
0x1800e1c26  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1c2d  mov     edx, 20Ch; void *
0x1800e1c32  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1c37  lea     r13, [rsi+48h]
0x1800e1c3b  mov     [rsp+548h+var_528], r14; int
0x1800e1c40  lea     r9, aApplications_0; "Applications"
0x1800e1c47  lea     r8, aGatheringManag_0; "Gathering Manager"
0x1800e1c4e  mov     rdx, r13; struct CConfigNode *
0x1800e1c51  lea     rcx, [rsp+548h+var_278]; this
0x1800e1c59  call    ?OpenComponent@CCatalogRootNode@@QEAAJAEAVCConfigNode@@PEB_W11@Z; CCatalogRootNode::OpenComponent(CConfigNode &,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800e1c5e  mov     rcx, [rsp+548h]; this
0x1800e1c66  test    eax, eax
0x1800e1c68  jns     short loc_1800E1C7E
0x1800e1c6a  mov     r9d, eax; char *
0x1800e1c6d  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1c74  mov     edx, 210h; void *
0x1800e1c79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1c7e  mov     rdx, [rsp+548h+var_4F0]
0x1800e1c83  lea     rcx, [rsp+548h+var_458]
0x1800e1c8b  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800e1c90  mov     rcx, [rsp+548h+lpPathName]; this
0x1800e1c98  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEB_W@Z; wil::CreateDirectoryDeepNoThrow(wchar_t const *)
0x1800e1c9d  mov     rcx, [rsp+548h]; this
0x1800e1ca5  test    eax, eax
0x1800e1ca7  jns     short loc_1800E1CBD
0x1800e1ca9  mov     r9d, eax; char *
0x1800e1cac  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1cb3  mov     edx, 215h; void *
0x1800e1cb8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1cbd  xor     edx, edx; wchar_t *
0x1800e1cbf  mov     rcx, [rsp+548h+lpPathName]; this
0x1800e1cc7  cmp     [rsi+97Ch], dil
0x1800e1cce  jz      short loc_1800E1CE5
0x1800e1cd0  mov     r8, [r15+1B0h]
0x1800e1cd7  mov     r8, [r8+118h]; void *
0x1800e1cde  call    ?CreateDirectoryWithSecurity@FSOp@@YAXPEB_WPEAX0@Z; FSOp::CreateDirectoryWithSecurity(wchar_t const *,void *,wchar_t const *)
0x1800e1ce3  jmp     short loc_1800E1CED
0x1800e1ce5  xor     r8d, r8d; void *
0x1800e1ce8  call    ?CreateDirectoryWithSecurity@FSOp@@YAXPEB_WPEAX0@Z; FSOp::CreateDirectoryWithSecurity(wchar_t const *,void *,wchar_t const *)
0x1800e1ced  lea     rbx, [rsi+130h]
0x1800e1cf4  lea     rdx, [rsp+548h+var_458]
0x1800e1cfc  mov     rcx, rbx
0x1800e1cff  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1800e1d04  mov     r8, rbx; struct CLMString *
0x1800e1d07  lea     rdx, aWorkingdirecto; "WorkingDirectory"
0x1800e1d0e  mov     rcx, r12; this
0x1800e1d11  call    ?SetValue@CConfigNode@@QEAAHPEB_WAEBVCLMString@@@Z; CConfigNode::SetValue(wchar_t const *,CLMString const &)
0x1800e1d16  test    eax, eax
0x1800e1d18  jnz     short loc_1800E1D3B
0x1800e1d1a  call    cs:__imp_GetLastError
0x1800e1d20  test    eax, eax
0x1800e1d22  jle     short loc_1800E1D2C
0x1800e1d24  movzx   eax, ax
0x1800e1d27  or      eax, 80070000h
0x1800e1d2c  mov     ecx, 80040D04h
0x1800e1d31  cmp     eax, 80070006h
0x1800e1d36  cmovz   eax, ecx
0x1800e1d39  jmp     short loc_1800E1D3D
0x1800e1d3b  mov     eax, edi
0x1800e1d3d  mov     rcx, [rsp+548h]; this
0x1800e1d45  test    eax, eax
0x1800e1d47  jns     short loc_1800E1D5D
0x1800e1d49  mov     r9d, eax; char *
0x1800e1d4c  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1d53  mov     edx, 221h; void *
0x1800e1d58  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1d5d  xor     edx, edx; int
0x1800e1d5f  mov     rcx, rsi; this
0x1800e1d62  call    ?SetCrawlInterval@CGthrPrj@@QEAAJJ@Z; CGthrPrj::SetCrawlInterval(long)
0x1800e1d67  mov     rcx, [rsp+548h]; this
0x1800e1d6f  test    eax, eax
0x1800e1d71  jns     short loc_1800E1D87
0x1800e1d73  mov     r9d, eax; char *
0x1800e1d76  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1d7d  mov     edx, 225h; void *
0x1800e1d82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1d87  lea     r14, [rsi+0A88h]
0x1800e1d8e  lea     r9, [rsi+18h]; struct ISearchAccessListSite *
0x1800e1d92  xor     r8d, r8d; unsigned int
0x1800e1d95  mov     rdx, [r13+0]; struct PConfigNode *
0x1800e1d99  mov     rcx, r14; this
0x1800e1d9c  call    ?Init@CAccessControlImpl@@QEAAJPEAVPConfigNode@@KPEAUISearchAccessListSite@@@Z; CAccessControlImpl::Init(PConfigNode *,ulong,ISearchAccessListSite *)
0x1800e1da1  mov     rcx, [rsp+548h]; this
0x1800e1da9  test    eax, eax
0x1800e1dab  jns     short loc_1800E1DC1
0x1800e1dad  mov     r9d, eax; char *
0x1800e1db0  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1db7  mov     edx, 228h; void *
0x1800e1dbc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1dc1  mov     [rsp+548h+var_4F0], rdi
0x1800e1dc6  mov     rbx, [r15+1B0h]
0x1800e1dcd  add     rbx, 558h
0x1800e1dd4  mov     rax, [rbx]
0x1800e1dd7  mov     rcx, rbx
0x1800e1dda  mov     rax, [rax+8]
0x1800e1dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1de3  mov     [rsp+548h+var_4F0], rbx
0x1800e1de8  mov     [rsp+548h+var_4A0], rdi
0x1800e1df0  mov     [rsp+548h+var_4A8], edi
0x1800e1df7  mov     [rsp+548h+var_4B0], edi
0x1800e1dfe  mov     [rsp+548h+var_498], edi
0x1800e1e05  lea     rdx, [rsp+548h+var_4B0]; struct CBlob *
0x1800e1e0d  mov     rcx, rbx; this
0x1800e1e10  call    ?GetBlob@CAccessControlImpl@@QEAAJAEAVCBlob@@@Z; CAccessControlImpl::GetBlob(CBlob &)
0x1800e1e15  test    eax, eax
0x1800e1e17  js      short loc_1800E1E29
0x1800e1e19  lea     rdx, [rsp+548h+var_4B0]; struct CBlob *
0x1800e1e21  mov     rcx, r14; this
0x1800e1e24  call    ?AssignFromBlob@CAccessControlImpl@@QEAAJAEAVCBlob@@@Z; CAccessControlImpl::AssignFromBlob(CBlob &)
0x1800e1e29  mov     rcx, [rsp+548h]; this
0x1800e1e31  test    eax, eax
0x1800e1e33  jns     short loc_1800E1E49
0x1800e1e35  mov     r9d, eax; char *
0x1800e1e38  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e1e3f  mov     edx, 239h; void *
0x1800e1e44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e1e49  lea     rcx, [rsi+990h]
0x1800e1e50  mov     [rsi+0A30h], rcx
  ... truncated ...
```

# CGatherer::Initialize(wchar_t const *,IGatherSite *)

- ea: `0x1800cb940`
- end: `0x1800cc8f6`
- name: `?Initialize@CGatherer@@UEAAJPEB_WPEAUIGatherSite@@@Z`
- size: `4022`
- prototype: `__int64 __fastcall(CGatherer *__hidden this, const wchar_t *, struct IGatherSite *)`
- caller_count: `0`
- callee_count: `54`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a23c`
- `0x18000e628`
- `0x1800252e4`
- `0x180027164`
- `0x18002751c`
- `0x18002dc6c`
- `0x1800495c0`
- `0x18004e5d8`
- `0x180050928`
- `0x180050968`
- `0x180050a80`
- `0x180050ac4`
- `0x18005150c`
- `0x180052460`
- `0x180052c14`
- `0x180052fd0`
- `0x180053258`
- `0x180054ef4`
- `0x18005521c`
- `0x1800555f0`
- `0x180055680`
- `0x18006a040`
- `0x18006a618`
- `0x18007f870`
- `0x1800800f4`
- `0x1800b2ec0`
- `0x1800b2fd8`
- `0x1800b500c`
- `0x1800b7a70`
- `0x1800bd828`
- `0x1800c1be8`
- `0x1800c2800`
- `0x1800cae14`
- `0x1800cb940`
- `0x1800cc8fc`
- `0x1800cccec`
- `0x1800ccd20`
- `0x1800ccda4`
- `0x1800d26dc`
- `0x1800e2420`
- `0x1800f5b34`
- `0x1800f5e08`
- `0x180104c10`
- `0x180108190`
- `0x1801244c0`
- `0x180124d80`
- `0x1801c0b50`
- `0x1801c51fc`
- `0x1801c7c0c`
- `0x1801cb1f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x1800cbc7d`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x1800cbc7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbe60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbeff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbe60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbeff`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800cbfd0`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800cbfd0`
- `OLEAUT32!__imp_VariantInit` at `0x1800cbb3e`
- `OLEAUT32!__imp_VariantInit` at `0x1800cbb3e`
- `OLEAUT32!__imp_VariantClear` at `0x1800cc8b2`
- `OLEAUT32!__imp_VariantClear` at `0x1800cc8b2`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800cbb58`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800cbb58`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cc5a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cc5a4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800cc783`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800cc783`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800cc7b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800cc7b3`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800cbe01`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800cbe01`
- `RPCRT4!UuidFromStringW` at `0x1800cc4ef`
- `RPCRT4!UuidFromStringW` at `0x1800cc537`
- `RPCRT4!UuidFromStringW` at `0x1800cc4ef`
- `RPCRT4!UuidFromStringW` at `0x1800cc537`

## string_xrefs

- `0x1800cc0b9`: `FollowComplexUrls`
- `0x1800cc0d6`: `FollowComplexUrls`
- `0x1800cc364`: `LazyCheckPointUpdateInterval`
- `0x1800cc37e`: `LazyCheckPointUpdateInterval`
- `0x1800cbe19`: `LogDirectory`
- `0x1800cbe84`: `LogDirectory`
- `0x1800cbebc`: `StreamLogsDirectory`
- `0x1800cbf23`: `StreamLogsDirectory`
- `0x1800cc32c`: `FailureUpdateInterval`
- `0x1800cc34b`: `FailureUpdateInterval`
- `0x1800cc408`: `ParentPathCacheSize`
- `0x1800cc422`: `ParentPathCacheSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CGatherer::Initialize(CGatherer *this, const wchar_t *a2, struct IGatherSite *a3)
{
  _DWORD *v6; // r13
  _QWORD *v8; // r15
  HRESULT Instance; // ebx
  const struct CLMString *v10; // rax
  int Property; // ebx
  __int64 RootRegistryKeyName; // rax
  int v13; // eax
  const struct CLMString *v14; // rax
  int v15; // ebx
  BOOL v16; // eax
  unsigned __int64 v17; // r15
  const wchar_t *v18; // r9
  __int64 v19; // rax
  const size_t *v20; // rbx
  const size_t *v21; // rdx
  __int64 v22; // rax
  const size_t *v23; // rdx
  const size_t *v24; // rdx
  LPVOID *ppv; // rax
  HRESULT ClassObject; // eax
  signed int v27; // eax
  CSearchEventEntry *v28; // rcx
  signed int LastError; // eax
  LCID SystemDefaultLCID; // eax
  unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rax
  const wchar_t *v33; // r9
  const wchar_t *v34; // rdx
  __int64 v35; // rcx
  const wchar_t *v36; // r9
  const wchar_t *v37; // r9
  const wchar_t *v38; // rdx
  const wchar_t *v39; // r9
  unsigned int v40; // r9d
  CStatusThread *v41; // rax
  CStatusThread *v42; // rax
  unsigned int v43; // [rsp+50h] [rbp-2038h] BYREF
  __int64 v44; // [rsp+58h] [rbp-2030h] BYREF
  CStatusThread *v45; // [rsp+60h] [rbp-2028h]
  VARIANTARG pvarg; // [rsp+68h] [rbp-2020h] BYREF
  CGatherer *v47; // [rsp+80h] [rbp-2008h]
  GUID clsid; // [rsp+88h] [rbp-2000h] BYREF
  _BYTE v49[96]; // [rsp+A0h] [rbp-1FE8h] BYREF
  _BYTE v50[192]; // [rsp+100h] [rbp-1F88h] BYREF
  _BYTE v51[528]; // [rsp+1C0h] [rbp-1EC8h] BYREF
  _BYTE v52[8]; // [rsp+3D0h] [rbp-1CB8h] BYREF
  _BYTE v53[160]; // [rsp+3D8h] [rbp-1CB0h] BYREF
  _BYTE v54[2248]; // [rsp+478h] [rbp-1C10h] BYREF
  _BYTE v55[168]; // [rsp+D40h] [rbp-1348h] BYREF
  _BYTE v56[2248]; // [rsp+DE8h] [rbp-12A0h] BYREF
  _BYTE v57[168]; // [rsp+16B0h] [rbp-9D8h] BYREF
  _BYTE v58[2248]; // [rsp+1758h] [rbp-930h] BYREF
  wchar_t Buffer[4]; // [rsp+2020h] [rbp-68h] BYREF
  int v60; // [rsp+2028h] [rbp-60h]
  __int64 v61; // [rsp+2030h] [rbp-58h]
  int v62; // [rsp+2038h] [rbp-50h]
  void *retaddr; // [rsp+2088h] [rbp+0h]

  v47 = this;
  v6 = (_DWORD *)((char *)this - 16);
  v45 = (CGatherer *)((char *)this - 16);
  if ( !*((_DWORD *)this + 298) )
    return 2147549183LL;
  if ( !a3 )
    return 2147500035LL;
  v8 = (_QWORD *)((char *)this + 424);
  TComNoUnkPointer<CPlugin>::operator=((char *)this + 424, a3);
  v44 = 0;
  Instance = (**(__int64 (__fastcall ***)(struct IGatherSite *, GUID *, __int64 *))a3)(
               a3,
               &GUID_b53a2216_744f_4ac9_b20d_6767e167d4fc,
               &v44);
  if ( Instance >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 5448);
    Instance = CUrlConverter_CreateInstance((struct IUrlConverter **)this + 681);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v44 + 24LL))(v44, (char *)this + 1328);
      if ( Instance >= 0 )
      {
        CLMString::operator=((char *)this + 232, a2);
        TLMString<192,64,32767>::operator=((char *)this + 328, *((_QWORD *)this + 448) + 320LL);
        CLMString::operator+=((char *)this + 328, 32);
        CLMString::operator+=((char *)this + 328, (char *)this + 232);
        CCatalogConfigProps::CCatalogConfigProps(
          (CCatalogConfigProps *)v50,
          (const struct CLMString *)(*((_QWORD *)this + 448) + 224LL),
          (CGatherer *)((char *)this + 232),
          *(_BYTE *)(*((_QWORD *)this + 448) + 416LL));
        v10 = (const struct CLMString *)TLMString<32,32,1024>::TLMString<32,32,1024>(v49, L"CatalogURL");
        Property = CCatalogConfigProps::GetProperty((CCatalogConfigProps *)v50, v10, (CGatherer *)((char *)this + 4600));
        TLMString<32,32,1024>::~TLMString<32,32,1024>(v49);
        if ( Property < 0 )
        {
          RootRegistryKeyName = GetRootRegistryKeyName(v49);
          CLMString::operator=((char *)this + 4600, RootRegistryKeyName);
          TLMString<32,32,1024>::~TLMString<32,32,1024>(v49);
        }
        v13 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v8 + 72LL))(*v8, (char *)this + 4136);
        Instance = v13;
        if ( v13 < 0 )
        {
          SearchIndexerTrace::Error(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\gatherobj.cxx\"",
            (const wchar_t *)0x352,
            (unsigned int)L"[SrchGatherPI] gatherSite get duplicate detection failed hr 0x%08x",
            (const wchar_t *)(unsigned int)v13);
LABEL_144:
          CRegistry::~CRegistry((CRegistry *)v50);
          goto LABEL_145;
        }
        VariantInit(&pvarg);
        VariantChangeType(&pvarg, &pvarg, 0, 0xBu);
        v14 = (const struct CLMString *)TLMString<32,32,1024>::TLMString<32,32,1024>(v49, L"MSSearch:MD5Calculation");
        v15 = CCatalogConfigProps::GetProperty((CCatalogConfigProps *)v50, v14, &pvarg);
        TLMString<32,32,1024>::~TLMString<32,32,1024>(v49);
        v16 = v15 < 0 || pvarg.iVal == -1;
        v6[1039] = v16;
        CCatalogRootNode::CCatalogRootNode(
          (CCatalogRootNode *)v51,
          *(const wchar_t **)(*((_QWORD *)this + 448) + 232LL),
          *((const wchar_t **)this + 30),
          *((const wchar_t **)this + 576),
          *(_BYTE *)(*((_QWORD *)this + 448) + 416LL));
        Instance = CCatalogRootNode::OpenComponentInRegistry(
                     (CCatalogRootNode *)v51,
                     (CGatherer *)((char *)this + 4584),
                     L"Gather",
                     0,
                     0);
        if ( Instance < 0
          || (v17 = (unsigned __int64)this + 160,
              Instance = CCatalogRootNode::OpenComponent(
                           (CCatalogRootNode *)v51,
                           (CGatherer *)((char *)this + 160),
                           L"Gather",
                           0,
                           0),
              Instance < 0) )
        {
LABEL_143:
          CCatalogRootNode::~CCatalogRootNode((CCatalogRootNode *)v51);
          VariantClear(&pvarg);
          goto LABEL_144;
        }
        if ( !*((_BYTE *)this + 4580) )
        {
          if ( HIWORD(qword_1802DAFE0) != 1026 )
          {
            _ultow(0x4020000u, Buffer, 16);
            CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v52, qword_1802DAFD8);
            v19 = *((_QWORD *)this + 448);
            v20 = &cchOriginalDestLength;
            v21 = &cchOriginalDestLength;
            if ( *(_QWORD *)(v19 + 328) )
              v21 = *(const size_t **)(v19 + 328);
            CLMString::operator=(v53, v21);
            if ( *((_QWORD *)this + 30) )
              v20 = (const size_t *)*((_QWORD *)this + 30);
            CLMString::operator=(v54, v20);
            CSearchEventEntry::ReportError((CSearchEventEntry *)v52, 0xC0000BDA, Buffer, 0);
            CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v52);
            Instance = -2147024891;
            goto LABEL_143;
          }
          if ( !(_DWORD)qword_1802DAFE0 )
          {
            SearchIndexerTrace::Error(
              (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\gatherobj.cxx\"",
              (const wchar_t *)0x383,
              (unsigned int)L"[SrchGatherPI] Error initializing performance monitoring",
              v18);
            CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v52, qword_1802DAFD8);
            v22 = *((_QWORD *)this + 448);
            v23 = &cchOriginalDestLength;
            if ( *(_QWORD *)(v22 + 328) )
              v23 = *(const size_t **)(v22 + 328);
            CLMString::operator=(v53, v23);
            v24 = &cchOriginalDestLength;
            if ( *((_QWORD *)this + 30) )
              v24 = (const size_t *)*((_QWORD *)this + 30);
            CLMString::operator=(v54, v24);
            CSearchEventEntry::ReportError((CSearchEventEntry *)v52, 0xC0000BBF, 0);
            CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v52);
          }
        }
        if ( !*((_BYTE *)this + 4580) )
        {
          ppv = (LPVOID *)((char *)this + 432);
          if ( *((_QWORD *)this + 54) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            ppv = (LPVOID *)((char *)this + 432);
          }
          ClassObject = CoGetClassObject(&CLSID_CGatherTransaction, 0x17u, 0, &IID_IClassFactory, ppv);
          if ( ClassObject < 0 )
          {
LABEL_35:
            Instance = ClassObject;
            goto LABEL_143;
          }
        }
        if ( CConfigNode::GetValue(
               (CGatherer *)((char *)this + 4584),
               L"LogDirectory",
               (CGatherer *)((char *)this + 520)) )
        {
          if ( CConfigNode::GetValue(
                 (CGatherer *)((char *)this + 4584),
                 L"StreamLogsDirectory",
                 (CGatherer *)((char *)this + 680)) )
          {
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 4584),
                                  L"NewCrawlNumber",
                                  (unsigned int *)this + 302) )
            {
              *((_DWORD *)this + 302) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"NewCrawlNumber", 0);
            }
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 4584),
                                  L"NewClientID",
                                  (unsigned int *)this + 303) )
            {
              *((_DWORD *)this + 303) = 1;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"NewClientID", 1u);
            }
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 4584),
                                  L"SystemLcid",
                                  (unsigned int *)this + 304) )
            {
              SystemDefaultLCID = GetSystemDefaultLCID();
              *((_DWORD *)this + 304) = SystemDefaultLCID;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"SystemLcid", SystemDefaultLCID);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"LogSuccess", &v43) )
            {
              *((_DWORD *)this + 408) = v43;
            }
            else
            {
              *((_DWORD *)this + 408) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"LogSuccess", 0);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"LogExcluded", &v43) )
            {
              *((_DWORD *)this + 409) = v43;
            }
            else
            {
              *((_DWORD *)this + 409) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"LogExcluded", 0);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"LogDisabled", &v43) )
            {
              *((_DWORD *)this + 410) = v43;
            }
            else
            {
              *((_DWORD *)this + 410) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"LogDisabled", 0);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"FollowComplexUrls", &v43) )
            {
              *((_DWORD *)this + 411) = v43;
            }
            else
            {
              *((_DWORD *)this + 411) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"FollowComplexUrls", 0);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 4584), L"ForceFullCrawl", &v43) )
            {
              *((_DWORD *)this + 412) = v43;
            }
            else
            {
              *((_DWORD *)this + 412) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"ForceFullCrawl", 0);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"DisableRecovery", &v43) )
            {
              *((_DWORD *)this + 413) = v43;
            }
            else
            {
              *((_DWORD *)this + 413) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"DisableRecovery", 0);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"PausedExternal", &v43) )
            {
              *((_DWORD *)this + 293) = v43;
            }
            else
            {
              *((_DWORD *)this + 293) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"PausedExternal", 0);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"DisableRobotsExclusion", &v43) )
            {
              *((_DWORD *)this + 414) = v43;
            }
            else
            {
              *((_DWORD *)this + 414) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"DisableRobotsExclusion", 0);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"NormalizeUrls", &v43) )
            {
              *((_DWORD *)this + 415) = v43;
            }
            else
            {
              *((_DWORD *)this + 415) = 1;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"NormalizeUrls", 1u);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"CaseSensitiveUrls", &v43) )
            {
              *((_DWORD *)this + 416) = v43;
            }
            else
            {
              *((_DWORD *)this + 416) = 1;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"CaseSensitiveUrls", 1u);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue(
                                 (CGatherer *)((char *)this + 160),
                                 L"UseIncrementalCrawlDirIter",
                                 &v43) )
            {
              *((_DWORD *)this + 417) = v43;
            }
            else
            {
              *((_DWORD *)this + 417) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"UseIncrementalCrawlDirIter", 0);
            }
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 160),
                                  L"ElapsedRunTime",
                                  (unsigned int *)this + 444) )
            {
              *((_DWORD *)this + 444) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"ElapsedRunTime", 0);
            }
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 160),
                                  L"PersistedFullCrawlCount",
                                  (unsigned int *)this + 445) )
            {
              *((_DWORD *)this + 445) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"PersistedFullCrawlCount", 0);
            }
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 160),
                                  L"FailureUpdateInterval",
                                  (unsigned int *)this + 447) )
            {
              *((_DWORD *)this + 447) = 86400;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"FailureUpdateInterval", 0x15180u);
            }
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 160),
                                  L"LazyCheckPointUpdateInterval",
                                  (unsigned int *)this + 448) )
            {
              *((_DWORD *)this + 448) = 86400;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"LazyCheckPointUpdateInterval", 0x15180u);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"EnableCheckPoint", &v43) )
            {
              *((_DWORD *)this + 418) = v43;
            }
            else
            {
              *((_DWORD *)this + 418) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"EnableCheckPoint", 0);
            }
            CConfigNode::GetValue(
              (CGatherer *)((char *)this + 160),
              L"CatalogGroup",
              (CGatherer *)((char *)this + 3592));
            CConfigNode::GetValue(
              (CGatherer *)((char *)this + 160),
              L"LogProviderProgId",
              (CGatherer *)((char *)this + 1680));
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 160),
                                  L"ParentPathCacheSize",
                                  (unsigned int *)this + 446) )
            {
              *((_DWORD *)this + 446) = 15;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"ParentPathCacheSize", 0xFu);
            }
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 160),
                                  L"RespectPowerModes",
                                  (unsigned int *)this + 449) )
            {
              *((_DWORD *)this + 449) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"RespectPowerModes", 0);
            }
            *((_DWORD *)this + 1074) = *((_DWORD *)this + 303);
            if ( !*((_DWORD *)this + 425) )
              CLMString::operator=((char *)this + 1680, L"Search.GathererLogFileProvider.1");
            if ( !(unsigned int)CConfigNode::GetValue(
                                  (CGatherer *)((char *)this + 160),
                                  L"CheckPointNumber",
                                  (unsigned int *)this + 498) )
            {
              *((_DWORD *)this + 498) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"CheckPointNumber", 0);
            }
            CConfigNode::GetValue(
              (CGatherer *)((char *)this + 160),
              L"CatalogResetSignature",
              (CGatherer *)((char *)this + 1800));
            if ( !*((_DWORD *)this + 455)
              || (v31 = CLMString::GetBuffer((CGatherer *)((char *)this + 1800), 0),
                  UuidFromStringW(v31, (UUID *)this + 261)) )
            {
              CGatherer::UpdateCatalogSignature(v6);
            }
            CConfigNode::GetValue(
              (CGatherer *)((char *)this + 160),
              L"CheckPointSignature",
              (CGatherer *)((char *)this + 1896));
            if ( !*((_DWORD *)this + 479)
              || (v32 = CLMString::GetBuffer((CGatherer *)((char *)this + 1896), 0),
                  UuidFromStringW(v32, (UUID *)this + 260)) )
            {
              CGatherer::UpdateCheckPointSignature(v6, 1);
            }
            v43 = 0;
            if ( (unsigned int)CConfigNode::GetValue((CGatherer *)((char *)this + 160), L"FilterAlways", &v43) )
            {
              *((_DWORD *)this + 499) = v43;
            }
            else
            {
              *((_DWORD *)this + 499) = 0;
              CConfigNode::SetValue((CGatherer *)((char *)this + 160), L"FilterAlways", 0);
            }
            ClassObject = CGatherer::CheckSystemLcidAndRemoveFilesAsNecessary((CGatherer *)v6);
            if ( ClassObject >= 0 )
            {
              GetSystemTimeAsFileTime((LPFILETIME)this + 176);
              Instance = CSiteRestrCollection::Init(
                           (CGatherer *)((char *)this + 2000),
                           *((const wchar_t **)this + 42),
                           (struct CGatherer *)v6,
                           v33,
                           *((struct IUrlConverter **)this + 681));
              if ( Instance >= 0 )
              {
                Instance = CStartPageCollection::Init(
                             (CGatherer *)((char *)this + 2488),
                             *((const wchar_t **)this + 42),
                             (struct CGatherer *)v6,
                             v36,
                             *((struct IUrlConverter **)this + 681));
                if ( Instance >= 0 )
                  Instance = CGatherer::_AddStartPagesToUrlConverter((CGatherer *)v6);
              }
              if ( Instance == -2147218173 || Instance == -2147218061 || (unsigned int)(Instance + 2147024894) <= 1 )
                RecoveryReportIndexRebuildEx_3(v35, *((_QWORD *)g_pGatheringService + 49));
              if ( Instance >= 0 )
              {
                Instance = CExtCll::Init(
                             (CGatherer *)((char *)this + 2240),
                             v34,
                             (struct CConfigNode *)(v17 & -(__int64)(v6 != 0)),
                             v36);
                if ( Instance >= 0 )
                {
                  Instance = CGatherer::InitCatGuid((CGatherer *)v6);
                  if ( Instance >= 0 )
                  {
                    Instance = CUMapCll::Init(
                                 (CGatherer *)((char *)this + 2912),
                                 *((const wchar_t **)this + 42),
                                 (struct CConfigNode *)(v17 & -(__int64)(v6 != 0)),
                                 v37);
                    if ( Instance >= 0 )
                    {
                      Instance = CProtocolCollection::Init(
                                   (CGatherer *)((char *)this + 3216),
                                   v38,
                                   (struct CConfigNode *)(v17 & -(__int64)(v6 != 0)),
                                   v39);
                      if ( Instance >= 0 )
                      {
                        CConfigNode::CreateSubKey((CGatherer *)((char *)this + 4584), L"Crawls");
                        Instance = CConfigNode::Init(
                                     (CGatherer *)((char *)this + 1000),
                                     (CGatherer *)((char *)this + 4584),
                                     L"Crawls",
                                     v40);
                        if ( Instance >= 0 )
                        {
                          Instance = CGatherer::LoadCrawls((CGatherer *)v6);
                          if ( Instance >= 0 )
                          {
                            CGatherer::InitPerformanceMonitoring((CGatherer *)v6, 1);
                            if ( *((_BYTE *)this + 4580) )
                              goto LABEL_136;
                            v61 = 0;
                            v60 = 0;
                            *(_DWORD *)Buffer = 0;
                            v62 = 0;
                            Instance = CGatherer::GetProjectSecurity((CGatherer *)v6, (struct CBlob *)Buffer);
                            if ( Instance >= 0 )
                            {
                              clsid = 0;
                              Instance = CLSIDFromProgID(*((LPCOLESTR *)this + 211), &clsid);
                              if ( Instance >= 0 )
                              {
                                Instance = CoCreateInstance(
                                             &clsid,
                                             0,
                                             1u,
                                             &GUID_a373e680_7a87_11d3_b1c1_00c04f68155c,
                                             (LPVOID *)this + 443);
                                if ( Instance >= 0 )
                                {
                                  try
                                  {
                                    Instance = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, char *, const wchar_t *, _QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 443) + 24LL))(
                                                 *((_QWORD *)this + 443),
                                                 v17 & -(__int64)(v6 != 0),
                                                 (char *)this + 4584,
                                                 L"StreamLog",
                                                 *((_QWORD *)this + 30),
                                                 *(_QWORD *)(*((_QWORD *)this + 448) + 232LL),
                                                 *((_QWORD *)this + 86),
                                                 v61);
                                  }
                                  catch ( ... )
                                  {
                                    indexer::result::details::result_from_caught_exception<1>(
                                      retaddr,
                                      1085,
                                      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\gatherobj.cxx");
                                  }
                                }
                              }
                            }
                            CBlob::Free((CBlob *)Buffer);
                            if ( Instance >= 0 )
                            {
LABEL_136:
                              v41 = (CStatusThread *)operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
                              v45 = v41;
                              if ( v41 )
                                v42 = CStatusThread::CStatusThread(v41, (struct CGatherer *)v6);
                              else
                                v42 = 0;
                              *((_QWORD *)this + 165) = v42;
                              if ( v42 )
                              {
                                Instance = CGatherer::CommonInit((CGatherer *)v6);
                                if ( Instance >= 0 )
                                  *((_DWORD *)this + 298) = 0;
                              }
                              else
                              {
                                Instance = -2147024882;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              goto LABEL_143;
            }
            goto LABEL_35;
          }
          CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v57, qword_1802DAFD8);
          if ( !a2 )
            a2 = (const wchar_t *)&cchOriginalDestLength;
          CLMString::operator=(v58, a2);
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          CSearchEventEntry::SetError((CSearchEventEntry *)v57, LastError);
          CSearchEventEntry::ReportError((CSearchEventEntry *)v57, 0x80000BDE, L"StreamLogsDirectory", 0);
          v28 = (CSearchEventEntry *)v57;
        }
        else
        {
          CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v55, qword_1802DAFD8);
          if ( !a2 )
            a2 = (const wchar_t *)&cchOriginalDestLength;
          CLMString::operator=(v56, a2);
          v27 = GetLastError();
          if ( v27 > 0 )
            v27 = (unsigned __int16)v27 | 0x80070000;
          CSearchEventEntry::SetError((CSearchEventEntry *)v55, v27);
          CSearchEventEntry::ReportError((CSearchEventEntry *)v55, 0x80000BDE, L"LogDirectory", 0);
          v28 = (CSearchEventEntry *)v55;
        }
        CSearchEventEntry::~CSearchEventEntry(v28);
        Instance = -2147218173;
        goto LABEL_143;
      }
    }
  }
LABEL_145:
  TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v44);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800cb940  push    rbx
0x1800cb942  push    rsi
0x1800cb943  push    rdi
0x1800cb944  push    r12
0x1800cb946  push    r13
0x1800cb948  push    r14
0x1800cb94a  push    r15
0x1800cb94c  mov     eax, 2050h
0x1800cb951  call    _alloca_probe
0x1800cb956  sub     rsp, rax
0x1800cb959  mov     rax, cs:__security_cookie
0x1800cb960  xor     rax, rsp
0x1800cb963  mov     [rsp+2088h+var_40], rax
0x1800cb96b  mov     rbx, r8
0x1800cb96e  mov     r12, rdx
0x1800cb971  mov     r14, rcx
0x1800cb974  mov     [rsp+2088h+var_2008], rcx
0x1800cb97c  lea     r13, [rcx-10h]
0x1800cb980  mov     [rsp+2088h+var_2028], r13
0x1800cb985  xor     esi, esi
0x1800cb987  cmp     [r13+4B8h], esi
0x1800cb98e  jnz     short loc_1800CB99A
0x1800cb990  mov     eax, 8000FFFFh
0x1800cb995  jmp     loc_1800CC8D3
0x1800cb99a  test    rbx, rbx
0x1800cb99d  jnz     short loc_1800CB9A9
0x1800cb99f  mov     eax, 80004003h
0x1800cb9a4  jmp     loc_1800CC8D3
0x1800cb9a9  lea     r15, [rcx+1A8h]
0x1800cb9b0  mov     rdx, rbx
0x1800cb9b3  mov     rcx, r15
0x1800cb9b6  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x1800cb9bb  mov     [rsp+2088h+var_2030], rsi
0x1800cb9c0  mov     rax, [rbx]
0x1800cb9c3  lea     r8, [rsp+2088h+var_2030]
0x1800cb9c8  lea     rdx, _GUID_b53a2216_744f_4ac9_b20d_6767e167d4fc
0x1800cb9cf  mov     rcx, rbx
0x1800cb9d2  mov     rax, [rax]
0x1800cb9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb9da  mov     ebx, eax
0x1800cb9dc  test    eax, eax
0x1800cb9de  js      loc_1800CC8C7
0x1800cb9e4  lea     rbx, [r14+1548h]
0x1800cb9eb  mov     rcx, rbx
0x1800cb9ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cb9f3  mov     rcx, rbx; struct IUrlConverter **
0x1800cb9f6  call    ?CUrlConverter_CreateInstance@@YAJPEAPEAUIUrlConverter@@@Z; CUrlConverter_CreateInstance(IUrlConverter * *)
0x1800cb9fb  mov     ebx, eax
0x1800cb9fd  test    eax, eax
0x1800cb9ff  js      loc_1800CC8C7
0x1800cba05  mov     rcx, [rsp+2088h+var_2030]
0x1800cba0a  mov     rax, [rcx]
0x1800cba0d  lea     rdx, [r14+530h]
0x1800cba14  mov     rax, [rax+18h]
0x1800cba18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cba1d  mov     ebx, eax
0x1800cba1f  test    eax, eax
0x1800cba21  js      loc_1800CC8C7
0x1800cba27  lea     rdi, [r14+0E8h]
0x1800cba2e  mov     rdx, r12
0x1800cba31  mov     rcx, rdi
0x1800cba34  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cba39  lea     rbx, [r14+148h]
0x1800cba40  mov     rdx, [r14+0E00h]
0x1800cba47  add     rdx, 140h
0x1800cba4e  mov     rcx, rbx
0x1800cba51  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1800cba56  mov     edx, 20h ; ' '
0x1800cba5b  mov     rcx, rbx
0x1800cba5e  call    ??YCLMString@@QEAAX_W@Z; CLMString::operator+=(wchar_t)
0x1800cba63  mov     rdx, rdi
0x1800cba66  mov     rcx, rbx
0x1800cba69  call    ??YCLMString@@QEAAXAEBV0@@Z; CLMString::operator+=(CLMString const &)
0x1800cba6e  mov     r9, [r14+0E00h]
0x1800cba75  lea     rdx, [r9+0E0h]; struct CLMString *
0x1800cba7c  mov     r9b, [r9+1A0h]; bool
0x1800cba83  mov     r8, rdi; struct CLMString *
0x1800cba86  lea     rcx, [rsp+2088h+var_1F88]; this
0x1800cba8e  call    ??0CCatalogConfigProps@@QEAA@AEBVCLMString@@0_N@Z; CCatalogConfigProps::CCatalogConfigProps(CLMString const &,CLMString const &,bool)
0x1800cba93  nop
0x1800cba94  lea     rdx, aCatalogurl; "CatalogURL"
0x1800cba9b  lea     rcx, [rsp+2088h+var_1FE8]
0x1800cbaa3  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800cbaa8  nop
0x1800cbaa9  lea     rdi, [r14+11F8h]
0x1800cbab0  mov     r8, rdi; struct CLMString *
0x1800cbab3  mov     rdx, rax; struct CLMString *
0x1800cbab6  lea     rcx, [rsp+2088h+var_1F88]; this
0x1800cbabe  call    ?GetProperty@CCatalogConfigProps@@QEAAJAEBVCLMString@@AEAV2@@Z; CCatalogConfigProps::GetProperty(CLMString const &,CLMString &)
0x1800cbac3  mov     ebx, eax
0x1800cbac5  lea     rcx, [rsp+2088h+var_1FE8]
0x1800cbacd  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800cbad2  test    ebx, ebx
0x1800cbad4  jns     short loc_1800CBAFD
0x1800cbad6  lea     rcx, [rsp+2088h+var_1FE8]
0x1800cbade  call    ?GetRootRegistryKeyName@@YA?AV?$TLMString@$0CA@$0CA@$0EAA@@@XZ; GetRootRegistryKeyName(void)
0x1800cbae3  nop
0x1800cbae4  mov     rdx, rax
0x1800cbae7  mov     rcx, rdi
0x1800cbaea  call    ??4CLMString@@QEAAXAEBV0@@Z; CLMString::operator=(CLMString const &)
0x1800cbaef  nop
0x1800cbaf0  lea     rcx, [rsp+2088h+var_1FE8]
0x1800cbaf8  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800cbafd  mov     rcx, [r15]
0x1800cbb00  mov     rax, [rcx]
0x1800cbb03  lea     rdx, [r14+1028h]
0x1800cbb0a  mov     rax, [rax+48h]
0x1800cbb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbb13  mov     ebx, eax
0x1800cbb15  test    eax, eax
0x1800cbb17  jns     short loc_1800CBB39
0x1800cbb19  mov     r9d, eax; wchar_t *
0x1800cbb1c  lea     r8, aSrchgatherpiGa; "[SrchGatherPI] gatherSite get duplicate"...
0x1800cbb23  mov     edx, 352h; wchar_t *
0x1800cbb28  lea     rcx, aOnecoreuapBase_114; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800cbb2f  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800cbb34  jmp     loc_1800CC8B9
0x1800cbb39  lea     rcx, [rsp+2088h+pvarg]; pvarg
0x1800cbb3e  call    cs:__imp_VariantInit
0x1800cbb44  nop
0x1800cbb45  mov     r9d, 0Bh; vt
0x1800cbb4b  xor     r8d, r8d; wFlags
0x1800cbb4e  lea     rdx, [rsp+2088h+pvarg]; pvarSrc
0x1800cbb53  lea     rcx, [rsp+2088h+pvarg]; pvargDest
0x1800cbb58  call    cs:__imp_VariantChangeType
0x1800cbb5e  lea     rdx, aMssearchMd5cal; "MSSearch:MD5Calculation"
0x1800cbb65  lea     rcx, [rsp+2088h+var_1FE8]
0x1800cbb6d  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800cbb72  nop
0x1800cbb73  lea     r8, [rsp+2088h+pvarg]; struct tagVARIANT *
0x1800cbb78  mov     rdx, rax; struct CLMString *
0x1800cbb7b  lea     rcx, [rsp+2088h+var_1F88]; this
0x1800cbb83  call    ?GetProperty@CCatalogConfigProps@@QEAAJAEBVCLMString@@PEAUtagVARIANT@@@Z; CCatalogConfigProps::GetProperty(CLMString const &,tagVARIANT *)
0x1800cbb88  mov     ebx, eax
0x1800cbb8a  lea     rcx, [rsp+2088h+var_1FE8]
0x1800cbb92  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800cbb97  test    ebx, ebx
0x1800cbb99  js      short loc_1800CBBAC
0x1800cbb9b  cmp     word ptr [rsp+2088h+pvarg+8], 0FFFFh
0x1800cbba1  jz      short loc_1800CBBAC
0x1800cbba3  mov     eax, esi
0x1800cbba5  mov     edi, 1
0x1800cbbaa  jmp     short loc_1800CBBB3
0x1800cbbac  mov     edi, 1
0x1800cbbb1  mov     eax, edi
0x1800cbbb3  mov     [r13+103Ch], eax
0x1800cbbba  mov     rdx, [r14+0E00h]
0x1800cbbc1  mov     al, [rdx+1A0h]
0x1800cbbc7  mov     byte ptr [rsp+2088h+ppv], al; bool
0x1800cbbcb  mov     r9, [r14+1200h]; wchar_t *
0x1800cbbd2  mov     r8, [r14+0F0h]; wchar_t *
0x1800cbbd9  mov     rdx, [rdx+0E8h]; wchar_t *
0x1800cbbe0  lea     rcx, [rsp+2088h+var_1EC8]; this
0x1800cbbe8  call    ??0CCatalogRootNode@@QEAA@PEB_W00_N@Z; CCatalogRootNode::CCatalogRootNode(wchar_t const *,wchar_t const *,wchar_t const *,bool)
0x1800cbbed  nop
0x1800cbbee  lea     rdx, [r14+11E8h]; struct CConfigNode *
0x1800cbbf5  mov     [rsp+2088h+ppv], rsi; wchar_t *
0x1800cbbfa  xor     r9d, r9d; wchar_t *
0x1800cbbfd  lea     r8, aGather; "Gather"
0x1800cbc04  lea     rcx, [rsp+2088h+var_1EC8]; this
0x1800cbc0c  call    ?OpenComponentInRegistry@CCatalogRootNode@@QEAAJAEAVCConfigNode@@PEB_W11@Z; CCatalogRootNode::OpenComponentInRegistry(CConfigNode &,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800cbc11  mov     ebx, eax
0x1800cbc13  test    eax, eax
0x1800cbc15  js      loc_1800CC89F
0x1800cbc1b  lea     r15, [r14+0A0h]
0x1800cbc22  mov     [rsp+2088h+ppv], rsi; wchar_t *
0x1800cbc27  xor     r9d, r9d; wchar_t *
0x1800cbc2a  lea     r8, aGather; "Gather"
0x1800cbc31  mov     rdx, r15; struct CConfigNode *
0x1800cbc34  lea     rcx, [rsp+2088h+var_1EC8]; this
0x1800cbc3c  call    ?OpenComponent@CCatalogRootNode@@QEAAJAEAVCConfigNode@@PEB_W11@Z; CCatalogRootNode::OpenComponent(CConfigNode &,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800cbc41  mov     ebx, eax
0x1800cbc43  test    eax, eax
0x1800cbc45  js      loc_1800CC89F
0x1800cbc4b  cmp     [r14+11E4h], sil
0x1800cbc52  jnz     loc_1800CBDBF
0x1800cbc58  mov     eax, 402h
0x1800cbc5d  cmp     word ptr cs:qword_1802DAFE0+6, ax
0x1800cbc64  jz      loc_1800CBD17
0x1800cbc6a  mov     r8d, 10h; Radix
0x1800cbc70  lea     rdx, [rsp+2088h+Buffer]; Buffer
0x1800cbc78  mov     ecx, 4020000h; Value
0x1800cbc7d  call    cs:__imp__ultow
0x1800cbc83  mov     rdx, cs:qword_1802DAFD8; struct CEventLog *
0x1800cbc8a  lea     rcx, [rsp+2088h+var_1CB8]; this
0x1800cbc92  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1800cbc97  nop
0x1800cbc98  mov     rax, [r14+0E00h]
0x1800cbc9f  mov     rcx, [rax+148h]
0x1800cbca6  lea     rbx, cchOriginalDestLength
0x1800cbcad  mov     rdx, rbx
0x1800cbcb0  test    rcx, rcx
0x1800cbcb3  cmovnz  rdx, rcx
0x1800cbcb7  lea     rcx, [rsp+2088h+var_1CB0]
0x1800cbcbf  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cbcc4  mov     rax, [r14+0F0h]
0x1800cbccb  test    rax, rax
0x1800cbcce  cmovnz  rbx, rax
0x1800cbcd2  mov     rdx, rbx
0x1800cbcd5  lea     rcx, [rsp+2088h+var_1C10]
0x1800cbcdd  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cbce2  xor     r9d, r9d
0x1800cbce5  lea     r8, [rsp+2088h+Buffer]
0x1800cbced  mov     edx, 0C0000BDAh; unsigned int
0x1800cbcf2  lea     rcx, [rsp+2088h+var_1CB8]; this
0x1800cbcfa  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800cbcff  nop
0x1800cbd00  lea     rcx, [rsp+2088h+var_1CB8]; this
0x1800cbd08  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1800cbd0d  mov     ebx, 80070005h
0x1800cbd12  jmp     loc_1800CC89F
0x1800cbd17  cmp     dword ptr cs:qword_1802DAFE0, esi
0x1800cbd1d  jnz     loc_1800CBDBF
0x1800cbd23  lea     r8, aSrchgatherpiEr; "[SrchGatherPI] Error initializing perfo"...
0x1800cbd2a  mov     edx, 383h; wchar_t *
0x1800cbd2f  lea     rcx, aOnecoreuapBase_114; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800cbd36  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800cbd3b  mov     rdx, cs:qword_1802DAFD8; struct CEventLog *
0x1800cbd42  lea     rcx, [rsp+2088h+var_1CB8]; this
0x1800cbd4a  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1800cbd4f  nop
0x1800cbd50  mov     rax, [r14+0E00h]
0x1800cbd57  mov     rcx, [rax+148h]
0x1800cbd5e  lea     rbx, cchOriginalDestLength
0x1800cbd65  mov     rdx, rbx
0x1800cbd68  test    rcx, rcx
0x1800cbd6b  cmovnz  rdx, rcx
0x1800cbd6f  lea     rcx, [rsp+2088h+var_1CB0]
0x1800cbd77  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cbd7c  mov     rax, [r14+0F0h]
0x1800cbd83  mov     rdx, rbx
0x1800cbd86  test    rax, rax
0x1800cbd89  cmovnz  rdx, rax
0x1800cbd8d  lea     rcx, [rsp+2088h+var_1C10]
0x1800cbd95  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cbd9a  xor     r8d, r8d
0x1800cbd9d  mov     edx, 0C0000BBFh; unsigned int
0x1800cbda2  lea     rcx, [rsp+2088h+var_1CB8]; this
0x1800cbdaa  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800cbdaf  nop
0x1800cbdb0  lea     rcx, [rsp+2088h+var_1CB8]; this
0x1800cbdb8  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1800cbdbd  jmp     short loc_1800CBDC6
0x1800cbdbf  lea     rbx, cchOriginalDestLength
0x1800cbdc6  cmp     [r14+11E4h], sil
0x1800cbdcd  jnz     short loc_1800CBE12
0x1800cbdcf  lea     rax, [r14+1B0h]
0x1800cbdd6  cmp     [rax], rsi
0x1800cbdd9  jz      short loc_1800CBDE7
0x1800cbddb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800cbde0  lea     rax, [r14+1B0h]
0x1800cbde7  mov     [rsp+2088h+ppv], rax; ppv
0x1800cbdec  lea     r9, IID_IClassFactory; riid
0x1800cbdf3  xor     r8d, r8d; pvReserved
0x1800cbdf6  lea     edx, [r8+17h]; dwClsContext
0x1800cbdfa  lea     rcx, CLSID_CGatherTransaction; rclsid
0x1800cbe01  call    cs:__imp_CoGetClassObject
0x1800cbe07  test    eax, eax
0x1800cbe09  jns     short loc_1800CBE12
0x1800cbe0b  mov     ebx, eax
0x1800cbe0d  jmp     loc_1800CC89F
0x1800cbe12  lea     r8, [r14+208h]; struct CLMString *
0x1800cbe19  lea     rdx, aLogdirectory; "LogDirectory"
0x1800cbe20  lea     rcx, [r14+11E8h]; this
0x1800cbe27  call    ?GetValue@CConfigNode@@QEAAHPEB_WAEAVCLMString@@@Z; CConfigNode::GetValue(wchar_t const *,CLMString &)
0x1800cbe2c  test    eax, eax
0x1800cbe2e  jnz     loc_1800CBEB5
0x1800cbe34  mov     rdx, cs:qword_1802DAFD8; struct CEventLog *
0x1800cbe3b  lea     rcx, [rsp+2088h+var_1348]; this
0x1800cbe43  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1800cbe48  nop
0x1800cbe49  test    r12, r12
0x1800cbe4c  cmovz   r12, rbx
0x1800cbe50  mov     rdx, r12
0x1800cbe53  lea     rcx, [rsp+2088h+var_12A0]
0x1800cbe5b  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cbe60  call    cs:__imp_GetLastError
0x1800cbe66  test    eax, eax
0x1800cbe68  jle     short loc_1800CBE72
0x1800cbe6a  movzx   eax, ax
0x1800cbe6d  or      eax, 80070000h
0x1800cbe72  mov     edx, eax; int
0x1800cbe74  lea     rcx, [rsp+2088h+var_1348]; this
0x1800cbe7c  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x1800cbe81  xor     r9d, r9d
0x1800cbe84  lea     r8, aLogdirectory; "LogDirectory"
0x1800cbe8b  mov     edx, 80000BDEh; unsigned int
0x1800cbe90  lea     rcx, [rsp+2088h+var_1348]; this
0x1800cbe98  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800cbe9d  nop
0x1800cbe9e  lea     rcx, [rsp+2088h+var_1348]; this
0x1800cbea6  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1800cbeab  mov     ebx, 80040D03h
0x1800cbeb0  jmp     loc_1800CC89F
0x1800cbeb5  lea     r8, [r14+2A8h]; struct CLMString *
0x1800cbebc  lea     rdx, aStreamlogsdire; "StreamLogsDirectory"
0x1800cbec3  lea     rcx, [r14+11E8h]; this
0x1800cbeca  call    ?GetValue@CConfigNode@@QEAAHPEB_WAEAVCLMString@@@Z; CConfigNode::GetValue(wchar_t const *,CLMString &)
0x1800cbecf  test    eax, eax
0x1800cbed1  jnz     short loc_1800CBF4A
  ... truncated ...
```

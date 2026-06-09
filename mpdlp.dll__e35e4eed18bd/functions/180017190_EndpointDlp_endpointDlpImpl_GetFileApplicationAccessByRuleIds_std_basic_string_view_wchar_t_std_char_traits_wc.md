# EndpointDlp::endpointDlpImpl::GetFileApplicationAccessByRuleIds(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,EndpointDlp::Client::RuleKind,std::optional<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>> const &,std::optional<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>> const &,ulong,unsigned __int64,ulong,ulong,ulong,std::optional<EndpointDlp::Client::FileAccessInfo> &)

- ea: `0x180017190`
- end: `0x180018559`
- name: `?GetFileApplicationAccessByRuleIds@endpointDlpImpl@EndpointDlp@@QEBAJAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@W4RuleKind@Client@2@AEBV?$optional@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@4@3K_KKKKAEAV?$optional@UFileAccessInfo@Client@EndpointDlp@@@4@@Z`
- size: `5065`
- prototype: ``
- caller_count: `3`
- callee_count: `42`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180018620`
- `0x18002ed90`
- `0x180177a48`

## callees

- `0x180001000`
- `0x180003110`
- `0x180004f3c`
- `0x180005078`
- `0x1800058a4`
- `0x180005c28`
- `0x180017190`
- `0x1800225f4`
- `0x180028a10`
- `0x180029590`
- `0x18002c150`
- `0x1800301a0`
- `0x1800333fc`
- `0x180033520`
- `0x180034420`
- `0x180037afc`
- `0x180038450`
- `0x1800398a0`
- `0x180039ecc`
- `0x18003cc38`
- `0x18004bc70`
- `0x18004bd00`
- `0x1800572a0`
- `0x18005c748`
- `0x18005c780`
- `0x18008acf0`
- `0x180096cf0`
- `0x180099d10`
- `0x1800a23c0`
- `0x1800a244c`
- `0x1800a30d4`
- `0x1800b35d0`
- `0x1800c9310`
- `0x1800c9370`
- `0x1800c9d34`
- `0x1800cc1a0`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18010d56c`
- `0x1801760a8`
- `0x18021492c`
- `0x18023a310`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18001737e`
- `KERNEL32!AcquireSRWLockShared` at `0x18001737e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800173e5`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001754e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800177bc`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800178c7`
- `KERNEL32!ReleaseSRWLockShared` at `0x180017fb1`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800173e5`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001754e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800177bc`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800178c7`
- `KERNEL32!ReleaseSRWLockShared` at `0x180017fb1`
- `ADVAPI32!EventWriteTransfer` at `0x1800172f4`
- `ADVAPI32!EventWriteTransfer` at `0x1800174d7`
- `ADVAPI32!EventWriteTransfer` at `0x1800172f4`
- `ADVAPI32!EventWriteTransfer` at `0x1800174d7`

## string_xrefs

- `0x1800176e7`: `DlpGetFileApplicationAccess: file is excluded. returned empty enforcement array`
- `0x180017414`: `DlpGetFileApplicationAccess: DLP policy doesn't exist`
- `0x1800173a2`: `Call to DlpGetFileApplicationAccess before Initialization`
- `0x180017217`: `Invalid argument for GetFileApplicationAccessByRuleIds`
- `0x18001847a`: `DlpGetFileApplicationAccess: Completed successfully`
- `0x180018045`: `DlpGetFileApplicationAccess: Too many rules to process`
- `0x1800177f2`: `DlpGetFileApplicationAccess: DLP is disabled on server. returned empty enforcement array`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall EndpointDlp::endpointDlpImpl::GetFileApplicationAccessByRuleIds(
        const wchar_t *a1,
        __int64 a2,
        const wchar_t *a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        _BYTE *a8,
        int a9,
        char a10,
        int a11,
        __int64 a12)
{
  const wchar_t *v13; // rdi
  struct EndpointDlp::TraceLoggingProvider *v14; // rax
  _DWORD *v15; // rcx
  __int64 result; // rax
  RTL_SRWLOCK *v17; // r13
  struct EndpointDlp::TraceLoggingProvider *v18; // rax
  int v19; // r8d
  int v20; // r9d
  _DWORD *v21; // rcx
  struct EndpointDlp::TraceLoggingProvider *v22; // rax
  _DWORD *v23; // rcx
  const wchar_t **v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  char Value; // al
  struct EndpointDlp::TraceLoggingProvider *v28; // rax
  int v29; // r8d
  int v30; // r9d
  _DWORD *v31; // rcx
  struct EndpointDlp::TraceLoggingProvider *v32; // rax
  int v33; // r8d
  int v34; // r9d
  _DWORD *v35; // rcx
  unsigned int v36; // r14d
  __int64 v37; // rbx
  __m128i si128; // xmm6
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rdi
  _BYTE *v42; // r8
  const wchar_t *v43; // rdx
  const wchar_t *v44; // r9
  _BYTE *v45; // r10
  char *v46; // r12
  __int64 v47; // rsi
  _QWORD *v48; // r14
  _QWORD *v49; // rbx
  void *v50; // rcx
  __int64 v51; // rcx
  char v52; // al
  void *v53; // r15
  __int64 v54; // rcx
  unsigned __int8 v55; // r13
  unsigned __int64 i; // rsi
  int v57; // ebx
  const wchar_t **v58; // rsi
  int v59; // r10d
  __int64 v60; // rdi
  unsigned int EnforcementForAction; // eax
  unsigned int v62; // edx
  unsigned int v63; // eax
  const char *v64; // rdi
  __int64 v65; // rax
  struct EndpointDlp::TraceLoggingProvider *v66; // rax
  _DWORD *v67; // rbx
  int v68; // r8d
  int v69; // r9d
  wil::ResultException *v70; // rbx
  int v71; // edi
  struct EndpointDlp::TraceLoggingProvider *v72; // rax
  int v73; // ecx
  struct EndpointDlp::TraceLoggingProvider *v74; // rax
  _DWORD *v75; // rbx
  char v76[8]; // [rsp+50h] [rbp-948h] BYREF
  __int64 v77; // [rsp+58h] [rbp-940h] BYREF
  const wchar_t *v78; // [rsp+60h] [rbp-938h] BYREF
  const wchar_t *v79; // [rsp+68h] [rbp-930h] BYREF
  const wchar_t *v80; // [rsp+70h] [rbp-928h] BYREF
  _QWORD *v81; // [rsp+78h] [rbp-920h] BYREF
  const wchar_t *v82; // [rsp+80h] [rbp-918h] BYREF
  wil::ResultException *v83; // [rsp+88h] [rbp-910h] BYREF
  std::exception *v84; // [rsp+90h] [rbp-908h] BYREF
  _BYTE *v85; // [rsp+98h] [rbp-900h] BYREF
  int v86; // [rsp+A0h] [rbp-8F8h]
  __int128 v87; // [rsp+A8h] [rbp-8F0h] BYREF
  __int128 v88; // [rsp+B8h] [rbp-8E0h]
  char v89; // [rsp+C8h] [rbp-8D0h]
  _BYTE v90[24]; // [rsp+D0h] [rbp-8C8h] BYREF
  _BYTE v91[4]; // [rsp+E8h] [rbp-8B0h] BYREF
  _BYTE v92[4]; // [rsp+ECh] [rbp-8ACh] BYREF
  char v93; // [rsp+F0h] [rbp-8A8h] BYREF
  __int16 v94; // [rsp+F1h] [rbp-8A7h]
  char v95; // [rsp+F3h] [rbp-8A5h]
  int v96; // [rsp+F4h] [rbp-8A4h]
  _BYTE v97[4]; // [rsp+F8h] [rbp-8A0h] BYREF
  _BYTE v98[312]; // [rsp+100h] [rbp-898h] BYREF
  __int64 v99; // [rsp+238h] [rbp-760h] BYREF
  __int128 v100; // [rsp+240h] [rbp-758h]
  int v101; // [rsp+250h] [rbp-748h]
  _BYTE v102[32]; // [rsp+258h] [rbp-740h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v103; // [rsp+278h] [rbp-720h] BYREF
  __m128i v104; // [rsp+288h] [rbp-710h]
  __int128 v105; // [rsp+298h] [rbp-700h] BYREF
  __m128i v106; // [rsp+2A8h] [rbp-6F0h]
  __int128 v107; // [rsp+2B8h] [rbp-6E0h] BYREF
  __m128i v108; // [rsp+2C8h] [rbp-6D0h]
  char v109; // [rsp+2D8h] [rbp-6C0h]
  _BYTE v110[32]; // [rsp+2E0h] [rbp-6B8h] BYREF
  char v111[32]; // [rsp+300h] [rbp-698h] BYREF
  char v112[48]; // [rsp+320h] [rbp-678h] BYREF
  char v113; // [rsp+350h] [rbp-648h]
  _OWORD v114[21]; // [rsp+360h] [rbp-638h] BYREF
  __int64 v115; // [rsp+4B0h] [rbp-4E8h]
  __int64 v116; // [rsp+4B8h] [rbp-4E0h]
  __int128 v117; // [rsp+4C0h] [rbp-4D8h]
  __m128i v118; // [rsp+4D0h] [rbp-4C8h]
  _WORD v119[464]; // [rsp+4E0h] [rbp-4B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+880h] [rbp-118h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+8A0h] [rbp-F8h] BYREF
  __int128 v122; // [rsp+8B0h] [rbp-E8h]
  const char *v123; // [rsp+8C0h] [rbp-D8h]
  __int64 v124; // [rsp+8C8h] [rbp-D0h]
  const wchar_t *v125; // [rsp+8D0h] [rbp-C8h]
  __int64 v126; // [rsp+8D8h] [rbp-C0h]
  struct _EVENT_DATA_DESCRIPTOR v127; // [rsp+8E0h] [rbp-B8h] BYREF
  __m128i v128; // [rsp+8F0h] [rbp-A8h]
  __int128 v129; // [rsp+900h] [rbp-98h] BYREF
  __m128i v130; // [rsp+910h] [rbp-88h] BYREF
  __int128 v131; // [rsp+920h] [rbp-78h] BYREF
  __m128i v132; // [rsp+930h] [rbp-68h]

  v78 = a3;
  v80 = (const wchar_t *)a2;
  v13 = a1;
  v79 = a1;
  v81 = (_QWORD *)a2;
  if ( !*(_QWORD *)(a2 + 8) )
  {
    v14 = EndpointDlp::TraceLoggingProvider::Instance();
    v15 = *(_DWORD **)v14;
    if ( **(_DWORD **)v14 > 2u )
    {
      LODWORD(v85) = -2147024809;
      v125 = L"Invalid argument for GetFileApplicationAccessByRuleIds";
      v126 = 110;
      v123 = (const char *)&v85;
      v124 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = *((_QWORD *)v15 + 1);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      *(_QWORD *)&v122 = byte_1802BDE45;
      *((_QWORD *)&v122 + 1) = 0x100000024LL;
      LODWORD(v77) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*((_QWORD *)v15 + 4), &EventDescriptor, 0, 0, 4u, &UserData);
    }
    return 2147942487LL;
  }
  if ( *(_BYTE *)(a12 + 616) )
  {
    if ( *(_BYTE *)(a12 + 608) )
    {
      std::optional<std::wstring>::~optional<std::wstring>(a12 + 560);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 528));
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 496));
    }
    if ( *(_BYTE *)(a12 + 488) )
    {
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 456));
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 424));
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 392));
    }
    EndpointDlp::Client::FileRuleInfo::~FileRuleInfo((EndpointDlp::Client::FileRuleInfo *)(a12 + 8));
    *(_BYTE *)(a12 + 616) = 0;
  }
  v17 = (RTL_SRWLOCK *)(v13 + 184);
  AcquireSRWLockShared((PSRWLOCK)v13 + 46);
  v82 = v13 + 184;
  if ( !*((_BYTE *)v13 + 376) )
  {
    v18 = EndpointDlp::TraceLoggingProvider::Instance();
    v21 = *(_DWORD **)v18;
    if ( **(_DWORD **)v18 > 2u )
    {
      v82 = L"Call to DlpGetFileApplicationAccess before Initialization";
      LODWORD(v77) = -2147023782;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (_DWORD)v21,
        (unsigned int)byte_1802BE449,
        v19,
        v20,
        (__int64)&v77,
        (__int64)&v82);
    }
    if ( v13 != (const wchar_t *)-368LL )
      ReleaseSRWLockShared((PSRWLOCK)v13 + 46);
    return 2147943514LL;
  }
  if ( !*((_QWORD *)v13 + 48) )
  {
    v22 = EndpointDlp::TraceLoggingProvider::Instance();
    v23 = *(_DWORD **)v22;
    if ( **(_DWORD **)v22 > 4u )
    {
      v123 = "DlpGetFileApplicationAccess: DLP policy doesn't exist";
      v124 = 54;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = *((_QWORD *)v23 + 1);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      *(_QWORD *)&v122 = &dword_1802C0D7C;
      *((_QWORD *)&v122 + 1) = 0x100000018LL;
      LODWORD(v77) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*((_QWORD *)v23 + 4), &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( *(_BYTE *)(a12 + 616) )
    {
      if ( *(_BYTE *)(a12 + 608) )
      {
        std::optional<std::wstring>::~optional<std::wstring>(a12 + 560);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 528));
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 496));
      }
      if ( *(_BYTE *)(a12 + 488) )
      {
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 456));
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 424));
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 392));
      }
      EndpointDlp::Client::FileRuleInfo::~FileRuleInfo((EndpointDlp::Client::FileRuleInfo *)(a12 + 8));
      *(_BYTE *)(a12 + 616) = 0;
    }
    if ( v13 != (const wchar_t *)-368LL )
      ReleaseSRWLockShared((PSRWLOCK)v13 + 46);
    return 0;
  }
  try
  {
    v24 = (const wchar_t **)v80;
    std::wstring::wstring(v90, v80);
    v89 = 0;
    if ( *(_BYTE *)(a6 + 16) )
    {
      v25 = std::wstring::wstring(&EventDescriptor, a6);
      v87 = 0;
      v88 = 0;
      v87 = *(_OWORD *)v25;
      v88 = *(_OWORD *)(v25 + 16);
      *(_QWORD *)(v25 + 16) = 0;
      *(_QWORD *)(v25 + 24) = 7;
      *(_WORD *)v25 = 0;
      v89 = 1;
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&EventDescriptor);
    }
    LOBYTE(v123) = 0;
    if ( *(_BYTE *)(a5 + 16) )
    {
      v26 = std::wstring::wstring(&EventDescriptor, a5);
      if ( (_BYTE)v123 )
      {
        std::wstring::operator=(&UserData, v26);
      }
      else
      {
        UserData = 0;
        v122 = 0;
        UserData = *(struct _EVENT_DATA_DESCRIPTOR *)v26;
        v122 = *(_OWORD *)(v26 + 16);
        *(_QWORD *)(v26 + 16) = 0;
        *(_QWORD *)(v26 + 24) = 7;
        *(_WORD *)v26 = 0;
        LOBYTE(v123) = 1;
      }
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&EventDescriptor);
    }
    Value = Dlp::FeatureControl::GetValue(85);
    if ( (unsigned __int8)EndpointDlp::DlpPolicy::IsExcluded(*((_QWORD *)v13 + 48), v90, (Value & 4) != 0) )
    {
      v28 = EndpointDlp::TraceLoggingProvider::Instance();
      v31 = *(_DWORD **)v28;
      if ( **(_DWORD **)v28 > 4u )
      {
        v78 = *v24;
        v79 = L"DlpGetFileApplicationAccess: file is excluded. returned empty enforcement array";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
          (_DWORD)v31,
          (unsigned int)&word_1802C17A6,
          v29,
          v30,
          (__int64)&v79,
          (__int64)&v78);
      }
      if ( *(_BYTE *)(a12 + 616) )
      {
        if ( *(_BYTE *)(a12 + 608) )
        {
          std::optional<std::wstring>::~optional<std::wstring>(a12 + 560);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 528));
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 496));
        }
        if ( *(_BYTE *)(a12 + 488) )
        {
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 456));
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 424));
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 392));
        }
        EndpointDlp::Client::FileRuleInfo::~FileRuleInfo((EndpointDlp::Client::FileRuleInfo *)(a12 + 8));
        *(_BYTE *)(a12 + 616) = 0;
      }
      std::optional<std::wstring>::~optional<std::wstring>(&UserData);
      std::optional<std::wstring>::~optional<std::wstring>(&v87);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v90);
      if ( v13 != (const wchar_t *)-368LL )
        ReleaseSRWLockShared((PSRWLOCK)v13 + 46);
      return 0;
    }
    if ( *(_BYTE *)(*((_QWORD *)v13 + 48) + 177LL) )
    {
      v32 = EndpointDlp::TraceLoggingProvider::Instance();
      v35 = *(_DWORD **)v32;
      if ( **(_DWORD **)v32 > 4u )
      {
        v78 = *v24;
        v79 = L"DlpGetFileApplicationAccess: DLP is disabled on server. returned empty enforcement array";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
          (_DWORD)v35,
          (unsigned int)byte_1802C05A9,
          v33,
          v34,
          (__int64)&v79,
          (__int64)&v78);
      }
      if ( *(_BYTE *)(a12 + 616) )
      {
        if ( *(_BYTE *)(a12 + 608) )
        {
          std::optional<std::wstring>::~optional<std::wstring>(a12 + 560);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 528));
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 496));
        }
        if ( *(_BYTE *)(a12 + 488) )
        {
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 456));
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 424));
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 392));
        }
        EndpointDlp::Client::FileRuleInfo::~FileRuleInfo((EndpointDlp::Client::FileRuleInfo *)(a12 + 8));
        *(_BYTE *)(a12 + 616) = 0;
      }
      std::optional<std::wstring>::~optional<std::wstring>(&UserData);
      std::optional<std::wstring>::~optional<std::wstring>(&v87);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v90);
      if ( v13 != (const wchar_t *)-368LL )
        ReleaseSRWLockShared((PSRWLOCK)v13 + 46);
      return 0;
    }
    if ( !*((_QWORD *)v13 + 50) )
      di::TelemetryAssert::AssertTriggeredNoArgs();
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v36 = 0;
    v96 = 0;
    memset(v114, 0, 0x140u);
    v37 = 10;
    v77 = 10;
    `eh vector constructor iterator'(
      v114,
      0x20u,
      0xAu,
      (void (*)(void *))EndpointDlp::Client::DlpActionInfoRuleType::DlpActionInfoRuleType,
      (void (*)(void *))EndpointDlp::Client::DlpActionInfoRuleType::~DlpActionInfoRuleType);
    v114[20] = 0;
    v115 = 0;
    v116 = 0;
    v117 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v118 = si128;
    LOWORD(v117) = 0;
    *(_QWORD *)&v114[0] = 0;
    BYTE9(v114[1]) = 0;
    *(_QWORD *)&v114[2] = 1;
    BYTE9(v114[3]) = 0;
    *(_QWORD *)&v114[4] = 2;
    BYTE9(v114[5]) = 0;
    *(_QWORD *)&v114[6] = 3;
    BYTE9(v114[7]) = 0;
    *(_QWORD *)&v114[8] = 4;
    BYTE9(v114[9]) = 0;
    *(_QWORD *)&v114[10] = 5;
    BYTE9(v114[11]) = 0;
    *(_QWORD *)&v114[12] = 6;
    BYTE9(v114[13]) = 0;
    *(_QWORD *)&v114[14] = 7;
    BYTE9(v114[15]) = 0;
    *(_QWORD *)&v114[16] = 8;
    BYTE9(v114[17]) = 0;
    *(_QWORD *)&v114[18] = 9;
    BYTE9(v114[19]) = 0;
    EndpointDlp::Client::FileRuleInfo::FileRuleInfo(v97, v114);
    EndpointDlp::Client::FileRuleInfo::~FileRuleInfo((EndpointDlp::Client::FileRuleInfo *)v114);
    v109 = 0;
    v113 = 0;
    v93 = 0;
    v96 = 0;
    v101 = a4;
    if ( &v99 != (__int64 *)v78 )
      std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(
        &v99,
        *(_QWORD *)v78,
        (__int64)(*((_QWORD *)v78 + 1) - *(_QWORD *)v78) >> 5);
    std::wstring::operator=(v102, *((void **)v13 + 48));
    if ( (a10 & 1) != 0 || !v89 )
    {
      v55 = 0;
    }
    else
    {
      v85 = a8;
      v86 = a7;
      EventDescriptor = 0;
      v39 = *((_QWORD *)v13 + 49);
      if ( v39 )
        _InterlockedIncrement((volatile signed __int32 *)(v39 + 8));
      EventDescriptor = (EVENT_DESCRIPTOR)*((_OWORD *)v13 + 24);
      v76[0] = EndpointDlp::Enlightenment::IsEnlightenedApplication(&EventDescriptor, v90, &v87, &v85);
      if ( v76[0] && !(unsigned int)Dlp::FeatureControl::GetValue(133) )
      {
        v40 = a12 + 8;
        *(_BYTE *)a12 = v93;
        *(_DWORD *)(a12 + 4) = v96;
        if ( *(_BYTE *)(a12 + 616) )
        {
          v41 = a12 + 24;
          v42 = &v97[-v40];
          v79 = (const wchar_t *)&v97[-v40];
          v43 = (const wchar_t *)&v98[-v40];
          v78 = (const wchar_t *)&v98[-v40];
          v44 = (const wchar_t *)&v91[-v40];
          v80 = (const wchar_t *)&v91[-v40];
          v45 = &v92[-v40];
          v85 = &v92[-v40];
          v46 = &v93 - v40;
          do
          {
            *(_DWORD *)(v41 - 16) = *(_DWORD *)((char *)v44 + v41);
            *(_DWORD *)(v41 - 12) = *(_DWORD *)&v45[v41];
            v47 = v41 - 8;
            if ( (char *)(v41 - 8) != &v46[v41] )
            {
              v48 = *(_QWORD **)v47;
              v49 = *(_QWORD **)(*(_QWORD *)v47 + 8LL);
              if ( !*((_BYTE *)v49 + 25) )
              {
                do
                {
                  std::_Tree_val<std::_Tree_simple_types<unsigned char>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned char,void *>>>(
                    v41 - 8,
                    v41 - 8,
                    v49[2]);
                  v50 = v49;
                  v49 = (_QWORD *)*v49;
                  operator delete(v50, (const struct std::nothrow_t *)0x20);
                }
                while ( !*((_BYTE *)v49 + 25) );
                v43 = v78;
                v42 = v79;
                v44 = v80;
                v45 = v85;
              }
              v48[1] = v48;
              *v48 = v48;
              v48[2] = v48;
              v51 = *(_QWORD *)(v41 - 8);
              *(_QWORD *)(v41 - 8) = *(_QWORD *)&v46[v41];
              *(_QWORD *)&v46[v41] = v51;
              *(_QWORD *)v41 = *(_QWORD *)&v42[v41];
              *(_QWORD *)&v42[v41] = 0;
              v37 = v77;
            }
            *(_WORD *)(v41 + 8) = *(const wchar_t *)((char *)v43 + v41);
            v41 += 32;
            v77 = --v37;
          }
          while ( v37 );
          if ( (__int64 *)(a12 + 328) != &v99 )
          {
            std::vector<std::wstring>::_Tidy(a12 + 328);
            *(_QWORD *)(a12 + 328) = v99;
            *(_OWORD *)(a12 + 336) = v100;
            v99 = 0;
            v100 = 0;
          }
          *(_DWORD *)(a12 + 352) = v101;
          std::wstring::operator=(a12 + 360, v102);
          v52 = *(_BYTE *)(a12 + 488);
          if ( v109 )
          {
            if ( v52 )
            {
              std::wstring::operator=(a12 + 392, &v103);
              std::wstring::operator=(a12 + 424, &v105);
              std::wstring::operator=(a12 + 456, &v107);
            }
            else
            {
              *(struct _EVENT_DATA_DESCRIPTOR *)(a12 + 392) = v103;
              *(__m128i *)(a12 + 408) = v104;
              v104.m128i_i64[0] = 0;
              v104.m128i_i64[1] = 7;
              LOWORD(v103.Ptr) = 0;
              *(_OWORD *)(a12 + 424) = v105;
              *(__m128i *)(a12 + 440) = v106;
              v106.m128i_i64[0] = 0;
              v106.m128i_i64[1] = 7;
              LOWORD(v105) = 0;
              *(_OWORD *)(a12 + 456) = v107;
              *(__m128i *)(a12 + 472) = v108;
              v108.m128i_i64[0] = 0;
              v108.m128i_i64[1] = 7;
              LOWORD(v107) = 0;
              *(_BYTE *)(a12 + 488) = 1;
            }
          }
          else if ( v52 )
          {
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 456));
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 424));
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 392));
            *(_BYTE *)(a12 + 488) = 0;
          }
          v53 = (void *)(a12 + 496);
          if ( v113 )
          {
            std::_Optional_construct_base<EndpointDlp::Client::OverrideActionInfo>::_Assign<EndpointDlp::Client::OverrideActionInfo>(
              v53,
              v110);
          }
          else if ( *(_BYTE *)(a12 + 608) )
          {
            std::optional<std::wstring>::~optional<std::wstring>(a12 + 560);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>((void *)(a12 + 528));
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v53);
            *(_BYTE *)(a12 + 608) = 0;
          }
        }
        else
        {
          EndpointDlp::Client::FileRuleInfo::FileRuleInfo(v40, v97);
          *(_BYTE *)(a12 + 488) = 0;
          if ( v109 )
            std::_Optional_construct_base<EndpointDlp::Client::ApplicationGroupInfo>::_Construct<EndpointDlp::Client::ApplicationGroupInfo>(
              a12 + 392,
              &v103);
          *(_BYTE *)(a12 + 608) = 0;
          if ( v113 )
          {
            EndpointDlp::Client::OverrideActionInfo::OverrideActionInfo(a12 + 496, v110);
            *(_BYTE *)(v54 + 112) = 1;
          }
          *(_BYTE *)(a12 + 616) = 1;
        }
        if ( v113 )
        {
          std::optional<std::wstring>::~optional<std::wstring>(v112);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v111);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v110);
        }
        if ( v109 )
        {
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v107);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v105);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v103);
        }
        EndpointDlp::Client::FileRuleInfo::~FileRuleInfo((EndpointDlp::Client::FileRuleInfo *)v97);
        std::optional<std::wstring>::~optional<std::wstring>(&UserData);
        std::optional<std::wstring>::~optional<std::wstring>(&v87);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v90);
        if ( v17 )
          ReleaseSRWLockShared(v17);
        return 0;
      }
      v55 = v76[0];
    }
    for ( i = 0; ; ++i )
    {
      v57 = v99;
      if ( i >= ((__int64)v100 - v99) >> 5 )
      {
LABEL_128:
        v58 = (const wchar_t **)v80;
LABEL_129:
        if ( *(_QWORD *)v78 == *((_QWORD *)v78 + 1) )
        {
          v64 = L"None";
        }
        else
        {
          v65 = std::vector<std::wstring>::at(v78);
          v64 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v65);
        }
        v66 = EndpointDlp::TraceLoggingProvider::Instance();
        v67 = *(_DWORD **)v66;
        if ( **(_DWORD **)v66 > 4u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)v66, 0) )
        {
          *(_QWORD *)&EventDescriptor.Id = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v102);
          v78 = (const wchar_t *)v64;
          v79 = *v58;
          v80 = L"DlpGetFileApplicationAccess: Completed successfully";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            (_DWORD)v67,
            (unsigned int)&byte_1802C0AB7,
            v68,
            v69,
            (__int64)&v80,
            (__int64)&v79,
            (__int64)&v78,
            (__int64)&EventDescriptor);
        }
        std::_Optional_construct_base<EndpointDlp::Client::FileAccessInfo>::_Assign<EndpointDlp::Client::FileAccessInfo>(
          a12,
          &v93);
        EndpointDlp::Client::FileAccessInfo::~FileAccessInfo((EndpointDlp::Client::FileAccessInfo *)&v93);
        std::optional<std::wstring>::~optional<std::wstring>(&UserData);
        std::optional<std::wstring>::~optional<std::wstring>(&v87);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v90);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v82);
        return 0;
      }
      if ( i > 0xFF )
      {
        if ( **(_DWORD **)EndpointDlp::TraceLoggingProvider::Instance() > 2u )
        {
          v79 = (const wchar_t *)(((__int64)v100 - v99) >> 5);
          v58 = (const wchar_t **)v80;
          v80 = *(const wchar_t **)v80;
          *(_QWORD *)&EventDescriptor.Id = L"DlpGetFileApplicationAccess: Too many rules to process";
          LODWORD(v77) = -2147024809;
          v132.m128i_i64[0] = (__int64)&v79;
          v132.m128i_i64[1] = 8;
          _tlgWrapSz<wchar_t>::Fill(&v80, &v131);
          _tlgWrapSz<wchar_t>::Fill(&EventDescriptor, &v130);
          *(_QWORD *)&v129 = &v77;
          *((_QWORD *)&v129 + 1) = 4;
          tlgWriteTransfer_EventWriteTransfer(v59, (int)&word_1802BEEDA, 0, 0, 6u, &v127);
          goto LABEL_129;
        }
        goto LABEL_128;
      }
      v76[0] = 0;
      memset(v119, 0, 0x396u);
      LODWORD(v85) = 0;
      memset(v114, 0, 88);
      BYTE8(v114[11]) = 0;
      LODWORD(v77) = 10;
      v60 = *((_QWORD *)v13 + 48);
      if ( v89 )
        std::wstring::wstring(&EventDescriptor, &v87);
      else
        std::wstring::wstring(&EventDescriptor, &qword_18025C818);
      _mm_lfence();
      EndpointDlp::DlpPolicy::GetApplicationAccess(
        v60,
        v57 + 32 * i,
        (unsigned int)&EventDescriptor,
        (unsigned int)&UserData,
        (__int64)v76,
        (__int64)&v77,
        (__int64)v114 + 4,
        (__int64)v119,
        (__int64)&v85,
        a11);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&EventDescriptor);
      if ( v119[0] )
      {
        std::wstring::wstring(&v127, v119);
        std::wstring::wstring(&v129, &v119[73]);
        std::wstring::wstring(&v131, &v119[202]);
        if ( v109 )
        {
          std::wstring::operator=(&v103, &v127);
          std::wstring::operator=(&v105, &v129);
          std::wstring::operator=(&v107, &v131);
        }
        else
        {
          v103 = v127;
          v104 = v128;
          v128 = si128;
          LOWORD(v127.Ptr) = 0;
          v105 = v129;
          v106 = v130;
          v130 = si128;
          LOWORD(v129) = 0;
          v107 = v131;
          v108 = v132;
          v132 = si128;
          LOWORD(v131) = 0;
          v109 = 1;
        }
        RealtimeProtection::DlpThrottle::DlpThrottleCloudSyncEvent::~DlpThrottleCloudSyncEvent((RealtimeProtection::DlpThrottle::DlpThrottleCloudSyncEvent *)&v127);
      }
      if ( (_DWORD)v85 )
      {
        if ( (_DWORD)v85 == 2 )
        {
          v96 = 2;
          EnforcementForAction = EndpointDlp::Client::RuleAccessInfo::GetEnforcementForAction(v114, 7);
          if ( (unsigned __int8)_(v36, EnforcementForAction) )
            goto LABEL_123;
        }
        else
        {
          v63 = EndpointDlp::Client::RuleAccessInfo::GetEnforcementForAction(v114, 5);
          if ( (unsigned __int8)_(v36, v63) )
          {
            v96 = (int)v85;
LABEL_123:
            v36 = v62;
          }
        }
      }
      if ( v93 || (v93 = 0, v76[0]) )
        v93 = 1;
      EndpointDlp::_anonymous_namespace_::MergeRuleAccessActions(v97, v114, (unsigned __int8)i, v55);
      EndpointDlp::Client::RuleAccessInfo::~RuleAccessInfo((EndpointDlp::Client::RuleAccessInfo *)v114);
      v13 = v79;
    }
  }
  catch ( wil::ResultException *v83 )
  {
    v70 = v83;
    v71 = *((_DWORD *)v83 + 8);
    LODWORD(v85) = v71;
    v72 = EndpointDlp::TraceLoggingProvider::Instance();
    if ( **(_DWORD **)v72 > 2u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)v72, 0) )
    {
      *(_QWORD *)&EventDescriptor.Id = *((_QWORD *)v70 + 6);
      v81 = (_QWORD *)*v81;
      v78 = L"DlpGetFileApplicationAccess: Failed to get the file actions";
      LODWORD(v77) = v71;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v73,
        (int)&word_1802BEB8E,
        (__int64)&v77,
        (__int64)&v78,
        (__int64)&v81,
        (__int64)&EventDescriptor);
    }
    goto LABEL_136;
  }
  catch ( std::exception *v84 )
  {
    LODWORD(v85) = -2147418113;
    v74 = EndpointDlp::TraceLoggingProvider::Instance();
    v75 = *(_DWORD **)v74;
    if ( **(_DWORD **)v74 > 2u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)v74, 0) )
    {
      *(_QWORD *)&EventDescriptor.Id = (*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v84 + 8LL))(v84);
      v81 = (_QWORD *)*v81;
      v78 = L"DlpGetFileApplicationAccess: Failed to get the file actions";
      LODWORD(v77) = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        (int)v75,
        (int)&byte_1802BEFC5,
        (__int64)&v77,
        (__int64)&v78,
        (__int64)&v81,
        (__int64)&EventDescriptor);
    }
LABEL_136:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v82);
    return (unsigned int)v85;
  }
  return result;
}

```

## disassembly

```asm
0x180017190  push    rbx
0x180017192  push    rsi
0x180017193  push    rdi
0x180017194  push    r12
0x180017196  push    r13
0x180017198  push    r14
0x18001719a  push    r15
0x18001719c  sub     rsp, 960h
0x1800171a3  movaps  [rsp+998h+var_48], xmm6
0x1800171ab  mov     rax, cs:__security_cookie
0x1800171b2  xor     rax, rsp
0x1800171b5  mov     [rsp+998h+var_58], rax
0x1800171bd  mov     r12d, r9d
0x1800171c0  mov     [rsp+998h+var_938], r8
0x1800171c5  mov     [rsp+998h+var_928], rdx
0x1800171ca  mov     rdi, rcx
0x1800171cd  mov     [rsp+998h+var_930], rcx
0x1800171d2  mov     r15, [rsp+998h+arg_58]
0x1800171da  mov     [rsp+998h+var_920], rdx
0x1800171df  mov     r14, [rsp+998h+arg_20]
0x1800171e7  mov     rsi, [rsp+998h+arg_28]
0x1800171ef  xor     ebx, ebx
0x1800171f1  cmp     [rdx+8], rbx
0x1800171f5  jnz     loc_180017304
0x1800171fb  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x180017200  mov     rcx, [rax]
0x180017203  cmp     dword ptr [rcx], 2
0x180017206  jbe     loc_1800172FA
0x18001720c  mov     dword ptr [rsp+998h+var_900], 80070057h
0x180017217  lea     rax, aInvalidArgumen_21; "Invalid argument for GetFileApplication"...
0x18001721e  mov     [rsp+998h+var_C8], rax
0x180017226  mov     [rsp+998h+var_C0], 6Eh ; 'n'
0x180017232  lea     rax, [rsp+998h+var_900]
0x18001723a  mov     [rsp+998h+var_D8], rax
0x180017242  mov     [rsp+998h+var_D0], 4
0x18001724e  mov     dword ptr [rsp+998h+EventDescriptor.Id], 0B000000h
0x180017259  movzx   eax, cs:word_1802BDE3B
0x180017260  mov     dword ptr [rsp+998h+EventDescriptor.Level], eax
0x180017267  mov     [rsp+998h+EventDescriptor.Keyword], rbx
0x18001726f  mov     rax, [rcx+8]
0x180017273  mov     [rsp+998h+var_F8.Ptr], rax
0x18001727b  movzx   eax, word ptr [rax]
0x18001727e  mov     [rsp+998h+var_F8.Size], eax
0x180017285  mov     dword ptr [rsp+998h+var_F8.0Ch], 2
0x180017290  lea     rax, byte_1802BDE45
0x180017297  mov     qword ptr [rsp+998h+var_E8], rax
0x18001729f  mov     dword ptr [rsp+998h+var_E8+8], 24h ; '$'
0x1800172aa  mov     dword ptr [rsp+998h+var_E8+0Ch], 1
0x1800172b5  lea     rax, _TraceLoggingMetadataEnd
0x1800172bc  lea     rdx, _TraceLoggingMetadata
0x1800172c3  sub     eax, edx
0x1800172c5  mov     dword ptr [rsp+998h+var_940], eax
0x1800172c9  mov     eax, dword ptr [rsp+998h+var_940]
0x1800172cd  lea     rax, [rsp+998h+var_F8]
0x1800172d5  mov     [rsp+998h+UserData], rax; UserData
0x1800172da  mov     [rsp+998h+UserDataCount], 4; UserDataCount
0x1800172e2  xor     r9d, r9d; RelatedActivityId
0x1800172e5  xor     r8d, r8d; ActivityId
0x1800172e8  lea     rdx, [rsp+998h+EventDescriptor]; EventDescriptor
0x1800172f0  mov     rcx, [rcx+20h]; RegHandle
0x1800172f4  call    cs:__imp_EventWriteTransfer
0x1800172fa  mov     eax, 80070057h
0x1800172ff  jmp     loc_18001852E
0x180017304  lea     rbx, [r15+1F0h]
0x18001730b  cmp     byte ptr [r15+268h], 0
0x180017313  jz      short loc_180017374
0x180017315  cmp     byte ptr [rbx+70h], 0
0x180017319  jz      short loc_180017335
0x18001731b  lea     rcx, [rbx+40h]
0x18001731f  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x180017324  lea     rcx, [rbx+20h]; void *
0x180017328  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001732d  mov     rcx, rbx; void *
0x180017330  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180017335  cmp     byte ptr [r15+1E8h], 0
0x18001733d  jz      short loc_180017363
0x18001733f  lea     rcx, [r15+1C8h]; void *
0x180017346  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001734b  lea     rcx, [r15+1A8h]; void *
0x180017352  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180017357  lea     rcx, [r15+188h]; void *
0x18001735e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180017363  lea     rcx, [r15+8]; this
0x180017367  call    ??1FileRuleInfo@Client@EndpointDlp@@QEAA@XZ; EndpointDlp::Client::FileRuleInfo::~FileRuleInfo(void)
0x18001736c  mov     byte ptr [r15+268h], 0
0x180017374  lea     r13, [rdi+170h]
0x18001737b  mov     rcx, r13; SRWLock
0x18001737e  call    cs:__imp_AcquireSRWLockShared
0x180017384  mov     [rsp+998h+var_918], r13
0x18001738c  cmp     byte ptr [rdi+178h], 0
0x180017393  jnz     short loc_1800173F5
0x180017395  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x18001739a  mov     rcx, [rax]
0x18001739d  cmp     dword ptr [rcx], 2
0x1800173a0  jbe     short loc_1800173DD
0x1800173a2  lea     rax, aCallToDlpgetfi; "Call to DlpGetFileApplicationAccess bef"...
0x1800173a9  mov     [rsp+998h+var_918], rax
0x1800173b1  mov     dword ptr [rsp+998h+var_940], 8007045Ah
0x1800173b9  lea     rax, [rsp+998h+var_918]
0x1800173c1  mov     [rsp+998h+UserData], rax
0x1800173c6  lea     rax, [rsp+998h+var_940]
0x1800173cb  mov     qword ptr [rsp+998h+UserDataCount], rax
0x1800173d0  lea     rdx, byte_1802BE449
0x1800173d7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800173dc  nop
0x1800173dd  test    r13, r13
0x1800173e0  jz      short loc_1800173EB
0x1800173e2  mov     rcx, r13; SRWLock
0x1800173e5  call    cs:__imp_ReleaseSRWLockShared
0x1800173eb  mov     eax, 8007045Ah
0x1800173f0  jmp     loc_18001852E
0x1800173f5  cmp     qword ptr [rdi+180h], 0
0x1800173fd  jnz     loc_18001755B
0x180017403  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x180017408  mov     rcx, [rax]
0x18001740b  cmp     dword ptr [rcx], 4
0x18001740e  jbe     loc_1800174DD
0x180017414  lea     rax, aDlpgetfileappl_4; "DlpGetFileApplicationAccess: DLP policy"...
0x18001741b  mov     [rsp+998h+var_D8], rax
0x180017423  mov     [rsp+998h+var_D0], 36h ; '6'
0x18001742f  xor     esi, esi
0x180017431  mov     dword ptr [rsp+998h+EventDescriptor.Id], 0B000000h
0x18001743c  movzx   eax, cs:word_1802C0D72
0x180017443  mov     dword ptr [rsp+998h+EventDescriptor.Level], eax
0x18001744a  mov     [rsp+998h+EventDescriptor.Keyword], rsi
0x180017452  mov     rax, [rcx+8]
0x180017456  mov     [rsp+998h+var_F8.Ptr], rax
0x18001745e  movzx   eax, word ptr [rax]
0x180017461  mov     [rsp+998h+var_F8.Size], eax
0x180017468  mov     dword ptr [rsp+998h+var_F8.0Ch], 2
0x180017473  lea     rax, dword_1802C0D7C
0x18001747a  mov     qword ptr [rsp+998h+var_E8], rax
0x180017482  mov     dword ptr [rsp+998h+var_E8+8], 18h
0x18001748d  mov     dword ptr [rsp+998h+var_E8+0Ch], 1
0x180017498  lea     rax, _TraceLoggingMetadataEnd
0x18001749f  lea     rdx, _TraceLoggingMetadata
0x1800174a6  sub     eax, edx
0x1800174a8  mov     dword ptr [rsp+998h+var_940], eax
0x1800174ac  mov     eax, dword ptr [rsp+998h+var_940]
0x1800174b0  lea     rax, [rsp+998h+var_F8]
0x1800174b8  mov     [rsp+998h+UserData], rax; UserData
0x1800174bd  mov     [rsp+998h+UserDataCount], 3; UserDataCount
0x1800174c5  xor     r9d, r9d; RelatedActivityId
0x1800174c8  xor     r8d, r8d; ActivityId
0x1800174cb  lea     rdx, [rsp+998h+EventDescriptor]; EventDescriptor
0x1800174d3  mov     rcx, [rcx+20h]; RegHandle
0x1800174d7  call    cs:__imp_EventWriteTransfer
0x1800174dd  cmp     byte ptr [r15+268h], 0
0x1800174e5  jz      short loc_180017546
0x1800174e7  cmp     byte ptr [rbx+70h], 0
0x1800174eb  jz      short loc_180017507
0x1800174ed  lea     rcx, [rbx+40h]
0x1800174f1  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800174f6  lea     rcx, [rbx+20h]; void *
0x1800174fa  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800174ff  mov     rcx, rbx; void *
0x180017502  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180017507  cmp     byte ptr [r15+1E8h], 0
0x18001750f  jz      short loc_180017535
0x180017511  lea     rcx, [r15+1C8h]; void *
0x180017518  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001751d  lea     rcx, [r15+1A8h]; void *
0x180017524  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180017529  lea     rcx, [r15+188h]; void *
0x180017530  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180017535  lea     rcx, [r15+8]; this
0x180017539  call    ??1FileRuleInfo@Client@EndpointDlp@@QEAA@XZ; EndpointDlp::Client::FileRuleInfo::~FileRuleInfo(void)
0x18001753e  mov     byte ptr [r15+268h], 0
0x180017546  test    r13, r13
0x180017549  jz      short loc_180017554
0x18001754b  mov     rcx, r13; SRWLock
0x18001754e  call    cs:__imp_ReleaseSRWLockShared
0x180017554  xor     eax, eax
0x180017556  jmp     loc_18001852E
0x18001755b  mov     rbx, [rsp+998h+var_928]
0x180017560  mov     rdx, rbx
0x180017563  lea     rcx, [rsp+998h+var_8C8]
0x18001756b  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x180017570  nop
0x180017571  mov     [rsp+998h+var_8D0], 0
0x180017579  cmp     byte ptr [rsi+10h], 0
0x18001757d  jz      loc_180017614
0x180017583  mov     rdx, rsi
0x180017586  lea     rcx, [rsp+998h+EventDescriptor]
0x18001758e  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x180017593  cmp     [rsp+998h+var_8D0], 0
0x18001759b  jz      short loc_1800175BE
0x18001759d  mov     rdx, rax
0x1800175a0  lea     rcx, [rsp+998h+var_8F0]
0x1800175a8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800175ad  xor     esi, esi
0x1800175af  lea     rcx, [rsp+998h+EventDescriptor]; void *
0x1800175b7  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800175bc  jmp     short loc_180017616
0x1800175be  xorps   xmm0, xmm0
0x1800175c1  movups  [rsp+998h+var_8F0], xmm0
0x1800175c9  xorps   xmm1, xmm1
0x1800175cc  movdqu  [rsp+998h+var_8E0], xmm1
0x1800175d5  movups  xmm0, xmmword ptr [rax]
0x1800175d8  movups  [rsp+998h+var_8F0], xmm0
0x1800175e0  movups  xmm1, xmmword ptr [rax+10h]
0x1800175e4  movups  [rsp+998h+var_8E0], xmm1
0x1800175ec  xor     esi, esi
0x1800175ee  mov     [rax+10h], rsi
0x1800175f2  mov     qword ptr [rax+18h], 7
0x1800175fa  mov     [rax], si
0x1800175fd  mov     [rsp+998h+var_8D0], 1
0x180017605  lea     rcx, [rsp+998h+EventDescriptor]; void *
0x18001760d  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180017612  jmp     short loc_180017616
0x180017614  xor     esi, esi
0x180017616  mov     byte ptr [rsp+998h+var_D8], 0
0x18001761e  cmp     byte ptr [r14+10h], 0
0x180017623  jz      short loc_1800176A3
0x180017625  mov     rdx, r14
0x180017628  lea     rcx, [rsp+998h+EventDescriptor]
0x180017630  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x180017635  cmp     byte ptr [rsp+998h+var_D8], 0
0x18001763d  jz      short loc_180017651
0x18001763f  mov     rdx, rax
0x180017642  lea     rcx, [rsp+998h+var_F8]
0x18001764a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001764f  jmp     short loc_180017696
0x180017651  xorps   xmm0, xmm0
0x180017654  movups  xmmword ptr [rsp+998h+var_F8.Ptr], xmm0
0x18001765c  xorps   xmm1, xmm1
0x18001765f  movdqu  [rsp+998h+var_E8], xmm1
0x180017668  movups  xmm0, xmmword ptr [rax]
0x18001766b  movups  xmmword ptr [rsp+998h+var_F8.Ptr], xmm0
0x180017673  movups  xmm1, xmmword ptr [rax+10h]
0x180017677  movups  [rsp+998h+var_E8], xmm1
0x18001767f  mov     [rax+10h], rsi
0x180017683  mov     qword ptr [rax+18h], 7
0x18001768b  mov     [rax], si
0x18001768e  mov     byte ptr [rsp+998h+var_D8], 1
0x180017696  lea     rcx, [rsp+998h+EventDescriptor]; void *
0x18001769e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800176a3  mov     ecx, 55h ; 'U'
0x1800176a8  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x1800176ad  shr     eax, 2
0x1800176b0  and     al, 1
0x1800176b2  movzx   r8d, al
0x1800176b6  lea     rdx, [rsp+998h+var_8C8]
0x1800176be  mov     rcx, [rdi+180h]
0x1800176c5  call    ?IsExcluded@DlpPolicy@EndpointDlp@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; EndpointDlp::DlpPolicy::IsExcluded(std::wstring const &,bool)
0x1800176ca  test    al, al
0x1800176cc  jz      loc_1800177C9
0x1800176d2  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x1800176d7  mov     rcx, [rax]
0x1800176da  cmp     dword ptr [rcx], 4
0x1800176dd  jbe     short loc_180017713
0x1800176df  mov     rax, [rbx]
0x1800176e2  mov     [rsp+998h+var_938], rax
0x1800176e7  lea     rax, aDlpgetfileappl_1; "DlpGetFileApplicationAccess: file is ex"...
0x1800176ee  mov     [rsp+998h+var_930], rax
0x1800176f3  lea     rax, [rsp+998h+var_938]
0x1800176f8  mov     [rsp+998h+UserData], rax
0x1800176fd  lea     rax, [rsp+998h+var_930]
0x180017702  mov     qword ptr [rsp+998h+UserDataCount], rax
0x180017707  lea     rdx, word_1802C17A6
0x18001770e  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180017713  cmp     byte ptr [r15+268h], 0
0x18001771b  jz      short loc_18001778A
0x18001771d  cmp     byte ptr [r15+260h], 0
0x180017725  jz      short loc_18001774B
0x180017727  lea     rcx, [r15+230h]
0x18001772e  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x180017733  lea     rcx, [r15+210h]; void *
0x18001773a  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001773f  lea     rcx, [r15+1F0h]; void *
0x180017746  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001774b  cmp     byte ptr [r15+1E8h], 0
0x180017753  jz      short loc_180017779
0x180017755  lea     rcx, [r15+1C8h]; void *
0x18001775c  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180017761  lea     rcx, [r15+1A8h]; void *
0x180017768  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001776d  lea     rcx, [r15+188h]; void *
0x180017774  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180017779  lea     rcx, [r15+8]; this
0x18001777d  call    ??1FileRuleInfo@Client@EndpointDlp@@QEAA@XZ; EndpointDlp::Client::FileRuleInfo::~FileRuleInfo(void)
0x180017782  mov     byte ptr [r15+268h], 0
0x18001778a  lea     rcx, [rsp+998h+var_F8]
0x180017792  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x180017797  nop
0x180017798  lea     rcx, [rsp+998h+var_8F0]
0x1800177a0  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1800177a5  nop
0x1800177a6  lea     rcx, [rsp+998h+var_8C8]; void *
0x1800177ae  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800177b3  nop
0x1800177b4  test    r13, r13
0x1800177b7  jz      short loc_1800177C2
0x1800177b9  mov     rcx, r13; SRWLock
0x1800177bc  call    cs:__imp_ReleaseSRWLockShared
0x1800177c2  xor     eax, eax
0x1800177c4  jmp     loc_18001852E
0x1800177c9  mov     rax, [rdi+180h]
0x1800177d0  cmp     byte ptr [rax+0B1h], 0
0x1800177d7  jz      loc_1800178D4
  ... truncated ...
```

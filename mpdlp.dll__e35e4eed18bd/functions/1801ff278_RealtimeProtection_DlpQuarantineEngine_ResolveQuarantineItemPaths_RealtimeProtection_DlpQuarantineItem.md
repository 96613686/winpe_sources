# RealtimeProtection::DlpQuarantineEngine::ResolveQuarantineItemPaths(RealtimeProtection::_DlpQuarantineItem &)

- ea: `0x1801ff278`
- end: `0x180200968`
- name: `?ResolveQuarantineItemPaths@DlpQuarantineEngine@RealtimeProtection@@AEAAJAEAU_DlpQuarantineItem@2@@Z`
- size: `5872`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpQuarantineEngine *__hidden this, struct RealtimeProtection::_DlpQuarantineItem *)`
- caller_count: `2`
- callee_count: `39`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009358c`
- `0x180200fc0`

## callees

- `0x180005c28`
- `0x18000b228`
- `0x18001a444`
- `0x180021f88`
- `0x180022404`
- `0x180029290`
- `0x180029590`
- `0x18002c150`
- `0x180034420`
- `0x180037afc`
- `0x180038450`
- `0x18004b3bc`
- `0x1800542d0`
- `0x1800809d0`
- `0x1800839a0`
- `0x180083a80`
- `0x180083b30`
- `0x180089510`
- `0x1800943dc`
- `0x1800a1a28`
- `0x1800b3710`
- `0x1800b8fcc`
- `0x1800cacac`
- `0x180105f50`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18011db88`
- `0x1801286c8`
- `0x18012b6d8`
- `0x18018411c`
- `0x180184244`
- `0x1801d38fc`
- `0x1801daa2c`
- `0x1801df0d4`
- `0x1801df150`
- `0x1801fcf48`
- `0x1801fe13c`
- `0x1801ff278`
- `0x180201a68`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1801ff741`
- `KERNEL32!GetFileAttributesW` at `0x1801fffb0`
- `KERNEL32!GetFileAttributesW` at `0x1801ff741`
- `KERNEL32!GetFileAttributesW` at `0x1801fffb0`

## string_xrefs

- `0x1801ffb2a`: `ResolveQuarantineItemPaths.InvalidPolicyPath`
- `0x1801ff4bb`: `{"Path":"`
- `0x1801ff816`: `{"Path":"`
- `0x1801ffaa0`: `{"Path":"`
- `0x1801ffd22`: `{"Path":"`
- `0x18020007e`: `{"Path":"`
- `0x180200314`: `{"Path":"`
- `0x1801ff8a0`: `ResolveQuarantineItemPaths.CreateDirectory`
- `0x1802003a1`: `ResolveQuarantineItemPaths.InvalidDefaultPath`
- `0x1801ffdac`: `ResolveQuarantineItemPaths.DefaultPathExpansionFailure`
- `0x1801ff54f`: `ResolveQuarantineItemPaths.PathExpansionFailure`
- `0x18020010b`: `ResolveQuarantineItemPaths.CreateDefaultDirectory`
- `0x180200656`: `ResolveQuarantineItemPaths.Disable`
- `0x18020059c`: `","DefaultPath":"`
- `0x180200588`: `{"PrimaryPath":"`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall RealtimeProtection::DlpQuarantineEngine::ResolveQuarantineItemPaths(
        RealtimeProtection::DlpQuarantineEngine *this,
        struct RealtimeProtection::_DlpQuarantineItem *a2)
{
  struct RealtimeProtection::_DlpQuarantineItem *v2; // rbx
  unsigned int v3; // r14d
  _QWORD *v4; // rsi
  void *const *v5; // r15
  struct tm *v6; // rax
  RealtimeProtection::DlpQuarantineEngine *v7; // rcx
  __int64 v8; // rax
  const wchar_t *v9; // r8
  int v10; // eax
  __int64 v11; // r12
  wchar_t *v12; // rdi
  unsigned int LastFailure; // eax
  __int64 v14; // rax
  int v15; // r9d
  wchar_t *v16; // rax
  wchar_t **v17; // rcx
  const WCHAR *v18; // rcx
  DWORD FileAttributesW; // eax
  __int64 v20; // r8
  __int64 v21; // rax
  struct std::error_code *v22; // r8
  bool directories; // bl
  __int64 v24; // rax
  int v25; // r9d
  _QWORD *v26; // rax
  char *v27; // rdx
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // rax
  _QWORD *v31; // r12
  void *v32; // rax
  __int64 v33; // rax
  _QWORD *v34; // rax
  __int64 v35; // rax
  RealtimeProtection::DlpQuarantineEngine *v36; // rcx
  const wchar_t **v37; // r12
  const wchar_t *v38; // r8
  wchar_t *v39; // rbx
  unsigned int v40; // eax
  __int64 v41; // rax
  int v42; // r9d
  void **v43; // rax
  struct RealtimeProtection::_DlpQuarantineItem *v44; // rsi
  const WCHAR *v45; // rcx
  DWORD v46; // eax
  __int64 v47; // r8
  __int64 v48; // rax
  struct std::error_code *v49; // r8
  bool v50; // si
  __int64 v51; // rax
  int v52; // r9d
  _QWORD *v53; // rax
  char *v54; // rdx
  _QWORD *v55; // rax
  _QWORD *v56; // rax
  __int64 v57; // rax
  _QWORD *v58; // rax
  void *v59; // rax
  __int64 v60; // rax
  _QWORD *v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  int v65; // r9d
  _QWORD *v66; // rax
  const struct std::nothrow_t *v67; // rdx
  void *v68; // r12
  _QWORD *v69; // rax
  _QWORD *v70; // rax
  struct RealtimeProtection::_DlpQuarantineItem *v71; // r15
  std::filesystem::path *v72; // rsi
  const struct std::nothrow_t *v73; // rdx
  char v75; // [rsp+C0h] [rbp-80h]
  char v76; // [rsp+C1h] [rbp-7Fh]
  int v77; // [rsp+C4h] [rbp-7Ch] BYREF
  int v78; // [rsp+C8h] [rbp-78h] BYREF
  int v79; // [rsp+CCh] [rbp-74h] BYREF
  int v80; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v81; // [rsp+D4h] [rbp-6Ch] BYREF
  int v82; // [rsp+DCh] [rbp-64h] BYREF
  int v83; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v84; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v85; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v86; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v87; // [rsp+100h] [rbp-40h] BYREF
  __int64 v88; // [rsp+108h] [rbp-38h] BYREF
  __int64 v89; // [rsp+110h] [rbp-30h] BYREF
  __int64 v90; // [rsp+118h] [rbp-28h] BYREF
  __int64 v91; // [rsp+120h] [rbp-20h] BYREF
  __int64 v92; // [rsp+128h] [rbp-18h] BYREF
  __int64 v93; // [rsp+130h] [rbp-10h] BYREF
  wchar_t *v94; // [rsp+138h] [rbp-8h] BYREF
  __int64 v95[2]; // [rsp+140h] [rbp+0h] BYREF
  void **v96; // [rsp+150h] [rbp+10h] BYREF
  struct RealtimeProtection::_DlpQuarantineItem *v97; // [rsp+158h] [rbp+18h]
  wchar_t *v98; // [rsp+160h] [rbp+20h] BYREF
  __int64 v99; // [rsp+168h] [rbp+28h] BYREF
  __int64 v100; // [rsp+170h] [rbp+30h] BYREF
  void *Src; // [rsp+178h] [rbp+38h]
  _QWORD v102[3]; // [rsp+180h] [rbp+40h] BYREF
  unsigned __int64 v103; // [rsp+198h] [rbp+58h]
  wchar_t *v104; // [rsp+1A0h] [rbp+60h] BYREF
  char v105; // [rsp+1ACh] [rbp+6Ch]
  unsigned __int64 v106; // [rsp+1B8h] [rbp+78h]
  _BYTE v107[32]; // [rsp+1C0h] [rbp+80h] BYREF
  __int64 v108[4]; // [rsp+1E0h] [rbp+A0h] BYREF
  char v109; // [rsp+200h] [rbp+C0h]
  _BYTE v110[32]; // [rsp+208h] [rbp+C8h] BYREF
  _OWORD v111[2]; // [rsp+228h] [rbp+E8h] BYREF
  __time64_t v112[2]; // [rsp+248h] [rbp+108h] BYREF
  __time64_t Time; // [rsp+268h] [rbp+128h] BYREF
  _BYTE v114[48]; // [rsp+270h] [rbp+130h] BYREF
  wchar_t Buffer[80]; // [rsp+2A0h] [rbp+160h] BYREF

  v2 = a2;
  v97 = a2;
  v100 = (__int64)this;
  v75 = 1;
  v76 = 1;
  v111[0] = 0;
  v111[1] = _mm_load_si128((const __m128i *)&_xmm);
  v3 = 0;
  LOWORD(v111[0]) = 0;
  Time = 0;
  v4 = (_QWORD *)((char *)a2 + 440);
  v99 = (__int64)a2 + 440;
  if ( *((_BYTE *)a2 + 48) == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
    goto LABEL_160;
  }
  v5 = (void *const *)((char *)a2 + 720);
  v96 = (void **)((char *)a2 + 720);
  if ( !*((_QWORD *)a2 + 90) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
    goto LABEL_9;
  }
  time64(&Time);
  v6 = localtime64(&Time);
  wcsftime(Buffer, 0x50u, L"_%Y%m%d_%H%M%S", v6);
  std::wstring::wstring(v112, Buffer);
  Src = (char *)v2 + 224;
  if ( !*((_QWORD *)v2 + 30) )
  {
    std::filesystem::path::operator std::wstring((char *)v2 + 192, v102);
    RealtimeProtection::DlpPathCache::GetDosPath(v114, v102);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v102);
    if ( !v114[32] )
    {
      std::optional<std::wstring>::~optional<std::wstring>(v114);
LABEL_13:
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v112);
LABEL_9:
      v3 = -2147024809;
      goto LABEL_160;
    }
    v8 = std::optional<std::wstring>::value(v114);
    std::filesystem::path::operator=<std::wstring,0>((char *)v2 + 224, v8);
    std::optional<std::wstring>::~optional<std::wstring>(v114);
  }
  v98 = 0;
  v9 = (const wchar_t *)v4;
  if ( v4[3] > 7u )
    v9 = (const wchar_t *)*v4;
  v10 = RealtimeProtection::DlpQuarantineEngine::ExpandQuarantinePath(v7, v5, v9, &v98);
  v11 = v10;
  v12 = v98;
  if ( v10 >= 0 )
  {
    std::filesystem::path::path(v110, &v98);
    if ( std::filesystem::path::is_absolute((std::filesystem::path *)v110) )
    {
      std::wstring::assign(v4, v12);
      std::wstring::append(v4, (void *)L"\\");
      std::wstring::append(v4);
      v18 = (const WCHAR *)v4;
      if ( v4[3] > 7u )
        v18 = (const WCHAR *)*v4;
      FileAttributesW = GetFileAttributesW(v18);
      if ( FileAttributesW == -1 || (FileAttributesW & 0x410) != 0x10 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
        v108[0] = 0;
        v108[1] = (__int64)&`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        v21 = (__int64)v4;
        if ( v4[3] > 7u )
          v21 = *v4;
        v84 = v21;
        LOBYTE(v20) = 0;
        std::filesystem::_Convert_Source_to_wide<wchar_t const *,std::filesystem::_Normal_conversion>(v102, &v84, v20);
        directories = std::filesystem::create_directories(
                        (std::filesystem *)v102,
                        (const struct std::filesystem::path *)v108,
                        v22);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v102);
        if ( !directories )
        {
          v75 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              126,
              &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
              LODWORD(v108[0]));
          v24 = std::operator+<wchar_t>(v107);
          std::operator+<wchar_t>(v102, v24, L"\"}");
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
          if ( !g_pcsAsimovLock )
            goto LABEL_73;
          CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
          if ( **(_DWORD **)&g_hMpAsimovProvider <= 5u
            || !(unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
          {
LABEL_72:
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
LABEL_73:
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v102);
LABEL_74:
            v17 = (wchar_t **)v110;
            goto LABEL_75;
          }
          v26 = v102;
          if ( v103 > 7 )
            v26 = (_QWORD *)v102[0];
          v84 = (__int64)v26;
          v90 = (__int64)L"ResolveQuarantineItemPaths.CreateDirectory";
          v89 = (__int64)L"DLPEngine";
          v88 = SLODWORD(v108[0]);
          v27 = byte_1802C715D;
LABEL_71:
          v82 = *((_DWORD *)g_aAsimov + 18);
          v81 = *((_QWORD *)g_aAsimov + 8);
          v80 = *((unsigned __int8 *)g_aAsimov + 60);
          v79 = *((unsigned __int8 *)g_aAsimov + 59);
          v78 = *((unsigned __int8 *)g_aAsimov + 58);
          v77 = *((unsigned __int8 *)g_aAsimov + 57);
          v83 = *((unsigned __int8 *)g_aAsimov + 56);
          v87 = *((_QWORD *)g_aAsimov + 6);
          v35 = *((_QWORD *)g_aAsimov + 5);
          v95[0] = (__int64)L"Quarantine";
          v86 = v35;
          v91 = *((_QWORD *)g_aAsimov + 4);
          v93 = *((_QWORD *)g_aAsimov + 3);
          v92 = *((_QWORD *)g_aAsimov + 2);
          v94 = (wchar_t *)*((_QWORD *)g_aAsimov + 1);
          v85 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            v25,
            (int)v27,
            (__int64)&v85,
            (__int64)&v94,
            (__int64)&v92,
            (__int64)&v93,
            (__int64)&v91,
            (__int64)&v86,
            (__int64)&v87,
            (__int64)&v83,
            (__int64)&v77,
            (__int64)&v78,
            (__int64)&v79,
            (__int64)&v80,
            (__int64)&v81,
            (__int64)&v81 + 4,
            (__int64)&v82,
            (__int64)&v88,
            (__int64)&v89,
            (__int64)v95,
            (__int64)&v90,
            (__int64)&v84);
          goto LABEL_72;
        }
        v2 = v97;
      }
      v28 = (_QWORD *)std::filesystem::path::stem((char *)v2 + 224, v107);
      if ( v28[3] > 7u )
        v28 = (_QWORD *)*v28;
      std::wstring::assign(v111, v28);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
      std::wstring::append(v111);
      v29 = (_QWORD *)std::filesystem::path::extension((char *)v2 + 224, v107);
      if ( v29[3] > 7u )
        v29 = (_QWORD *)*v29;
      std::wstring::append(v111, v29);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
      std::filesystem::_Convert_Source_to_wide<std::wstring,std::filesystem::_Normal_conversion>(&v104, v111);
      std::filesystem::_Convert_Source_to_wide<std::wstring,std::filesystem::_Normal_conversion>(v102, v4);
      v30 = std::filesystem::operator/(v107, v102, &v104);
      v31 = (_QWORD *)((char *)v2 + 272);
      std::wstring::operator=((char *)v2 + 272, v30);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v102);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v104);
      v105 = 0;
      if ( *((_QWORD *)v2 + 37) > 7u )
        v31 = (_QWORD *)*v31;
      std::wstring::wstring(v102, v31);
      RealtimeProtection::DlpPathCache::GetFilterPath(v108, v102, &v104);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v102);
      if ( v109 )
      {
        v32 = (void *)std::optional<std::wstring>::value(v108);
        std::wstring::operator=((char *)v2 + 304, v32);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
      }
      std::optional<std::wstring>::~optional<std::wstring>(v108);
      goto LABEL_74;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
    v75 = 0;
    v33 = std::operator+<wchar_t>(v107);
    std::operator+<wchar_t>(v102, v33, L"\"}");
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
    if ( !g_pcsAsimovLock )
      goto LABEL_73;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
    if ( **(_DWORD **)&g_hMpAsimovProvider <= 5u
      || !(unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
    {
      goto LABEL_72;
    }
    v34 = v102;
    if ( v103 > 7 )
      v34 = (_QWORD *)v102[0];
    v84 = (__int64)v34;
    v90 = (__int64)L"ResolveQuarantineItemPaths.InvalidPolicyPath";
    v89 = (__int64)L"DLPEngine";
    v88 = 1;
    v27 = (char *)&byte_1802C6D11;
    goto LABEL_71;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastFailure = HrGetLastFailure();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, LastFailure);
  }
  v75 = 0;
  v14 = std::operator+<wchar_t>(v107);
  std::operator+<wchar_t>(&v104, v14, L"\"}");
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
  if ( g_pcsAsimovLock )
  {
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v108);
    if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
      && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
    {
      v16 = (wchar_t *)&v104;
      if ( v106 > 7 )
        v16 = v104;
      v94 = v16;
      v85 = (__int64)L"ResolveQuarantineItemPaths.PathExpansionFailure";
      v92 = (__int64)L"Quarantine";
      v93 = (__int64)L"DLPEngine";
      v91 = v11;
      v83 = *((_DWORD *)g_aAsimov + 18);
      v77 = *((_DWORD *)g_aAsimov + 17);
      v78 = *((_DWORD *)g_aAsimov + 16);
      v79 = *((unsigned __int8 *)g_aAsimov + 60);
      v80 = *((unsigned __int8 *)g_aAsimov + 59);
      LODWORD(v81) = *((unsigned __int8 *)g_aAsimov + 58);
      HIDWORD(v81) = *((unsigned __int8 *)g_aAsimov + 57);
      v82 = *((unsigned __int8 *)g_aAsimov + 56);
      v86 = *((_QWORD *)g_aAsimov + 6);
      v87 = *((_QWORD *)g_aAsimov + 5);
      v88 = *((_QWORD *)g_aAsimov + 4);
      v89 = *((_QWORD *)g_aAsimov + 3);
      v95[0] = *((_QWORD *)g_aAsimov + 2);
      v90 = *((_QWORD *)g_aAsimov + 1);
      v84 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v15,
        (int)&dword_1802C6E24,
        (__int64)&v84,
        (__int64)&v90,
        (__int64)v95,
        (__int64)&v89,
        (__int64)&v88,
        (__int64)&v87,
        (__int64)&v86,
        (__int64)&v82,
        (__int64)&v81 + 4,
        (__int64)&v81,
        (__int64)&v80,
        (__int64)&v79,
        (__int64)&v78,
        (__int64)&v77,
        (__int64)&v83,
        (__int64)&v91,
        (__int64)&v93,
        (__int64)&v92,
        (__int64)&v85,
        (__int64)&v94);
    }
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v108);
  }
  v17 = &v104;
LABEL_75:
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v17);
  v94 = 0;
  v37 = (const wchar_t **)(v4 + 4);
  v38 = (const wchar_t *)(v4 + 4);
  if ( v4[7] > 7u )
    v38 = *v37;
  v83 = RealtimeProtection::DlpQuarantineEngine::ExpandQuarantinePath(v36, v96, v38, &v94);
  v39 = v94;
  if ( v83 >= 0 )
  {
    std::filesystem::path::path(v107, &v94);
    if ( std::filesystem::path::is_absolute((std::filesystem::path *)v107) )
    {
      std::wstring::assign(v4 + 4, v39);
      std::wstring::append(v4 + 4, (void *)L"\\");
      v44 = v97;
      std::wstring::append(v37);
      v45 = (const WCHAR *)v37;
      if ( (unsigned __int64)v37[3] > 7 )
        v45 = *v37;
      v46 = GetFileAttributesW(v45);
      if ( v46 == -1 || (v46 & 0x10) == 0 || (v46 & 0x400) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
        v95[0] = 0;
        v95[1] = (__int64)&`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        v48 = (__int64)v37;
        if ( (unsigned __int64)v37[3] > 7 )
          v48 = (__int64)*v37;
        v108[0] = v48;
        LOBYTE(v47) = 0;
        std::filesystem::_Convert_Source_to_wide<wchar_t const *,std::filesystem::_Normal_conversion>(v110, v108, v47);
        v50 = std::filesystem::create_directories(
                (std::filesystem *)v110,
                (const struct std::filesystem::path *)v95,
                v49);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v110);
        if ( !v50 )
        {
          v76 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              131,
              &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
              LODWORD(v95[0]));
          v51 = std::operator+<wchar_t>(v110);
          std::operator+<wchar_t>(v102, v51, L"\"}");
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v110);
          if ( !g_pcsAsimovLock )
            goto LABEL_134;
          CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
          if ( **(_DWORD **)&g_hMpAsimovProvider <= 5u
            || !(unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
          {
LABEL_133:
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
LABEL_134:
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v102);
            goto LABEL_135;
          }
          v53 = v102;
          if ( v103 > 7 )
            v53 = (_QWORD *)v102[0];
          v108[0] = (__int64)v53;
          v96 = (void **)L"ResolveQuarantineItemPaths.CreateDefaultDirectory";
          v84 = (__int64)L"Quarantine";
          v90 = (__int64)L"DLPEngine";
          v95[0] = SLODWORD(v95[0]);
          v54 = &byte_1802C6F37;
LABEL_132:
          LODWORD(v85) = *((_DWORD *)g_aAsimov + 18);
          v82 = *((_DWORD *)g_aAsimov + 17);
          HIDWORD(v81) = *((_DWORD *)g_aAsimov + 16);
          LODWORD(v81) = *((unsigned __int8 *)g_aAsimov + 60);
          v80 = *((unsigned __int8 *)g_aAsimov + 59);
          v79 = *((unsigned __int8 *)g_aAsimov + 58);
          v78 = *((unsigned __int8 *)g_aAsimov + 57);
          v77 = *((unsigned __int8 *)g_aAsimov + 56);
          v89 = *((_QWORD *)g_aAsimov + 6);
          v88 = *((_QWORD *)g_aAsimov + 5);
          v87 = *((_QWORD *)g_aAsimov + 4);
          v86 = *((_QWORD *)g_aAsimov + 3);
          v91 = *((_QWORD *)g_aAsimov + 2);
          v93 = *((_QWORD *)g_aAsimov + 1);
          v92 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            v52,
            (int)v54,
            (__int64)&v92,
            (__int64)&v93,
            (__int64)&v91,
            (__int64)&v86,
            (__int64)&v87,
            (__int64)&v88,
            (__int64)&v89,
            (__int64)&v77,
            (__int64)&v78,
            (__int64)&v79,
            (__int64)&v80,
            (__int64)&v81,
            (__int64)&v81 + 4,
            (__int64)&v82,
            (__int64)&v85,
            (__int64)v95,
            (__int64)&v90,
            (__int64)&v84,
            (__int64)&v96,
            (__int64)v108);
          goto LABEL_133;
        }
        v44 = v97;
      }
      v55 = (_QWORD *)std::filesystem::path::stem((char *)v44 + 224, v110);
      if ( v55[3] > 7u )
        v55 = (_QWORD *)*v55;
      std::wstring::assign(v111, v55);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v110);
      std::wstring::append(v111);
      v56 = (_QWORD *)std::filesystem::path::extension((char *)v44 + 224, v110);
      if ( v56[3] > 7u )
        v56 = (_QWORD *)*v56;
      std::wstring::append(v111, v56);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v110);
      std::filesystem::_Convert_Source_to_wide<std::wstring,std::filesystem::_Normal_conversion>(v102, v111);
      std::filesystem::_Convert_Source_to_wide<std::wstring,std::filesystem::_Normal_conversion>(v110, v37);
      v57 = std::filesystem::operator/(&v104, v110, v102);
      std::wstring::operator=((char *)v44 + 336, v57);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v104);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v110);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v102);
      v105 = 0;
      v58 = (_QWORD *)((char *)v44 + 336);
      if ( *((_QWORD *)v44 + 45) > 7u )
        v58 = (_QWORD *)*v58;
      std::wstring::wstring(v110, v58);
      RealtimeProtection::DlpPathCache::GetFilterPath(v108, v110, &v104);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v110);
      if ( v109 )
      {
        v59 = (void *)std::optional<std::wstring>::value(v108);
        std::wstring::operator=((char *)v44 + 368, v59);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
      }
      std::optional<std::wstring>::~optional<std::wstring>(v108);
LABEL_135:
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
      if ( v76 )
        goto LABEL_151;
      goto LABEL_136;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
    v76 = 0;
    v60 = std::operator+<wchar_t>(v110);
    std::operator+<wchar_t>(v102, v60, L"\"}");
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v110);
    if ( !g_pcsAsimovLock )
      goto LABEL_134;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
    if ( **(_DWORD **)&g_hMpAsimovProvider <= 5u
      || !(unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
    {
      goto LABEL_133;
    }
    v61 = v102;
    if ( v103 > 7 )
      v61 = (_QWORD *)v102[0];
    v108[0] = (__int64)v61;
    v96 = (void **)L"ResolveQuarantineItemPaths.InvalidDefaultPath";
    v84 = (__int64)L"Quarantine";
    v90 = (__int64)L"DLPEngine";
    v95[0] = 1;
    v54 = (char *)&word_1802C704A;
    goto LABEL_132;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v40 = HrGetLastFailure();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v40);
  }
  v41 = std::operator+<wchar_t>(v107);
  std::operator+<wchar_t>(v102, v41, L"\"}");
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
  if ( g_pcsAsimovLock )
  {
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
    if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
      && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
    {
      v43 = (void **)v102;
      if ( v103 > 7 )
        v43 = (void **)v102[0];
      v96 = v43;
      v84 = (__int64)L"ResolveQuarantineItemPaths.DefaultPathExpansionFailure";
      v90 = (__int64)L"Quarantine";
      v95[0] = (__int64)L"DLPEngine";
      v89 = v83;
      v82 = *((_DWORD *)g_aAsimov + 18);
      v81 = *((_QWORD *)g_aAsimov + 8);
      v80 = *((unsigned __int8 *)g_aAsimov + 60);
      v79 = *((unsigned __int8 *)g_aAsimov + 59);
      v78 = *((unsigned __int8 *)g_aAsimov + 58);
      v77 = *((unsigned __int8 *)g_aAsimov + 57);
      LODWORD(v85) = *((unsigned __int8 *)g_aAsimov + 56);
      v88 = *((_QWORD *)g_aAsimov + 6);
      v87 = *((_QWORD *)g_aAsimov + 5);
      v86 = *((_QWORD *)g_aAsimov + 4);
      v91 = *((_QWORD *)g_aAsimov + 3);
      v93 = *((_QWORD *)g_aAsimov + 2);
      v92 = *((_QWORD *)g_aAsimov + 1);
      v108[0] = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v42,
        (int)&byte_1802C6AEB,
        (__int64)v108,
        (__int64)&v92,
        (__int64)&v93,
        (__int64)&v91,
        (__int64)&v86,
        (__int64)&v87,
        (__int64)&v88,
        (__int64)&v85,
        (__int64)&v77,
        (__int64)&v78,
        (__int64)&v79,
        (__int64)&v80,
        (__int64)&v81,
        (__int64)&v81 + 4,
        (__int64)&v82,
        (__int64)&v89,
        (__int64)v95,
        (__int64)&v90,
        (__int64)&v84,
        (__int64)&v96);
    }
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v102);
LABEL_136:
  if ( !v75 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
    _InterlockedExchange((volatile __int32 *)(v100 + 160), 2);
    v62 = std::operator+<wchar_t>(v108);
    v63 = std::operator+<wchar_t>(v110, v62, L"\",\"DefaultPath\":\"");
    v64 = std::operator+<wchar_t>(v107, v63, v37);
    std::operator+<wchar_t>(v102, v64, L"\"}");
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v110);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v108);
    if ( g_pcsAsimovLock )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
      if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
        && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
      {
        v66 = v102;
        if ( v103 > 7 )
          v66 = (_QWORD *)v102[0];
        v100 = (__int64)v66;
        v99 = (__int64)L"ResolveQuarantineItemPaths.Disable";
        v108[0] = (__int64)L"Quarantine";
        v96 = (void **)L"DLPEngine";
        v84 = 1;
        LODWORD(v85) = *((_DWORD *)g_aAsimov + 18);
        v82 = *((_DWORD *)g_aAsimov + 17);
        HIDWORD(v81) = *((_DWORD *)g_aAsimov + 16);
        LODWORD(v81) = *((unsigned __int8 *)g_aAsimov + 60);
        v80 = *((unsigned __int8 *)g_aAsimov + 59);
        v79 = *((unsigned __int8 *)g_aAsimov + 58);
        v78 = *((unsigned __int8 *)g_aAsimov + 57);
        v77 = *((unsigned __int8 *)g_aAsimov + 56);
        v90 = *((_QWORD *)g_aAsimov + 6);
        v95[0] = *((_QWORD *)g_aAsimov + 5);
        v89 = *((_QWORD *)g_aAsimov + 4);
        v88 = *((_QWORD *)g_aAsimov + 3);
        v87 = *((_QWORD *)g_aAsimov + 2);
        v86 = *((_QWORD *)g_aAsimov + 1);
        v91 = 0x2000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
          v65,
          (int)&word_1802C6BFE,
          (__int64)&v91,
          (__int64)&v86,
          (__int64)&v87,
          (__int64)&v88,
          (__int64)&v89,
          (__int64)v95,
          (__int64)&v90,
          (__int64)&v77,
          (__int64)&v78,
          (__int64)&v79,
          (__int64)&v80,
          (__int64)&v81,
          (__int64)&v81 + 4,
          (__int64)&v82,
          (__int64)&v85,
          (__int64)&v84,
          (__int64)&v96,
          (__int64)v108,
          (__int64)&v99,
          (__int64)&v100);
      }
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v104);
    }
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v102);
    if ( v39 )
      operator delete(v39, v67);
    if ( v12 )
      operator delete(v12, v67);
    goto LABEL_13;
  }
LABEL_151:
  v68 = Src;
  v69 = (_QWORD *)std::filesystem::path::stem(Src, v107);
  if ( v69[3] > 7u )
    v69 = (_QWORD *)*v69;
  std::wstring::assign(v111, v69);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
  v70 = (_QWORD *)std::filesystem::path::extension(v68, v107);
  if ( v70[3] > 7u )
    v70 = (_QWORD *)*v70;
  std::wstring::append(v111, v70);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
  std::wstring::append(v111);
  std::wstring::append(v111, L".txt");
  v71 = v97;
  v72 = (struct RealtimeProtection::_DlpQuarantineItem *)((char *)v97 + 400);
  std::wstring::operator=((char *)v97 + 400, v68);
  std::filesystem::_Convert_Source_to_wide<std::wstring,std::filesystem::_Normal_conversion>(v107, v111);
  std::filesystem::path::replace_filename(v72, (const struct std::filesystem::path *)v107);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v107);
  *((_BYTE *)v71 + 48) = 1;
  if ( v39 )
    operator delete(v39, v73);
  if ( v12 )
    operator delete(v12, v73);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v112);
  v3 = v83;
LABEL_160:
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v111);
  return v3;
}

```

## disassembly

```asm
0x1801ff278  mov     [rsp-8+arg_10], rbx
0x1801ff27d  push    rbp
0x1801ff27e  push    rsi
0x1801ff27f  push    rdi
0x1801ff280  push    r12
0x1801ff282  push    r13
0x1801ff284  push    r14
0x1801ff286  push    r15
0x1801ff288  lea     rbp, [rsp-210h]
0x1801ff290  sub     rsp, 350h
0x1801ff297  mov     rax, cs:__security_cookie
0x1801ff29e  xor     rax, rsp
0x1801ff2a1  mov     [rbp+240h+var_40], rax
0x1801ff2a8  mov     rbx, rdx
0x1801ff2ab  mov     [rbp+240h+var_228], rdx
0x1801ff2af  mov     [rbp+240h+var_210], rcx
0x1801ff2b3  mov     [rbp+240h+var_2C0], 1
0x1801ff2b7  mov     [rbp+240h+var_2BF], 1
0x1801ff2bb  xorps   xmm0, xmm0
0x1801ff2be  movups  [rbp+240h+var_158], xmm0
0x1801ff2c5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801ff2cd  movdqu  [rbp+240h+var_148], xmm1
0x1801ff2d5  xor     r14d, r14d
0x1801ff2d8  mov     word ptr [rbp+240h+var_158], r14w
0x1801ff2e0  mov     [rbp+240h+Time], r14
0x1801ff2e7  lea     rsi, [rdx+1B8h]
0x1801ff2ee  mov     [rbp+240h+var_218], rsi
0x1801ff2f2  cmp     byte ptr [rdx+30h], 1
0x1801ff2f6  jnz     short loc_1801FF332
0x1801ff2f8  lea     r15, WPP_GLOBAL_Control
0x1801ff2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ff306  cmp     rcx, r15
0x1801ff309  jz      loc_18020092F
0x1801ff30f  test    byte ptr [rcx+1Ch], 10h
0x1801ff313  jz      loc_18020092F
0x1801ff319  lea     edx, [r14+7Bh]
0x1801ff31d  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801ff324  mov     rcx, [rcx+10h]
0x1801ff328  call    WPP_SF_
0x1801ff32d  jmp     loc_18020092F
0x1801ff332  lea     r15, [rdx+2D0h]
0x1801ff339  mov     [rbp+240h+var_230], r15
0x1801ff33d  cmp     [r15], r14
0x1801ff340  jnz     short loc_1801FF37B
0x1801ff342  lea     r15, WPP_GLOBAL_Control
0x1801ff349  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ff350  cmp     rcx, r15
0x1801ff353  jz      short loc_1801FF370
0x1801ff355  test    byte ptr [rcx+1Ch], 1
0x1801ff359  jz      short loc_1801FF370
0x1801ff35b  mov     edx, 7Ch ; '|'
0x1801ff360  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801ff367  mov     rcx, [rcx+10h]
0x1801ff36b  call    WPP_SF_
0x1801ff370  mov     r14d, 80070057h
0x1801ff376  jmp     loc_18020092F
0x1801ff37b  lea     rcx, [rbp+240h+Time]; Time
0x1801ff382  call    _time64
0x1801ff387  lea     rcx, [rbp+240h+Time]; Time
0x1801ff38e  call    _localtime64
0x1801ff393  mov     r9, rax; Tm
0x1801ff396  lea     r8, aYMDHMS; "_%Y%m%d_%H%M%S"
0x1801ff39d  mov     edx, 50h ; 'P'; SizeInWords
0x1801ff3a2  lea     rcx, [rbp+240h+Buffer]; Buffer
0x1801ff3a9  call    wcsftime
0x1801ff3ae  lea     rdx, [rbp+240h+Buffer]
0x1801ff3b5  lea     rcx, [rbp+240h+var_138]
0x1801ff3bc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801ff3c1  nop
0x1801ff3c2  lea     rdi, [rbx+0E0h]
0x1801ff3c9  mov     [rbp+240h+Src], rdi
0x1801ff3cd  cmp     [rdi+10h], r14
0x1801ff3d1  jnz     short loc_1801FF448
0x1801ff3d3  lea     rcx, [rbx+0C0h]
0x1801ff3da  lea     rdx, [rbp+240h+var_200]
0x1801ff3de  call    ??Bpath@filesystem@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::filesystem::path::operator std::wstring(void)
0x1801ff3e3  lea     rdx, [rbp+240h+var_200]
0x1801ff3e7  lea     rcx, [rbp+240h+var_110]
0x1801ff3ee  call    ?GetDosPath@DlpPathCache@RealtimeProtection@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; RealtimeProtection::DlpPathCache::GetDosPath(std::wstring const &)
0x1801ff3f3  nop
0x1801ff3f4  lea     rcx, [rbp+240h+var_200]; void *
0x1801ff3f8  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801ff3fd  cmp     [rbp+240h+var_F0], r14b
0x1801ff404  jnz     short loc_1801FF424
0x1801ff406  lea     rcx, [rbp+240h+var_110]
0x1801ff40d  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1801ff412  nop
0x1801ff413  lea     rcx, [rbp+240h+var_138]; void *
0x1801ff41a  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801ff41f  jmp     loc_1801FF370
0x1801ff424  lea     rcx, [rbp+240h+var_110]
0x1801ff42b  call    ?value@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1801ff430  mov     rdx, rax
0x1801ff433  mov     rcx, rdi
0x1801ff436  call    ??$?4V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@path@filesystem@std@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::filesystem::path::operator=<std::wstring,0>(std::wstring const &)
0x1801ff43b  nop
0x1801ff43c  lea     rcx, [rbp+240h+var_110]
0x1801ff443  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1801ff448  mov     [rbp+240h+var_220], r14
0x1801ff44c  mov     r8, rsi
0x1801ff44f  cmp     qword ptr [rsi+18h], 7
0x1801ff454  jbe     short loc_1801FF459
0x1801ff456  mov     r8, [rsi]; wchar_t *
0x1801ff459  lea     r9, [rbp+240h+var_220]; wchar_t **
0x1801ff45d  mov     rdx, r15; void **
0x1801ff460  call    ?ExpandQuarantinePath@DlpQuarantineEngine@RealtimeProtection@@AEAAJAEBQEAXPEB_WPEAPEA_W@Z; RealtimeProtection::DlpQuarantineEngine::ExpandQuarantinePath(void * const &,wchar_t const *,wchar_t * *)
0x1801ff465  movsxd  r12, eax
0x1801ff468  mov     rdi, [rbp+240h+var_220]
0x1801ff46c  test    eax, eax
0x1801ff46e  jns     loc_1801FF6D1
0x1801ff474  lea     r15, WPP_GLOBAL_Control
0x1801ff47b  lea     r13, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801ff482  mov     rax, cs:WPP_GLOBAL_Control
0x1801ff489  cmp     rax, r15
0x1801ff48c  jz      short loc_1801FF4B4
0x1801ff48e  test    byte ptr [rax+1Ch], 1
0x1801ff492  jz      short loc_1801FF4B4
0x1801ff494  call    HrGetLastFailure
0x1801ff499  mov     edx, 81h
0x1801ff49e  mov     r9d, eax
0x1801ff4a1  mov     r8, r13
0x1801ff4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ff4ab  mov     rcx, [rcx+10h]
0x1801ff4af  call    WPP_SF_d
0x1801ff4b4  mov     [rbp+240h+var_2C0], r14b
0x1801ff4b8  mov     r8, rsi
0x1801ff4bb  lea     rdx, aPath_0; "{\"Path\":\""
0x1801ff4c2  lea     rcx, [rbp+240h+var_1C0]; void *
0x1801ff4c9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_WAEBV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring const &)
0x1801ff4ce  nop
0x1801ff4cf  lea     r8, asc_1802A29E8; "\"}"
0x1801ff4d6  mov     rdx, rax
0x1801ff4d9  lea     rcx, [rbp+240h+var_1E0]
0x1801ff4dd  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1801ff4e2  nop
0x1801ff4e3  lea     rcx, [rbp+240h+var_1C0]; void *
0x1801ff4ea  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801ff4ef  lea     rbx, aQuarantine; "Quarantine"
0x1801ff4f6  mov     rdx, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x1801ff4fd  test    rdx, rdx
0x1801ff500  jz      loc_1801FF6C8
0x1801ff506  lea     rcx, [rbp+240h+var_1A0]
0x1801ff50d  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1801ff512  mov     r9, cs:g_hMpAsimovProvider
0x1801ff519  cmp     dword ptr [r9], 5
0x1801ff51d  jbe     loc_1801FF6BC
0x1801ff523  mov     rdx, 400000000000h
0x1801ff52d  mov     rcx, r9
0x1801ff530  call    _tlgKeywordOn
0x1801ff535  test    al, al
0x1801ff537  jz      loc_1801FF6BC
0x1801ff53d  lea     rax, [rbp+240h+var_1E0]
0x1801ff541  cmp     [rbp+240h+var_1C8], 7
0x1801ff546  cmova   rax, [rbp+240h+var_1E0]
0x1801ff54b  mov     [rbp+240h+var_248], rax
0x1801ff54f  lea     rax, aResolvequarant_0; "ResolveQuarantineItemPaths.PathExpansio"...
0x1801ff556  mov     [rbp+240h+var_290], rax
0x1801ff55a  mov     [rbp+240h+var_258], rbx
0x1801ff55e  lea     rax, aDlpengine_0; "DLPEngine"
0x1801ff565  mov     [rbp+240h+var_250], rax
0x1801ff569  mov     [rbp+240h+var_260], r12
0x1801ff56d  mov     rcx, cs:?g_aAsimov@@3PEAVCMpAsimov@@EA; CMpAsimov * g_aAsimov
0x1801ff574  mov     eax, [rcx+48h]
0x1801ff577  mov     dword ptr [rbp+240h+var_2A4+4], eax
0x1801ff57a  mov     eax, [rcx+44h]
0x1801ff57d  mov     dword ptr [rbp+240h+var_2BC], eax
0x1801ff580  mov     eax, [rcx+40h]
0x1801ff583  mov     dword ptr [rbp+240h+var_2BC+4], eax
0x1801ff586  movzx   eax, byte ptr [rcx+3Ch]
0x1801ff58a  mov     dword ptr [rbp+240h+var_2B4], eax
0x1801ff58d  movzx   eax, byte ptr [rcx+3Bh]
0x1801ff591  mov     dword ptr [rbp+240h+var_2B4+4], eax
0x1801ff594  movzx   eax, byte ptr [rcx+3Ah]
0x1801ff598  mov     dword ptr [rbp+240h+var_2AC], eax
0x1801ff59b  movzx   eax, byte ptr [rcx+39h]
0x1801ff59f  mov     dword ptr [rbp+240h+var_2AC+4], eax
0x1801ff5a2  movzx   eax, byte ptr [rcx+38h]
0x1801ff5a6  mov     dword ptr [rbp+240h+var_2A4], eax
0x1801ff5a9  mov     rax, [rcx+30h]
0x1801ff5ad  mov     [rbp+240h+var_288], rax
0x1801ff5b1  mov     rax, [rcx+28h]
0x1801ff5b5  mov     [rbp+240h+var_280], rax
0x1801ff5b9  mov     rax, [rcx+20h]
0x1801ff5bd  mov     [rbp+240h+var_278], rax
0x1801ff5c1  mov     rax, [rcx+18h]
0x1801ff5c5  mov     [rbp+240h+var_270], rax
0x1801ff5c9  mov     rax, [rcx+10h]
0x1801ff5cd  mov     [rbp+240h+var_240], rax
0x1801ff5d1  mov     rax, [rcx+8]
0x1801ff5d5  mov     [rbp+240h+var_268], rax
0x1801ff5d9  mov     [rbp+240h+var_298], 2000000h
0x1801ff5e1  lea     rax, [rbp+240h+var_248]
0x1801ff5e5  mov     [rsp+380h+var_2C8], rax; __int64
0x1801ff5ed  lea     rax, [rbp+240h+var_290]
0x1801ff5f1  mov     [rsp+380h+var_2D0], rax; __int64
0x1801ff5f9  lea     rax, [rbp+240h+var_258]
0x1801ff5fd  mov     [rsp+380h+var_2D8], rax; __int64
0x1801ff605  lea     rax, [rbp+240h+var_250]
0x1801ff609  mov     [rsp+380h+var_2E0], rax; __int64
0x1801ff611  lea     rax, [rbp+240h+var_260]
0x1801ff615  mov     [rsp+380h+var_2E8], rax; __int64
0x1801ff61d  lea     rax, [rbp+240h+var_2A4+4]
0x1801ff621  mov     [rsp+380h+var_2F0], rax; __int64
0x1801ff629  lea     rax, [rbp+240h+var_2BC]
0x1801ff62d  mov     [rsp+380h+var_2F8], rax; __int64
0x1801ff635  lea     rax, [rbp+240h+var_2BC+4]
0x1801ff639  mov     [rsp+380h+var_300], rax; __int64
0x1801ff641  lea     rax, [rbp+240h+var_2B4]
0x1801ff645  mov     [rsp+380h+var_308], rax; __int64
0x1801ff64a  lea     rax, [rbp+240h+var_2B4+4]
0x1801ff64e  mov     [rsp+380h+var_310], rax; __int64
0x1801ff653  lea     rax, [rbp+240h+var_2AC]
0x1801ff657  mov     [rsp+380h+var_318], rax; __int64
0x1801ff65c  lea     rax, [rbp+240h+var_2AC+4]
0x1801ff660  mov     [rsp+380h+var_320], rax; __int64
0x1801ff665  lea     rax, [rbp+240h+var_2A4]
0x1801ff669  mov     [rsp+380h+var_328], rax; __int64
0x1801ff66e  lea     rax, [rbp+240h+var_288]
0x1801ff672  mov     [rsp+380h+var_330], rax; __int64
0x1801ff677  lea     rax, [rbp+240h+var_280]
0x1801ff67b  mov     [rsp+380h+var_338], rax; __int64
0x1801ff680  lea     rax, [rbp+240h+var_278]
0x1801ff684  mov     [rsp+380h+var_340], rax; __int64
0x1801ff689  lea     rax, [rbp+240h+var_270]
0x1801ff68d  mov     [rsp+380h+var_348], rax; __int64
0x1801ff692  lea     rax, [rbp+240h+var_240]
0x1801ff696  mov     [rsp+380h+var_350], rax; __int64
0x1801ff69b  lea     rax, [rbp+240h+var_268]
0x1801ff69f  mov     [rsp+380h+var_358], rax; __int64
0x1801ff6a4  lea     rax, [rbp+240h+var_298]
0x1801ff6a8  mov     [rsp+380h+var_360], rax; __int64
0x1801ff6ad  lea     rdx, dword_1802C6E24; int
0x1801ff6b4  mov     rcx, r9; int
0x1801ff6b7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U1@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@44444AEBU?$_tlgWrapperByVal@$03@@555555534444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x1801ff6bc  lea     rcx, [rbp+240h+var_1A0]
0x1801ff6c3  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1801ff6c8  lea     rcx, [rbp+240h+var_1E0]
0x1801ff6cc  jmp     loc_1801FFCB5
0x1801ff6d1  lea     rdx, [rbp+240h+var_220]
0x1801ff6d5  lea     rcx, [rbp+240h+var_178]
0x1801ff6dc  call    ??$?0PEA_W$0A@@path@filesystem@std@@QEAA@AEBQEA_WW4format@012@@Z; std::filesystem::path::path(wchar_t * const &,std::filesystem::path::format)
0x1801ff6e1  nop
0x1801ff6e2  lea     rcx, [rbp+240h+var_178]; this
0x1801ff6e9  call    ?is_absolute@path@filesystem@std@@QEBA_NXZ; std::filesystem::path::is_absolute(void)
0x1801ff6ee  lea     r12, aQuarantine; "Quarantine"
0x1801ff6f5  test    al, al
0x1801ff6f7  jz      loc_1801FFA68
0x1801ff6fd  mov     rdx, rdi; Src
0x1801ff700  mov     rcx, rsi; void *
0x1801ff703  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1801ff708  lea     rdx, SubBlock; "\\"
0x1801ff70f  mov     rcx, rsi; Src
0x1801ff712  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1801ff717  lea     rdx, [rbx+238h]
0x1801ff71e  mov     r8, [rdx+10h]
0x1801ff722  cmp     qword ptr [rdx+18h], 7
0x1801ff727  jbe     short loc_1801FF72C
0x1801ff729  mov     rdx, [rdx]
0x1801ff72c  mov     rcx, rsi; Src
0x1801ff72f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1801ff734  mov     rcx, rsi
0x1801ff737  cmp     qword ptr [rsi+18h], 7
0x1801ff73c  jbe     short loc_1801FF741
0x1801ff73e  mov     rcx, [rsi]; lpFileName
0x1801ff741  call    cs:__imp_GetFileAttributesW
0x1801ff747  lea     r15, WPP_GLOBAL_Control
0x1801ff74e  lea     r13, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801ff755  cmp     eax, 0FFFFFFFFh
0x1801ff758  jz      short loc_1801FF768
0x1801ff75a  and     eax, 410h
0x1801ff75f  cmp     eax, 10h
0x1801ff762  jz      loc_1801FF8D1
0x1801ff768  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ff76f  cmp     rcx, r15
0x1801ff772  jz      short loc_1801FF78B
0x1801ff774  test    byte ptr [rcx+1Ch], 4
0x1801ff778  jz      short loc_1801FF78B
0x1801ff77a  mov     edx, 7Dh ; '}'
0x1801ff77f  mov     r8, r13
0x1801ff782  mov     rcx, [rcx+10h]
0x1801ff786  call    WPP_SF_
0x1801ff78b  mov     [rbp+240h+var_1A0], r14
0x1801ff792  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1801ff799  mov     [rbp+240h+var_198], rax
0x1801ff7a0  mov     rax, rsi
0x1801ff7a3  cmp     qword ptr [rsi+18h], 7
0x1801ff7a8  jbe     short loc_1801FF7AD
0x1801ff7aa  mov     rax, [rsi]
0x1801ff7ad  mov     [rbp+240h+var_298], rax
0x1801ff7b1  mov     r8b, r14b
0x1801ff7b4  lea     rdx, [rbp+240h+var_298]
0x1801ff7b8  lea     rcx, [rbp+240h+var_200]
0x1801ff7bc  call    ??$_Convert_Source_to_wide@PEB_WU_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBQEB_WU_Normal_conversion@01@@Z; std::filesystem::_Convert_Source_to_wide<wchar_t const *,std::filesystem::_Normal_conversion>(wchar_t const * const &,std::filesystem::_Normal_conversion)
0x1801ff7c1  nop
0x1801ff7c2  lea     rdx, [rbp+240h+var_1A0]; struct std::filesystem::path *
0x1801ff7c9  lea     rcx, [rbp+240h+var_200]; this
0x1801ff7cd  call    ?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)
0x1801ff7d2  mov     bl, al
0x1801ff7d4  lea     rcx, [rbp+240h+var_200]; void *
0x1801ff7d8  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
  ... truncated ...
```

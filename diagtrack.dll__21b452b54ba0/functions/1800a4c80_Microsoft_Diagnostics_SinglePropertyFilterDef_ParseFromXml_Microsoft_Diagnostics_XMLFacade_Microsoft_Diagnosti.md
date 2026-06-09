# Microsoft::Diagnostics::SinglePropertyFilterDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1800a4c80`
- end: `0x1800a571f`
- name: `?ParseFromXml@SinglePropertyFilterDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `2719`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::SinglePropertyFilterDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002cae0`
- `0x18002df00`
- `0x180040558`
- `0x1800566e0`
- `0x180064e8c`
- `0x1800653d0`
- `0x18007878c`
- `0x18008b254`
- `0x18009c8c0`
- `0x18009dec0`
- `0x1800a3760`
- `0x1800a4504`
- `0x1800a4c80`
- `0x1800a6438`
- `0x1800a658c`
- `0x1800afab0`
- `0x180120b6c`
- `0x1801304ac`
- `0x1801b7bd0`
- `0x1801bbc78`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4d88`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4dd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4e1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4e64`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4f54`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4f99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4d88`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4dd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4e1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4e64`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4f54`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a4f99`

## string_xrefs

- `0x1800a5136`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a51c1`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a524a`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a5291`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a52dd`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a5320`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a5351`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a5390`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a53cf`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a540e`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a543f`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a5470`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a551b`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a5592`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a55df`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a563a`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a567d`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a56ae`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a56d6`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a56fe`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1800a51f4`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::SinglePropertyFilterDef::ParseFromXml(
        char **this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  int v6; // ecx
  __int64 v7; // r8
  __int64 v8; // rax
  const void *v9; // r10
  unsigned int Element; // eax
  unsigned int v11; // edi
  _QWORD *v12; // rdx
  int v13; // edi
  __int64 v14; // r8
  _QWORD *v15; // rdx
  int v16; // edi
  __int64 v17; // r8
  _QWORD *v18; // rdx
  int v19; // edi
  __int64 v20; // r8
  _QWORD *v21; // rdx
  int v22; // edi
  __int64 v23; // r8
  int v24; // eax
  unsigned int v25; // edi
  __int128 *v26; // rax
  int v27; // eax
  unsigned int v28; // edi
  int v29; // eax
  unsigned int v30; // edi
  __int128 *v31; // rcx
  _QWORD *v32; // rdx
  int v33; // edi
  __int64 v34; // r8
  _QWORD *v35; // rdx
  int v36; // edi
  __int64 v37; // r8
  int v38; // eax
  unsigned int v39; // edi
  int v40; // eax
  unsigned int v41; // edi
  int v42; // eax
  unsigned int v43; // edi
  int v44; // eax
  unsigned int v45; // edi
  const char *v46; // r9
  __int64 result; // rax
  int v48; // ecx
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int InnerText; // eax
  unsigned int v54; // edi
  int v55; // eax
  unsigned int v56; // edi
  int v57; // eax
  unsigned int v58; // edi
  int v59; // eax
  unsigned int v60; // edi
  int v61; // eax
  unsigned int v62; // edi
  int v63; // eax
  unsigned int v64; // edi
  int v65; // eax
  unsigned int v66; // edi
  int v67; // eax
  unsigned int v68; // edi
  int v69; // eax
  unsigned int v70; // edi
  int v71; // [rsp+20h] [rbp-128h]
  int v72; // [rsp+24h] [rbp-124h]
  int v73; // [rsp+28h] [rbp-120h]
  int v74; // [rsp+2Ch] [rbp-11Ch]
  int v75; // [rsp+30h] [rbp-118h]
  __int64 v77; // [rsp+40h] [rbp-108h] BYREF
  _QWORD v78[2]; // [rsp+50h] [rbp-F8h] BYREF
  __int128 v79; // [rsp+60h] [rbp-E8h] BYREF
  _BYTE v80[16]; // [rsp+70h] [rbp-D8h] BYREF
  _BYTE v81[16]; // [rsp+80h] [rbp-C8h] BYREF
  _BYTE v82[16]; // [rsp+90h] [rbp-B8h] BYREF
  _QWORD v83[2]; // [rsp+A0h] [rbp-A8h] BYREF
  unsigned __int64 v84; // [rsp+B0h] [rbp-98h]
  unsigned __int64 v85; // [rsp+B8h] [rbp-90h]
  __int128 v86; // [rsp+C0h] [rbp-88h] BYREF
  __int64 v87; // [rsp+D0h] [rbp-78h]
  unsigned __int64 v88; // [rsp+D8h] [rbp-70h]
  _BYTE v89[32]; // [rsp+E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    v6 = *((unsigned __int16 *)this + 8);
    if ( v6 )
    {
      v48 = v6 - 1;
      if ( v48 )
      {
        v49 = v48 - 1;
        if ( v49 )
        {
          v50 = v49 - 1;
          if ( v50 )
          {
            v51 = v50 - 1;
            if ( v51 )
            {
              v52 = v51 - 1;
              if ( v52 )
              {
                if ( v52 != 1 )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0x3B5,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                    (const char *)a3);
                v7 = 11;
              }
              else
              {
                v7 = 10;
              }
            }
            else
            {
              v7 = 9;
            }
          }
          else
          {
            v7 = 8;
          }
        }
        else
        {
          v7 = 7;
        }
      }
      else
      {
        v7 = 6;
      }
    }
    else
    {
      v7 = 5;
    }
    Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v77, (char *)a3 + 112, v7);
    v8 = std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(v77);
    std::wstring::_Assign<wchar_t>((char **)(v8 + 8), v9, this[5]);
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v71 = 0;
    while ( 1 )
    {
      Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v11 = Element;
      if ( Element )
        break;
      std::wstring::wstring(v83);
      Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v83);
      v12 = v83;
      if ( v85 > 7 )
        v12 = (_QWORD *)v83[0];
      v13 = v84;
      v14 = v84;
      if ( v84 >= 0xB )
        v14 = 11;
      if ( !(unsigned int)_o__wcsnicmp(L"triggername", v12, v14) && v13 == 11 )
      {
        InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, this + 10);
        v54 = InnerText;
        if ( InnerText < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D3,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
            (const char *)(unsigned int)InnerText,
            v71);
          std::wstring::_Tidy_deallocate(v83);
          return v54;
        }
        v55 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v56 = v55;
        if ( v55 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D4,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
            (const char *)(unsigned int)v55,
            v71);
          std::wstring::_Tidy_deallocate(v83);
          return v56;
        }
        ++v72;
      }
      else
      {
        v15 = v83;
        if ( v85 > 7 )
          v15 = (_QWORD *)v83[0];
        v16 = v84;
        v17 = v84;
        if ( v84 >= 0x10 )
          v17 = 16;
        if ( !(unsigned int)_o__wcsnicmp(L"propertyselector", v15, v17) && v16 == 16 )
        {
          v57 = Microsoft::Diagnostics::SinglePropertyFilterDef::ParsePropertySelector(
                  (Microsoft::Diagnostics::SinglePropertyFilterDef *)this,
                  a2,
                  a3);
          v58 = v57;
          if ( v57 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D9,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
              (const char *)(unsigned int)v57,
              v71);
            std::wstring::_Tidy_deallocate(v83);
            return v58;
          }
          ++v73;
        }
        else
        {
          v18 = v83;
          if ( v85 > 7 )
            v18 = (_QWORD *)v83[0];
          v19 = v84;
          v20 = v84;
          if ( v84 >= 7 )
            v20 = 7;
          if ( !(unsigned int)_o__wcsnicmp(L"bitmask", v18, v20) && v19 == 7 )
          {
            v59 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, this + 14);
            v60 = v59;
            if ( v59 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1DE,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)v59,
                v71);
              std::wstring::_Tidy_deallocate(v83);
              return v60;
            }
            v61 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v62 = v61;
            if ( v61 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1DF,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)v61,
                v71);
              std::wstring::_Tidy_deallocate(v83);
              return v62;
            }
          }
          else
          {
            v21 = v83;
            if ( v85 > 7 )
              v21 = (_QWORD *)v83[0];
            v22 = v84;
            v23 = v84;
            if ( v84 >= 0xD )
              v23 = 13;
            if ( !(unsigned int)_o__wcsnicmp(L"mathoperation", v21, v23) && v22 == 13 )
            {
              std::wstring::wstring(&v86);
              v24 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, &v86);
              v25 = v24;
              if ( v24 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1E4,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v24,
                  v71);
                std::wstring::_Tidy_deallocate(&v86);
                std::wstring::_Tidy_deallocate(v83);
                return v25;
              }
              v26 = &v86;
              if ( v88 > 7 )
                v26 = (__int128 *)v86;
              v78[0] = v26;
              v78[1] = v87;
              v27 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToMathOperation(v78, (char *)this + 60);
              v28 = v27;
              if ( v27 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1E5,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v27,
                  v71);
                std::wstring::_Tidy_deallocate(&v86);
                std::wstring::_Tidy_deallocate(v83);
                return v28;
              }
              v29 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
              v30 = v29;
              if ( v29 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1E6,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v29,
                  v71);
                std::wstring::_Tidy_deallocate(&v86);
                std::wstring::_Tidy_deallocate(v83);
                return v30;
              }
              ++v71;
              v31 = &v86;
              goto LABEL_36;
            }
            v32 = v83;
            if ( v85 > 7 )
              v32 = (_QWORD *)v83[0];
            v33 = v84;
            v34 = v84;
            if ( v84 >= 8 )
              v34 = 8;
            if ( !(unsigned int)_o__wcsnicmp(L"constant", v32, v34) && v33 == 8 )
            {
              v42 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, this + 18);
              v43 = v42;
              if ( v42 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1EC,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v42,
                  v71);
                std::wstring::_Tidy_deallocate(v83);
                return v43;
              }
              v44 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
              v45 = v44;
              if ( v44 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1ED,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v44,
                  v71);
                std::wstring::_Tidy_deallocate(v83);
                return v45;
              }
              ++v71;
            }
            else
            {
              v35 = v83;
              if ( v85 > 7 )
                v35 = (_QWORD *)v83[0];
              v36 = v84;
              v37 = v84;
              if ( v84 >= 5 )
                v37 = 5;
              if ( !(unsigned int)_o__wcsnicmp(L"value", v35, v37) && v36 == 5 )
              {
                std::wstring::wstring(v89);
                v38 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v89);
                v39 = v38;
                if ( v38 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1F4,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                    (const char *)(unsigned int)v38,
                    v71);
                  std::wstring::_Tidy_deallocate(v89);
                  std::wstring::_Tidy_deallocate(v83);
                  return v39;
                }
                std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                  this + 25,
                  v80,
                  v89);
                v40 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
                v41 = v40;
                if ( v40 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1F8,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                    (const char *)(unsigned int)v40,
                    v71);
                  std::wstring::_Tidy_deallocate(v89);
                  std::wstring::_Tidy_deallocate(v83);
                  return v41;
                }
                ++v74;
LABEL_53:
                v31 = (__int128 *)v89;
LABEL_36:
                std::wstring::_Tidy_deallocate(v31);
                goto LABEL_37;
              }
              v79 = *(_OWORD *)std::wstring::operator std::wstring_view(v83, v81);
              v86 = *(_OWORD *)&off_180386D10;
              if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v86, &v79) )
              {
                std::wstring::wstring(v89);
                v63 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v89);
                v64 = v63;
                if ( v63 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1FF,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                    (const char *)(unsigned int)v63,
                    v71);
                  std::wstring::_Tidy_deallocate(v89);
                  std::wstring::_Tidy_deallocate(v83);
                  return v64;
                }
                v86 = *(_OWORD *)std::wstring::operator std::wstring_view(v89, v82);
                v65 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToOperation(&v86, (char *)this + 68);
                v66 = v65;
                if ( v65 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x200,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                    (const char *)(unsigned int)v65,
                    v71);
                  std::wstring::_Tidy_deallocate(v89);
                  std::wstring::_Tidy_deallocate(v83);
                  return v66;
                }
                v67 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
                v68 = v67;
                if ( v67 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x201,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                    (const char *)(unsigned int)v67,
                    v71);
                  std::wstring::_Tidy_deallocate(v89);
                  std::wstring::_Tidy_deallocate(v83);
                  return v68;
                }
                ++v75;
                goto LABEL_53;
              }
              if ( *((_BYTE *)a3 + 152) )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x209,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)0x87C52407LL,
                  v71);
                std::wstring::_Tidy_deallocate(v83);
                return 2277843975LL;
              }
              v69 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
              v70 = v69;
              if ( v69 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x20C,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v69,
                  v71);
                std::wstring::_Tidy_deallocate(v83);
                return v70;
              }
            }
          }
        }
      }
LABEL_37:
      std::wstring::_Tidy_deallocate(v83);
    }
    if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
    {
      Microsoft::Diagnostics::SinglePropertyFilterDef::EstablishParseDynamicMembers((Microsoft::Diagnostics::SinglePropertyFilterDef *)this);
      if ( v73 == 1 && v74 && v75 == 1 && v72 == 1 )
      {
        if ( (v71 & 0xFFFFFFFD) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x21B,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
            (const char *)0x87C52402LL,
            v71);
          result = 2277843970LL;
        }
        else
        {
          (*((void (__fastcall **)(char **, _QWORD))*this + 2))(this, 0);
          std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v77);
          result = 0;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x216,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
          (const char *)0x87C52402LL,
          v71);
        result = 2277843970LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20F,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
        (const char *)Element,
        v71);
      result = v11;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x222,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                           v46);
  }
  return result;
}

```

## disassembly

```asm
0x1800a4c80  push    rbx
0x1800a4c82  push    rsi
0x1800a4c83  push    rdi
0x1800a4c84  push    r12
0x1800a4c86  push    r13
0x1800a4c88  push    r14
0x1800a4c8a  push    r15
0x1800a4c8c  sub     rsp, 110h
0x1800a4c93  mov     rax, cs:__security_cookie
0x1800a4c9a  xor     rax, rsp
0x1800a4c9d  mov     [rsp+148h+var_48], rax
0x1800a4ca5  mov     r9, r8; char *
0x1800a4ca8  mov     [rsp+148h+var_110], r8
0x1800a4cad  mov     rsi, rdx
0x1800a4cb0  mov     r15, rcx
0x1800a4cb3  movzx   ecx, word ptr [rcx+10h]
0x1800a4cb7  test    ecx, ecx
0x1800a4cb9  jnz     loc_1800A50E6
0x1800a4cbf  lea     r13d, [rcx+5]
0x1800a4cc3  movzx   r8d, r13w
0x1800a4cc7  mov     r12d, 0Bh
0x1800a4ccd  mov     r14d, 8
0x1800a4cd3  mov     ebx, 7
0x1800a4cd8  lea     rdx, [r9+70h]
0x1800a4cdc  lea     rcx, [rsp+148h+var_108]
0x1800a4ce1  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1800a4ce6  cmp     [r15+30h], rbx
0x1800a4cea  jbe     loc_1800A50DD
0x1800a4cf0  mov     r10, [r15+18h]
0x1800a4cf4  mov     rcx, [rsp+148h+var_108]
0x1800a4cf9  call    ?top@?$stack@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$deque@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@@2@@2@@std@@QEAAAEAV?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@2@XZ; std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(void)
0x1800a4cfe  lea     rcx, [r14+rax]
0x1800a4d02  mov     r8, [r15+28h]
0x1800a4d06  mov     rdx, r10
0x1800a4d09  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800a4d0e  xor     eax, eax
0x1800a4d10  mov     [rsp+148h+var_124], eax
0x1800a4d14  xor     ecx, ecx
0x1800a4d16  mov     [rsp+148h+var_120], ecx
0x1800a4d1a  mov     [rsp+148h+var_11C], eax
0x1800a4d1e  mov     [rsp+148h+var_118], eax
0x1800a4d22  mov     [rsp+148h+var_128], eax; int
0x1800a4d26  mov     rcx, rsi; this
0x1800a4d29  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1800a4d2e  mov     edi, eax
0x1800a4d30  test    eax, eax
0x1800a4d32  jnz     loc_1800A504C
0x1800a4d38  lea     rcx, [rsp+148h+var_A8]; void *
0x1800a4d40  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a4d45  nop
0x1800a4d46  lea     rdx, [rsp+148h+var_A8]
0x1800a4d4e  mov     rcx, rsi
0x1800a4d51  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1800a4d56  lea     rdx, [rsp+148h+var_A8]
0x1800a4d5e  cmp     [rsp+148h+var_90], rbx
0x1800a4d66  cmova   rdx, [rsp+148h+var_A8]
0x1800a4d6f  mov     rdi, [rsp+148h+var_98]
0x1800a4d77  mov     r8, rdi
0x1800a4d7a  cmp     rdi, r12
0x1800a4d7d  cmovnb  r8, r12
0x1800a4d81  mov     rcx, cs:off_18036CBF8; "triggername"
0x1800a4d88  call    cs:__imp__o__wcsnicmp
0x1800a4d8e  test    eax, eax
0x1800a4d90  jnz     short loc_1800A4D9B
0x1800a4d92  cmp     r12d, edi
0x1800a4d95  jz      loc_1800A5189
0x1800a4d9b  lea     rdx, [rsp+148h+var_A8]
0x1800a4da3  cmp     [rsp+148h+var_90], rbx
0x1800a4dab  cmova   rdx, [rsp+148h+var_A8]
0x1800a4db4  mov     rdi, [rsp+148h+var_98]
0x1800a4dbc  mov     r8, rdi
0x1800a4dbf  mov     eax, 10h
0x1800a4dc4  cmp     rdi, rax
0x1800a4dc7  cmovnb  r8, rax
0x1800a4dcb  mov     rcx, cs:off_18036CC48; "propertyselector"
0x1800a4dd2  call    cs:__imp__o__wcsnicmp
0x1800a4dd8  test    eax, eax
0x1800a4dda  jnz     short loc_1800A4DE9
0x1800a4ddc  mov     eax, 10h
0x1800a4de1  cmp     eax, edi
0x1800a4de3  jz      loc_1800A5270
0x1800a4de9  lea     rdx, [rsp+148h+var_A8]
0x1800a4df1  cmp     [rsp+148h+var_90], rbx
0x1800a4df9  cmova   rdx, [rsp+148h+var_A8]
0x1800a4e02  mov     rdi, [rsp+148h+var_98]
0x1800a4e0a  mov     r8, rdi
0x1800a4e0d  cmp     rdi, rbx
0x1800a4e10  cmovnb  r8, rbx
0x1800a4e14  mov     rcx, cs:off_18036CC38; "bitmask"
0x1800a4e1b  call    cs:__imp__o__wcsnicmp
0x1800a4e21  test    eax, eax
0x1800a4e23  jnz     short loc_1800A4E2D
0x1800a4e25  cmp     ebx, edi
0x1800a4e27  jz      loc_1800A52C0
0x1800a4e2d  lea     rdx, [rsp+148h+var_A8]
0x1800a4e35  cmp     [rsp+148h+var_90], rbx
0x1800a4e3d  cmova   rdx, [rsp+148h+var_A8]
0x1800a4e46  mov     rdi, [rsp+148h+var_98]
0x1800a4e4e  mov     r8, rdi
0x1800a4e51  mov     eax, 0Dh
0x1800a4e56  cmp     rdi, rax
0x1800a4e59  cmovnb  r8, rax
0x1800a4e5d  mov     rcx, cs:off_18036CC58; "mathoperation"
0x1800a4e64  call    cs:__imp__o__wcsnicmp
0x1800a4e6a  test    eax, eax
0x1800a4e6c  jnz     loc_1800A4F22
0x1800a4e72  mov     eax, 0Dh
0x1800a4e77  sub     eax, edi
0x1800a4e79  test    eax, eax
0x1800a4e7b  jnz     loc_1800A4F22
0x1800a4e81  lea     rcx, [rsp+148h+var_88]; void *
0x1800a4e89  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a4e8e  nop
0x1800a4e8f  lea     rdx, [rsp+148h+var_88]
0x1800a4e97  mov     rcx, rsi
0x1800a4e9a  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a4e9f  mov     edi, eax
0x1800a4ea1  test    eax, eax
0x1800a4ea3  js      loc_1800A5346
0x1800a4ea9  lea     rax, [rsp+148h+var_88]
0x1800a4eb1  cmp     [rsp+148h+var_70], rbx
0x1800a4eb9  cmova   rax, qword ptr [rsp+148h+var_88]
0x1800a4ec2  mov     [rsp+148h+var_F8], rax
0x1800a4ec7  mov     rax, [rsp+148h+var_78]
0x1800a4ecf  mov     [rsp+148h+var_F0], rax
0x1800a4ed4  lea     rdx, [r15+3Ch]
0x1800a4ed8  lea     rcx, [rsp+148h+var_F8]
0x1800a4edd  call    ?ConvertStringToMathOperation@Xml@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU?$optional@VMathOperator@Filters@Diagnostics@Microsoft@@@better_enums@@@Z; Microsoft::Diagnostics::Utils::Xml::ConvertStringToMathOperation(std::wstring_view,better_enums::optional<Microsoft::Diagnostics::Filters::MathOperator> &)
0x1800a4ee2  mov     edi, eax
0x1800a4ee4  test    eax, eax
0x1800a4ee6  js      loc_1800A5385
0x1800a4eec  mov     rcx, rsi; this
0x1800a4eef  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a4ef4  mov     edi, eax
0x1800a4ef6  test    eax, eax
0x1800a4ef8  js      loc_1800A53C4
0x1800a4efe  inc     [rsp+148h+var_128]
0x1800a4f02  lea     rcx, [rsp+148h+var_88]
0x1800a4f0a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a4f0f  nop
0x1800a4f10  lea     rcx, [rsp+148h+var_A8]
0x1800a4f18  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a4f1d  jmp     loc_1800A4D26
0x1800a4f22  lea     rdx, [rsp+148h+var_A8]
0x1800a4f2a  cmp     [rsp+148h+var_90], rbx
0x1800a4f32  cmova   rdx, [rsp+148h+var_A8]
0x1800a4f3b  mov     rdi, [rsp+148h+var_98]
0x1800a4f43  mov     r8, rdi
0x1800a4f46  cmp     rdi, r14
0x1800a4f49  cmovnb  r8, r14
0x1800a4f4d  mov     rcx, cs:off_18036CC88; "constant"
0x1800a4f54  call    cs:__imp__o__wcsnicmp
0x1800a4f5a  test    eax, eax
0x1800a4f5c  jnz     short loc_1800A4F67
0x1800a4f5e  cmp     r14d, edi
0x1800a4f61  jz      loc_1800A5018
0x1800a4f67  lea     rdx, [rsp+148h+var_A8]
0x1800a4f6f  cmp     [rsp+148h+var_90], rbx
0x1800a4f77  cmova   rdx, [rsp+148h+var_A8]
0x1800a4f80  mov     rdi, [rsp+148h+var_98]
0x1800a4f88  mov     r8, rdi
0x1800a4f8b  cmp     rdi, r13
0x1800a4f8e  cmovnb  r8, r13
0x1800a4f92  mov     rcx, cs:off_18036CD18; "value"
0x1800a4f99  call    cs:__imp__o__wcsnicmp
0x1800a4f9f  test    eax, eax
0x1800a4fa1  jnz     loc_1800A54A4
0x1800a4fa7  mov     eax, r13d
0x1800a4faa  sub     eax, edi
0x1800a4fac  test    eax, eax
0x1800a4fae  jnz     loc_1800A54A4
0x1800a4fb4  lea     rcx, [rsp+148h+var_68]; void *
0x1800a4fbc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a4fc1  nop
0x1800a4fc2  lea     rdx, [rsp+148h+var_68]
0x1800a4fca  mov     rcx, rsi
0x1800a4fcd  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a4fd2  mov     edi, eax
0x1800a4fd4  test    eax, eax
0x1800a4fd6  js      loc_1800A512B
0x1800a4fdc  lea     rcx, [r15+0C8h]
0x1800a4fe3  lea     r8, [rsp+148h+var_68]
0x1800a4feb  lea     rdx, [rsp+148h+var_D8]
0x1800a4ff0  call    ??$_Emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x1800a4ff5  mov     rcx, rsi; this
0x1800a4ff8  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a4ffd  mov     edi, eax
0x1800a4fff  test    eax, eax
0x1800a5001  js      loc_1800A5465
0x1800a5007  inc     [rsp+148h+var_11C]
0x1800a500b  lea     rcx, [rsp+148h+var_68]
0x1800a5013  jmp     loc_1800A4F0A
0x1800a5018  lea     rdx, [r15+90h]
0x1800a501f  mov     rcx, rsi
0x1800a5022  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a5027  mov     edi, eax
0x1800a5029  test    eax, eax
0x1800a502b  js      loc_1800A5403
0x1800a5031  mov     rcx, rsi; this
0x1800a5034  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a5039  mov     edi, eax
0x1800a503b  test    eax, eax
0x1800a503d  js      loc_1800A5434
0x1800a5043  inc     [rsp+148h+var_128]
0x1800a5047  jmp     loc_1800A4F10
0x1800a504c  mov     ecx, 80000000h
0x1800a5051  add     eax, ecx
0x1800a5053  test    ecx, eax
0x1800a5055  jz      loc_1800A511A
0x1800a505b  mov     rcx, r15; this
0x1800a505e  call    ?EstablishParseDynamicMembers@SinglePropertyFilterDef@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::SinglePropertyFilterDef::EstablishParseDynamicMembers(void)
0x1800a5063  cmp     [rsp+148h+var_120], 1
0x1800a5068  jnz     loc_1800A56EE
0x1800a506e  cmp     [rsp+148h+var_11C], 0
0x1800a5073  jz      loc_1800A56EE
0x1800a5079  cmp     [rsp+148h+var_118], 1
0x1800a507e  jnz     loc_1800A56EE
0x1800a5084  cmp     [rsp+148h+var_124], 1
0x1800a5089  jnz     loc_1800A56EE
0x1800a508f  test    [rsp+148h+var_128], 0FFFFFFFDh
0x1800a5097  jnz     loc_1800A56C6
0x1800a509d  mov     rax, [r15]
0x1800a50a0  xor     edx, edx
0x1800a50a2  mov     rcx, r15
0x1800a50a5  mov     rax, [rax+10h]
0x1800a50a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a50ae  mov     rcx, [rsp+148h+var_108]
0x1800a50b3  call    ?pop_back@?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAXXZ; std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(void)
0x1800a50b8  xor     eax, eax
0x1800a50ba  mov     rcx, [rsp+148h+var_48]
0x1800a50c2  xor     rcx, rsp; StackCookie
0x1800a50c5  call    __security_check_cookie
0x1800a50ca  add     rsp, 110h
0x1800a50d1  pop     r15
0x1800a50d3  pop     r14
0x1800a50d5  pop     r13
0x1800a50d7  pop     r12
0x1800a50d9  pop     rdi
0x1800a50da  pop     rsi
0x1800a50db  pop     rbx
0x1800a50dc  retn
0x1800a50dd  lea     r10, [r15+18h]
0x1800a50e1  jmp     loc_1800A4CF4
0x1800a50e6  sub     ecx, 1
0x1800a50e9  jz      loc_1800A5234
0x1800a50ef  sub     ecx, 1
0x1800a50f2  jz      loc_1800A521A
0x1800a50f8  sub     ecx, 1
0x1800a50fb  jz      short loc_1800A516A
0x1800a50fd  sub     ecx, 1
0x1800a5100  jz      short loc_1800A5181
0x1800a5102  sub     ecx, 1
0x1800a5105  jnz     loc_1800A51E7
0x1800a510b  lea     r8d, [rcx+0Ah]
0x1800a510f  mov     r13d, 5
0x1800a5115  jmp     loc_1800A4CC7
0x1800a511a  cmp     edi, 80070272h
0x1800a5120  jz      loc_1800A505B
0x1800a5126  jmp     loc_1800A56A3
0x1800a512b  mov     rcx, [rsp+148h]; this
0x1800a5133  mov     r9d, edi; char *
0x1800a5136  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x1800a513d  mov     edx, 1F4h; void *
0x1800a5142  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5147  nop
0x1800a5148  lea     rcx, [rsp+148h+var_68]
0x1800a5150  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5155  nop
0x1800a5156  lea     rcx, [rsp+148h+var_A8]
0x1800a515e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5163  mov     eax, edi
0x1800a5165  jmp     loc_1800A50BA
0x1800a516a  mov     r14d, 8
0x1800a5170  movzx   r8d, r14w
0x1800a5174  lea     r12d, [r14+3]
0x1800a5178  lea     r13d, [r14-3]
0x1800a517c  jmp     loc_1800A4CD3
0x1800a5181  mov     r8d, 9
0x1800a5187  jmp     short loc_1800A510F
0x1800a5189  lea     rdx, [r15+50h]
0x1800a518d  mov     rcx, rsi
0x1800a5190  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a5195  mov     edi, eax
0x1800a5197  test    eax, eax
0x1800a5199  js      short loc_1800A51B6
0x1800a519b  mov     rcx, rsi; this
0x1800a519e  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a51a3  mov     edi, eax
0x1800a51a5  test    eax, eax
0x1800a51a7  js      loc_1800A523F
0x1800a51ad  inc     [rsp+148h+var_124]
0x1800a51b1  jmp     loc_1800A4F10
0x1800a51b6  mov     rcx, [rsp+148h]; this
0x1800a51be  mov     r9d, edi; char *
0x1800a51c1  lea     r8, aOnecoreBaseTel_252; "onecore\\base\\telemetry\\utc\\service"...
0x1800a51c8  mov     edx, 1D3h; void *
0x1800a51cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a51d2  nop
0x1800a51d3  lea     rcx, [rsp+148h+var_A8]
0x1800a51db  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```

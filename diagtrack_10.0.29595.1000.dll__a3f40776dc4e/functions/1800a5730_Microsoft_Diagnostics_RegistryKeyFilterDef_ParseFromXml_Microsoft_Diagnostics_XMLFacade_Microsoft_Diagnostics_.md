# Microsoft::Diagnostics::RegistryKeyFilterDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1800a5730`
- end: `0x1800a6431`
- name: `?ParseFromXml@RegistryKeyFilterDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `3329`
- prototype: `int(Microsoft::Diagnostics::RegistryKeyFilterDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002b318`
- `0x18002cae0`
- `0x18002df00`
- `0x180040558`
- `0x1800566e0`
- `0x180064e8c`
- `0x1800653d0`
- `0x18008b254`
- `0x18009dec0`
- `0x1800a0558`
- `0x1800a3760`
- `0x1800a3f5c`
- `0x1800a42e0`
- `0x1800a5730`
- `0x1800a6438`
- `0x1800a658c`
- `0x180120b6c`
- `0x1801b7bd0`
- `0x1801bbc78`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a58af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a58fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a5940`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a5987`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a59c7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a5bf1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a58af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a58fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a5940`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a5987`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a59c7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a5bf1`

## string_xrefs

- `0x1800a5c85`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a5e52`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a5ecd`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a5f68`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a5fb5`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a6002`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a6041`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a6080`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a60bf`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a60fe`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a614b`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a61a8`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a61f5`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a6242`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a628f`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a62dc`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a633c`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a638d`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a63cc`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a6402`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1800a5f1c`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::RegistryKeyFilterDef::ParseFromXml(
        Microsoft::Diagnostics::RegistryKeyFilterDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  int v6; // ecx
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // r10
  char v14; // al
  unsigned int Element; // eax
  unsigned int v16; // edi
  _QWORD *v17; // rdx
  int v18; // edi
  __int64 v19; // r8
  _QWORD *v20; // rdx
  int v21; // edi
  __int64 v22; // r8
  _QWORD *v23; // rdx
  int v24; // edi
  __int64 v25; // r8
  _QWORD *v26; // rdx
  int v27; // edi
  __int64 v28; // r8
  _QWORD *v29; // rdx
  int v30; // edi
  __int64 v31; // r8
  int v32; // eax
  unsigned int v33; // edi
  int v34; // eax
  unsigned int v35; // edi
  int v36; // eax
  unsigned int v37; // edi
  _QWORD *v38; // rax
  _DWORD *v39; // r12
  int v40; // eax
  unsigned int v41; // edi
  int v42; // eax
  unsigned int v43; // edi
  int InnerText; // eax
  unsigned int v45; // edi
  _QWORD *v46; // rax
  int HiveFromString; // eax
  unsigned int v48; // edi
  int v49; // eax
  unsigned int v50; // edi
  int v51; // eax
  unsigned int v52; // edi
  int v53; // eax
  unsigned int v54; // edi
  _QWORD *v55; // rdx
  int v56; // edi
  __int64 v57; // r8
  int v58; // eax
  unsigned int v59; // edi
  _QWORD *v60; // rax
  int v61; // eax
  unsigned int v62; // edi
  const char *v63; // r9
  __int64 result; // rax
  _WORD *v65; // rax
  int v66; // ecx
  int v67; // ecx
  int v68; // ecx
  int v69; // ecx
  int v70; // ecx
  int v71; // eax
  unsigned int v72; // edi
  int v73; // eax
  unsigned int v74; // edi
  int v75; // eax
  unsigned int v76; // edi
  int v77; // eax
  unsigned int v78; // edi
  int v79; // [rsp+20h] [rbp-118h]
  int v80; // [rsp+24h] [rbp-114h]
  int v81; // [rsp+28h] [rbp-110h]
  int v82; // [rsp+2Ch] [rbp-10Ch]
  int v83; // [rsp+30h] [rbp-108h]
  int v84; // [rsp+34h] [rbp-104h]
  __int128 v85; // [rsp+40h] [rbp-F8h] BYREF
  struct Microsoft::Diagnostics::ScenarioParsingState *v86; // [rsp+50h] [rbp-E8h]
  _QWORD v87[2]; // [rsp+60h] [rbp-D8h] BYREF
  _QWORD v88[2]; // [rsp+70h] [rbp-C8h] BYREF
  _BYTE v89[16]; // [rsp+80h] [rbp-B8h] BYREF
  _QWORD v90[2]; // [rsp+90h] [rbp-A8h] BYREF
  unsigned __int64 v91; // [rsp+A0h] [rbp-98h]
  unsigned __int64 v92; // [rsp+A8h] [rbp-90h]
  _QWORD v93[2]; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v94; // [rsp+C0h] [rbp-78h]
  unsigned __int64 v95; // [rsp+C8h] [rbp-70h]
  _QWORD v96[4]; // [rsp+D0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    v86 = a3;
    v6 = *((unsigned __int16 *)this + 8);
    if ( v6 )
    {
      v66 = v6 - 1;
      if ( v66 )
      {
        v67 = v66 - 1;
        if ( v67 )
        {
          v68 = v67 - 1;
          if ( v68 )
          {
            v69 = v68 - 1;
            if ( v69 )
            {
              v70 = v69 - 1;
              if ( v70 )
              {
                if ( v70 != 1 )
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
    Microsoft::Diagnostics::ParsingDomain::ParsingDomain(v93, (char *)a3 + 112, v7);
    v8 = v93[0];
    v12 = std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(v93[0], v9, v10, v11);
    std::wstring::_Assign<wchar_t>(v12 + 8, v13, *((_QWORD *)this + 5));
    std::wstring::wstring(v96);
    v85 = *(_OWORD *)&off_18036CD88;
    v93[0] = &Src;
    v93[1] = std::_WChar_traits<wchar_t>::length(&Src);
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v93, &v85, v96) == 1 )
      goto LABEL_5;
    v65 = v96;
    if ( v96[3] > 7u )
      v65 = (_WORD *)v96[0];
    if ( v96[2] && (*v65 == 84 || *v65 == 49 || *v65 == 116) )
      v14 = 1;
    else
LABEL_5:
      v14 = 0;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    v83 = 0;
    v84 = 0;
    v79 = 0;
    *((_BYTE *)this + 160) = v14;
    while ( 1 )
    {
      Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v16 = Element;
      if ( Element )
        break;
      std::wstring::wstring(v90);
      Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v90);
      v17 = v90;
      if ( v92 > 7 )
        v17 = (_QWORD *)v90[0];
      v18 = v91;
      v19 = v91;
      if ( v91 >= 4 )
        v19 = 4;
      if ( !(unsigned int)_o__wcsnicmp(L"hive", v17, v19) && v18 == 4 )
      {
        std::wstring::wstring(v93);
        InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v93);
        v45 = InnerText;
        if ( InnerText < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x180,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
            (const char *)(unsigned int)InnerText,
            v79);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v90);
          std::wstring::_Tidy_deallocate(v96);
          return v45;
        }
        v46 = v93;
        if ( v95 > 7 )
          v46 = (_QWORD *)v93[0];
        v87[0] = v46;
        v87[1] = v94;
        HiveFromString = Microsoft::Diagnostics::Utils::Xml::GetHiveFromString(v87, 0, (char *)this + 56);
        v48 = HiveFromString;
        if ( HiveFromString < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x181,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
            (const char *)(unsigned int)HiveFromString,
            v79);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v90);
          std::wstring::_Tidy_deallocate(v96);
          return v48;
        }
        v49 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v50 = v49;
        if ( v49 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x182,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
            (const char *)(unsigned int)v49,
            v79);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v90);
          std::wstring::_Tidy_deallocate(v96);
          return v50;
        }
        ++v80;
LABEL_40:
        std::wstring::_Tidy_deallocate(v93);
        goto LABEL_41;
      }
      v20 = v90;
      if ( v92 > 7 )
        v20 = (_QWORD *)v90[0];
      v21 = v91;
      v22 = v91;
      if ( v91 >= 7 )
        v22 = 7;
      if ( !(unsigned int)_o__wcsnicmp(L"keyname", v20, v22) && v21 == 7 )
      {
        v71 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 64);
        v72 = v71;
        if ( v71 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x188,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
            (const char *)(unsigned int)v71,
            v79);
          std::wstring::_Tidy_deallocate(v90);
          std::wstring::_Tidy_deallocate(v96);
          return v72;
        }
        v73 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v74 = v73;
        if ( v73 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x189,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
            (const char *)(unsigned int)v73,
            v79);
          std::wstring::_Tidy_deallocate(v90);
          std::wstring::_Tidy_deallocate(v96);
          return v74;
        }
        ++v81;
      }
      else
      {
        v23 = v90;
        if ( v92 > 7 )
          v23 = (_QWORD *)v90[0];
        v24 = v91;
        v25 = v91;
        if ( v91 >= 9 )
          v25 = 9;
        if ( !(unsigned int)_o__wcsnicmp(L"valuename", v23, v25) && v24 == 9 )
        {
          v51 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 96);
          v52 = v51;
          if ( v51 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x18F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)(unsigned int)v51,
              v79);
            std::wstring::_Tidy_deallocate(v90);
            std::wstring::_Tidy_deallocate(v96);
            return v52;
          }
          v53 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v54 = v53;
          if ( v53 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x190,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)(unsigned int)v53,
              v79);
            std::wstring::_Tidy_deallocate(v90);
            std::wstring::_Tidy_deallocate(v96);
            return v54;
          }
          ++v82;
        }
        else
        {
          v26 = v90;
          if ( v92 > 7 )
            v26 = (_QWORD *)v90[0];
          v27 = v91;
          v28 = v91;
          if ( v91 >= 9 )
            v28 = 9;
          if ( !(unsigned int)_o__wcsnicmp(L"valuetype", v26, v28) && v27 == 9 )
          {
            std::wstring::wstring(v93);
            v36 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v93);
            v37 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x197,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v36,
                v79);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              return v37;
            }
            v38 = v93;
            if ( v95 > 7 )
              v38 = (_QWORD *)v93[0];
            v88[0] = v38;
            v88[1] = v94;
            v39 = (_DWORD *)((char *)this + 128);
            v40 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToRegistryType(v88, (char *)this + 128);
            v41 = v40;
            if ( v40 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x198,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v40,
                v79);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              return v41;
            }
            if ( *v39 > 4u && *v39 != 11 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x19B,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)0x87C5243FLL,
                v79);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              return 2277844031LL;
            }
            v42 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v43 = v42;
            if ( v42 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x19D,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v42,
                v79);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              return v43;
            }
            ++v83;
            goto LABEL_40;
          }
          v29 = v90;
          if ( v92 > 7 )
            v29 = (_QWORD *)v90[0];
          v30 = v91;
          v31 = v91;
          if ( v91 >= 5 )
            v31 = 5;
          if ( !(unsigned int)_o__wcsnicmp(L"value", v29, v31) && v30 == 5 )
          {
            std::wstring::wstring(v93);
            v32 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v93);
            v33 = v32;
            if ( v32 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A4,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v32,
                v79);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              return v33;
            }
            v34 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v35 = v34;
            if ( v34 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A5,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v34,
                v79);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              return v35;
            }
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
              (char *)this + 144,
              v89,
              v93);
            ++v84;
            goto LABEL_40;
          }
          v55 = v90;
          if ( v92 > 7 )
            v55 = (_QWORD *)v90[0];
          v56 = v91;
          v57 = v91;
          if ( v91 >= 9 )
            v57 = 9;
          if ( !(unsigned int)_o__wcsnicmp(L"operation", v55, v57) && v56 == 9 )
          {
            std::wstring::wstring(v93);
            v58 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v93);
            v59 = v58;
            if ( v58 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AE,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v58,
                v79);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              return v59;
            }
            v60 = v93;
            if ( v95 > 7 )
              v60 = (_QWORD *)v93[0];
            *(_QWORD *)&v85 = v60;
            *((_QWORD *)&v85 + 1) = v94;
            v61 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToOperation(&v85, (char *)this + 132);
            v62 = v61;
            if ( v61 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AF,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v61,
                v79);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              return v62;
            }
            v75 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v76 = v75;
            if ( v75 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1B0,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v75,
                v79);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              return v76;
            }
            ++v79;
            goto LABEL_40;
          }
          if ( *((_BYTE *)v86 + 152) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B8,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)0x87C52407LL,
              v79);
            std::wstring::_Tidy_deallocate(v90);
            std::wstring::_Tidy_deallocate(v96);
            return 2277843975LL;
          }
          v77 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v78 = v77;
          if ( v77 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1BB,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)(unsigned int)v77,
              v79);
            std::wstring::_Tidy_deallocate(v90);
            std::wstring::_Tidy_deallocate(v96);
            return v78;
          }
        }
      }
LABEL_41:
      std::wstring::_Tidy_deallocate(v90);
    }
    if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
    {
      if ( v80 == 1 && v81 == 1 && v82 == 1 && v83 == 1 && v84 && v79 == 1 )
      {
        (*(void (__fastcall **)(Microsoft::Diagnostics::RegistryKeyFilterDef *, _QWORD))(*(_QWORD *)this + 16LL))(
          this,
          0);
        std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v8);
        std::wstring::_Tidy_deallocate(v96);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C6,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
          (const char *)0x87C52402LL,
          v79);
        std::wstring::_Tidy_deallocate(v96);
        result = 2277843970LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
        (const char *)Element,
        v79);
      std::wstring::_Tidy_deallocate(v96);
      result = v16;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1CD,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                           v63);
  }
  return result;
}

```

## disassembly

```asm
0x1800a5730  push    rbx
0x1800a5732  push    rsi
0x1800a5733  push    rdi
0x1800a5734  push    r12
0x1800a5736  push    r13
0x1800a5738  push    r14
0x1800a573a  push    r15
0x1800a573c  sub     rsp, 100h
0x1800a5743  mov     rax, cs:__security_cookie
0x1800a574a  xor     rax, rsp
0x1800a574d  mov     [rsp+138h+var_48], rax
0x1800a5755  mov     r9, r8; char *
0x1800a5758  mov     [rsp+138h+var_E8], r8
0x1800a575d  mov     r14, rdx
0x1800a5760  mov     r13, rcx
0x1800a5763  movzx   ecx, word ptr [rcx+10h]
0x1800a5767  test    ecx, ecx
0x1800a5769  jnz     loc_1800A5D33
0x1800a576f  lea     r12d, [rcx+5]
0x1800a5773  movzx   r8d, r12w
0x1800a5777  mov     r15d, 9
0x1800a577d  mov     edi, 8
0x1800a5782  mov     esi, 7
0x1800a5787  lea     rdx, [r9+70h]
0x1800a578b  lea     rcx, [rsp+138h+var_88]
0x1800a5793  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1800a5798  cmp     [r13+30h], rsi
0x1800a579c  jbe     loc_1800A5D2A
0x1800a57a2  mov     r10, [r13+18h]
0x1800a57a6  mov     rbx, [rsp+138h+var_88]
0x1800a57ae  mov     rcx, rbx
0x1800a57b1  call    ?top@?$stack@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$deque@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@@2@@2@@std@@QEAAAEAV?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@2@XZ; std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(void)
0x1800a57b6  lea     rcx, [rdi+rax]
0x1800a57ba  mov     r8, [r13+28h]
0x1800a57be  mov     rdx, r10
0x1800a57c1  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800a57c6  lea     rcx, [rsp+138h+var_68]; void *
0x1800a57ce  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a57d3  nop
0x1800a57d4  movups  xmm0, xmmword ptr cs:off_18036CD88; "treatnotexistsassuccess"
0x1800a57db  movdqu  [rsp+138h+var_F8], xmm0
0x1800a57e1  lea     rcx, Src
0x1800a57e8  mov     [rsp+138h+var_88], rcx
0x1800a57f0  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a57f5  mov     [rsp+138h+var_80], rax
0x1800a57fd  lea     r9, [rsp+138h+var_68]
0x1800a5805  lea     r8, [rsp+138h+var_F8]
0x1800a580a  lea     rdx, [rsp+138h+var_88]
0x1800a5812  mov     rcx, r14
0x1800a5815  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a581a  cmp     eax, 1
0x1800a581d  jnz     loc_1800A5CE5
0x1800a5823  xor     al, al
0x1800a5825  xor     ecx, ecx
0x1800a5827  mov     [rsp+138h+var_114], ecx
0x1800a582b  mov     [rsp+138h+var_110], ecx
0x1800a582f  xor     edx, edx
0x1800a5831  mov     [rsp+138h+var_10C], edx
0x1800a5835  mov     [rsp+138h+var_108], ecx
0x1800a5839  mov     [rsp+138h+var_104], ecx
0x1800a583d  mov     [rsp+138h+var_118], ecx; int
0x1800a5841  mov     [r13+0A0h], al
0x1800a5848  mov     rcx, r14; this
0x1800a584b  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1800a5850  mov     edi, eax
0x1800a5852  test    eax, eax
0x1800a5854  jnz     loc_1800A5DA0
0x1800a585a  lea     rcx, [rsp+138h+var_A8]; void *
0x1800a5862  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5867  nop
0x1800a5868  lea     rdx, [rsp+138h+var_A8]
0x1800a5870  mov     rcx, r14
0x1800a5873  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1800a5878  lea     rdx, [rsp+138h+var_A8]
0x1800a5880  cmp     [rsp+138h+var_90], rsi
0x1800a5888  cmova   rdx, [rsp+138h+var_A8]
0x1800a5891  mov     rdi, [rsp+138h+var_98]
0x1800a5899  mov     r8, rdi
0x1800a589c  mov     eax, 4
0x1800a58a1  cmp     rdi, rax
0x1800a58a4  cmovnb  r8, rax
0x1800a58a8  mov     rcx, cs:off_18036CC08; "hive"
0x1800a58af  call    cs:__imp__o__wcsnicmp
0x1800a58b5  test    eax, eax
0x1800a58b7  jnz     short loc_1800A58C8
0x1800a58b9  mov     eax, 4
0x1800a58be  sub     eax, edi
0x1800a58c0  test    eax, eax
0x1800a58c2  jz      loc_1800A5B06
0x1800a58c8  lea     rdx, [rsp+138h+var_A8]
0x1800a58d0  cmp     [rsp+138h+var_90], rsi
0x1800a58d8  cmova   rdx, [rsp+138h+var_A8]
0x1800a58e1  mov     rdi, [rsp+138h+var_98]
0x1800a58e9  mov     r8, rdi
0x1800a58ec  cmp     rdi, rsi
0x1800a58ef  cmovnb  r8, rsi
0x1800a58f3  mov     rcx, cs:off_18036CC18; "keyname"
0x1800a58fa  call    cs:__imp__o__wcsnicmp
0x1800a5900  test    eax, eax
0x1800a5902  jnz     short loc_1800A590E
0x1800a5904  mov     eax, esi
0x1800a5906  sub     eax, edi
0x1800a5908  jz      loc_1800A5D6F
0x1800a590e  lea     rdx, [rsp+138h+var_A8]
0x1800a5916  cmp     [rsp+138h+var_90], rsi
0x1800a591e  cmova   rdx, [rsp+138h+var_A8]
0x1800a5927  mov     rdi, [rsp+138h+var_98]
0x1800a592f  mov     r8, rdi
0x1800a5932  cmp     rdi, r15
0x1800a5935  cmovnb  r8, r15
0x1800a5939  mov     rcx, cs:off_18036CC28; "valuename"
0x1800a5940  call    cs:__imp__o__wcsnicmp
0x1800a5946  test    eax, eax
0x1800a5948  jnz     short loc_1800A5955
0x1800a594a  mov     eax, r15d
0x1800a594d  sub     eax, edi
0x1800a594f  jz      loc_1800A5B8E
0x1800a5955  lea     rdx, [rsp+138h+var_A8]
0x1800a595d  cmp     [rsp+138h+var_90], rsi
0x1800a5965  cmova   rdx, [rsp+138h+var_A8]
0x1800a596e  mov     rdi, [rsp+138h+var_98]
0x1800a5976  mov     r8, rdi
0x1800a5979  cmp     rdi, r15
0x1800a597c  cmovnb  r8, r15
0x1800a5980  mov     rcx, cs:off_18036CC68; "valuetype"
0x1800a5987  call    cs:__imp__o__wcsnicmp
0x1800a598d  test    eax, eax
0x1800a598f  jz      loc_1800A5A62
0x1800a5995  lea     rdx, [rsp+138h+var_A8]
0x1800a599d  cmp     [rsp+138h+var_90], rsi
0x1800a59a5  cmova   rdx, [rsp+138h+var_A8]
0x1800a59ae  mov     rdi, [rsp+138h+var_98]
0x1800a59b6  mov     r8, rdi
0x1800a59b9  cmp     rdi, r12
0x1800a59bc  cmovnb  r8, r12
0x1800a59c0  mov     rcx, cs:off_18036CC98; "value"
0x1800a59c7  call    cs:__imp__o__wcsnicmp
0x1800a59cd  test    eax, eax
0x1800a59cf  jnz     loc_1800A5BBF
0x1800a59d5  mov     eax, r12d
0x1800a59d8  sub     eax, edi
0x1800a59da  test    eax, eax
0x1800a59dc  jnz     loc_1800A5BBF
0x1800a59e2  lea     rcx, [rsp+138h+var_88]; void *
0x1800a59ea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a59ef  nop
0x1800a59f0  lea     rdx, [rsp+138h+var_88]
0x1800a59f8  mov     rcx, r14
0x1800a59fb  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a5a00  mov     edi, eax
0x1800a5a02  test    eax, eax
0x1800a5a04  js      loc_1800A5E47
0x1800a5a0a  mov     rcx, r14; this
0x1800a5a0d  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a5a12  mov     edi, eax
0x1800a5a14  test    eax, eax
0x1800a5a16  js      loc_1800A6237
0x1800a5a1c  lea     rcx, [r13+90h]
0x1800a5a23  lea     r8, [rsp+138h+var_88]
0x1800a5a2b  lea     rdx, [rsp+138h+var_B8]
0x1800a5a33  call    ??$_Emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x1800a5a38  inc     [rsp+138h+var_104]
0x1800a5a3c  lea     rcx, [rsp+138h+var_88]
0x1800a5a44  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5a49  nop
0x1800a5a4a  lea     rcx, [rsp+138h+var_A8]
0x1800a5a52  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5a57  mov     r12d, 5
0x1800a5a5d  jmp     loc_1800A5848
0x1800a5a62  mov     eax, r15d
0x1800a5a65  sub     eax, edi
0x1800a5a67  test    eax, eax
0x1800a5a69  jnz     loc_1800A5995
0x1800a5a6f  lea     rcx, [rsp+138h+var_88]; void *
0x1800a5a77  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5a7c  nop
0x1800a5a7d  lea     rdx, [rsp+138h+var_88]
0x1800a5a85  mov     rcx, r14
0x1800a5a88  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a5a8d  mov     edi, eax
0x1800a5a8f  test    eax, eax
0x1800a5a91  js      loc_1800A60F3
0x1800a5a97  lea     rax, [rsp+138h+var_88]
0x1800a5a9f  cmp     [rsp+138h+var_70], rsi
0x1800a5aa7  cmova   rax, [rsp+138h+var_88]
0x1800a5ab0  mov     [rsp+138h+var_C8], rax
0x1800a5ab5  mov     rax, [rsp+138h+var_78]
0x1800a5abd  mov     [rsp+138h+var_C0], rax
0x1800a5ac2  lea     r12, [r13+80h]
0x1800a5ac9  mov     rdx, r12
0x1800a5acc  lea     rcx, [rsp+138h+var_C8]
0x1800a5ad1  call    ?ConvertStringToRegistryType@Xml@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAK@Z; Microsoft::Diagnostics::Utils::Xml::ConvertStringToRegistryType(std::wstring_view,ulong &)
0x1800a5ad6  mov     edi, eax
0x1800a5ad8  test    eax, eax
0x1800a5ada  js      loc_1800A6140
0x1800a5ae0  cmp     dword ptr [r12], 4
0x1800a5ae5  ja      loc_1800A618D
0x1800a5aeb  mov     rcx, r14; this
0x1800a5aee  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a5af3  mov     edi, eax
0x1800a5af5  test    eax, eax
0x1800a5af7  js      loc_1800A61EA
0x1800a5afd  inc     [rsp+138h+var_108]
0x1800a5b01  jmp     loc_1800A5A3C
0x1800a5b06  lea     rcx, [rsp+138h+var_88]; void *
0x1800a5b0e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5b13  nop
0x1800a5b14  lea     rdx, [rsp+138h+var_88]
0x1800a5b1c  mov     rcx, r14
0x1800a5b1f  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a5b24  mov     edi, eax
0x1800a5b26  test    eax, eax
0x1800a5b28  js      loc_1800A5EC2
0x1800a5b2e  lea     rax, [rsp+138h+var_88]
0x1800a5b36  cmp     [rsp+138h+var_70], rsi
0x1800a5b3e  cmova   rax, [rsp+138h+var_88]
0x1800a5b47  mov     [rsp+138h+var_D8], rax
0x1800a5b4c  mov     rax, [rsp+138h+var_78]
0x1800a5b54  mov     [rsp+138h+var_D0], rax
0x1800a5b59  lea     r8, [r13+38h]
0x1800a5b5d  xor     edx, edx
0x1800a5b5f  lea     rcx, [rsp+138h+var_D8]
0x1800a5b64  call    ?GetHiveFromString@Xml@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_NAEAPEAUHKEY__@@@Z; Microsoft::Diagnostics::Utils::Xml::GetHiveFromString(std::wstring_view,bool,HKEY__ * &)
0x1800a5b69  mov     edi, eax
0x1800a5b6b  test    eax, eax
0x1800a5b6d  js      loc_1800A5F5D
0x1800a5b73  mov     rcx, r14; this
0x1800a5b76  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a5b7b  mov     edi, eax
0x1800a5b7d  test    eax, eax
0x1800a5b7f  js      loc_1800A5FAA
0x1800a5b85  inc     [rsp+138h+var_114]
0x1800a5b89  jmp     loc_1800A5A3C
0x1800a5b8e  lea     rdx, [r13+60h]
0x1800a5b92  mov     rcx, r14
0x1800a5b95  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a5b9a  mov     edi, eax
0x1800a5b9c  test    eax, eax
0x1800a5b9e  js      loc_1800A6075
0x1800a5ba4  mov     rcx, r14; this
0x1800a5ba7  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a5bac  mov     edi, eax
0x1800a5bae  test    eax, eax
0x1800a5bb0  js      loc_1800A60B4
0x1800a5bb6  inc     [rsp+138h+var_10C]
0x1800a5bba  jmp     loc_1800A5A4A
0x1800a5bbf  lea     rdx, [rsp+138h+var_A8]
0x1800a5bc7  cmp     [rsp+138h+var_90], rsi
0x1800a5bcf  cmova   rdx, [rsp+138h+var_A8]
0x1800a5bd8  mov     rdi, [rsp+138h+var_98]
0x1800a5be0  mov     r8, rdi
0x1800a5be3  cmp     rdi, r15
0x1800a5be6  cmovnb  r8, r15
0x1800a5bea  mov     rcx, cs:off_18036CDC8; "operation"
0x1800a5bf1  call    cs:__imp__o__wcsnicmp
0x1800a5bf7  test    eax, eax
0x1800a5bf9  jnz     loc_1800A631E
0x1800a5bff  mov     eax, r15d
0x1800a5c02  sub     eax, edi
0x1800a5c04  test    eax, eax
0x1800a5c06  jnz     loc_1800A631E
0x1800a5c0c  lea     rcx, [rsp+138h+var_88]; void *
0x1800a5c14  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5c19  nop
0x1800a5c1a  lea     rdx, [rsp+138h+var_88]
0x1800a5c22  mov     rcx, r14
0x1800a5c25  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a5c2a  mov     edi, eax
0x1800a5c2c  test    eax, eax
0x1800a5c2e  js      loc_1800A6284
0x1800a5c34  lea     rax, [rsp+138h+var_88]
0x1800a5c3c  cmp     [rsp+138h+var_70], rsi
0x1800a5c44  cmova   rax, [rsp+138h+var_88]
0x1800a5c4d  mov     qword ptr [rsp+138h+var_F8], rax
0x1800a5c52  mov     rax, [rsp+138h+var_78]
0x1800a5c5a  mov     qword ptr [rsp+138h+var_F8+8], rax
0x1800a5c5f  lea     rdx, [r13+84h]
0x1800a5c66  lea     rcx, [rsp+138h+var_F8]
0x1800a5c6b  call    ?ConvertStringToOperation@Xml@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU?$optional@VComparisonOperator@Filters@Diagnostics@Microsoft@@@better_enums@@@Z; Microsoft::Diagnostics::Utils::Xml::ConvertStringToOperation(std::wstring_view,better_enums::optional<Microsoft::Diagnostics::Filters::ComparisonOperator> &)
0x1800a5c70  mov     edi, eax
0x1800a5c72  test    eax, eax
0x1800a5c74  jns     loc_1800A5E94
0x1800a5c7a  mov     rcx, [rsp+138h]; this
0x1800a5c82  mov     r9d, eax; char *
0x1800a5c85  lea     r8, aOnecoreBaseTel_10; "onecore\\base\\telemetry\\utc\\service"...
0x1800a5c8c  mov     edx, 1AFh; void *
0x1800a5c91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5c96  nop
0x1800a5c97  lea     rcx, [rsp+138h+var_88]
0x1800a5c9f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5ca4  nop
0x1800a5ca5  lea     rcx, [rsp+138h+var_A8]
0x1800a5cad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5cb2  nop
0x1800a5cb3  lea     rcx, [rsp+138h+var_68]
0x1800a5cbb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5cc0  mov     eax, edi
0x1800a5cc2  mov     rcx, [rsp+138h+var_48]
0x1800a5cca  xor     rcx, rsp; StackCookie
0x1800a5ccd  call    __security_check_cookie
  ... truncated ...
```

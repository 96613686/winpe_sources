# Microsoft::Diagnostics::ScenarioStateModelDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1800a1940`
- end: `0x1800a23aa`
- name: `?ParseFromXml@ScenarioStateModelDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `2666`
- prototype: `int(Microsoft::Diagnostics::ScenarioStateModelDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001d9a0`
- `0x18002b318`
- `0x18002cae0`
- `0x18002df00`
- `0x180064e8c`
- `0x1800653d0`
- `0x18007038c`
- `0x18008b254`
- `0x18009c8c0`
- `0x18009dec0`
- `0x1800a0558`
- `0x1800a1940`
- `0x1800a23b0`
- `0x1800a24e0`
- `0x1800a274c`
- `0x1800a346c`
- `0x1800a3584`
- `0x1800a3760`
- `0x1800a37b0`
- `0x1800afab0`
- `0x1801b7bd0`
- `0x1801bbc78`
- `0x18020aac0`
- `0x1802be760`
- `0x180369010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800a1e58`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800a1e58`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1aa8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1b4b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1b96`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1bde`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1d53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1de8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1e33`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1aa8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1b4b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1b96`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1bde`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1d53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1de8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1e33`

## string_xrefs

- `0x1800a1f94`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a1fce`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a2058`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a20bb`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a2118`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a215c`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a21a0`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a21e4`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a2228`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a22b4`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a2304`: `onecore\base\telemetry\utc\service\scenarios\base\scenariostatemodeldef.cpp`
- `0x1800a234a`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x1800a2382`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::ScenarioStateModelDef::ParseFromXml(
        Microsoft::Diagnostics::ScenarioStateModelDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  const WCHAR *v6; // rax
  _BYTE *v7; // r13
  unsigned int Element; // edi
  _QWORD *v9; // rdx
  int v10; // edi
  __int64 v11; // r8
  _QWORD *v12; // rcx
  int v13; // edi
  __int64 v14; // r8
  _QWORD *v15; // rcx
  int v16; // edi
  __int64 v17; // r8
  _QWORD *v18; // rcx
  __int64 v19; // r8
  _QWORD *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  char v23; // r9
  __int64 *v24; // rax
  _QWORD *v25; // rdx
  int v26; // edi
  __int64 v27; // r8
  _QWORD *v28; // rcx
  int v29; // edi
  __int64 v30; // r8
  _QWORD *v31; // rcx
  int v32; // edi
  __int64 v33; // r8
  char *v34; // r15
  _QWORD *v35; // r14
  _QWORD *v36; // r13
  int v37; // r12d
  __int64 v38; // rax
  const char *v39; // r9
  __int16 v40; // cx
  Microsoft::Diagnostics::ScenarioStateModelDef *v41; // r15
  _QWORD *v42; // r14
  _QWORD *v43; // r12
  const char *v44; // r9
  __int64 result; // rax
  int v46; // esi
  __int64 v47; // rax
  const char *v48; // r9
  __int16 v49; // cx
  int v50[4]; // [rsp+20h] [rbp-168h] BYREF
  const WCHAR *v51; // [rsp+30h] [rbp-158h] BYREF
  __int64 v52; // [rsp+38h] [rbp-150h]
  Microsoft::Diagnostics::ScenarioStateModelDef *v53; // [rsp+48h] [rbp-140h]
  __int128 v54; // [rsp+50h] [rbp-138h] BYREF
  __int128 v55; // [rsp+60h] [rbp-128h] BYREF
  __int64 v56; // [rsp+70h] [rbp-118h] BYREF
  _QWORD v57[2]; // [rsp+80h] [rbp-108h] BYREF
  _QWORD v58[2]; // [rsp+90h] [rbp-F8h] BYREF
  char v59; // [rsp+A0h] [rbp-E8h]
  _BYTE v60[24]; // [rsp+A8h] [rbp-E0h] BYREF
  __int128 v61; // [rsp+C0h] [rbp-C8h] BYREF
  _BYTE v62[16]; // [rsp+E0h] [rbp-A8h] BYREF
  _BYTE v63[16]; // [rsp+F0h] [rbp-98h] BYREF
  _QWORD v64[2]; // [rsp+100h] [rbp-88h] BYREF
  unsigned __int64 v65; // [rsp+110h] [rbp-78h]
  unsigned __int64 v66; // [rsp+118h] [rbp-70h]
  _QWORD v67[2]; // [rsp+120h] [rbp-68h] BYREF
  unsigned __int64 v68; // [rsp+130h] [rbp-58h]
  unsigned __int64 v69; // [rsp+138h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  try
  {
    v53 = this;
    Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v56, (char *)a3 + 112, 41);
    std::wstring::wstring(v64);
    v55 = *(_OWORD *)&off_18036CB28;
    v51 = &Src;
    v52 = std::_WChar_traits<wchar_t>::length(&Src);
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v51, &v55, v64) == 1 )
    {
      if ( *((_BYTE *)a3 + 152) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EE,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
          (const char *)0x87C5241ALL,
          v50[0]);
        std::wstring::_Tidy_deallocate(v64);
        return 2277843994LL;
      }
      std::wstring::_Assign<wchar_t>(v64, L"start", 5);
    }
    v6 = (const WCHAR *)v64;
    if ( v66 > 7 )
      v6 = (const WCHAR *)v64[0];
    v51 = v6;
    v52 = v65;
    v7 = (char *)this + 16;
    if ( (int)Microsoft::Diagnostics::StateDef::ConvertStringToStateOrdinal(&v51, (char *)this + 16) < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
        (const char *)0x87C5241BLL,
        v50[0]);
      std::wstring::_Tidy_deallocate(v64);
      result = 2277843995LL;
    }
    else if ( *v7 == 0xFA || *v7 == 0xFD )
    {
      if ( Microsoft::Diagnostics::XMLFacade::IsEmptyElement(a2) )
      {
        (*(void (__fastcall **)(Microsoft::Diagnostics::ScenarioStateModelDef *, _QWORD))(*(_QWORD *)this + 16LL))(
          this,
          0);
        std::wstring::_Tidy_deallocate(v64);
        result = 0;
      }
      else
      {
        while ( 1 )
        {
          Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
          if ( Element )
            break;
          std::wstring::wstring(v67);
          Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v67);
          v9 = v67;
          if ( v69 > 7 )
            v9 = (_QWORD *)v67[0];
          v10 = v68;
          v11 = v68;
          if ( v68 >= 5 )
            v11 = 5;
          if ( (unsigned int)_o__wcsnicmp(L"state", v9, v11) || v10 != 5 )
          {
            v25 = v67;
            if ( v69 > 7 )
              v25 = (_QWORD *)v67[0];
            v26 = v68;
            v27 = v68;
            if ( v68 >= 5 )
              v27 = 5;
            if ( (unsigned int)_o__wcsnicmp(L"final", v25, v27) || v26 != 5 )
            {
              if ( *((_BYTE *)a3 + 152) )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x24A,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
                  (const char *)0x87C52407LL,
                  v50[0]);
                std::wstring::_Tidy_deallocate(v67);
                std::wstring::_Tidy_deallocate(v64);
                return 2277843975LL;
              }
            }
            else
            {
              v54 = *(_OWORD *)&off_18036C678;
              *(_QWORD *)&v55 = &Src;
              *((_QWORD *)&v55 + 1) = std::_WChar_traits<wchar_t>::length(&Src);
              if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v55, &v54, v64) == 1 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x239,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
                  (const char *)0x87C52420LL,
                  v50[0]);
                std::wstring::_Tidy_deallocate(v67);
                std::wstring::_Tidy_deallocate(v64);
                return 2277844000LL;
              }
              v28 = v64;
              if ( v66 > 7 )
                v28 = (_QWORD *)v64[0];
              v29 = v65;
              v30 = 5;
              if ( v65 <= 5 )
                v30 = v65;
              if ( (unsigned int)_o__wcsnicmp(v28, Microsoft::Diagnostics::StateDef::k_reservedStateNameFail, v30)
                || v29 != 5 )
              {
                v31 = v64;
                if ( v66 > 7 )
                  v31 = (_QWORD *)v64[0];
                v32 = v65;
                v33 = 7;
                if ( v65 <= 7 )
                  v33 = v65;
                if ( (unsigned int)_o__wcsnicmp(v31, Microsoft::Diagnostics::StateDef::k_reservedStateNameCancel, v33)
                  || v32 != 7 )
                {
                  v54 = *(_OWORD *)&Microsoft::Diagnostics::StateDef::k_reservedStateNameComplete;
                  v61 = *(_OWORD *)std::wstring::operator std::wstring_view(v64, v63);
                  if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v61, &v54) )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x241,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
                      (const char *)0x87C52421LL,
                      v50[0]);
                    std::wstring::_Tidy_deallocate(v67);
                    std::wstring::_Tidy_deallocate(v64);
                    return 2277844001LL;
                  }
                }
              }
            }
          }
          else
          {
            if ( *v7 == 0xFD )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x210,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
                (const char *)0x87C5241CLL,
                v50[0]);
              std::wstring::_Tidy_deallocate(v67);
              std::wstring::_Tidy_deallocate(v64);
              return 2277843996LL;
            }
            v54 = *(_OWORD *)&off_18036C678;
            v51 = &Src;
            v52 = std::_WChar_traits<wchar_t>::length(&Src);
            if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v51, &v54, v64) == 1 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x217,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
                (const char *)0x87C5241DLL,
                v50[0]);
              std::wstring::_Tidy_deallocate(v67);
              std::wstring::_Tidy_deallocate(v64);
              return 2277843997LL;
            }
            v12 = v64;
            if ( v66 > 7 )
              v12 = (_QWORD *)v64[0];
            v13 = v65;
            v14 = 9;
            if ( v65 <= 9 )
              v14 = v65;
            if ( !(unsigned int)_o__wcsnicmp(v12, Microsoft::Diagnostics::StateDef::k_reservedStateNameComplete, v14)
              && v13 == 9 )
            {
              goto LABEL_94;
            }
            v15 = v64;
            if ( v66 > 7 )
              v15 = (_QWORD *)v64[0];
            v16 = v65;
            v17 = 7;
            if ( v65 <= 7 )
              v17 = v65;
            if ( !(unsigned int)_o__wcsnicmp(v15, Microsoft::Diagnostics::StateDef::k_reservedStateNameCancel, v17)
              && v16 == 7 )
            {
              goto LABEL_94;
            }
            v18 = v64;
            if ( v66 > 7 )
              v18 = (_QWORD *)v64[0];
            Element = v65;
            v19 = 5;
            if ( v65 <= 5 )
              v19 = v65;
            if ( !(unsigned int)_o__wcsnicmp(v18, Microsoft::Diagnostics::StateDef::k_reservedStateNameFail, v19)
              && Element == 5 )
            {
LABEL_94:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x21F,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
                (const char *)0x87C5241ELL,
                v50[0]);
              std::wstring::_Tidy_deallocate(v67);
              std::wstring::_Tidy_deallocate(v64);
              return 2277843998LL;
            }
            LOBYTE(v50[0]) = -1;
            v20 = v64;
            if ( v66 > 7 )
              v20 = (_QWORD *)v64[0];
            v57[0] = v20;
            v57[1] = v65;
            if ( (int)Microsoft::Diagnostics::StateDef::ConvertStringToStateOrdinal(v57, v50) < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x227,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
                (const char *)0x87C5241FLL,
                v50[0]);
              std::wstring::_Tidy_deallocate(v67);
              std::wstring::_Tidy_deallocate(v64);
              return 2277843999LL;
            }
            v58[1] = 0;
            v58[0] = &Microsoft::Diagnostics::StateDef::`vftable';
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(v60);
            v59 = v50[0];
            Microsoft::Diagnostics::StateDef::ParseFromXml((Microsoft::Diagnostics::StateDef *)v58, a2, a3);
            std::_Tree<std::_Tmap_traits<unsigned char,std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>>>,0>>::_Emplace<unsigned char &,std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair> const &>(
              (char *)this + 72,
              v62,
              v50,
              v60);
            v21 = *((_QWORD *)this + 9);
            v22 = *(_QWORD *)(v21 + 8);
            HIDWORD(v61) = 0;
            while ( !*(_BYTE *)(v22 + 25) )
            {
              if ( *(_BYTE *)(v22 + 32) < LOBYTE(v50[0]) )
              {
                v23 = 1;
              }
              else
              {
                v23 = 0;
                v21 = v22;
              }
              v24 = (__int64 *)(v22 + 16);
              if ( !v23 )
                v24 = (__int64 *)v22;
              v22 = *v24;
            }
            if ( *(_BYTE *)(v21 + 25) || LOBYTE(v50[0]) < *(_BYTE *)(v21 + 32) )
            {
              std::_Xout_of_range("invalid map<K, T> key");
              break;
            }
            std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::shrink_to_fit(v21 + 40);
            std::vector<std::wstring_view>::~vector<std::wstring_view>(v60);
          }
          std::wstring::_Tidy_deallocate(v67);
        }
        v34 = (char *)this + 24;
        std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::reserve(
          (char *)this + 24,
          ((__int64)(*((_QWORD *)a3 + 29) - *((_QWORD *)a3 + 28)) >> 4)
        + ((__int64)(*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) >> 4));
        v35 = (_QWORD *)*((_QWORD *)a3 + 28);
        v36 = (_QWORD *)*((_QWORD *)a3 + 29);
        while ( v35 != v36 )
        {
          v37 = *(unsigned __int8 *)(*v35 + 48LL);
          v38 = (**(__int64 (__fastcall ***)(_QWORD))*v35)(*v35);
          if ( (_BYTE)v37 )
          {
            if ( v37 == 1 )
            {
              v40 = 3;
            }
            else
            {
              if ( v37 != 2 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x3A4,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                  v39);
              v40 = 4;
            }
          }
          else
          {
            v40 = 2;
          }
          LOWORD(v51) = v40;
          v52 = v38;
          std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::emplace_back<Microsoft::Diagnostics::ScenarioDbLookupPair>(
            v34,
            &v51);
          v35 += 2;
        }
        v41 = v53;
        std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::reserve(
          (char *)v53 + 48,
          ((__int64)(*((_QWORD *)a3 + 32) - *((_QWORD *)a3 + 31)) >> 4)
        + ((__int64)(*((_QWORD *)v53 + 7) - *((_QWORD *)v53 + 6)) >> 4));
        v42 = (_QWORD *)*((_QWORD *)a3 + 31);
        v43 = (_QWORD *)*((_QWORD *)a3 + 32);
        while ( v42 != v43 )
        {
          v46 = *(unsigned __int8 *)(*v42 + 48LL);
          v47 = (**(__int64 (__fastcall ***)(_QWORD))*v42)(*v42);
          if ( (_BYTE)v46 )
          {
            if ( v46 == 1 )
            {
              v49 = 3;
            }
            else
            {
              if ( v46 != 2 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x3A4,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                  v48);
              v49 = 4;
            }
          }
          else
          {
            v49 = 2;
          }
          LOWORD(v51) = v49;
          v52 = v47;
          std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::emplace_back<Microsoft::Diagnostics::ScenarioDbLookupPair>(
            (char *)v41 + 48,
            &v51);
          v42 += 2;
        }
        if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
        {
          (*(void (__fastcall **)(Microsoft::Diagnostics::ScenarioStateModelDef *, _QWORD))(*(_QWORD *)v41 + 16LL))(
            v41,
            0);
          std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v56);
          std::wstring::_Tidy_deallocate(v64);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25B,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
            (const char *)Element,
            v50[0]);
          std::wstring::_Tidy_deallocate(v64);
          result = Element;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
        (const char *)0x87C5241BLL,
        v50[0]);
      std::wstring::_Tidy_deallocate(v64);
      result = 2277843995LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x261,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariostatemodeldef.cpp",
                           v44);
  }
  return result;
}

```

## disassembly

```asm
0x1800a1940  push    rbx
0x1800a1942  push    rsi
0x1800a1943  push    rdi
0x1800a1944  push    r12
0x1800a1946  push    r13
0x1800a1948  push    r14
0x1800a194a  push    r15
0x1800a194c  sub     rsp, 150h
0x1800a1953  mov     rax, cs:__security_cookie
0x1800a195a  xor     rax, rsp
0x1800a195d  mov     [rsp+188h+var_48], rax
0x1800a1965  mov     rsi, r8
0x1800a1968  mov     r15, rdx
0x1800a196b  mov     r12, rcx
0x1800a196e  mov     [rsp+188h+var_140], rcx
0x1800a1973  mov     r8d, 29h ; ')'
0x1800a1979  lea     rdx, [rsi+70h]
0x1800a197d  lea     rcx, [rsp+188h+var_118]
0x1800a1982  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1800a1987  lea     rcx, [rsp+188h+var_88]; void *
0x1800a198f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a1994  nop
0x1800a1995  movups  xmm0, xmmword ptr cs:off_18036CB28; "initial"
0x1800a199c  movdqu  [rsp+188h+var_128], xmm0
0x1800a19a2  lea     rax, Src
0x1800a19a9  mov     [rsp+188h+var_158], rax
0x1800a19ae  mov     rcx, rax
0x1800a19b1  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a19b6  mov     [rsp+188h+var_150], rax
0x1800a19bb  lea     r9, [rsp+188h+var_88]
0x1800a19c3  lea     r8, [rsp+188h+var_128]
0x1800a19c8  lea     rdx, [rsp+188h+var_158]
0x1800a19cd  mov     rcx, r15
0x1800a19d0  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a19d5  xor     ebx, ebx
0x1800a19d7  cmp     eax, 1
0x1800a19da  jz      loc_1800A2040
0x1800a19e0  lea     r14d, [rbx+5]
0x1800a19e4  lea     rax, [rsp+188h+var_88]
0x1800a19ec  cmp     [rsp+188h+var_70], 7
0x1800a19f5  cmova   rax, [rsp+188h+var_88]
0x1800a19fe  mov     [rsp+188h+var_158], rax
0x1800a1a03  mov     rax, [rsp+188h+var_78]
0x1800a1a0b  mov     [rsp+188h+var_150], rax
0x1800a1a10  lea     r13, [r12+10h]
0x1800a1a15  mov     rdx, r13
0x1800a1a18  lea     rcx, [rsp+188h+var_158]
0x1800a1a1d  call    ?ConvertStringToStateOrdinal@StateDef@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAE@Z; Microsoft::Diagnostics::StateDef::ConvertStringToStateOrdinal(std::wstring_view,uchar &)
0x1800a1a22  test    eax, eax
0x1800a1a24  js      loc_1800A1F84
0x1800a1a2a  cmp     byte ptr [r13+0], 0FAh
0x1800a1a2f  jnz     loc_1800A20A0
0x1800a1a35  mov     rcx, r15; this
0x1800a1a38  call    ?IsEmptyElement@XMLFacade@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::XMLFacade::IsEmptyElement(void)
0x1800a1a3d  test    al, al
0x1800a1a3f  jnz     loc_1800A20E1
0x1800a1a45  mov     rcx, r15; this
0x1800a1a48  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1800a1a4d  mov     edi, eax
0x1800a1a4f  test    eax, eax
0x1800a1a51  jnz     loc_1800A1E5F
0x1800a1a57  lea     rcx, [rsp+188h+var_68]; void *
0x1800a1a5f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a1a64  nop
0x1800a1a65  lea     rdx, [rsp+188h+var_68]
0x1800a1a6d  mov     rcx, r15
0x1800a1a70  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1800a1a75  lea     rdx, [rsp+188h+var_68]
0x1800a1a7d  cmp     [rsp+188h+var_50], 7
0x1800a1a86  cmova   rdx, [rsp+188h+var_68]
0x1800a1a8f  mov     rdi, [rsp+188h+var_58]
0x1800a1a97  mov     r8, rdi
0x1800a1a9a  cmp     rdi, r14
0x1800a1a9d  cmovnb  r8, r14
0x1800a1aa1  mov     rcx, cs:off_18036C698; "state"
0x1800a1aa8  call    cs:__imp__o__wcsnicmp
0x1800a1aae  test    eax, eax
0x1800a1ab0  jnz     loc_1800A1D20
0x1800a1ab6  mov     eax, r14d
0x1800a1ab9  sub     eax, edi
0x1800a1abb  jnz     loc_1800A1D20
0x1800a1ac1  cmp     byte ptr [r13+0], 0FDh
0x1800a1ac6  jz      loc_1800A2108
0x1800a1acc  movups  xmm0, xmmword ptr cs:off_18036C678; "id"
0x1800a1ad3  movdqu  [rsp+188h+var_138], xmm0
0x1800a1ad9  lea     rax, Src
0x1800a1ae0  mov     [rsp+188h+var_158], rax
0x1800a1ae5  mov     rcx, rax
0x1800a1ae8  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a1aed  mov     [rsp+188h+var_150], rax
0x1800a1af2  lea     r9, [rsp+188h+var_88]
0x1800a1afa  lea     r8, [rsp+188h+var_138]
0x1800a1aff  lea     rdx, [rsp+188h+var_158]
0x1800a1b04  mov     rcx, r15
0x1800a1b07  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a1b0c  cmp     eax, 1
0x1800a1b0f  jz      loc_1800A214C
0x1800a1b15  lea     rcx, [rsp+188h+var_88]
0x1800a1b1d  cmp     [rsp+188h+var_70], 7
0x1800a1b26  cmova   rcx, [rsp+188h+var_88]
0x1800a1b2f  mov     rdi, [rsp+188h+var_78]
0x1800a1b37  mov     r8d, 9
0x1800a1b3d  cmp     rdi, r8
0x1800a1b40  cmovbe  r8, rdi
0x1800a1b44  mov     rdx, cs:?k_reservedStateNameComplete@StateDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::StateDef::k_reservedStateNameComplete
0x1800a1b4b  call    cs:__imp__o__wcsnicmp
0x1800a1b51  test    eax, eax
0x1800a1b53  jnz     short loc_1800A1B60
0x1800a1b55  lea     eax, [rdi-9]
0x1800a1b58  test    eax, eax
0x1800a1b5a  jz      loc_1800A2190
0x1800a1b60  lea     rcx, [rsp+188h+var_88]
0x1800a1b68  cmp     [rsp+188h+var_70], 7
0x1800a1b71  cmova   rcx, [rsp+188h+var_88]
0x1800a1b7a  mov     rdi, [rsp+188h+var_78]
0x1800a1b82  mov     r8d, 7
0x1800a1b88  cmp     rdi, r8
0x1800a1b8b  cmovbe  r8, rdi
0x1800a1b8f  mov     rdx, cs:?k_reservedStateNameCancel@StateDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::StateDef::k_reservedStateNameCancel
0x1800a1b96  call    cs:__imp__o__wcsnicmp
0x1800a1b9c  test    eax, eax
0x1800a1b9e  jnz     short loc_1800A1BAB
0x1800a1ba0  lea     eax, [rdi-7]
0x1800a1ba3  test    eax, eax
0x1800a1ba5  jz      loc_1800A2190
0x1800a1bab  lea     rcx, [rsp+188h+var_88]
0x1800a1bb3  cmp     [rsp+188h+var_70], 7
0x1800a1bbc  cmova   rcx, [rsp+188h+var_88]
0x1800a1bc5  mov     rdi, [rsp+188h+var_78]
0x1800a1bcd  mov     r8, r14
0x1800a1bd0  cmp     rdi, r14
0x1800a1bd3  cmovbe  r8, rdi
0x1800a1bd7  mov     rdx, cs:?k_reservedStateNameFail@StateDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::StateDef::k_reservedStateNameFail
0x1800a1bde  call    cs:__imp__o__wcsnicmp
0x1800a1be4  test    eax, eax
0x1800a1be6  jnz     short loc_1800A1BF3
0x1800a1be8  lea     eax, [rdi-5]
0x1800a1beb  test    eax, eax
0x1800a1bed  jz      loc_1800A2190
0x1800a1bf3  mov     byte ptr [rsp+188h+var_168], 0FFh; int
0x1800a1bf8  lea     rax, [rsp+188h+var_88]
0x1800a1c00  cmp     [rsp+188h+var_70], 7
0x1800a1c09  cmova   rax, [rsp+188h+var_88]
0x1800a1c12  mov     [rsp+188h+var_108], rax
0x1800a1c1a  mov     rax, [rsp+188h+var_78]
0x1800a1c22  mov     [rsp+188h+var_100], rax
0x1800a1c2a  lea     rdx, [rsp+188h+var_168]
0x1800a1c2f  lea     rcx, [rsp+188h+var_108]
0x1800a1c37  call    ?ConvertStringToStateOrdinal@StateDef@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAE@Z; Microsoft::Diagnostics::StateDef::ConvertStringToStateOrdinal(std::wstring_view,uchar &)
0x1800a1c3c  test    eax, eax
0x1800a1c3e  js      loc_1800A21D4
0x1800a1c44  mov     [rsp+188h+var_F0], rbx
0x1800a1c4c  lea     rax, ??_7StateDef@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::StateDef::`vftable'
0x1800a1c53  mov     [rsp+188h+var_F8], rax
0x1800a1c5b  lea     rcx, [rsp+188h+var_E0]; void *
0x1800a1c63  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x1800a1c68  nop
0x1800a1c69  mov     al, byte ptr [rsp+188h+var_168]
0x1800a1c6d  mov     [rsp+188h+var_E8], al
0x1800a1c74  mov     r8, rsi; struct Microsoft::Diagnostics::ScenarioParsingState *
0x1800a1c77  mov     rdx, r15; struct Microsoft::Diagnostics::XMLFacade *
0x1800a1c7a  lea     rcx, [rsp+188h+var_F8]; this
0x1800a1c82  call    ?ParseFromXml@StateDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z; Microsoft::Diagnostics::StateDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)
0x1800a1c87  lea     r9, [rsp+188h+var_E0]
0x1800a1c8f  lea     r8, [rsp+188h+var_168]
0x1800a1c94  lea     rdx, [rsp+188h+var_A8]
0x1800a1c9c  lea     rcx, [r12+48h]
0x1800a1ca1  call    ??$_Emplace@AEAEAEBV?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@EV?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBEV?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@@std@@PEAX@std@@_N@1@AEAEAEBV?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<uchar,std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>,std::less<uchar>,std::allocator<std::pair<uchar const,std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>>>,0>>::_Emplace<uchar &,std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair> const &>(uchar &,std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair> const &)
0x1800a1ca6  mov     rdx, [r12+48h]
0x1800a1cab  mov     rcx, [rdx+8]
0x1800a1caf  xor     eax, eax
0x1800a1cb1  mov     [rsp+188h+var_BC], eax
0x1800a1cb8  mov     r8b, byte ptr [rsp+188h+var_168]
0x1800a1cbd  cmp     [rcx+19h], bl
0x1800a1cc0  jnz     short loc_1800A1CDE
0x1800a1cc2  cmp     [rcx+20h], r8b
0x1800a1cc6  jb      short loc_1800A1D1B
0x1800a1cc8  mov     r9b, bl
0x1800a1ccb  mov     rdx, rcx
0x1800a1cce  lea     rax, [rcx+10h]
0x1800a1cd2  test    r9b, r9b
0x1800a1cd5  cmovz   rax, rcx
0x1800a1cd9  mov     rcx, [rax]
0x1800a1cdc  jmp     short loc_1800A1CBD
0x1800a1cde  cmp     [rdx+19h], bl
0x1800a1ce1  jnz     loc_1800A1E51
0x1800a1ce7  cmp     r8b, [rdx+20h]
0x1800a1ceb  jb      loc_1800A1E51
0x1800a1cf1  lea     rcx, [rdx+28h]
0x1800a1cf5  call    ?shrink_to_fit@?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@QEAAXXZ; std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::shrink_to_fit(void)
0x1800a1cfa  nop
0x1800a1cfb  lea     rcx, [rsp+188h+var_E0]
0x1800a1d03  call    ??1?$vector@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring_view>::~vector<std::wstring_view>(void)
0x1800a1d08  nop
0x1800a1d09  lea     rcx, [rsp+188h+var_68]
0x1800a1d11  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a1d16  jmp     loc_1800A1A45
0x1800a1d1b  mov     r9b, 1
0x1800a1d1e  jmp     short loc_1800A1CCE
0x1800a1d20  lea     rdx, [rsp+188h+var_68]
0x1800a1d28  cmp     [rsp+188h+var_50], 7
0x1800a1d31  cmova   rdx, [rsp+188h+var_68]
0x1800a1d3a  mov     rdi, [rsp+188h+var_58]
0x1800a1d42  mov     r8, rdi
0x1800a1d45  cmp     rdi, r14
0x1800a1d48  cmovnb  r8, r14
0x1800a1d4c  mov     rcx, cs:off_18036CE50; "final"
0x1800a1d53  call    cs:__imp__o__wcsnicmp
0x1800a1d59  test    eax, eax
0x1800a1d5b  jnz     loc_1800A22E8
0x1800a1d61  mov     eax, r14d
0x1800a1d64  sub     eax, edi
0x1800a1d66  jnz     loc_1800A22E8
0x1800a1d6c  movups  xmm0, xmmword ptr cs:off_18036C678; "id"
0x1800a1d73  movdqu  [rsp+188h+var_138], xmm0
0x1800a1d79  lea     rax, Src
0x1800a1d80  mov     qword ptr [rsp+188h+var_128], rax
0x1800a1d85  mov     rcx, rax
0x1800a1d88  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a1d8d  mov     qword ptr [rsp+188h+var_128+8], rax
0x1800a1d92  lea     r9, [rsp+188h+var_88]
0x1800a1d9a  lea     r8, [rsp+188h+var_138]
0x1800a1d9f  lea     rdx, [rsp+188h+var_128]
0x1800a1da4  mov     rcx, r15
0x1800a1da7  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a1dac  cmp     eax, 1
0x1800a1daf  jz      loc_1800A2218
0x1800a1db5  lea     rcx, [rsp+188h+var_88]
0x1800a1dbd  cmp     [rsp+188h+var_70], 7
0x1800a1dc6  cmova   rcx, [rsp+188h+var_88]
0x1800a1dcf  mov     rdi, [rsp+188h+var_78]
0x1800a1dd7  mov     r8, r14
0x1800a1dda  cmp     rdi, r14
0x1800a1ddd  cmovbe  r8, rdi
0x1800a1de1  mov     rdx, cs:?k_reservedStateNameFail@StateDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::StateDef::k_reservedStateNameFail
0x1800a1de8  call    cs:__imp__o__wcsnicmp
0x1800a1dee  test    eax, eax
0x1800a1df0  jnz     short loc_1800A1DFD
0x1800a1df2  lea     eax, [rdi-5]
0x1800a1df5  test    eax, eax
0x1800a1df7  jz      loc_1800A1D09
0x1800a1dfd  lea     rcx, [rsp+188h+var_88]
0x1800a1e05  cmp     [rsp+188h+var_70], 7
0x1800a1e0e  cmova   rcx, [rsp+188h+var_88]
0x1800a1e17  mov     rdi, [rsp+188h+var_78]
0x1800a1e1f  mov     r8d, 7
0x1800a1e25  cmp     rdi, r8
0x1800a1e28  cmovbe  r8, rdi
0x1800a1e2c  mov     rdx, cs:?k_reservedStateNameCancel@StateDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::StateDef::k_reservedStateNameCancel
0x1800a1e33  call    cs:__imp__o__wcsnicmp
0x1800a1e39  test    eax, eax
0x1800a1e3b  jnz     loc_1800A225C
0x1800a1e41  lea     eax, [rdi-7]
0x1800a1e44  test    eax, eax
0x1800a1e46  jz      loc_1800A1D09
0x1800a1e4c  jmp     loc_1800A225C
0x1800a1e51  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1800a1e58  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800a1e5e  nop
0x1800a1e5f  lea     r15, [r12+18h]
0x1800a1e64  mov     rdx, [r15+8]
0x1800a1e68  sub     rdx, [r15]
0x1800a1e6b  sar     rdx, 4
0x1800a1e6f  mov     rax, [rsi+0E8h]
0x1800a1e76  sub     rax, [rsi+0E0h]
0x1800a1e7d  sar     rax, 4
0x1800a1e81  add     rdx, rax
0x1800a1e84  mov     rcx, r15
0x1800a1e87  call    ?reserve@?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@QEAAX_K@Z; std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::reserve(unsigned __int64)
0x1800a1e8c  mov     r14, [rsi+0E0h]
0x1800a1e93  mov     r13, [rsi+0E8h]
0x1800a1e9a  cmp     r14, r13
0x1800a1e9d  jz      short loc_1800A1EE0
0x1800a1e9f  mov     rcx, [r14]
0x1800a1ea2  movzx   r12d, byte ptr [rcx+30h]
0x1800a1ea7  mov     rax, [rcx]
0x1800a1eaa  mov     rax, [rax]
0x1800a1ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1eb2  mov     edx, r12d
0x1800a1eb5  test    r12b, r12b
0x1800a1eb8  jnz     loc_1800A2338
0x1800a1ebe  mov     ecx, 2
0x1800a1ec3  mov     word ptr [rsp+188h+var_158], cx
0x1800a1ec8  mov     [rsp+188h+var_150], rax
0x1800a1ecd  lea     rdx, [rsp+188h+var_158]
0x1800a1ed2  mov     rcx, r15
0x1800a1ed5  call    ??$emplace_back@UScenarioDbLookupPair@Diagnostics@Microsoft@@@?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@QEAAAEAUScenarioDbLookupPair@Diagnostics@Microsoft@@$$QEAU234@@Z; std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::emplace_back<Microsoft::Diagnostics::ScenarioDbLookupPair>(Microsoft::Diagnostics::ScenarioDbLookupPair &&)
0x1800a1eda  add     r14, 10h
0x1800a1ede  jmp     short loc_1800A1E9A
0x1800a1ee0  mov     r15, [rsp+188h+var_140]
0x1800a1ee5  mov     rdx, [r15+38h]
0x1800a1ee9  sub     rdx, [r15+30h]
0x1800a1eed  sar     rdx, 4
0x1800a1ef1  mov     rax, [rsi+100h]
0x1800a1ef8  sub     rax, [rsi+0F8h]
0x1800a1eff  sar     rax, 4
0x1800a1f03  add     rdx, rax
0x1800a1f06  lea     rcx, [r15+30h]
0x1800a1f0a  call    ?reserve@?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@QEAAX_K@Z; std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::reserve(unsigned __int64)
0x1800a1f0f  mov     r14, [rsi+0F8h]
  ... truncated ...
```

# Microsoft::Diagnostics::TransitionDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1800a06d0`
- end: `0x1800a192c`
- name: `?ParseFromXml@TransitionDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `4700`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::TransitionDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18002b318`
- `0x18002cae0`
- `0x18002df00`
- `0x180040558`
- `0x180052240`
- `0x180064e8c`
- `0x1800653d0`
- `0x18008b254`
- `0x18009c8c0`
- `0x18009dec0`
- `0x1800a0558`
- `0x1800a06d0`
- `0x1800a23b0`
- `0x1800a3760`
- `0x1800a37b0`
- `0x1800a6438`
- `0x1800a658c`
- `0x1800afab0`
- `0x1800fc440`
- `0x1801b7bd0`
- `0x1801bbc78`
- `0x1801c90e0`
- `0x18020aac0`
- `0x1802be760`
- `0x1802c3304`
- `0x1802c33dc`
- `0x1802c3670`
- `0x1802e72a8`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a08c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a10bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a115d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1254`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a08c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a10bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a115d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a1254`

## string_xrefs

- `0x1800a078b`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a09b3`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0a5e`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0ae0`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0b2b`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0c66`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0cfe`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0d48`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0e6d`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0ed2`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0f4d`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a11a4`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a1340`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a13c4`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a1491`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a15cb`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a1651`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a171b`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a177a`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a17d5`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a184a`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a1895`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800a0907`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x1800a0fc1`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x1800a12a9`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x1800a1583`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::TransitionDef::ParseFromXml(
        Microsoft::Diagnostics::TransitionDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct _GUID *a3)
{
  struct Microsoft::Diagnostics::XMLFacade *v4; // rsi
  _QWORD *v7; // rdx
  __int64 v8; // rax
  const void *v9; // r9
  _QWORD *v10; // rdi
  _QWORD *v11; // r12
  _QWORD *v12; // rdx
  int v13; // r15d
  _QWORD *v14; // rcx
  unsigned __int64 v15; // rsi
  char *v16; // r8
  int v17; // esi
  __int64 v18; // r8
  const char *v19; // r9
  __int16 v20; // r12
  __int16 v21; // ax
  __int64 v22; // rax
  __int64 v23; // r15
  std::_Ref_count_base *v24; // rdi
  const WCHAR *v25; // rax
  _WORD *v26; // rax
  bool v27; // al
  int v28; // eax
  unsigned int v29; // esi
  unsigned __int8 *v30; // r15
  int v31; // eax
  int v32; // esi
  __int64 v33; // r8
  const char *v34; // r9
  struct _GUID *v35; // r15
  unsigned int Element; // eax
  unsigned int v37; // esi
  Microsoft::Diagnostics::XMLFacade *v38; // r12
  _QWORD *v39; // rdx
  int v40; // esi
  __int64 v41; // r8
  _QWORD *v42; // rcx
  int v43; // esi
  __int64 v44; // r8
  int InnerText; // eax
  __int64 v46; // rsi
  __int64 v47; // r13
  __int128 *v48; // rdx
  int v49; // r12d
  _QWORD *v50; // rcx
  unsigned __int64 v51; // r15
  unsigned __int64 v52; // r8
  __int64 (__fastcall ***v53)(_QWORD); // rcx
  int v54; // esi
  __int64 v55; // rax
  const char *v56; // r9
  __int16 v57; // cx
  int v58; // eax
  int v59; // eax
  __int64 v60; // rsi
  __int64 v61; // r15
  __int128 *v62; // r8
  __int64 (__fastcall ***v63)(_QWORD); // rcx
  char v64; // si
  std::_Ref_count_base *v65; // rax
  const char *v66; // r9
  int v67; // eax
  int v68; // eax
  int v69; // eax
  __int64 v70; // [rsp+20h] [rbp-188h] BYREF
  __int64 v71; // [rsp+28h] [rbp-180h]
  const WCHAR *v72; // [rsp+30h] [rbp-178h] BYREF
  char *v73; // [rsp+38h] [rbp-170h]
  std::_Ref_count_base *v74[2]; // [rsp+40h] [rbp-168h] BYREF
  Microsoft::Diagnostics::XMLFacade *v75; // [rsp+50h] [rbp-158h]
  struct _GUID *v76; // [rsp+58h] [rbp-150h]
  __int128 v77; // [rsp+60h] [rbp-148h] BYREF
  __int128 v78; // [rsp+70h] [rbp-138h] BYREF
  __int128 v79; // [rsp+80h] [rbp-128h] BYREF
  __int64 v80; // [rsp+90h] [rbp-118h] BYREF
  __int128 v81; // [rsp+A0h] [rbp-108h] BYREF
  char v82[16]; // [rsp+B0h] [rbp-F8h] BYREF
  char v83[16]; // [rsp+C0h] [rbp-E8h] BYREF
  char v84[16]; // [rsp+D0h] [rbp-D8h] BYREF
  _QWORD v85[2]; // [rsp+E0h] [rbp-C8h] BYREF
  char *v86; // [rsp+F0h] [rbp-B8h]
  unsigned __int64 v87; // [rsp+F8h] [rbp-B0h]
  _QWORD v88[2]; // [rsp+100h] [rbp-A8h] BYREF
  unsigned __int64 v89; // [rsp+110h] [rbp-98h]
  unsigned __int64 v90; // [rsp+118h] [rbp-90h]
  __int128 v91; // [rsp+120h] [rbp-88h] BYREF
  unsigned __int64 v92; // [rsp+130h] [rbp-78h]
  unsigned __int64 v93; // [rsp+138h] [rbp-70h]
  _BYTE v94[32]; // [rsp+140h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v76 = a3;
  v4 = a2;
  v75 = a2;
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v80, &a3[7], 42);
  std::wstring::wstring(v85);
  v77 = 0;
  *(_OWORD *)v74 = *(_OWORD *)&off_18036CAB8;
  v72 = &Src;
  v73 = (char *)std::_WChar_traits<wchar_t>::length(&Src);
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v72, v74, v85, v70, v71) == 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52423LL,
      v70);
    std::wstring::_Tidy_deallocate(v85);
    return 2277844003LL;
  }
  v7 = v85;
  if ( v87 > 7 )
    v7 = (_QWORD *)v85[0];
  std::wstring::_Assign<wchar_t>((char **)this + 2, v7, v86);
  *((_QWORD *)this + 6) = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((unsigned __int8 *)this + 16);
  v8 = std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(v80);
  std::wstring::_Assign<wchar_t>((char **)(v8 + 8), v9, v86);
  *(_OWORD *)v74 = *(_OWORD *)&off_18036CAF8;
  v72 = &Src;
  v73 = (char *)std::_WChar_traits<wchar_t>::length(&Src);
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v72, v74, v85, v70, v71) == 1 )
  {
    LOBYTE(v70) = 1;
    v20 = 4;
    v24 = (std::_Ref_count_base *)*((_QWORD *)&v77 + 1);
    v23 = v77;
    goto LABEL_35;
  }
  v10 = *(_QWORD **)&a3[17].Data1;
  v11 = *(_QWORD **)a3[17].Data4;
  while ( 1 )
  {
    if ( v10 == v11 )
    {
      v20 = 4;
      v24 = (std::_Ref_count_base *)*((_QWORD *)&v77 + 1);
      v23 = v77;
      goto LABEL_29;
    }
    v12 = v85;
    if ( v87 > 7 )
      v12 = (_QWORD *)v85[0];
    v13 = (int)v86;
    v14 = (_QWORD *)(*v10 + 16LL);
    if ( *(_QWORD *)(*v10 + 40LL) > 7u )
      v14 = (_QWORD *)*v14;
    v15 = *(_QWORD *)(*v10 + 32LL);
    v16 = v86;
    if ( (unsigned __int64)v86 >= v15 )
      v16 = *(char **)(*v10 + 32LL);
    if ( !(unsigned int)_o__wcsnicmp(v14, v12, v16) && (_DWORD)v15 == v13 )
      break;
    v10 += 2;
  }
  v17 = *(unsigned __int8 *)(*v10 + 48LL);
  v18 = (**(__int64 (__fastcall ***)(_QWORD))*v10)(*v10);
  if ( !(_BYTE)v17 )
  {
    v21 = 2;
    goto LABEL_23;
  }
  if ( v17 == 1 )
  {
    v21 = 3;
LABEL_23:
    v20 = 4;
    goto LABEL_24;
  }
  if ( v17 != 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
      v19);
  v20 = 4;
  v21 = 4;
LABEL_24:
  *((_WORD *)this + 28) = v21;
  *(_DWORD *)((char *)this + 58) = *(_DWORD *)((char *)v74 + 2);
  *((_WORD *)this + 31) = HIWORD(v74[0]);
  *((_QWORD *)this + 8) = v18;
  v22 = v10[1];
  if ( v22 )
    _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
  v23 = *v10;
  *(_QWORD *)&v77 = *v10;
  v24 = (std::_Ref_count_base *)v10[1];
  *((_QWORD *)&v77 + 1) = v24;
LABEL_29:
  if ( !v23 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52424LL,
      v70);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    std::wstring::_Tidy_deallocate(v85);
    return 2277844004LL;
  }
  LOBYTE(v70) = 0;
  v4 = v75;
LABEL_35:
  *(_OWORD *)v74 = *(_OWORD *)&off_18036CAC8;
  v72 = &Src;
  v73 = (char *)std::_WChar_traits<wchar_t>::length(&Src);
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v72, v74, v85, v70, v71) == 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52425LL,
      v70);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    std::wstring::_Tidy_deallocate(v85);
    return 2277844005LL;
  }
  v25 = (const WCHAR *)v85;
  if ( v87 > 7 )
    v25 = (const WCHAR *)v85[0];
  v72 = v25;
  v73 = v86;
  if ( (int)Microsoft::Diagnostics::StateDef::ConvertStringToStateOrdinal(&v72, (char *)this + 120) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C5241FLL,
      v70);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    std::wstring::_Tidy_deallocate(v85);
    return 2277843999LL;
  }
  if ( *((_BYTE *)this + 120) == 0xFA )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52426LL,
      v70);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    std::wstring::_Tidy_deallocate(v85);
    return 2277844006LL;
  }
  *(_OWORD *)v74 = *(_OWORD *)&off_18036CAD8;
  v72 = &Src;
  v73 = (char *)std::_WChar_traits<wchar_t>::length(&Src);
  if ( !(unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v72, v74, v85, v70, v71) )
  {
    v26 = v85;
    if ( v87 > 7 )
      v26 = (_WORD *)v85[0];
    v27 = v86 && (*v26 == 84 || *v26 == 49 || *v26 == 116);
    *((_BYTE *)this + 152) = v27;
  }
  *(_OWORD *)v74 = *(_OWORD *)&off_18036CB08;
  v72 = &Src;
  v73 = (char *)std::_WChar_traits<wchar_t>::length(&Src);
  if ( !(unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v72, v74, v85, v70, v71) )
  {
    *(_OWORD *)v74 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, &v81);
    v28 = Microsoft::Diagnostics::TransitionDef::ParseSelectFieldsAttribute(this, v74);
    v29 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x264,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)(unsigned int)v28,
        v70);
      if ( v24 )
        std::_Ref_count_base::_Decref(v24);
LABEL_63:
      std::wstring::_Tidy_deallocate(v85);
      return v29;
    }
    v4 = v75;
  }
  *(_OWORD *)v74 = *(_OWORD *)&off_18036CAE8;
  v72 = &Src;
  v73 = (char *)std::_WChar_traits<wchar_t>::length(&Src);
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v72, v74, v85, v70, v71) )
    goto LABEL_84;
  if ( !*((_WORD *)this + 28) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52427LL,
      v70);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    std::wstring::_Tidy_deallocate(v85);
    return 2277844007LL;
  }
  if ( *(_BYTE *)(v23 + 48) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x276,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52428LL,
      v70);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    std::wstring::_Tidy_deallocate(v85);
    return 2277844008LL;
  }
  *(_OWORD *)v74 = *(_OWORD *)&off_1803867E0;
  v78 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, &v81);
  if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v78, v74) )
    goto LABEL_83;
  *(_OWORD *)v74 = *(_OWORD *)&off_1803867F0;
  v78 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, &v81);
  if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v78, v74) )
  {
    *(_OWORD *)v74 = *(_OWORD *)&off_1803867D0;
    v78 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, &v81);
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v78, v74) )
    {
      *((_BYTE *)this + 153) = 2;
      goto LABEL_84;
    }
    if ( v76[9].Data4[0] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x289,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)0x87C5244DLL,
        v70);
      if ( v24 )
        std::_Ref_count_base::_Decref(v24);
      std::wstring::_Tidy_deallocate(v85);
      return 2277844045LL;
    }
LABEL_83:
    *((_BYTE *)this + 153) = 0;
    goto LABEL_84;
  }
  *((_BYTE *)this + 153) = 1;
LABEL_84:
  if ( v23 )
  {
    if ( *(_BYTE *)(v23 + 48) == 1 )
    {
      if ( *((_BYTE *)this + 121) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29B,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C51030LL,
          v70);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
        std::wstring::_Tidy_deallocate(v85);
        return 2277838896LL;
      }
      v30 = *(unsigned __int8 **)std::static_pointer_cast<Microsoft::Diagnostics::ITriggerDef const,Microsoft::Diagnostics::IScenarioSerializable const>(
                                   v74,
                                   &v77);
      if ( v74[1] )
        std::_Ref_count_base::_Decref(v74[1]);
      v31 = Microsoft::Diagnostics::TimeTriggerDef::OnOwningTransitionParse(
              (Microsoft::Diagnostics::TimeTriggerDef *)v30,
              v76,
              *((_BYTE *)this + 120),
              *((_QWORD *)this + 6));
      v29 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v31,
          v70);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
        goto LABEL_63;
      }
      (*(void (__fastcall **)(unsigned __int8 *, _QWORD))(*(_QWORD *)v30 + 16LL))(v30, 0);
      v32 = v30[48];
      v33 = (**(__int64 (__fastcall ***)(unsigned __int8 *))v30)(v30);
      if ( (_BYTE)v32 )
      {
        if ( v32 == 1 )
        {
          v20 = 3;
        }
        else if ( v32 != 2 )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3A4,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v34);
        }
      }
      else
      {
        v20 = 2;
      }
      *((_WORD *)this + 28) = v20;
      *(_DWORD *)((char *)this + 58) = *(_DWORD *)((char *)v74 + 2);
      *((_WORD *)this + 31) = HIWORD(v74[0]);
      *((_QWORD *)this + 8) = v33;
      v4 = v75;
    }
    v35 = v76;
    if ( (*((_BYTE *)this + 153) & 0xFD) == 0 )
      std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::emplace_back<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const> &>(
        &v76[14],
        &v77);
    if ( (unsigned __int8)(*((_BYTE *)this + 153) - 1) <= 1u )
      std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::emplace_back<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const> &>(
        v35[15].Data4,
        &v77);
  }
  if ( Microsoft::Diagnostics::XMLFacade::IsEmptyElement(v4) )
    goto LABEL_205;
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(v4);
    v37 = Element;
    if ( Element )
      break;
    std::wstring::wstring(v88);
    v38 = v75;
    Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(v75, v88);
    v39 = v88;
    if ( v90 > 7 )
      v39 = (_QWORD *)v88[0];
    v40 = v89;
    v41 = v89;
    if ( v89 >= 6 )
      v41 = 6;
    if ( !(unsigned int)_o__wcsnicmp(L"filter", v39, v41) && v40 == 6 )
    {
      LOBYTE(v70) = 1;
      v79 = *(_OWORD *)&off_18036C508;
      *(_QWORD *)&v78 = &Src;
      *((_QWORD *)&v78 + 1) = std::_WChar_traits<wchar_t>::length(&Src);
      if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(
                           v38,
                           &v78,
                           &v79,
                           v85,
                           v70,
                           v71) != 1 )
      {
        v42 = v85;
        if ( v87 > 7 )
          v42 = (_QWORD *)v85[0];
        v43 = (int)v86;
        v44 = 5;
        if ( (unsigned __int64)v86 <= 5 )
          v44 = (__int64)v86;
        if ( !(unsigned int)_o__wcsnicmp(v42, L"false", v44) )
          LOBYTE(v70) = v43 != 5;
      }
      std::wstring::wstring(&v91);
      InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(v38, &v91);
      v37 = InnerText;
      if ( InnerText >= 0 )
      {
        v46 = *(_QWORD *)v76[12].Data4;
        v47 = *(_QWORD *)&v76[13].Data1;
        while ( 1 )
        {
          if ( v46 == v47 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2EA,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
              (const char *)0x87C52429LL,
              v70);
            std::wstring::_Tidy_deallocate(&v91);
            std::wstring::_Tidy_deallocate(v88);
            if ( v24 )
              std::_Ref_count_base::_Decref(v24);
            std::wstring::_Tidy_deallocate(v85);
            return 2277844009LL;
          }
          v48 = &v91;
          if ( v93 > 7 )
            v48 = (__int128 *)v91;
          v49 = v92;
          v50 = (_QWORD *)(*(_QWORD *)v46 + 24LL);
          if ( *(_QWORD *)(*(_QWORD *)v46 + 48LL) > 7u )
            v50 = (_QWORD *)*v50;
          v51 = *(_QWORD *)(*(_QWORD *)v46 + 40LL);
          v52 = v92;
          if ( v92 >= v51 )
            v52 = *(_QWORD *)(*(_QWORD *)v46 + 40LL);
          if ( !(unsigned int)_o__wcsnicmp(v50, v48, v52) && (_DWORD)v51 == v49 )
            break;
          v46 += 16;
        }
        v53 = *(__int64 (__fastcall ****)(_QWORD))v46;
        v54 = *(unsigned __int16 *)(*(_QWORD *)v46 + 16LL);
        v55 = (**v53)(v53);
        if ( v54 )
        {
          if ( v54 == 1 )
          {
            LOWORD(v72) = 6;
          }
          else
          {
            switch ( v54 )
            {
              case 2:
                v57 = 7;
                break;
              case 3:
                v57 = 8;
                break;
              case 4:
                v57 = 9;
                break;
              case 5:
                v57 = 10;
                break;
              case 6:
                v57 = 11;
                break;
              default:
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x3B5,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                  v56);
            }
            LOWORD(v72) = v57;
          }
        }
        else
        {
          LOWORD(v72) = 5;
        }
        v73 = (char *)v55;
        std::vector<std::pair<bool,Microsoft::Diagnostics::ScenarioDbLookupPair>>::emplace_back<bool &,Microsoft::Diagnostics::ScenarioDbLookupPair>(
          (char *)this + 72,
          &v70,
          &v72);
        v58 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(v75);
        v37 = v58;
        if ( v58 >= 0 )
        {
          std::wstring::_Tidy_deallocate(&v91);
          LOBYTE(v70) = 0;
          v4 = v75;
          goto LABEL_195;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2ED,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v58,
          v70);
        std::wstring::_Tidy_deallocate(&v91);
        std::wstring::_Tidy_deallocate(v88);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D7,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)InnerText,
          v70);
        std::wstring::_Tidy_deallocate(&v91);
        std::wstring::_Tidy_deallocate(v88);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
      }
      goto LABEL_200;
    }
    v79 = *(_OWORD *)std::wstring::operator std::wstring_view(v88, v82);
    v91 = *(_OWORD *)&off_1803867C0;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v91, &v79) )
    {
      std::wstring::wstring(v94);
      v59 = Microsoft::Diagnostics::XMLFacade::GetInnerText(v38, v94);
      v37 = v59;
      if ( v59 >= 0 )
      {
        v60 = *(_QWORD *)v76[24].Data4;
        v61 = *(_QWORD *)&v76[25].Data1;
        while ( 1 )
        {
          if ( v60 == v61 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x304,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
              (const char *)0x87C52607LL,
              v70);
            std::wstring::_Tidy_deallocate(v94);
            std::wstring::_Tidy_deallocate(v88);
            if ( v24 )
              std::_Ref_count_base::_Decref(v24);
            std::wstring::_Tidy_deallocate(v85);
            return 2277844487LL;
          }
          std::wstring::operator std::wstring_view(v94, v83);
          std::wstring::operator std::wstring_view(*(_QWORD *)v60 + 16LL, &v81);
          v91 = *v62;
          v79 = v81;
          if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v79, &v91) )
            break;
          v60 += 16;
        }
        v63 = *(__int64 (__fastcall ****)(_QWORD))v60;
        v64 = *(_BYTE *)(*(_QWORD *)v60 + 80LL);
        v65 = (std::_Ref_count_base *)(**v63)(v63);
        if ( v64 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3D8,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v66);
        LOWORD(v74[0]) = 52;
        v74[1] = v65;
        std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::emplace_back<Microsoft::Diagnostics::ScenarioDbLookupPair>(
          (char *)this + 96,
          v74);
        v67 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(v38);
        v37 = v67;
        if ( v67 >= 0 )
        {
          std::wstring::_Tidy_deallocate(v94);
          v4 = v75;
          goto LABEL_195;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x307,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v67,
          v70);
        std::wstring::_Tidy_deallocate(v94);
        std::wstring::_Tidy_deallocate(v88);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2F2,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v59,
          v70);
        std::wstring::_Tidy_deallocate(v94);
        std::wstring::_Tidy_deallocate(v88);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
      }
      goto LABEL_200;
    }
    v91 = *(_OWORD *)std::wstring::operator std::wstring_view(v88, v84);
    v79 = *(_OWORD *)&off_1803867B0;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v79, &v91) )
    {
      if ( v76[9].Data4[0] )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x315,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52407LL,
          v70);
        std::wstring::_Tidy_deallocate(v88);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
        std::wstring::_Tidy_deallocate(v85);
        return 2277843975LL;
      }
      v69 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(v38);
      v37 = v69;
      if ( v69 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x318,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v69,
          v70);
        std::wstring::_Tidy_deallocate(v88);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
        goto LABEL_200;
      }
    }
    else
    {
      v4 = v38;
      if ( Microsoft::Diagnostics::XMLFacade::IsEmptyElement(v38) )
        goto LABEL_195;
      v68 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(v38);
      v37 = v68;
      if ( v68 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v68,
          v70);
        std::wstring::_Tidy_deallocate(v88);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
LABEL_200:
        std::wstring::_Tidy_deallocate(v85);
        return v37;
      }
    }
    v4 = v38;
LABEL_195:
    std::wstring::_Tidy_deallocate(v88);
  }
  if ( (int)(Element + 0x80000000) >= 0 && Element != -2147024270 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)Element,
      v70);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    goto LABEL_200;
  }
  if ( (_BYTE)v70 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x325,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C5242ALL,
      v70);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    std::wstring::_Tidy_deallocate(v85);
    return 2277844010LL;
  }
LABEL_205:
  (*(void (__fastcall **)(Microsoft::Diagnostics::TransitionDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
  std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v80);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  std::wstring::_Tidy_deallocate(v85);
  return 0;
}

```

## disassembly

```asm
0x1800a06d0  push    rbx
0x1800a06d2  push    rsi
0x1800a06d3  push    rdi
0x1800a06d4  push    r12
0x1800a06d6  push    r13
0x1800a06d8  push    r14
0x1800a06da  push    r15
0x1800a06dc  sub     rsp, 170h
0x1800a06e3  mov     rax, cs:__security_cookie
0x1800a06ea  xor     rax, rsp
0x1800a06ed  mov     [rsp+1A8h+var_48], rax
0x1800a06f5  mov     r15, r8
0x1800a06f8  mov     [rsp+1A8h+var_150], r8
0x1800a06fd  mov     rsi, rdx
0x1800a0700  mov     [rsp+1A8h+var_158], rdx
0x1800a0705  mov     r14, rcx
0x1800a0708  mov     r8d, 2Ah ; '*'
0x1800a070e  lea     rdx, [r15+70h]
0x1800a0712  lea     rcx, [rsp+1A8h+var_118]
0x1800a071a  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1800a071f  lea     rcx, [rsp+1A8h+var_C8]; void *
0x1800a0727  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a072c  nop
0x1800a072d  xorps   xmm0, xmm0
0x1800a0730  movdqu  [rsp+1A8h+var_148], xmm0
0x1800a0736  movups  xmm0, xmmword ptr cs:off_18036CAB8; "name"
0x1800a073d  movdqu  xmmword ptr [rsp+1A8h+var_168], xmm0
0x1800a0743  lea     rdi, Src
0x1800a074a  mov     [rsp+1A8h+var_178], rdi
0x1800a074f  mov     rcx, rdi
0x1800a0752  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a0757  mov     [rsp+1A8h+var_170], rax
0x1800a075c  lea     r9, [rsp+1A8h+var_C8]
0x1800a0764  lea     r8, [rsp+1A8h+var_168]
0x1800a0769  lea     rdx, [rsp+1A8h+var_178]
0x1800a076e  mov     rcx, rsi
0x1800a0771  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a0776  cmp     eax, 1
0x1800a0779  jnz     short loc_1800A07B1
0x1800a077b  mov     rcx, [rsp+1A8h]; this
0x1800a0783  mov     ebx, 87C52423h
0x1800a0788  mov     r9d, ebx; char *
0x1800a078b  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x1800a0792  mov     edx, 223h; void *
0x1800a0797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a079c  nop
0x1800a079d  lea     rcx, [rsp+1A8h+var_C8]
0x1800a07a5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a07aa  mov     eax, ebx
0x1800a07ac  jmp     loc_1800A1908
0x1800a07b1  lea     rdx, [rsp+1A8h+var_C8]
0x1800a07b9  mov     r13d, 7
0x1800a07bf  cmp     [rsp+1A8h+var_B0], r13
0x1800a07c7  cmova   rdx, [rsp+1A8h+var_C8]
0x1800a07d0  mov     r8, [rsp+1A8h+var_B8]
0x1800a07d8  lea     rcx, [r14+10h]
0x1800a07dc  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800a07e1  lea     rcx, [r14+10h]; unsigned __int8 *
0x1800a07e5  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$00@std@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x1800a07ea  mov     [r14+30h], rax
0x1800a07ee  lea     r9, [rsp+1A8h+var_C8]
0x1800a07f6  cmp     [rsp+1A8h+var_B0], r13
0x1800a07fe  cmova   r9, [rsp+1A8h+var_C8]
0x1800a0807  mov     rcx, [rsp+1A8h+var_118]
0x1800a080f  call    ?top@?$stack@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$deque@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@@2@@2@@std@@QEAAAEAV?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@2@XZ; std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(void)
0x1800a0814  lea     rcx, [rax+8]
0x1800a0818  mov     r8, [rsp+1A8h+var_B8]
0x1800a0820  mov     rdx, r9
0x1800a0823  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800a0828  movups  xmm0, xmmword ptr cs:off_18036CAF8; "event"
0x1800a082f  movdqu  xmmword ptr [rsp+1A8h+var_168], xmm0
0x1800a0835  mov     [rsp+1A8h+var_178], rdi
0x1800a083a  mov     rcx, rdi
0x1800a083d  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a0842  mov     [rsp+1A8h+var_170], rax
0x1800a0847  lea     r9, [rsp+1A8h+var_C8]
0x1800a084f  lea     r8, [rsp+1A8h+var_168]
0x1800a0854  lea     rdx, [rsp+1A8h+var_178]
0x1800a0859  mov     rcx, rsi
0x1800a085c  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a0861  xor     ebx, ebx
0x1800a0863  cmp     eax, 1
0x1800a0866  jz      loc_1800A09F2
0x1800a086c  mov     rdi, [r15+110h]
0x1800a0873  mov     r12, [r15+118h]
0x1800a087a  cmp     rdi, r12
0x1800a087d  jz      loc_1800A0989
0x1800a0883  lea     rdx, [rsp+1A8h+var_C8]
0x1800a088b  cmp     [rsp+1A8h+var_B0], r13
0x1800a0893  cmova   rdx, [rsp+1A8h+var_C8]
0x1800a089c  mov     r15, [rsp+1A8h+var_B8]
0x1800a08a4  mov     rsi, [rdi]
0x1800a08a7  lea     rcx, [rsi+10h]
0x1800a08ab  cmp     [rsi+28h], r13
0x1800a08af  jbe     short loc_1800A08B4
0x1800a08b1  mov     rcx, [rcx]
0x1800a08b4  mov     rsi, [rsi+20h]
0x1800a08b8  mov     r8, r15
0x1800a08bb  cmp     r15, rsi
0x1800a08be  cmovnb  r8, rsi
0x1800a08c2  call    cs:__imp__o__wcsnicmp
0x1800a08c8  test    eax, eax
0x1800a08ca  jnz     loc_1800A0980
0x1800a08d0  cmp     esi, r15d
0x1800a08d3  jnz     loc_1800A0980
0x1800a08d9  mov     rcx, [rdi]
0x1800a08dc  movzx   esi, byte ptr [rcx+30h]
0x1800a08e0  mov     rax, [rcx]
0x1800a08e3  mov     rax, [rax]
0x1800a08e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a08eb  mov     r8, rax
0x1800a08ee  mov     edx, esi
0x1800a08f0  test    sil, sil
0x1800a08f3  jz      short loc_1800A0935
0x1800a08f5  sub     edx, 1
0x1800a08f8  jz      short loc_1800A092A
0x1800a08fa  cmp     edx, 1
0x1800a08fd  jz      short loc_1800A0919
0x1800a08ff  mov     rcx, [rsp+1A8h]; this
0x1800a0907  lea     r8, aOnecoreBaseTel_14; "onecore\\base\\telemetry\\utc\\service"...
0x1800a090e  mov     edx, 3A4h; void *
0x1800a0913  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800a0919  mov     r12d, 4
0x1800a091f  movzx   eax, r12w
0x1800a0923  lea     r13d, [r12-2]
0x1800a0928  jmp     short loc_1800A0945
0x1800a092a  mov     eax, 3
0x1800a092f  lea     r13d, [rax-1]
0x1800a0933  jmp     short loc_1800A093F
0x1800a0935  mov     r13d, 2
0x1800a093b  movzx   eax, r13w
0x1800a093f  mov     r12d, 4
0x1800a0945  mov     [r14+38h], ax
0x1800a094a  mov     eax, dword ptr [rsp+1A8h+var_168+2]
0x1800a094e  mov     [r14+3Ah], eax
0x1800a0952  movzx   eax, word ptr [rsp+1A8h+var_168+6]
0x1800a0957  mov     [r14+3Eh], ax
0x1800a095c  mov     [r14+40h], r8
0x1800a0960  mov     rax, [rdi+8]
0x1800a0964  test    rax, rax
0x1800a0967  jz      short loc_1800A096D
0x1800a0969  lock inc dword ptr [rax+8]
0x1800a096d  mov     r15, [rdi]
0x1800a0970  mov     qword ptr [rsp+1A8h+var_148], r15
0x1800a0975  mov     rdi, [rdi+8]
0x1800a0979  mov     qword ptr [rsp+1A8h+var_148+8], rdi
0x1800a097e  jmp     short loc_1800A099E
0x1800a0980  add     rdi, 10h
0x1800a0984  jmp     loc_1800A087A
0x1800a0989  mov     r12d, 4
0x1800a098f  lea     r13d, [r12-2]
0x1800a0994  mov     rdi, qword ptr [rsp+1A8h+var_148+8]
0x1800a0999  mov     r15, qword ptr [rsp+1A8h+var_148]
0x1800a099e  test    r15, r15
0x1800a09a1  jnz     short loc_1800A09E7
0x1800a09a3  mov     rcx, [rsp+1A8h]; this
0x1800a09ab  mov     esi, 87C52424h
0x1800a09b0  mov     r9d, esi; char *
0x1800a09b3  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x1800a09ba  mov     edx, 23Dh; void *
0x1800a09bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a09c4  nop
0x1800a09c5  test    rdi, rdi
0x1800a09c8  jz      short loc_1800A09D3
0x1800a09ca  mov     rcx, rdi; this
0x1800a09cd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a09d2  nop
0x1800a09d3  lea     rcx, [rsp+1A8h+var_C8]
0x1800a09db  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a09e0  mov     eax, esi
0x1800a09e2  jmp     loc_1800A1908
0x1800a09e7  mov     byte ptr [rsp+1A8h+var_188], bl
0x1800a09eb  mov     rsi, [rsp+1A8h+var_158]
0x1800a09f0  jmp     short loc_1800A0A0C
0x1800a09f2  mov     byte ptr [rsp+1A8h+var_188], 1; int
0x1800a09f7  mov     r12d, 4
0x1800a09fd  lea     r13d, [r12-2]
0x1800a0a02  mov     rdi, qword ptr [rsp+1A8h+var_148+8]
0x1800a0a07  mov     r15, qword ptr [rsp+1A8h+var_148]
0x1800a0a0c  movups  xmm0, xmmword ptr cs:off_18036CAC8; "target"
0x1800a0a13  movdqu  xmmword ptr [rsp+1A8h+var_168], xmm0
0x1800a0a19  lea     rcx, Src
0x1800a0a20  mov     [rsp+1A8h+var_178], rcx
0x1800a0a25  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a0a2a  mov     [rsp+1A8h+var_170], rax
0x1800a0a2f  lea     r9, [rsp+1A8h+var_C8]
0x1800a0a37  lea     r8, [rsp+1A8h+var_168]
0x1800a0a3c  lea     rdx, [rsp+1A8h+var_178]
0x1800a0a41  mov     rcx, rsi
0x1800a0a44  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a0a49  cmp     eax, 1
0x1800a0a4c  jnz     short loc_1800A0A92
0x1800a0a4e  mov     rcx, [rsp+1A8h]; this
0x1800a0a56  mov     esi, 87C52425h
0x1800a0a5b  mov     r9d, esi; char *
0x1800a0a5e  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x1800a0a65  mov     edx, 249h; void *
0x1800a0a6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0a6f  nop
0x1800a0a70  test    rdi, rdi
0x1800a0a73  jz      short loc_1800A0A7E
0x1800a0a75  mov     rcx, rdi; this
0x1800a0a78  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a0a7d  nop
0x1800a0a7e  lea     rcx, [rsp+1A8h+var_C8]
0x1800a0a86  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a0a8b  mov     eax, esi
0x1800a0a8d  jmp     loc_1800A1908
0x1800a0a92  lea     rax, [rsp+1A8h+var_C8]
0x1800a0a9a  cmp     [rsp+1A8h+var_B0], 7
0x1800a0aa3  cmova   rax, [rsp+1A8h+var_C8]
0x1800a0aac  mov     [rsp+1A8h+var_178], rax
0x1800a0ab1  mov     rax, [rsp+1A8h+var_B8]
0x1800a0ab9  mov     [rsp+1A8h+var_170], rax
0x1800a0abe  lea     rdx, [r14+78h]
0x1800a0ac2  lea     rcx, [rsp+1A8h+var_178]
0x1800a0ac7  call    ?ConvertStringToStateOrdinal@StateDef@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAE@Z; Microsoft::Diagnostics::StateDef::ConvertStringToStateOrdinal(std::wstring_view,uchar &)
0x1800a0acc  test    eax, eax
0x1800a0ace  jns     short loc_1800A0B14
0x1800a0ad0  mov     rcx, [rsp+1A8h]; this
0x1800a0ad8  mov     esi, 87C5241Fh
0x1800a0add  mov     r9d, esi; char *
0x1800a0ae0  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x1800a0ae7  mov     edx, 24Fh; void *
0x1800a0aec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0af1  nop
0x1800a0af2  test    rdi, rdi
0x1800a0af5  jz      short loc_1800A0B00
0x1800a0af7  mov     rcx, rdi; this
0x1800a0afa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a0aff  nop
0x1800a0b00  lea     rcx, [rsp+1A8h+var_C8]
0x1800a0b08  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a0b0d  mov     eax, esi
0x1800a0b0f  jmp     loc_1800A1908
0x1800a0b14  cmp     byte ptr [r14+78h], 0FAh
0x1800a0b19  jnz     short loc_1800A0B5F
0x1800a0b1b  mov     rcx, [rsp+1A8h]; this
0x1800a0b23  mov     esi, 87C52426h
0x1800a0b28  mov     r9d, esi; char *
0x1800a0b2b  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x1800a0b32  mov     edx, 255h; void *
0x1800a0b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0b3c  nop
0x1800a0b3d  test    rdi, rdi
0x1800a0b40  jz      short loc_1800A0B4B
0x1800a0b42  mov     rcx, rdi; this
0x1800a0b45  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a0b4a  nop
0x1800a0b4b  lea     rcx, [rsp+1A8h+var_C8]
0x1800a0b53  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a0b58  mov     eax, esi
0x1800a0b5a  jmp     loc_1800A1908
0x1800a0b5f  movups  xmm0, xmmword ptr cs:off_18036CAD8; "uploadtrigger"
0x1800a0b66  movdqu  xmmword ptr [rsp+1A8h+var_168], xmm0
0x1800a0b6c  lea     rax, Src
0x1800a0b73  mov     [rsp+1A8h+var_178], rax
0x1800a0b78  mov     rcx, rax
0x1800a0b7b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a0b80  mov     [rsp+1A8h+var_170], rax
0x1800a0b85  lea     r9, [rsp+1A8h+var_C8]
0x1800a0b8d  lea     r8, [rsp+1A8h+var_168]
0x1800a0b92  lea     rdx, [rsp+1A8h+var_178]
0x1800a0b97  mov     rcx, rsi
0x1800a0b9a  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a0b9f  test    eax, eax
0x1800a0ba1  jnz     short loc_1800A0BE6
0x1800a0ba3  lea     rax, [rsp+1A8h+var_C8]
0x1800a0bab  cmp     [rsp+1A8h+var_B0], 7
0x1800a0bb4  cmova   rax, [rsp+1A8h+var_C8]
0x1800a0bbd  cmp     [rsp+1A8h+var_B8], rbx
0x1800a0bc5  jz      short loc_1800A0BDD
0x1800a0bc7  cmp     word ptr [rax], 54h ; 'T'
0x1800a0bcb  jz      short loc_1800A0BD9
0x1800a0bcd  cmp     word ptr [rax], 31h ; '1'
0x1800a0bd1  jz      short loc_1800A0BD9
0x1800a0bd3  cmp     word ptr [rax], 74h ; 't'
0x1800a0bd7  jnz     short loc_1800A0BDD
0x1800a0bd9  mov     al, 1
0x1800a0bdb  jmp     short loc_1800A0BDF
0x1800a0bdd  mov     al, bl
0x1800a0bdf  mov     [r14+98h], al
0x1800a0be6  movups  xmm0, xmmword ptr cs:off_18036CB08; "triggerfields"
0x1800a0bed  movdqu  xmmword ptr [rsp+1A8h+var_168], xmm0
0x1800a0bf3  lea     rax, Src
0x1800a0bfa  mov     [rsp+1A8h+var_178], rax
0x1800a0bff  mov     rcx, rax
0x1800a0c02  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a0c07  mov     [rsp+1A8h+var_170], rax
0x1800a0c0c  lea     r9, [rsp+1A8h+var_C8]
0x1800a0c14  lea     r8, [rsp+1A8h+var_168]
0x1800a0c19  lea     rdx, [rsp+1A8h+var_178]
0x1800a0c1e  mov     rcx, rsi
0x1800a0c21  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a0c26  test    eax, eax
0x1800a0c28  jnz     short loc_1800A0C9F
0x1800a0c2a  lea     rdx, [rsp+1A8h+var_108]
0x1800a0c32  lea     rcx, [rsp+1A8h+var_C8]
0x1800a0c3a  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800a0c3f  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```

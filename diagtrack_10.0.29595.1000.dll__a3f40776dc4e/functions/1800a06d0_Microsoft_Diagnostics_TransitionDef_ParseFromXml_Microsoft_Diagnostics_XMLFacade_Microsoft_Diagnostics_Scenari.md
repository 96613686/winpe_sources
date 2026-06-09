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
  __int64 v8; // rdx
  __int64 v9; // r8
  _QWORD *v10; // r9
  __int64 v11; // rax
  __int64 v12; // r9
  _QWORD *v13; // rdi
  _QWORD *v14; // r12
  _QWORD *v15; // rdx
  int v16; // r15d
  _QWORD *v17; // rcx
  unsigned __int64 v18; // rsi
  unsigned __int64 v19; // r8
  int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int16 v23; // r12
  __int16 v24; // ax
  __int64 v25; // rax
  __int64 v26; // r15
  std::_Ref_count_base *v27; // rdi
  const WCHAR *v28; // rax
  _WORD *v29; // rax
  bool v30; // al
  int v31; // eax
  unsigned int v32; // esi
  unsigned __int8 *v33; // r15
  int v34; // eax
  int v35; // esi
  __int64 v36; // r8
  const char *v37; // r9
  struct _GUID *v38; // r15
  unsigned int Element; // eax
  unsigned int v40; // esi
  Microsoft::Diagnostics::XMLFacade *v41; // r12
  _QWORD *v42; // rdx
  int v43; // esi
  __int64 v44; // r8
  _QWORD *v45; // rcx
  int v46; // esi
  __int64 v47; // r8
  int InnerText; // eax
  __int64 v49; // rsi
  __int64 v50; // r13
  __int128 *v51; // rdx
  int v52; // r12d
  _QWORD *v53; // rcx
  unsigned __int64 v54; // r15
  unsigned __int64 v55; // r8
  __int64 (__fastcall ***v56)(_QWORD); // rcx
  int v57; // esi
  __int64 v58; // rax
  const char *v59; // r9
  __int16 v60; // cx
  int v61; // eax
  int v62; // eax
  __int64 v63; // rsi
  __int64 v64; // r15
  __int128 *v65; // r8
  __int64 (__fastcall ***v66)(_QWORD); // rcx
  char v67; // si
  std::_Ref_count_base *v68; // rax
  const char *v69; // r9
  int v70; // eax
  int v71; // eax
  int v72; // eax
  int v73[4]; // [rsp+20h] [rbp-188h] BYREF
  const WCHAR *v74; // [rsp+30h] [rbp-178h] BYREF
  __int64 v75; // [rsp+38h] [rbp-170h]
  std::_Ref_count_base *v76[2]; // [rsp+40h] [rbp-168h] BYREF
  Microsoft::Diagnostics::XMLFacade *v77; // [rsp+50h] [rbp-158h]
  struct _GUID *v78; // [rsp+58h] [rbp-150h]
  __int128 v79; // [rsp+60h] [rbp-148h] BYREF
  __int128 v80; // [rsp+70h] [rbp-138h] BYREF
  __int128 v81; // [rsp+80h] [rbp-128h] BYREF
  __int64 v82; // [rsp+90h] [rbp-118h] BYREF
  __int128 v83; // [rsp+A0h] [rbp-108h] BYREF
  char v84[16]; // [rsp+B0h] [rbp-F8h] BYREF
  char v85[16]; // [rsp+C0h] [rbp-E8h] BYREF
  char v86[16]; // [rsp+D0h] [rbp-D8h] BYREF
  _QWORD v87[2]; // [rsp+E0h] [rbp-C8h] BYREF
  unsigned __int64 v88; // [rsp+F0h] [rbp-B8h]
  unsigned __int64 v89; // [rsp+F8h] [rbp-B0h]
  _QWORD v90[2]; // [rsp+100h] [rbp-A8h] BYREF
  unsigned __int64 v91; // [rsp+110h] [rbp-98h]
  unsigned __int64 v92; // [rsp+118h] [rbp-90h]
  __int128 v93; // [rsp+120h] [rbp-88h] BYREF
  unsigned __int64 v94; // [rsp+130h] [rbp-78h]
  unsigned __int64 v95; // [rsp+138h] [rbp-70h]
  _BYTE v96[32]; // [rsp+140h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v78 = a3;
  v4 = a2;
  v77 = a2;
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v82, &a3[7], 42);
  std::wstring::wstring(v87);
  v79 = 0;
  *(_OWORD *)v76 = *(_OWORD *)&off_18036CAB8;
  v74 = &Src;
  v75 = std::_WChar_traits<wchar_t>::length(&Src);
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v74, v76, v87) == 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52423LL,
      v73[0]);
    std::wstring::_Tidy_deallocate(v87);
    return 2277844003LL;
  }
  v7 = v87;
  if ( v89 > 7 )
    v7 = (_QWORD *)v87[0];
  std::wstring::_Assign<wchar_t>((char *)this + 16, v7, v88);
  *((_QWORD *)this + 6) = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((unsigned __int8 *)this + 16);
  v10 = v87;
  if ( v89 > 7 )
    v10 = (_QWORD *)v87[0];
  v11 = std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(v82, v8, v9, v10);
  std::wstring::_Assign<wchar_t>(v11 + 8, v12, v88);
  *(_OWORD *)v76 = *(_OWORD *)&off_18036CAF8;
  v74 = &Src;
  v75 = std::_WChar_traits<wchar_t>::length(&Src);
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v74, v76, v87) == 1 )
  {
    LOBYTE(v73[0]) = 1;
    v23 = 4;
    v27 = (std::_Ref_count_base *)*((_QWORD *)&v79 + 1);
    v26 = v79;
    goto LABEL_37;
  }
  v13 = *(_QWORD **)&a3[17].Data1;
  v14 = *(_QWORD **)a3[17].Data4;
  while ( 1 )
  {
    if ( v13 == v14 )
    {
      v23 = 4;
      v27 = (std::_Ref_count_base *)*((_QWORD *)&v79 + 1);
      v26 = v79;
      goto LABEL_31;
    }
    v15 = v87;
    if ( v89 > 7 )
      v15 = (_QWORD *)v87[0];
    v16 = v88;
    v17 = (_QWORD *)(*v13 + 16LL);
    if ( *(_QWORD *)(*v13 + 40LL) > 7u )
      v17 = (_QWORD *)*v17;
    v18 = *(_QWORD *)(*v13 + 32LL);
    v19 = v88;
    if ( v88 >= v18 )
      v19 = *(_QWORD *)(*v13 + 32LL);
    if ( !(unsigned int)_o__wcsnicmp(v17, v15, v19) && (_DWORD)v18 == v16 )
      break;
    v13 += 2;
  }
  v20 = *(unsigned __int8 *)(*v13 + 48LL);
  v21 = (**(__int64 (__fastcall ***)(_QWORD))*v13)(*v13);
  if ( !(_BYTE)v20 )
  {
    v24 = 2;
    goto LABEL_25;
  }
  if ( v20 == 1 )
  {
    v24 = 3;
LABEL_25:
    v23 = 4;
    goto LABEL_26;
  }
  if ( v20 != 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
      v22);
  v23 = 4;
  v24 = 4;
LABEL_26:
  *((_WORD *)this + 28) = v24;
  *(_DWORD *)((char *)this + 58) = *(_DWORD *)((char *)v76 + 2);
  *((_WORD *)this + 31) = HIWORD(v76[0]);
  *((_QWORD *)this + 8) = v21;
  v25 = v13[1];
  if ( v25 )
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
  v26 = *v13;
  *(_QWORD *)&v79 = *v13;
  v27 = (std::_Ref_count_base *)v13[1];
  *((_QWORD *)&v79 + 1) = v27;
LABEL_31:
  if ( !v26 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52424LL,
      v73[0]);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    std::wstring::_Tidy_deallocate(v87);
    return 2277844004LL;
  }
  LOBYTE(v73[0]) = 0;
  v4 = v77;
LABEL_37:
  *(_OWORD *)v76 = *(_OWORD *)&off_18036CAC8;
  v74 = &Src;
  v75 = std::_WChar_traits<wchar_t>::length(&Src);
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v74, v76, v87) == 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52425LL,
      v73[0]);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    std::wstring::_Tidy_deallocate(v87);
    return 2277844005LL;
  }
  v28 = (const WCHAR *)v87;
  if ( v89 > 7 )
    v28 = (const WCHAR *)v87[0];
  v74 = v28;
  v75 = v88;
  if ( (int)Microsoft::Diagnostics::StateDef::ConvertStringToStateOrdinal(&v74, (char *)this + 120) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C5241FLL,
      v73[0]);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    std::wstring::_Tidy_deallocate(v87);
    return 2277843999LL;
  }
  if ( *((_BYTE *)this + 120) == 0xFA )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52426LL,
      v73[0]);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    std::wstring::_Tidy_deallocate(v87);
    return 2277844006LL;
  }
  *(_OWORD *)v76 = *(_OWORD *)&off_18036CAD8;
  v74 = &Src;
  v75 = std::_WChar_traits<wchar_t>::length(&Src);
  if ( !(unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v74, v76, v87) )
  {
    v29 = v87;
    if ( v89 > 7 )
      v29 = (_WORD *)v87[0];
    v30 = v88 && (*v29 == 84 || *v29 == 49 || *v29 == 116);
    *((_BYTE *)this + 152) = v30;
  }
  *(_OWORD *)v76 = *(_OWORD *)&off_18036CB08;
  v74 = &Src;
  v75 = std::_WChar_traits<wchar_t>::length(&Src);
  if ( !(unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v74, v76, v87) )
  {
    *(_OWORD *)v76 = *(_OWORD *)std::wstring::operator std::wstring_view(v87, &v83);
    v31 = Microsoft::Diagnostics::TransitionDef::ParseSelectFieldsAttribute(this, v76);
    v32 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x264,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)(unsigned int)v31,
        v73[0]);
      if ( v27 )
        std::_Ref_count_base::_Decref(v27);
LABEL_65:
      std::wstring::_Tidy_deallocate(v87);
      return v32;
    }
    v4 = v77;
  }
  *(_OWORD *)v76 = *(_OWORD *)&off_18036CAE8;
  v74 = &Src;
  v75 = std::_WChar_traits<wchar_t>::length(&Src);
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v4, &v74, v76, v87) )
    goto LABEL_86;
  if ( !*((_WORD *)this + 28) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52427LL,
      v73[0]);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    std::wstring::_Tidy_deallocate(v87);
    return 2277844007LL;
  }
  if ( *(_BYTE *)(v26 + 48) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x276,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52428LL,
      v73[0]);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    std::wstring::_Tidy_deallocate(v87);
    return 2277844008LL;
  }
  *(_OWORD *)v76 = *(_OWORD *)&off_1803867D0;
  v80 = *(_OWORD *)std::wstring::operator std::wstring_view(v87, &v83);
  if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v80, v76) )
    goto LABEL_85;
  *(_OWORD *)v76 = *(_OWORD *)&off_1803867E0;
  v80 = *(_OWORD *)std::wstring::operator std::wstring_view(v87, &v83);
  if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v80, v76) )
  {
    *(_OWORD *)v76 = *(_OWORD *)&off_1803867F0;
    v80 = *(_OWORD *)std::wstring::operator std::wstring_view(v87, &v83);
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v80, v76) )
    {
      *((_BYTE *)this + 153) = 2;
      goto LABEL_86;
    }
    if ( v78[9].Data4[0] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x289,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)0x87C5244DLL,
        v73[0]);
      if ( v27 )
        std::_Ref_count_base::_Decref(v27);
      std::wstring::_Tidy_deallocate(v87);
      return 2277844045LL;
    }
LABEL_85:
    *((_BYTE *)this + 153) = 0;
    goto LABEL_86;
  }
  *((_BYTE *)this + 153) = 1;
LABEL_86:
  if ( v26 )
  {
    if ( *(_BYTE *)(v26 + 48) == 1 )
    {
      if ( *((_BYTE *)this + 121) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29B,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C51030LL,
          v73[0]);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
        std::wstring::_Tidy_deallocate(v87);
        return 2277838896LL;
      }
      v33 = *(unsigned __int8 **)std::static_pointer_cast<Microsoft::Diagnostics::ITriggerDef const,Microsoft::Diagnostics::IScenarioSerializable const>(
                                   v76,
                                   &v79);
      if ( v76[1] )
        std::_Ref_count_base::_Decref(v76[1]);
      v34 = Microsoft::Diagnostics::TimeTriggerDef::OnOwningTransitionParse(
              (Microsoft::Diagnostics::TimeTriggerDef *)v33,
              v78,
              *((_BYTE *)this + 120),
              *((_QWORD *)this + 6));
      v32 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v34,
          v73[0]);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
        goto LABEL_65;
      }
      (*(void (__fastcall **)(unsigned __int8 *, _QWORD))(*(_QWORD *)v33 + 16LL))(v33, 0);
      v35 = v33[48];
      v36 = (**(__int64 (__fastcall ***)(unsigned __int8 *))v33)(v33);
      if ( (_BYTE)v35 )
      {
        if ( v35 == 1 )
        {
          v23 = 3;
        }
        else if ( v35 != 2 )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3A4,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v37);
        }
      }
      else
      {
        v23 = 2;
      }
      *((_WORD *)this + 28) = v23;
      *(_DWORD *)((char *)this + 58) = *(_DWORD *)((char *)v76 + 2);
      *((_WORD *)this + 31) = HIWORD(v76[0]);
      *((_QWORD *)this + 8) = v36;
      v4 = v77;
    }
    v38 = v78;
    if ( (*((_BYTE *)this + 153) & 0xFD) == 0 )
      std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::emplace_back<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const> &>(
        &v78[14],
        &v79);
    if ( (unsigned __int8)(*((_BYTE *)this + 153) - 1) <= 1u )
      std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::emplace_back<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const> &>(
        v38[15].Data4,
        &v79);
  }
  if ( Microsoft::Diagnostics::XMLFacade::IsEmptyElement(v4) )
    goto LABEL_207;
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(v4);
    v40 = Element;
    if ( Element )
      break;
    std::wstring::wstring(v90);
    v41 = v77;
    Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(v77, v90);
    v42 = v90;
    if ( v92 > 7 )
      v42 = (_QWORD *)v90[0];
    v43 = v91;
    v44 = v91;
    if ( v91 >= 6 )
      v44 = 6;
    if ( !(unsigned int)_o__wcsnicmp(L"filter", v42, v44) && v43 == 6 )
    {
      LOBYTE(v73[0]) = 1;
      v81 = *(_OWORD *)&off_18036C508;
      *(_QWORD *)&v80 = &Src;
      *((_QWORD *)&v80 + 1) = std::_WChar_traits<wchar_t>::length(&Src);
      if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(v41, &v80, &v81, v87) != 1 )
      {
        v45 = v87;
        if ( v89 > 7 )
          v45 = (_QWORD *)v87[0];
        v46 = v88;
        v47 = 5;
        if ( v88 <= 5 )
          v47 = v88;
        if ( !(unsigned int)_o__wcsnicmp(v45, L"false", v47) )
          LOBYTE(v73[0]) = v46 != 5;
      }
      std::wstring::wstring(&v93);
      InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(v41, &v93);
      v40 = InnerText;
      if ( InnerText >= 0 )
      {
        v49 = *(_QWORD *)v78[12].Data4;
        v50 = *(_QWORD *)&v78[13].Data1;
        while ( 1 )
        {
          if ( v49 == v50 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2EA,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
              (const char *)0x87C52429LL,
              v73[0]);
            std::wstring::_Tidy_deallocate(&v93);
            std::wstring::_Tidy_deallocate(v90);
            if ( v27 )
              std::_Ref_count_base::_Decref(v27);
            std::wstring::_Tidy_deallocate(v87);
            return 2277844009LL;
          }
          v51 = &v93;
          if ( v95 > 7 )
            v51 = (__int128 *)v93;
          v52 = v94;
          v53 = (_QWORD *)(*(_QWORD *)v49 + 24LL);
          if ( *(_QWORD *)(*(_QWORD *)v49 + 48LL) > 7u )
            v53 = (_QWORD *)*v53;
          v54 = *(_QWORD *)(*(_QWORD *)v49 + 40LL);
          v55 = v94;
          if ( v94 >= v54 )
            v55 = *(_QWORD *)(*(_QWORD *)v49 + 40LL);
          if ( !(unsigned int)_o__wcsnicmp(v53, v51, v55) && (_DWORD)v54 == v52 )
            break;
          v49 += 16;
        }
        v56 = *(__int64 (__fastcall ****)(_QWORD))v49;
        v57 = *(unsigned __int16 *)(*(_QWORD *)v49 + 16LL);
        v58 = (**v56)(v56);
        if ( v57 )
        {
          if ( v57 == 1 )
          {
            LOWORD(v74) = 6;
          }
          else
          {
            switch ( v57 )
            {
              case 2:
                v60 = 7;
                break;
              case 3:
                v60 = 8;
                break;
              case 4:
                v60 = 9;
                break;
              case 5:
                v60 = 10;
                break;
              case 6:
                v60 = 11;
                break;
              default:
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x3B5,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                  v59);
            }
            LOWORD(v74) = v60;
          }
        }
        else
        {
          LOWORD(v74) = 5;
        }
        v75 = v58;
        std::vector<std::pair<bool,Microsoft::Diagnostics::ScenarioDbLookupPair>>::emplace_back<bool &,Microsoft::Diagnostics::ScenarioDbLookupPair>(
          (char *)this + 72,
          v73,
          &v74);
        v61 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(v77);
        v40 = v61;
        if ( v61 >= 0 )
        {
          std::wstring::_Tidy_deallocate(&v93);
          LOBYTE(v73[0]) = 0;
          v4 = v77;
          goto LABEL_197;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2ED,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v61,
          v73[0]);
        std::wstring::_Tidy_deallocate(&v93);
        std::wstring::_Tidy_deallocate(v90);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D7,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)InnerText,
          v73[0]);
        std::wstring::_Tidy_deallocate(&v93);
        std::wstring::_Tidy_deallocate(v90);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
      }
      goto LABEL_202;
    }
    v81 = *(_OWORD *)std::wstring::operator std::wstring_view(v90, v84);
    v93 = *(_OWORD *)&off_1803867C0;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v93, &v81) )
    {
      std::wstring::wstring(v96);
      v62 = Microsoft::Diagnostics::XMLFacade::GetInnerText(v41, v96);
      v40 = v62;
      if ( v62 >= 0 )
      {
        v63 = *(_QWORD *)v78[24].Data4;
        v64 = *(_QWORD *)&v78[25].Data1;
        while ( 1 )
        {
          if ( v63 == v64 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x304,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
              (const char *)0x87C52607LL,
              v73[0]);
            std::wstring::_Tidy_deallocate(v96);
            std::wstring::_Tidy_deallocate(v90);
            if ( v27 )
              std::_Ref_count_base::_Decref(v27);
            std::wstring::_Tidy_deallocate(v87);
            return 2277844487LL;
          }
          std::wstring::operator std::wstring_view(v96, v85);
          std::wstring::operator std::wstring_view(*(_QWORD *)v63 + 16LL, &v83);
          v93 = *v65;
          v81 = v83;
          if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v81, &v93) )
            break;
          v63 += 16;
        }
        v66 = *(__int64 (__fastcall ****)(_QWORD))v63;
        v67 = *(_BYTE *)(*(_QWORD *)v63 + 80LL);
        v68 = (std::_Ref_count_base *)(**v66)(v66);
        if ( v67 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3D8,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v69);
        LOWORD(v76[0]) = 52;
        v76[1] = v68;
        std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::emplace_back<Microsoft::Diagnostics::ScenarioDbLookupPair>(
          (char *)this + 96,
          v76);
        v70 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(v41);
        v40 = v70;
        if ( v70 >= 0 )
        {
          std::wstring::_Tidy_deallocate(v96);
          v4 = v77;
          goto LABEL_197;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x307,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v70,
          v73[0]);
        std::wstring::_Tidy_deallocate(v96);
        std::wstring::_Tidy_deallocate(v90);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2F2,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v62,
          v73[0]);
        std::wstring::_Tidy_deallocate(v96);
        std::wstring::_Tidy_deallocate(v90);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
      }
      goto LABEL_202;
    }
    v93 = *(_OWORD *)std::wstring::operator std::wstring_view(v90, v86);
    v81 = *(_OWORD *)&off_1803867B0;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v81, &v93) )
    {
      if ( v78[9].Data4[0] )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x315,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52407LL,
          v73[0]);
        std::wstring::_Tidy_deallocate(v90);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
        std::wstring::_Tidy_deallocate(v87);
        return 2277843975LL;
      }
      v72 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(v41);
      v40 = v72;
      if ( v72 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x318,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v72,
          v73[0]);
        std::wstring::_Tidy_deallocate(v90);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
        goto LABEL_202;
      }
    }
    else
    {
      v4 = v41;
      if ( Microsoft::Diagnostics::XMLFacade::IsEmptyElement(v41) )
        goto LABEL_197;
      v71 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(v41);
      v40 = v71;
      if ( v71 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v71,
          v73[0]);
        std::wstring::_Tidy_deallocate(v90);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
LABEL_202:
        std::wstring::_Tidy_deallocate(v87);
        return v40;
      }
    }
    v4 = v41;
LABEL_197:
    std::wstring::_Tidy_deallocate(v90);
  }
  if ( (int)(Element + 0x80000000) >= 0 && Element != -2147024270 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)Element,
      v73[0]);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    goto LABEL_202;
  }
  if ( LOBYTE(v73[0]) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x325,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C5242ALL,
      v73[0]);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    std::wstring::_Tidy_deallocate(v87);
    return 2277844010LL;
  }
LABEL_207:
  (*(void (__fastcall **)(Microsoft::Diagnostics::TransitionDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
  std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v82);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  std::wstring::_Tidy_deallocate(v87);
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

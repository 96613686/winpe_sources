# Microsoft::Diagnostics::ETWTriggerDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x18018f0e0`
- end: `0x18018fc01`
- name: `?ParseFromXml@ETWTriggerDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `2849`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::ETWTriggerDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18002df00`
- `0x180064e8c`
- `0x1800653d0`
- `0x1800796c0`
- `0x180080254`
- `0x18008abf4`
- `0x18008b254`
- `0x18009c8c0`
- `0x18009dec0`
- `0x1800a3760`
- `0x1800a42b4`
- `0x1800a6438`
- `0x1800a658c`
- `0x1800afab0`
- `0x1800ded9c`
- `0x1800ea398`
- `0x1800ed28c`
- `0x180135800`
- `0x180142fcc`
- `0x18018f0e0`
- `0x1801bbc78`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18018f2e5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18018f2e5`

## string_xrefs

- `0x18018f1ee`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f290`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f2fc`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f39f`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f3ed`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f4b2`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f50f`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f5ca`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f627`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f6e2`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f740`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f7fc`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f859`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f8fa`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f939`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f978`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f9b7`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018f9fa`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018fa3e`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018fa7d`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018fad4`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018fb1f`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018fb7d`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018fba2`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18018fbee`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::ETWTriggerDef::ParseFromXml(
        Microsoft::Diagnostics::ETWTriggerDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  int v6; // ecx
  int v7; // ecx
  __int64 v8; // r8
  int v9; // r14d
  int v10; // r13d
  int v11; // r12d
  __m128i si128; // xmm6
  unsigned int Element; // edi
  int CurrentElementName; // eax
  unsigned int v15; // edi
  int InnerText; // eax
  unsigned int v18; // edi
  const OLECHAR *v19; // rcx
  HRESULT v20; // eax
  unsigned int v21; // edi
  Microsoft::Diagnostics::SettingsManager *SettingsManager; // rax
  int v23; // r8d
  int v24; // r9d
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // edi
  int v28; // eax
  unsigned int v29; // edi
  int v30; // eax
  unsigned int v31; // edi
  int v32; // eax
  unsigned int v33; // edi
  int v34; // eax
  unsigned int v35; // edi
  int v36; // eax
  unsigned int v37; // edi
  int v38; // eax
  unsigned int v39; // edi
  int v40; // eax
  unsigned int v41; // edi
  int v42; // eax
  unsigned int v43; // edi
  int v44; // eax
  unsigned int v45; // edi
  int v46; // eax
  unsigned int v47; // edi
  int v48; // eax
  unsigned int v49; // edi
  int v50; // eax
  unsigned int v51; // edi
  int v52; // eax
  unsigned int v53; // edi
  int v54; // eax
  unsigned int v55; // edi
  unsigned int v56; // [rsp+20h] [rbp-148h]
  int v57; // [rsp+30h] [rbp-138h]
  int v58; // [rsp+34h] [rbp-134h]
  __int128 v59; // [rsp+40h] [rbp-128h] BYREF
  __int128 v60; // [rsp+50h] [rbp-118h] BYREF
  unsigned int v61[2]; // [rsp+60h] [rbp-108h] BYREF
  struct Microsoft::Diagnostics::ScenarioParsingState *v62; // [rsp+68h] [rbp-100h]
  _BYTE v63[16]; // [rsp+70h] [rbp-F8h] BYREF
  _BYTE v64[16]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE v65[16]; // [rsp+90h] [rbp-D8h] BYREF
  _BYTE v66[16]; // [rsp+A0h] [rbp-C8h] BYREF
  _BYTE v67[16]; // [rsp+B0h] [rbp-B8h] BYREF
  _BYTE v68[16]; // [rsp+C0h] [rbp-A8h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+D0h] [rbp-98h] BYREF
  __m128i v70; // [rsp+E0h] [rbp-88h]
  _OWORD v71[2]; // [rsp+F0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v62 = a3;
  v6 = *((unsigned __int8 *)this + 48);
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 != 1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x3A4,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
          (const char *)a3);
      v8 = 4;
    }
    else
    {
      v8 = 3;
    }
  }
  else
  {
    v8 = 2;
  }
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(v61, (char *)a3 + 112, v8);
  v59 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 16, &v60);
  Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(v61, &v59);
  v9 = 0;
  v57 = 0;
  v10 = 0;
  v11 = 0;
  v58 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    if ( Element )
      break;
    v71[0] = 0;
    v71[1] = si128;
    LOWORD(v71[0]) = 0;
    CurrentElementName = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v71);
    v15 = CurrentElementName;
    if ( CurrentElementName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
        (const char *)(unsigned int)CurrentElementName,
        v56);
      std::wstring::_Tidy_deallocate(v71);
      return v15;
    }
    v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v71, v63);
    v60 = *(_OWORD *)&off_180387820;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
    {
      *(_OWORD *)lpsz = 0;
      v70 = si128;
      LOWORD(lpsz[0]) = 0;
      InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v18 = InnerText;
      if ( InnerText < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x109,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)InnerText,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v18;
      }
      v19 = (const OLECHAR *)lpsz;
      if ( v70.m128i_i64[1] > 7uLL )
        v19 = lpsz[0];
      v20 = CLSIDFromString(v19, (LPCLSID)((char *)this + 56));
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v20,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v21;
      }
      SettingsManager = Microsoft::Diagnostics::LifetimeManager::GetSettingsManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      if ( Microsoft::Diagnostics::SettingsManager::IsRecognizedProviderGroupId(
             SettingsManager,
             (const struct _GUID *)((char *)this + 56)) )
      {
        if ( (unsigned int)dword_1804543B0 > 2 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 8) )
          {
            *(_QWORD *)v61 = (char *)this + 56;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
              (unsigned int)&dword_1804543B0,
              (unsigned int)&unk_1803FE1F0,
              v23,
              v24,
              (__int64)v61);
          }
        }
        v25 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x11A,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
                (const char *)0x7DE,
                v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v25;
      }
      v26 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v27 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11D,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v26,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v27;
      }
      v9 = ++v57;
      goto LABEL_49;
    }
    v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v71, v64);
    v59 = *(_OWORD *)&off_180387810;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v59, &v60) )
    {
      *(_OWORD *)lpsz = 0;
      v70 = si128;
      LOWORD(lpsz[0]) = 0;
      v28 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x124,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v28,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v29;
      }
      *((_DWORD *)this + 18) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(lpsz);
      v30 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x128,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v30,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v31;
      }
      ++v10;
LABEL_49:
      std::wstring::_Tidy_deallocate(lpsz);
      goto LABEL_65;
    }
    v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v71, v65);
    v59 = *(_OWORD *)&off_180387800;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v59, &v60) )
    {
      *(_OWORD *)lpsz = 0;
      v70 = si128;
      LOWORD(lpsz[0]) = 0;
      v32 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v32,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v33;
      }
      *((_DWORD *)this + 19) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(lpsz);
      v34 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x133,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v34,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v35;
      }
      ++v11;
      goto LABEL_49;
    }
    v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v71, v66);
    v59 = *(_OWORD *)&off_180387850;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v59, &v60) )
    {
      *(_OWORD *)lpsz = 0;
      v70 = si128;
      LOWORD(lpsz[0]) = 0;
      v36 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v37 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v36,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v37;
      }
      *((_QWORD *)this + 10) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned __int64>(lpsz);
      v38 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v39 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v38,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v39;
      }
      ++v58;
      goto LABEL_49;
    }
    v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v71, v67);
    v59 = *(_OWORD *)&off_180387840;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v59, &v60) )
    {
      *(_OWORD *)lpsz = 0;
      v70 = si128;
      LOWORD(lpsz[0]) = 0;
      v40 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v41 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x145,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v40,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v41;
      }
      *((_BYTE *)this + 88) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(lpsz);
      v42 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v43 = v42;
      if ( v42 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x149,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v42,
          v56);
        std::wstring::_Tidy_deallocate(lpsz);
        std::wstring::_Tidy_deallocate(v71);
        return v43;
      }
      goto LABEL_49;
    }
    v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v71, v68);
    v59 = *(_OWORD *)&off_180387830;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v59, &v60) )
    {
      if ( *((_BYTE *)v62 + 152) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)0x87C52407LL,
          v56);
        std::wstring::_Tidy_deallocate(v71);
        return 2277843975LL;
      }
      v54 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v55 = v54;
      if ( v54 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x162,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v54,
          v56);
        std::wstring::_Tidy_deallocate(v71);
        return v55;
      }
    }
    else
    {
      v44 = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v45 = v44;
      if ( v44 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x153,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v44,
          v56);
        std::wstring::_Tidy_deallocate(v71);
        return v45;
      }
      v46 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v47 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x154,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v46,
          v56);
        std::wstring::_Tidy_deallocate(v71);
        return v47;
      }
      v48 = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v49 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v48,
          v56);
        std::wstring::_Tidy_deallocate(v71);
        return v49;
      }
      v50 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v51 = v50;
      if ( v50 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x156,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v50,
          v56);
        std::wstring::_Tidy_deallocate(v71);
        return v51;
      }
      v52 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v53 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x159,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v52,
          v56);
        std::wstring::_Tidy_deallocate(v71);
        return v53;
      }
    }
LABEL_65:
    std::wstring::_Tidy_deallocate(v71);
  }
  if ( (int)(Element + 0x80000000) >= 0 && Element != -2147024270 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
      (const char *)Element,
      v56);
    return Element;
  }
  if ( v9 == 1 && v58 == 1 )
  {
    if ( v10 )
    {
      *((_BYTE *)this + 89) = 0;
      if ( v10 != 1 || v11 != 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)0x87C52402LL,
          v56);
        return 2277843970LL;
      }
    }
    else
    {
      *((_BYTE *)this + 89) = 1;
      if ( v11 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)0x87C52402LL,
          v56);
        return 2277843970LL;
      }
    }
    Microsoft::Diagnostics::ETWTriggerDef::EstablishParseDynamicMembers(this);
    (*(void (__fastcall **)(Microsoft::Diagnostics::ETWTriggerDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
    std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(*(_QWORD *)v61);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16F,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
    (const char *)0x87C52402LL,
    v56);
  return 2277843970LL;
}

```

## disassembly

```asm
0x18018f0e0  mov     rax, rsp
0x18018f0e3  push    rbx
0x18018f0e4  push    rsi
0x18018f0e5  push    rdi
0x18018f0e6  push    r12
0x18018f0e8  push    r13
0x18018f0ea  push    r14
0x18018f0ec  push    r15
0x18018f0ee  sub     rsp, 130h
0x18018f0f5  movaps  xmmword ptr [rax-48h], xmm6
0x18018f0f9  mov     rax, cs:__security_cookie
0x18018f100  xor     rax, rsp
0x18018f103  mov     [rsp+168h+var_58], rax
0x18018f10b  mov     r9, r8; char *
0x18018f10e  mov     [rsp+168h+var_100], r8
0x18018f113  mov     rbx, rdx
0x18018f116  mov     rsi, rcx
0x18018f119  movzx   ecx, byte ptr [rcx+30h]
0x18018f11d  test    ecx, ecx
0x18018f11f  jz      short loc_18018F145
0x18018f121  sub     ecx, 1
0x18018f124  jz      short loc_18018F137
0x18018f126  cmp     ecx, 1
0x18018f129  jnz     loc_18018FBE6
0x18018f12f  mov     r8d, 4
0x18018f135  jmp     short loc_18018F13D
0x18018f137  mov     r8d, 3
0x18018f13d  mov     r15d, 2
0x18018f143  jmp     short loc_18018F14F
0x18018f145  mov     r15d, 2
0x18018f14b  movzx   r8d, r15w
0x18018f14f  lea     rdx, [r9+70h]
0x18018f153  lea     rcx, [rsp+168h+var_108]
0x18018f158  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x18018f15d  lea     rcx, [rsi+10h]
0x18018f161  lea     rdx, [rsp+168h+var_118]
0x18018f166  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018f16b  movups  xmm0, xmmword ptr [rax]
0x18018f16e  movdqu  [rsp+168h+var_128], xmm0
0x18018f174  lea     rdx, [rsp+168h+var_128]
0x18018f179  lea     rcx, [rsp+168h+var_108]
0x18018f17e  call    ?AddDetailToCurrentFrame@ParsingDomain@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(std::wstring_view)
0x18018f183  xor     r14d, r14d
0x18018f186  mov     [rsp+168h+var_138], r14d
0x18018f18b  xor     r13d, r13d
0x18018f18e  xor     r12d, r12d
0x18018f191  xor     eax, eax
0x18018f193  mov     [rsp+168h+var_134], eax
0x18018f197  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18018f19f  mov     rcx, rbx; this
0x18018f1a2  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x18018f1a7  mov     edi, eax
0x18018f1a9  test    eax, eax
0x18018f1ab  jnz     loc_18018FAB5
0x18018f1b1  xorps   xmm0, xmm0
0x18018f1b4  movups  [rsp+168h+var_78], xmm0
0x18018f1bc  movdqu  [rsp+168h+var_68], xmm6
0x18018f1c5  mov     word ptr [rsp+168h+var_78], ax
0x18018f1cd  lea     rdx, [rsp+168h+var_78]
0x18018f1d5  mov     rcx, rbx
0x18018f1d8  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x18018f1dd  mov     edi, eax
0x18018f1df  test    eax, eax
0x18018f1e1  jns     short loc_18018F214
0x18018f1e3  mov     rcx, [rsp+168h]; this
0x18018f1eb  mov     r9d, eax; char *
0x18018f1ee  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18018f1f5  mov     edx, 104h; void *
0x18018f1fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f1ff  nop
0x18018f200  lea     rcx, [rsp+168h+var_78]
0x18018f208  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f20d  mov     eax, edi
0x18018f20f  jmp     loc_18018FBBB
0x18018f214  lea     rdx, [rsp+168h+var_F8]
0x18018f219  lea     rcx, [rsp+168h+var_78]
0x18018f221  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018f226  movups  xmm0, xmmword ptr [rax]
0x18018f229  movdqu  [rsp+168h+var_128], xmm0
0x18018f22f  movups  xmm1, xmmword ptr cs:off_180387820; "provider"
0x18018f236  movdqu  [rsp+168h+var_118], xmm1
0x18018f23c  lea     rdx, [rsp+168h+var_128]
0x18018f241  lea     rcx, [rsp+168h+var_118]
0x18018f246  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18018f24b  test    eax, eax
0x18018f24d  jnz     loc_18018F433
0x18018f253  xorps   xmm0, xmm0
0x18018f256  movups  xmmword ptr [rsp+168h+lpsz], xmm0
0x18018f25e  movdqu  [rsp+168h+var_88], xmm6
0x18018f267  mov     word ptr [rsp+168h+lpsz], ax
0x18018f26f  lea     rdx, [rsp+168h+lpsz]
0x18018f277  mov     rcx, rbx
0x18018f27a  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18018f27f  mov     edi, eax
0x18018f281  test    eax, eax
0x18018f283  jns     short loc_18018F2C4
0x18018f285  mov     rcx, [rsp+168h]; this
0x18018f28d  mov     r9d, eax; char *
0x18018f290  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18018f297  mov     edx, 109h; void *
0x18018f29c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f2a1  nop
0x18018f2a2  lea     rcx, [rsp+168h+lpsz]
0x18018f2aa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f2af  nop
0x18018f2b0  lea     rcx, [rsp+168h+var_78]
0x18018f2b8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f2bd  mov     eax, edi
0x18018f2bf  jmp     loc_18018FBBB
0x18018f2c4  lea     rcx, [rsp+168h+lpsz]
0x18018f2cc  cmp     qword ptr [rsp+168h+var_88+8], 7
0x18018f2d5  cmova   rcx, [rsp+168h+lpsz]; lpsz
0x18018f2de  lea     r14, [rsi+38h]
0x18018f2e2  mov     rdx, r14; pclsid
0x18018f2e5  call    cs:__imp_CLSIDFromString
0x18018f2eb  mov     edi, eax
0x18018f2ed  test    eax, eax
0x18018f2ef  jns     short loc_18018F330
0x18018f2f1  mov     rcx, [rsp+168h]; this
0x18018f2f9  mov     r9d, eax; char *
0x18018f2fc  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18018f303  mov     edx, 10Fh; void *
0x18018f308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f30d  nop
0x18018f30e  lea     rcx, [rsp+168h+lpsz]
0x18018f316  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f31b  nop
0x18018f31c  lea     rcx, [rsp+168h+var_78]
0x18018f324  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f329  mov     eax, edi
0x18018f32b  jmp     loc_18018FBBB
0x18018f330  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18018f337  call    ?GetSettingsManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVSettingsManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetSettingsManager(void)
0x18018f33c  mov     rdx, r14; struct _GUID *
0x18018f33f  mov     rcx, rax; this
0x18018f342  call    ?IsRecognizedProviderGroupId@SettingsManager@Diagnostics@Microsoft@@QEAA_NAEBU_GUID@@@Z; Microsoft::Diagnostics::SettingsManager::IsRecognizedProviderGroupId(_GUID const &)
0x18018f347  test    al, al
0x18018f349  jz      loc_18018F3D4
0x18018f34f  mov     eax, cs:dword_1804543B0
0x18018f355  cmp     eax, r15d
0x18018f358  jbe     short loc_18018F391
0x18018f35a  mov     edx, 8
0x18018f35f  lea     rcx, dword_1804543B0
0x18018f366  call    _tlgKeywordOn
0x18018f36b  test    al, al
0x18018f36d  jz      short loc_18018F391
0x18018f36f  mov     qword ptr [rsp+168h+var_108], r14
0x18018f374  lea     rax, [rsp+168h+var_108]
0x18018f379  mov     qword ptr [rsp+168h+var_148], rax; unsigned int
0x18018f37e  lea     rdx, unk_1803FE1F0
0x18018f385  lea     rcx, dword_1804543B0
0x18018f38c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18018f391  mov     rcx, [rsp+168h]; this
0x18018f399  mov     r9d, 7DEh; char *
0x18018f39f  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18018f3a6  mov     edx, 11Ah; void *
0x18018f3ab  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18018f3b0  mov     ebx, eax
0x18018f3b2  lea     rcx, [rsp+168h+lpsz]
0x18018f3ba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f3bf  nop
0x18018f3c0  lea     rcx, [rsp+168h+var_78]
0x18018f3c8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f3cd  mov     eax, ebx
0x18018f3cf  jmp     loc_18018FBBB
0x18018f3d4  mov     rcx, rbx; this
0x18018f3d7  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18018f3dc  mov     edi, eax
0x18018f3de  test    eax, eax
0x18018f3e0  jns     short loc_18018F421
0x18018f3e2  mov     rcx, [rsp+168h]; this
0x18018f3ea  mov     r9d, eax; char *
0x18018f3ed  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18018f3f4  mov     edx, 11Dh; void *
0x18018f3f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f3fe  nop
0x18018f3ff  lea     rcx, [rsp+168h+lpsz]
0x18018f407  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f40c  nop
0x18018f40d  lea     rcx, [rsp+168h+var_78]
0x18018f415  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f41a  mov     eax, edi
0x18018f41c  jmp     loc_18018FBBB
0x18018f421  mov     r14d, [rsp+168h+var_138]
0x18018f426  inc     r14d
0x18018f429  mov     [rsp+168h+var_138], r14d
0x18018f42e  jmp     loc_18018F88D
0x18018f433  lea     rdx, [rsp+168h+var_E8]
0x18018f43b  lea     rcx, [rsp+168h+var_78]
0x18018f443  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018f448  movups  xmm0, xmmword ptr [rax]
0x18018f44b  movdqu  [rsp+168h+var_118], xmm0
0x18018f451  movups  xmm1, xmmword ptr cs:off_180387810; "id"
0x18018f458  movdqu  [rsp+168h+var_128], xmm1
0x18018f45e  lea     rdx, [rsp+168h+var_118]
0x18018f463  lea     rcx, [rsp+168h+var_128]
0x18018f468  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18018f46d  test    eax, eax
0x18018f46f  jnz     loc_18018F54B
0x18018f475  xorps   xmm0, xmm0
0x18018f478  movups  xmmword ptr [rsp+168h+lpsz], xmm0
0x18018f480  movdqu  [rsp+168h+var_88], xmm6
0x18018f489  mov     word ptr [rsp+168h+lpsz], ax
0x18018f491  lea     rdx, [rsp+168h+lpsz]
0x18018f499  mov     rcx, rbx
0x18018f49c  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18018f4a1  mov     edi, eax
0x18018f4a3  test    eax, eax
0x18018f4a5  jns     short loc_18018F4E6
0x18018f4a7  mov     rcx, [rsp+168h]; this
0x18018f4af  mov     r9d, eax; char *
0x18018f4b2  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18018f4b9  mov     edx, 124h; void *
0x18018f4be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f4c3  nop
0x18018f4c4  lea     rcx, [rsp+168h+lpsz]
0x18018f4cc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f4d1  nop
0x18018f4d2  lea     rcx, [rsp+168h+var_78]
0x18018f4da  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f4df  mov     eax, edi
0x18018f4e1  jmp     loc_18018FBBB
0x18018f4e6  lea     rcx, [rsp+168h+lpsz]
0x18018f4ee  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x18018f4f3  mov     [rsi+48h], eax
0x18018f4f6  mov     rcx, rbx; this
0x18018f4f9  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18018f4fe  mov     edi, eax
0x18018f500  test    eax, eax
0x18018f502  jns     short loc_18018F543
0x18018f504  mov     rcx, [rsp+168h]; this
0x18018f50c  mov     r9d, eax; char *
0x18018f50f  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18018f516  mov     edx, 128h; void *
0x18018f51b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f520  nop
0x18018f521  lea     rcx, [rsp+168h+lpsz]
0x18018f529  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f52e  nop
0x18018f52f  lea     rcx, [rsp+168h+var_78]
0x18018f537  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f53c  mov     eax, edi
0x18018f53e  jmp     loc_18018FBBB
0x18018f543  inc     r13d
0x18018f546  jmp     loc_18018F88D
0x18018f54b  lea     rdx, [rsp+168h+var_D8]
0x18018f553  lea     rcx, [rsp+168h+var_78]
0x18018f55b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018f560  movups  xmm0, xmmword ptr [rax]
0x18018f563  movdqu  [rsp+168h+var_118], xmm0
0x18018f569  movups  xmm1, xmmword ptr cs:off_180387800; "version"
0x18018f570  movdqu  [rsp+168h+var_128], xmm1
0x18018f576  lea     rdx, [rsp+168h+var_118]
0x18018f57b  lea     rcx, [rsp+168h+var_128]
0x18018f580  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18018f585  test    eax, eax
0x18018f587  jnz     loc_18018F663
0x18018f58d  xorps   xmm0, xmm0
0x18018f590  movups  xmmword ptr [rsp+168h+lpsz], xmm0
0x18018f598  movdqu  [rsp+168h+var_88], xmm6
0x18018f5a1  mov     word ptr [rsp+168h+lpsz], ax
0x18018f5a9  lea     rdx, [rsp+168h+lpsz]
0x18018f5b1  mov     rcx, rbx
0x18018f5b4  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18018f5b9  mov     edi, eax
0x18018f5bb  test    eax, eax
0x18018f5bd  jns     short loc_18018F5FE
0x18018f5bf  mov     rcx, [rsp+168h]; this
0x18018f5c7  mov     r9d, eax; char *
0x18018f5ca  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18018f5d1  mov     edx, 12Fh; void *
0x18018f5d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f5db  nop
0x18018f5dc  lea     rcx, [rsp+168h+lpsz]
0x18018f5e4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f5e9  nop
0x18018f5ea  lea     rcx, [rsp+168h+var_78]
0x18018f5f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f5f7  mov     eax, edi
0x18018f5f9  jmp     loc_18018FBBB
0x18018f5fe  lea     rcx, [rsp+168h+lpsz]
0x18018f606  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x18018f60b  mov     [rsi+4Ch], eax
0x18018f60e  mov     rcx, rbx; this
0x18018f611  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18018f616  mov     edi, eax
0x18018f618  test    eax, eax
0x18018f61a  jns     short loc_18018F65B
0x18018f61c  mov     rcx, [rsp+168h]; this
0x18018f624  mov     r9d, eax; char *
0x18018f627  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18018f62e  mov     edx, 133h; void *
0x18018f633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f638  nop
0x18018f639  lea     rcx, [rsp+168h+lpsz]
0x18018f641  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f646  nop
0x18018f647  lea     rcx, [rsp+168h+var_78]
0x18018f64f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f654  mov     eax, edi
  ... truncated ...
```

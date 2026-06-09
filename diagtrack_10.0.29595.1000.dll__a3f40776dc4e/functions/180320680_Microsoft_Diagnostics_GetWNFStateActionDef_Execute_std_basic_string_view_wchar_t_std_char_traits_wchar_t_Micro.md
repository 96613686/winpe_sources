# Microsoft::Diagnostics::GetWNFStateActionDef::Execute(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState &,Microsoft::Diagnostics::ScenarioInst const &)

- ea: `0x180320680`
- end: `0x18032114b`
- name: `?Execute@GetWNFStateActionDef@Diagnostics@Microsoft@@UEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVEscalationWorkItemState@23@AEBVScenarioInst@23@@Z`
- size: `2763`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x18001a644`
- `0x18001a8f0`
- `0x18001b010`
- `0x18001b24c`
- `0x18001b434`
- `0x18001b510`
- `0x18001b52c`
- `0x180020150`
- `0x180022570`
- `0x180027c28`
- `0x180027e50`
- `0x18002ac10`
- `0x18002b7c0`
- `0x18002df00`
- `0x18003119c`
- `0x180064e6c`
- `0x180064e8c`
- `0x18009c8c0`
- `0x1800a8ed4`
- `0x1800c4b14`
- `0x1800df5d0`
- `0x1800f7b34`
- `0x180102bbc`
- `0x180105ad8`
- `0x18010e55c`
- `0x18010f9b8`
- `0x18011bccc`
- `0x18011d2bc`
- `0x180135800`
- `0x180142fcc`
- `0x18016323c`
- `0x1801dc068`
- `0x18020aac0`
- `0x180312c78`
- `0x180313400`
- `0x180320680`
- `0x180321154`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x180320900`
- `ntdll!NtQueryWnfStateData` at `0x180320a21`
- `ntdll!NtQueryWnfStateData` at `0x180320900`
- `ntdll!NtQueryWnfStateData` at `0x180320a21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803207f6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18032083f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18032083f`

## string_xrefs

- `0x1803206ee`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180320851`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x1803209a7`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180320a8e`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180320cec`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180320feb`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x180321095`: `XML written to file: `

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetWNFStateActionDef::Execute(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int16 v7; // ax
  int *v8; // rsi
  const WCHAR *v9; // rcx
  const char *v10; // r9
  unsigned int LastError; // ebx
  __int64 v12; // rbx
  __int64 v13; // r12
  int WnfStateData; // r15d
  __int64 v15; // rax
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // ebx
  int v19; // r15d
  int v20; // r8d
  int v21; // r9d
  unsigned int v22; // ebx
  __int64 v23; // r13
  int *v24; // rbx
  unsigned int v25; // r15d
  const wchar_t *v26; // r14
  int SizeFromTdhType; // eax
  unsigned int v28; // r12d
  __int128 *v29; // rax
  wil *v30; // rcx
  int appended; // eax
  unsigned int v32; // ebx
  __int64 v33; // rax
  int v34; // eax
  int v35; // [rsp+20h] [rbp-1E8h]
  int v36; // [rsp+20h] [rbp-1E8h]
  int v37; // [rsp+20h] [rbp-1E8h]
  int v38; // [rsp+20h] [rbp-1E8h]
  int v39; // [rsp+20h] [rbp-1E8h]
  int v40; // [rsp+30h] [rbp-1D8h] BYREF
  unsigned int v41; // [rsp+34h] [rbp-1D4h] BYREF
  int v42; // [rsp+38h] [rbp-1D0h] BYREF
  PSID Sid; // [rsp+40h] [rbp-1C8h] BYREF
  __int64 v44; // [rsp+48h] [rbp-1C0h] BYREF
  _DWORD v45[4]; // [rsp+50h] [rbp-1B8h] BYREF
  __int128 v46; // [rsp+60h] [rbp-1A8h] BYREF
  int *v47; // [rsp+70h] [rbp-198h] BYREF
  int v48; // [rsp+78h] [rbp-190h] BYREF
  const wchar_t *v49; // [rsp+80h] [rbp-188h] BYREF
  __int64 v50; // [rsp+88h] [rbp-180h]
  __int128 v51; // [rsp+90h] [rbp-178h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-168h]
  _BYTE v53[16]; // [rsp+A8h] [rbp-160h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-150h]
  __int64 v55; // [rsp+C0h] [rbp-148h]
  __int64 v56; // [rsp+C8h] [rbp-140h]
  __int64 v57; // [rsp+D0h] [rbp-138h]
  _BYTE v58[80]; // [rsp+E0h] [rbp-128h] BYREF
  _OWORD v59[2]; // [rsp+130h] [rbp-D8h] BYREF
  LPCWSTR StringSid[4]; // [rsp+150h] [rbp-B8h] BYREF
  _BYTE v61[32]; // [rsp+170h] [rbp-98h] BYREF
  _BYTE v62[48]; // [rsp+190h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v52 = a3;
  v55 = a2;
  v56 = a2;
  v57 = a3;
  v54 = a3;
  if ( !*(_QWORD *)(a2 + 8) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
      (const char *)0x8007010BLL,
      v36);
    return 2147942667LL;
  }
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)v62);
  Microsoft::Diagnostics::XmlWriterFacade::XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
  *(_QWORD *)&v59[0] = L"result";
  *((_QWORD *)&v59[0] + 1) = 6;
  Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v58, v53, v59);
  Sid = 0;
  v48 = 0;
  v59[0] = *(_OWORD *)std::wstring::operator std::wstring_view(a1 + 192, &v46);
  Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a4, StringSid, v59);
  v7 = *(_WORD *)(a1 + 224);
  if ( v7 == 1 )
  {
    v48 = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(StringSid);
    v8 = &v48;
  }
  else
  {
    v8 = 0;
    if ( v7 == 2 )
    {
      Sid = 0;
      v9 = (const WCHAR *)StringSid;
      if ( StringSid[3] > (LPCWSTR)7 )
        v9 = StringSid[0];
      if ( !ConvertStringSidToSidW(v9, &Sid) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x3C,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
                      v10);
        std::wstring::_Tidy_deallocate(StringSid);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
        Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
        Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
        std::wstring::_Tidy_deallocate(v62);
        return LastError;
      }
      v8 = (int *)Sid;
    }
  }
  std::wstring::_Tidy_deallocate(StringSid);
  v41 = 0;
  v45[0] = 0;
  v12 = 0;
  v44 = 0;
  v13 = (a1 + 168) & -(__int64)(*(_BYTE *)(a1 + 184) != 0);
  v37 = 0;
  WnfStateData = NtQueryWnfStateData(a1 + 160, v13, v8, v45);
  if ( WnfStateData == -1073741789 )
  {
    v15 = std::make_unique<unsigned char [0],0>(&v47);
    std::unique_ptr<enum gsl::byte [0]>::operator=<std::default_delete<enum gsl::byte [0]>,0>(&v44, v15);
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v47);
    v12 = v44;
  }
  else if ( WnfStateData < 0 )
  {
    if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
    {
      v42 = 1;
      v40 = WnfStateData;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)byte_18040314D,
        v16,
        v17,
        (__int64)&v40,
        (__int64)&v42);
    }
    v18 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x5A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
            (const char *)(unsigned int)WnfStateData,
            v37);
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
    Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
    std::wstring::_Tidy_deallocate(v62);
    return v18;
  }
  v38 = v12;
  v19 = NtQueryWnfStateData(a1 + 160, v13, v8, v45);
  if ( v19 >= 0 )
  {
    gsl::span<enum gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
      &v51,
      v12,
      v41);
    *(_QWORD *)&v59[0] = L"changestamp";
    *((_QWORD *)&v59[0] + 1) = 11;
    v49 = L"info";
    v50 = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
      (unsigned int)v58,
      (unsigned int)&v49,
      (unsigned int)v59,
      (unsigned int)v45,
      0);
    *(_QWORD *)&v59[0] = L"wnfmessagesize";
    *((_QWORD *)&v59[0] + 1) = 14;
    v49 = L"info";
    v50 = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
      (unsigned int)v58,
      (unsigned int)&v49,
      (unsigned int)v59,
      (unsigned int)&v41,
      0);
    if ( *(_BYTE *)(a1 + 128) )
    {
      v59[0] = v51;
      Microsoft::Diagnostics::Utils::String::ConvertBufferToHexString(StringSid, v59);
      *(_QWORD *)&v59[0] = L"wnfhex";
      *((_QWORD *)&v59[0] + 1) = 6;
      *(_QWORD *)&v51 = L"info";
      *((_QWORD *)&v51 + 1) = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(v58, &v51, v59, StringSid);
      std::wstring::_Tidy_deallocate(StringSid);
      v23 = v52;
    }
    else
    {
      v24 = *(int **)(a1 + 136);
      v47 = v24;
      v25 = 0;
      v42 = 0;
      v49 = L"wnfstructure";
      v50 = 12;
      Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v58, v59, &v49);
      v26 = (const wchar_t *)(a1 + 144);
      while ( v25 < (unsigned int)v51 )
      {
        v26 = (const wchar_t *)(a1 + 144);
        v49 = (const wchar_t *)(a1 + 144);
        if ( v24 == *(int **)(a1 + 144) )
          break;
        v40 = 0;
        v46 = 0;
        SizeFromTdhType = Microsoft::Diagnostics::Utils::Xml::GetSizeFromTdhType((unsigned int)*v24, &v46, &v40);
        v28 = SizeFromTdhType;
        if ( SizeFromTdhType < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
            (const char *)(unsigned int)SizeFromTdhType,
            v39);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v59);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
          Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
          std::wstring::_Tidy_deallocate(v62);
          return v28;
        }
        v29 = (__int128 *)gsl::span<enum gsl::byte const,-1>::subspan(&v51, StringSid, v25, -1);
        try
        {
          v46 = *v29;
          Microsoft::Diagnostics::XmlWriterFacade::WriteTdhBufferToXml(
            (__int64)v58,
            *v24,
            (unsigned int)v40,
            (__int64)&v46);
          v25 += v40;
          v42 = v25;
          v47 = ++v24;
        }
        catch ( ... )
        {
          v34 = wil::ResultFromCaughtException(v30);
          v40 = v34;
          if ( v34 == -2147024785 )
          {
            v26 = v49;
            v24 = v47;
            v25 = v42;
            v55 = v56;
            v23 = v57;
            goto LABEL_32;
          }
          if ( v34 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
              (const char *)(unsigned int)v34,
              v35);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v59);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
          Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
          std::wstring::_Tidy_deallocate(v62);
          return (unsigned int)v40;
        }
      }
      v23 = v52;
LABEL_32:
      Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v59);
      if ( v24 != *(int **)v26 )
        goto LABEL_38;
      if ( v25 >= v41 )
        goto LABEL_42;
      if ( v24 == *(int **)v26 )
      {
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v54 + 168));
        if ( (unsigned int)dword_1804543B0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1804543B0,
            &dword_1804030D4);
      }
      else
      {
LABEL_38:
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v54 + 168));
        if ( (unsigned int)dword_1804543B0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1804543B0,
            &word_1804030A6);
      }
      v46 = v51;
      Microsoft::Diagnostics::Utils::String::ConvertBufferToHexString(StringSid, &v46);
      *(_QWORD *)&v59[0] = L"wnfhex";
      *((_QWORD *)&v59[0] + 1) = 6;
      *(_QWORD *)&v51 = L"info";
      *((_QWORD *)&v51 + 1) = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(v58, &v51, v59, StringSid);
      std::wstring::_Tidy_deallocate(StringSid);
    }
LABEL_42:
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
    std::wstring::wstring(v61);
    v46 = *(_OWORD *)&Microsoft::Diagnostics::GetWNFStateActionDef::k_wnfInfoOutputFileName;
    appended = Microsoft::Diagnostics::Utils::String::AppendPath(v61, &v46);
    v32 = appended;
    if ( appended >= 0 )
    {
      v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v61, StringSid);
      Microsoft::Diagnostics::XmlWriterFacade::WriteToFile(v58, &v46);
      v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v61, StringSid);
      Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(v23, &v46);
      Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v23 + 168));
      v33 = std::operator+<wchar_t>(v59, v61, L"\r\n");
      v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v33, StringSid);
      Microsoft::Diagnostics::WideStringStream::AppendString((void *)(v23 + 168));
      std::wstring::_Tidy_deallocate(v59);
      std::wstring::_Tidy_deallocate(v61);
      Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
      std::wstring::_Tidy_deallocate(v62);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
        (const char *)(unsigned int)appended,
        v39);
      std::wstring::_Tidy_deallocate(v61);
      Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
      std::wstring::_Tidy_deallocate(v62);
      return v32;
    }
  }
  else
  {
    if ( (unsigned int)dword_1804543B0 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
      {
        v42 = 2;
        v40 = v19;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1804543B0,
          (unsigned int)&dword_180403104,
          v20,
          v21,
          (__int64)&v40,
          (__int64)&v42);
      }
    }
    v22 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x67,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
            (const char *)(unsigned int)v19,
            v38);
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
    Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
    std::wstring::_Tidy_deallocate(v62);
    return v22;
  }
}

```

## disassembly

```asm
0x180320680  push    rbx
0x180320682  push    rsi
0x180320683  push    rdi
0x180320684  push    r12
0x180320686  push    r13
0x180320688  push    r14
0x18032068a  push    r15
0x18032068c  sub     rsp, 1D0h
0x180320693  mov     rax, cs:__security_cookie
0x18032069a  xor     rax, rsp
0x18032069d  mov     [rsp+208h+var_48], rax
0x1803206a5  mov     rbx, r9
0x1803206a8  mov     rax, r8
0x1803206ab  mov     [rsp+208h+var_168], rax
0x1803206b3  mov     [rsp+208h+var_148], rdx
0x1803206bb  mov     r13, rcx
0x1803206be  mov     [rsp+208h+var_140], rdx
0x1803206c6  mov     [rsp+208h+var_138], rax
0x1803206ce  mov     [rsp+208h+var_150], rax
0x1803206d6  xor     edi, edi
0x1803206d8  cmp     [rdx+8], rdi
0x1803206dc  jnz     short loc_180320704
0x1803206de  mov     rcx, [rsp+208h]; this
0x1803206e6  mov     ebx, 8007010Bh
0x1803206eb  mov     r9d, ebx; char *
0x1803206ee  lea     r8, aOnecoreBaseTel_152; "onecore\\base\\telemetry\\utc\\service"...
0x1803206f5  lea     edx, [rdi+22h]; void *
0x1803206f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803206fd  mov     eax, ebx
0x1803206ff  jmp     loc_180321127
0x180320704  lea     rcx, [rsp+208h+var_78]; this
0x18032070c  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x180320711  nop
0x180320712  lea     rcx, [rsp+208h+var_128]; this
0x18032071a  call    ??0XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::XmlWriterFacade(void)
0x18032071f  nop
0x180320720  lea     rax, aResult_0; "result"
0x180320727  mov     qword ptr [rsp+208h+var_D8], rax
0x18032072f  mov     qword ptr [rsp+208h+var_D8+8], 6
0x18032073b  lea     r8, [rsp+208h+var_D8]
0x180320743  lea     rdx, [rsp+208h+var_160]
0x18032074b  lea     rcx, [rsp+208h+var_128]
0x180320753  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x180320758  nop
0x180320759  mov     [rsp+208h+Sid], rdi
0x18032075e  mov     [rsp+208h+var_190], edi
0x180320762  lea     rcx, [r13+0C0h]
0x180320769  lea     rdx, [rsp+208h+var_1A8]
0x18032076e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180320773  movups  xmm0, xmmword ptr [rax]
0x180320776  movdqu  [rsp+208h+var_D8], xmm0
0x18032077f  lea     r8, [rsp+208h+var_D8]
0x180320787  lea     rdx, [rsp+208h+StringSid]
0x18032078f  mov     rcx, rbx
0x180320792  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x180320797  movzx   eax, word ptr [r13+0E0h]
0x18032079f  mov     ecx, 1
0x1803207a4  cmp     ax, cx
0x1803207a7  jnz     short loc_1803207CA
0x1803207a9  lea     rcx, [rsp+208h+StringSid]
0x1803207b1  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x1803207b6  mov     [rsp+208h+var_190], eax
0x1803207ba  lea     rsi, [rsp+208h+var_190]
0x1803207bf  mov     r14d, 2
0x1803207c5  jmp     loc_1803208B0
0x1803207ca  mov     rsi, rdi
0x1803207cd  mov     r14d, 2
0x1803207d3  cmp     ax, r14w
0x1803207d7  jnz     loc_1803208B0
0x1803207dd  mov     rax, [rsp+208h+Sid]
0x1803207e2  test    rax, rax
0x1803207e5  jz      short loc_18032081B
0x1803207e7  mov     [rsp+208h+var_198], rax
0x1803207ec  lea     rcx, [rsp+208h+var_1D0]; this
0x1803207f1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1803207f6  mov     rax, cs:__imp_LocalFree
0x1803207fd  mov     [rsp+208h+var_1C0], rax
0x180320802  lea     rdx, [rsp+208h+var_198]
0x180320807  lea     rcx, [rsp+208h+var_1C0]
0x18032080c  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x180320811  lea     rcx, [rsp+208h+var_1D0]; this
0x180320816  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18032081b  mov     [rsp+208h+Sid], rdi
0x180320820  lea     rcx, [rsp+208h+StringSid]
0x180320828  cmp     [rsp+208h+var_A0], 7
0x180320831  cmova   rcx, [rsp+208h+StringSid]; StringSid
0x18032083a  lea     rdx, [rsp+208h+Sid]; Sid
0x18032083f  call    cs:__imp_ConvertStringSidToSidW
0x180320845  test    eax, eax
0x180320847  jnz     short loc_1803208AB
0x180320849  mov     rcx, [rsp+208h]; this
0x180320851  lea     r8, aOnecoreBaseTel_152; "onecore\\base\\telemetry\\utc\\service"...
0x180320858  lea     edx, [rax+3Ch]; void *
0x18032085b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180320860  mov     ebx, eax
0x180320862  lea     rcx, [rsp+208h+StringSid]
0x18032086a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18032086f  nop
0x180320870  lea     rcx, [rsp+208h+Sid]
0x180320875  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18032087a  nop
0x18032087b  lea     rcx, [rsp+208h+var_160]; this
0x180320883  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x180320888  nop
0x180320889  lea     rcx, [rsp+208h+var_128]; this
0x180320891  call    ??1XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade(void)
0x180320896  nop
0x180320897  lea     rcx, [rsp+208h+var_78]
0x18032089f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803208a4  mov     eax, ebx
0x1803208a6  jmp     loc_180321127
0x1803208ab  mov     rsi, [rsp+208h+Sid]
0x1803208b0  lea     rcx, [rsp+208h+StringSid]
0x1803208b8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803208bd  mov     [rsp+208h+var_1D4], edi
0x1803208c1  mov     [rsp+208h+var_1B8], edi
0x1803208c5  mov     rbx, rdi
0x1803208c8  mov     [rsp+208h+var_1C0], rbx
0x1803208cd  lea     rcx, [r13+0A8h]
0x1803208d4  mov     al, [rcx+10h]
0x1803208d7  neg     al
0x1803208d9  sbb     r12, r12
0x1803208dc  and     r12, rcx
0x1803208df  lea     rcx, [rsp+208h+var_1D4]
0x1803208e4  mov     [rsp+208h+var_1E0], rcx
0x1803208e9  mov     qword ptr [rsp+208h+var_1E8], rdi
0x1803208ee  lea     r9, [rsp+208h+var_1B8]
0x1803208f3  mov     r8, rsi
0x1803208f6  mov     rdx, r12
0x1803208f9  lea     rcx, [r13+0A0h]
0x180320900  call    cs:__imp_NtQueryWnfStateData
0x180320906  mov     r15d, eax
0x180320909  cmp     eax, 0C0000023h
0x18032090e  jnz     short loc_18032093F
0x180320910  mov     edx, [rsp+208h+var_1D4]
0x180320914  lea     rcx, [rsp+208h+var_198]
0x180320919  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18032091e  mov     rdx, rax
0x180320921  lea     rcx, [rsp+208h+var_1C0]
0x180320926  call    ??$?4U?$default_delete@$$BY0A@W4byte@gsl@@@std@@$0A@@?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<gsl::byte [0]>::operator=<std::default_delete<gsl::byte [0]>,0>(std::unique_ptr<gsl::byte [0]> &&)
0x18032092b  lea     rcx, [rsp+208h+var_198]
0x180320930  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180320935  mov     rbx, [rsp+208h+var_1C0]
0x18032093a  jmp     loc_180320A00
0x18032093f  test    r15d, r15d
0x180320942  jns     loc_180320A00
0x180320948  mov     eax, cs:dword_1804543B0
0x18032094e  cmp     eax, r14d
0x180320951  jbe     short loc_18032099C
0x180320953  mov     edx, 4
0x180320958  lea     rcx, dword_1804543B0
0x18032095f  call    _tlgKeywordOn
0x180320964  test    al, al
0x180320966  jz      short loc_18032099C
0x180320968  mov     [rsp+208h+var_1D0], 1
0x180320970  mov     [rsp+208h+var_1D8], r15d
0x180320975  lea     rax, [rsp+208h+var_1D0]
0x18032097a  mov     [rsp+208h+var_1E0], rax
0x18032097f  lea     rax, [rsp+208h+var_1D8]
0x180320984  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x180320989  lea     rdx, byte_18040314D
0x180320990  lea     rcx, dword_1804543B0
0x180320997  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18032099c  mov     rcx, [rsp+208h]; this
0x1803209a4  mov     r9d, r15d; char *
0x1803209a7  lea     r8, aOnecoreBaseTel_152; "onecore\\base\\telemetry\\utc\\service"...
0x1803209ae  mov     edx, 5Ah ; 'Z'; void *
0x1803209b3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1803209b8  mov     ebx, eax
0x1803209ba  lea     rcx, [rsp+208h+var_1C0]
0x1803209bf  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1803209c4  nop
0x1803209c5  lea     rcx, [rsp+208h+Sid]
0x1803209ca  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1803209cf  nop
0x1803209d0  lea     rcx, [rsp+208h+var_160]; this
0x1803209d8  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x1803209dd  nop
0x1803209de  lea     rcx, [rsp+208h+var_128]; this
0x1803209e6  call    ??1XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade(void)
0x1803209eb  nop
0x1803209ec  lea     rcx, [rsp+208h+var_78]
0x1803209f4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803209f9  mov     eax, ebx
0x1803209fb  jmp     loc_180321127
0x180320a00  lea     rax, [rsp+208h+var_1D4]
0x180320a05  mov     [rsp+208h+var_1E0], rax
0x180320a0a  mov     qword ptr [rsp+208h+var_1E8], rbx
0x180320a0f  lea     r9, [rsp+208h+var_1B8]
0x180320a14  mov     r8, rsi
0x180320a17  mov     rdx, r12
0x180320a1a  lea     rcx, [r13+0A0h]
0x180320a21  call    cs:__imp_NtQueryWnfStateData
0x180320a27  mov     r15d, eax
0x180320a2a  test    eax, eax
0x180320a2c  jns     loc_180320AE7
0x180320a32  mov     ecx, cs:dword_1804543B0
0x180320a38  cmp     ecx, r14d
0x180320a3b  jbe     short loc_180320A83
0x180320a3d  mov     edx, 4
0x180320a42  lea     rcx, dword_1804543B0
0x180320a49  call    _tlgKeywordOn
0x180320a4e  test    al, al
0x180320a50  jz      short loc_180320A83
0x180320a52  mov     [rsp+208h+var_1D0], r14d
0x180320a57  mov     [rsp+208h+var_1D8], r15d
0x180320a5c  lea     rax, [rsp+208h+var_1D0]
0x180320a61  mov     [rsp+208h+var_1E0], rax
0x180320a66  lea     rax, [rsp+208h+var_1D8]
0x180320a6b  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x180320a70  lea     rdx, dword_180403104
0x180320a77  lea     rcx, dword_1804543B0
0x180320a7e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180320a83  mov     rcx, [rsp+208h]; this
0x180320a8b  mov     r9d, r15d; char *
0x180320a8e  lea     r8, aOnecoreBaseTel_152; "onecore\\base\\telemetry\\utc\\service"...
0x180320a95  mov     edx, 67h ; 'g'; void *
0x180320a9a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180320a9f  mov     ebx, eax
0x180320aa1  lea     rcx, [rsp+208h+var_1C0]
0x180320aa6  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180320aab  nop
0x180320aac  lea     rcx, [rsp+208h+Sid]
0x180320ab1  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180320ab6  nop
0x180320ab7  lea     rcx, [rsp+208h+var_160]; this
0x180320abf  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x180320ac4  nop
0x180320ac5  lea     rcx, [rsp+208h+var_128]; this
0x180320acd  call    ??1XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade(void)
0x180320ad2  nop
0x180320ad3  lea     rcx, [rsp+208h+var_78]
0x180320adb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180320ae0  mov     eax, ebx
0x180320ae2  jmp     loc_180321127
0x180320ae7  mov     r8d, [rsp+208h+var_1D4]
0x180320aec  mov     rdx, rbx
0x180320aef  lea     rcx, [rsp+208h+var_178]
0x180320af7  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEAA@PEBW4byte@2@_K@Z; gsl::span<gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(gsl::byte const *,unsigned __int64)
0x180320afc  lea     rax, aChangestamp; "changestamp"
0x180320b03  mov     qword ptr [rsp+208h+var_D8], rax
0x180320b0b  mov     qword ptr [rsp+208h+var_D8+8], 0Bh
0x180320b17  lea     r12, aInfo_0; "info"
0x180320b1e  mov     [rsp+208h+var_188], r12
0x180320b26  mov     esi, 4
0x180320b2b  mov     [rsp+208h+var_180], rsi
0x180320b33  mov     byte ptr [rsp+208h+var_1E8], dil
0x180320b38  lea     r9, [rsp+208h+var_1B8]
0x180320b3d  lea     r8, [rsp+208h+var_D8]
0x180320b45  lea     rdx, [rsp+208h+var_188]
0x180320b4d  lea     rcx, [rsp+208h+var_128]
0x180320b55  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x180320b5a  lea     rax, aWnfmessagesize; "wnfmessagesize"
0x180320b61  mov     qword ptr [rsp+208h+var_D8], rax
0x180320b69  mov     qword ptr [rsp+208h+var_D8+8], 0Eh
0x180320b75  mov     [rsp+208h+var_188], r12
0x180320b7d  mov     [rsp+208h+var_180], rsi
0x180320b85  mov     byte ptr [rsp+208h+var_1E8], dil; int
0x180320b8a  lea     r9, [rsp+208h+var_1D4]
0x180320b8f  lea     r8, [rsp+208h+var_D8]
0x180320b97  lea     rdx, [rsp+208h+var_188]
0x180320b9f  lea     rcx, [rsp+208h+var_128]
0x180320ba7  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x180320bac  lea     rdx, [rsp+208h+var_D8]
0x180320bb4  cmp     [r13+80h], dil
0x180320bbb  jz      loc_180320C4B
0x180320bc1  movaps  xmm0, [rsp+208h+var_178]
0x180320bc9  movdqa  [rsp+208h+var_D8], xmm0
0x180320bd2  lea     rcx, [rsp+208h+StringSid]
0x180320bda  call    ?ConvertBufferToHexString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; Microsoft::Diagnostics::Utils::String::ConvertBufferToHexString(gsl::span<gsl::byte const,-1>)
0x180320bdf  nop
0x180320be0  lea     rax, aWnfhex; "wnfhex"
0x180320be7  mov     qword ptr [rsp+208h+var_D8], rax
0x180320bef  mov     qword ptr [rsp+208h+var_D8+8], 6
0x180320bfb  mov     qword ptr [rsp+208h+var_178], r12
0x180320c03  mov     qword ptr [rsp+208h+var_178+8], rsi
0x180320c0b  lea     r9, [rsp+208h+StringSid]
0x180320c13  lea     r8, [rsp+208h+var_D8]
0x180320c1b  lea     rdx, [rsp+208h+var_178]
0x180320c23  lea     rcx, [rsp+208h+var_128]
0x180320c2b  call    ??$WriteInfoElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(std::wstring_view,std::wstring_view,std::wstring const &,bool)
0x180320c30  nop
0x180320c31  lea     rcx, [rsp+208h+StringSid]
0x180320c39  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180320c3e  mov     r13, [rsp+208h+var_168]
0x180320c46  jmp     loc_180320F82
0x180320c4b  mov     rbx, [r13+88h]
0x180320c52  mov     [rsp+208h+var_198], rbx
0x180320c57  mov     r15d, edi
0x180320c5a  mov     [rsp+208h+var_1D0], edi
0x180320c5e  lea     rax, aWnfstructure; "wnfstructure"
0x180320c65  mov     [rsp+208h+var_188], rax
0x180320c6d  mov     [rsp+208h+var_180], 0Ch
0x180320c79  lea     r8, [rsp+208h+var_188]
0x180320c81  lea     rcx, [rsp+208h+var_128]
0x180320c89  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x180320c8e  nop
0x180320c8f  lea     r14, [r13+90h]
0x180320c96  cmp     r15d, dword ptr [rsp+208h+var_178]
0x180320c9e  jnb     loc_180320E3E
  ... truncated ...
```

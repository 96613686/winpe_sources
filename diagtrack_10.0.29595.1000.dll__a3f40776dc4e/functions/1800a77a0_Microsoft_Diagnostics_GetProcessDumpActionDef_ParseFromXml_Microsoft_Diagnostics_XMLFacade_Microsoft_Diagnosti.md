# Microsoft::Diagnostics::GetProcessDumpActionDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1800a77a0`
- end: `0x1800a8191`
- name: `?ParseFromXml@GetProcessDumpActionDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `2545`
- prototype: `int(Microsoft::Diagnostics::GetProcessDumpActionDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18002b318`
- `0x18002cae0`
- `0x18002df00`
- `0x180037b40`
- `0x180040558`
- `0x180064e8c`
- `0x1800653d0`
- `0x18008b254`
- `0x18009dec0`
- `0x1800a0558`
- `0x1800a3760`
- `0x1800a3d14`
- `0x1800a6438`
- `0x1800a658c`
- `0x1800a77a0`
- `0x1801b7bd0`
- `0x180202eb4`
- `0x18020aac0`
- `0x18020db1c`
- `0x18020db84`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7973`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7ac8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7bd8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7cfb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7e15`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7f34`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7973`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7ac8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7bd8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7cfb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7e15`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a7f34`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x1800a7fd3`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x1800a7fd3`

## string_xrefs

- `0x1800a789f`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7915`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a79f6`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7a62`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7b06`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7b72`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7c16`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7c8b`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7d39`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7dae`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7e53`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7ec8`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7f80`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7ff8`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a805f`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a809e`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a80f4`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a8154`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800a7858`: `dbghelp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetProcessDumpActionDef::ParseFromXml(
        Microsoft::Diagnostics::GetProcessDumpActionDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // r10
  __int64 v11; // rcx
  unsigned int v12; // ebx
  int v14; // r12d
  int v15; // r15d
  int v16; // r13d
  int v17; // r14d
  unsigned int Element; // eax
  unsigned int v19; // ebx
  int CurrentElementName; // eax
  unsigned int v21; // ebx
  _QWORD *v22; // rdx
  int v23; // ebx
  __int64 v24; // r8
  int InnerText; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  _QWORD *v29; // rdx
  int v30; // ebx
  __int64 v31; // r8
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // eax
  unsigned int v35; // ebx
  _QWORD *v36; // rdx
  int v37; // ebx
  __int64 v38; // r8
  int v39; // eax
  unsigned int v40; // ebx
  int v41; // eax
  unsigned int v42; // ebx
  _QWORD *v43; // rdx
  int v44; // ebx
  __int64 v45; // r8
  int v46; // eax
  unsigned int v47; // ebx
  int v48; // eax
  unsigned int v49; // ebx
  _QWORD *v50; // rdx
  int v51; // ebx
  __int64 v52; // r8
  int v53; // eax
  unsigned int v54; // ebx
  int v55; // eax
  unsigned int v56; // ebx
  _QWORD *v57; // rdx
  int v58; // ebx
  __int64 v59; // r8
  int v60; // eax
  unsigned int v61; // ebx
  const wchar_t *v62; // rcx
  int v63; // eax
  unsigned int v64; // ebx
  int v65; // eax
  unsigned int v66; // ebx
  int v67; // [rsp+20h] [rbp-118h] BYREF
  int v68; // [rsp+24h] [rbp-114h]
  int v69; // [rsp+2Ch] [rbp-10Ch]
  __int64 v70; // [rsp+30h] [rbp-108h] BYREF
  const wchar_t *v71; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v72; // [rsp+48h] [rbp-F0h]
  struct Microsoft::Diagnostics::ScenarioParsingState *v73; // [rsp+50h] [rbp-E8h]
  _QWORD v74[2]; // [rsp+60h] [rbp-D8h] BYREF
  _QWORD v75[2]; // [rsp+70h] [rbp-C8h] BYREF
  _QWORD v76[2]; // [rsp+80h] [rbp-B8h] BYREF
  _QWORD v77[2]; // [rsp+90h] [rbp-A8h] BYREF
  _QWORD v78[2]; // [rsp+A0h] [rbp-98h] BYREF
  _QWORD v79[2]; // [rsp+B0h] [rbp-88h] BYREF
  unsigned __int64 v80; // [rsp+C0h] [rbp-78h]
  unsigned __int64 v81; // [rsp+C8h] [rbp-70h]
  wchar_t *String[2]; // [rsp+D0h] [rbp-68h] BYREF
  unsigned __int64 v83; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v73 = a3;
  Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(
    &v67,
    *((unsigned __int16 *)this + 60));
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v70, (char *)a3 + 112, (unsigned __int16)v67);
  v9 = std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(v70, v6, v7, v8);
  std::wstring::_Assign<wchar_t>(v9 + 8, v10, *((_QWORD *)this + 13));
  if ( dword_180467304 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_180467304);
    if ( dword_180467304 == -1 )
    {
      v71 = L"dbghelp.dll";
      v72 = std::_WChar_traits<wchar_t>::length(L"dbghelp.dll");
      LODWORD(dword_180467308) = Microsoft::Diagnostics::GetProcessDumpActionDef::CheckModuleExists(v11, &v71);
      Init_thread_footer(&dword_180467304);
    }
  }
  v12 = (unsigned int)dword_180467308;
  if ( (int)dword_180467308 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
      (const char *)(unsigned int)dword_180467308,
      v67);
    return v12;
  }
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v67 = 0;
  v69 = 0;
  v68 = 0;
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    v19 = Element;
    if ( Element )
      break;
    std::wstring::wstring(v79);
    CurrentElementName = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v79);
    v21 = CurrentElementName;
    if ( CurrentElementName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
        (const char *)(unsigned int)CurrentElementName,
        v67);
      std::wstring::_Tidy_deallocate(v79);
      return v21;
    }
    v22 = v79;
    if ( v81 > 7 )
      v22 = (_QWORD *)v79[0];
    v23 = v80;
    v24 = v80;
    if ( v80 >= 0xB )
      v24 = 11;
    if ( !(unsigned int)_o__wcsnicmp(L"processname", v22, v24) && v23 == 11 )
    {
      *(_OWORD *)String = *(_OWORD *)&off_18036CEA0;
      v71 = &Src;
      v72 = std::_WChar_traits<wchar_t>::length(&Src);
      Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v71, String, (char *)this + 168);
      InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 136);
      v26 = InnerText;
      if ( InnerText < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF0,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
          (const char *)(unsigned int)InnerText,
          v67);
        std::wstring::_Tidy_deallocate(v79);
        return v26;
      }
      v74[0] = L" \n\r\t";
      v74[1] = std::_WChar_traits<wchar_t>::length(L" \n\r\t");
      Microsoft::Diagnostics::Utils::String::Trim((char *)this + 136, v74);
      *((_BYTE *)this + 128) = 0;
      v27 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF4,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
          (const char *)(unsigned int)v27,
          v67);
        std::wstring::_Tidy_deallocate(v79);
        return v28;
      }
      ++v14;
LABEL_65:
      v17 = v67;
      goto LABEL_83;
    }
    v29 = v79;
    if ( v81 > 7 )
      v29 = (_QWORD *)v79[0];
    v30 = v80;
    v31 = v80;
    if ( v80 >= 9 )
      v31 = 9;
    if ( !(unsigned int)_o__wcsnicmp(L"processid", v29, v31) && v30 == 9 )
    {
      v32 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 136);
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
          (const char *)(unsigned int)v32,
          v67);
        std::wstring::_Tidy_deallocate(v79);
        return v33;
      }
      v75[0] = L" \n\r\t";
      v75[1] = std::_WChar_traits<wchar_t>::length(L" \n\r\t");
      Microsoft::Diagnostics::Utils::String::Trim((char *)this + 136, v75);
      *((_BYTE *)this + 128) = 1;
      v34 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
          (const char *)(unsigned int)v34,
          v67);
        std::wstring::_Tidy_deallocate(v79);
        return v35;
      }
      ++v16;
      goto LABEL_65;
    }
    v36 = v79;
    if ( v81 > 7 )
      v36 = (_QWORD *)v79[0];
    v37 = v80;
    v38 = v80;
    if ( v80 >= 0xB )
      v38 = 11;
    if ( (unsigned int)_o__wcsnicmp(L"servicename", v36, v38) || v37 != 11 )
    {
      v43 = v79;
      if ( v81 > 7 )
        v43 = (_QWORD *)v79[0];
      v44 = v80;
      v45 = v80;
      if ( v80 >= 0xC )
        v45 = 12;
      if ( !(unsigned int)_o__wcsnicmp(L"serviceregex", v43, v45) && v44 == 12 )
      {
        v46 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 136);
        v47 = v46;
        if ( v46 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10E,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v46,
            v67);
          std::wstring::_Tidy_deallocate(v79);
          return v47;
        }
        v77[0] = L" \n\r\t";
        v77[1] = std::_WChar_traits<wchar_t>::length(L" \n\r\t");
        Microsoft::Diagnostics::Utils::String::Trim((char *)this + 136, v77);
        *((_BYTE *)this + 128) = 3;
        v48 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v49 = v48;
        if ( v48 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x112,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v48,
            v67);
          std::wstring::_Tidy_deallocate(v79);
          return v49;
        }
        ++v69;
        goto LABEL_65;
      }
      v50 = v79;
      if ( v81 > 7 )
        v50 = (_QWORD *)v79[0];
      v51 = v80;
      v52 = v80;
      if ( v80 >= 0xB )
        v52 = 11;
      if ( !(unsigned int)_o__wcsnicmp(L"moduleregex", v50, v52) && v51 == 11 )
      {
        v53 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 136);
        v54 = v53;
        if ( v53 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x118,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v53,
            v67);
          std::wstring::_Tidy_deallocate(v79);
          return v54;
        }
        v78[0] = L" \n\r\t";
        v78[1] = std::_WChar_traits<wchar_t>::length(L" \n\r\t");
        Microsoft::Diagnostics::Utils::String::Trim((char *)this + 136, v78);
        *((_BYTE *)this + 128) = 4;
        v55 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v56 = v55;
        if ( v55 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v55,
            v67);
          std::wstring::_Tidy_deallocate(v79);
          return v56;
        }
        ++v68;
        goto LABEL_65;
      }
      v57 = v79;
      if ( v81 > 7 )
        v57 = (_QWORD *)v79[0];
      v58 = v80;
      v59 = v80;
      if ( v80 >= 4 )
        v59 = 4;
      if ( (unsigned int)_o__wcsnicmp(L"type", v57, v59) || v58 != 4 )
      {
        if ( *((_BYTE *)v73 + 152) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)0x87C52407LL,
            v67);
          std::wstring::_Tidy_deallocate(v79);
          return 2277843975LL;
        }
        v65 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v66 = v65;
        if ( v65 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x132,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v65,
            v67);
          std::wstring::_Tidy_deallocate(v79);
          return v66;
        }
      }
      else
      {
        std::wstring::wstring(String);
        v60 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, String);
        v61 = v60;
        if ( v60 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x123,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v60,
            v67);
          std::wstring::_Tidy_deallocate(String);
          std::wstring::_Tidy_deallocate(v79);
          return v61;
        }
        v62 = (const wchar_t *)String;
        if ( v83 > 7 )
          v62 = String[0];
        *((_DWORD *)this + 50) = _wcstoi64(v62, 0, 0);
        v63 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v64 = v63;
        if ( v63 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x127,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v63,
            v67);
          std::wstring::_Tidy_deallocate(String);
          std::wstring::_Tidy_deallocate(v79);
          return v64;
        }
        ++v15;
        std::wstring::_Tidy_deallocate(String);
      }
    }
    else
    {
      v39 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 136);
      v40 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x104,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
          (const char *)(unsigned int)v39,
          v67);
        std::wstring::_Tidy_deallocate(v79);
        return v40;
      }
      v76[0] = L" \n\r\t";
      v76[1] = std::_WChar_traits<wchar_t>::length(L" \n\r\t");
      Microsoft::Diagnostics::Utils::String::Trim((char *)this + 136, v76);
      *((_BYTE *)this + 128) = 2;
      v41 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v42 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x108,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
          (const char *)(unsigned int)v41,
          v67);
        std::wstring::_Tidy_deallocate(v79);
        return v42;
      }
      v17 = ++v67;
    }
LABEL_83:
    std::wstring::_Tidy_deallocate(v79);
  }
  if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
  {
    if ( v15 == 1 && v14 + v16 + v17 + v68 + v69 == 1 )
    {
      (*(void (__fastcall **)(Microsoft::Diagnostics::GetProcessDumpActionDef *, _QWORD))(*(_QWORD *)this + 16LL))(
        this,
        0);
      std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v70);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
        (const char *)0x87C52402LL,
        v67);
      return 2277843970LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
      (const char *)Element,
      v67);
    return v19;
  }
}

```

## disassembly

```asm
0x1800a77a0  push    rbx
0x1800a77a2  push    rsi
0x1800a77a3  push    rdi
0x1800a77a4  push    r12
0x1800a77a6  push    r13
0x1800a77a8  push    r14
0x1800a77aa  push    r15
0x1800a77ac  sub     rsp, 100h
0x1800a77b3  mov     rax, cs:__security_cookie
0x1800a77ba  xor     rax, rsp
0x1800a77bd  mov     [rsp+138h+var_48], rax
0x1800a77c5  mov     rbx, r8
0x1800a77c8  mov     [rsp+138h+var_E8], rbx
0x1800a77cd  mov     rsi, rdx
0x1800a77d0  mov     rdi, rcx
0x1800a77d3  movzx   edx, word ptr [rcx+78h]
0x1800a77d7  lea     rcx, [rsp+138h+var_118]
0x1800a77dc  call    ?ConvertActionTypeToScenarioDbObjectType@TypeToScenarioDbObjectTypeConverter@Diagnostics@Microsoft@@SA?AVScenarioDbObjectType@23@VActionType@23@@Z; Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(Microsoft::Diagnostics::ActionType)
0x1800a77e1  lea     rdx, [rbx+70h]
0x1800a77e5  movzx   r8d, word ptr [rsp+138h+var_118]
0x1800a77eb  lea     rcx, [rsp+138h+var_108]
0x1800a77f0  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1800a77f5  cmp     qword ptr [rdi+70h], 7
0x1800a77fa  jbe     short loc_1800A7802
0x1800a77fc  mov     r10, [rdi+58h]
0x1800a7800  jmp     short loc_1800A7806
0x1800a7802  lea     r10, [rdi+58h]
0x1800a7806  mov     rcx, [rsp+138h+var_108]
0x1800a780b  call    ?top@?$stack@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$deque@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@@2@@2@@std@@QEAAAEAV?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@2@XZ; std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(void)
0x1800a7810  lea     rcx, [rax+8]
0x1800a7814  mov     r8, [rdi+68h]
0x1800a7818  mov     rdx, r10
0x1800a781b  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800a7820  mov     ecx, cs:_tls_index
0x1800a7826  mov     rax, gs:58h
0x1800a782f  mov     edx, 10h
0x1800a7834  mov     rax, [rax+rcx*8]
0x1800a7838  mov     ecx, [rdx+rax]
0x1800a783b  cmp     cs:dword_180467304, ecx
0x1800a7841  jle     short loc_1800A788A
0x1800a7843  lea     rcx, dword_180467304
0x1800a784a  call    _Init_thread_header
0x1800a784f  cmp     cs:dword_180467304, 0FFFFFFFFh
0x1800a7856  jnz     short loc_1800A788A
0x1800a7858  lea     rcx, aDbghelpDll; "dbghelp.dll"
0x1800a785f  mov     [rsp+138h+var_F8], rcx
0x1800a7864  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a7869  mov     [rsp+138h+var_F0], rax
0x1800a786e  lea     rdx, [rsp+138h+var_F8]
0x1800a7873  call    ?CheckModuleExists@GetProcessDumpActionDef@Diagnostics@Microsoft@@AEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::GetProcessDumpActionDef::CheckModuleExists(std::wstring_view)
0x1800a7878  mov     cs:dword_180467308, eax
0x1800a787e  lea     rcx, dword_180467304
0x1800a7885  call    _Init_thread_footer
0x1800a788a  mov     ebx, cs:dword_180467308
0x1800a7890  test    ebx, ebx
0x1800a7892  jns     short loc_1800A78B7
0x1800a7894  mov     rcx, [rsp+138h]; this
0x1800a789c  mov     r9d, ebx; char *
0x1800a789f  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1800a78a6  mov     edx, 0DFh; void *
0x1800a78ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a78b0  mov     eax, ebx
0x1800a78b2  jmp     loc_1800A816D
0x1800a78b7  xor     r12d, r12d
0x1800a78ba  xor     r15d, r15d
0x1800a78bd  xor     r13d, r13d
0x1800a78c0  xor     r14d, r14d
0x1800a78c3  mov     [rsp+138h+var_118], r14d; int
0x1800a78c8  xor     eax, eax
0x1800a78ca  mov     [rsp+138h+var_10C], eax
0x1800a78ce  xor     ecx, ecx
0x1800a78d0  mov     [rsp+138h+var_114], ecx
0x1800a78d4  mov     rcx, rsi; this
0x1800a78d7  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1800a78dc  mov     ebx, eax
0x1800a78de  test    eax, eax
0x1800a78e0  jnz     loc_1800A80D6
0x1800a78e6  lea     rcx, [rsp+138h+var_88]; void *
0x1800a78ee  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a78f3  nop
0x1800a78f4  lea     rdx, [rsp+138h+var_88]
0x1800a78fc  mov     rcx, rsi
0x1800a78ff  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1800a7904  mov     ebx, eax
0x1800a7906  test    eax, eax
0x1800a7908  jns     short loc_1800A793B
0x1800a790a  mov     rcx, [rsp+138h]; this
0x1800a7912  mov     r9d, eax; char *
0x1800a7915  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1800a791c  mov     edx, 0E8h; void *
0x1800a7921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7926  nop
0x1800a7927  lea     rcx, [rsp+138h+var_88]
0x1800a792f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7934  mov     eax, ebx
0x1800a7936  jmp     loc_1800A816D
0x1800a793b  lea     rdx, [rsp+138h+var_88]
0x1800a7943  cmp     [rsp+138h+var_70], 7
0x1800a794c  cmova   rdx, [rsp+138h+var_88]
0x1800a7955  mov     rbx, [rsp+138h+var_78]
0x1800a795d  mov     r8, rbx
0x1800a7960  mov     eax, 0Bh
0x1800a7965  cmp     rbx, rax
0x1800a7968  cmovnb  r8, rax
0x1800a796c  mov     rcx, cs:off_18036CCB8; "processname"
0x1800a7973  call    cs:__imp__o__wcsnicmp
0x1800a7979  test    eax, eax
0x1800a797b  jnz     loc_1800A7A90
0x1800a7981  mov     eax, 0Bh
0x1800a7986  cmp     eax, ebx
0x1800a7988  jnz     loc_1800A7A90
0x1800a798e  movups  xmm0, xmmword ptr cs:off_18036CEA0; "prioritypidlist"
0x1800a7995  movdqu  xmmword ptr [rsp+138h+String], xmm0
0x1800a799e  lea     rax, Src
0x1800a79a5  mov     [rsp+138h+var_F8], rax
0x1800a79aa  mov     rcx, rax
0x1800a79ad  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a79b2  mov     [rsp+138h+var_F0], rax
0x1800a79b7  lea     r9, [rdi+0A8h]
0x1800a79be  lea     r8, [rsp+138h+String]
0x1800a79c6  lea     rdx, [rsp+138h+var_F8]
0x1800a79cb  mov     rcx, rsi
0x1800a79ce  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800a79d3  lea     r14, [rdi+88h]
0x1800a79da  mov     rdx, r14
0x1800a79dd  mov     rcx, rsi
0x1800a79e0  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a79e5  mov     ebx, eax
0x1800a79e7  test    eax, eax
0x1800a79e9  jns     short loc_1800A7A1C
0x1800a79eb  mov     rcx, [rsp+138h]; this
0x1800a79f3  mov     r9d, eax; char *
0x1800a79f6  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1800a79fd  mov     edx, 0F0h; void *
0x1800a7a02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7a07  nop
0x1800a7a08  lea     rcx, [rsp+138h+var_88]
0x1800a7a10  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7a15  mov     eax, ebx
0x1800a7a17  jmp     loc_1800A816D
0x1800a7a1c  lea     rax, asc_1803948B8; " \n\r\t"
0x1800a7a23  mov     [rsp+138h+var_D8], rax
0x1800a7a28  mov     rcx, rax
0x1800a7a2b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a7a30  mov     [rsp+138h+var_D0], rax
0x1800a7a35  lea     rdx, [rsp+138h+var_D8]
0x1800a7a3a  mov     rcx, r14
0x1800a7a3d  call    ?Trim@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::String::Trim(std::wstring &,std::wstring_view)
0x1800a7a42  mov     byte ptr [rdi+80h], 0
0x1800a7a49  mov     rcx, rsi; this
0x1800a7a4c  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a7a51  mov     ebx, eax
0x1800a7a53  test    eax, eax
0x1800a7a55  jns     short loc_1800A7A88
0x1800a7a57  mov     rcx, [rsp+138h]; this
0x1800a7a5f  mov     r9d, eax; char *
0x1800a7a62  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1800a7a69  mov     edx, 0F4h; void *
0x1800a7a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7a73  nop
0x1800a7a74  lea     rcx, [rsp+138h+var_88]
0x1800a7a7c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7a81  mov     eax, ebx
0x1800a7a83  jmp     loc_1800A816D
0x1800a7a88  inc     r12d
0x1800a7a8b  jmp     loc_1800A7EF2
0x1800a7a90  lea     rdx, [rsp+138h+var_88]
0x1800a7a98  cmp     [rsp+138h+var_70], 7
0x1800a7aa1  cmova   rdx, [rsp+138h+var_88]
0x1800a7aaa  mov     rbx, [rsp+138h+var_78]
0x1800a7ab2  mov     r8, rbx
0x1800a7ab5  mov     eax, 9
0x1800a7aba  cmp     rbx, rax
0x1800a7abd  cmovnb  r8, rax
0x1800a7ac1  mov     rcx, cs:off_18036CCC8; "processid"
0x1800a7ac8  call    cs:__imp__o__wcsnicmp
0x1800a7ace  test    eax, eax
0x1800a7ad0  jnz     loc_1800A7BA0
0x1800a7ad6  mov     eax, 9
0x1800a7adb  cmp     eax, ebx
0x1800a7add  jnz     loc_1800A7BA0
0x1800a7ae3  lea     r14, [rdi+88h]
0x1800a7aea  mov     rdx, r14
0x1800a7aed  mov     rcx, rsi
0x1800a7af0  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a7af5  mov     ebx, eax
0x1800a7af7  test    eax, eax
0x1800a7af9  jns     short loc_1800A7B2C
0x1800a7afb  mov     rcx, [rsp+138h]; this
0x1800a7b03  mov     r9d, eax; char *
0x1800a7b06  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1800a7b0d  mov     edx, 0FAh; void *
0x1800a7b12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7b17  nop
0x1800a7b18  lea     rcx, [rsp+138h+var_88]
0x1800a7b20  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7b25  mov     eax, ebx
0x1800a7b27  jmp     loc_1800A816D
0x1800a7b2c  lea     rax, asc_1803948B8; " \n\r\t"
0x1800a7b33  mov     [rsp+138h+var_C8], rax
0x1800a7b38  mov     rcx, rax
0x1800a7b3b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a7b40  mov     [rsp+138h+var_C0], rax
0x1800a7b45  lea     rdx, [rsp+138h+var_C8]
0x1800a7b4a  mov     rcx, r14
0x1800a7b4d  call    ?Trim@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::String::Trim(std::wstring &,std::wstring_view)
0x1800a7b52  mov     byte ptr [rdi+80h], 1
0x1800a7b59  mov     rcx, rsi; this
0x1800a7b5c  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a7b61  mov     ebx, eax
0x1800a7b63  test    eax, eax
0x1800a7b65  jns     short loc_1800A7B98
0x1800a7b67  mov     rcx, [rsp+138h]; this
0x1800a7b6f  mov     r9d, eax; char *
0x1800a7b72  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1800a7b79  mov     edx, 0FEh; void *
0x1800a7b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7b83  nop
0x1800a7b84  lea     rcx, [rsp+138h+var_88]
0x1800a7b8c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7b91  mov     eax, ebx
0x1800a7b93  jmp     loc_1800A816D
0x1800a7b98  inc     r13d
0x1800a7b9b  jmp     loc_1800A7EF2
0x1800a7ba0  lea     rdx, [rsp+138h+var_88]
0x1800a7ba8  cmp     [rsp+138h+var_70], 7
0x1800a7bb1  cmova   rdx, [rsp+138h+var_88]
0x1800a7bba  mov     rbx, [rsp+138h+var_78]
0x1800a7bc2  mov     r8, rbx
0x1800a7bc5  mov     eax, 0Bh
0x1800a7bca  cmp     rbx, rax
0x1800a7bcd  cmovnb  r8, rax
0x1800a7bd1  mov     rcx, cs:off_18036CCF8; "servicename"
0x1800a7bd8  call    cs:__imp__o__wcsnicmp
0x1800a7bde  test    eax, eax
0x1800a7be0  jnz     loc_1800A7CC3
0x1800a7be6  mov     eax, 0Bh
0x1800a7beb  cmp     eax, ebx
0x1800a7bed  jnz     loc_1800A7CC3
0x1800a7bf3  lea     r14, [rdi+88h]
0x1800a7bfa  mov     rdx, r14
0x1800a7bfd  mov     rcx, rsi
0x1800a7c00  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a7c05  mov     ebx, eax
0x1800a7c07  test    eax, eax
0x1800a7c09  jns     short loc_1800A7C3C
0x1800a7c0b  mov     rcx, [rsp+138h]; this
0x1800a7c13  mov     r9d, eax; char *
0x1800a7c16  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1800a7c1d  mov     edx, 104h; void *
0x1800a7c22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7c27  nop
0x1800a7c28  lea     rcx, [rsp+138h+var_88]
0x1800a7c30  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7c35  mov     eax, ebx
0x1800a7c37  jmp     loc_1800A816D
0x1800a7c3c  lea     rax, asc_1803948B8; " \n\r\t"
0x1800a7c43  mov     [rsp+138h+var_B8], rax
0x1800a7c4b  mov     rcx, rax
0x1800a7c4e  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a7c53  mov     [rsp+138h+var_B0], rax
0x1800a7c5b  lea     rdx, [rsp+138h+var_B8]
0x1800a7c63  mov     rcx, r14
0x1800a7c66  call    ?Trim@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::String::Trim(std::wstring &,std::wstring_view)
0x1800a7c6b  mov     byte ptr [rdi+80h], 2
0x1800a7c72  mov     rcx, rsi; this
0x1800a7c75  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a7c7a  mov     ebx, eax
0x1800a7c7c  test    eax, eax
0x1800a7c7e  jns     short loc_1800A7CB1
0x1800a7c80  mov     rcx, [rsp+138h]; this
0x1800a7c88  mov     r9d, eax; char *
0x1800a7c8b  lea     r8, aOnecoreBaseTel_161; "onecore\\base\\telemetry\\utc\\service"...
0x1800a7c92  mov     edx, 108h; void *
0x1800a7c97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7c9c  nop
0x1800a7c9d  lea     rcx, [rsp+138h+var_88]
0x1800a7ca5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7caa  mov     eax, ebx
0x1800a7cac  jmp     loc_1800A816D
0x1800a7cb1  mov     r14d, [rsp+138h+var_118]
0x1800a7cb6  inc     r14d
0x1800a7cb9  mov     [rsp+138h+var_118], r14d
0x1800a7cbe  jmp     loc_1800A80C4
0x1800a7cc3  lea     rdx, [rsp+138h+var_88]
0x1800a7ccb  cmp     [rsp+138h+var_70], 7
0x1800a7cd4  cmova   rdx, [rsp+138h+var_88]
0x1800a7cdd  mov     rbx, [rsp+138h+var_78]
0x1800a7ce5  mov     r8, rbx
0x1800a7ce8  mov     eax, 0Ch
0x1800a7ced  cmp     rbx, rax
0x1800a7cf0  cmovnb  r8, rax
0x1800a7cf4  mov     rcx, cs:off_18036CCD8; "serviceregex"
0x1800a7cfb  call    cs:__imp__o__wcsnicmp
0x1800a7d01  test    eax, eax
0x1800a7d03  jnz     loc_1800A7DDD
0x1800a7d09  mov     eax, 0Ch
0x1800a7d0e  cmp     eax, ebx
0x1800a7d10  jnz     loc_1800A7DDD
0x1800a7d16  lea     r14, [rdi+88h]
  ... truncated ...
```

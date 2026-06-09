# Microsoft::Diagnostics::GetRegKeyActionDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x18012a250`
- end: `0x18012a97f`
- name: `?ParseFromXml@GetRegKeyActionDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `1839`
- prototype: `int(Microsoft::Diagnostics::GetRegKeyActionDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002b318`
- `0x18002cae0`
- `0x18002df00`
- `0x180037b40`
- `0x180040558`
- `0x180064e8c`
- `0x1800653d0`
- `0x18008b254`
- `0x18009c8c0`
- `0x18009dec0`
- `0x1800a0558`
- `0x1800a3760`
- `0x1800a3d14`
- `0x1800a3f5c`
- `0x1800a6438`
- `0x1800a658c`
- `0x18012a250`
- `0x1801b7bd0`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012a425`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012a5e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012a705`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012a425`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012a5e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012a705`

## string_xrefs

- `0x18012a3b9`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a471`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a4f2`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a54d`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a61e`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a691`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a743`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a7b6`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a815`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a862`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a8c6`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`
- `0x18012a934`: `onecore\base\telemetry\utc\service\scenarios\actions\getregkeyaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetRegKeyActionDef::ParseFromXml(
        Microsoft::Diagnostics::GetRegKeyActionDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // r10
  _WORD *v12; // rax
  char v13; // al
  int v14; // r15d
  int v15; // r13d
  int v16; // r12d
  unsigned int Element; // eax
  unsigned int v18; // edi
  int CurrentElementName; // eax
  unsigned int v20; // edi
  _QWORD *v22; // rdx
  int v23; // edi
  __int64 v24; // r8
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // rdx
  int HiveFromString; // eax
  unsigned int v29; // edi
  int v30; // eax
  unsigned int v31; // edi
  _QWORD *v32; // rdx
  int v33; // edi
  __int64 v34; // r8
  int InnerText; // eax
  unsigned int v36; // edi
  int v37; // eax
  unsigned int v38; // edi
  _QWORD *v39; // rdx
  int v40; // edi
  __int64 v41; // r8
  int v42; // eax
  unsigned int v43; // edi
  int v44; // eax
  unsigned int v45; // edi
  int v46; // eax
  unsigned int v47; // edi
  int v48[4]; // [rsp+20h] [rbp-108h] BYREF
  __int128 v49; // [rsp+30h] [rbp-F8h] BYREF
  __int128 v50; // [rsp+40h] [rbp-E8h] BYREF
  struct Microsoft::Diagnostics::ScenarioParsingState *v51; // [rsp+50h] [rbp-D8h]
  _QWORD v52[2]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v53[16]; // [rsp+70h] [rbp-B8h] BYREF
  _QWORD v54[2]; // [rsp+80h] [rbp-A8h] BYREF
  unsigned __int64 v55; // [rsp+90h] [rbp-98h]
  unsigned __int64 v56; // [rsp+98h] [rbp-90h]
  _QWORD v57[4]; // [rsp+A0h] [rbp-88h] BYREF
  _BYTE v58[32]; // [rsp+C0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v51 = a3;
  Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(
    v48,
    *((unsigned __int16 *)this + 60));
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v49, (char *)a3 + 112, LOWORD(v48[0]));
  v6 = v49;
  v10 = std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(v49, v7, v8, v9);
  std::wstring::_Assign<wchar_t>(v10 + 8, v11, *((_QWORD *)this + 13));
  std::wstring::wstring(v57);
  v50 = *(_OWORD *)&off_180370110;
  *(_QWORD *)&v49 = &Src;
  *((_QWORD *)&v49 + 1) = std::_WChar_traits<wchar_t>::length(&Src);
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v49, &v50, v57) == 1 )
    goto LABEL_9;
  v12 = v57;
  if ( v57[3] > 7u )
    v12 = (_WORD *)v57[0];
  if ( v57[2] && (*v12 == 84 || *v12 == 49 || *v12 == 116) )
    v13 = 1;
  else
LABEL_9:
    v13 = 0;
  v14 = 0;
  v48[0] = 0;
  v15 = 0;
  v16 = 0;
  *((_BYTE *)this + 200) = v13;
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    v18 = Element;
    if ( Element )
      break;
    std::wstring::wstring(v54);
    CurrentElementName = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v54);
    v20 = CurrentElementName;
    if ( CurrentElementName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x291,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
        (const char *)(unsigned int)CurrentElementName,
        v48[0]);
      std::wstring::_Tidy_deallocate(v54);
      std::wstring::_Tidy_deallocate(v57);
      return v20;
    }
    v22 = v54;
    if ( v56 > 7 )
      v22 = (_QWORD *)v54[0];
    v23 = v55;
    v24 = v55;
    if ( v55 >= 4 )
      v24 = 4;
    if ( (unsigned int)_o__wcsnicmp(L"hive", v22, v24) || v23 != 4 )
    {
      v32 = v54;
      if ( v56 > 7 )
        v32 = (_QWORD *)v54[0];
      v33 = v55;
      v34 = v55;
      if ( v55 >= 7 )
        v34 = 7;
      if ( !(unsigned int)_o__wcsnicmp(L"keyname", v32, v34) && v33 == 7 )
      {
        InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 128);
        v36 = InnerText;
        if ( InnerText < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x29E,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
            (const char *)(unsigned int)InnerText,
            v48[0]);
          std::wstring::_Tidy_deallocate(v54);
          std::wstring::_Tidy_deallocate(v57);
          return v36;
        }
        v52[0] = L" \n\r\t";
        v52[1] = std::_WChar_traits<wchar_t>::length(L" \n\r\t");
        Microsoft::Diagnostics::Utils::String::Trim((char *)this + 128, v52);
        v37 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v38 = v37;
        if ( v37 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2A0,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
            (const char *)(unsigned int)v37,
            v48[0]);
          std::wstring::_Tidy_deallocate(v54);
          std::wstring::_Tidy_deallocate(v57);
          return v38;
        }
        ++v15;
LABEL_49:
        v14 = v48[0];
        goto LABEL_54;
      }
      v39 = v54;
      if ( v56 > 7 )
        v39 = (_QWORD *)v54[0];
      v40 = v55;
      v41 = v55;
      if ( v55 >= 9 )
        v41 = 9;
      if ( !(unsigned int)_o__wcsnicmp(L"valuename", v39, v41) && v40 == 9 )
      {
        v42 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 160);
        v43 = v42;
        if ( v42 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2A6,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
            (const char *)(unsigned int)v42,
            v48[0]);
          std::wstring::_Tidy_deallocate(v54);
          std::wstring::_Tidy_deallocate(v57);
          return v43;
        }
        *(_QWORD *)&v50 = L" \n\r\t";
        *((_QWORD *)&v50 + 1) = std::_WChar_traits<wchar_t>::length(L" \n\r\t");
        Microsoft::Diagnostics::Utils::String::Trim((char *)this + 160, &v50);
        v44 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v45 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2A8,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
            (const char *)(unsigned int)v44,
            v48[0]);
          std::wstring::_Tidy_deallocate(v54);
          std::wstring::_Tidy_deallocate(v57);
          return v45;
        }
        ++v16;
        goto LABEL_49;
      }
      if ( *((_BYTE *)v51 + 152) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B0,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
          (const char *)0x87C52407LL,
          v48[0]);
        std::wstring::_Tidy_deallocate(v54);
        std::wstring::_Tidy_deallocate(v57);
        return 2277843975LL;
      }
      v46 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v47 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B3,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
          (const char *)(unsigned int)v46,
          v48[0]);
        std::wstring::_Tidy_deallocate(v54);
        std::wstring::_Tidy_deallocate(v57);
        return v47;
      }
    }
    else
    {
      std::wstring::wstring(v58);
      v25 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v58);
      v26 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x296,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
          (const char *)(unsigned int)v25,
          v48[0]);
        std::wstring::_Tidy_deallocate(v58);
        std::wstring::_Tidy_deallocate(v54);
        std::wstring::_Tidy_deallocate(v57);
        return v26;
      }
      v49 = *(_OWORD *)std::wstring::operator std::wstring_view(v58, v53);
      LOBYTE(v27) = 1;
      HiveFromString = Microsoft::Diagnostics::Utils::Xml::GetHiveFromString(&v49, v27, (char *)this + 192);
      v29 = HiveFromString;
      if ( HiveFromString < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x297,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
          (const char *)(unsigned int)HiveFromString,
          v48[0]);
        std::wstring::_Tidy_deallocate(v58);
        std::wstring::_Tidy_deallocate(v54);
        std::wstring::_Tidy_deallocate(v57);
        return v29;
      }
      v30 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x298,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
          (const char *)(unsigned int)v30,
          v48[0]);
        std::wstring::_Tidy_deallocate(v58);
        std::wstring::_Tidy_deallocate(v54);
        std::wstring::_Tidy_deallocate(v57);
        return v31;
      }
      v48[0] = ++v14;
      std::wstring::_Tidy_deallocate(v58);
    }
LABEL_54:
    std::wstring::_Tidy_deallocate(v54);
  }
  if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
  {
    if ( v14 == 1 && v15 == 1 && v16 == 1 )
    {
      (*(void (__fastcall **)(Microsoft::Diagnostics::GetRegKeyActionDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
      std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v6);
      std::wstring::_Tidy_deallocate(v57);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BC,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
        (const char *)0x87C52402LL,
        v48[0]);
      std::wstring::_Tidy_deallocate(v57);
      return 2277843970LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getregkeyaction.cpp",
      (const char *)Element,
      v48[0]);
    std::wstring::_Tidy_deallocate(v57);
    return v18;
  }
}

```

## disassembly

```asm
0x18012a250  push    rbx
0x18012a252  push    rsi
0x18012a253  push    rdi
0x18012a254  push    r12
0x18012a256  push    r13
0x18012a258  push    r14
0x18012a25a  push    r15
0x18012a25c  sub     rsp, 0F0h
0x18012a263  mov     rax, cs:__security_cookie
0x18012a26a  xor     rax, rsp
0x18012a26d  mov     [rsp+128h+var_48], rax
0x18012a275  mov     rbx, r8
0x18012a278  mov     [rsp+128h+var_D8], rbx
0x18012a27d  mov     rsi, rdx
0x18012a280  mov     r14, rcx
0x18012a283  movzx   edx, word ptr [rcx+78h]
0x18012a287  lea     rcx, [rsp+128h+var_108]
0x18012a28c  call    ?ConvertActionTypeToScenarioDbObjectType@TypeToScenarioDbObjectTypeConverter@Diagnostics@Microsoft@@SA?AVScenarioDbObjectType@23@VActionType@23@@Z; Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(Microsoft::Diagnostics::ActionType)
0x18012a291  lea     rdx, [rbx+70h]
0x18012a295  movzx   r8d, word ptr [rsp+128h+var_108]
0x18012a29b  lea     rcx, [rsp+128h+var_F8]
0x18012a2a0  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x18012a2a5  mov     edi, 7
0x18012a2aa  cmp     [r14+70h], rdi
0x18012a2ae  jbe     short loc_18012A2B6
0x18012a2b0  mov     r10, [r14+58h]
0x18012a2b4  jmp     short loc_18012A2BA
0x18012a2b6  lea     r10, [r14+58h]
0x18012a2ba  mov     rbx, qword ptr [rsp+128h+var_F8]
0x18012a2bf  mov     rcx, rbx
0x18012a2c2  call    ?top@?$stack@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$deque@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@@2@@2@@std@@QEAAAEAV?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@2@XZ; std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(void)
0x18012a2c7  lea     rcx, [rax+8]
0x18012a2cb  mov     r8, [r14+68h]
0x18012a2cf  mov     rdx, r10
0x18012a2d2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18012a2d7  lea     rcx, [rsp+128h+var_88]; void *
0x18012a2df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012a2e4  nop
0x18012a2e5  movups  xmm0, xmmword ptr cs:off_180370110; "querysecurity"
0x18012a2ec  movdqu  [rsp+128h+var_E8], xmm0
0x18012a2f2  lea     rcx, Src
0x18012a2f9  mov     qword ptr [rsp+128h+var_F8], rcx
0x18012a2fe  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18012a303  mov     qword ptr [rsp+128h+var_F8+8], rax
0x18012a308  lea     r9, [rsp+128h+var_88]
0x18012a310  lea     r8, [rsp+128h+var_E8]
0x18012a315  lea     rdx, [rsp+128h+var_F8]
0x18012a31a  mov     rcx, rsi
0x18012a31d  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18012a322  cmp     eax, 1
0x18012a325  jz      short loc_18012A361
0x18012a327  lea     rax, [rsp+128h+var_88]
0x18012a32f  cmp     [rsp+128h+var_70], rdi
0x18012a337  cmova   rax, [rsp+128h+var_88]
0x18012a340  cmp     [rsp+128h+var_78], 0
0x18012a349  jz      short loc_18012A361
0x18012a34b  cmp     word ptr [rax], 54h ; 'T'
0x18012a34f  jz      short loc_18012A35D
0x18012a351  cmp     word ptr [rax], 31h ; '1'
0x18012a355  jz      short loc_18012A35D
0x18012a357  cmp     word ptr [rax], 74h ; 't'
0x18012a35b  jnz     short loc_18012A361
0x18012a35d  mov     al, 1
0x18012a35f  jmp     short loc_18012A363
0x18012a361  xor     al, al
0x18012a363  xor     r15d, r15d
0x18012a366  mov     [rsp+128h+var_108], r15d; int
0x18012a36b  xor     r13d, r13d
0x18012a36e  xor     r12d, r12d
0x18012a371  mov     [r14+0C8h], al
0x18012a378  mov     rcx, rsi; this
0x18012a37b  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x18012a380  mov     edi, eax
0x18012a382  test    eax, eax
0x18012a384  jnz     loc_18012A8A8
0x18012a38a  lea     rcx, [rsp+128h+var_A8]; void *
0x18012a392  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012a397  nop
0x18012a398  lea     rdx, [rsp+128h+var_A8]
0x18012a3a0  mov     rcx, rsi
0x18012a3a3  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x18012a3a8  mov     edi, eax
0x18012a3aa  test    eax, eax
0x18012a3ac  jns     short loc_18012A3ED
0x18012a3ae  mov     rcx, [rsp+128h]; this
0x18012a3b6  mov     r9d, eax; char *
0x18012a3b9  lea     r8, aOnecoreBaseTel_43; "onecore\\base\\telemetry\\utc\\service"...
0x18012a3c0  mov     edx, 291h; void *
0x18012a3c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a3ca  nop
0x18012a3cb  lea     rcx, [rsp+128h+var_A8]
0x18012a3d3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a3d8  nop
0x18012a3d9  lea     rcx, [rsp+128h+var_88]
0x18012a3e1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a3e6  mov     eax, edi
0x18012a3e8  jmp     loc_18012A95B
0x18012a3ed  lea     rdx, [rsp+128h+var_A8]
0x18012a3f5  cmp     [rsp+128h+var_90], 7
0x18012a3fe  cmova   rdx, [rsp+128h+var_A8]
0x18012a407  mov     rdi, [rsp+128h+var_98]
0x18012a40f  mov     r8, rdi
0x18012a412  mov     eax, 4
0x18012a417  cmp     rdi, rax
0x18012a41a  cmovnb  r8, rax
0x18012a41e  mov     rcx, cs:off_1803700E0; "hive"
0x18012a425  call    cs:__imp__o__wcsnicmp
0x18012a42b  test    eax, eax
0x18012a42d  jnz     loc_18012A5A9
0x18012a433  mov     eax, 4
0x18012a438  sub     eax, edi
0x18012a43a  test    eax, eax
0x18012a43c  jnz     loc_18012A5A9
0x18012a442  lea     rcx, [rsp+128h+var_68]; void *
0x18012a44a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012a44f  nop
0x18012a450  lea     rdx, [rsp+128h+var_68]
0x18012a458  mov     rcx, rsi
0x18012a45b  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18012a460  mov     edi, eax
0x18012a462  test    eax, eax
0x18012a464  jns     short loc_18012A4B3
0x18012a466  mov     rcx, [rsp+128h]; this
0x18012a46e  mov     r9d, eax; char *
0x18012a471  lea     r8, aOnecoreBaseTel_43; "onecore\\base\\telemetry\\utc\\service"...
0x18012a478  mov     edx, 296h; void *
0x18012a47d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a482  nop
0x18012a483  lea     rcx, [rsp+128h+var_68]
0x18012a48b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a490  nop
0x18012a491  lea     rcx, [rsp+128h+var_A8]
0x18012a499  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a49e  nop
0x18012a49f  lea     rcx, [rsp+128h+var_88]
0x18012a4a7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a4ac  mov     eax, edi
0x18012a4ae  jmp     loc_18012A95B
0x18012a4b3  lea     rdx, [rsp+128h+var_B8]
0x18012a4b8  lea     rcx, [rsp+128h+var_68]
0x18012a4c0  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18012a4c5  movups  xmm0, xmmword ptr [rax]
0x18012a4c8  movdqu  [rsp+128h+var_F8], xmm0
0x18012a4ce  lea     r8, [r14+0C0h]
0x18012a4d5  mov     dl, 1
0x18012a4d7  lea     rcx, [rsp+128h+var_F8]
0x18012a4dc  call    ?GetHiveFromString@Xml@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_NAEAPEAUHKEY__@@@Z; Microsoft::Diagnostics::Utils::Xml::GetHiveFromString(std::wstring_view,bool,HKEY__ * &)
0x18012a4e1  mov     edi, eax
0x18012a4e3  test    eax, eax
0x18012a4e5  jns     short loc_18012A534
0x18012a4e7  mov     rcx, [rsp+128h]; this
0x18012a4ef  mov     r9d, eax; char *
0x18012a4f2  lea     r8, aOnecoreBaseTel_43; "onecore\\base\\telemetry\\utc\\service"...
0x18012a4f9  mov     edx, 297h; void *
0x18012a4fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a503  nop
0x18012a504  lea     rcx, [rsp+128h+var_68]
0x18012a50c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a511  nop
0x18012a512  lea     rcx, [rsp+128h+var_A8]
0x18012a51a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a51f  nop
0x18012a520  lea     rcx, [rsp+128h+var_88]
0x18012a528  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a52d  mov     eax, edi
0x18012a52f  jmp     loc_18012A95B
0x18012a534  mov     rcx, rsi; this
0x18012a537  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18012a53c  mov     edi, eax
0x18012a53e  test    eax, eax
0x18012a540  jns     short loc_18012A58F
0x18012a542  mov     rcx, [rsp+128h]; this
0x18012a54a  mov     r9d, eax; char *
0x18012a54d  lea     r8, aOnecoreBaseTel_43; "onecore\\base\\telemetry\\utc\\service"...
0x18012a554  mov     edx, 298h; void *
0x18012a559  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a55e  nop
0x18012a55f  lea     rcx, [rsp+128h+var_68]
0x18012a567  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a56c  nop
0x18012a56d  lea     rcx, [rsp+128h+var_A8]
0x18012a575  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a57a  nop
0x18012a57b  lea     rcx, [rsp+128h+var_88]
0x18012a583  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a588  mov     eax, edi
0x18012a58a  jmp     loc_18012A95B
0x18012a58f  inc     r15d
0x18012a592  mov     [rsp+128h+var_108], r15d
0x18012a597  lea     rcx, [rsp+128h+var_68]
0x18012a59f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a5a4  jmp     loc_18012A896
0x18012a5a9  lea     rdx, [rsp+128h+var_A8]
0x18012a5b1  mov     eax, 7
0x18012a5b6  cmp     [rsp+128h+var_90], rax
0x18012a5be  cmova   rdx, [rsp+128h+var_A8]
0x18012a5c7  mov     rdi, [rsp+128h+var_98]
0x18012a5cf  mov     r8, rdi
0x18012a5d2  cmp     rdi, rax
0x18012a5d5  cmovnb  r8, rax
0x18012a5d9  mov     rcx, cs:off_1803700F0; "keyname"
0x18012a5e0  call    cs:__imp__o__wcsnicmp
0x18012a5e6  test    eax, eax
0x18012a5e8  jnz     loc_18012A6CD
0x18012a5ee  mov     eax, 7
0x18012a5f3  sub     eax, edi
0x18012a5f5  jnz     loc_18012A6CD
0x18012a5fb  lea     r15, [r14+80h]
0x18012a602  mov     rdx, r15
0x18012a605  mov     rcx, rsi
0x18012a608  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18012a60d  mov     edi, eax
0x18012a60f  test    eax, eax
0x18012a611  jns     short loc_18012A652
0x18012a613  mov     rcx, [rsp+128h]; this
0x18012a61b  mov     r9d, eax; char *
0x18012a61e  lea     r8, aOnecoreBaseTel_43; "onecore\\base\\telemetry\\utc\\service"...
0x18012a625  mov     edx, 29Eh; void *
0x18012a62a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a62f  nop
0x18012a630  lea     rcx, [rsp+128h+var_A8]
0x18012a638  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a63d  nop
0x18012a63e  lea     rcx, [rsp+128h+var_88]
0x18012a646  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a64b  mov     eax, edi
0x18012a64d  jmp     loc_18012A95B
0x18012a652  lea     rax, asc_1803948B8; " \n\r\t"
0x18012a659  mov     [rsp+128h+var_C8], rax
0x18012a65e  mov     rcx, rax
0x18012a661  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18012a666  mov     [rsp+128h+var_C0], rax
0x18012a66b  lea     rdx, [rsp+128h+var_C8]
0x18012a670  mov     rcx, r15
0x18012a673  call    ?Trim@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::String::Trim(std::wstring &,std::wstring_view)
0x18012a678  mov     rcx, rsi; this
0x18012a67b  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18012a680  mov     edi, eax
0x18012a682  test    eax, eax
0x18012a684  jns     short loc_18012A6C5
0x18012a686  mov     rcx, [rsp+128h]; this
0x18012a68e  mov     r9d, eax; char *
0x18012a691  lea     r8, aOnecoreBaseTel_43; "onecore\\base\\telemetry\\utc\\service"...
0x18012a698  mov     edx, 2A0h; void *
0x18012a69d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a6a2  nop
0x18012a6a3  lea     rcx, [rsp+128h+var_A8]
0x18012a6ab  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a6b0  nop
0x18012a6b1  lea     rcx, [rsp+128h+var_88]
0x18012a6b9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a6be  mov     eax, edi
0x18012a6c0  jmp     loc_18012A95B
0x18012a6c5  inc     r13d
0x18012a6c8  jmp     loc_18012A7ED
0x18012a6cd  lea     rdx, [rsp+128h+var_A8]
0x18012a6d5  cmp     [rsp+128h+var_90], 7
0x18012a6de  cmova   rdx, [rsp+128h+var_A8]
0x18012a6e7  mov     rdi, [rsp+128h+var_98]
0x18012a6ef  mov     r8, rdi
0x18012a6f2  mov     eax, 9
0x18012a6f7  cmp     rdi, rax
0x18012a6fa  cmovnb  r8, rax
0x18012a6fe  mov     rcx, cs:off_180370100; "valuename"
0x18012a705  call    cs:__imp__o__wcsnicmp
0x18012a70b  test    eax, eax
0x18012a70d  jnz     loc_18012A7F7
0x18012a713  mov     eax, 9
0x18012a718  sub     eax, edi
0x18012a71a  jnz     loc_18012A7F7
0x18012a720  lea     r15, [r14+0A0h]
0x18012a727  mov     rdx, r15
0x18012a72a  mov     rcx, rsi
0x18012a72d  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18012a732  mov     edi, eax
0x18012a734  test    eax, eax
0x18012a736  jns     short loc_18012A777
0x18012a738  mov     rcx, [rsp+128h]; this
0x18012a740  mov     r9d, eax; char *
0x18012a743  lea     r8, aOnecoreBaseTel_43; "onecore\\base\\telemetry\\utc\\service"...
0x18012a74a  mov     edx, 2A6h; void *
0x18012a74f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a754  nop
0x18012a755  lea     rcx, [rsp+128h+var_A8]
0x18012a75d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a762  nop
0x18012a763  lea     rcx, [rsp+128h+var_88]
0x18012a76b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a770  mov     eax, edi
0x18012a772  jmp     loc_18012A95B
0x18012a777  lea     rax, asc_1803948B8; " \n\r\t"
0x18012a77e  mov     qword ptr [rsp+128h+var_E8], rax
0x18012a783  mov     rcx, rax
0x18012a786  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18012a78b  mov     qword ptr [rsp+128h+var_E8+8], rax
0x18012a790  lea     rdx, [rsp+128h+var_E8]
0x18012a795  mov     rcx, r15
0x18012a798  call    ?Trim@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::String::Trim(std::wstring &,std::wstring_view)
0x18012a79d  mov     rcx, rsi; this
0x18012a7a0  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
  ... truncated ...
```

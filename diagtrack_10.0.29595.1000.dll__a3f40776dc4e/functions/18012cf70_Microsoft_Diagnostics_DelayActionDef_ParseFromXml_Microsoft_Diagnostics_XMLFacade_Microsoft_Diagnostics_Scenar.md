# Microsoft::Diagnostics::DelayActionDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x18012cf70`
- end: `0x18012d4f0`
- name: `?ParseFromXml@DelayActionDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `1408`
- prototype: `int(Microsoft::Diagnostics::DelayActionDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002cae0`
- `0x18002df00`
- `0x180040558`
- `0x180064e8c`
- `0x1800653d0`
- `0x18008b254`
- `0x18009dec0`
- `0x1800a3760`
- `0x1800a37b0`
- `0x1800a3d14`
- `0x1800a6438`
- `0x1800a658c`
- `0x1800ded9c`
- `0x18012cf70`
- `0x1801b7bd0`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012d085`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012d17d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012d279`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012d085`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012d17d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012d279`

## string_xrefs

- `0x18012d03c`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d0c9`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d121`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d1c1`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d220`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d2bd`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d31c`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d370`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d3ac`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d3fc`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d447`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d494`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`
- `0x18012d4b9`: `onecore\base\telemetry\utc\service\scenarios\actions\delayaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::DelayActionDef::ParseFromXml(
        Microsoft::Diagnostics::DelayActionDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // r10
  int v11; // r14d
  unsigned int Element; // eax
  unsigned int v13; // esi
  int CurrentElementName; // eax
  unsigned int v15; // esi
  _QWORD *v17; // rdx
  int v18; // esi
  __int64 v19; // r8
  int InnerText; // eax
  unsigned int v21; // esi
  int v22; // eax
  unsigned int v23; // esi
  _QWORD *v24; // rdx
  int v25; // esi
  __int64 v26; // r8
  int v27; // eax
  unsigned int v28; // esi
  int v29; // eax
  unsigned int v30; // esi
  _QWORD *v31; // rdx
  int v32; // esi
  __int64 v33; // r8
  int v34; // eax
  unsigned int v35; // esi
  int v36; // eax
  unsigned int v37; // esi
  int v38; // eax
  unsigned int v39; // esi
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // [rsp+20h] [rbp-88h] BYREF
  _QWORD v43[2]; // [rsp+28h] [rbp-80h] BYREF
  unsigned __int64 v44; // [rsp+38h] [rbp-70h]
  unsigned __int64 v45; // [rsp+40h] [rbp-68h]
  _BYTE v46[32]; // [rsp+48h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(
    &v42,
    *((unsigned __int16 *)this + 60));
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v42, (char *)a3 + 112, (unsigned __int16)v42);
  v9 = std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(v42, v6, v7, v8);
  std::wstring::_Assign<wchar_t>(v9 + 8, v10, *((_QWORD *)this + 13));
  v11 = 0;
  if ( Microsoft::Diagnostics::XMLFacade::IsEmptyElement(a2) )
  {
    v40 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
    v41 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
        (const char *)(unsigned int)v40,
        v42);
      return v41;
    }
    goto LABEL_52;
  }
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    v13 = Element;
    if ( Element )
      break;
    std::wstring::wstring(v43);
    CurrentElementName = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v43);
    v15 = CurrentElementName;
    if ( CurrentElementName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
        (const char *)(unsigned int)CurrentElementName,
        v42);
      std::wstring::_Tidy_deallocate(v43);
      return v15;
    }
    v17 = v43;
    if ( v45 > 7 )
      v17 = (_QWORD *)v43[0];
    v18 = v44;
    v19 = v44;
    if ( v44 >= 7 )
      v19 = 7;
    if ( !(unsigned int)_o__wcsnicmp(L"delayms", v17, v19) && v18 == 7 )
    {
      std::wstring::wstring(v46);
      InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v46);
      v21 = InnerText;
      if ( InnerText < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
          (const char *)(unsigned int)InnerText,
          v42);
        std::wstring::_Tidy_deallocate(v46);
        std::wstring::_Tidy_deallocate(v43);
        return v21;
      }
      *((_QWORD *)this + 16) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned __int64>(v46);
      v22 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
          (const char *)(unsigned int)v22,
          v42);
        std::wstring::_Tidy_deallocate(v46);
        std::wstring::_Tidy_deallocate(v43);
        return v23;
      }
      ++v11;
LABEL_36:
      std::wstring::_Tidy_deallocate(v46);
      goto LABEL_41;
    }
    v24 = v43;
    if ( v45 > 7 )
      v24 = (_QWORD *)v43[0];
    v25 = v44;
    v26 = v44;
    if ( v44 >= 7 )
      v26 = 7;
    if ( !(unsigned int)_o__wcsnicmp(L"rangems", v24, v26) && v25 == 7 )
    {
      std::wstring::wstring(v46);
      v27 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v46);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF3,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
          (const char *)(unsigned int)v27,
          v42);
        std::wstring::_Tidy_deallocate(v46);
        std::wstring::_Tidy_deallocate(v43);
        return v28;
      }
      *((_QWORD *)this + 17) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned __int64>(v46);
      *((_BYTE *)this + 152) = 1;
      v29 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v30 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
          (const char *)(unsigned int)v29,
          v42);
        std::wstring::_Tidy_deallocate(v46);
        std::wstring::_Tidy_deallocate(v43);
        return v30;
      }
      goto LABEL_36;
    }
    v31 = v43;
    if ( v45 > 7 )
      v31 = (_QWORD *)v43[0];
    v32 = v44;
    v33 = v44;
    if ( v44 >= 0xB )
      v33 = 11;
    if ( !(unsigned int)_o__wcsnicmp(L"tolerancems", v31, v33) && v32 == 11 )
    {
      std::wstring::wstring(v46);
      v34 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v46);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFD,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
          (const char *)(unsigned int)v34,
          v42);
        std::wstring::_Tidy_deallocate(v46);
        std::wstring::_Tidy_deallocate(v43);
        return v35;
      }
      *((_QWORD *)this + 18) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned __int64>(v46);
      *((_BYTE *)this + 153) = 1;
      v36 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v37 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x102,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
          (const char *)(unsigned int)v36,
          v42);
        std::wstring::_Tidy_deallocate(v46);
        std::wstring::_Tidy_deallocate(v43);
        return v37;
      }
      goto LABEL_36;
    }
    if ( *((_BYTE *)a3 + 152) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
        (const char *)0x87C52407LL,
        v42);
      std::wstring::_Tidy_deallocate(v43);
      return 2277843975LL;
    }
    v38 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
    v39 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
        (const char *)(unsigned int)v38,
        v42);
      std::wstring::_Tidy_deallocate(v43);
      return v39;
    }
LABEL_41:
    std::wstring::_Tidy_deallocate(v43);
  }
  if ( (int)(Element + 0x80000000) >= 0 && Element != -2147024270 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
      (const char *)Element,
      v42);
    return v13;
  }
  if ( v11 != 1 )
  {
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
      (const char *)0x87C52402LL,
      v42);
    return 2277843970LL;
  }
  if ( *((_BYTE *)this + 152) && *((_QWORD *)this + 17) > *((_QWORD *)this + 16) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\delayaction.cpp",
      (const char *)0x87C5242ELL,
      v42);
    return 2277844014LL;
  }
  else
  {
    (*(void (__fastcall **)(Microsoft::Diagnostics::DelayActionDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
    std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v42);
    return 0;
  }
}

```

## disassembly

```asm
0x18012cf70  push    rbx
0x18012cf72  push    rsi
0x18012cf73  push    rdi
0x18012cf74  push    r12
0x18012cf76  push    r13
0x18012cf78  push    r14
0x18012cf7a  push    r15
0x18012cf7c  sub     rsp, 70h
0x18012cf80  mov     rax, cs:__security_cookie
0x18012cf87  xor     rax, rsp
0x18012cf8a  mov     [rsp+0A8h+var_40], rax
0x18012cf8f  mov     r15, r8
0x18012cf92  mov     rdi, rdx
0x18012cf95  mov     rbx, rcx
0x18012cf98  movzx   edx, word ptr [rcx+78h]
0x18012cf9c  lea     rcx, [rsp+0A8h+var_88]
0x18012cfa1  call    ?ConvertActionTypeToScenarioDbObjectType@TypeToScenarioDbObjectTypeConverter@Diagnostics@Microsoft@@SA?AVScenarioDbObjectType@23@VActionType@23@@Z; Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(Microsoft::Diagnostics::ActionType)
0x18012cfa6  lea     rdx, [r15+70h]
0x18012cfaa  movzx   r8d, word ptr [rsp+0A8h+var_88]
0x18012cfb0  lea     rcx, [rsp+0A8h+var_88]
0x18012cfb5  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x18012cfba  mov     r12d, 7
0x18012cfc0  cmp     [rbx+70h], r12
0x18012cfc4  jbe     short loc_18012CFCC
0x18012cfc6  mov     r10, [rbx+58h]
0x18012cfca  jmp     short loc_18012CFD0
0x18012cfcc  lea     r10, [rbx+58h]
0x18012cfd0  mov     rcx, [rsp+0A8h+var_88]
0x18012cfd5  call    ?top@?$stack@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$deque@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@@2@@2@@std@@QEAAAEAV?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@2@XZ; std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(void)
0x18012cfda  lea     rcx, [rax+8]
0x18012cfde  mov     r8, [rbx+68h]
0x18012cfe2  mov     rdx, r10
0x18012cfe5  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18012cfea  xor     r14d, r14d
0x18012cfed  mov     rcx, rdi; this
0x18012cff0  call    ?IsEmptyElement@XMLFacade@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::XMLFacade::IsEmptyElement(void)
0x18012cff5  test    al, al
0x18012cff7  jnz     loc_18012D47B
0x18012cffd  lea     r13d, [r14+0Bh]
0x18012d001  mov     rcx, rdi; this
0x18012d004  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x18012d009  mov     esi, eax
0x18012d00b  test    eax, eax
0x18012d00d  jnz     loc_18012D3DE
0x18012d013  lea     rcx, [rsp+0A8h+var_80]; void *
0x18012d018  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012d01d  nop
0x18012d01e  lea     rdx, [rsp+0A8h+var_80]
0x18012d023  mov     rcx, rdi
0x18012d026  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x18012d02b  mov     esi, eax
0x18012d02d  test    eax, eax
0x18012d02f  jns     short loc_18012D05F
0x18012d031  mov     rcx, [rsp+0A8h]; this
0x18012d039  mov     r9d, eax; char *
0x18012d03c  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d043  mov     edx, 0E3h; void *
0x18012d048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d04d  nop
0x18012d04e  lea     rcx, [rsp+0A8h+var_80]
0x18012d053  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d058  mov     eax, esi
0x18012d05a  jmp     loc_18012D4D2
0x18012d05f  lea     rdx, [rsp+0A8h+var_80]
0x18012d064  cmp     [rsp+0A8h+var_68], r12
0x18012d069  cmova   rdx, [rsp+0A8h+var_80]
0x18012d06f  mov     rsi, [rsp+0A8h+var_70]
0x18012d074  mov     r8, rsi
0x18012d077  cmp     rsi, r12
0x18012d07a  cmovnb  r8, r12
0x18012d07e  mov     rcx, cs:off_180370308; "delayms"
0x18012d085  call    cs:__imp__o__wcsnicmp
0x18012d08b  test    eax, eax
0x18012d08d  jnz     loc_18012D157
0x18012d093  mov     eax, r12d
0x18012d096  sub     eax, esi
0x18012d098  test    eax, eax
0x18012d09a  jnz     loc_18012D157
0x18012d0a0  lea     rcx, [rsp+0A8h+var_60]; void *
0x18012d0a5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012d0aa  nop
0x18012d0ab  lea     rdx, [rsp+0A8h+var_60]
0x18012d0b0  mov     rcx, rdi
0x18012d0b3  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18012d0b8  mov     esi, eax
0x18012d0ba  test    eax, eax
0x18012d0bc  jns     short loc_18012D0F7
0x18012d0be  mov     rcx, [rsp+0A8h]; this
0x18012d0c6  mov     r9d, eax; char *
0x18012d0c9  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d0d0  mov     edx, 0E8h; void *
0x18012d0d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d0da  nop
0x18012d0db  lea     rcx, [rsp+0A8h+var_60]
0x18012d0e0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d0e5  nop
0x18012d0e6  lea     rcx, [rsp+0A8h+var_80]
0x18012d0eb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d0f0  mov     eax, esi
0x18012d0f2  jmp     loc_18012D4D2
0x18012d0f7  lea     rcx, [rsp+0A8h+var_60]
0x18012d0fc  call    ??$ToUIntT@_K@String@Utils@Diagnostics@Microsoft@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned __int64>(std::wstring const &)
0x18012d101  mov     [rbx+80h], rax
0x18012d108  mov     rcx, rdi; this
0x18012d10b  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18012d110  mov     esi, eax
0x18012d112  test    eax, eax
0x18012d114  jns     short loc_18012D14F
0x18012d116  mov     rcx, [rsp+0A8h]; this
0x18012d11e  mov     r9d, eax; char *
0x18012d121  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d128  mov     edx, 0ECh; void *
0x18012d12d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d132  nop
0x18012d133  lea     rcx, [rsp+0A8h+var_60]
0x18012d138  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d13d  nop
0x18012d13e  lea     rcx, [rsp+0A8h+var_80]
0x18012d143  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d148  mov     eax, esi
0x18012d14a  jmp     loc_18012D4D2
0x18012d14f  inc     r14d
0x18012d152  jmp     loc_18012D34A
0x18012d157  lea     rdx, [rsp+0A8h+var_80]
0x18012d15c  cmp     [rsp+0A8h+var_68], r12
0x18012d161  cmova   rdx, [rsp+0A8h+var_80]
0x18012d167  mov     rsi, [rsp+0A8h+var_70]
0x18012d16c  mov     r8, rsi
0x18012d16f  cmp     rsi, r12
0x18012d172  cmovnb  r8, r12
0x18012d176  mov     rcx, cs:off_180370328; "rangems"
0x18012d17d  call    cs:__imp__o__wcsnicmp
0x18012d183  test    eax, eax
0x18012d185  jnz     loc_18012D253
0x18012d18b  mov     eax, r12d
0x18012d18e  sub     eax, esi
0x18012d190  test    eax, eax
0x18012d192  jnz     loc_18012D253
0x18012d198  lea     rcx, [rsp+0A8h+var_60]; void *
0x18012d19d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012d1a2  nop
0x18012d1a3  lea     rdx, [rsp+0A8h+var_60]
0x18012d1a8  mov     rcx, rdi
0x18012d1ab  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18012d1b0  mov     esi, eax
0x18012d1b2  test    eax, eax
0x18012d1b4  jns     short loc_18012D1EF
0x18012d1b6  mov     rcx, [rsp+0A8h]; this
0x18012d1be  mov     r9d, eax; char *
0x18012d1c1  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d1c8  mov     edx, 0F3h; void *
0x18012d1cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d1d2  nop
0x18012d1d3  lea     rcx, [rsp+0A8h+var_60]
0x18012d1d8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d1dd  nop
0x18012d1de  lea     rcx, [rsp+0A8h+var_80]
0x18012d1e3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d1e8  mov     eax, esi
0x18012d1ea  jmp     loc_18012D4D2
0x18012d1ef  lea     rcx, [rsp+0A8h+var_60]
0x18012d1f4  call    ??$ToUIntT@_K@String@Utils@Diagnostics@Microsoft@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned __int64>(std::wstring const &)
0x18012d1f9  mov     [rbx+88h], rax
0x18012d200  mov     byte ptr [rbx+98h], 1
0x18012d207  mov     rcx, rdi; this
0x18012d20a  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18012d20f  mov     esi, eax
0x18012d211  test    eax, eax
0x18012d213  jns     short loc_18012D24E
0x18012d215  mov     rcx, [rsp+0A8h]; this
0x18012d21d  mov     r9d, eax; char *
0x18012d220  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d227  mov     edx, 0F8h; void *
0x18012d22c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d231  nop
0x18012d232  lea     rcx, [rsp+0A8h+var_60]
0x18012d237  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d23c  nop
0x18012d23d  lea     rcx, [rsp+0A8h+var_80]
0x18012d242  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d247  mov     eax, esi
0x18012d249  jmp     loc_18012D4D2
0x18012d24e  jmp     loc_18012D34A
0x18012d253  lea     rdx, [rsp+0A8h+var_80]
0x18012d258  cmp     [rsp+0A8h+var_68], r12
0x18012d25d  cmova   rdx, [rsp+0A8h+var_80]
0x18012d263  mov     rsi, [rsp+0A8h+var_70]
0x18012d268  mov     r8, rsi
0x18012d26b  cmp     rsi, r13
0x18012d26e  cmovnb  r8, r13
0x18012d272  mov     rcx, cs:off_180370318; "tolerancems"
0x18012d279  call    cs:__imp__o__wcsnicmp
0x18012d27f  test    eax, eax
0x18012d281  jnz     loc_18012D356
0x18012d287  mov     eax, r13d
0x18012d28a  sub     eax, esi
0x18012d28c  test    eax, eax
0x18012d28e  jnz     loc_18012D356
0x18012d294  lea     rcx, [rsp+0A8h+var_60]; void *
0x18012d299  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012d29e  nop
0x18012d29f  lea     rdx, [rsp+0A8h+var_60]
0x18012d2a4  mov     rcx, rdi
0x18012d2a7  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18012d2ac  mov     esi, eax
0x18012d2ae  test    eax, eax
0x18012d2b0  jns     short loc_18012D2EB
0x18012d2b2  mov     rcx, [rsp+0A8h]; this
0x18012d2ba  mov     r9d, eax; char *
0x18012d2bd  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d2c4  mov     edx, 0FDh; void *
0x18012d2c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d2ce  nop
0x18012d2cf  lea     rcx, [rsp+0A8h+var_60]
0x18012d2d4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d2d9  nop
0x18012d2da  lea     rcx, [rsp+0A8h+var_80]
0x18012d2df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d2e4  mov     eax, esi
0x18012d2e6  jmp     loc_18012D4D2
0x18012d2eb  lea     rcx, [rsp+0A8h+var_60]
0x18012d2f0  call    ??$ToUIntT@_K@String@Utils@Diagnostics@Microsoft@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned __int64>(std::wstring const &)
0x18012d2f5  mov     [rbx+90h], rax
0x18012d2fc  mov     byte ptr [rbx+99h], 1
0x18012d303  mov     rcx, rdi; this
0x18012d306  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18012d30b  mov     esi, eax
0x18012d30d  test    eax, eax
0x18012d30f  jns     short loc_18012D34A
0x18012d311  mov     rcx, [rsp+0A8h]; this
0x18012d319  mov     r9d, eax; char *
0x18012d31c  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d323  mov     edx, 102h; void *
0x18012d328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d32d  nop
0x18012d32e  lea     rcx, [rsp+0A8h+var_60]
0x18012d333  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d338  nop
0x18012d339  lea     rcx, [rsp+0A8h+var_80]
0x18012d33e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d343  mov     eax, esi
0x18012d345  jmp     loc_18012D4D2
0x18012d34a  lea     rcx, [rsp+0A8h+var_60]
0x18012d34f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d354  jmp     short loc_18012D3CF
0x18012d356  cmp     byte ptr [r15+98h], 0
0x18012d35e  jz      short loc_18012D393
0x18012d360  mov     rcx, [rsp+0A8h]; this
0x18012d368  mov     ebx, 87C52407h
0x18012d36d  mov     r9d, ebx; char *
0x18012d370  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d377  mov     edx, 108h; void *
0x18012d37c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d381  nop
0x18012d382  lea     rcx, [rsp+0A8h+var_80]
0x18012d387  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d38c  mov     eax, ebx
0x18012d38e  jmp     loc_18012D4D2
0x18012d393  mov     rcx, rdi; this
0x18012d396  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18012d39b  mov     esi, eax
0x18012d39d  test    eax, eax
0x18012d39f  jns     short loc_18012D3CF
0x18012d3a1  mov     rcx, [rsp+0A8h]; this
0x18012d3a9  mov     r9d, eax; char *
0x18012d3ac  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d3b3  mov     edx, 10Bh; void *
0x18012d3b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d3bd  nop
0x18012d3be  lea     rcx, [rsp+0A8h+var_80]
0x18012d3c3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d3c8  mov     eax, esi
0x18012d3ca  jmp     loc_18012D4D2
0x18012d3cf  lea     rcx, [rsp+0A8h+var_80]
0x18012d3d4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012d3d9  jmp     loc_18012D001
0x18012d3de  mov     ecx, 80000000h
0x18012d3e3  add     eax, ecx
0x18012d3e5  test    ecx, eax
0x18012d3e7  jnz     short loc_18012D414
0x18012d3e9  cmp     esi, 80070272h
0x18012d3ef  jz      short loc_18012D414
0x18012d3f1  mov     rcx, [rsp+0A8h]; this
0x18012d3f9  mov     r9d, esi; char *
0x18012d3fc  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
0x18012d403  mov     edx, 10Fh; void *
0x18012d408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d40d  mov     eax, esi
0x18012d40f  jmp     loc_18012D4D2
0x18012d414  cmp     r14d, 1
0x18012d418  jnz     loc_18012D4A9
0x18012d41e  cmp     byte ptr [rbx+98h], 0
0x18012d425  jz      short loc_18012D45C
0x18012d427  mov     rax, [rbx+80h]
0x18012d42e  cmp     [rbx+88h], rax
0x18012d435  jbe     short loc_18012D45C
0x18012d437  mov     rcx, [rsp+0A8h]; this
0x18012d43f  mov     ebx, 87C5242Eh
0x18012d444  mov     r9d, ebx; char *
0x18012d447  lea     r8, aOnecoreBaseTel_99; "onecore\\base\\telemetry\\utc\\service"...
  ... truncated ...
```

# Microsoft::Diagnostics::RunExeWithArgsActionDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1800a37e0`
- end: `0x1800a3cd8`
- name: `?ParseFromXml@RunExeWithArgsActionDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `1272`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::RunExeWithArgsActionDef *this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `18`
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
- `0x1800a37e0`
- `0x1800a3d14`
- `0x1800a6438`
- `0x1800a658c`
- `0x1800ca65c`
- `0x1800ded9c`
- `0x1801b7bd0`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a38f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a39d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a3aa0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a38f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a39d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a3aa0`

## string_xrefs

- `0x1800a38ae`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3933`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3977`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3a0e`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3a4a`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3ae6`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3b3e`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3b92`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3bce`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3c1e`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3c79`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`
- `0x1800a3c9e`: `onecore\base\telemetry\utc\service\scenarios\actions\runexewithargsaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::RunExeWithArgsActionDef::ParseFromXml(
        Microsoft::Diagnostics::RunExeWithArgsActionDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  __int64 v6; // rax
  __int64 v7; // r10
  int v8; // r12d
  int v9; // r15d
  unsigned int Element; // eax
  unsigned int v11; // edi
  int CurrentElementName; // eax
  unsigned int v13; // edi
  _QWORD *v15; // rdx
  int v16; // edi
  __int64 v17; // r8
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  unsigned int v21; // edi
  _QWORD *v22; // rdx
  int v23; // edi
  __int64 v24; // r8
  int v25; // eax
  unsigned int v26; // edi
  int v27; // eax
  unsigned int v28; // edi
  _QWORD *v29; // rdx
  int v30; // edi
  __int64 v31; // r8
  int InnerText; // eax
  unsigned int v33; // edi
  int v34; // eax
  unsigned int v35; // edi
  int v36; // eax
  unsigned int v37; // edi
  int v38; // eax
  unsigned int v39; // ebx
  int v40; // [rsp+20h] [rbp-98h] BYREF
  __int64 v41; // [rsp+28h] [rbp-90h] BYREF
  _QWORD v42[2]; // [rsp+30h] [rbp-88h] BYREF
  unsigned __int64 v43; // [rsp+40h] [rbp-78h]
  unsigned __int64 v44; // [rsp+48h] [rbp-70h]
  _BYTE v45[32]; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(
    &v40,
    *((unsigned __int16 *)this + 60));
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v41, (char *)a3 + 112, (unsigned __int16)v40);
  v6 = std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(v41);
  std::wstring::_Assign<wchar_t>(v6 + 8, v7, *((_QWORD *)this + 13));
  v8 = 0;
  v9 = 0;
  if ( Microsoft::Diagnostics::XMLFacade::IsEmptyElement(a2) )
  {
    v38 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
    v39 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
        (const char *)(unsigned int)v38,
        v40);
      return v39;
    }
  }
  else
  {
    while ( 1 )
    {
      Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v11 = Element;
      if ( Element )
        break;
      std::wstring::wstring(v42);
      CurrentElementName = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v42);
      v13 = CurrentElementName;
      if ( CurrentElementName < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
          (const char *)(unsigned int)CurrentElementName,
          v40);
        std::wstring::_Tidy_deallocate(v42);
        return v13;
      }
      v15 = v42;
      if ( v44 > 7 )
        v15 = (_QWORD *)v42[0];
      v16 = v43;
      v17 = v43;
      if ( v43 >= 7 )
        v17 = 7;
      if ( (unsigned int)_o__wcsnicmp(L"exename", v15, v17) || v16 != 7 )
      {
        v22 = v42;
        if ( v44 > 7 )
          v22 = (_QWORD *)v42[0];
        v23 = v43;
        v24 = v43;
        if ( v43 >= 0xB )
          v24 = 11;
        if ( (unsigned int)_o__wcsnicmp(L"commandline", v22, v24) || v23 != 11 )
        {
          v29 = v42;
          if ( v44 > 7 )
            v29 = (_QWORD *)v42[0];
          v30 = v43;
          v31 = v43;
          if ( v43 >= 0x10 )
            v31 = 16;
          if ( (unsigned int)_o__wcsnicmp(L"maximumruntimems", v29, v31) || v30 != 16 )
          {
            if ( *((_BYTE *)a3 + 152) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x12A,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
                (const char *)0x87C52407LL,
                v40);
              std::wstring::_Tidy_deallocate(v42);
              return 2277843975LL;
            }
            v36 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v37 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x12D,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
                (const char *)(unsigned int)v36,
                v40);
              std::wstring::_Tidy_deallocate(v42);
              return v37;
            }
          }
          else
          {
            std::wstring::wstring(v45);
            InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v45);
            v33 = InnerText;
            if ( InnerText < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x122,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
                (const char *)(unsigned int)InnerText,
                v40);
              std::wstring::_Tidy_deallocate(v45);
              std::wstring::_Tidy_deallocate(v42);
              return v33;
            }
            *((_QWORD *)this + 20) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned __int64>(v45);
            v34 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v35 = v34;
            if ( v34 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x124,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
                (const char *)(unsigned int)v34,
                v40);
              std::wstring::_Tidy_deallocate(v45);
              std::wstring::_Tidy_deallocate(v42);
              return v35;
            }
            std::wstring::_Tidy_deallocate(v45);
          }
        }
        else
        {
          v25 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 168);
          v26 = v25;
          if ( v25 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11A,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
              (const char *)(unsigned int)v25,
              v40);
            std::wstring::_Tidy_deallocate(v42);
            return v26;
          }
          v27 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v28 = v27;
          if ( v27 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
              (const char *)(unsigned int)v27,
              v40);
            std::wstring::_Tidy_deallocate(v42);
            return v28;
          }
          ++v9;
        }
      }
      else
      {
        v18 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 128);
        v19 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x112,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
            (const char *)(unsigned int)v18,
            v40);
          std::wstring::_Tidy_deallocate(v42);
          return v19;
        }
        Microsoft::Diagnostics::Utils::String::ToLowercase((char *)this + 128);
        v20 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v21 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x114,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
            (const char *)(unsigned int)v20,
            v40);
          std::wstring::_Tidy_deallocate(v42);
          return v21;
        }
        ++v8;
      }
      std::wstring::_Tidy_deallocate(v42);
    }
    if ( (int)(Element + 0x80000000) >= 0 && Element != -2147024270 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
        (const char *)Element,
        v40);
      return v11;
    }
    if ( v8 == 1 && v9 == 1 )
    {
      (*(void (__fastcall **)(Microsoft::Diagnostics::RunExeWithArgsActionDef *, _QWORD))(*(_QWORD *)this + 16LL))(
        this,
        0);
      std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v41);
      return 0;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13B,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexewithargsaction.cpp",
    (const char *)0x87C52402LL,
    v40);
  return 2277843970LL;
}

```

## disassembly

```asm
0x1800a37e0  push    rbx
0x1800a37e2  push    rsi
0x1800a37e3  push    rdi
0x1800a37e4  push    r12
0x1800a37e6  push    r13
0x1800a37e8  push    r14
0x1800a37ea  push    r15
0x1800a37ec  sub     rsp, 80h
0x1800a37f3  mov     rax, cs:__security_cookie
0x1800a37fa  xor     rax, rsp
0x1800a37fd  mov     [rsp+0B8h+var_48], rax
0x1800a3802  mov     r13, r8
0x1800a3805  mov     rbx, rdx
0x1800a3808  mov     rsi, rcx
0x1800a380b  movzx   edx, word ptr [rcx+78h]
0x1800a380f  lea     rcx, [rsp+0B8h+var_98]
0x1800a3814  call    ?ConvertActionTypeToScenarioDbObjectType@TypeToScenarioDbObjectTypeConverter@Diagnostics@Microsoft@@SA?AVScenarioDbObjectType@23@VActionType@23@@Z; Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(Microsoft::Diagnostics::ActionType)
0x1800a3819  lea     rdx, [r13+70h]
0x1800a381d  movzx   r8d, word ptr [rsp+0B8h+var_98]
0x1800a3823  lea     rcx, [rsp+0B8h+var_90]
0x1800a3828  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1800a382d  mov     r14d, 7
0x1800a3833  cmp     [rsi+70h], r14
0x1800a3837  jbe     short loc_1800A383F
0x1800a3839  mov     r10, [rsi+58h]
0x1800a383d  jmp     short loc_1800A3843
0x1800a383f  lea     r10, [rsi+58h]
0x1800a3843  mov     rcx, [rsp+0B8h+var_90]
0x1800a3848  call    ?top@?$stack@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$deque@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@@2@@2@@std@@QEAAAEAV?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@2@XZ; std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(void)
0x1800a384d  lea     rcx, [rax+8]
0x1800a3851  mov     r8, [rsi+68h]
0x1800a3855  mov     rdx, r10
0x1800a3858  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800a385d  xor     r12d, r12d
0x1800a3860  xor     r15d, r15d
0x1800a3863  mov     rcx, rbx; this
0x1800a3866  call    ?IsEmptyElement@XMLFacade@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::XMLFacade::IsEmptyElement(void)
0x1800a386b  test    al, al
0x1800a386d  jnz     loc_1800A3C60
0x1800a3873  mov     rcx, rbx; this
0x1800a3876  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1800a387b  mov     edi, eax
0x1800a387d  test    eax, eax
0x1800a387f  jnz     loc_1800A3C00
0x1800a3885  lea     rcx, [rsp+0B8h+var_88]; void *
0x1800a388a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a388f  nop
0x1800a3890  lea     rdx, [rsp+0B8h+var_88]
0x1800a3895  mov     rcx, rbx
0x1800a3898  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1800a389d  mov     edi, eax
0x1800a389f  test    eax, eax
0x1800a38a1  jns     short loc_1800A38D1
0x1800a38a3  mov     rcx, [rsp+0B8h]; this
0x1800a38ab  mov     r9d, eax; char *
0x1800a38ae  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a38b5  mov     edx, 10Eh; void *
0x1800a38ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a38bf  nop
0x1800a38c0  lea     rcx, [rsp+0B8h+var_88]
0x1800a38c5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a38ca  mov     eax, edi
0x1800a38cc  jmp     loc_1800A3CB7
0x1800a38d1  lea     rdx, [rsp+0B8h+var_88]
0x1800a38d6  cmp     [rsp+0B8h+var_70], r14
0x1800a38db  cmova   rdx, [rsp+0B8h+var_88]
0x1800a38e1  mov     rdi, [rsp+0B8h+var_78]
0x1800a38e6  mov     r8, rdi
0x1800a38e9  cmp     rdi, r14
0x1800a38ec  cmovnb  r8, r14
0x1800a38f0  mov     rcx, cs:off_18036CDB8; "exename"
0x1800a38f7  call    cs:__imp__o__wcsnicmp
0x1800a38fd  test    eax, eax
0x1800a38ff  jnz     loc_1800A39A8
0x1800a3905  mov     eax, r14d
0x1800a3908  sub     eax, edi
0x1800a390a  jnz     loc_1800A39A8
0x1800a3910  lea     r14, [rsi+80h]
0x1800a3917  mov     rdx, r14
0x1800a391a  mov     rcx, rbx
0x1800a391d  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a3922  mov     edi, eax
0x1800a3924  test    eax, eax
0x1800a3926  jns     short loc_1800A3956
0x1800a3928  mov     rcx, [rsp+0B8h]; this
0x1800a3930  mov     r9d, eax; char *
0x1800a3933  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a393a  mov     edx, 112h; void *
0x1800a393f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3944  nop
0x1800a3945  lea     rcx, [rsp+0B8h+var_88]
0x1800a394a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a394f  mov     eax, edi
0x1800a3951  jmp     loc_1800A3CB7
0x1800a3956  mov     rcx, r14
0x1800a3959  call    ?ToLowercase@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToLowercase(std::wstring &)
0x1800a395e  mov     rcx, rbx; this
0x1800a3961  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a3966  mov     edi, eax
0x1800a3968  test    eax, eax
0x1800a396a  jns     short loc_1800A399A
0x1800a396c  mov     rcx, [rsp+0B8h]; this
0x1800a3974  mov     r9d, eax; char *
0x1800a3977  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a397e  mov     edx, 114h; void *
0x1800a3983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3988  nop
0x1800a3989  lea     rcx, [rsp+0B8h+var_88]
0x1800a398e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3993  mov     eax, edi
0x1800a3995  jmp     loc_1800A3CB7
0x1800a399a  inc     r12d
0x1800a399d  mov     r14d, 7
0x1800a39a3  jmp     loc_1800A3BF1
0x1800a39a8  lea     rdx, [rsp+0B8h+var_88]
0x1800a39ad  cmp     [rsp+0B8h+var_70], r14
0x1800a39b2  cmova   rdx, [rsp+0B8h+var_88]
0x1800a39b8  mov     rdi, [rsp+0B8h+var_78]
0x1800a39bd  mov     r8, rdi
0x1800a39c0  mov     eax, 0Bh
0x1800a39c5  cmp     rdi, rax
0x1800a39c8  cmovnb  r8, rax
0x1800a39cc  mov     rcx, cs:off_18036CE40; "commandline"
0x1800a39d3  call    cs:__imp__o__wcsnicmp
0x1800a39d9  test    eax, eax
0x1800a39db  jnz     loc_1800A3A75
0x1800a39e1  mov     eax, 0Bh
0x1800a39e6  sub     eax, edi
0x1800a39e8  jnz     loc_1800A3A75
0x1800a39ee  lea     rdx, [rsi+0A8h]
0x1800a39f5  mov     rcx, rbx
0x1800a39f8  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a39fd  mov     edi, eax
0x1800a39ff  test    eax, eax
0x1800a3a01  jns     short loc_1800A3A31
0x1800a3a03  mov     rcx, [rsp+0B8h]; this
0x1800a3a0b  mov     r9d, eax; char *
0x1800a3a0e  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3a15  mov     edx, 11Ah; void *
0x1800a3a1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3a1f  nop
0x1800a3a20  lea     rcx, [rsp+0B8h+var_88]
0x1800a3a25  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3a2a  mov     eax, edi
0x1800a3a2c  jmp     loc_1800A3CB7
0x1800a3a31  mov     rcx, rbx; this
0x1800a3a34  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a3a39  mov     edi, eax
0x1800a3a3b  test    eax, eax
0x1800a3a3d  jns     short loc_1800A3A6D
0x1800a3a3f  mov     rcx, [rsp+0B8h]; this
0x1800a3a47  mov     r9d, eax; char *
0x1800a3a4a  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3a51  mov     edx, 11Bh; void *
0x1800a3a56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3a5b  nop
0x1800a3a5c  lea     rcx, [rsp+0B8h+var_88]
0x1800a3a61  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3a66  mov     eax, edi
0x1800a3a68  jmp     loc_1800A3CB7
0x1800a3a6d  inc     r15d
0x1800a3a70  jmp     loc_1800A3BF1
0x1800a3a75  lea     rdx, [rsp+0B8h+var_88]
0x1800a3a7a  cmp     [rsp+0B8h+var_70], r14
0x1800a3a7f  cmova   rdx, [rsp+0B8h+var_88]
0x1800a3a85  mov     rdi, [rsp+0B8h+var_78]
0x1800a3a8a  mov     r8, rdi
0x1800a3a8d  mov     eax, 10h
0x1800a3a92  cmp     rdi, rax
0x1800a3a95  cmovnb  r8, rax
0x1800a3a99  mov     rcx, cs:off_18036CF10; "maximumruntimems"
0x1800a3aa0  call    cs:__imp__o__wcsnicmp
0x1800a3aa6  test    eax, eax
0x1800a3aa8  jnz     loc_1800A3B78
0x1800a3aae  mov     eax, 10h
0x1800a3ab3  sub     eax, edi
0x1800a3ab5  test    eax, eax
0x1800a3ab7  jnz     loc_1800A3B78
0x1800a3abd  lea     rcx, [rsp+0B8h+var_68]; void *
0x1800a3ac2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a3ac7  nop
0x1800a3ac8  lea     rdx, [rsp+0B8h+var_68]
0x1800a3acd  mov     rcx, rbx
0x1800a3ad0  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a3ad5  mov     edi, eax
0x1800a3ad7  test    eax, eax
0x1800a3ad9  jns     short loc_1800A3B14
0x1800a3adb  mov     rcx, [rsp+0B8h]; this
0x1800a3ae3  mov     r9d, eax; char *
0x1800a3ae6  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3aed  mov     edx, 122h; void *
0x1800a3af2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3af7  nop
0x1800a3af8  lea     rcx, [rsp+0B8h+var_68]
0x1800a3afd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3b02  nop
0x1800a3b03  lea     rcx, [rsp+0B8h+var_88]
0x1800a3b08  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3b0d  mov     eax, edi
0x1800a3b0f  jmp     loc_1800A3CB7
0x1800a3b14  lea     rcx, [rsp+0B8h+var_68]
0x1800a3b19  call    ??$ToUIntT@_K@String@Utils@Diagnostics@Microsoft@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned __int64>(std::wstring const &)
0x1800a3b1e  mov     [rsi+0A0h], rax
0x1800a3b25  mov     rcx, rbx; this
0x1800a3b28  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a3b2d  mov     edi, eax
0x1800a3b2f  test    eax, eax
0x1800a3b31  jns     short loc_1800A3B6C
0x1800a3b33  mov     rcx, [rsp+0B8h]; this
0x1800a3b3b  mov     r9d, eax; char *
0x1800a3b3e  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3b45  mov     edx, 124h; void *
0x1800a3b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3b4f  nop
0x1800a3b50  lea     rcx, [rsp+0B8h+var_68]
0x1800a3b55  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3b5a  nop
0x1800a3b5b  lea     rcx, [rsp+0B8h+var_88]
0x1800a3b60  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3b65  mov     eax, edi
0x1800a3b67  jmp     loc_1800A3CB7
0x1800a3b6c  lea     rcx, [rsp+0B8h+var_68]
0x1800a3b71  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3b76  jmp     short loc_1800A3BF1
0x1800a3b78  cmp     byte ptr [r13+98h], 0
0x1800a3b80  jz      short loc_1800A3BB5
0x1800a3b82  mov     rcx, [rsp+0B8h]; this
0x1800a3b8a  mov     ebx, 87C52407h
0x1800a3b8f  mov     r9d, ebx; char *
0x1800a3b92  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3b99  mov     edx, 12Ah; void *
0x1800a3b9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3ba3  nop
0x1800a3ba4  lea     rcx, [rsp+0B8h+var_88]
0x1800a3ba9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3bae  mov     eax, ebx
0x1800a3bb0  jmp     loc_1800A3CB7
0x1800a3bb5  mov     rcx, rbx; this
0x1800a3bb8  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a3bbd  mov     edi, eax
0x1800a3bbf  test    eax, eax
0x1800a3bc1  jns     short loc_1800A3BF1
0x1800a3bc3  mov     rcx, [rsp+0B8h]; this
0x1800a3bcb  mov     r9d, eax; char *
0x1800a3bce  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3bd5  mov     edx, 12Dh; void *
0x1800a3bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3bdf  nop
0x1800a3be0  lea     rcx, [rsp+0B8h+var_88]
0x1800a3be5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3bea  mov     eax, edi
0x1800a3bec  jmp     loc_1800A3CB7
0x1800a3bf1  lea     rcx, [rsp+0B8h+var_88]
0x1800a3bf6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3bfb  jmp     loc_1800A3873
0x1800a3c00  mov     ecx, 80000000h
0x1800a3c05  add     eax, ecx
0x1800a3c07  test    ecx, eax
0x1800a3c09  jnz     short loc_1800A3C36
0x1800a3c0b  cmp     edi, 80070272h
0x1800a3c11  jz      short loc_1800A3C36
0x1800a3c13  mov     rcx, [rsp+0B8h]; this
0x1800a3c1b  mov     r9d, edi; char *
0x1800a3c1e  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3c25  mov     edx, 131h; void *
0x1800a3c2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3c2f  mov     eax, edi
0x1800a3c31  jmp     loc_1800A3CB7
0x1800a3c36  cmp     r12d, 1
0x1800a3c3a  jnz     short loc_1800A3C8E
0x1800a3c3c  cmp     r15d, r12d
0x1800a3c3f  jnz     short loc_1800A3C8E
0x1800a3c41  mov     rax, [rsi]
0x1800a3c44  xor     edx, edx
0x1800a3c46  mov     rcx, rsi
0x1800a3c49  mov     rax, [rax+10h]
0x1800a3c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3c52  mov     rcx, [rsp+0B8h+var_90]
0x1800a3c57  call    ?pop_back@?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAXXZ; std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(void)
0x1800a3c5c  xor     eax, eax
0x1800a3c5e  jmp     short loc_1800A3CB7
0x1800a3c60  mov     rcx, rbx; this
0x1800a3c63  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a3c68  mov     ebx, eax
0x1800a3c6a  test    eax, eax
0x1800a3c6c  jns     short loc_1800A3C8E
0x1800a3c6e  mov     rcx, [rsp+0B8h]; this
0x1800a3c76  mov     r9d, eax; char *
0x1800a3c79  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3c80  mov     edx, 135h; void *
0x1800a3c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3c8a  mov     eax, ebx
0x1800a3c8c  jmp     short loc_1800A3CB7
0x1800a3c8e  mov     rcx, [rsp+0B8h]; this
0x1800a3c96  mov     ebx, 87C52402h
0x1800a3c9b  mov     r9d, ebx; char *
0x1800a3c9e  lea     r8, aOnecoreBaseTel_260; "onecore\\base\\telemetry\\utc\\service"...
0x1800a3ca5  mov     edx, 13Bh; void *
0x1800a3caa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3caf  mov     eax, ebx
  ... truncated ...
```

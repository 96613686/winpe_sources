# MakeOtherProfilesNonDefault(void *,_GUID const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180042f44`
- end: `0x18004364c`
- name: `?MakeOtherProfilesNonDefault@@YAXPEAXAEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z`
- size: `1800`
- prototype: `void __fastcall(void *hWwan, const _GUID *InterfaceGuid, const std::wstring *SubscriberId, const std::wstring *ProfileName)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043660`

## callees

- `0x180002790`
- `0x18000a42c`
- `0x18000af94`
- `0x18000fa6c`
- `0x180011844`
- `0x180011cfc`
- `0x180012400`
- `0x180012770`
- `0x180012bc8`
- `0x180020a6c`
- `0x180020bcc`
- `0x180020c48`
- `0x180020cd8`
- `0x180022c28`
- `0x180024960`
- `0x180042f44`
- `0x180048194`
- `0x180048558`
- `0x180048f28`
- `0x180048f78`
- `0x1800498dc`
- `0x180049d4c`
- `0x180049d70`
- `0x180049e4c`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180042fa6`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180042fa6`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x1800430a9`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x1800430a9`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetProfile` at `0x180043515`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetProfile` at `0x180043515`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180042ff8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800430fa`

## string_xrefs

- `0x18004313c`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x1800433ee`: `http://www.microsoft.com/networking/WWAN/profile/v1`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
void __fastcall MakeOtherProfilesNonDefault(
        void *hWwan,
        const _GUID *InterfaceGuid,
        std::wstring *SubscriberId,
        std::wstring *ProfileName)
{
  std::wstring *v4; // r12
  void *v6; // rbx
  int v7; // r15d
  int _a2; // eax
  WWAN_PROFILE_INFO_LIST *v9; // rdx
  __int64 v10; // rax
  const wchar_t *strProfileName; // rdi
  const wchar_t *v12; // rax
  unsigned __int64 v13; // r9
  unsigned int _a3; // eax
  WcmCommon::Xml::Document *Ptr; // rbx
  std::wstring *v16; // rax
  const wchar_t *v17; // rax
  __int64 v18; // rdx
  const wchar_t *v19; // r8
  unsigned __int64 v20; // r9
  WcmCommon::Xml::Document *v21; // rbx
  WcmCommon::Xml::Node *v22; // r12
  const std::wstring *v23; // rax
  bool v24; // bl
  WcmCommon::Xml::Document *v25; // rbx
  WcmCommon::Xml::Node *v26; // rbx
  WcmCommon::Xml::Node *v27; // r12
  const wchar_t *v28; // rax
  int v29; // eax
  unsigned int v30; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v31; // rcx
  int i; // [rsp+50h] [rbp-B0h]
  std::shared_ptr<WcmCommon::Xml::Document> xmlDoc; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+70h] [rbp-90h]
  const std::wstring *v36; // [rsp+78h] [rbp-88h]
  std::wstring Xml; // [rsp+80h] [rbp-80h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> isDefaultNode; // [rsp+A0h] [rbp-60h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> userName; // [rsp+B0h] [rbp-50h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> userLogonCred; // [rsp+D0h] [rbp-30h] BYREF
  std::_String_val<std::_Simple_types<unsigned short> > *v41; // [rsp+F0h] [rbp-10h]
  std::shared_ptr<WcmCommon::Xml::Node> ignorePasswordNode; // [rsp+F8h] [rbp-8h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> ignorePassword; // [rsp+108h] [rbp+8h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+118h] [rbp+18h] BYREF
  std::wstring result; // [rsp+130h] [rbp+30h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> v46; // [rsp+150h] [rbp+50h] BYREF
  std::wstring Path; // [rsp+168h] [rbp+68h] BYREF
  std::wstring v48; // [rsp+188h] [rbp+88h] BYREF
  std::wstring v49; // [rsp+1A8h] [rbp+A8h] BYREF
  std::wstring Text; // [rsp+1C8h] [rbp+C8h] BYREF
  std::wstring Name; // [rsp+1E8h] [rbp+E8h] BYREF
  WWAN_PROFILE_INFO_LIST *pProfileList; // [rsp+208h] [rbp+108h] BYREF
  wchar_t *profileXml; // [rsp+210h] [rbp+110h] BYREF
  WWAN_PROFILE_INVALID_REASON dwReasonCode; // [rsp+218h] [rbp+118h] BYREF
  unsigned int pdwFlags; // [rsp+21Ch] [rbp+11Ch] BYREF
  std::wstring newProfileXml; // [rsp+220h] [rbp+120h] BYREF

  v4 = ProfileName;
  v36 = ProfileName;
  v41 = (std::_String_val<std::_Simple_types<unsigned short> > *)SubscriberId;
  v6 = hWwan;
  v7 = 0;
  v35 = 0;
  pProfileList = 0;
  _a2 = WwanGetProfileList(hWwan, &GUID_NULL, 0, &pProfileList);
  if ( _a2 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
    {
      WPP_SF__guid_D(
        WPP_GLOBAL_Control->Control.Logger,
        0xCu,
        WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids,
        InterfaceGuid,
        _a2);
    }
  }
  else
  {
    v9 = pProfileList;
    v46.dismissed_ = 0;
    v46.fun_ = (void (__fastcall *)(void *))WwanFreeMemory;
    v46.p1_ = (WWAN_INTERFACE_OBJECT *const)pProfileList;
    v10 = 0;
    for ( i = 0; (unsigned int)v10 < pProfileList->dwNumberOfItems; v9 = pProfileList )
    {
      strProfileName = v9->pProfileInfo[v10].strProfileName;
      dwReasonCode = WwanProfileErrNone;
      profileXml = 0;
      pdwFlags = 0;
      std::_WChar_traits<unsigned short>::length(strProfileName);
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v4->_Mypair._Myval2);
      if ( !std::_Traits_equal<std::char_traits<unsigned short>>(v12, v4->_Mypair._Myval2._Mysize, strProfileName, v13) )
      {
        _a3 = WwanGetProfile(v6, &GUID_NULL, strProfileName, 0, &profileXml, &pdwFlags, 0);
        if ( _a3 )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
          {
            WPP_SF_S_guid_D(
              WPP_GLOBAL_Control->Control.Logger,
              0xDu,
              WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids,
              strProfileName,
              InterfaceGuid,
              _a3);
          }
        }
        else
        {
          j.dismissed_ = 0;
          j.fun_ = (void (__fastcall *)(void *))WwanFreeMemory;
          j.p1_ = (WWAN_INTERFACE_OBJECT *const)profileXml;
          xmlDoc = 0;
          std::wstring::wstring(&Xml, profileXml);
          WcmCommon::Xml::Document::LoadFromString(&xmlDoc, &Xml);
          std::wstring::_Tidy_deallocate(&Xml);
          Ptr = xmlDoc._Ptr;
          std::wstring::wstring((std::wstring *)&userName, L"http://www.microsoft.com/networking/WWAN/profile/v1");
          std::wstring::wstring((std::wstring *)&userLogonCred, L"default");
          WcmCommon::Xml::Document::AddSelectionNamespace(
            Ptr,
            (const std::wstring *)&userLogonCred,
            (const std::wstring *)&userName);
          std::wstring::_Tidy_deallocate((std::wstring *)&userLogonCred);
          std::wstring::_Tidy_deallocate((std::wstring *)&userName);
          std::wstring::wstring((std::wstring *)&userLogonCred, L"./default:SubscriberID");
          v16 = WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Document>>(
                  &result,
                  &xmlDoc,
                  (const std::wstring *)&userLogonCred);
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v16->_Mypair._Myval2);
          v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
          LOBYTE(Ptr) = std::_Traits_equal<std::char_traits<unsigned short>>(v17, *(_QWORD *)(v18 + 16), v19, v20);
          std::wstring::_Tidy_deallocate(&result);
          std::wstring::_Tidy_deallocate((std::wstring *)&userLogonCred);
          if ( (_BYTE)Ptr )
          {
            isDefaultNode = 0;
            v21 = xmlDoc._Ptr;
            std::wstring::wstring((std::wstring *)&userName, L"./default:IsDefault");
            WcmCommon::Xml::Document::SelectSingle(v21, &isDefaultNode, (const std::wstring *)&userName);
            std::wstring::_Tidy_deallocate((std::wstring *)&userName);
            v22 = isDefaultNode._Ptr;
            v24 = 1;
            if ( isDefaultNode._Ptr )
            {
              v23 = WcmCommon::Xml::Node::GetText(isDefaultNode._Ptr, &result);
              v7 |= 1u;
              v35 = v7;
              if ( WcmCommon::Xml::GetBooleanFieldValue(v23) )
                v24 = 0;
            }
            if ( (v7 & 1) != 0 )
            {
              v7 &= ~1u;
              std::wstring::_Tidy_deallocate(&result);
            }
            if ( !v24 )
            {
              if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
              {
                WPP_SF_S_guid_(
                  WPP_GLOBAL_Control->Control.Logger,
                  0xEu,
                  WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids,
                  strProfileName,
                  InterfaceGuid);
              }
              std::wstring::wstring(&Xml, L"false");
              WcmCommon::Xml::Node::SetText(v22, &Xml);
              std::wstring::_Tidy_deallocate(&Xml);
              userLogonCred = 0;
              v25 = xmlDoc._Ptr;
              std::wstring::wstring(&Path, L"./default:Context/default:UserLogonCred");
              WcmCommon::Xml::Document::SelectSingle(v25, &userLogonCred, &Path);
              std::wstring::_Tidy_deallocate(&Path);
              v26 = userLogonCred._Ptr;
              if ( userLogonCred._Ptr )
              {
                userName = 0;
                std::wstring::wstring(&v48, L"./default:UserName");
                WcmCommon::Xml::Node::SelectSingle(v26, &userName, &v48);
                std::wstring::_Tidy_deallocate(&v48);
                if ( userName._Ptr )
                {
                  ignorePassword = 0;
                  std::wstring::wstring(&v49, L"./default:IgnorePassword");
                  WcmCommon::Xml::Node::SelectSingle(v26, &ignorePassword, &v49);
                  std::wstring::_Tidy_deallocate(&v49);
                  v27 = ignorePassword._Ptr;
                  if ( ignorePassword._Ptr )
                  {
                    std::wstring::wstring(&Text, L"true");
                    WcmCommon::Xml::Node::SetText(v27, &Text);
                    std::wstring::_Tidy_deallocate(&Text);
                  }
                  else
                  {
                    ignorePasswordNode = 0;
                    Xml._Mypair._Myval2._Bx = 0;
                    std::wstring::wstring(&result, L"http://www.microsoft.com/networking/WWAN/profile/v1");
                    std::wstring::wstring(&Name, L"IgnorePassword");
                    WcmCommon::Xml::Node::CreateChild(
                      v26,
                      &ignorePasswordNode,
                      &Name,
                      &result,
                      (const std::shared_ptr<WcmCommon::Xml::Node> *)&Xml);
                    std::wstring::_Tidy_deallocate(&Name);
                    std::wstring::_Tidy_deallocate(&result);
                    if ( *(_QWORD *)&Xml._Mypair._Myval2._Bx._Alias[8] )
                      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&Xml._Mypair._Myval2._Bx._Alias[8]);
                    std::wstring::wstring(&Xml, L"true");
                    WcmCommon::Xml::Node::SetText(ignorePasswordNode._Ptr, &Xml);
                    std::wstring::_Tidy_deallocate(&Xml);
                    if ( ignorePasswordNode._Rep )
                      std::_Ref_count_base::_Decref(ignorePasswordNode._Rep);
                  }
                  if ( ignorePassword._Rep )
                    std::_Ref_count_base::_Decref(ignorePassword._Rep);
                }
                if ( userName._Rep )
                  std::_Ref_count_base::_Decref(userName._Rep);
              }
              WcmCommon::Xml::Document::GetXml((WcmCommon::Xml::Node *)xmlDoc._Ptr, &newProfileXml);
              v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&newProfileXml._Mypair._Myval2);
              v29 = WwanSetProfile(hWwan, &GUID_NULL, 0, v28, 0, 1, 0, 0, 0, &dwReasonCode);
              v30 = v29;
              if ( v29 )
              {
                if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x1000) != 0 )
                {
                  if ( v29 > 0 )
                    v29 = (unsigned __int16)v29 | 0x80070000;
                  McTemplateU0jzdq_EtwEventWriteTransfer(
                    (_MCGEN_TRACE_CONTEXT *)(unsigned int)dwReasonCode,
                    &SetWwanProfileFailed,
                    InterfaceGuid,
                    strProfileName,
                    v29,
                    dwReasonCode);
                }
                v31 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                {
                  if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
                  {
                    WPP_SF_S_guid_D(
                      WPP_GLOBAL_Control->Control.Logger,
                      0xFu,
                      WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids,
                      strProfileName,
                      InterfaceGuid,
                      v30);
                    v31 = WPP_GLOBAL_Control;
                  }
                  if ( v31 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v31->ReserveSpace[28] & 8) != 0 )
                    WPP_SF_d(v31->Control.Logger, 0x10u, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids, dwReasonCode);
                }
              }
              std::wstring::_Tidy_deallocate(&newProfileXml);
              if ( userLogonCred._Rep )
                std::_Ref_count_base::_Decref(userLogonCred._Rep);
            }
            if ( isDefaultNode._Rep )
              std::_Ref_count_base::_Decref(isDefaultNode._Rep);
            if ( xmlDoc._Rep )
              std::_Ref_count_base::_Decref(xmlDoc._Rep);
            ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
            v4 = (std::wstring *)v36;
          }
          else
          {
            if ( xmlDoc._Rep )
              std::_Ref_count_base::_Decref(xmlDoc._Rep);
            ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
          }
          v6 = hWwan;
        }
      }
      v10 = (unsigned int)(i + 1);
      i = v10;
    }
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&v46);
  }
}

```

## disassembly

```asm
0x180042f44  push    rbp
0x180042f46  push    rbx
0x180042f47  push    rsi
0x180042f48  push    rdi
0x180042f49  push    r12
0x180042f4b  push    r13
0x180042f4d  push    r15
0x180042f4f  lea     rbp, [rsp-150h]
0x180042f57  sub     rsp, 250h
0x180042f5e  mov     rax, cs:__security_cookie
0x180042f65  xor     rax, rsp
0x180042f68  mov     [rbp+180h+var_40], rax
0x180042f6f  mov     r12, ProfileName
0x180042f72  mov     [rsp+280h+var_208], ProfileName
0x180042f77  mov     [rbp+180h+var_190], SubscriberId
0x180042f7b  mov     r13, InterfaceGuid
0x180042f7e  mov     rbx, hWwan
0x180042f81  mov     [rsp+280h+var_228], hWwan
0x180042f86  xor     r15d, r15d
0x180042f89  mov     [rsp+280h+var_210], r15d
0x180042f8e  mov     [rbp+180h+pProfileList], r15
0x180042f95  lea     ProfileName, [rbp+180h+pProfileList]
0x180042f9c  xor     r8d, r8d
0x180042f9f  lea     InterfaceGuid, GUID_NULL
0x180042fa6  call    cs:__imp_WwanGetProfileList
0x180042fac  test    eax, eax
0x180042fae  jz      short loc_180042FF1
0x180042fb0  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180042fb7  mov     hWwan, cs:WPP_GLOBAL_Control
0x180042fbe  cmp     hWwan, rsi
0x180042fc1  jz      loc_18004362B
0x180042fc7  test    byte ptr [hWwan+1Ch], 8
0x180042fcb  jz      loc_18004362B
0x180042fd1  lea     edx, [r15+0Ch]; id
0x180042fd5  mov     [rsp+280h+_a2], eax; _a2
0x180042fd9  mov     ProfileName, r13; _a1
0x180042fdc  lea     SubscriberId, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180042fe3  mov     hWwan, [hWwan+10h]; Logger
0x180042fe7  call    WPP_SF__guid_D
0x180042fec  jmp     loc_18004362B
0x180042ff1  mov     InterfaceGuid, [rbp+180h+pProfileList]
0x180042ff8  mov     rax, cs:__imp_WwanFreeMemory
0x180042fff  mov     [rbp+180h+var_130.dismissed_], r15b
0x180043003  mov     [rbp+180h+var_130.fun_], rax
0x180043007  mov     [rbp+180h+var_130.p1_], InterfaceGuid
0x18004300b  xor     eax, eax
0x18004300d  mov     [rsp+280h+var_230], eax
0x180043011  cmp     [InterfaceGuid], eax
0x180043013  jbe     loc_180043622
0x180043019  lea     rsi, WPP_GLOBAL_Control
0x180043020  imul    hWwan, rax, 204h
0x180043027  lea     rdi, [InterfaceGuid+4]
0x18004302b  add     rdi, hWwan
0x18004302e  mov     [rbp+180h+dwReasonCode], 0
0x180043038  mov     [rbp+180h+profileXml], 0
0x180043043  mov     [rbp+180h+pdwFlags], 0
0x18004304d  mov     hWwan, rdi; _First
0x180043050  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180043055  mov     ProfileName, rax
0x180043058  mov     hWwan, r12; this
0x18004305b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043060  mov     SubscriberId, rdi; _Right
0x180043063  mov     InterfaceGuid, [r12+10h]; _Left_size
0x180043068  mov     hWwan, rax; _Left
0x18004306b  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180043070  test    al, al
0x180043072  jnz     loc_180043609
0x180043078  mov     [rsp+280h+var_250], 0
0x180043081  lea     rax, [rbp+180h+pdwFlags]
0x180043088  mov     qword ptr [rsp+280h+_a3], rax
0x18004308d  lea     rax, [rbp+180h+profileXml]
0x180043094  mov     qword ptr [rsp+280h+_a2], rax
0x180043099  xor     r9d, r9d
0x18004309c  mov     SubscriberId, rdi
0x18004309f  lea     InterfaceGuid, GUID_NULL
0x1800430a6  mov     hWwan, rbx
0x1800430a9  call    cs:__imp_WwanGetProfile
0x1800430af  test    eax, eax
0x1800430b1  jz      short loc_1800430F3
0x1800430b3  mov     hWwan, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800430ba  cmp     hWwan, rsi
0x1800430bd  jz      loc_180043609
0x1800430c3  test    byte ptr [hWwan+1Ch], 8
0x1800430c7  jz      loc_180043609
0x1800430cd  mov     edx, 0Dh; id
0x1800430d2  mov     [rsp+280h+_a3], eax; _a3
0x1800430d6  mov     qword ptr [rsp+280h+_a2], r13; _a2
0x1800430db  mov     ProfileName, rdi; _a1
0x1800430de  lea     SubscriberId, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x1800430e5  mov     hWwan, [hWwan+10h]; Logger
0x1800430e9  call    WPP_SF_S_guid_D
0x1800430ee  jmp     loc_180043609
0x1800430f3  mov     InterfaceGuid, [rbp+180h+profileXml]; _Ptr
0x1800430fa  mov     rax, cs:__imp_WwanFreeMemory
0x180043101  mov     [rbp+180h+j.dismissed_], 0
0x180043105  mov     [rbp+180h+j.fun_], rax
0x180043109  mov     [rbp+180h+j.p1_], InterfaceGuid
0x18004310d  xorps   xmm0, xmm0
0x180043110  movups  xmmword ptr [rsp+280h+xmlDoc._Ptr], xmm0
0x180043115  lea     hWwan, [rbp+180h+Xml]; this
0x180043119  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004311e  nop
0x18004311f  lea     InterfaceGuid, [rbp+180h+Xml]; Xml
0x180043123  lea     hWwan, [rsp+280h+xmlDoc]; result
0x180043128  call    ?LoadFromString@Document@Xml@WcmCommon@@SA?AV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::LoadFromString(std::wstring const &)
0x18004312d  nop
0x18004312e  lea     hWwan, [rbp+180h+Xml]; this
0x180043132  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043137  mov     rbx, [rsp+280h+xmlDoc._Ptr]
0x18004313c  lea     InterfaceGuid, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x180043143  lea     hWwan, [rbp+180h+userName]; this
0x180043147  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004314c  nop
0x18004314d  lea     InterfaceGuid, aDefault; "default"
0x180043154  lea     hWwan, [rbp+180h+userLogonCred]; this
0x180043158  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004315d  nop
0x18004315e  lea     SubscriberId, [rbp+180h+userName]; ns
0x180043162  lea     InterfaceGuid, [rbp+180h+userLogonCred]; key
0x180043166  mov     hWwan, rbx; this
0x180043169  call    ?AddSelectionNamespace@Document@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WcmCommon::Xml::Document::AddSelectionNamespace(std::wstring const &,std::wstring const &)
0x18004316e  nop
0x18004316f  lea     hWwan, [rbp+180h+userLogonCred]; this
0x180043173  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043178  nop
0x180043179  lea     hWwan, [rbp+180h+userName]; this
0x18004317d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043182  lea     InterfaceGuid, aDefaultSubscri; "./default:SubscriberID"
0x180043189  lea     hWwan, [rbp+180h+userLogonCred]; this
0x18004318d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043192  nop
0x180043193  lea     SubscriberId, [rbp+180h+userLogonCred]; Path
0x180043197  lea     InterfaceGuid, [rsp+280h+xmlDoc]; s
0x18004319c  lea     hWwan, [rbp+180h+result]; result
0x1800431a0  call    ??$ExtractText@V?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@@Xml@WcmCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VDocument@Xml@WcmCommon@@@3@AEBV23@@Z; WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Document>>(std::shared_ptr<WcmCommon::Xml::Document> const &,std::wstring const &)
0x1800431a5  mov     ProfileName, [rax+10h]
0x1800431a9  mov     hWwan, rax; this
0x1800431ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800431b1  mov     SubscriberId, rax
0x1800431b4  mov     InterfaceGuid, [rbp+180h+var_190]
0x1800431b8  mov     hWwan, InterfaceGuid; this
0x1800431bb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800431c0  mov     InterfaceGuid, [InterfaceGuid+10h]; _Left_size
0x1800431c4  mov     hWwan, rax; _Left
0x1800431c7  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800431cc  mov     bl, al
0x1800431ce  lea     hWwan, [rbp+180h+result]; this
0x1800431d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800431d7  nop
0x1800431d8  lea     hWwan, [rbp+180h+userLogonCred]; this
0x1800431dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800431e1  test    bl, bl
0x1800431e3  jnz     short loc_180043203
0x1800431e5  mov     hWwan, [rsp+280h+xmlDoc._Rep]; this
0x1800431ea  test    hWwan, hWwan
0x1800431ed  jz      short loc_1800431F5
0x1800431ef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800431f4  nop
0x1800431f5  lea     hWwan, [rbp+180h+j]; j
0x1800431f9  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x1800431fe  jmp     loc_180043604
0x180043203  xorps   xmm0, xmm0
0x180043206  movups  xmmword ptr [rbp+180h+isDefaultNode._Ptr], xmm0
0x18004320a  mov     rbx, [rsp+280h+xmlDoc._Ptr]
0x18004320f  lea     InterfaceGuid, aDefaultIsdefau; "./default:IsDefault"
0x180043216  lea     hWwan, [rbp+180h+userName]; this
0x18004321a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004321f  nop
0x180043220  lea     SubscriberId, [rbp+180h+userName]; Path
0x180043224  lea     InterfaceGuid, [rbp+180h+isDefaultNode]; result
0x180043228  mov     hWwan, rbx; this
0x18004322b  call    ?SelectSingle@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::SelectSingle(std::wstring const &)
0x180043230  nop
0x180043231  lea     hWwan, [rbp+180h+userName]; this
0x180043235  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004323a  mov     r12, [rbp+180h+isDefaultNode._Ptr]
0x18004323e  test    r12, r12
0x180043241  jz      short loc_180043269
0x180043243  lea     InterfaceGuid, [rbp+180h+result]; result
0x180043247  mov     hWwan, r12; this
0x18004324a  call    ?GetText@Node@Xml@WcmCommon@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WcmCommon::Xml::Node::GetText(void)
0x18004324f  nop
0x180043250  or      r15d, 1
0x180043254  mov     [rsp+280h+var_210], r15d
0x180043259  mov     hWwan, rax; BooleanField
0x18004325c  call    ?GetBooleanFieldValue@Xml@WcmCommon@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::GetBooleanFieldValue(std::wstring const &)
0x180043261  test    al, al
0x180043263  jz      short loc_180043269
0x180043265  xor     bl, bl
0x180043267  jmp     short loc_18004326B
0x180043269  mov     bl, 1
0x18004326b  test    r15b, 1
0x18004326f  jz      short loc_18004327E
0x180043271  and     r15d, 0FFFFFFFEh
0x180043275  lea     hWwan, [rbp+180h+result]; this
0x180043279  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004327e  test    bl, bl
0x180043280  jnz     loc_1800435D7
0x180043286  mov     hWwan, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18004328d  cmp     hWwan, rsi
0x180043290  jz      short loc_1800432B5
0x180043292  test    byte ptr [hWwan+1Ch], 10h
0x180043296  jz      short loc_1800432B5
0x180043298  mov     edx, 0Eh; id
0x18004329d  mov     qword ptr [rsp+280h+_a2], r13; _a2
0x1800432a2  mov     ProfileName, rdi; _a1
0x1800432a5  lea     SubscriberId, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x1800432ac  mov     hWwan, [hWwan+10h]; Logger
0x1800432b0  call    WPP_SF_S_guid_
0x1800432b5  lea     InterfaceGuid, aFalse; "false"
0x1800432bc  lea     hWwan, [rbp+180h+Xml]; this
0x1800432c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800432c5  nop
0x1800432c6  lea     InterfaceGuid, [rbp+180h+Xml]; Text
0x1800432ca  mov     hWwan, r12; this
0x1800432cd  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x1800432d2  nop
0x1800432d3  lea     hWwan, [rbp+180h+Xml]; this
0x1800432d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800432dc  xorps   xmm0, xmm0
0x1800432df  movups  xmmword ptr [rbp+180h+userLogonCred._Ptr], xmm0
0x1800432e3  mov     rbx, [rsp+280h+xmlDoc._Ptr]
0x1800432e8  lea     InterfaceGuid, aDefaultContext; "./default:Context/default:UserLogonCred"
0x1800432ef  lea     hWwan, [rbp+180h+Path]; this
0x1800432f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800432f8  nop
0x1800432f9  lea     SubscriberId, [rbp+180h+Path]; Path
0x1800432fd  lea     InterfaceGuid, [rbp+180h+userLogonCred]; result
0x180043301  mov     hWwan, rbx; this
0x180043304  call    ?SelectSingle@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::SelectSingle(std::wstring const &)
0x180043309  nop
0x18004330a  lea     hWwan, [rbp+180h+Path]; this
0x18004330e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043313  mov     rbx, [rbp+180h+userLogonCred._Ptr]
0x180043317  test    rbx, rbx
0x18004331a  jz      loc_1800434AE
0x180043320  xorps   xmm0, xmm0
0x180043323  movups  xmmword ptr [rbp+180h+userName._Ptr], xmm0
0x180043327  lea     InterfaceGuid, aDefaultUsernam; "./default:UserName"
0x18004332e  lea     hWwan, [rbp+180h+var_F8]; this
0x180043335  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004333a  nop
0x18004333b  lea     SubscriberId, [rbp+180h+var_F8]; Path
0x180043342  lea     InterfaceGuid, [rbp+180h+userName]; result
0x180043346  mov     hWwan, rbx; this
0x180043349  call    ?SelectSingle@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Node::SelectSingle(std::wstring const &)
0x18004334e  nop
0x18004334f  lea     hWwan, [rbp+180h+var_F8]; this
0x180043356  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004335b  cmp     [rbp+180h+userName._Ptr], 0
0x180043360  jz      loc_1800434A0
0x180043366  xorps   xmm0, xmm0
0x180043369  movups  xmmword ptr [rbp+180h+ignorePassword._Ptr], xmm0
0x18004336d  lea     InterfaceGuid, aDefaultIgnorep; "./default:IgnorePassword"
0x180043374  lea     hWwan, [rbp+180h+var_D8]; this
0x18004337b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043380  nop
0x180043381  lea     SubscriberId, [rbp+180h+var_D8]; Path
0x180043388  lea     InterfaceGuid, [rbp+180h+ignorePassword]; result
0x18004338c  mov     hWwan, rbx; this
0x18004338f  call    ?SelectSingle@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Node::SelectSingle(std::wstring const &)
0x180043394  nop
0x180043395  lea     hWwan, [rbp+180h+var_D8]; this
0x18004339c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800433a1  mov     r12, [rbp+180h+ignorePassword._Ptr]
0x1800433a5  test    r12, r12
0x1800433a8  jz      short loc_1800433DF
0x1800433aa  lea     InterfaceGuid, aTrue; "true"
0x1800433b1  lea     hWwan, [rbp+180h+Text]; this
0x1800433b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800433bd  nop
0x1800433be  lea     InterfaceGuid, [rbp+180h+Text]; Text
0x1800433c5  mov     hWwan, r12; this
0x1800433c8  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x1800433cd  nop
0x1800433ce  lea     hWwan, [rbp+180h+Text]; this
0x1800433d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800433da  jmp     loc_180043491
0x1800433df  xorps   xmm0, xmm0
0x1800433e2  movups  xmmword ptr [rbp+180h+ignorePasswordNode._Ptr], xmm0
0x1800433e6  xorps   xmm1, xmm1
0x1800433e9  movdqu  xmmword ptr [rbp+180h+Xml._Mypair._Myval2._Bx], xmm1
0x1800433ee  lea     InterfaceGuid, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x1800433f5  lea     hWwan, [rbp+180h+result]; this
0x1800433f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800433fe  nop
0x1800433ff  lea     InterfaceGuid, aIgnorepassword; "IgnorePassword"
0x180043406  lea     hWwan, [rbp+180h+Name]; this
0x18004340d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043412  nop
0x180043413  lea     rax, [rbp+180h+Xml]
0x180043417  mov     qword ptr [rsp+280h+_a2], rax; insertBefore
0x18004341c  lea     ProfileName, [rbp+180h+result]; Namespace
0x180043420  lea     SubscriberId, [rbp+180h+Name]; Name
0x180043427  lea     InterfaceGuid, [rbp+180h+ignorePasswordNode]; result
0x18004342b  mov     hWwan, rbx; this
0x18004342e  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180043433  nop
0x180043434  lea     hWwan, [rbp+180h+Name]; this
0x18004343b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```

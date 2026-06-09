# WwanHandler::DeleteProfiles(std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,bool)

- ea: `0x180042298`
- end: `0x1800426fb`
- name: `?DeleteProfiles@WwanHandler@@AEAAXAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_N@Z`
- size: `1123`
- prototype: `void __fastcall(WwanHandler *this, const std::set<std::wstring> *NewProfiles, bool DeleteOnlyProvisionedProfiles)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042704`
- `0x180044560`

## callees

- `0x180002790`
- `0x18000a42c`
- `0x18000af94`
- `0x18000b0a0`
- `0x18000b178`
- `0x180011844`
- `0x180011cfc`
- `0x180012770`
- `0x18001282c`
- `0x180012bc8`
- `0x18001a0d4`
- `0x18001aa2c`
- `0x180020a14`
- `0x180020bcc`
- `0x180020c48`
- `0x180020cd8`
- `0x18003fc60`
- `0x1800406f0`
- `0x180042298`
- `0x180044fec`
- `0x180045580`
- `0x180045d80`
- `0x180046114`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180042358`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180042358`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x180042680`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x180042680`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x180042463`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x180042463`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800426ce`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800426ce`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800423a9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800424b9`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmCloseHandle` at `0x1800426c1`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmCloseHandle` at `0x1800426c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall WwanHandler::DeleteProfiles(
        WwanHandler *this,
        const std::set<std::wstring> *NewProfiles,
        bool DeleteOnlyProvisionedProfiles)
{
  int WwanInterface; // eax
  int _a2; // eax
  WWAN_PROFILE_INFO_LIST *v8; // rdx
  unsigned int v9; // r14d
  const wchar_t *strProfileName; // rsi
  bool v11; // bl
  signed int Profile; // eax
  bool IsAdditionalPdpContextProfile; // bl
  bool IsOperatorProvisionedProfile; // bl
  bool v15; // bl
  unsigned int _a3; // eax
  const wchar_t *v17; // rax
  const wchar_t *v18; // r8
  const wchar_t *v19; // rax
  const wchar_t *v20; // r8
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+40h] [rbp-C0h] BYREF
  WwanHandler::DeleteProfiles::__l28::<lambda_1> f; // [rsp+58h] [rbp-A8h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> v23; // [rsp+70h] [rbp-90h] BYREF
  std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring > > > result; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *pProfileXml; // [rsp+90h] [rbp-70h] BYREF
  WWAN_PROFILE_INFO_LIST *pProfileList; // [rsp+98h] [rbp-68h] BYREF
  Wwan wwan; // [rsp+A0h] [rbp-60h] BYREF
  Wcmutil wcm; // [rsp+A8h] [rbp-58h] BYREF
  _GUID interfaceGuid; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int pFlags; // [rsp+C0h] [rbp-40h] BYREF
  std::wstring carrierId; // [rsp+C8h] [rbp-38h] BYREF
  std::vector<unsigned char> DataBlob; // [rsp+E8h] [rbp-18h] BYREF
  std::wstring subscriberId; // [rsp+100h] [rbp+0h] BYREF

  interfaceGuid = 0;
  wwan.m_handle = 0;
  Wwan::Wwan(&wwan);
  WwanInterface = Wwan::FindWwanInterface(&wwan, &this->m_params.SubscriberId, &this->m_params.DeviceId, &interfaceGuid);
  if ( WwanInterface >= 0 )
  {
    wcm.m_hWcm = 0;
    Wcmutil::Wcmutil(&wcm);
    pProfileList = 0;
    _a2 = WwanGetProfileList(wwan.m_handle, &interfaceGuid, 0, &pProfileList);
    if ( _a2 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
      {
        WPP_SF__guid_D(
          WPP_GLOBAL_Control->Control.Logger,
          0x34u,
          WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids,
          &interfaceGuid,
          _a2);
      }
      goto LABEL_37;
    }
    v8 = pProfileList;
    v23.dismissed_ = 0;
    v23.fun_ = (void (__fastcall *)(void *))WwanFreeMemory;
    v23.p1_ = (WWAN_INTERFACE_OBJECT *const)pProfileList;
    v9 = 0;
    if ( !pProfileList->dwNumberOfItems )
    {
LABEL_36:
      ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&v23);
LABEL_37:
      WcmCloseHandle(wcm.m_hWcm, 0);
      goto LABEL_38;
    }
    while ( 1 )
    {
      strProfileName = v8->pProfileInfo[v9].strProfileName;
      memset(&DataBlob, 0, sizeof(DataBlob));
      std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&DataBlob);
      if ( NewProfiles->_Mypair._Myval2._Myval2._Mysize )
      {
        std::wstring::wstring(&carrierId, strProfileName);
        v11 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                &NewProfiles->std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring >,std::allocator<std::wstring >,0> >,
                &result,
                &carrierId)->_Ptr != NewProfiles->_Mypair._Myval2._Myval2._Myhead;
        std::wstring::_Tidy_deallocate(&carrierId);
        if ( v11 )
          goto LABEL_35;
      }
      pProfileXml = 0;
      pFlags = 0;
      Profile = WwanGetProfile(wwan.m_handle, &interfaceGuid, strProfileName, 0, &pProfileXml, &pFlags, 0);
      if ( Profile )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
        {
          if ( Profile > 0 )
            Profile = (unsigned __int16)Profile | 0x80070000;
          WPP_SF_Sd(
            WPP_GLOBAL_Control->Control.Logger,
            0x35u,
            WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids,
            pProfileXml,
            Profile);
        }
        goto LABEL_35;
      }
      j.dismissed_ = 0;
      j.fun_ = (void (__fastcall *)(void *))WwanFreeMemory;
      j.p1_ = (WWAN_INTERFACE_OBJECT *const)pProfileXml;
      std::wstring::wstring(&carrierId, pProfileXml);
      IsAdditionalPdpContextProfile = Wwan::IsAdditionalPdpContextProfile(&carrierId);
      std::wstring::_Tidy_deallocate(&carrierId);
      if ( !IsAdditionalPdpContextProfile )
      {
        std::wstring::wstring(&carrierId, pProfileXml);
        IsOperatorProvisionedProfile = Wwan::IsOperatorProvisionedProfile(&carrierId);
        std::wstring::_Tidy_deallocate(&carrierId);
        if ( IsOperatorProvisionedProfile )
        {
          v15 = !DeleteOnlyProvisionedProfiles;
          if ( !DeleteOnlyProvisionedProfiles )
            goto LABEL_29;
          _a3 = Wcmutil::WcmQueryParameterBlob(
                  &wcm,
                  &interfaceGuid,
                  strProfileName,
                  wcm_intf_opcode_provisioning,
                  &DataBlob);
          if ( !_a3 )
          {
            std::wstring::wstring(&carrierId);
            std::wstring::wstring(&subscriberId);
            f.DataBlob = &DataBlob;
            f.carrierId = &carrierId;
            f.subscriberId = &subscriberId;
            ExecuteAndConvertAnyException__WwanHandler::DeleteProfiles_::_28_::_lambda_1___(&f);
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_params.CarrierId._Mypair._Myval2);
            v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&carrierId._Mypair._Myval2);
            if ( std::_Traits_equal<std::char_traits<unsigned short>>(
                   v17,
                   carrierId._Mypair._Myval2._Mysize,
                   v18,
                   this->m_params.CarrierId._Mypair._Myval2._Mysize) )
            {
              std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_params.SubscriberId._Mypair._Myval2);
              v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&subscriberId._Mypair._Myval2);
              if ( std::_Traits_equal<std::char_traits<unsigned short>>(
                     v19,
                     subscriberId._Mypair._Myval2._Mysize,
                     v20,
                     this->m_params.SubscriberId._Mypair._Myval2._Mysize) )
              {
                v15 = 1;
              }
            }
            std::wstring::_Tidy_deallocate(&subscriberId);
            std::wstring::_Tidy_deallocate(&carrierId);
LABEL_29:
            if ( v15 )
            {
              if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
              {
                WPP_SF_S_guid_(
                  WPP_GLOBAL_Control->Control.Logger,
                  0x37u,
                  WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids,
                  strProfileName,
                  &interfaceGuid);
              }
              WwanDeleteProfile(wwan.m_handle, &interfaceGuid, strProfileName, 0);
            }
            goto LABEL_34;
          }
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_S_guid_D(
              WPP_GLOBAL_Control->Control.Logger,
              0x36u,
              WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids,
              strProfileName,
              &interfaceGuid,
              _a3);
          }
        }
      }
LABEL_34:
      ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
LABEL_35:
      std::vector<unsigned char>::_Tidy((std::vector<char> *)&DataBlob);
      ++v9;
      v8 = pProfileList;
      if ( v9 >= pProfileList->dwNumberOfItems )
        goto LABEL_36;
    }
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x33u, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids, WwanInterface);
  }
LABEL_38:
  WwanCloseHandle(wwan.m_handle, 0);
}

```

## disassembly

```asm
0x180042298  mov     [rsp-8+arg_10], rbx
0x18004229d  push    rbp
0x18004229e  push    rsi
0x18004229f  push    rdi
0x1800422a0  push    r12
0x1800422a2  push    r13
0x1800422a4  push    r14
0x1800422a6  push    r15
0x1800422a8  lea     rbp, [rsp-30h]
0x1800422ad  sub     rsp, 130h
0x1800422b4  mov     rax, cs:__security_cookie
0x1800422bb  xor     rax, rsp
0x1800422be  mov     [rbp+60h+var_40], rax
0x1800422c2  mov     r13b, DeleteOnlyProvisionedProfiles
0x1800422c5  mov     r12, NewProfiles
0x1800422c8  mov     r15, this
0x1800422cb  xorps   xmm0, xmm0
0x1800422ce  movups  xmmword ptr [rbp+60h+interfaceGuid.Data1], xmm0
0x1800422d2  xor     ebx, ebx
0x1800422d4  mov     [rbp+60h+wwan.m_handle], rbx
0x1800422d8  lea     this, [rbp+60h+wwan]; this
0x1800422dc  call    ??0Wwan@@QEAA@XZ; Wwan::Wwan(void)
0x1800422e1  nop
0x1800422e2  lea     NewProfiles, [r15+28h]; SubscriberId
0x1800422e6  lea     r8, [r15+48h]; DeviceId
0x1800422ea  lea     r9, [rbp+60h+interfaceGuid]; InterfaceGuid
0x1800422ee  lea     this, [rbp+60h+wwan]; this
0x1800422f2  call    ?FindWwanInterface@Wwan@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU_GUID@@@Z; Wwan::FindWwanInterface(std::wstring const &,std::wstring const &,_GUID &)
0x1800422f7  test    eax, eax
0x1800422f9  jns     short loc_180042337
0x1800422fb  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180042302  mov     this, cs:WPP_GLOBAL_Control
0x180042309  cmp     this, rdi
0x18004230c  jz      loc_1800426C8
0x180042312  test    byte ptr [this+1Ch], 4
0x180042316  jz      loc_1800426C8
0x18004231c  lea     edx, [rbx+33h]; id
0x18004231f  mov     r9d, eax; _a1
0x180042322  lea     r8, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180042329  mov     this, [this+10h]; Logger
0x18004232d  call    WPP_SF_d
0x180042332  jmp     loc_1800426C8
0x180042337  mov     [rbp+60h+wcm.m_hWcm], rbx
0x18004233b  lea     this, [rbp+60h+wcm]; this
0x18004233f  call    ??0Wcmutil@@QEAA@XZ; Wcmutil::Wcmutil(void)
0x180042344  nop
0x180042345  mov     [rbp+60h+pProfileList], rbx
0x180042349  lea     r9, [rbp+60h+pProfileList]
0x18004234d  xor     r8d, r8d
0x180042350  lea     NewProfiles, [rbp+60h+interfaceGuid]
0x180042354  mov     this, [rbp+60h+wwan.m_handle]
0x180042358  call    cs:__imp_WwanGetProfileList
0x18004235e  test    eax, eax
0x180042360  jz      short loc_1800423A5
0x180042362  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180042369  mov     this, cs:WPP_GLOBAL_Control
0x180042370  cmp     this, rdi
0x180042373  jz      loc_1800426BB
0x180042379  test    byte ptr [this+1Ch], 8
0x18004237d  jz      loc_1800426BB
0x180042383  mov     edx, 34h ; '4'; id
0x180042388  mov     [rsp+160h+_a2], eax; _a2
0x18004238c  lea     r9, [rbp+60h+interfaceGuid]; _a1
0x180042390  lea     r8, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180042397  mov     this, [this+10h]; Logger
0x18004239b  call    WPP_SF__guid_D
0x1800423a0  jmp     loc_1800426BB
0x1800423a5  mov     NewProfiles, [rbp+60h+pProfileList]
0x1800423a9  mov     rax, cs:__imp_WwanFreeMemory
0x1800423b0  mov     [rsp+160h+var_F0.dismissed_], bl
0x1800423b4  mov     [rsp+160h+var_F0.fun_], rax
0x1800423b9  mov     [rbp+60h+var_F0.p1_], NewProfiles
0x1800423bd  mov     r14d, ebx
0x1800423c0  cmp     [NewProfiles], ebx
0x1800423c2  jbe     loc_1800426B0
0x1800423c8  lea     rdi, WPP_GLOBAL_Control
0x1800423cf  mov     eax, r14d
0x1800423d2  imul    rsi, rax, 204h
0x1800423d9  add     rsi, 4
0x1800423dd  add     rsi, NewProfiles
0x1800423e0  xorps   xmm0, xmm0
0x1800423e3  xor     eax, eax
0x1800423e5  movups  xmmword ptr [rbp+60h+DataBlob._Mypair._Myval2._Myfirst], xmm0
0x1800423e9  mov     [rbp+60h+DataBlob._Mypair._Myval2._Myend], rax
0x1800423ed  lea     this, [rbp+60h+DataBlob]; this
0x1800423f1  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x1800423f6  nop
0x1800423f7  cmp     [r12+8], rbx
0x1800423fc  jz      short loc_180042437
0x1800423fe  mov     NewProfiles, rsi; _Ptr
0x180042401  lea     this, [rbp+60h+carrierId]; this
0x180042405  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004240a  lea     r8, [rbp+60h+carrierId]; _Keyval
0x18004240e  lea     NewProfiles, [rbp+60h+result]; result
0x180042412  mov     this, r12; this
0x180042415  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x18004241a  mov     this, [r12]
0x18004241e  cmp     [rax], this
0x180042421  setnz   bl
0x180042424  lea     this, [rbp+60h+carrierId]; this
0x180042428  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004242d  test    bl, bl
0x18004242f  jnz     loc_180042692
0x180042435  xor     ebx, ebx
0x180042437  mov     [rbp+60h+pProfileXml], rbx
0x18004243b  mov     [rbp+60h+pFlags], ebx
0x18004243e  mov     [rsp+160h+var_130], rbx
0x180042443  lea     rax, [rbp+60h+pFlags]
0x180042447  mov     qword ptr [rsp+160h+_a3], rax
0x18004244c  lea     rax, [rbp+60h+pProfileXml]
0x180042450  mov     qword ptr [rsp+160h+_a2], rax
0x180042455  xor     r9d, r9d
0x180042458  mov     r8, rsi
0x18004245b  lea     NewProfiles, [rbp+60h+interfaceGuid]
0x18004245f  mov     this, [rbp+60h+wwan.m_handle]
0x180042463  call    cs:__imp_WwanGetProfile
0x180042469  test    eax, eax
0x18004246b  jz      short loc_1800424B5
0x18004246d  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180042474  cmp     this, rdi
0x180042477  jz      loc_180042692
0x18004247d  test    byte ptr [this+1Ch], 4
0x180042481  jz      loc_180042692
0x180042487  test    eax, eax
0x180042489  jle     short loc_180042493
0x18004248b  movzx   eax, ax
0x18004248e  or      eax, 80070000h
0x180042493  mov     edx, 35h ; '5'; id
0x180042498  mov     [rsp+160h+_a2], eax; _a2
0x18004249c  mov     r9, [rbp+60h+pProfileXml]; _a1
0x1800424a0  lea     r8, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x1800424a7  mov     this, [this+10h]; Logger
0x1800424ab  call    WPP_SF_Sd
0x1800424b0  jmp     loc_180042692
0x1800424b5  mov     NewProfiles, [rbp+60h+pProfileXml]; _Ptr
0x1800424b9  mov     rax, cs:__imp_WwanFreeMemory
0x1800424c0  mov     [rsp+160h+j.dismissed_], bl
0x1800424c4  mov     [rsp+160h+j.fun_], rax
0x1800424c9  mov     [rsp+160h+j.p1_], NewProfiles
0x1800424ce  lea     this, [rbp+60h+carrierId]; this
0x1800424d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800424d7  nop
0x1800424d8  lea     this, [rbp+60h+carrierId]; ProfileXml
0x1800424dc  call    ?IsAdditionalPdpContextProfile@Wwan@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Wwan::IsAdditionalPdpContextProfile(std::wstring const &)
0x1800424e1  mov     bl, al
0x1800424e3  lea     this, [rbp+60h+carrierId]; this
0x1800424e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800424ec  test    bl, bl
0x1800424ee  jnz     loc_180042687
0x1800424f4  mov     NewProfiles, [rbp+60h+pProfileXml]; _Ptr
0x1800424f8  lea     this, [rbp+60h+carrierId]; this
0x1800424fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042501  nop
0x180042502  lea     this, [rbp+60h+carrierId]; ProfileXml
0x180042506  call    ?IsOperatorProvisionedProfile@Wwan@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Wwan::IsOperatorProvisionedProfile(std::wstring const &)
0x18004250b  mov     bl, al
0x18004250d  lea     this, [rbp+60h+carrierId]; this
0x180042511  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042516  test    bl, bl
0x180042518  jz      loc_180042687
0x18004251e  mov     bl, r13b
0x180042521  xor     bl, 1
0x180042524  test    r13b, r13b
0x180042527  jz      loc_18004263B
0x18004252d  lea     rax, [rbp+60h+DataBlob]
0x180042531  mov     qword ptr [rsp+160h+_a2], rax; DataBlob
0x180042536  mov     r9d, 107h; OpCode
0x18004253c  mov     r8, rsi; strProfileName
0x18004253f  lea     NewProfiles, [rbp+60h+interfaceGuid]; pInterface
0x180042543  lea     this, [rbp+60h+wcm]; this
0x180042547  call    ?WcmQueryParameterBlob@Wcmutil@@QEBAKPEBU_GUID@@PEBGW4_WCM_OPCODE@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Wcmutil::WcmQueryParameterBlob(_GUID const *,ushort const *,_WCM_OPCODE,std::vector<uchar> &)
0x18004254c  test    eax, eax
0x18004254e  jz      short loc_180042594
0x180042550  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180042557  cmp     this, rdi
0x18004255a  jz      loc_180042687
0x180042560  test    byte ptr [this+1Ch], 10h
0x180042564  jz      loc_180042687
0x18004256a  mov     edx, 36h ; '6'; id
0x18004256f  mov     [rsp+160h+_a3], eax; _a3
0x180042573  lea     rax, [rbp+60h+interfaceGuid]
0x180042577  mov     qword ptr [rsp+160h+_a2], rax; _a2
0x18004257c  mov     r9, rsi; _a1
0x18004257f  lea     r8, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180042586  mov     this, [this+10h]; Logger
0x18004258a  call    WPP_SF_S_guid_D
0x18004258f  jmp     loc_180042687
0x180042594  lea     this, [rbp+60h+carrierId]; this
0x180042598  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004259d  nop
0x18004259e  lea     this, [rbp+60h+subscriberId]; this
0x1800425a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800425a7  nop
0x1800425a8  lea     rax, [rbp+60h+DataBlob]
0x1800425ac  mov     [rsp+160h+f.DataBlob], rax
0x1800425b1  lea     rax, [rbp+60h+carrierId]
0x1800425b5  mov     [rsp+160h+f.carrierId], rax
0x1800425ba  lea     rax, [rbp+60h+subscriberId]
0x1800425be  mov     [rsp+160h+f.subscriberId], rax
0x1800425c3  lea     this, [rsp+160h+f]; f
0x1800425c8  call    ExecuteAndConvertAnyException__WwanHandler__DeleteProfiles____28____lambda_1___
0x1800425cd  lea     this, [r15+8]; this
0x1800425d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800425d6  mov     r8, rax
0x1800425d9  lea     this, [rbp+60h+carrierId]; this
0x1800425dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800425e2  mov     this, rax; _Left
0x1800425e5  mov     r9, [r15+18h]; _Right_size
0x1800425e9  mov     NewProfiles, [rbp+60h+carrierId._Mypair._Myval2._Mysize]; _Left_size
0x1800425ed  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800425f2  test    al, al
0x1800425f4  jz      short loc_180042628
0x1800425f6  lea     this, [r15+28h]; this
0x1800425fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800425ff  mov     r8, rax
0x180042602  lea     this, [rbp+60h+subscriberId]; this
0x180042606  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004260b  mov     this, rax; _Left
0x18004260e  mov     r9, [r15+38h]; _Right_size
0x180042612  mov     NewProfiles, [rbp+60h+subscriberId._Mypair._Myval2._Mysize]; _Left_size
0x180042616  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004261b  movzx   ebx, bl
0x18004261e  test    al, al
0x180042620  mov     eax, 1
0x180042625  cmovnz  ebx, eax
0x180042628  lea     this, [rbp+60h+subscriberId]; this
0x18004262c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042631  nop
0x180042632  lea     this, [rbp+60h+carrierId]; this
0x180042636  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004263b  test    bl, bl
0x18004263d  jz      short loc_180042687
0x18004263f  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180042646  cmp     this, rdi
0x180042649  jz      short loc_180042672
0x18004264b  test    byte ptr [this+1Ch], 8
0x18004264f  jz      short loc_180042672
0x180042651  mov     edx, 37h ; '7'; id
0x180042656  lea     rax, [rbp+60h+interfaceGuid]
0x18004265a  mov     qword ptr [rsp+160h+_a2], rax; _a2
0x18004265f  mov     r9, rsi; _a1
0x180042662  lea     r8, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180042669  mov     this, [this+10h]; Logger
0x18004266d  call    WPP_SF_S_guid_
0x180042672  xor     r9d, r9d
0x180042675  mov     r8, rsi
0x180042678  lea     NewProfiles, [rbp+60h+interfaceGuid]
0x18004267c  mov     this, [rbp+60h+wwan.m_handle]
0x180042680  call    cs:__imp_WwanDeleteProfile
0x180042686  nop
0x180042687  lea     this, [rsp+160h+j]; j
0x18004268c  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180042691  nop
0x180042692  lea     this, [rbp+60h+DataBlob]; this
0x180042696  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004269b  inc     r14d
0x18004269e  mov     NewProfiles, [rbp+60h+pProfileList]
0x1800426a2  cmp     r14d, [NewProfiles]
0x1800426a5  mov     ebx, 0
0x1800426aa  jb      loc_1800423CF
0x1800426b0  lea     this, [rsp+160h+var_F0]; j
0x1800426b5  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x1800426ba  nop
0x1800426bb  xor     edx, edx
0x1800426bd  mov     this, [rbp+60h+wcm.m_hWcm]
0x1800426c1  call    cs:__imp_WcmCloseHandle
0x1800426c7  nop
0x1800426c8  xor     edx, edx
0x1800426ca  mov     this, [rbp+60h+wwan.m_handle]
0x1800426ce  call    cs:__imp_WwanCloseHandle
0x1800426d4  mov     this, [rbp+60h+var_40]
0x1800426d8  xor     this, rsp; StackCookie
0x1800426db  call    __security_check_cookie
0x1800426e0  mov     rbx, [rsp+160h+arg_10]
0x1800426e8  add     rsp, 130h
0x1800426ef  pop     r15
0x1800426f1  pop     r14
0x1800426f3  pop     r13
0x1800426f5  pop     r12
0x1800426f7  pop     rdi
0x1800426f8  pop     rsi
0x1800426f9  pop     rbp
0x1800426fa  retn
```

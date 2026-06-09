# ApnHandler::DeleteProfiles(std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18001c928`
- end: `0x18001ce8f`
- name: `?DeleteProfiles@ApnHandler@@AEAAXAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1383`
- prototype: `void __fastcall(ApnHandler *this, const std::set<std::wstring> *ProfilesNotMarkedForRecreation)`
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ce98`
- `0x18001f260`

## callees

- `0x180002790`
- `0x18000a42c`
- `0x18000af94`
- `0x18000b0a0`
- `0x18000b178`
- `0x180011844`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x18001282c`
- `0x180012bc8`
- `0x18001a0d4`
- `0x18001aa2c`
- `0x18001c928`
- `0x180020a14`
- `0x180020bcc`
- `0x180020c48`
- `0x180020cd8`
- `0x180020e70`
- `0x18002108c`
- `0x1800211e0`
- `0x18003fc60`
- `0x180040658`
- `0x1800406f0`
- `0x180044fec`
- `0x180045580`
- `0x180045a2c`
- `0x180045d80`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x18001cb43`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x18001cb43`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x18001cdf7`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x18001cdf7`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x18001cc3e`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfile` at `0x18001cc3e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18001ce62`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18001ce62`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001cb89`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001cc90`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmCloseHandle` at `0x18001ce55`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmCloseHandle` at `0x18001ce55`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall ApnHandler::DeleteProfiles(ApnHandler *this, std::set<std::wstring> *ProfilesNotMarkedForRecreation)
{
  std::set<std::wstring> *v2; // rbx
  int WwanInterface; // eax
  const wchar_t *v5; // rax
  int v6; // eax
  WPP_PROJECT_CONTROL_BLOCK *v7; // rcx
  const wchar_t *v8; // rax
  int v9; // eax
  int ProfileList; // eax
  WWAN_PROFILE_INFO_LIST *v11; // rdx
  unsigned int i; // r15d
  const wchar_t *strProfileName; // r14
  bool v14; // bl
  signed int Profile; // eax
  bool IsAdditionalPdpContextProfile; // bl
  unsigned int _a3; // eax
  const wchar_t *v18; // rax
  const wchar_t *v19; // r8
  const wchar_t *v20; // rax
  const wchar_t *v21; // r8
  AutoRevertImpersonate revertImpersonate; // [rsp+40h] [rbp-C0h] BYREF
  std::wstring _Keyval; // [rsp+48h] [rbp-B8h] BYREF
  const std::set<std::wstring> *v24; // [rsp+68h] [rbp-98h]
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+70h] [rbp-90h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> v26; // [rsp+88h] [rbp-78h] BYREF
  std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring > > > result; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *pProfileXml; // [rsp+A8h] [rbp-58h] BYREF
  WWAN_PROFILE_INFO_LIST *pProfileList; // [rsp+B0h] [rbp-50h] BYREF
  Wwan wwan; // [rsp+B8h] [rbp-48h] BYREF
  Wcmutil wcm; // [rsp+C0h] [rbp-40h] BYREF
  _GUID interfaceGuid; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int pFlags; // [rsp+D8h] [rbp-28h] BYREF
  std::vector<unsigned char> DataBlob; // [rsp+E0h] [rbp-20h] BYREF
  std::wstring defaultProfileName; // [rsp+F8h] [rbp-8h] BYREF
  std::wstring subscriberId; // [rsp+118h] [rbp+18h] BYREF
  std::wstring carrierId; // [rsp+138h] [rbp+38h] BYREF

  v2 = ProfilesNotMarkedForRecreation;
  v24 = ProfilesNotMarkedForRecreation;
  interfaceGuid = 0;
  wwan.m_handle = 0;
  Wwan::Wwan(&wwan);
  WwanInterface = Wwan::FindWwanInterface(&wwan, &this->m_params.SubscriberId, &this->m_params.DeviceId, &interfaceGuid);
  if ( WwanInterface < 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->Control.Logger,
        0x2Eu,
        WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
        WwanInterface);
    }
    goto LABEL_54;
  }
  wcm.m_hWcm = 0;
  Wcmutil::Wcmutil(&wcm);
  std::wstring::wstring(&defaultProfileName);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x2Fu, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids);
  }
  if ( Wwan::GetProvisionedDefaultProfile(
         &wwan,
         &interfaceGuid,
         &this->m_params.CarrierId,
         &this->m_params.SubscriberId,
         &defaultProfileName) >= 0 )
  {
    AutoRevertImpersonate::AutoRevertImpersonate(&revertImpersonate);
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x30u, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids);
    }
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&defaultProfileName._Mypair._Myval2);
    v6 = Wcmutil::WcmDeleteParameter(&wcm, &interfaceGuid, v5, wcm_intf_opcode_multiple_pdp_support);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
LABEL_20:
        v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&defaultProfileName._Mypair._Myval2);
        v9 = Wcmutil::WcmDeleteParameter(&wcm, &interfaceGuid, v8, wcm_intf_opcode_tethering_information);
        if ( v9
          && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x33u, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, v9);
        }
        AutoRevertImpersonate::~AutoRevertImpersonate(&revertImpersonate);
        VerifyUserIsImpersonating();
        goto LABEL_25;
      }
      if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 4) == 0 )
      {
LABEL_17:
        if ( v7 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v7->ReserveSpace[28] & 0x10) != 0 )
          WPP_SF_(v7->Control.Logger, 0x32u, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids);
        goto LABEL_20;
      }
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x31u, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, v6);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_17;
  }
LABEL_25:
  pProfileList = 0;
  ProfileList = WwanGetProfileList(wwan.m_handle, &interfaceGuid, 0, &pProfileList);
  if ( ProfileList )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
    {
      WPP_SF__guid_D(
        WPP_GLOBAL_Control->Control.Logger,
        0x34u,
        WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
        &interfaceGuid,
        ProfileList);
    }
  }
  else
  {
    v11 = pProfileList;
    v26.dismissed_ = 0;
    v26.fun_ = (void (__fastcall *)(void *))WwanFreeMemory;
    v26.p1_ = (WWAN_INTERFACE_OBJECT *const)pProfileList;
    for ( i = 0; i < pProfileList->dwNumberOfItems; v2 = (std::set<std::wstring> *)v24 )
    {
      strProfileName = v11->pProfileInfo[i].strProfileName;
      memset(&DataBlob, 0, sizeof(DataBlob));
      std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&DataBlob);
      if ( !v2->_Mypair._Myval2._Myval2._Mysize
        || (std::wstring::wstring(&_Keyval, strProfileName),
            v14 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                    v2,
                    &result,
                    &_Keyval)->_Ptr != v2->_Mypair._Myval2._Myval2._Myhead,
            std::wstring::_Tidy_deallocate(&_Keyval),
            !v14) )
      {
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
              WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
              pProfileXml,
              Profile);
          }
        }
        else
        {
          j.dismissed_ = 0;
          j.fun_ = (void (__fastcall *)(void *))WwanFreeMemory;
          j.p1_ = (WWAN_INTERFACE_OBJECT *const)pProfileXml;
          std::wstring::wstring(&_Keyval, pProfileXml);
          IsAdditionalPdpContextProfile = Wwan::IsAdditionalPdpContextProfile(&_Keyval);
          std::wstring::_Tidy_deallocate(&_Keyval);
          if ( IsAdditionalPdpContextProfile )
          {
            _a3 = Wcmutil::WcmQueryParameterBlob(
                    &wcm,
                    &interfaceGuid,
                    strProfileName,
                    wcm_intf_opcode_provisioning,
                    &DataBlob);
            if ( _a3 )
            {
              if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
              {
                WPP_SF_S_guid_D(
                  WPP_GLOBAL_Control->Control.Logger,
                  0x36u,
                  WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
                  strProfileName,
                  &interfaceGuid,
                  _a3);
              }
            }
            else
            {
              std::wstring::wstring(&carrierId);
              std::wstring::wstring(&subscriberId);
              _Keyval._Mypair._Myval2._Bx._Ptr = (wchar_t *)&DataBlob;
              *(_QWORD *)&_Keyval._Mypair._Myval2._Bx._Alias[8] = &carrierId;
              _Keyval._Mypair._Myval2._Mysize = (unsigned __int64)&subscriberId;
              ExecuteAndConvertAnyException__WwanHandler::DeleteProfiles_::_28_::_lambda_1___((const WwanHandler::DeleteProfiles::__l28::<lambda_1> *)&_Keyval);
              std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_params.CarrierId._Mypair._Myval2);
              v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&carrierId._Mypair._Myval2);
              if ( std::_Traits_equal<std::char_traits<unsigned short>>(
                     v18,
                     carrierId._Mypair._Myval2._Mysize,
                     v19,
                     this->m_params.CarrierId._Mypair._Myval2._Mysize) )
              {
                std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_params.SubscriberId._Mypair._Myval2);
                v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&subscriberId._Mypair._Myval2);
                if ( std::_Traits_equal<std::char_traits<unsigned short>>(
                       v20,
                       subscriberId._Mypair._Myval2._Mysize,
                       v21,
                       this->m_params.SubscriberId._Mypair._Myval2._Mysize) )
                {
                  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                    && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
                  {
                    WPP_SF_S_guid_(
                      WPP_GLOBAL_Control->Control.Logger,
                      0x37u,
                      WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
                      strProfileName,
                      &interfaceGuid);
                  }
                  WwanDeleteProfile(wwan.m_handle, &interfaceGuid, strProfileName, 0);
                }
              }
              std::wstring::_Tidy_deallocate(&subscriberId);
              std::wstring::_Tidy_deallocate(&carrierId);
            }
          }
          ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
        }
      }
      std::vector<unsigned char>::_Tidy((std::vector<char> *)&DataBlob);
      ++i;
      v11 = pProfileList;
    }
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&v26);
  }
  std::wstring::_Tidy_deallocate(&defaultProfileName);
  WcmCloseHandle(wcm.m_hWcm, 0);
LABEL_54:
  WwanCloseHandle(wwan.m_handle, 0);
}

```

## disassembly

```asm
0x18001c928  mov     [rsp-8+arg_10], rbx
0x18001c92d  push    rbp
0x18001c92e  push    rsi
0x18001c92f  push    rdi
0x18001c930  push    r12
0x18001c932  push    r13
0x18001c934  push    r14
0x18001c936  push    r15
0x18001c938  lea     rbp, [rsp-60h]
0x18001c93d  sub     rsp, 160h
0x18001c944  mov     rax, cs:__security_cookie
0x18001c94b  xor     rax, rsp
0x18001c94e  mov     [rbp+90h+var_38], rax
0x18001c952  mov     rbx, ProfilesNotMarkedForRecreation
0x18001c955  mov     [rsp+190h+var_128], ProfilesNotMarkedForRecreation
0x18001c95a  mov     r13, this
0x18001c95d  xorps   xmm0, xmm0
0x18001c960  movups  xmmword ptr [rbp+90h+interfaceGuid.Data1], xmm0
0x18001c964  xor     r14d, r14d
0x18001c967  mov     [rbp+90h+wwan.m_handle], r14
0x18001c96b  lea     this, [rbp+90h+wwan]; this
0x18001c96f  call    ??0Wwan@@QEAA@XZ; Wwan::Wwan(void)
0x18001c974  nop
0x18001c975  lea     r12, [r13+28h]
0x18001c979  lea     r8, [r13+48h]; DeviceId
0x18001c97d  lea     r9, [rbp+90h+interfaceGuid]; InterfaceGuid
0x18001c981  mov     ProfilesNotMarkedForRecreation, r12; SubscriberId
0x18001c984  lea     this, [rbp+90h+wwan]; this
0x18001c988  call    ?FindWwanInterface@Wwan@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU_GUID@@@Z; Wwan::FindWwanInterface(std::wstring const &,std::wstring const &,_GUID &)
0x18001c98d  test    eax, eax
0x18001c98f  jns     short loc_18001C9CE
0x18001c991  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18001c998  mov     this, cs:WPP_GLOBAL_Control
0x18001c99f  cmp     this, rdi
0x18001c9a2  jz      loc_18001CE5C
0x18001c9a8  test    byte ptr [this+1Ch], 4
0x18001c9ac  jz      loc_18001CE5C
0x18001c9b2  lea     edx, [r14+2Eh]; id
0x18001c9b6  mov     r9d, eax; _a1
0x18001c9b9  lea     r8, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001c9c0  mov     this, [this+10h]; Logger
0x18001c9c4  call    WPP_SF_d
0x18001c9c9  jmp     loc_18001CE5C
0x18001c9ce  mov     [rbp+90h+wcm.m_hWcm], r14
0x18001c9d2  lea     this, [rbp+90h+wcm]; this
0x18001c9d6  call    ??0Wcmutil@@QEAA@XZ; Wcmutil::Wcmutil(void)
0x18001c9db  nop
0x18001c9dc  lea     this, [rbp+90h+defaultProfileName]; this
0x18001c9e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001c9e5  nop
0x18001c9e6  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18001c9ed  lea     rsi, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids
0x18001c9f4  mov     r15b, 10h
0x18001c9f7  mov     this, cs:WPP_GLOBAL_Control
0x18001c9fe  cmp     this, rdi
0x18001ca01  jz      short loc_18001CA1A
0x18001ca03  test    [this+1Ch], r15b
0x18001ca07  jz      short loc_18001CA1A
0x18001ca09  mov     edx, 2Fh ; '/'; id
0x18001ca0e  mov     r8, rsi; TraceGuid
0x18001ca11  mov     this, [this+10h]; Logger
0x18001ca15  call    WPP_SF_
0x18001ca1a  lea     r8, [r13+8]; CarrierId
0x18001ca1e  lea     this, [rbp+90h+defaultProfileName]
0x18001ca22  mov     [rsp+190h+ProvisionedDefaultProfileName], this; ProvisionedDefaultProfileName
0x18001ca27  mov     r9, r12; SubscriberId
0x18001ca2a  lea     ProfilesNotMarkedForRecreation, [rbp+90h+interfaceGuid]; InterfaceGuid
0x18001ca2e  lea     this, [rbp+90h+wwan]; this
0x18001ca32  call    ?GetProvisionedDefaultProfile@Wwan@@QEAAJAEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEAV34@@Z; Wwan::GetProvisionedDefaultProfile(_GUID const &,std::wstring const &,std::wstring const &,std::wstring &)
0x18001ca37  test    eax, eax
0x18001ca39  js      loc_18001CB30
0x18001ca3f  lea     this, [rsp+190h+revertImpersonate]; this
0x18001ca44  call    ??0AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::AutoRevertImpersonate(void)
0x18001ca49  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001ca50  cmp     this, rdi
0x18001ca53  jz      short loc_18001CA6C
0x18001ca55  test    [this+1Ch], r15b
0x18001ca59  jz      short loc_18001CA6C
0x18001ca5b  mov     edx, 30h ; '0'; id
0x18001ca60  mov     r8, rsi; TraceGuid
0x18001ca63  mov     this, [this+10h]; Logger
0x18001ca67  call    WPP_SF_
0x18001ca6c  lea     this, [rbp+90h+defaultProfileName]; this
0x18001ca70  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ca75  mov     r8, rax; strProfileName
0x18001ca78  mov     r9d, 110h; OpCode
0x18001ca7e  lea     ProfilesNotMarkedForRecreation, [rbp+90h+interfaceGuid]; pInterface
0x18001ca82  lea     this, [rbp+90h+wcm]; this
0x18001ca86  call    ?WcmDeleteParameter@Wcmutil@@QEBAKPEBU_GUID@@PEBGW4_WCM_OPCODE@@@Z; Wcmutil::WcmDeleteParameter(_GUID const *,ushort const *,_WCM_OPCODE)
0x18001ca8b  test    eax, eax
0x18001ca8d  jz      short loc_18001CAB5
0x18001ca8f  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001ca96  cmp     this, rdi
0x18001ca99  jz      short loc_18001CAD8
0x18001ca9b  test    byte ptr [this+1Ch], 4
0x18001ca9f  jz      short loc_18001CABC
0x18001caa1  mov     edx, 31h ; '1'; id
0x18001caa6  mov     r9d, eax; _a1
0x18001caa9  mov     r8, rsi; TraceGuid
0x18001caac  mov     this, [this+10h]; Logger
0x18001cab0  call    WPP_SF_d
0x18001cab5  mov     this, cs:WPP_GLOBAL_Control
0x18001cabc  cmp     this, rdi; __annotation("TMF:",
0x18001cabf  jz      short loc_18001CAD8
0x18001cac1  test    [this+1Ch], r15b
0x18001cac5  jz      short loc_18001CAD8
0x18001cac7  mov     edx, 32h ; '2'; id
0x18001cacc  mov     r8, rsi; TraceGuid
0x18001cacf  mov     this, [this+10h]; Logger
0x18001cad3  call    WPP_SF_
0x18001cad8  lea     this, [rbp+90h+defaultProfileName]; this
0x18001cadc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cae1  mov     r8, rax; strProfileName
0x18001cae4  mov     r9d, 118h; OpCode
0x18001caea  lea     ProfilesNotMarkedForRecreation, [rbp+90h+interfaceGuid]; pInterface
0x18001caee  lea     this, [rbp+90h+wcm]; this
0x18001caf2  call    ?WcmDeleteParameter@Wcmutil@@QEBAKPEBU_GUID@@PEBGW4_WCM_OPCODE@@@Z; Wcmutil::WcmDeleteParameter(_GUID const *,ushort const *,_WCM_OPCODE)
0x18001caf7  test    eax, eax
0x18001caf9  jz      short loc_18001CB21
0x18001cafb  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001cb02  cmp     this, rdi
0x18001cb05  jz      short loc_18001CB21
0x18001cb07  test    byte ptr [this+1Ch], 4
0x18001cb0b  jz      short loc_18001CB21
0x18001cb0d  mov     edx, 33h ; '3'; id
0x18001cb12  mov     r9d, eax; _a1
0x18001cb15  mov     r8, rsi; TraceGuid
0x18001cb18  mov     this, [this+10h]; Logger
0x18001cb1c  call    WPP_SF_d
0x18001cb21  lea     this, [rsp+190h+revertImpersonate]; this
0x18001cb26  call    ??1AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::~AutoRevertImpersonate(void)
0x18001cb2b  call    ?VerifyUserIsImpersonating@@YAXXZ; VerifyUserIsImpersonating(void)
0x18001cb30  mov     [rbp+90h+pProfileList], r14
0x18001cb34  lea     r9, [rbp+90h+pProfileList]
0x18001cb38  xor     r8d, r8d
0x18001cb3b  lea     ProfilesNotMarkedForRecreation, [rbp+90h+interfaceGuid]
0x18001cb3f  mov     this, [rbp+90h+wwan.m_handle]
0x18001cb43  call    cs:__imp_WwanGetProfileList
0x18001cb49  test    eax, eax
0x18001cb4b  jz      short loc_18001CB85
0x18001cb4d  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001cb54  cmp     this, rdi
0x18001cb57  jz      loc_18001CE45
0x18001cb5d  test    byte ptr [this+1Ch], 8
0x18001cb61  jz      loc_18001CE45
0x18001cb67  mov     edx, 34h ; '4'; id
0x18001cb6c  mov     dword ptr [rsp+190h+ProvisionedDefaultProfileName], eax; _a2
0x18001cb70  lea     r9, [rbp+90h+interfaceGuid]; _a1
0x18001cb74  mov     r8, rsi; TraceGuid
0x18001cb77  mov     this, [this+10h]; Logger
0x18001cb7b  call    WPP_SF__guid_D
0x18001cb80  jmp     loc_18001CE45
0x18001cb85  mov     ProfilesNotMarkedForRecreation, [rbp+90h+pProfileList]
0x18001cb89  mov     rax, cs:__imp_WwanFreeMemory
0x18001cb90  mov     [rbp+90h+var_108.dismissed_], r14b
0x18001cb94  mov     [rbp+90h+var_108.fun_], rax
0x18001cb98  mov     [rbp+90h+var_108.p1_], ProfilesNotMarkedForRecreation
0x18001cb9c  mov     r15d, r14d
0x18001cb9f  cmp     [ProfilesNotMarkedForRecreation], r14d
0x18001cba2  jbe     loc_18001CE3B
0x18001cba8  mov     eax, r15d
0x18001cbab  imul    r14, rax, 204h
0x18001cbb2  add     r14, 4
0x18001cbb6  add     r14, ProfilesNotMarkedForRecreation
0x18001cbb9  xorps   xmm0, xmm0
0x18001cbbc  xor     eax, eax
0x18001cbbe  movups  xmmword ptr [rbp+90h+DataBlob._Mypair._Myval2._Myfirst], xmm0
0x18001cbc2  mov     [rbp+90h+DataBlob._Mypair._Myval2._Myend], rax
0x18001cbc6  lea     this, [rbp+90h+DataBlob]; this
0x18001cbca  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18001cbcf  nop
0x18001cbd0  cmp     qword ptr [rbx+8], 0
0x18001cbd5  jz      short loc_18001CC10
0x18001cbd7  mov     ProfilesNotMarkedForRecreation, r14; _Ptr
0x18001cbda  lea     this, [rsp+190h+_Keyval]; this
0x18001cbdf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001cbe4  lea     r8, [rsp+190h+_Keyval]; _Keyval
0x18001cbe9  lea     ProfilesNotMarkedForRecreation, [rbp+90h+result]; result
0x18001cbed  mov     this, rbx; this
0x18001cbf0  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x18001cbf5  mov     this, [rbx]
0x18001cbf8  cmp     [rax], this
0x18001cbfb  setnz   bl
0x18001cbfe  lea     this, [rsp+190h+_Keyval]; this
0x18001cc03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cc08  test    bl, bl
0x18001cc0a  jnz     loc_18001CE1D
0x18001cc10  xor     ebx, ebx
0x18001cc12  mov     [rbp+90h+pProfileXml], rbx
0x18001cc16  mov     [rbp+90h+pFlags], ebx
0x18001cc19  mov     [rsp+190h+var_160], rbx
0x18001cc1e  lea     rax, [rbp+90h+pFlags]
0x18001cc22  mov     qword ptr [rsp+190h+_a3], rax
0x18001cc27  lea     rax, [rbp+90h+pProfileXml]
0x18001cc2b  mov     [rsp+190h+ProvisionedDefaultProfileName], rax
0x18001cc30  xor     r9d, r9d
0x18001cc33  mov     r8, r14
0x18001cc36  lea     ProfilesNotMarkedForRecreation, [rbp+90h+interfaceGuid]
0x18001cc3a  mov     this, [rbp+90h+wwan.m_handle]
0x18001cc3e  call    cs:__imp_WwanGetProfile
0x18001cc44  test    eax, eax
0x18001cc46  jz      short loc_18001CC8C
0x18001cc48  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001cc4f  cmp     this, rdi
0x18001cc52  jz      loc_18001CE1D
0x18001cc58  test    byte ptr [this+1Ch], 4
0x18001cc5c  jz      loc_18001CE1D
0x18001cc62  test    eax, eax
0x18001cc64  jle     short loc_18001CC6E
0x18001cc66  movzx   eax, ax
0x18001cc69  or      eax, 80070000h
0x18001cc6e  mov     edx, 35h ; '5'; id
0x18001cc73  mov     dword ptr [rsp+190h+ProvisionedDefaultProfileName], eax; _a2
0x18001cc77  mov     r9, [rbp+90h+pProfileXml]; _a1
0x18001cc7b  mov     r8, rsi; TraceGuid
0x18001cc7e  mov     this, [this+10h]; Logger
0x18001cc82  call    WPP_SF_Sd
0x18001cc87  jmp     loc_18001CE1D
0x18001cc8c  mov     ProfilesNotMarkedForRecreation, [rbp+90h+pProfileXml]; _Ptr
0x18001cc90  mov     rax, cs:__imp_WwanFreeMemory
0x18001cc97  mov     [rsp+190h+j.dismissed_], bl
0x18001cc9b  mov     [rsp+190h+j.fun_], rax
0x18001cca0  mov     [rbp+90h+j.p1_], ProfilesNotMarkedForRecreation
0x18001cca4  lea     this, [rsp+190h+_Keyval]; this
0x18001cca9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ccae  nop
0x18001ccaf  lea     this, [rsp+190h+_Keyval]; ProfileXml
0x18001ccb4  call    ?IsAdditionalPdpContextProfile@Wwan@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Wwan::IsAdditionalPdpContextProfile(std::wstring const &)
0x18001ccb9  mov     bl, al
0x18001ccbb  lea     this, [rsp+190h+_Keyval]; this
0x18001ccc0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ccc5  test    bl, bl
0x18001ccc7  jz      loc_18001CE12
0x18001cccd  lea     rax, [rbp+90h+DataBlob]
0x18001ccd1  mov     [rsp+190h+ProvisionedDefaultProfileName], rax; DataBlob
0x18001ccd6  mov     r9d, 107h; OpCode
0x18001ccdc  mov     r8, r14; strProfileName
0x18001ccdf  lea     ProfilesNotMarkedForRecreation, [rbp+90h+interfaceGuid]; pInterface
0x18001cce3  lea     this, [rbp+90h+wcm]; this
0x18001cce7  call    ?WcmQueryParameterBlob@Wcmutil@@QEBAKPEBU_GUID@@PEBGW4_WCM_OPCODE@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Wcmutil::WcmQueryParameterBlob(_GUID const *,ushort const *,_WCM_OPCODE,std::vector<uchar> &)
0x18001ccec  test    eax, eax
0x18001ccee  jz      short loc_18001CD30
0x18001ccf0  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001ccf7  cmp     this, rdi
0x18001ccfa  jz      loc_18001CE12
0x18001cd00  test    byte ptr [this+1Ch], 10h
0x18001cd04  jz      loc_18001CE12
0x18001cd0a  mov     edx, 36h ; '6'; id
0x18001cd0f  mov     [rsp+190h+_a3], eax; _a3
0x18001cd13  lea     rax, [rbp+90h+interfaceGuid]
0x18001cd17  mov     [rsp+190h+ProvisionedDefaultProfileName], rax; _a2
0x18001cd1c  mov     r9, r14; _a1
0x18001cd1f  mov     r8, rsi; TraceGuid
0x18001cd22  mov     this, [this+10h]; Logger
0x18001cd26  call    WPP_SF_S_guid_D
0x18001cd2b  jmp     loc_18001CE12
0x18001cd30  lea     this, [rbp+90h+carrierId]; this
0x18001cd34  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001cd39  nop
0x18001cd3a  lea     this, [rbp+90h+subscriberId]; this
0x18001cd3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001cd43  nop
0x18001cd44  lea     rax, [rbp+90h+DataBlob]
0x18001cd48  mov     qword ptr [rsp+190h+_Keyval._Mypair._Myval2._Bx], rax
0x18001cd4d  lea     rax, [rbp+90h+carrierId]
0x18001cd51  mov     qword ptr [rsp+190h+_Keyval._Mypair._Myval2._Bx+8], rax
0x18001cd56  lea     rax, [rbp+90h+subscriberId]
0x18001cd5a  mov     [rsp+190h+_Keyval._Mypair._Myval2._Mysize], rax
0x18001cd5f  lea     this, [rsp+190h+_Keyval]; f
0x18001cd64  call    ExecuteAndConvertAnyException__WwanHandler__DeleteProfiles____28____lambda_1___
0x18001cd69  lea     this, [r13+8]; this
0x18001cd6d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cd72  mov     r8, rax
0x18001cd75  lea     this, [rbp+90h+carrierId]; this
0x18001cd79  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cd7e  mov     this, rax; _Left
0x18001cd81  mov     r9, [r13+18h]; _Right_size
0x18001cd85  mov     ProfilesNotMarkedForRecreation, [rbp+90h+carrierId._Mypair._Myval2._Mysize]; _Left_size
0x18001cd89  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001cd8e  test    al, al
0x18001cd90  jz      short loc_18001CDFE
0x18001cd92  mov     this, r12; this
0x18001cd95  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cd9a  mov     r8, rax
0x18001cd9d  lea     this, [rbp+90h+subscriberId]; this
0x18001cda1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cda6  mov     this, rax; _Left
0x18001cda9  mov     r9, [r13+38h]; _Right_size
0x18001cdad  mov     ProfilesNotMarkedForRecreation, [rbp+90h+subscriberId._Mypair._Myval2._Mysize]; _Left_size
0x18001cdb1  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001cdb6  test    al, al
0x18001cdb8  jz      short loc_18001CDFE
0x18001cdba  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001cdc1  cmp     this, rdi
0x18001cdc4  jz      short loc_18001CDE9
0x18001cdc6  test    byte ptr [this+1Ch], 8
0x18001cdca  jz      short loc_18001CDE9
0x18001cdcc  mov     edx, 37h ; '7'; id
0x18001cdd1  lea     rax, [rbp+90h+interfaceGuid]
0x18001cdd5  mov     [rsp+190h+ProvisionedDefaultProfileName], rax; _a2
  ... truncated ...
```

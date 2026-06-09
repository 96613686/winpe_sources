# ApnHandler::ProvisionAdditionalApnProfiles(std::vector<std::shared_ptr<WcmCommon::Xml::Node>,std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>> const &,void *,_GUID const &,std::unique_ptr<Wcmutil,std::default_delete<Wcmutil>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e71c`
- end: `0x18001edd2`
- name: `?ProvisionAdditionalApnProfiles@ApnHandler@@AEAA_NAEBV?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@PEAXAEBU_GUID@@AEBV?$unique_ptr@VWcmutil@@U?$default_delete@VWcmutil@@@std@@@3@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `1718`
- prototype: `bool __fastcall(ApnHandler *this, const std::vector<std::shared_ptr<WcmCommon::Xml::Node>> *ProfileNodes, void *hWwan, const _GUID *InterfaceGuid, const std::unique_ptr<Wcmutil> *Wcm, std::wstring *ApnResultXml)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001df00`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x18000af94`
- `0x18000b0a0`
- `0x18000b8c0`
- `0x18000b8fc`
- `0x18000fa6c`
- `0x180011844`
- `0x180011cfc`
- `0x180011fdc`
- `0x180012770`
- `0x1800127cc`
- `0x18001a0d4`
- `0x18001c07c`
- `0x18001c340`
- `0x18001c61c`
- `0x18001d304`
- `0x18001d608`
- `0x18001d664`
- `0x18001e71c`
- `0x18001f2e4`
- `0x180020a6c`
- `0x180020bcc`
- `0x180020c48`
- `0x180020e70`
- `0x18002108c`
- `0x1800211e0`
- `0x18003fe90`
- `0x180040800`
- `0x1800408c0`
- `0x180048194`
- `0x180048f28`
- `0x180048f78`
- `0x180049d70`
- `0x180049ed0`
- `0x180057790`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x18001eb0d`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x18001eb0d`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetProfile` at `0x18001e94d`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetProfile` at `0x18001e94d`

## string_xrefs

- `0x18001e83a`: `http://www.microsoft.com/networking/WWAN/profile/v1`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
bool __fastcall ApnHandler::ProvisionAdditionalApnProfiles(
        ApnHandler *this,
        const std::vector<std::shared_ptr<WcmCommon::Xml::Node>> *ProfileNodes,
        void *hWwan,
        const _GUID *InterfaceGuid,
        const std::unique_ptr<Wcmutil> *Wcm,
        std::wstring *ApnResultXml)
{
  void *v7; // rdi
  _QWORD *v10; // rdx
  char v11; // r15
  std::shared_ptr<WcmCommon::Xml::Node> *Myfirst; // r14
  std::shared_ptr<WcmCommon::Xml::Node> *Mylast; // r12
  WcmCommon::Xml::Node *Ptr; // rbx
  std::shared_ptr<WcmCommon::Xml::Node> *v15; // rax
  WcmCommon::Xml::Node *v16; // rbx
  std::wstring *Xml; // rax
  std::wstring *v18; // rax
  const wchar_t *v19; // rax
  int _a3; // edi
  const wchar_t *v21; // rax
  __int64 v22; // r10
  const std::wstring *v23; // rax
  const wchar_t *v24; // rax
  Wcmutil **v25; // rbx
  int v26; // eax
  const wchar_t *v27; // rax
  WPP_PROJECT_CONTROL_BLOCK *v28; // r10
  const wchar_t *v29; // rax
  __int64 v30; // r10
  const wchar_t *v31; // rax
  __int64 v32; // r10
  const wchar_t *v33; // rax
  const wchar_t *v34; // rax
  int v35; // edx
  _MCGEN_TRACE_CONTEXT *v36; // rcx
  unsigned int v37; // r8d
  WPP_PROJECT_CONTROL_BLOCK *v38; // r10
  const wchar_t *v39; // rax
  __int64 v40; // r10
  const wchar_t *v41; // rax
  __int64 v42; // r10
  std::wstring *v43; // rax
  std::wstring *v44; // rax
  std::wstring *v45; // rbx
  std::wstring *v46; // rax
  std::wstring *v47; // rbx
  std::wstring *v48; // rax
  AutoRevertImpersonate revertImpersonate; // [rsp+50h] [rbp-B0h] BYREF
  void *v51; // [rsp+58h] [rbp-A8h]
  std::wstring *p_Path; // [rsp+60h] [rbp-A0h]
  std::shared_ptr<WcmCommon::Xml::Document> profileDoc; // [rsp+68h] [rbp-98h] BYREF
  std::wstring Path; // [rsp+78h] [rbp-88h] BYREF
  const std::unique_ptr<Wcmutil> *v55; // [rsp+98h] [rbp-68h]
  std::wstring *v56; // [rsp+A0h] [rbp-60h]
  std::wstring *v57; // [rsp+A8h] [rbp-58h]
  std::shared_ptr<WcmCommon::Xml::Node> appIdListNode; // [rsp+B0h] [rbp-50h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> result; // [rsp+D0h] [rbp-30h] BYREF
  std::wstring v60; // [rsp+E0h] [rbp-20h] BYREF
  std::wstring v61; // [rsp+100h] [rbp+0h] BYREF
  WWAN_PROFILE_INVALID_REASON dwReasonCode; // [rsp+120h] [rbp+20h] BYREF
  std::vector<unsigned char> provisioningOpcodeData; // [rsp+128h] [rbp+28h] BYREF
  std::wstring profileName; // [rsp+148h] [rbp+48h] BYREF
  std::wstring appIdListXml; // [rsp+168h] [rbp+68h] BYREF
  std::wstring originalProfileName; // [rsp+188h] [rbp+88h] BYREF
  std::wstring resultXml; // [rsp+1A8h] [rbp+A8h] BYREF
  XmlBuilder::Node results; // [rsp+1D0h] [rbp+D0h] BYREF

  v7 = hWwan;
  v51 = hWwan;
  v55 = Wcm;
  v56 = ApnResultXml;
  std::wstring::wstring(&resultXml);
  v11 = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->Control.Logger,
      0x17u,
      WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
      (__int64)(v10[1] - *v10) >> 4);
  }
  Myfirst = ProfileNodes->_Mypair._Myval2._Myfirst;
  Mylast = ProfileNodes->_Mypair._Myval2._Mylast;
  while ( Myfirst != Mylast )
  {
    std::wstring::wstring(&appIdListXml);
    dwReasonCode = WwanProfileErrNone;
    Ptr = Myfirst->_Ptr;
    std::wstring::wstring((std::wstring *)&provisioningOpcodeData, L"./prov_v2:Name");
    v15 = WcmCommon::Xml::Node::SelectSingle(Ptr, &result, (const std::wstring *)&provisioningOpcodeData);
    WcmCommon::Xml::Node::GetText(v15->_Ptr, &profileName);
    if ( result._Rep )
      std::_Ref_count_base::_Decref(result._Rep);
    std::wstring::_Tidy_deallocate((std::wstring *)&provisioningOpcodeData);
    profileDoc = 0;
    WcmCommon::Xml::Node::TransformIntoDocument(Myfirst->_Ptr, &profileDoc, &this->m_additionalApnXsl);
    std::wstring::wstring((std::wstring *)&appIdListNode, L"http://www.microsoft.com/networking/WWAN/profile/v1");
    std::wstring::wstring((std::wstring *)&provisioningOpcodeData, L"default");
    WcmCommon::Xml::Document::AddSelectionNamespace(
      profileDoc._Ptr,
      (const std::wstring *)&provisioningOpcodeData,
      (const std::wstring *)&appIdListNode);
    std::wstring::_Tidy_deallocate((std::wstring *)&provisioningOpcodeData);
    std::wstring::_Tidy_deallocate((std::wstring *)&appIdListNode);
    InsertNodesInProfileXml(&profileDoc, &this->m_params.SubscriberId, 0);
    appIdListNode = 0;
    v16 = Myfirst->_Ptr;
    std::wstring::wstring(&Path, L"./prov_v2:AppIDList");
    WcmCommon::Xml::Node::SelectSingle(v16, &appIdListNode, &Path);
    std::wstring::_Tidy_deallocate(&Path);
    if ( appIdListNode._Ptr )
    {
      Xml = WcmCommon::Xml::Document::GetXml(appIdListNode._Ptr, &v61);
      std::wstring::operator=(&appIdListXml, Xml);
      std::wstring::_Tidy_deallocate(&v61);
    }
    v18 = WcmCommon::Xml::Document::GetXml(
            (WcmCommon::Xml::Node *)profileDoc._Ptr,
            (std::wstring *)&provisioningOpcodeData);
    v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v18->_Mypair._Myval2);
    _a3 = WwanSetProfile(v7, &GUID_NULL, 0, v19, 0, 1, 0, 0, 0, &dwReasonCode);
    std::wstring::_Tidy_deallocate((std::wstring *)&provisioningOpcodeData);
    if ( _a3 )
    {
      if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x1000) != 0 )
      {
        v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
        McTemplateU0jzdq_EtwEventWriteTransfer(v36, &SetWwanProfileFailed, InterfaceGuid, v34, v35, v37);
      }
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
        {
          v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
          WPP_SF_S_guid_D(
            *(_QWORD *)(v40 + 16),
            0x1Cu,
            WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
            v39,
            InterfaceGuid,
            _a3);
          v38 = WPP_GLOBAL_Control;
        }
        if ( v38 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v38->ReserveSpace[28] & 8) != 0 )
          WPP_SF_d(v38->Control.Logger, 0x1Du, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, dwReasonCode);
      }
LABEL_36:
      v11 = 1;
      goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
      WPP_SF_S_guid_(*(_QWORD *)(v22 + 16), 0x18u, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, v21, InterfaceGuid);
    }
    memset(&provisioningOpcodeData, 0, sizeof(provisioningOpcodeData));
    std::wstring::wstring(&v60);
    Wcmutil::GetCarrierSubscriberPlanBlob(&provisioningOpcodeData, &this->m_params, v23);
    std::wstring::_Tidy_deallocate(&v60);
    AutoRevertImpersonate::AutoRevertImpersonate(&revertImpersonate);
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
    v25 = (Wcmutil **)v55;
    v26 = Wcmutil::WcmSetParameterFromBlob(
            v55->_Mypair._Myval2,
            InterfaceGuid,
            v24,
            wcm_intf_opcode_provisioning,
            &provisioningOpcodeData);
    if ( v26
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, v26);
    }
    if ( appIdListXml._Mypair._Myval2._Mysize )
    {
      v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
      _a3 = Wcmutil::WcmSetParameterFromString(*v25, InterfaceGuid, v27, wcm_intf_opcode_app_allow_list, &appIdListXml);
      if ( _a3 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
          {
            v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
            WPP_SF_S_guid_D(
              *(_QWORD *)(v30 + 16),
              0x1Au,
              WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
              v29,
              InterfaceGuid,
              _a3);
            v28 = WPP_GLOBAL_Control;
          }
          if ( v28 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v28->ReserveSpace[28] & 4) != 0 )
          {
            v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
            WPP_SF_S_guid_(
              *(_QWORD *)(v32 + 16),
              0x1Bu,
              WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
              v31,
              InterfaceGuid);
          }
        }
        v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
        WwanDeleteProfile(v51, InterfaceGuid, v33, 0);
      }
    }
    AutoRevertImpersonate::~AutoRevertImpersonate(&revertImpersonate);
    VerifyUserIsImpersonating();
    std::vector<unsigned char>::_Tidy((std::vector<char> *)&provisioningOpcodeData);
    if ( _a3 )
      goto LABEL_36;
LABEL_37:
    ProfileUtil::GetOriginalProfileName(&originalProfileName, &profileName);
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&originalProfileName._Mypair._Myval2);
      WPP_SF_S(*(_QWORD *)(v42 + 16), 0x1Eu, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, v41);
    }
    memset_0(&results, 0, sizeof(results));
    std::wstring::wstring(&v60, L"PDPContextPolicy");
    XmlBuilder::Node::Node(&results, v43);
    p_Path = &Path;
    std::wstring::wstring(&Path, &originalProfileName);
    v45 = v44;
    std::wstring::wstring((std::wstring *)&provisioningOpcodeData, L"name");
    XmlBuilder::Node::SetAttribute(&results, v46, v45);
    v57 = &Path;
    if ( _a3 > 0 )
      _a3 = (unsigned __int16)_a3 | 0x80070000;
    v47 = XmlBuilder::HrToString(&Path, _a3);
    std::wstring::wstring((std::wstring *)&provisioningOpcodeData, L"errorCode");
    XmlBuilder::Node::SetAttribute(&results, v48, v47);
    XmlBuilder::Node::GenerateXml(&results, &Path, 0);
    std::wstring::append(&resultXml, &Path);
    std::wstring::_Tidy_deallocate(&Path);
    XmlBuilder::Node::~Node(&results);
    std::wstring::_Tidy_deallocate(&originalProfileName);
    if ( appIdListNode._Rep )
      std::_Ref_count_base::_Decref(appIdListNode._Rep);
    if ( profileDoc._Rep )
      std::_Ref_count_base::_Decref(profileDoc._Rep);
    std::wstring::_Tidy_deallocate(&profileName);
    std::wstring::_Tidy_deallocate(&appIdListXml);
    ++Myfirst;
    v7 = v51;
  }
  std::wstring::operator=(v56, &resultXml);
  std::wstring::_Tidy_deallocate(&resultXml);
  return v11 == 0;
}

```

## disassembly

```asm
0x18001e71c  push    rbp
0x18001e71e  push    rbx
0x18001e71f  push    rsi
0x18001e720  push    rdi
0x18001e721  push    r12
0x18001e723  push    r13
0x18001e725  push    r14
0x18001e727  push    r15
0x18001e729  lea     rbp, [rsp-138h]
0x18001e731  sub     rsp, 238h
0x18001e738  mov     rax, cs:__security_cookie
0x18001e73f  xor     rax, rsp
0x18001e742  mov     [rbp+170h+var_50], rax
0x18001e749  mov     rsi, InterfaceGuid
0x18001e74c  mov     rdi, hWwan
0x18001e74f  mov     [rsp+270h+var_218], hWwan
0x18001e754  mov     rbx, ProfileNodes
0x18001e757  mov     r13, this
0x18001e75a  mov     rax, [rbp+170h+arg_20]
0x18001e761  mov     [rbp+170h+var_1D8], rax
0x18001e765  mov     rax, [rbp+170h+arg_28]
0x18001e76c  mov     [rbp+170h+var_1D0], rax
0x18001e770  lea     this, [rbp+170h+resultXml]; this
0x18001e777  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e77c  nop
0x18001e77d  xor     r15b, r15b
0x18001e780  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x18001e787  mov     this, cs:WPP_GLOBAL_Control
0x18001e78e  cmp     this, rax
0x18001e791  jz      short loc_18001E7B9
0x18001e793  test    byte ptr [this+1Ch], 10h
0x18001e797  jz      short loc_18001E7B9
0x18001e799  mov     InterfaceGuid, [ProfileNodes+8]
0x18001e79d  sub     InterfaceGuid, [ProfileNodes]
0x18001e7a0  sar     InterfaceGuid, 4; _a1
0x18001e7a4  mov     edx, 17h; id
0x18001e7a9  lea     hWwan, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001e7b0  mov     this, [this+10h]; Logger
0x18001e7b4  call    WPP_SF_d
0x18001e7b9  mov     r14, [rbx]
0x18001e7bc  mov     r12, [rbx+8]
0x18001e7c0  jmp     loc_18001ED81
0x18001e7c5  lea     this, [rbp+170h+appIdListXml]; this
0x18001e7c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e7ce  nop
0x18001e7cf  mov     [rbp+170h+dwReasonCode], 0
0x18001e7d6  mov     rbx, [r14]
0x18001e7d9  lea     ProfileNodes, aProvV2Name; "./prov_v2:Name"
0x18001e7e0  lea     this, [rbp+170h+provisioningOpcodeData]; this
0x18001e7e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001e7e9  nop
0x18001e7ea  lea     hWwan, [rbp+170h+provisioningOpcodeData]; Path
0x18001e7ee  lea     ProfileNodes, [rbp+170h+result]; result
0x18001e7f2  mov     this, rbx; this
0x18001e7f5  call    ?SelectSingle@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Node::SelectSingle(std::wstring const &)
0x18001e7fa  nop
0x18001e7fb  lea     ProfileNodes, [rbp+170h+profileName]; result
0x18001e7ff  mov     this, [rax]; this
0x18001e802  call    ?GetText@Node@Xml@WcmCommon@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WcmCommon::Xml::Node::GetText(void)
0x18001e807  nop
0x18001e808  mov     this, [rbp+170h+result._Rep]; this
0x18001e80c  test    this, this
0x18001e80f  jz      short loc_18001E817
0x18001e811  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e816  nop
0x18001e817  lea     this, [rbp+170h+provisioningOpcodeData]; this
0x18001e81b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e820  xorps   xmm0, xmm0
0x18001e823  movups  xmmword ptr [rsp+270h+profileDoc._Ptr], xmm0
0x18001e828  lea     hWwan, [r13+68h]; xslDoc
0x18001e82c  lea     ProfileNodes, [rsp+270h+profileDoc]; result
0x18001e831  mov     this, [r14]; this
0x18001e834  call    ?TransformIntoDocument@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV45@@Z; WcmCommon::Xml::Node::TransformIntoDocument(std::shared_ptr<WcmCommon::Xml::Document> const &)
0x18001e839  nop
0x18001e83a  lea     ProfileNodes, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x18001e841  lea     this, [rbp+170h+appIdListNode]; this
0x18001e845  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001e84a  nop
0x18001e84b  lea     ProfileNodes, aDefault; "default"
0x18001e852  lea     this, [rbp+170h+provisioningOpcodeData]; this
0x18001e856  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001e85b  nop
0x18001e85c  lea     hWwan, [rbp+170h+appIdListNode]; ns
0x18001e860  lea     ProfileNodes, [rbp+170h+provisioningOpcodeData]; key
0x18001e864  mov     this, [rsp+270h+profileDoc._Ptr]; this
0x18001e869  call    ?AddSelectionNamespace@Document@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WcmCommon::Xml::Document::AddSelectionNamespace(std::wstring const &,std::wstring const &)
0x18001e86e  nop
0x18001e86f  lea     this, [rbp+170h+provisioningOpcodeData]; this
0x18001e873  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e878  nop
0x18001e879  lea     this, [rbp+170h+appIdListNode]; this
0x18001e87d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e882  xor     r8d, r8d; IsTethering
0x18001e885  lea     ProfileNodes, [r13+28h]; SubscriberId
0x18001e889  lea     this, [rsp+270h+profileDoc]; ProfileDoc
0x18001e88e  call    ?InsertNodesInProfileXml@@YAXAEBV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@Z; InsertNodesInProfileXml(std::shared_ptr<WcmCommon::Xml::Document> const &,std::wstring const &,bool)
0x18001e893  xorps   xmm0, xmm0
0x18001e896  movups  xmmword ptr [rbp+170h+appIdListNode._Ptr], xmm0
0x18001e89a  mov     rbx, [r14]
0x18001e89d  lea     ProfileNodes, aProvV2Appidlis; "./prov_v2:AppIDList"
0x18001e8a4  lea     this, [rsp+270h+Path]; this
0x18001e8a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001e8ae  nop
0x18001e8af  lea     hWwan, [rsp+270h+Path]; Path
0x18001e8b4  lea     ProfileNodes, [rbp+170h+appIdListNode]; result
0x18001e8b8  mov     this, rbx; this
0x18001e8bb  call    ?SelectSingle@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Node::SelectSingle(std::wstring const &)
0x18001e8c0  nop
0x18001e8c1  lea     this, [rsp+270h+Path]; this
0x18001e8c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e8cb  mov     this, [rbp+170h+appIdListNode._Ptr]; this
0x18001e8cf  test    this, this
0x18001e8d2  jz      short loc_18001E8F2
0x18001e8d4  lea     ProfileNodes, [rbp+170h+var_170]; result
0x18001e8d8  call    ?GetXml@Document@Xml@WcmCommon@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WcmCommon::Xml::Document::GetXml(void)
0x18001e8dd  mov     ProfileNodes, rax; _Right
0x18001e8e0  lea     this, [rbp+170h+appIdListXml]; this
0x18001e8e4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001e8e9  lea     this, [rbp+170h+var_170]; this
0x18001e8ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e8f2  lea     ProfileNodes, [rbp+170h+provisioningOpcodeData]; result
0x18001e8f6  mov     this, [rsp+270h+profileDoc._Ptr]; this
0x18001e8fb  call    ?GetXml@Document@Xml@WcmCommon@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WcmCommon::Xml::Document::GetXml(void)
0x18001e900  mov     this, rax; this
0x18001e903  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e908  lea     this, [rbp+170h+dwReasonCode]
0x18001e90c  mov     [rsp+270h+var_228], this
0x18001e911  mov     [rsp+270h+var_230], 0
0x18001e91a  mov     [rsp+270h+var_238], 0
0x18001e923  mov     [rsp+270h+var_240], 0
0x18001e92c  mov     [rsp+270h+_a3], 1
0x18001e934  mov     [rsp+270h+_a2], 0
0x18001e93d  mov     InterfaceGuid, rax
0x18001e940  xor     r8d, r8d
0x18001e943  lea     ProfileNodes, GUID_NULL
0x18001e94a  mov     this, rdi
0x18001e94d  call    cs:__imp_WwanSetProfile
0x18001e953  mov     edi, eax
0x18001e955  lea     this, [rbp+170h+provisioningOpcodeData]; this
0x18001e959  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e95e  test    edi, edi
0x18001e960  jnz     loc_18001EB42
0x18001e966  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001e96d  lea     rax, WPP_GLOBAL_Control
0x18001e974  cmp     r10, rax
0x18001e977  jz      short loc_18001E9A4
0x18001e979  test    byte ptr [r10+1Ch], 10h
0x18001e97e  jz      short loc_18001E9A4
0x18001e980  lea     this, [rbp+170h+profileName]; this
0x18001e984  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e989  mov     InterfaceGuid, rax; _a1
0x18001e98c  lea     edx, [rdi+18h]; id
0x18001e98f  mov     [rsp+270h+_a2], rsi; _a2
0x18001e994  lea     hWwan, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001e99b  mov     this, [r10+10h]; Logger
0x18001e99f  call    WPP_SF_S_guid_
0x18001e9a4  xorps   xmm0, xmm0
0x18001e9a7  xor     eax, eax
0x18001e9a9  movups  xmmword ptr [rbp+170h+provisioningOpcodeData._Mypair._Myval2._Myfirst], xmm0
0x18001e9ad  mov     [rbp+170h+provisioningOpcodeData._Mypair._Myval2._Myend], rax
0x18001e9b1  lea     this, [rbp+170h+var_190]; this
0x18001e9b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e9ba  nop
0x18001e9bb  lea     ProfileNodes, [r13+8]; Params
0x18001e9bf  mov     hWwan, rax; PlanName
0x18001e9c2  lea     this, [rbp+170h+provisioningOpcodeData]; result
0x18001e9c6  call    ?GetCarrierSubscriberPlanBlob@Wcmutil@@SA?AV?$vector@EV?$allocator@E@std@@@std@@AEBUParameters@Handler@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Wcmutil::GetCarrierSubscriberPlanBlob(Handler::Parameters const &,std::wstring const &)
0x18001e9cb  nop
0x18001e9cc  lea     this, [rbp+170h+var_190]; this
0x18001e9d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e9d5  lea     this, [rsp+270h+revertImpersonate]; this
0x18001e9da  call    ??0AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::AutoRevertImpersonate(void)
0x18001e9df  lea     this, [rbp+170h+profileName]; this
0x18001e9e3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e9e8  mov     hWwan, rax; strProfileName
0x18001e9eb  lea     rax, [rbp+170h+provisioningOpcodeData]
0x18001e9ef  mov     [rsp+270h+_a2], rax; DataBlob
0x18001e9f4  mov     r9d, 107h; OpCode
0x18001e9fa  mov     ProfileNodes, rsi; pInterface
0x18001e9fd  mov     rbx, [rbp+170h+var_1D8]
0x18001ea01  mov     this, [rbx]; this
0x18001ea04  call    ?WcmSetParameterFromBlob@Wcmutil@@QEBAKPEBU_GUID@@PEBGW4_WCM_OPCODE@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Wcmutil::WcmSetParameterFromBlob(_GUID const *,ushort const *,_WCM_OPCODE,std::vector<uchar> const &)
0x18001ea09  test    eax, eax
0x18001ea0b  jz      short loc_18001EA3E
0x18001ea0d  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001ea14  lea     ProfileNodes, WPP_GLOBAL_Control
0x18001ea1b  cmp     this, ProfileNodes
0x18001ea1e  jz      short loc_18001EA3E
0x18001ea20  test    byte ptr [this+1Ch], 4
0x18001ea24  jz      short loc_18001EA3E
0x18001ea26  mov     edx, 19h; id
0x18001ea2b  mov     r9d, eax; _a1
0x18001ea2e  lea     hWwan, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001ea35  mov     this, [this+10h]; Logger
0x18001ea39  call    WPP_SF_d
0x18001ea3e  cmp     [rbp+170h+appIdListXml._Mypair._Myval2._Mysize], 0
0x18001ea43  jz      loc_18001EB15
0x18001ea49  lea     this, [rbp+170h+profileName]; this
0x18001ea4d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ea52  mov     hWwan, rax; strProfileName
0x18001ea55  lea     rax, [rbp+170h+appIdListXml]
0x18001ea59  mov     [rsp+270h+_a2], rax; DataString
0x18001ea5e  mov     r9d, 113h; OpCode
0x18001ea64  mov     ProfileNodes, rsi; pInterface
0x18001ea67  mov     this, [rbx]; this
0x18001ea6a  call    ?WcmSetParameterFromString@Wcmutil@@QEBAKPEBU_GUID@@PEBGW4_WCM_OPCODE@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Wcmutil::WcmSetParameterFromString(_GUID const *,ushort const *,_WCM_OPCODE,std::wstring &)
0x18001ea6f  mov     edi, eax
0x18001ea71  test    eax, eax
0x18001ea73  jz      loc_18001EB15
0x18001ea79  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001ea80  lea     rbx, WPP_GLOBAL_Control
0x18001ea87  cmp     r10, rbx
0x18001ea8a  jz      short loc_18001EAF6
0x18001ea8c  test    byte ptr [r10+1Ch], 4
0x18001ea91  jz      short loc_18001EAC4
0x18001ea93  lea     this, [rbp+170h+profileName]; this
0x18001ea97  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ea9c  mov     InterfaceGuid, rax; _a1
0x18001ea9f  mov     edx, 1Ah; id
0x18001eaa4  mov     [rsp+270h+_a3], edi; _a3
0x18001eaa8  mov     [rsp+270h+_a2], rsi; _a2
0x18001eaad  lea     hWwan, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001eab4  mov     this, [r10+10h]; Logger
0x18001eab8  call    WPP_SF_S_guid_D
0x18001eabd  mov     r10, cs:WPP_GLOBAL_Control
0x18001eac4  cmp     r10, rbx; __annotation("TMF:",
0x18001eac7  jz      short loc_18001EAF6
0x18001eac9  test    byte ptr [r10+1Ch], 4
0x18001eace  jz      short loc_18001EAF6
0x18001ead0  lea     this, [rbp+170h+profileName]; this
0x18001ead4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ead9  mov     InterfaceGuid, rax; _a1
0x18001eadc  mov     edx, 1Bh; id
0x18001eae1  mov     [rsp+270h+_a2], rsi; _a2
0x18001eae6  lea     hWwan, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001eaed  mov     this, [r10+10h]; Logger
0x18001eaf1  call    WPP_SF_S_guid_
0x18001eaf6  lea     this, [rbp+170h+profileName]; this
0x18001eafa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001eaff  mov     hWwan, rax
0x18001eb02  xor     r9d, r9d
0x18001eb05  mov     ProfileNodes, rsi
0x18001eb08  mov     this, [rsp+270h+var_218]
0x18001eb0d  call    cs:__imp_WwanDeleteProfile
0x18001eb13  jmp     short loc_18001EB1C
0x18001eb15  lea     rbx, WPP_GLOBAL_Control
0x18001eb1c  lea     this, [rsp+270h+revertImpersonate]; this
0x18001eb21  call    ??1AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::~AutoRevertImpersonate(void)
0x18001eb26  call    ?VerifyUserIsImpersonating@@YAXXZ; VerifyUserIsImpersonating(void)
0x18001eb2b  nop
0x18001eb2c  lea     this, [rbp+170h+provisioningOpcodeData]; this
0x18001eb30  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001eb35  test    edi, edi
0x18001eb37  jz      loc_18001EBF7
0x18001eb3d  jmp     loc_18001EBF4
0x18001eb42  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits+1, 10h
0x18001eb49  jz      short loc_18001EB84
0x18001eb4b  mov     r8d, [rbp+170h+dwReasonCode]
0x18001eb4f  test    edi, edi
0x18001eb51  jg      short loc_18001EB57
0x18001eb53  mov     edx, edi
0x18001eb55  jmp     short loc_18001EB60
0x18001eb57  movzx   edx, di
0x18001eb5a  or      edx, 80070000h
0x18001eb60  lea     this, [rbp+170h+profileName]; this
0x18001eb64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001eb69  mov     InterfaceGuid, rax; _Arg2
0x18001eb6c  mov     [rsp+270h+_a3], r8d; Context
0x18001eb71  mov     dword ptr [rsp+270h+_a2], edx; _Arg3
0x18001eb75  mov     hWwan, rsi; _Arg1
0x18001eb78  lea     ProfileNodes, SetWwanProfileFailed; _Arg0
0x18001eb7f  call    McTemplateU0jzdq_EtwEventWriteTransfer
0x18001eb84  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001eb8b  lea     rbx, WPP_GLOBAL_Control
0x18001eb92  cmp     r10, rbx
0x18001eb95  jz      short loc_18001EBF4
0x18001eb97  test    byte ptr [r10+1Ch], 8
0x18001eb9c  jz      short loc_18001EBCF
0x18001eb9e  lea     this, [rbp+170h+profileName]; this
0x18001eba2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001eba7  mov     InterfaceGuid, rax; _a1
0x18001ebaa  mov     edx, 1Ch; id
0x18001ebaf  mov     [rsp+270h+_a3], edi; _a3
0x18001ebb3  mov     [rsp+270h+_a2], rsi; _a2
0x18001ebb8  lea     hWwan, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001ebbf  mov     this, [r10+10h]; Logger
0x18001ebc3  call    WPP_SF_S_guid_D
0x18001ebc8  mov     r10, cs:WPP_GLOBAL_Control
0x18001ebcf  cmp     r10, rbx; __annotation("TMF:",
0x18001ebd2  jz      short loc_18001EBF4
0x18001ebd4  test    byte ptr [r10+1Ch], 8
0x18001ebd9  jz      short loc_18001EBF4
0x18001ebdb  mov     edx, 1Dh; id
0x18001ebe0  mov     r9d, [rbp+170h+dwReasonCode]; _a1
0x18001ebe4  lea     hWwan, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001ebeb  mov     this, [r10+10h]; Logger
0x18001ebef  call    WPP_SF_d
0x18001ebf4  mov     r15b, 1
0x18001ebf7  lea     ProfileNodes, [rbp+170h+profileName]; UniqueProfileName
0x18001ebfb  lea     this, [rbp+170h+originalProfileName]; result
  ... truncated ...
```

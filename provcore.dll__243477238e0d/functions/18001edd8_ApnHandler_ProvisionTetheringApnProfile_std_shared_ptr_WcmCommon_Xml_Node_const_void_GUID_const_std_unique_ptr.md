# ApnHandler::ProvisionTetheringApnProfile(std::shared_ptr<WcmCommon::Xml::Node> const &,void *,_GUID const &,std::unique_ptr<Wcmutil,std::default_delete<Wcmutil>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001edd8`
- end: `0x18001f24c`
- name: `?ProvisionTetheringApnProfile@ApnHandler@@AEAA_NAEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@PEAXAEBU_GUID@@AEBV?$unique_ptr@VWcmutil@@U?$default_delete@VWcmutil@@@std@@@3@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `1140`
- prototype: `bool __fastcall(ApnHandler *this, const std::shared_ptr<WcmCommon::Xml::Node> *TetheringProfileNode, void *hWwan, const _GUID *InterfaceGuid, const std::unique_ptr<Wcmutil> *Wcm, std::wstring *TetheringResultXml)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001df00`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x18000af94`
- `0x18000b0a0`
- `0x18000b8c0`
- `0x18000fa6c`
- `0x180011844`
- `0x180011cfc`
- `0x180012770`
- `0x1800127cc`
- `0x18001a0d4`
- `0x18001c07c`
- `0x18001c340`
- `0x18001c61c`
- `0x18001d304`
- `0x18001d608`
- `0x18001d664`
- `0x18001edd8`
- `0x18001f2e4`
- `0x180020a6c`
- `0x180020bcc`
- `0x180020c48`
- `0x180020e70`
- `0x18002108c`
- `0x1800211e0`
- `0x18003fe90`
- `0x180040800`
- `0x180048194`
- `0x180048f28`
- `0x180048f78`
- `0x180049d70`
- `0x180049ed0`
- `0x180057790`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetProfile` at `0x18001ef32`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetProfile` at `0x18001ef32`

## string_xrefs

- `0x18001ee8d`: `http://www.microsoft.com/networking/WWAN/profile/v1`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
bool __fastcall ApnHandler::ProvisionTetheringApnProfile(
        ApnHandler *this,
        const std::shared_ptr<WcmCommon::Xml::Node> *TetheringProfileNode,
        void *hWwan,
        const _GUID *InterfaceGuid,
        const std::unique_ptr<Wcmutil> *Wcm,
        std::wstring *TetheringResultXml)
{
  WcmCommon::Xml::Node *Ptr; // rbx
  std::shared_ptr<WcmCommon::Xml::Node> *v11; // rax
  std::wstring *Xml; // rax
  const wchar_t *v13; // rax
  signed int v14; // edi
  const wchar_t *v15; // rax
  __int64 v16; // r10
  const std::wstring *v17; // rax
  const wchar_t *v18; // rax
  int v19; // eax
  const wchar_t *v20; // rax
  int v21; // edx
  _MCGEN_TRACE_CONTEXT *v22; // rcx
  unsigned int Context; // r8d
  WPP_PROJECT_CONTROL_BLOCK *v24; // r10
  const wchar_t *v25; // rax
  __int64 v26; // r10
  const wchar_t *v27; // rax
  __int64 v28; // r10
  std::wstring *v29; // rax
  std::wstring *v30; // rax
  std::wstring *v31; // rbx
  std::wstring *v32; // rax
  HRESULT v33; // edx
  std::wstring *v34; // rbx
  std::wstring *v35; // rax
  AutoRevertImpersonate revertImpersonate; // [rsp+50h] [rbp-B0h] BYREF
  std::wstring Path; // [rsp+58h] [rbp-A8h] BYREF
  std::wstring *p_Path; // [rsp+78h] [rbp-88h]
  std::shared_ptr<WcmCommon::Xml::Document> profileDoc; // [rsp+80h] [rbp-80h] BYREF
  std::wstring result; // [rsp+90h] [rbp-70h] BYREF
  std::wstring v42; // [rsp+B0h] [rbp-50h] BYREF
  WWAN_PROFILE_INVALID_REASON dwReasonCode; // [rsp+D0h] [rbp-30h] BYREF
  std::vector<unsigned char> provisioningOpcodeData; // [rsp+D8h] [rbp-28h] BYREF
  std::wstring profileName; // [rsp+F8h] [rbp-8h] BYREF
  std::wstring originalProfileName; // [rsp+118h] [rbp+18h] BYREF
  XmlBuilder::Node results; // [rsp+140h] [rbp+40h] BYREF

  dwReasonCode = WwanProfileErrNone;
  Ptr = TetheringProfileNode->_Ptr;
  std::wstring::wstring(&Path, L"./prov_v2:Name");
  v11 = WcmCommon::Xml::Node::SelectSingle(Ptr, (std::shared_ptr<WcmCommon::Xml::Node> *)&provisioningOpcodeData, &Path);
  WcmCommon::Xml::Node::GetText(v11->_Ptr, &profileName);
  if ( provisioningOpcodeData._Mypair._Myval2._Mylast )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)provisioningOpcodeData._Mypair._Myval2._Mylast);
  std::wstring::_Tidy_deallocate(&Path);
  profileDoc = 0;
  WcmCommon::Xml::Node::TransformIntoDocument(TetheringProfileNode->_Ptr, &profileDoc, &this->m_tetheringApnXsl);
  std::wstring::wstring((std::wstring *)&provisioningOpcodeData, L"http://www.microsoft.com/networking/WWAN/profile/v1");
  std::wstring::wstring(&Path, L"default");
  WcmCommon::Xml::Document::AddSelectionNamespace(profileDoc._Ptr, &Path, (const std::wstring *)&provisioningOpcodeData);
  std::wstring::_Tidy_deallocate(&Path);
  std::wstring::_Tidy_deallocate((std::wstring *)&provisioningOpcodeData);
  InsertNodesInProfileXml(&profileDoc, &this->m_params.SubscriberId, 1);
  Xml = WcmCommon::Xml::Document::GetXml((WcmCommon::Xml::Node *)profileDoc._Ptr, &Path);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Xml->_Mypair._Myval2);
  v14 = WwanSetProfile(hWwan, &GUID_NULL, 0, v13, 0, 1, 0, 0, 0, &dwReasonCode);
  std::wstring::_Tidy_deallocate(&Path);
  if ( v14 )
  {
    if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x1000) != 0 )
    {
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
      McTemplateU0jzdq_EtwEventWriteTransfer(v22, &SetWwanProfileFailed, InterfaceGuid, v20, v21, Context);
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
      {
        v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
        WPP_SF_S_guid_D(
          *(_QWORD *)(v26 + 16),
          0x21u,
          WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids,
          v25,
          InterfaceGuid,
          v14);
        v24 = WPP_GLOBAL_Control;
      }
      if ( v24 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v24->ReserveSpace[28] & 8) != 0 )
        WPP_SF_d(v24->Control.Logger, 0x22u, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, dwReasonCode);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
      WPP_SF_S_guid_(*(_QWORD *)(v16 + 16), 0x1Fu, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, v15, InterfaceGuid);
    }
    memset(&provisioningOpcodeData, 0, sizeof(provisioningOpcodeData));
    std::wstring::wstring(&Path);
    Wcmutil::GetCarrierSubscriberPlanBlob(&provisioningOpcodeData, &this->m_params, v17);
    std::wstring::_Tidy_deallocate(&Path);
    AutoRevertImpersonate::AutoRevertImpersonate(&revertImpersonate);
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
    v19 = Wcmutil::WcmSetParameterFromBlob(
            Wcm->_Mypair._Myval2,
            InterfaceGuid,
            v18,
            wcm_intf_opcode_provisioning,
            &provisioningOpcodeData);
    if ( v19
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x20u, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, v19);
    }
    AutoRevertImpersonate::~AutoRevertImpersonate(&revertImpersonate);
    VerifyUserIsImpersonating();
    std::vector<unsigned char>::_Tidy((std::vector<char> *)&provisioningOpcodeData);
  }
  ProfileUtil::GetOriginalProfileName(&originalProfileName, &profileName);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&originalProfileName._Mypair._Myval2);
    WPP_SF_S(*(_QWORD *)(v28 + 16), 0x23u, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, v27);
  }
  memset_0(&results, 0, sizeof(results));
  std::wstring::wstring(&v42, L"TetheringProfile");
  XmlBuilder::Node::Node(&results, v29);
  p_Path = &Path;
  std::wstring::wstring(&Path, &originalProfileName);
  v31 = v30;
  std::wstring::wstring(&result, L"name");
  XmlBuilder::Node::SetAttribute(&results, v32, v31);
  provisioningOpcodeData._Mypair._Myval2._Myfirst = (unsigned __int8 *)&result;
  if ( v14 > 0 )
    v33 = (unsigned __int16)v14 | 0x80070000;
  else
    v33 = v14;
  v34 = XmlBuilder::HrToString(&result, v33);
  std::wstring::wstring(&Path, L"errorCode");
  XmlBuilder::Node::SetAttribute(&results, v35, v34);
  XmlBuilder::Node::GenerateXml(&results, &Path, 0);
  std::wstring::operator=(TetheringResultXml, &Path);
  std::wstring::_Tidy_deallocate(&Path);
  XmlBuilder::Node::~Node(&results);
  std::wstring::_Tidy_deallocate(&originalProfileName);
  if ( profileDoc._Rep )
    std::_Ref_count_base::_Decref(profileDoc._Rep);
  std::wstring::_Tidy_deallocate(&profileName);
  return v14 == 0;
}

```

## disassembly

```asm
0x18001edd8  push    rbp
0x18001edda  push    rbx
0x18001eddb  push    rsi
0x18001eddc  push    rdi
0x18001eddd  push    r12
0x18001eddf  push    r13
0x18001ede1  push    r14
0x18001ede3  push    r15
0x18001ede5  lea     rbp, [rsp-0A8h]
0x18001eded  sub     rsp, 1A8h
0x18001edf4  mov     rax, cs:__security_cookie
0x18001edfb  xor     rax, rsp
0x18001edfe  mov     [rbp+0E0h+var_50], rax
0x18001ee05  mov     rsi, InterfaceGuid
0x18001ee08  mov     r12, hWwan
0x18001ee0b  mov     rdi, TetheringProfileNode
0x18001ee0e  mov     r14, this
0x18001ee11  mov     r15, [rbp+0E0h+arg_20]
0x18001ee18  mov     r13, [rbp+0E0h+arg_28]
0x18001ee1f  mov     [rbp+0E0h+dwReasonCode], 0
0x18001ee26  mov     rbx, [TetheringProfileNode]
0x18001ee29  lea     TetheringProfileNode, aProvV2Name; "./prov_v2:Name"
0x18001ee30  lea     this, [rsp+1E0h+Path]; this
0x18001ee35  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ee3a  nop
0x18001ee3b  lea     hWwan, [rsp+1E0h+Path]; Path
0x18001ee40  lea     TetheringProfileNode, [rbp+0E0h+provisioningOpcodeData]; result
0x18001ee44  mov     this, rbx; this
0x18001ee47  call    ?SelectSingle@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Node::SelectSingle(std::wstring const &)
0x18001ee4c  nop
0x18001ee4d  lea     TetheringProfileNode, [rbp+0E0h+profileName]; result
0x18001ee51  mov     this, [rax]; this
0x18001ee54  call    ?GetText@Node@Xml@WcmCommon@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WcmCommon::Xml::Node::GetText(void)
0x18001ee59  nop
0x18001ee5a  mov     this, [rbp+0E0h+provisioningOpcodeData._Mypair._Myval2._Mylast]; this
0x18001ee5e  xor     ebx, ebx
0x18001ee60  test    this, this
0x18001ee63  jz      short loc_18001EE6B
0x18001ee65  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ee6a  nop
0x18001ee6b  lea     this, [rsp+1E0h+Path]; this
0x18001ee70  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ee75  xorps   xmm0, xmm0
0x18001ee78  movups  xmmword ptr [rbp+0E0h+profileDoc._Ptr], xmm0
0x18001ee7c  lea     hWwan, [r14+78h]; xslDoc
0x18001ee80  lea     TetheringProfileNode, [rbp+0E0h+profileDoc]; result
0x18001ee84  mov     this, [rdi]; this
0x18001ee87  call    ?TransformIntoDocument@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV45@@Z; WcmCommon::Xml::Node::TransformIntoDocument(std::shared_ptr<WcmCommon::Xml::Document> const &)
0x18001ee8c  nop
0x18001ee8d  lea     TetheringProfileNode, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x18001ee94  lea     this, [rbp+0E0h+provisioningOpcodeData]; this
0x18001ee98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ee9d  nop
0x18001ee9e  lea     TetheringProfileNode, aDefault; "default"
0x18001eea5  lea     this, [rsp+1E0h+Path]; this
0x18001eeaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001eeaf  nop
0x18001eeb0  lea     hWwan, [rbp+0E0h+provisioningOpcodeData]; ns
0x18001eeb4  lea     TetheringProfileNode, [rsp+1E0h+Path]; key
0x18001eeb9  mov     this, [rbp+0E0h+profileDoc._Ptr]; this
0x18001eebd  call    ?AddSelectionNamespace@Document@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WcmCommon::Xml::Document::AddSelectionNamespace(std::wstring const &,std::wstring const &)
0x18001eec2  nop
0x18001eec3  lea     this, [rsp+1E0h+Path]; this
0x18001eec8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eecd  nop
0x18001eece  lea     this, [rbp+0E0h+provisioningOpcodeData]; this
0x18001eed2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eed7  lea     TetheringProfileNode, [r14+28h]; SubscriberId
0x18001eedb  mov     r8b, 1; IsTethering
0x18001eede  lea     this, [rbp+0E0h+profileDoc]; ProfileDoc
0x18001eee2  call    ?InsertNodesInProfileXml@@YAXAEBV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@Z; InsertNodesInProfileXml(std::shared_ptr<WcmCommon::Xml::Document> const &,std::wstring const &,bool)
0x18001eee7  lea     TetheringProfileNode, [rsp+1E0h+Path]; result
0x18001eeec  mov     this, [rbp+0E0h+profileDoc._Ptr]; this
0x18001eef0  call    ?GetXml@Document@Xml@WcmCommon@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WcmCommon::Xml::Document::GetXml(void)
0x18001eef5  mov     this, rax; this
0x18001eef8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001eefd  lea     this, [rbp+0E0h+dwReasonCode]
0x18001ef01  mov     [rsp+1E0h+var_198], this
0x18001ef06  mov     [rsp+1E0h+var_1A0], rbx
0x18001ef0b  mov     [rsp+1E0h+var_1A8], rbx
0x18001ef10  mov     [rsp+1E0h+var_1B0], rbx
0x18001ef15  mov     [rsp+1E0h+Context], 1
0x18001ef1d  mov     [rsp+1E0h+_a2], rbx
0x18001ef22  mov     InterfaceGuid, rax
0x18001ef25  xor     r8d, r8d
0x18001ef28  lea     TetheringProfileNode, GUID_NULL
0x18001ef2f  mov     this, r12
0x18001ef32  call    cs:__imp_WwanSetProfile
0x18001ef38  mov     edi, eax
0x18001ef3a  lea     this, [rsp+1E0h+Path]; this
0x18001ef3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ef44  lea     r12, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids
0x18001ef4b  test    edi, edi
0x18001ef4d  jnz     loc_18001F038
0x18001ef53  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x18001ef5a  mov     r10, cs:WPP_GLOBAL_Control
0x18001ef61  cmp     r10, rbx
0x18001ef64  jz      short loc_18001EF8D
0x18001ef66  test    byte ptr [r10+1Ch], 10h
0x18001ef6b  jz      short loc_18001EF8D
0x18001ef6d  lea     this, [rbp+0E0h+profileName]; this
0x18001ef71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ef76  mov     InterfaceGuid, rax; _a1
0x18001ef79  lea     edx, [rdi+1Fh]; id
0x18001ef7c  mov     [rsp+1E0h+_a2], rsi; _a2
0x18001ef81  mov     hWwan, r12; TraceGuid
0x18001ef84  mov     this, [r10+10h]; Logger
0x18001ef88  call    WPP_SF_S_guid_
0x18001ef8d  xorps   xmm0, xmm0
0x18001ef90  xor     eax, eax
0x18001ef92  movups  xmmword ptr [rbp+0E0h+provisioningOpcodeData._Mypair._Myval2._Myfirst], xmm0
0x18001ef96  mov     [rbp+0E0h+provisioningOpcodeData._Mypair._Myval2._Myend], rax
0x18001ef9a  lea     this, [rsp+1E0h+Path]; this
0x18001ef9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001efa4  nop
0x18001efa5  lea     TetheringProfileNode, [r14+8]; Params
0x18001efa9  mov     hWwan, rax; PlanName
0x18001efac  lea     this, [rbp+0E0h+provisioningOpcodeData]; result
0x18001efb0  call    ?GetCarrierSubscriberPlanBlob@Wcmutil@@SA?AV?$vector@EV?$allocator@E@std@@@std@@AEBUParameters@Handler@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Wcmutil::GetCarrierSubscriberPlanBlob(Handler::Parameters const &,std::wstring const &)
0x18001efb5  nop
0x18001efb6  lea     this, [rsp+1E0h+Path]; this
0x18001efbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001efc0  lea     this, [rsp+1E0h+revertImpersonate]; this
0x18001efc5  call    ??0AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::AutoRevertImpersonate(void)
0x18001efca  lea     this, [rbp+0E0h+profileName]; this
0x18001efce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001efd3  mov     hWwan, rax; strProfileName
0x18001efd6  lea     rax, [rbp+0E0h+provisioningOpcodeData]
0x18001efda  mov     [rsp+1E0h+_a2], rax; DataBlob
0x18001efdf  mov     r9d, 107h; OpCode
0x18001efe5  mov     TetheringProfileNode, rsi; pInterface
0x18001efe8  mov     this, [r15]; this
0x18001efeb  call    ?WcmSetParameterFromBlob@Wcmutil@@QEBAKPEBU_GUID@@PEBGW4_WCM_OPCODE@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Wcmutil::WcmSetParameterFromBlob(_GUID const *,ushort const *,_WCM_OPCODE,std::vector<uchar> const &)
0x18001eff0  test    eax, eax
0x18001eff2  jz      short loc_18001F01A
0x18001eff4  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001effb  cmp     this, rbx
0x18001effe  jz      short loc_18001F01A
0x18001f000  test    byte ptr [this+1Ch], 4
0x18001f004  jz      short loc_18001F01A
0x18001f006  mov     edx, 20h ; ' '; id
0x18001f00b  mov     r9d, eax; _a1
0x18001f00e  mov     hWwan, r12; TraceGuid
0x18001f011  mov     this, [this+10h]; Logger
0x18001f015  call    WPP_SF_d
0x18001f01a  lea     this, [rsp+1E0h+revertImpersonate]; this
0x18001f01f  call    ??1AutoRevertImpersonate@@QEAA@XZ; AutoRevertImpersonate::~AutoRevertImpersonate(void)
0x18001f024  call    ?VerifyUserIsImpersonating@@YAXXZ; VerifyUserIsImpersonating(void)
0x18001f029  nop
0x18001f02a  lea     this, [rbp+0E0h+provisioningOpcodeData]; this
0x18001f02e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001f033  jmp     loc_18001F0E2
0x18001f038  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits+1, 10h
0x18001f03f  jz      short loc_18001F07A
0x18001f041  mov     r8d, [rbp+0E0h+dwReasonCode]
0x18001f045  test    edi, edi
0x18001f047  jg      short loc_18001F04D
0x18001f049  mov     edx, edi
0x18001f04b  jmp     short loc_18001F056
0x18001f04d  movzx   edx, di
0x18001f050  or      edx, 80070000h
0x18001f056  lea     this, [rbp+0E0h+profileName]; this
0x18001f05a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f05f  mov     InterfaceGuid, rax; _Arg2
0x18001f062  mov     [rsp+1E0h+Context], r8d; Context
0x18001f067  mov     dword ptr [rsp+1E0h+_a2], edx; _Arg3
0x18001f06b  mov     hWwan, rsi; _Arg1
0x18001f06e  lea     TetheringProfileNode, SetWwanProfileFailed; _Arg0
0x18001f075  call    McTemplateU0jzdq_EtwEventWriteTransfer
0x18001f07a  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x18001f081  mov     r10, cs:WPP_GLOBAL_Control
0x18001f088  cmp     r10, rbx
0x18001f08b  jz      short loc_18001F0E2
0x18001f08d  test    byte ptr [r10+1Ch], 8
0x18001f092  jz      short loc_18001F0C1
0x18001f094  lea     this, [rbp+0E0h+profileName]; this
0x18001f098  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f09d  mov     InterfaceGuid, rax; _a1
0x18001f0a0  mov     edx, 21h ; '!'; id
0x18001f0a5  mov     [rsp+1E0h+Context], edi; _a3
0x18001f0a9  mov     [rsp+1E0h+_a2], rsi; _a2
0x18001f0ae  mov     hWwan, r12; TraceGuid
0x18001f0b1  mov     this, [r10+10h]; Logger
0x18001f0b5  call    WPP_SF_S_guid_D
0x18001f0ba  mov     r10, cs:WPP_GLOBAL_Control
0x18001f0c1  cmp     r10, rbx; __annotation("TMF:",
0x18001f0c4  jz      short loc_18001F0E2
0x18001f0c6  test    byte ptr [r10+1Ch], 8
0x18001f0cb  jz      short loc_18001F0E2
0x18001f0cd  mov     edx, 22h ; '"'; id
0x18001f0d2  mov     r9d, [rbp+0E0h+dwReasonCode]; _a1
0x18001f0d6  mov     hWwan, r12; TraceGuid
0x18001f0d9  mov     this, [r10+10h]; Logger
0x18001f0dd  call    WPP_SF_d
0x18001f0e2  lea     TetheringProfileNode, [rbp+0E0h+profileName]; UniqueProfileName
0x18001f0e6  lea     this, [rbp+0E0h+originalProfileName]; result
0x18001f0ea  call    ?GetOriginalProfileName@ProfileUtil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ProfileUtil::GetOriginalProfileName(std::wstring const &)
0x18001f0ef  nop
0x18001f0f0  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001f0f7  cmp     r10, rbx
0x18001f0fa  jz      short loc_18001F120
0x18001f0fc  test    byte ptr [r10+1Ch], 10h
0x18001f101  jz      short loc_18001F120
0x18001f103  lea     this, [rbp+0E0h+originalProfileName]; this
0x18001f107  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f10c  mov     InterfaceGuid, rax; _a1
0x18001f10f  mov     edx, 23h ; '#'; id
0x18001f114  mov     hWwan, r12; TraceGuid
0x18001f117  mov     this, [r10+10h]; Logger
0x18001f11b  call    WPP_SF_S
0x18001f120  xor     edx, edx; Val
0x18001f122  lea     r8d, [TetheringProfileNode+50h]; Size
0x18001f126  lea     this, [rbp+0E0h+results]; void *
0x18001f12a  call    memset_0
0x18001f12f  lea     TetheringProfileNode, aTetheringprofi; "TetheringProfile"
0x18001f136  lea     this, [rbp+0E0h+var_130]; this
0x18001f13a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f13f  mov     TetheringProfileNode, rax
0x18001f142  lea     this, [rbp+0E0h+results]
0x18001f146  call    ??0Node@XmlBuilder@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlBuilder::Node::Node(std::wstring)
0x18001f14b  nop
0x18001f14c  lea     rax, [rsp+1E0h+Path]
0x18001f151  mov     [rsp+1E0h+var_168], rax
0x18001f156  lea     TetheringProfileNode, [rbp+0E0h+originalProfileName]; _Right
0x18001f15a  lea     this, [rsp+1E0h+Path]; this
0x18001f15f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f164  mov     rbx, rax
0x18001f167  lea     TetheringProfileNode, aName_1; "name"
0x18001f16e  lea     this, [rbp+0E0h+result]; this
0x18001f172  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f177  nop
0x18001f178  mov     hWwan, rbx
0x18001f17b  mov     TetheringProfileNode, rax
0x18001f17e  lea     this, [rbp+0E0h+results]
0x18001f182  call    ?SetAttribute@Node@XmlBuilder@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; XmlBuilder::Node::SetAttribute(std::wstring,std::wstring)
0x18001f187  lea     rax, [rbp+0E0h+result]
0x18001f18b  mov     [rbp+0E0h+provisioningOpcodeData._Mypair._Myval2._Myfirst], rax
0x18001f18f  test    edi, edi
0x18001f191  jg      short loc_18001F197
0x18001f193  mov     edx, edi
0x18001f195  jmp     short loc_18001F1A0
0x18001f197  movzx   edx, di
0x18001f19a  or      edx, 80070000h; Hr
0x18001f1a0  lea     this, [rbp+0E0h+result]; result
0x18001f1a4  call    ?HrToString@XmlBuilder@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; XmlBuilder::HrToString(long)
0x18001f1a9  mov     rbx, rax
0x18001f1ac  lea     TetheringProfileNode, aErrorcode; "errorCode"
0x18001f1b3  lea     this, [rsp+1E0h+Path]; this
0x18001f1b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f1bd  nop
0x18001f1be  mov     hWwan, rbx
0x18001f1c1  mov     TetheringProfileNode, rax
0x18001f1c4  lea     this, [rbp+0E0h+results]
0x18001f1c8  call    ?SetAttribute@Node@XmlBuilder@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; XmlBuilder::Node::SetAttribute(std::wstring,std::wstring)
0x18001f1cd  xor     r8d, r8d; indentationLevel
0x18001f1d0  lea     TetheringProfileNode, [rsp+1E0h+Path]; result
0x18001f1d5  lea     this, [rbp+0E0h+results]; this
0x18001f1d9  call    ?GenerateXml@Node@XmlBuilder@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; XmlBuilder::Node::GenerateXml(unsigned __int64)
0x18001f1de  lea     TetheringProfileNode, [rsp+1E0h+Path]; _Right
0x18001f1e3  mov     this, r13; this
0x18001f1e6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001f1eb  lea     this, [rsp+1E0h+Path]; this
0x18001f1f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f1f5  nop
0x18001f1f6  test    edi, edi
0x18001f1f8  setz    bl
0x18001f1fb  lea     this, [rbp+0E0h+results]; this
0x18001f1ff  call    ??1Node@XmlBuilder@@QEAA@XZ; XmlBuilder::Node::~Node(void)
0x18001f204  nop
0x18001f205  lea     this, [rbp+0E0h+originalProfileName]; this
0x18001f209  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f20e  nop
0x18001f20f  mov     this, [rbp+0E0h+profileDoc._Rep]; this
0x18001f213  test    this, this
0x18001f216  jz      short loc_18001F21E
0x18001f218  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f21d  nop
0x18001f21e  lea     this, [rbp+0E0h+profileName]; this
0x18001f222  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f227  mov     al, bl
0x18001f229  mov     this, [rbp+0E0h+var_50]
0x18001f230  xor     this, rsp; StackCookie
0x18001f233  call    __security_check_cookie
0x18001f238  add     rsp, 1A8h
0x18001f23f  pop     r15
0x18001f241  pop     r14
0x18001f243  pop     r13
0x18001f245  pop     r12
0x18001f247  pop     rdi
0x18001f248  pop     rsi
0x18001f249  pop     rbx
0x18001f24a  pop     rbp
0x18001f24b  retn
```

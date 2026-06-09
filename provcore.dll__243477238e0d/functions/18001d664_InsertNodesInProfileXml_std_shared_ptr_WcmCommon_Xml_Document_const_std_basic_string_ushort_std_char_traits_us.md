# InsertNodesInProfileXml(std::shared_ptr<WcmCommon::Xml::Document> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x18001d664`
- end: `0x18001db68`
- name: `?InsertNodesInProfileXml@@YAXAEBV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_N@Z`
- size: `1284`
- prototype: `void __fastcall(const std::shared_ptr<WcmCommon::Xml::Document> *ProfileDoc, const std::wstring *SubscriberId, bool IsTethering)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e71c`
- `0x18001edd8`

## callees

- `0x18000af94`
- `0x18000fa6c`
- `0x180011844`
- `0x180011cfc`
- `0x180012748`
- `0x1800127cc`
- `0x18001d664`
- `0x180048558`
- `0x180048f04`
- `0x180049d70`
- `0x180049e4c`

## string_xrefs

- `0x18001d72d`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18001d7e5`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18001d851`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18001d900`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18001d994`: `http://www.microsoft.com/networking/WWAN/profile/v3`
- `0x18001da43`: `http://www.microsoft.com/networking/WWAN/profile/v3`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
void __fastcall InsertNodesInProfileXml(
        const std::shared_ptr<WcmCommon::Xml::Document> *ProfileDoc,
        const std::wstring *SubscriberId,
        bool IsTethering)
{
  WcmCommon::Xml::Node *Ptr; // rbx
  const wchar_t *v7; // rax
  __int64 v8; // r10
  std::wstring Path; // [rsp+30h] [rbp-D0h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> isTetheringProfileNode; // [rsp+50h] [rbp-B0h] BYREF
  std::wstring Namespace; // [rsp+70h] [rbp-90h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> profileCreationTypeNode; // [rsp+90h] [rbp-70h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> subscriberIdNode; // [rsp+A0h] [rbp-60h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> connectionModeNode; // [rsp+B0h] [rbp-50h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> isAdditionalPdpContextProfileNode; // [rsp+C0h] [rbp-40h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> contextNode; // [rsp+E0h] [rbp-20h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> rootNode; // [rsp+F0h] [rbp-10h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> isDefaultNode; // [rsp+100h] [rbp+0h] BYREF
  std::wstring v19; // [rsp+120h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids);
  }
  rootNode = 0;
  WcmCommon::Xml::Document::GetRoot(ProfileDoc->_Ptr, &rootNode);
  contextNode = 0;
  Ptr = rootNode._Ptr;
  std::wstring::wstring(&Path, L"./default:Context");
  WcmCommon::Xml::Node::SelectSingle(Ptr, &contextNode, &Path);
  std::wstring::_Tidy_deallocate(&Path);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids);
  }
  connectionModeNode = 0;
  std::wstring::wstring(
    (std::wstring *)&isAdditionalPdpContextProfileNode,
    L"http://www.microsoft.com/networking/WWAN/profile/v1");
  std::wstring::wstring((std::wstring *)&isDefaultNode, L"ConnectionMode");
  WcmCommon::Xml::Node::CreateChild(
    Ptr,
    &connectionModeNode,
    (const std::wstring *)&isDefaultNode,
    (const std::wstring *)&isAdditionalPdpContextProfileNode,
    &contextNode);
  std::wstring::_Tidy_deallocate((std::wstring *)&isDefaultNode);
  std::wstring::_Tidy_deallocate((std::wstring *)&isAdditionalPdpContextProfileNode);
  std::wstring::wstring(&Path, L"manual");
  WcmCommon::Xml::Node::SetText(connectionModeNode._Ptr, &Path);
  std::wstring::_Tidy_deallocate(&Path);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&SubscriberId->_Mypair._Myval2);
    WPP_SF_S(*(_QWORD *)(v8 + 16), 0xCu, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids, v7);
  }
  subscriberIdNode = 0;
  std::wstring::wstring((std::wstring *)&isTetheringProfileNode, L"http://www.microsoft.com/networking/WWAN/profile/v1");
  std::wstring::wstring(&Path, L"SubscriberID");
  WcmCommon::Xml::Node::CreateChild(
    Ptr,
    &subscriberIdNode,
    &Path,
    (const std::wstring *)&isTetheringProfileNode,
    &connectionModeNode);
  std::wstring::_Tidy_deallocate(&Path);
  std::wstring::_Tidy_deallocate((std::wstring *)&isTetheringProfileNode);
  WcmCommon::Xml::Node::SetText(subscriberIdNode._Ptr, SubscriberId);
  profileCreationTypeNode = 0;
  std::wstring::wstring(&Namespace, L"http://www.microsoft.com/networking/WWAN/profile/v1");
  std::wstring::wstring((std::wstring *)&isAdditionalPdpContextProfileNode, L"ProfileCreationType");
  WcmCommon::Xml::Node::CreateChild(
    Ptr,
    &profileCreationTypeNode,
    (const std::wstring *)&isAdditionalPdpContextProfileNode,
    &Namespace,
    &subscriberIdNode);
  std::wstring::_Tidy_deallocate((std::wstring *)&isAdditionalPdpContextProfileNode);
  std::wstring::_Tidy_deallocate(&Namespace);
  std::wstring::wstring(&Path, L"OperatorProvisioned");
  WcmCommon::Xml::Node::SetText(profileCreationTypeNode._Ptr, &Path);
  std::wstring::_Tidy_deallocate(&Path);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids);
  }
  isDefaultNode = 0;
  std::wstring::wstring((std::wstring *)&isTetheringProfileNode, L"http://www.microsoft.com/networking/WWAN/profile/v1");
  std::wstring::wstring(&Path, L"IsDefault");
  WcmCommon::Xml::Node::CreateChild(
    Ptr,
    &isDefaultNode,
    &Path,
    (const std::wstring *)&isTetheringProfileNode,
    &profileCreationTypeNode);
  std::wstring::_Tidy_deallocate(&Path);
  std::wstring::_Tidy_deallocate((std::wstring *)&isTetheringProfileNode);
  std::wstring::wstring(&Namespace, L"false");
  WcmCommon::Xml::Node::SetText(isDefaultNode._Ptr, &Namespace);
  std::wstring::_Tidy_deallocate(&Namespace);
  isAdditionalPdpContextProfileNode = 0;
  isTetheringProfileNode = 0;
  std::wstring::wstring(&Path, L"http://www.microsoft.com/networking/WWAN/profile/v3");
  std::wstring::wstring(&Namespace, L"IsAdditionalPdpContextProfile");
  WcmCommon::Xml::Node::CreateChild(Ptr, &isAdditionalPdpContextProfileNode, &Namespace, &Path, &isTetheringProfileNode);
  std::wstring::_Tidy_deallocate(&Namespace);
  std::wstring::_Tidy_deallocate(&Path);
  if ( isTetheringProfileNode._Rep )
    std::_Ref_count_base::_Decref(isTetheringProfileNode._Rep);
  std::wstring::wstring((std::wstring *)&isTetheringProfileNode, L"true");
  WcmCommon::Xml::Node::SetText(isAdditionalPdpContextProfileNode._Ptr, (const std::wstring *)&isTetheringProfileNode);
  std::wstring::_Tidy_deallocate((std::wstring *)&isTetheringProfileNode);
  if ( IsTethering )
  {
    isTetheringProfileNode = 0;
    Path._Mypair._Myval2._Bx = 0;
    std::wstring::wstring(&v19, L"http://www.microsoft.com/networking/WWAN/profile/v3");
    std::wstring::wstring(&Namespace, L"IsTetheringProfile");
    WcmCommon::Xml::Node::CreateChild(
      Ptr,
      &isTetheringProfileNode,
      &Namespace,
      &v19,
      (const std::shared_ptr<WcmCommon::Xml::Node> *)&Path);
    std::wstring::_Tidy_deallocate(&Namespace);
    std::wstring::_Tidy_deallocate(&v19);
    if ( *(_QWORD *)&Path._Mypair._Myval2._Bx._Alias[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&Path._Mypair._Myval2._Bx._Alias[8]);
    std::wstring::wstring(&Path, L"true");
    WcmCommon::Xml::Node::SetText(isTetheringProfileNode._Ptr, &Path);
    std::wstring::_Tidy_deallocate(&Path);
    if ( isTetheringProfileNode._Rep )
      std::_Ref_count_base::_Decref(isTetheringProfileNode._Rep);
  }
  if ( isAdditionalPdpContextProfileNode._Rep )
    std::_Ref_count_base::_Decref(isAdditionalPdpContextProfileNode._Rep);
  if ( isDefaultNode._Rep )
    std::_Ref_count_base::_Decref(isDefaultNode._Rep);
  if ( profileCreationTypeNode._Rep )
    std::_Ref_count_base::_Decref(profileCreationTypeNode._Rep);
  if ( subscriberIdNode._Rep )
    std::_Ref_count_base::_Decref(subscriberIdNode._Rep);
  if ( connectionModeNode._Rep )
    std::_Ref_count_base::_Decref(connectionModeNode._Rep);
  if ( contextNode._Rep )
    std::_Ref_count_base::_Decref(contextNode._Rep);
  if ( rootNode._Rep )
    std::_Ref_count_base::_Decref(rootNode._Rep);
}

```

## disassembly

```asm
0x18001d664  mov     [rsp-8+arg_10], rbx
0x18001d669  mov     [rsp-8+arg_18], rsi
0x18001d66e  push    rbp
0x18001d66f  push    rdi
0x18001d670  push    r12
0x18001d672  lea     rbp, [rsp-40h]
0x18001d677  sub     rsp, 140h
0x18001d67e  mov     sil, IsTethering
0x18001d681  mov     rdi, SubscriberId
0x18001d684  mov     rbx, ProfileDoc
0x18001d687  lea     r12, WPP_GLOBAL_Control; __annotation("TMF:",
0x18001d68e  mov     ProfileDoc, cs:WPP_GLOBAL_Control
0x18001d695  cmp     ProfileDoc, r12
0x18001d698  jz      short loc_18001D6B5
0x18001d69a  test    byte ptr [ProfileDoc+1Ch], 10h
0x18001d69e  jz      short loc_18001D6B5
0x18001d6a0  mov     edx, 0Ah; id
0x18001d6a5  lea     r8, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001d6ac  mov     ProfileDoc, [ProfileDoc+10h]; Logger
0x18001d6b0  call    WPP_SF_
0x18001d6b5  xorps   xmm0, xmm0
0x18001d6b8  movups  xmmword ptr [rbp+50h+rootNode._Ptr], xmm0
0x18001d6bc  lea     SubscriberId, [rbp+50h+rootNode]; result
0x18001d6c0  mov     ProfileDoc, [rbx]; this
0x18001d6c3  call    ?GetRoot@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@XZ; WcmCommon::Xml::Document::GetRoot(void)
0x18001d6c8  nop
0x18001d6c9  movups  xmmword ptr [rbp+50h+contextNode._Ptr], xmm0
0x18001d6cd  mov     rbx, [rbp+50h+rootNode._Ptr]
0x18001d6d1  lea     SubscriberId, aDefaultContext_0; "./default:Context"
0x18001d6d8  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d6dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d6e2  nop
0x18001d6e3  lea     r8, [rsp+150h+Path]; Path
0x18001d6e8  lea     SubscriberId, [rbp+50h+contextNode]; result
0x18001d6ec  mov     ProfileDoc, rbx; this
0x18001d6ef  call    ?SelectSingle@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Node::SelectSingle(std::wstring const &)
0x18001d6f4  nop
0x18001d6f5  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d6fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d6ff  mov     ProfileDoc, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001d706  cmp     ProfileDoc, r12
0x18001d709  jz      short loc_18001D726
0x18001d70b  test    byte ptr [ProfileDoc+1Ch], 10h
0x18001d70f  jz      short loc_18001D726
0x18001d711  mov     edx, 0Bh; id
0x18001d716  lea     r8, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001d71d  mov     ProfileDoc, [ProfileDoc+10h]; Logger
0x18001d721  call    WPP_SF_
0x18001d726  xorps   xmm0, xmm0
0x18001d729  movups  xmmword ptr [rbp+50h+connectionModeNode._Ptr], xmm0
0x18001d72d  lea     SubscriberId, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x18001d734  lea     ProfileDoc, [rbp+50h+isAdditionalPdpContextProfileNode]; this
0x18001d738  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d73d  nop
0x18001d73e  lea     SubscriberId, aConnectionmode; "ConnectionMode"
0x18001d745  lea     ProfileDoc, [rbp+50h+isDefaultNode]; this
0x18001d749  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d74e  nop
0x18001d74f  lea     rax, [rbp+50h+contextNode]
0x18001d753  mov     [rsp+150h+insertBefore], rax; insertBefore
0x18001d758  lea     r9, [rbp+50h+isAdditionalPdpContextProfileNode]; Namespace
0x18001d75c  lea     r8, [rbp+50h+isDefaultNode]; Name
0x18001d760  lea     SubscriberId, [rbp+50h+connectionModeNode]; result
0x18001d764  mov     ProfileDoc, rbx; this
0x18001d767  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001d76c  nop
0x18001d76d  lea     ProfileDoc, [rbp+50h+isDefaultNode]; this
0x18001d771  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d776  nop
0x18001d777  lea     ProfileDoc, [rbp+50h+isAdditionalPdpContextProfileNode]; this
0x18001d77b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d780  lea     SubscriberId, aManual; "manual"
0x18001d787  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d78c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d791  nop
0x18001d792  lea     SubscriberId, [rsp+150h+Path]; Text
0x18001d797  mov     ProfileDoc, [rbp+50h+connectionModeNode._Ptr]; this
0x18001d79b  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x18001d7a0  nop
0x18001d7a1  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d7a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d7ab  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001d7b2  cmp     r10, r12
0x18001d7b5  jz      short loc_18001D7DE
0x18001d7b7  test    byte ptr [r10+1Ch], 10h
0x18001d7bc  jz      short loc_18001D7DE
0x18001d7be  mov     ProfileDoc, rdi; this
0x18001d7c1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d7c6  mov     edx, 0Ch; id
0x18001d7cb  mov     r9, rax; _a1
0x18001d7ce  lea     r8, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001d7d5  mov     ProfileDoc, [r10+10h]; Logger
0x18001d7d9  call    WPP_SF_S
0x18001d7de  xorps   xmm0, xmm0
0x18001d7e1  movups  xmmword ptr [rbp+50h+subscriberIdNode._Ptr], xmm0
0x18001d7e5  lea     SubscriberId, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x18001d7ec  lea     ProfileDoc, [rsp+150h+isTetheringProfileNode]; this
0x18001d7f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d7f6  nop
0x18001d7f7  lea     SubscriberId, aSubscriberid; "SubscriberID"
0x18001d7fe  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d803  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d808  nop
0x18001d809  lea     rax, [rbp+50h+connectionModeNode]
0x18001d80d  mov     [rsp+150h+insertBefore], rax; insertBefore
0x18001d812  lea     r9, [rsp+150h+isTetheringProfileNode]; Namespace
0x18001d817  lea     r8, [rsp+150h+Path]; Name
0x18001d81c  lea     SubscriberId, [rbp+50h+subscriberIdNode]; result
0x18001d820  mov     ProfileDoc, rbx; this
0x18001d823  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001d828  nop
0x18001d829  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d82e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d833  nop
0x18001d834  lea     ProfileDoc, [rsp+150h+isTetheringProfileNode]; this
0x18001d839  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d83e  mov     SubscriberId, rdi; Text
0x18001d841  mov     ProfileDoc, [rbp+50h+subscriberIdNode._Ptr]; this
0x18001d845  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x18001d84a  xorps   xmm0, xmm0
0x18001d84d  movups  xmmword ptr [rbp+50h+profileCreationTypeNode._Ptr], xmm0
0x18001d851  lea     SubscriberId, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x18001d858  lea     ProfileDoc, [rsp+150h+Namespace]; this
0x18001d85d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d862  nop
0x18001d863  lea     SubscriberId, aProfilecreatio; "ProfileCreationType"
0x18001d86a  lea     ProfileDoc, [rbp+50h+isAdditionalPdpContextProfileNode]; this
0x18001d86e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d873  nop
0x18001d874  lea     rax, [rbp+50h+subscriberIdNode]
0x18001d878  mov     [rsp+150h+insertBefore], rax; insertBefore
0x18001d87d  lea     r9, [rsp+150h+Namespace]; Namespace
0x18001d882  lea     r8, [rbp+50h+isAdditionalPdpContextProfileNode]; Name
0x18001d886  lea     SubscriberId, [rbp+50h+profileCreationTypeNode]; result
0x18001d88a  mov     ProfileDoc, rbx; this
0x18001d88d  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001d892  nop
0x18001d893  lea     ProfileDoc, [rbp+50h+isAdditionalPdpContextProfileNode]; this
0x18001d897  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d89c  nop
0x18001d89d  lea     ProfileDoc, [rsp+150h+Namespace]; this
0x18001d8a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d8a7  lea     SubscriberId, aOperatorprovis; "OperatorProvisioned"
0x18001d8ae  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d8b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d8b8  nop
0x18001d8b9  lea     SubscriberId, [rsp+150h+Path]; Text
0x18001d8be  mov     ProfileDoc, [rbp+50h+profileCreationTypeNode._Ptr]; this
0x18001d8c2  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x18001d8c7  nop
0x18001d8c8  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d8cd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d8d2  mov     ProfileDoc, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001d8d9  cmp     ProfileDoc, r12
0x18001d8dc  jz      short loc_18001D8F9
0x18001d8de  test    byte ptr [ProfileDoc+1Ch], 10h
0x18001d8e2  jz      short loc_18001D8F9
0x18001d8e4  mov     edx, 0Dh; id
0x18001d8e9  lea     r8, WPP_7c447b71f22933875d49a435d71bb2ce_Traceguids; TraceGuid
0x18001d8f0  mov     ProfileDoc, [ProfileDoc+10h]; Logger
0x18001d8f4  call    WPP_SF_
0x18001d8f9  xorps   xmm0, xmm0
0x18001d8fc  movups  xmmword ptr [rbp+50h+isDefaultNode._Ptr], xmm0
0x18001d900  lea     SubscriberId, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x18001d907  lea     ProfileDoc, [rsp+150h+isTetheringProfileNode]; this
0x18001d90c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d911  nop
0x18001d912  lea     SubscriberId, aIsdefault; "IsDefault"
0x18001d919  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d91e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d923  nop
0x18001d924  lea     rax, [rbp+50h+profileCreationTypeNode]
0x18001d928  mov     [rsp+150h+insertBefore], rax; insertBefore
0x18001d92d  lea     r9, [rsp+150h+isTetheringProfileNode]; Namespace
0x18001d932  lea     r8, [rsp+150h+Path]; Name
0x18001d937  lea     SubscriberId, [rbp+50h+isDefaultNode]; result
0x18001d93b  mov     ProfileDoc, rbx; this
0x18001d93e  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001d943  nop
0x18001d944  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d949  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d94e  nop
0x18001d94f  lea     ProfileDoc, [rsp+150h+isTetheringProfileNode]; this
0x18001d954  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d959  lea     SubscriberId, aFalse; "false"
0x18001d960  lea     ProfileDoc, [rsp+150h+Namespace]; this
0x18001d965  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d96a  nop
0x18001d96b  lea     SubscriberId, [rsp+150h+Namespace]; Text
0x18001d970  mov     ProfileDoc, [rbp+50h+isDefaultNode._Ptr]; this
0x18001d974  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x18001d979  nop
0x18001d97a  lea     ProfileDoc, [rsp+150h+Namespace]; this
0x18001d97f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d984  xorps   xmm0, xmm0
0x18001d987  movups  xmmword ptr [rbp+50h+isAdditionalPdpContextProfileNode._Ptr], xmm0
0x18001d98b  xorps   xmm1, xmm1
0x18001d98e  movdqu  xmmword ptr [rsp+150h+isTetheringProfileNode._Ptr], xmm1
0x18001d994  lea     SubscriberId, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/WWA"...
0x18001d99b  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d9a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d9a5  nop
0x18001d9a6  lea     SubscriberId, aIsadditionalpd; "IsAdditionalPdpContextProfile"
0x18001d9ad  lea     ProfileDoc, [rsp+150h+Namespace]; this
0x18001d9b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d9b7  nop
0x18001d9b8  lea     rax, [rsp+150h+isTetheringProfileNode]
0x18001d9bd  mov     [rsp+150h+insertBefore], rax; insertBefore
0x18001d9c2  lea     r9, [rsp+150h+Path]; Namespace
0x18001d9c7  lea     r8, [rsp+150h+Namespace]; Name
0x18001d9cc  lea     SubscriberId, [rbp+50h+isAdditionalPdpContextProfileNode]; result
0x18001d9d0  mov     ProfileDoc, rbx; this
0x18001d9d3  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001d9d8  nop
0x18001d9d9  lea     ProfileDoc, [rsp+150h+Namespace]; this
0x18001d9de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d9e3  nop
0x18001d9e4  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001d9e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d9ee  nop
0x18001d9ef  mov     ProfileDoc, [rsp+150h+isTetheringProfileNode._Rep]; this
0x18001d9f4  test    ProfileDoc, ProfileDoc
0x18001d9f7  jz      short loc_18001D9FE
0x18001d9f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001d9fe  lea     SubscriberId, aTrue; "true"
0x18001da05  lea     ProfileDoc, [rsp+150h+isTetheringProfileNode]; this
0x18001da0a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001da0f  nop
0x18001da10  lea     SubscriberId, [rsp+150h+isTetheringProfileNode]; Text
0x18001da15  mov     ProfileDoc, [rbp+50h+isAdditionalPdpContextProfileNode._Ptr]; this
0x18001da19  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x18001da1e  nop
0x18001da1f  lea     ProfileDoc, [rsp+150h+isTetheringProfileNode]; this
0x18001da24  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001da29  test    sil, sil
0x18001da2c  jz      loc_18001DAE8
0x18001da32  xorps   xmm0, xmm0
0x18001da35  movups  xmmword ptr [rsp+150h+isTetheringProfileNode._Ptr], xmm0
0x18001da3a  xorps   xmm1, xmm1
0x18001da3d  movdqu  xmmword ptr [rsp+150h+Path._Mypair._Myval2._Bx], xmm1
0x18001da43  lea     SubscriberId, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/WWA"...
0x18001da4a  lea     ProfileDoc, [rbp+50h+var_30]; this
0x18001da4e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001da53  nop
0x18001da54  lea     SubscriberId, aIstetheringpro; "IsTetheringProfile"
0x18001da5b  lea     ProfileDoc, [rsp+150h+Namespace]; this
0x18001da60  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001da65  nop
0x18001da66  lea     rax, [rsp+150h+Path]
0x18001da6b  mov     [rsp+150h+insertBefore], rax; insertBefore
0x18001da70  lea     r9, [rbp+50h+var_30]; Namespace
0x18001da74  lea     r8, [rsp+150h+Namespace]; Name
0x18001da79  lea     SubscriberId, [rsp+150h+isTetheringProfileNode]; result
0x18001da7e  mov     ProfileDoc, rbx; this
0x18001da81  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001da86  nop
0x18001da87  lea     ProfileDoc, [rsp+150h+Namespace]; this
0x18001da8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001da91  nop
0x18001da92  lea     ProfileDoc, [rbp+50h+var_30]; this
0x18001da96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001da9b  nop
0x18001da9c  mov     ProfileDoc, qword ptr [rsp+150h+Path._Mypair._Myval2._Bx+8]; this
0x18001daa1  test    ProfileDoc, ProfileDoc
0x18001daa4  jz      short loc_18001DAAB
0x18001daa6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001daab  lea     SubscriberId, aTrue; "true"
0x18001dab2  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001dab7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001dabc  nop
0x18001dabd  lea     SubscriberId, [rsp+150h+Path]; Text
0x18001dac2  mov     ProfileDoc, [rsp+150h+isTetheringProfileNode._Ptr]; this
0x18001dac7  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x18001dacc  nop
0x18001dacd  lea     ProfileDoc, [rsp+150h+Path]; this
0x18001dad2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dad7  nop
0x18001dad8  mov     ProfileDoc, [rsp+150h+isTetheringProfileNode._Rep]; this
0x18001dadd  test    ProfileDoc, ProfileDoc
0x18001dae0  jz      short loc_18001DAE8
0x18001dae2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001dae7  nop
0x18001dae8  mov     ProfileDoc, [rbp+50h+isAdditionalPdpContextProfileNode._Rep]; this
0x18001daec  test    ProfileDoc, ProfileDoc
0x18001daef  jz      short loc_18001DAF7
0x18001daf1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001daf6  nop
0x18001daf7  mov     ProfileDoc, [rbp+50h+isDefaultNode._Rep]; this
0x18001dafb  test    ProfileDoc, ProfileDoc
0x18001dafe  jz      short loc_18001DB06
0x18001db00  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001db05  nop
0x18001db06  mov     ProfileDoc, [rbp+50h+profileCreationTypeNode._Rep]; this
0x18001db0a  test    ProfileDoc, ProfileDoc
0x18001db0d  jz      short loc_18001DB15
0x18001db0f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001db14  nop
0x18001db15  mov     ProfileDoc, [rbp+50h+subscriberIdNode._Rep]; this
0x18001db19  test    ProfileDoc, ProfileDoc
0x18001db1c  jz      short loc_18001DB24
  ... truncated ...
```

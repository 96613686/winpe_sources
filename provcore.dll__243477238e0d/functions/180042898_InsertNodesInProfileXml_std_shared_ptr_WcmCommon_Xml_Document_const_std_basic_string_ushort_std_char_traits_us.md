# InsertNodesInProfileXml(std::shared_ptr<WcmCommon::Xml::Document> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180042898`
- end: `0x180042f3c`
- name: `?InsertNodesInProfileXml@@YAXAEBV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@1_N1@Z`
- size: `1700`
- prototype: `void __fastcall(const std::shared_ptr<WcmCommon::Xml::Document> *profileDoc, const std::wstring *IconPath, const std::wstring *DisplayProviderName, bool IsDefault, const std::wstring *SubscriberId)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043660`

## callees

- `0x180002790`
- `0x18000af94`
- `0x18000fa6c`
- `0x180011844`
- `0x180011c10`
- `0x180011cfc`
- `0x180012748`
- `0x1800127cc`
- `0x180013fe4`
- `0x18002fd88`
- `0x1800416d4`
- `0x1800418ac`
- `0x180042898`
- `0x180048558`
- `0x180048c94`
- `0x180048f04`
- `0x180049e4c`

## string_xrefs

- `0x1800429b4`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180042c9b`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180042bb1`: `ICONFilePath`
- `0x180042d34`: `http://www.microsoft.com/networking/WWAN/profile/v2`
- `0x180042e24`: `http://www.microsoft.com/networking/WWAN/profile/v2`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
void __fastcall InsertNodesInProfileXml(
        const std::shared_ptr<WcmCommon::Xml::Document> *profileDoc,
        const std::wstring *IconPath,
        const std::wstring *DisplayProviderName,
        bool IsDefault,
        const std::wstring *SubscriberId)
{
  WcmCommon::Xml::Node *Ptr; // rsi
  const std::shared_ptr<WcmCommon::Xml::Node> *v10; // rcx
  std::shared_ptr<WcmCommon::Xml::Node> *Myfirst; // rbx
  std::shared_ptr<WcmCommon::Xml::Node> *Mylast; // rdi
  const wchar_t *v13; // rax
  __int64 v14; // r10
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rax
  __int64 v17; // r10
  const wchar_t *v18; // rax
  __int64 v19; // r10
  std::_Ref_count_base *Rep; // rcx
  std::shared_ptr<WcmCommon::Xml::Node> *v21; // rbx
  std::shared_ptr<WcmCommon::Xml::Node> *v22; // rdi
  const wchar_t *v23; // rax
  __int64 v24; // r10
  std::shared_ptr<WcmCommon::Xml::Node> displayProviderNameNode; // [rsp+30h] [rbp-D0h] BYREF
  std::wstring Name; // [rsp+50h] [rbp-B0h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> insertBeforeNode; // [rsp+70h] [rbp-90h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> connectionModeNode; // [rsp+80h] [rbp-80h] BYREF
  std::wstring Namespace; // [rsp+A0h] [rbp-60h] BYREF
  std::wstring v30; // [rsp+C0h] [rbp-40h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> profileCreationTypeNode; // [rsp+E0h] [rbp-20h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> subscriberIdNode; // [rsp+F0h] [rbp-10h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> isDefaultNode; // [rsp+100h] [rbp+0h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> rootNode; // [rsp+120h] [rbp+20h] BYREF
  std::vector<std::shared_ptr<WcmCommon::Xml::Node>> nodeList; // [rsp+130h] [rbp+30h] BYREF
  std::wstring Text; // [rsp+148h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids);
  }
  rootNode = 0;
  WcmCommon::Xml::Document::GetRoot(profileDoc->_Ptr, &rootNode);
  memset(&nodeList, 0, sizeof(nodeList));
  Ptr = rootNode._Ptr;
  WcmCommon::Xml::Node::GetChildren(rootNode._Ptr, &nodeList);
  insertBeforeNode = 0;
  Myfirst = nodeList._Mypair._Myval2._Myfirst;
  Mylast = nodeList._Mypair._Myval2._Mylast;
  if ( nodeList._Mypair._Myval2._Myfirst != nodeList._Mypair._Myval2._Mylast )
  {
    do
    {
      if ( InsertNodesInProfileXml_::_2_::_lambda_1_::operator()(v10) )
        break;
      ++Myfirst;
    }
    while ( Myfirst != Mylast );
    if ( Myfirst != nodeList._Mypair._Myval2._Mylast )
      std::shared_ptr<WcmCommon::Xml::Node>::operator=(&insertBeforeNode, Myfirst);
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&SubscriberId->_Mypair._Myval2);
    WPP_SF_S(*(_QWORD *)(v14 + 16), 0x1Au, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids, v13);
  }
  subscriberIdNode = 0;
  std::wstring::wstring((std::wstring *)&connectionModeNode, L"http://www.microsoft.com/networking/WWAN/profile/v1");
  std::wstring::wstring(&Name, L"SubscriberID");
  WcmCommon::Xml::Node::CreateChild(
    Ptr,
    &subscriberIdNode,
    &Name,
    (const std::wstring *)&connectionModeNode,
    &insertBeforeNode);
  std::wstring::_Tidy_deallocate(&Name);
  std::wstring::_Tidy_deallocate((std::wstring *)&connectionModeNode);
  WcmCommon::Xml::Node::SetText(subscriberIdNode._Ptr, SubscriberId);
  profileCreationTypeNode = 0;
  std::wstring::wstring((std::wstring *)&isDefaultNode, L"http://www.microsoft.com/networking/WWAN/profile/v1");
  std::wstring::wstring((std::wstring *)&displayProviderNameNode, L"ProfileCreationType");
  WcmCommon::Xml::Node::CreateChild(
    Ptr,
    &profileCreationTypeNode,
    (const std::wstring *)&displayProviderNameNode,
    (const std::wstring *)&isDefaultNode,
    &subscriberIdNode);
  std::wstring::_Tidy_deallocate((std::wstring *)&displayProviderNameNode);
  std::wstring::_Tidy_deallocate((std::wstring *)&isDefaultNode);
  std::wstring::wstring(&Name, L"OperatorProvisioned");
  WcmCommon::Xml::Node::SetText(profileCreationTypeNode._Ptr, &Name);
  std::wstring::_Tidy_deallocate(&Name);
  v15 = L"true";
  if ( !IsDefault )
    v15 = L"false";
  std::wstring::wstring(&Text, v15);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Text._Mypair._Myval2);
    WPP_SF_S(*(_QWORD *)(v17 + 16), 0x1Bu, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids, v16);
  }
  isDefaultNode = 0;
  std::wstring::wstring(&Namespace, L"http://www.microsoft.com/networking/WWAN/profile/v1");
  std::wstring::wstring(&Name, L"IsDefault");
  WcmCommon::Xml::Node::CreateChild(Ptr, &isDefaultNode, &Name, &Namespace, &profileCreationTypeNode);
  std::wstring::_Tidy_deallocate(&Name);
  std::wstring::_Tidy_deallocate(&Namespace);
  WcmCommon::Xml::Node::SetText(isDefaultNode._Ptr, &Text);
  if ( IconPath->_Mypair._Myval2._Mysize )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&IconPath->_Mypair._Myval2);
      WPP_SF_S(*(_QWORD *)(v19 + 16), 0x1Cu, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids, v18);
    }
    displayProviderNameNode = 0;
    std::wstring::wstring(&v30, L"http://www.microsoft.com/networking/WWAN/profile/v1");
    std::wstring::wstring((std::wstring *)&connectionModeNode, L"ICONFilePath");
    WcmCommon::Xml::Node::CreateChild(
      Ptr,
      &displayProviderNameNode,
      (const std::wstring *)&connectionModeNode,
      &v30,
      &isDefaultNode);
    std::wstring::_Tidy_deallocate((std::wstring *)&connectionModeNode);
    std::wstring::_Tidy_deallocate(&v30);
    WcmCommon::Xml::Node::SetText(displayProviderNameNode._Ptr, IconPath);
    if ( displayProviderNameNode._Rep )
      std::_Ref_count_base::_Decref(displayProviderNameNode._Rep);
  }
  connectionModeNode = 0;
  std::shared_ptr<WcmCommon::Xml::Node>::operator=(
    (std::shared_ptr<Notification::Configuration::Node> *)&insertBeforeNode,
    (std::shared_ptr<Notification::Configuration::Node> *)&connectionModeNode);
  Rep = connectionModeNode._Rep;
  if ( connectionModeNode._Rep )
    std::_Ref_count_base::_Decref(connectionModeNode._Rep);
  v21 = nodeList._Mypair._Myval2._Myfirst;
  v22 = nodeList._Mypair._Myval2._Mylast;
  if ( nodeList._Mypair._Myval2._Myfirst != nodeList._Mypair._Myval2._Mylast )
  {
    do
    {
      if ( InsertNodesInProfileXml_::_2_::_lambda_2_::operator()((const std::shared_ptr<WcmCommon::Xml::Node> *)Rep) )
        break;
      ++v21;
    }
    while ( v21 != v22 );
    if ( v21 != nodeList._Mypair._Myval2._Mylast )
      std::shared_ptr<WcmCommon::Xml::Node>::operator=(&insertBeforeNode, v21);
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Du, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids);
  }
  connectionModeNode = 0;
  std::wstring::wstring(
    (std::wstring *)&displayProviderNameNode,
    L"http://www.microsoft.com/networking/WWAN/profile/v1");
  std::wstring::wstring(&v30, L"ConnectionMode");
  WcmCommon::Xml::Node::CreateChild(
    Ptr,
    &connectionModeNode,
    &v30,
    (const std::wstring *)&displayProviderNameNode,
    &insertBeforeNode);
  std::wstring::_Tidy_deallocate(&v30);
  std::wstring::_Tidy_deallocate((std::wstring *)&displayProviderNameNode);
  std::wstring::wstring(&Namespace, L"auto");
  WcmCommon::Xml::Node::SetText(connectionModeNode._Ptr, &Namespace);
  std::wstring::_Tidy_deallocate(&Namespace);
  if ( !IsDefault )
  {
    displayProviderNameNode = 0;
    Name._Mypair._Myval2._Bx = 0;
    std::wstring::wstring(&Namespace, L"http://www.microsoft.com/networking/WWAN/profile/v2");
    std::wstring::wstring(&v30, L"IsPurchaseProfile");
    WcmCommon::Xml::Node::CreateChild(
      Ptr,
      &displayProviderNameNode,
      &v30,
      &Namespace,
      (const std::shared_ptr<WcmCommon::Xml::Node> *)&Name);
    std::wstring::_Tidy_deallocate(&v30);
    std::wstring::_Tidy_deallocate(&Namespace);
    if ( *(_QWORD *)&Name._Mypair._Myval2._Bx._Alias[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&Name._Mypair._Myval2._Bx._Alias[8]);
    std::wstring::wstring(&Name, L"true");
    WcmCommon::Xml::Node::SetText(displayProviderNameNode._Ptr, &Name);
    std::wstring::_Tidy_deallocate(&Name);
    if ( displayProviderNameNode._Rep )
      std::_Ref_count_base::_Decref(displayProviderNameNode._Rep);
  }
  if ( DisplayProviderName->_Mypair._Myval2._Mysize )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&DisplayProviderName->_Mypair._Myval2);
      WPP_SF_S(*(_QWORD *)(v24 + 16), 0x1Eu, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids, v23);
    }
    displayProviderNameNode = 0;
    Name._Mypair._Myval2._Bx = 0;
    std::wstring::wstring(&Namespace, L"http://www.microsoft.com/networking/WWAN/profile/v2");
    std::wstring::wstring(&v30, L"DisplayProviderName");
    WcmCommon::Xml::Node::CreateChild(
      Ptr,
      &displayProviderNameNode,
      &v30,
      &Namespace,
      (const std::shared_ptr<WcmCommon::Xml::Node> *)&Name);
    std::wstring::_Tidy_deallocate(&v30);
    std::wstring::_Tidy_deallocate(&Namespace);
    if ( *(_QWORD *)&Name._Mypair._Myval2._Bx._Alias[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&Name._Mypair._Myval2._Bx._Alias[8]);
    WcmCommon::Xml::Node::SetText(displayProviderNameNode._Ptr, DisplayProviderName);
    if ( displayProviderNameNode._Rep )
      std::_Ref_count_base::_Decref(displayProviderNameNode._Rep);
  }
  if ( connectionModeNode._Rep )
    std::_Ref_count_base::_Decref(connectionModeNode._Rep);
  if ( isDefaultNode._Rep )
    std::_Ref_count_base::_Decref(isDefaultNode._Rep);
  std::wstring::_Tidy_deallocate(&Text);
  if ( profileCreationTypeNode._Rep )
    std::_Ref_count_base::_Decref(profileCreationTypeNode._Rep);
  if ( subscriberIdNode._Rep )
    std::_Ref_count_base::_Decref(subscriberIdNode._Rep);
  if ( insertBeforeNode._Rep )
    std::_Ref_count_base::_Decref(insertBeforeNode._Rep);
  std::vector<std::shared_ptr<Handler::Interface>>::~vector<std::shared_ptr<Handler::Interface>>((std::vector<std::shared_ptr<Notification::Configuration::Node>> *)&nodeList);
  if ( rootNode._Rep )
    std::_Ref_count_base::_Decref(rootNode._Rep);
}

```

## disassembly

```asm
0x180042898  mov     [rsp-8+arg_18], rbx
0x18004289d  push    rbp
0x18004289e  push    rsi
0x18004289f  push    rdi
0x1800428a0  push    r12
0x1800428a2  push    r13
0x1800428a4  push    r14
0x1800428a6  push    r15
0x1800428a8  lea     rbp, [rsp-70h]
0x1800428ad  sub     rsp, 170h
0x1800428b4  mov     rax, cs:__security_cookie
0x1800428bb  xor     rax, rsp
0x1800428be  mov     [rbp+0A0h+var_38], rax
0x1800428c2  mov     r13b, IsDefault
0x1800428c5  mov     r14, DisplayProviderName
0x1800428c8  mov     r15, IconPath
0x1800428cb  mov     rbx, profileDoc
0x1800428ce  mov     r12, [rbp+0A0h+arg_20]
0x1800428d5  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800428dc  mov     profileDoc, cs:WPP_GLOBAL_Control
0x1800428e3  cmp     profileDoc, rax
0x1800428e6  jz      short loc_180042903
0x1800428e8  test    byte ptr [profileDoc+1Ch], 10h
0x1800428ec  jz      short loc_180042903
0x1800428ee  mov     edx, 19h; id
0x1800428f3  lea     DisplayProviderName, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x1800428fa  mov     profileDoc, [profileDoc+10h]; Logger
0x1800428fe  call    WPP_SF_
0x180042903  xorps   xmm0, xmm0
0x180042906  movups  xmmword ptr [rbp+0A0h+rootNode._Ptr], xmm0
0x18004290a  lea     IconPath, [rbp+0A0h+rootNode]; result
0x18004290e  mov     profileDoc, [rbx]; this
0x180042911  call    ?GetRoot@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@XZ; WcmCommon::Xml::Document::GetRoot(void)
0x180042916  nop
0x180042917  xor     eax, eax
0x180042919  movups  xmmword ptr [rbp+0A0h+nodeList._Mypair._Myval2._Myfirst], xmm0
0x18004291d  mov     [rbp+0A0h+nodeList._Mypair._Myval2._Myend], rax
0x180042921  lea     IconPath, [rbp+0A0h+nodeList]; result
0x180042925  mov     rsi, [rbp+0A0h+rootNode._Ptr]
0x180042929  mov     profileDoc, rsi; this
0x18004292c  call    ?GetChildren@Node@Xml@WcmCommon@@QEBA?AV?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@XZ; WcmCommon::Xml::Node::GetChildren(void)
0x180042931  nop
0x180042932  xorps   xmm1, xmm1
0x180042935  movdqu  xmmword ptr [rsp+1A0h+insertBeforeNode._Ptr], xmm1
0x18004293b  mov     rbx, [rbp+0A0h+nodeList._Mypair._Myval2._Myfirst]
0x18004293f  mov     rdi, [rbp+0A0h+nodeList._Mypair._Myval2._Mylast]
0x180042943  cmp     rbx, rdi
0x180042946  jz      short loc_180042973
0x180042948  mov     IconPath, rbx
0x18004294b  call    _InsertNodesInProfileXml____2____lambda_1___operator__
0x180042950  test    al, al
0x180042952  jnz     short loc_18004295D
0x180042954  add     rbx, 10h
0x180042958  cmp     rbx, rdi
0x18004295b  jnz     short loc_180042948
0x18004295d  mov     rdi, [rbp+0A0h+nodeList._Mypair._Myval2._Mylast]
0x180042961  cmp     rbx, rdi
0x180042964  jz      short loc_180042973
0x180042966  mov     IconPath, rbx; _Right
0x180042969  lea     profileDoc, [rsp+1A0h+insertBeforeNode]; this
0x18004296e  call    ??4?$shared_ptr@VNode@Xml@WcmCommon@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WcmCommon::Xml::Node>::operator=(std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180042973  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18004297a  lea     rax, WPP_GLOBAL_Control
0x180042981  cmp     r10, rax
0x180042984  jz      short loc_1800429AD
0x180042986  test    byte ptr [r10+1Ch], 10h
0x18004298b  jz      short loc_1800429AD
0x18004298d  mov     profileDoc, r12; this
0x180042990  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042995  mov     edx, 1Ah; id
0x18004299a  mov     r9, rax; _a1
0x18004299d  lea     DisplayProviderName, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x1800429a4  mov     profileDoc, [r10+10h]; Logger
0x1800429a8  call    WPP_SF_S
0x1800429ad  xorps   xmm0, xmm0
0x1800429b0  movups  xmmword ptr [rbp+0A0h+subscriberIdNode._Ptr], xmm0
0x1800429b4  lea     rbx, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x1800429bb  mov     IconPath, rbx; _Ptr
0x1800429be  lea     profileDoc, [rbp+0A0h+connectionModeNode]; this
0x1800429c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800429c7  nop
0x1800429c8  lea     IconPath, aSubscriberid; "SubscriberID"
0x1800429cf  lea     profileDoc, [rsp+1A0h+Name]; this
0x1800429d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800429d9  nop
0x1800429da  lea     rax, [rsp+1A0h+insertBeforeNode]
0x1800429df  mov     [rsp+1A0h+insertBefore], rax; insertBefore
0x1800429e4  lea     r9, [rbp+0A0h+connectionModeNode]; Namespace
0x1800429e8  lea     DisplayProviderName, [rsp+1A0h+Name]; Name
0x1800429ed  lea     IconPath, [rbp+0A0h+subscriberIdNode]; result
0x1800429f1  mov     profileDoc, rsi; this
0x1800429f4  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x1800429f9  nop
0x1800429fa  lea     profileDoc, [rsp+1A0h+Name]; this
0x1800429ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042a04  nop
0x180042a05  lea     profileDoc, [rbp+0A0h+connectionModeNode]; this
0x180042a09  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042a0e  mov     IconPath, r12; Text
0x180042a11  mov     profileDoc, [rbp+0A0h+subscriberIdNode._Ptr]; this
0x180042a15  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x180042a1a  xorps   xmm0, xmm0
0x180042a1d  movups  xmmword ptr [rbp+0A0h+profileCreationTypeNode._Ptr], xmm0
0x180042a21  mov     IconPath, rbx; _Ptr
0x180042a24  lea     profileDoc, [rbp+0A0h+isDefaultNode]; this
0x180042a28  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042a2d  nop
0x180042a2e  lea     IconPath, aProfilecreatio; "ProfileCreationType"
0x180042a35  lea     profileDoc, [rsp+1A0h+displayProviderNameNode]; this
0x180042a3a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042a3f  nop
0x180042a40  lea     rax, [rbp+0A0h+subscriberIdNode]
0x180042a44  mov     [rsp+1A0h+insertBefore], rax; insertBefore
0x180042a49  lea     r9, [rbp+0A0h+isDefaultNode]; Namespace
0x180042a4d  lea     DisplayProviderName, [rsp+1A0h+displayProviderNameNode]; Name
0x180042a52  lea     IconPath, [rbp+0A0h+profileCreationTypeNode]; result
0x180042a56  mov     profileDoc, rsi; this
0x180042a59  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180042a5e  nop
0x180042a5f  lea     profileDoc, [rsp+1A0h+displayProviderNameNode]; this
0x180042a64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042a69  nop
0x180042a6a  lea     profileDoc, [rbp+0A0h+isDefaultNode]; this
0x180042a6e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042a73  lea     IconPath, aOperatorprovis; "OperatorProvisioned"
0x180042a7a  lea     profileDoc, [rsp+1A0h+Name]; this
0x180042a7f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042a84  nop
0x180042a85  lea     IconPath, [rsp+1A0h+Name]; Text
0x180042a8a  mov     profileDoc, [rbp+0A0h+profileCreationTypeNode._Ptr]; this
0x180042a8e  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x180042a93  nop
0x180042a94  lea     profileDoc, [rsp+1A0h+Name]; this
0x180042a99  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042a9e  lea     rax, aFalse; "false"
0x180042aa5  lea     IconPath, aTrue; "true"
0x180042aac  test    r13b, r13b
0x180042aaf  cmovz   IconPath, rax; _Ptr
0x180042ab3  lea     profileDoc, [rbp+0A0h+Text]; this
0x180042ab7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042abc  nop
0x180042abd  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180042ac4  lea     r12, WPP_GLOBAL_Control
0x180042acb  cmp     r10, r12
0x180042ace  jz      short loc_180042AF8
0x180042ad0  test    byte ptr [r10+1Ch], 10h
0x180042ad5  jz      short loc_180042AF8
0x180042ad7  lea     profileDoc, [rbp+0A0h+Text]; this
0x180042adb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042ae0  mov     r9, rax; _a1
0x180042ae3  mov     edx, 1Bh; id
0x180042ae8  lea     DisplayProviderName, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180042aef  mov     profileDoc, [r10+10h]; Logger
0x180042af3  call    WPP_SF_S
0x180042af8  xorps   xmm0, xmm0
0x180042afb  movups  xmmword ptr [rbp+0A0h+isDefaultNode._Ptr], xmm0
0x180042aff  mov     IconPath, rbx; _Ptr
0x180042b02  lea     profileDoc, [rbp+0A0h+Namespace]; this
0x180042b06  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042b0b  nop
0x180042b0c  lea     IconPath, aIsdefault; "IsDefault"
0x180042b13  lea     profileDoc, [rsp+1A0h+Name]; this
0x180042b18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042b1d  nop
0x180042b1e  lea     rax, [rbp+0A0h+profileCreationTypeNode]
0x180042b22  mov     [rsp+1A0h+insertBefore], rax; insertBefore
0x180042b27  lea     r9, [rbp+0A0h+Namespace]; Namespace
0x180042b2b  lea     DisplayProviderName, [rsp+1A0h+Name]; Name
0x180042b30  lea     IconPath, [rbp+0A0h+isDefaultNode]; result
0x180042b34  mov     profileDoc, rsi; this
0x180042b37  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180042b3c  nop
0x180042b3d  lea     profileDoc, [rsp+1A0h+Name]; this
0x180042b42  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042b47  nop
0x180042b48  lea     profileDoc, [rbp+0A0h+Namespace]; this
0x180042b4c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042b51  lea     IconPath, [rbp+0A0h+Text]; Text
0x180042b55  mov     profileDoc, [rbp+0A0h+isDefaultNode._Ptr]; this
0x180042b59  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x180042b5e  cmp     qword ptr [r15+10h], 0
0x180042b63  jz      loc_180042C11
0x180042b69  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180042b70  cmp     r10, r12
0x180042b73  jz      short loc_180042B9C
0x180042b75  test    byte ptr [r10+1Ch], 10h
0x180042b7a  jz      short loc_180042B9C
0x180042b7c  mov     profileDoc, r15; this
0x180042b7f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042b84  mov     edx, 1Ch; id
0x180042b89  mov     r9, rax; _a1
0x180042b8c  lea     DisplayProviderName, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180042b93  mov     profileDoc, [r10+10h]; Logger
0x180042b97  call    WPP_SF_S
0x180042b9c  xorps   xmm0, xmm0
0x180042b9f  movups  xmmword ptr [rsp+1A0h+displayProviderNameNode._Ptr], xmm0
0x180042ba4  mov     IconPath, rbx; _Ptr
0x180042ba7  lea     profileDoc, [rbp+0A0h+var_E0]; this
0x180042bab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042bb0  nop
0x180042bb1  lea     IconPath, aIconfilepath; "ICONFilePath"
0x180042bb8  lea     profileDoc, [rbp+0A0h+connectionModeNode]; this
0x180042bbc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042bc1  nop
0x180042bc2  lea     rax, [rbp+0A0h+isDefaultNode]
0x180042bc6  mov     [rsp+1A0h+insertBefore], rax; insertBefore
0x180042bcb  lea     r9, [rbp+0A0h+var_E0]; Namespace
0x180042bcf  lea     DisplayProviderName, [rbp+0A0h+connectionModeNode]; Name
0x180042bd3  lea     IconPath, [rsp+1A0h+displayProviderNameNode]; result
0x180042bd8  mov     profileDoc, rsi; this
0x180042bdb  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180042be0  nop
0x180042be1  lea     profileDoc, [rbp+0A0h+connectionModeNode]; this
0x180042be5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042bea  nop
0x180042beb  lea     profileDoc, [rbp+0A0h+var_E0]; this
0x180042bef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042bf4  mov     IconPath, r15; Text
0x180042bf7  mov     profileDoc, [rsp+1A0h+displayProviderNameNode._Ptr]; this
0x180042bfc  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x180042c01  nop
0x180042c02  mov     profileDoc, [rsp+1A0h+displayProviderNameNode._Rep]; this
0x180042c07  test    profileDoc, profileDoc
0x180042c0a  jz      short loc_180042C11
0x180042c0c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042c11  xorps   xmm0, xmm0
0x180042c14  movdqu  xmmword ptr [rbp+0A0h+connectionModeNode._Ptr], xmm0
0x180042c19  lea     IconPath, [rbp+0A0h+connectionModeNode]; _Right
0x180042c1d  lea     profileDoc, [rsp+1A0h+insertBeforeNode]; this
0x180042c22  call    ??4?$shared_ptr@VNode@Xml@WcmCommon@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WcmCommon::Xml::Node>::operator=(std::shared_ptr<WcmCommon::Xml::Node> &&)
0x180042c27  mov     profileDoc, [rbp+0A0h+connectionModeNode._Rep]; this
0x180042c2b  test    profileDoc, profileDoc
0x180042c2e  jz      short loc_180042C35
0x180042c30  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042c35  mov     rbx, [rbp+0A0h+nodeList._Mypair._Myval2._Myfirst]
0x180042c39  mov     rdi, [rbp+0A0h+nodeList._Mypair._Myval2._Mylast]
0x180042c3d  cmp     rbx, rdi
0x180042c40  jz      short loc_180042C6D
0x180042c42  mov     IconPath, rbx
0x180042c45  call    _InsertNodesInProfileXml____2____lambda_2___operator__
0x180042c4a  test    al, al
0x180042c4c  jnz     short loc_180042C57
0x180042c4e  add     rbx, 10h
0x180042c52  cmp     rbx, rdi
0x180042c55  jnz     short loc_180042C42
0x180042c57  mov     rdi, [rbp+0A0h+nodeList._Mypair._Myval2._Mylast]
0x180042c5b  cmp     rbx, rdi
0x180042c5e  jz      short loc_180042C6D
0x180042c60  mov     IconPath, rbx; _Right
0x180042c63  lea     profileDoc, [rsp+1A0h+insertBeforeNode]; this
0x180042c68  call    ??4?$shared_ptr@VNode@Xml@WcmCommon@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WcmCommon::Xml::Node>::operator=(std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180042c6d  mov     profileDoc, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180042c74  cmp     profileDoc, r12
0x180042c77  jz      short loc_180042C94
0x180042c79  test    byte ptr [profileDoc+1Ch], 10h
0x180042c7d  jz      short loc_180042C94
0x180042c7f  mov     edx, 1Dh; id
0x180042c84  lea     DisplayProviderName, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180042c8b  mov     profileDoc, [profileDoc+10h]; Logger
0x180042c8f  call    WPP_SF_
0x180042c94  xorps   xmm0, xmm0
0x180042c97  movups  xmmword ptr [rbp+0A0h+connectionModeNode._Ptr], xmm0
0x180042c9b  lea     IconPath, aHttpWwwMicroso_1; "http://www.microsoft.com/networking/WWA"...
0x180042ca2  lea     profileDoc, [rsp+1A0h+displayProviderNameNode]; this
0x180042ca7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042cac  nop
0x180042cad  lea     IconPath, aConnectionmode; "ConnectionMode"
0x180042cb4  lea     profileDoc, [rbp+0A0h+var_E0]; this
0x180042cb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042cbd  nop
0x180042cbe  lea     rax, [rsp+1A0h+insertBeforeNode]
0x180042cc3  mov     [rsp+1A0h+insertBefore], rax; insertBefore
0x180042cc8  lea     r9, [rsp+1A0h+displayProviderNameNode]; Namespace
0x180042ccd  lea     DisplayProviderName, [rbp+0A0h+var_E0]; Name
0x180042cd1  lea     IconPath, [rbp+0A0h+connectionModeNode]; result
0x180042cd5  mov     profileDoc, rsi; this
0x180042cd8  call    ?CreateChild@Node@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@0AEBV45@@Z; WcmCommon::Xml::Node::CreateChild(std::wstring const &,std::wstring const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180042cdd  nop
0x180042cde  lea     profileDoc, [rbp+0A0h+var_E0]; this
0x180042ce2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042ce7  nop
0x180042ce8  lea     profileDoc, [rsp+1A0h+displayProviderNameNode]; this
0x180042ced  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042cf2  lea     IconPath, aAuto; "auto"
0x180042cf9  lea     profileDoc, [rbp+0A0h+Namespace]; this
0x180042cfd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042d02  nop
0x180042d03  lea     IconPath, [rbp+0A0h+Namespace]; Text
0x180042d07  mov     profileDoc, [rbp+0A0h+connectionModeNode._Ptr]; this
0x180042d0b  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x180042d10  nop
0x180042d11  lea     profileDoc, [rbp+0A0h+Namespace]; this
0x180042d15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042d1a  test    r13b, r13b
0x180042d1d  jnz     loc_180042DD5
0x180042d23  xorps   xmm0, xmm0
0x180042d26  movups  xmmword ptr [rsp+1A0h+displayProviderNameNode._Ptr], xmm0
0x180042d2b  xorps   xmm1, xmm1
0x180042d2e  movdqu  xmmword ptr [rsp+1A0h+Name._Mypair._Myval2._Bx], xmm1
0x180042d34  lea     IconPath, aHttpWwwMicroso; "http://www.microsoft.com/networking/WWA"...
  ... truncated ...
```

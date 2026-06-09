# PlanHandler::Provision(std::shared_ptr<WcmCommon::Xml::Document> const &)

- ea: `0x180030380`
- end: `0x180030b19`
- name: `?Provision@PlanHandler@@UEAA?AU?$pair@JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$shared_ptr@VDocument@Xml@WcmCommon@@@3@@Z`
- size: `1945`
- prototype: `std::pair<long,std::wstring > *__fastcall(PlanHandler *this, std::pair<long,std::wstring > *result, const std::shared_ptr<WcmCommon::Xml::Document> *XmlDoc)`
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002790`
- `0x180008234`
- `0x18000846c`
- `0x180009090`
- `0x18000af94`
- `0x18000b0a0`
- `0x18000b178`
- `0x18000fa6c`
- `0x180010984`
- `0x180011844`
- `0x180011c10`
- `0x180011cfc`
- `0x180011fdc`
- `0x180012748`
- `0x1800127cc`
- `0x18001a0d4`
- `0x18001a9f0`
- `0x18001b078`
- `0x18001b310`
- `0x18001bd60`
- `0x180025c9c`
- `0x180027768`
- `0x18002f828`
- `0x18002fa18`
- `0x18002fd88`
- `0x18002fdd8`
- `0x180030018`
- `0x180030380`
- `0x180030b20`
- `0x180030d60`
- `0x18003fc60`
- `0x18003fe90`
- `0x180049b8c`
- `0x180049d4c`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800307a2`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800307a2`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmCloseHandle` at `0x1800309a1`
- `ext-ms-win-networking-wcmapi-l1-1-0!WcmCloseHandle` at `0x1800309a1`

## string_xrefs

- `0x180030503`: `/default:CarrierProvisioning/default:Extensions/plans_v2:Plans_v2/plans_v2:Plan_v2`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
std::pair<long,std::wstring > *__fastcall PlanHandler::Provision(
        PlanHandler *this,
        std::pair<long,std::wstring > *result,
        const std::shared_ptr<WcmCommon::Xml::Document> *XmlDoc)
{
  std::pair<long,std::wstring > *v4; // r14
  PlanHandler *v5; // r13
  WcmCommon::Xml::Document **v6; // r8
  WcmCommon::Xml::Document *v7; // rbx
  WcmCommon::Xml::Document *Ptr; // rbx
  WcmCommon::Xml::Document *v9; // rbx
  std::shared_ptr<WcmCommon::Xml::Node> *Mylast; // rsi
  std::shared_ptr<WcmCommon::Xml::Node> *i; // rbx
  std::shared_ptr<WcmCommon::Xml::Node> **v12; // rax
  std::shared_ptr<WcmCommon::Xml::Node> *Myfirst; // r12
  std::shared_ptr<WcmCommon::Xml::Node> *v14; // rax
  HRESULT v15; // ebx
  const wchar_t *v16; // rax
  __int64 v17; // r10
  HRESULT v18; // eax
  std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring >,std::allocator<std::pair<std::wstring const ,bool> >,0> > *v19; // rcx
  const wchar_t *v20; // rax
  __int64 v21; // r10
  HRESULT v22; // edx
  std::wstring *v23; // rbx
  std::wstring *v24; // rax
  std::wstring *v25; // rax
  std::_String_constructor_concat_tag v26; // dl
  const std::wstring *v27; // rax
  std::allocator<std::pair<_GUID,std::wstring > > *v28; // r8
  bool badPlan; // [rsp+30h] [rbp-1D8h]
  HRESULT wlanError; // [rsp+34h] [rbp-1D4h] BYREF
  HRESULT hr; // [rsp+38h] [rbp-1D0h] BYREF
  int v33; // [rsp+3Ch] [rbp-1CCh]
  std::wstring Path; // [rsp+40h] [rbp-1C8h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> *v35; // [rsp+60h] [rbp-1A8h]
  std::shared_ptr<WcmCommon::Xml::Node> *j; // [rsp+68h] [rbp-1A0h]
  std::shared_ptr<WcmCommon::Xml::Node> plansPresent; // [rsp+70h] [rbp-198h] BYREF
  std::pair<long,std::wstring > *v38; // [rsp+80h] [rbp-188h]
  PlanHandler *v39; // [rsp+88h] [rbp-180h]
  std::wstring v40; // [rsp+90h] [rbp-178h] BYREF
  std::wstring v41; // [rsp+B0h] [rbp-158h] BYREF
  std::wstring resulta; // [rsp+D0h] [rbp-138h] BYREF
  Wcmutil Wcm; // [rsp+F0h] [rbp-118h] BYREF
  std::vector<std::pair<_GUID,std::wstring >> mbnProfileInterfaceList; // [rsp+F8h] [rbp-110h] BYREF
  std::vector<std::pair<_GUID,std::wstring >> wlanProfileInterfaceList; // [rsp+110h] [rbp-F8h] BYREF
  std::wstring planName; // [rsp+128h] [rbp-E0h] BYREF
  std::vector<std::shared_ptr<WcmCommon::Xml::Node>> planNodes; // [rsp+148h] [rbp-C0h] BYREF
  std::vector<unsigned char> provisioningOpcodeData; // [rsp+160h] [rbp-A8h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> plan2Node; // [rsp+180h] [rbp-88h] BYREF
  std::vector<std::shared_ptr<WcmCommon::Xml::Node>> plan2Nodes; // [rsp+1A0h] [rbp-68h] BYREF
  std::wstring resultXml; // [rsp+1B8h] [rbp-50h] BYREF

  v4 = result;
  v5 = this;
  v39 = this;
  v38 = result;
  v33 = 0;
  hr = 0;
  std::wstring::wstring(&resultXml);
  plansPresent = 0;
  v7 = *v6;
  std::wstring::wstring(&planName, L"/default:CarrierProvisioning/default:Plans");
  WcmCommon::Xml::Document::SelectSingle(v7, &plansPresent, &planName);
  std::wstring::_Tidy_deallocate(&planName);
  if ( plansPresent._Ptr )
  {
    memset(&planNodes, 0, sizeof(planNodes));
    Ptr = XmlDoc->_Ptr;
    std::wstring::wstring(&Path, L"/default:CarrierProvisioning/default:Plans/plans:Plan");
    WcmCommon::Xml::Document::Select(Ptr, &planNodes, &Path);
    std::wstring::_Tidy_deallocate(&Path);
    if ( planNodes._Mypair._Myval2._Myfirst == planNodes._Mypair._Myval2._Mylast )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids);
      }
      wlanError = 0;
      std::make_pair<long &,std::wstring &>(v4, &wlanError, &resultXml);
    }
    else
    {
      badPlan = 0;
      memset(&plan2Nodes, 0, sizeof(plan2Nodes));
      v9 = XmlDoc->_Ptr;
      std::wstring::wstring(
        &planName,
        L"/default:CarrierProvisioning/default:Extensions/plans_v2:Plans_v2/plans_v2:Plan_v2");
      WcmCommon::Xml::Document::Select(v9, &plan2Nodes, &planName);
      std::wstring::_Tidy_deallocate(&planName);
      Mylast = plan2Nodes._Mypair._Myval2._Mylast;
      for ( i = plan2Nodes._Mypair._Myval2._Myfirst; i != Mylast; ++i )
      {
        std::wstring::wstring(&Path, L"@AssociatedPlan");
        WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Node>>(
          (std::wstring *)&provisioningOpcodeData,
          i,
          &Path);
        std::wstring::_Tidy_deallocate(&Path);
        v12 = (std::shared_ptr<WcmCommon::Xml::Node> **)std::map<std::wstring,std::shared_ptr<WcmCommon::Xml::Node>>::_Try_emplace<std::wstring const &,>(
                                                          &v5->m_plan2NodeMap,
                                                          (std::pair<std::_Tree_node<std::pair<std::wstring const ,std::shared_ptr<WcmCommon::Xml::Node> >,void *> *,bool> *)&plan2Node,
                                                          (const std::wstring *)&provisioningOpcodeData);
        std::shared_ptr<WcmCommon::Xml::Node>::operator=(*v12 + 4, i);
        std::wstring::_Tidy_deallocate((std::wstring *)&provisioningOpcodeData);
      }
      memset(&wlanProfileInterfaceList, 0, sizeof(wlanProfileInterfaceList));
      std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&wlanProfileInterfaceList);
      GetWlanInterfaceProfileList(&wlanProfileInterfaceList);
      memset(&mbnProfileInterfaceList, 0, sizeof(mbnProfileInterfaceList));
      std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&mbnProfileInterfaceList);
      GetMbnInterfaceProfileList(&v5->m_params.SubscriberId, &v5->m_params.DeviceId, &mbnProfileInterfaceList);
      Wcm.m_hWcm = 0;
      Wcmutil::Wcmutil(&Wcm);
      Myfirst = planNodes._Mypair._Myval2._Myfirst;
      v14 = planNodes._Mypair._Myval2._Mylast;
      for ( j = planNodes._Mypair._Myval2._Mylast; ; v14 = j )
      {
        v35 = Myfirst;
        if ( Myfirst == v14 )
          break;
        std::wstring::wstring(&Path, L"@Name");
        WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Node>>(&planName, Myfirst, &Path);
        std::wstring::_Tidy_deallocate(&Path);
        memset(&provisioningOpcodeData, 0, sizeof(provisioningOpcodeData));
        Wcmutil::GetCarrierSubscriberPlanBlob(&provisioningOpcodeData, &v5->m_params, &planName);
        if ( wlanProfileInterfaceList._Mypair._Myval2._Myfirst == wlanProfileInterfaceList._Mypair._Myval2._Mylast )
        {
          v15 = -2112421869;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&planName._Mypair._Myval2);
            WPP_SF_S(*(_QWORD *)(v17 + 16), 0x1Au, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids, v16);
          }
          v15 = SetPlanForWlanProfiles(&provisioningOpcodeData, Myfirst, &Wcm, &wlanProfileInterfaceList);
        }
        wlanError = v15;
        if ( mbnProfileInterfaceList._Mypair._Myval2._Myfirst == mbnProfileInterfaceList._Mypair._Myval2._Mylast )
        {
          v18 = -2112421869;
        }
        else
        {
          plan2Node = 0;
          try
          {
            std::_Tree<std::_Tmap_traits<std::wstring,Unit,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Unit>>,0>>::_Find_lower_bound<std::wstring>(
              (std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring >,std::allocator<std::pair<std::wstring const ,bool> >,0> > *)&v5->m_plan2NodeMap,
              (std::_Tree_find_result<std::_Tree_node<std::pair<std::wstring const ,bool>,void *> *> *)&Path,
              &planName);
            if ( !std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<WcmCommon::Xml::Node>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<WcmCommon::Xml::Node>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                    v19,
                    (std::_Tree_node<std::pair<std::wstring const ,bool>,void *> *const)Path._Mypair._Myval2._Mysize,
                    (std::strong_ordering *)&planName) )
              std::_Xout_of_range("invalid map<K, T> key");
            std::shared_ptr<WcmCommon::Xml::Node>::operator=(
              &plan2Node,
              (const std::shared_ptr<WcmCommon::Xml::Node> *)(Path._Mypair._Myval2._Mysize + 64));
          }
          catch ( std::out_of_range )
          {
            Myfirst = v35;
            v15 = wlanError;
            v4 = v38;
            v5 = v39;
          }
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&planName._Mypair._Myval2);
            WPP_SF_S(*(_QWORD *)(v21 + 16), 0x1Bu, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids, v20);
          }
          v18 = SetPlanForMbnProfiles(&provisioningOpcodeData, Myfirst, &Wcm, &mbnProfileInterfaceList, &plan2Node);
          wlanError = v18;
          if ( plan2Node._Rep )
          {
            std::_Ref_count_base::_Decref(plan2Node._Rep);
            v18 = wlanError;
          }
        }
        v22 = 0;
        if ( v15 == -2112421869 && v18 == -2112421869 )
        {
          v22 = -2112421869;
          badPlan = 1;
        }
        v23 = wstringFromHRESULT(&resulta, v22);
        v24 = std::operator+<unsigned short>(&v41, L"<Plan name=\"", &planName);
        v25 = std::operator+<unsigned short>(&v40, v24, L"\" errorCode=\"");
        std::wstring::wstring(&Path, v26, v25, v23);
        v33 |= 2u;
        v27 = std::operator+<unsigned short>((std::wstring *)&plan2Node, &Path, L"\"/>");
        std::wstring::append(&resultXml, v27);
        std::wstring::_Tidy_deallocate((std::wstring *)&plan2Node);
        std::wstring::_Tidy_deallocate(&Path);
        std::wstring::_Tidy_deallocate(&v40);
        std::wstring::_Tidy_deallocate(&v41);
        std::wstring::_Tidy_deallocate(&resulta);
        std::vector<unsigned char>::_Tidy((std::vector<char> *)&provisioningOpcodeData);
        std::wstring::_Tidy_deallocate(&planName);
        ++Myfirst;
      }
      if ( !badPlan )
        std::wstring::_Eos(&resultXml, 0);
      std::make_pair<long &,std::wstring &>(v4, &hr, &resultXml);
      WcmCloseHandle(Wcm.m_hWcm, 0);
      if ( mbnProfileInterfaceList._Mypair._Myval2._Myfirst )
      {
        std::_Destroy_range<std::allocator<std::pair<_GUID,std::wstring>>>(
          mbnProfileInterfaceList._Mypair._Myval2._Myfirst,
          mbnProfileInterfaceList._Mypair._Myval2._Mylast,
          v28);
        std::_Deallocate<16>(
          mbnProfileInterfaceList._Mypair._Myval2._Myfirst,
          16
        * (((char *)mbnProfileInterfaceList._Mypair._Myval2._Myend
          - (char *)mbnProfileInterfaceList._Mypair._Myval2._Myfirst) >> 4));
        memset(&mbnProfileInterfaceList, 0, sizeof(mbnProfileInterfaceList));
      }
      if ( wlanProfileInterfaceList._Mypair._Myval2._Myfirst )
      {
        std::_Destroy_range<std::allocator<std::pair<_GUID,std::wstring>>>(
          wlanProfileInterfaceList._Mypair._Myval2._Myfirst,
          wlanProfileInterfaceList._Mypair._Myval2._Mylast,
          v28);
        std::_Deallocate<16>(
          wlanProfileInterfaceList._Mypair._Myval2._Myfirst,
          16
        * (((char *)wlanProfileInterfaceList._Mypair._Myval2._Myend
          - (char *)wlanProfileInterfaceList._Mypair._Myval2._Myfirst) >> 4));
        memset(&wlanProfileInterfaceList, 0, sizeof(wlanProfileInterfaceList));
      }
      std::vector<std::shared_ptr<Handler::Interface>>::~vector<std::shared_ptr<Handler::Interface>>((std::vector<std::shared_ptr<Notification::Configuration::Node>> *)&plan2Nodes);
    }
    std::vector<std::shared_ptr<Handler::Interface>>::~vector<std::shared_ptr<Handler::Interface>>((std::vector<std::shared_ptr<Notification::Configuration::Node>> *)&planNodes);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids);
    }
    hr = 1;
    std::make_pair<long &,std::wstring &>(v4, &hr, &resultXml);
  }
  if ( plansPresent._Rep )
    std::_Ref_count_base::_Decref(plansPresent._Rep);
  std::wstring::_Tidy_deallocate(&resultXml);
  return v4;
}

```

## disassembly

```asm
0x180030380  mov     r11, rsp
0x180030383  mov     [r11+20h], rbx
0x180030387  push    rsi
0x180030388  push    r12
0x18003038a  push    r13
0x18003038c  push    r14
0x18003038e  push    r15
0x180030390  sub     rsp, 1E0h
0x180030397  mov     rax, cs:__security_cookie
0x18003039e  xor     rax, rsp
0x1800303a1  mov     [rsp+208h+var_30], rax
0x1800303a9  mov     rsi, XmlDoc
0x1800303ac  mov     r14, rdx
0x1800303af  mov     r13, this
0x1800303b2  mov     [rsp+208h+var_180], this
0x1800303ba  mov     [rsp+208h+var_188], rdx
0x1800303c2  mov     [rsp+208h+var_1CC], 0
0x1800303ca  mov     [rsp+208h+hr], 0
0x1800303d2  lea     this, [r11-50h]; this
0x1800303d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800303db  nop
0x1800303dc  xorps   xmm0, xmm0
0x1800303df  movups  xmmword ptr [rsp+208h+plansPresent._Ptr], xmm0
0x1800303e4  mov     rbx, [XmlDoc]
0x1800303e7  lea     rdx, aDefaultCarrier_10; "/default:CarrierProvisioning/default:Pl"...
0x1800303ee  lea     this, [rsp+208h+planName]; this
0x1800303f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800303fb  nop
0x1800303fc  lea     XmlDoc, [rsp+208h+planName]; Path
0x180030404  lea     rdx, [rsp+208h+plansPresent]; result
0x180030409  mov     this, rbx; this
0x18003040c  call    ?SelectSingle@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::SelectSingle(std::wstring const &)
0x180030411  nop
0x180030412  lea     this, [rsp+208h+planName]; this
0x18003041a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003041f  cmp     [rsp+208h+plansPresent._Ptr], 0
0x180030425  jz      loc_180030A84
0x18003042b  xorps   xmm0, xmm0
0x18003042e  xor     eax, eax
0x180030430  movups  xmmword ptr [rsp+208h+planNodes._Mypair._Myval2._Myfirst], xmm0
0x180030438  mov     [rsp+208h+planNodes._Mypair._Myval2._Myend], rax
0x180030440  mov     rbx, [rsi]
0x180030443  lea     rdx, aDefaultCarrier_6; "/default:CarrierProvisioning/default:Pl"...
0x18003044a  lea     this, [rsp+208h+Path]; this
0x18003044f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030454  nop
0x180030455  lea     XmlDoc, [rsp+208h+Path]; Path
0x18003045a  lea     rdx, [rsp+208h+planNodes]; result
0x180030462  mov     this, rbx; this
0x180030465  call    ?Select@Document@Xml@WcmCommon@@QEAA?AV?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::Select(std::wstring const &)
0x18003046a  nop
0x18003046b  lea     this, [rsp+208h+Path]; this
0x180030470  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030475  mov     rax, [rsp+208h+planNodes._Mypair._Myval2._Mylast]
0x18003047d  cmp     [rsp+208h+planNodes._Mypair._Myval2._Myfirst], rax
0x180030485  jnz     short loc_1800304E5
0x180030487  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003048e  mov     this, cs:WPP_GLOBAL_Control
0x180030495  cmp     this, rsi
0x180030498  jz      short loc_1800304B5
0x18003049a  test    byte ptr [this+1Ch], 8
0x18003049e  jz      short loc_1800304B5
0x1800304a0  mov     edx, 19h; id
0x1800304a5  lea     XmlDoc, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids; TraceGuid
0x1800304ac  mov     this, [this+10h]; Logger
0x1800304b0  call    WPP_SF_
0x1800304b5  mov     [rsp+208h+wlanError], 0
0x1800304bd  lea     XmlDoc, [rsp+208h+resultXml]; _Val2
0x1800304c5  lea     rdx, [rsp+208h+wlanError]; _Val1
0x1800304ca  mov     this, r14; result
0x1800304cd  call    ??$make_pair@AEAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@YA?AU?$pair@JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@AEAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::make_pair<long &,std::wstring &>(long &,std::wstring &)
0x1800304d2  nop
0x1800304d3  lea     this, [rsp+208h+planNodes]; this
0x1800304db  call    ??1?$vector@V?$shared_ptr@VInterface@Handler@@@std@@V?$allocator@V?$shared_ptr@VInterface@Handler@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Handler::Interface>>::~vector<std::shared_ptr<Handler::Interface>>(void)
0x1800304e0  jmp     loc_180030AD0
0x1800304e5  xor     al, al
0x1800304e7  mov     [rsp+208h+badPlan], al
0x1800304eb  xorps   xmm0, xmm0
0x1800304ee  xor     eax, eax
0x1800304f0  movups  xmmword ptr [rsp+208h+plan2Nodes._Mypair._Myval2._Myfirst], xmm0
0x1800304f8  mov     [rsp+208h+plan2Nodes._Mypair._Myval2._Myend], rax
0x180030500  mov     rbx, [rsi]
0x180030503  lea     rdx, aDefaultCarrier_5; "/default:CarrierProvisioning/default:Ex"...
0x18003050a  lea     this, [rsp+208h+planName]; this
0x180030512  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030517  nop
0x180030518  lea     XmlDoc, [rsp+208h+planName]; Path
0x180030520  lea     rdx, [rsp+208h+plan2Nodes]; result
0x180030528  mov     this, rbx; this
0x18003052b  call    ?Select@Document@Xml@WcmCommon@@QEAA?AV?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::Select(std::wstring const &)
0x180030530  nop
0x180030531  lea     this, [rsp+208h+planName]; this
0x180030539  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003053e  mov     rsi, [rsp+208h+plan2Nodes._Mypair._Myval2._Mylast]
0x180030546  mov     rbx, [rsp+208h+plan2Nodes._Mypair._Myval2._Myfirst]
0x18003054e  jmp     short loc_1800305BC
0x180030550  lea     rdx, aAssociatedplan; "@AssociatedPlan"
0x180030557  lea     this, [rsp+208h+Path]; this
0x18003055c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030561  nop
0x180030562  lea     XmlDoc, [rsp+208h+Path]; Path
0x180030567  mov     rdx, rbx; s
0x18003056a  lea     this, [rsp+208h+provisioningOpcodeData]; result
0x180030572  call    ??$ExtractText@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@Xml@WcmCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@3@AEBV23@@Z; WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Node>>(std::shared_ptr<WcmCommon::Xml::Node> const &,std::wstring const &)
0x180030577  nop
0x180030578  lea     this, [rsp+208h+Path]; this
0x18003057d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030582  lea     XmlDoc, [rsp+208h+provisioningOpcodeData]; _Keyval
0x18003058a  lea     rdx, [rsp+208h+plan2Node]; result
0x180030592  lea     this, [r13+68h]; this
0x180030596  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VNode@Xml@WcmCommon@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VNode@Xml@WcmCommon@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VNode@Xml@WcmCommon@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::shared_ptr<WcmCommon::Xml::Node>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003059b  mov     this, [rax]
0x18003059e  add     this, 40h ; '@'; this
0x1800305a2  mov     rdx, rbx; _Right
0x1800305a5  call    ??4?$shared_ptr@VNode@Xml@WcmCommon@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WcmCommon::Xml::Node>::operator=(std::shared_ptr<WcmCommon::Xml::Node> const &)
0x1800305aa  nop
0x1800305ab  lea     this, [rsp+208h+provisioningOpcodeData]; this
0x1800305b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800305b8  add     rbx, 10h
0x1800305bc  cmp     rbx, rsi
0x1800305bf  jnz     short loc_180030550
0x1800305c1  xorps   xmm0, xmm0
0x1800305c4  xor     eax, eax
0x1800305c6  movups  xmmword ptr [rsp+208h+wlanProfileInterfaceList._Mypair._Myval2._Myfirst], xmm0
0x1800305ce  mov     [rsp+208h+wlanProfileInterfaceList._Mypair._Myval2._Myend], rax
0x1800305d6  lea     this, [rsp+208h+wlanProfileInterfaceList]; this
0x1800305de  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x1800305e3  nop
0x1800305e4  lea     this, [rsp+208h+wlanProfileInterfaceList]; ProfileInterfaceList
0x1800305ec  call    ?GetWlanInterfaceProfileList@@YAXAEAV?$vector@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@@Z; GetWlanInterfaceProfileList(std::vector<std::pair<_GUID,std::wstring>> &)
0x1800305f1  xorps   xmm0, xmm0
0x1800305f4  xor     eax, eax
0x1800305f6  movups  xmmword ptr [rsp+208h+mbnProfileInterfaceList._Mypair._Myval2._Myfirst], xmm0
0x1800305fe  mov     [rsp+208h+mbnProfileInterfaceList._Mypair._Myval2._Myend], rax
0x180030606  lea     this, [rsp+208h+mbnProfileInterfaceList]; this
0x18003060e  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x180030613  nop
0x180030614  lea     rdx, [r13+48h]; DeviceId
0x180030618  lea     this, [r13+28h]; SubscriberId
0x18003061c  lea     XmlDoc, [rsp+208h+mbnProfileInterfaceList]; InterfaceProfileList
0x180030624  call    ?GetMbnInterfaceProfileList@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV?$vector@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@2@@Z; GetMbnInterfaceProfileList(std::wstring const &,std::wstring const &,std::vector<std::pair<_GUID,std::wstring>> &)
0x180030629  mov     [rsp+208h+Wcm.m_hWcm], 0
0x180030635  lea     this, [rsp+208h+Wcm]; this
0x18003063d  call    ??0Wcmutil@@QEAA@XZ; Wcmutil::Wcmutil(void)
0x180030642  nop
0x180030643  mov     r12, [rsp+208h+planNodes._Mypair._Myval2._Myfirst]
0x18003064b  mov     rax, [rsp+208h+planNodes._Mypair._Myval2._Mylast]
0x180030653  mov     [rsp+208h+var_1A0], rax
0x180030658  lea     rsi, WPP_GLOBAL_Control
0x18003065f  mov     r15d, 82170013h
0x180030665  mov     [rsp+208h+var_1A8], r12
0x18003066a  cmp     r12, rax
0x18003066d  jz      loc_18003096B
0x180030673  lea     rdx, aName_0; "@Name"
0x18003067a  lea     this, [rsp+208h+Path]; this
0x18003067f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030684  nop
0x180030685  lea     XmlDoc, [rsp+208h+Path]; Path
0x18003068a  mov     rdx, r12; s
0x18003068d  lea     this, [rsp+208h+planName]; result
0x180030695  call    ??$ExtractText@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@Xml@WcmCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@3@AEBV23@@Z; WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Node>>(std::shared_ptr<WcmCommon::Xml::Node> const &,std::wstring const &)
0x18003069a  nop
0x18003069b  lea     this, [rsp+208h+Path]; this
0x1800306a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800306a5  xorps   xmm0, xmm0
0x1800306a8  xor     eax, eax
0x1800306aa  movups  xmmword ptr [rsp+208h+provisioningOpcodeData._Mypair._Myval2._Myfirst], xmm0
0x1800306b2  mov     [rsp+208h+provisioningOpcodeData._Mypair._Myval2._Myend], rax
0x1800306ba  lea     rdx, [r13+8]; Params
0x1800306be  lea     XmlDoc, [rsp+208h+planName]; PlanName
0x1800306c6  lea     this, [rsp+208h+provisioningOpcodeData]; result
0x1800306ce  call    ?GetCarrierSubscriberPlanBlob@Wcmutil@@SA?AV?$vector@EV?$allocator@E@std@@@std@@AEBUParameters@Handler@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Wcmutil::GetCarrierSubscriberPlanBlob(Handler::Parameters const &,std::wstring const &)
0x1800306d3  nop
0x1800306d4  mov     rax, [rsp+208h+wlanProfileInterfaceList._Mypair._Myval2._Mylast]
0x1800306dc  cmp     [rsp+208h+wlanProfileInterfaceList._Mypair._Myval2._Myfirst], rax
0x1800306e4  jnz     short loc_1800306EB
0x1800306e6  mov     ebx, r15d
0x1800306e9  jmp     short loc_180030745
0x1800306eb  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800306f2  cmp     r10, rsi
0x1800306f5  jz      short loc_180030723
0x1800306f7  test    byte ptr [r10+1Ch], 10h
0x1800306fc  jz      short loc_180030723
0x1800306fe  lea     this, [rsp+208h+planName]; this
0x180030706  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003070b  mov     r9, rax; _a1
0x18003070e  mov     edx, 1Ah; id
0x180030713  lea     XmlDoc, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids; TraceGuid
0x18003071a  mov     this, [r10+10h]; Logger
0x18003071e  call    WPP_SF_S
0x180030723  lea     r9, [rsp+208h+wlanProfileInterfaceList]; WlanInterfaceProfileList
0x18003072b  lea     XmlDoc, [rsp+208h+Wcm]; Wcm
0x180030733  mov     rdx, r12; CostNode
0x180030736  lea     this, [rsp+208h+provisioningOpcodeData]; ProvisioningOpcodeData
0x18003073e  call    ?SetPlanForWlanProfiles@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@2@AEBVWcmutil@@AEBV?$vector@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@2@@Z; SetPlanForWlanProfiles(std::vector<uchar> const &,std::shared_ptr<WcmCommon::Xml::Node> const &,Wcmutil const &,std::vector<std::pair<_GUID,std::wstring>> const &)
0x180030743  mov     ebx, eax
0x180030745  mov     [rsp+208h+wlanError], ebx
0x180030749  mov     this, [rsp+208h+mbnProfileInterfaceList._Mypair._Myval2._Mylast]
0x180030751  cmp     [rsp+208h+mbnProfileInterfaceList._Mypair._Myval2._Myfirst], this
0x180030759  jnz     short loc_180030763
0x18003075b  mov     eax, r15d
0x18003075e  jmp     loc_180030866
0x180030763  xorps   xmm1, xmm1
0x180030766  movdqu  xmmword ptr [rsp+208h+plan2Node._Ptr], xmm1
0x18003076f  lea     this, [r13+68h]; this
0x180030773  lea     XmlDoc, [rsp+208h+planName]; _Keyval
0x18003077b  lea     rdx, [rsp+208h+Path]; result
0x180030780  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VUnit@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VUnit@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VUnit@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Unit,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Unit>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180030785  lea     XmlDoc, [rsp+208h+planName]; _Keyval
0x18003078d  mov     rdx, [rsp+208h+Path._Mypair._Myval2._Mysize]; _Bound
0x180030792  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VNode@Xml@WcmCommon@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VNode@Xml@WcmCommon@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VNode@Xml@WcmCommon@@@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<WcmCommon::Xml::Node>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<WcmCommon::Xml::Node>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<WcmCommon::Xml::Node>>,void *> * const,std::wstring const &)
0x180030797  test    al, al
0x180030799  jnz     short loc_1800307A8
0x18003079b  lea     this, aInvalidMapKTKe; "invalid map<K, T> key"
0x1800307a2  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800307a8  mov     rdx, [rsp+208h+Path._Mypair._Myval2._Mysize]
0x1800307ad  add     rdx, 40h ; '@'; _Right
0x1800307b1  lea     this, [rsp+208h+plan2Node]; this
0x1800307b9  call    ??4?$shared_ptr@VNode@Xml@WcmCommon@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WcmCommon::Xml::Node>::operator=(std::shared_ptr<WcmCommon::Xml::Node> const &)
0x1800307be  nop
0x1800307bf  jmp     short loc_1800307E7
0x1800307c1  lea     rsi, WPP_GLOBAL_Control
0x1800307c8  mov     r15d, 82170013h
0x1800307ce  mov     r12, [rsp+208h+var_1A8]
0x1800307d3  mov     ebx, [rsp+208h+wlanError]
0x1800307d7  mov     r14, [rsp+208h+var_188]
0x1800307df  mov     r13, [rsp+208h+var_180]
0x1800307e7  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800307ee  cmp     r10, rsi
0x1800307f1  jz      short loc_18003081F
0x1800307f3  test    byte ptr [r10+1Ch], 10h
0x1800307f8  jz      short loc_18003081F
0x1800307fa  lea     this, [rsp+208h+planName]; this
0x180030802  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030807  mov     r9, rax; _a1
0x18003080a  mov     edx, 1Bh; id
0x18003080f  lea     XmlDoc, WPP_d59c69ff07203bfcdefe5df382b5e0ba_Traceguids; TraceGuid
0x180030816  mov     this, [r10+10h]; Logger
0x18003081a  call    WPP_SF_S
0x18003081f  lea     rax, [rsp+208h+plan2Node]
0x180030827  mov     [rsp+208h+Plan2Node], rax; Plan2Node
0x18003082c  lea     r9, [rsp+208h+mbnProfileInterfaceList]; MbnInterfaceProfileList
0x180030834  lea     XmlDoc, [rsp+208h+Wcm]; Wcm
0x18003083c  mov     rdx, r12; CostNode
0x18003083f  lea     this, [rsp+208h+provisioningOpcodeData]; ProvisioningOpcodeData
0x180030847  call    ?SetPlanForMbnProfiles@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@2@AEBVWcmutil@@AEBV?$vector@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@2@1@Z; SetPlanForMbnProfiles(std::vector<uchar> const &,std::shared_ptr<WcmCommon::Xml::Node> const &,Wcmutil const &,std::vector<std::pair<_GUID,std::wstring>> const &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18003084c  mov     [rsp+208h+wlanError], eax
0x180030850  mov     this, [rsp+208h+plan2Node._Rep]; this
0x180030858  test    this, this
0x18003085b  jz      short loc_180030866
0x18003085d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180030862  mov     eax, [rsp+208h+wlanError]
0x180030866  xor     edx, edx
0x180030868  cmp     ebx, r15d
0x18003086b  jnz     short loc_18003087A
0x18003086d  cmp     eax, r15d
0x180030870  jnz     short loc_18003087A
0x180030872  mov     edx, r15d; hr
0x180030875  mov     [rsp+208h+badPlan], 1
0x18003087a  lea     this, [rsp+208h+result]; result
0x180030882  call    ?wstringFromHRESULT@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; wstringFromHRESULT(long)
0x180030887  mov     rbx, rax
0x18003088a  lea     XmlDoc, [rsp+208h+planName]; _Right
0x180030892  lea     rdx, aPlanName; "<Plan name=\""
0x180030899  lea     this, [rsp+208h+var_158]; result
0x1800308a1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1800308a6  nop
0x1800308a7  lea     XmlDoc, aErrorcode_1; "\" errorCode=\""
0x1800308ae  mov     rdx, rax; _Left
0x1800308b1  lea     this, [rsp+208h+var_178]; result
0x1800308b9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800308be  nop
0x1800308bf  mov     r9, rbx; __formal
0x1800308c2  mov     XmlDoc, rax; _Right
0x1800308c5  lea     this, [rsp+208h+Path]; this
0x1800308ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800308cf  or      [rsp+208h+var_1CC], 2
0x1800308d4  lea     XmlDoc, asc_180078598; "\"/>"
0x1800308db  lea     rdx, [rsp+208h+Path]; _Left
0x1800308e0  lea     this, [rsp+208h+plan2Node]; result
0x1800308e8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800308ed  nop
0x1800308ee  mov     rdx, rax; _Right
0x1800308f1  lea     this, [rsp+208h+resultXml]; this
0x1800308f9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800308fe  nop
0x1800308ff  lea     this, [rsp+208h+plan2Node]; this
0x180030907  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003090c  nop
0x18003090d  lea     this, [rsp+208h+Path]; this
0x180030912  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030917  nop
0x180030918  lea     this, [rsp+208h+var_178]; this
0x180030920  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030925  nop
0x180030926  lea     this, [rsp+208h+var_158]; this
0x18003092e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030933  nop
0x180030934  lea     this, [rsp+208h+result]; this
0x18003093c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```

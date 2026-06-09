# Microsoft::Basix::Dct::SmilesV3::SmilesV3(boost::property_tree::basic_ptree<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,boost::any,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> const &)

- ea: `0x1802572a4`
- end: `0x180258f63`
- name: `??0SmilesV3@Dct@Basix@Microsoft@@QEAA@AEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z`
- size: `7359`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800df9fc`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x18001db78`
- `0x18001dc00`
- `0x18001f814`
- `0x18001f970`
- `0x180024568`
- `0x180024760`
- `0x180028820`
- `0x18003c308`
- `0x180099fa8`
- `0x18009a0e8`
- `0x1800c408c`
- `0x1800f33a4`
- `0x180106038`
- `0x180192cec`
- `0x1801b0ab4`
- `0x1801b5228`
- `0x1802535d4`
- `0x180256724`
- `0x180256840`
- `0x180256960`
- `0x1802572a4`
- `0x180258f64`
- `0x1802e78ec`
- `0x1802f304c`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x18032f140`
- `0x180375c40`
- `0x180376380`

## string_xrefs

- `0x18025759e`: `Microsoft::Basix::Dct.Smiles.UseSideband`
- `0x1802589fa`: `NanoConfigurations`
- `0x18025766f`: `Microsoft::Basix::Dct.ICE.Smiles.SmallLinkTardyCntThreshold`
- `0x1802589e2`: `Smiles Configurations`
- `0x180257a2c`: `RendezvousLinkSwitch_61430490`
- `0x180257b8b`: `LinkSwitchStopped_61492275`
- `0x180257e14`: `secLinksSendInterval`
- `0x180257ffb`: `smallPrimaryLinkTardyCountThreshold`
- `0x1802580f6`: `primaryLinkReceiveTimeVarMultiple`
- `0x180258352`: `SmilesSidebandOperationId`
- `0x1802584ac`: `SmilesSidebandOperationId`

## pseudocode

```c
// Hidden C++ exception states: #wind=189
__int64 __fastcall Microsoft::Basix::Dct::SmilesV3::SmilesV3(__int64 a1, __int64 a2, int a3)
{
  int v5; // edi
  const struct Microsoft::Basix::Instrumentation::MultiLinkActivity *Description; // rax
  const struct Microsoft::Basix::Instrumentation::MultiLinkError *v7; // rax
  _QWORD *v8; // rax
  __int64 Property; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  double v14; // xmm0_8
  unsigned __int64 v15; // rcx
  void *v16; // rax
  __int64 v17; // rax
  void *v18; // rcx
  void *v19; // rax
  __int64 v20; // rax
  void *v21; // rcx
  __int64 v22; // rax
  volatile signed __int32 *v23; // rcx
  __int64 v24; // rcx
  const char *v25; // r9
  const char *v26; // r14
  const char *v27; // rbx
  volatile signed __int32 *v28; // rbx
  const char *v29; // r9
  volatile signed __int32 *v30; // rbx
  __int64 v31; // rax
  int v32; // ebx
  volatile signed __int32 *v33; // rbx
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  int v54; // edi
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rdx
  _BYTE *v59; // rax
  int v60; // edi
  int v61; // edi
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int64 v65; // rdx
  int v66; // edi
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rdx
  __int64 v70; // rdx
  int v71; // ebx
  _BYTE *v72; // rax
  int v73; // edi
  int v74; // edi
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rdx
  __int64 v78; // rdx
  int v79; // ebx
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rdx
  __int64 v83; // rdx
  volatile signed __int32 *v84; // rbx
  _BYTE v86[4]; // [rsp+70h] [rbp-90h] BYREF
  int v87; // [rsp+74h] [rbp-8Ch]
  double v88; // [rsp+78h] [rbp-88h] BYREF
  __int128 v89; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  __int128 v91; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v92; // [rsp+B0h] [rbp-50h]
  _OWORD v93[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v94[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v95[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v96[2]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v97[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v98[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v99[2]; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v100[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v101[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _OWORD v102[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  _OWORD v103[2]; // [rsp+200h] [rbp+100h] BYREF
  _OWORD v104[2]; // [rsp+220h] [rbp+120h] BYREF
  _OWORD v105[2]; // [rsp+240h] [rbp+140h] BYREF
  _OWORD v106[2]; // [rsp+260h] [rbp+160h] BYREF
  _OWORD v107[2]; // [rsp+280h] [rbp+180h] BYREF
  _OWORD v108[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _OWORD v109[2]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _OWORD v110[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _OWORD v111[2]; // [rsp+300h] [rbp+200h] BYREF
  _OWORD v112[2]; // [rsp+320h] [rbp+220h] BYREF
  _OWORD v113[2]; // [rsp+340h] [rbp+240h] BYREF
  _OWORD v114[2]; // [rsp+360h] [rbp+260h] BYREF
  _OWORD v115[2]; // [rsp+380h] [rbp+280h] BYREF
  _OWORD v116[2]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _OWORD v117[2]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _OWORD v118[2]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _OWORD v119[2]; // [rsp+400h] [rbp+300h] BYREF
  _OWORD v120[2]; // [rsp+420h] [rbp+320h] BYREF
  _OWORD v121[2]; // [rsp+440h] [rbp+340h] BYREF
  _OWORD v122[2]; // [rsp+460h] [rbp+360h] BYREF
  _OWORD v123[2]; // [rsp+480h] [rbp+380h] BYREF
  __int64 v124; // [rsp+4A0h] [rbp+3A0h]
  __int64 *v125; // [rsp+4A8h] [rbp+3A8h]
  __int64 *v126; // [rsp+4B0h] [rbp+3B0h]
  __int64 *v127; // [rsp+4B8h] [rbp+3B8h]
  __int64 *v128; // [rsp+4C0h] [rbp+3C0h]
  __int64 *v129; // [rsp+4C8h] [rbp+3C8h]
  __int64 *v130; // [rsp+4D0h] [rbp+3D0h]
  __int64 *v131; // [rsp+4D8h] [rbp+3D8h]
  __int64 v132[2]; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int128 v133; // [rsp+4F0h] [rbp+3F0h]
  __int64 v134[2]; // [rsp+500h] [rbp+400h] BYREF
  __int128 v135; // [rsp+510h] [rbp+410h]
  __int64 v136[4]; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v137[32]; // [rsp+540h] [rbp+440h] BYREF
  __int64 v138[4]; // [rsp+560h] [rbp+460h] BYREF
  __int64 v139[4]; // [rsp+580h] [rbp+480h] BYREF
  __int64 v140[4]; // [rsp+5A0h] [rbp+4A0h] BYREF
  __int64 v141[4]; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v142[32]; // [rsp+5E0h] [rbp+4E0h] BYREF
  __int64 v143[4]; // [rsp+600h] [rbp+500h] BYREF
  _BYTE v144[32]; // [rsp+620h] [rbp+520h] BYREF
  _BYTE v145[32]; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v146[32]; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v147[32]; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v148[32]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v149[32]; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE v150[32]; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE v151[32]; // [rsp+700h] [rbp+600h] BYREF
  _BYTE v152[32]; // [rsp+720h] [rbp+620h] BYREF
  _BYTE v153[32]; // [rsp+740h] [rbp+640h] BYREF
  _BYTE v154[32]; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v155[32]; // [rsp+780h] [rbp+680h] BYREF
  _BYTE v156[32]; // [rsp+7A0h] [rbp+6A0h] BYREF
  _BYTE v157[32]; // [rsp+7C0h] [rbp+6C0h] BYREF
  _BYTE v158[32]; // [rsp+7E0h] [rbp+6E0h] BYREF
  _BYTE v159[32]; // [rsp+800h] [rbp+700h] BYREF
  _BYTE v160[32]; // [rsp+820h] [rbp+720h] BYREF
  _BYTE v161[32]; // [rsp+840h] [rbp+740h] BYREF
  _BYTE v162[32]; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v163[32]; // [rsp+880h] [rbp+780h] BYREF
  _BYTE v164[32]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE v165[32]; // [rsp+8C0h] [rbp+7C0h] BYREF
  _BYTE v166[32]; // [rsp+8E0h] [rbp+7E0h] BYREF
  _BYTE v167[32]; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v168[32]; // [rsp+920h] [rbp+820h] BYREF
  _BYTE v169[32]; // [rsp+940h] [rbp+840h] BYREF
  _BYTE v170[32]; // [rsp+960h] [rbp+860h] BYREF
  _BYTE v171[32]; // [rsp+980h] [rbp+880h] BYREF
  _BYTE v172[32]; // [rsp+9A0h] [rbp+8A0h] BYREF
  _BYTE v173[32]; // [rsp+9C0h] [rbp+8C0h] BYREF
  _BYTE v174[32]; // [rsp+9E0h] [rbp+8E0h] BYREF
  _BYTE v175[32]; // [rsp+A00h] [rbp+900h] BYREF
  _BYTE v176[32]; // [rsp+A20h] [rbp+920h] BYREF
  _BYTE v177[32]; // [rsp+A40h] [rbp+940h] BYREF
  _BYTE v178[32]; // [rsp+A60h] [rbp+960h] BYREF
  _BYTE v179[32]; // [rsp+A80h] [rbp+980h] BYREF
  _BYTE v180[32]; // [rsp+AA0h] [rbp+9A0h] BYREF
  _BYTE v181[32]; // [rsp+AC0h] [rbp+9C0h] BYREF
  _OWORD v182[2]; // [rsp+AE0h] [rbp+9E0h] BYREF
  int v183[4]; // [rsp+B00h] [rbp+A00h] BYREF
  _QWORD v184[12]; // [rsp+B20h] [rbp+A20h] BYREF

  v124 = a1;
  v5 = 0;
  v87 = 0;
  LODWORD(v88) = 0;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 8) = &Microsoft::Basix::Dct::SmilesV3::`vbtable';
    *(_QWORD *)(a1 + 3208) = 0;
    *(_QWORD *)(a1 + 3216) = 0;
    *(_QWORD *)(a1 + 3200) = &Microsoft::Basix::SharedFromThisVirtualBase::`vftable';
    v5 = 1;
    v87 = 1;
  }
  Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataV3>::Smiles<Microsoft::Basix::Dct::LinkDataV3>(a1, a2, 0);
  *(_QWORD *)a1 = &Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'};
  *(_QWORD *)(a1 + 40) = &Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'};
  *(_QWORD *)(a1 + 1088) = &Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::ILinkDataCallback'};
  *(_QWORD *)(a1 + 1096) = &Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::ISmiles'};
  *(_QWORD *)(a1 + 1104) = &Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::ISmilesLink'};
  *(_QWORD *)(a1 + 2048) = &Microsoft::Basix::Dct::SmilesV3::`vftable';
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 4LL) + a1 + 8) = &Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::SharedFromThis'};
  Microsoft::Basix::Dct::SmilesV3::Summary::Summary((Microsoft::Basix::Dct::SmilesV3::Summary *)(a1 + 2056));
  *(_QWORD *)(a1 + 2208) = 0;
  *(_DWORD *)(a1 + 2216) = 0;
  v89 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v89) = 0;
  Description = Microsoft::Basix::Instrumentation::MultiLinkActivity::GetDescription();
  Microsoft::Basix::Instrumentation::EventBase::EventBase(a1 + 2240, Description, &v89);
  *(_QWORD *)(a1 + 2240) = &Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::Instrumentation::MultiLinkActivity>::`vftable';
  std::string::_Tidy_deallocate(&v89);
  v89 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v89) = 0;
  v7 = Microsoft::Basix::Instrumentation::MultiLinkError::GetDescription();
  Microsoft::Basix::Instrumentation::EventBase::EventBase(a1 + 2560, v7, &v89);
  *(_QWORD *)(a1 + 2560) = &Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::Instrumentation::MultiLinkError>::`vftable';
  std::string::_Tidy_deallocate(&v89);
  *(_QWORD *)(a1 + 2880) = 0;
  *(_QWORD *)(a1 + 2896) = 0;
  *(_QWORD *)(a1 + 2904) = 0;
  *(_QWORD *)(a1 + 2936) = 0;
  *(_WORD *)(a1 + 2944) = 0;
  *(_QWORD *)(a1 + 2952) = 0;
  *(_QWORD *)(a1 + 2960) = 0;
  *(_QWORD *)(a1 + 2968) = 0;
  *(_QWORD *)(a1 + 2976) = 0;
  *(_QWORD *)(a1 + 2984) = 0;
  *(_QWORD *)(a1 + 2992) = -1;
  *(_QWORD *)(a1 + 3000) = 20;
  *(_QWORD *)(a1 + 3008) = 0;
  *(_DWORD *)(a1 + 3016) = 0;
  *(_BYTE *)(a1 + 3020) = 0;
  *(_QWORD *)(a1 + 3024) = &Microsoft::Basix::Timer::`vftable';
  Microsoft::Basix::CreateTimerImpl(a1 + 3032, 0);
  *(_QWORD *)(a1 + 3048) = *(_QWORD *)std::chrono::steady_clock::now(&v88) / 1000000LL;
  *(_BYTE *)(a1 + 3056) = 0;
  *(_QWORD *)(a1 + 3064) = 0;
  *(_QWORD *)(a1 + 3072) = 0;
  *(_QWORD *)(a1 + 3080) = 0;
  *(_WORD *)(a1 + 3088) = 0;
  *(_BYTE *)(a1 + 3090) = 0;
  *(_QWORD *)(a1 + 3096) = 0;
  *(_QWORD *)(a1 + 3104) = 0;
  *(_WORD *)(a1 + 3112) = 0;
  *(_QWORD *)(a1 + 3120) = 0;
  *(_QWORD *)(a1 + 3128) = 0;
  *(_QWORD *)(a1 + 3136) = 0;
  *(_QWORD *)(a1 + 3144) = 0;
  *(_QWORD *)(a1 + 3152) = 0;
  v8 = operator new(0x10u);
  v8[1] = 0;
  *(_QWORD *)(a1 + 3120) = v8;
  *v8 = a1 + 3120;
  *(_QWORD *)(a1 + 3160) = 0;
  *(_QWORD *)(a1 + 3168) = 0x7FFFFFFFFFFFFFFFLL;
  *(_WORD *)(a1 + 3176) = 0;
  v89 = 0;
  si128 = 0;
  std::string::_Construct<1,char const *>(&v89, "Microsoft::Basix::Dct.Smiles.UseSideband", 40);
  Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(a1 + 40, v183, &v89);
  v86[0] = 0;
  *(_BYTE *)(a1 + 3177) = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
                            *(_QWORD *)(Property + 16),
                            v86);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v183);
  std::string::_Tidy_deallocate(&v89);
  v89 = 0;
  si128 = 0;
  std::string::_Construct<1,char const *>(&v89, "Microsoft::Basix::Dct.ICE.Smiles.ReceiveTimeVarMultiple", 55);
  v10 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(a1 + 40, v183, &v89);
  LODWORD(v88) = 4;
  *(_DWORD *)(a1 + 2920) = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned int>(
                             *(_QWORD *)(v10 + 16),
                             &v88);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v183);
  std::string::_Tidy_deallocate(&v89);
  v89 = 0;
  si128 = 0;
  std::string::_Construct<1,char const *>(&v89, "Microsoft::Basix::Dct.ICE.Smiles.SmallLinkTardyCntThreshold", 59);
  v11 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(a1 + 40, v183, &v89);
  LODWORD(v88) = 5;
  *(_DWORD *)(a1 + 2916) = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned int>(
                             *(_QWORD *)(v11 + 16),
                             &v88);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v183);
  std::string::_Tidy_deallocate(&v89);
  v89 = 0;
  si128 = 0;
  std::string::_Construct<1,char const *>(&v89, "Microsoft::Basix::Dct.ICE.Smiles.MinCounterGap", 46);
  v12 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(a1 + 40, v183, &v89);
  LODWORD(v88) = 3;
  *(_DWORD *)(a1 + 2912) = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned int>(
                             *(_QWORD *)(v12 + 16),
                             &v88);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v183);
  std::string::_Tidy_deallocate(&v89);
  v89 = 0;
  si128 = 0;
  std::string::_Construct<1,char const *>(&v89, "Microsoft::Basix::Dct.ICE.Smiles.TestTimeout", 44);
  v13 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(a1 + 40, v183, &v89);
  v88 = DOUBLE_1_0;
  v14 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<double>(
          *(_QWORD *)(v13 + 16),
          &v88)
      * 1000.0;
  v15 = 0;
  if ( v14 >= 9.223372036854776e18 )
  {
    v14 = v14 - 9.223372036854776e18;
    if ( v14 < 9.223372036854776e18 )
      v15 = 0x8000000000000000uLL;
  }
  *(_QWORD *)(a1 + 2928) = v15 + (unsigned int)(int)v14;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v183);
  std::string::_Tidy_deallocate(&v89);
  v16 = operator new(0x978u);
  v88 = *(double *)&v16;
  if ( v16 )
    v17 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::SlidingStats<double,20,1,1>(v16);
  else
    v17 = 0;
  v18 = *(void **)(a1 + 2896);
  *(_QWORD *)(a1 + 2896) = v17;
  if ( v18 )
    operator delete(v18, (const struct std::nothrow_t *)0x978);
  v19 = operator new(0x320u);
  v88 = *(double *)&v19;
  if ( v19 )
    v20 = Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::SlidingStats<double,5,1,1>(v19);
  else
    v20 = 0;
  v21 = *(void **)(a1 + 2904);
  *(_QWORD *)(a1 + 2904) = v20;
  if ( v21 )
    operator delete(v21, (const struct std::nothrow_t *)0x320);
  *(_QWORD *)(a1 + 2888) = 0;
  v91 = 0;
  v92 = 0;
  std::string::_Construct<1,char const *>(&v91, "Microsoft::Basix::Dct.Smiles.Callback", 37);
  v22 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(a1 + 40, &v89, &v91);
  v182[0] = 0;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::weak_ptr<Microsoft::Basix::Dct::ISmiles::ISmilesCallback>>(
    *(_QWORD *)(v22 + 16),
    v183,
    v182);
  *(_QWORD *)(a1 + 1472) = *(_QWORD *)v183;
  v23 = *(volatile signed __int32 **)(a1 + 1480);
  *(_QWORD *)(a1 + 1480) = *(_QWORD *)&v183[2];
  if ( v23 && _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
  v24 = *((_QWORD *)&v182[0] + 1);
  if ( *((_QWORD *)&v182[0] + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v182[0] + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
  }
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v89);
  std::string::_Tidy_deallocate(&v91);
  memset(v184, 0, sizeof(v184));
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::basic_ptree<std::string,boost::any,std::less<std::string>>(
    v184,
    a2);
  memset(&v184[3], 0, 64);
  v184[11] = 0xFFFFFFFFLL;
  LODWORD(v184[2]) = 2;
  Microsoft::Basix::Dct::s_bugfixenabled_RendezvousLinkSwitch_61430490 = Microsoft::Basix::Dct::PropertyImpl::IsEnabled(
                                                                           (Microsoft::Basix::Dct::PropertyImpl *)v184,
                                                                           (const struct Microsoft::Basix::Dct::ContainmentSwitch *)off_180423450);
  v182[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v182);
  v26 = "disabled";
  if ( *(_QWORD *)&v182[0] && *(_BYTE *)(*(_QWORD *)&v182[0] + 128LL) )
  {
    v27 = "disabled";
    if ( Microsoft::Basix::Dct::s_bugfixenabled_RendezvousLinkSwitch_61430490 )
      v27 = "enabled";
    v91 = 0;
    v92 = 0;
    std::string::_Construct<1,char const *>(&v91, "Feature %s was %s by containment", (const char *)0x20, v25);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *>(
      (unsigned int)v182,
      (unsigned int)"BASIX_DCT",
      (unsigned int)&v91,
      (unsigned int)"RendezvousLinkSwitch_61430490",
      (__int64)v27);
    std::string::_Tidy_deallocate(&v91);
  }
  v28 = (volatile signed __int32 *)*((_QWORD *)&v182[0] + 1);
  if ( *((_QWORD *)&v182[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v182[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
  }
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v184);
  memset(v184, 0, sizeof(v184));
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::basic_ptree<std::string,boost::any,std::less<std::string>>(
    v184,
    a2);
  memset(&v184[3], 0, 64);
  v184[11] = 0xFFFFFFFFLL;
  LODWORD(v184[2]) = 2;
  Microsoft::Basix::Dct::s_bugfixenabled_LinkSwitchStopped_61492275 = Microsoft::Basix::Dct::PropertyImpl::IsEnabled(
                                                                        (Microsoft::Basix::Dct::PropertyImpl *)v184,
                                                                        (const struct Microsoft::Basix::Dct::ContainmentSwitch *)off_180423468);
  v182[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v182);
  if ( *(_QWORD *)&v182[0] && *(_BYTE *)(*(_QWORD *)&v182[0] + 128LL) )
  {
    if ( Microsoft::Basix::Dct::s_bugfixenabled_LinkSwitchStopped_61492275 )
      v26 = "enabled";
    v91 = 0;
    v92 = 0;
    std::string::_Construct<1,char const *>(&v91, "Feature %s was %s by containment", (const char *)0x20, v29);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *>(
      (unsigned int)v182,
      (unsigned int)"BASIX_DCT",
      (unsigned int)&v91,
      (unsigned int)"LinkSwitchStopped_61492275",
      (__int64)v26);
    std::string::_Tidy_deallocate(&v91);
  }
  v30 = (volatile signed __int32 *)*((_QWORD *)&v182[0] + 1);
  if ( *((_QWORD *)&v182[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v182[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
      if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v184);
  v91 = 0;
  v92 = 0;
  std::string::_Construct<1,char const *>(&v91, "Microsoft::Basix::Dct.Transport.AutoReconnectionTimeoutSeconds", 62);
  v31 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(a1 + 40, &v89, &v91);
  LODWORD(v88) = 0;
  v32 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned int>(
          *(_QWORD *)(v31 + 16),
          &v88);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v89);
  std::string::_Tidy_deallocate(&v91);
  if ( v32 )
  {
    *(_BYTE *)(a1 + 1504) = 1;
    *(_DWORD *)(a1 + 1508) = v32;
  }
  v182[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v182);
  if ( *(_QWORD *)&v182[0] && *(_BYTE *)(*(_QWORD *)&v182[0] + 128LL) )
  {
    v91 = 0;
    v92 = 0;
    std::string::_Construct<1,char const *>(&v91, "SmilesV3 constructed: 0x%llx", 28);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(
      v182,
      "BASIX_DCT",
      &v91,
      a1);
    std::string::_Tidy_deallocate(&v91);
  }
  v33 = (volatile signed __int32 *)*((_QWORD *)&v182[0] + 1);
  if ( *((_QWORD *)&v182[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v182[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
    }
  }
  *(_OWORD *)v183 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v183);
  if ( *(_QWORD *)v183 && *(_BYTE *)(*(_QWORD *)v183 + 128LL) )
  {
    v125 = v138;
    std::_Integral_to_string<char,unsigned __int64>(v148, *(_QWORD *)(a1 + 2928));
    memset(v110, 0, sizeof(v110));
    std::string::_Construct<1,char const *>(v110, ":", 1);
    memset(v102, 0, sizeof(v102));
    std::string::_Construct<1,char const *>(v102, "\"", 1);
    memset(v100, 0, sizeof(v100));
    std::string::_Construct<1,char const *>(v100, "\"", 1);
    v34 = std::operator+<char>(v181, v100, "secLinksSendInterval");
    LOBYTE(v35) = v86[0];
    std::string::string(v137, v35, v34, v102);
    LOBYTE(v36) = v86[0];
    std::string::string(v171, v36, v137, v110);
    LOBYTE(v37) = v86[0];
    std::string::string(v138, v37, v171, v148);
    v126 = v139;
    std::_Integral_to_string<char,unsigned int>(v170, *(unsigned int *)(a1 + 2912));
    memset(v99, 0, sizeof(v99));
    std::string::_Construct<1,char const *>(v99, ":", 1);
    memset(v98, 0, sizeof(v98));
    std::string::_Construct<1,char const *>(v98, "\"", 1);
    memset(v97, 0, sizeof(v97));
    std::string::_Construct<1,char const *>(v97, "\"", 1);
    v38 = std::operator+<char>(v180, v97, "minCounterGapForSwitch");
    LOBYTE(v39) = v86[0];
    std::string::string(v169, v39, v38, v98);
    LOBYTE(v40) = v86[0];
    std::string::string(v168, v40, v169, v99);
    LOBYTE(v41) = v86[0];
    std::string::string(v139, v41, v168, v170);
    v127 = v140;
    std::_Integral_to_string<char,unsigned int>(v167, *(unsigned int *)(a1 + 2916));
    memset(v96, 0, sizeof(v96));
    std::string::_Construct<1,char const *>(v96, ":", 1);
    memset(v95, 0, sizeof(v95));
    std::string::_Construct<1,char const *>(v95, "\"", 1);
    memset(v94, 0, sizeof(v94));
    std::string::_Construct<1,char const *>(v94, "\"", 1);
    v42 = std::operator+<char>(v179, v94, "smallPrimaryLinkTardyCountThreshold");
    LOBYTE(v43) = v86[0];
    std::string::string(v166, v43, v42, v95);
    LOBYTE(v44) = v86[0];
    std::string::string(v165, v44, v166, v96);
    LOBYTE(v45) = v86[0];
    std::string::string(v140, v45, v165, v167);
    v128 = v141;
    std::_Integral_to_string<char,unsigned int>(v164, *(unsigned int *)(a1 + 2920));
    memset(v93, 0, sizeof(v93));
    std::string::_Construct<1,char const *>(v93, ":", 1);
    memset(v123, 0, sizeof(v123));
    std::string::_Construct<1,char const *>(v123, "\"", 1);
    memset(v122, 0, sizeof(v122));
    std::string::_Construct<1,char const *>(v122, "\"", 1);
    v46 = std::operator+<char>(v178, v122, "primaryLinkReceiveTimeVarMultiple");
    LOBYTE(v47) = v86[0];
    std::string::string(v163, v47, v46, v123);
    LOBYTE(v48) = v86[0];
    std::string::string(v162, v48, v163, v93);
    LOBYTE(v49) = v86[0];
    std::string::string(v141, v49, v162, v164);
    v129 = v136;
    std::_Integral_to_string<char,unsigned int>(v161, *(unsigned int *)(a1 + 1508));
    memset(v121, 0, sizeof(v121));
    std::string::_Construct<1,char const *>(v121, ":", 1);
    memset(v120, 0, sizeof(v120));
    std::string::_Construct<1,char const *>(v120, "\"", 1);
    memset(v119, 0, sizeof(v119));
    std::string::_Construct<1,char const *>(v119, "\"", 1);
    v50 = std::operator+<char>(v177, v119, "autoReconnectTimeoutSeconds");
    LOBYTE(v51) = v86[0];
    std::string::string(v160, v51, v50, v120);
    LOBYTE(v52) = v86[0];
    std::string::string(v159, v52, v160, v121);
    LOBYTE(v53) = v86[0];
    std::string::string(v136, v53, v159, v161);
    v130 = v132;
    if ( *(_BYTE *)(a1 + 3177) )
    {
      memset(v118, 0, sizeof(v118));
      std::string::_Construct<1,char const *>(v118, "true", 4);
      v54 = v5 | 2;
      v87 = v54;
      memset(v117, 0, sizeof(v117));
      std::string::_Construct<1,char const *>(v117, ":", 1);
      v54 |= 4u;
      v87 = v54;
      memset(v116, 0, sizeof(v116));
      std::string::_Construct<1,char const *>(v116, "\"", 1);
      v54 |= 8u;
      v87 = v54;
      memset(v115, 0, sizeof(v115));
      std::string::_Construct<1,char const *>(v115, "\"", 1);
      v54 |= 0x10u;
      v87 = v54;
      v55 = std::operator+<char>(v176, v115, "SmilesSidebandOperationId");
      v54 |= 0x20u;
      v87 = v54;
      LOBYTE(v56) = v86[0];
      std::string::string(v158, v56, v55, v116);
      v54 |= 0x40u;
      v87 = v54;
      LOBYTE(v57) = v86[0];
      std::string::string(v157, v57, v158, v117);
      v54 |= 0x80u;
      v87 = v54;
      LOBYTE(v58) = v86[0];
      std::string::string(v156, v58, v157, v118);
      v59 = v156;
      v60 = v54 | 0x100;
    }
    else
    {
      memset(v114, 0, sizeof(v114));
      std::string::_Construct<1,char const *>(v114, "false", 5);
      v61 = v5 | 0x200;
      v87 = v61;
      memset(v113, 0, sizeof(v113));
      std::string::_Construct<1,char const *>(v113, ":", 1);
      v61 |= 0x400u;
      v87 = v61;
      memset(v112, 0, sizeof(v112));
      std::string::_Construct<1,char const *>(v112, "\"", 1);
      v61 |= 0x800u;
      v87 = v61;
      memset(v111, 0, sizeof(v111));
      std::string::_Construct<1,char const *>(v111, "\"", 1);
      v61 |= 0x1000u;
      v87 = v61;
      v62 = std::operator+<char>(v175, v111, "SmilesSidebandOperationId");
      v61 |= 0x2000u;
      v87 = v61;
      LOBYTE(v63) = v86[0];
      std::string::string(v155, v63, v62, v112);
      v61 |= 0x4000u;
      v87 = v61;
      LOBYTE(v64) = v86[0];
      std::string::string(v154, v64, v155, v113);
      v61 |= 0x8000u;
      v87 = v61;
      LOBYTE(v65) = v86[0];
      std::string::string(v153, v65, v154, v114);
      v59 = v153;
      v60 = v61 | 0x10000;
    }
    v87 = v60;
    *(_OWORD *)v132 = *(_OWORD *)v59;
    v133 = *((_OWORD *)v59 + 1);
    *((_QWORD *)v59 + 2) = 0;
    *((_QWORD *)v59 + 3) = 15;
    *v59 = 0;
    v131 = v134;
    if ( *(_BYTE *)(a1 + 1504) )
    {
      memset(v101, 0, sizeof(v101));
      std::string::_Construct<1,char const *>(v101, "true", 4);
      v66 = v60 | 0x20000;
      v87 = v66;
      memset(v109, 0, sizeof(v109));
      std::string::_Construct<1,char const *>(v109, ":", 1);
      v66 |= 0x40000u;
      v87 = v66;
      memset(v108, 0, sizeof(v108));
      std::string::_Construct<1,char const *>(v108, "\"", 1);
      v66 |= 0x80000u;
      v87 = v66;
      memset(v107, 0, sizeof(v107));
      std::string::_Construct<1,char const *>(v107, "\"", 1);
      v66 |= 0x100000u;
      v87 = v66;
      v67 = std::operator+<char>(v174, v107, "autoReconnectTimeoutSupported");
      v66 |= 0x200000u;
      v87 = v66;
      LOBYTE(v68) = v86[0];
      std::string::string(v152, v68, v67, v108);
      v66 |= 0x400000u;
      v87 = v66;
      LOBYTE(v69) = v86[0];
      std::string::string(v151, v69, v152, v109);
      v66 |= 0x800000u;
      v87 = v66;
      LOBYTE(v70) = v86[0];
      std::string::string(v150, v70, v151, v101);
      v71 = 947912702;
      LODWORD(v88) = 947912702;
      v72 = v150;
      v73 = v66 | 0x1000000;
      v87 = v73;
    }
    else
    {
      memset(v106, 0, sizeof(v106));
      std::string::_Construct<1,char const *>(v106, "false", 5);
      v74 = v60 | 0x2000000;
      v87 = v74;
      memset(v105, 0, sizeof(v105));
      std::string::_Construct<1,char const *>(v105, ":", 1);
      v74 |= 0x4000000u;
      v87 = v74;
      memset(v104, 0, sizeof(v104));
      std::string::_Construct<1,char const *>(v104, "\"", 1);
      v74 |= 0x8000000u;
      v87 = v74;
      memset(v103, 0, sizeof(v103));
      std::string::_Construct<1,char const *>(v103, "\"", 1);
      v74 |= 0x10000000u;
      v87 = v74;
      v75 = std::operator+<char>(v173, v103, "autoReconnectTimeoutSupported");
      v74 |= 0x20000000u;
      v87 = v74;
      LOBYTE(v76) = v86[0];
      std::string::string(v149, v76, v75, v104);
      v74 |= 0x40000000u;
      v87 = v74;
      LOBYTE(v77) = v86[0];
      std::string::string(v142, v77, v149, v105);
      v73 = v74 | 0x80000000;
      v87 = v73;
      LOBYTE(v78) = v86[0];
      std::string::string(v147, v78, v142, v106);
      v72 = v147;
      v71 = -1065353217;
      LODWORD(v88) = -1065353217;
    }
    *(_OWORD *)v134 = *(_OWORD *)v72;
    v135 = *((_OWORD *)v72 + 1);
    *((_QWORD *)v72 + 2) = 0;
    *((_QWORD *)v72 + 3) = 15;
    *v72 = 0;
    std::_Integral_to_string<char,unsigned int>(v146, *(unsigned int *)(a1 + 1928));
    v79 = v71 | 0x800000;
    LODWORD(v88) = v79;
    memset(v182, 0, sizeof(v182));
    std::string::_Construct<1,char const *>(v182, ":", 1);
    v89 = 0;
    si128 = 0;
    std::string::_Construct<1,char const *>(&v89, "\"", 1);
    v91 = 0;
    v92 = 0;
    std::string::_Construct<1,char const *>(&v91, "\"", 1);
    v80 = std::operator+<char>(v172, &v91, "SmilesVersion");
    LOBYTE(v81) = v86[0];
    std::string::string(v145, v81, v80, &v89);
    v79 |= 0x1000000u;
    LODWORD(v88) = v79;
    LOBYTE(v82) = v86[0];
    std::string::string(v144, v82, v145, v182);
    v79 |= 0x2000000u;
    LODWORD(v88) = v79;
    LOBYTE(v83) = v86[0];
    std::string::string(v143, v83, v144, v146);
    v79 |= 0x4000000u;
    LODWORD(v88) = v79;
    Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
      (int)v183,
      (int)"RD_CHECKPOINT",
      0,
      (int)"NanoConfigurations",
      "Smiles",
      "Smiles Configurations",
      (__int64)v143,
      (__int64)v134,
      (__int64)v132,
      (__int64)v136,
      (__int64)v141,
      (__int64)v140,
      (__int64)v139,
      (__int64)v138);
    std::string::_Tidy_deallocate(v144);
    std::string::_Tidy_deallocate(v145);
    std::string::_Tidy_deallocate(v172);
    std::string::_Tidy_deallocate(&v91);
    std::string::_Tidy_deallocate(&v89);
    std::string::_Tidy_deallocate(v182);
    std::string::_Tidy_deallocate(v146);
    if ( (v79 & 1) != 0 )
      std::string::_Tidy_deallocate(v147);
    if ( v73 < 0 )
    {
      v73 &= ~0x80000000;
      std::string::_Tidy_deallocate(v142);
    }
    if ( (v73 & 0x40000000) != 0 )
    {
      v73 &= ~0x40000000u;
      std::string::_Tidy_deallocate(v149);
    }
    if ( (v73 & 0x20000000) != 0 )
    {
      v73 &= ~0x20000000u;
      std::string::_Tidy_deallocate(v173);
    }
    if ( (v73 & 0x10000000) != 0 )
    {
      v73 &= ~0x10000000u;
      std::string::_Tidy_deallocate(v103);
    }
    if ( (v73 & 0x8000000) != 0 )
    {
      v73 &= ~0x8000000u;
      std::string::_Tidy_deallocate(v104);
    }
    if ( (v73 & 0x4000000) != 0 )
    {
      v73 &= ~0x4000000u;
      std::string::_Tidy_deallocate(v105);
    }
    if ( (v73 & 0x2000000) != 0 )
    {
      v73 &= ~0x2000000u;
      std::string::_Tidy_deallocate(v106);
    }
    if ( (v73 & 0x1000000) != 0 )
    {
      v73 &= ~0x1000000u;
      std::string::_Tidy_deallocate(v150);
    }
    if ( (v73 & 0x800000) != 0 )
    {
      v73 &= ~0x800000u;
      std::string::_Tidy_deallocate(v151);
    }
    if ( (v73 & 0x400000) != 0 )
    {
      v73 &= ~0x400000u;
      std::string::_Tidy_deallocate(v152);
    }
    if ( (v73 & 0x200000) != 0 )
    {
      v73 &= ~0x200000u;
      std::string::_Tidy_deallocate(v174);
    }
    if ( (v73 & 0x100000) != 0 )
    {
      v73 &= ~0x100000u;
      std::string::_Tidy_deallocate(v107);
    }
    if ( (v73 & 0x80000) != 0 )
    {
      v73 &= ~0x80000u;
      std::string::_Tidy_deallocate(v108);
    }
    if ( (v73 & 0x40000) != 0 )
    {
      v73 &= ~0x40000u;
      std::string::_Tidy_deallocate(v109);
    }
    if ( (v73 & 0x20000) != 0 )
    {
      v73 &= ~0x20000u;
      std::string::_Tidy_deallocate(v101);
    }
    if ( (v73 & 0x10000) != 0 )
      std::string::_Tidy_deallocate(v153);
    if ( (v73 & 0x8000) != 0 )
    {
      LOWORD(v73) = v73 & 0x7FFF;
      std::string::_Tidy_deallocate(v154);
    }
    if ( (v73 & 0x4000) != 0 )
    {
      LOWORD(v73) = v73 & 0xBFFF;
      std::string::_Tidy_deallocate(v155);
    }
    if ( (v73 & 0x2000) != 0 )
    {
      LOWORD(v73) = v73 & 0xDFFF;
      std::string::_Tidy_deallocate(v175);
    }
    if ( (v73 & 0x1000) != 0 )
    {
      LOWORD(v73) = v73 & 0xEFFF;
      std::string::_Tidy_deallocate(v111);
    }
    if ( (v73 & 0x800) != 0 )
    {
      LOWORD(v73) = v73 & 0xF7FF;
      std::string::_Tidy_deallocate(v112);
    }
    if ( (v73 & 0x400) != 0 )
    {
      LOWORD(v73) = v73 & 0xFBFF;
      std::string::_Tidy_deallocate(v113);
    }
    if ( (v73 & 0x200) != 0 )
    {
      LOWORD(v73) = v73 & 0xFDFF;
      std::string::_Tidy_deallocate(v114);
    }
    if ( (v73 & 0x100) != 0 )
      std::string::_Tidy_deallocate(v156);
    if ( (v73 & 0x80u) != 0 )
    {
      LOBYTE(v73) = v73 & 0x7F;
      std::string::_Tidy_deallocate(v157);
    }
    if ( (v73 & 0x40) != 0 )
    {
      LOBYTE(v73) = v73 & 0xBF;
      std::string::_Tidy_deallocate(v158);
    }
    if ( (v73 & 0x20) != 0 )
    {
      LOBYTE(v73) = v73 & 0xDF;
      std::string::_Tidy_deallocate(v176);
    }
    if ( (v73 & 0x10) != 0 )
    {
      LOBYTE(v73) = v73 & 0xEF;
      std::string::_Tidy_deallocate(v115);
    }
    if ( (v73 & 8) != 0 )
    {
      LOBYTE(v73) = v73 & 0xF7;
      std::string::_Tidy_deallocate(v116);
    }
    if ( (v73 & 4) != 0 )
    {
      LOBYTE(v73) = v73 & 0xFB;
      std::string::_Tidy_deallocate(v117);
    }
    if ( (v73 & 2) != 0 )
      std::string::_Tidy_deallocate(v118);
    std::string::_Tidy_deallocate(v159);
    std::string::_Tidy_deallocate(v160);
    std::string::_Tidy_deallocate(v177);
    std::string::_Tidy_deallocate(v119);
    std::string::_Tidy_deallocate(v120);
    std::string::_Tidy_deallocate(v121);
    std::string::_Tidy_deallocate(v161);
    std::string::_Tidy_deallocate(v162);
    std::string::_Tidy_deallocate(v163);
    std::string::_Tidy_deallocate(v178);
    std::string::_Tidy_deallocate(v122);
    std::string::_Tidy_deallocate(v123);
    std::string::_Tidy_deallocate(v93);
    std::string::_Tidy_deallocate(v164);
    std::string::_Tidy_deallocate(v165);
    std::string::_Tidy_deallocate(v166);
    std::string::_Tidy_deallocate(v179);
    std::string::_Tidy_deallocate(v94);
    std::string::_Tidy_deallocate(v95);
    std::string::_Tidy_deallocate(v96);
    std::string::_Tidy_deallocate(v167);
    std::string::_Tidy_deallocate(v168);
    std::string::_Tidy_deallocate(v169);
    std::string::_Tidy_deallocate(v180);
    std::string::_Tidy_deallocate(v97);
    std::string::_Tidy_deallocate(v98);
    std::string::_Tidy_deallocate(v99);
    std::string::_Tidy_deallocate(v170);
    std::string::_Tidy_deallocate(v171);
    std::string::_Tidy_deallocate(v137);
    std::string::_Tidy_deallocate(v181);
    std::string::_Tidy_deallocate(v100);
    std::string::_Tidy_deallocate(v102);
    std::string::_Tidy_deallocate(v110);
    std::string::_Tidy_deallocate(v148);
  }
  v84 = *(volatile signed __int32 **)&v183[2];
  if ( *(_QWORD *)&v183[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v183[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v84)(v84);
      if ( _InterlockedExchangeAdd(v84 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v84 + 8LL))(v84);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1802572a4  mov     [rsp-8+arg_10], rbx
0x1802572a9  push    rbp
0x1802572aa  push    rsi
0x1802572ab  push    rdi
0x1802572ac  push    r12
0x1802572ae  push    r13
0x1802572b0  push    r14
0x1802572b2  push    r15
0x1802572b4  lea     rbp, [rsp-0A90h]
0x1802572bc  mov     eax, 0B90h
0x1802572c1  call    _alloca_probe
0x1802572c6  sub     rsp, rax
0x1802572c9  mov     rax, cs:__security_cookie
0x1802572d0  xor     rax, rsp
0x1802572d3  mov     [rbp+0AC0h+var_40], rax
0x1802572da  mov     r12, rdx
0x1802572dd  mov     rsi, rcx
0x1802572e0  mov     [rbp+0AC0h+var_720], rcx
0x1802572e7  xor     r13d, r13d
0x1802572ea  mov     edi, r13d
0x1802572ed  mov     [rsp+0BC0h+var_B4C], r13d
0x1802572f2  mov     dword ptr [rsp+0BC0h+var_B48], r13d
0x1802572f7  test    r8d, r8d
0x1802572fa  jz      short loc_18025732B
0x1802572fc  lea     rax, ??_8SmilesV3@Dct@Basix@Microsoft@@7B@; const Microsoft::Basix::Dct::SmilesV3::`vbtable'
0x180257303  mov     [rcx+8], rax
0x180257307  mov     [rcx+0C88h], r13
0x18025730e  mov     [rcx+0C90h], r13
0x180257315  lea     rax, ??_7SharedFromThisVirtualBase@Basix@Microsoft@@6B@; const Microsoft::Basix::SharedFromThisVirtualBase::`vftable'
0x18025731c  mov     [rcx+0C80h], rax
0x180257323  lea     edi, [r13+1]
0x180257327  mov     [rsp+0BC0h+var_B4C], edi
0x18025732b  xor     r8d, r8d
0x18025732e  call    ??0?$Smiles@VLinkDataV3@Dct@Basix@Microsoft@@@Dct@Basix@Microsoft@@QEAA@AEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z; Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataV3>::Smiles<Microsoft::Basix::Dct::LinkDataV3>(boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &)
0x180257333  nop
0x180257334  lea     rax, ??_7SmilesV3@Dct@Basix@Microsoft@@6BFindInterfaceBase@detail@123@@; const Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'}
0x18025733b  mov     [rsi], rax
0x18025733e  lea     r15, [rsi+28h]
0x180257342  lea     rax, ??_7SmilesV3@Dct@Basix@Microsoft@@6BDCTBaseChannelImpl@123@@; const Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'}
0x180257349  mov     [r15], rax
0x18025734c  lea     rax, ??_7SmilesV3@Dct@Basix@Microsoft@@6BILinkDataCallback@123@@; const Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::ILinkDataCallback'}
0x180257353  mov     [rsi+440h], rax
0x18025735a  lea     rax, ??_7SmilesV3@Dct@Basix@Microsoft@@6BISmiles@123@@; const Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::ISmiles'}
0x180257361  mov     [rsi+448h], rax
0x180257368  lea     rax, ??_7SmilesV3@Dct@Basix@Microsoft@@6BISmilesLink@123@@; const Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::Dct::ISmilesLink'}
0x18025736f  mov     [rsi+450h], rax
0x180257376  lea     rax, ??_7SmilesV3@Dct@Basix@Microsoft@@6B@; const Microsoft::Basix::Dct::SmilesV3::`vftable'
0x18025737d  mov     [rsi+800h], rax
0x180257384  mov     rax, [rsi+8]
0x180257388  movsxd  rcx, dword ptr [rax+4]
0x18025738c  lea     rax, ??_7SmilesV3@Dct@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::Dct::SmilesV3::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x180257393  mov     [rcx+rsi+8], rax
0x180257398  lea     rcx, [rsi+808h]; this
0x18025739f  call    ??0Summary@SmilesV3@Dct@Basix@Microsoft@@QEAA@XZ; Microsoft::Basix::Dct::SmilesV3::Summary::Summary(void)
0x1802573a4  nop
0x1802573a5  mov     [rsi+8A0h], r13
0x1802573ac  mov     [rsi+8A8h], r13d
0x1802573b3  lea     rbx, [rsi+8C0h]
0x1802573ba  xorps   xmm0, xmm0
0x1802573bd  movups  [rbp+0AC0h+var_B40], xmm0
0x1802573c1  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1802573c9  movdqu  [rbp+0AC0h+var_B30], xmm1
0x1802573ce  mov     byte ptr [rbp+0AC0h+var_B40], r13b
0x1802573d2  call    ?GetDescription@MultiLinkActivity@Instrumentation@Basix@Microsoft@@SAAEBV1234@XZ; Microsoft::Basix::Instrumentation::MultiLinkActivity::GetDescription(void)
0x1802573d7  mov     rdx, rax
0x1802573da  lea     r8, [rbp+0AC0h+var_B40]
0x1802573de  mov     rcx, rbx
0x1802573e1  call    ??0EventBase@Instrumentation@Basix@Microsoft@@IEAA@AEBVRecordDescriptor@123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Instrumentation::EventBase::EventBase(Microsoft::Basix::Instrumentation::RecordDescriptor const &,std::string const &)
0x1802573e6  lea     rax, ??_7?$Event@VMultiLinkActivity@Instrumentation@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@6B@; const Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::Instrumentation::MultiLinkActivity>::`vftable'
0x1802573ed  mov     [rbx], rax
0x1802573f0  lea     rcx, [rbp+0AC0h+var_B40]
0x1802573f4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802573f9  lea     rbx, [rsi+0A00h]
0x180257400  xorps   xmm0, xmm0
0x180257403  movups  [rbp+0AC0h+var_B40], xmm0
0x180257407  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18025740f  movdqu  [rbp+0AC0h+var_B30], xmm1
0x180257414  mov     byte ptr [rbp+0AC0h+var_B40], r13b
0x180257418  call    ?GetDescription@MultiLinkError@Instrumentation@Basix@Microsoft@@SAAEBV1234@XZ; Microsoft::Basix::Instrumentation::MultiLinkError::GetDescription(void)
0x18025741d  mov     rdx, rax
0x180257420  lea     r8, [rbp+0AC0h+var_B40]
0x180257424  mov     rcx, rbx
0x180257427  call    ??0EventBase@Instrumentation@Basix@Microsoft@@IEAA@AEBVRecordDescriptor@123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Instrumentation::EventBase::EventBase(Microsoft::Basix::Instrumentation::RecordDescriptor const &,std::string const &)
0x18025742c  lea     rax, ??_7?$Event@VMultiLinkError@Instrumentation@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@6B@; const Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::Instrumentation::MultiLinkError>::`vftable'
0x180257433  mov     [rbx], rax
0x180257436  lea     rcx, [rbp+0AC0h+var_B40]
0x18025743a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18025743f  mov     [rsi+0B40h], r13
0x180257446  mov     [rsi+0B50h], r13
0x18025744d  mov     [rsi+0B58h], r13
0x180257454  mov     [rsi+0B78h], r13
0x18025745b  mov     [rsi+0B80h], r13w
0x180257463  mov     [rsi+0B88h], r13
0x18025746a  mov     [rsi+0B90h], r13
0x180257471  mov     [rsi+0B98h], r13
0x180257478  mov     [rsi+0BA0h], r13
0x18025747f  mov     [rsi+0BA8h], r13
0x180257486  or      r14, 0FFFFFFFFFFFFFFFFh
0x18025748a  mov     [rsi+0BB0h], r14
0x180257491  mov     qword ptr [rsi+0BB8h], 14h
0x18025749c  mov     [rsi+0BC0h], r13
0x1802574a3  mov     [rsi+0BC8h], r13d
0x1802574aa  mov     [rsi+0BCCh], r13b
0x1802574b1  lea     rax, ??_7Timer@Basix@Microsoft@@6B@; const Microsoft::Basix::Timer::`vftable'
0x1802574b8  mov     [rsi+0BD0h], rax
0x1802574bf  lea     rcx, [rsi+0BD8h]
0x1802574c6  xor     edx, edx
0x1802574c8  call    ?CreateTimerImpl@Basix@Microsoft@@YA?AV?$shared_ptr@VITimer@Basix@Microsoft@@@std@@_N@Z; Microsoft::Basix::CreateTimerImpl(bool)
0x1802574cd  nop
0x1802574ce  lea     rcx, [rsp+0BC0h+var_B48]
0x1802574d3  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1802574d8  mov     rcx, [rax]
0x1802574db  mov     rax, 431BDE82D7B634DBh
0x1802574e5  imul    rcx
0x1802574e8  sar     rdx, 12h
0x1802574ec  mov     rax, rdx
0x1802574ef  shr     rax, 3Fh
0x1802574f3  add     rdx, rax
0x1802574f6  mov     [rsi+0BE8h], rdx
0x1802574fd  mov     [rsi+0BF0h], r13b
0x180257504  mov     [rsi+0BF8h], r13
0x18025750b  mov     [rsi+0C00h], r13
0x180257512  mov     [rsi+0C08h], r13
0x180257519  mov     [rsi+0C10h], r13w
0x180257521  mov     [rsi+0C12h], r13b
0x180257528  mov     [rsi+0C18h], r13
0x18025752f  mov     [rsi+0C20h], r13
0x180257536  mov     [rsi+0C28h], r13w
0x18025753e  lea     rbx, [rsi+0C30h]
0x180257545  mov     [rbx], r13
0x180257548  mov     [rbx+8], r13
0x18025754c  mov     [rbx+10h], r13
0x180257550  mov     [rbx+18h], r13
0x180257554  mov     [rbx+20h], r13
0x180257558  lea     ecx, [r14+11h]; Size
0x18025755c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180257561  mov     [rax+8], r13
0x180257565  mov     [rbx], rax
0x180257568  mov     [rax], rbx
0x18025756b  mov     [rsi+0C58h], r13
0x180257572  mov     rax, 7FFFFFFFFFFFFFFFh
0x18025757c  mov     [rsi+0C60h], rax
0x180257583  mov     [rsi+0C68h], r13w
0x18025758b  xorps   xmm0, xmm0
0x18025758e  movups  [rbp+0AC0h+var_B40], xmm0
0x180257592  xorps   xmm1, xmm1
0x180257595  movdqu  [rbp+0AC0h+var_B30], xmm1
0x18025759a  lea     r8d, [r14+29h]
0x18025759e  lea     rdx, aMicrosoftBasix_454; "Microsoft::Basix::Dct.Smiles.UseSideban"...
0x1802575a5  lea     rcx, [rbp+0AC0h+var_B40]
0x1802575a9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802575ae  nop
0x1802575af  lea     r8, [rbp+0AC0h+var_B40]
0x1802575b3  lea     rdx, [rbp+0AC0h+var_C0]
0x1802575ba  mov     rcx, r15
0x1802575bd  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x1802575c2  nop
0x1802575c3  mov     [rsp+0BC0h+var_B50], r13b
0x1802575c8  lea     rdx, [rsp+0BC0h+var_B50]
0x1802575cd  mov     rcx, [rax+10h]
0x1802575d1  call    ??$get_value@_N@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA_NAEB_N@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(bool const &)
0x1802575d6  mov     [rsi+0C69h], al
0x1802575dc  lea     rcx, [rbp+0AC0h+var_C0]
0x1802575e3  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1802575e8  nop
0x1802575e9  lea     rcx, [rbp+0AC0h+var_B40]
0x1802575ed  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802575f2  xorps   xmm0, xmm0
0x1802575f5  movups  [rbp+0AC0h+var_B40], xmm0
0x1802575f9  xorps   xmm1, xmm1
0x1802575fc  movdqu  [rbp+0AC0h+var_B30], xmm1
0x180257601  lea     r8d, [r14+38h]
0x180257605  lea     rdx, aMicrosoftBasix_261; "Microsoft::Basix::Dct.ICE.Smiles.Receiv"...
0x18025760c  lea     rcx, [rbp+0AC0h+var_B40]
0x180257610  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180257615  nop
0x180257616  lea     r8, [rbp+0AC0h+var_B40]
0x18025761a  lea     rdx, [rbp+0AC0h+var_C0]
0x180257621  mov     rcx, r15
0x180257624  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180257629  nop
0x18025762a  mov     dword ptr [rsp+0BC0h+var_B48], 4
0x180257632  lea     rdx, [rsp+0BC0h+var_B48]
0x180257637  mov     rcx, [rax+10h]
0x18025763b  call    ??$get_value@I@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBAIAEBI@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<uint>(uint const &)
0x180257640  mov     [rsi+0B68h], eax
0x180257646  lea     rcx, [rbp+0AC0h+var_C0]
0x18025764d  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180257652  nop
0x180257653  lea     rcx, [rbp+0AC0h+var_B40]
0x180257657  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18025765c  xorps   xmm0, xmm0
0x18025765f  movups  [rbp+0AC0h+var_B40], xmm0
0x180257663  xorps   xmm1, xmm1
0x180257666  movdqu  [rbp+0AC0h+var_B30], xmm1
0x18025766b  lea     r8d, [r14+3Ch]
0x18025766f  lea     rdx, aMicrosoftBasix_470; "Microsoft::Basix::Dct.ICE.Smiles.SmallL"...
0x180257676  lea     rcx, [rbp+0AC0h+var_B40]
0x18025767a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025767f  nop
0x180257680  lea     r8, [rbp+0AC0h+var_B40]
0x180257684  lea     rdx, [rbp+0AC0h+var_C0]
0x18025768b  mov     rcx, r15
0x18025768e  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180257693  nop
0x180257694  mov     dword ptr [rsp+0BC0h+var_B48], 5
0x18025769c  lea     rdx, [rsp+0BC0h+var_B48]
0x1802576a1  mov     rcx, [rax+10h]
0x1802576a5  call    ??$get_value@I@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBAIAEBI@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<uint>(uint const &)
0x1802576aa  mov     [rsi+0B64h], eax
0x1802576b0  lea     rcx, [rbp+0AC0h+var_C0]
0x1802576b7  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1802576bc  nop
0x1802576bd  lea     rcx, [rbp+0AC0h+var_B40]
0x1802576c1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802576c6  xorps   xmm0, xmm0
0x1802576c9  movups  [rbp+0AC0h+var_B40], xmm0
0x1802576cd  xorps   xmm1, xmm1
0x1802576d0  movdqu  [rbp+0AC0h+var_B30], xmm1
0x1802576d5  lea     r8d, [r14+2Fh]
0x1802576d9  lea     rdx, aMicrosoftBasix_358; "Microsoft::Basix::Dct.ICE.Smiles.MinCou"...
0x1802576e0  lea     rcx, [rbp+0AC0h+var_B40]
0x1802576e4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802576e9  nop
0x1802576ea  lea     r8, [rbp+0AC0h+var_B40]
0x1802576ee  lea     rdx, [rbp+0AC0h+var_C0]
0x1802576f5  mov     rcx, r15
0x1802576f8  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x1802576fd  nop
0x1802576fe  mov     dword ptr [rsp+0BC0h+var_B48], 3
0x180257706  lea     rdx, [rsp+0BC0h+var_B48]
0x18025770b  mov     rcx, [rax+10h]
0x18025770f  call    ??$get_value@I@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBAIAEBI@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<uint>(uint const &)
0x180257714  mov     [rsi+0B60h], eax
0x18025771a  lea     rcx, [rbp+0AC0h+var_C0]
0x180257721  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180257726  nop
0x180257727  lea     rcx, [rbp+0AC0h+var_B40]
0x18025772b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180257730  xorps   xmm0, xmm0
0x180257733  movups  [rbp+0AC0h+var_B40], xmm0
0x180257737  xorps   xmm1, xmm1
0x18025773a  movdqu  [rbp+0AC0h+var_B30], xmm1
0x18025773f  lea     r8d, [r14+2Dh]
0x180257743  lea     rdx, aMicrosoftBasix_403; "Microsoft::Basix::Dct.ICE.Smiles.TestTi"...
0x18025774a  lea     rcx, [rbp+0AC0h+var_B40]
0x18025774e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180257753  nop
0x180257754  lea     r8, [rbp+0AC0h+var_B40]
0x180257758  lea     rdx, [rbp+0AC0h+var_C0]
0x18025775f  mov     rcx, r15
0x180257762  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180257767  nop
0x180257768  movsd   xmm0, cs:__real@3ff0000000000000
0x180257770  movsd   [rsp+0BC0h+var_B48], xmm0
0x180257776  lea     rdx, [rsp+0BC0h+var_B48]
0x18025777b  mov     rcx, [rax+10h]
0x18025777f  call    ??$get_value@N@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBANAEBN@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<double>(double const &)
0x180257784  mulsd   xmm0, cs:__real@408f400000000000
0x18025778c  xor     ecx, ecx
0x18025778e  movsd   xmm1, cs:__real@43e0000000000000
0x180257796  comisd  xmm0, xmm1
0x18025779a  jb      short loc_1802577B3
0x18025779c  subsd   xmm0, xmm1
0x1802577a0  comisd  xmm0, xmm1
0x1802577a4  jnb     short loc_1802577B3
0x1802577a6  mov     rax, 8000000000000000h
0x1802577b0  mov     rcx, rax
0x1802577b3  cvttsd2si rax, xmm0
0x1802577b8  add     rax, rcx
0x1802577bb  mov     [rsi+0B70h], rax
0x1802577c2  lea     rcx, [rbp+0AC0h+var_C0]
0x1802577c9  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1802577ce  nop
0x1802577cf  lea     rcx, [rbp+0AC0h+var_B40]
0x1802577d3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802577d8  mov     ebx, 978h
0x1802577dd  mov     ecx, ebx; Size
0x1802577df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802577e4  mov     [rsp+0BC0h+var_B48], rax
0x1802577e9  test    rax, rax
0x1802577ec  jz      short loc_180257800
0x1802577ee  movsd   xmm1, cs:__real@4082c00000000000
0x1802577f6  mov     rcx, rax
0x1802577f9  call    ??0?$SlidingStats@N$0BE@$00$00@Algorithm@Basix@Microsoft@@QEAA@N@Z; Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::SlidingStats<double,20,1,1>(double)
0x1802577fe  jmp     short loc_180257803
0x180257800  mov     rax, r13
0x180257803  mov     rcx, [rsi+0B50h]; void *
0x18025780a  mov     [rsi+0B50h], rax
0x180257811  test    rcx, rcx
0x180257814  jz      short loc_18025781E
0x180257816  mov     rdx, rbx; struct std::nothrow_t *
0x180257819  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18025781e  mov     ebx, 320h
0x180257823  mov     ecx, ebx; Size
0x180257825  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18025782a  mov     [rsp+0BC0h+var_B48], rax
0x18025782f  test    rax, rax
0x180257832  jz      short loc_180257846
0x180257834  movsd   xmm1, cs:__real@4024000000000000
  ... truncated ...
```

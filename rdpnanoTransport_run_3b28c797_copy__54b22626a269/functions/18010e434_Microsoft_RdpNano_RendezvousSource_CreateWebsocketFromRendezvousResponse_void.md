# Microsoft::RdpNano::RendezvousSource::CreateWebsocketFromRendezvousResponse(void)

- ea: `0x18010e434`
- end: `0x18010fa7e`
- name: `?CreateWebsocketFromRendezvousResponse@RendezvousSource@RdpNano@Microsoft@@AEAAXXZ`
- size: `5706`
- prototype: `void __fastcall(Microsoft::RdpNano::RendezvousSource *__hidden this)`
- caller_count: `2`
- callee_count: `46`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010d728`
- `0x180112440`

## callees

- `0x18000d9c0`
- `0x18000da90`
- `0x180015bb8`
- `0x18001902c`
- `0x18001dad8`
- `0x18001f970`
- `0x180021850`
- `0x180021a00`
- `0x180024568`
- `0x180024c14`
- `0x180028820`
- `0x1800ba94c`
- `0x1800f64ec`
- `0x1800f91d0`
- `0x180105524`
- `0x180105ae0`
- `0x180106038`
- `0x180107190`
- `0x180107ad8`
- `0x180107b8c`
- `0x1801083b8`
- `0x1801084a0`
- `0x180108578`
- `0x18010d048`
- `0x18010e434`
- `0x180113258`
- `0x1801134fc`
- `0x1801b0ab4`
- `0x1801c52ac`
- `0x1801c6244`
- `0x1801c728c`
- `0x1801c8efc`
- `0x1802f6b1c`
- `0x1802f7604`
- `0x1802f7e0c`
- `0x1802fa2b4`
- `0x1802fa438`
- `0x1802fb360`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x180375c40`
- `0x180376380`

## string_xrefs

- `0x18010e567`: `clientHeartBeatReply.uri`
- `0x18010e4a3`: `gatewayLoadBalancerToken`
- `0x18010e883`: `gatewayConnectionToken`
- `0x18010e8d2`: `RDmiGatewayToken`
- `0x18010ee1f`: `CreateWebsocketFromRendezvousResponse: creating websocket to %s, connectionId=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=98
void __fastcall Microsoft::RdpNano::RendezvousSource::CreateWebsocketFromRendezvousResponse(
        Microsoft::RdpNano::RendezvousSource *this)
{
  char *v2; // r15
  __int128 *v3; // rax
  __int128 *v4; // rax
  __int128 *v5; // rax
  __int128 *v6; // rax
  struct Microsoft::Basix::HTTP::Headers *Headers; // rax
  struct Microsoft::Basix::HTTP::Headers *v8; // rax
  struct Microsoft::Basix::HTTP::Headers *v9; // rbx
  struct Microsoft::Basix::HTTP::Headers *v10; // rbx
  __int64 v11; // rax
  struct Microsoft::Basix::HTTP::Headers *v12; // rbx
  struct Microsoft::Basix::HTTP::Headers *v13; // rdi
  __int128 *v14; // rcx
  __int64 v15; // rbx
  struct Microsoft::Basix::HTTP::Headers *v16; // rdi
  __int128 *v17; // rcx
  __int64 v18; // rbx
  struct Microsoft::Basix::HTTP::Headers *v19; // rbx
  struct Microsoft::Basix::HTTP::Headers *v20; // rdi
  __m128i *v21; // r8
  int v22; // ebx
  Microsoft::RdpNano::RendezvousSource::RendezvousContext *v23; // rax
  __int64 v24; // rax
  __int128 *v25; // rax
  __m128i v26; // xmm6
  __int64 Property; // rax
  __int64 v28; // r8
  volatile signed __int32 *v29; // xmm1_8
  __int64 v30; // rax
  __int128 *v31; // rax
  __int64 *v32; // rax
  const char *v33; // r9
  __int64 v34; // rdi
  _QWORD *v35; // rbx
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rax
  char v38; // bl
  Microsoft::RdpNano::RendezvousSource::RendezvousContext *v39; // rax
  __int64 v40; // rax
  __int64 *v41; // rdx
  __int128 *v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, Microsoft::RdpNano::RendezvousSource::RendezvousContext **, __m128i *, __int128 *, __int128 *); // rbx
  unsigned __int64 *v46; // rax
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // rcx
  volatile signed __int32 *v49; // rbx
  volatile signed __int32 *v50; // rbx
  Microsoft::RdpNano::RendezvousSource::RendezvousContext *v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, __int128 *, __m128i *, __int128 *, __int128 *); // rbx
  unsigned __int64 *v56; // rax
  unsigned __int64 v57; // rdx
  unsigned __int64 v58; // rcx
  volatile signed __int32 *v59; // rbx
  volatile signed __int32 *v60; // rbx
  Microsoft::RdpNano::RendezvousSource::RendezvousContext *v61; // rax
  __int64 v62; // rax
  __int128 *v63; // rax
  __int128 *v64; // rax
  __int128 *v65; // rax
  __int64 v66; // rbx
  __int128 *v67; // rcx
  __int128 *v68; // rax
  __int128 *v69; // rax
  __int64 v70; // rbx
  __int128 *v71; // rcx
  __int128 *v72; // rax
  __int64 v73; // rbx
  __int128 *v74; // rcx
  __int128 *v75; // rax
  __int64 v76; // rbx
  __int64 v77; // r8
  __int64 v78; // r9
  const char *v79; // rdx
  int v80; // eax
  __int64 v81; // rcx
  Microsoft::RdpNano::RendezvousSource::RendezvousContext *v82; // rdi
  __int64 v83; // rdx
  volatile signed __int32 *v84; // rdi
  volatile signed __int32 *v85; // rbx
  volatile signed __int32 *v86; // rbx
  char v87; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v88; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v89; // [rsp+58h] [rbp-A8h]
  __int64 v90; // [rsp+68h] [rbp-98h]
  __int128 *v91; // [rsp+70h] [rbp-90h]
  __int128 v92; // [rsp+78h] [rbp-88h] BYREF
  __int128 v93; // [rsp+88h] [rbp-78h]
  __int128 v94; // [rsp+98h] [rbp-68h] BYREF
  __int128 v95; // [rsp+A8h] [rbp-58h]
  char v96; // [rsp+B8h] [rbp-48h]
  __int128 *v97; // [rsp+C0h] [rbp-40h]
  __int128 v98; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v99; // [rsp+D8h] [rbp-28h]
  char v100; // [rsp+E8h] [rbp-18h]
  __int128 *v101; // [rsp+F0h] [rbp-10h]
  __int128 v102; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v103; // [rsp+108h] [rbp+8h]
  char v104; // [rsp+118h] [rbp+18h]
  __int128 *v105; // [rsp+120h] [rbp+20h]
  int v106; // [rsp+128h] [rbp+28h]
  __m128i v107; // [rsp+130h] [rbp+30h] BYREF
  __int128 v108; // [rsp+140h] [rbp+40h]
  __int64 v109; // [rsp+150h] [rbp+50h] BYREF
  char v110; // [rsp+158h] [rbp+58h]
  _BYTE v111[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v112[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v113[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v114[40]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v115[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v116[32]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v117[40]; // [rsp+228h] [rbp+128h] BYREF
  Microsoft::RdpNano::RendezvousSource::RendezvousContext *v118[2]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int128 v119; // [rsp+260h] [rbp+160h] BYREF
  __m128i v120; // [rsp+270h] [rbp+170h] BYREF
  __int128 v121; // [rsp+280h] [rbp+180h] BYREF
  _QWORD v122[2]; // [rsp+290h] [rbp+190h] BYREF
  __m128i v123; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v124; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v125; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v126; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v127; // [rsp+2E0h] [rbp+1E0h]
  char v128; // [rsp+2F0h] [rbp+1F0h]
  __int128 *v129; // [rsp+2F8h] [rbp+1F8h]
  __int128 v130; // [rsp+300h] [rbp+200h] BYREF
  _QWORD v131[4]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v132[32]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v133[384]; // [rsp+350h] [rbp+250h] BYREF

  v106 = 0;
  v2 = (char *)this + 392;
  v126 = 0;
  v127 = 0;
  std::string::_Construct<1,char const *>(&v126, "gatewayLoadBalancerToken", 24);
  v128 = 46;
  v3 = &v126;
  if ( *((_QWORD *)&v127 + 1) > 0xFu )
    v3 = (__int128 *)v126;
  v129 = v3;
  boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(v2, v132, &v126);
  std::string::_Tidy_deallocate(&v126);
  std::_Hash<std::_Umap_traits<std::string,unsigned short,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,unsigned short>>,0>>::_Try_emplace<std::string const &,unsigned short &>(
    (char *)this + 592,
    &v109,
    v132,
    (char *)this + 656);
  if ( v110 )
    ++*((_WORD *)this + 328);
  v92 = 0;
  v93 = 0;
  std::string::_Construct<1,char const *>(&v92, (const char *)&Str1, 0);
  v88 = 0;
  v89 = 0;
  std::string::_Construct<1,char const *>(&v88, "clientHeartBeatReply.uri", 24);
  LOBYTE(v90) = 46;
  v4 = &v88;
  if ( *((_QWORD *)&v89 + 1) > 0xFu )
    v4 = (__int128 *)v88;
  v91 = v4;
  boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
    v2,
    &v126,
    &v88,
    &v92);
  std::string::_Tidy_deallocate(&v88);
  std::string::_Tidy_deallocate(&v92);
  v118[0] = 0;
  v94 = 0;
  v95 = 0;
  std::string::_Construct<1,char const *>(&v94, "clientHeartBeatReply.reportInTime", 33);
  v96 = 46;
  v5 = &v94;
  if ( *((_QWORD *)&v95 + 1) > 0xFu )
    v5 = (__int128 *)v94;
  v97 = v5;
  boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::chrono::duration<__int64,std::ratio<1,1000>>>(
    v2,
    v122,
    &v94,
    v118);
  std::string::_Tidy_deallocate(&v94);
  v94 = 0;
  v95 = 0;
  std::string::_Construct<1,char const *>(&v94, "gatewayLocation", 15);
  v96 = 46;
  v6 = &v94;
  if ( *((_QWORD *)&v95 + 1) > 0xFu )
    v6 = (__int128 *)v94;
  v97 = v6;
  boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(v2, v131, &v94);
  std::string::_Tidy_deallocate(&v94);
  memset(v133, 0, 0x178u);
  Microsoft::Basix::HTTP::URI::URI(v111, v131);
  Microsoft::Basix::HTTP::Request::Request(v133, v111, &Microsoft::Basix::HTTP::Request::Get);
  std::string::_Tidy_deallocate(v117);
  std::string::_Tidy_deallocate(v116);
  std::string::_Tidy_deallocate(v115);
  std::string::_Tidy_deallocate(v114);
  std::string::_Tidy_deallocate(v113);
  std::string::_Tidy_deallocate(v112);
  std::string::_Tidy_deallocate(v111);
  Headers = Microsoft::Basix::HTTP::Request::GetHeaders((Microsoft::Basix::HTTP::Request *)v133);
  Microsoft::Basix::HTTP::Headers::Set(
    Headers,
    Microsoft::Basix::HTTP::Headers::UserAgent,
    Microsoft::RdpNano::FakeUserAgent);
  v8 = Microsoft::Basix::HTTP::Request::GetHeaders((Microsoft::Basix::HTTP::Request *)v133);
  Microsoft::Basix::HTTP::Headers::Set(v8, Microsoft::RdpNano::X_MS_User_Agent, Microsoft::RdpNano::FakeUserAgent);
  v9 = Microsoft::Basix::HTTP::Request::GetHeaders((Microsoft::Basix::HTTP::Request *)v133);
  v92 = 0;
  v93 = 0;
  std::string::_Construct<1,char const *>(&v92, "Cookie", 6);
  Microsoft::Basix::HTTP::Headers::Add(v9, &v92, v132);
  std::string::_Tidy_deallocate(&v92);
  v10 = Microsoft::Basix::HTTP::Request::GetHeaders((Microsoft::Basix::HTTP::Request *)v133);
  v11 = Microsoft::Basix::ToStringWithoutBrackets(&v88, (char *)this + 472);
  Microsoft::Basix::HTTP::Headers::Set(v10, Microsoft::RdpNano::X_MS_Correlation_Id, v11);
  std::string::_Tidy_deallocate(&v88);
  v12 = Microsoft::Basix::HTTP::Request::GetHeaders((Microsoft::Basix::HTTP::Request *)v133);
  v107 = 0;
  v108 = 0;
  std::string::_Construct<1,char const *>(&v107, "CONNID", 6);
  v92 = 0;
  v93 = 0;
  std::string::_Construct<1,char const *>(&v92, "RDG-Auth-Scheme", 15);
  Microsoft::Basix::HTTP::Headers::Add(v12, &v92, &v107);
  std::string::_Tidy_deallocate(&v92);
  std::string::_Tidy_deallocate(&v107);
  v13 = Microsoft::Basix::HTTP::Request::GetHeaders((Microsoft::Basix::HTTP::Request *)v133);
  v94 = 0;
  v95 = 0;
  std::string::_Construct<1,char const *>(&v94, "gatewayConnectionToken", 22);
  v96 = 46;
  v14 = &v94;
  if ( *((_QWORD *)&v95 + 1) > 0xFu )
    v14 = (__int128 *)v94;
  v97 = v14;
  v15 = boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
          v2,
          &v88,
          &v94);
  v92 = 0;
  v93 = 0;
  std::string::_Construct<1,char const *>(&v92, "RDmiGatewayToken", 16);
  Microsoft::Basix::HTTP::Headers::Add(v13, &v92, v15);
  std::string::_Tidy_deallocate(&v92);
  std::string::_Tidy_deallocate(&v88);
  std::string::_Tidy_deallocate(&v94);
  v16 = Microsoft::Basix::HTTP::Request::GetHeaders((Microsoft::Basix::HTTP::Request *)v133);
  v94 = 0;
  v95 = 0;
  std::string::_Construct<1,char const *>(&v94, "connectionId", 12);
  v96 = 46;
  v17 = &v94;
  if ( *((_QWORD *)&v95 + 1) > 0xFu )
    v17 = (__int128 *)v94;
  v97 = v17;
  v18 = boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
          v2,
          &v88,
          &v94);
  v92 = 0;
  v93 = 0;
  std::string::_Construct<1,char const *>(&v92, "RDG-Connection-Id", 17);
  Microsoft::Basix::HTTP::Headers::Add(v16, &v92, v18);
  std::string::_Tidy_deallocate(&v92);
  std::string::_Tidy_deallocate(&v88);
  std::string::_Tidy_deallocate(&v94);
  v19 = Microsoft::Basix::HTTP::Request::GetHeaders((Microsoft::Basix::HTTP::Request *)v133);
  v92 = 0;
  v93 = 0;
  std::string::_Construct<1,char const *>(&v92, "ms-wvd-activity-hint", 20);
  Microsoft::Basix::HTTP::Headers::Add(v19, &v92, (char *)this + 520);
  std::string::_Tidy_deallocate(&v92);
  v20 = Microsoft::Basix::HTTP::Request::GetHeaders((Microsoft::Basix::HTTP::Request *)v133);
  if ( *((_BYTE *)this + 560) )
  {
    v107 = 0;
    v108 = 0;
    std::string::_Construct<1,char const *>(&v107, "server", 6);
    v21 = &v107;
    v22 = 17;
  }
  else
  {
    v92 = 0;
    v93 = 0;
    std::string::_Construct<1,char const *>(&v92, "client", 6);
    v21 = (__m128i *)&v92;
    v22 = 34;
  }
  v106 = v22;
  Microsoft::Basix::HTTP::Headers::Set(v20, qword_18053D430, v21);
  if ( (v22 & 2) != 0 )
  {
    LOBYTE(v22) = v22 & 0xFD;
    std::string::_Tidy_deallocate(&v92);
  }
  if ( (v22 & 1) != 0 )
    std::string::_Tidy_deallocate(&v107);
  v124 = 0u;
  v23 = (Microsoft::RdpNano::RendezvousSource::RendezvousContext *)operator new(0x20u);
  v118[0] = v23;
  if ( v23 )
    v24 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v23);
  else
    v24 = 0;
  *((_QWORD *)&v124 + 1) = v24;
  v87 = 1;
  v88 = 0;
  v89 = 0;
  std::string::_Construct<1,char const *>(&v88, "Microsoft::Basix::Dct.ICE.Smiles.Enabled", 40);
  LOBYTE(v90) = 46;
  v25 = &v88;
  if ( *((_QWORD *)&v89 + 1) > 0xFu )
    v25 = (__int128 *)v88;
  v91 = v25;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<bool>(&v124, &v88, &v87);
  std::string::_Tidy_deallocate(&v88);
  v123 = 0;
  Microsoft::Basix::HTTP::URI::URI(v111, v131);
  Microsoft::Basix::Dct::HTTPClientContextFactory::CreateContext((char *)this + 224, &v123, v111, &v124);
  std::string::_Tidy_deallocate(v117);
  std::string::_Tidy_deallocate(v116);
  std::string::_Tidy_deallocate(v115);
  std::string::_Tidy_deallocate(v114);
  std::string::_Tidy_deallocate(v113);
  std::string::_Tidy_deallocate(v112);
  std::string::_Tidy_deallocate(v111);
  v26 = 0;
  v107 = 0;
  if ( v123.m128i_i64[1] )
  {
    v26 = v123;
    v107 = v123;
    _InterlockedAdd((volatile signed __int32 *)(v123.m128i_i64[1] + 12), 1u);
  }
  v130 = 0;
  v98 = 0;
  v99 = 0;
  std::string::_Construct<1,char const *>(&v98, (const char *)&Str1, 0);
  Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, &v92, &v98);
  LOBYTE(v28) = v87;
  Microsoft::Basix::Containers::PTreeResult<boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>>::As(
    Property,
    &v130,
    v28);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v92);
  std::string::_Tidy_deallocate(&v98);
  v125 = 0;
  v118[0] = (Microsoft::RdpNano::RendezvousSource::RendezvousContext *)&v120;
  v120 = 0;
  v29 = (volatile signed __int32 *)_mm_srli_si128(v26, 8).m128i_u64[0];
  if ( v29 )
  {
    v120 = v26;
    _InterlockedAdd(v29 + 3, 1u);
  }
  v92 = 0;
  v93 = 0;
  std::string::_Construct<1,char const *>(&v92, "Microsoft::Basix::Dct.WebSocket.HttpRequest", 43);
  v30 = Microsoft::Basix::Containers::AnyPTreeAddPairs<Microsoft::Basix::HTTP::Request,char const *,std::weak_ptr<Microsoft::Basix::Dct::HTTPClientContext>,char const *,unsigned int>(
          (unsigned int)&v130,
          (unsigned int)&v92,
          (unsigned int)v133,
          (unsigned int)"Microsoft::Basix::Dct.WebSocket.HttpClientContext",
          (__int64)&v120,
          (__int64)"Microsoft::Basix::Dct.Tcp.ConnectTimeoutMs",
          2000);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::basic_ptree<std::string,boost::any,std::less<std::string>>(
    &v125,
    v30);
  std::string::_Tidy_deallocate(&v92);
  v119 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v119);
  if ( (_QWORD)v119 && *(_BYTE *)(v119 + 128) )
  {
    v98 = 0;
    v99 = 0;
    std::string::_Construct<1,char const *>(&v98, (const char *)&Str1, 0);
    v94 = 0;
    v95 = 0;
    std::string::_Construct<1,char const *>(&v94, "connectionId", 12);
    v96 = 46;
    v31 = &v94;
    if ( *((_QWORD *)&v95 + 1) > 0xFu )
      v31 = (__int128 *)v94;
    v97 = v31;
    v32 = (__int64 *)boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
                       v2,
                       &v88,
                       &v94,
                       &v98);
    v34 = (__int64)v32;
    if ( (unsigned __int64)v32[3] > 0xF )
      v34 = *v32;
    v35 = v131;
    if ( v131[3] > 0xFu )
      LODWORD(v35) = v131[0];
    v92 = 0;
    v93 = 0;
    std::string::_Construct<1,char const *>(
      &v92,
      "CreateWebsocketFromRendezvousResponse: creating websocket to %s, connectionId=%s",
      (const char *)0x50,
      v33);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *>(
      (unsigned int)&v119,
      (unsigned int)"RENDEZVOUS",
      (unsigned int)&v92,
      (_DWORD)v35,
      v34);
    std::string::_Tidy_deallocate(&v92);
    std::string::_Tidy_deallocate(&v88);
    std::string::_Tidy_deallocate(&v94);
    std::string::_Tidy_deallocate(&v98);
  }
  v36 = (volatile signed __int32 *)*((_QWORD *)&v119 + 1);
  if ( *((_QWORD *)&v119 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v119 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
      if ( !_InterlockedDecrement(v36 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
  v119 = 0;
  v98 = 0;
  v99 = 0;
  std::string::_Construct<1,char const *>(&v98, "Microsoft::Basix::Dct.Rendezvous.UseOsWebsocketApi", 50);
  v37 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, &v92, &v98);
  v87 = 0;
  v38 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
          *(_QWORD *)(v37 + 16),
          &v87);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v92);
  std::string::_Tidy_deallocate(&v98);
  *(_QWORD *)&v98 = 0;
  v120 = 0;
  if ( v38 )
  {
    v39 = (Microsoft::RdpNano::RendezvousSource::RendezvousContext *)operator new(0x20u);
    v118[0] = v39;
    if ( v39 )
      v40 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v39);
    else
      v40 = 0;
    *((_QWORD *)&v98 + 1) = v40;
    Microsoft::Basix::Dct::DCTFactory::GetWellKnownStackDescription(&v120, 16, &v98);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v98);
    v88 = 0;
    v89 = 0;
    v41 = &Microsoft::Basix::Dct::DCTFactory::ComponentTypeKey;
    if ( (unsigned __int64)qword_18053DE10 > 0xF )
      v41 = (__int64 *)Microsoft::Basix::Dct::DCTFactory::ComponentTypeKey;
    std::string::_Construct<2,char const *>(&v88, v41, qword_18053DE08);
    LOBYTE(v90) = 46;
    v42 = &v88;
    if ( *((_QWORD *)&v89 + 1) > 0xFu )
      v42 = (__int128 *)v88;
    v91 = v42;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<char [17]>(
      &v120,
      &v88,
      "WinHttpWebSocket");
    std::string::_Tidy_deallocate(&v88);
    v43 = Microsoft::Basix::Dct::DCTFactory::GlobalFactory(&v92);
    v44 = *(_QWORD *)v43;
    v45 = *(__int64 (__fastcall **)(__int64, Microsoft::RdpNano::RendezvousSource::RendezvousContext **, __m128i *, __int128 *, __int128 *))(**(_QWORD **)v43 + 24LL);
    v94 = 0;
    v95 = 0;
    std::string::_Construct<1,char const *>(&v94, "rendezvousWinHttp", 17);
    v46 = (unsigned __int64 *)v45(v44, v118, &v120, &v94, &v125);
    v47 = *v46;
    v48 = v46[1];
    *v46 = 0;
    v46[1] = 0;
    v119 = __PAIR128__(v48, v47);
    v49 = (volatile signed __int32 *)v118[1];
    if ( v118[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v118[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
        if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
      }
    }
    std::string::_Tidy_deallocate(&v94);
    v50 = (volatile signed __int32 *)*((_QWORD *)&v92 + 1);
    if ( *((_QWORD *)&v92 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v92 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
        if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
      }
    }
  }
  else
  {
    v51 = (Microsoft::RdpNano::RendezvousSource::RendezvousContext *)operator new(0x20u);
    v118[0] = v51;
    if ( v51 )
      v52 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v51);
    else
      v52 = 0;
    *((_QWORD *)&v98 + 1) = v52;
    v94 = 0;
    v95 = 0;
    std::string::_Construct<1,char const *>(&v94, "WebSocket", 9);
    Microsoft::Basix::Dct::DCTFactory::BeginStack(&v120, &v94, &v98);
    std::string::_Tidy_deallocate(&v94);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v98);
    v53 = Microsoft::Basix::Dct::DCTFactory::GlobalFactory(v118);
    v54 = *(_QWORD *)v53;
    v55 = *(__int64 (__fastcall **)(__int64, __int128 *, __m128i *, __int128 *, __int128 *))(**(_QWORD **)v53 + 24LL);
    v88 = 0;
    v89 = 0;
    std::string::_Construct<1,char const *>(&v88, "rendezvous", 10);
    v56 = (unsigned __int64 *)v55(v54, &v92, &v120, &v88, &v125);
    v57 = *v56;
    v58 = v56[1];
    *v56 = 0;
    v56[1] = 0;
    v119 = __PAIR128__(v58, v57);
    v59 = (volatile signed __int32 *)*((_QWORD *)&v92 + 1);
    if ( *((_QWORD *)&v92 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v92 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
        if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
      }
    }
    std::string::_Tidy_deallocate(&v88);
    v60 = (volatile signed __int32 *)v118[1];
    if ( v118[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v118[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
        if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
      }
    }
  }
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v120);
  v121 = 0u;
  v61 = (Microsoft::RdpNano::RendezvousSource::RendezvousContext *)operator new(0x20u);
  v118[0] = v61;
  if ( v61 )
    v62 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v61);
  else
    v62 = 0;
  *((_QWORD *)&v121 + 1) = v62;
  v88 = 0;
  v89 = 0;
  std::string::_Construct<1,char const *>(&v88, "TransportTypeServer", 19);
  LOBYTE(v90) = 46;
  v63 = &v88;
  if ( *((_QWORD *)&v89 + 1) > 0xFu )
    v63 = (__int128 *)v88;
  v91 = v63;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<char [10]>(
    &v121,
    &v88,
    "WEBSOCKET");
  std::string::_Tidy_deallocate(&v88);
  v88 = 0;
  v89 = 0;
  std::string::_Construct<1,char const *>(&v88, "TransportTypeClient", 19);
  LOBYTE(v90) = 46;
  v64 = &v88;
  if ( *((_QWORD *)&v89 + 1) > 0xFu )
    v64 = (__int128 *)v88;
  v91 = v64;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<char [10]>(
    &v121,
    &v88,
    "WEBSOCKET");
  std::string::_Tidy_deallocate(&v88);
  v88 = 0;
  v89 = 0;
  std::string::_Construct<1,char const *>(&v88, (const char *)&Str1, 0);
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "connectionId", 12);
  v104 = 46;
  v65 = &v102;
  if ( *((_QWORD *)&v103 + 1) > 0xFu )
    v65 = (__int128 *)v102;
  v105 = v65;
  v66 = boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
          v2,
          &v94,
          &v102,
          &v88);
  v98 = 0;
  v99 = 0;
  std::string::_Construct<1,char const *>(&v98, "GatewayConnectionID", 19);
  v100 = 46;
  v67 = &v98;
  if ( *((_QWORD *)&v99 + 1) > 0xFu )
    v67 = (__int128 *)v98;
  v101 = v67;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v121, &v98, v66);
  std::string::_Tidy_deallocate(&v98);
  std::string::_Tidy_deallocate(&v94);
  std::string::_Tidy_deallocate(&v102);
  std::string::_Tidy_deallocate(&v88);
  std::_Integral_to_string<char,int>(&v88, *(unsigned __int16 *)(v109 + 48));
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "GatewayInstanceID", 17);
  v104 = 46;
  v68 = &v102;
  if ( *((_QWORD *)&v103 + 1) > 0xFu )
    v68 = (__int128 *)v102;
  v105 = v68;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v121, &v102, &v88);
  std::string::_Tidy_deallocate(&v102);
  std::string::_Tidy_deallocate(&v88);
  v88 = 0;
  v89 = 0;
  std::string::_Construct<1,char const *>(&v88, (const char *)&Str1, 0);
  v98 = 0;
  v99 = 0;
  std::string::_Construct<1,char const *>(&v98, "gatewayDiagnosticsInfo.gatewayCluster", 37);
  v100 = 46;
  v69 = &v98;
  if ( *((_QWORD *)&v99 + 1) > 0xFu )
    v69 = (__int128 *)v98;
  v101 = v69;
  v70 = boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
          v2,
          &v94,
          &v98,
          &v88);
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "GatewayCluster", 14);
  v104 = 46;
  v71 = &v102;
  if ( *((_QWORD *)&v103 + 1) > 0xFu )
    v71 = (__int128 *)v102;
  v105 = v71;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v121, &v102, v70);
  std::string::_Tidy_deallocate(&v102);
  std::string::_Tidy_deallocate(&v94);
  std::string::_Tidy_deallocate(&v98);
  std::string::_Tidy_deallocate(&v88);
  v88 = 0;
  v89 = 0;
  std::string::_Construct<1,char const *>(&v88, (const char *)&Str1, 0);
  v98 = 0;
  v99 = 0;
  std::string::_Construct<1,char const *>(&v98, "gatewayRegion", 13);
  v100 = 46;
  v72 = &v98;
  if ( *((_QWORD *)&v99 + 1) > 0xFu )
    v72 = (__int128 *)v98;
  v101 = v72;
  v73 = boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
          v2,
          &v94,
          &v98,
          &v88);
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "GatewayRegion", 13);
  v104 = 46;
  v74 = &v102;
  if ( *((_QWORD *)&v103 + 1) > 0xFu )
    v74 = (__int128 *)v102;
  v105 = v74;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v121, &v102, v73);
  std::string::_Tidy_deallocate(&v102);
  std::string::_Tidy_deallocate(&v94);
  std::string::_Tidy_deallocate(&v98);
  std::string::_Tidy_deallocate(&v88);
  v88 = 0;
  v89 = 0;
  std::string::_Construct<1,char const *>(&v88, (const char *)&Str1, 0);
  v102 = 0;
  v103 = 0;
  std::string::_Construct<1,char const *>(&v102, "clientIpAddress", 15);
  v104 = 46;
  v75 = &v102;
  if ( *((_QWORD *)&v103 + 1) > 0xFu )
    v75 = (__int128 *)v102;
  v105 = v75;
  v76 = boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
          v2,
          &v94,
          &v102,
          &v88);
  v79 = "NatIPClient";
  if ( *((_BYTE *)this + 560) )
    v79 = "NatIPServer";
  LOBYTE(v78) = v87;
  LOBYTE(v77) = 46;
  boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
    &v98,
    v79,
    v77,
    v78);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v121, &v98, v76);
  std::string::_Tidy_deallocate(&v98);
  std::string::_Tidy_deallocate(&v94);
  std::string::_Tidy_deallocate(&v102);
  std::string::_Tidy_deallocate(&v88);
  *(_OWORD *)v118 = 0;
  v80 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::RdpNano::RendezvousSource>(
          (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
          &v92);
  std::make_shared<Microsoft::RdpNano::RendezvousSource::RendezvousContext,std::weak_ptr<Microsoft::RdpNano::RendezvousSource>,std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::shared_ptr<Microsoft::Basix::Dct::HTTPClientContext>,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> &,bool &,std::string,std::chrono::duration<__int64,std::ratio<1,1000>> &>(
    (unsigned int)v118,
    v80,
    (unsigned int)&v119,
    (unsigned int)&v123,
    (__int64)&v121,
    (__int64)this + 560,
    (__int64)&v126,
    (__int64)v122);
  v81 = *((_QWORD *)&v92 + 1);
  if ( *((_QWORD *)&v92 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v92 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 8LL))(v81);
  }
  v82 = v118[0];
  Microsoft::RdpNano::RendezvousSource::RendezvousContext::Start(v118[0]);
  v122[0] = (char *)this + 296;
  if ( Mtx_lock((Microsoft::RdpNano::RendezvousSource *)((char *)this + 296)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 93) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 93) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v83 = *((_QWORD *)this + 72);
  if ( v83 == *((_QWORD *)this + 73) )
  {
    std::vector<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>(
      (char *)this + 568,
      v83,
      v118);
    v84 = (volatile signed __int32 *)v118[1];
  }
  else
  {
    *(_QWORD *)v83 = v82;
    *(Microsoft::RdpNano::RendezvousSource::RendezvousContext **)(v83 + 8) = v118[1];
    v84 = 0;
    *((_QWORD *)this + 72) += 16LL;
  }
  Mtx_unlock((Microsoft::RdpNano::RendezvousSource *)((char *)this + 296));
  if ( v84 )
  {
    if ( _InterlockedExchangeAdd(v84 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v84)(v84);
      if ( _InterlockedExchangeAdd(v84 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v84 + 8LL))(v84);
    }
  }
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v121);
  v85 = (volatile signed __int32 *)*((_QWORD *)&v119 + 1);
  if ( *((_QWORD *)&v119 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v119 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v85)(v85);
      if ( _InterlockedExchangeAdd(v85 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v85 + 8LL))(v85);
    }
  }
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v125);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v130);
  if ( v29 && _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
  v86 = (volatile signed __int32 *)v123.m128i_i64[1];
  if ( v123.m128i_i64[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v123.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
      if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
    }
  }
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v124);
  Microsoft::Basix::HTTP::Request::~Request((Microsoft::Basix::HTTP::Request *)v133);
  std::string::_Tidy_deallocate(v131);
  std::string::_Tidy_deallocate(&v126);
  std::string::_Tidy_deallocate(v132);
}

```

## disassembly

```asm
0x18010e434  mov     rax, rsp
0x18010e437  mov     [rax+10h], rbx
0x18010e43b  mov     [rax+18h], rsi
0x18010e43f  mov     [rax+20h], rdi
0x18010e443  push    rbp
0x18010e444  push    r12
0x18010e446  push    r13
0x18010e448  push    r14
0x18010e44a  push    r15
0x18010e44c  lea     rbp, [rax-418h]
0x18010e453  mov     eax, 4F0h
0x18010e458  call    _alloca_probe
0x18010e45d  sub     rsp, rax
0x18010e460  movaps  [rsp+510h+var_38+8], xmm6
0x18010e468  mov     rax, cs:__security_cookie
0x18010e46f  xor     rax, rsp
0x18010e472  mov     [rbp+410h+var_40], rax
0x18010e479  mov     r14, rcx
0x18010e47c  xor     esi, esi
0x18010e47e  mov     [rbp+410h+var_3E8], esi
0x18010e481  lea     r15, [rcx+188h]
0x18010e488  xorps   xmm0, xmm0
0x18010e48b  movups  [rbp+410h+var_240], xmm0
0x18010e492  xorps   xmm1, xmm1
0x18010e495  movdqu  [rbp+410h+var_230], xmm1
0x18010e49d  lea     edi, [rsi+18h]
0x18010e4a0  mov     r8d, edi
0x18010e4a3  lea     rdx, aGatewayloadbal_0; "gatewayLoadBalancerToken"
0x18010e4aa  lea     rcx, [rbp+410h+var_240]
0x18010e4b1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e4b6  mov     [rbp+410h+var_220], 2Eh ; '.'
0x18010e4bd  lea     rax, [rbp+410h+var_240]
0x18010e4c4  lea     r12d, [rsi+0Fh]
0x18010e4c8  cmp     qword ptr [rbp+410h+var_230+8], r12
0x18010e4cf  cmova   rax, qword ptr [rbp+410h+var_240]
0x18010e4d7  mov     [rbp+410h+var_218], rax
0x18010e4de  lea     r8, [rbp+410h+var_240]
0x18010e4e5  lea     rdx, [rbp+410h+var_1E0]
0x18010e4ec  mov     rcx, r15
0x18010e4ef  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &)
0x18010e4f4  nop
0x18010e4f5  lea     rcx, [rbp+410h+var_240]
0x18010e4fc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e501  lea     rbx, [r14+290h]
0x18010e508  lea     rcx, [r14+250h]
0x18010e50f  mov     r9, rbx
0x18010e512  lea     r8, [rbp+410h+var_1E0]
0x18010e519  lea     rdx, [rbp+410h+var_3C0]
0x18010e51d  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAG@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@GV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@G@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@G@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@AEAG@Z; std::_Hash<std::_Umap_traits<std::string,ushort,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,ushort>>,0>>::_Try_emplace<std::string const &,ushort &>(std::string const &,ushort &)
0x18010e522  lea     eax, [rsi+1]
0x18010e525  cmp     [rbp+410h+var_3B8], sil
0x18010e529  jz      short loc_18010E52E
0x18010e52b  add     [rbx], ax
0x18010e52e  xorps   xmm0, xmm0
0x18010e531  movups  [rsp+510h+var_4A0+8], xmm0
0x18010e536  xorps   xmm1, xmm1
0x18010e539  movdqu  [rbp+410h+var_488], xmm1
0x18010e53e  xor     r8d, r8d
0x18010e541  lea     rdx, Str1
0x18010e548  lea     rcx, [rsp+510h+var_4A0+8]
0x18010e54d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e552  nop
0x18010e553  xorps   xmm0, xmm0
0x18010e556  movups  [rsp+510h+var_4D0+8], xmm0
0x18010e55b  xorps   xmm1, xmm1
0x18010e55e  movdqu  [rsp+510h+var_4C0+8], xmm1
0x18010e564  mov     r8, rdi
0x18010e567  lea     rdx, aClientheartbea_18; "clientHeartBeatReply.uri"
0x18010e56e  lea     rcx, [rsp+510h+var_4D0+8]
0x18010e573  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e578  mov     byte ptr [rsp+510h+var_4A8], 2Eh ; '.'
0x18010e57d  lea     rax, [rsp+510h+var_4D0+8]
0x18010e582  cmp     qword ptr [rsp+510h+var_4B0], r12
0x18010e587  cmova   rax, qword ptr [rsp+510h+var_4D0+8]
0x18010e58d  mov     qword ptr [rsp+510h+var_4A0], rax
0x18010e592  lea     r9, [rsp+510h+var_4A0+8]
0x18010e597  lea     r8, [rsp+510h+var_4D0+8]
0x18010e59c  lea     rdx, [rbp+410h+var_240]
0x18010e5a3  mov     rcx, r15
0x18010e5a6  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::string const &)
0x18010e5ab  nop
0x18010e5ac  lea     rcx, [rsp+510h+var_4D0+8]
0x18010e5b1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e5b6  nop
0x18010e5b7  lea     rcx, [rsp+510h+var_4A0+8]
0x18010e5bc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e5c1  mov     [rbp+410h+var_2C0], rsi
0x18010e5c8  xorps   xmm0, xmm0
0x18010e5cb  movups  [rbp+410h+var_478], xmm0
0x18010e5cf  xorps   xmm1, xmm1
0x18010e5d2  movdqu  [rbp+410h+var_468], xmm1
0x18010e5d7  mov     r8d, 21h ; '!'
0x18010e5dd  lea     rdx, aClientheartbea_20; "clientHeartBeatReply.reportInTime"
0x18010e5e4  lea     rcx, [rbp+410h+var_478]
0x18010e5e8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e5ed  mov     [rbp+410h+var_458], 2Eh ; '.'
0x18010e5f1  lea     rax, [rbp+410h+var_478]
0x18010e5f5  cmp     qword ptr [rbp+410h+var_468+8], r12
0x18010e5f9  cmova   rax, qword ptr [rbp+410h+var_478]
0x18010e5fe  mov     [rbp+410h+var_450], rax
0x18010e602  lea     r9, [rbp+410h+var_2C0]
0x18010e609  lea     r8, [rbp+410h+var_478]
0x18010e60d  lea     rdx, [rbp+410h+var_280]
0x18010e614  mov     rcx, r15
0x18010e617  call    ??$get@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV345@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::chrono::duration<__int64,std::ratio<1,1000>>>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18010e61c  nop
0x18010e61d  lea     rcx, [rbp+410h+var_478]
0x18010e621  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e626  xorps   xmm0, xmm0
0x18010e629  movups  [rbp+410h+var_478], xmm0
0x18010e62d  xorps   xmm1, xmm1
0x18010e630  movdqu  [rbp+410h+var_468], xmm1
0x18010e635  mov     r8, r12
0x18010e638  lea     rdx, aGatewaylocatio; "gatewayLocation"
0x18010e63f  lea     rcx, [rbp+410h+var_478]
0x18010e643  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e648  mov     [rbp+410h+var_458], 2Eh ; '.'
0x18010e64c  lea     rax, [rbp+410h+var_478]
0x18010e650  cmp     qword ptr [rbp+410h+var_468+8], r12
0x18010e654  cmova   rax, qword ptr [rbp+410h+var_478]
0x18010e659  mov     [rbp+410h+var_450], rax
0x18010e65d  lea     r8, [rbp+410h+var_478]
0x18010e661  lea     rdx, [rbp+410h+var_200]
0x18010e668  mov     rcx, r15
0x18010e66b  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &)
0x18010e670  nop
0x18010e671  lea     rcx, [rbp+410h+var_478]
0x18010e675  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e67a  xor     edx, edx; Val
0x18010e67c  mov     r8d, 178h; Size
0x18010e682  lea     rcx, [rbp+410h+var_1C0]; void *
0x18010e689  call    memset
0x18010e68e  lea     rdx, [rbp+410h+var_200]
0x18010e695  lea     rcx, [rbp+410h+var_3B0]
0x18010e699  call    ??0URI@HTTP@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::HTTP::URI::URI(std::string const &)
0x18010e69e  nop
0x18010e69f  lea     r8, ?Get@Request@HTTP@Basix@Microsoft@@2V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Microsoft::Basix::HTTP::Request::Get
0x18010e6a6  lea     rdx, [rbp+410h+var_3B0]
0x18010e6aa  lea     rcx, [rbp+410h+var_1C0]
0x18010e6b1  call    ??0Request@HTTP@Basix@Microsoft@@QEAA@AEBVURI@123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::HTTP::Request::Request(Microsoft::Basix::HTTP::URI const &,std::string const &)
0x18010e6b6  nop
0x18010e6b7  lea     rcx, [rbp+410h+var_2E8]
0x18010e6be  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e6c3  lea     rcx, [rbp+410h+var_308]
0x18010e6ca  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e6cf  lea     rcx, [rbp+410h+var_328]
0x18010e6d6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e6db  lea     rcx, [rbp+410h+var_350]
0x18010e6e2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e6e7  lea     rcx, [rbp+410h+var_370]
0x18010e6ee  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e6f3  lea     rcx, [rbp+410h+var_390]
0x18010e6fa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e6ff  lea     rcx, [rbp+410h+var_3B0]
0x18010e703  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e708  lea     rcx, [rbp+410h+var_1C0]; this
0x18010e70f  call    ?GetHeaders@Request@HTTP@Basix@Microsoft@@QEAAAEAVHeaders@234@XZ; Microsoft::Basix::HTTP::Request::GetHeaders(void)
0x18010e714  lea     r8, ?FakeUserAgent@RdpNano@Microsoft@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Microsoft::RdpNano::FakeUserAgent
0x18010e71b  lea     rdx, ?UserAgent@Headers@HTTP@Basix@Microsoft@@2V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Microsoft::Basix::HTTP::Headers::UserAgent
0x18010e722  mov     rcx, rax
0x18010e725  call    ?Set@Headers@HTTP@Basix@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Basix::HTTP::Headers::Set(std::string const &,std::string const &)
0x18010e72a  lea     rcx, [rbp+410h+var_1C0]; this
0x18010e731  call    ?GetHeaders@Request@HTTP@Basix@Microsoft@@QEAAAEAVHeaders@234@XZ; Microsoft::Basix::HTTP::Request::GetHeaders(void)
0x18010e736  lea     r8, ?FakeUserAgent@RdpNano@Microsoft@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Microsoft::RdpNano::FakeUserAgent
0x18010e73d  lea     rdx, ?X_MS_User_Agent@RdpNano@Microsoft@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Microsoft::RdpNano::X_MS_User_Agent
0x18010e744  mov     rcx, rax
0x18010e747  call    ?Set@Headers@HTTP@Basix@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Basix::HTTP::Headers::Set(std::string const &,std::string const &)
0x18010e74c  lea     rcx, [rbp+410h+var_1C0]; this
0x18010e753  call    ?GetHeaders@Request@HTTP@Basix@Microsoft@@QEAAAEAVHeaders@234@XZ; Microsoft::Basix::HTTP::Request::GetHeaders(void)
0x18010e758  mov     rbx, rax
0x18010e75b  xorps   xmm0, xmm0
0x18010e75e  movups  [rsp+510h+var_4A0+8], xmm0
0x18010e763  xorps   xmm1, xmm1
0x18010e766  movdqu  [rbp+410h+var_488], xmm1
0x18010e76b  mov     edi, 6
0x18010e770  mov     r8d, edi
0x18010e773  lea     rdx, aCookie; "Cookie"
0x18010e77a  lea     rcx, [rsp+510h+var_4A0+8]
0x18010e77f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e784  nop
0x18010e785  lea     r8, [rbp+410h+var_1E0]
0x18010e78c  lea     rdx, [rsp+510h+var_4A0+8]
0x18010e791  mov     rcx, rbx
0x18010e794  call    ?Add@Headers@HTTP@Basix@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Basix::HTTP::Headers::Add(std::string const &,std::string const &)
0x18010e799  nop
0x18010e79a  lea     rcx, [rsp+510h+var_4A0+8]
0x18010e79f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e7a4  lea     rcx, [rbp+410h+var_1C0]; this
0x18010e7ab  call    ?GetHeaders@Request@HTTP@Basix@Microsoft@@QEAAAEAVHeaders@234@XZ; Microsoft::Basix::HTTP::Request::GetHeaders(void)
0x18010e7b0  mov     rbx, rax
0x18010e7b3  lea     rdx, [r14+1D8h]
0x18010e7ba  lea     rcx, [rsp+510h+var_4D0+8]
0x18010e7bf  call    ?ToStringWithoutBrackets@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUGuid@12@@Z; Microsoft::Basix::ToStringWithoutBrackets(Microsoft::Basix::Guid const &)
0x18010e7c4  nop
0x18010e7c5  mov     r8, rax
0x18010e7c8  lea     rdx, ?X_MS_Correlation_Id@RdpNano@Microsoft@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Microsoft::RdpNano::X_MS_Correlation_Id
0x18010e7cf  mov     rcx, rbx
0x18010e7d2  call    ?Set@Headers@HTTP@Basix@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Basix::HTTP::Headers::Set(std::string const &,std::string const &)
0x18010e7d7  nop
0x18010e7d8  lea     rcx, [rsp+510h+var_4D0+8]
0x18010e7dd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e7e2  lea     rcx, [rbp+410h+var_1C0]; this
0x18010e7e9  call    ?GetHeaders@Request@HTTP@Basix@Microsoft@@QEAAAEAVHeaders@234@XZ; Microsoft::Basix::HTTP::Request::GetHeaders(void)
0x18010e7ee  mov     rbx, rax
0x18010e7f1  xorps   xmm0, xmm0
0x18010e7f4  movups  [rbp+410h+var_3E0], xmm0
0x18010e7f8  xorps   xmm1, xmm1
0x18010e7fb  movdqu  [rbp+410h+var_3D0], xmm1
0x18010e800  mov     r8d, edi
0x18010e803  lea     rdx, aConnid; "CONNID"
0x18010e80a  lea     rcx, [rbp+410h+var_3E0]
0x18010e80e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e813  nop
0x18010e814  xorps   xmm0, xmm0
0x18010e817  movups  [rsp+510h+var_4A0+8], xmm0
0x18010e81c  xorps   xmm1, xmm1
0x18010e81f  movdqu  [rbp+410h+var_488], xmm1
0x18010e824  mov     r8, r12
0x18010e827  lea     rdx, aRdgAuthScheme; "RDG-Auth-Scheme"
0x18010e82e  lea     rcx, [rsp+510h+var_4A0+8]
0x18010e833  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e838  nop
0x18010e839  lea     r8, [rbp+410h+var_3E0]
0x18010e83d  lea     rdx, [rsp+510h+var_4A0+8]
0x18010e842  mov     rcx, rbx
0x18010e845  call    ?Add@Headers@HTTP@Basix@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Basix::HTTP::Headers::Add(std::string const &,std::string const &)
0x18010e84a  nop
0x18010e84b  lea     rcx, [rsp+510h+var_4A0+8]
0x18010e850  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e855  nop
0x18010e856  lea     rcx, [rbp+410h+var_3E0]
0x18010e85a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e85f  lea     rcx, [rbp+410h+var_1C0]; this
0x18010e866  call    ?GetHeaders@Request@HTTP@Basix@Microsoft@@QEAAAEAVHeaders@234@XZ; Microsoft::Basix::HTTP::Request::GetHeaders(void)
0x18010e86b  mov     rdi, rax
0x18010e86e  xorps   xmm0, xmm0
0x18010e871  movups  [rbp+410h+var_478], xmm0
0x18010e875  xorps   xmm1, xmm1
0x18010e878  movdqu  [rbp+410h+var_468], xmm1
0x18010e87d  mov     r8d, 16h
0x18010e883  lea     rdx, aGatewayconnect; "gatewayConnectionToken"
0x18010e88a  lea     rcx, [rbp+410h+var_478]
0x18010e88e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e893  mov     [rbp+410h+var_458], 2Eh ; '.'
0x18010e897  lea     rcx, [rbp+410h+var_478]
0x18010e89b  cmp     qword ptr [rbp+410h+var_468+8], r12
0x18010e89f  cmova   rcx, qword ptr [rbp+410h+var_478]
0x18010e8a4  mov     [rbp+410h+var_450], rcx
0x18010e8a8  lea     r8, [rbp+410h+var_478]
0x18010e8ac  lea     rdx, [rsp+510h+var_4D0+8]
0x18010e8b1  mov     rcx, r15
0x18010e8b4  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &)
0x18010e8b9  mov     rbx, rax
0x18010e8bc  xorps   xmm0, xmm0
0x18010e8bf  movups  [rsp+510h+var_4A0+8], xmm0
0x18010e8c4  xorps   xmm1, xmm1
0x18010e8c7  movdqu  [rbp+410h+var_488], xmm1
0x18010e8cc  mov     r8d, 10h
0x18010e8d2  lea     rdx, aRdmigatewaytok; "RDmiGatewayToken"
0x18010e8d9  lea     rcx, [rsp+510h+var_4A0+8]
0x18010e8de  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e8e3  nop
0x18010e8e4  mov     r8, rbx
0x18010e8e7  lea     rdx, [rsp+510h+var_4A0+8]
0x18010e8ec  mov     rcx, rdi
0x18010e8ef  call    ?Add@Headers@HTTP@Basix@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Basix::HTTP::Headers::Add(std::string const &,std::string const &)
0x18010e8f4  nop
0x18010e8f5  lea     rcx, [rsp+510h+var_4A0+8]
0x18010e8fa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e8ff  nop
0x18010e900  lea     rcx, [rsp+510h+var_4D0+8]
0x18010e905  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e90a  nop
0x18010e90b  lea     rcx, [rbp+410h+var_478]
0x18010e90f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010e914  lea     rcx, [rbp+410h+var_1C0]; this
0x18010e91b  call    ?GetHeaders@Request@HTTP@Basix@Microsoft@@QEAAAEAVHeaders@234@XZ; Microsoft::Basix::HTTP::Request::GetHeaders(void)
0x18010e920  mov     rdi, rax
0x18010e923  xorps   xmm0, xmm0
0x18010e926  movups  [rbp+410h+var_478], xmm0
0x18010e92a  xorps   xmm1, xmm1
0x18010e92d  movdqu  [rbp+410h+var_468], xmm1
0x18010e932  mov     r8d, 0Ch
0x18010e938  lea     rdx, aConnectionid; "connectionId"
0x18010e93f  lea     rcx, [rbp+410h+var_478]
0x18010e943  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010e948  mov     [rbp+410h+var_458], 2Eh ; '.'
0x18010e94c  lea     rcx, [rbp+410h+var_478]
0x18010e950  cmp     qword ptr [rbp+410h+var_468+8], r12
0x18010e954  cmova   rcx, qword ptr [rbp+410h+var_478]
0x18010e959  mov     [rbp+410h+var_450], rcx
0x18010e95d  lea     r8, [rbp+410h+var_478]
0x18010e961  lea     rdx, [rsp+510h+var_4D0+8]
0x18010e966  mov     rcx, r15
0x18010e969  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@@Z; boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &)
0x18010e96e  mov     rbx, rax
0x18010e971  xorps   xmm0, xmm0
0x18010e974  movups  [rsp+510h+var_4A0+8], xmm0
0x18010e979  xorps   xmm1, xmm1
0x18010e97c  movdqu  [rbp+410h+var_488], xmm1
  ... truncated ...
```

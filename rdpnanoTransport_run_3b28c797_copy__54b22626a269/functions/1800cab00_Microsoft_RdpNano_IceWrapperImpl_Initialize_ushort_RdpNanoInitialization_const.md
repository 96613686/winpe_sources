# Microsoft::RdpNano::IceWrapperImpl::Initialize(ushort,RdpNanoInitialization const *)

- ea: `0x1800cab00`
- end: `0x1800ccc69`
- name: `?Initialize@IceWrapperImpl@RdpNano@Microsoft@@UEAAJGPEBURdpNanoInitialization@@@Z`
- size: `8553`
- prototype: `__int64 __fastcall(Microsoft::RdpNano::IceWrapperImpl *__hidden this, unsigned __int16, const struct RdpNanoInitialization *)`
- caller_count: `0`
- callee_count: `60`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001000`
- `0x18000be70`
- `0x18000d9c0`
- `0x18000da90`
- `0x1800111fc`
- `0x180015b04`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x180018ea4`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ab4c`
- `0x18001ae64`
- `0x18001c080`
- `0x18001dad8`
- `0x180021a00`
- `0x180024760`
- `0x180024c14`
- `0x180028820`
- `0x180029d20`
- `0x1800386d0`
- `0x18003f998`
- `0x18003fa30`
- `0x1800448dc`
- `0x18004569c`
- `0x1800b9d94`
- `0x1800c0000`
- `0x1800c2004`
- `0x1800c2f14`
- `0x1800c3044`
- `0x1800c3524`
- `0x1800c3814`
- `0x1800c408c`
- `0x1800c4758`
- `0x1800c5750`
- `0x1800c5c30`
- `0x1800c5ccc`
- `0x1800c5d4c`
- `0x1800c5e70`
- `0x1800c5f74`
- `0x1800cab00`
- `0x1800cf814`
- `0x1800d0e58`
- `0x1800d0f30`
- `0x1800d1f60`
- `0x1800fa23c`
- `0x1800fdb80`
- `0x1800ff398`
- `0x1801002ac`

## string_xrefs

- `0x1800caef9`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`
- `0x1800cabc9`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800caccc`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800cad10`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800cad3d`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800cada3`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800cae21`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800cb110`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800cbbe3`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800caba0`: `rdpnanoTransport.dll load version mismatch: load=%d, built=%d\n    %s(%d): %s()`
- `0x1800cac64`: `Ping from inside IceWrapperImpl::initialize()`
- `0x1800cb376`: `Microsoft::Basix::Dct.Smiles.UseSideband`
- `0x1800cb482`: `early create smiles`
- `0x1800cb895`: `No Rendezvous URL provided during ICE initialization`
- `0x1800cbd9a`: `iceSourceAdapter->SetISmilesLink(%p)`
- `0x1800cc702`: `Nano General sxsStack Configurations`
- `0x1800cc70e`: `sxsStackConfiguration`
- `0x1800cc71a`: `NanoConfigurations`

## pseudocode

```c
// Hidden C++ exception states: #wind=117
__int64 __fastcall Microsoft::RdpNano::IceWrapperImpl::Initialize(
        Microsoft::RdpNano::IceWrapperImpl *this,
        unsigned __int16 a2,
        const struct RdpNanoInitialization *a3)
{
  const char *v6; // r9
  volatile signed __int32 *v7; // rbx
  __int64 result; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 *v11; // rax
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  struct Microsoft::RdpNano::GlobalState *Instance; // rax
  _QWORD *v16; // rdx
  void (__fastcall ***v17)(_QWORD, __int128 *, _QWORD); // rcx
  __int128 *v18; // rdx
  __int128 *v19; // rax
  unsigned int v20; // ebx
  volatile signed __int32 *v21; // rbx
  int v22; // r9d
  volatile signed __int32 *v23; // rbx
  volatile signed __int32 *v24; // rbx
  __int128 *v25; // rax
  char v26; // bl
  int v27; // r13d
  int v28; // r12d
  int v29; // esi
  __int64 v30; // rax
  int v31; // eax
  volatile signed __int32 *v32; // rbx
  __int64 v33; // rbx
  volatile signed __int32 *v34; // rbx
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // r12
  const char *v38; // rsi
  const char *v39; // rbx
  size_t v40; // r8
  const char *v41; // rbx
  size_t v42; // r8
  size_t v43; // r8
  _DWORD *v44; // r12
  __int64 v45; // rax
  volatile signed __int32 *v46; // rbx
  __int64 v47; // rcx
  __int64 v48; // rcx
  volatile signed __int32 *v49; // rbx
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rdx
  int v54; // ebx
  volatile signed __int32 *v55; // rbx
  int v56; // edx
  int v57; // ecx
  __int64 v58; // rax
  int v59; // r8d
  __int64 v60; // r9
  volatile signed __int32 *v61; // rsi
  int v62; // eax
  unsigned int v63; // r12d
  volatile signed __int32 *v64; // rbx
  volatile signed __int32 *v65; // rbx
  volatile signed __int32 *v66; // rbx
  __int64 v67; // rbx
  volatile signed __int32 *v68; // rbx
  Microsoft::RdpNano::ICESourceAdapter *v69; // rcx
  void *v70; // rax
  __int64 v71; // rax
  int v72; // eax
  __int64 v73; // rcx
  __int64 v74; // rax
  volatile signed __int32 *v75; // rbx
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rdx
  __int64 v79; // rdx
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rdx
  __int64 v83; // rdx
  _BYTE *v84; // rax
  int v85; // ebx
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rdx
  __int64 v89; // rdx
  __int64 v90; // rax
  __int64 v91; // rdx
  __int64 v92; // rdx
  __int64 v93; // rdx
  int v94; // ebx
  volatile signed __int32 *v95; // rbx
  volatile signed __int32 *v96; // rbx
  volatile signed __int32 *v97; // rbx
  volatile signed __int32 *v98; // rbx
  char *v99; // [rsp+20h] [rbp-698h]
  int v100; // [rsp+20h] [rbp-698h]
  char *Str; // [rsp+28h] [rbp-690h]
  const char *v102; // [rsp+30h] [rbp-688h]
  __int64 v103; // [rsp+48h] [rbp-670h]
  __int128 v104; // [rsp+90h] [rbp-628h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-618h]
  char *v106; // [rsp+B0h] [rbp-608h] BYREF
  __int64 *v107; // [rsp+B8h] [rbp-600h] BYREF
  _OWORD v108[2]; // [rsp+C0h] [rbp-5F8h] BYREF
  __int128 v109; // [rsp+E0h] [rbp-5D8h] BYREF
  __int128 v110; // [rsp+F0h] [rbp-5C8h]
  char v111; // [rsp+100h] [rbp-5B8h]
  __int128 *v112; // [rsp+108h] [rbp-5B0h]
  _OWORD v113[2]; // [rsp+110h] [rbp-5A8h] BYREF
  _OWORD v114[2]; // [rsp+130h] [rbp-588h] BYREF
  _OWORD v115[2]; // [rsp+150h] [rbp-568h] BYREF
  _OWORD v116[2]; // [rsp+170h] [rbp-548h] BYREF
  _OWORD v117[2]; // [rsp+190h] [rbp-528h] BYREF
  _OWORD v118[2]; // [rsp+1B0h] [rbp-508h] BYREF
  _OWORD v119[2]; // [rsp+1D0h] [rbp-4E8h] BYREF
  _OWORD v120[2]; // [rsp+1F0h] [rbp-4C8h] BYREF
  _OWORD v121[2]; // [rsp+210h] [rbp-4A8h] BYREF
  _OWORD v122[2]; // [rsp+230h] [rbp-488h] BYREF
  _OWORD v123[2]; // [rsp+250h] [rbp-468h] BYREF
  _OWORD v124[2]; // [rsp+270h] [rbp-448h] BYREF
  _OWORD v125[2]; // [rsp+290h] [rbp-428h] BYREF
  _OWORD v126[2]; // [rsp+2B0h] [rbp-408h] BYREF
  _OWORD v127[2]; // [rsp+2D0h] [rbp-3E8h] BYREF
  __int64 v128[2]; // [rsp+2F0h] [rbp-3C8h] BYREF
  __m128i v129; // [rsp+300h] [rbp-3B8h]
  __int64 v130[2]; // [rsp+310h] [rbp-3A8h] BYREF
  __int128 v131; // [rsp+320h] [rbp-398h]
  _BYTE v132[32]; // [rsp+330h] [rbp-388h] BYREF
  _BYTE v133[32]; // [rsp+350h] [rbp-368h] BYREF
  _BYTE v134[32]; // [rsp+370h] [rbp-348h] BYREF
  _BYTE v135[32]; // [rsp+390h] [rbp-328h] BYREF
  _BYTE v136[32]; // [rsp+3B0h] [rbp-308h] BYREF
  __int64 v137[4]; // [rsp+3D0h] [rbp-2E8h] BYREF
  _BYTE v138[32]; // [rsp+3F0h] [rbp-2C8h] BYREF
  _BYTE v139[32]; // [rsp+410h] [rbp-2A8h] BYREF
  _BYTE v140[32]; // [rsp+430h] [rbp-288h] BYREF
  _BYTE v141[32]; // [rsp+450h] [rbp-268h] BYREF
  _BYTE v142[32]; // [rsp+470h] [rbp-248h] BYREF
  _BYTE v143[32]; // [rsp+490h] [rbp-228h] BYREF
  _BYTE v144[32]; // [rsp+4B0h] [rbp-208h] BYREF
  _BYTE v145[32]; // [rsp+4D0h] [rbp-1E8h] BYREF
  _BYTE v146[32]; // [rsp+4F0h] [rbp-1C8h] BYREF
  _BYTE v147[32]; // [rsp+510h] [rbp-1A8h] BYREF
  _BYTE v148[32]; // [rsp+530h] [rbp-188h] BYREF
  char v149; // [rsp+550h] [rbp-168h] BYREF
  _BYTE v150[15]; // [rsp+551h] [rbp-167h] BYREF
  _OWORD v151[2]; // [rsp+560h] [rbp-158h] BYREF
  unsigned int v152; // [rsp+580h] [rbp-138h] BYREF
  unsigned __int8 v153[12]; // [rsp+584h] [rbp-134h] BYREF
  int v154[4]; // [rsp+590h] [rbp-128h] BYREF
  __int128 v155; // [rsp+5A0h] [rbp-118h]
  __int128 v156; // [rsp+5B0h] [rbp-108h] BYREF
  __int128 v157; // [rsp+5C0h] [rbp-F8h] BYREF
  Microsoft::RdpNano::ICESourceAdapter *v158[2]; // [rsp+5D0h] [rbp-E8h] BYREF
  __int128 v159; // [rsp+5E0h] [rbp-D8h] BYREF
  __int128 v160; // [rsp+5F0h] [rbp-C8h] BYREF
  __int128 v161; // [rsp+600h] [rbp-B8h]
  __int128 v162; // [rsp+610h] [rbp-A8h] BYREF
  __int64 v163; // [rsp+620h] [rbp-98h]
  __int128 v164; // [rsp+628h] [rbp-90h] BYREF
  __int64 v165; // [rsp+638h] [rbp-80h]
  __int128 v166; // [rsp+640h] [rbp-78h] BYREF
  __int128 v167; // [rsp+650h] [rbp-68h] BYREF
  __int64 v168; // [rsp+660h] [rbp-58h]
  __int64 v169; // [rsp+668h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+0h]

  try
  {
    if ( a2 != 276 )
    {
      v151[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v151);
      if ( *(_QWORD *)&v151[0] && *(_BYTE *)(*(_QWORD *)&v151[0] + 128LL) )
      {
        v104 = 0;
        si128 = 0;
        std::string::_Construct<1,char const *>(
          &v104,
          "rdpnanoTransport.dll load version mismatch: load=%d, built=%d\n    %s(%d): %s()",
          78,
          (_DWORD)v6,
          v99,
          (_DWORD)Str,
          v102);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,unsigned short,unsigned short,char const *,int,char const *>(
          (unsigned int)v151,
          (unsigned int)"RDPNANO",
          (unsigned int)&v104,
          a2,
          20,
          (__int64)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
          130,
          (__int64)"Microsoft::RdpNano::IceWrapperImpl::Initialize");
        std::string::_Tidy_deallocate(&v104);
      }
      v7 = (volatile signed __int32 *)*((_QWORD *)&v151[0] + 1);
      if ( *((_QWORD *)&v151[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v151[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
          if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        }
      }
      return 2147943706LL;
    }
    if ( *g_hRDPNanoLogger[0] > 4u )
    {
      v106 = "Ping from inside IceWrapperImpl::initialize()";
      v107 = (__int64 *)"RDPNANO";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        g_hRDPNanoLogger[0],
        (unsigned int)&dword_1804A281C,
        0,
        0,
        (__int64)&v107,
        (__int64)&v106);
    }
    if ( !a3 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
        (const char *)0x80070057LL,
        (int)v99);
      return 2147942487LL;
    }
    v9 = *(_QWORD *)a3;
    *((_QWORD *)this + 13) = *(_QWORD *)a3;
    v10 = *((_QWORD *)a3 + 1);
    *((_QWORD *)this + 14) = v10;
    *((_QWORD *)this + 15) = *((_QWORD *)a3 + 2);
    if ( !v9 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
        (const char *)0x80070057LL,
        (int)v99);
      return 2147942487LL;
    }
    if ( !v10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
        (const char *)0x80070057LL,
        (int)v99);
      return 2147942487LL;
    }
    LODWORD(v106) = 0;
    if ( !(unsigned __int8)std::_Atomic_storage<enum Microsoft::Basix::Pattern::IThreadedObject::State,4>::compare_exchange_strong(
                             (char *)this + 96,
                             &v106,
                             1) )
    {
      LODWORD(Str) = (_DWORD)v106;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x9C,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
        (const char *)0x8000000DLL,
        (unsigned __int64)"State=%d",
        Str);
      return 2147483661LL;
    }
    v157 = 0u;
    v11 = (__int64 *)operator new(0x20u);
    v107 = v11;
    if ( v11 )
      v12 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v11);
    else
      v12 = 0;
    *((_QWORD *)&v157 + 1) = v12;
    v13 = Microsoft::RdpNano::IceWrapperImpl::ParseSmilesInitializationParameters(this, a3, &v157);
    v14 = v13;
    if ( v13 < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
        (const char *)(unsigned int)v13,
        (int)v99);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v157);
      return v14;
    }
    *((_BYTE *)this + 265) = *((_DWORD *)a3 + 8) != 0;
    *((_BYTE *)this + 272) = (*((_DWORD *)a3 + 16) & 0x1000LL) != 0;
    Instance = Microsoft::RdpNano::GlobalState::GetInstance();
    v16 = (_QWORD *)((char *)Instance + 16);
    v160 = 0;
    v161 = 0;
    if ( *((_QWORD *)Instance + 5) > 0xFu )
      v16 = (_QWORD *)*v16;
    std::string::_Construct<2,char const *>(&v160, v16, *((_QWORD *)Instance + 4));
    if ( (_QWORD)v161 )
    {
      _mm_lfence();
      v17 = (void (__fastcall ***)(_QWORD, __int128 *, _QWORD))*((_QWORD *)this + 15);
      if ( v17 )
      {
        v18 = &v160;
        if ( *((_QWORD *)&v161 + 1) > 0xFu )
          v18 = (__int128 *)v160;
        (**v17)(v17, v18, (unsigned int)v161);
      }
    }
    *(_DWORD *)v153 = 0;
    v152 = 4;
    if ( ReadRegistryValueA(
           "LOG_ICE_TRAFFIC",
           v153,
           &v152,
           "SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services") )
    {
      v109 = 0;
      v110 = 0;
      std::string::_Construct<1,char const *>(&v109, "Microsoft::Basix::Dct.ICE.LogTrafficLevel", 41);
      v111 = 46;
      v19 = &v109;
      if ( *((_QWORD *)&v110 + 1) > 0xFu )
        v19 = (__int128 *)v109;
      v112 = v19;
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned long>(
        &v157,
        &v109,
        v153);
      std::string::_Tidy_deallocate(&v109);
    }
    v156 = 0;
    v151[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v151);
    if ( *(_QWORD *)&v151[0] && *(_BYTE *)(*(_QWORD *)&v151[0] + 128LL) )
    {
      _mm_lfence();
      v20 = *((_DWORD *)a3 + 30);
      v104 = 0;
      si128 = 0;
      std::string::_Construct<1,char const *>(&v104, "parameters->smilesVersion=%d", 28);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int>(
        v151,
        "RDPNANO",
        &v104,
        v20);
      std::string::_Tidy_deallocate(&v104);
    }
    _mm_lfence();
    v21 = (volatile signed __int32 *)*((_QWORD *)&v151[0] + 1);
    if ( *((_QWORD *)&v151[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v151[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    if ( *((_DWORD *)a3 + 30) == -1 )
    {
      v151[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v151);
      if ( *(_QWORD *)&v151[0] && *(_BYTE *)(*(_QWORD *)&v151[0] + 128LL) )
      {
        v104 = 0;
        si128 = 0;
        std::string::_Construct<1,char const *>(
          &v104,
          "peer does not support orchietration blob exchange\n    %s(%d): %s()",
          (const char *)0x42,
          v22,
          v99);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)v151,
          (unsigned int)"RDPNANO",
          (unsigned int)&v104,
          (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
          196,
          (__int64)"Microsoft::RdpNano::IceWrapperImpl::Initialize");
        std::string::_Tidy_deallocate(&v104);
      }
      v23 = (volatile signed __int32 *)*((_QWORD *)&v151[0] + 1);
      if ( *((_QWORD *)&v151[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v151[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
      v24 = (volatile signed __int32 *)*((_QWORD *)&v156 + 1);
      if ( *((_QWORD *)&v156 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
          if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        }
      }
      std::string::_Tidy_deallocate(&v160);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v157);
      return 2147942487LL;
    }
    v149 = *((_DWORD *)a3 + 30) != 0;
    if ( (*((_QWORD *)a3 + 8) & 0x20000LL) != 0 )
    {
      *((_DWORD *)this + 67) = 2;
    }
    else if ( (*((_QWORD *)a3 + 8) & 0x2000LL) != 0 )
    {
      *((_DWORD *)this + 67) = 1;
    }
    if ( (*((_DWORD *)a3 + 16) & 0x10000LL) != 0 )
    {
      v150[0] = 1;
      v109 = 0;
      v110 = 0;
      std::string::_Construct<1,char const *>(&v109, "Microsoft::Basix::Dct.ICE.DisableDelayTrace", 43);
      v111 = 46;
      v25 = &v109;
      if ( *((_QWORD *)&v110 + 1) > 0xFu )
        v25 = (__int128 *)v109;
      v112 = v25;
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<bool>(&v157, &v109, v150);
      std::string::_Tidy_deallocate(&v109);
    }
    _mm_lfence();
    v26 = (*((_DWORD *)a3 + 16) & 0x40000LL) != 0;
    v107 = (__int64 *)v108;
    v27 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::IAsyncTransport::DataReceiveCallback>(
            (char *)this + *(int *)(*((_QWORD *)this + 7) + 4LL) + 56,
            v108);
    _mm_lfence();
    v106 = (char *)v154;
    v28 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::IAsyncTransport::StateChangeCallback>(
            (char *)this + *(int *)(*((_QWORD *)this + 7) + 4LL) + 56,
            v154);
    _mm_lfence();
    v29 = *((_DWORD *)a3 + 30);
    v30 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::ISmiles::ISmilesCallback>(
            (char *)this + *(int *)(*((_QWORD *)this + 7) + 4LL) + 56,
            v113);
    _mm_lfence();
    v151[0] = *(_OWORD *)((char *)a3 + 40);
    v31 = Microsoft::Basix::Containers::AnyPTreeFromPairs<char const *,Microsoft::Basix::Guid,char const *,int,char const *,unsigned int,char const *,bool,char const *,unsigned int,char const *,bool,char const *,std::weak_ptr<Microsoft::Basix::Dct::ISmiles::ISmilesCallback>>(
            (unsigned int)&v104,
            (unsigned int)"Microsoft::Basix::Dct.ActivityId",
            (unsigned int)v151,
            (unsigned int)"Microsoft::Basix::Dct.IsServerConnection",
            *((_DWORD *)a3 + 8),
            (__int64)"Microsoft::Basix::Dct.ICE.Smiles.Version",
            *((_DWORD *)a3 + 30),
            (__int64)"Microsoft::Basix::Dct.ICE.Smiles.Enabled",
            v149,
            (__int64)"Microsoft::Basix::Dct.Transport.AutoReconnectionTimeoutSeconds",
            *((_DWORD *)a3 + 40),
            (__int64)"Microsoft::Basix::Dct.Smiles.UseSideband",
            v26,
            (__int64)"Microsoft::Basix::Dct.Smiles.Callback",
            v30);
    _mm_lfence();
    Microsoft::Basix::Dct::MakeSmiles(v31, v29, v28, v27, (__int64)this + 144, (__int64)&v156, (__int64)this + 128);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v104);
    v151[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v151);
    if ( *(_QWORD *)&v151[0] && *(_BYTE *)(*(_QWORD *)&v151[0] + 128LL) )
    {
      v104 = 0;
      si128 = 0;
      std::string::_Construct<1,char const *>(&v104, "early create smiles", 19);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        v151,
        "RDPNANO",
        &v104);
      std::string::_Tidy_deallocate(&v104);
    }
    v32 = (volatile signed __int32 *)*((_QWORD *)&v151[0] + 1);
    if ( *((_QWORD *)&v151[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v151[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    v151[0] = 0;
    if ( *((_QWORD *)a3 + 16) )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v151);
      if ( *(_QWORD *)&v151[0] && *(_BYTE *)(*(_QWORD *)&v151[0] + 128LL) )
      {
        v33 = *((_QWORD *)a3 + 16);
        v104 = 0;
        si128 = 0;
        std::string::_Construct<1,char const *>(&v104, "ICE initialized with Rendezvous URL %s", (const char *)0x26);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,char const *>(
          v151,
          "RENDEZVOUS",
          &v104,
          v33);
        std::string::_Tidy_deallocate(&v104);
      }
      v34 = (volatile signed __int32 *)*((_QWORD *)&v151[0] + 1);
      if ( *((_QWORD *)&v151[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v151[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
          if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
        }
      }
      v35 = *((_QWORD *)a3 + 8);
      v150[0] = (v35 & 0x400) != 0;
      v149 = (v35 & 0x800) != 0;
      v36 = *((_DWORD *)a3 + 36);
      if ( v36 == 3 || v36 == 4 )
      {
        v37 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::RdpNano::SourceAdapter::Delegate>(
                (char *)this + *(int *)(*((_QWORD *)this + 7) + 4LL) + 56,
                v113);
        v38 = (const char *)&Str1;
        v39 = (const char *)&Str1;
        if ( *((_QWORD *)a3 + 7) )
          v39 = (const char *)*((_QWORD *)a3 + 7);
        memset(v151, 0, sizeof(v151));
        v40 = strlen(v39);
        std::string::_Construct<1,char const *>(v151, v39, v40);
        v41 = (const char *)&Str1;
        if ( *((_QWORD *)a3 + 16) )
          v41 = (const char *)*((_QWORD *)a3 + 16);
        *(_OWORD *)v154 = 0;
        v155 = 0;
        v42 = strlen(v41);
        std::string::_Construct<1,char const *>(v154, v41, v42);
        if ( *((_QWORD *)a3 + 17) )
          v38 = (const char *)*((_QWORD *)a3 + 17);
        memset(v108, 0, sizeof(v108));
        v43 = strlen(v38);
        std::string::_Construct<1,char const *>(v108, v38, v43);
        v103 = v37;
        v44 = (_DWORD *)((char *)a3 + 32);
        v45 = std::make_shared<Microsoft::RdpNano::RendezvousSourceAdapter,std::string,std::string,std::string,int const &,Microsoft::Basix::Guid const &,unsigned int const &,bool &,bool &,std::weak_ptr<Microsoft::RdpNano::SourceAdapter::Delegate>>(
                (unsigned int)&v104,
                (unsigned int)v108,
                (unsigned int)v154,
                (unsigned int)v151,
                (__int64)a3 + 32,
                (__int64)a3 + 40,
                (__int64)a3 + 160,
                (__int64)v150,
                (__int64)&v149,
                v103);
        std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
          (char *)this + 80,
          v45);
        v46 = (volatile signed __int32 *)*((_QWORD *)&v104 + 1);
        if ( *((_QWORD *)&v104 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v104 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
            if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
          }
        }
        std::string::_Tidy_deallocate(v108);
        std::string::_Tidy_deallocate(v154);
        std::string::_Tidy_deallocate(v151);
        v47 = *((_QWORD *)&v113[0] + 1);
        if ( *((_QWORD *)&v113[0] + 1)
          && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v113[0] + 1) + 12LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
        }
        v48 = *((_QWORD *)this + 10);
        *(_OWORD *)v154 = 0;
        if ( *((_QWORD *)&v156 + 1) )
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL));
        *(_OWORD *)v154 = v156;
        Microsoft::RdpNano::SourceAdapter::SetISmilesLink(v48, v154);
        goto LABEL_106;
      }
    }
    else
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v151);
      if ( *(_QWORD *)&v151[0] && *(_BYTE *)(*(_QWORD *)&v151[0] + 128LL) )
      {
        v104 = 0;
        si128 = 0;
        std::string::_Construct<1,char const *>(&v104, "No Rendezvous URL provided during ICE initialization", 52);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          v151,
          "RENDEZVOUS",
          &v104);
        std::string::_Tidy_deallocate(&v104);
      }
      v49 = (volatile signed __int32 *)*((_QWORD *)&v151[0] + 1);
      if ( *((_QWORD *)&v151[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v151[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
          if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
        }
      }
    }
    v44 = (_DWORD *)((char *)a3 + 32);
LABEL_106:
    *(_OWORD *)v158 = 0;
    v50 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::RdpNano::SourceAdapter::Delegate>(
            (char *)this + *(int *)(*((_QWORD *)this + 7) + 4LL) + 56,
            &v104);
    std::make_shared<Microsoft::RdpNano::ICESourceAdapter,std::weak_ptr<Microsoft::RdpNano::SourceAdapter::Delegate>>(
      v158,
      v50);
    v51 = *((_QWORD *)&v104 + 1);
    if ( *((_QWORD *)&v104 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v104 + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
    }
    v167 = 0;
    v52 = 0;
    v168 = 0;
    v169 = 15;
    LOBYTE(v167) = 0;
    v53 = *((_QWORD *)a3 + 19);
    if ( v53 )
    {
      std::string::assign(&v167, v53);
      v52 = v168;
    }
    v162 = 0;
    v163 = 0;
    v164 = 0;
    v165 = 0;
    if ( v52 )
    {
      v54 = Microsoft::RdpNano::ICESourceAdapter::ParseIceServers(&v167, &v162, &v164);
      if ( v54 < 0 )
      {
        v151[0] = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v151);
        if ( *(_QWORD *)&v151[0] && *(_BYTE *)(*(_QWORD *)&v151[0] + 128LL) )
        {
          v104 = 0;
          si128 = 0;
          std::string::_Construct<1,char const *>(
            &v104,
            "ICESourceAdapter::ParseIceServers failed: 0x%x. Proceeding without STUN and TURN servers.",
            89);
          _mm_lfence();
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,long>(
            v151,
            "RDPNANO",
            &v104,
            (unsigned int)v54);
          std::string::_Tidy_deallocate(&v104);
        }
        v55 = (volatile signed __int32 *)*((_QWORD *)&v151[0] + 1);
        if ( *((_QWORD *)&v151[0] + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v151[0] + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
            if ( !_InterlockedDecrement(v55 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
          }
        }
      }
    }
    v166 = 0;
    std::make_shared<Microsoft::RdpNano::IceWrapperImpl::PortAllocator,IRdpNanoPortAllocator * const &>(
      &v166,
      (char *)a3 + 24);
    v108[0] = 0;
    std::dynamic_pointer_cast<Microsoft::Basix::Dct::IPortAllocator,Microsoft::RdpNano::IceWrapperImpl::PortAllocator>(
      v108,
      &v166);
    v57 = (int)v158[0];
    v58 = *((_QWORD *)a3 + 13);
    v59 = *((_DWORD *)a3 + 9);
    v60 = *((_QWORD *)a3 + 8);
    *(_OWORD *)v154 = 0;
    v61 = (volatile signed __int32 *)*((_QWORD *)&v108[0] + 1);
    if ( *((_QWORD *)&v108[0] + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v108[0] + 1) + 8LL));
    *(_OWORD *)v154 = v108[0];
    v104 = *(_OWORD *)((char *)a3 + 40);
    LOBYTE(v56) = *v44 == 1;
    v62 = Microsoft::RdpNano::ICESourceAdapter::Initialize(
            v57,
            v56,
            (unsigned int)&v104,
            (unsigned int)v154,
            v60,
            v59,
            v58,
            (__int64)&v162,
            (__int64)&v164,
            (__int64)&v157);
    v63 = v62;
    if ( v62 >= 0 )
    {
      v151[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v151);
      if ( *(_QWORD *)&v151[0] && *(_BYTE *)(*(_QWORD *)&v151[0] + 128LL) )
      {
        v67 = v156;
        v104 = 0;
        si128 = 0;
        std::string::_Construct<1,char const *>(&v104, "iceSourceAdapter->SetISmilesLink(%p)", (const void *)0x24);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(
          v151,
          "RDPNANO",
          &v104,
          v67);
        std::string::_Tidy_deallocate(&v104);
      }
      v68 = (volatile signed __int32 *)*((_QWORD *)&v151[0] + 1);
      if ( *((_QWORD *)&v151[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v151[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
          if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
        }
      }
      v69 = v158[0];
      *(_OWORD *)v154 = 0;
      if ( *((_QWORD *)&v156 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL));
      *(_OWORD *)v154 = v156;
      Microsoft::RdpNano::SourceAdapter::SetISmilesLink(v69, v154);
      Microsoft::RdpNano::ICESourceAdapter::Start(v158[0]);
      v159 = 0u;
      v70 = operator new(0x20u);
      *(_QWORD *)&v151[0] = v70;
      if ( v70 )
        v71 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v70);
      else
        v71 = 0;
      *((_QWORD *)&v159 + 1) = v71;
      *(_QWORD *)&v151[0] = (char *)this + 168;
      if ( Mtx_lock((Microsoft::RdpNano::IceWrapperImpl *)((char *)this + 168)) )
        std::_Throw_Cpp_error(5);
      if ( *((_DWORD *)this + 61) == 0x7FFFFFFF )
      {
        *((_DWORD *)this + 61) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
        (char *)this + 64,
        v158);
      if ( *(_QWORD *)((*((_QWORD *)this + 40) & -(__int64)(*((_QWORD *)this + 40) != -17)) + 0x18)
        && ((*((_BYTE *)this + 304) >> 4) & 0xF) == 0 )
      {
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::operator=(&v159);
      }
      Mtx_unlock((Microsoft::RdpNano::IceWrapperImpl *)((char *)this + 168));
      if ( *(_QWORD *)((*((_QWORD *)&v159 + 1) & -(__int64)(*((_QWORD *)&v159 + 1) != -17)) + 0x18) )
      {
        Microsoft::RdpNano::ICESourceAdapter::OnReceiveSideBandData(
          *((_QWORD *)this + 8),
          *((unsigned __int16 *)this + 152),
          &v159);
        *((_WORD *)this + 152) = 0;
      }
      v72 = *((_DWORD *)a3 + 40);
      *((_DWORD *)this + 69) = v72;
      *((_BYTE *)this + 273) = v72 != 0;
      v73 = *((_QWORD *)a3 + 8) & 0x8000LL;
      *((_BYTE *)this + 284) = (*((_QWORD *)a3 + 8) & 0x8000) != 0;
      if ( v73 )
      {
        LODWORD(v106) = 2;
        v74 = std::make_shared<Microsoft::RdpNano::IceRestartAgent,std::shared_ptr<Microsoft::RdpNano::ICESourceAdapter> &,enum Microsoft::RdpNano::IceSourceState>(
                &v104,
                (char *)this + 64,
                &v106);
        std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
          (char *)this + 288,
          v74);
        v75 = (volatile signed __int32 *)*((_QWORD *)&v104 + 1);
        if ( *((_QWORD *)&v104 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v104 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
            if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
          }
        }
        Microsoft::RdpNano::IceRestartAgent::Start(*((Microsoft::RdpNano::IceRestartAgent **)this + 36));
      }
      *(_OWORD *)v154 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v154);
      if ( *(_QWORD *)v154 && *(_BYTE *)(*(_QWORD *)v154 + 128LL) )
      {
        *(_QWORD *)&v151[0] = v137;
        std::_Integral_to_string<char,int>(v135, *((unsigned int *)this + 67));
        memset(v119, 0, sizeof(v119));
        std::string::_Construct<1,char const *>(v119, ":", 1);
        memset(v120, 0, sizeof(v120));
        std::string::_Construct<1,char const *>(v120, "\"", 1);
        memset(v121, 0, sizeof(v121));
        std::string::_Construct<1,char const *>(v121, "\"", 1);
        v76 = std::operator+<char>(v147, v121, "sequencerMode");
        LOBYTE(v77) = v149;
        std::string::string(v134, v77, v76, v120);
        LOBYTE(v78) = v149;
        std::string::string(v133, v78, v134, v119);
        LOBYTE(v79) = v149;
        std::string::string(v137, v79, v133, v135);
        v107 = v130;
        if ( *((_BYTE *)this + 284) )
        {
          memset(v122, 0, sizeof(v122));
          std::string::_Construct<1,char const *>(v122, "true", 4);
          memset(v123, 0, sizeof(v123));
          std::string::_Construct<1,char const *>(v123, ":", 1);
          memset(v124, 0, sizeof(v124));
          std::string::_Construct<1,char const *>(v124, "\"", 1);
          memset(v125, 0, sizeof(v125));
          std::string::_Construct<1,char const *>(v125, "\"", 1);
          v80 = std::operator+<char>(v146, v125, "IceRestartEnabled");
          LOBYTE(v81) = v149;
          std::string::string(v132, v81, v80, v124);
          LOBYTE(v82) = v149;
          std::string::string(v143, v82, v132, v123);
          LOBYTE(v83) = v149;
          std::string::string(v142, v83, v143, v122);
          v84 = v142;
          v85 = 255;
        }
        else
        {
          memset(v117, 0, sizeof(v117));
          std::string::_Construct<1,char const *>(v117, "false", 5);
          memset(v118, 0, sizeof(v118));
          std::string::_Construct<1,char const *>(v118, ":", 1);
          memset(v116, 0, sizeof(v116));
          std::string::_Construct<1,char const *>(v116, "\"", 1);
          memset(v115, 0, sizeof(v115));
          std::string::_Construct<1,char const *>(v115, "\"", 1);
          v86 = std::operator+<char>(v145, v115, "IceRestartEnabled");
          LOBYTE(v87) = v149;
          std::string::string(v136, v87, v86, v116);
          LOBYTE(v88) = v149;
          std::string::string(v141, v88, v136, v118);
          LOBYTE(v89) = v149;
          std::string::string(v140, v89, v141, v117);
          v84 = v140;
          v85 = 65280;
        }
        *(_OWORD *)v130 = *(_OWORD *)v84;
        v131 = *((_OWORD *)v84 + 1);
        *((_QWORD *)v84 + 2) = 0;
        *((_QWORD *)v84 + 3) = 15;
        *v84 = 0;
        memset(v114, 0, sizeof(v114));
        std::string::_Construct<1,char const *>(v114, "false", 5);
        memset(v127, 0, sizeof(v127));
        std::string::_Construct<1,char const *>(v127, ":", 1);
        memset(v126, 0, sizeof(v126));
        std::string::_Construct<1,char const *>(v126, "\"", 1);
        memset(v113, 0, sizeof(v113));
        std::string::_Construct<1,char const *>(v113, "\"", 1);
        v90 = std::operator+<char>(v144, v113, "OptimizedStackUsed");
        LOBYTE(v91) = v149;
        std::string::string(v139, v91, v90, v126);
        LOBYTE(v92) = v149;
        std::string::string(v138, v92, v139, v127);
        LOBYTE(v93) = v149;
        std::string::string(&v104, v93, v138, v114);
        *(_OWORD *)v128 = v104;
        v129 = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(v104) = 0;
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
          (int)v154,
          (int)"RD_CHECKPOINT",
          0,
          (int)"NanoConfigurations",
          "sxsStackConfiguration",
          "Nano General sxsStack Configurations",
          (__int64)v128,
          (__int64)v130,
          (__int64)v137);
        v94 = v85 & 0xFFFFFF | 0x7F000000;
        std::string::_Tidy_deallocate(&v104);
        if ( (v94 & 0x40000000) != 0 )
        {
          v94 &= ~0x40000000u;
          std::string::_Tidy_deallocate(v138);
        }
        if ( (v94 & 0x20000000) != 0 )
        {
          v94 &= ~0x20000000u;
          std::string::_Tidy_deallocate(v139);
        }
        if ( (v94 & 0x10000000) != 0 )
        {
          v94 &= ~0x10000000u;
          std::string::_Tidy_deallocate(v144);
        }
        if ( (v94 & 0x8000000) != 0 )
        {
          v94 &= ~0x8000000u;
          std::string::_Tidy_deallocate(v113);
        }
        if ( (v94 & 0x4000000) != 0 )
        {
          v94 &= ~0x4000000u;
          std::string::_Tidy_deallocate(v126);
        }
        if ( (v94 & 0x2000000) != 0 )
        {
          v94 &= ~0x2000000u;
          std::string::_Tidy_deallocate(v127);
        }
        if ( (v94 & 0x1000000) != 0 )
        {
          v94 &= ~0x1000000u;
          std::string::_Tidy_deallocate(v114);
        }
        if ( (v94 & 0x800000) != 0 )
        {
          v94 &= ~0x800000u;
          std::string::_Tidy_deallocate(v108);
        }
        if ( (v94 & 0x400000) != 0 )
        {
          v94 &= ~0x400000u;
          std::string::_Tidy_deallocate(v108);
        }
        if ( (v94 & 0x200000) != 0 )
        {
          v94 &= ~0x200000u;
          std::string::_Tidy_deallocate(v108);
        }
        if ( (v94 & 0x100000) != 0 )
        {
          v94 &= ~0x100000u;
          std::string::_Tidy_deallocate(v148);
        }
        if ( (v94 & 0x80000) != 0 )
        {
          v94 &= ~0x80000u;
          std::string::_Tidy_deallocate(&v109);
        }
        if ( (v94 & 0x40000) != 0 )
        {
          v94 &= ~0x40000u;
          std::string::_Tidy_deallocate(v108);
        }
        if ( (v94 & 0x20000) != 0 )
        {
          v94 &= ~0x20000u;
          std::string::_Tidy_deallocate(v108);
        }
        if ( (v94 & 0x10000) != 0 )
          std::string::_Tidy_deallocate(v108);
        if ( (v94 & 0x8000) != 0 )
        {
          LOWORD(v94) = v94 & 0x7FFF;
          std::string::_Tidy_deallocate(v140);
        }
        if ( (v94 & 0x4000) != 0 )
        {
          LOWORD(v94) = v94 & 0xBFFF;
          std::string::_Tidy_deallocate(v141);
        }
        if ( (v94 & 0x2000) != 0 )
        {
          LOWORD(v94) = v94 & 0xDFFF;
          std::string::_Tidy_deallocate(v136);
        }
        if ( (v94 & 0x1000) != 0 )
        {
          LOWORD(v94) = v94 & 0xEFFF;
          std::string::_Tidy_deallocate(v145);
        }
        if ( (v94 & 0x800) != 0 )
        {
          LOWORD(v94) = v94 & 0xF7FF;
          std::string::_Tidy_deallocate(v115);
        }
        if ( (v94 & 0x400) != 0 )
        {
          LOWORD(v94) = v94 & 0xFBFF;
          std::string::_Tidy_deallocate(v116);
        }
        if ( (v94 & 0x200) != 0 )
        {
          LOWORD(v94) = v94 & 0xFDFF;
          std::string::_Tidy_deallocate(v118);
        }
        if ( (v94 & 0x100) != 0 )
          std::string::_Tidy_deallocate(v117);
        if ( (v94 & 0x80u) != 0 )
        {
          LOBYTE(v94) = v94 & 0x7F;
          std::string::_Tidy_deallocate(v142);
        }
        if ( (v94 & 0x40) != 0 )
        {
          LOBYTE(v94) = v94 & 0xBF;
          std::string::_Tidy_deallocate(v143);
        }
        if ( (v94 & 0x20) != 0 )
        {
          LOBYTE(v94) = v94 & 0xDF;
          std::string::_Tidy_deallocate(v132);
        }
        if ( (v94 & 0x10) != 0 )
        {
          LOBYTE(v94) = v94 & 0xEF;
          std::string::_Tidy_deallocate(v146);
        }
        if ( (v94 & 8) != 0 )
        {
          LOBYTE(v94) = v94 & 0xF7;
          std::string::_Tidy_deallocate(v125);
        }
        if ( (v94 & 4) != 0 )
        {
          LOBYTE(v94) = v94 & 0xFB;
          std::string::_Tidy_deallocate(v124);
        }
        if ( (v94 & 2) != 0 )
        {
          LOBYTE(v94) = v94 & 0xFD;
          std::string::_Tidy_deallocate(v123);
        }
        if ( (v94 & 1) != 0 )
          std::string::_Tidy_deallocate(v122);
        std::string::_Tidy_deallocate(v133);
        std::string::_Tidy_deallocate(v134);
        std::string::_Tidy_deallocate(v147);
        std::string::_Tidy_deallocate(v121);
        std::string::_Tidy_deallocate(v120);
        std::string::_Tidy_deallocate(v119);
        std::string::_Tidy_deallocate(v135);
      }
      v95 = *(volatile signed __int32 **)&v154[2];
      if ( *(_QWORD *)&v154[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v154[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
          if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
        }
      }
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v159);
      if ( v61 )
      {
        if ( !_InterlockedDecrement(v61 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
          if ( !_InterlockedDecrement(v61 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
        }
      }
      v96 = (volatile signed __int32 *)*((_QWORD *)&v166 + 1);
      if ( *((_QWORD *)&v166 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v166 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v96)(v96);
          if ( !_InterlockedDecrement(v96 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
        }
      }
      std::vector<Microsoft::Basix::Dct::ICE::Agent::TurnServer>::_Tidy(&v164);
      std::vector<std::string>::_Tidy(&v162);
      std::string::_Tidy_deallocate(&v167);
      v97 = (volatile signed __int32 *)v158[1];
      if ( v158[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v158[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
          if ( _InterlockedExchangeAdd(v97 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
        }
      }
      v98 = (volatile signed __int32 *)*((_QWORD *)&v156 + 1);
      if ( *((_QWORD *)&v156 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v98)(v98);
          if ( _InterlockedExchangeAdd(v98 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v98 + 8LL))(v98);
        }
      }
      std::string::_Tidy_deallocate(&v160);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v157);
      result = 0;
    }
    else
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x138,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
        (const char *)(unsigned int)v62,
        v100);
      if ( v61 )
      {
        if ( !_InterlockedDecrement(v61 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
          if ( !_InterlockedDecrement(v61 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
        }
      }
      v64 = (volatile signed __int32 *)*((_QWORD *)&v166 + 1);
      if ( *((_QWORD *)&v166 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v166 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
          if ( !_InterlockedDecrement(v64 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
        }
      }
      std::vector<Microsoft::Basix::Dct::ICE::Agent::TurnServer>::_Tidy(&v164);
      std::vector<std::string>::_Tidy(&v162);
      std::string::_Tidy_deallocate(&v167);
      v65 = (volatile signed __int32 *)v158[1];
      if ( v158[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v158[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
          if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
        }
      }
      v66 = (volatile signed __int32 *)*((_QWORD *)&v156 + 1);
      if ( *((_QWORD *)&v156 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
          if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
        }
      }
      std::string::_Tidy_deallocate(&v160);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v157);
      result = v63;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x169,
                           (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800cab00  push    rbx
0x1800cab02  push    rsi
0x1800cab03  push    rdi
0x1800cab04  push    r12
0x1800cab06  push    r13
0x1800cab08  push    r14
0x1800cab0a  push    r15
0x1800cab0c  mov     eax, 680h
0x1800cab11  call    _alloca_probe
0x1800cab16  sub     rsp, rax
0x1800cab19  mov     rax, cs:__security_cookie
0x1800cab20  xor     rax, rsp
0x1800cab23  mov     [rsp+6B8h+var_48], rax
0x1800cab2b  mov     r15, r8
0x1800cab2e  movzx   ebx, dx
0x1800cab31  mov     r14, rcx
0x1800cab34  xor     r12d, r12d
0x1800cab37  mov     [rsp+6B8h+var_638], r12d
0x1800cab3f  mov     edi, 114h
0x1800cab44  cmp     dx, di
0x1800cab47  jz      loc_1800CAC58
0x1800cab4d  xorps   xmm0, xmm0
0x1800cab50  movups  [rsp+6B8h+var_158], xmm0
0x1800cab58  lea     rcx, [rsp+6B8h+var_158]
0x1800cab60  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1800cab65  nop
0x1800cab66  mov     rax, qword ptr [rsp+6B8h+var_158]
0x1800cab6e  test    rax, rax
0x1800cab71  jz      loc_1800CAC09
0x1800cab77  cmp     [rax+80h], r12b
0x1800cab7e  jz      loc_1800CAC09
0x1800cab84  xorps   xmm0, xmm0
0x1800cab87  movups  [rsp+6B8h+var_628], xmm0
0x1800cab8f  xorps   xmm1, xmm1
0x1800cab92  movdqu  [rsp+6B8h+var_618], xmm1
0x1800cab9b  lea     r8d, [r12+4Eh]
0x1800caba0  lea     rdx, aRdpnanotranspo_2; "rdpnanoTransport.dll load version misma"...
0x1800caba7  lea     rcx, [rsp+6B8h+var_628]
0x1800cabaf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800cabb4  nop
0x1800cabb5  lea     rax, aMicrosoftRdpna_6; "Microsoft::RdpNano::IceWrapperImpl::Ini"...
0x1800cabbc  mov     [rsp+6B8h+var_680], rax
0x1800cabc1  mov     dword ptr [rsp+6B8h+var_688], 82h
0x1800cabc9  lea     r8, aCW1SRdpnanodll_12; "C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\"...
0x1800cabd0  mov     [rsp+6B8h+Str], r8
0x1800cabd5  mov     word ptr [rsp+6B8h+var_698], di
0x1800cabda  movzx   r9d, bx
0x1800cabde  lea     r8, [rsp+6B8h+var_628]
0x1800cabe6  lea     rdx, aRdpnano; "RDPNANO"
0x1800cabed  lea     rcx, [rsp+6B8h+var_158]
0x1800cabf5  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@GGPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@GG1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,ushort,ushort,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,ushort,ushort,char const *,int,char const *)
0x1800cabfa  nop
0x1800cabfb  lea     rcx, [rsp+6B8h+var_628]
0x1800cac03  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800cac08  nop
0x1800cac09  mov     rbx, qword ptr [rsp+6B8h+var_158+8]
0x1800cac11  test    rbx, rbx
0x1800cac14  jz      short loc_1800CAC4E
0x1800cac16  or      edi, 0FFFFFFFFh
0x1800cac19  mov     eax, edi
0x1800cac1b  lock xadd [rbx+8], eax
0x1800cac20  add     eax, edi
0x1800cac22  jnz     short loc_1800CAC4E
0x1800cac24  mov     rax, [rbx]
0x1800cac27  mov     rcx, rbx
0x1800cac2a  mov     rax, [rax]
0x1800cac2d  call    cs:__guard_dispatch_icall_fptr
0x1800cac33  mov     eax, edi
0x1800cac35  lock xadd [rbx+0Ch], eax
0x1800cac3a  add     eax, edi
0x1800cac3c  jnz     short loc_1800CAC4E
0x1800cac3e  mov     rax, [rbx]
0x1800cac41  mov     rcx, rbx
0x1800cac44  mov     rax, [rax+8]
0x1800cac48  call    cs:__guard_dispatch_icall_fptr
0x1800cac4e  mov     eax, 8007051Ah
0x1800cac53  jmp     loc_1800CCC29
0x1800cac58  mov     rcx, cs:g_hRDPNanoLogger
0x1800cac5f  cmp     dword ptr [rcx], 4
0x1800cac62  jbe     short loc_1800CACB0
0x1800cac64  lea     rax, aPingFromInside_0; "Ping from inside IceWrapperImpl::initia"...
0x1800cac6b  mov     [rsp+6B8h+var_608], rax
0x1800cac73  lea     rsi, aRdpnano; "RDPNANO"
0x1800cac7a  mov     [rsp+6B8h+var_600], rsi
0x1800cac82  lea     rax, [rsp+6B8h+var_608]
0x1800cac8a  mov     [rsp+6B8h+Str], rax
0x1800cac8f  lea     rax, [rsp+6B8h+var_600]
0x1800cac97  mov     [rsp+6B8h+var_698], rax
0x1800cac9c  xor     r9d, r9d
0x1800cac9f  xor     r8d, r8d
0x1800caca2  lea     rdx, dword_1804A281C
0x1800caca9  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800cacae  jmp     short loc_1800CACB7
0x1800cacb0  lea     rsi, aRdpnano; "RDPNANO"
0x1800cacb7  test    r15, r15
0x1800cacba  jnz     short loc_1800CACE4
0x1800cacbc  mov     rcx, [rsp+6B8h]; this
0x1800cacc4  mov     ebx, 80070057h
0x1800cacc9  mov     r9d, ebx; char *
0x1800caccc  lea     r8, aCW1SRdpnanodll_12; "C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\"...
0x1800cacd3  mov     edx, 8Eh; void *
0x1800cacd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cacdd  mov     eax, ebx
0x1800cacdf  jmp     loc_1800CCC29
0x1800cace4  mov     rcx, [r15]
0x1800cace7  mov     [r14+68h], rcx
0x1800caceb  mov     rdx, [r15+8]
0x1800cacef  mov     [r14+70h], rdx
0x1800cacf3  mov     rax, [r15+10h]
0x1800cacf7  mov     [r14+78h], rax
0x1800cacfb  test    rcx, rcx
0x1800cacfe  jnz     short loc_1800CAD28
0x1800cad00  mov     rcx, [rsp+6B8h]; this
0x1800cad08  mov     ebx, 80070057h
0x1800cad0d  mov     r9d, ebx; char *
0x1800cad10  lea     r8, aCW1SRdpnanodll_12; "C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\"...
0x1800cad17  mov     edx, 95h; void *
0x1800cad1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cad21  mov     eax, ebx
0x1800cad23  jmp     loc_1800CCC29
0x1800cad28  test    rdx, rdx
0x1800cad2b  jnz     short loc_1800CAD55
0x1800cad2d  mov     rcx, [rsp+6B8h]; this
0x1800cad35  mov     ebx, 80070057h
0x1800cad3a  mov     r9d, ebx; char *
0x1800cad3d  lea     r8, aCW1SRdpnanodll_12; "C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\"...
0x1800cad44  mov     edx, 96h; void *
0x1800cad49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cad4e  mov     eax, ebx
0x1800cad50  jmp     loc_1800CCC29
0x1800cad55  mov     dword ptr [rsp+6B8h+var_608], r12d
0x1800cad5d  lea     rcx, [r14+60h]
0x1800cad61  mov     r9d, 5
0x1800cad67  lea     r8d, [r9-4]
0x1800cad6b  lea     rdx, [rsp+6B8h+var_608]
0x1800cad73  call    ?compare_exchange_strong@?$_Atomic_storage@W4State@IThreadedObject@Pattern@Basix@Microsoft@@$03@std@@QEAA_NAEAW4State@IThreadedObject@Pattern@Basix@Microsoft@@W434567@W4memory_order@2@@Z; std::_Atomic_storage<Microsoft::Basix::Pattern::IThreadedObject::State,4>::compare_exchange_strong(Microsoft::Basix::Pattern::IThreadedObject::State &,Microsoft::Basix::Pattern::IThreadedObject::State,std::memory_order)
0x1800cad78  test    al, al
0x1800cad7a  jnz     short loc_1800CADBB
0x1800cad7c  mov     rcx, [rsp+6B8h]; this
0x1800cad84  mov     eax, dword ptr [rsp+6B8h+var_608]
0x1800cad8b  mov     dword ptr [rsp+6B8h+Str], eax; char *
0x1800cad8f  lea     rax, aStateD; "State=%d"
0x1800cad96  mov     [rsp+6B8h+var_698], rax; unsigned __int64
0x1800cad9b  mov     ebx, 8000000Dh
0x1800cada0  mov     r9d, ebx; char *
0x1800cada3  lea     r8, aCW1SRdpnanodll_12; "C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\"...
0x1800cadaa  mov     edx, 9Ch; void *
0x1800cadaf  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800cadb4  mov     eax, ebx
0x1800cadb6  jmp     loc_1800CCC29
0x1800cadbb  xorps   xmm0, xmm0
0x1800cadbe  movups  [rsp+6B8h+var_F8], xmm0
0x1800cadc6  mov     qword ptr [rsp+6B8h+var_F8], r12
0x1800cadce  mov     ecx, 20h ; ' '; Size
0x1800cadd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cadd8  mov     [rsp+6B8h+var_600], rax
0x1800cade0  test    rax, rax
0x1800cade3  jz      short loc_1800CADEF
0x1800cade5  mov     rcx, rax
0x1800cade8  call    ??0?$multi_index_container@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@U?$indexed_by@U?$sequenced@U?$tag@Una@mpl@boost@@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@@multi_index@boost@@@multi_index@boost@@U?$ordered_non_unique@U?$tag@Uby_name@subs@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@Una@mpl@5@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@@multi_index@boost@@U?$member@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@$0A@@23@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@23@Una@mpl@3@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@@multi_index@boost@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@multi_index@boost@@QEAA@XZ
0x1800caded  jmp     short loc_1800CADF2
0x1800cadef  mov     rax, r12
0x1800cadf2  mov     qword ptr [rsp+6B8h+var_F8+8], rax
0x1800cadfa  lea     r8, [rsp+6B8h+var_F8]
0x1800cae02  mov     rdx, r15
0x1800cae05  mov     rcx, r14
0x1800cae08  call    ?ParseSmilesInitializationParameters@IceWrapperImpl@RdpNano@Microsoft@@AEAAJPEAURdpNanoInitialization@@AEAV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z; Microsoft::RdpNano::IceWrapperImpl::ParseSmilesInitializationParameters(RdpNanoInitialization *,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> &)
0x1800cae0d  mov     ebx, eax
0x1800cae0f  test    eax, eax
0x1800cae11  jns     short loc_1800CAE47
0x1800cae13  lfence
0x1800cae16  mov     rcx, [rsp+6B8h]; this
0x1800cae1e  mov     r9d, eax; char *
0x1800cae21  lea     r8, aCW1SRdpnanodll_12; "C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\"...
0x1800cae28  mov     edx, 0A5h; void *
0x1800cae2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cae32  nop
0x1800cae33  lea     rcx, [rsp+6B8h+var_F8]
0x1800cae3b  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1800cae40  mov     eax, ebx
0x1800cae42  jmp     loc_1800CCC29
0x1800cae47  cmp     [r15+20h], r12d
0x1800cae4b  setnz   al
0x1800cae4e  mov     [r14+109h], al
0x1800cae55  mov     eax, [r15+40h]
0x1800cae59  shr     rax, 0Ch
0x1800cae5d  and     al, 1
0x1800cae5f  mov     [r14+110h], al
0x1800cae66  call    ?GetInstance@GlobalState@RdpNano@Microsoft@@SAAEAV123@XZ; Microsoft::RdpNano::GlobalState::GetInstance(void)
0x1800cae6b  lea     rdx, [rax+10h]
0x1800cae6f  xorps   xmm0, xmm0
0x1800cae72  movups  [rsp+6B8h+var_C8], xmm0
0x1800cae7a  xorps   xmm1, xmm1
0x1800cae7d  movdqu  [rsp+6B8h+var_B8], xmm1
0x1800cae86  mov     r8, [rdx+10h]
0x1800cae8a  cmp     qword ptr [rdx+18h], 0Fh
0x1800cae8f  jbe     short loc_1800CAE94
0x1800cae91  mov     rdx, [rdx]
0x1800cae94  lea     rcx, [rsp+6B8h+var_C8]
0x1800cae9c  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800caea1  nop
0x1800caea2  cmp     qword ptr [rsp+6B8h+var_B8], r12
0x1800caeaa  jbe     short loc_1800CAEE6
0x1800caeac  lfence
0x1800caeaf  mov     rcx, [r14+78h]
0x1800caeb3  test    rcx, rcx
0x1800caeb6  jz      short loc_1800CAEE6
0x1800caeb8  mov     rax, [rcx]
0x1800caebb  lea     rdx, [rsp+6B8h+var_C8]
0x1800caec3  cmp     qword ptr [rsp+6B8h+var_B8+8], 0Fh
0x1800caecc  cmova   rdx, qword ptr [rsp+6B8h+var_C8]
0x1800caed5  mov     r8d, dword ptr [rsp+6B8h+var_B8]
0x1800caedd  mov     rax, [rax]
0x1800caee0  call    cs:__guard_dispatch_icall_fptr
0x1800caee6  mov     dword ptr [rsp+6B8h+var_134], r12d
0x1800caeee  mov     [rsp+6B8h+var_138], 4
0x1800caef9  lea     r9, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x1800caf00  lea     r8, [rsp+6B8h+var_138]; unsigned int *
0x1800caf08  lea     rdx, [rsp+6B8h+var_134]; unsigned __int8 *
0x1800caf10  lea     rcx, aLogIceTraffic; "LOG_ICE_TRAFFIC"
0x1800caf17  call    ?ReadRegistryValueA@@YA_NPEBDPEAEPEAK0@Z; ReadRegistryValueA(char const *,uchar *,ulong *,char const *)
0x1800caf1c  test    al, al
0x1800caf1e  jz      loc_1800CAFAA
0x1800caf24  xorps   xmm0, xmm0
0x1800caf27  movups  [rsp+6B8h+var_5D8], xmm0
0x1800caf2f  xorps   xmm1, xmm1
0x1800caf32  movdqu  [rsp+6B8h+var_5C8], xmm1
0x1800caf3b  mov     r8d, 29h ; ')'
0x1800caf41  lea     rdx, aMicrosoftBasix_369; "Microsoft::Basix::Dct.ICE.LogTrafficLev"...
0x1800caf48  lea     rcx, [rsp+6B8h+var_5D8]
0x1800caf50  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800caf55  mov     [rsp+6B8h+var_5B8], 2Eh ; '.'
0x1800caf5d  lea     rax, [rsp+6B8h+var_5D8]
0x1800caf65  cmp     qword ptr [rsp+6B8h+var_5C8+8], 0Fh
0x1800caf6e  cmova   rax, qword ptr [rsp+6B8h+var_5D8]
0x1800caf77  mov     [rsp+6B8h+var_5B0], rax
0x1800caf7f  lea     r8, [rsp+6B8h+var_134]
0x1800caf87  lea     rdx, [rsp+6B8h+var_5D8]
0x1800caf8f  lea     rcx, [rsp+6B8h+var_F8]
0x1800caf97  call    ??$put@K@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBK@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<ulong>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,ulong const &)
0x1800caf9c  nop
0x1800caf9d  lea     rcx, [rsp+6B8h+var_5D8]
0x1800cafa5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800cafaa  xorps   xmm0, xmm0
0x1800cafad  xorps   xmm1, xmm1
0x1800cafb0  movdqa  [rsp+6B8h+var_108], xmm1
0x1800cafb9  movups  [rsp+6B8h+var_158], xmm0
0x1800cafc1  lea     rcx, [rsp+6B8h+var_158]
0x1800cafc9  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800cafce  nop
0x1800cafcf  mov     rax, qword ptr [rsp+6B8h+var_158]
0x1800cafd7  test    rax, rax
0x1800cafda  jz      short loc_1800CB048
0x1800cafdc  cmp     [rax+80h], r12b
0x1800cafe3  jz      short loc_1800CB048
0x1800cafe5  lfence
0x1800cafe8  mov     ebx, [r15+78h]
0x1800cafec  xorps   xmm0, xmm0
0x1800cafef  movups  [rsp+6B8h+var_628], xmm0
0x1800caff7  xorps   xmm1, xmm1
0x1800caffa  movdqu  [rsp+6B8h+var_618], xmm1
0x1800cb003  mov     r8d, 1Ch
0x1800cb009  lea     rdx, aParametersSmil; "parameters->smilesVersion=%d"
0x1800cb010  lea     rcx, [rsp+6B8h+var_628]
0x1800cb018  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800cb01d  nop
0x1800cb01e  mov     r9d, ebx
0x1800cb021  lea     r8, [rsp+6B8h+var_628]
0x1800cb029  mov     rdx, rsi
0x1800cb02c  lea     rcx, [rsp+6B8h+var_158]
0x1800cb034  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@I@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@I@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint)
0x1800cb039  nop
0x1800cb03a  lea     rcx, [rsp+6B8h+var_628]
0x1800cb042  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800cb047  nop
0x1800cb048  lfence
0x1800cb04b  mov     rbx, qword ptr [rsp+6B8h+var_158+8]
0x1800cb053  or      edi, 0FFFFFFFFh
0x1800cb056  test    rbx, rbx
0x1800cb059  jz      short loc_1800CB090
0x1800cb05b  mov     eax, edi
0x1800cb05d  lock xadd [rbx+8], eax
0x1800cb062  add     eax, edi
0x1800cb064  jnz     short loc_1800CB090
0x1800cb066  mov     rax, [rbx]
0x1800cb069  mov     rcx, rbx
0x1800cb06c  mov     rax, [rax]
0x1800cb06f  call    cs:__guard_dispatch_icall_fptr
0x1800cb075  mov     eax, edi
0x1800cb077  lock xadd [rbx+0Ch], eax
0x1800cb07c  add     eax, edi
0x1800cb07e  jnz     short loc_1800CB090
0x1800cb080  mov     rax, [rbx]
0x1800cb083  mov     rcx, rbx
0x1800cb086  mov     rax, [rax+8]
0x1800cb08a  call    cs:__guard_dispatch_icall_fptr
0x1800cb090  cmp     dword ptr [r15+78h], 0FFFFFFFFh
0x1800cb095  jnz     loc_1800CB1E9
0x1800cb09b  xorps   xmm0, xmm0
0x1800cb09e  movups  [rsp+6B8h+var_158], xmm0
  ... truncated ...
```

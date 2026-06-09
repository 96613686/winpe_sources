# Microsoft::RdpNano::RdpSideTransport::Connect(bool,Microsoft::Basix::Guid const &,RdpNanoSecurityCookieHash const &,RdpNanoCommonInitializationParams const *,RdpNanoClientToListenerConnectionParams const *,RdpNanoMultipathInitializationParams const *,RdpNanoIceInitializationParams const *,RdpNanoRendezvousInitializationParams const *)

- ea: `0x1800e1a60`
- end: `0x1800e3d30`
- name: `?Connect@RdpSideTransport@RdpNano@Microsoft@@UEAAJ_NAEBUGuid@Basix@3@AEBURdpNanoSecurityCookieHash@@PEBURdpNanoCommonInitializationParams@@PEBURdpNanoClientToListenerConnectionParams@@PEBURdpNanoMultipathInitializationParams@@PEBURdpNanoIceInitializationParams@@PEBURdpNanoRendezvousInitializationParams@@@Z`
- size: `8912`
- prototype: `__int64 __fastcall(Microsoft::RdpNano::RdpSideTransport *__hidden this, bool, const struct Microsoft::Basix::Guid *, const struct RdpNanoSecurityCookieHash *, const struct RdpNanoCommonInitializationParams *, const struct RdpNanoClientToListenerConnectionParams *, const struct RdpNanoMultipathInitializationParams *, const struct RdpNanoIceInitializationParams *, const struct RdpNanoRendezvousInitializationParams *)`
- caller_count: `0`
- callee_count: `59`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015b04`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x180018d1c`
- `0x180018ea4`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ab4c`
- `0x18001ae64`
- `0x18001b6b8`
- `0x180021a00`
- `0x180024568`
- `0x180024700`
- `0x180024760`
- `0x180024c14`
- `0x180028820`
- `0x180029d20`
- `0x1800448dc`
- `0x1800c2f14`
- `0x1800c3044`
- `0x1800c320c`
- `0x1800c3524`
- `0x1800c408c`
- `0x1800c4758`
- `0x1800c5ccc`
- `0x1800d0f30`
- `0x1800d1f60`
- `0x1800dd658`
- `0x1800dd97c`
- `0x1800de240`
- `0x1800de3ec`
- `0x1800df5f0`
- `0x1800df65c`
- `0x1800df720`
- `0x1800df844`
- `0x1800e1a60`
- `0x1800e8530`
- `0x1800fa23c`
- `0x1800fdb80`
- `0x1800ff398`
- `0x1801002ac`
- `0x18011634c`
- `0x180122a70`
- `0x1801b5228`
- `0x1802f13d4`
- `0x18031215c`
- `0x180312164`

## string_xrefs

- `0x1800e1ee4`: `Microsoft::Basix::Dct.Smiles.UseSideband`
- `0x1800e2a09`: `iceSourceAdapter->SetISmilesLink(%p)`
- `0x1800e3791`: `Nano General sxsStack Configurations`
- `0x1800e379d`: `sxsStackConfiguration`
- `0x1800e37a9`: `NanoConfigurations`
- `0x1800e2883`: `C:\__w\1\s\rdnanolib\rdnano\RdpSideTransport.cpp`
- `0x1800e1fe6`: `Microsoft::Basix::Dct.RawUdpRdpFilter.WriteCallback`
- `0x1800e1fff`: `Microsoft::Basix::Dct.RawUdpRdpFilter.SecurityCookieHash`
- `0x1800e2091`: `Early create smiles`
- `0x1800e286f`: `Microsoft::RdpNano::RdpSideTransport::Connect`
- `0x1800e2dc3`: `RdpSideTransport::Connect: EXIT hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=137
__int64 __fastcall Microsoft::RdpNano::RdpSideTransport::Connect(
        Microsoft::RdpNano::RdpSideTransport *this,
        bool a2,
        const struct Microsoft::Basix::Guid *a3,
        __m128i *a4,
        const struct RdpNanoCommonInitializationParams *a5,
        const struct RdpNanoClientToListenerConnectionParams *a6,
        const struct RdpNanoMultipathInitializationParams *a7,
        const struct RdpNanoIceInitializationParams *a8,
        const struct RdpNanoRendezvousInitializationParams *a9)
{
  unsigned int v11; // r15d
  int v12; // r12d
  volatile signed __int32 *v13; // rbx
  __m128i v14; // xmm6
  __m128i v15; // xmm7
  int v16; // ecx
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rax
  volatile signed __int32 *v19; // rbx
  Microsoft::RdpNano::ICESourceAdapter *v20; // r15
  __int64 v21; // rcx
  __int64 v22; // r14
  const char *v23; // rdi
  const char *v24; // rbx
  size_t v25; // r8
  size_t v26; // r8
  size_t v27; // r8
  _OWORD *v28; // r15
  __int64 v29; // rax
  volatile signed __int32 *v30; // rbx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r14
  unsigned __int64 v35; // rdi
  __int64 v36; // rax
  __int64 v37; // rcx
  void *v38; // rax
  __int64 v39; // rax
  __int128 *v40; // rax
  __int64 v41; // rdx
  int v42; // ebx
  int v43; // r8d
  __int64 v44; // rdx
  volatile signed __int32 *v45; // rbx
  _WORD *v46; // rdx
  __int64 v47; // rax
  volatile signed __int32 *v48; // rbx
  __int128 *v49; // rax
  int v50; // ecx
  __int64 v51; // r8
  int v52; // r9d
  __int64 v53; // rax
  int v54; // r15d
  int v55; // r8d
  const char *v56; // r9
  volatile signed __int32 *v57; // rbx
  volatile signed __int32 *v58; // rbx
  __int64 v59; // rcx
  __int64 result; // rax
  const void *v61; // r8
  __int64 v62; // rbx
  volatile signed __int32 *v63; // rbx
  Microsoft::RdpNano::ICESourceAdapter *v64; // rcx
  __int64 v65; // rax
  void *v66; // rax
  __int64 v67; // rax
  _QWORD *v68; // rbx
  volatile signed __int32 *v69; // rbx
  unsigned int v70; // r14d
  __int64 v71; // rax
  volatile signed __int32 *v72; // rbx
  volatile signed __int32 *v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rdx
  __int64 v77; // rdx
  int v78; // edi
  _BYTE *v79; // rax
  int v80; // ebx
  __int64 v81; // rax
  __int64 v82; // rdx
  __int64 v83; // rdx
  __int64 v84; // rdx
  int v85; // ebx
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rdx
  __int64 v89; // rdx
  int v90; // edi
  _BYTE *v91; // rax
  unsigned int v92; // ebx
  int v93; // ebx
  __int64 v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rdx
  __int64 v97; // rdx
  int v98; // edi
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rdx
  __int64 v102; // rdx
  unsigned int v103; // edi
  volatile signed __int32 *v104; // rbx
  __int64 v105; // rcx
  int v106; // [rsp+20h] [rbp-788h]
  char *Str; // [rsp+28h] [rbp-780h]
  _BYTE v108[4]; // [rsp+80h] [rbp-728h] BYREF
  int v109; // [rsp+84h] [rbp-724h]
  unsigned int v110; // [rsp+88h] [rbp-720h]
  bool v111; // [rsp+8Ch] [rbp-71Ch]
  unsigned int v112; // [rsp+90h] [rbp-718h]
  __int64 v113[2]; // [rsp+A0h] [rbp-708h] BYREF
  __m128i v114; // [rsp+B0h] [rbp-6F8h]
  __int128 v115; // [rsp+C0h] [rbp-6E8h] BYREF
  __int128 v116; // [rsp+D0h] [rbp-6D8h]
  char v117; // [rsp+E0h] [rbp-6C8h]
  __int128 *v118; // [rsp+E8h] [rbp-6C0h]
  __int128 v119; // [rsp+F0h] [rbp-6B8h] BYREF
  _OWORD v120[2]; // [rsp+100h] [rbp-6A8h] BYREF
  _OWORD v121[2]; // [rsp+120h] [rbp-688h] BYREF
  _OWORD v122[2]; // [rsp+140h] [rbp-668h] BYREF
  _OWORD v123[2]; // [rsp+160h] [rbp-648h] BYREF
  _OWORD v124[2]; // [rsp+180h] [rbp-628h] BYREF
  _OWORD v125[2]; // [rsp+1A0h] [rbp-608h] BYREF
  _OWORD v126[2]; // [rsp+1C0h] [rbp-5E8h] BYREF
  _OWORD v127[2]; // [rsp+1E0h] [rbp-5C8h] BYREF
  _OWORD v128[2]; // [rsp+200h] [rbp-5A8h] BYREF
  _OWORD v129[2]; // [rsp+220h] [rbp-588h] BYREF
  _OWORD v130[2]; // [rsp+240h] [rbp-568h] BYREF
  _OWORD v131[2]; // [rsp+260h] [rbp-548h] BYREF
  _OWORD v132[2]; // [rsp+280h] [rbp-528h] BYREF
  _OWORD v133[2]; // [rsp+2A0h] [rbp-508h] BYREF
  _OWORD v134[2]; // [rsp+2C0h] [rbp-4E8h] BYREF
  _OWORD v135[2]; // [rsp+2E0h] [rbp-4C8h] BYREF
  _OWORD v136[2]; // [rsp+300h] [rbp-4A8h] BYREF
  _OWORD v137[2]; // [rsp+320h] [rbp-488h] BYREF
  __int64 v138[2]; // [rsp+340h] [rbp-468h] BYREF
  __int128 v139; // [rsp+350h] [rbp-458h]
  __int64 v140[2]; // [rsp+360h] [rbp-448h] BYREF
  __int128 v141; // [rsp+370h] [rbp-438h]
  _BYTE v142[32]; // [rsp+380h] [rbp-428h] BYREF
  _BYTE v143[32]; // [rsp+3A0h] [rbp-408h] BYREF
  _BYTE v144[32]; // [rsp+3C0h] [rbp-3E8h] BYREF
  _BYTE v145[32]; // [rsp+3E0h] [rbp-3C8h] BYREF
  _BYTE v146[32]; // [rsp+400h] [rbp-3A8h] BYREF
  _BYTE v147[32]; // [rsp+420h] [rbp-388h] BYREF
  _BYTE v148[32]; // [rsp+440h] [rbp-368h] BYREF
  _BYTE v149[32]; // [rsp+460h] [rbp-348h] BYREF
  _BYTE v150[32]; // [rsp+480h] [rbp-328h] BYREF
  _BYTE v151[32]; // [rsp+4A0h] [rbp-308h] BYREF
  _BYTE v152[32]; // [rsp+4C0h] [rbp-2E8h] BYREF
  _BYTE v153[32]; // [rsp+4E0h] [rbp-2C8h] BYREF
  _BYTE v154[32]; // [rsp+500h] [rbp-2A8h] BYREF
  _BYTE v155[32]; // [rsp+520h] [rbp-288h] BYREF
  _BYTE v156[32]; // [rsp+540h] [rbp-268h] BYREF
  _BYTE v157[32]; // [rsp+560h] [rbp-248h] BYREF
  _BYTE v158[32]; // [rsp+580h] [rbp-228h] BYREF
  _BYTE v159[32]; // [rsp+5A0h] [rbp-208h] BYREF
  char v160[32]; // [rsp+5C0h] [rbp-1E8h] BYREF
  char v161; // [rsp+5E0h] [rbp-1C8h] BYREF
  bool v162[7]; // [rsp+5E1h] [rbp-1C7h] BYREF
  int v163[4]; // [rsp+5E8h] [rbp-1C0h] BYREF
  __int128 v164; // [rsp+5F8h] [rbp-1B0h] BYREF
  int v165; // [rsp+608h] [rbp-1A0h] BYREF
  __int128 v166; // [rsp+610h] [rbp-198h] BYREF
  __m128i si128; // [rsp+620h] [rbp-188h]
  Microsoft::RdpNano::ICESourceAdapter *v168[2]; // [rsp+630h] [rbp-178h] BYREF
  _OWORD v169[2]; // [rsp+640h] [rbp-168h] BYREF
  __int128 v170; // [rsp+660h] [rbp-148h] BYREF
  __int128 v171; // [rsp+670h] [rbp-138h]
  __int128 v172; // [rsp+680h] [rbp-128h] BYREF
  __int128 v173; // [rsp+690h] [rbp-118h]
  __int128 v174; // [rsp+6A0h] [rbp-108h] BYREF
  _OWORD v175[2]; // [rsp+6B0h] [rbp-F8h] BYREF
  __int128 v176; // [rsp+6D0h] [rbp-D8h] BYREF
  __int128 v177; // [rsp+6E0h] [rbp-C8h] BYREF
  _QWORD v178[12]; // [rsp+6F0h] [rbp-B8h] BYREF

  *(_QWORD *)&v175[0] = a3;
  v162[0] = a2;
  *(_QWORD *)&v164 = a8;
  v168[0] = a9;
  v109 = 0;
  v112 = 0;
  v11 = 0;
  v110 = 0;
  v111 = 0;
  v12 = 0;
  v165 = 0;
  v161 = 0;
  v174 = 0;
  try
  {
    Microsoft::RdpNano::ParseContainmentSwitches();
    memset(v178, 0, sizeof(v178));
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::basic_ptree<std::string,boost::any,std::less<std::string>>(
      v178,
      &v174);
    memset(&v178[3], 0, 64);
    v178[11] = 0xFFFFFFFFLL;
    LODWORD(v178[2]) = 2;
    if ( !Microsoft::Basix::Dct::PropertyImpl::IsEnabled(
            (Microsoft::Basix::Dct::PropertyImpl *)v178,
            (const struct Microsoft::Basix::Dct::ContainmentSwitch *)off_1803F1EA0) )
    {
      *(_OWORD *)v163 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v163);
      if ( *(_QWORD *)v163 && *(_BYTE *)(*(_QWORD *)v163 + 128LL) )
      {
        v166 = 0;
        si128 = 0;
        std::string::_Construct<1,char const *>(&v166, "Feature %s was disabled by containment", (const char *)0x26);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *>(
          v163,
          "RDPNANO",
          &v166,
          "TestContainmentFeature");
        std::string::_Tidy_deallocate(&v166);
      }
      v13 = *(volatile signed __int32 **)&v163[2];
      if ( *(_QWORD *)&v163[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v163[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
    }
    *((_BYTE *)this + 49) = v162[0];
    *(_OWORD *)((char *)this + 340) = **(_OWORD **)&v175[0];
    if ( a4 )
    {
      v14 = *a4;
      v15 = a4[1];
    }
    else
    {
      v14 = 0;
      v15 = 0;
      *errno() = 22;
      invalid_parameter_noinfo();
    }
    if ( a5 )
    {
      if ( (*((_BYTE *)a5 + 8) & 0x10) != 0 )
      {
        v110 = 2;
      }
      else
      {
        v16 = v110;
        if ( (*((_BYTE *)a5 + 8) & 2) != 0 )
          v16 = 1;
        v110 = v16;
      }
      v12 = *((_DWORD *)a5 + 5);
      v165 = v12;
      *((_BYTE *)this + 52) = v12 != 0;
      *((_BYTE *)this + 60) = (*((_BYTE *)a5 + 8) & 4) != 0;
      v111 = (*((_BYTE *)a5 + 8) & 8) != 0;
    }
    _InterlockedAdd(
      (volatile signed __int32 *)(*(__int64 (__fastcall **)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(Microsoft::RdpNano::RdpSideTransport::s_connectionIdNext),
      2u);
    v121[0] = 0;
    if ( a7 )
    {
      v11 = 3;
      if ( *(_DWORD *)a7 != 3 )
        v11 = 0;
      *((_BYTE *)this + 51) = *((_BYTE *)a7 + 8) & 1;
      v161 = (*((_BYTE *)a7 + 8) & 2) != 0;
    }
    *(_OWORD *)v163 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v163);
    if ( *(_QWORD *)v163 && *(_BYTE *)(*(_QWORD *)v163 + 128LL) )
    {
      v166 = 0;
      si128 = 0;
      std::string::_Construct<1,char const *>(&v166, "smilesVersion=%d", 16);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int>(
        v163,
        "RDPNANO",
        &v166,
        v11);
      std::string::_Tidy_deallocate(&v166);
    }
    v17 = *(volatile signed __int32 **)&v163[2];
    if ( *(_QWORD *)&v163[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v163[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v108[0] = v11 != 0;
    v176 = 0;
    v18 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::ISmiles::ISmilesCallback>(
            (char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 16,
            v169);
    v120[0] = *(_OWORD *)((char *)this + 340);
    Microsoft::Basix::Containers::AnyPTreeFromPairs<char const *,Microsoft::Basix::Guid,char const *,bool,char const *,enum Microsoft::Basix::Dct::SMILES_VER,char const *,bool,char const *,unsigned int,char const *,bool,char const *,std::weak_ptr<Microsoft::Basix::Dct::ISmiles::ISmilesCallback>>(
      (unsigned int)&v176,
      (unsigned int)"Microsoft::Basix::Dct.ActivityId",
      (unsigned int)v120,
      (unsigned int)"Microsoft::Basix::Dct.IsServerConnection",
      *((_BYTE *)this + 49),
      (__int64)"Microsoft::Basix::Dct.ICE.Smiles.Version",
      v11,
      (__int64)"Microsoft::Basix::Dct.ICE.Smiles.Enabled",
      v11 != 0,
      (__int64)"Microsoft::Basix::Dct.Transport.AutoReconnectionTimeoutSeconds",
      v12,
      (__int64)"Microsoft::Basix::Dct.Smiles.UseSideband",
      v161,
      (__int64)"Microsoft::Basix::Dct.Smiles.Callback",
      v18);
    v119 = 0;
    Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::IAsyncTransport::WriteCompletionCallback>(
      (char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 16,
      &v119);
    v177 = 0;
    v120[0] = 0;
    if ( *((_QWORD *)&v119 + 1) )
    {
      v120[0] = v119;
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v119 + 1) + 12LL), 1u);
    }
    *(__m128i *)v113 = v14;
    v114 = v15;
    v169[0] = *(_OWORD *)((char *)this + 340);
    Microsoft::Basix::Containers::AnyPTreeFromPairs<char const *,Microsoft::Basix::Guid,char const *,Microsoft::RdpNano::SecurityCookieHash,char const *,std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::WriteCompletionCallback>,char const *,unsigned int>(
      (unsigned int)&v177,
      (unsigned int)"Microsoft::Basix::Dct.ActivityId",
      (unsigned int)v169,
      (unsigned int)"Microsoft::Basix::Dct.RawUdpRdpFilter.SecurityCookieHash",
      (__int64)v113,
      (__int64)"Microsoft::Basix::Dct.RawUdpRdpFilter.WriteCallback",
      (__int64)v120,
      (__int64)"Microsoft::Basix::Dct.Transport.AutoReconnectionTimeoutSeconds",
      v12);
    Microsoft::RdpNano::RdpSideTransport::StartSmiles(this, &v176, &v177, &v174);
    *(_OWORD *)v163 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v163);
    if ( *(_QWORD *)v163 && *(_BYTE *)(*(_QWORD *)v163 + 128LL) )
    {
      v166 = 0;
      si128 = 0;
      std::string::_Construct<1,char const *>(&v166, "Early create smiles", 19);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        v163,
        "RDPNANO",
        &v166);
      std::string::_Tidy_deallocate(&v166);
    }
    v19 = *(volatile signed __int32 **)&v163[2];
    if ( *(_QWORD *)&v163[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v163[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    v20 = v168[0];
    if ( v168[0] && *((_QWORD *)v168[0] + 2) )
    {
      v21 = *((_QWORD *)v168[0] + 1);
      v161 = (v21 & 2) != 0;
      v162[0] = (v21 & 4) != 0;
      v22 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::RdpNano::SourceAdapter::Delegate>(
              (char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 16,
              v163);
      v23 = (const char *)&Str1;
      v24 = (const char *)&Str1;
      if ( *((_QWORD *)v20 + 4) )
        v24 = (const char *)*((_QWORD *)v20 + 4);
      v172 = 0;
      v173 = 0;
      v25 = strlen(v24);
      std::string::_Construct<1,char const *>(&v172, v24, v25);
      v170 = 0;
      v171 = 0;
      v26 = strlen(*((const char **)v20 + 2));
      std::string::_Construct<1,char const *>(&v170, *((const char **)v20 + 2), v26);
      if ( *((_QWORD *)v20 + 3) )
        v23 = (const char *)*((_QWORD *)v20 + 3);
      v166 = 0;
      si128 = 0;
      v27 = strlen(v23);
      std::string::_Construct<1,char const *>(&v166, v23, v27);
      v28 = (_OWORD *)((char *)this + 340);
      v29 = std::make_shared<Microsoft::RdpNano::RendezvousSourceAdapter,std::string,std::string,std::string,bool &,Microsoft::Basix::Guid &,unsigned int &,bool &,bool &,std::weak_ptr<Microsoft::RdpNano::SourceAdapter::Delegate>,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> &>(
              (unsigned int)v169,
              (unsigned int)&v166,
              (unsigned int)&v170,
              (unsigned int)&v172,
              (__int64)this + 49,
              (__int64)this + 340,
              (__int64)&v165,
              (__int64)&v161,
              (__int64)v162,
              v22,
              (__int64)&v174);
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
        (char *)this + 128,
        v29);
      v30 = (volatile signed __int32 *)*((_QWORD *)&v169[0] + 1);
      if ( *((_QWORD *)&v169[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
          if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        }
      }
      std::string::_Tidy_deallocate(&v166);
      std::string::_Tidy_deallocate(&v170);
      std::string::_Tidy_deallocate(&v172);
      v31 = *(_QWORD *)&v163[2];
      if ( *(_QWORD *)&v163[2]
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v163[2] + 12LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      }
      v32 = *((_QWORD *)this + 16);
      *(_OWORD *)v163 = 0;
      v33 = *((_QWORD *)this + 23);
      if ( v33 )
        _InterlockedAdd((volatile signed __int32 *)(v33 + 8), 1u);
      *(_QWORD *)v163 = *((_QWORD *)this + 22);
      *(_QWORD *)&v163[2] = *((_QWORD *)this + 23);
      Microsoft::RdpNano::SourceAdapter::SetISmilesLink(v32, v163);
    }
    else
    {
      v28 = (_OWORD *)((char *)this + 340);
    }
    v34 = v164;
    if ( (_QWORD)v164 )
    {
      v35 = *(_QWORD *)(v164 + 8) & 0xFFFFFFFFFFFFFFFDuLL;
      *(_OWORD *)v168 = 0;
      v36 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::RdpNano::SourceAdapter::Delegate>(
              (char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 16,
              v169);
      std::make_shared<Microsoft::RdpNano::ICESourceAdapter,std::weak_ptr<Microsoft::RdpNano::SourceAdapter::Delegate>,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> &>(
        v168,
        v36,
        &v174);
      v37 = *((_QWORD *)&v169[0] + 1);
      if ( *((_QWORD *)&v169[0] + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169[0] + 1) + 12LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
      }
      v170 = 0;
      *(_QWORD *)&v171 = 0;
      v172 = 0;
      *(_QWORD *)&v173 = 0;
      v175[0] = 0u;
      v38 = operator new(0x20u);
      *(_QWORD *)&v164 = v38;
      if ( v38 )
        v39 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v38);
      else
        v39 = 0;
      *((_QWORD *)&v175[0] + 1) = v39;
      v115 = 0;
      v116 = 0;
      std::string::_Construct<1,char const *>(&v115, "Microsoft::Basix::Dct.ICE.Smiles.Enabled", 40);
      v117 = 46;
      v40 = &v115;
      if ( *((_QWORD *)&v116 + 1) > 0xFu )
        v40 = (__int128 *)v115;
      v118 = v40;
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<bool>(v175, &v115, v108);
      std::string::_Tidy_deallocate(&v115);
      v166 = 0;
      si128.m128i_i64[0] = 0;
      si128.m128i_i64[1] = 15;
      LOBYTE(v166) = 0;
      v41 = *(_QWORD *)(v34 + 24);
      if ( v41 )
      {
        std::string::assign(&v166, v41);
        if ( si128.m128i_i64[0] )
        {
          v42 = Microsoft::RdpNano::ICESourceAdapter::ParseIceServers(&v166, &v170, &v172);
          if ( v42 < 0 )
          {
            v164 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v164);
            v44 = 0;
            if ( (_QWORD)v164 && *(_BYTE *)(v164 + 128) )
            {
              std::string::string(
                v113,
                "ICESourceAdapter::ParseIceServers failed: 0x%x. Proceeding without STUN and TURN servers.",
                v43);
              _mm_lfence();
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,long>(
                &v164,
                "RDPNANO",
                v113,
                (unsigned int)v42);
              std::string::_Tidy_deallocate(v113);
            }
            v45 = (volatile signed __int32 *)*((_QWORD *)&v164 + 1);
            if ( *((_QWORD *)&v164 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v164 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v45)(v45, v44);
                if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
              }
            }
          }
        }
      }
      v46 = (_WORD *)(v34 + 32);
      if ( *(_WORD *)(v34 + 34) )
      {
        v47 = *v46
            ? std::make_shared<Microsoft::Basix::Dct::PortRangeAllocator,unsigned short &,int>(v169)
            : std::make_shared<Microsoft::Basix::Dct::EphemeralPortAllocator,>(v169);
        std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
          (char *)this + 200,
          v47);
        v48 = (volatile signed __int32 *)*((_QWORD *)&v169[0] + 1);
        if ( *((_QWORD *)&v169[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
            if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
          }
        }
      }
      if ( v111 )
      {
        v108[0] = 1;
        v115 = 0;
        v116 = 0;
        std::string::_Construct<1,char const *>(&v115, "Microsoft::Basix::Dct.ICE.DisableDelayTrace", 43);
        v117 = 46;
        v49 = &v115;
        if ( *((_QWORD *)&v116 + 1) > 0xFu )
          v49 = (__int128 *)v115;
        v118 = v49;
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<bool>(v175, &v115, v108);
        std::string::_Tidy_deallocate(&v115);
      }
      v50 = (int)v168[0];
      v51 = *(_QWORD *)(v34 + 40);
      v52 = *(_DWORD *)(v34 + 16);
      v164 = 0;
      v53 = *((_QWORD *)this + 26);
      if ( v53 )
        _InterlockedAdd((volatile signed __int32 *)(v53 + 8), 1u);
      v164 = *(_OWORD *)((char *)this + 200);
      v169[0] = *v28;
      LOBYTE(v46) = *((_BYTE *)this + 49);
      v54 = Microsoft::RdpNano::ICESourceAdapter::Initialize(
              v50,
              (_DWORD)v46,
              (unsigned int)v169,
              (unsigned int)&v164,
              v35,
              v52,
              v51,
              (__int64)&v170,
              (__int64)&v172,
              (__int64)v175);
      v112 = v54;
      v164 = 0;
      if ( v54 < 0 )
      {
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v164);
        if ( (_QWORD)v164 && *(_BYTE *)(v164 + 128) )
        {
          std::string::string(v113, "iceSourceAdapter->Initialize Failed, HR:%x\n    %s(%d): %s()", v55, v56, v106, Str);
          _mm_lfence();
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,long,char const *,int,char const *>(
            (unsigned int)&v164,
            (unsigned int)"RDPNANO",
            (unsigned int)v113,
            v54,
            (__int64)"C:\\__w\\1\\s\\rdnanolib\\rdnano\\RdpSideTransport.cpp",
            194,
            (__int64)"Microsoft::RdpNano::RdpSideTransport::Connect");
          std::string::_Tidy_deallocate(v113);
        }
        _mm_lfence();
        v57 = (volatile signed __int32 *)*((_QWORD *)&v164 + 1);
        if ( *((_QWORD *)&v164 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v164 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
            if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
          }
        }
        std::string::_Tidy_deallocate(&v166);
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v175);
        std::vector<Microsoft::Basix::Dct::ICE::Agent::TurnServer>::_Tidy(&v172);
        std::vector<std::string>::_Tidy(&v170);
        v58 = (volatile signed __int32 *)v168[1];
        if ( v168[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v168[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
            if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
          }
        }
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v177);
        v59 = *((_QWORD *)&v119 + 1);
        if ( *((_QWORD *)&v119 + 1)
          && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v119 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
        }
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v176);
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v178);
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v174);
        return (unsigned int)v54;
      }
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v164);
      if ( (_QWORD)v164 && *(_BYTE *)(v164 + 128) )
      {
        v62 = *((_QWORD *)this + 22);
        std::string::string(v113, "iceSourceAdapter->SetISmilesLink(%p)", v61);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(
          &v164,
          "RDPNANO",
          v113,
          v62);
        std::string::_Tidy_deallocate(v113);
      }
      v63 = (volatile signed __int32 *)*((_QWORD *)&v164 + 1);
      if ( *((_QWORD *)&v164 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v164 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
          if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
        }
      }
      v64 = v168[0];
      v164 = 0;
      v65 = *((_QWORD *)this + 23);
      if ( v65 )
        _InterlockedAdd((volatile signed __int32 *)(v65 + 8), 1u);
      v164 = *((_OWORD *)this + 11);
      Microsoft::RdpNano::SourceAdapter::SetISmilesLink(v64, &v164);
      Microsoft::RdpNano::ICESourceAdapter::Start(v168[0]);
      memset(v163, 0, sizeof(v163));
      v66 = operator new(0x20u);
      *(_QWORD *)&v164 = v66;
      if ( v66 )
        v67 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v66);
      else
        v67 = 0;
      *(_QWORD *)&v163[2] = v67;
      v164 = (unsigned __int64)this + 256;
      if ( Mtx_lock((Microsoft::RdpNano::RdpSideTransport *)((char *)this + 256)) )
        std::_Throw_Cpp_error(5);
      if ( *((_DWORD *)this + 83) == 0x7FFFFFFF )
      {
        *((_DWORD *)this + 83) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      BYTE8(v164) = 1;
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
        (char *)this + 112,
        v168);
      v68 = (_QWORD *)((char *)this + 224);
      if ( *((_QWORD *)this + 30) && ((*((_BYTE *)this + 216) >> 4) & 0xF) == 0 )
      {
        v169[0] = 0;
        Microsoft::Basix::Containers::AnyPTreeFromJson(v169, (char *)this + 224);
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::operator=(v163, v169);
        *((_QWORD *)this + 30) = 0;
        if ( *((_QWORD *)this + 31) > 0xFu )
          v68 = (_QWORD *)*v68;
        *(_BYTE *)v68 = 0;
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v169);
      }
      Mtx_unlock((Microsoft::RdpNano::RdpSideTransport *)((char *)this + 256));
      if ( *(_QWORD *)((*(_QWORD *)&v163[2] & -(__int64)(*(_QWORD *)&v163[2] != -17)) + 0x18) )
      {
        Microsoft::RdpNano::ICESourceAdapter::OnReceiveSideBandData(v168[0], *((unsigned __int16 *)this + 108), v163);
        *((_WORD *)this + 108) = 0;
      }
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v163);
      std::string::_Tidy_deallocate(&v166);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v175);
      std::vector<Microsoft::Basix::Dct::ICE::Agent::TurnServer>::_Tidy(&v172);
      std::vector<std::string>::_Tidy(&v170);
      v69 = (volatile signed __int32 *)v168[1];
      if ( v168[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v168[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
          if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
        }
      }
    }
    else
    {
      v54 = v112;
    }
    v70 = v110;
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 12) + 144LL))(*((_QWORD *)this + 12), v110);
    if ( *((_BYTE *)this + 60) )
    {
      v165 = 2;
      v71 = std::make_shared<Microsoft::RdpNano::IceRestartAgent,std::shared_ptr<Microsoft::RdpNano::ICESourceAdapter> &,enum Microsoft::RdpNano::IceSourceState>(
              v169,
              (char *)this + 112,
              &v165);
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
        (char *)this + 64,
        v71);
      v72 = (volatile signed __int32 *)*((_QWORD *)&v169[0] + 1);
      if ( *((_QWORD *)&v169[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
          if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
        }
      }
      Microsoft::RdpNano::IceRestartAgent::Start(*((Microsoft::RdpNano::IceRestartAgent **)this + 8));
    }
    *(_OWORD *)v163 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v163);
    if ( *(_QWORD *)v163 && *(_BYTE *)(*(_QWORD *)v163 + 128LL) )
    {
      v166 = 0;
      si128 = 0;
      std::string::_Construct<1,char const *>(&v166, "RdpSideTransport::Connect: EXIT hr=0x%x", 39);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,long>(
        v163,
        "RDPNANO",
        &v166,
        (unsigned int)v54);
      std::string::_Tidy_deallocate(&v166);
    }
    v73 = *(volatile signed __int32 **)&v163[2];
    if ( *(_QWORD *)&v163[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v163[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v73)(v73);
        if ( _InterlockedExchangeAdd(v73 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v73 + 8LL))(v73);
      }
    }
    *(_OWORD *)v163 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v163);
    if ( *(_QWORD *)v163 && *(_BYTE *)(*(_QWORD *)v163 + 128LL) )
    {
      *(_QWORD *)&v164 = v140;
      if ( v70 )
      {
        memset(v128, 0, sizeof(v128));
        std::string::_Construct<1,char const *>(v128, "true", 4);
        v109 = 1;
        memset(v129, 0, sizeof(v129));
        std::string::_Construct<1,char const *>(v129, ":", 1);
        v109 = 3;
        memset(v130, 0, sizeof(v130));
        std::string::_Construct<1,char const *>(v130, "\"", 1);
        v109 = 7;
        memset(v131, 0, sizeof(v131));
        std::string::_Construct<1,char const *>(v131, "\"", 1);
        v109 = 15;
        v74 = std::operator+<char>(v158, v131, "sequencerMode");
        v109 = 31;
        LOBYTE(v75) = v108[0];
        std::string::string(v153, v75, v74, v130);
        v109 = 63;
        LOBYTE(v76) = v108[0];
        std::string::string(v152, v76, v153, v129);
        v109 = 127;
        LOBYTE(v77) = v108[0];
        std::string::string(v151, v77, v152, v128);
        v78 = 917504;
        v79 = v151;
        v80 = 255;
      }
      else
      {
        memset(v132, 0, sizeof(v132));
        std::string::_Construct<1,char const *>(v132, "false", 5);
        v109 = 256;
        memset(v133, 0, sizeof(v133));
        std::string::_Construct<1,char const *>(v133, ":", 1);
        v109 = 768;
        memset(v123, 0, sizeof(v123));
        std::string::_Construct<1,char const *>(v123, "\"", 1);
        v109 = 1792;
        memset(v127, 0, sizeof(v127));
        std::string::_Construct<1,char const *>(v127, "\"", 1);
        v109 = 3840;
        v81 = std::operator+<char>(v157, v127, "sequencerMode");
        v109 = 7936;
        LOBYTE(v82) = v108[0];
        std::string::string(v150, v82, v81, v123);
        v109 = 16128;
        LOBYTE(v83) = v108[0];
        std::string::string(v149, v83, v150, v133);
        v109 = 32512;
        LOBYTE(v84) = v108[0];
        std::string::string(v148, v84, v149, v132);
        v78 = 7340032;
        v79 = v148;
        v80 = 65280;
      }
      v109 = v80;
      *(_OWORD *)v140 = *(_OWORD *)v79;
      v141 = *((_OWORD *)v79 + 1);
      *((_QWORD *)v79 + 2) = 0;
      *((_QWORD *)v79 + 3) = 15;
      *v79 = 0;
      v168[0] = (Microsoft::RdpNano::ICESourceAdapter *)v138;
      if ( *((_BYTE *)this + 60) )
      {
        memset(v126, 0, sizeof(v126));
        std::string::_Construct<1,char const *>(v126, "true", 4);
        v85 = v80 | 0x10000;
        v109 = v85;
        memset(v125, 0, sizeof(v125));
        std::string::_Construct<1,char const *>(v125, ":", 1);
        v85 |= 0x20000u;
        v109 = v85;
        memset(v124, 0, sizeof(v124));
        std::string::_Construct<1,char const *>(v124, "\"", 1);
        v85 |= 0x40000u;
        v109 = v85;
        memset(v122, 0, sizeof(v122));
        std::string::_Construct<1,char const *>(v122, "\"", 1);
        v85 |= 0x80000u;
        v109 = v85;
        v86 = std::operator+<char>(v156, v122, "IceRestartEnabled");
        v85 |= 0x100000u;
        v109 = v85;
        LOBYTE(v87) = v108[0];
        std::string::string(v147, v87, v86, v124);
        v85 |= 0x200000u;
        v109 = v85;
        LOBYTE(v88) = v108[0];
        std::string::string(v146, v88, v147, v125);
        v85 |= 0x400000u;
        v109 = v85;
        LOBYTE(v89) = v108[0];
        std::string::string(v145, v89, v146, v126);
        v90 = v78 | 0x3800000;
        v91 = v145;
        v92 = v85 | 0x800000;
      }
      else
      {
        memset(v137, 0, sizeof(v137));
        std::string::_Construct<1,char const *>(v137, "false", 5);
        v93 = v80 | 0x1000000;
        v109 = v93;
        memset(v136, 0, sizeof(v136));
        std::string::_Construct<1,char const *>(v136, ":", 1);
        v93 |= 0x2000000u;
        v109 = v93;
        memset(v135, 0, sizeof(v135));
        std::string::_Construct<1,char const *>(v135, "\"", 1);
        v93 |= 0x4000000u;
        v109 = v93;
        memset(v134, 0, sizeof(v134));
        std::string::_Construct<1,char const *>(v134, "\"", 1);
        v93 |= 0x8000000u;
        v109 = v93;
        v94 = std::operator+<char>(v155, v134, "IceRestartEnabled");
        v93 |= 0x10000000u;
        v109 = v93;
        LOBYTE(v95) = v108[0];
        std::string::string(v154, v95, v94, v135);
        v93 |= 0x20000000u;
        v109 = v93;
        LOBYTE(v96) = v108[0];
        std::string::string(v142, v96, v154, v136);
        v93 |= 0x40000000u;
        v109 = v93;
        LOBYTE(v97) = v108[0];
        std::string::string(v143, v97, v142, v137);
        v90 = v78 | 0x1C000000;
        v91 = v143;
        v92 = v93 | 0x80000000;
      }
      v109 = v92;
      *(_OWORD *)v138 = *(_OWORD *)v91;
      v139 = *((_OWORD *)v91 + 1);
      *((_QWORD *)v91 + 2) = 0;
      *((_QWORD *)v91 + 3) = 15;
      *v91 = 0;
      memset(v120, 0, sizeof(v120));
      std::string::_Construct<1,char const *>(v120, "true", 4);
      v98 = v90 | 1;
      v110 = v98;
      memset(v169, 0, sizeof(v169));
      std::string::_Construct<1,char const *>(v169, ":", 1);
      v98 |= 2u;
      v110 = v98;
      v172 = 0;
      v173 = 0;
      std::string::_Construct<1,char const *>(&v172, "\"", 1);
      v98 |= 4u;
      v110 = v98;
      v170 = 0;
      v171 = 0;
      std::string::_Construct<1,char const *>(&v170, "\"", 1);
      v98 |= 8u;
      v110 = v98;
      v99 = std::operator+<char>(v159, &v170, "OptimizedStackUsed");
      v98 |= 0x10u;
      v110 = v98;
      LOBYTE(v100) = v108[0];
      std::string::string(v144, v100, v99, &v172);
      v98 |= 0x20000020u;
      v110 = v98;
      LOBYTE(v101) = v108[0];
      std::string::string(v175, v101, v144, v169);
      v98 |= 0x40000040u;
      v110 = v98;
      LOBYTE(v102) = v108[0];
      std::string::string(&v166, v102, v175, v120);
      v103 = v98 | 0x80000080;
      v110 = v103;
      *(_OWORD *)v113 = v166;
      v114 = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v166) = 0;
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
        (int)v163,
        (int)"RD_CHECKPOINT",
        0,
        (int)"NanoConfigurations",
        "sxsStackConfiguration",
        "Nano General sxsStack Configurations",
        (__int64)v113,
        (__int64)v138,
        (__int64)v140);
      if ( (v103 & 0x8000) != 0 )
      {
        LOWORD(v103) = v103 & 0x7FFF;
        std::string::_Tidy_deallocate(v121);
      }
      if ( (v103 & 0x4000) != 0 )
      {
        LOWORD(v103) = v103 & 0xBFFF;
        std::string::_Tidy_deallocate(v121);
      }
      if ( (v103 & 0x2000) != 0 )
      {
        LOWORD(v103) = v103 & 0xDFFF;
        std::string::_Tidy_deallocate(v121);
      }
      if ( (v103 & 0x1000) != 0 )
      {
        LOWORD(v103) = v103 & 0xEFFF;
        std::string::_Tidy_deallocate(v160);
      }
      if ( (v103 & 0x800) != 0 )
      {
        LOWORD(v103) = v103 & 0xF7FF;
        std::string::_Tidy_deallocate(&v115);
      }
      if ( (v103 & 0x400) != 0 )
      {
        LOWORD(v103) = v103 & 0xFBFF;
        std::string::_Tidy_deallocate(v121);
      }
      if ( (v103 & 0x200) != 0 )
      {
        LOWORD(v103) = v103 & 0xFDFF;
        std::string::_Tidy_deallocate(v121);
      }
      if ( (v103 & 0x100) != 0 )
        std::string::_Tidy_deallocate(v121);
      if ( (v103 & 0x80u) != 0 )
      {
        LOBYTE(v103) = v103 & 0x7F;
        std::string::_Tidy_deallocate(&v166);
      }
      if ( (v103 & 0x40) != 0 )
      {
        LOBYTE(v103) = v103 & 0xBF;
        std::string::_Tidy_deallocate(v175);
      }
      if ( (v103 & 0x20) != 0 )
      {
        LOBYTE(v103) = v103 & 0xDF;
        std::string::_Tidy_deallocate(v144);
      }
      if ( (v103 & 0x10) != 0 )
      {
        LOBYTE(v103) = v103 & 0xEF;
        std::string::_Tidy_deallocate(v159);
      }
      if ( (v103 & 8) != 0 )
      {
        LOBYTE(v103) = v103 & 0xF7;
        std::string::_Tidy_deallocate(&v170);
      }
      if ( (v103 & 4) != 0 )
      {
        LOBYTE(v103) = v103 & 0xFB;
        std::string::_Tidy_deallocate(&v172);
      }
      if ( (v103 & 2) != 0 )
      {
        LOBYTE(v103) = v103 & 0xFD;
        std::string::_Tidy_deallocate(v169);
      }
      if ( (v103 & 1) != 0 )
        std::string::_Tidy_deallocate(v120);
      if ( (v92 & 0x80000000) != 0 )
      {
        v92 &= ~0x80000000;
        std::string::_Tidy_deallocate(v143);
      }
      if ( (v92 & 0x40000000) != 0 )
      {
        v92 &= ~0x40000000u;
        std::string::_Tidy_deallocate(v142);
      }
      if ( (v92 & 0x20000000) != 0 )
      {
        v92 &= ~0x20000000u;
        std::string::_Tidy_deallocate(v154);
      }
      if ( (v92 & 0x10000000) != 0 )
      {
        v92 &= ~0x10000000u;
        std::string::_Tidy_deallocate(v155);
      }
      if ( (v92 & 0x8000000) != 0 )
      {
        v92 &= ~0x8000000u;
        std::string::_Tidy_deallocate(v134);
      }
      if ( (v92 & 0x4000000) != 0 )
      {
        v92 &= ~0x4000000u;
        std::string::_Tidy_deallocate(v135);
      }
      if ( (v92 & 0x2000000) != 0 )
      {
        v92 &= ~0x2000000u;
        std::string::_Tidy_deallocate(v136);
      }
      if ( (v92 & 0x1000000) != 0 )
      {
        v92 &= ~0x1000000u;
        std::string::_Tidy_deallocate(v137);
      }
      if ( (v92 & 0x800000) != 0 )
      {
        v92 &= ~0x800000u;
        std::string::_Tidy_deallocate(v145);
      }
      if ( (v92 & 0x400000) != 0 )
      {
        v92 &= ~0x400000u;
        std::string::_Tidy_deallocate(v146);
      }
      if ( (v92 & 0x200000) != 0 )
      {
        v92 &= ~0x200000u;
        std::string::_Tidy_deallocate(v147);
      }
      if ( (v92 & 0x100000) != 0 )
      {
        v92 &= ~0x100000u;
        std::string::_Tidy_deallocate(v156);
      }
      if ( (v92 & 0x80000) != 0 )
      {
        v92 &= ~0x80000u;
        std::string::_Tidy_deallocate(v122);
      }
      if ( (v92 & 0x40000) != 0 )
      {
        v92 &= ~0x40000u;
        std::string::_Tidy_deallocate(v124);
      }
      if ( (v92 & 0x20000) != 0 )
      {
        v92 &= ~0x20000u;
        std::string::_Tidy_deallocate(v125);
      }
      if ( (v92 & 0x10000) != 0 )
        std::string::_Tidy_deallocate(v126);
      if ( (v92 & 0x8000) != 0 )
      {
        LOWORD(v92) = v92 & 0x7FFF;
        std::string::_Tidy_deallocate(v148);
      }
      if ( (v92 & 0x4000) != 0 )
      {
        LOWORD(v92) = v92 & 0xBFFF;
        std::string::_Tidy_deallocate(v149);
      }
      if ( (v92 & 0x2000) != 0 )
      {
        LOWORD(v92) = v92 & 0xDFFF;
        std::string::_Tidy_deallocate(v150);
      }
      if ( (v92 & 0x1000) != 0 )
      {
        LOWORD(v92) = v92 & 0xEFFF;
        std::string::_Tidy_deallocate(v157);
      }
      if ( (v92 & 0x800) != 0 )
      {
        LOWORD(v92) = v92 & 0xF7FF;
        std::string::_Tidy_deallocate(v127);
      }
      if ( (v92 & 0x400) != 0 )
      {
        LOWORD(v92) = v92 & 0xFBFF;
        std::string::_Tidy_deallocate(v123);
      }
      if ( (v92 & 0x200) != 0 )
      {
        LOWORD(v92) = v92 & 0xFDFF;
        std::string::_Tidy_deallocate(v133);
      }
      if ( (v92 & 0x100) != 0 )
        std::string::_Tidy_deallocate(v132);
      if ( (v92 & 0x80u) != 0 )
      {
        LOBYTE(v92) = v92 & 0x7F;
        std::string::_Tidy_deallocate(v151);
      }
      if ( (v92 & 0x40) != 0 )
      {
        LOBYTE(v92) = v92 & 0xBF;
        std::string::_Tidy_deallocate(v152);
      }
      if ( (v92 & 0x20) != 0 )
      {
        LOBYTE(v92) = v92 & 0xDF;
        std::string::_Tidy_deallocate(v153);
      }
      if ( (v92 & 0x10) != 0 )
      {
        LOBYTE(v92) = v92 & 0xEF;
        std::string::_Tidy_deallocate(v158);
      }
      if ( (v92 & 8) != 0 )
      {
        LOBYTE(v92) = v92 & 0xF7;
        std::string::_Tidy_deallocate(v131);
      }
      if ( (v92 & 4) != 0 )
      {
        LOBYTE(v92) = v92 & 0xFB;
        std::string::_Tidy_deallocate(v130);
      }
      if ( (v92 & 2) != 0 )
      {
        LOBYTE(v92) = v92 & 0xFD;
        std::string::_Tidy_deallocate(v129);
      }
      if ( (v92 & 1) != 0 )
        std::string::_Tidy_deallocate(v128);
    }
    v104 = *(volatile signed __int32 **)&v163[2];
    if ( *(_QWORD *)&v163[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v163[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v104)(v104);
        if ( _InterlockedExchangeAdd(v104 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v104 + 8LL))(v104);
      }
    }
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v177);
    v105 = *((_QWORD *)&v119 + 1);
    if ( *((_QWORD *)&v119 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v119 + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 8LL))(v105);
    }
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v176);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v178);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v174);
    result = v112;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return 2147942974LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800e1a60  mov     [rsp+arg_8], rbx
0x1800e1a65  mov     [rsp+arg_10], rsi
0x1800e1a6a  push    rdi
0x1800e1a6b  push    r12
0x1800e1a6d  push    r13
0x1800e1a6f  push    r14
0x1800e1a71  push    r15
0x1800e1a73  mov     eax, 780h
0x1800e1a78  call    _alloca_probe
0x1800e1a7d  sub     rsp, rax
0x1800e1a80  movaps  [rsp+7A8h+var_38], xmm6
0x1800e1a88  movaps  [rsp+7A8h+var_48], xmm7
0x1800e1a90  mov     rax, cs:__security_cookie
0x1800e1a97  xor     rax, rsp
0x1800e1a9a  mov     [rsp+7A8h+var_58], rax
0x1800e1aa2  mov     r14, r9
0x1800e1aa5  mov     qword ptr [rsp+7A8h+var_F8], r8
0x1800e1aad  mov     [rsp+7A8h+var_1C7], dl
0x1800e1ab4  mov     rsi, rcx
0x1800e1ab7  mov     r13, [rsp+7A8h+arg_30]
0x1800e1abf  mov     rdi, [rsp+7A8h+arg_20]
0x1800e1ac7  mov     rax, [rsp+7A8h+arg_38]
0x1800e1acf  mov     qword ptr [rsp+7A8h+var_1B0], rax
0x1800e1ad7  mov     rax, [rsp+7A8h+arg_40]
0x1800e1adf  mov     [rsp+7A8h+var_178], rax
0x1800e1ae7  xor     ebx, ebx
0x1800e1ae9  mov     [rsp+7A8h+var_724], ebx
0x1800e1af0  mov     [rsp+7A8h+var_720], ebx
0x1800e1af7  mov     [rsp+7A8h+var_718], ebx
0x1800e1afe  mov     r15d, ebx
0x1800e1b01  mov     [rsp+7A8h+var_720], ebx
0x1800e1b08  mov     [rsp+7A8h+var_71C], bl
0x1800e1b0f  mov     r12d, ebx
0x1800e1b12  mov     [rsp+7A8h+var_1A0], ebx
0x1800e1b19  mov     [rsp+7A8h+var_1C8], bl
0x1800e1b20  xorps   xmm0, xmm0
0x1800e1b23  movups  [rsp+7A8h+var_108], xmm0
0x1800e1b2b  test    rdi, rdi
0x1800e1b2e  jz      short loc_1800E1B36
0x1800e1b30  mov     rdx, [rdi+18h]
0x1800e1b34  jmp     short loc_1800E1B39
0x1800e1b36  mov     rdx, rbx
0x1800e1b39  lea     rcx, [rsp+7A8h+var_108]
0x1800e1b41  call    ?ParseContainmentSwitches@RdpNano@Microsoft@@YA?AV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@PEBD@Z; Microsoft::RdpNano::ParseContainmentSwitches(char const *)
0x1800e1b46  nop
0x1800e1b47  xor     edx, edx; Val
0x1800e1b49  lea     r8d, [rdx+60h]; Size
0x1800e1b4d  lea     rcx, [rsp+7A8h+var_B8]; void *
0x1800e1b55  call    memset
0x1800e1b5a  lea     rdx, [rsp+7A8h+var_108]
0x1800e1b62  lea     rcx, [rsp+7A8h+var_B8]
0x1800e1b6a  call    ??0?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@AEBV012@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::basic_ptree<std::string,boost::any,std::less<std::string>>(boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &)
0x1800e1b6f  xorps   xmm0, xmm0
0x1800e1b72  movups  [rsp+7A8h+var_90], xmm0
0x1800e1b7a  movups  [rsp+7A8h+var_80], xmm0
0x1800e1b82  movups  [rsp+7A8h+var_70], xmm0
0x1800e1b8a  mov     [rsp+7A8h+var_A0], rbx
0x1800e1b92  mov     [rsp+7A8h+var_98], rbx
0x1800e1b9a  mov     [rsp+7A8h+var_60], 0FFFFFFFFh
0x1800e1ba5  mov     [rsp+7A8h+var_A8], 2
0x1800e1bb0  mov     [rsp+7A8h+var_5C], ebx
0x1800e1bb7  lea     rdx, off_1803F1EA0; struct Microsoft::Basix::Dct::ContainmentSwitch *
0x1800e1bbe  lea     rcx, [rsp+7A8h+var_B8]; this
0x1800e1bc6  call    ?IsEnabled@PropertyImpl@Dct@Basix@Microsoft@@QEBA_NAEBUContainmentSwitch@234@@Z; Microsoft::Basix::Dct::PropertyImpl::IsEnabled(Microsoft::Basix::Dct::ContainmentSwitch const &)
0x1800e1bcb  test    al, al
0x1800e1bcd  jnz     loc_1800E1CAB
0x1800e1bd3  xorps   xmm0, xmm0
0x1800e1bd6  movups  xmmword ptr [rsp+7A8h+var_1C0], xmm0
0x1800e1bde  lea     rcx, [rsp+7A8h+var_1C0]
0x1800e1be6  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800e1beb  nop
0x1800e1bec  mov     rax, qword ptr [rsp+7A8h+var_1C0]
0x1800e1bf4  test    rax, rax
0x1800e1bf7  jz      short loc_1800E1C65
0x1800e1bf9  cmp     [rax+80h], bl
0x1800e1bff  jz      short loc_1800E1C65
0x1800e1c01  xorps   xmm0, xmm0
0x1800e1c04  movups  [rsp+7A8h+var_198], xmm0
0x1800e1c0c  xorps   xmm1, xmm1
0x1800e1c0f  movdqu  [rsp+7A8h+var_188], xmm1
0x1800e1c18  mov     r8d, 26h ; '&'
0x1800e1c1e  lea     rdx, aFeatureSWasDis; "Feature %s was disabled by containment"
0x1800e1c25  lea     rcx, [rsp+7A8h+var_198]
0x1800e1c2d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e1c32  nop
0x1800e1c33  lea     r9, aTestcontainmen; "TestContainmentFeature"
0x1800e1c3a  lea     r8, [rsp+7A8h+var_198]
0x1800e1c42  lea     rdx, aRdpnano; "RDPNANO"
0x1800e1c49  lea     rcx, [rsp+7A8h+var_1C0]
0x1800e1c51  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,char const *)
0x1800e1c56  nop
0x1800e1c57  lea     rcx, [rsp+7A8h+var_198]
0x1800e1c5f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e1c64  nop
0x1800e1c65  mov     rbx, qword ptr [rsp+7A8h+var_1C0+8]
0x1800e1c6d  test    rbx, rbx
0x1800e1c70  jz      short loc_1800E1CAB
0x1800e1c72  or      eax, 0FFFFFFFFh
0x1800e1c75  lock xadd [rbx+8], eax
0x1800e1c7a  cmp     eax, 1
0x1800e1c7d  jnz     short loc_1800E1CAB
0x1800e1c7f  mov     rax, [rbx]
0x1800e1c82  mov     rcx, rbx
0x1800e1c85  mov     rax, [rax]
0x1800e1c88  call    cs:__guard_dispatch_icall_fptr
0x1800e1c8e  or      eax, 0FFFFFFFFh
0x1800e1c91  lock xadd [rbx+0Ch], eax
0x1800e1c96  cmp     eax, 1
0x1800e1c99  jnz     short loc_1800E1CAB
0x1800e1c9b  mov     rax, [rbx]
0x1800e1c9e  mov     rcx, rbx
0x1800e1ca1  mov     rax, [rax+8]
0x1800e1ca5  call    cs:__guard_dispatch_icall_fptr
0x1800e1cab  mov     al, [rsp+7A8h+var_1C7]
0x1800e1cb2  mov     [rsi+31h], al
0x1800e1cb5  mov     rax, qword ptr [rsp+7A8h+var_F8]
0x1800e1cbd  movups  xmm0, xmmword ptr [rax]
0x1800e1cc0  movdqu  xmmword ptr [rsi+154h], xmm0
0x1800e1cc8  test    r14, r14
0x1800e1ccb  jz      short loc_1800E1CD8
0x1800e1ccd  movups  xmm6, xmmword ptr [r14]
0x1800e1cd1  movups  xmm7, xmmword ptr [r14+10h]
0x1800e1cd6  jmp     short loc_1800E1CEE
0x1800e1cd8  xorps   xmm6, xmm6
0x1800e1cdb  xorps   xmm7, xmm7
0x1800e1cde  call    _errno
0x1800e1ce3  mov     dword ptr [rax], 16h
0x1800e1ce9  call    _invalid_parameter_noinfo
0x1800e1cee  mov     ebx, 1
0x1800e1cf3  test    rdi, rdi
0x1800e1cf6  jz      short loc_1800E1D54
0x1800e1cf8  test    byte ptr [rdi+8], 10h
0x1800e1cfc  jz      short loc_1800E1D0B
0x1800e1cfe  mov     [rsp+7A8h+var_720], 2
0x1800e1d09  jmp     short loc_1800E1D20
0x1800e1d0b  test    byte ptr [rdi+8], 2
0x1800e1d0f  mov     ecx, [rsp+7A8h+var_720]
0x1800e1d16  cmovnz  ecx, ebx
0x1800e1d19  mov     [rsp+7A8h+var_720], ecx
0x1800e1d20  mov     r12d, [rdi+14h]
0x1800e1d24  mov     [rsp+7A8h+var_1A0], r12d
0x1800e1d2c  xor     r14d, r14d
0x1800e1d2f  test    r12d, r12d
0x1800e1d32  setnz   al
0x1800e1d35  mov     [rsi+34h], al
0x1800e1d38  mov     al, [rdi+8]
0x1800e1d3b  shr     al, 2
0x1800e1d3e  and     al, bl
0x1800e1d40  mov     [rsi+3Ch], al
0x1800e1d43  mov     al, [rdi+8]
0x1800e1d46  shr     al, 3
0x1800e1d49  and     al, bl
0x1800e1d4b  mov     [rsp+7A8h+var_71C], al
0x1800e1d52  jmp     short loc_1800E1D57
0x1800e1d54  xor     r14d, r14d
0x1800e1d57  lea     rcx, ?s_connectionIdNext@RdpSideTransport@RdpNano@Microsoft@@1U?$atomic@H@std@@A; std::atomic<int> Microsoft::RdpNano::RdpSideTransport::s_connectionIdNext
0x1800e1d5e  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x1800e1d63  lock add dword ptr [rax], 2
0x1800e1d67  xorps   xmm0, xmm0
0x1800e1d6a  xorps   xmm1, xmm1
0x1800e1d6d  movdqu  [rsp+7A8h+var_688], xmm1
0x1800e1d76  test    r13, r13
0x1800e1d79  jz      short loc_1800E1DAA
0x1800e1d7b  mov     r15d, 3
0x1800e1d81  cmp     [r13+0], r15d
0x1800e1d85  cmovnz  r15d, r14d
0x1800e1d89  mov     al, [r13+8]
0x1800e1d8d  and     al, bl
0x1800e1d8f  mov     [rsi+33h], al
0x1800e1d92  mov     bl, [r13+8]
0x1800e1d96  shr     bl, 1
0x1800e1d98  mov     r13d, 1
0x1800e1d9e  and     bl, r13b
0x1800e1da1  mov     [rsp+7A8h+var_1C8], bl
0x1800e1da8  jmp     short loc_1800E1DB0
0x1800e1daa  mov     r13d, 1
0x1800e1db0  movups  xmmword ptr [rsp+7A8h+var_1C0], xmm0
0x1800e1db8  lea     rcx, [rsp+7A8h+var_1C0]
0x1800e1dc0  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800e1dc5  nop
0x1800e1dc6  mov     rax, qword ptr [rsp+7A8h+var_1C0]
0x1800e1dce  test    rax, rax
0x1800e1dd1  jz      short loc_1800E1E3C
0x1800e1dd3  cmp     [rax+80h], r14b
0x1800e1dda  jz      short loc_1800E1E3C
0x1800e1ddc  xorps   xmm0, xmm0
0x1800e1ddf  movups  [rsp+7A8h+var_198], xmm0
0x1800e1de7  xorps   xmm1, xmm1
0x1800e1dea  movdqu  [rsp+7A8h+var_188], xmm1
0x1800e1df3  mov     r8d, 10h
0x1800e1df9  lea     rdx, aSmilesversionD; "smilesVersion=%d"
0x1800e1e00  lea     rcx, [rsp+7A8h+var_198]
0x1800e1e08  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e1e0d  nop
0x1800e1e0e  mov     r9d, r15d
0x1800e1e11  lea     r8, [rsp+7A8h+var_198]
0x1800e1e19  lea     rdx, aRdpnano; "RDPNANO"
0x1800e1e20  lea     rcx, [rsp+7A8h+var_1C0]
0x1800e1e28  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@I@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@I@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint)
0x1800e1e2d  nop
0x1800e1e2e  lea     rcx, [rsp+7A8h+var_198]
0x1800e1e36  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e1e3b  nop
0x1800e1e3c  mov     rbx, qword ptr [rsp+7A8h+var_1C0+8]
0x1800e1e44  test    rbx, rbx
0x1800e1e47  jz      short loc_1800E1E81
0x1800e1e49  or      edi, 0FFFFFFFFh
0x1800e1e4c  mov     eax, edi
0x1800e1e4e  lock xadd [rbx+8], eax
0x1800e1e53  add     eax, edi
0x1800e1e55  jnz     short loc_1800E1E81
0x1800e1e57  mov     rax, [rbx]
0x1800e1e5a  mov     rcx, rbx
0x1800e1e5d  mov     rax, [rax]
0x1800e1e60  call    cs:__guard_dispatch_icall_fptr
0x1800e1e66  mov     eax, edi
0x1800e1e68  lock xadd [rbx+0Ch], eax
0x1800e1e6d  add     eax, edi
0x1800e1e6f  jnz     short loc_1800E1E81
0x1800e1e71  mov     rax, [rbx]
0x1800e1e74  mov     rcx, rbx
0x1800e1e77  mov     rax, [rax+8]
0x1800e1e7b  call    cs:__guard_dispatch_icall_fptr
0x1800e1e81  test    r15d, r15d
0x1800e1e84  setnz   bl
0x1800e1e87  mov     [rsp+7A8h+var_728], bl
0x1800e1e8e  xorps   xmm0, xmm0
0x1800e1e91  movups  [rsp+7A8h+var_D8], xmm0
0x1800e1e99  mov     rax, [rsi+10h]
0x1800e1e9d  movsxd  rcx, dword ptr [rax+4]
0x1800e1ea1  add     rcx, 10h
0x1800e1ea5  add     rcx, rsi
0x1800e1ea8  lea     rdx, [rsp+7A8h+var_168]
0x1800e1eb0  call    ??$GetWeakPtr@VISmilesCallback@ISmiles@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VISmilesCallback@ISmiles@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::ISmiles::ISmilesCallback>(void)
0x1800e1eb5  lea     rdi, [rsi+154h]
0x1800e1ebc  movups  xmm0, xmmword ptr [rdi]
0x1800e1ebf  movdqu  [rsp+7A8h+var_6A8], xmm0
0x1800e1ec8  mov     [rsp+7A8h+var_738], rax
0x1800e1ecd  lea     rax, aMicrosoftBasix_478; "Microsoft::Basix::Dct.Smiles.Callback"
0x1800e1ed4  mov     [rsp+7A8h+var_740], rax
0x1800e1ed9  mov     al, [rsp+7A8h+var_1C8]
0x1800e1ee0  mov     [rsp+7A8h+var_748], al
0x1800e1ee4  lea     rax, aMicrosoftBasix_454; "Microsoft::Basix::Dct.Smiles.UseSideban"...
0x1800e1eeb  mov     [rsp+7A8h+var_750], rax
0x1800e1ef0  mov     dword ptr [rsp+7A8h+var_758], r12d
0x1800e1ef5  lea     rax, aMicrosoftBasix_387; "Microsoft::Basix::Dct.Transport.AutoRec"...
0x1800e1efc  mov     [rsp+7A8h+var_760], rax
0x1800e1f01  mov     byte ptr [rsp+7A8h+var_768], bl
0x1800e1f05  lea     rax, aMicrosoftBasix_231; "Microsoft::Basix::Dct.ICE.Smiles.Enable"...
0x1800e1f0c  mov     [rsp+7A8h+var_770], rax
0x1800e1f11  mov     dword ptr [rsp+7A8h+var_778], r15d
0x1800e1f16  lea     rax, aMicrosoftBasix_425; "Microsoft::Basix::Dct.ICE.Smiles.Versio"...
0x1800e1f1d  mov     [rsp+7A8h+Str], rax
0x1800e1f22  mov     al, [rsi+31h]
0x1800e1f25  mov     byte ptr [rsp+7A8h+var_788], al
0x1800e1f29  lea     r9, aMicrosoftBasix_442; "Microsoft::Basix::Dct.IsServerConnectio"...
0x1800e1f30  lea     r8, [rsp+7A8h+var_6A8]
0x1800e1f38  lea     rdx, aMicrosoftBasix_226; "Microsoft::Basix::Dct.ActivityId"
0x1800e1f3f  lea     rcx, [rsp+7A8h+var_D8]
0x1800e1f47  call    ??$AnyPTreeFromPairs@PEBDUGuid@Basix@Microsoft@@PEBD_NPEBDW4SMILES_VER@Dct@23@PEBD_NPEBDIPEBD_NPEBDV?$weak_ptr@VISmilesCallback@ISmiles@Dct@Basix@Microsoft@@@std@@@Containers@Basix@Microsoft@@YA?AV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@PEBDUGuid@12@0_N0W4SMILES_VER@Dct@12@020I020V?$weak_ptr@VISmilesCallback@ISmiles@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Containers::AnyPTreeFromPairs<char const *,Microsoft::Basix::Guid,char const *,bool,char const *,Microsoft::Basix::Dct::SMILES_VER,char const *,bool,char const *,uint,char const *,bool,char const *,std::weak_ptr<Microsoft::Basix::Dct::ISmiles::ISmilesCallback>>(char const *,Microsoft::Basix::Guid,char const *,bool,char const *,Microsoft::Basix::Dct::SMILES_VER,char const *,bool,char const *,uint,char const *,bool,char const *,std::weak_ptr<Microsoft::Basix::Dct::ISmiles::ISmilesCallback>)
0x1800e1f4c  nop
0x1800e1f4d  xorps   xmm0, xmm0
0x1800e1f50  movups  [rsp+7A8h+var_6B8], xmm0
0x1800e1f58  mov     rax, [rsi+10h]
0x1800e1f5c  movsxd  rcx, dword ptr [rax+4]
0x1800e1f60  add     rcx, 10h
0x1800e1f64  add     rcx, rsi
0x1800e1f67  lea     rdx, [rsp+7A8h+var_6B8]
0x1800e1f6f  call    ??$GetWeakPtr@VWriteCompletionCallback@IAsyncTransport@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VWriteCompletionCallback@IAsyncTransport@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::IAsyncTransport::WriteCompletionCallback>(void)
0x1800e1f74  nop
0x1800e1f75  xorps   xmm0, xmm0
0x1800e1f78  movups  [rsp+7A8h+var_C8], xmm0
0x1800e1f80  movdqa  [rsp+7A8h+var_6A8], xmm0
0x1800e1f89  mov     rax, qword ptr [rsp+7A8h+var_6B8+8]
0x1800e1f91  test    rax, rax
0x1800e1f94  jz      short loc_1800E1FAC
0x1800e1f96  movaps  xmm0, [rsp+7A8h+var_6B8]
0x1800e1f9e  movdqa  [rsp+7A8h+var_6A8], xmm0
0x1800e1fa7  lock add [rax+0Ch], r13d
0x1800e1fac  movaps  xmmword ptr [rsp+7A8h+var_708], xmm6
0x1800e1fb4  movaps  [rsp+7A8h+var_6F8], xmm7
0x1800e1fbc  movups  xmm0, xmmword ptr [rdi]
0x1800e1fbf  movdqu  [rsp+7A8h+var_168], xmm0
0x1800e1fc8  mov     dword ptr [rsp+7A8h+var_768], r12d
0x1800e1fcd  lea     rax, aMicrosoftBasix_387; "Microsoft::Basix::Dct.Transport.AutoRec"...
0x1800e1fd4  mov     [rsp+7A8h+var_770], rax
0x1800e1fd9  lea     rax, [rsp+7A8h+var_6A8]
0x1800e1fe1  mov     [rsp+7A8h+var_778], rax
0x1800e1fe6  lea     rax, aMicrosoftBasix_437; "Microsoft::Basix::Dct.RawUdpRdpFilter.W"...
0x1800e1fed  mov     [rsp+7A8h+Str], rax
0x1800e1ff2  lea     rax, [rsp+7A8h+var_708]
0x1800e1ffa  mov     [rsp+7A8h+var_788], rax
0x1800e1fff  lea     r9, aMicrosoftBasix_180; "Microsoft::Basix::Dct.RawUdpRdpFilter.S"...
0x1800e2006  lea     r8, [rsp+7A8h+var_168]
0x1800e200e  lea     rdx, aMicrosoftBasix_226; "Microsoft::Basix::Dct.ActivityId"
0x1800e2015  lea     rcx, [rsp+7A8h+var_C8]
0x1800e201d  call    ??$AnyPTreeFromPairs@PEBDUGuid@Basix@Microsoft@@PEBDUSecurityCookieHash@RdpNano@3@PEBDV?$weak_ptr@VWriteCompletionCallback@IAsyncTransport@Dct@Basix@Microsoft@@@std@@PEBDI@Containers@Basix@Microsoft@@YA?AV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@PEBDUGuid@12@0USecurityCookieHash@RdpNano@2@0V?$weak_ptr@VWriteCompletionCallback@IAsyncTransport@Dct@Basix@Microsoft@@@std@@0I@Z; Microsoft::Basix::Containers::AnyPTreeFromPairs<char const *,Microsoft::Basix::Guid,char const *,Microsoft::RdpNano::SecurityCookieHash,char const *,std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::WriteCompletionCallback>,char const *,uint>(char const *,Microsoft::Basix::Guid,char const *,Microsoft::RdpNano::SecurityCookieHash,char const *,std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::WriteCompletionCallback>,char const *,uint)
0x1800e2022  nop
0x1800e2023  lea     r9, [rsp+7A8h+var_108]
0x1800e202b  lea     r8, [rsp+7A8h+var_C8]
  ... truncated ...
```

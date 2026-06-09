# Microsoft::Basix::Dct::ICECore::LinkContext::Set(Microsoft::Basix::Dct::ICE::Agent::CandidatePair const &,std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase> const &,std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer> const &,ushort,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::weak_ptr<Microsoft::Basix::Dct::LinkContextDelegate>)

- ea: `0x180241724`
- end: `0x1802429e6`
- name: `?Set@LinkContext@ICECore@Dct@Basix@Microsoft@@QEAAXAEBVCandidatePair@Agent@ICE@345@AEBV?$shared_ptr@VCandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@AEBV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@GAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$weak_ptr@VLinkContextDelegate@Dct@Basix@Microsoft@@@std@@@Z`
- size: `4802`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `service_task, broker_com_uri`

## callers

- `0x18021a548`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015bb8`
- `0x180017380`
- `0x180017404`
- `0x180017494`
- `0x180017518`
- `0x18001902c`
- `0x18001ab4c`
- `0x180021850`
- `0x180024760`
- `0x180024c14`
- `0x180028820`
- `0x180029d6c`
- `0x18003cfd4`
- `0x18003f5c0`
- `0x18004e1dc`
- `0x1800d38d0`
- `0x1800f2fcc`
- `0x1800f91d0`
- `0x180108650`
- `0x18015b990`
- `0x1801e3074`
- `0x1802242ac`
- `0x180241724`
- `0x1802491c8`
- `0x18031213c`
- `0x18031214c`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x180375c40`

## string_xrefs

- `0x180241ee6`: `Microsoft::Basix::Dct.Smiles.LinkType`
- `0x1802424ca`: `Microsoft::Basix::Dct.Smiles.AddLinkInfo.Summary`
- `0x1802428f6`: `Microsoft::Basix::Dct.Smiles.AddLinkInfo.Components`
- `0x180241e42`: `Could not set a valid type for Ice link!`

## pseudocode

```c
// Hidden C++ exception states: #wind=111
__int64 __fastcall Microsoft::Basix::Dct::ICECore::LinkContext::Set(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int16 a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  volatile signed __int32 *v14; // rcx
  __int64 v15; // r15
  __int64 *v16; // rdi
  __m128i v17; // xmm1
  __int64 *Transport; // rax
  __int64 v19; // r13
  __int64 v20; // rbx
  volatile signed __int32 *v21; // rdi
  __m128i *v22; // rdx
  char v23; // di
  __int64 v24; // rbx
  __int64 v25; // rax
  volatile signed __int32 *v26; // rbx
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rax
  volatile signed __int32 *v31; // rbx
  __int64 v32; // rdi
  __int64 v33; // rsi
  __int64 v34; // rdi
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // r9
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rbx
  int v50; // edx
  int v51; // ecx
  char v52; // r8
  int v53; // eax
  volatile signed __int32 *v54; // rbx
  __int128 *v55; // rax
  __int64 v56; // r13
  __int64 v57; // r12
  __int64 v58; // r15
  __int64 v59; // r14
  __int64 v60; // rsi
  __int64 v61; // rdi
  __int64 v62; // rbx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rdx
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rdx
  __int128 *v92; // rax
  __int64 v93; // r15
  void *v94; // rax
  __int64 v95; // r8
  __int64 v96; // r9
  const char *v97; // rdi
  const char *v98; // rax
  const char *v99; // rbx
  const char *v100; // rdx
  const char *v101; // rsi
  __int64 v102; // r8
  __int64 v103; // r9
  _QWORD *v104; // r14
  __int64 v105; // rbx
  __int64 v106; // r8
  __int64 v107; // r9
  const char *v108; // rdi
  const char *v109; // rdx
  __int64 v110; // rbx
  __int64 v111; // r8
  __int64 v112; // r9
  __int64 v113; // rbx
  __int64 v114; // r8
  __int64 v115; // r9
  const char *v116; // rdi
  const char *v117; // rdx
  __int64 v118; // rbx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // rbx
  __int64 v122; // r8
  __int64 v123; // r9
  const char *v124; // rdi
  const char *v125; // rdx
  __int64 v126; // rbx
  __int64 v127; // r8
  __int64 v128; // r9
  __int128 *v129; // rax
  __int64 result; // rax
  volatile signed __int32 *v131; // rbx
  volatile signed __int32 *v132; // rcx
  char v133; // [rsp+30h] [rbp-D0h]
  bool v134; // [rsp+30h] [rbp-D0h]
  char v135; // [rsp+31h] [rbp-CFh]
  __int64 v136; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v137; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v138; // [rsp+50h] [rbp-B0h]
  char v139; // [rsp+60h] [rbp-A0h]
  __int128 *v140; // [rsp+68h] [rbp-98h]
  int v141; // [rsp+70h] [rbp-90h]
  int v142; // [rsp+74h] [rbp-8Ch]
  __int128 v143; // [rsp+78h] [rbp-88h] BYREF
  __int128 v144; // [rsp+88h] [rbp-78h]
  char v145; // [rsp+98h] [rbp-68h]
  __int128 *v146; // [rsp+A0h] [rbp-60h]
  const char *v147; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v148; // [rsp+B0h] [rbp-50h]
  volatile signed __int32 *v149; // [rsp+B8h] [rbp-48h]
  __m128i v150; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v151; // [rsp+D0h] [rbp-30h]
  _BYTE v152[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v153[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v154[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v155[32]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v156[32]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v157[32]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v158[32]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v159[32]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v160[32]; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD *v161; // [rsp+1F8h] [rbp+F8h]
  _BYTE v162[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v163[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v164[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v165[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v166[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v167[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v168[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v169[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v170[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v171[32]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v172[32]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v173[32]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v174[32]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v175[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v176[32]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v177[32]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v178[32]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v179[32]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v180[32]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v181[32]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v182[32]; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v183[32]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v184[32]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v185[32]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v186[32]; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v187[32]; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v188[32]; // [rsp+540h] [rbp+440h] BYREF
  __int128 v189; // [rsp+560h] [rbp+460h] BYREF
  _OWORD v190[2]; // [rsp+570h] [rbp+470h] BYREF
  __m128i v191; // [rsp+590h] [rbp+490h] BYREF

  v147 = (const char *)a1;
  v151 = a7;
  v161 = a7;
  v141 = 0;
  v11 = a7[1];
  v12 = 0;
  v13 = 0;
  if ( v11 )
  {
    v12 = *a7;
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 12));
    v13 = v11;
  }
  *(_QWORD *)(a1 + 1456) = v12;
  v14 = *(volatile signed __int32 **)(a1 + 1464);
  *(_QWORD *)(a1 + 1464) = v13;
  if ( v14 && _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
  v15 = a1 + 1376;
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(a1 + 1376, a4);
  v16 = (__int64 *)(a1 + 1360);
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(a1 + 1360, a3);
  *(_WORD *)(a1 + 1352) = a5;
  Microsoft::Basix::Dct::SocketAddress::operator=(a1 + 1216, a6);
  v17 = 0;
  v150 = 0;
  if ( *(_QWORD *)(a1 + 1376) )
  {
    Transport = (__int64 *)Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer::GetTransport(
                             *(_QWORD *)(a1 + 1376),
                             v190);
    v19 = *Transport;
    v149 = (volatile signed __int32 *)Transport[1];
    v20 = (__int64)v149;
    *Transport = 0;
    Transport[1] = 0;
    v150.m128i_i64[0] = v19;
    v150.m128i_i64[1] = v20;
    v21 = (volatile signed __int32 *)*((_QWORD *)&v190[0] + 1);
    if ( *((_QWORD *)&v190[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v190[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    v17 = _mm_load_si128(&v150);
    v16 = (__int64 *)(a1 + 1360);
  }
  else
  {
    v20 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v149 = (volatile signed __int32 *)v20;
    v19 = 0;
  }
  if ( v19 )
  {
    if ( v20 )
      _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
    v191 = v17;
    v22 = &v191;
    v23 = 1;
  }
  else
  {
    v24 = *v16;
    Smtx_lock_shared((_Smtx_t *)(*v16 + 32));
    v25 = *(_QWORD *)(v24 + 256);
    if ( v25 )
      _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
    v190[0] = *(_OWORD *)(v24 + 248);
    Smtx_unlock_shared((_Smtx_t *)(v24 + 32));
    v22 = (__m128i *)v190;
    v23 = 6;
  }
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(a1 + 1120, v22);
  if ( (v23 & 4) != 0 )
  {
    v23 &= ~4u;
    v26 = (volatile signed __int32 *)*((_QWORD *)&v190[0] + 1);
    if ( *((_QWORD *)&v190[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v190[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
  }
  if ( (v23 & 2) != 0 )
    v23 &= ~2u;
  if ( (v23 & 1) != 0 )
  {
    v27 = (volatile signed __int32 *)v191.m128i_i64[1];
    if ( v191.m128i_i64[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v191.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
        if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
  }
  if ( v19 )
    v28 = *(_QWORD *)(*(_QWORD *)v15 + 208LL) + 128LL;
  else
    v28 = a6;
  std::string::operator=(a1 + 1136, v28);
  if ( *(_QWORD *)v15 )
    v29 = *(_QWORD *)(*(_QWORD *)v15 + 208LL) + 128LL;
  else
    v29 = a6;
  std::string::operator=(a1 + 1184, v29);
  v30 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64, _QWORD))(**(_QWORD **)(a1 + 1120) + 112LL))(
          *(_QWORD *)(a1 + 1120),
          v190,
          a1 + 1184,
          0);
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(a1 + 1168, v30);
  v31 = (volatile signed __int32 *)*((_QWORD *)&v190[0] + 1);
  if ( *((_QWORD *)&v190[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v190[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  v32 = a1 + 1392;
  v148 = (_QWORD *)(a1 + 1392);
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(a1 + 1392, a2);
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(a1 + 1408, a2 + 16);
  *(_QWORD *)(a1 + 1424) = *(_QWORD *)(a2 + 32);
  *(_QWORD *)(a1 + 1432) = *(_QWORD *)(a2 + 40);
  *(_DWORD *)(a1 + 1440) = *(_DWORD *)(a2 + 48);
  *(_BYTE *)(a1 + 1444) = *(_BYTE *)(a2 + 52);
  *(_DWORD *)(a1 + 1448) = *(_DWORD *)(a2 + 56);
  if ( *(_QWORD *)v15 )
  {
    v33 = *(_QWORD *)(*(_QWORD *)v15 + 208LL);
    v34 = Microsoft::Basix::ToString<unsigned short>(v154, a1 + 1352, 0, 6);
    v35 = *(_QWORD *)(*(_QWORD *)v15 + 208LL);
    v36 = std::operator+<char>(&v191, v35 + 248, "/");
    v37 = std::operator+<char>(v155, v36, v35 + 64);
    v38 = std::operator+<char>(v156, v37, ":");
    v39 = std::operator+<char>(v157, v38, v35 + 96);
    v40 = std::operator+<char>(v158, v39, "(");
    LOBYTE(v41) = v133;
    std::string::string(v190, v41, v40, v34);
    v42 = std::operator+<char>(v159, v190, "):");
    v43 = std::operator+<char>(v160, v42, v33 + 328);
    v44 = std::operator+<char>(v152, v43, ":");
    v45 = std::operator+<char>(v153, v44, a6);
    if ( a1 + 1088 != v45 )
    {
      std::string::_Tidy_deallocate(a1 + 1088);
      *(_OWORD *)(a1 + 1088) = *(_OWORD *)v45;
      *(_OWORD *)(a1 + 1104) = *(_OWORD *)(v45 + 16);
      *(_QWORD *)(v45 + 16) = 0;
      *(_QWORD *)(v45 + 24) = 15;
      *(_BYTE *)v45 = 0;
    }
    std::string::_Tidy_deallocate(v153);
    std::string::_Tidy_deallocate(v152);
    std::string::_Tidy_deallocate(v160);
    std::string::_Tidy_deallocate(v159);
    std::string::_Tidy_deallocate(v190);
    std::string::_Tidy_deallocate(v158);
    std::string::_Tidy_deallocate(v157);
    std::string::_Tidy_deallocate(v156);
    std::string::_Tidy_deallocate(v155);
    std::string::_Tidy_deallocate(&v191);
    std::string::_Tidy_deallocate(v154);
    v32 = a1 + 1392;
  }
  else
  {
    v47 = std::operator+<char>(v152, "udp:", *(_QWORD *)(a1 + 1360) + 216LL);
    v48 = std::operator+<char>(v153, v47, ":");
    v49 = std::operator+<char>(v154, v48, a6);
    if ( a1 + 1088 != v49 )
    {
      std::string::_Tidy_deallocate(a1 + 1088);
      *(_OWORD *)(a1 + 1088) = *(_OWORD *)v49;
      *(_OWORD *)(a1 + 1104) = *(_OWORD *)(v49 + 16);
      *(_QWORD *)(v49 + 16) = 0;
      *(_QWORD *)(v49 + 24) = 15;
      *(_BYTE *)v49 = 0;
    }
    std::string::_Tidy_deallocate(v154);
    std::string::_Tidy_deallocate(v153);
    std::string::_Tidy_deallocate(v152);
  }
  v50 = *(_DWORD *)(*(_QWORD *)v32 + 228LL);
  v142 = v50;
  v51 = *(_DWORD *)(*(_QWORD *)(a1 + 1408) + 228LL);
  v141 = v51;
  if ( !v50 && !v51 )
  {
    LOBYTE(v46) = 1;
LABEL_53:
    v52 = 0;
    goto LABEL_55;
  }
  LOBYTE(v46) = 0;
  if ( (unsigned int)(v50 - 1) > 1 )
    goto LABEL_53;
  v52 = 1;
LABEL_55:
  v135 = v52;
  v134 = (unsigned int)(v51 - 1) <= 1;
  LODWORD(v136) = 0;
  if ( v50 == 3 )
  {
    v53 = 8;
    if ( v51 != 3 )
      v53 = 6;
    goto LABEL_63;
  }
  if ( v51 == 3 )
  {
    LODWORD(v136) = 7;
    goto LABEL_75;
  }
  if ( v52 )
  {
    v53 = 2 * ((unsigned int)(v51 - 1) <= 1) + 3;
LABEL_63:
    LODWORD(v136) = v53;
    goto LABEL_75;
  }
  if ( (unsigned int)(v51 - 1) > 1 )
  {
    if ( (_BYTE)v46 )
    {
      LODWORD(v136) = 2;
    }
    else
    {
      v190[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v190);
      if ( *(_QWORD *)&v190[0] && *(_BYTE *)(*(_QWORD *)&v190[0] + 128LL) )
      {
        memset(&v191, 0, 32);
        std::string::_Construct<1,char const *>(&v191, "Could not set a valid type for Ice link!", 40);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          v190,
          "BASIX_DCT",
          &v191);
        std::string::_Tidy_deallocate(&v191);
      }
      v54 = (volatile signed __int32 *)*((_QWORD *)&v190[0] + 1);
      if ( *((_QWORD *)&v190[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v190[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
          if ( !_InterlockedDecrement(v54 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
        }
      }
    }
  }
  else
  {
    LODWORD(v136) = 4;
  }
LABEL_75:
  *(_QWORD *)&v190[0] = a1 + 960;
  v143 = 0;
  v144 = 0;
  std::string::_Construct<1,char const *>(&v143, "Microsoft::Basix::Dct.Smiles.LinkType", 37, v46);
  v145 = 46;
  v55 = &v143;
  if ( *((_QWORD *)&v144 + 1) > 0xFu )
    v55 = (__int128 *)v143;
  v146 = v55;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<enum Microsoft::Basix::Dct::ISmiles::LinkType>(
    a1 + 960,
    &v143,
    &v136);
  std::string::_Tidy_deallocate(&v143);
  v191.m128i_i64[0] = Microsoft::Basix::ToString<std::string>(&v143, *(_QWORD *)(a1 + 1408) + 128LL, 0, 6);
  v136 = Microsoft::Basix::ToString<std::string>(v188, *(_QWORD *)(a1 + 1408) + 160LL, 0, 6);
  v56 = Microsoft::Basix::ToString<std::string>(v187, *(_QWORD *)(a1 + 1408) + 64LL, 0, 6);
  v57 = Microsoft::Basix::ToString<std::string>(v186, *(_QWORD *)(a1 + 1408) + 96LL, 0, 6);
  v58 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ICE::Candidate::Type>(
          v185,
          *(_QWORD *)(a1 + 1408) + 228LL,
          0,
          6);
  v59 = Microsoft::Basix::ToString<std::string>(v162, *(_QWORD *)v32 + 128LL, 0, 6);
  v60 = Microsoft::Basix::ToString<std::string>(v183, *(_QWORD *)v32 + 160LL, 0, 6);
  v61 = Microsoft::Basix::ToString<std::string>(v182, *(_QWORD *)v32 + 64LL, 0, 6);
  v62 = Microsoft::Basix::ToString<std::string>(v181, *v148 + 96LL, 0, 6);
  v63 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ICE::Candidate::Type>(v180, *v148 + 228LL, 0, 6);
  v64 = std::operator+<char>(v179, "LocalType=", v63);
  v65 = std::operator+<char>(v184, v64, ",");
  v66 = std::operator+<char>(v178, v65, "LocalBaseAddress=");
  LOBYTE(v67) = v134;
  std::string::string(v153, v67, v66, v62);
  v68 = std::operator+<char>(v177, v153, ",");
  v69 = std::operator+<char>(v176, v68, "LocalTransportAddress=");
  LOBYTE(v70) = v134;
  std::string::string(v152, v70, v69, v61);
  v71 = std::operator+<char>(v175, v152, ",");
  v72 = std::operator+<char>(v174, v71, "LocalNatAddress=");
  LOBYTE(v73) = v134;
  std::string::string(v160, v73, v72, v60);
  v74 = std::operator+<char>(v173, v160, ",");
  v75 = std::operator+<char>(v172, v74, "LocalServerAddress=");
  LOBYTE(v76) = v134;
  std::string::string(v159, v76, v75, v59);
  v77 = std::operator+<char>(v171, v159, ",");
  v78 = std::operator+<char>(v170, v77, "RemoteType=");
  LOBYTE(v79) = v134;
  std::string::string(v158, v79, v78, v58);
  v80 = std::operator+<char>(v169, v158, ",");
  v81 = std::operator+<char>(v168, v80, "RemoteBaseAddress=");
  LOBYTE(v82) = v134;
  std::string::string(v157, v82, v81, v57);
  v83 = std::operator+<char>(v167, v157, ",");
  v84 = std::operator+<char>(v166, v83, "RemoteTransportAddress=");
  LOBYTE(v85) = v134;
  std::string::string(v156, v85, v84, v56);
  v86 = std::operator+<char>(v165, v156, ",");
  v87 = std::operator+<char>(v164, v86, "RemoteNatAddress=");
  LOBYTE(v88) = v134;
  std::string::string(v155, v88, v87, v136);
  v89 = std::operator+<char>(v163, v155, ",");
  v90 = std::operator+<char>(v154, v89, "RemoteServerAddress=");
  LOBYTE(v91) = v134;
  std::string::string(&v191, v91, v90, v191.m128i_i64[0]);
  std::string::_Tidy_deallocate(v154);
  std::string::_Tidy_deallocate(v163);
  std::string::_Tidy_deallocate(v155);
  std::string::_Tidy_deallocate(v164);
  std::string::_Tidy_deallocate(v165);
  std::string::_Tidy_deallocate(v156);
  std::string::_Tidy_deallocate(v166);
  std::string::_Tidy_deallocate(v167);
  std::string::_Tidy_deallocate(v157);
  std::string::_Tidy_deallocate(v168);
  std::string::_Tidy_deallocate(v169);
  std::string::_Tidy_deallocate(v158);
  std::string::_Tidy_deallocate(v170);
  std::string::_Tidy_deallocate(v171);
  std::string::_Tidy_deallocate(v159);
  std::string::_Tidy_deallocate(v172);
  std::string::_Tidy_deallocate(v173);
  std::string::_Tidy_deallocate(v160);
  std::string::_Tidy_deallocate(v174);
  std::string::_Tidy_deallocate(v175);
  std::string::_Tidy_deallocate(v152);
  std::string::_Tidy_deallocate(v176);
  std::string::_Tidy_deallocate(v177);
  std::string::_Tidy_deallocate(v153);
  std::string::_Tidy_deallocate(v178);
  std::string::_Tidy_deallocate(v184);
  std::string::_Tidy_deallocate(v179);
  std::string::_Tidy_deallocate(v180);
  std::string::_Tidy_deallocate(v181);
  std::string::_Tidy_deallocate(v182);
  std::string::_Tidy_deallocate(v183);
  std::string::_Tidy_deallocate(v162);
  std::string::_Tidy_deallocate(v185);
  std::string::_Tidy_deallocate(v186);
  std::string::_Tidy_deallocate(v187);
  std::string::_Tidy_deallocate(v188);
  std::string::_Tidy_deallocate(&v143);
  v137 = 0;
  v138 = 0;
  std::string::_Construct<1,char const *>(&v137, "Microsoft::Basix::Dct.Smiles.AddLinkInfo.Summary", 48);
  v139 = 46;
  v92 = &v137;
  if ( *((_QWORD *)&v138 + 1) > 0xFu )
    v92 = (__int128 *)v137;
  v140 = v92;
  v93 = *(_QWORD *)&v190[0];
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(
    *(_QWORD *)&v190[0],
    &v137,
    &v191);
  std::string::_Tidy_deallocate(&v137);
  v189 = 0;
  v94 = operator new(0x20u);
  *(_QWORD *)&v190[0] = v94;
  if ( v94 )
    v94 = (void *)__0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v94);
  *((_QWORD *)&v189 + 1) = v94;
  v97 = "DIRECT";
  v98 = "DIRECT";
  if ( v135 )
    v98 = "STUN";
  if ( v142 == 3 )
    v98 = "TURN";
  *(_QWORD *)&v190[0] = v98;
  v99 = "TransportTypeClient";
  v100 = "TransportTypeClient";
  v101 = v147;
  if ( v147[1504] )
    v100 = "TransportTypeServer";
  LOBYTE(v96) = v134;
  LOBYTE(v95) = 46;
  boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
    &v137,
    v100,
    v95,
    v96);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<char const *>(
    &v189,
    &v137,
    v190);
  std::string::_Tidy_deallocate(&v137);
  if ( v134 )
    v97 = "STUN";
  if ( v141 == 3 )
    v97 = "TURN";
  v147 = v97;
  if ( !v101[1504] )
    v99 = "TransportTypeServer";
  LOBYTE(v103) = v134;
  LOBYTE(v102) = 46;
  boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
    &v137,
    v99,
    v102,
    v103);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<char const *>(
    &v189,
    &v137,
    &v147);
  std::string::_Tidy_deallocate(&v137);
  v104 = v101 + 1392;
  v105 = Microsoft::Basix::ToString<std::string>(&v143, *((_QWORD *)v101 + 174) + 64LL, 0, 6);
  v108 = "TransportIPClient";
  v109 = "TransportIPClient";
  if ( v101[1504] )
    v109 = "TransportIPServer";
  LOBYTE(v107) = v134;
  LOBYTE(v106) = 46;
  boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
    &v137,
    v109,
    v106,
    v107);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v189, &v137, v105);
  std::string::_Tidy_deallocate(&v137);
  std::string::_Tidy_deallocate(&v143);
  v110 = Microsoft::Basix::ToString<std::string>(&v143, *((_QWORD *)v101 + 176) + 64LL, 0, 6);
  if ( !v101[1504] )
    v108 = "TransportIPServer";
  LOBYTE(v112) = v134;
  LOBYTE(v111) = 46;
  boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
    &v137,
    v108,
    v111,
    v112);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v189, &v137, v110);
  std::string::_Tidy_deallocate(&v137);
  std::string::_Tidy_deallocate(&v143);
  v113 = Microsoft::Basix::ToString<std::string>(&v143, *v104 + 160LL, 0, 6);
  v116 = "NatIPClient";
  v117 = "NatIPClient";
  if ( v101[1504] )
    v117 = "NatIPServer";
  LOBYTE(v115) = v134;
  LOBYTE(v114) = 46;
  boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
    &v137,
    v117,
    v114,
    v115);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v189, &v137, v113);
  std::string::_Tidy_deallocate(&v137);
  std::string::_Tidy_deallocate(&v143);
  v118 = Microsoft::Basix::ToString<std::string>(&v143, *((_QWORD *)v101 + 176) + 160LL, 0, 6);
  if ( !v101[1504] )
    v116 = "NatIPServer";
  LOBYTE(v120) = v134;
  LOBYTE(v119) = 46;
  boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
    &v137,
    v116,
    v119,
    v120);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v189, &v137, v118);
  std::string::_Tidy_deallocate(&v137);
  std::string::_Tidy_deallocate(&v143);
  v121 = Microsoft::Basix::ToString<std::string>(&v143, *v104 + 128LL, 0, 6);
  v124 = "TurnServerIPClient";
  v125 = "TurnServerIPClient";
  if ( v101[1504] )
    v125 = "TurnServerIPServer";
  LOBYTE(v123) = v134;
  LOBYTE(v122) = 46;
  boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
    &v137,
    v125,
    v122,
    v123);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v189, &v137, v121);
  std::string::_Tidy_deallocate(&v137);
  std::string::_Tidy_deallocate(&v143);
  v126 = Microsoft::Basix::ToString<std::string>(&v143, *((_QWORD *)v101 + 176) + 128LL, 0, 6);
  if ( !v101[1504] )
    v124 = "TurnServerIPServer";
  LOBYTE(v128) = v134;
  LOBYTE(v127) = 46;
  boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
    &v137,
    v124,
    v127,
    v128);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(&v189, &v137, v126);
  std::string::_Tidy_deallocate(&v137);
  std::string::_Tidy_deallocate(&v143);
  v137 = 0;
  v138 = 0;
  std::string::_Construct<1,char const *>(&v137, "Microsoft::Basix::Dct.Smiles.AddLinkInfo.Components", 51);
  v139 = 46;
  v129 = &v137;
  if ( *((_QWORD *)&v138 + 1) > 0xFu )
    v129 = (__int128 *)v137;
  v140 = v129;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put_child(v93, &v137, &v189);
  std::string::_Tidy_deallocate(&v137);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v189);
  result = std::string::_Tidy_deallocate(&v191);
  v131 = v149;
  if ( v149 )
  {
    result = (unsigned int)_InterlockedDecrement(v149 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v131)(v131);
      result = (unsigned int)_InterlockedDecrement(v131 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v131 + 8LL))(v131);
    }
  }
  v132 = (volatile signed __int32 *)v151[1];
  if ( v132 )
  {
    result = (unsigned int)_InterlockedDecrement(v132 + 3);
    if ( !(_DWORD)result )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v132 + 8LL))(v132);
  }
  return result;
}

```

## disassembly

```asm
0x180241724  push    rbp
0x180241726  push    rbx
0x180241727  push    rsi
0x180241728  push    rdi
0x180241729  push    r12
0x18024172b  push    r13
0x18024172d  push    r14
0x18024172f  push    r15
0x180241731  lea     rbp, [rsp-4C8h]
0x180241739  mov     eax, 5C8h
0x18024173e  call    _alloca_probe
0x180241743  sub     rsp, rax
0x180241746  mov     rax, cs:__security_cookie
0x18024174d  xor     rax, rsp
0x180241750  mov     [rbp+500h+var_50], rax
0x180241757  mov     rdi, r9
0x18024175a  mov     rbx, r8
0x18024175d  mov     rsi, rdx
0x180241760  mov     r14, rcx
0x180241763  mov     [rbp+500h+var_558], rcx
0x180241767  mov     r12, [rbp+500h+arg_28]
0x18024176e  mov     rcx, [rbp+500h+arg_30]
0x180241775  mov     [rbp+500h+var_530], rcx
0x180241779  mov     [rbp+500h+var_408], rcx
0x180241780  mov     [rsp+600h+var_590], 0
0x180241788  mov     rax, [rcx+8]
0x18024178c  xor     edx, edx
0x18024178e  xor     r8d, r8d
0x180241791  test    rax, rax
0x180241794  jz      short loc_1802417A0
0x180241796  mov     rdx, [rcx]
0x180241799  lock inc dword ptr [rax+0Ch]
0x18024179d  mov     r8, rax
0x1802417a0  mov     [r14+5B0h], rdx
0x1802417a7  mov     rcx, [r14+5B8h]
0x1802417ae  mov     [r14+5B8h], r8
0x1802417b5  test    rcx, rcx
0x1802417b8  jz      short loc_1802417D4
0x1802417ba  or      eax, 0FFFFFFFFh
0x1802417bd  lock xadd [rcx+0Ch], eax
0x1802417c2  cmp     eax, 1
0x1802417c5  jnz     short loc_1802417D4
0x1802417c7  mov     rax, [rcx]
0x1802417ca  mov     rax, [rax+8]
0x1802417ce  call    cs:__guard_dispatch_icall_fptr
0x1802417d4  lea     r15, [r14+560h]
0x1802417db  mov     rdx, rdi
0x1802417de  mov     rcx, r15
0x1802417e1  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x1802417e6  lea     rdi, [r14+550h]
0x1802417ed  mov     rdx, rbx
0x1802417f0  mov     rcx, rdi
0x1802417f3  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x1802417f8  movzx   eax, [rbp+500h+arg_20]
0x1802417ff  mov     [r14+548h], ax
0x180241807  lea     rcx, [r14+4C0h]
0x18024180e  mov     rdx, r12
0x180241811  call    ??4SocketAddress@Dct@Basix@Microsoft@@QEAAAEAV0123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::SocketAddress::operator=(std::string const &)
0x180241816  xorps   xmm0, xmm0
0x180241819  xorps   xmm1, xmm1
0x18024181c  movdqa  [rbp+500h+var_540], xmm1
0x180241821  mov     rcx, [r15]
0x180241824  test    rcx, rcx
0x180241827  jz      loc_1802418AE
0x18024182d  lea     rdx, [rbp+500h+var_90]
0x180241834  call    ?GetTransport@TurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@QEBA?AV?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer::GetTransport(void)
0x180241839  mov     r13, [rax]
0x18024183c  mov     rbx, [rax+8]
0x180241840  mov     [rbp+500h+var_548], rbx
0x180241844  mov     qword ptr [rax], 0
0x18024184b  mov     qword ptr [rax+8], 0
0x180241853  mov     qword ptr [rbp+500h+var_540], r13
0x180241857  mov     qword ptr [rbp+500h+var_540+8], rbx
0x18024185b  mov     rdi, qword ptr [rbp+500h+var_90+8]
0x180241862  test    rdi, rdi
0x180241865  jz      short loc_1802418A0
0x180241867  or      eax, 0FFFFFFFFh
0x18024186a  lock xadd [rdi+8], eax
0x18024186f  cmp     eax, 1
0x180241872  jnz     short loc_1802418A0
0x180241874  mov     rax, [rdi]
0x180241877  mov     rcx, rdi
0x18024187a  mov     rax, [rax]
0x18024187d  call    cs:__guard_dispatch_icall_fptr
0x180241883  or      eax, 0FFFFFFFFh
0x180241886  lock xadd [rdi+0Ch], eax
0x18024188b  cmp     eax, 1
0x18024188e  jnz     short loc_1802418A0
0x180241890  mov     rax, [rdi]
0x180241893  mov     rcx, rdi
0x180241896  mov     rax, [rax+8]
0x18024189a  call    cs:__guard_dispatch_icall_fptr
0x1802418a0  movdqa  xmm1, [rbp+500h+var_540]
0x1802418a5  lea     rdi, [r14+550h]
0x1802418ac  jmp     short loc_1802418C1
0x1802418ae  psrldq  xmm0, 8
0x1802418b3  movq    rbx, xmm0
0x1802418b8  mov     [rbp+500h+var_548], rbx
0x1802418bc  movq    r13, xmm1
0x1802418c1  test    r13, r13
0x1802418c4  jz      short loc_1802418E5
0x1802418c6  test    rbx, rbx
0x1802418c9  jz      short loc_1802418CF
0x1802418cb  lock inc dword ptr [rbx+8]
0x1802418cf  movdqa  [rbp+500h+var_70], xmm1
0x1802418d7  lea     rdx, [rbp+500h+var_70]
0x1802418de  mov     edi, 1
0x1802418e3  jmp     short loc_180241932
0x1802418e5  mov     rbx, [rdi]
0x1802418e8  lea     rcx, [rbx+20h]; _Smtx_t *
0x1802418ec  call    _Smtx_lock_shared
0x1802418f1  mov     rax, [rbx+100h]
0x1802418f8  test    rax, rax
0x1802418fb  jz      short loc_180241901
0x1802418fd  lock inc dword ptr [rax+8]
0x180241901  mov     rax, [rbx+0F8h]
0x180241908  mov     qword ptr [rbp+500h+var_90], rax
0x18024190f  mov     rax, [rbx+100h]
0x180241916  mov     qword ptr [rbp+500h+var_90+8], rax
0x18024191d  lea     rcx, [rbx+20h]; _Smtx_t *
0x180241921  call    _Smtx_unlock_shared
0x180241926  lea     rdx, [rbp+500h+var_90]
0x18024192d  mov     edi, 6
0x180241932  lea     rcx, [r14+460h]
0x180241939  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18024193e  test    dil, 4
0x180241942  jz      short loc_18024198C
0x180241944  and     edi, 0FFFFFFFBh
0x180241947  mov     rbx, qword ptr [rbp+500h+var_90+8]
0x18024194e  test    rbx, rbx
0x180241951  jz      short loc_18024198C
0x180241953  or      eax, 0FFFFFFFFh
0x180241956  lock xadd [rbx+8], eax
0x18024195b  cmp     eax, 1
0x18024195e  jnz     short loc_18024198C
0x180241960  mov     rax, [rbx]
0x180241963  mov     rcx, rbx
0x180241966  mov     rax, [rax]
0x180241969  call    cs:__guard_dispatch_icall_fptr
0x18024196f  or      eax, 0FFFFFFFFh
0x180241972  lock xadd [rbx+0Ch], eax
0x180241977  cmp     eax, 1
0x18024197a  jnz     short loc_18024198C
0x18024197c  mov     rax, [rbx]
0x18024197f  mov     rcx, rbx
0x180241982  mov     rax, [rax+8]
0x180241986  call    cs:__guard_dispatch_icall_fptr
0x18024198c  test    dil, 2
0x180241990  jz      short loc_180241995
0x180241992  and     edi, 0FFFFFFFDh
0x180241995  test    dil, 1
0x180241999  jz      short loc_1802419E1
0x18024199b  mov     rbx, qword ptr [rbp+500h+var_70+8]
0x1802419a2  or      edi, 0FFFFFFFFh
0x1802419a5  test    rbx, rbx
0x1802419a8  jz      short loc_1802419E4
0x1802419aa  mov     eax, edi
0x1802419ac  lock xadd [rbx+8], eax
0x1802419b1  add     eax, edi
0x1802419b3  jnz     short loc_1802419E4
0x1802419b5  mov     rax, [rbx]
0x1802419b8  mov     rcx, rbx
0x1802419bb  mov     rax, [rax]
0x1802419be  call    cs:__guard_dispatch_icall_fptr
0x1802419c4  mov     eax, edi
0x1802419c6  lock xadd [rbx+0Ch], eax
0x1802419cb  add     eax, edi
0x1802419cd  jnz     short loc_1802419E4
0x1802419cf  mov     rax, [rbx]
0x1802419d2  mov     rcx, rbx
0x1802419d5  mov     rax, [rax+8]
0x1802419d9  call    cs:__guard_dispatch_icall_fptr
0x1802419df  jmp     short loc_1802419E4
0x1802419e1  or      edi, 0FFFFFFFFh
0x1802419e4  mov     ebx, 80h
0x1802419e9  test    r13, r13
0x1802419ec  jz      short loc_1802419FD
0x1802419ee  mov     rax, [r15]
0x1802419f1  mov     rdx, [rax+0D0h]
0x1802419f8  add     rdx, rbx
0x1802419fb  jmp     short loc_180241A00
0x1802419fd  mov     rdx, r12
0x180241a00  lea     rcx, [r14+470h]
0x180241a07  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x180241a0c  mov     rdx, [r15]
0x180241a0f  xor     r13d, r13d
0x180241a12  test    rdx, rdx
0x180241a15  jz      short loc_180241A23
0x180241a17  mov     rdx, [rdx+0D0h]
0x180241a1e  add     rdx, rbx
0x180241a21  jmp     short loc_180241A26
0x180241a23  mov     rdx, r12
0x180241a26  lea     rbx, [r14+4A0h]
0x180241a2d  mov     rcx, rbx
0x180241a30  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x180241a35  mov     rcx, [r14+460h]
0x180241a3c  mov     rax, [rcx]
0x180241a3f  xor     r9d, r9d
0x180241a42  mov     r8, rbx
0x180241a45  lea     rdx, [rbp+500h+var_90]
0x180241a4c  mov     rax, [rax+70h]
0x180241a50  call    cs:__guard_dispatch_icall_fptr
0x180241a56  lea     rcx, [r14+490h]
0x180241a5d  mov     rdx, rax
0x180241a60  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x180241a65  mov     rbx, qword ptr [rbp+500h+var_90+8]
0x180241a6c  test    rbx, rbx
0x180241a6f  jz      short loc_180241AA6
0x180241a71  mov     eax, edi
0x180241a73  lock xadd [rbx+8], eax
0x180241a78  add     eax, edi
0x180241a7a  jnz     short loc_180241AA6
0x180241a7c  mov     rax, [rbx]
0x180241a7f  mov     rcx, rbx
0x180241a82  mov     rax, [rax]
0x180241a85  call    cs:__guard_dispatch_icall_fptr
0x180241a8b  mov     eax, edi
0x180241a8d  lock xadd [rbx+0Ch], eax
0x180241a92  add     eax, edi
0x180241a94  jnz     short loc_180241AA6
0x180241a96  mov     rax, [rbx]
0x180241a99  mov     rcx, rbx
0x180241a9c  mov     rax, [rax+8]
0x180241aa0  call    cs:__guard_dispatch_icall_fptr
0x180241aa6  lea     rdi, [r14+570h]
0x180241aad  mov     [rbp+500h+var_550], rdi
0x180241ab1  mov     rdx, rsi
0x180241ab4  mov     rcx, rdi
0x180241ab7  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x180241abc  lea     rdx, [rsi+10h]
0x180241ac0  lea     rcx, [rdi+10h]
0x180241ac4  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x180241ac9  mov     rax, [rsi+20h]
0x180241acd  mov     [rdi+20h], rax
0x180241ad1  mov     rax, [rsi+28h]
0x180241ad5  mov     [rdi+28h], rax
0x180241ad9  mov     eax, [rsi+30h]
0x180241adc  mov     [rdi+30h], eax
0x180241adf  mov     al, [rsi+34h]
0x180241ae2  mov     [rdi+34h], al
0x180241ae5  mov     eax, [rsi+38h]
0x180241ae8  mov     [rdi+38h], eax
0x180241aeb  mov     rax, [r15]
0x180241aee  test    rax, rax
0x180241af1  jz      loc_180241CB4
0x180241af7  mov     rsi, [rax+0D0h]
0x180241afe  mov     r9d, 6
0x180241b04  xor     r8d, r8d
0x180241b07  lea     rdx, [r14+548h]
0x180241b0e  lea     rcx, [rbp+500h+var_4E8]
0x180241b12  call    ??$ToString@G@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBGHH@Z; Microsoft::Basix::ToString<ushort>(ushort const &,int,int)
0x180241b17  mov     rdi, rax
0x180241b1a  mov     rcx, [r15]
0x180241b1d  mov     rbx, [rcx+0D0h]
0x180241b24  lea     rdx, [rbx+0F8h]
0x180241b2b  lea     r8, asc_180405508; "/"
0x180241b32  lea     rcx, [rbp+500h+var_70]
0x180241b39  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x180241b3e  nop
0x180241b3f  lea     r8, [rbx+40h]
0x180241b43  mov     rdx, rax
0x180241b46  lea     rcx, [rbp+500h+var_4C8]
0x180241b4a  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x180241b4f  nop
0x180241b50  lea     r8, asc_1803D71C4; ":"
0x180241b57  mov     rdx, rax
0x180241b5a  lea     rcx, [rbp+500h+var_4A8]
0x180241b5e  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180241b63  nop
0x180241b64  lea     r8, [rbx+60h]
0x180241b68  mov     rdx, rax
0x180241b6b  lea     rcx, [rbp+500h+var_488]
0x180241b6f  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x180241b74  nop
0x180241b75  lea     r8, asc_1803EE4E4; "("
0x180241b7c  mov     rdx, rax
0x180241b7f  lea     rcx, [rbp+500h+var_468]
0x180241b86  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180241b8b  nop
0x180241b8c  mov     r9, rdi
0x180241b8f  mov     r8, rax
0x180241b92  mov     dl, [rsp+600h+var_5D0]
0x180241b96  lea     rcx, [rbp+500h+var_90]
0x180241b9d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180241ba2  nop
0x180241ba3  lea     r8, asc_1803F25A4; "):"
0x180241baa  lea     rdx, [rbp+500h+var_90]
0x180241bb1  lea     rcx, [rbp+500h+var_448]
0x180241bb8  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180241bbd  nop
0x180241bbe  lea     r8, [rsi+148h]
0x180241bc5  mov     rdx, rax
0x180241bc8  lea     rcx, [rbp+500h+var_428]
0x180241bcf  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x180241bd4  nop
0x180241bd5  lea     r8, asc_1803D71C4; ":"
0x180241bdc  mov     rdx, rax
0x180241bdf  lea     rcx, [rbp+500h+var_528]
0x180241be3  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180241be8  nop
  ... truncated ...
```

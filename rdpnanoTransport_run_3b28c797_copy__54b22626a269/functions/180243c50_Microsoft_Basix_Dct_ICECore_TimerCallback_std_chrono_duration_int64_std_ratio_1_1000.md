# Microsoft::Basix::Dct::ICECore::TimerCallback(std::chrono::duration<__int64,std::ratio<1,1000>>)

- ea: `0x180243c50`
- end: `0x180244e70`
- name: `?TimerCallback@ICECore@Dct@Basix@Microsoft@@MEAAXV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z`
- size: `4640`
- prototype: ``
- caller_count: `0`
- callee_count: `41`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x18000da90`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ab4c`
- `0x18001c080`
- `0x18001db78`
- `0x18001dc00`
- `0x180024760`
- `0x18003302c`
- `0x1800371cc`
- `0x18003c308`
- `0x1800d34ac`
- `0x1800d3740`
- `0x1801c1fd8`
- `0x180201f54`
- `0x180202de0`
- `0x18020413c`
- `0x18020bbf8`
- `0x18020fd88`
- `0x18021fe58`
- `0x180223aa8`
- `0x18023cacc`
- `0x18024081c`
- `0x18024379c`
- `0x180243c50`
- `0x1802473d8`
- `0x1802e2464`
- `0x180311dbc`
- `0x180311e54`
- `0x180312064`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`
- `0x180376380`

## string_xrefs

- `0x1802441a1`: `start pruning relay %s. DoR=%d, number of links(%d)`
- `0x1802442df`: `after pruning relay %s. DoR=%d, number of links(%d)`
- `0x1802443e5`: `pruning relay %s did not reduce DoR or number of links, something is wrong!`
- `0x180244540`: `newNumLinks`
- `0x180244631`: `oldNumLinks`

## pseudocode

```c
// Hidden C++ exception states: #wind=95
__int64 __fastcall Microsoft::Basix::Dct::ICECore::TimerCallback(__int64 a1)
{
  struct Microsoft::Basix::Instrumentation::ActivityManager *v2; // rax
  __int64 v3; // r9
  Microsoft::Basix::Dct::ICECore *v4; // r13
  __int64 v5; // rax
  _QWORD *v6; // r15
  _QWORD *v7; // rbx
  __int64 v8; // r13
  __int64 v9; // rdx
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  unsigned __int128 v12; // kr00_16
  __int64 v13; // rcx
  _QWORD *v14; // rsi
  _QWORD *i; // rbx
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rsi
  __int64 v18; // rdx
  volatile signed __int32 *v19; // rdi
  bool v20; // zf
  __int64 v21; // rbx
  char v22; // al
  unsigned int v23; // esi
  __int64 v24; // rbx
  int v25; // r9d
  int v26; // edi
  volatile signed __int32 *v27; // rbx
  _QWORD *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r15
  unsigned int v31; // r12d
  int v32; // r9d
  __int128 *v33; // rbx
  volatile signed __int32 *v34; // rbx
  int v35; // r9d
  __int64 v36; // rbx
  int v37; // edi
  __int128 *v38; // rsi
  volatile signed __int32 *v39; // rbx
  __int128 *v40; // rbx
  volatile signed __int32 *v41; // rbx
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
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int128 *v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rdx
  volatile signed __int32 *v65; // rbx
  volatile signed __int32 *v66; // rbx
  volatile signed __int32 *v67; // rbx
  struct Microsoft::Basix::Instrumentation::ActivityManager *v68; // rax
  int v70; // [rsp+20h] [rbp-E0h]
  __int64 v71; // [rsp+60h] [rbp-A0h] BYREF
  __int64 ticks; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v73[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v74; // [rsp+88h] [rbp-78h]
  _OWORD v75[2]; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v76[2]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v77[2]; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v78[2]; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v79[2]; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v80[2]; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v81[2]; // [rsp+158h] [rbp+58h] BYREF
  _OWORD v82[2]; // [rsp+178h] [rbp+78h] BYREF
  _OWORD v83[2]; // [rsp+198h] [rbp+98h] BYREF
  _OWORD v84[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  _OWORD v85[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  _OWORD v86[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  _OWORD v87[2]; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v88[2]; // [rsp+238h] [rbp+138h] BYREF
  _OWORD v89[2]; // [rsp+258h] [rbp+158h] BYREF
  __int64 *v90; // [rsp+278h] [rbp+178h]
  __int64 *v91; // [rsp+280h] [rbp+180h]
  _BYTE v92[32]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v93[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v94[32]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v95[32]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v96[32]; // [rsp+308h] [rbp+208h] BYREF
  __int64 v97[4]; // [rsp+328h] [rbp+228h] BYREF
  __int64 v98[4]; // [rsp+348h] [rbp+248h] BYREF
  __int64 v99[4]; // [rsp+368h] [rbp+268h] BYREF
  __int64 v100[4]; // [rsp+388h] [rbp+288h] BYREF
  __int64 v101[4]; // [rsp+3A8h] [rbp+2A8h] BYREF
  _BYTE v102[32]; // [rsp+3C8h] [rbp+2C8h] BYREF
  _BYTE v103[32]; // [rsp+3E8h] [rbp+2E8h] BYREF
  _BYTE v104[32]; // [rsp+408h] [rbp+308h] BYREF
  _BYTE v105[32]; // [rsp+428h] [rbp+328h] BYREF
  _BYTE v106[32]; // [rsp+448h] [rbp+348h] BYREF
  _BYTE v107[32]; // [rsp+468h] [rbp+368h] BYREF
  _BYTE v108[32]; // [rsp+488h] [rbp+388h] BYREF
  _BYTE v109[32]; // [rsp+4A8h] [rbp+3A8h] BYREF
  _BYTE v110[32]; // [rsp+4C8h] [rbp+3C8h] BYREF
  _BYTE v111[32]; // [rsp+4E8h] [rbp+3E8h] BYREF
  _BYTE v112[32]; // [rsp+508h] [rbp+408h] BYREF
  _BYTE v113[32]; // [rsp+528h] [rbp+428h] BYREF
  _BYTE v114[32]; // [rsp+548h] [rbp+448h] BYREF
  _BYTE v115[32]; // [rsp+568h] [rbp+468h] BYREF
  _BYTE v116[32]; // [rsp+588h] [rbp+488h] BYREF
  _BYTE v117[40]; // [rsp+5A8h] [rbp+4A8h] BYREF
  _BYTE v118[56]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE *v119; // [rsp+608h] [rbp+508h]
  int v120[4]; // [rsp+610h] [rbp+510h] BYREF
  __int128 v121; // [rsp+620h] [rbp+520h]
  _OWORD v122[2]; // [rsp+630h] [rbp+530h] BYREF
  __int128 v123; // [rsp+650h] [rbp+550h] BYREF
  __int128 v124; // [rsp+660h] [rbp+560h]
  __int128 v125; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v126[16]; // [rsp+680h] [rbp+580h] BYREF
  _QWORD v127[8]; // [rsp+690h] [rbp+590h] BYREF

  v2 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
  LOBYTE(v3) = 1;
  Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(v2, v126, a1 + 160, v3);
  v4 = (Microsoft::Basix::Dct::ICECore *)(a1 - 8);
  v5 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::ITimerCallback>(
         a1 + *(int *)(*(_QWORD *)(a1 - 8 + 128) + 4LL) + 120LL,
         v120);
  Microsoft::Basix::Timer::Setup<__int64,std::ratio<1,1>>(a1 + 352, qword_18041D0B8, v5);
  memset(v127, 0, sizeof(v127));
  LODWORD(ticks) = 0;
  std::_Hash<std::_Uset_traits<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::_Uhash_compare<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::hash<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>>,std::allocator<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>,0>>::_Hash<std::_Uset_traits<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::_Uhash_compare<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::hash<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>>,std::allocator<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>,0>>(
    v127,
    &ticks,
    &v71);
  ticks = Xtime_get_ticks();
  v73[0] = a1 + 448;
  if ( Mtx_lock((_Mtx_t)(a1 + 448)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 524) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 524) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v6 = *(_QWORD **)(a1 + 536);
  v7 = (_QWORD *)*v6;
  if ( (_QWORD *)*v6 != v6 )
  {
    v8 = ticks;
    do
    {
      v122[0] = 0;
      v9 = v7[10];
      if ( v9 )
      {
        v10 = *(_DWORD *)(v9 + 8);
        while ( v10 )
        {
          v11 = v10;
          v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 8), v10 + 1, v10);
          if ( v11 == v10 )
          {
            v16 = v7[9];
            *(_QWORD *)&v122[0] = v16;
            v17 = v7[10];
            *((_QWORD *)&v122[0] + 1) = v17;
            v12 = __PAIR128__(v17, v16);
            goto LABEL_10;
          }
        }
      }
      v12 = v122[0];
LABEL_10:
      if ( (_QWORD)v12 )
      {
        v13 = *(_QWORD *)(v12 + 1376);
        if ( v13 )
        {
          if ( v8 >= *(_QWORD *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v13 + 520) )
            std::_Hash<std::_Uset_traits<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>,std::_Uhash_compare<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>,std::hash<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>>>,std::allocator<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>>,0>>::emplace<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer> const &>(
              v127,
              v120,
              v12 + 1376);
        }
      }
      if ( *((_QWORD *)&v12 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v12 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (***((void (__fastcall ****)(_QWORD))&v12 + 1))(*((_QWORD *)&v12 + 1));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v12 + 1) + 12LL), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v12 + 1) + 8LL))(*((_QWORD *)&v12 + 1));
        }
      }
      v7 = (_QWORD *)*v7;
    }
    while ( v7 != v6 );
    v4 = (Microsoft::Basix::Dct::ICECore *)(a1 - 8);
  }
  Mtx_unlock((_Mtx_t)(a1 + 448));
  v14 = (_QWORD *)v127[1];
  for ( i = *(_QWORD **)v127[1]; i != v14; i = (_QWORD *)*i )
  {
    *(_OWORD *)v120 = 0;
    Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer::GetBase(i[2], v120);
    if ( *(_QWORD *)v120 )
    {
      v119 = 0;
      Microsoft::Basix::Dct::ICECore::CandidateBase::SendTurnRefreshRequest(*(_QWORD *)v120, i + 2, v118);
      if ( v119 )
      {
        LOBYTE(v18) = v119 != v118;
        (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v119 + 32LL))(v119, v18);
      }
    }
    v19 = *(volatile signed __int32 **)&v120[2];
    if ( *(_QWORD *)&v120[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v120[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
  }
  v20 = *(_DWORD *)(a1 + 9072) == 1;
  if ( *(_DWORD *)(a1 + 9072) > 1u )
  {
    if ( *(_DWORD *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(a1 + 9048) == 2 )
      Microsoft::Basix::Dct::ICECore::StartTestCloneRelay(v4);
    v20 = *(_DWORD *)(a1 + 9072) == 1;
  }
  if ( v20 && *(_DWORD *)(a1 + 9052) > *(_DWORD *)(a1 + 9056) )
  {
    v21 = *(_QWORD *)std::chrono::steady_clock::now(v73) / 1000000LL;
    if ( !*(_BYTE *)(a1 + 256) || (v22 = 1, *(_QWORD *)(a1 + 248) + 60000LL >= v21) )
      v22 = 0;
    v23 = v21 - *(_DWORD *)(a1 + 264);
    if ( v22 && v23 > 0xEA60 && !*(_BYTE *)(a1 + 240) )
    {
      if ( !*(_BYTE *)(a1 + 256) )
        std::_Throw_bad_optional_access();
      v24 = v21 - *(_QWORD *)(a1 + 248);
      v125 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v125);
      if ( (_QWORD)v125 && *(_BYTE *)(v125 + 128) )
      {
        _mm_lfence();
        v26 = *(_DWORD *)(a1 + 9052);
        v123 = 0;
        v124 = 0;
        std::string::_Construct<1,char const *>(
          &v123,
          "Check relay prunning: dor=%d, time in ms to last DoR crossing=%d, to last pruning=%d",
          84,
          v25,
          v70);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,int,int>(
          (unsigned int)&v125,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v123,
          v26,
          v24,
          v23);
        std::string::_Tidy_deallocate(&v123);
      }
      v27 = (volatile signed __int32 *)*((_QWORD *)&v125 + 1);
      if ( *((_QWORD *)&v125 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v125 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      v125 = 0;
      Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(a1 - 8, &v125);
      if ( (_QWORD)v125 )
      {
        v28 = (_QWORD *)(*(_QWORD *)(v125 + 208) + 128LL);
        v123 = 0;
        v124 = 0;
        v29 = v28[2];
        if ( v28[3] > 0xFu )
          v28 = (_QWORD *)*v28;
        std::string::_Construct<2,char const *>(&v123, v28, v29);
        v30 = *(_QWORD *)(a1 + 544);
        v31 = *(_DWORD *)(a1 + 9052);
        v122[0] = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v122);
        if ( *(_QWORD *)&v122[0] && *(_BYTE *)(*(_QWORD *)&v122[0] + 128LL) )
        {
          v33 = &v123;
          if ( *((_QWORD *)&v124 + 1) > 0xFu )
            LODWORD(v33) = v123;
          *(_OWORD *)v120 = 0;
          v121 = 0;
          std::string::_Construct<1,char const *>(
            v120,
            "start pruning relay %s. DoR=%d, number of links(%d)",
            (const char *)0x33,
            v32,
            v70);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,unsigned int,unsigned __int64>(
            (unsigned int)v122,
            (unsigned int)"BASIX_DCT",
            (unsigned int)v120,
            (_DWORD)v33,
            v31,
            v30);
          std::string::_Tidy_deallocate(v120);
        }
        v34 = (volatile signed __int32 *)*((_QWORD *)&v122[0] + 1);
        if ( *((_QWORD *)&v122[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v122[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
            if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
          }
        }
        *(_OWORD *)v120 = 0;
        __ExceptionPtrCreate(v120);
        Microsoft::Basix::Dct::ICECore::RemoveLinksForRelay(a1 - 8, &v125, v120);
        __ExceptionPtrDestroy(v120);
        v122[0] = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v122);
        if ( *(_QWORD *)&v122[0] && *(_BYTE *)(*(_QWORD *)&v122[0] + 128LL) )
        {
          v36 = *(_QWORD *)(a1 + 544);
          v37 = *(_DWORD *)(a1 + 9052);
          v38 = &v123;
          if ( *((_QWORD *)&v124 + 1) > 0xFu )
            LODWORD(v38) = v123;
          *(_OWORD *)v120 = 0;
          v121 = 0;
          std::string::_Construct<1,char const *>(
            v120,
            "after pruning relay %s. DoR=%d, number of links(%d)",
            (const char *)0x33,
            v35,
            v70);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,unsigned int,unsigned __int64>(
            (unsigned int)v122,
            (unsigned int)"BASIX_DCT",
            (unsigned int)v120,
            (_DWORD)v38,
            v37,
            v36);
          std::string::_Tidy_deallocate(v120);
        }
        v39 = (volatile signed __int32 *)*((_QWORD *)&v122[0] + 1);
        if ( *((_QWORD *)&v122[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v122[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
            if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
          }
        }
        if ( *(_DWORD *)(a1 + 9052) == v31 && *(_QWORD *)(a1 + 544) == v30 )
        {
          v122[0] = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v122);
          if ( *(_QWORD *)&v122[0] && *(_BYTE *)(*(_QWORD *)&v122[0] + 128LL) )
          {
            v40 = &v123;
            if ( *((_QWORD *)&v124 + 1) > 0xFu )
              v40 = (__int128 *)v123;
            *(_OWORD *)v120 = 0;
            v121 = 0;
            std::string::_Construct<1,char const *>(
              v120,
              "pruning relay %s did not reduce DoR or number of links, something is wrong!",
              (const char *)0x4B);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,char const *>(
              v122,
              "BASIX_DCT",
              v120,
              v40);
            std::string::_Tidy_deallocate(v120);
          }
          v41 = (volatile signed __int32 *)*((_QWORD *)&v122[0] + 1);
          if ( *((_QWORD *)&v122[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v122[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
              if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
            }
          }
        }
        else
        {
          *(_OWORD *)v120 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v120);
          if ( *(_QWORD *)v120 && *(_BYTE *)(*(_QWORD *)v120 + 128LL) )
          {
            v73[0] = v97;
            std::_Integral_to_string<char,unsigned __int64>(v96, *(_QWORD *)(a1 + 544));
            *(_OWORD *)&v73[1] = 0;
            v74 = 0;
            std::string::_Construct<1,char const *>(&v73[1], ":", 1);
            memset(v79, 0, sizeof(v79));
            std::string::_Construct<1,char const *>(v79, "\"", 1);
            memset(v78, 0, sizeof(v78));
            std::string::_Construct<1,char const *>(v78, "\"", 1);
            v42 = std::operator+<char>(v117, v78, "newNumLinks");
            LOBYTE(v43) = v71;
            std::string::string(v95, v43, v42, v79);
            LOBYTE(v44) = v71;
            std::string::string(v94, v44, v95, &v73[1]);
            LOBYTE(v45) = v71;
            std::string::string(v97, v45, v94, v96);
            ticks = (__int64)v98;
            std::_Integral_to_string<char,unsigned __int64>(v93, v30);
            memset(v77, 0, sizeof(v77));
            std::string::_Construct<1,char const *>(v77, ":", 1);
            memset(v75, 0, sizeof(v75));
            std::string::_Construct<1,char const *>(v75, "\"", 1);
            memset(v89, 0, sizeof(v89));
            std::string::_Construct<1,char const *>(v89, "\"", 1);
            v46 = std::operator+<char>(v116, v89, "oldNumLinks");
            LOBYTE(v47) = v71;
            std::string::string(v92, v47, v46, v75);
            LOBYTE(v48) = v71;
            std::string::string(v111, v48, v92, v77);
            LOBYTE(v49) = v71;
            std::string::string(v98, v49, v111, v93);
            v90 = v99;
            std::_Integral_to_string<char,unsigned int>(v110, *(unsigned int *)(a1 + 9052));
            memset(v88, 0, sizeof(v88));
            std::string::_Construct<1,char const *>(v88, ":", 1);
            memset(v87, 0, sizeof(v87));
            std::string::_Construct<1,char const *>(v87, "\"", 1);
            memset(v86, 0, sizeof(v86));
            std::string::_Construct<1,char const *>(v86, "\"", 1);
            v50 = std::operator+<char>(v115, v86, "newDoR");
            LOBYTE(v51) = v71;
            std::string::string(v109, v51, v50, v87);
            LOBYTE(v52) = v71;
            std::string::string(v108, v52, v109, v88);
            LOBYTE(v53) = v71;
            std::string::string(v99, v53, v108, v110);
            v91 = v100;
            std::_Integral_to_string<char,unsigned int>(v107, v31);
            memset(v85, 0, sizeof(v85));
            std::string::_Construct<1,char const *>(v85, ":", 1);
            memset(v84, 0, sizeof(v84));
            std::string::_Construct<1,char const *>(v84, "\"", 1);
            memset(v83, 0, sizeof(v83));
            std::string::_Construct<1,char const *>(v83, "\"", 1);
            v54 = std::operator+<char>(v114, v83, "oldDoR");
            LOBYTE(v55) = v71;
            std::string::string(v106, v55, v54, v84);
            LOBYTE(v56) = v71;
            std::string::string(v105, v56, v106, v85);
            LOBYTE(v57) = v71;
            std::string::string(v100, v57, v105, v107);
            memset(v82, 0, sizeof(v82));
            std::string::_Construct<1,char const *>(v82, "\"", 1);
            v58 = &v123;
            if ( *((_QWORD *)&v124 + 1) > 0xFu )
              v58 = (__int128 *)v123;
            memset(v76, 0, sizeof(v76));
            std::string::_Construct<1,char const *>(v76, "\"", 1);
            memset(v81, 0, sizeof(v81));
            std::string::_Construct<1,char const *>(v81, ":", 1);
            memset(v122, 0, sizeof(v122));
            std::string::_Construct<1,char const *>(v122, "\"", 1);
            memset(v80, 0, sizeof(v80));
            std::string::_Construct<1,char const *>(v80, "\"", 1);
            v59 = std::operator+<char>(v113, v80, "relay");
            LOBYTE(v60) = v71;
            std::string::string(v104, v60, v59, v122);
            LOBYTE(v61) = v71;
            std::string::string(v103, v61, v104, v81);
            LOBYTE(v62) = v71;
            std::string::string(v102, v62, v103, v76);
            v63 = std::operator+<char>(v112, v102, v58);
            LOBYTE(v64) = v71;
            std::string::string(v101, v64, v63, v82);
            Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string>(
              (int)v120,
              (int)"RD_CHECKPOINT",
              0,
              (int)"ICECore",
              "RelayPruning",
              "Pruned relay due to high DoR",
              (__int64)v101,
              (__int64)v100,
              (__int64)v99,
              (__int64)v98,
              (__int64)v97);
            std::string::_Tidy_deallocate(v112);
            std::string::_Tidy_deallocate(v102);
            std::string::_Tidy_deallocate(v103);
            std::string::_Tidy_deallocate(v104);
            std::string::_Tidy_deallocate(v113);
            std::string::_Tidy_deallocate(v80);
            std::string::_Tidy_deallocate(v122);
            std::string::_Tidy_deallocate(v81);
            std::string::_Tidy_deallocate(v76);
            std::string::_Tidy_deallocate(v82);
            std::string::_Tidy_deallocate(v105);
            std::string::_Tidy_deallocate(v106);
            std::string::_Tidy_deallocate(v114);
            std::string::_Tidy_deallocate(v83);
            std::string::_Tidy_deallocate(v84);
            std::string::_Tidy_deallocate(v85);
            std::string::_Tidy_deallocate(v107);
            std::string::_Tidy_deallocate(v108);
            std::string::_Tidy_deallocate(v109);
            std::string::_Tidy_deallocate(v115);
            std::string::_Tidy_deallocate(v86);
            std::string::_Tidy_deallocate(v87);
            std::string::_Tidy_deallocate(v88);
            std::string::_Tidy_deallocate(v110);
            std::string::_Tidy_deallocate(v111);
            std::string::_Tidy_deallocate(v92);
            std::string::_Tidy_deallocate(v116);
            std::string::_Tidy_deallocate(v89);
            std::string::_Tidy_deallocate(v75);
            std::string::_Tidy_deallocate(v77);
            std::string::_Tidy_deallocate(v93);
            std::string::_Tidy_deallocate(v94);
            std::string::_Tidy_deallocate(v95);
            std::string::_Tidy_deallocate(v117);
            std::string::_Tidy_deallocate(v78);
            std::string::_Tidy_deallocate(v79);
            std::string::_Tidy_deallocate(&v73[1]);
            std::string::_Tidy_deallocate(v96);
          }
          v65 = *(volatile signed __int32 **)&v120[2];
          if ( *(_QWORD *)&v120[2] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v120[2] + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
              if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
            }
          }
          *(_QWORD *)(a1 + 264) = *(_QWORD *)std::chrono::steady_clock::now(v122) / 1000000LL;
        }
        std::string::_Tidy_deallocate(&v123);
      }
      else
      {
        *(_OWORD *)v120 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v120);
        if ( *(_QWORD *)v120 && *(_BYTE *)(*(_QWORD *)v120 + 128LL) )
        {
          *(_OWORD *)&v73[1] = 0;
          v74 = 0;
          std::string::_Construct<1,char const *>(
            &v73[1],
            "no suitable relay found for prunning - likely the peer doing the pruning",
            72);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
            v120,
            "BASIX_DCT",
            &v73[1]);
          std::string::_Tidy_deallocate(&v73[1]);
        }
        v66 = *(volatile signed __int32 **)&v120[2];
        if ( *(_QWORD *)&v120[2] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v120[2] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
            if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
          }
        }
      }
      v67 = (volatile signed __int32 *)*((_QWORD *)&v125 + 1);
      if ( *((_QWORD *)&v125 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v125 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
          if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
        }
      }
    }
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned short const,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo>>>>>>::_Tidy(&v127[3]);
  std::list<std::shared_ptr<Microsoft::Basix::Dct::Rcp::IUDPRateControllerHost::rawBuffer>>::_Tidy(&v127[1]);
  v68 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
  return (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, int *, _BYTE *))(*(_QWORD *)v68 + 32LL))(
           v68,
           v120,
           v126);
}

```

## disassembly

```asm
0x180243c50  mov     rax, rsp
0x180243c53  mov     [rax+10h], rbx
0x180243c57  mov     [rax+18h], rsi
0x180243c5b  mov     [rax+20h], rdi
0x180243c5f  push    rbp
0x180243c60  push    r12
0x180243c62  push    r13
0x180243c64  push    r14
0x180243c66  push    r15
0x180243c68  lea     rbp, [rax-608h]
0x180243c6f  mov     eax, 6E0h
0x180243c74  call    _alloca_probe
0x180243c79  sub     rsp, rax
0x180243c7c  mov     rax, cs:__security_cookie
0x180243c83  xor     rax, rsp
0x180243c86  mov     [rbp+600h+var_30], rax
0x180243c8d  mov     r14, rcx
0x180243c90  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x180243c95  lea     r8, [r14+0A0h]
0x180243c9c  mov     r9b, 1
0x180243c9f  lea     rdx, [rbp+600h+var_80]
0x180243ca6  mov     rcx, rax
0x180243ca9  call    ?SetActivityId@ActivityManager@Instrumentation@Basix@Microsoft@@QEAA?AUGuid@34@AEBU534@_N@Z; Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(Microsoft::Basix::Guid const &,bool)
0x180243cae  nop
0x180243caf  lea     r13, [r14-8]
0x180243cb3  mov     rax, [r13+80h]
0x180243cba  movsxd  rcx, dword ptr [rax+4]
0x180243cbe  add     rcx, 78h ; 'x'
0x180243cc2  add     rcx, r14
0x180243cc5  lea     rdx, [rbp+600h+var_F0]
0x180243ccc  call    ??$GetWeakPtr@VITimerCallback@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VITimerCallback@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::ITimerCallback>(void)
0x180243cd1  lea     rcx, [r14+160h]
0x180243cd8  mov     r8, rax
0x180243cdb  lea     rdx, qword_18041D0B8
0x180243ce2  call    ??$Setup@_JU?$ratio@$00$00@std@@@Timer@Basix@Microsoft@@QEAAXAEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@V?$weak_ptr@VITimerCallback@Basix@Microsoft@@@5@@Z; Microsoft::Basix::Timer::Setup<__int64,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,1>> const &,std::weak_ptr<Microsoft::Basix::ITimerCallback>)
0x180243ce7  xor     edx, edx; Val
0x180243ce9  lea     r8d, [rdx+40h]; Size
0x180243ced  lea     rcx, [rbp+600h+var_70]; void *
0x180243cf4  call    memset
0x180243cf9  mov     dword ptr [rsp+700h+var_698], 0
0x180243d01  lea     r8, [rsp+700h+var_6A0]
0x180243d06  lea     rdx, [rsp+700h+var_698]
0x180243d0b  lea     rcx, [rbp+600h+var_70]
0x180243d12  call    ??0?$_Hash@V?$_Uset_traits@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@std@@V?$_Uhash_compare@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@std@@U?$hash@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@std@@@2@U?$equal_to@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@std@@@2@@2@V?$allocator@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@std@@@2@$0A@@std@@@std@@IEAA@AEBV?$_Uhash_compare@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@std@@U?$hash@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@std@@@2@U?$equal_to@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@std@@@2@@1@AEBV?$allocator@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@std@@@1@@Z; std::_Hash<std::_Uset_traits<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::_Uhash_compare<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::hash<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>>,std::allocator<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>,0>>::_Hash<std::_Uset_traits<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::_Uhash_compare<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::hash<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>>,std::allocator<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>,0>>(std::_Uhash_compare<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::hash<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>> const &,std::allocator<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>> const &)
0x180243d17  nop
0x180243d18  call    _Xtime_get_ticks
0x180243d1d  mov     [rsp+700h+var_698], rax
0x180243d22  lea     rdi, [r14+1C0h]
0x180243d29  mov     qword ptr [rsp+700h+var_690], rdi
0x180243d2e  mov     rcx, rdi; _Mtx_t
0x180243d31  call    _Mtx_lock
0x180243d36  test    eax, eax
0x180243d38  jnz     loc_180244E53
0x180243d3e  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180243d45  jz      loc_180244E5E
0x180243d4b  mov     r15, [r14+218h]
0x180243d52  mov     rbx, [r15]
0x180243d55  cmp     rbx, r15
0x180243d58  jz      loc_180243E2B
0x180243d5e  mov     r13, [rsp+700h+var_698]
0x180243d63  xorps   xmm1, xmm1
0x180243d66  movdqu  [rbp+600h+var_D0], xmm1
0x180243d6e  mov     rdx, [rbx+50h]
0x180243d72  test    rdx, rdx
0x180243d75  jz      short loc_180243D8E
0x180243d77  mov     eax, [rdx+8]
0x180243d7a  jmp     short loc_180243D8A
0x180243d7c  lea     ecx, [rax+1]
0x180243d7f  lock cmpxchg [rdx+8], ecx
0x180243d84  jz      loc_180243E42
0x180243d8a  test    eax, eax
0x180243d8c  jnz     short loc_180243D7C
0x180243d8e  mov     rax, qword ptr [rbp+600h+var_D0]
0x180243d95  mov     rsi, qword ptr [rbp+600h+var_D0+8]
0x180243d9c  test    rax, rax
0x180243d9f  jz      short loc_180243DDD
0x180243da1  lea     r12, [rax+560h]
0x180243da8  mov     rcx, [r12]
0x180243dac  test    rcx, rcx
0x180243daf  jz      short loc_180243DDD
0x180243db1  add     rcx, 208h
0x180243db8  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180243dbd  mov     rcx, [rax]
0x180243dc0  nop
0x180243dc1  cmp     r13, rcx
0x180243dc4  jl      short loc_180243DDD
0x180243dc6  mov     r8, r12
0x180243dc9  lea     rdx, [rbp+600h+var_F0]
0x180243dd0  lea     rcx, [rbp+600h+var_70]
0x180243dd7  call    ??$emplace@AEBV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@@?$_Hash@V?$_Uset_traits@V?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@V?$_Uhash_compare@V?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@U?$hash@V?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@@2@U?$equal_to@V?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@@2@@2@V?$allocator@V?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@@std@@@std@@@std@@_N@1@AEBV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@1@@Z; std::_Hash<std::_Uset_traits<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>,std::_Uhash_compare<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>,std::hash<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>>>,std::allocator<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer>>,0>>::emplace<std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer> const &>(std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer> const &)
0x180243ddc  nop
0x180243ddd  test    rsi, rsi
0x180243de0  jz      short loc_180243E1B
0x180243de2  or      eax, 0FFFFFFFFh
0x180243de5  lock xadd [rsi+8], eax
0x180243dea  cmp     eax, 1
0x180243ded  jnz     short loc_180243E1B
0x180243def  mov     rax, [rsi]
0x180243df2  mov     rcx, rsi
0x180243df5  mov     rax, [rax]
0x180243df8  call    cs:__guard_dispatch_icall_fptr
0x180243dfe  or      eax, 0FFFFFFFFh
0x180243e01  lock xadd [rsi+0Ch], eax
0x180243e06  cmp     eax, 1
0x180243e09  jnz     short loc_180243E1B
0x180243e0b  mov     rax, [rsi]
0x180243e0e  mov     rcx, rsi
0x180243e11  mov     rax, [rax+8]
0x180243e15  call    cs:__guard_dispatch_icall_fptr
0x180243e1b  mov     rbx, [rbx]
0x180243e1e  cmp     rbx, r15
0x180243e21  jnz     loc_180243D63
0x180243e27  lea     r13, [r14-8]
0x180243e2b  mov     rcx, rdi; _Mtx_t
0x180243e2e  call    _Mtx_unlock
0x180243e33  mov     rsi, [rbp+600h+var_68]
0x180243e3a  mov     rbx, [rsi]
0x180243e3d  jmp     loc_180243F0F
0x180243e42  mov     rax, [rbx+48h]
0x180243e46  mov     qword ptr [rbp+600h+var_D0], rax
0x180243e4d  mov     rsi, [rbx+50h]
0x180243e51  mov     qword ptr [rbp+600h+var_D0+8], rsi
0x180243e58  jmp     loc_180243D9C
0x180243e5d  xorps   xmm0, xmm0
0x180243e60  movups  xmmword ptr [rbp+600h+var_F0], xmm0
0x180243e67  lea     rdx, [rbp+600h+var_F0]
0x180243e6e  mov     rcx, [rbx+10h]
0x180243e72  call    ?GetBase@TurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@QEBA?AV?$shared_ptr@VCandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer::GetBase(void)
0x180243e77  nop
0x180243e78  mov     rcx, qword ptr [rbp+600h+var_F0]
0x180243e7f  test    rcx, rcx
0x180243e82  jz      short loc_180243EC7
0x180243e84  mov     [rbp+600h+var_F8], 0
0x180243e8f  lea     r8, [rbp+600h+var_130]
0x180243e96  lea     rdx, [rbx+10h]
0x180243e9a  call    ?SendTurnRefreshRequest@CandidateBase@ICECore@Dct@Basix@Microsoft@@AEAAXAEBV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@AEBV?$function@$$A6AXVexception_ptr@std@@@Z@7@@Z; Microsoft::Basix::Dct::ICECore::CandidateBase::SendTurnRefreshRequest(std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer> const &,std::function<void (std::exception_ptr)> const &)
0x180243e9f  nop
0x180243ea0  mov     rcx, [rbp+600h+var_F8]
0x180243ea7  test    rcx, rcx
0x180243eaa  jz      short loc_180243EC7
0x180243eac  lea     rax, [rbp+600h+var_130]
0x180243eb3  cmp     rcx, rax
0x180243eb6  setnz   dl
0x180243eb9  mov     rax, [rcx]
0x180243ebc  mov     rax, [rax+20h]
0x180243ec0  call    cs:__guard_dispatch_icall_fptr
0x180243ec6  nop
0x180243ec7  mov     rdi, qword ptr [rbp+600h+var_F0+8]
0x180243ece  test    rdi, rdi
0x180243ed1  jz      short loc_180243F0C
0x180243ed3  or      eax, 0FFFFFFFFh
0x180243ed6  lock xadd [rdi+8], eax
0x180243edb  cmp     eax, 1
0x180243ede  jnz     short loc_180243F0C
0x180243ee0  mov     rax, [rdi]
0x180243ee3  mov     rcx, rdi
0x180243ee6  mov     rax, [rax]
0x180243ee9  call    cs:__guard_dispatch_icall_fptr
0x180243eef  or      eax, 0FFFFFFFFh
0x180243ef2  lock xadd [rdi+0Ch], eax
0x180243ef7  cmp     eax, 1
0x180243efa  jnz     short loc_180243F0C
0x180243efc  mov     rax, [rdi]
0x180243eff  mov     rcx, rdi
0x180243f02  mov     rax, [rax+8]
0x180243f06  call    cs:__guard_dispatch_icall_fptr
0x180243f0c  mov     rbx, [rbx]
0x180243f0f  cmp     rbx, rsi
0x180243f12  jnz     loc_180243E5D
0x180243f18  cmp     dword ptr [r14+2370h], 1
0x180243f20  jbe     short loc_180243F46
0x180243f22  lea     rcx, [r14+2358h]
0x180243f29  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180243f2e  mov     edx, [rax]
0x180243f30  nop
0x180243f31  cmp     edx, 2
0x180243f34  jnz     short loc_180243F3E
0x180243f36  mov     rcx, r13; this
0x180243f39  call    ?StartTestCloneRelay@ICECore@Dct@Basix@Microsoft@@QEAAXXZ; Microsoft::Basix::Dct::ICECore::StartTestCloneRelay(void)
0x180243f3e  cmp     dword ptr [r14+2370h], 1
0x180243f46  jnz     loc_180244DDD
0x180243f4c  mov     eax, [r14+2360h]
0x180243f53  cmp     [r14+235Ch], eax
0x180243f5a  jbe     loc_180244DDD
0x180243f60  lea     rcx, [rsp+700h+var_690]
0x180243f65  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180243f6a  mov     rcx, [rax]
0x180243f6d  mov     rax, 431BDE82D7B634DBh
0x180243f77  imul    rcx
0x180243f7a  mov     rbx, rdx
0x180243f7d  sar     rbx, 12h
0x180243f81  mov     rax, rbx
0x180243f84  shr     rax, 3Fh
0x180243f88  add     rbx, rax
0x180243f8b  mov     ecx, 0EA60h
0x180243f90  xor     edi, edi
0x180243f92  cmp     [r14+100h], dil
0x180243f99  jz      short loc_180243FAC
0x180243f9b  mov     rax, [r14+0F8h]
0x180243fa2  add     rax, rcx
0x180243fa5  cmp     rax, rbx
0x180243fa8  mov     al, 1
0x180243faa  jl      short loc_180243FAF
0x180243fac  mov     al, dil
0x180243faf  mov     esi, ebx
0x180243fb1  sub     esi, [r14+108h]
0x180243fb8  test    al, al
0x180243fba  jz      loc_180244DDD
0x180243fc0  cmp     esi, ecx
0x180243fc2  jbe     loc_180244DDD
0x180243fc8  cmp     [r14+0F0h], dil
0x180243fcf  jnz     loc_180244DDD
0x180243fd5  cmp     [r14+100h], dil
0x180243fdc  jz      loc_180244E4D
0x180243fe2  sub     rbx, [r14+0F8h]
0x180243fe9  xorps   xmm0, xmm0
0x180243fec  movups  [rbp+600h+var_90], xmm0
0x180243ff3  lea     rcx, [rbp+600h+var_90]
0x180243ffa  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180243fff  nop
0x180244000  mov     rax, qword ptr [rbp+600h+var_90]
0x180244007  test    rax, rax
0x18024400a  jz      short loc_180244082
0x18024400c  cmp     [rax+80h], dil
0x180244013  jz      short loc_180244082
0x180244015  lfence
0x180244018  mov     edi, [r14+235Ch]
0x18024401f  xorps   xmm0, xmm0
0x180244022  movups  [rbp+600h+var_B0], xmm0
0x180244029  xorps   xmm1, xmm1
0x18024402c  movdqu  [rbp+600h+var_A0], xmm1
0x180244034  mov     r8d, 54h ; 'T'
0x18024403a  lea     rdx, aCheckRelayPrun; "Check relay prunning: dor=%d, time in m"...
0x180244041  lea     rcx, [rbp+600h+var_B0]
0x180244048  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18024404d  nop
0x18024404e  mov     dword ptr [rsp+700h+Str], esi
0x180244052  mov     dword ptr [rsp+700h+var_6E0], ebx
0x180244056  mov     r9d, edi
0x180244059  lea     r8, [rbp+600h+var_B0]
0x180244060  lea     rdx, aBasixDct; "BASIX_DCT"
0x180244067  lea     rcx, [rbp+600h+var_90]
0x18024406e  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@IHH@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@IHH@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint,int,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint,int,int)
0x180244073  nop
0x180244074  lea     rcx, [rbp+600h+var_B0]
0x18024407b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180244080  xor     edi, edi
0x180244082  mov     rbx, qword ptr [rbp+600h+var_90+8]
0x180244089  or      r13d, 0FFFFFFFFh
0x18024408d  test    rbx, rbx
0x180244090  jz      short loc_1802440CB
0x180244092  mov     eax, r13d
0x180244095  lock xadd [rbx+8], eax
0x18024409a  add     eax, r13d
0x18024409d  jnz     short loc_1802440CB
0x18024409f  mov     rax, [rbx]
0x1802440a2  mov     rcx, rbx
0x1802440a5  mov     rax, [rax]
0x1802440a8  call    cs:__guard_dispatch_icall_fptr
0x1802440ae  mov     eax, r13d
0x1802440b1  lock xadd [rbx+0Ch], eax
0x1802440b6  add     eax, r13d
0x1802440b9  jnz     short loc_1802440CB
0x1802440bb  mov     rax, [rbx]
0x1802440be  mov     rcx, rbx
0x1802440c1  mov     rax, [rax+8]
0x1802440c5  call    cs:__guard_dispatch_icall_fptr
0x1802440cb  xorps   xmm0, xmm0
0x1802440ce  movups  [rbp+600h+var_90], xmm0
0x1802440d5  lea     rcx, [r14-8]
0x1802440d9  lea     rdx, [rbp+600h+var_90]
0x1802440e0  call    ?ComputeDegreeOfRedundency@ICECore@Dct@Basix@Microsoft@@QEAA?AV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(void)
0x1802440e5  nop
0x1802440e6  mov     rax, qword ptr [rbp+600h+var_90]
0x1802440ed  xorps   xmm0, xmm0
0x1802440f0  test    rax, rax
0x1802440f3  jz      loc_180244CDC
0x1802440f9  mov     rdx, [rax+0D0h]
0x180244100  sub     rdx, 0FFFFFFFFFFFFFF80h
0x180244104  movups  [rbp+600h+var_B0], xmm0
0x18024410b  xorps   xmm1, xmm1
0x18024410e  movdqu  [rbp+600h+var_A0], xmm1
0x180244116  mov     r8, [rdx+10h]
0x18024411a  cmp     qword ptr [rdx+18h], 0Fh
0x18024411f  jbe     short loc_180244124
0x180244121  mov     rdx, [rdx]
0x180244124  lea     rcx, [rbp+600h+var_B0]
0x18024412b  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x180244130  nop
0x180244131  mov     r15, [r14+220h]
0x180244138  mov     r12d, [r14+235Ch]
0x18024413f  xorps   xmm0, xmm0
0x180244142  movups  [rbp+600h+var_D0], xmm0
0x180244149  lea     rcx, [rbp+600h+var_D0]
0x180244150  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180244155  nop
0x180244156  mov     rax, qword ptr [rbp+600h+var_D0]
0x18024415d  test    rax, rax
0x180244160  jz      loc_1802441EA
0x180244166  cmp     [rax+80h], dil
  ... truncated ...
```

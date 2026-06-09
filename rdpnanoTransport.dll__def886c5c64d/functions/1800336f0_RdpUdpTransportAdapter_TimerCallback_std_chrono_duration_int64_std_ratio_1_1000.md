# RdpUdpTransportAdapter::TimerCallback(std::chrono::duration<__int64,std::ratio<1,1000>>)

- ea: `0x1800336f0`
- end: `0x1800356d3`
- name: `?TimerCallback@RdpUdpTransportAdapter@@UEAAXV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z`
- size: `8163`
- prototype: ``
- caller_count: `0`
- callee_count: `56`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017344`
- `0x180017380`
- `0x180017494`
- `0x1800187a8`
- `0x180018b94`
- `0x180018ea4`
- `0x1800191b4`
- `0x18001944c`
- `0x18001955c`
- `0x18001979c`
- `0x1800199ec`
- `0x18001a768`
- `0x18001bd48`
- `0x18001bed4`
- `0x18001c258`
- `0x18001d174`
- `0x18001dad8`
- `0x18001db78`
- `0x18001dc00`
- `0x18001f814`
- `0x18001f860`
- `0x18001f8d4`
- `0x18001f970`
- `0x180024700`
- `0x180024760`
- `0x180027bf8`
- `0x180028820`
- `0x18002a8ec`
- `0x18002d030`
- `0x18002dfa0`
- `0x18002fec0`
- `0x18003302c`
- `0x18003334c`
- `0x1800334a8`
- `0x1800336f0`
- `0x1800377b4`
- `0x180037ce4`
- `0x18003c308`
- `0x18003d8fc`
- `0x18003da74`
- `0x1801b0ab4`
- `0x1802e2464`
- `0x1802ea40c`
- `0x1802ef188`
- `0x1802efc44`
- `0x180311d5c`

## string_xrefs

- `0x180035655`: `C:\__w\1\s\rdpnanodll\rdpnanostreamwrapper.cpp`
- `0x180033f61`: `wsReadQueueDepth=%d, wsSendQueueDepth=%d`
- `0x1800341ba`: `Microsoft::Basix::Dct.Smiles.LinkPoolSize`
- `0x180034568`: `numSmilesLinks`
- `0x1800348c5`: `WSreadBufferDepth`
- `0x180034ead`: `Microsoft::Basix::Dct.NetworkExceptionRead`
- `0x180034f6c`: `Microsoft::Basix::Dct.NetworkExceptionWrite`
- `0x180035386`: `LinkSwitch`
- `0x1800353e1`: `OnWritableThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=151
__int64 __fastcall RdpUdpTransportAdapter::TimerCallback(__int64 a1)
{
  struct Microsoft::Basix::Instrumentation::ActivityManager *v2; // rax
  __int64 v3; // r9
  struct Microsoft::Basix::Instrumentation::ActivityManager *v4; // rax
  ClosingCallback **v6; // r9
  ClosingCallback **v7; // rdx
  __int64 v8; // r8
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  ClosingCallback *v11; // rcx
  ClosingCallback *v12; // r12
  struct Microsoft::Basix::Instrumentation::ActivityManager *v13; // rax
  _QWORD *v14; // rax
  unsigned __int64 v15; // rbx
  unsigned int *v16; // rsi
  _QWORD *v17; // rax
  volatile signed __int32 *v18; // rdi
  volatile signed __int32 *v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  volatile signed __int32 *v24; // rbx
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdx
  signed __int32 v29; // eax
  signed __int32 v30; // ett
  __int64 v31; // rdi
  volatile signed __int32 *v32; // r13
  __int64 v33; // rsi
  __int64 v34; // rax
  unsigned int v35; // ebx
  __int64 v36; // rax
  int v37; // r15d
  int v38; // r9d
  volatile signed __int32 *v39; // rbx
  unsigned __int64 v40; // rdi
  __int64 Property; // rax
  char v42; // bl
  __int64 v43; // rax
  __int64 v44; // rdi
  bool v45; // zf
  char v46; // bl
  unsigned __int64 v47; // rsi
  __int64 v48; // rax
  __int64 v49; // rsi
  __int64 v50; // rdi
  __int64 v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rdx
  _BYTE *v57; // rax
  int v58; // esi
  __int64 v59; // rsi
  __int64 v60; // rdi
  __int64 v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rdx
  __int64 v70; // rdx
  __int64 v71; // rax
  __int64 v72; // rdx
  unsigned int v73; // esi
  __int64 v74; // rdx
  __int64 v75; // rdx
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rdx
  __int64 v79; // rdx
  __int64 v80; // rdi
  __int64 v81; // rbx
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rdx
  __int64 v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rdx
  __int64 v90; // rdx
  int v91; // esi
  unsigned int v92; // edi
  volatile signed __int32 *v93; // rbx
  __int64 v94; // rbx
  __int64 v95; // rdx
  __int64 v96; // rdx
  __int64 v97; // rbx
  __int64 v98; // rdx
  __int64 v99; // rbx
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // r8
  unsigned int v103; // ebx
  volatile signed __int32 *v104; // rbx
  unsigned int v105; // ebx
  volatile signed __int32 *v106; // rbx
  __int64 v107; // rbx
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // rbx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  Microsoft::Basix::Instrumentation::DelayedTraceManager **v115; // rax
  __int64 *v116; // r8
  volatile signed __int32 **v117; // rbx
  volatile signed __int32 *v118; // rdx
  signed __int32 v119; // eax
  signed __int32 v120; // ett
  __int64 v121; // rcx
  volatile signed __int32 *v122; // rbx
  struct Microsoft::Basix::Instrumentation::ActivityManager *v123; // rax
  __int64 v124; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v125; // rax
  __int64 Description; // rax
  __int64 v127; // rbx
  const char *v128; // r8
  const char *v129; // r9
  __int64 *v130; // rbp
  unsigned __int16 *v131; // rbx
  char v132; // al
  _QWORD *v133; // rcx
  int v134; // eax
  __int64 v135; // rax
  __int64 v136; // rbx
  const char *v137; // r8
  __int64 v138; // rax
  __int64 v139; // rbx
  const char *v140; // r8
  __int64 *v141; // rdx
  __int64 v142; // [rsp+0h] [rbp-948h] BYREF
  char *v143; // [rsp+20h] [rbp-928h]
  char *Str; // [rsp+28h] [rbp-920h]
  __int64 v145; // [rsp+30h] [rbp-918h]
  char v146[4]; // [rsp+60h] [rbp-8E8h] BYREF
  int v147; // [rsp+64h] [rbp-8E4h]
  unsigned int v148; // [rsp+68h] [rbp-8E0h] BYREF
  __int128 v149; // [rsp+70h] [rbp-8D8h] BYREF
  __int128 v150; // [rsp+80h] [rbp-8C8h]
  __int64 *v151; // [rsp+90h] [rbp-8B8h] BYREF
  __int128 v152; // [rsp+98h] [rbp-8B0h] BYREF
  unsigned __int64 v153; // [rsp+A8h] [rbp-8A0h] BYREF
  __int128 v154; // [rsp+B0h] [rbp-898h] BYREF
  __int128 v155; // [rsp+C0h] [rbp-888h]
  _BYTE v156[32]; // [rsp+D0h] [rbp-878h] BYREF
  volatile signed __int32 **v157; // [rsp+F0h] [rbp-858h]
  ClosingCallback *v158[2]; // [rsp+F8h] [rbp-850h]
  __int64 v159; // [rsp+108h] [rbp-840h]
  unsigned int *v160; // [rsp+110h] [rbp-838h] BYREF
  __int128 v161; // [rsp+118h] [rbp-830h]
  __int128 v162; // [rsp+128h] [rbp-820h] BYREF
  __int128 v163; // [rsp+138h] [rbp-810h]
  __int64 *v164; // [rsp+148h] [rbp-800h]
  unsigned int v165; // [rsp+150h] [rbp-7F8h]
  __int64 *v166; // [rsp+158h] [rbp-7F0h] BYREF
  __int128 v167; // [rsp+160h] [rbp-7E8h] BYREF
  __int128 v168; // [rsp+170h] [rbp-7D8h]
  _OWORD v169[2]; // [rsp+180h] [rbp-7C8h] BYREF
  __int64 *v170; // [rsp+1A0h] [rbp-7A8h]
  __int64 v171[2]; // [rsp+1A8h] [rbp-7A0h] BYREF
  __int128 v172; // [rsp+1B8h] [rbp-790h]
  _BYTE v173[32]; // [rsp+1C8h] [rbp-780h] BYREF
  _BYTE v174[32]; // [rsp+1E8h] [rbp-760h] BYREF
  _OWORD v175[2]; // [rsp+208h] [rbp-740h] BYREF
  _OWORD v176[2]; // [rsp+228h] [rbp-720h] BYREF
  _OWORD v177[2]; // [rsp+248h] [rbp-700h] BYREF
  _OWORD v178[2]; // [rsp+268h] [rbp-6E0h] BYREF
  _OWORD v179[2]; // [rsp+288h] [rbp-6C0h] BYREF
  _OWORD v180[2]; // [rsp+2A8h] [rbp-6A0h] BYREF
  _OWORD v181[2]; // [rsp+2C8h] [rbp-680h] BYREF
  const Microsoft::Basix::SystemException *v182; // [rsp+2E8h] [rbp-660h] BYREF
  _BYTE v183[32]; // [rsp+2F0h] [rbp-658h] BYREF
  __int64 v184[4]; // [rsp+310h] [rbp-638h] BYREF
  __int64 v185[4]; // [rsp+330h] [rbp-618h] BYREF
  __int64 v186[4]; // [rsp+350h] [rbp-5F8h] BYREF
  __int64 v187[4]; // [rsp+370h] [rbp-5D8h] BYREF
  __int64 v188[4]; // [rsp+390h] [rbp-5B8h] BYREF
  _BYTE v189[32]; // [rsp+3B0h] [rbp-598h] BYREF
  _BYTE v190[32]; // [rsp+3D0h] [rbp-578h] BYREF
  _BYTE v191[32]; // [rsp+3F0h] [rbp-558h] BYREF
  _BYTE v192[32]; // [rsp+410h] [rbp-538h] BYREF
  _BYTE v193[32]; // [rsp+430h] [rbp-518h] BYREF
  _BYTE v194[32]; // [rsp+450h] [rbp-4F8h] BYREF
  _BYTE v195[32]; // [rsp+470h] [rbp-4D8h] BYREF
  _BYTE v196[32]; // [rsp+490h] [rbp-4B8h] BYREF
  _BYTE v197[32]; // [rsp+4B0h] [rbp-498h] BYREF
  _BYTE v198[32]; // [rsp+4D0h] [rbp-478h] BYREF
  _BYTE v199[32]; // [rsp+4F0h] [rbp-458h] BYREF
  _BYTE v200[32]; // [rsp+510h] [rbp-438h] BYREF
  _BYTE v201[32]; // [rsp+530h] [rbp-418h] BYREF
  _BYTE v202[32]; // [rsp+550h] [rbp-3F8h] BYREF
  _BYTE v203[32]; // [rsp+570h] [rbp-3D8h] BYREF
  _BYTE v204[32]; // [rsp+590h] [rbp-3B8h] BYREF
  _BYTE v205[32]; // [rsp+5B0h] [rbp-398h] BYREF
  _BYTE v206[32]; // [rsp+5D0h] [rbp-378h] BYREF
  _BYTE v207[56]; // [rsp+5F0h] [rbp-358h] BYREF
  _BYTE v208[112]; // [rsp+628h] [rbp-320h] BYREF
  void *v209[2]; // [rsp+698h] [rbp-2B0h] BYREF
  _BYTE v210[32]; // [rsp+6A8h] [rbp-2A0h] BYREF
  _BYTE v211[32]; // [rsp+6C8h] [rbp-280h] BYREF
  _BYTE v212[32]; // [rsp+6E8h] [rbp-260h] BYREF
  _BYTE v213[32]; // [rsp+708h] [rbp-240h] BYREF
  _BYTE v214[32]; // [rsp+728h] [rbp-220h] BYREF
  _BYTE v215[32]; // [rsp+748h] [rbp-200h] BYREF
  _BYTE v216[32]; // [rsp+768h] [rbp-1E0h] BYREF
  _BYTE v217[32]; // [rsp+788h] [rbp-1C0h] BYREF
  _BYTE v218[32]; // [rsp+7A8h] [rbp-1A0h] BYREF
  _BYTE v219[32]; // [rsp+7C8h] [rbp-180h] BYREF
  _BYTE v220[32]; // [rsp+7E8h] [rbp-160h] BYREF
  _BYTE v221[32]; // [rsp+808h] [rbp-140h] BYREF
  _BYTE v222[32]; // [rsp+828h] [rbp-120h] BYREF
  _BYTE v223[32]; // [rsp+848h] [rbp-100h] BYREF
  _BYTE v224[32]; // [rsp+868h] [rbp-E0h] BYREF
  _BYTE v225[32]; // [rsp+888h] [rbp-C0h] BYREF
  _BYTE v226[32]; // [rsp+8A8h] [rbp-A0h] BYREF
  int v227[4]; // [rsp+8C8h] [rbp-80h] BYREF
  int v228[4]; // [rsp+8D8h] [rbp-70h] BYREF
  __int128 v229; // [rsp+8E8h] [rbp-60h]
  __int128 v230; // [rsp+8F8h] [rbp-50h] BYREF
  _BYTE v231[16]; // [rsp+908h] [rbp-40h] BYREF

  v147 = 0;
  v2 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
  LOBYTE(v3) = 1;
  Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(v2, v231, a1 + 252, v3);
  if ( *(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(a1 + 384) )
  {
    v4 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
    return (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, int *, _BYTE *))(*(_QWORD *)v4 + 32LL))(
             v4,
             v228,
             v231);
  }
  v148 = 0;
  v6 = (ClosingCallback **)(a1 + 312);
  v170 = (__int64 *)(a1 + 312);
  *(_OWORD *)v158 = 0;
  v7 = (ClosingCallback **)(a1 + 320);
  v157 = (volatile signed __int32 **)(a1 + 320);
  v8 = *(_QWORD *)(a1 + 320);
  if ( v8 )
  {
    v9 = *(_DWORD *)(v8 + 8);
    while ( v9 )
    {
      v10 = v9;
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9);
      if ( v10 == v9 )
      {
        v11 = *v6;
        v158[0] = *v6;
        v12 = *v7;
        v158[1] = *v7;
        goto LABEL_8;
      }
    }
  }
  v11 = v158[0];
  v12 = v158[1];
LABEL_8:
  if ( v11 )
  {
    ClosingCallback::GetClosingReason(v11, (enum ClosingReason *)&v148);
    if ( v148 )
    {
      if ( v12 && _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(ClosingCallback *))v12)(v12);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(ClosingCallback *))(*(_QWORD *)v12 + 8LL))(v12);
      }
LABEL_14:
      v13 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
      return (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, int *, _BYTE *))(*(_QWORD *)v13 + 32LL))(
               v13,
               v228,
               v231);
    }
  }
  v14 = (_QWORD *)std::chrono::steady_clock::now(&v152);
  v159 = a1 - 1088;
  v15 = *v14 / 1000000LL - *(_QWORD *)(a1 - 1088 + 1392);
  v153 = v15;
  v16 = (unsigned int *)(a1 + 296);
  v160 = (unsigned int *)(a1 + 296);
  if ( v15 < (unsigned int)(*(_DWORD *)(a1 + 296) - 500) )
  {
    v17 = (_QWORD *)Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::ITimerCallback>(
                      a1 + *(int *)(*(_QWORD *)(a1 - 1080) + 4LL) - 1080LL,
                      v228);
    *(_OWORD *)v227 = 0;
    if ( v17[1] )
    {
      *(_QWORD *)v227 = *v17;
      *(_QWORD *)&v227[2] = v17[1];
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)&v227[2] + 12LL), 1u);
    }
    v160 = (unsigned int *)((unsigned __int64)*v16 >> 2);
    Microsoft::Basix::Timer::Setup(a1 + 272, &v160, v227);
    v18 = *(volatile signed __int32 **)&v228[2];
    if ( *(_QWORD *)&v228[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v228[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    *(_OWORD *)v227 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v227);
    if ( *(_QWORD *)v227 && *(_BYTE *)(*(_QWORD *)v227 + 128LL) )
    {
      v149 = 0;
      v150 = 0;
      std::string::_Construct<1,char const *>(
        &v149,
        "The controller hasn't received any packets in the last %d ms!!! ",
        64);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned __int64>(
        v227,
        "RDPNANOSTREAM",
        &v149,
        v15);
      std::string::_Tidy_deallocate(&v149);
    }
    v19 = *(volatile signed __int32 **)&v227[2];
    if ( *(_QWORD *)&v227[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v227[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    *(_OWORD *)v227 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v227);
    if ( *(_QWORD *)v227 && *(_BYTE *)(*(_QWORD *)v227 + 128LL) )
    {
      std::_Integral_to_string<char,unsigned __int64>(v169, v15);
      *(_OWORD *)v228 = 0;
      v229 = 0;
      std::string::_Construct<1,char const *>(v228, ":", 1);
      v167 = 0;
      v168 = 0;
      std::string::_Construct<1,char const *>(&v167, "\"", 1);
      v149 = 0;
      v150 = 0;
      std::string::_Construct<1,char const *>(&v149, "\"", 1);
      v20 = std::operator+<char>(v156, &v149, "timegap");
      LOBYTE(v21) = v146[0];
      std::string::string(&v162, v21, v20, &v167);
      LOBYTE(v22) = v146[0];
      std::string::string(&v154, v22, &v162, v228);
      LOBYTE(v23) = v146[0];
      std::string::string(v171, v23, &v154, v169);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v227,
        (int)"RD_CHECKPOINT",
        0,
        (int)"UDPTransport",
        "NetworkDrop",
        "The controller hasn't received any packets in the last a while",
        (__int64)v171);
      std::string::_Tidy_deallocate(&v154);
      std::string::_Tidy_deallocate(&v162);
      std::string::_Tidy_deallocate(v156);
      std::string::_Tidy_deallocate(&v149);
      std::string::_Tidy_deallocate(&v167);
      std::string::_Tidy_deallocate(v228);
      std::string::_Tidy_deallocate(v169);
    }
    v24 = *(volatile signed __int32 **)&v227[2];
    if ( *(_QWORD *)&v227[2] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v227[2] + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( !_InterlockedDecrement(v24 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    v25 = Microsoft::Basix::ToString<unsigned __int64>(v174, &v153, 0, 6);
    v26 = std::operator+<char>(v173, "The controller hasn't received any packets in the last", v25);
    v27 = std::operator+<char>(v156, v26, " ms, but it is not yet time to shut down.");
    RdpUdpTransportAdapter::DumpLastIOInfo(a1 - 1088, v27);
    std::string::_Tidy_deallocate(v173);
    std::string::_Tidy_deallocate(v174);
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(ClosingCallback *))v12)(v12);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(ClosingCallback *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    goto LABEL_14;
  }
  LOBYTE(v151) = 0;
  v148 = 0;
  v161 = 0;
  v28 = *(_QWORD *)(a1 + 368);
  if ( v28 )
  {
    v29 = *(_DWORD *)(v28 + 8);
    while ( v29 )
    {
      v30 = v29;
      v29 = _InterlockedCompareExchange((volatile signed __int32 *)(v28 + 8), v29 + 1, v29);
      if ( v30 == v29 )
      {
        v31 = *(_QWORD *)(a1 + 360);
        *(_QWORD *)&v161 = v31;
        v32 = *(volatile signed __int32 **)(a1 + 368);
        *((_QWORD *)&v161 + 1) = v32;
        goto LABEL_47;
      }
    }
  }
  v32 = (volatile signed __int32 *)*((_QWORD *)&v161 + 1);
  v31 = v161;
LABEL_47:
  if ( !v31 )
  {
    *(_OWORD *)v228 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v228);
    if ( *(_QWORD *)v228 && *(_BYTE *)(*(_QWORD *)v228 + 128LL) )
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,char const *>(
        (int)v228,
        (int)"RD_CHECKPOINT",
        0,
        (int)"UDPTransport",
        "NetworkDrop",
        "UDP Transport at transport layer not receiving any traffic in 17000 ms, and no winsock info",
        (__int64)&Str1);
    v104 = *(volatile signed __int32 **)&v228[2];
    if ( *(_QWORD *)&v228[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v228[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v104)(v104);
        if ( _InterlockedExchangeAdd(v104 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v104 + 8LL))(v104);
      }
    }
    v92 = 4;
    goto LABEL_124;
  }
  v33 = *(_QWORD *)std::chrono::steady_clock::now(&v152) / 1000LL;
  v34 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 72LL))(v31, v207);
  v35 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v34 + 20);
  v165 = v35;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,Microsoft::Basix::Dct::IAsyncTransport::IOMetrics::PeerIOInfoCircularBuffer>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::string const,Microsoft::Basix::Dct::IAsyncTransport::IOMetrics::PeerIOInfoCircularBuffer>,void *>>>(
    v209,
    v209,
    *((_QWORD *)v209[0] + 1));
  operator delete(v209[0], (const struct std::nothrow_t *)0x270);
  std::string::_Tidy_deallocate(v208);
  v36 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 72LL))(v31, v207);
  v37 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v36 + 32);
  LODWORD(v164) = v37;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,Microsoft::Basix::Dct::IAsyncTransport::IOMetrics::PeerIOInfoCircularBuffer>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::string const,Microsoft::Basix::Dct::IAsyncTransport::IOMetrics::PeerIOInfoCircularBuffer>,void *>>>(
    v209,
    v209,
    *((_QWORD *)v209[0] + 1));
  operator delete(v209[0], (const struct std::nothrow_t *)0x270);
  std::string::_Tidy_deallocate(v208);
  v230 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v230);
  if ( (_QWORD)v230 && *(_BYTE *)(v230 + 128) )
  {
    v149 = 0;
    v150 = 0;
    std::string::_Construct<1,char const *>(&v149, "wsReadQueueDepth=%d, wsSendQueueDepth=%d", 40, v38);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,int,int>(
      (unsigned int)&v230,
      (unsigned int)"RDPNANOSTREAM",
      (unsigned int)&v149,
      v35,
      v37);
    std::string::_Tidy_deallocate(&v149);
  }
  v39 = (volatile signed __int32 *)*((_QWORD *)&v230 + 1);
  if ( *((_QWORD *)&v230 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v230 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      if ( !_InterlockedDecrement(v39 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
  v149 = 0;
  v150 = 0u;
  std::string::_Construct<1,char const *>(
    &v149,
    "The controller hasn't received any packets in the last 17000 ms, shutting down...",
    81);
  LODWORD(v159) = RdpUdpTransportAdapter::DumpLastIOInfo(v159, &v149);
  v40 = v31 + 40;
  v153 = v40;
  v149 = 0;
  v150 = 0;
  std::string::_Construct<1,char const *>(&v149, "Microsoft::Basix::Dct.ICE.Turn.LackOfCap", 40);
  Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v40, v228, &v149);
  v146[0] = 0;
  v42 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
          *(_QWORD *)(Property + 16),
          v146);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v228);
  std::string::_Tidy_deallocate(&v149);
  v149 = 0;
  v150 = 0;
  std::string::_Construct<1,char const *>(&v149, "Microsoft::Basix::Dct.ICE.Turn.LackOfCapTime", 44);
  v43 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v40, v228, &v149);
  v166 = 0;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::chrono::duration<__int64,std::ratio<1,1000000>>>(
    *(_QWORD *)(v43 + 16),
    &v152,
    &v166);
  v44 = (v33 - (__int64)v152) / 1000000;
  *(_QWORD *)&v152 = v44;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v228);
  std::string::_Tidy_deallocate(&v149);
  v45 = v42 == 0;
  v46 = (char)v151;
  if ( !v45 && (unsigned int)v44 < 0x4B0 )
    v46 = 1;
  v146[0] = v46;
  v149 = 0;
  v150 = 0;
  std::string::_Construct<1,char const *>(&v149, "Microsoft::Basix::Dct.Smiles.LinkPoolSize", 41);
  v47 = v153;
  v48 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v153, v228, &v149);
  LODWORD(v151) = 0;
  LODWORD(v151) = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned int>(
                    *(_QWORD *)(v48 + 16),
                    &v151);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v228);
  std::string::_Tidy_deallocate(&v149);
  *(_OWORD *)v228 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v228);
  if ( *(_QWORD *)v228 && *(_BYTE *)(*(_QWORD *)v228 + 128LL) )
  {
    v166 = v171;
    if ( v46 )
    {
      v49 = std::string::string(v183, "true");
      v147 = 1;
      v50 = std::string::string(v225, ":");
      v147 = 3;
      v51 = std::string::string(v224, "\"");
      v147 = 7;
      v52 = std::string::string(v223, "\"");
      v147 = 15;
      v53 = std::operator+<char>(v222, v52, "turnLackOfCapFlagged");
      v147 = 31;
      LOBYTE(v54) = v146[0];
      std::string::string(v156, v54, v53, v51);
      v147 = 63;
      LOBYTE(v55) = v146[0];
      std::string::string(v173, v55, v156, v50);
      v147 = 127;
      LOBYTE(v56) = v146[0];
      std::string::string(v174, v56, v173, v49);
      v57 = v174;
      v58 = 255;
    }
    else
    {
      v59 = std::string::string(v221, "false");
      v147 = 256;
      v60 = std::string::string(v220, ":");
      v147 = 768;
      v61 = std::string::string(v219, "\"");
      v147 = 1792;
      v62 = std::string::string(v226, "\"");
      v147 = 3840;
      v63 = std::operator+<char>(v217, v62, "turnLackOfCapFlagged");
      v147 = 7936;
      LOBYTE(v64) = v146[0];
      std::string::string(v206, v64, v63, v61);
      v147 = 16128;
      LOBYTE(v65) = v146[0];
      std::string::string(v205, v65, v206, v60);
      v147 = 32512;
      LOBYTE(v66) = v146[0];
      std::string::string(v204, v66, v205, v59);
      v57 = v204;
      v58 = 65280;
    }
    v147 = v58;
    *(_OWORD *)v171 = *(_OWORD *)v57;
    v172 = *((_OWORD *)v57 + 1);
    *((_QWORD *)v57 + 2) = 0;
    *((_QWORD *)v57 + 3) = 15;
    *v57 = 0;
    *(_QWORD *)&v230 = v184;
    std::_Integral_to_string<char,unsigned int>(v203, (unsigned int)v151);
    v154 = 0;
    v155 = 0;
    std::string::_Construct<1,char const *>(&v154, ":", 1);
    v162 = 0;
    v163 = 0;
    std::string::_Construct<1,char const *>(&v162, "\"", 1);
    memset(v169, 0, sizeof(v169));
    std::string::_Construct<1,char const *>(v169, "\"", 1);
    v67 = std::operator+<char>(v216, v169, "numSmilesLinks");
    LOBYTE(v68) = v146[0];
    std::string::string(v202, v68, v67, &v162);
    LOBYTE(v69) = v146[0];
    std::string::string(v201, v69, v202, &v154);
    LOBYTE(v70) = v146[0];
    std::string::string(v184, v70, v201, v203);
    v151 = v185;
    std::_Integral_to_string<char,unsigned int>(v200, (unsigned int)v152);
    memset(v181, 0, sizeof(v181));
    std::string::_Construct<1,char const *>(v181, ":", 1);
    memset(v180, 0, sizeof(v180));
    std::string::_Construct<1,char const *>(v180, "\"", 1);
    memset(v179, 0, sizeof(v179));
    std::string::_Construct<1,char const *>(v179, "\"", 1);
    v71 = std::operator+<char>(v215, v179, "tsInSecAgoTurnLackOfCapFlagged");
    LOBYTE(v72) = v146[0];
    std::string::string(v199, v72, v71, v180);
    v73 = v58 | 0x80000000;
    v147 = v73;
    LOBYTE(v74) = v146[0];
    std::string::string(v198, v74, v199, v181);
    v73 |= 0x40000000u;
    v147 = v73;
    LOBYTE(v75) = v146[0];
    std::string::string(v185, v75, v198, v200);
    v73 |= 0x20000000u;
    v147 = v73;
    *(_QWORD *)&v152 = v186;
    std::_Integral_to_string<char,int>(v197, (unsigned int)v164);
    v73 |= 0x10000000u;
    v147 = v73;
    memset(v178, 0, sizeof(v178));
    std::string::_Construct<1,char const *>(v178, ":", 1);
    memset(v177, 0, sizeof(v177));
    std::string::_Construct<1,char const *>(v177, "\"", 1);
    memset(v176, 0, sizeof(v176));
    std::string::_Construct<1,char const *>(v176, "\"", 1);
    v76 = std::operator+<char>(v214, v176, "WSSendBufferDepth");
    LOBYTE(v77) = v146[0];
    std::string::string(v196, v77, v76, v177);
    v73 |= 0x8000000u;
    v147 = v73;
    LOBYTE(v78) = v146[0];
    std::string::string(v195, v78, v196, v178);
    LOBYTE(v79) = v146[0];
    std::string::string(v186, v79, v195, v197);
    v164 = v187;
    std::_Integral_to_string<char,int>(v194, v165);
    v80 = std::string::string(v213, ":");
    v81 = std::string::string(v212, "\"");
    v82 = std::string::string(v211, "\"");
    v83 = std::operator+<char>(v210, v82, "WSreadBufferDepth");
    LOBYTE(v84) = v146[0];
    std::string::string(v193, v84, v83, v81);
    LOBYTE(v85) = v146[0];
    std::string::string(v192, v85, v193, v80);
    LOBYTE(v86) = v146[0];
    std::string::string(v187, v86, v192, v194);
    std::_Integral_to_string<char,int>(v191, (unsigned int)v159);
    memset(v175, 0, sizeof(v175));
    std::string::_Construct<1,char const *>(v175, ":", 1);
    v167 = 0;
    v168 = 0;
    std::string::_Construct<1,char const *>(&v167, "\"", 1);
    v149 = 0;
    v150 = 0;
    std::string::_Construct<1,char const *>(&v149, "\"", 1);
    v87 = std::operator+<char>(v218, &v149, "diffFromLastReceivedTimeInMs");
    LOBYTE(v88) = v146[0];
    std::string::string(v190, v88, v87, &v167);
    LOBYTE(v89) = v146[0];
    std::string::string(v189, v89, v190, v175);
    LOBYTE(v90) = v146[0];
    std::string::string(v188, v90, v189, v191);
    v91 = v73 | 0x4000000;
    v147 = v91;
    Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string>(
      (int)v228,
      (int)"RD_CHECKPOINT",
      0,
      (int)"UDPTransport",
      "NetworkDrop",
      "UDP Transport at winsock layer not receiving any traffic in 17000 ms",
      (__int64)v188,
      (__int64)v187,
      (__int64)v186,
      (__int64)v185,
      (__int64)v184,
      (__int64)v171);
    std::string::_Tidy_deallocate(v189);
    std::string::_Tidy_deallocate(v190);
    std::string::_Tidy_deallocate(v218);
    std::string::_Tidy_deallocate(&v149);
    std::string::_Tidy_deallocate(&v167);
    std::string::_Tidy_deallocate(v175);
    std::string::_Tidy_deallocate(v191);
    std::string::_Tidy_deallocate(v192);
    std::string::_Tidy_deallocate(v193);
    std::string::_Tidy_deallocate(v210);
    std::string::_Tidy_deallocate(v211);
    std::string::_Tidy_deallocate(v212);
    std::string::_Tidy_deallocate(v213);
    std::string::_Tidy_deallocate(v194);
    std::string::_Tidy_deallocate(v195);
    std::string::_Tidy_deallocate(v196);
    std::string::_Tidy_deallocate(v214);
    std::string::_Tidy_deallocate(v176);
    std::string::_Tidy_deallocate(v177);
    std::string::_Tidy_deallocate(v178);
    std::string::_Tidy_deallocate(v197);
    std::string::_Tidy_deallocate(v198);
    std::string::_Tidy_deallocate(v199);
    std::string::_Tidy_deallocate(v215);
    std::string::_Tidy_deallocate(v179);
    std::string::_Tidy_deallocate(v180);
    std::string::_Tidy_deallocate(v181);
    std::string::_Tidy_deallocate(v200);
    std::string::_Tidy_deallocate(v201);
    std::string::_Tidy_deallocate(v202);
    std::string::_Tidy_deallocate(v216);
    std::string::_Tidy_deallocate(v169);
    std::string::_Tidy_deallocate(&v162);
    std::string::_Tidy_deallocate(&v154);
    std::string::_Tidy_deallocate(v203);
    if ( (v91 & 0x8000) != 0 )
    {
      LOWORD(v91) = v91 & 0x7FFF;
      std::string::_Tidy_deallocate(v204);
    }
    if ( (v91 & 0x4000) != 0 )
    {
      LOWORD(v91) = v91 & 0xBFFF;
      std::string::_Tidy_deallocate(v205);
    }
    if ( (v91 & 0x2000) != 0 )
    {
      LOWORD(v91) = v91 & 0xDFFF;
      std::string::_Tidy_deallocate(v206);
    }
    if ( (v91 & 0x1000) != 0 )
    {
      LOWORD(v91) = v91 & 0xEFFF;
      std::string::_Tidy_deallocate(v217);
    }
    if ( (v91 & 0x800) != 0 )
    {
      LOWORD(v91) = v91 & 0xF7FF;
      std::string::_Tidy_deallocate(v226);
    }
    if ( (v91 & 0x400) != 0 )
    {
      LOWORD(v91) = v91 & 0xFBFF;
      std::string::_Tidy_deallocate(v219);
    }
    if ( (v91 & 0x200) != 0 )
    {
      LOWORD(v91) = v91 & 0xFDFF;
      std::string::_Tidy_deallocate(v220);
    }
    if ( (v91 & 0x100) != 0 )
      std::string::_Tidy_deallocate(v221);
    if ( (v91 & 0x80u) != 0 )
    {
      LOBYTE(v91) = v91 & 0x7F;
      std::string::_Tidy_deallocate(v174);
    }
    if ( (v91 & 0x40) != 0 )
    {
      LOBYTE(v91) = v91 & 0xBF;
      std::string::_Tidy_deallocate(v173);
    }
    if ( (v91 & 0x20) != 0 )
    {
      LOBYTE(v91) = v91 & 0xDF;
      std::string::_Tidy_deallocate(v156);
    }
    if ( (v91 & 0x10) != 0 )
    {
      LOBYTE(v91) = v91 & 0xEF;
      std::string::_Tidy_deallocate(v222);
    }
    if ( (v91 & 8) != 0 )
    {
      LOBYTE(v91) = v91 & 0xF7;
      std::string::_Tidy_deallocate(v223);
    }
    v92 = 4;
    if ( (v91 & 4) != 0 )
    {
      LOBYTE(v91) = v91 & 0xFB;
      std::string::_Tidy_deallocate(v224);
    }
    if ( (v91 & 2) != 0 )
    {
      LOBYTE(v91) = v91 & 0xFD;
      std::string::_Tidy_deallocate(v225);
    }
    if ( (v91 & 1) != 0 )
      std::string::_Tidy_deallocate(v183);
    v47 = v153;
  }
  else
  {
    v92 = 4;
  }
  v93 = *(volatile signed __int32 **)&v228[2];
  if ( *(_QWORD *)&v228[2] )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v228[2] + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v93)(v93);
      if ( !_InterlockedDecrement(v93 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v93 + 8LL))(v93);
    }
  }
  *(_OWORD *)v227 = 0;
  v154 = 0;
  v155 = 0;
  std::string::_Construct<1,char const *>(&v154, "Microsoft::Basix::Dct.NetworkExceptionRead", 42);
  v94 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v47, &v167, &v154);
  v152 = 0;
  __ExceptionPtrCreate(&v152);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
    *(_QWORD *)(v94 + 16),
    v227,
    &v152);
  __ExceptionPtrDestroy(&v152);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v167);
  std::string::_Tidy_deallocate(&v154);
  if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                           v227,
                           v95) )
  {
    v162 = 0;
    v163 = 0;
    std::string::_Construct<1,char const *>(&v162, "Microsoft::Basix::Dct.NetworkExceptionWrite", 43);
    v97 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v47, &v149, &v162);
    *(_OWORD *)v228 = 0;
    __ExceptionPtrCreate(v228);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
      *(_QWORD *)(v97 + 16),
      &v230,
      v228);
    __ExceptionPtrAssign(v227, &v230);
    __ExceptionPtrDestroy(&v230);
    __ExceptionPtrDestroy(v228);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v149);
    std::string::_Tidy_deallocate(&v162);
  }
  if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                           v227,
                           v96) )
  {
    v162 = 0;
    v163 = 0;
    std::string::_Construct<1,char const *>(&v162, "Microsoft::Basix::Dct.LastException", 35);
    v99 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v47, &v149, &v162);
    *(_OWORD *)v228 = 0;
    __ExceptionPtrCreate(v228);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
      *(_QWORD *)(v99 + 16),
      &v230,
      v228);
    __ExceptionPtrAssign(v227, &v230);
    __ExceptionPtrDestroy(&v230);
    __ExceptionPtrDestroy(v228);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v149);
    std::string::_Tidy_deallocate(&v162);
  }
  if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                          v227,
                          v98) )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v230, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v230);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                            &v230,
                            v124) )
    {
      v125 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v230);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v125) )
      {
        Description = Microsoft::Basix::Exception::CreateDescription(v183, v227);
        v127 = std::string::c_str(Description);
        std::string::string(
          v156,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          v128,
          v129,
          v143,
          (_DWORD)Str,
          (const char *)v145);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (unsigned int)&v230,
          (unsigned int)"BASIX_NETWORK_DCT",
          (unsigned int)v156,
          (unsigned int)"NetworkDown due to winsock layer exception",
          v127,
          (__int64)"C:\\__w\\1\\s\\rdpnanodll\\rdpnanostreamwrapper.cpp",
          62,
          (__int64)"RdpUdpTransportAdapter::TimerCallback");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v156);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v183);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v230);
    std::exception_ptr::exception_ptr((std::exception_ptr *)v228, (const struct std::exception_ptr *)v227);
    try
    {
      std::rethrow_exception();
      JUMPOUT(0x1800356D1LL);
    }
    catch ( const Microsoft::Basix::SystemException *v182 )
    {
      v141 = &v142;
      v130 = v141;
      v131 = (unsigned __int16 *)v141[93];
      v132 = std::operator==<char>(v131 + 56, "tcp(winsock)");
      v133 = v130 + 283;
      *(_OWORD *)(v130 + 283) = 0;
      v45 = v132 == 0;
      v134 = v131[12];
      if ( v45 )
      {
        *((_DWORD *)v130 + 25) = v134 | 0x8BB90000;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v133);
        v138 = v130[283];
        if ( v138 && *(_BYTE *)(v138 + 128) )
        {
          v139 = (*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v131 + 8LL))(v131);
          std::string::string(v130 + 26, "Exception in winsock layer: %s", v140);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,char const *>(
            v130 + 283,
            "RDPNANOSTREAM",
            v130 + 26,
            v139);
          std::string::_Tidy_deallocate(v130 + 26);
        }
      }
      else
      {
        *((_DWORD *)v130 + 25) = v134 | 0x8BBB0000;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v133);
        v135 = v130[283];
        if ( v135 && *(_BYTE *)(v135 + 128) )
        {
          v136 = (*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v131 + 8LL))(v131);
          std::string::string(v130 + 26, "Exception in TCP winsock layer: %s", v137);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,char const *>(
            v130 + 283,
            "RDPNANOSTREAM",
            v130 + 26,
            v136);
          std::string::_Tidy_deallocate(v130 + 26);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v130 + 283);
      v148 = v147;
      goto LABEL_109;
    }
    catch ( ... )
    {
      v147 = -1950744577;
      v148 = -1950744577;
LABEL_109:
      v32 = (volatile signed __int32 *)*((_QWORD *)&v161 + 1);
      v12 = v158[1];
      v92 = 4;
    }
  }
  __ExceptionPtrDestroy(v227);
  if ( !v146[0] )
  {
    v16 = v160;
LABEL_124:
    *(_OWORD *)v228 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v228);
    if ( *(_QWORD *)v228 && *(_BYTE *)(*(_QWORD *)v228 + 128LL) )
    {
      v105 = *v16;
      std::string::string(
        v156,
        "The UDP transport hasn't received any packets in the last %d ms due to network issues. closing UDP now ...",
        v102);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
        v228,
        "RDPNANOSTREAM",
        v156,
        v105);
      std::string::_Tidy_deallocate(v156);
    }
    goto LABEL_127;
  }
  v92 = 6;
  *(_OWORD *)v228 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v228);
  if ( *(_QWORD *)v228 && *(_BYTE *)(*(_QWORD *)v228 + 128LL) )
  {
    v103 = *v160;
    std::string::string(
      v156,
      "The UDP transport hasn't received any packets in the last %d ms due to turn server down. closing UDP now ...",
      v102);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
      v228,
      "RDPNANOSTREAM",
      v156,
      v103);
    std::string::_Tidy_deallocate(v156);
  }
LABEL_127:
  v106 = *(volatile signed __int32 **)&v228[2];
  if ( *(_QWORD *)&v228[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v228[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v106)(v106);
      if ( _InterlockedExchangeAdd(v106 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v106 + 8LL))(v106);
    }
  }
  v107 = *(_QWORD *)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(v101, v100, v102);
  v154 = 0;
  v155 = 0;
  std::string::_Construct<1,char const *>(&v154, "LinkSwitch", 10);
  Microsoft::Basix::Instrumentation::DelayedTraceManager::complete(v107, &v154, 0);
  std::string::_Tidy_deallocate(&v154);
  v111 = *(_QWORD *)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(v109, v108, v110);
  v154 = 0;
  v155 = 0;
  std::string::_Construct<1,char const *>(&v154, "OnWritableThread", 16);
  Microsoft::Basix::Instrumentation::DelayedTraceManager::complete(v111, &v154, 0);
  std::string::_Tidy_deallocate(&v154);
  v115 = (Microsoft::Basix::Instrumentation::DelayedTraceManager **)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(
                                                                      v113,
                                                                      v112,
                                                                      v114);
  Microsoft::Basix::Instrumentation::DelayedTraceManager::end(*v115);
  v116 = v170;
  *(_OWORD *)v227 = 0;
  v117 = v157;
  v118 = *v157;
  if ( *v157 )
  {
    v119 = *((_DWORD *)v118 + 2);
    while ( v119 )
    {
      v120 = v119;
      v119 = _InterlockedCompareExchange(v118 + 2, v119 + 1, v119);
      if ( v120 == v119 )
      {
        v121 = *v116;
        *(_QWORD *)v227 = *v116;
        v122 = *v117;
        *(_QWORD *)&v227[2] = v122;
        goto LABEL_136;
      }
    }
  }
  v121 = *(_QWORD *)v227;
  v122 = *(volatile signed __int32 **)&v227[2];
LABEL_136:
  if ( v121 )
    ClosingCallback::SetClosingReasonAndClose(v121, v92, v148);
  if ( v122 )
  {
    if ( _InterlockedExchangeAdd(v122 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *, volatile signed __int32 *, __int64 *))v122)(v122, v118, v116);
      if ( _InterlockedExchangeAdd(v122 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v122 + 8LL))(v122);
    }
  }
  if ( v32 )
  {
    if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *, volatile signed __int32 *, __int64 *))v32)(v32, v118, v116);
      if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
    }
  }
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(ClosingCallback *, volatile signed __int32 *, __int64 *))v12)(v12, v118, v116);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(ClosingCallback *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v123 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
  return (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, int *, _BYTE *))(*(_QWORD *)v123 + 32LL))(
           v123,
           v228,
           v231);
}

```

## disassembly

```asm
0x1800336f0  mov     [rsp+arg_8], rbx
0x1800336f5  mov     [rsp+arg_10], rsi
0x1800336fa  push    rdi
0x1800336fb  push    r12
0x1800336fd  push    r13
0x1800336ff  push    r14
0x180033701  push    r15
0x180033703  mov     eax, 920h
0x180033708  call    _alloca_probe
0x18003370d  sub     rsp, rax
0x180033710  mov     rax, cs:__security_cookie
0x180033717  xor     rax, rsp
0x18003371a  mov     [rsp+948h+var_30], rax
0x180033722  mov     r13, rcx
0x180033725  xor     r14d, r14d
0x180033728  mov     [rsp+948h+var_8E4], r14d
0x18003372d  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x180033732  lea     r8, [r13+0FCh]
0x180033739  lea     r15d, [r14+1]
0x18003373d  mov     r9b, r15b
0x180033740  lea     rdx, [rsp+948h+var_40]
0x180033748  mov     rcx, rax
0x18003374b  call    ?SetActivityId@ActivityManager@Instrumentation@Basix@Microsoft@@QEAA?AUGuid@34@AEBU534@_N@Z; Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(Microsoft::Basix::Guid const &,bool)
0x180033750  nop
0x180033751  lea     rcx, [r13+180h]
0x180033758  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18003375d  mov     cl, [rax]
0x18003375f  nop
0x180033760  test    cl, cl
0x180033762  jz      short loc_180033792
0x180033764  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x180033769  mov     r9, rax
0x18003376c  mov     rcx, [rax]
0x18003376f  mov     rax, [rcx+20h]
0x180033773  lea     r8, [rsp+948h+var_40]
0x18003377b  lea     rdx, [rsp+948h+var_70]
0x180033783  mov     rcx, r9
0x180033786  call    cs:__guard_dispatch_icall_fptr
0x18003378c  nop
0x18003378d  jmp     loc_180035571
0x180033792  mov     [rsp+948h+var_8E0], r14d
0x180033797  lea     r9, [r13+138h]
0x18003379e  mov     [rsp+948h+var_7A8], r9
0x1800337a6  xorps   xmm1, xmm1
0x1800337a9  movdqu  xmmword ptr [rsp+948h+var_850], xmm1
0x1800337b2  lea     rdx, [r9+8]
0x1800337b6  mov     [rsp+948h+var_858], rdx
0x1800337be  mov     r8, [rdx]
0x1800337c1  test    r8, r8
0x1800337c4  jz      short loc_1800337DF
0x1800337c6  mov     eax, [r8+8]
0x1800337ca  jmp     short loc_1800337DB
0x1800337cc  lea     ecx, [rax+1]
0x1800337cf  lock cmpxchg [r8+8], ecx
0x1800337d5  jz      loc_180033884
0x1800337db  test    eax, eax
0x1800337dd  jnz     short loc_1800337CC
0x1800337df  mov     rcx, [rsp+948h+var_850]; this
0x1800337e7  mov     r12, [rsp+948h+var_850+8]
0x1800337ef  test    rcx, rcx
0x1800337f2  jz      loc_18003389F
0x1800337f8  lea     rdx, [rsp+948h+var_8E0]; enum ClosingReason *
0x1800337fd  call    ?GetClosingReason@ClosingCallback@@QEAAXAEAW4ClosingReason@@@Z; ClosingCallback::GetClosingReason(ClosingReason &)
0x180033802  cmp     [rsp+948h+var_8E0], r14d
0x180033807  jz      loc_18003389F
0x18003380d  test    r12, r12
0x180033810  jz      short loc_180033856
0x180033812  or      r15d, 0FFFFFFFFh
0x180033816  mov     eax, r15d
0x180033819  lock xadd [r12+8], eax
0x180033820  add     eax, r15d
0x180033823  jnz     short loc_180033856
0x180033825  mov     rax, [r12]
0x180033829  mov     rcx, r12
0x18003382c  mov     rax, [rax]
0x18003382f  call    cs:__guard_dispatch_icall_fptr
0x180033835  mov     eax, r15d
0x180033838  lock xadd [r12+0Ch], eax
0x18003383f  add     eax, r15d
0x180033842  jnz     short loc_180033856
0x180033844  mov     rax, [r12]
0x180033848  mov     rcx, r12
0x18003384b  mov     rax, [rax+8]
0x18003384f  call    cs:__guard_dispatch_icall_fptr
0x180033855  nop
0x180033856  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x18003385b  mov     r9, rax
0x18003385e  mov     rcx, [rax]
0x180033861  mov     rax, [rcx+20h]
0x180033865  lea     r8, [rsp+948h+var_40]
0x18003386d  lea     rdx, [rsp+948h+var_70]
0x180033875  mov     rcx, r9
0x180033878  call    cs:__guard_dispatch_icall_fptr
0x18003387e  nop
0x18003387f  jmp     loc_180035571
0x180033884  mov     rcx, [r9]
0x180033887  mov     [rsp+948h+var_850], rcx
0x18003388f  mov     r12, [rdx]
0x180033892  mov     [rsp+948h+var_850+8], r12
0x18003389a  jmp     loc_1800337EF
0x18003389f  lea     rcx, [rsp+948h+var_8B0]
0x1800338a7  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800338ac  mov     rcx, rax
0x1800338af  lea     r8, [r13-440h]
0x1800338b6  mov     [rsp+948h+var_840], r8
0x1800338be  mov     rax, 431BDE82D7B634DBh
0x1800338c8  imul    qword ptr [rcx]
0x1800338cb  mov     rbx, rdx
0x1800338ce  sar     rbx, 12h
0x1800338d2  mov     rax, rbx
0x1800338d5  shr     rax, 3Fh
0x1800338d9  add     rbx, rax
0x1800338dc  sub     rbx, [r8+570h]
0x1800338e3  mov     [rsp+948h+var_8A0], rbx
0x1800338eb  lea     rsi, [r13+128h]
0x1800338f2  mov     [rsp+948h+var_838], rsi
0x1800338fa  mov     eax, [rsi]
0x1800338fc  sub     eax, 1F4h
0x180033901  cmp     rbx, rax
0x180033904  jnb     loc_180033DBD
0x18003390a  mov     rax, [r13-438h]
0x180033911  movsxd  rcx, dword ptr [rax+4]
0x180033915  add     rcx, 0FFFFFFFFFFFFFBC8h
0x18003391c  add     rcx, r13
0x18003391f  lea     rdx, [rsp+948h+var_70]
0x180033927  call    ??$GetSharedPtr@VITimerCallback@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$shared_ptr@VITimerCallback@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::ITimerCallback>(void)
0x18003392c  nop
0x18003392d  xorps   xmm0, xmm0
0x180033930  movdqu  xmmword ptr [rsp+948h+var_80], xmm0
0x180033939  cmp     [rax+8], r14
0x18003393d  jz      short loc_18003395B
0x18003393f  mov     rdx, [rax]
0x180033942  mov     qword ptr [rsp+948h+var_80], rdx
0x18003394a  mov     rax, [rax+8]
0x18003394e  mov     qword ptr [rsp+948h+var_80+8], rax
0x180033956  lock add [rax+0Ch], r15d
0x18003395b  mov     eax, [rsi]
0x18003395d  shr     rax, 2
0x180033961  mov     [rsp+948h+var_838], rax
0x180033969  lea     r8, [rsp+948h+var_80]
0x180033971  lea     rdx, [rsp+948h+var_838]
0x180033979  lea     rcx, [r13+110h]
0x180033980  call    ?Setup@Timer@Basix@Microsoft@@QEAAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@V?$weak_ptr@VITimerCallback@Basix@Microsoft@@@6@@Z; Microsoft::Basix::Timer::Setup(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::weak_ptr<Microsoft::Basix::ITimerCallback>)
0x180033985  nop
0x180033986  mov     rdi, qword ptr [rsp+948h+var_70+8]
0x18003398e  or      r15d, 0FFFFFFFFh
0x180033992  test    rdi, rdi
0x180033995  jz      short loc_1800339D0
0x180033997  mov     eax, r15d
0x18003399a  lock xadd [rdi+8], eax
0x18003399f  add     eax, r15d
0x1800339a2  jnz     short loc_1800339D0
0x1800339a4  mov     rax, [rdi]
0x1800339a7  mov     rcx, rdi
0x1800339aa  mov     rax, [rax]
0x1800339ad  call    cs:__guard_dispatch_icall_fptr
0x1800339b3  mov     eax, r15d
0x1800339b6  lock xadd [rdi+0Ch], eax
0x1800339bb  add     eax, r15d
0x1800339be  jnz     short loc_1800339D0
0x1800339c0  mov     rax, [rdi]
0x1800339c3  mov     rcx, rdi
0x1800339c6  mov     rax, [rax+8]
0x1800339ca  call    cs:__guard_dispatch_icall_fptr
0x1800339d0  xorps   xmm0, xmm0
0x1800339d3  movups  xmmword ptr [rsp+948h+var_80], xmm0
0x1800339db  lea     rcx, [rsp+948h+var_80]
0x1800339e3  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1800339e8  nop
0x1800339e9  mov     rax, qword ptr [rsp+948h+var_80]
0x1800339f1  test    rax, rax
0x1800339f4  jz      short loc_180033A53
0x1800339f6  cmp     [rax+80h], r14b
0x1800339fd  jz      short loc_180033A53
0x1800339ff  xorps   xmm0, xmm0
0x180033a02  movups  [rsp+948h+var_8D8], xmm0
0x180033a07  xorps   xmm1, xmm1
0x180033a0a  movdqu  [rsp+948h+var_8C8], xmm1
0x180033a13  mov     r8d, 40h ; '@'
0x180033a19  lea     rdx, aTheControllerH_4; "The controller hasn't received any pack"...
0x180033a20  lea     rcx, [rsp+948h+var_8D8]
0x180033a25  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180033a2a  nop
0x180033a2b  mov     r9, rbx
0x180033a2e  lea     r8, [rsp+948h+var_8D8]
0x180033a33  lea     rdx, aRdpnanostream; "RDPNANOSTREAM"
0x180033a3a  lea     rcx, [rsp+948h+var_80]
0x180033a42  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@_K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@_K@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned __int64>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,unsigned __int64)
0x180033a47  nop
0x180033a48  lea     rcx, [rsp+948h+var_8D8]
0x180033a4d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180033a52  nop
0x180033a53  mov     rdi, qword ptr [rsp+948h+var_80+8]
0x180033a5b  test    rdi, rdi
0x180033a5e  jz      short loc_180033A99
0x180033a60  mov     eax, r15d
0x180033a63  lock xadd [rdi+8], eax
0x180033a68  add     eax, r15d
0x180033a6b  jnz     short loc_180033A99
0x180033a6d  mov     rax, [rdi]
0x180033a70  mov     rcx, rdi
0x180033a73  mov     rax, [rax]
0x180033a76  call    cs:__guard_dispatch_icall_fptr
0x180033a7c  mov     eax, r15d
0x180033a7f  lock xadd [rdi+0Ch], eax
0x180033a84  add     eax, r15d
0x180033a87  jnz     short loc_180033A99
0x180033a89  mov     rax, [rdi]
0x180033a8c  mov     rcx, rdi
0x180033a8f  mov     rax, [rax+8]
0x180033a93  call    cs:__guard_dispatch_icall_fptr
0x180033a99  xorps   xmm0, xmm0
0x180033a9c  movups  xmmword ptr [rsp+948h+var_80], xmm0
0x180033aa4  lea     rcx, [rsp+948h+var_80]
0x180033aac  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x180033ab1  nop
0x180033ab2  mov     rax, qword ptr [rsp+948h+var_80]
0x180033aba  test    rax, rax
0x180033abd  jz      loc_180033C8A
0x180033ac3  cmp     [rax+80h], r14b
0x180033aca  jz      loc_180033C8A
0x180033ad0  mov     rdx, rbx
0x180033ad3  lea     rcx, [rsp+948h+var_7C8]
0x180033adb  call    ??$_Integral_to_string@D_K@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@_K@Z; std::_Integral_to_string<char,unsigned __int64>(unsigned __int64)
0x180033ae0  nop
0x180033ae1  xorps   xmm0, xmm0
0x180033ae4  movups  xmmword ptr [rsp+948h+var_70], xmm0
0x180033aec  xorps   xmm1, xmm1
0x180033aef  movdqu  [rsp+948h+var_60], xmm1
0x180033af8  mov     ebx, 1
0x180033afd  mov     r8d, ebx
0x180033b00  lea     rdx, asc_1803D71C4; ":"
0x180033b07  lea     rcx, [rsp+948h+var_70]
0x180033b0f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180033b14  nop
0x180033b15  xorps   xmm0, xmm0
0x180033b18  movups  [rsp+948h+var_7E8], xmm0
0x180033b20  xorps   xmm1, xmm1
0x180033b23  movdqu  [rsp+948h+var_7D8], xmm1
0x180033b2c  mov     r8d, ebx
0x180033b2f  lea     rdx, asc_1803D71C8; "\""
0x180033b36  lea     rcx, [rsp+948h+var_7E8]
0x180033b3e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180033b43  nop
0x180033b44  xorps   xmm0, xmm0
0x180033b47  movups  [rsp+948h+var_8D8], xmm0
0x180033b4c  xorps   xmm1, xmm1
0x180033b4f  movdqu  [rsp+948h+var_8C8], xmm1
0x180033b58  mov     r8d, ebx
0x180033b5b  lea     rdx, asc_1803D71C8; "\""
0x180033b62  lea     rcx, [rsp+948h+var_8D8]
0x180033b67  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180033b6c  nop
0x180033b6d  lea     r8, aTimegap; "timegap"
0x180033b74  lea     rdx, [rsp+948h+var_8D8]
0x180033b79  lea     rcx, [rsp+948h+var_878]
0x180033b81  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180033b86  nop
0x180033b87  lea     r9, [rsp+948h+var_7E8]
0x180033b8f  mov     r8, rax
0x180033b92  mov     dl, [rsp+948h+var_8E8]
0x180033b96  lea     rcx, [rsp+948h+var_820]
0x180033b9e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180033ba3  nop
0x180033ba4  lea     r9, [rsp+948h+var_70]
0x180033bac  lea     r8, [rsp+948h+var_820]
0x180033bb4  mov     dl, [rsp+948h+var_8E8]
0x180033bb8  lea     rcx, [rsp+948h+var_898]
0x180033bc0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180033bc5  nop
0x180033bc6  lea     r9, [rsp+948h+var_7C8]
0x180033bce  lea     r8, [rsp+948h+var_898]
0x180033bd6  mov     dl, [rsp+948h+var_8E8]
0x180033bda  lea     rcx, [rsp+948h+var_7A0]
0x180033be2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180033be7  lea     rax, [rsp+948h+var_7A0]
0x180033bef  mov     [rsp+948h+var_918], rax; __int64
0x180033bf4  lea     rax, aTheControllerH_5; "The controller hasn't received any pack"...
0x180033bfb  mov     [rsp+948h+Str], rax; Str
0x180033c00  lea     rax, aNetworkdrop; "NetworkDrop"
0x180033c07  mov     [rsp+948h+var_928], rax; char *
0x180033c0c  lea     r9, aUdptransport; "UDPTransport"
0x180033c13  xor     r8d, r8d; int
0x180033c16  lea     rdx, aRdCheckpoint; "RD_CHECKPOINT"
0x180033c1d  lea     rcx, [rsp+948h+var_80]; int
0x180033c25  call    ??$TraceCheckpointMessage@VTraceCheckpoint@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDI111V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,char const *,uint,char const *,char const *,char const *,std::string)
0x180033c2a  nop
0x180033c2b  lea     rcx, [rsp+948h+var_898]
0x180033c33  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180033c38  nop
0x180033c39  lea     rcx, [rsp+948h+var_820]
0x180033c41  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180033c46  nop
0x180033c47  lea     rcx, [rsp+948h+var_878]
0x180033c4f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180033c54  nop
0x180033c55  lea     rcx, [rsp+948h+var_8D8]
0x180033c5a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180033c5f  nop
0x180033c60  lea     rcx, [rsp+948h+var_7E8]
  ... truncated ...
```

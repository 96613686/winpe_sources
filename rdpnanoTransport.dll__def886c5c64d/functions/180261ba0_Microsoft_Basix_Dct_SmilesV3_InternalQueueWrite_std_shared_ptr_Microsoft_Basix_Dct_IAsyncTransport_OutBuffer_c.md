# Microsoft::Basix::Dct::SmilesV3::InternalQueueWrite(std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::OutBuffer> const &)

- ea: `0x180261ba0`
- end: `0x180264167`
- name: `?InternalQueueWrite@SmilesV3@Dct@Basix@Microsoft@@EEAAXAEBV?$shared_ptr@VOutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@Z`
- size: `9671`
- prototype: ``
- caller_count: `0`
- callee_count: `60`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180008f80`
- `0x18000d9c0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x180018d1c`
- `0x18001902c`
- `0x1800191b4`
- `0x18001955c`
- `0x18001979c`
- `0x18001acb8`
- `0x18001bbdc`
- `0x18001dad8`
- `0x180024700`
- `0x180024760`
- `0x180028100`
- `0x18002a8f4`
- `0x18003c308`
- `0x18003da74`
- `0x18003f0f4`
- `0x18004e1dc`
- `0x1800bb210`
- `0x1800d621c`
- `0x1801483c0`
- `0x18015b234`
- `0x1801acb74`
- `0x1801ad7b4`
- `0x1801b408c`
- `0x1802474f0`
- `0x18024b19c`
- `0x18024e418`
- `0x18024e5dc`
- `0x18024ed58`
- `0x18024eee4`
- `0x180251e30`
- `0x1802571d0`
- `0x180259f24`
- `0x180261ba0`
- `0x180264168`
- `0x18027b390`
- `0x18027c814`
- `0x18027e690`
- `0x18027f490`
- `0x18027f628`
- `0x1802ec708`
- `0x1802ecaac`
- `0x1802ed49c`
- `0x1802ed54c`
- `0x1802ee5e0`

## string_xrefs

- `0x180262328`: `OnWritableThread`
- `0x1802634fa`: `OnWritableThread`
- `0x180263ac5`: `OnWritableThread`
- `0x180261c52`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x180261f47`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x180262564`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x180262bd7`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x1802631c2`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x1802636c6`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x180263e0f`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x180261bfc`: `TestPrimaryOutLinkNull`
- `0x1802620b6`: `TestPrimaryOutLinkNull`
- `0x1802626d3`: `TestPrimaryOutLinkNull`
- `0x180262d81`: `TestPrimaryOutLinkNull`
- `0x18026335a`: `TestPrimaryOutLinkNull`
- `0x180263861`: `TestPrimaryOutLinkNull`
- `0x180263fa3`: `TestPrimaryOutLinkNull`
- `0x1802621e8`: `SmilesV3::InternalQueueWrite: m_lastSentInMs=%x, now=%x, m_cntSendsInLastNMs[0]=%d,  m_cntSendsInLastNMs[1]=%d, m_cntSendsInLastNMs[2]=%d, m_cntSendsInLastNMs[3]=%d`
- `0x18026236f`: `smilesV3:InternalQueueWrite: NO primaryLink and drop`
- `0x1802623e4`: `SmilesV3: there is no m_primaryOutLink for sending, drop it`
- `0x18026248b`: `no out primary link`
- `0x180262497`: `QueueWrite`
- `0x180262afa`: `SmilesV3::InternalQueueWrite: m_nextSecondaryLinkFireTime=%d, currenttime=%d`
- `0x180262f9e`: `Initial primaryOutLink on QueueWrite`
- `0x180263085`: `linkSwitch`
- `0x180263546`: `smilesV3:InternalQueueWrite: send on primary link`
- `0x180263966`: `SmilesV3: QueueWrite on primary link(%d) a packet(size=%d) with counter(%d), runningClockInMs(%d), sendTimeInMs(%llu)`
- `0x180263b1c`: `smilesV3:InternalQueueWrite: send on secondary link`
- `0x180263c82`: `SmilesV3: QueueWrite on secondary link(%d) a packet(size=%d) with counter(%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=105
__int64 __fastcall Microsoft::Basix::Dct::SmilesV3::InternalQueueWrite(
        __int64 a1,
        Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **a2)
{
  int v3; // r14d
  int v4; // r8d
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned __int64 v12; // rsi
  __int64 v13; // rdi
  struct _Mtx_internal_imp_t *v14; // rbx
  _DWORD *v15; // r15
  int i; // ecx
  int v17; // r8d
  volatile signed __int32 *v18; // rdi
  __int64 v19; // rsi
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25; // r14d
  __int64 v26; // rdx
  volatile signed __int32 *v27; // rdi
  int v28; // r9d
  __int16 v29; // di
  __int16 v30; // si
  __int16 v31; // r14
  __int16 v32; // r15
  __int64 v33; // r12
  volatile signed __int32 *v34; // rdi
  char v35; // al
  volatile signed __int32 *v36; // r12
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rdi
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **DelayedTraceRecord; // rsi
  int j; // edi
  char *Buffer; // rax
  int v44; // eax
  volatile signed __int32 *v45; // rdi
  volatile signed __int32 *v46; // rdi
  volatile signed __int32 *v47; // rdi
  int v48; // r8d
  volatile signed __int32 *v49; // rdi
  __int64 v50; // rsi
  __int64 v51; // rdi
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rdx
  volatile signed __int32 *v57; // rdi
  int v58; // esi
  Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **v59; // r12
  void **v60; // r14
  _QWORD **v61; // rcx
  __int64 v62; // rdi
  __int64 v63; // rax
  Microsoft::Basix::Containers::FlexOBuffer *v64; // rax
  unsigned __int64 v65; // rdi
  struct Microsoft::Basix::Containers::FlexOBuffer *v66; // rax
  __int64 v67; // rax
  __int128 *v68; // rax
  __int128 v69; // xmm6
  Microsoft::Basix::Containers::FlexOBuffer *v70; // rax
  volatile signed __int32 *v71; // rax
  size_t v72; // rcx
  volatile signed __int32 *v73; // rdi
  volatile signed __int32 *v74; // rdi
  volatile signed __int32 *v75; // rdi
  __int64 v76; // rcx
  double v77; // xmm0_8
  __int64 v78; // rax
  double v79; // xmm0_8
  unsigned __int64 v80; // rcx
  char v81; // r14
  int v82; // r9d
  __int64 v83; // rdi
  volatile signed __int32 *v84; // rdi
  volatile signed __int32 *v85; // rdi
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rdx
  int v89; // esi
  __int64 v90; // rdx
  volatile signed __int32 *v91; // rdi
  _WORD *v92; // rax
  __int64 v93; // rcx
  __int16 v94; // dx
  __int64 v95; // rdi
  __int64 v97; // r14
  __m128i si128; // xmm7
  const struct std::nothrow_t *v99; // rdx
  int v100; // ecx
  __int128 *v101; // rax
  double v102; // xmm0_8
  int v103; // r15d
  volatile signed __int32 *v104; // rbx
  __int64 v105; // rax
  __int64 v106; // rdx
  __int64 v107; // rdx
  __int64 v108; // rdx
  volatile signed __int32 *v109; // rbx
  Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **v110; // rbx
  Microsoft::Basix::Containers::FlexOBuffer *v111; // rax
  double v112; // xmm0_8
  char v113; // si
  bool IsOpened; // al
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // r8
  int v118; // r9d
  __int64 v119; // rbx
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **v120; // r15
  int k; // ebx
  char *v122; // rax
  int v123; // eax
  Microsoft::Basix::Dct::IAsyncTransport::OutBuffer *v124; // rax
  volatile signed __int32 *v125; // rbx
  __int64 v126; // rax
  __int64 v127; // rdx
  __int64 v128; // rdx
  __int64 v129; // rdx
  volatile signed __int32 *v130; // rbx
  int v131; // r9d
  int v132; // ebx
  volatile signed __int32 *v133; // rbx
  volatile signed __int32 **v134; // r15
  __int64 v135; // r12
  volatile signed __int32 *v136; // r14
  char v137; // bl
  volatile signed __int32 *v138; // rax
  volatile signed __int32 *v139; // rsi
  __int64 v140; // rdx
  __int64 v141; // rcx
  __int64 v142; // r8
  int v143; // r9d
  __int64 v144; // rbx
  _QWORD *v145; // rbx
  int v146; // ebx
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **v147; // r12
  char *v148; // rax
  int v149; // eax
  int v150; // r9d
  int v151; // ebx
  volatile signed __int32 *v152; // rbx
  volatile signed __int32 *v153; // rbx
  __int64 v154; // rax
  __int64 v155; // rdx
  __int64 v156; // rdx
  __int64 v157; // rdx
  volatile signed __int32 *v158; // rbx
  __int64 result; // rax
  int v160; // [rsp+20h] [rbp-E0h]
  int v161; // [rsp+20h] [rbp-E0h]
  int Str; // [rsp+28h] [rbp-D8h]
  __int64 v163; // [rsp+30h] [rbp-D0h]
  int v164; // [rsp+38h] [rbp-C8h]
  char v165; // [rsp+38h] [rbp-C8h]
  char v166; // [rsp+50h] [rbp-B0h]
  bool v167; // [rsp+50h] [rbp-B0h]
  __int16 v168; // [rsp+51h] [rbp-AFh]
  int v169[3]; // [rsp+54h] [rbp-ACh] BYREF
  _OWORD pExceptionObject[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v171; // [rsp+80h] [rbp-80h]
  void *v172[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v173; // [rsp+A0h] [rbp-60h]
  __int64 v174[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v175; // [rsp+C0h] [rbp-40h]
  __int64 v176; // [rsp+D0h] [rbp-30h]
  Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **v177; // [rsp+E0h] [rbp-20h]
  _OWORD v178[2]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v179; // [rsp+110h] [rbp+10h] BYREF
  __int64 v180[4]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v181[16]; // [rsp+138h] [rbp+38h] BYREF
  __int128 v182; // [rsp+148h] [rbp+48h]
  size_t v183[2]; // [rsp+158h] [rbp+58h] BYREF
  size_t BufferCount[3]; // [rsp+178h] [rbp+78h] BYREF
  _OWORD v185[2]; // [rsp+190h] [rbp+90h] BYREF
  int v186[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v187[24]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int16 v188; // [rsp+1D8h] [rbp+D8h]
  __int128 v189; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v190; // [rsp+1F0h] [rbp+F0h]
  __int128 v191; // [rsp+200h] [rbp+100h] BYREF
  __int128 v192; // [rsp+210h] [rbp+110h]
  __int128 v193; // [rsp+220h] [rbp+120h] BYREF
  __int64 v194; // [rsp+230h] [rbp+130h]

  v177 = a2;
  v3 = 0;
  v169[0] = 0;
  LODWORD(v176) = 0;
  if ( *(_BYTE *)(a1 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(a1 + 1816),
                          0) )
  {
    *(_OWORD *)v186 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v186);
    if ( *(_QWORD *)v186 && *(_BYTE *)(*(_QWORD *)v186 + 128LL) )
    {
      std::string::string(v174, "SmilesV3: Location %d m_primaryOutLink == nullptr", v4);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        v186,
        "BASIX_DCT",
        v174,
        0);
      std::string::_Tidy_deallocate(v174);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v186);
    *(_OWORD *)v186 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v186);
    if ( *(_QWORD *)v186 && *(_BYTE *)(*(_QWORD *)v186 + 128LL) )
    {
      std::_Integral_to_string<char,int>(v172, 0);
      v5 = std::string::string(v185, ":");
      v6 = std::string::string(v178, "\"");
      v7 = std::string::string(&v189, "\"");
      v8 = std::operator+<char>(v180, v7, "Location");
      LOBYTE(v9) = v166;
      std::string::string(pExceptionObject, v9, v8, v6);
      LOBYTE(v10) = v166;
      std::string::string(&v191, v10, pExceptionObject, v5);
      LOBYTE(v11) = v166;
      std::string::string(v174, v11, &v191, v172);
      v3 = -268435456;
      v169[0] = -268435456;
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v186,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)v174);
      std::string::_Tidy_deallocate(&v191);
      std::string::_Tidy_deallocate(pExceptionObject);
      std::string::_Tidy_deallocate(v180);
      std::string::_Tidy_deallocate(&v189);
      std::string::_Tidy_deallocate(v178);
      std::string::_Tidy_deallocate(v185);
      std::string::_Tidy_deallocate(v172);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v186);
  }
  v12 = *(_QWORD *)std::chrono::steady_clock::now(v185) / 1000000LL - *(_QWORD *)(a1 + 3008);
  BufferCount[0] = v12;
  *(_OWORD *)v186 = 0;
  v193 = 0;
  v194 = 0;
  v13 = *(_QWORD *)(a1 + 2880);
  v171 = 0;
  v191 = 0;
  v192 = 0;
  pExceptionObject[0] = 0;
  Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(&v191, 0, 0, pExceptionObject);
  v14 = (struct _Mtx_internal_imp_t *)(a1 + 1832);
  *(_QWORD *)&v185[0] = a1 + 1832;
  if ( Mtx_lock((_Mtx_t)(a1 + 1832)) )
    goto LABEL_284;
  v15 = (_DWORD *)(a1 + 1908);
  if ( *(_DWORD *)(a1 + 1908) == 0x7FFFFFFF )
    goto LABEL_285;
  for ( i = 0; i < 4; ++i )
  {
    if ( v13 == v12 )
    {
      ++*(_WORD *)(a1 + 2 * (v13 & 3) + 2888);
      goto LABEL_18;
    }
    *(_WORD *)(a1 + 2 * (++v13 & 3) + 2888) = 0;
  }
  if ( i == 4 )
    ++*(_WORD *)(a1 + 2 * (v12 & 3) + 2888);
LABEL_18:
  if ( *(_BYTE *)(a1 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(a1 + 1816),
                          0) )
  {
    *(_OWORD *)v183 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v183);
    if ( v183[0] && *(_BYTE *)(v183[0] + 128) )
    {
      std::string::string(v174, "SmilesV3: Location %d m_primaryOutLink == nullptr", v17);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        v183,
        "BASIX_DCT",
        v174,
        1);
      std::string::_Tidy_deallocate(v174);
    }
    v18 = (volatile signed __int32 *)v183[1];
    if ( v183[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v183[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    *(_OWORD *)v187 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v187);
    if ( *(_QWORD *)v187 && *(_BYTE *)(*(_QWORD *)v187 + 128LL) )
    {
      std::_Integral_to_string<char,int>(&v189, 1);
      v19 = std::string::string(v181, ":");
      v20 = std::string::string(v183, "\"");
      v21 = std::string::string(v178, "\"");
      v22 = std::operator+<char>(v180, v21, "Location");
      LOBYTE(v23) = v166;
      std::string::string(v172, v23, v22, v20);
      LOBYTE(v24) = v166;
      std::string::string(pExceptionObject, v24, v172, v19);
      v25 = v3 | 0xD00000;
      LODWORD(v176) = v25;
      LOBYTE(v26) = v166;
      std::string::string(v174, v26, pExceptionObject, &v189);
      v169[0] = v25 | 0x200000;
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v187,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)v174);
      std::string::_Tidy_deallocate(pExceptionObject);
      std::string::_Tidy_deallocate(v172);
      std::string::_Tidy_deallocate(v180);
      std::string::_Tidy_deallocate(v178);
      std::string::_Tidy_deallocate(v183);
      std::string::_Tidy_deallocate(v181);
      std::string::_Tidy_deallocate(&v189);
      v12 = BufferCount[0];
    }
    v27 = *(volatile signed __int32 **)&v187[8];
    if ( *(_QWORD *)&v187[8] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v187[8] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
        if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
  }
  *(_OWORD *)v183 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v183);
  if ( v183[0] && *(_BYTE *)(v183[0] + 128) )
  {
    v29 = *(_WORD *)(a1 + 2894);
    v30 = *(_WORD *)(a1 + 2892);
    v31 = *(_WORD *)(a1 + 2890);
    v32 = *(_WORD *)(a1 + 2888);
    v33 = *(_QWORD *)(a1 + 2880);
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    std::string::_Construct<1,char const *>(
      pExceptionObject,
      "SmilesV3::InternalQueueWrite: m_lastSentInMs=%x, now=%x, m_cntSendsInLastNMs[0]=%d,  m_cntSendsInLastNMs[1]=%d, m_"
      "cntSendsInLastNMs[2]=%d, m_cntSendsInLastNMs[3]=%d",
      164,
      v28,
      v160,
      Str,
      v163,
      v164);
    v165 = v30;
    v12 = BufferCount[0];
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64,unsigned __int64,unsigned short,unsigned short,unsigned short,unsigned short>(
      (unsigned int)v183,
      (unsigned int)"BASIX_DCT",
      (unsigned int)pExceptionObject,
      v33,
      BufferCount[0],
      v32,
      v31,
      v165,
      v29);
    std::string::_Tidy_deallocate(pExceptionObject);
    v15 = (_DWORD *)(a1 + 1908);
  }
  v34 = (volatile signed __int32 *)v183[1];
  if ( v183[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v183[1] + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
      if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
    }
  }
  *(_QWORD *)(a1 + 2880) = v12;
  Mtx_unlock((_Mtx_t)(a1 + 1832));
  *(_QWORD *)&v185[0] = a1 + 1832;
  if ( Mtx_lock((_Mtx_t)(a1 + 1832)) )
LABEL_284:
    std::_Throw_Cpp_error(5);
  if ( *v15 == 0x7FFFFFFF )
  {
LABEL_285:
    *v15 = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v167 = Microsoft::Basix::Dct::SmilesV3::SetInitialPrimaryOutLink((Microsoft::Basix::Dct::SmilesV3 *)a1);
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(v186, *(_QWORD *)(a1 + 1816));
  v35 = std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(v186, 0);
  v36 = *(volatile signed __int32 **)&v186[2];
  if ( v35 )
  {
    if ( *(_BYTE *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v177) == 104 )
    {
      v40 = *(_QWORD *)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(v38, v37, v39);
      memset(pExceptionObject, 0, sizeof(pExceptionObject));
      std::string::_Construct<1,char const *>(pExceptionObject, "OnWritableThread", 16);
      DelayedTraceRecord = (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(v40, pExceptionObject, 0);
      std::string::_Tidy_deallocate(pExceptionObject);
      if ( *DelayedTraceRecord )
      {
        BufferCount[0] = 0;
        for ( j = 0; j < 2; ++j )
        {
          Buffer = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(
                     *DelayedTraceRecord,
                     BufferCount);
          v44 = snprintf(Buffer, BufferCount[0], "smilesV3:InternalQueueWrite: NO primaryLink and drop");
          if ( v44 < BufferCount[0] )
            break;
          BufferCount[0] = v44;
        }
        Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(
          *DelayedTraceRecord,
          4,
          "BASIX_DCT");
      }
    }
    *(_OWORD *)BufferCount = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(BufferCount);
    if ( BufferCount[0] && *(_BYTE *)(BufferCount[0] + 128) )
    {
      memset(pExceptionObject, 0, sizeof(pExceptionObject));
      std::string::_Construct<1,char const *>(
        pExceptionObject,
        "SmilesV3: there is no m_primaryOutLink for sending, drop it",
        59);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
        BufferCount,
        "BASIX_DCT",
        pExceptionObject);
      std::string::_Tidy_deallocate(pExceptionObject);
    }
    v45 = (volatile signed __int32 *)BufferCount[1];
    if ( BufferCount[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(BufferCount[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
    *(_OWORD *)BufferCount = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(BufferCount);
    if ( BufferCount[0] && *(_BYTE *)(BufferCount[0] + 128) )
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,char const *>(
        (int)BufferCount,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "QueueWrite",
        "no out primary link",
        (__int64)&Str1);
    v46 = (volatile signed __int32 *)BufferCount[1];
    if ( BufferCount[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(BufferCount[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
        if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
      }
    }
    Mtx_unlock((_Mtx_t)(a1 + 1832));
    v47 = (volatile signed __int32 *)v192;
  }
  else
  {
    if ( *(_BYTE *)(a1 + 1524)
      && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                            *(_QWORD *)(a1 + 1816),
                            0) )
    {
      *(_OWORD *)v183 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v183);
      if ( v183[0] && *(_BYTE *)(v183[0] + 128) )
      {
        std::string::string(v174, "SmilesV3: Location %d m_primaryOutLink == nullptr", v48);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
          v183,
          "BASIX_DCT",
          v174,
          2);
        std::string::_Tidy_deallocate(v174);
      }
      v49 = (volatile signed __int32 *)v183[1];
      if ( v183[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v183[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
          if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
        }
      }
      *(_OWORD *)v187 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v187);
      if ( *(_QWORD *)v187 && *(_BYTE *)(*(_QWORD *)v187 + 128LL) )
      {
        std::_Integral_to_string<char,int>(&v189, 2);
        v50 = std::string::string(v183, ":");
        v51 = std::string::string(v178, "\"");
        v52 = std::string::string(v180, "\"");
        v53 = std::operator+<char>(v181, v52, "Location");
        LOBYTE(v54) = v167;
        std::string::string(v172, v54, v53, v51);
        LOBYTE(v55) = v167;
        std::string::string(pExceptionObject, v55, v172, v50);
        LODWORD(v176) = v169[0] | 0x7000000;
        LOBYTE(v56) = v167;
        std::string::string(v174, v56, pExceptionObject, &v189);
        v169[0] |= 0xF000000u;
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
          (int)v187,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "TestPrimaryOutLinkNull",
          "TestPrimaryOutLinkNull",
          (__int64)v174);
        std::string::_Tidy_deallocate(pExceptionObject);
        std::string::_Tidy_deallocate(v172);
        std::string::_Tidy_deallocate(v181);
        std::string::_Tidy_deallocate(v180);
        std::string::_Tidy_deallocate(v178);
        std::string::_Tidy_deallocate(v183);
        std::string::_Tidy_deallocate(&v189);
        v12 = BufferCount[0];
      }
      v57 = *(volatile signed __int32 **)&v187[8];
      if ( *(_QWORD *)&v187[8] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v187[8] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
          if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
        }
      }
    }
    if ( v12 > *(_QWORD *)(a1 + 2936)
      || *(_BYTE *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v177) + 131) )
    {
      *(_OWORD *)v187 = 0;
      Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
        v187,
        a1 + 1528);
      pExceptionObject[0] = 0;
      v58 = v169[0] | 0xC000;
      v59 = v177;
      while ( *(_QWORD *)v187 )
      {
        v60 = *(void ***)&v187[8];
        if ( (unsigned __int8)std::operator!=<Microsoft::Basix::Dct::LinkDataV3,Microsoft::Basix::Dct::LinkDataV3>(
                                *(_QWORD *)&v187[8],
                                v186) )
        {
          if ( Microsoft::Basix::Dct::detail::BasicStateManagement::IsOpened(*((Microsoft::Basix::Dct::detail::BasicStateManagement **)*v60
                                                                             + 13)) )
          {
            v61 = (_QWORD **)*v60;
            if ( *((_DWORD *)*v60 + 71) != 2 )
            {
              *(_OWORD *)v183 = 0;
              (*(void (__fastcall **)(_QWORD *, size_t *))(*v61[13] + 80LL))(v61[13], v183);
              v62 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v59);
              v63 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(v183[0]);
              Microsoft::Basix::Dct::IAsyncTransport::OutDescriptor::operator=(v63, v62);
              v64 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*v59);
              v65 = Microsoft::Basix::Containers::FlexOBuffer::Size(v64);
              v66 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO((Microsoft::Basix::Dct::IAsyncTransport::OutBuffer *)v183[0]);
              v67 = Microsoft::Basix::Containers::FlexOBuffer::Begin(v66, v172);
              v68 = (__int128 *)Microsoft::Basix::Containers::FlexOBuffer::Iterator::ReserveBlob(v67, v181, v65);
              v69 = *v68;
              v182 = v68[1];
              v70 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*v59);
              Microsoft::Basix::Containers::FlexOBuffer::Flatten(v70, (unsigned __int8 *)v69);
              v71 = (volatile signed __int32 *)v60[1];
              if ( v71 )
                _InterlockedAdd(v71 + 2, 1u);
              v172[0] = *v60;
              v172[1] = v60[1];
              v72 = v183[1];
              if ( v183[1] )
              {
                _InterlockedAdd((volatile signed __int32 *)(v183[1] + 8), 1u);
                v72 = v183[1];
              }
              *(_QWORD *)&v173 = v183[0];
              *((_QWORD *)&v173 + 1) = v72;
              std::vector<std::pair<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::OutBuffer>>>::_Emplace_one_at_back<std::pair<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::OutBuffer>>>(
                &v193,
                v172);
              v73 = (volatile signed __int32 *)*((_QWORD *)&v173 + 1);
              if ( *((_QWORD *)&v173 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v173 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v73)(v73);
                  if ( _InterlockedExchangeAdd(v73 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v73 + 8LL))(v73);
                }
              }
              v74 = (volatile signed __int32 *)v172[1];
              if ( v172[1] )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v172[1] + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
                  if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
                }
              }
              v75 = (volatile signed __int32 *)v183[1];
              if ( v183[1] )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v183[1] + 8), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
                  if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
                }
              }
            }
          }
        }
        Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(v187);
      }
      v14 = (struct _Mtx_internal_imp_t *)(a1 + 1832);
      v36 = *(volatile signed __int32 **)&v186[2];
      v76 = *(_QWORD *)(a1 + 2928);
      if ( v76 < 0 )
      {
        v78 = *(_QWORD *)(a1 + 2928) & 1LL | ((unsigned __int64)v76 >> 1);
        v77 = (double)(int)v78 + (double)(int)v78;
      }
      else
      {
        v77 = (double)(int)v76;
      }
      v79 = v77 * 0.98;
      v80 = 0;
      if ( v79 >= 9.223372036854776e18 )
      {
        v79 = v79 - 9.223372036854776e18;
        if ( v79 < 9.223372036854776e18 )
          v80 = 0x8000000000000000uLL;
      }
      v81 = BufferCount[0];
      *(_QWORD *)(a1 + 2936) = BufferCount[0] + v80 + (unsigned int)(int)v79;
      if ( *(_BYTE *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v177) + 131) )
        *(_QWORD *)(a1 + 2936) += 100LL;
      *(_OWORD *)v183 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v183);
      if ( v183[0] && *(_BYTE *)(v183[0] + 128) )
      {
        v83 = *(_QWORD *)(a1 + 2936);
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        std::string::_Construct<1,char const *>(
          pExceptionObject,
          "SmilesV3::InternalQueueWrite: m_nextSecondaryLinkFireTime=%d, currenttime=%d",
          76,
          v82);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64,unsigned __int64>(
          (unsigned int)v183,
          (unsigned int)"BASIX_DCT",
          (unsigned int)pExceptionObject,
          v83,
          v81);
        std::string::_Tidy_deallocate(pExceptionObject);
      }
      v84 = (volatile signed __int32 *)v183[1];
      if ( v183[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v183[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v84)(v84);
          if ( _InterlockedExchangeAdd(v84 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v84 + 8LL))(v84);
        }
      }
      if ( *(_BYTE *)(a1 + 1524)
        && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                              *(_QWORD *)(a1 + 1816),
                              0) )
      {
        *(_OWORD *)v183 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v183);
        if ( v183[0] && *(_BYTE *)(v183[0] + 128) )
        {
          memset(pExceptionObject, 0, sizeof(pExceptionObject));
          std::string::_Construct<1,char const *>(
            pExceptionObject,
            "SmilesV3: Location %d m_primaryOutLink == nullptr",
            49);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
            v183,
            "BASIX_DCT",
            pExceptionObject,
            3);
          std::string::_Tidy_deallocate(pExceptionObject);
        }
        v85 = (volatile signed __int32 *)v183[1];
        if ( v183[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v183[1] + 8), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v85)(v85);
            if ( _InterlockedExchangeAdd(v85 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v85 + 8LL))(v85);
          }
        }
        *(_OWORD *)v187 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v187);
        if ( *(_QWORD *)v187 && *(_BYTE *)(*(_QWORD *)v187 + 128LL) )
        {
          std::_Integral_to_string<char,int>(v180, 3);
          v189 = 0;
          v190 = 0;
          std::string::_Construct<1,char const *>(&v189, ":", 1);
          *(_OWORD *)v172 = 0;
          v173 = 0;
          std::string::_Construct<1,char const *>(v172, "\"", 1);
          memset(pExceptionObject, 0, sizeof(pExceptionObject));
          std::string::_Construct<1,char const *>(pExceptionObject, "\"", 1);
          v86 = std::operator+<char>(v181, pExceptionObject, "Location");
          LOBYTE(v87) = v167;
          std::string::string(v183, v87, v86, v172);
          LOBYTE(v88) = v167;
          std::string::string(v178, v88, v183, &v189);
          v89 = v58 | 0xD0000;
          LODWORD(v176) = v89;
          LOBYTE(v90) = v167;
          std::string::string(v174, v90, v178, v180);
          v58 = v89 | 0x20000;
          Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
            (int)v187,
            (int)"RD_CHECKPOINT",
            0,
            (int)"Smiles",
            "TestPrimaryOutLinkNull",
            "TestPrimaryOutLinkNull",
            (__int64)v174);
          std::string::_Tidy_deallocate(v178);
          std::string::_Tidy_deallocate(v183);
          std::string::_Tidy_deallocate(v181);
          std::string::_Tidy_deallocate(pExceptionObject);
          std::string::_Tidy_deallocate(v172);
          std::string::_Tidy_deallocate(&v189);
          std::string::_Tidy_deallocate(v180);
        }
        v91 = *(volatile signed __int32 **)&v187[8];
        if ( *(_QWORD *)&v187[8] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v187[8] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v91)(v91);
            if ( _InterlockedExchangeAdd(v91 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v91 + 8LL))(v91);
          }
        }
      }
    }
    else
    {
      v58 = v169[0];
    }
    if ( !((__int64)(*((_QWORD *)&v193 + 1) - v193) >> 5) )
      goto LABEL_145;
    v92 = (_WORD *)(a1 + 2888);
    v93 = 4;
    v94 = v171;
    do
    {
      v94 += *v92;
      *v92++ = 0;
      --v93;
    }
    while ( v93 );
    v171 = v94;
    if ( !*(_BYTE *)(a1 + 3177) && *(_QWORD *)(a1 + 3152) )
    {
      v95 = *(_QWORD *)(*(_QWORD *)(a1 + 3128) + 8 * (*(_QWORD *)(a1 + 3144) & (*(_QWORD *)(a1 + 3136) - 1LL)));
      LOBYTE(v191) = *(_BYTE *)v95;
      *(_DWORD *)((char *)&v191 + 2) = *(_DWORD *)(v95 + 2);
      std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=((char *)&v191 + 8, v95 + 8);
      LOBYTE(v168) = *(_BYTE *)(v95 + 24);
      BYTE8(v192) = v168;
      HIBYTE(v168) = *(_BYTE *)(v95 + 25);
      BYTE9(v192) = HIBYTE(v168);
      Microsoft::Basix::Dct::OperationOnLinkId::`scalar deleting destructor'(
        *(Microsoft::Basix::Dct::OperationOnLinkId **)(*(_QWORD *)(a1 + 3128)
                                                     + 8 * (*(_QWORD *)(a1 + 3144) & (*(_QWORD *)(a1 + 3136) - 1LL))),
        0);
      if ( (*(_QWORD *)(a1 + 3152))-- == 1 )
        *(_QWORD *)(a1 + 3144) = 0;
      else
        ++*(_QWORD *)(a1 + 3144);
    }
    else
    {
LABEL_145:
      v168 = WORD4(v192);
    }
    Mtx_unlock(v14);
    v97 = *(_QWORD *)v186;
    si128 = _mm_load_si128((const __m128i *)v186);
    if ( v167 )
    {
      memset(v178, 0, sizeof(v178));
      std::string::_Construct<1,char const *>(v178, "Initial primaryOutLink on QueueWrite", 36);
      v185[0] = 0;
      if ( v36 )
        _InterlockedIncrement(v36 + 2);
      v185[0] = si128;
      Microsoft::Basix::Dct::SmilesV3::LogInitialLinkSwitchOn(
        a1,
        (unsigned int)&v189,
        (unsigned int)v185,
        (unsigned int)v178,
        0);
      std::string::_Tidy_deallocate(v178);
      v100 = *(_DWORD *)(a1 + 2216);
      *(_DWORD *)(a1 + 2216) = v100 + 1;
      *(_DWORD *)(v97 + 260) = v100;
      if ( *(_BYTE *)(a1 + 2368) )
      {
        LODWORD(v172[0]) = 2;
        v101 = &v189;
        if ( *((_QWORD *)&v190 + 1) > 0xFu )
          v101 = (__int128 *)v189;
        v172[1] = v101;
        *(_QWORD *)&v173 = v190;
        BYTE8(v173) = 0;
        v58 |= 1u;
        LODWORD(v176) = v58;
        v169[0] = -1;
        if ( (int)Microsoft::Basix::Algorithm::SlidingStats<double,5,0,0>::num(*(_QWORD *)(v97 + 200)) <= 0 )
          v102 = DOUBLE_1000_0;
        else
          v102 = Microsoft::Basix::Algorithm::SlidingStats<double,5,1,0>::navg(*(_QWORD *)(v97 + 200));
        LODWORD(v179) = (int)v102;
        LODWORD(pExceptionObject[0]) = 2;
        *((_QWORD *)&pExceptionObject[0] + 1) = "linkSwitch";
        *(_QWORD *)&pExceptionObject[1] = 10;
        BYTE8(pExceptionObject[1]) = 0;
        LOBYTE(v58) = v58 | 2;
        *(_DWORD *)v187 = *(_DWORD *)(v97 + 260);
        LODWORD(v183[0]) = *(_DWORD *)(v97 + 152);
        Microsoft::Basix::Instrumentation::MultiLinkActivity::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
          a1 + 2496,
          a1 + 2376,
          (unsigned int)v183,
          (unsigned int)v187,
          (__int64)pExceptionObject,
          (__int64)&v179,
          (__int64)v169,
          a1 + 2212,
          (__int64)v172);
      }
      if ( (v58 & 2) != 0 )
      {
        LOBYTE(v58) = v58 & 0xFD;
        if ( BYTE8(pExceptionObject[1]) )
          operator delete(*((void **)&pExceptionObject[0] + 1), v99);
      }
      HIWORD(v103) = 0;
      if ( (v58 & 1) != 0 && BYTE8(v173) )
        operator delete(v172[1], v99);
      Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnStackLayoutChanged(
        (Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *)a1,
        0);
      std::string::_Tidy_deallocate(&v189);
    }
    else
    {
      HIWORD(v103) = 0;
    }
    if ( *(_BYTE *)(a1 + 1524)
      && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                            *(_QWORD *)(a1 + 1816),
                            0) )
    {
      v185[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v185);
      if ( *(_QWORD *)&v185[0] && *(_BYTE *)(*(_QWORD *)&v185[0] + 128LL) )
      {
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        std::string::_Construct<1,char const *>(
          pExceptionObject,
          "SmilesV3: Location %d m_primaryOutLink == nullptr",
          49);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
          v185,
          "BASIX_DCT",
          pExceptionObject,
          4);
        std::string::_Tidy_deallocate(pExceptionObject);
      }
      v104 = (volatile signed __int32 *)*((_QWORD *)&v185[0] + 1);
      if ( *((_QWORD *)&v185[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v185[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v104)(v104);
          if ( _InterlockedExchangeAdd(v104 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v104 + 8LL))(v104);
        }
      }
      *(_OWORD *)v183 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v183);
      if ( v183[0] && *(_BYTE *)(v183[0] + 128) )
      {
        std::_Integral_to_string<char,int>(v185, 4);
        v189 = 0;
        v190 = 0;
        std::string::_Construct<1,char const *>(&v189, ":", 1);
        *(_OWORD *)v172 = 0;
        v173 = 0;
        std::string::_Construct<1,char const *>(v172, "\"", 1);
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        std::string::_Construct<1,char const *>(pExceptionObject, "\"", 1);
        v105 = std::operator+<char>(v181, pExceptionObject, "Location");
        LOBYTE(v106) = v167;
        std::string::string(v178, v106, v105, v172);
        LOBYTE(v107) = v167;
        std::string::string(v174, v107, v178, &v189);
        LOBYTE(v108) = v167;
        std::string::string(v180, v108, v174, v185);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
          (int)v183,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "TestPrimaryOutLinkNull",
          "TestPrimaryOutLinkNull",
          (__int64)v180);
        std::string::_Tidy_deallocate(v174);
        std::string::_Tidy_deallocate(v178);
        std::string::_Tidy_deallocate(v181);
        std::string::_Tidy_deallocate(pExceptionObject);
        std::string::_Tidy_deallocate(v172);
        std::string::_Tidy_deallocate(&v189);
        std::string::_Tidy_deallocate(v185);
      }
      v109 = (volatile signed __int32 *)v183[1];
      if ( v183[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v183[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v109)(v109);
          if ( _InterlockedExchangeAdd(v109 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v109 + 8LL))(v109);
        }
      }
    }
    v110 = v177;
    v111 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*v177);
    v179 = Microsoft::Basix::Containers::FlexOBuffer::Size(v111);
    if ( (int)Microsoft::Basix::Algorithm::SlidingStats<double,5,0,0>::num(*(_QWORD *)(v97 + 200)) <= 0 )
      v112 = DOUBLE_1000_0;
    else
      v112 = Microsoft::Basix::Algorithm::SlidingStats<double,5,1,0>::navg(*(_QWORD *)(v97 + 200));
    if ( v112 != 1000.0 )
      Microsoft::Basix::Dct::SmilesV3::Summary::UpdateDelay(
        (Microsoft::Basix::Dct::SmilesV3::Summary *)(a1 + 2056),
        v112);
    v113 = (*(_WORD *)(v97 + 240) != 0 ? -109 : 1)
         | ((unsigned __int64)((__int64)(*((_QWORD *)&v193 + 1) - v193) >> 5) > 0 ? 0x88 : 0);
    LOWORD(v103) = _InterlockedIncrement16((volatile signed __int16 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(a1 + 2944));
    v169[0] = v103;
    IsOpened = Microsoft::Basix::Dct::detail::BasicStateManagement::IsOpened(*(Microsoft::Basix::Dct::detail::BasicStateManagement **)(v97 + 104));
    v47 = (volatile signed __int32 *)v192;
    if ( IsOpened )
    {
      if ( *(_BYTE *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v110) == 104 )
      {
        v119 = *(_QWORD *)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(v116, v115, v117);
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        std::string::_Construct<1,char const *>(pExceptionObject, "OnWritableThread", 16);
        v120 = (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(
                                                                                                v119,
                                                                                                pExceptionObject,
                                                                                                0);
        std::string::_Tidy_deallocate(pExceptionObject);
        if ( *v120 )
        {
          v183[0] = 0;
          for ( k = 0; k < 2; ++k )
          {
            v122 = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(*v120, v183);
            v123 = snprintf(v122, v183[0], "smilesV3:InternalQueueWrite: send on primary link");
            if ( v123 < v183[0] )
              break;
            v183[0] = v123;
          }
          Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(*v120, 4, "BASIX_DCT");
          v36 = *(volatile signed __int32 **)&v186[2];
        }
        v110 = v177;
        LOWORD(v103) = v169[0];
      }
      LOBYTE(pExceptionObject[0]) = v191;
      *(_DWORD *)((char *)pExceptionObject + 2) = *(_DWORD *)((char *)&v191 + 2);
      *(_OWORD *)((char *)pExceptionObject + 8) = 0;
      if ( v47 )
        _InterlockedAdd(v47 + 2, 1u);
      *((_QWORD *)&pExceptionObject[0] + 1) = *((_QWORD *)&v191 + 1);
      *(_QWORD *)&pExceptionObject[1] = v47;
      WORD4(pExceptionObject[1]) = v168;
      *(_OWORD *)v183 = 0;
      v124 = v110[1];
      if ( v124 )
        _InterlockedAdd((volatile signed __int32 *)v124 + 2, 1u);
      v183[0] = (size_t)*v110;
      v183[1] = (size_t)v110[1];
      *(_OWORD *)v187 = 0;
      if ( v36 )
        _InterlockedAdd(v36 + 2, 1u);
      *(__m128i *)v187 = si128;
      LOBYTE(v118) = v113;
      Microsoft::Basix::Dct::SmilesV3::Send(
        a1,
        (unsigned int)v187,
        (unsigned int)v183,
        v118,
        v103,
        BufferCount[0],
        v171,
        (__int64)pExceptionObject);
    }
    if ( *(_BYTE *)(a1 + 1524)
      && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                            *(_QWORD *)(a1 + 1816),
                            0) )
    {
      v185[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v185);
      if ( *(_QWORD *)&v185[0] && *(_BYTE *)(*(_QWORD *)&v185[0] + 128LL) )
      {
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        std::string::_Construct<1,char const *>(
          pExceptionObject,
          "SmilesV3: Location %d m_primaryOutLink == nullptr",
          49);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
          v185,
          "BASIX_DCT",
          pExceptionObject,
          5);
        std::string::_Tidy_deallocate(pExceptionObject);
      }
      v125 = (volatile signed __int32 *)*((_QWORD *)&v185[0] + 1);
      if ( *((_QWORD *)&v185[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v185[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v125)(v125);
          if ( _InterlockedExchangeAdd(v125 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v125 + 8LL))(v125);
        }
      }
      *(_OWORD *)v183 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v183);
      if ( v183[0] && *(_BYTE *)(v183[0] + 128) )
      {
        std::_Integral_to_string<char,int>(v185, 5);
        v189 = 0;
        v190 = 0;
        std::string::_Construct<1,char const *>(&v189, ":", 1);
        *(_OWORD *)v172 = 0;
        v173 = 0;
        std::string::_Construct<1,char const *>(v172, "\"", 1);
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        std::string::_Construct<1,char const *>(pExceptionObject, "\"", 1);
        v126 = std::operator+<char>(v181, pExceptionObject, "Location");
        LOBYTE(v127) = v167;
        std::string::string(v178, v127, v126, v172);
        LOBYTE(v128) = v167;
        std::string::string(v174, v128, v178, &v189);
        LOBYTE(v129) = v167;
        std::string::string(v180, v129, v174, v185);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
          (int)v183,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "TestPrimaryOutLinkNull",
          "TestPrimaryOutLinkNull",
          (__int64)v180);
        std::string::_Tidy_deallocate(v174);
        std::string::_Tidy_deallocate(v178);
        std::string::_Tidy_deallocate(v181);
        std::string::_Tidy_deallocate(pExceptionObject);
        std::string::_Tidy_deallocate(v172);
        std::string::_Tidy_deallocate(&v189);
        std::string::_Tidy_deallocate(v185);
      }
      v130 = (volatile signed __int32 *)v183[1];
      if ( v183[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v183[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v130)(v130);
          if ( _InterlockedExchangeAdd(v130 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v130 + 8LL))(v130);
        }
      }
    }
    v185[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v185);
    if ( *(_QWORD *)&v185[0] && *(_BYTE *)(*(_QWORD *)&v185[0] + 128LL) )
    {
      v132 = *(_DWORD *)(v97 + 152);
      memset(pExceptionObject, 0, sizeof(pExceptionObject));
      std::string::_Construct<1,char const *>(
        pExceptionObject,
        "SmilesV3: QueueWrite on primary link(%d) a packet(size=%d) with counter(%d), runningClockInMs(%d), sendTimeInMs(%llu)",
        117,
        v131,
        v160,
        Str,
        v163);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned __int64,unsigned short,unsigned short,unsigned __int64>(
        (unsigned int)v185,
        (unsigned int)"BASIX_DCT",
        (unsigned int)pExceptionObject,
        v132,
        v179,
        v103,
        BufferCount[0],
        BufferCount[0]);
      std::string::_Tidy_deallocate(pExceptionObject);
    }
    v133 = (volatile signed __int32 *)*((_QWORD *)&v185[0] + 1);
    if ( *((_QWORD *)&v185[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v185[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v133)(v133);
        if ( _InterlockedExchangeAdd(v133 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v133 + 8LL))(v133);
      }
    }
    *(_QWORD *)&v185[0] = *((_QWORD *)&v193 + 1);
    if ( (_QWORD)v193 != *((_QWORD *)&v193 + 1) )
    {
      v134 = (volatile signed __int32 **)(v193 + 8);
      do
      {
        v189 = 0;
        if ( *v134 )
          _InterlockedAdd(*v134 + 2, 1u);
        v135 = (__int64)*(v134 - 1);
        v176 = v135;
        *(_QWORD *)&v189 = v135;
        v136 = *v134;
        *((_QWORD *)&v189 + 1) = *v134;
        v137 = *(_WORD *)(v135 + 240) != 0 ? -102 : -120;
        v167 = v137;
        v178[0] = 0;
        v138 = v134[2];
        if ( v138 )
          _InterlockedAdd(v138 + 2, 1u);
        *(_QWORD *)&v178[0] = v134[1];
        v139 = v134[2];
        *((_QWORD *)&v178[0] + 1) = v139;
        if ( *(_BYTE *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v177) == 104 )
        {
          v144 = *(_QWORD *)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(v141, v140, v142);
          *(_OWORD *)v174 = 0;
          v175 = 0;
          std::string::_Construct<1,char const *>(v174, "OnWritableThread", 16);
          v145 = (_QWORD *)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(v144, v174, 0);
          *(_QWORD *)v187 = v145;
          std::string::_Tidy_deallocate(v174);
          if ( *v145 )
          {
            v183[0] = 0;
            v146 = 0;
            v147 = *(Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord ***)v187;
            do
            {
              v148 = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(*v147, v183);
              v149 = snprintf(v148, v183[0], "smilesV3:InternalQueueWrite: send on secondary link");
              if ( v149 < v183[0] )
                break;
              v183[0] = v149;
              ++v146;
            }
            while ( v146 < 2 );
            Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(*v147, 4, "BASIX_DCT");
            v47 = (volatile signed __int32 *)v192;
            v135 = v176;
          }
          v137 = v167;
        }
        v187[0] = v191;
        *(_DWORD *)&v187[2] = *(_DWORD *)((char *)&v191 + 2);
        *(_OWORD *)&v187[8] = 0;
        if ( v47 )
          _InterlockedAdd(v47 + 2, 1u);
        *(_QWORD *)&v187[8] = *((_QWORD *)&v191 + 1);
        *(_QWORD *)&v187[16] = v47;
        v188 = v168;
        *(_OWORD *)v172 = 0;
        if ( v139 )
          _InterlockedAdd(v139 + 2, 1u);
        *(_OWORD *)v172 = v178[0];
        pExceptionObject[0] = 0;
        if ( v136 )
          _InterlockedAdd(v136 + 2, 1u);
        pExceptionObject[0] = v189;
        LOBYTE(v143) = v137;
        Microsoft::Basix::Dct::SmilesV3::Send(
          a1,
          (unsigned int)pExceptionObject,
          (unsigned int)v172,
          v143,
          v169[0],
          BufferCount[0],
          v171,
          (__int64)v187);
        *(_OWORD *)v183 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v183);
        if ( v183[0] && *(_BYTE *)(v183[0] + 128) )
        {
          v151 = *(_DWORD *)(v135 + 152);
          *(_OWORD *)v174 = 0;
          v175 = 0;
          std::string::_Construct<1,char const *>(
            v174,
            "SmilesV3: QueueWrite on secondary link(%d) a packet(size=%d) with counter(%d)",
            77,
            v150,
            v161);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned __int64,unsigned short>(
            (unsigned int)v183,
            (unsigned int)"BASIX_DCT",
            (unsigned int)v174,
            v151,
            v179,
            v169[0]);
          std::string::_Tidy_deallocate(v174);
        }
        v152 = (volatile signed __int32 *)v183[1];
        if ( v183[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v183[1] + 8), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v152)(v152);
            if ( _InterlockedExchangeAdd(v152 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v152 + 8LL))(v152);
          }
        }
        if ( v139 )
        {
          if ( _InterlockedExchangeAdd(v139 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v139)(v139);
            if ( _InterlockedExchangeAdd(v139 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v139 + 8LL))(v139);
          }
        }
        if ( v136 )
        {
          if ( _InterlockedExchangeAdd(v136 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v136)(v136);
            if ( _InterlockedExchangeAdd(v136 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v136 + 8LL))(v136);
          }
        }
        v134 += 4;
      }
      while ( v134 - 1 != *(volatile signed __int32 ***)&v185[0] );
      v36 = *(volatile signed __int32 **)&v186[2];
    }
    if ( *(_BYTE *)(a1 + 1524)
      && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                            *(_QWORD *)(a1 + 1816),
                            0) )
    {
      v185[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v185);
      if ( *(_QWORD *)&v185[0] && *(_BYTE *)(*(_QWORD *)&v185[0] + 128LL) )
      {
        *(_OWORD *)v174 = 0;
        v175 = 0;
        std::string::_Construct<1,char const *>(v174, "SmilesV3: Location %d m_primaryOutLink == nullptr", 49);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
          v185,
          "BASIX_DCT",
          v174,
          6);
        std::string::_Tidy_deallocate(v174);
      }
      v153 = (volatile signed __int32 *)*((_QWORD *)&v185[0] + 1);
      if ( *((_QWORD *)&v185[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v185[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v153)(v153);
          if ( _InterlockedExchangeAdd(v153 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v153 + 8LL))(v153);
        }
      }
      *(_OWORD *)BufferCount = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(BufferCount);
      if ( BufferCount[0] && *(_BYTE *)(BufferCount[0] + 128) )
      {
        std::_Integral_to_string<char,int>(v185, 6);
        *(_OWORD *)v172 = 0;
        v173 = 0;
        std::string::_Construct<1,char const *>(v172, ":", 1);
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        std::string::_Construct<1,char const *>(pExceptionObject, "\"", 1);
        *(_OWORD *)v174 = 0;
        v175 = 0;
        std::string::_Construct<1,char const *>(v174, "\"", 1);
        v154 = std::operator+<char>(v181, v174, "Location");
        LOBYTE(v155) = v167;
        std::string::string(v178, v155, v154, pExceptionObject);
        LOBYTE(v156) = v167;
        std::string::string(&v189, v156, v178, v172);
        LOBYTE(v157) = v167;
        std::string::string(v180, v157, &v189, v185);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
          (int)BufferCount,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "TestPrimaryOutLinkNull",
          "TestPrimaryOutLinkNull",
          (__int64)v180);
        std::string::_Tidy_deallocate(&v189);
        std::string::_Tidy_deallocate(v178);
        std::string::_Tidy_deallocate(v181);
        std::string::_Tidy_deallocate(v174);
        std::string::_Tidy_deallocate(pExceptionObject);
        std::string::_Tidy_deallocate(v172);
        std::string::_Tidy_deallocate(v185);
      }
      v158 = (volatile signed __int32 *)BufferCount[1];
      if ( BufferCount[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(BufferCount[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v158)(v158);
          if ( _InterlockedExchangeAdd(v158 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v158 + 8LL))(v158);
        }
      }
    }
  }
  if ( v47 )
  {
    if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
      if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
    }
  }
  result = std::vector<std::pair<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>,std::shared_ptr<Microsoft::Basix::Dct::IChannel>>>::_Tidy(&v193);
  if ( v36 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
      result = (unsigned int)_InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180261ba0  mov     [rsp-8+arg_10], rbx
0x180261ba5  push    rbp
0x180261ba6  push    rsi
0x180261ba7  push    rdi
0x180261ba8  push    r12
0x180261baa  push    r13
0x180261bac  push    r14
0x180261bae  push    r15
0x180261bb0  lea     rbp, [rsp-160h]
0x180261bb8  mov     eax, 260h
0x180261bbd  call    _alloca_probe
0x180261bc2  sub     rsp, rax
0x180261bc5  movaps  [rsp+290h+var_40], xmm6
0x180261bcd  movaps  [rsp+290h+var_50], xmm7
0x180261bd5  mov     rax, cs:__security_cookie
0x180261bdc  xor     rax, rsp
0x180261bdf  mov     [rbp+190h+var_58], rax
0x180261be6  mov     [rbp+190h+var_1B0], rdx
0x180261bea  mov     r13, rcx
0x180261bed  xor     r12d, r12d
0x180261bf0  mov     r14d, r12d
0x180261bf3  mov     [rsp+290h+var_23C], r12d
0x180261bf8  mov     dword ptr [rbp+190h+var_1C0], r12d
0x180261bfc  lea     rsi, aTestprimaryout; "TestPrimaryOutLinkNull"
0x180261c03  cmp     [rcx+5F4h], r12b
0x180261c0a  jz      loc_180261E03
0x180261c10  xor     edx, edx
0x180261c12  mov     rcx, [rcx+718h]
0x180261c19  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x180261c1e  test    al, al
0x180261c20  jz      loc_180261E03
0x180261c26  xorps   xmm0, xmm0
0x180261c29  movups  xmmword ptr [rbp+190h+var_E0], xmm0
0x180261c30  lea     rcx, [rbp+190h+var_E0]
0x180261c37  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180261c3c  nop
0x180261c3d  mov     rax, qword ptr [rbp+190h+var_E0]
0x180261c44  test    rax, rax
0x180261c47  jz      short loc_180261C88
0x180261c49  cmp     [rax+80h], r12b
0x180261c50  jz      short loc_180261C88
0x180261c52  lea     rdx, aSmilesv3Locati; "SmilesV3: Location %d m_primaryOutLink "...
0x180261c59  lea     rcx, [rbp+190h+var_1E0]
0x180261c5d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180261c62  nop
0x180261c63  xor     r9d, r9d
0x180261c66  lea     r8, [rbp+190h+var_1E0]
0x180261c6a  lea     rdx, aBasixDct; "BASIX_DCT"
0x180261c71  lea     rcx, [rbp+190h+var_E0]
0x180261c78  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@H@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@H@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,int)
0x180261c7d  nop
0x180261c7e  lea     rcx, [rbp+190h+var_1E0]
0x180261c82  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180261c87  nop
0x180261c88  lea     rcx, [rbp+190h+var_E0]; void *
0x180261c8f  call    ??1?$shared_ptr@VMicrosoft_Basix_Instrumentation_RioBuffersReceive_Logger@Microsoft_Streaming_Nano_Network@GlobalProviderList@@@std@@QEAA@XZ; std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(void)
0x180261c94  xorps   xmm0, xmm0
0x180261c97  movups  xmmword ptr [rbp+190h+var_E0], xmm0
0x180261c9e  lea     rcx, [rbp+190h+var_E0]
0x180261ca5  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x180261caa  nop
0x180261cab  mov     rax, qword ptr [rbp+190h+var_E0]
0x180261cb2  test    rax, rax
0x180261cb5  jz      loc_180261DF7
0x180261cbb  cmp     [rax+80h], r12b
0x180261cc2  jz      loc_180261DF7
0x180261cc8  xor     edx, edx
0x180261cca  lea     rcx, [rbp+190h+var_200]
0x180261cce  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x180261cd3  nop
0x180261cd4  lea     rdx, asc_1803D71C4; ":"
0x180261cdb  lea     rcx, [rbp+190h+var_100]
0x180261ce2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180261ce7  mov     rdi, rax
0x180261cea  lea     rdx, asc_1803D71C8; "\""
0x180261cf1  lea     rcx, [rbp+190h+var_1A0]
0x180261cf5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180261cfa  mov     rbx, rax
0x180261cfd  lea     rdx, asc_1803D71C8; "\""
0x180261d04  lea     rcx, [rbp+190h+var_B0]
0x180261d0b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180261d10  nop
0x180261d11  lea     r8, aLocation_0; "Location"
0x180261d18  mov     rdx, rax
0x180261d1b  lea     rcx, [rbp+190h+var_178]
0x180261d1f  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180261d24  nop
0x180261d25  mov     r9, rbx
0x180261d28  mov     r8, rax
0x180261d2b  mov     dl, [rsp+290h+var_240]
0x180261d2f  lea     rcx, [rsp+290h+pExceptionObject]
0x180261d34  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180261d39  nop
0x180261d3a  mov     r9, rdi
0x180261d3d  lea     r8, [rsp+290h+pExceptionObject]
0x180261d42  mov     dl, [rsp+290h+var_240]
0x180261d46  lea     rcx, [rbp+190h+var_90]
0x180261d4d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180261d52  nop
0x180261d53  lea     r9, [rbp+190h+var_200]
0x180261d57  lea     r8, [rbp+190h+var_90]
0x180261d5e  mov     dl, [rsp+290h+var_240]
0x180261d62  lea     rcx, [rbp+190h+var_1E0]
0x180261d66  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180261d6b  mov     r14d, 0F0000000h
0x180261d71  mov     [rsp+290h+var_23C], r14d
0x180261d76  lea     rax, [rbp+190h+var_1E0]
0x180261d7a  mov     [rsp+290h+var_260], rax; __int64
0x180261d7f  mov     [rsp+290h+Str], rsi; Str
0x180261d84  mov     [rsp+290h+var_270], rsi; char *
0x180261d89  lea     r9, aSmiles; "Smiles"
0x180261d90  xor     r8d, r8d; int
0x180261d93  lea     rdx, aRdCheckpoint; "RD_CHECKPOINT"
0x180261d9a  lea     rcx, [rbp+190h+var_E0]; int
0x180261da1  call    ??$TraceCheckpointMessage@VTraceCheckpoint@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDI111V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,char const *,uint,char const *,char const *,char const *,std::string)
0x180261da6  nop
0x180261da7  lea     rcx, [rbp+190h+var_90]
0x180261dae  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180261db3  nop
0x180261db4  lea     rcx, [rsp+290h+pExceptionObject]
0x180261db9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180261dbe  nop
0x180261dbf  lea     rcx, [rbp+190h+var_178]
0x180261dc3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180261dc8  nop
0x180261dc9  lea     rcx, [rbp+190h+var_B0]
0x180261dd0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180261dd5  nop
0x180261dd6  lea     rcx, [rbp+190h+var_1A0]
0x180261dda  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180261ddf  nop
0x180261de0  lea     rcx, [rbp+190h+var_100]
0x180261de7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180261dec  nop
0x180261ded  lea     rcx, [rbp+190h+var_200]
0x180261df1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180261df6  nop
0x180261df7  lea     rcx, [rbp+190h+var_E0]; void *
0x180261dfe  call    ??1?$shared_ptr@VMicrosoft_Basix_Instrumentation_RioBuffersReceive_Logger@Microsoft_Streaming_Nano_Network@GlobalProviderList@@@std@@QEAA@XZ; std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(void)
0x180261e03  lea     rcx, [rbp+190h+var_100]
0x180261e0a  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180261e0f  mov     rcx, [rax]
0x180261e12  mov     rax, 431BDE82D7B634DBh
0x180261e1c  imul    rcx
0x180261e1f  mov     rsi, rdx
0x180261e22  sar     rsi, 12h
0x180261e26  mov     rax, rsi
0x180261e29  shr     rax, 3Fh
0x180261e2d  add     rsi, rax
0x180261e30  sub     rsi, [r13+0BC0h]
0x180261e37  mov     [rbp+190h+BufferCount], rsi
0x180261e3b  xorps   xmm0, xmm0
0x180261e3e  xorps   xmm1, xmm1
0x180261e41  movdqa  xmmword ptr [rbp+190h+var_E0], xmm1
0x180261e49  movdqu  [rbp+190h+var_70], xmm1
0x180261e51  mov     [rbp+190h+var_60], r12
0x180261e58  mov     rdi, [r13+0B40h]
0x180261e5f  mov     [rbp+190h+var_210], r12w
0x180261e64  movups  [rbp+190h+var_90], xmm0
0x180261e6b  movups  [rbp+190h+var_80], xmm0
0x180261e72  movdqu  [rsp+290h+pExceptionObject], xmm0
0x180261e78  lea     r9, [rsp+290h+pExceptionObject]
0x180261e7d  xor     r8d, r8d
0x180261e80  xor     edx, edx
0x180261e82  lea     rcx, [rbp+190h+var_90]
0x180261e89  call    ??0OperationOnLinkId@Dct@Basix@Microsoft@@QEAA@W4Direction@LinkData@123@W4Mode@0123@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(Microsoft::Basix::Dct::LinkData::Direction,Microsoft::Basix::Dct::OperationOnLinkId::Mode,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>)
0x180261e8e  nop
0x180261e8f  lea     rbx, [r13+728h]
0x180261e96  mov     qword ptr [rbp+190h+var_100], rbx
0x180261e9d  mov     rcx, rbx; _Mtx_t
0x180261ea0  call    _Mtx_lock
0x180261ea5  test    eax, eax
0x180261ea7  jnz     loc_180264149
0x180261ead  lea     r15, [rbx+4Ch]
0x180261eb1  cmp     dword ptr [r15], 7FFFFFFFh
0x180261eb8  jz      loc_180264154
0x180261ebe  mov     ecx, r12d
0x180261ec1  lea     edx, [rax+1]
0x180261ec4  cmp     rdi, rsi
0x180261ec7  jz      short loc_180261EF5
0x180261ec9  add     rdi, rdx
0x180261ecc  mov     rax, rdi
0x180261ecf  and     eax, 3
0x180261ed2  mov     [r13+rax*2+0B48h], r12w
0x180261edb  add     ecx, edx
0x180261edd  cmp     ecx, 4
0x180261ee0  jl      short loc_180261EC4
0x180261ee2  jnz     short loc_180261F01
0x180261ee4  mov     rax, rsi
0x180261ee7  and     eax, 3
0x180261eea  add     [r13+rax*2+0B48h], dx
0x180261ef3  jmp     short loc_180261F01
0x180261ef5  and     edi, 3
0x180261ef8  add     [r13+rdi*2+0B48h], dx
0x180261f01  cmp     [r13+5F4h], r12b
0x180261f08  jz      loc_18026217C
0x180261f0e  xor     edx, edx
0x180261f10  mov     rcx, [r13+718h]
0x180261f17  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x180261f1c  test    al, al
0x180261f1e  jz      loc_18026217C
0x180261f24  xorps   xmm0, xmm0
0x180261f27  movups  xmmword ptr [rbp+190h+var_138], xmm0
0x180261f2b  lea     rcx, [rbp+190h+var_138]
0x180261f2f  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180261f34  nop
0x180261f35  mov     rax, [rbp+190h+var_138]
0x180261f39  test    rax, rax
0x180261f3c  jz      short loc_180261F7D
0x180261f3e  cmp     [rax+80h], r12b
0x180261f45  jz      short loc_180261F7D
0x180261f47  lea     rdx, aSmilesv3Locati; "SmilesV3: Location %d m_primaryOutLink "...
0x180261f4e  lea     rcx, [rbp+190h+var_1E0]
0x180261f52  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180261f57  nop
0x180261f58  mov     r9d, 1
0x180261f5e  lea     r8, [rbp+190h+var_1E0]
0x180261f62  lea     rdx, aBasixDct; "BASIX_DCT"
0x180261f69  lea     rcx, [rbp+190h+var_138]
0x180261f6d  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@H@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@H@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,int)
0x180261f72  nop
0x180261f73  lea     rcx, [rbp+190h+var_1E0]
0x180261f77  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180261f7c  nop
0x180261f7d  mov     rdi, [rbp+190h+var_138+8]
0x180261f81  test    rdi, rdi
0x180261f84  jz      short loc_180261FBF
0x180261f86  or      eax, 0FFFFFFFFh
0x180261f89  lock xadd [rdi+8], eax
0x180261f8e  cmp     eax, 1
0x180261f91  jnz     short loc_180261FBF
0x180261f93  mov     rax, [rdi]
0x180261f96  mov     rcx, rdi
0x180261f99  mov     rax, [rax]
0x180261f9c  call    cs:__guard_dispatch_icall_fptr
0x180261fa2  or      eax, 0FFFFFFFFh
0x180261fa5  lock xadd [rdi+0Ch], eax
0x180261faa  cmp     eax, 1
0x180261fad  jnz     short loc_180261FBF
0x180261faf  mov     rax, [rdi]
0x180261fb2  mov     rcx, rdi
0x180261fb5  mov     rax, [rax+8]
0x180261fb9  call    cs:__guard_dispatch_icall_fptr
0x180261fbf  xorps   xmm0, xmm0
0x180261fc2  movups  xmmword ptr [rbp+190h+var_D0], xmm0
0x180261fc9  lea     rcx, [rbp+190h+var_D0]
0x180261fd0  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x180261fd5  nop
0x180261fd6  mov     rax, qword ptr [rbp+190h+var_D0]
0x180261fdd  test    rax, rax
0x180261fe0  jz      loc_180262132
0x180261fe6  cmp     [rax+80h], r12b
0x180261fed  jz      loc_180262132
0x180261ff3  mov     edx, 1
0x180261ff8  lea     rcx, [rbp+190h+var_B0]
0x180261fff  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x180262004  bts     r14d, 17h
0x180262009  lea     rdx, asc_1803D71C4; ":"
0x180262010  lea     rcx, [rbp+190h+var_158]
0x180262014  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180262019  mov     rsi, rax
0x18026201c  lea     rdx, asc_1803D71C8; "\""
0x180262023  lea     rcx, [rbp+190h+var_138]
0x180262027  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18026202c  mov     rdi, rax
0x18026202f  lea     rdx, asc_1803D71C8; "\""
0x180262036  lea     rcx, [rbp+190h+var_1A0]
0x18026203a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18026203f  nop
0x180262040  lea     r8, aLocation_0; "Location"
0x180262047  mov     rdx, rax
0x18026204a  lea     rcx, [rbp+190h+var_178]
0x18026204e  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180262053  nop
0x180262054  mov     r9, rdi
0x180262057  mov     r8, rax
0x18026205a  mov     dl, [rsp+290h+var_240]
0x18026205e  lea     rcx, [rbp+190h+var_200]
0x180262062  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180262067  bts     r14d, 14h
0x18026206c  mov     r9, rsi
0x18026206f  lea     r8, [rbp+190h+var_200]
0x180262073  mov     dl, [rsp+290h+var_240]
0x180262077  lea     rcx, [rsp+290h+pExceptionObject]
0x18026207c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180262081  bts     r14d, 16h
0x180262086  mov     dword ptr [rbp+190h+var_1C0], r14d
0x18026208a  lea     r9, [rbp+190h+var_B0]
0x180262091  lea     r8, [rsp+290h+pExceptionObject]
0x180262096  mov     dl, [rsp+290h+var_240]
0x18026209a  lea     rcx, [rbp+190h+var_1E0]
0x18026209e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1802620a3  bts     r14d, 15h
0x1802620a8  mov     [rsp+290h+var_23C], r14d
0x1802620ad  lea     rax, [rbp+190h+var_1E0]
0x1802620b1  mov     [rsp+290h+var_260], rax; __int64
0x1802620b6  lea     rax, aTestprimaryout; "TestPrimaryOutLinkNull"
0x1802620bd  mov     [rsp+290h+Str], rax; Str
0x1802620c2  mov     [rsp+290h+var_270], rax; char *
0x1802620c7  lea     r9, aSmiles; "Smiles"
  ... truncated ...
```

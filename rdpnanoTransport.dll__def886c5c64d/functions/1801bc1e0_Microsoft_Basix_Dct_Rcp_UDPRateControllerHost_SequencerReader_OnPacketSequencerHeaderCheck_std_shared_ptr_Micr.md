# Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::OnPacketSequencerHeaderCheck(std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const &)

- ea: `0x1801bc1e0`
- end: `0x1801befbc`
- name: `?OnPacketSequencerHeaderCheck@SequencerReader@UDPRateControllerHost@Rcp@Dct@Basix@Microsoft@@UEAA_NAEBV?$shared_ptr@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@Z`
- size: `11740`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x1800191b4`
- `0x18001979c`
- `0x1800199ec`
- `0x18001bbdc`
- `0x18001dad8`
- `0x18001db78`
- `0x18001dc00`
- `0x180024700`
- `0x180024760`
- `0x180035838`
- `0x1800bb210`
- `0x1800c3524`
- `0x1800c4238`
- `0x1800c4ac4`
- `0x1800f30dc`
- `0x18010587c`
- `0x18010fbb0`
- `0x1801825a8`
- `0x1801b6e20`
- `0x1801b741c`
- `0x1801b7b58`
- `0x1801b7ce4`
- `0x1801b7ee8`
- `0x1801b80b0`
- `0x1801b8274`
- `0x1801b866c`
- `0x1801b884c`
- `0x1801bc1e0`
- `0x1801c20f0`
- `0x1802b08f0`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1801bc29c`: `RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: insufficint packet size for the header %d`
- `0x1801bc5ad`: `RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck:  insufficint packet size for the header extension(%d), tail size=%d`
- `0x1801bc802`: `header extension size`
- `0x1801bc873`: `insufficint packet size for the header extension`
- `0x1801bc997`: `RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: insufficient packet length for seqnum`
- `0x1801bcbe7`: `RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: user packet size (%d) smaller than coded size(%d): seqnum=%04x`
- `0x1801bd0a6`: `RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: seqnum=%04x, crc16 mismatch: coded(%04x), calc(%04x), sizes: coded(%d), actual(%d), expected seqnum=%04x, numPacketsInWaiting=%d`
- `0x1801bdce3`: `RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: subsequent mismatch cnt=%d, seqnum=%04x, recorded: CodedCRC(%04x), calcCRC(%04x), codedSize(%d), actualSize(%d)`
- `0x1801be51a`: `RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: mismatch forced restored: seqnum=%04x`
- `0x1801be776`: `RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: mismatch restored: seqnum=%04x`
- `0x1801bea54`: `RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: seqnum=%04x, received length(%d) longer than coded length(%d), but trim works successfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=330
char __fastcall Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::OnPacketSequencerHeaderCheck(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rax
  _DWORD *v5; // rdi
  unsigned int v6; // ebx
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rbx
  unsigned int v13; // r15d
  __int64 v14; // rdx
  __int64 v15; // rsi
  int v16; // r9d
  int v17; // ebx
  int v18; // r9d
  volatile signed __int32 *v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  unsigned int v28; // esi
  volatile signed __int32 *v29; // rbx
  __int64 v30; // rdi
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  unsigned int v37; // r12d
  Microsoft::Basix::Dct::Rcp *Pointer; // rcx
  unsigned __int64 v39; // r8
  char v40; // r15
  signed int v41; // ebx
  int v42; // r8d
  int v43; // r9d
  char v44; // bl
  volatile signed __int32 *v45; // rbx
  __int64 v46; // rdi
  __int64 v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdi
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdi
  __int64 v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // rdx
  char v67; // r13
  int v68; // r9d
  __int64 v69; // rbx
  __int64 v70; // rdi
  unsigned __int16 v71; // si
  volatile signed __int32 *v72; // rbx
  __int64 v73; // rdi
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rdx
  __int64 v77; // rdx
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rdx
  __int64 v81; // rdx
  __int64 v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rdx
  __int64 v85; // rdx
  int v86; // edi
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rdx
  __int64 v90; // rdx
  __int64 v91; // rax
  __int64 v92; // rdx
  __int64 v93; // rdx
  __int64 v94; // rdx
  __int64 v95; // rax
  __int64 v96; // rdx
  __int64 v97; // rdx
  __int64 v98; // rdx
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rdx
  __int64 v102; // rdx
  volatile signed __int32 *v103; // rbx
  __int64 v104; // r12
  int v105; // ecx
  int v106; // r8d
  int v107; // r9d
  int v108; // ebx
  int v109; // edi
  __int16 v110; // si
  __int16 v111; // r14
  char v112; // r15
  int v113; // r12d
  volatile signed __int32 *v114; // rbx
  __int64 v115; // rdi
  __int64 v116; // rbx
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rdx
  __int64 v120; // rdx
  __int64 v121; // rdx
  __int64 v122; // rdi
  __int64 v123; // rbx
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rdx
  __int64 v127; // rdx
  __int64 v128; // rdx
  __int64 v129; // rdi
  __int64 v130; // rbx
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rdx
  __int64 v135; // rdx
  __int64 v136; // rdi
  __int64 v137; // rbx
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 v140; // rdx
  __int64 v141; // rdx
  __int64 v142; // rdx
  __int64 v143; // rdi
  __int64 v144; // rbx
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rdx
  __int64 v148; // rdx
  __int64 v149; // rdx
  __int64 v150; // rdi
  __int64 v151; // rbx
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rdx
  __int64 v155; // rdx
  __int64 v156; // rdx
  volatile signed __int32 *v157; // rbx
  int v158; // r8d
  unsigned __int16 v159; // bx
  __int64 v160; // rdi
  __int64 v161; // rbx
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 v164; // rdx
  __int64 v165; // rdx
  __int64 v166; // rdx
  unsigned __int16 v167; // bx
  volatile signed __int32 *v168; // rbx
  __int64 v169; // rax
  __int64 v170; // rdx
  __int64 v171; // rdx
  __int64 v172; // rdx
  volatile signed __int32 *v173; // rbx
  int v174; // r9d
  unsigned __int16 v175; // bx
  volatile signed __int32 *v176; // rbx
  __int64 v177; // rax
  __int64 v178; // rdx
  __int64 v179; // rdx
  __int64 v180; // rdx
  __int64 v181; // rax
  __int64 v182; // rdx
  __int64 v183; // rdx
  __int64 v184; // rdx
  __int64 v185; // rax
  __int64 v186; // rdx
  __int64 v187; // rdx
  __int64 v188; // rdx
  int v189; // [rsp+20h] [rbp-E0h]
  int Str; // [rsp+28h] [rbp-D8h]
  int v191; // [rsp+30h] [rbp-D0h]
  int v192; // [rsp+38h] [rbp-C8h]
  int v193; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v194[2]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v195[2]; // [rsp+74h] [rbp-8Ch] BYREF
  char v196; // [rsp+78h] [rbp-88h]
  unsigned __int16 v197; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v198; // [rsp+80h] [rbp-80h]
  unsigned __int16 v199; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v200[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v201; // [rsp+98h] [rbp-68h]
  __int64 *v202; // [rsp+A8h] [rbp-58h]
  __int64 *v203; // [rsp+B0h] [rbp-50h]
  __int64 v204[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v205; // [rsp+C8h] [rbp-38h]
  __int64 v206[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v207[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v208; // [rsp+108h] [rbp+8h]
  __int64 v209; // [rsp+118h] [rbp+18h]
  __int128 v210; // [rsp+120h] [rbp+20h] BYREF
  __int128 v211; // [rsp+130h] [rbp+30h]
  __int128 v212; // [rsp+140h] [rbp+40h] BYREF
  __int128 v213; // [rsp+150h] [rbp+50h]
  __int64 v214[4]; // [rsp+160h] [rbp+60h] BYREF
  __int64 *v215; // [rsp+180h] [rbp+80h]
  __int128 v216; // [rsp+188h] [rbp+88h] BYREF
  __int128 v217; // [rsp+198h] [rbp+98h]
  __int64 v218[4]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v219[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v220; // [rsp+1E8h] [rbp+E8h] BYREF
  __int128 v221; // [rsp+1F8h] [rbp+F8h]
  __int128 v222; // [rsp+208h] [rbp+108h] BYREF
  __int128 v223; // [rsp+218h] [rbp+118h]
  __int128 v224; // [rsp+228h] [rbp+128h] BYREF
  __int128 v225; // [rsp+238h] [rbp+138h]
  __int128 v226; // [rsp+248h] [rbp+148h] BYREF
  __int128 v227; // [rsp+258h] [rbp+158h]
  __int128 v228; // [rsp+268h] [rbp+168h] BYREF
  __int128 v229; // [rsp+278h] [rbp+178h]
  __int128 v230; // [rsp+288h] [rbp+188h] BYREF
  __int128 v231; // [rsp+298h] [rbp+198h]
  __int64 *v232; // [rsp+2A8h] [rbp+1A8h]
  __int64 *v233; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v234[32]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v235[32]; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v236[32]; // [rsp+2F8h] [rbp+1F8h] BYREF
  _BYTE v237[32]; // [rsp+318h] [rbp+218h] BYREF
  _BYTE v238[32]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v239[32]; // [rsp+358h] [rbp+258h] BYREF
  __int64 v240[4]; // [rsp+378h] [rbp+278h] BYREF
  __int64 v241[4]; // [rsp+398h] [rbp+298h] BYREF
  _OWORD v242[2]; // [rsp+3B8h] [rbp+2B8h] BYREF
  __int128 v243; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int128 v244; // [rsp+3E8h] [rbp+2E8h]
  _OWORD v245[2]; // [rsp+3F8h] [rbp+2F8h] BYREF
  _OWORD v246[2]; // [rsp+418h] [rbp+318h] BYREF
  _BYTE v247[32]; // [rsp+438h] [rbp+338h] BYREF
  __int128 v248; // [rsp+458h] [rbp+358h] BYREF
  __int128 v249; // [rsp+468h] [rbp+368h]
  __int64 *v250; // [rsp+478h] [rbp+378h]
  __int64 *v251; // [rsp+480h] [rbp+380h]
  _BYTE v252[32]; // [rsp+488h] [rbp+388h] BYREF
  _BYTE v253[32]; // [rsp+4A8h] [rbp+3A8h] BYREF
  __int64 *v254; // [rsp+4C8h] [rbp+3C8h]
  _OWORD v255[2]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _OWORD v256[2]; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int64 v257[4]; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v258[32]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v259[32]; // [rsp+550h] [rbp+450h] BYREF
  _BYTE v260[32]; // [rsp+570h] [rbp+470h] BYREF
  _BYTE v261[32]; // [rsp+590h] [rbp+490h] BYREF
  _BYTE v262[32]; // [rsp+5B0h] [rbp+4B0h] BYREF
  _BYTE v263[32]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v264[32]; // [rsp+5F0h] [rbp+4F0h] BYREF
  _BYTE v265[32]; // [rsp+610h] [rbp+510h] BYREF
  __int64 v266[4]; // [rsp+630h] [rbp+530h] BYREF
  __int64 v267[4]; // [rsp+650h] [rbp+550h] BYREF
  __int64 v268[4]; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v269[32]; // [rsp+690h] [rbp+590h] BYREF
  _OWORD v270[2]; // [rsp+6B0h] [rbp+5B0h] BYREF
  __int64 v271[4]; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int64 v272[4]; // [rsp+6F0h] [rbp+5F0h] BYREF
  __int64 v273[4]; // [rsp+710h] [rbp+610h] BYREF
  _OWORD v274[2]; // [rsp+730h] [rbp+630h] BYREF
  _BYTE v275[32]; // [rsp+750h] [rbp+650h] BYREF
  _BYTE v276[32]; // [rsp+770h] [rbp+670h] BYREF
  _BYTE v277[32]; // [rsp+790h] [rbp+690h] BYREF
  int v278[4]; // [rsp+7B0h] [rbp+6B0h] BYREF
  __int128 v279; // [rsp+7C0h] [rbp+6C0h]
  int v280[4]; // [rsp+7D0h] [rbp+6D0h] BYREF

  v209 = a1;
  if ( !*(_BYTE *)(a1 + 1594) )
    return 1;
  v196 = 0;
  v4 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
  v5 = (_DWORD *)v4;
  if ( *(_QWORD *)(v4 + 32) - *(_QWORD *)(v4 + 24) < 5u )
  {
    *(_OWORD *)v280 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v280);
    if ( *(_QWORD *)v280 && *(_BYTE *)(*(_QWORD *)v280 + 128LL) )
    {
      v6 = v5[8] - v5[6];
      v212 = 0;
      v213 = 0;
      std::string::_Construct<1,char const *>(
        &v212,
        "RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: insufficint packet size for the header %d",
        110);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,enum Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode>(
        v280,
        "RDPNANOSTREAM",
        &v212,
        v6);
      std::string::_Tidy_deallocate(&v212);
    }
    v7 = *(volatile signed __int32 **)&v280[2];
    if ( *(_QWORD *)&v280[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v280[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    *(_OWORD *)v280 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v280);
    if ( *(_QWORD *)v280 && *(_BYTE *)(*(_QWORD *)v280 + 128LL) )
    {
      std::_Integral_to_string<char,int>(&v210, (unsigned int)(v5[8] - v5[6]));
      v216 = 0;
      v217 = 0;
      std::string::_Construct<1,char const *>(&v216, ":", 1);
      *(_OWORD *)v278 = 0;
      v279 = 0;
      std::string::_Construct<1,char const *>(v278, "\"", 1);
      v212 = 0;
      v213 = 0;
      std::string::_Construct<1,char const *>(&v212, "\"", 1);
      v8 = std::operator+<char>(v206, &v212, "tail length");
      LOBYTE(v9) = v194[0];
      std::string::string(v204, v9, v8, v278);
      LOBYTE(v10) = v194[0];
      std::string::string(v207, v10, v204, &v216);
      LOBYTE(v11) = v194[0];
      std::string::string(v200, v11, v207, &v210);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v280,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Sequencer",
        "HeaderCheckFailed",
        "insufficint packet size for the header",
        (__int64)v200);
      std::string::_Tidy_deallocate(v207);
      std::string::_Tidy_deallocate(v204);
      std::string::_Tidy_deallocate(v206);
      std::string::_Tidy_deallocate(&v212);
      std::string::_Tidy_deallocate(v278);
      std::string::_Tidy_deallocate(&v216);
      std::string::_Tidy_deallocate(&v210);
    }
    goto LABEL_14;
  }
  v195[0] = 0;
  Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v4, &v199);
  LOBYTE(v194[0]) = 0;
  Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v5, &v197);
  Microsoft::Basix::Containers::FlexIBuffer::Extract<unsigned char>(v5, v194);
  v13 = LOBYTE(v194[0]);
  v14 = *((_QWORD *)v5 + 3);
  v15 = *((_QWORD *)v5 + 4);
  if ( v15 - v14 < (unsigned __int64)LOBYTE(v194[0]) )
  {
    *(_OWORD *)v280 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v280);
    if ( *(_QWORD *)v280 && *(_BYTE *)(*(_QWORD *)v280 + 128LL) )
    {
      v17 = v5[8] - v5[6];
      v216 = 0;
      v217 = 0;
      std::string::_Construct<1,char const *>(
        &v216,
        "RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck:  insufficint packet size for the header ext"
        "ension(%d), tail size=%d",
        136,
        v16);
      LOBYTE(v18) = v13;
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned char,int>(
        (unsigned int)v280,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v216,
        v18,
        v17);
      std::string::_Tidy_deallocate(&v216);
    }
    v19 = *(volatile signed __int32 **)&v280[2];
    if ( *(_QWORD *)&v280[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v280[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    *(_OWORD *)v280 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v280);
    if ( *(_QWORD *)v280 && *(_BYTE *)(*(_QWORD *)v280 + 128LL) )
    {
      v203 = v200;
      std::_Integral_to_string<char,int>(&v220, (unsigned int)(v5[8] - v5[6]));
      v230 = 0;
      v231 = 0;
      std::string::_Construct<1,char const *>(&v230, ":", 1);
      v243 = 0;
      v244 = 0;
      std::string::_Construct<1,char const *>(&v243, "\"", 1);
      v248 = 0;
      v249 = 0;
      std::string::_Construct<1,char const *>(&v248, "\"", 1);
      v20 = std::operator+<char>(v214, &v248, "tail length");
      LOBYTE(v21) = v194[0];
      std::string::string(&v222, v21, v20, &v243);
      LOBYTE(v22) = v194[0];
      std::string::string(&v224, v22, &v222, &v230);
      LOBYTE(v23) = v194[0];
      std::string::string(v200, v23, &v224, &v220);
      std::_Integral_to_string<char,int>(&v226, v13);
      *(_OWORD *)v278 = 0;
      v279 = 0;
      std::string::_Construct<1,char const *>(v278, ":", 1);
      v212 = 0;
      v213 = 0;
      std::string::_Construct<1,char const *>(&v212, "\"", 1);
      v216 = 0;
      v217 = 0;
      std::string::_Construct<1,char const *>(&v216, "\"", 1);
      v24 = std::operator+<char>(v206, &v216, "header extension size");
      LOBYTE(v25) = v194[0];
      std::string::string(&v210, v25, v24, &v212);
      LOBYTE(v26) = v194[0];
      std::string::string(v204, v26, &v210, v278);
      LOBYTE(v27) = v194[0];
      std::string::string(v207, v27, v204, &v226);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string>(
        (int)v280,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Sequencer",
        "HeaderCheckFailed",
        "insufficint packet size for the header extension",
        (__int64)v207,
        (__int64)v200);
      std::string::_Tidy_deallocate(v204);
      std::string::_Tidy_deallocate(&v210);
      std::string::_Tidy_deallocate(v206);
      std::string::_Tidy_deallocate(&v216);
      std::string::_Tidy_deallocate(&v212);
      std::string::_Tidy_deallocate(v278);
      std::string::_Tidy_deallocate(&v226);
      std::string::_Tidy_deallocate(&v224);
      std::string::_Tidy_deallocate(&v222);
      std::string::_Tidy_deallocate(v214);
      std::string::_Tidy_deallocate(&v248);
      std::string::_Tidy_deallocate(&v243);
      std::string::_Tidy_deallocate(&v230);
      std::string::_Tidy_deallocate(&v220);
    }
    goto LABEL_14;
  }
  *((_QWORD *)v5 + 3) = v14 + LOBYTE(v194[0]);
  v28 = v15 - v13 - v14;
  if ( v28 < 2 )
  {
    *(_OWORD *)v280 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v280);
    if ( *(_QWORD *)v280 && *(_BYTE *)(*(_QWORD *)v280 + 128LL) )
    {
      std::string::string(
        v200,
        "RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: insufficient packet length for seqnum");
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
        v280,
        "BASIX_DCT",
        v200);
      std::string::_Tidy_deallocate(v200);
    }
    v29 = *(volatile signed __int32 **)&v280[2];
    if ( *(_QWORD *)&v280[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v280[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
    *(_OWORD *)v280 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v280);
    if ( *(_QWORD *)v280 && *(_BYTE *)(*(_QWORD *)v280 + 128LL) )
    {
      _mm_lfence();
      std::_Integral_to_string<char,int>(&v210, v28);
      v30 = std::string::string(v218, ":");
      v31 = std::string::string(v219, "\"");
      v32 = std::string::string(v214, "\"");
      v33 = std::operator+<char>(v206, v32, "tail length");
      LOBYTE(v34) = v194[0];
      std::string::string(v204, v34, v33, v31);
      LOBYTE(v35) = v194[0];
      std::string::string(v207, v35, v204, v30);
      LOBYTE(v36) = v194[0];
      std::string::string(v200, v36, v207, &v210);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v280,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Sequencer",
        "HeaderCheckFailed",
        "insufficint packet size for checksum",
        (__int64)v200);
      std::string::_Tidy_deallocate(v207);
      std::string::_Tidy_deallocate(v204);
      std::string::_Tidy_deallocate(v206);
      std::string::_Tidy_deallocate(v214);
      std::string::_Tidy_deallocate(v219);
      std::string::_Tidy_deallocate(v218);
      std::string::_Tidy_deallocate(&v210);
    }
    goto LABEL_14;
  }
  v37 = v28 - 2;
  v198 = v28 - 2;
  Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v5, v195);
  Pointer = (Microsoft::Basix::Dct::Rcp *)Microsoft::Basix::Containers::FlexIBuffer::GetPointer(
                                            (Microsoft::Basix::Containers::FlexIBuffer *)v5,
                                            0);
  v203 = (__int64 *)Pointer;
  *((_QWORD *)v5 + 3) -= 2LL;
  v40 = v199;
  v41 = v199;
  LODWORD(v202) = v199;
  if ( (int)(v28 - 2) < v199 )
  {
    *(_OWORD *)v280 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v280);
    if ( *(_QWORD *)v280 && *(_BYTE *)(*(_QWORD *)v280 + 128LL) )
    {
      _mm_lfence();
      v44 = v195[0];
      std::string::string(
        v200,
        "RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: user packet size (%d) smaller than coded si"
        "ze(%d): seqnum=%04x",
        v42,
        v43,
        v189);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,int,unsigned short,unsigned short>(
        (unsigned int)v280,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v200,
        v37,
        v40,
        v44);
      std::string::_Tidy_deallocate(v200);
    }
    v45 = *(volatile signed __int32 **)&v280[2];
    if ( *(_QWORD *)&v280[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v280[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
    *(_OWORD *)v280 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v280);
    if ( *(_QWORD *)v280 && *(_BYTE *)(*(_QWORD *)v280 + 128LL) )
    {
      _mm_lfence();
      v203 = v200;
      std::_Integral_to_string<char,int>(v246, v195[0]);
      v46 = std::string::string(v234, ":");
      v47 = std::string::string(v235, "\"");
      v48 = std::string::string(v236, "\"");
      v49 = std::operator+<char>(v237, v48, "seqnum");
      LOBYTE(v50) = v194[0];
      std::string::string(v245, v50, v49, v47);
      LOBYTE(v51) = v194[0];
      std::string::string(v242, v51, v245, v46);
      LOBYTE(v52) = v194[0];
      std::string::string(v200, v52, v242, v246);
      v215 = v207;
      std::_Integral_to_string<char,int>(&v228, (unsigned int)v202);
      v53 = std::string::string(v238, ":");
      v54 = std::string::string(v239, "\"");
      v55 = std::string::string(v240, "\"");
      v56 = std::operator+<char>(v241, v55, "coded packet length");
      LOBYTE(v57) = v194[0];
      std::string::string(&v220, v57, v56, v54);
      LOBYTE(v58) = v194[0];
      std::string::string(&v222, v58, &v220, v53);
      LOBYTE(v59) = v194[0];
      std::string::string(v207, v59, &v222, &v228);
      std::_Integral_to_string<char,int>(&v224, v37);
      v60 = std::string::string(v218, ":");
      v61 = std::string::string(v219, "\"");
      v62 = std::string::string(v214, "\"");
      v63 = std::operator+<char>(v206, v62, "user packet length");
      LOBYTE(v64) = v194[0];
      std::string::string(&v226, v64, v63, v61);
      LOBYTE(v65) = v194[0];
      std::string::string(&v210, v65, &v226, v60);
      LOBYTE(v66) = v194[0];
      std::string::string(v204, v66, &v210, &v224);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
        (int)v280,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Sequencer",
        "HeaderCheckFailed",
        "user packet size smaller than coded size",
        (__int64)v204,
        (__int64)v207,
        (__int64)v200);
      std::string::_Tidy_deallocate(&v210);
      std::string::_Tidy_deallocate(&v226);
      std::string::_Tidy_deallocate(v206);
      std::string::_Tidy_deallocate(v214);
      std::string::_Tidy_deallocate(v219);
      std::string::_Tidy_deallocate(v218);
      std::string::_Tidy_deallocate(&v224);
      std::string::_Tidy_deallocate(&v222);
      std::string::_Tidy_deallocate(&v220);
      std::string::_Tidy_deallocate(v241);
      std::string::_Tidy_deallocate(v240);
      std::string::_Tidy_deallocate(v239);
      std::string::_Tidy_deallocate(v238);
      std::string::_Tidy_deallocate(&v228);
      std::string::_Tidy_deallocate(v242);
      std::string::_Tidy_deallocate(v245);
      std::string::_Tidy_deallocate(v237);
      std::string::_Tidy_deallocate(v236);
      std::string::_Tidy_deallocate(v235);
      std::string::_Tidy_deallocate(v234);
      std::string::_Tidy_deallocate(v246);
    }
LABEL_14:
    v12 = *(volatile signed __int32 **)&v280[2];
    if ( !*(_QWORD *)&v280[2] )
      return v196;
    if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v280[2] + 8LL)) )
      return v196;
    (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
    if ( _InterlockedDecrement(v12 + 3) )
      return v196;
    goto LABEL_129;
  }
  v215 = (__int64 *)v199;
  v194[0] = Microsoft::Basix::Dct::Rcp::compute16bitOnesComplementChecksum(Pointer, (const unsigned __int8 *)v199, v39);
  v67 = v197;
  if ( v197 != v194[0] )
  {
    *(_OWORD *)v280 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v280);
    if ( *(_QWORD *)v280 && *(_BYTE *)(*(_QWORD *)v280 + 128LL) )
    {
      _mm_lfence();
      v69 = *(_QWORD *)(a1 + 1488);
      v70 = *(_QWORD *)(a1 + 1584);
      v71 = v195[0];
      v230 = 0;
      v231 = 0;
      std::string::_Construct<1,char const *>(
        &v230,
        "RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: seqnum=%04x, crc16 mismatch: coded(%04x), c"
        "alc(%04x), sizes: coded(%d), actual(%d), expected seqnum=%04x, numPacketsInWaiting=%d",
        197,
        v68,
        v189,
        Str,
        v191,
        v192,
        v193);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned short,unsigned short,unsigned short,unsigned short,int,unsigned __int64,unsigned __int64>(
        (unsigned int)v280,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v230,
        v71,
        v67,
        v194[0],
        v40,
        v37,
        v70,
        v69);
      std::string::_Tidy_deallocate(&v230);
    }
    v72 = *(volatile signed __int32 **)&v280[2];
    if ( *(_QWORD *)&v280[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v280[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
        if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
      }
    }
    *(_OWORD *)v278 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v278);
    if ( *(_QWORD *)v278 && *(_BYTE *)(*(_QWORD *)v278 + 128LL) )
    {
      _mm_lfence();
      v254 = v273;
      v73 = v209;
      std::_Integral_to_string<char,unsigned __int64>(v206, *(_QWORD *)(v209 + 1488));
      *(_OWORD *)v200 = 0;
      v201 = 0;
      std::string::_Construct<1,char const *>(v200, ":", 1);
      *(_OWORD *)v207 = 0;
      v208 = 0;
      std::string::_Construct<1,char const *>(v207, "\"", 1);
      *(_OWORD *)v204 = 0;
      v205 = 0;
      std::string::_Construct<1,char const *>(v204, "\"", 1);
      v74 = std::operator+<char>(v247, v204, "num of packets in waiting");
      LOBYTE(v75) = v194[0];
      std::string::string(v214, v75, v74, v207);
      LOBYTE(v76) = v194[0];
      std::string::string(v219, v76, v214, v200);
      LOBYTE(v77) = v194[0];
      std::string::string(v273, v77, v219, v206);
      v250 = v271;
      std::_Integral_to_string<char,unsigned __int64>(v218, *(_QWORD *)(v73 + 1584));
      v210 = 0;
      v211 = 0;
      std::string::_Construct<1,char const *>(&v210, ":", 1);
      v226 = 0;
      v227 = 0;
      std::string::_Construct<1,char const *>(&v226, "\"", 1);
      v224 = 0;
      v225 = 0;
      std::string::_Construct<1,char const *>(&v224, "\"", 1);
      v78 = std::operator+<char>(v253, &v224, "expected seqnum");
      LOBYTE(v79) = v194[0];
      std::string::string(v241, v79, v78, &v226);
      LOBYTE(v80) = v194[0];
      std::string::string(v240, v80, v241, &v210);
      LOBYTE(v81) = v194[0];
      std::string::string(v271, v81, v240, v218);
      v251 = v272;
      std::_Integral_to_string<char,int>(v239, v195[0]);
      v222 = 0;
      v223 = 0;
      std::string::_Construct<1,char const *>(&v222, ":", 1);
      v220 = 0;
      v221 = 0;
      std::string::_Construct<1,char const *>(&v220, "\"", 1);
      v228 = 0;
      v229 = 0;
      std::string::_Construct<1,char const *>(&v228, "\"", 1);
      v82 = std::operator+<char>(v252, &v228, "seqnum");
      LOBYTE(v83) = v194[0];
      std::string::string(v238, v83, v82, &v220);
      LOBYTE(v84) = v194[0];
      std::string::string(v237, v84, v238, &v222);
      LOBYTE(v85) = v194[0];
      std::string::string(v272, v85, v237, v239);
      v232 = v266;
      v86 = (int)v202;
      std::_Integral_to_string<char,int>(v236, (unsigned int)v202);
      memset(v242, 0, sizeof(v242));
      std::string::_Construct<1,char const *>(v242, ":", 1);
      memset(v245, 0, sizeof(v245));
      std::string::_Construct<1,char const *>(v245, "\"", 1);
      memset(v246, 0, sizeof(v246));
      std::string::_Construct<1,char const *>(v246, "\"", 1);
      v87 = std::operator+<char>(v269, v246, "coded PacketSize");
      LOBYTE(v88) = v194[0];
      std::string::string(v235, v88, v87, v245);
      LOBYTE(v89) = v194[0];
      std::string::string(v234, v89, v235, v242);
      LOBYTE(v90) = v194[0];
      std::string::string(v266, v90, v234, v236);
      v202 = v267;
      std::_Integral_to_string<char,int>(v265, v37);
      memset(v255, 0, sizeof(v255));
      std::string::_Construct<1,char const *>(v255, ":", 1);
      memset(v256, 0, sizeof(v256));
      std::string::_Construct<1,char const *>(v256, "\"", 1);
      memset(v274, 0, sizeof(v274));
      std::string::_Construct<1,char const *>(v274, "\"", 1);
      v91 = std::operator+<char>(v277, v274, "actualPacketSize");
      LOBYTE(v92) = v194[0];
      std::string::string(v264, v92, v91, v256);
      LOBYTE(v93) = v194[0];
      std::string::string(v263, v93, v264, v255);
      LOBYTE(v94) = v194[0];
      std::string::string(v267, v94, v263, v265);
      v233 = v268;
      std::_Integral_to_string<char,int>(v262, v197);
      memset(v270, 0, sizeof(v270));
      std::string::_Construct<1,char const *>(v270, ":", 1);
      v212 = 0;
      v213 = 0;
      std::string::_Construct<1,char const *>(&v212, "\"", 1);
      v216 = 0;
      v217 = 0;
      std::string::_Construct<1,char const *>(&v216, "\"", 1);
      v95 = std::operator+<char>(v276, &v216, "coded CRC value");
      LOBYTE(v96) = v194[0];
      std::string::string(v261, v96, v95, &v212);
      LOBYTE(v97) = v194[0];
      std::string::string(v260, v97, v261, v270);
      LOBYTE(v98) = v194[0];
      std::string::string(v268, v98, v260, v262);
      std::_Integral_to_string<char,int>(v259, v194[0]);
      v248 = 0;
      v249 = 0;
      std::string::_Construct<1,char const *>(&v248, ":", 1);
      v243 = 0;
      v244 = 0;
      std::string::_Construct<1,char const *>(&v243, "\"", 1);
      v230 = 0;
      v231 = 0;
      std::string::_Construct<1,char const *>(&v230, "\"", 1);
      v99 = std::operator+<char>(v275, &v230, "calc CRC value");
      LOBYTE(v100) = v194[0];
      std::string::string(v258, v100, v99, &v243);
      LOBYTE(v101) = v194[0];
      std::string::string(v280, v101, v258, &v248);
      LOBYTE(v102) = v194[0];
      std::string::string(v257, v102, v280, v259);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
        (int)v278,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Sequencer",
        "HeaderCheckFailed",
        "crc mismatch",
        (__int64)v257,
        (__int64)v268,
        (__int64)v267,
        (__int64)v266,
        (__int64)v272,
        (__int64)v271,
        (__int64)v273);
      std::string::_Tidy_deallocate(v280);
      std::string::_Tidy_deallocate(v258);
      std::string::_Tidy_deallocate(v275);
      std::string::_Tidy_deallocate(&v230);
      std::string::_Tidy_deallocate(&v243);
      std::string::_Tidy_deallocate(&v248);
      std::string::_Tidy_deallocate(v259);
      std::string::_Tidy_deallocate(v260);
      std::string::_Tidy_deallocate(v261);
      std::string::_Tidy_deallocate(v276);
      std::string::_Tidy_deallocate(&v216);
      std::string::_Tidy_deallocate(&v212);
      std::string::_Tidy_deallocate(v270);
      std::string::_Tidy_deallocate(v262);
      std::string::_Tidy_deallocate(v263);
      std::string::_Tidy_deallocate(v264);
      std::string::_Tidy_deallocate(v277);
      std::string::_Tidy_deallocate(v274);
      std::string::_Tidy_deallocate(v256);
      std::string::_Tidy_deallocate(v255);
      std::string::_Tidy_deallocate(v265);
      std::string::_Tidy_deallocate(v234);
      std::string::_Tidy_deallocate(v235);
      std::string::_Tidy_deallocate(v269);
      std::string::_Tidy_deallocate(v246);
      std::string::_Tidy_deallocate(v245);
      std::string::_Tidy_deallocate(v242);
      std::string::_Tidy_deallocate(v236);
      std::string::_Tidy_deallocate(v237);
      std::string::_Tidy_deallocate(v238);
      std::string::_Tidy_deallocate(v252);
      std::string::_Tidy_deallocate(&v228);
      std::string::_Tidy_deallocate(&v220);
      std::string::_Tidy_deallocate(&v222);
      std::string::_Tidy_deallocate(v239);
      std::string::_Tidy_deallocate(v240);
      std::string::_Tidy_deallocate(v241);
      std::string::_Tidy_deallocate(v253);
      std::string::_Tidy_deallocate(&v224);
      std::string::_Tidy_deallocate(&v226);
      std::string::_Tidy_deallocate(&v210);
      std::string::_Tidy_deallocate(v218);
      std::string::_Tidy_deallocate(v219);
      std::string::_Tidy_deallocate(v214);
      std::string::_Tidy_deallocate(v247);
      std::string::_Tidy_deallocate(v204);
      std::string::_Tidy_deallocate(v207);
      std::string::_Tidy_deallocate(v200);
      std::string::_Tidy_deallocate(v206);
    }
    else
    {
      v86 = (int)v202;
    }
    v103 = *(volatile signed __int32 **)&v278[2];
    if ( *(_QWORD *)&v278[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v278[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v103)(v103);
        if ( _InterlockedExchangeAdd(v103 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v103 + 8LL))(v103);
      }
    }
    v202 = (__int64 *)(v209 + 1336);
    v104 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned short,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo>>,0>>::_Try_emplace<unsigned short const &,>(
                        v209 + 1336,
                        &v212,
                        v195);
    v209 = v104;
    v105 = *(_DWORD *)(v104 + 20);
    *(_DWORD *)(v104 + 20) = v105 + 1;
    if ( v105 )
    {
      if ( *(_WORD *)(v104 + 24) != v197
        || *(_WORD *)(v104 + 26) != v194[0]
        || *(_DWORD *)(v104 + 28) != v86
        || *(_DWORD *)(v104 + 32) != v198 )
      {
        *(_OWORD *)v278 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v278);
        if ( *(_QWORD *)v278 && *(_BYTE *)(*(_QWORD *)v278 + 128LL) )
        {
          v108 = *(_DWORD *)(v104 + 32);
          v109 = *(_DWORD *)(v104 + 28);
          v110 = *(_WORD *)(v104 + 26);
          v111 = *(_WORD *)(v104 + 24);
          v112 = v195[0];
          v113 = *(_DWORD *)(v104 + 20);
          std::string::string(
            v206,
            "RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: subsequent mismatch cnt=%d, seqnum=%04x"
            ", recorded: CodedCRC(%04x), calcCRC(%04x), codedSize(%d), actualSize(%d)",
            v106,
            v107,
            v189,
            Str,
            v191,
            v192);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned int,unsigned short,unsigned short,unsigned short,unsigned int,unsigned int>(
            (unsigned int)v278,
            (unsigned int)"BASIX_DCT",
            (unsigned int)v206,
            v113,
            v112,
            v111,
            v110,
            v109,
            v108);
          std::string::_Tidy_deallocate(v206);
          v104 = v209;
        }
        v114 = *(volatile signed __int32 **)&v278[2];
        if ( *(_QWORD *)&v278[2] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v278[2] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v114)(v114);
            if ( _InterlockedExchangeAdd(v114 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v114 + 8LL))(v114);
          }
        }
        *(_OWORD *)v278 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v278);
        if ( *(_QWORD *)v278 && *(_BYTE *)(*(_QWORD *)v278 + 128LL) )
        {
          *(_QWORD *)v280 = v206;
          std::_Integral_to_string<char,int>(v266, v195[0]);
          v115 = std::string::string(v256, ":");
          v116 = std::string::string(v255, "\"");
          v117 = std::string::string(v246, "\"");
          v118 = std::operator+<char>(v245, v117, "seqnum");
          LOBYTE(v119) = v194[0];
          std::string::string(v267, v119, v118, v116);
          LOBYTE(v120) = v194[0];
          std::string::string(v268, v120, v267, v115);
          LOBYTE(v121) = v194[0];
          std::string::string(v206, v121, v268, v266);
          v233 = v214;
          std::_Integral_to_string<char,unsigned int>(v257, *(unsigned int *)(v104 + 28));
          v122 = std::string::string(v242, ":");
          v123 = std::string::string(&v228, "\"");
          v124 = std::string::string(&v220, "\"");
          v125 = std::operator+<char>(&v222, v124, "coded PacketSize");
          LOBYTE(v126) = v194[0];
          std::string::string(v258, v126, v125, v123);
          LOBYTE(v127) = v194[0];
          std::string::string(v259, v127, v258, v122);
          LOBYTE(v128) = v194[0];
          std::string::string(v214, v128, v259, v257);
          v232 = v219;
          std::_Integral_to_string<char,unsigned int>(v260, *(unsigned int *)(v104 + 32));
          v129 = std::string::string(&v224, ":");
          v130 = std::string::string(&v226, "\"");
          v131 = std::string::string(&v210, "\"");
          v132 = std::operator+<char>(v204, v131, "actualPacketSize");
          LOBYTE(v133) = v194[0];
          std::string::string(v261, v133, v132, v130);
          LOBYTE(v134) = v194[0];
          std::string::string(v262, v134, v261, v129);
          LOBYTE(v135) = v194[0];
          std::string::string(v219, v135, v262, v260);
          v251 = v218;
          std::_Integral_to_string<char,int>(v263, *(unsigned __int16 *)(v104 + 24));
          v136 = std::string::string(v207, ":");
          v137 = std::string::string(v200, "\"");
          v138 = std::string::string(v273, "\"");
          v139 = std::operator+<char>(v271, v138, "coded CRC value");
          LOBYTE(v140) = v194[0];
          std::string::string(v264, v140, v139, v137);
          LOBYTE(v141) = v194[0];
          std::string::string(v265, v141, v264, v136);
          LOBYTE(v142) = v194[0];
          std::string::string(v218, v142, v265, v263);
          v250 = v241;
          std::_Integral_to_string<char,int>(v234, *(unsigned __int16 *)(v104 + 26));
          v143 = std::string::string(v272, ":");
          v144 = std::string::string(v275, "\"");
          v145 = std::string::string(v276, "\"");
          v146 = std::operator+<char>(v277, v145, "calc CRC value");
          LOBYTE(v147) = v194[0];
          std::string::string(v235, v147, v146, v144);
          LOBYTE(v148) = v194[0];
          std::string::string(v236, v148, v235, v143);
          LOBYTE(v149) = v194[0];
          std::string::string(v241, v149, v236, v234);
          std::_Integral_to_string<char,unsigned int>(v237, *(unsigned int *)(v104 + 20));
          v150 = std::string::string(v269, ":");
          v151 = std::string::string(v252, "\"");
          v152 = std::string::string(v253, "\"");
          v153 = std::operator+<char>(v247, v152, "count");
          LOBYTE(v154) = v194[0];
          std::string::string(v238, v154, v153, v151);
          LOBYTE(v155) = v194[0];
          std::string::string(v239, v155, v238, v150);
          LOBYTE(v156) = v194[0];
          std::string::string(v240, v156, v239, v237);
          Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string>(
            (int)v278,
            (int)"RD_CHECKPOINT",
            0,
            (int)"Sequencer",
            "HeaderCheckFailed",
            "subsequent crc mismatch: recorded crc info",
            (__int64)v240,
            (__int64)v241,
            (__int64)v218,
            (__int64)v219,
            (__int64)v214,
            (__int64)v206);
          std::string::_Tidy_deallocate(v239);
          std::string::_Tidy_deallocate(v238);
          std::string::_Tidy_deallocate(v247);
          std::string::_Tidy_deallocate(v253);
          std::string::_Tidy_deallocate(v252);
          std::string::_Tidy_deallocate(v269);
          std::string::_Tidy_deallocate(v237);
          std::string::_Tidy_deallocate(v236);
          std::string::_Tidy_deallocate(v235);
          std::string::_Tidy_deallocate(v277);
          std::string::_Tidy_deallocate(v276);
          std::string::_Tidy_deallocate(v275);
          std::string::_Tidy_deallocate(v272);
          std::string::_Tidy_deallocate(v234);
          std::string::_Tidy_deallocate(v265);
          std::string::_Tidy_deallocate(v264);
          std::string::_Tidy_deallocate(v271);
          std::string::_Tidy_deallocate(v273);
          std::string::_Tidy_deallocate(v200);
          std::string::_Tidy_deallocate(v207);
          std::string::_Tidy_deallocate(v263);
          std::string::_Tidy_deallocate(v262);
          std::string::_Tidy_deallocate(v261);
          std::string::_Tidy_deallocate(v204);
          std::string::_Tidy_deallocate(&v210);
          std::string::_Tidy_deallocate(&v226);
          std::string::_Tidy_deallocate(&v224);
          std::string::_Tidy_deallocate(v260);
          std::string::_Tidy_deallocate(v259);
          std::string::_Tidy_deallocate(v258);
          std::string::_Tidy_deallocate(&v222);
          std::string::_Tidy_deallocate(&v220);
          std::string::_Tidy_deallocate(&v228);
          std::string::_Tidy_deallocate(v242);
          std::string::_Tidy_deallocate(v257);
          std::string::_Tidy_deallocate(v268);
          std::string::_Tidy_deallocate(v267);
          std::string::_Tidy_deallocate(v245);
          std::string::_Tidy_deallocate(v246);
          std::string::_Tidy_deallocate(v255);
          std::string::_Tidy_deallocate(v256);
          std::string::_Tidy_deallocate(v266);
        }
        v157 = *(volatile signed __int32 **)&v278[2];
        if ( *(_QWORD *)&v278[2] )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v278[2] + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v157)(v157);
            if ( !_InterlockedDecrement(v157 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v157 + 8LL))(v157);
          }
        }
      }
      if ( *(_DWORD *)(v104 + 20) > 1u )
      {
        v196 = 1;
        *(_OWORD *)v278 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v278);
        if ( *(_QWORD *)v278 && *(_BYTE *)(*(_QWORD *)v278 + 128LL) )
        {
          v159 = v195[0];
          std::string::string(
            v206,
            "RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: mismatch forced restored: seqnum=%04x",
            v158);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned short>(
            v278,
            "BASIX_DCT",
            v206,
            v159);
          std::string::_Tidy_deallocate(v206);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v278);
        *(_OWORD *)v278 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v278);
        if ( *(_QWORD *)v278 && *(_BYTE *)(*(_QWORD *)v278 + 128LL) )
        {
          std::_Integral_to_string<char,int>(v218, v195[0]);
          v160 = std::string::string(v269, ":");
          v161 = std::string::string(v252, "\"");
          v162 = std::string::string(v253, "\"");
          v163 = std::operator+<char>(v247, v162, "seqnum");
          LOBYTE(v164) = v194[0];
          std::string::string(v219, v164, v163, v161);
          LOBYTE(v165) = v194[0];
          std::string::string(v214, v165, v219, v160);
          LOBYTE(v166) = v194[0];
          std::string::string(v206, v166, v214, v218);
          Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
            (int)v278,
            (int)"RD_CHECKPOINT",
            0,
            (int)"Sequencer",
            "HeaderCheckFailed",
            "mismatch forced restored:",
            (__int64)v206);
          std::string::_Tidy_deallocate(v214);
          std::string::_Tidy_deallocate(v219);
          std::string::_Tidy_deallocate(v247);
          std::string::_Tidy_deallocate(v253);
          std::string::_Tidy_deallocate(v252);
          std::string::_Tidy_deallocate(v269);
          std::string::_Tidy_deallocate(v218);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v278);
        std::_Hash<std::_Umap_traits<unsigned short,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo>>,0>>::_Erase<unsigned short>(
          v202,
          v195);
      }
    }
    else
    {
      *(_WORD *)(v104 + 24) = v197;
      *(_WORD *)(v104 + 26) = v194[0];
      *(_DWORD *)(v104 + 28) = v86;
      *(_DWORD *)(v104 + 32) = v198;
      if ( v195[0] == 1 )
        Microsoft::Basix::Instrumentation::TraceManager::Hexdump<Microsoft::Basix::TraceNormal,>(
          "BASIX_DCT",
          v203,
          v215,
          "receive seqnum = 1:");
    }
    return v196;
  }
  v203 = (__int64 *)(a1 + 1336);
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned short,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo>>,0>>::find(
                    a1 + 1336,
                    v280,
                    v195) != *(_QWORD *)(a1 + 1344) )
  {
    *(_OWORD *)v278 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v278);
    if ( *(_QWORD *)v278 && *(_BYTE *)(*(_QWORD *)v278 + 128LL) )
    {
      v167 = v195[0];
      *(_OWORD *)v200 = 0;
      v201 = 0;
      std::string::_Construct<1,char const *>(
        v200,
        "RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: mismatch restored: seqnum=%04x",
        99);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned short>(
        v278,
        "BASIX_DCT",
        v200,
        v167);
      std::string::_Tidy_deallocate(v200);
    }
    v168 = *(volatile signed __int32 **)&v278[2];
    if ( *(_QWORD *)&v278[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v278[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v168)(v168);
        if ( _InterlockedExchangeAdd(v168 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v168 + 8LL))(v168);
      }
    }
    *(_OWORD *)v278 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v278);
    if ( *(_QWORD *)v278 && *(_BYTE *)(*(_QWORD *)v278 + 128LL) )
    {
      std::_Integral_to_string<char,int>(v218, v195[0]);
      *(_OWORD *)v204 = 0;
      v205 = 0;
      std::string::_Construct<1,char const *>(v204, ":", 1);
      *(_OWORD *)v207 = 0;
      v208 = 0;
      std::string::_Construct<1,char const *>(v207, "\"", 1);
      *(_OWORD *)v200 = 0;
      v201 = 0;
      std::string::_Construct<1,char const *>(v200, "\"", 1);
      v169 = std::operator+<char>(v247, v200, "seqnum");
      LOBYTE(v170) = v194[0];
      std::string::string(v219, v170, v169, v207);
      LOBYTE(v171) = v194[0];
      std::string::string(v214, v171, v219, v204);
      LOBYTE(v172) = v194[0];
      std::string::string(v206, v172, v214, v218);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v278,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Sequencer",
        "HeaderCheckFailed",
        "mismatch restored:",
        (__int64)v206);
      std::string::_Tidy_deallocate(v214);
      std::string::_Tidy_deallocate(v219);
      std::string::_Tidy_deallocate(v247);
      std::string::_Tidy_deallocate(v200);
      std::string::_Tidy_deallocate(v207);
      std::string::_Tidy_deallocate(v204);
      std::string::_Tidy_deallocate(v218);
    }
    v173 = *(volatile signed __int32 **)&v278[2];
    if ( *(_QWORD *)&v278[2] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v278[2] + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v173)(v173);
        if ( !_InterlockedDecrement(v173 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v173 + 8LL))(v173);
      }
    }
    std::_Hash<std::_Umap_traits<unsigned short,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo>>,0>>::_Erase<unsigned short>(
      v203,
      v195);
    v41 = (int)v202;
  }
  v196 = 1;
  if ( (int)v37 <= v41 )
    return v196;
  *((_QWORD *)v5 + 3) += (char *)v215 + 2;
  Microsoft::Basix::Containers::FlexIBuffer::TrimEnd((Microsoft::Basix::Containers::FlexIBuffer *)v5);
  *((_QWORD *)v5 + 3) += -2 - v41;
  *(_OWORD *)v278 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v278);
  if ( *(_QWORD *)v278 && *(_BYTE *)(*(_QWORD *)v278 + 128LL) )
  {
    _mm_lfence();
    v175 = v195[0];
    *(_OWORD *)v200 = 0;
    v201 = 0;
    std::string::_Construct<1,char const *>(
      v200,
      "RdpNanoStreamWrapper::SequencerReader::OnPacketSequencerHeaderCheck: seqnum=%04x, received length(%d) longer than "
      "coded length(%d), but trim works successfully",
      159,
      v174,
      v189);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned short,int,unsigned short>(
      (unsigned int)v278,
      (unsigned int)"BASIX_DCT",
      (unsigned int)v200,
      v175,
      v37,
      v199);
    std::string::_Tidy_deallocate(v200);
  }
  v176 = *(volatile signed __int32 **)&v278[2];
  if ( *(_QWORD *)&v278[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v278[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v176)(v176);
      if ( _InterlockedExchangeAdd(v176 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v176 + 8LL))(v176);
    }
  }
  *(_OWORD *)v278 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v278);
  if ( *(_QWORD *)v278 && *(_BYTE *)(*(_QWORD *)v278 + 128LL) )
  {
    _mm_lfence();
    *(_QWORD *)v280 = v206;
    std::_Integral_to_string<char,int>(v234, v195[0]);
    v228 = 0;
    v229 = 0;
    std::string::_Construct<1,char const *>(&v228, ":", 1);
    v220 = 0;
    v221 = 0;
    std::string::_Construct<1,char const *>(&v220, "\"", 1);
    v222 = 0;
    v223 = 0;
    std::string::_Construct<1,char const *>(&v222, "\"", 1);
    v177 = std::operator+<char>(v252, &v222, "seqnum");
    LOBYTE(v178) = v194[0];
    std::string::string(v235, v178, v177, &v220);
    LOBYTE(v179) = v194[0];
    std::string::string(v236, v179, v235, &v228);
    LOBYTE(v180) = v194[0];
    std::string::string(v206, v180, v236, v234);
    v233 = v214;
    std::_Integral_to_string<char,int>(v237, (unsigned int)v202);
    v224 = 0;
    v225 = 0;
    std::string::_Construct<1,char const *>(&v224, ":", 1);
    v226 = 0;
    v227 = 0;
    std::string::_Construct<1,char const *>(&v226, "\"", 1);
    v210 = 0;
    v211 = 0;
    std::string::_Construct<1,char const *>(&v210, "\"", 1);
    v181 = std::operator+<char>(v253, &v210, "coded packet length");
    LOBYTE(v182) = v194[0];
    std::string::string(v238, v182, v181, &v226);
    LOBYTE(v183) = v194[0];
    std::string::string(v239, v183, v238, &v224);
    LOBYTE(v184) = v194[0];
    std::string::string(v214, v184, v239, v237);
    std::_Integral_to_string<char,int>(v240, v37);
    *(_OWORD *)v204 = 0;
    v205 = 0;
    std::string::_Construct<1,char const *>(v204, ":", 1);
    *(_OWORD *)v207 = 0;
    v208 = 0;
    std::string::_Construct<1,char const *>(v207, "\"", 1);
    *(_OWORD *)v200 = 0;
    v201 = 0;
    std::string::_Construct<1,char const *>(v200, "\"", 1);
    v185 = std::operator+<char>(v247, v200, "user packet length");
    LOBYTE(v186) = v194[0];
    std::string::string(v241, v186, v185, v207);
    LOBYTE(v187) = v194[0];
    std::string::string(v218, v187, v241, v204);
    LOBYTE(v188) = v194[0];
    std::string::string(v219, v188, v218, v240);
    Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
      (int)v278,
      (int)"RD_CHECKPOINT",
      0,
      (int)"Sequencer",
      "HeaderCheckFailed",
      "user packet size larger than coded size, but trim worked successfully",
      (__int64)v219,
      (__int64)v214,
      (__int64)v206);
    std::string::_Tidy_deallocate(v218);
    std::string::_Tidy_deallocate(v241);
    std::string::_Tidy_deallocate(v247);
    std::string::_Tidy_deallocate(v200);
    std::string::_Tidy_deallocate(v207);
    std::string::_Tidy_deallocate(v204);
    std::string::_Tidy_deallocate(v240);
    std::string::_Tidy_deallocate(v239);
    std::string::_Tidy_deallocate(v238);
    std::string::_Tidy_deallocate(v253);
    std::string::_Tidy_deallocate(&v210);
    std::string::_Tidy_deallocate(&v226);
    std::string::_Tidy_deallocate(&v224);
    std::string::_Tidy_deallocate(v237);
    std::string::_Tidy_deallocate(v236);
    std::string::_Tidy_deallocate(v235);
    std::string::_Tidy_deallocate(v252);
    std::string::_Tidy_deallocate(&v222);
    std::string::_Tidy_deallocate(&v220);
    std::string::_Tidy_deallocate(&v228);
    std::string::_Tidy_deallocate(v234);
  }
  v12 = *(volatile signed __int32 **)&v278[2];
  if ( !*(_QWORD *)&v278[2] )
    return v196;
  if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v278[2] + 8LL)) )
    return v196;
  (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
  if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) != 1 )
    return v196;
LABEL_129:
  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
  return v196;
}

```

## disassembly

```asm
0x1801bc1e0  mov     [rsp-8+arg_10], rbx
0x1801bc1e5  push    rbp
0x1801bc1e6  push    rsi
0x1801bc1e7  push    rdi
0x1801bc1e8  push    r12
0x1801bc1ea  push    r13
0x1801bc1ec  push    r14
0x1801bc1ee  push    r15
0x1801bc1f0  lea     rbp, [rsp-700h]
0x1801bc1f8  mov     eax, 800h
0x1801bc1fd  call    _alloca_probe
0x1801bc202  sub     rsp, rax
0x1801bc205  mov     rax, cs:__security_cookie
0x1801bc20c  xor     rax, rsp
0x1801bc20f  mov     [rbp+730h+var_40], rax
0x1801bc216  mov     r14, rcx
0x1801bc219  mov     [rbp+730h+var_718], rcx
0x1801bc21d  xor     r12d, r12d
0x1801bc220  cmp     [rcx+63Ah], r12b
0x1801bc227  jnz     short loc_1801BC233
0x1801bc229  lea     eax, [r12+1]
0x1801bc22e  jmp     loc_1801BEF92
0x1801bc233  mov     [rsp+830h+var_7B8], r12b
0x1801bc238  mov     rcx, [rdx]
0x1801bc23b  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x1801bc240  mov     rdi, rax
0x1801bc243  mov     rcx, [rax+20h]
0x1801bc247  sub     rcx, [rax+18h]
0x1801bc24b  cmp     rcx, 5
0x1801bc24f  jnb     loc_1801BC512
0x1801bc255  xorps   xmm0, xmm0
0x1801bc258  movups  xmmword ptr [rbp+730h+var_60], xmm0
0x1801bc25f  lea     rcx, [rbp+730h+var_60]
0x1801bc266  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1801bc26b  nop
0x1801bc26c  mov     rax, qword ptr [rbp+730h+var_60]
0x1801bc273  test    rax, rax
0x1801bc276  jz      short loc_1801BC2D2
0x1801bc278  cmp     [rax+80h], r12b
0x1801bc27f  jz      short loc_1801BC2D2
0x1801bc281  mov     ebx, [rdi+20h]
0x1801bc284  sub     ebx, [rdi+18h]
0x1801bc287  xorps   xmm0, xmm0
0x1801bc28a  movups  [rbp+730h+var_6F0], xmm0
0x1801bc28e  xorps   xmm1, xmm1
0x1801bc291  movdqu  [rbp+730h+var_6E0], xmm1
0x1801bc296  mov     r8d, 6Eh ; 'n'
0x1801bc29c  lea     rdx, aRdpnanostreamw_1; "RdpNanoStreamWrapper::SequencerReader::"...
0x1801bc2a3  lea     rcx, [rbp+730h+var_6F0]
0x1801bc2a7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801bc2ac  nop
0x1801bc2ad  mov     r9d, ebx
0x1801bc2b0  lea     r8, [rbp+730h+var_6F0]
0x1801bc2b4  lea     rdx, aRdpnanostream; "RDPNANOSTREAM"
0x1801bc2bb  lea     rcx, [rbp+730h+var_60]
0x1801bc2c2  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@W4ErrorCode@WebsocketException@WebSocket@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@W4ErrorCode@WebsocketException@WebSocket@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode)
0x1801bc2c7  nop
0x1801bc2c8  lea     rcx, [rbp+730h+var_6F0]
0x1801bc2cc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801bc2d1  nop
0x1801bc2d2  or      r13d, 0FFFFFFFFh
0x1801bc2d6  mov     rbx, qword ptr [rbp+730h+var_60+8]
0x1801bc2dd  test    rbx, rbx
0x1801bc2e0  jz      short loc_1801BC31B
0x1801bc2e2  mov     eax, r13d
0x1801bc2e5  lock xadd [rbx+8], eax
0x1801bc2ea  add     eax, r13d
0x1801bc2ed  jnz     short loc_1801BC31B
0x1801bc2ef  mov     rax, [rbx]
0x1801bc2f2  mov     rcx, rbx
0x1801bc2f5  mov     rax, [rax]
0x1801bc2f8  call    cs:__guard_dispatch_icall_fptr
0x1801bc2fe  mov     eax, r13d
0x1801bc301  lock xadd [rbx+0Ch], eax
0x1801bc306  add     eax, r13d
0x1801bc309  jnz     short loc_1801BC31B
0x1801bc30b  mov     rax, [rbx]
0x1801bc30e  mov     rcx, rbx
0x1801bc311  mov     rax, [rax+8]
0x1801bc315  call    cs:__guard_dispatch_icall_fptr
0x1801bc31b  xorps   xmm0, xmm0
0x1801bc31e  movups  xmmword ptr [rbp+730h+var_60], xmm0
0x1801bc325  lea     rcx, [rbp+730h+var_60]
0x1801bc32c  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x1801bc331  nop
0x1801bc332  mov     rax, qword ptr [rbp+730h+var_60]
0x1801bc339  test    rax, rax
0x1801bc33c  jz      loc_1801BC4C5
0x1801bc342  cmp     [rax+80h], r12b
0x1801bc349  jz      loc_1801BC4C5
0x1801bc34f  mov     edx, [rdi+20h]
0x1801bc352  sub     edx, [rdi+18h]
0x1801bc355  lea     rcx, [rbp+730h+var_710]
0x1801bc359  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x1801bc35e  nop
0x1801bc35f  xorps   xmm0, xmm0
0x1801bc362  movups  [rbp+730h+var_6A8], xmm0
0x1801bc369  xorps   xmm1, xmm1
0x1801bc36c  movdqu  [rbp+730h+var_698], xmm1
0x1801bc374  mov     r14d, 1
0x1801bc37a  mov     r8d, r14d
0x1801bc37d  lea     rdx, asc_1803D71C4; ":"
0x1801bc384  lea     rcx, [rbp+730h+var_6A8]
0x1801bc38b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801bc390  nop
0x1801bc391  xorps   xmm0, xmm0
0x1801bc394  movups  xmmword ptr [rbp+730h+var_80], xmm0
0x1801bc39b  xorps   xmm1, xmm1
0x1801bc39e  movdqu  [rbp+730h+var_70], xmm1
0x1801bc3a6  mov     r8d, r14d
0x1801bc3a9  lea     rsi, asc_1803D71C8; "\""
0x1801bc3b0  mov     rdx, rsi
0x1801bc3b3  lea     rcx, [rbp+730h+var_80]
0x1801bc3ba  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801bc3bf  nop
0x1801bc3c0  xorps   xmm0, xmm0
0x1801bc3c3  movups  [rbp+730h+var_6F0], xmm0
0x1801bc3c7  xorps   xmm1, xmm1
0x1801bc3ca  movdqu  [rbp+730h+var_6E0], xmm1
0x1801bc3cf  mov     r8d, r14d
0x1801bc3d2  mov     rdx, rsi
0x1801bc3d5  lea     rcx, [rbp+730h+var_6F0]
0x1801bc3d9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801bc3de  nop
0x1801bc3df  lea     r8, aTailLength; "tail length"
0x1801bc3e6  lea     rdx, [rbp+730h+var_6F0]
0x1801bc3ea  lea     rcx, [rbp+730h+var_758]
0x1801bc3ee  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1801bc3f3  nop
0x1801bc3f4  lea     r9, [rbp+730h+var_80]
0x1801bc3fb  mov     r8, rax
0x1801bc3fe  mov     dl, byte ptr [rsp+830h+var_7C0]
0x1801bc402  lea     rcx, [rbp+730h+var_778]
0x1801bc406  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1801bc40b  nop
0x1801bc40c  lea     r9, [rbp+730h+var_6A8]
0x1801bc413  lea     r8, [rbp+730h+var_778]
0x1801bc417  mov     dl, byte ptr [rsp+830h+var_7C0]
0x1801bc41b  lea     rcx, [rbp+730h+var_738]
0x1801bc41f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1801bc424  nop
0x1801bc425  lea     r9, [rbp+730h+var_710]
0x1801bc429  lea     r8, [rbp+730h+var_738]
0x1801bc42d  mov     dl, byte ptr [rsp+830h+var_7C0]
0x1801bc431  lea     rcx, [rbp+730h+var_7A8]
0x1801bc435  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1801bc43a  lea     rax, [rbp+730h+var_7A8]
0x1801bc43e  mov     [rsp+830h+var_800], rax; __int64
0x1801bc443  lea     rax, aInsufficintPac_0; "insufficint packet size for the header"
0x1801bc44a  mov     [rsp+830h+Str], rax; Str
0x1801bc44f  lea     rax, aHeadercheckfai; "HeaderCheckFailed"
0x1801bc456  mov     [rsp+830h+var_810], rax; char *
0x1801bc45b  lea     r9, aSequencer; "Sequencer"
0x1801bc462  xor     r8d, r8d; int
0x1801bc465  lea     rdx, aRdCheckpoint; "RD_CHECKPOINT"
0x1801bc46c  lea     rcx, [rbp+730h+var_60]; int
0x1801bc473  call    ??$TraceCheckpointMessage@VTraceCheckpoint@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDI111V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,char const *,uint,char const *,char const *,char const *,std::string)
0x1801bc478  nop
0x1801bc479  lea     rcx, [rbp+730h+var_738]
0x1801bc47d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801bc482  nop
0x1801bc483  lea     rcx, [rbp+730h+var_778]
0x1801bc487  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801bc48c  nop
0x1801bc48d  lea     rcx, [rbp+730h+var_758]
0x1801bc491  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801bc496  nop
0x1801bc497  lea     rcx, [rbp+730h+var_6F0]
0x1801bc49b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801bc4a0  nop
0x1801bc4a1  lea     rcx, [rbp+730h+var_80]
0x1801bc4a8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801bc4ad  nop
0x1801bc4ae  lea     rcx, [rbp+730h+var_6A8]
0x1801bc4b5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801bc4ba  nop
0x1801bc4bb  lea     rcx, [rbp+730h+var_710]
0x1801bc4bf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801bc4c4  nop
0x1801bc4c5  mov     rbx, qword ptr [rbp+730h+var_60+8]
0x1801bc4cc  test    rbx, rbx
0x1801bc4cf  jz      loc_1801BEF8E
0x1801bc4d5  mov     eax, r13d
0x1801bc4d8  lock xadd [rbx+8], eax
0x1801bc4dd  add     eax, r13d
0x1801bc4e0  jnz     loc_1801BEF8E
0x1801bc4e6  mov     rax, [rbx]
0x1801bc4e9  mov     rcx, rbx
0x1801bc4ec  mov     rax, [rax]
0x1801bc4ef  call    cs:__guard_dispatch_icall_fptr
0x1801bc4f5  mov     eax, r13d
0x1801bc4f8  lock xadd [rbx+0Ch], eax
0x1801bc4fd  add     eax, r13d
0x1801bc500  jnz     loc_1801BEF8E
0x1801bc506  mov     rax, [rbx]
0x1801bc509  mov     rax, [rax+8]
0x1801bc50d  jmp     loc_1801BEF85
0x1801bc512  mov     [rsp+830h+var_7BC], r12w
0x1801bc518  lea     rdx, [rbp+730h+var_7AC]
0x1801bc51c  mov     rcx, rdi
0x1801bc51f  call    ??$Extract@W4Type@STUNMessage@ICE@Dct@Basix@Microsoft@@@FlexIBuffer@Containers@Basix@Microsoft@@QEAAXAEAW4Type@STUNMessage@ICE@Dct@23@@Z; Microsoft::Basix::Containers::FlexIBuffer::Extract<Microsoft::Basix::Dct::ICE::STUNMessage::Type>(Microsoft::Basix::Dct::ICE::STUNMessage::Type &)
0x1801bc524  mov     byte ptr [rsp+830h+var_7C0], r12b
0x1801bc529  lea     rdx, [rsp+830h+var_7B4]
0x1801bc52e  mov     rcx, rdi
0x1801bc531  call    ??$Extract@W4Type@STUNMessage@ICE@Dct@Basix@Microsoft@@@FlexIBuffer@Containers@Basix@Microsoft@@QEAAXAEAW4Type@STUNMessage@ICE@Dct@23@@Z; Microsoft::Basix::Containers::FlexIBuffer::Extract<Microsoft::Basix::Dct::ICE::STUNMessage::Type>(Microsoft::Basix::Dct::ICE::STUNMessage::Type &)
0x1801bc536  lea     rdx, [rsp+830h+var_7C0]
0x1801bc53b  mov     rcx, rdi
0x1801bc53e  call    ??$Extract@E@FlexIBuffer@Containers@Basix@Microsoft@@QEAAXAEAE@Z; Microsoft::Basix::Containers::FlexIBuffer::Extract<uchar>(uchar &)
0x1801bc543  movzx   r15d, byte ptr [rsp+830h+var_7C0]
0x1801bc549  mov     rdx, [rdi+18h]
0x1801bc54d  mov     rsi, [rdi+20h]
0x1801bc551  mov     rax, rsi
0x1801bc554  sub     rax, rdx
0x1801bc557  cmp     rax, r15
0x1801bc55a  jnb     loc_1801BC955
0x1801bc560  xorps   xmm0, xmm0
0x1801bc563  movups  xmmword ptr [rbp+730h+var_60], xmm0
0x1801bc56a  lea     rcx, [rbp+730h+var_60]
0x1801bc571  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1801bc576  nop
0x1801bc577  mov     rax, qword ptr [rbp+730h+var_60]
0x1801bc57e  test    rax, rax
0x1801bc581  jz      short loc_1801BC5F0
0x1801bc583  cmp     [rax+80h], r12b
0x1801bc58a  jz      short loc_1801BC5F0
0x1801bc58c  mov     ebx, [rdi+20h]
0x1801bc58f  sub     ebx, [rdi+18h]
0x1801bc592  xorps   xmm0, xmm0
0x1801bc595  movups  [rbp+730h+var_6A8], xmm0
0x1801bc59c  xorps   xmm1, xmm1
0x1801bc59f  movdqu  [rbp+730h+var_698], xmm1
0x1801bc5a7  mov     r8d, 88h
0x1801bc5ad  lea     rdx, aRdpnanostreamw; "RdpNanoStreamWrapper::SequencerReader::"...
0x1801bc5b4  lea     rcx, [rbp+730h+var_6A8]
0x1801bc5bb  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801bc5c0  nop
0x1801bc5c1  mov     dword ptr [rsp+830h+var_810], ebx
0x1801bc5c5  mov     r9b, r15b
0x1801bc5c8  lea     r8, [rbp+730h+var_6A8]
0x1801bc5cf  lea     rdx, aBasixDct; "BASIX_DCT"
0x1801bc5d6  lea     rcx, [rbp+730h+var_60]
0x1801bc5dd  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@EH@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@EH@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,uchar,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,uchar,int)
0x1801bc5e2  nop
0x1801bc5e3  lea     rcx, [rbp+730h+var_6A8]
0x1801bc5ea  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801bc5ef  nop
0x1801bc5f0  or      r13d, 0FFFFFFFFh
0x1801bc5f4  mov     rbx, qword ptr [rbp+730h+var_60+8]
0x1801bc5fb  test    rbx, rbx
0x1801bc5fe  jz      short loc_1801BC639
0x1801bc600  mov     eax, r13d
0x1801bc603  lock xadd [rbx+8], eax
0x1801bc608  add     eax, r13d
0x1801bc60b  jnz     short loc_1801BC639
0x1801bc60d  mov     rax, [rbx]
0x1801bc610  mov     rcx, rbx
0x1801bc613  mov     rax, [rax]
0x1801bc616  call    cs:__guard_dispatch_icall_fptr
0x1801bc61c  mov     eax, r13d
0x1801bc61f  lock xadd [rbx+0Ch], eax
0x1801bc624  add     eax, r13d
0x1801bc627  jnz     short loc_1801BC639
0x1801bc629  mov     rax, [rbx]
0x1801bc62c  mov     rcx, rbx
0x1801bc62f  mov     rax, [rax+8]
0x1801bc633  call    cs:__guard_dispatch_icall_fptr
0x1801bc639  xorps   xmm0, xmm0
0x1801bc63c  movups  xmmword ptr [rbp+730h+var_60], xmm0
0x1801bc643  lea     rcx, [rbp+730h+var_60]
0x1801bc64a  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x1801bc64f  nop
0x1801bc650  mov     rax, qword ptr [rbp+730h+var_60]
0x1801bc657  test    rax, rax
0x1801bc65a  jz      loc_1801BC950
0x1801bc660  cmp     [rax+80h], r12b
0x1801bc667  jz      loc_1801BC950
0x1801bc66d  lea     rax, [rbp+730h+var_7A8]
0x1801bc671  mov     [rbp+730h+var_780], rax
0x1801bc675  mov     edx, [rdi+20h]
0x1801bc678  sub     edx, [rdi+18h]
0x1801bc67b  lea     rcx, [rbp+730h+var_648]
0x1801bc682  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x1801bc687  nop
0x1801bc688  xorps   xmm0, xmm0
0x1801bc68b  movups  [rbp+730h+var_5A8], xmm0
0x1801bc692  xorps   xmm1, xmm1
0x1801bc695  movdqu  [rbp+730h+var_598], xmm1
0x1801bc69d  mov     r14d, 1
0x1801bc6a3  mov     r8d, r14d
0x1801bc6a6  lea     rdx, asc_1803D71C4; ":"
0x1801bc6ad  lea     rcx, [rbp+730h+var_5A8]
0x1801bc6b4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801bc6b9  nop
0x1801bc6ba  xorps   xmm0, xmm0
0x1801bc6bd  movups  [rbp+730h+var_458], xmm0
0x1801bc6c4  xorps   xmm1, xmm1
0x1801bc6c7  movdqu  [rbp+730h+var_448], xmm1
0x1801bc6cf  mov     r8d, r14d
0x1801bc6d2  lea     rsi, asc_1803D71C8; "\""
0x1801bc6d9  mov     rdx, rsi
  ... truncated ...
```

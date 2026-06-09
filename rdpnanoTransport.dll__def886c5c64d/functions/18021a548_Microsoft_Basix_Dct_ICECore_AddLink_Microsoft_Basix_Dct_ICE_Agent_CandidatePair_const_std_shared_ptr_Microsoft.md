# Microsoft::Basix::Dct::ICECore::AddLink(Microsoft::Basix::Dct::ICE::Agent::CandidatePair const &,std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase> &)

- ea: `0x18021a548`
- end: `0x18021b001`
- name: `?AddLink@ICECore@Dct@Basix@Microsoft@@IEAAXAEBVCandidatePair@Agent@ICE@234@AEAV?$shared_ptr@VCandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@@Z`
- size: `2745`
- prototype: ``
- caller_count: `1`
- callee_count: `39`
- tags: `service_task, broker_com_uri`

## callers

- `0x180239dd0`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x1800191b4`
- `0x18001979c`
- `0x180024700`
- `0x180024760`
- `0x18002a8ec`
- `0x1800386d0`
- `0x1801dab7c`
- `0x1801dbd34`
- `0x1801e6684`
- `0x1801ee000`
- `0x1801f8b58`
- `0x1801ff198`
- `0x1802014f0`
- `0x180202fa4`
- `0x18020838c`
- `0x18020ba58`
- `0x18020d668`
- `0x180219c90`
- `0x18021a548`
- `0x18021b170`
- `0x18021b1e8`
- `0x18021fe58`
- `0x1802216e4`
- `0x180221dac`
- `0x18023c8f8`
- `0x180241724`
- `0x1802e9b68`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x18021a642`: `AddLink: pre-closing has been called, ignore new link: local=%s, remote=%s`
- `0x18021af67`: `duplicated entry in m_linkContextMap`
- `0x18021aa84`: `AddLinkForChannelCreation: dor =%d, peer=%s, channelId=%d, transport=%p, base=%p`
- `0x18021ac42`: `LinkAddedPhase`
- `0x18021ace0`: `LinkAdded`
- `0x18021acec`: `LinkManagement`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall Microsoft::Basix::Dct::ICECore::AddLink(
        __int64 *a1,
        Microsoft::Basix::Dct::ICE::Candidate **a2,
        Microsoft::Basix::Dct::ICECore::CandidateBase **a3)
{
  Microsoft::Basix::Dct::ICECore::CandidateBase **v3; // r12
  __int16 ChannelId; // bx
  __int64 result; // rax
  __int64 *v8; // rax
  __int64 v9; // rdi
  __int64 *v10; // rax
  const char *v11; // r9
  __int64 v12; // rbx
  volatile signed __int32 *v13; // rbx
  signed __int32 v14; // eax
  bool v15; // zf
  Microsoft::Basix::Dct::ICECore::CandidateBase *v16; // rcx
  Microsoft::Basix::Dct::ICE::Candidate *v17; // rax
  __int64 *TurnServer; // rax
  __int64 v19; // r14
  __int64 v20; // rcx
  volatile signed __int32 *v21; // rbx
  Microsoft::Basix::Dct::ICE::Candidate *v22; // rcx
  Microsoft::Basix::Dct::ICE::Candidate *v23; // rcx
  __int64 v24; // rax
  int v25; // ebx
  int v26; // edx
  __int64 v27; // rax
  __int64 v28; // rcx
  volatile signed __int32 *v29; // rbx
  __int64 v30; // rax
  volatile signed __int32 *v31; // r14
  const char *v32; // r9
  __int64 v33; // r13
  _QWORD *v34; // r12
  int v35; // ebx
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdx
  volatile signed __int32 *v43; // rbx
  __int64 v44; // rdx
  signed __int32 v45; // eax
  signed __int32 v46; // ett
  __int128 v47; // rcx
  volatile signed __int32 *v48; // rbx
  __int16 v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  char *Str; // [rsp+28h] [rbp-D8h]
  const void *v52; // [rsp+30h] [rbp-D0h]
  __int64 v53; // [rsp+40h] [rbp-C0h]
  _OWORD v54[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v55; // [rsp+68h] [rbp-98h] BYREF
  __int128 v56; // [rsp+78h] [rbp-88h] BYREF
  __int128 v57; // [rsp+88h] [rbp-78h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  _BYTE v59[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v60[32]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v61[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v62[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v63[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v64[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v65[32]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v66[4]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v67[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v69[16]; // [rsp+240h] [rbp+140h] BYREF
  __int128 v70; // [rsp+250h] [rbp+150h] BYREF
  int v71[4]; // [rsp+260h] [rbp+160h] BYREF
  __int128 v72; // [rsp+270h] [rbp+170h]
  _BYTE v73[56]; // [rsp+280h] [rbp+180h] BYREF

  v3 = a3;
  *(_QWORD *)&v54[0] = a3;
  v55 = 0;
  ChannelId = 0;
  *(_WORD *)v69 = 0;
  if ( *((_BYTE *)a1 + 605) )
  {
    v70 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v70);
    result = v70;
    if ( (_QWORD)v70 && *(_BYTE *)(v70 + 128) )
    {
      v8 = (__int64 *)Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v59, a2[2], 0, 6);
      v9 = (__int64)v8;
      if ( (unsigned __int64)v8[3] > 0xF )
        v9 = *v8;
      v10 = (__int64 *)Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v60, *a2, 0, 6);
      LODWORD(v12) = (_DWORD)v10;
      if ( (unsigned __int64)v10[3] > 0xF )
        v12 = *v10;
      *(_OWORD *)v71 = 0;
      v72 = 0;
      std::string::_Construct<1,char const *>(
        v71,
        "AddLink: pre-closing has been called, ignore new link: local=%s, remote=%s",
        (const char *)0x4A,
        v11);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,char const *,char const *>(
        (unsigned int)&v70,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v71,
        v12,
        v9);
      std::string::_Tidy_deallocate(v71);
      std::string::_Tidy_deallocate(v60);
      result = std::string::_Tidy_deallocate(v59);
    }
    v13 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
    if ( *((_QWORD *)&v70 + 1) )
    {
      v14 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL), 0xFFFFFFFF);
      v15 = v14 == 1;
      result = (unsigned int)(v14 - 1);
      if ( v15 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        result = (unsigned int)_InterlockedDecrement(v13 + 3);
        if ( !(_DWORD)result )
          return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
  }
  else
  {
    if ( *((_DWORD *)*a2 + 57) == 3 )
    {
      v16 = *a3;
      v70 = 0;
      v17 = a2[1];
      if ( v17 )
        _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
      v70 = *(_OWORD *)a2;
      TurnServer = (__int64 *)Microsoft::Basix::Dct::ICECore::CandidateBase::FindTurnServer(v16, v71, &v70);
      v19 = *TurnServer;
      v20 = TurnServer[1];
      *TurnServer = 0;
      TurnServer[1] = 0;
      *(_QWORD *)&v55 = v19;
      *((_QWORD *)&v55 + 1) = v20;
      v21 = *(volatile signed __int32 **)&v71[2];
      if ( *(_QWORD *)&v71[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v71[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
          if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        }
      }
      if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                               &v55,
                               0) )
      {
        std::string::string(v60, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\icecore.cpp");
        std::string::string(v59, "Tried to check via TURN server which has not been prepared yet");
        Microsoft::Basix::Exception::Exception(pExceptionObject, v59, v60, 1678);
        throw (Microsoft::Basix::Exception *)pExceptionObject;
      }
      ChannelId = Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer::FindChannelId(v19, (char *)a2[2] + 64);
      *(_WORD *)v69 = ChannelId;
    }
    v22 = a2[2];
    if ( *((_DWORD *)*a2 + 57) == 3 )
      Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(v22, 1);
    else
      Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(v22, 1);
    v23 = *a2;
    if ( *((_DWORD *)a2[2] + 57) == 3 )
      Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(v23, 1);
    else
      Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(v23, 1);
    v70 = 0;
    std::make_shared<Microsoft::Basix::Dct::ICECore::LinkContext,bool &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> &>(
      &v70,
      (char *)a1 + 425,
      a1 + 4);
    v24 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::LinkContextDelegate>(
            (char *)a1 + *(int *)(a1[16] + 4) + 128,
            v71);
    v49 = ChannelId;
    v25 = v70;
    Microsoft::Basix::Dct::ICECore::LinkContext::Set(
      v70,
      (_DWORD)a2,
      (_DWORD)v3,
      (unsigned int)&v55,
      v49,
      (__int64)a2[2] + 64,
      v24);
    LOBYTE(v26) = v69[0];
    std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>(
      (unsigned int)v73,
      v26,
      v25 + 1120,
      v25 + 1136,
      (__int64)v69);
    if ( Mtx_lock((_Mtx_t)(a1 + 57)) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)a1 + 133) == 0x7FFFFFFF )
    {
      *((_DWORD *)a1 + 133) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v27 = Microsoft::Basix::Dct::ICECore::ReceiveHasher::operator()(a1 + 67, v73);
    v28 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>,std::weak_ptr<Microsoft::Basix::Dct::ICECore::LinkContext>,std::_Uhash_compare<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>,Microsoft::Basix::Dct::ICECore::ReceiveHasher,std::equal_to<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>>>,std::allocator<std::pair<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short> const,std::weak_ptr<Microsoft::Basix::Dct::ICECore::LinkContext>>>,0>>::_Find_last<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>>(
                        a1 + 67,
                        v71,
                        v73,
                        v27)
                    + 8);
    if ( !v28 )
      v28 = a1[68];
    if ( v28 != a1[68] )
    {
      std::string::string(v65, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\icecore.cpp");
      std::string::string(v64, "duplicated entry in m_linkContextMap");
      Microsoft::Basix::Exception::Exception(pExceptionObject, v64, v65, 1700);
      throw (Microsoft::Basix::Exception *)pExceptionObject;
    }
    std::_Hash<std::_Umap_traits<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>,std::weak_ptr<Microsoft::Basix::Dct::ICECore::LinkContext>,std::_Uhash_compare<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>,Microsoft::Basix::Dct::ICECore::ReceiveHasher,std::equal_to<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>>>,std::allocator<std::pair<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short> const,std::weak_ptr<Microsoft::Basix::Dct::ICECore::LinkContext>>>,0>>::emplace<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short> &,std::shared_ptr<Microsoft::Basix::Dct::ICECore::LinkContext> &>(
      a1 + 67,
      v71,
      v73,
      &v70);
    Mtx_unlock((_Mtx_t)(a1 + 57));
    Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(a1, v71);
    v29 = *(volatile signed __int32 **)&v71[2];
    if ( *(_QWORD *)&v71[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v71[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
    v30 = *a1;
    *(_OWORD *)v71 = 0;
    v31 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
    if ( *((_QWORD *)&v70 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL));
    *(_OWORD *)v71 = v70;
    if ( (*(unsigned __int8 (__fastcall **)(__int64 *, int *))(v30 + 40))(a1, v71) )
    {
      *((_DWORD *)*v3 + 70) = 1;
      *(_OWORD *)v71 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v71);
      v33 = v70;
      if ( *(_QWORD *)v71 && *(_BYTE *)(*(_QWORD *)v71 + 128LL) )
      {
        v58 = *(_QWORD *)(v70 + 1360);
        v53 = *(_QWORD *)(v70 + 1120);
        v34 = (_QWORD *)(v70 + 1136);
        if ( *(_QWORD *)(v70 + 1160) > 0xFu )
          v34 = (_QWORD *)*v34;
        v35 = *((_DWORD *)a1 + 2265);
        v56 = 0;
        v57 = 0;
        std::string::_Construct<1,char const *>(
          &v56,
          "AddLinkForChannelCreation: dor =%d, peer=%s, channelId=%d, transport=%p, base=%p",
          80,
          v32,
          v50,
          Str,
          v52);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,char const *,unsigned short,Microsoft::Basix::Dct::IChannel *,Microsoft::Basix::Dct::ICECore::CandidateBase *>(
          (unsigned int)v71,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v56,
          v35,
          (__int64)v34,
          v69[0],
          v53,
          v58);
        std::string::_Tidy_deallocate(&v56);
        v3 = *(Microsoft::Basix::Dct::ICECore::CandidateBase ***)&v54[0];
      }
      v36 = *(volatile signed __int32 **)&v71[2];
      if ( *(_QWORD *)&v71[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v71[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
          if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
        }
      }
      *(_DWORD *)v69 = 0;
      if ( (unsigned __int8)std::_Atomic_storage<enum Microsoft::Basix::Pattern::IThreadedObject::State,4>::compare_exchange_strong(
                              a1 + 1132,
                              v69,
                              1) )
      {
        *(_OWORD *)v71 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v71);
        if ( *(_QWORD *)v71 && *(_BYTE *)(*(_QWORD *)v71 + 128LL) )
        {
          memset(v63, 0, sizeof(v63));
          std::string::_Construct<1,char const *>(v63, "\"", 1);
          memset(v62, 0, sizeof(v62));
          std::string::_Construct<1,char const *>(v62, "\"", 1);
          memset(v61, 0, sizeof(v61));
          std::string::_Construct<1,char const *>(v61, ":", 1);
          memset(v54, 0, sizeof(v54));
          std::string::_Construct<1,char const *>(v54, "\"", 1);
          v56 = 0;
          v57 = 0;
          std::string::_Construct<1,char const *>(&v56, "\"", 1);
          v37 = std::operator+<char>(v65, &v56, "LinkAddedPhase");
          LOBYTE(v38) = v69[0];
          std::string::string(v60, v38, v37, v54);
          LOBYTE(v39) = v69[0];
          std::string::string(v59, v39, v60, v61);
          LOBYTE(v40) = v69[0];
          std::string::string(v67, v40, v59, v62);
          v41 = std::operator+<char>(v64, v67, "First");
          LOBYTE(v42) = v69[0];
          std::string::string(v66, v42, v41, v63);
          Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
            (int)v71,
            (int)"RD_CHECKPOINT",
            0,
            (int)"ICECore",
            "LinkManagement",
            "LinkAdded",
            (__int64)v66);
          std::string::_Tidy_deallocate(v64);
          std::string::_Tidy_deallocate(v67);
          std::string::_Tidy_deallocate(v59);
          std::string::_Tidy_deallocate(v60);
          std::string::_Tidy_deallocate(v65);
          std::string::_Tidy_deallocate(&v56);
          std::string::_Tidy_deallocate(v54);
          std::string::_Tidy_deallocate(v61);
          std::string::_Tidy_deallocate(v62);
          std::string::_Tidy_deallocate(v63);
        }
        v43 = *(volatile signed __int32 **)&v71[2];
        if ( *(_QWORD *)&v71[2] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v71[2] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
            if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
          }
        }
      }
      Microsoft::Basix::Dct::ICE::Agent::RemoveFromSucceeded(
        (Microsoft::Basix::Dct::ICE::Agent *)a1[17],
        (const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)(v33 + 1392));
      Microsoft::Basix::Dct::ICECore::CandidateBase::RemoveFromPeerNominationPairs(
        *v3,
        (const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)(v33 + 1392));
      if ( Microsoft::Basix::Dct::ICE::Agent::HasNoPairsChecking((Microsoft::Basix::Dct::ICE::Agent *)a1[17]) )
        (*(void (__fastcall **)(__int64 *))(a1[2] + 192))(a1 + 2);
      v54[0] = 0;
      v44 = a1[20];
      if ( v44 )
      {
        v45 = *(_DWORD *)(v44 + 8);
        while ( v45 )
        {
          v46 = v45;
          v45 = _InterlockedCompareExchange((volatile signed __int32 *)(v44 + 8), v45 + 1, v45);
          if ( v46 == v45 )
          {
            *(_QWORD *)&v47 = a1[19];
            *(_QWORD *)&v54[0] = v47;
            *((_QWORD *)&v47 + 1) = a1[20];
            *((_QWORD *)&v54[0] + 1) = *((_QWORD *)&v47 + 1);
            goto LABEL_65;
          }
        }
      }
      v47 = v54[0];
LABEL_65:
      if ( (_QWORD)v47 )
        (*(void (__fastcall **)(_QWORD, Microsoft::Basix::Dct::ICE::Candidate **))(*(_QWORD *)v47 + 40LL))(v47, a2);
      if ( *((_QWORD *)&v47 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL)) )
        {
          (***((void (__fastcall ****)(_QWORD))&v47 + 1))(*((_QWORD *)&v47 + 1));
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 12LL)) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v47 + 1) + 8LL))(*((_QWORD *)&v47 + 1));
        }
      }
    }
    result = std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>::~tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,unsigned short>(v73);
    if ( v31 )
    {
      result = (unsigned int)_InterlockedDecrement(v31 + 2);
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        result = (unsigned int)_InterlockedDecrement(v31 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    v48 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
    if ( *((_QWORD *)&v55 + 1) )
    {
      result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL));
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
        result = (unsigned int)_InterlockedDecrement(v48 + 3);
        if ( !(_DWORD)result )
          return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18021a548  mov     [rsp-8+arg_18], rbx
0x18021a54d  push    rbp
0x18021a54e  push    rsi
0x18021a54f  push    rdi
0x18021a550  push    r12
0x18021a552  push    r13
0x18021a554  push    r14
0x18021a556  push    r15
0x18021a558  lea     rbp, [rsp-1C0h]
0x18021a560  mov     eax, 2C0h
0x18021a565  call    _alloca_probe
0x18021a56a  sub     rsp, rax
0x18021a56d  mov     rax, cs:__security_cookie
0x18021a574  xor     rax, rsp
0x18021a577  mov     [rbp+1F0h+var_38], rax
0x18021a57e  mov     r12, r8
0x18021a581  mov     qword ptr [rsp+2F0h+var_2A8], r8
0x18021a586  mov     r15, rdx
0x18021a589  mov     rsi, rcx
0x18021a58c  xor     r13d, r13d
0x18021a58f  xorps   xmm0, xmm0
0x18021a592  xorps   xmm1, xmm1
0x18021a595  movdqu  [rsp+2F0h+var_288], xmm1
0x18021a59b  movzx   ebx, r13w
0x18021a59f  mov     word ptr [rbp+1F0h+var_B0], bx
0x18021a5a6  cmp     [rcx+25Dh], r13b
0x18021a5ad  jz      loc_18021A709
0x18021a5b3  movups  [rbp+1F0h+var_A0], xmm0
0x18021a5ba  lea     rcx, [rbp+1F0h+var_A0]
0x18021a5c1  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x18021a5c6  nop
0x18021a5c7  mov     rax, qword ptr [rbp+1F0h+var_A0]
0x18021a5ce  test    rax, rax
0x18021a5d1  jz      loc_18021A69A
0x18021a5d7  cmp     [rax+80h], r13b
0x18021a5de  jz      loc_18021A69A
0x18021a5e4  lea     r9d, [r13+6]
0x18021a5e8  xor     r8d, r8d
0x18021a5eb  mov     rdx, [r15+10h]
0x18021a5ef  lea     rcx, [rbp+1F0h+var_250]
0x18021a5f3  call    ??$ToString@VCandidate@ICE@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVCandidate@ICE@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(Microsoft::Basix::Dct::ICE::Candidate const &,int,int)
0x18021a5f8  mov     rdi, rax
0x18021a5fb  cmp     qword ptr [rax+18h], 0Fh
0x18021a600  jbe     short loc_18021A605
0x18021a602  mov     rdi, [rax]
0x18021a605  mov     r9d, 6
0x18021a60b  xor     r8d, r8d
0x18021a60e  mov     rdx, [r15]
0x18021a611  lea     rcx, [rbp+1F0h+var_230]
0x18021a615  call    ??$ToString@VCandidate@ICE@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVCandidate@ICE@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(Microsoft::Basix::Dct::ICE::Candidate const &,int,int)
0x18021a61a  mov     rbx, rax
0x18021a61d  cmp     qword ptr [rax+18h], 0Fh
0x18021a622  jbe     short loc_18021A627
0x18021a624  mov     rbx, [rax]
0x18021a627  xorps   xmm0, xmm0
0x18021a62a  movups  xmmword ptr [rbp+1F0h+var_90], xmm0
0x18021a631  xorps   xmm1, xmm1
0x18021a634  movdqu  [rbp+1F0h+var_80], xmm1
0x18021a63c  mov     r8d, 4Ah ; 'J'
0x18021a642  lea     rdx, aAddlinkPreClos; "AddLink: pre-closing has been called, i"...
0x18021a649  lea     rcx, [rbp+1F0h+var_90]
0x18021a650  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18021a655  nop
0x18021a656  mov     [rsp+2F0h+var_2D0], rdi
0x18021a65b  mov     r9, rbx
0x18021a65e  lea     r8, [rbp+1F0h+var_90]
0x18021a665  lea     rdx, aBasixDct; "BASIX_DCT"
0x18021a66c  lea     rcx, [rbp+1F0h+var_A0]
0x18021a673  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@PEBDPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@11@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,char const *,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,char const *,char const *)
0x18021a678  nop
0x18021a679  lea     rcx, [rbp+1F0h+var_90]
0x18021a680  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18021a685  nop
0x18021a686  lea     rcx, [rbp+1F0h+var_230]
0x18021a68a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18021a68f  nop
0x18021a690  lea     rcx, [rbp+1F0h+var_250]
0x18021a694  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18021a699  nop
0x18021a69a  mov     rbx, qword ptr [rbp+1F0h+var_A0+8]
0x18021a6a1  test    rbx, rbx
0x18021a6a4  jz      short loc_18021A6DF
0x18021a6a6  or      edi, 0FFFFFFFFh
0x18021a6a9  mov     eax, edi
0x18021a6ab  lock xadd [rbx+8], eax
0x18021a6b0  add     eax, edi
0x18021a6b2  jnz     short loc_18021A6DF
0x18021a6b4  mov     rax, [rbx]
0x18021a6b7  mov     rcx, rbx
0x18021a6ba  mov     rax, [rax]
0x18021a6bd  call    cs:__guard_dispatch_icall_fptr
0x18021a6c3  mov     eax, edi
0x18021a6c5  lock xadd [rbx+0Ch], eax
0x18021a6ca  add     eax, edi
0x18021a6cc  jnz     short loc_18021A6DF
0x18021a6ce  mov     rax, [rbx]
0x18021a6d1  mov     rcx, rbx
0x18021a6d4  mov     rax, [rax+8]
0x18021a6d8  call    cs:__guard_dispatch_icall_fptr
0x18021a6de  nop
0x18021a6df  mov     rcx, [rbp+1F0h+var_38]
0x18021a6e6  xor     rcx, rsp; StackCookie
0x18021a6e9  call    __security_check_cookie
0x18021a6ee  mov     rbx, [rsp+2F0h+arg_18]
0x18021a6f6  add     rsp, 2C0h
0x18021a6fd  pop     r15
0x18021a6ff  pop     r14
0x18021a701  pop     r13
0x18021a703  pop     r12
0x18021a705  pop     rdi
0x18021a706  pop     rsi
0x18021a707  pop     rbp
0x18021a708  retn
0x18021a709  mov     rax, [rdx]
0x18021a70c  or      edi, 0FFFFFFFFh
0x18021a70f  cmp     dword ptr [rax+0E4h], 3
0x18021a716  jnz     loc_18021A7E3
0x18021a71c  mov     rcx, [r8]
0x18021a71f  movdqu  [rbp+1F0h+var_A0], xmm0
0x18021a727  mov     rax, [rdx+8]
0x18021a72b  test    rax, rax
0x18021a72e  jz      short loc_18021A734
0x18021a730  lock inc dword ptr [rax+8]
0x18021a734  mov     rax, [rdx]
0x18021a737  mov     qword ptr [rbp+1F0h+var_A0], rax
0x18021a73e  mov     rax, [rdx+8]
0x18021a742  mov     qword ptr [rbp+1F0h+var_A0+8], rax
0x18021a749  lea     r8, [rbp+1F0h+var_A0]
0x18021a750  lea     rdx, [rbp+1F0h+var_90]
0x18021a757  call    ?FindTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@QEAA?AV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@V?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@7@@Z; Microsoft::Basix::Dct::ICECore::CandidateBase::FindTurnServer(std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>)
0x18021a75c  mov     r14, [rax]
0x18021a75f  mov     rcx, [rax+8]
0x18021a763  mov     [rax], r13
0x18021a766  mov     [rax+8], r13
0x18021a76a  mov     qword ptr [rsp+2F0h+var_288], r14
0x18021a76f  mov     qword ptr [rsp+2F0h+var_288+8], rcx
0x18021a774  mov     rbx, qword ptr [rbp+1F0h+var_90+8]
0x18021a77b  test    rbx, rbx
0x18021a77e  jz      short loc_18021A7B5
0x18021a780  mov     eax, edi
0x18021a782  lock xadd [rbx+8], eax
0x18021a787  add     eax, edi
0x18021a789  jnz     short loc_18021A7B5
0x18021a78b  mov     rax, [rbx]
0x18021a78e  mov     rcx, rbx
0x18021a791  mov     rax, [rax]
0x18021a794  call    cs:__guard_dispatch_icall_fptr
0x18021a79a  mov     eax, edi
0x18021a79c  lock xadd [rbx+0Ch], eax
0x18021a7a1  add     eax, edi
0x18021a7a3  jnz     short loc_18021A7B5
0x18021a7a5  mov     rax, [rbx]
0x18021a7a8  mov     rcx, rbx
0x18021a7ab  mov     rax, [rax+8]
0x18021a7af  call    cs:__guard_dispatch_icall_fptr
0x18021a7b5  xor     edx, edx
0x18021a7b7  lea     rcx, [rsp+2F0h+var_288]
0x18021a7bc  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x18021a7c1  test    al, al
0x18021a7c3  jz      loc_18021AFA6
0x18021a7c9  mov     rdx, [r15+10h]
0x18021a7cd  add     rdx, 40h ; '@'
0x18021a7d1  mov     rcx, r14
0x18021a7d4  call    ?FindChannelId@TurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@QEAAGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer::FindChannelId(std::string const &)
0x18021a7d9  movzx   ebx, ax
0x18021a7dc  mov     word ptr [rbp+1F0h+var_B0], ax
0x18021a7e3  mov     rcx, [r15+10h]; this
0x18021a7e7  mov     rax, [r15]
0x18021a7ea  mov     edx, 1; int
0x18021a7ef  cmp     dword ptr [rax+0E4h], 3
0x18021a7f6  jnz     short loc_18021A7FF
0x18021a7f8  call    ?AdjustRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(int)
0x18021a7fd  jmp     short loc_18021A804
0x18021a7ff  call    ?AdjustNonRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(int)
0x18021a804  mov     rax, [r15+10h]
0x18021a808  mov     edx, 1; int
0x18021a80d  mov     rcx, [r15]; this
0x18021a810  cmp     dword ptr [rax+0E4h], 3
0x18021a817  jnz     short loc_18021A820
0x18021a819  call    ?AdjustRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(int)
0x18021a81e  jmp     short loc_18021A825
0x18021a820  call    ?AdjustNonRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(int)
0x18021a825  xorps   xmm0, xmm0
0x18021a828  movups  [rbp+1F0h+var_A0], xmm0
0x18021a82f  lea     r8, [rsi+20h]
0x18021a833  lea     rdx, [rsi+1A9h]
0x18021a83a  lea     rcx, [rbp+1F0h+var_A0]
0x18021a841  call    ??$make_shared@VLinkContext@ICECore@Dct@Basix@Microsoft@@AEA_NAEAV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@YA?AV?$shared_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@0@AEA_NAEAV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z; std::make_shared<Microsoft::Basix::Dct::ICECore::LinkContext,bool &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> &>(bool &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> &)
0x18021a846  nop
0x18021a847  mov     rax, [rsi+80h]
0x18021a84e  movsxd  rcx, dword ptr [rax+4]
0x18021a852  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18021a856  add     rcx, rsi
0x18021a859  lea     rdx, [rbp+1F0h+var_90]
0x18021a860  call    ??$GetWeakPtr@VLinkContextDelegate@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VLinkContextDelegate@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::LinkContextDelegate>(void)
0x18021a865  mov     rcx, [r15+10h]
0x18021a869  add     rcx, 40h ; '@'
0x18021a86d  mov     [rsp+2F0h+var_2C0], rax
0x18021a872  mov     [rsp+2F0h+Str], rcx
0x18021a877  mov     word ptr [rsp+2F0h+var_2D0], bx
0x18021a87c  lea     r9, [rsp+2F0h+var_288]
0x18021a881  mov     r8, r12
0x18021a884  mov     rdx, r15
0x18021a887  mov     rbx, qword ptr [rbp+1F0h+var_A0]
0x18021a88e  mov     rcx, rbx
0x18021a891  call    ?Set@LinkContext@ICECore@Dct@Basix@Microsoft@@QEAAXAEBVCandidatePair@Agent@ICE@345@AEBV?$shared_ptr@VCandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@AEBV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@GAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$weak_ptr@VLinkContextDelegate@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::ICECore::LinkContext::Set(Microsoft::Basix::Dct::ICE::Agent::CandidatePair const &,std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase> const &,std::shared_ptr<Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer> const &,ushort,std::string const &,std::weak_ptr<Microsoft::Basix::Dct::LinkContextDelegate>)
0x18021a896  lea     r9, [rbx+470h]
0x18021a89d  lea     r8, [rbx+460h]
0x18021a8a4  lea     rax, [rbp+1F0h+var_B0]
0x18021a8ab  mov     [rsp+2F0h+var_2D0], rax
0x18021a8b0  mov     dl, [rbp+1F0h+var_B0]
0x18021a8b6  lea     rcx, [rbp+1F0h+var_70]
0x18021a8bd  call    ??$?0U_Exact_args_t@std@@AEBV?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@AEAG$0A@@?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@QEAA@U_Exact_args_t@1@AEBV?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@AEAG@Z; std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort>::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort>(std::_Exact_args_t,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,std::string const &,ushort &)
0x18021a8c2  nop
0x18021a8c3  lea     rbx, [rsi+1C8h]
0x18021a8ca  mov     [rsp+2F0h+var_2B0], rbx
0x18021a8cf  mov     rcx, rbx; _Mtx_t
0x18021a8d2  call    _Mtx_lock
0x18021a8d7  test    eax, eax
0x18021a8d9  jnz     loc_18021AFF6
0x18021a8df  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18021a8e6  jz      loc_18021AF44
0x18021a8ec  lea     r14, [rsi+218h]
0x18021a8f3  lea     rdx, [rbp+1F0h+var_70]
0x18021a8fa  mov     rcx, r14
0x18021a8fd  call    ??RReceiveHasher@ICECore@Dct@Basix@Microsoft@@QEBA_KAEBV?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@@Z; Microsoft::Basix::Dct::ICECore::ReceiveHasher::operator()(std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort> const &)
0x18021a902  mov     r9, rax
0x18021a905  lea     r8, [rbp+1F0h+var_70]
0x18021a90c  lea     rdx, [rbp+1F0h+var_90]
0x18021a913  mov     rcx, r14
0x18021a916  call    ??$_Find_last@V?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@@?$_Hash@V?$_Umap_traits@V?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@V?$weak_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@2@V?$_Uhash_compare@V?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@UReceiveHasher@ICECore@Dct@Basix@Microsoft@@U?$equal_to@V?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@V?$weak_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@V?$weak_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@2@@std@@PEAX@std@@@1@AEBV?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@1@_K@Z; std::_Hash<std::_Umap_traits<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort>,std::weak_ptr<Microsoft::Basix::Dct::ICECore::LinkContext>,std::_Uhash_compare<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort>,Microsoft::Basix::Dct::ICECore::ReceiveHasher,std::equal_to<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort>>>,std::allocator<std::pair<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort> const,std::weak_ptr<Microsoft::Basix::Dct::ICECore::LinkContext>>>,0>>::_Find_last<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort>>(std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort> const &,unsigned __int64)
0x18021a91b  mov     rcx, [rax+8]
0x18021a91f  test    rcx, rcx
0x18021a922  jnz     short loc_18021A928
0x18021a924  mov     rcx, [r14+8]
0x18021a928  cmp     rcx, [rsi+220h]
0x18021a92f  jnz     loc_18021AF56
0x18021a935  lea     r9, [rbp+1F0h+var_A0]
0x18021a93c  lea     r8, [rbp+1F0h+var_70]
0x18021a943  lea     rdx, [rbp+1F0h+var_90]
0x18021a94a  mov     rcx, r14
0x18021a94d  call    ??$emplace@AEAV?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@AEAV?$shared_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@2@@?$_Hash@V?$_Umap_traits@V?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@V?$weak_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@2@V?$_Uhash_compare@V?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@UReceiveHasher@ICECore@Dct@Basix@Microsoft@@U?$equal_to@V?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@V?$weak_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@std@@V?$weak_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@G@1@AEAV?$shared_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@1@@Z; std::_Hash<std::_Umap_traits<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort>,std::weak_ptr<Microsoft::Basix::Dct::ICECore::LinkContext>,std::_Uhash_compare<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort>,Microsoft::Basix::Dct::ICECore::ReceiveHasher,std::equal_to<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort>>>,std::allocator<std::pair<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort> const,std::weak_ptr<Microsoft::Basix::Dct::ICECore::LinkContext>>>,0>>::emplace<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort> &,std::shared_ptr<Microsoft::Basix::Dct::ICECore::LinkContext> &>(std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,std::string,ushort> &,std::shared_ptr<Microsoft::Basix::Dct::ICECore::LinkContext> &)
0x18021a952  nop
0x18021a953  mov     rcx, rbx; _Mtx_t
0x18021a956  call    _Mtx_unlock
0x18021a95b  lea     rdx, [rbp+1F0h+var_90]
0x18021a962  mov     rcx, rsi
0x18021a965  call    ?ComputeDegreeOfRedundency@ICECore@Dct@Basix@Microsoft@@QEAA?AV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(void)
0x18021a96a  mov     rbx, qword ptr [rbp+1F0h+var_90+8]
0x18021a971  test    rbx, rbx
0x18021a974  jz      short loc_18021A9AB
0x18021a976  mov     eax, edi
0x18021a978  lock xadd [rbx+8], eax
0x18021a97d  add     eax, edi
0x18021a97f  jnz     short loc_18021A9AB
0x18021a981  mov     rax, [rbx]
0x18021a984  mov     rcx, rbx
0x18021a987  mov     rax, [rax]
0x18021a98a  call    cs:__guard_dispatch_icall_fptr
0x18021a990  mov     eax, edi
0x18021a992  lock xadd [rbx+0Ch], eax
0x18021a997  add     eax, edi
0x18021a999  jnz     short loc_18021A9AB
0x18021a99b  mov     rax, [rbx]
0x18021a99e  mov     rcx, rbx
0x18021a9a1  mov     rax, [rax+8]
0x18021a9a5  call    cs:__guard_dispatch_icall_fptr
0x18021a9ab  mov     rax, [rsi]
0x18021a9ae  xorps   xmm0, xmm0
0x18021a9b1  movdqa  xmmword ptr [rbp+1F0h+var_90], xmm0
0x18021a9b9  mov     r14, qword ptr [rbp+1F0h+var_A0+8]
0x18021a9c0  test    r14, r14
0x18021a9c3  jz      short loc_18021A9CA
0x18021a9c5  lock inc dword ptr [r14+8]
0x18021a9ca  movaps  xmm0, [rbp+1F0h+var_A0]
0x18021a9d1  movdqa  xmmword ptr [rbp+1F0h+var_90], xmm0
0x18021a9d9  lea     rdx, [rbp+1F0h+var_90]
0x18021a9e0  mov     rcx, rsi
0x18021a9e3  mov     rax, [rax+28h]
0x18021a9e7  call    cs:__guard_dispatch_icall_fptr
0x18021a9ed  test    al, al
0x18021a9ef  jz      loc_18021AE8D
0x18021a9f5  mov     rax, [r12]
0x18021a9f9  mov     dword ptr [rax+118h], 1
0x18021aa03  xorps   xmm0, xmm0
0x18021aa06  movups  xmmword ptr [rbp+1F0h+var_90], xmm0
0x18021aa0d  lea     rcx, [rbp+1F0h+var_90]
0x18021aa14  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18021aa19  nop
0x18021aa1a  mov     r13, qword ptr [rbp+1F0h+var_A0]
0x18021aa21  mov     rax, qword ptr [rbp+1F0h+var_90]
0x18021aa28  test    rax, rax
0x18021aa2b  jz      loc_18021AAE5
0x18021aa31  cmp     byte ptr [rax+80h], 0
0x18021aa38  jz      loc_18021AAE5
0x18021aa3e  mov     rax, [r13+550h]
0x18021aa45  mov     [rbp+1F0h+var_258], rax
0x18021aa49  mov     rax, [r13+460h]
0x18021aa50  mov     [rsp+2F0h+var_2B0], rax
0x18021aa55  lea     r12, [r13+470h]
  ... truncated ...
```

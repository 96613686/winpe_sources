# Microsoft::Basix::Dct::ICECore::LinkContext::InternalClose(void)

- ea: `0x18022c110`
- end: `0x18022cb69`
- name: `?InternalClose@LinkContext@ICECore@Dct@Basix@Microsoft@@EEAAXXZ`
- size: `2649`
- prototype: `void __fastcall(Microsoft::Basix::Dct::ICECore::LinkContext *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180008f80`
- `0x18000d9c0`
- `0x180015bb8`
- `0x18001902c`
- `0x18001ab4c`
- `0x18001b51c`
- `0x1800c408c`
- `0x1800ea630`
- `0x1801b3b70`
- `0x18020105c`
- `0x180201458`
- `0x180203f58`
- `0x18022c110`
- `0x18023e3f4`
- `0x18023eae8`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18022c18b`: `ICECore::LinkContext::InternalClose() = 0x%llx`
- `0x18022c263`: `ICECore::LinkContext::InternalClose(): already closing, nothing to do`
- `0x18022c45d`: `LinkContext::InternalClose(): active close already checked for this server: relay=%p, base=%p`
- `0x18022c584`: `LinkContext::InternalClose(): remote active close already checked for this server: relay=%p, base=%p`
- `0x18022c651`: `LinkContext::InternalClose(): SendTurnActiveCloseRequest(): relay=%p, base=%p`
- `0x18022c883`: `LinkContext::InternalClose(): SendRemoteTurnActiveCloseRequest(): relay=%p, base=%p, remoteServer=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall Microsoft::Basix::Dct::ICECore::LinkContext::InternalClose(
        Microsoft::Basix::Dct::ICECore::LinkContext *this)
{
  char v2; // r15
  char v3; // r12
  volatile signed __int32 *v4; // rbx
  char v5; // bl
  char *v6; // rax
  char v7; // bl
  char v8; // t0
  __int64 v9; // rbx
  void (__fastcall **v10)(__int64); // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  signed __int32 v13; // eax
  signed __int32 v14; // ett
  unsigned __int128 v15; // kr00_16
  void (__fastcall *v16)(_QWORD, __int128 *); // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int32 v19; // ebx
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // rdi
  unsigned __int64 v23; // r14
  const void *v24; // r9
  __int64 v25; // rbx
  __int64 v26; // rdi
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rbx
  const void *v29; // r9
  __int64 v30; // rbx
  __int64 v31; // rdi
  volatile signed __int32 *v32; // rbx
  const void *v33; // r9
  __int64 v34; // rbx
  __int64 v35; // rdi
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rdi
  _QWORD *v38; // rax
  volatile signed __int32 *v39; // rbx
  __int64 v40; // rdx
  __int64 v41; // rdx
  volatile signed __int32 *v42; // rbx
  __int64 v43; // r15
  const void *v44; // r9
  __int64 v45; // r12
  __int64 v46; // rbx
  __int64 v47; // rdi
  volatile signed __int32 *v48; // rbx
  __int64 v49; // rdi
  _QWORD *v50; // rax
  volatile signed __int32 *v51; // rbx
  __int64 v52; // rdx
  __int64 v53; // rdx
  volatile signed __int32 *v54; // rbx
  __int64 v55; // rdx
  signed __int32 v56; // eax
  signed __int32 v57; // ett
  __int128 v58; // rcx
  const char *v59; // [rsp+20h] [rbp-E0h]
  char v60; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v61; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v62; // [rsp+48h] [rbp-B8h]
  _QWORD v63[7]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v64; // [rsp+98h] [rbp-68h]
  _QWORD v65[7]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v66; // [rsp+D8h] [rbp-28h]
  __int128 v67; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int128 v68; // [rsp+F0h] [rbp-10h] BYREF

  v2 = 0;
  v3 = 0;
  v68 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v68);
  if ( (_QWORD)v68 && *(_BYTE *)(v68 + 128) )
  {
    v61 = 0;
    v62 = 0;
    std::string::_Construct<1,char const *>(&v61, "ICECore::LinkContext::InternalClose() = 0x%llx", 46);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(
      &v68,
      "BASIX_DCT",
      &v61,
      this);
    std::string::_Tidy_deallocate(&v61);
  }
  v4 = (volatile signed __int32 *)*((_QWORD *)&v68 + 1);
  if ( *((_QWORD *)&v68 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v68 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( !_InterlockedDecrement(v4 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  v60 = 1;
  v5 = ((__int64 (__fastcall *)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data2)(&v60);
  v6 = (char *)(*(__int64 (__fastcall **)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((char *)this + 1472);
  v8 = v5;
  v7 = *v6;
  *v6 = v8;
  if ( v7 )
  {
    v68 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v68);
    if ( (_QWORD)v68 && *(_BYTE *)(v68 + 128) )
    {
      v61 = 0;
      v62 = 0;
      std::string::_Construct<1,char const *>(
        &v61,
        "ICECore::LinkContext::InternalClose(): already closing, nothing to do",
        69);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v68,
        "BASIX_DCT",
        &v61);
      std::string::_Tidy_deallocate(&v61);
    }
    v9 = *((_QWORD *)&v68 + 1);
    if ( *((_QWORD *)&v68 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v68 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(__int64))v9)(v9);
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v9 + 12)) )
        {
          v10 = *(void (__fastcall ***)(__int64))v9;
          v11 = v9;
LABEL_110:
          v10[1](v11);
        }
      }
    }
  }
  else
  {
    v68 = 0;
    v12 = *((_QWORD *)this + 183);
    if ( v12 )
    {
      v13 = *(_DWORD *)(v12 + 8);
      while ( v13 )
      {
        v14 = v13;
        v13 = _InterlockedCompareExchange((volatile signed __int32 *)(v12 + 8), v13 + 1, v13);
        if ( v14 == v13 )
        {
          v22 = *((_QWORD *)this + 182);
          *(_QWORD *)&v68 = v22;
          v23 = *((_QWORD *)this + 183);
          *((_QWORD *)&v68 + 1) = v23;
          v15 = __PAIR128__(v23, v22);
          goto LABEL_21;
        }
      }
    }
    v15 = v68;
LABEL_21:
    if ( (_QWORD)v15 )
    {
      v16 = **(void (__fastcall ***)(_QWORD, __int128 *))v15;
      v17 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::ICECore::LinkContext>(
              (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
              &v61);
      v67 = 0;
      v67 = *(_OWORD *)v17;
      *(_QWORD *)v17 = 0;
      *(_QWORD *)(v17 + 8) = 0;
      v16(v15, &v67);
      v18 = *((_QWORD *)&v61 + 1);
      if ( *((_QWORD *)&v61 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    LODWORD(v67) = 0;
    v19 = ((__int64 (__fastcall *)(__int128 *))boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data4)(&v67);
    _InterlockedExchange(
      (volatile __int32 *)(*(__int64 (__fastcall **)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((char *)this + 1476),
      v19);
    if ( *((_QWORD *)this + 140) )
    {
      v20 = *((_QWORD *)this + 172);
      if ( v20 )
      {
        if ( *((_QWORD *)this + 170) )
        {
          v21 = *(_QWORD *)(v20 + 208);
          if ( *(_BYTE *)(v21 + 364) )
          {
            v67 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v67);
            if ( (_QWORD)v67 && *(_BYTE *)(v67 + 128) )
            {
              v25 = *((_QWORD *)this + 170);
              v26 = *((_QWORD *)this + 172);
              v61 = 0;
              v62 = 0;
              std::string::_Construct<1,char const *>(
                &v61,
                "LinkContext::InternalClose(): active close already checked for this server: relay=%p, base=%p",
                (const void *)0x5D,
                v24);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer *,Microsoft::Basix::Dct::ICECore::CandidateBase *>(
                (unsigned int)&v67,
                (unsigned int)"BASIX_DCT",
                (unsigned int)&v61,
                v26,
                v25);
              std::string::_Tidy_deallocate(&v61);
            }
            v27 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
            if ( *((_QWORD *)&v67 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
                if ( !_InterlockedDecrement(v27 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
              }
            }
          }
          else
          {
            v2 = 1;
            *(_BYTE *)(v21 + 364) = 1;
            _InterlockedIncrement((volatile signed __int32 *)(*(__int64 (__fastcall **)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((char *)this + 1476));
          }
        }
      }
    }
    v28 = *((_QWORD *)this + 176);
    if ( v28
      && *((_QWORD *)this + 170)
      && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                            (char *)this + 1376,
                            0)
      && *(_DWORD *)(v28 + 228) == 3 )
    {
      if ( *(_BYTE *)(v28 + 364) )
      {
        v67 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v67);
        if ( (_QWORD)v67 && *(_BYTE *)(v67 + 128) )
        {
          v30 = *((_QWORD *)this + 170);
          v31 = *((_QWORD *)this + 172);
          v61 = 0;
          v62 = 0;
          std::string::_Construct<1,char const *>(
            &v61,
            "LinkContext::InternalClose(): remote active close already checked for this server: relay=%p, base=%p",
            (const void *)0x64,
            v29);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer *,Microsoft::Basix::Dct::ICECore::CandidateBase *>(
            (unsigned int)&v67,
            (unsigned int)"BASIX_DCT",
            (unsigned int)&v61,
            v31,
            v30);
          std::string::_Tidy_deallocate(&v61);
        }
        v32 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
        if ( *((_QWORD *)&v67 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
            if ( !_InterlockedDecrement(v32 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
          }
        }
      }
      else
      {
        v3 = 1;
        *(_BYTE *)(v28 + 364) = 1;
        _InterlockedIncrement((volatile signed __int32 *)(*(__int64 (__fastcall **)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((char *)this + 1476));
      }
    }
    if ( v2 )
    {
      v67 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v67);
      if ( (_QWORD)v67 && *(_BYTE *)(v67 + 128) )
      {
        v34 = *((_QWORD *)this + 170);
        v35 = *((_QWORD *)this + 172);
        v61 = 0;
        v62 = 0;
        std::string::_Construct<1,char const *>(
          &v61,
          "LinkContext::InternalClose(): SendTurnActiveCloseRequest(): relay=%p, base=%p",
          (const void *)0x4D,
          v33);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer *,Microsoft::Basix::Dct::ICECore::CandidateBase *>(
          (unsigned int)&v67,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v61,
          v35,
          v34);
        std::string::_Tidy_deallocate(&v61);
      }
      v36 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
          if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
        }
      }
      v37 = *((_QWORD *)this + 170);
      v38 = (_QWORD *)Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::Dct::ICECore::LinkContext>(
                        (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
                        &v61);
      *(_QWORD *)&v67 = *v38;
      v39 = (volatile signed __int32 *)v38[1];
      *((_QWORD *)&v67 + 1) = v39;
      *v38 = 0;
      v38[1] = 0;
      v64 = 0;
      if ( (unsigned __int8)std::_Test_callable<_lambda_052e919cc0e5399df76dff3972c0cac1_>(&v67) )
      {
        v63[0] = &std::_Func_impl_no_alloc<_lambda_aac54c9ab8ddc8ed41d6208aeeaf132c_,void,std::exception_ptr>::`vftable';
        v63[1] = v40;
        v63[2] = v39;
        v67 = 0;
        v64 = v63;
        v39 = 0;
      }
      Microsoft::Basix::Dct::ICECore::CandidateBase::SendTurnActiveCloseRequest(v37, (char *)this + 1376, v63);
      if ( v64 )
      {
        LOBYTE(v41) = v64 != v63;
        (*(void (__fastcall **)(_QWORD *, __int64))(*v64 + 32LL))(v64, v41);
        v64 = 0;
      }
      if ( v39 )
      {
        if ( !_InterlockedDecrement(v39 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
          if ( !_InterlockedDecrement(v39 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
        }
      }
      v42 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
      if ( *((_QWORD *)&v61 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
          if ( !_InterlockedDecrement(v42 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
        }
      }
    }
    if ( v3 )
    {
      v43 = *((_QWORD *)this + 176);
      v67 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v67);
      if ( (_QWORD)v67 && *(_BYTE *)(v67 + 128) )
      {
        v45 = v43 + 128;
        if ( *(_QWORD *)(v43 + 152) > 0xFu )
          v45 = *(_QWORD *)(v43 + 128);
        v46 = *((_QWORD *)this + 170);
        v47 = *((_QWORD *)this + 172);
        v61 = 0;
        v62 = 0;
        std::string::_Construct<1,char const *>(
          &v61,
          "LinkContext::InternalClose(): SendRemoteTurnActiveCloseRequest(): relay=%p, base=%p, remoteServer=%s",
          (const void *)0x64,
          v44,
          v59);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer *,Microsoft::Basix::Dct::ICECore::CandidateBase *,char const *>(
          (unsigned int)&v67,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v61,
          v47,
          v46,
          v45);
        std::string::_Tidy_deallocate(&v61);
      }
      v48 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
          if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
        }
      }
      v49 = *((_QWORD *)this + 170);
      v50 = (_QWORD *)Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::Dct::ICECore::LinkContext>(
                        (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
                        &v61);
      *(_QWORD *)&v67 = *v50;
      v51 = (volatile signed __int32 *)v50[1];
      *((_QWORD *)&v67 + 1) = v51;
      *v50 = 0;
      v50[1] = 0;
      v66 = 0;
      if ( (unsigned __int8)std::_Test_callable<_lambda_052e919cc0e5399df76dff3972c0cac1_>(&v67) )
      {
        v65[0] = &std::_Func_impl_no_alloc<_lambda_4649970518feeff33af745faa8befa6c_,void,std::exception_ptr>::`vftable';
        v65[1] = v52;
        v65[2] = v51;
        v67 = 0;
        v66 = v65;
        v51 = 0;
      }
      Microsoft::Basix::Dct::ICECore::CandidateBase::SendRemoteTurnActiveCloseRequest(
        v49,
        (char *)this + 1376,
        v43 + 128,
        v65);
      if ( v66 )
      {
        LOBYTE(v53) = v66 != v65;
        (*(void (__fastcall **)(_QWORD *, __int64))(*v66 + 32LL))(v66, v53);
        v66 = 0;
      }
      if ( v51 )
      {
        if ( !_InterlockedDecrement(v51 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
          if ( !_InterlockedDecrement(v51 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
        }
      }
      v54 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
      if ( *((_QWORD *)&v61 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
          if ( !_InterlockedDecrement(v54 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
        }
      }
    }
    if ( !*(_DWORD *)(*(__int64 (__fastcall **)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((char *)this + 1476) )
    {
      Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnClosed(this, 0);
      v67 = 0;
      v55 = *((_QWORD *)this + 183);
      if ( v55 )
      {
        v56 = *(_DWORD *)(v55 + 8);
        while ( v56 )
        {
          v57 = v56;
          v56 = _InterlockedCompareExchange((volatile signed __int32 *)(v55 + 8), v56 + 1, v56);
          if ( v57 == v56 )
          {
            *(_QWORD *)&v58 = *((_QWORD *)this + 182);
            *(_QWORD *)&v67 = v58;
            *((_QWORD *)&v58 + 1) = *((_QWORD *)this + 183);
            *((_QWORD *)&v67 + 1) = *((_QWORD *)&v58 + 1);
            goto LABEL_99;
          }
        }
      }
      v58 = v67;
LABEL_99:
      if ( (_QWORD)v58 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v58 + 8LL))(v58);
      if ( *((_QWORD *)&v58 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 8LL)) )
        {
          (***((void (__fastcall ****)(_QWORD))&v58 + 1))(*((_QWORD *)&v58 + 1));
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 12LL)) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v58 + 1) + 8LL))(*((_QWORD *)&v58 + 1));
        }
      }
    }
    if ( *((_QWORD *)&v15 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v15 + 1) + 8LL)) )
      {
        (***((void (__fastcall ****)(_QWORD))&v15 + 1))(*((_QWORD *)&v15 + 1));
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v15 + 1) + 12LL)) )
        {
          v10 = (void (__fastcall **)(__int64))**((_QWORD **)&v15 + 1);
          v11 = *((_QWORD *)&v15 + 1);
          goto LABEL_110;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18022c110  mov     rax, rsp
0x18022c113  mov     [rax+10h], rbx
0x18022c117  mov     [rax+18h], rsi
0x18022c11b  mov     [rax+20h], rdi
0x18022c11f  push    rbp
0x18022c120  push    r12
0x18022c122  push    r13
0x18022c124  push    r14
0x18022c126  push    r15
0x18022c128  lea     rbp, [rax-38h]
0x18022c12c  mov     eax, 110h
0x18022c131  call    _alloca_probe
0x18022c136  sub     rsp, rax
0x18022c139  mov     rax, cs:__security_cookie
0x18022c140  xor     rax, rsp
0x18022c143  mov     [rbp+30h+var_30], rax
0x18022c147  mov     rsi, rcx
0x18022c14a  xor     r13d, r13d
0x18022c14d  mov     r15b, r13b
0x18022c150  mov     r12b, r13b
0x18022c153  xorps   xmm0, xmm0
0x18022c156  movups  [rbp+30h+var_40], xmm0
0x18022c15a  lea     rcx, [rbp+30h+var_40]
0x18022c15e  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18022c163  nop
0x18022c164  mov     rax, qword ptr [rbp+30h+var_40]
0x18022c168  test    rax, rax
0x18022c16b  jz      short loc_18022C1C1
0x18022c16d  cmp     [rax+80h], r13b
0x18022c174  jz      short loc_18022C1C1
0x18022c176  xorps   xmm0, xmm0
0x18022c179  movups  [rsp+130h+var_100+8], xmm0
0x18022c17e  xorps   xmm1, xmm1
0x18022c181  movdqu  xmmword ptr [rsp+130h+var_F0+8], xmm1
0x18022c187  lea     r8d, [r13+2Eh]
0x18022c18b  lea     rdx, aIcecoreLinkcon_7; "ICECore::LinkContext::InternalClose() ="...
0x18022c192  lea     rcx, [rsp+130h+var_100+8]
0x18022c197  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022c19c  nop
0x18022c19d  mov     r9, rsi
0x18022c1a0  lea     r8, [rsp+130h+var_100+8]
0x18022c1a5  lea     rdx, aBasixDct; "BASIX_DCT"
0x18022c1ac  lea     rcx, [rbp+30h+var_40]
0x18022c1b0  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEAVISmilesLink@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVISmilesLink@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,Microsoft::Basix::Dct::ISmilesLink *)
0x18022c1b5  nop
0x18022c1b6  lea     rcx, [rsp+130h+var_100+8]
0x18022c1bb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18022c1c0  nop
0x18022c1c1  or      edi, 0FFFFFFFFh
0x18022c1c4  mov     rbx, qword ptr [rbp+30h+var_40+8]
0x18022c1c8  test    rbx, rbx
0x18022c1cb  jz      short loc_18022C202
0x18022c1cd  mov     eax, edi
0x18022c1cf  lock xadd [rbx+8], eax
0x18022c1d4  add     eax, edi
0x18022c1d6  jnz     short loc_18022C202
0x18022c1d8  mov     rax, [rbx]
0x18022c1db  mov     rcx, rbx
0x18022c1de  mov     rax, [rax]
0x18022c1e1  call    cs:__guard_dispatch_icall_fptr
0x18022c1e7  mov     eax, edi
0x18022c1e9  lock xadd [rbx+0Ch], eax
0x18022c1ee  add     eax, edi
0x18022c1f0  jnz     short loc_18022C202
0x18022c1f2  mov     rax, [rbx]
0x18022c1f5  mov     rcx, rbx
0x18022c1f8  mov     rax, [rax+8]
0x18022c1fc  call    cs:__guard_dispatch_icall_fptr
0x18022c202  mov     byte ptr [rsp+130h+var_100], 1
0x18022c207  lea     rcx, [rsp+130h+var_100]
0x18022c20c  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data2; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18022c211  mov     bl, al
0x18022c213  lea     rcx, [rsi+5C0h]
0x18022c21a  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18022c21f  xchg    bl, [rax]
0x18022c221  test    bl, bl
0x18022c223  jz      loc_18022C2DB
0x18022c229  xorps   xmm0, xmm0
0x18022c22c  movups  [rbp+30h+var_40], xmm0
0x18022c230  lea     rcx, [rbp+30h+var_40]
0x18022c234  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18022c239  nop
0x18022c23a  mov     rax, qword ptr [rbp+30h+var_40]
0x18022c23e  test    rax, rax
0x18022c241  jz      short loc_18022C296
0x18022c243  cmp     [rax+80h], r13b
0x18022c24a  jz      short loc_18022C296
0x18022c24c  xorps   xmm0, xmm0
0x18022c24f  movups  [rsp+130h+var_100+8], xmm0
0x18022c254  xorps   xmm1, xmm1
0x18022c257  movdqu  xmmword ptr [rsp+130h+var_F0+8], xmm1
0x18022c25d  mov     r8d, 45h ; 'E'
0x18022c263  lea     rdx, aIcecoreLinkcon; "ICECore::LinkContext::InternalClose(): "...
0x18022c26a  lea     rcx, [rsp+130h+var_100+8]
0x18022c26f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022c274  nop
0x18022c275  lea     r8, [rsp+130h+var_100+8]
0x18022c27a  lea     rdx, aBasixDct; "BASIX_DCT"
0x18022c281  lea     rcx, [rbp+30h+var_40]
0x18022c285  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x18022c28a  nop
0x18022c28b  lea     rcx, [rsp+130h+var_100+8]
0x18022c290  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18022c295  nop
0x18022c296  mov     rbx, qword ptr [rbp+30h+var_40+8]
0x18022c29a  test    rbx, rbx
0x18022c29d  jz      loc_18022CB3C
0x18022c2a3  mov     eax, edi
0x18022c2a5  lock xadd [rbx+8], eax
0x18022c2aa  add     eax, edi
0x18022c2ac  jnz     loc_18022CB3C
0x18022c2b2  mov     rax, [rbx]
0x18022c2b5  mov     rcx, rbx
0x18022c2b8  mov     rax, [rax]
0x18022c2bb  call    cs:__guard_dispatch_icall_fptr
0x18022c2c1  mov     eax, edi
0x18022c2c3  lock xadd [rbx+0Ch], eax
0x18022c2c8  add     eax, edi
0x18022c2ca  jnz     loc_18022CB3C
0x18022c2d0  mov     rax, [rbx]
0x18022c2d3  mov     rcx, rbx
0x18022c2d6  jmp     loc_18022CB32
0x18022c2db  xorps   xmm1, xmm1
0x18022c2de  movdqu  [rbp+30h+var_40], xmm1
0x18022c2e3  mov     rdx, [rsi+5B8h]
0x18022c2ea  test    rdx, rdx
0x18022c2ed  jz      short loc_18022C306
0x18022c2ef  mov     eax, [rdx+8]
0x18022c2f2  jmp     short loc_18022C302
0x18022c2f4  lea     ecx, [rax+1]
0x18022c2f7  lock cmpxchg [rdx+8], ecx
0x18022c2fc  jz      loc_18022C3FB
0x18022c302  test    eax, eax
0x18022c304  jnz     short loc_18022C2F4
0x18022c306  mov     rdi, qword ptr [rbp+30h+var_40]
0x18022c30a  mov     r14, qword ptr [rbp+30h+var_40+8]
0x18022c30e  test    rdi, rdi
0x18022c311  jz      short loc_18022C386
0x18022c313  mov     rax, [rdi]
0x18022c316  mov     rbx, [rax]
0x18022c319  mov     rax, [rsi+8]
0x18022c31d  movsxd  rcx, dword ptr [rax+4]
0x18022c321  add     rcx, 8
0x18022c325  add     rcx, rsi
0x18022c328  lea     rdx, [rsp+130h+var_100+8]
0x18022c32d  call    ??$GetWeakPtr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::ICECore::LinkContext>(void)
0x18022c332  nop
0x18022c333  xorps   xmm0, xmm0
0x18022c336  movdqu  [rbp+30h+var_50], xmm0
0x18022c33b  mov     rdx, [rax]
0x18022c33e  mov     qword ptr [rbp+30h+var_50], rdx
0x18022c342  mov     rdx, [rax+8]
0x18022c346  mov     qword ptr [rbp+30h+var_50+8], rdx
0x18022c34a  mov     [rax], r13
0x18022c34d  mov     [rax+8], r13
0x18022c351  lea     rdx, [rbp+30h+var_50]
0x18022c355  mov     rcx, rdi
0x18022c358  mov     rax, rbx
0x18022c35b  call    cs:__guard_dispatch_icall_fptr
0x18022c361  nop
0x18022c362  mov     rcx, qword ptr [rsp+130h+var_F0]
0x18022c367  test    rcx, rcx
0x18022c36a  jz      short loc_18022C386
0x18022c36c  or      eax, 0FFFFFFFFh
0x18022c36f  lock xadd [rcx+0Ch], eax
0x18022c374  cmp     eax, 1
0x18022c377  jnz     short loc_18022C386
0x18022c379  mov     rax, [rcx]
0x18022c37c  mov     rax, [rax+8]
0x18022c380  call    cs:__guard_dispatch_icall_fptr
0x18022c386  mov     dword ptr [rbp+30h+var_50], r13d
0x18022c38a  lea     r13, [rsi+5C4h]
0x18022c391  lea     rcx, [rbp+30h+var_50]
0x18022c395  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data4; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18022c39a  mov     ebx, eax
0x18022c39c  mov     rcx, r13
0x18022c39f  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18022c3a4  xchg    ebx, [rax]
0x18022c3a6  xor     ebx, ebx
0x18022c3a8  cmp     [rsi+460h], rbx
0x18022c3af  jz      loc_18022C4D9
0x18022c3b5  mov     rax, [rsi+560h]
0x18022c3bc  test    rax, rax
0x18022c3bf  jz      loc_18022C4D9
0x18022c3c5  cmp     [rsi+550h], rbx
0x18022c3cc  jz      loc_18022C4D9
0x18022c3d2  mov     rax, [rax+0D0h]
0x18022c3d9  cmp     [rax+16Ch], bl
0x18022c3df  jnz     short loc_18022C416
0x18022c3e1  mov     r15b, 1
0x18022c3e4  mov     [rax+16Ch], r15b
0x18022c3eb  mov     rcx, r13
0x18022c3ee  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18022c3f3  lock inc dword ptr [rax]
0x18022c3f6  jmp     loc_18022C4D9
0x18022c3fb  mov     rdi, [rsi+5B0h]
0x18022c402  mov     qword ptr [rbp+30h+var_40], rdi
0x18022c406  mov     r14, [rsi+5B8h]
0x18022c40d  mov     qword ptr [rbp+30h+var_40+8], r14
0x18022c411  jmp     loc_18022C30E
0x18022c416  xorps   xmm0, xmm0
0x18022c419  movups  [rbp+30h+var_50], xmm0
0x18022c41d  lea     rcx, [rbp+30h+var_50]
0x18022c421  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18022c426  nop
0x18022c427  mov     rax, qword ptr [rbp+30h+var_50]
0x18022c42b  test    rax, rax
0x18022c42e  jz      short loc_18022C498
0x18022c430  cmp     [rax+80h], bl
0x18022c436  jz      short loc_18022C498
0x18022c438  mov     rbx, [rsi+550h]
0x18022c43f  mov     rdi, [rsi+560h]
0x18022c446  xorps   xmm0, xmm0
0x18022c449  movups  [rsp+130h+var_100+8], xmm0
0x18022c44e  xorps   xmm1, xmm1
0x18022c451  movdqu  xmmword ptr [rsp+130h+var_F0+8], xmm1
0x18022c457  mov     r8d, 5Dh ; ']'
0x18022c45d  lea     rdx, aLinkcontextInt; "LinkContext::InternalClose(): active cl"...
0x18022c464  lea     rcx, [rsp+130h+var_100+8]
0x18022c469  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022c46e  nop
0x18022c46f  mov     [rsp+130h+var_110], rbx
0x18022c474  mov     r9, rdi
0x18022c477  lea     r8, [rsp+130h+var_100+8]
0x18022c47c  lea     rdx, aBasixDct; "BASIX_DCT"
0x18022c483  lea     rcx, [rbp+30h+var_50]
0x18022c487  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEAVTurnServer@CandidateBase@ICECore@Dct@23@PEAV56723@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVTurnServer@CandidateBase@ICECore@Dct@23@PEAV89Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer *,Microsoft::Basix::Dct::ICECore::CandidateBase *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer *,Microsoft::Basix::Dct::ICECore::CandidateBase *)
0x18022c48c  nop
0x18022c48d  lea     rcx, [rsp+130h+var_100+8]
0x18022c492  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18022c497  nop
0x18022c498  mov     rbx, qword ptr [rbp+30h+var_50+8]
0x18022c49c  test    rbx, rbx
0x18022c49f  jz      short loc_18022C4D9
0x18022c4a1  or      edi, 0FFFFFFFFh
0x18022c4a4  mov     eax, edi
0x18022c4a6  lock xadd [rbx+8], eax
0x18022c4ab  add     eax, edi
0x18022c4ad  jnz     short loc_18022C4D9
0x18022c4af  mov     rax, [rbx]
0x18022c4b2  mov     rcx, rbx
0x18022c4b5  mov     rax, [rax]
0x18022c4b8  call    cs:__guard_dispatch_icall_fptr
0x18022c4be  mov     eax, edi
0x18022c4c0  lock xadd [rbx+0Ch], eax
0x18022c4c5  add     eax, edi
0x18022c4c7  jnz     short loc_18022C4D9
0x18022c4c9  mov     rax, [rbx]
0x18022c4cc  mov     rcx, rbx
0x18022c4cf  mov     rax, [rax+8]
0x18022c4d3  call    cs:__guard_dispatch_icall_fptr
0x18022c4d9  mov     rbx, [rsi+580h]
0x18022c4e0  test    rbx, rbx
0x18022c4e3  jz      loc_18022C600
0x18022c4e9  cmp     qword ptr [rsi+550h], 0
0x18022c4f1  jz      loc_18022C600
0x18022c4f7  lea     rdi, [rsi+560h]
0x18022c4fe  xor     edx, edx
0x18022c500  mov     rcx, rdi
0x18022c503  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18022c508  test    al, al
0x18022c50a  jz      loc_18022C600
0x18022c510  cmp     dword ptr [rbx+0E4h], 3
0x18022c517  jnz     loc_18022C600
0x18022c51d  cmp     byte ptr [rbx+16Ch], 0
0x18022c524  jnz     short loc_18022C540
0x18022c526  mov     r12b, 1
0x18022c529  mov     [rbx+16Ch], r12b
0x18022c530  mov     rcx, r13
0x18022c533  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18022c538  lock inc dword ptr [rax]
0x18022c53b  jmp     loc_18022C600
0x18022c540  xorps   xmm0, xmm0
0x18022c543  movups  [rbp+30h+var_50], xmm0
0x18022c547  lea     rcx, [rbp+30h+var_50]
0x18022c54b  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18022c550  nop
0x18022c551  mov     rax, qword ptr [rbp+30h+var_50]
0x18022c555  test    rax, rax
0x18022c558  jz      short loc_18022C5BF
0x18022c55a  cmp     byte ptr [rax+80h], 0
0x18022c561  jz      short loc_18022C5BF
0x18022c563  mov     rbx, [rsi+550h]
0x18022c56a  mov     rdi, [rdi]
0x18022c56d  xorps   xmm0, xmm0
0x18022c570  movups  [rsp+130h+var_100+8], xmm0
0x18022c575  xorps   xmm1, xmm1
0x18022c578  movdqu  xmmword ptr [rsp+130h+var_F0+8], xmm1
0x18022c57e  mov     r8d, 64h ; 'd'
0x18022c584  lea     rdx, aLinkcontextInt_1; "LinkContext::InternalClose(): remote ac"...
0x18022c58b  lea     rcx, [rsp+130h+var_100+8]
0x18022c590  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022c595  nop
0x18022c596  mov     [rsp+130h+var_110], rbx
0x18022c59b  mov     r9, rdi
0x18022c59e  lea     r8, [rsp+130h+var_100+8]
0x18022c5a3  lea     rdx, aBasixDct; "BASIX_DCT"
0x18022c5aa  lea     rcx, [rbp+30h+var_50]
0x18022c5ae  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEAVTurnServer@CandidateBase@ICECore@Dct@23@PEAV56723@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVTurnServer@CandidateBase@ICECore@Dct@23@PEAV89Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer *,Microsoft::Basix::Dct::ICECore::CandidateBase *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,Microsoft::Basix::Dct::ICECore::CandidateBase::TurnServer *,Microsoft::Basix::Dct::ICECore::CandidateBase *)
0x18022c5b3  nop
  ... truncated ...
```

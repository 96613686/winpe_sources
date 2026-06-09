# Microsoft::Basix::Dct::ICE::Agent::CheckForTriggeredPair(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,Microsoft::Basix::Dct::ICE::Agent::RelayName const &)

- ea: `0x1801ec1d0`
- end: `0x1801ed524`
- name: `?CheckForTriggeredPair@Agent@ICE@Dct@Basix@Microsoft@@UEAA?AVCandidatePair@12345@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0AEBURelayName@12345@@Z`
- size: `4948`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017338`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x180024700`
- `0x180024760`
- `0x180029d6c`
- `0x18003302c`
- `0x1800bf3ac`
- `0x1800c838c`
- `0x1800f30dc`
- `0x1800f93f4`
- `0x180106038`
- `0x1801d89b4`
- `0x1801da718`
- `0x1801dab7c`
- `0x1801dc730`
- `0x1801e283c`
- `0x1801e3f8c`
- `0x1801ec1d0`
- `0x1801ed8e0`
- `0x1801f6110`
- `0x1801faa18`
- `0x180287f0c`
- `0x1802e2464`
- `0x1802e9b68`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f140`
- `0x180330b40`
- `0x180375c40`
- `0x180376380`

## string_xrefs

- `0x1801eca69`: `ICEAgent`
- `0x1801ec604`: `new peer reflexive candidate pair created: local=%s, remote=%s`
- `0x1801ed446`: `C:\__w\1\s\src\libbasix-network\dct\ice\agent.cpp`
- `0x1801ed498`: `C:\__w\1\s\src\libbasix-network\dct\ice\agent.cpp`
- `0x1801ed458`: `new peer reflexive pair must be created first`

## pseudocode

```c
// Hidden C++ exception states: #wind=55
__int64 __fastcall Microsoft::Basix::Dct::ICE::Agent::CheckForTriggeredPair(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v7; // r14
  char v9; // si
  struct Microsoft::Basix::Instrumentation::ActivityManager *v10; // rax
  __int64 v11; // r9
  char v12; // r13
  __int64 v13; // rax
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v18; // rbx
  _BYTE *v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rbx
  _QWORD *v22; // rdx
  __int64 v23; // rdx
  signed __int32 v24; // eax
  signed __int32 v25; // ett
  void *v26; // rcx
  volatile signed __int32 *v27; // rbx
  __int64 *v28; // rax
  __int64 v29; // r12
  __int64 *v30; // rax
  const char *v31; // r9
  __int64 v32; // rdi
  volatile signed __int32 *v33; // rdi
  _QWORD *v34; // rax
  _QWORD *v35; // rdi
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rdx
  _QWORD *v42; // rax
  _QWORD *v43; // rdi
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rdx
  volatile signed __int32 *v50; // rdi
  char v51; // r9
  unsigned int *v52; // rcx
  unsigned __int64 v53; // r8
  unsigned int *v54; // rax
  unsigned __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rcx
  unsigned __int64 v58; // rax
  int v59; // eax
  struct _Mtx_internal_imp_t *v60; // rbx
  volatile signed __int32 *v61; // rbx
  volatile signed __int32 *v62; // rbx
  __int64 v63; // r13
  __int64 v64; // rdi
  __int64 *v65; // r12
  __int64 v66; // rax
  __int64 v67; // rbx
  __int64 v68; // r14
  __int64 v69; // r13
  __int64 v70; // rdx
  volatile signed __int32 *v71; // rbx
  volatile signed __int32 *v72; // rbx
  const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair *v73; // rdi
  const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair *v74; // r12
  volatile signed __int32 *v75; // rbx
  volatile signed __int32 *v76; // rbx
  struct Microsoft::Basix::Instrumentation::ActivityManager *v77; // rax
  char v78; // r12
  _QWORD **v79; // r13
  _QWORD *i; // rdi
  const struct std::nothrow_t *v81; // rdx
  __int64 v82; // rax
  char v83; // si
  void *v84; // rcx
  __int64 v85; // rax
  char v86; // si
  void *v87; // rcx
  struct Microsoft::Basix::Instrumentation::ActivityManager *v88; // rax
  char v90; // [rsp+40h] [rbp-C0h]
  __int64 v91; // [rsp+48h] [rbp-B8h]
  void *v93[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v94; // [rsp+68h] [rbp-98h]
  char v95; // [rsp+70h] [rbp-90h]
  _BYTE v96[16]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v97[48]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v98[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v99[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v100[32]; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v101[2]; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v102[2]; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v103[2]; // [rsp+158h] [rbp+58h] BYREF
  _OWORD v104[2]; // [rsp+178h] [rbp+78h] BYREF
  _OWORD v105[2]; // [rsp+198h] [rbp+98h] BYREF
  _OWORD v106[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  _OWORD v107[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  _OWORD v108[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  _OWORD v109[2]; // [rsp+218h] [rbp+118h] BYREF
  __int64 v110; // [rsp+238h] [rbp+138h]
  _BYTE v111[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v112[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v113[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v114[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v115[4]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v116[4]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v117[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v118[32]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v119[32]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+360h] [rbp+260h] BYREF
  void *v121[2]; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int128 v122; // [rsp+3F0h] [rbp+2F0h]
  _OWORD v123[4]; // [rsp+400h] [rbp+300h] BYREF
  _OWORD v124[2]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v125[16]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v126[64]; // [rsp+470h] [rbp+370h] BYREF

  v7 = a2;
  v110 = a2;
  v9 = 0;
  v10 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
  LOBYTE(v11) = 1;
  Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(v10, v125, a1 + 696, v11);
  v12 = 0;
  v90 = 0;
  memset(v123, 0, sizeof(v123));
  Microsoft::Basix::Dct::ICE::Agent::FindPairFromBindingRequest(a1, (unsigned int)v123, a3, a4, a5);
  v13 = *(_QWORD *)&v123[1];
  if ( !*(_QWORD *)&v123[1] )
  {
    v14 = (__int64 *)std::make_shared<Microsoft::Basix::Dct::ICE::Candidate,>(v121);
    v15 = *v14;
    v16 = v14[1];
    *v14 = 0;
    v14[1] = 0;
    *(_QWORD *)&v123[1] = v15;
    v17 = (volatile signed __int32 *)*((_QWORD *)&v123[1] + 1);
    *((_QWORD *)&v123[1] + 1) = v16;
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v18 = (volatile signed __int32 *)v121[1];
    if ( v121[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v121[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    *(_DWORD *)(*(_QWORD *)&v123[1] + 228LL) = 2;
    v19 = (_BYTE *)a4;
    if ( *(_QWORD *)(a4 + 24) > 0xFu )
      v19 = *(_BYTE **)a4;
    *(_BYTE *)(*(_QWORD *)&v123[1] + 224LL) = *v19 == 91;
    std::string::operator=(*(_QWORD *)&v123[1] + 64LL, a4);
    std::string::operator=(*(_QWORD *)&v123[1] + 160LL, a4);
    v20 = *(_QWORD *)&v123[1];
    *(_OWORD *)v121 = 0;
    v122 = 0;
    std::string::_Construct<1,char const *>(v121, (const char *)&Str1, 0);
    std::string::operator=(v20 + 96, v121);
    std::string::_Tidy_deallocate(v121);
    v21 = *(_QWORD *)&v123[1];
    *(_OWORD *)v121 = 0;
    v122 = 0;
    std::string::_Construct<1,char const *>(v121, (const char *)&Str1, 0);
    std::string::operator=(v21 + 128, v121);
    std::string::_Tidy_deallocate(v121);
    *(_DWORD *)(*(_QWORD *)&v123[1] + 232LL) = 0;
    std::string::operator=(*(_QWORD *)&v123[1] + 248LL, *(_QWORD *)&v123[0] + 248LL);
    Microsoft::Basix::Dct::ICE::Candidate::ComputeFoundationAndPriority(
      *(Microsoft::Basix::Dct::ICE::Candidate **)&v123[1],
      0xFFFFu);
    if ( Mtx_lock((_Mtx_t)(a1 + 240)) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(a1 + 316) == 0x7FFFFFFF )
    {
      *(_DWORD *)(a1 + 316) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v22 = *(_QWORD **)(a1 + 1168);
    if ( v22 == *(_QWORD **)(a1 + 1176) )
    {
      std::vector<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &>(
        a1 + 1160,
        v22,
        &v123[1]);
    }
    else
    {
      *v22 = 0;
      v22[1] = 0;
      if ( *((_QWORD *)&v123[1] + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v123[1] + 1) + 8LL));
      *(_OWORD *)v22 = v123[1];
      *(_QWORD *)(a1 + 1168) += 16LL;
    }
    Mtx_unlock((_Mtx_t)(a1 + 240));
    v12 = 1;
    v90 = 1;
    *(_OWORD *)v93 = 0;
    v23 = *(_QWORD *)(a1 + 904);
    if ( v23 )
    {
      v24 = *(_DWORD *)(v23 + 8);
      while ( v24 )
      {
        v25 = v24;
        v24 = _InterlockedCompareExchange((volatile signed __int32 *)(v23 + 8), v24 + 1, v24);
        if ( v25 == v24 )
        {
          v26 = *(void **)(a1 + 896);
          v93[0] = v26;
          v27 = *(volatile signed __int32 **)(a1 + 904);
          v93[1] = (void *)v27;
          goto LABEL_24;
        }
      }
    }
    v26 = v93[0];
    v27 = (volatile signed __int32 *)v93[1];
LABEL_24:
    if ( v26 )
      (*(void (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)v26 + 160LL))(v26, *(_QWORD *)&v123[0] + 32LL, 0);
    v124[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v124);
    if ( *(_QWORD *)&v124[0] && *(_BYTE *)(*(_QWORD *)&v124[0] + 128LL) )
    {
      v28 = (__int64 *)Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v99, *(_QWORD *)&v123[1], 0, 6);
      v29 = (__int64)v28;
      if ( (unsigned __int64)v28[3] > 0xF )
        v29 = *v28;
      v30 = (__int64 *)Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(
                         v100,
                         *(_QWORD *)&v123[0],
                         0,
                         6);
      LODWORD(v32) = (_DWORD)v30;
      if ( (unsigned __int64)v30[3] > 0xF )
        v32 = *v30;
      *(_OWORD *)v121 = 0;
      v122 = 0;
      std::string::_Construct<1,char const *>(
        v121,
        "new peer reflexive candidate pair created: local=%s, remote=%s",
        (const char *)0x3E,
        v31);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *>(
        (unsigned int)v124,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v121,
        v32,
        v29);
      std::string::_Tidy_deallocate(v121);
      std::string::_Tidy_deallocate(v100);
      std::string::_Tidy_deallocate(v99);
    }
    v33 = (volatile signed __int32 *)*((_QWORD *)&v124[0] + 1);
    if ( *((_QWORD *)&v124[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    *(_OWORD *)v121 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v121);
    if ( v121[0] && *((_BYTE *)v121[0] + 128) )
    {
      memset(v109, 0, sizeof(v109));
      std::string::_Construct<1,char const *>(v109, "\"", 1);
      v34 = (_QWORD *)Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v96, *(_QWORD *)&v123[1], 0, 6);
      v35 = v34;
      if ( v34[3] > 0xFu )
        v35 = (_QWORD *)*v34;
      memset(v108, 0, sizeof(v108));
      std::string::_Construct<1,char const *>(v108, "\"", 1);
      memset(v107, 0, sizeof(v107));
      std::string::_Construct<1,char const *>(v107, ":", 1);
      memset(v106, 0, sizeof(v106));
      std::string::_Construct<1,char const *>(v106, "\"", 1);
      memset(v105, 0, sizeof(v105));
      std::string::_Construct<1,char const *>(v105, "\"", 1);
      v36 = std::operator+<char>(v98, v105, "RemoteCandidate");
      LOBYTE(v37) = 1;
      std::string::string(v100, v37, v36, v106);
      LOBYTE(v38) = 1;
      std::string::string(v99, v38, v100, v107);
      LOBYTE(v39) = 1;
      std::string::string(v114, v39, v99, v108);
      v40 = std::operator+<char>(v126, v114, v35);
      LOBYTE(v41) = 1;
      std::string::string(v115, v41, v40, v109);
      memset(v104, 0, sizeof(v104));
      std::string::_Construct<1,char const *>(v104, "\"", 1);
      v42 = (_QWORD *)Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v119, *(_QWORD *)&v123[0], 0, 6);
      v43 = v42;
      if ( v42[3] > 0xFu )
        v43 = (_QWORD *)*v42;
      memset(v103, 0, sizeof(v103));
      std::string::_Construct<1,char const *>(v103, "\"", 1);
      memset(v102, 0, sizeof(v102));
      std::string::_Construct<1,char const *>(v102, ":", 1);
      memset(v124, 0, sizeof(v124));
      std::string::_Construct<1,char const *>(v124, "\"", 1);
      memset(v101, 0, sizeof(v101));
      std::string::_Construct<1,char const *>(v101, "\"", 1);
      v44 = std::operator+<char>(v118, v101, "LocalCandidate");
      LOBYTE(v45) = 1;
      std::string::string(v113, v45, v44, v124);
      LOBYTE(v46) = 1;
      std::string::string(v112, v46, v113, v102);
      LOBYTE(v47) = 1;
      std::string::string(v111, v47, v112, v103);
      v48 = std::operator+<char>(v117, v111, v43);
      LOBYTE(v49) = 1;
      std::string::string(v116, v49, v48, v104);
      v9 = -32;
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string>(
        (int)v121,
        (int)"RD_CHECKPOINT",
        0,
        (int)"ICEAgent",
        "PairCreation",
        "new PeerReflexive pair added",
        (__int64)v116,
        (__int64)v115);
      std::string::_Tidy_deallocate(v117);
      std::string::_Tidy_deallocate(v111);
      std::string::_Tidy_deallocate(v112);
      std::string::_Tidy_deallocate(v113);
      std::string::_Tidy_deallocate(v118);
      std::string::_Tidy_deallocate(v101);
      std::string::_Tidy_deallocate(v124);
      std::string::_Tidy_deallocate(v102);
      std::string::_Tidy_deallocate(v103);
      std::string::_Tidy_deallocate(v119);
      std::string::_Tidy_deallocate(v104);
      std::string::_Tidy_deallocate(v126);
      std::string::_Tidy_deallocate(v114);
      std::string::_Tidy_deallocate(v99);
      std::string::_Tidy_deallocate(v100);
      std::string::_Tidy_deallocate(v98);
      std::string::_Tidy_deallocate(v105);
      std::string::_Tidy_deallocate(v106);
      std::string::_Tidy_deallocate(v107);
      std::string::_Tidy_deallocate(v108);
      std::string::_Tidy_deallocate(v96);
      std::string::_Tidy_deallocate(v109);
    }
    v50 = (volatile signed __int32 *)v121[1];
    if ( v121[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v121[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
        if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
      }
    }
    if ( v27 )
    {
      if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
        if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
    v13 = *(_QWORD *)&v123[1];
  }
  v51 = *(_BYTE *)(a1 + 524);
  v52 = (unsigned int *)(*(_QWORD *)&v123[0] + 236LL);
  if ( !v51 )
    v52 = (unsigned int *)(v13 + 236);
  v53 = *v52;
  if ( v51 )
    v54 = (unsigned int *)(v13 + 236);
  else
    v54 = (unsigned int *)(*(_QWORD *)&v123[0] + 236LL);
  v55 = *v54;
  v56 = *v52;
  if ( v55 < v53 )
    v56 = *v54;
  v57 = v56 << 31;
  v58 = v53;
  if ( v53 < v55 )
    v58 = v55;
  *((_QWORD *)&v123[2] + 1) = (v53 > v55) + 2 * (v58 + v57);
  v59 = v53;
  if ( v53 > v55 )
    v59 = v55;
  if ( v53 < v55 )
    LODWORD(v53) = v55;
  LODWORD(v123[3]) = v53 + 3 * v59;
  Microsoft::Basix::Dct::_anonymous_namespace_::PairMatcher(v126, v123);
  v60 = (struct _Mtx_internal_imp_t *)(a1 + 240);
  *(_QWORD *)&v124[0] = a1 + 240;
  if ( Mtx_lock((_Mtx_t)(a1 + 240)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 316) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 316) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( v12 )
    goto LABEL_119;
  if ( (unsigned __int8)Microsoft::Basix::Dct::ICE::Agent::SucceededPairMatchUnlocked(a1, v123, 0) )
  {
    *(_OWORD *)v7 = v123[0];
    v123[0] = 0;
    *(_OWORD *)(v7 + 16) = v123[1];
    v123[1] = 0;
    *(_OWORD *)(v7 + 32) = v123[2];
    *(_DWORD *)(v7 + 48) = v123[3];
    *(_BYTE *)(v7 + 52) = BYTE4(v123[3]);
    *(_DWORD *)(v7 + 56) = DWORD2(v123[3]);
    Mtx_unlock((_Mtx_t)(a1 + 240));
    Microsoft::Basix::TimerWheel::InstancePerSession::~InstancePerSession((Microsoft::Basix::TimerWheel::InstancePerSession *)v126);
    v61 = (volatile signed __int32 *)*((_QWORD *)&v123[1] + 1);
    if ( *((_QWORD *)&v123[1] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123[1] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
        if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
      }
    }
    v62 = (volatile signed __int32 *)*((_QWORD *)&v123[0] + 1);
    if ( *((_QWORD *)&v123[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
        if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
      }
    }
LABEL_118:
    v77 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
    (*(void (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, void **, _BYTE *))(*(_QWORD *)v77 + 32LL))(
      v77,
      v121,
      v125);
    return v7;
  }
  Microsoft::Basix::Dct::ICE::Agent::CandidatePair::CandidatePair(
    (Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v96,
    (const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v126);
  v63 = a1 + 1312;
  v64 = *(_QWORD *)(a1 + 1336);
  if ( a1 == -1312 )
  {
    v65 = 0;
    goto LABEL_84;
  }
  v65 = *(__int64 **)v63;
  if ( !*(_QWORD *)v63 )
  {
LABEL_84:
    v66 = 0;
    goto LABEL_85;
  }
  v66 = *v65;
LABEL_85:
  if ( v64 != v64 + *(_QWORD *)(a1 + 1344) )
  {
    v67 = *(_QWORD *)(v66 + 8);
    v68 = *(_QWORD *)(v66 + 16);
    v69 = v64 + *(_QWORD *)(a1 + 1344);
    do
    {
      v91 = *(_QWORD *)(v67 + 8 * (v64 & (v68 - 1)));
      if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                              v96,
                              v91)
        && (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                              v97,
                              v91 + 16) )
      {
        break;
      }
      ++v64;
    }
    while ( v64 != v69 );
    v60 = (struct _Mtx_internal_imp_t *)(a1 + 240);
    v7 = a2;
    v63 = a1 + 1312;
  }
  Microsoft::Basix::TimerWheel::InstancePerSession::~InstancePerSession((Microsoft::Basix::TimerWheel::InstancePerSession *)v96);
  if ( v64 != *(_QWORD *)(v63 + 24) + *(_QWORD *)(v63 + 32) )
  {
    if ( v65 )
      v70 = *v65;
    else
      v70 = 0;
    Microsoft::Basix::Dct::ICE::Agent::CandidatePair::CandidatePair(
      (Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v7,
      *(const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair **)(*(_QWORD *)(v70 + 8)
                                                                        + 8 * (v64 & (*(_QWORD *)(v70 + 16) - 1LL))));
    Mtx_unlock(v60);
    Microsoft::Basix::TimerWheel::InstancePerSession::~InstancePerSession((Microsoft::Basix::TimerWheel::InstancePerSession *)v126);
    v71 = (volatile signed __int32 *)*((_QWORD *)&v123[1] + 1);
    if ( *((_QWORD *)&v123[1] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123[1] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v71)(v71);
        if ( _InterlockedExchangeAdd(v71 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v71 + 8LL))(v71);
      }
    }
    v72 = (volatile signed __int32 *)*((_QWORD *)&v123[0] + 1);
    if ( *((_QWORD *)&v123[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
        if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
      }
    }
    goto LABEL_118;
  }
  Microsoft::Basix::Dct::ICE::Agent::CandidatePair::CandidatePair(
    (Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v96,
    (const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v126);
  v73 = *(const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair **)(a1 + 1472);
  v74 = *(const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair **)(a1 + 1480);
  while ( v73 != v74
       && (!(unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                               v96,
                               v73)
        || !(unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                               v97,
                               (char *)v73 + 16)) )
    v73 = (const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)((char *)v73 + 64);
  Microsoft::Basix::TimerWheel::InstancePerSession::~InstancePerSession((Microsoft::Basix::TimerWheel::InstancePerSession *)v96);
  if ( v73 != *(const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair **)(a1 + 1480) )
  {
    Microsoft::Basix::Dct::ICE::Agent::CandidatePair::CandidatePair(
      (Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v7,
      v73);
    Mtx_unlock(v60);
    Microsoft::Basix::TimerWheel::InstancePerSession::~InstancePerSession((Microsoft::Basix::TimerWheel::InstancePerSession *)v126);
    v75 = (volatile signed __int32 *)*((_QWORD *)&v123[1] + 1);
    if ( *((_QWORD *)&v123[1] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123[1] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
        if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
      }
    }
    v76 = (volatile signed __int32 *)*((_QWORD *)&v123[0] + 1);
    if ( *((_QWORD *)&v123[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
        if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
      }
    }
    goto LABEL_118;
  }
LABEL_119:
  Microsoft::Basix::Dct::ICE::Agent::CandidatePair::CandidatePair(
    (Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v96,
    (const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v126);
  v78 = Microsoft::Basix::Containers::modifiable_priority_queue_Microsoft::Basix::Dct::ICE::Agent::CandidatePair_std::vector_Microsoft::Basix::Dct::ICE::Agent::CandidatePair_std::allocator_Microsoft::Basix::Dct::ICE::Agent::CandidatePair____std::less_Microsoft::Basix::Dct::ICE::Agent::CandidatePair___::remove_if__lambda_5fa8e87d5336e61e6ec8a332ca4f74df___(
          a1 + 1352,
          v96);
  v79 = *(_QWORD ***)(a1 + 1256);
  for ( i = *v79; i != v79; i = (_QWORD *)*i )
  {
    Microsoft::Basix::Dct::ICE::Agent::CandidatePair::CandidatePair(
      (Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v96,
      (const struct Microsoft::Basix::Dct::ICE::Agent::CandidatePair *)v126);
    v78 |= Microsoft::Basix::Containers::modifiable_priority_queue_Microsoft::Basix::Dct::ICE::Agent::CandidatePair_std::vector_Microsoft::Basix::Dct::ICE::Agent::CandidatePair_std::allocator_Microsoft::Basix::Dct::ICE::Agent::CandidatePair____std::less_Microsoft::Basix::Dct::ICE::Agent::CandidatePair___::remove_if__lambda_5fa8e87d5336e61e6ec8a332ca4f74df___(
             i + 4,
             v96);
  }
  std::deque<Microsoft::Basix::Dct::ICE::Agent::CandidatePair>::_Emplace_back_internal<Microsoft::Basix::Dct::ICE::Agent::CandidatePair const &>(
    a1 + 1312,
    v123);
  if ( v78 )
  {
    if ( v90 )
    {
      std::string::string(v96, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\ice\\agent.cpp");
      std::string::string(v98, "new peer reflexive Pair must not be present in m_waiting nor m_foundations");
      Microsoft::Basix::Exception::Exception(pExceptionObject, v98, v96, 683);
      throw (Microsoft::Basix::Exception *)pExceptionObject;
    }
  }
  else
  {
    if ( !v90 )
    {
      std::string::string(v96, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\ice\\agent.cpp");
      std::string::string(v98, "new peer reflexive pair must be created first");
      Microsoft::Basix::Exception::Exception(pExceptionObject, v98, v96, 674);
      throw (Microsoft::Basix::Exception *)pExceptionObject;
    }
    if ( *(_BYTE *)(a1 + 6144) )
    {
      v82 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v98, *(_QWORD *)&v123[1], 0, 6);
      v83 = v9 | 2;
      LODWORD(v93[0]) = 2;
      v84 = (void *)v82;
      if ( *(_QWORD *)(v82 + 24) > 0xFu )
        v84 = *(void **)v82;
      v93[1] = v84;
      v94 = *(_QWORD *)(v82 + 16);
      v95 = 0;
      v85 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v96, *(_QWORD *)&v123[0], 0, 6);
      v86 = v83 | 0xC;
      LODWORD(v121[0]) = 2;
      v87 = (void *)v85;
      if ( *(_QWORD *)(v85 + 24) > 0xFu )
        v87 = *(void **)v85;
      v121[1] = v87;
      *(_QWORD *)&v122 = *(_QWORD *)(v85 + 16);
      BYTE8(v122) = 0;
      v9 = v86 | 0x10;
      Microsoft::Basix::Instrumentation::ICECandidatePairAdded::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        a1 + 6272,
        a1 + 6152,
        (unsigned int)v121,
        (unsigned int)v93,
        (__int64)&v123[2] + 8);
    }
    if ( (v9 & 0x10) != 0 )
    {
      v9 &= ~0x10u;
      if ( BYTE8(v122) )
        operator delete(v121[1], v81);
    }
    if ( (v9 & 8) != 0 )
    {
      v9 &= ~8u;
      std::string::_Tidy_deallocate(v96);
    }
    if ( (v9 & 4) != 0 )
    {
      v9 &= ~4u;
      if ( v95 )
        operator delete(v93[1], v81);
    }
    if ( (v9 & 2) != 0 )
      std::string::_Tidy_deallocate(v98);
  }
  v121[0] = Microsoft::Basix::Dct::ICE::Agent::ScheduleCheck;
  v121[1] = (void *)4294967288LL;
  Microsoft::Basix::Dct::ICE::Agent::ScheduleTaskIfNotBeforeNoLock<bool (Microsoft::Basix::Dct::ICE::Agent::*)(void)>(
    a1,
    v121,
    *(_QWORD *)(a1 + 712));
  *(_OWORD *)v7 = v123[0];
  v123[0] = 0;
  *(_OWORD *)(v7 + 16) = v123[1];
  v123[1] = 0;
  *(_OWORD *)(v7 + 32) = v123[2];
  *(_DWORD *)(v7 + 48) = v123[3];
  *(_BYTE *)(v7 + 52) = BYTE4(v123[3]);
  *(_DWORD *)(v7 + 56) = DWORD2(v123[3]);
  Mtx_unlock(v60);
  Microsoft::Basix::TimerWheel::InstancePerSession::~InstancePerSession((Microsoft::Basix::TimerWheel::InstancePerSession *)v126);
  Microsoft::Basix::TimerWheel::InstancePerSession::~InstancePerSession((Microsoft::Basix::TimerWheel::InstancePerSession *)v123);
  v88 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
  (*(void (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, void **, _BYTE *))(*(_QWORD *)v88 + 32LL))(
    v88,
    v121,
    v125);
  return v7;
}

```

## disassembly

```asm
0x1801ec1d0  mov     [rsp-8+arg_8], rdx
0x1801ec1d5  push    rbp
0x1801ec1d6  push    rbx
0x1801ec1d7  push    rsi
0x1801ec1d8  push    rdi
0x1801ec1d9  push    r12
0x1801ec1db  push    r13
0x1801ec1dd  push    r14
0x1801ec1df  push    r15
0x1801ec1e1  lea     rbp, [rsp-3C8h]
0x1801ec1e9  mov     eax, 4C8h
0x1801ec1ee  call    _alloca_probe
0x1801ec1f3  sub     rsp, rax
0x1801ec1f6  mov     rax, cs:__security_cookie
0x1801ec1fd  xor     rax, rsp
0x1801ec200  mov     [rbp+400h+var_50], rax
0x1801ec207  mov     r12, r9
0x1801ec20a  mov     rdi, r8
0x1801ec20d  mov     r14, rdx
0x1801ec210  mov     [rsp+500h+var_4B0], rdx
0x1801ec215  mov     r15, rcx
0x1801ec218  mov     [rbp+400h+var_2C8], rdx
0x1801ec21f  mov     rbx, [rbp+400h+arg_20]
0x1801ec226  xor     esi, esi
0x1801ec228  mov     [rsp+500h+var_4BC], esi
0x1801ec22c  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x1801ec231  lea     r8, [r15+2B8h]
0x1801ec238  mov     r9b, 1
0x1801ec23b  lea     rdx, [rbp+400h+var_A0]
0x1801ec242  mov     rcx, rax
0x1801ec245  call    ?SetActivityId@ActivityManager@Instrumentation@Basix@Microsoft@@QEAA?AUGuid@34@AEBU534@_N@Z; Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(Microsoft::Basix::Guid const &,bool)
0x1801ec24a  nop
0x1801ec24b  xor     r13b, r13b
0x1801ec24e  mov     [rsp+500h+var_4C0], r13b
0x1801ec253  xor     edx, edx; Val
0x1801ec255  lea     r8d, [rsi+40h]; Size
0x1801ec259  lea     rcx, [rbp+400h+var_100]; void *
0x1801ec260  call    memset
0x1801ec265  mov     [rsp+500h+var_4E0], rbx
0x1801ec26a  mov     r9, r12
0x1801ec26d  mov     r8, rdi
0x1801ec270  lea     rdx, [rbp+400h+var_100]
0x1801ec277  mov     rcx, r15
0x1801ec27a  call    ?FindPairFromBindingRequest@Agent@ICE@Dct@Basix@Microsoft@@AEAA?AVCandidatePair@12345@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0AEBURelayName@12345@@Z; Microsoft::Basix::Dct::ICE::Agent::FindPairFromBindingRequest(std::string const &,std::string const &,Microsoft::Basix::Dct::ICE::Agent::RelayName const &)
0x1801ec27f  nop
0x1801ec280  or      edi, 0FFFFFFFFh
0x1801ec283  mov     rax, [rbp+400h+var_F0]
0x1801ec28a  test    rax, rax
0x1801ec28d  jnz     loc_1801ECC18
0x1801ec293  lea     rcx, [rbp+400h+var_120]
0x1801ec29a  call    ??$make_shared@VCandidate@ICE@Dct@Basix@Microsoft@@$$V@std@@YA?AV?$shared_ptr@VCandidate@ICE@Dct@Basix@Microsoft@@@0@XZ; std::make_shared<Microsoft::Basix::Dct::ICE::Candidate,>(void)
0x1801ec29f  mov     rcx, [rax]
0x1801ec2a2  mov     rdx, [rax+8]
0x1801ec2a6  mov     [rax], rsi
0x1801ec2a9  mov     [rax+8], rsi
0x1801ec2ad  mov     [rbp+400h+var_F0], rcx
0x1801ec2b4  mov     rbx, [rbp+400h+var_F0+8]
0x1801ec2bb  mov     [rbp+400h+var_F0+8], rdx
0x1801ec2c2  test    rbx, rbx
0x1801ec2c5  jz      short loc_1801EC2FC
0x1801ec2c7  mov     eax, edi
0x1801ec2c9  lock xadd [rbx+8], eax
0x1801ec2ce  add     eax, edi
0x1801ec2d0  jnz     short loc_1801EC2FC
0x1801ec2d2  mov     rax, [rbx]
0x1801ec2d5  mov     rcx, rbx
0x1801ec2d8  mov     rax, [rax]
0x1801ec2db  call    cs:__guard_dispatch_icall_fptr
0x1801ec2e1  mov     eax, edi
0x1801ec2e3  lock xadd [rbx+0Ch], eax
0x1801ec2e8  add     eax, edi
0x1801ec2ea  jnz     short loc_1801EC2FC
0x1801ec2ec  mov     rax, [rbx]
0x1801ec2ef  mov     rcx, rbx
0x1801ec2f2  mov     rax, [rax+8]
0x1801ec2f6  call    cs:__guard_dispatch_icall_fptr
0x1801ec2fc  mov     rbx, [rbp+400h+var_120+8]
0x1801ec303  test    rbx, rbx
0x1801ec306  jz      short loc_1801EC33D
0x1801ec308  mov     eax, edi
0x1801ec30a  lock xadd [rbx+8], eax
0x1801ec30f  add     eax, edi
0x1801ec311  jnz     short loc_1801EC33D
0x1801ec313  mov     rax, [rbx]
0x1801ec316  mov     rcx, rbx
0x1801ec319  mov     rax, [rax]
0x1801ec31c  call    cs:__guard_dispatch_icall_fptr
0x1801ec322  mov     eax, edi
0x1801ec324  lock xadd [rbx+0Ch], eax
0x1801ec329  add     eax, edi
0x1801ec32b  jnz     short loc_1801EC33D
0x1801ec32d  mov     rax, [rbx]
0x1801ec330  mov     rcx, rbx
0x1801ec333  mov     rax, [rax+8]
0x1801ec337  call    cs:__guard_dispatch_icall_fptr
0x1801ec33d  mov     rax, [rbp+400h+var_F0]
0x1801ec344  mov     dword ptr [rax+0E4h], 2
0x1801ec34e  mov     rax, r12
0x1801ec351  cmp     qword ptr [r12+18h], 0Fh
0x1801ec357  jbe     short loc_1801EC35D
0x1801ec359  mov     rax, [r12]
0x1801ec35d  cmp     byte ptr [rax], 5Bh ; '['
0x1801ec360  setz    cl
0x1801ec363  mov     rax, [rbp+400h+var_F0]
0x1801ec36a  mov     [rax+0E0h], cl
0x1801ec370  mov     rcx, [rbp+400h+var_F0]
0x1801ec377  add     rcx, 40h ; '@'
0x1801ec37b  mov     rdx, r12
0x1801ec37e  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1801ec383  mov     rcx, [rbp+400h+var_F0]
0x1801ec38a  add     rcx, 0A0h
0x1801ec391  mov     rdx, r12
0x1801ec394  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1801ec399  mov     rbx, [rbp+400h+var_F0]
0x1801ec3a0  xorps   xmm0, xmm0
0x1801ec3a3  movups  xmmword ptr [rbp+400h+var_120], xmm0
0x1801ec3aa  xorps   xmm1, xmm1
0x1801ec3ad  movdqu  [rbp+400h+var_110], xmm1
0x1801ec3b5  xor     r8d, r8d
0x1801ec3b8  lea     rdx, Str1
0x1801ec3bf  lea     rcx, [rbp+400h+var_120]
0x1801ec3c6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801ec3cb  nop
0x1801ec3cc  lea     rcx, [rbx+60h]
0x1801ec3d0  lea     rdx, [rbp+400h+var_120]
0x1801ec3d7  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1801ec3dc  nop
0x1801ec3dd  lea     rcx, [rbp+400h+var_120]
0x1801ec3e4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801ec3e9  mov     rbx, [rbp+400h+var_F0]
0x1801ec3f0  xorps   xmm0, xmm0
0x1801ec3f3  movups  xmmword ptr [rbp+400h+var_120], xmm0
0x1801ec3fa  xorps   xmm1, xmm1
0x1801ec3fd  movdqu  [rbp+400h+var_110], xmm1
0x1801ec405  xor     r8d, r8d
0x1801ec408  lea     rdx, Str1
0x1801ec40f  lea     rcx, [rbp+400h+var_120]
0x1801ec416  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801ec41b  nop
0x1801ec41c  lea     rcx, [rbx+80h]
0x1801ec423  lea     rdx, [rbp+400h+var_120]
0x1801ec42a  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1801ec42f  nop
0x1801ec430  lea     rcx, [rbp+400h+var_120]
0x1801ec437  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801ec43c  mov     rax, [rbp+400h+var_F0]
0x1801ec443  mov     dword ptr [rax+0E8h], 0
0x1801ec44d  mov     rdx, qword ptr [rbp+400h+var_100]
0x1801ec454  add     rdx, 0F8h
0x1801ec45b  mov     rcx, [rbp+400h+var_F0]
0x1801ec462  add     rcx, 0F8h
0x1801ec469  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1801ec46e  mov     edx, 0FFFFh; unsigned __int16
0x1801ec473  mov     rcx, [rbp+400h+var_F0]; this
0x1801ec47a  call    ?ComputeFoundationAndPriority@Candidate@ICE@Dct@Basix@Microsoft@@QEAAXG@Z; Microsoft::Basix::Dct::ICE::Candidate::ComputeFoundationAndPriority(ushort)
0x1801ec47f  lea     rbx, [r15+0F0h]
0x1801ec486  mov     [rsp+500h+var_4B8], rbx
0x1801ec48b  mov     rcx, rbx; _Mtx_t
0x1801ec48e  call    _Mtx_lock
0x1801ec493  test    eax, eax
0x1801ec495  jnz     loc_1801ED4EA
0x1801ec49b  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1801ec4a2  jz      loc_1801ED4F5
0x1801ec4a8  lea     rcx, [r15+488h]
0x1801ec4af  mov     rdx, [rcx+8]
0x1801ec4b3  cmp     rdx, [rcx+10h]
0x1801ec4b7  jz      short loc_1801EC4F4
0x1801ec4b9  mov     qword ptr [rdx], 0
0x1801ec4c0  mov     qword ptr [rdx+8], 0
0x1801ec4c8  mov     rax, [rbp+400h+var_F0+8]
0x1801ec4cf  test    rax, rax
0x1801ec4d2  jz      short loc_1801EC4D8
0x1801ec4d4  lock inc dword ptr [rax+8]
0x1801ec4d8  mov     rax, [rbp+400h+var_F0]
0x1801ec4df  mov     [rdx], rax
0x1801ec4e2  mov     rax, [rbp+400h+var_F0+8]
0x1801ec4e9  mov     [rdx+8], rax
0x1801ec4ed  add     qword ptr [rcx+8], 10h
0x1801ec4f2  jmp     short loc_1801EC501
0x1801ec4f4  lea     r8, [rbp+400h+var_F0]
0x1801ec4fb  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@std@@@?$vector@V?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &>(std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> * const,std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &)
0x1801ec500  nop
0x1801ec501  mov     rcx, rbx; _Mtx_t
0x1801ec504  call    _Mtx_unlock
0x1801ec509  mov     r13b, 1
0x1801ec50c  mov     [rsp+500h+var_4C0], r13b
0x1801ec511  xorps   xmm1, xmm1
0x1801ec514  movdqu  xmmword ptr [rsp+500h+var_4A8], xmm1
0x1801ec51a  mov     rdx, [r15+388h]
0x1801ec521  test    rdx, rdx
0x1801ec524  jz      short loc_1801EC53D
0x1801ec526  mov     eax, [rdx+8]
0x1801ec529  jmp     short loc_1801EC539
0x1801ec52b  lea     ecx, [rax+1]
0x1801ec52e  lock cmpxchg [rdx+8], ecx
0x1801ec533  jz      loc_1801ECC49
0x1801ec539  test    eax, eax
0x1801ec53b  jnz     short loc_1801EC52B
0x1801ec53d  mov     rcx, [rsp+500h+var_4A8]
0x1801ec542  mov     rbx, [rsp+500h+var_4A8+8]
0x1801ec547  test    rcx, rcx
0x1801ec54a  jz      short loc_1801EC56A
0x1801ec54c  mov     rdx, qword ptr [rbp+400h+var_100]
0x1801ec553  add     rdx, 20h ; ' '
0x1801ec557  mov     rax, [rcx]
0x1801ec55a  xor     r8d, r8d
0x1801ec55d  mov     rax, [rax+0A0h]
0x1801ec564  call    cs:__guard_dispatch_icall_fptr
0x1801ec56a  xorps   xmm0, xmm0
0x1801ec56d  movups  [rbp+400h+var_C0], xmm0
0x1801ec574  lea     rcx, [rbp+400h+var_C0]
0x1801ec57b  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1801ec580  nop
0x1801ec581  mov     rax, qword ptr [rbp+400h+var_C0]
0x1801ec588  test    rax, rax
0x1801ec58b  jz      loc_1801EC65C
0x1801ec591  cmp     byte ptr [rax+80h], 0
0x1801ec598  jz      loc_1801EC65C
0x1801ec59e  mov     edi, 6
0x1801ec5a3  mov     r9d, edi
0x1801ec5a6  xor     r8d, r8d
0x1801ec5a9  mov     rdx, [rbp+400h+var_F0]
0x1801ec5b0  lea     rcx, [rbp+400h+var_428]
0x1801ec5b4  call    ??$ToString@VCandidate@ICE@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVCandidate@ICE@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(Microsoft::Basix::Dct::ICE::Candidate const &,int,int)
0x1801ec5b9  mov     r12, rax
0x1801ec5bc  cmp     qword ptr [rax+18h], 0Fh
0x1801ec5c1  jbe     short loc_1801EC5C6
0x1801ec5c3  mov     r12, [rax]
0x1801ec5c6  mov     r9d, edi
0x1801ec5c9  xor     r8d, r8d
0x1801ec5cc  mov     rdx, qword ptr [rbp+400h+var_100]
0x1801ec5d3  lea     rcx, [rbp+400h+var_408]
0x1801ec5d7  call    ??$ToString@VCandidate@ICE@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVCandidate@ICE@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(Microsoft::Basix::Dct::ICE::Candidate const &,int,int)
0x1801ec5dc  mov     rdi, rax
0x1801ec5df  cmp     qword ptr [rax+18h], 0Fh
0x1801ec5e4  jbe     short loc_1801EC5E9
0x1801ec5e6  mov     rdi, [rax]
0x1801ec5e9  xorps   xmm0, xmm0
0x1801ec5ec  movups  xmmword ptr [rbp+400h+var_120], xmm0
0x1801ec5f3  xorps   xmm1, xmm1
0x1801ec5f6  movdqu  [rbp+400h+var_110], xmm1
0x1801ec5fe  mov     r8d, 3Eh ; '>'
0x1801ec604  lea     rdx, aNewPeerReflexi_1; "new peer reflexive candidate pair creat"...
0x1801ec60b  lea     rcx, [rbp+400h+var_120]
0x1801ec612  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801ec617  nop
0x1801ec618  mov     [rsp+500h+var_4E0], r12
0x1801ec61d  mov     r9, rdi
0x1801ec620  lea     r8, [rbp+400h+var_120]
0x1801ec627  lea     rdx, aBasixDct; "BASIX_DCT"
0x1801ec62e  lea     rcx, [rbp+400h+var_C0]
0x1801ec635  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEBDPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@11@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,char const *,char const *)
0x1801ec63a  nop
0x1801ec63b  lea     rcx, [rbp+400h+var_120]
0x1801ec642  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801ec647  nop
0x1801ec648  lea     rcx, [rbp+400h+var_408]
0x1801ec64c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801ec651  nop
0x1801ec652  lea     rcx, [rbp+400h+var_428]
0x1801ec656  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801ec65b  nop
0x1801ec65c  mov     rdi, qword ptr [rbp+400h+var_C0+8]
0x1801ec663  or      r12d, 0FFFFFFFFh
0x1801ec667  test    rdi, rdi
0x1801ec66a  jz      short loc_1801EC6A5
0x1801ec66c  mov     eax, r12d
0x1801ec66f  lock xadd [rdi+8], eax
0x1801ec674  add     eax, r12d
0x1801ec677  jnz     short loc_1801EC6A5
0x1801ec679  mov     rax, [rdi]
0x1801ec67c  mov     rcx, rdi
0x1801ec67f  mov     rax, [rax]
0x1801ec682  call    cs:__guard_dispatch_icall_fptr
0x1801ec688  mov     eax, r12d
0x1801ec68b  lock xadd [rdi+0Ch], eax
0x1801ec690  add     eax, r12d
0x1801ec693  jnz     short loc_1801EC6A5
0x1801ec695  mov     rax, [rdi]
0x1801ec698  mov     rcx, rdi
0x1801ec69b  mov     rax, [rax+8]
0x1801ec69f  call    cs:__guard_dispatch_icall_fptr
0x1801ec6a5  xorps   xmm0, xmm0
0x1801ec6a8  movups  xmmword ptr [rbp+400h+var_120], xmm0
0x1801ec6af  lea     rcx, [rbp+400h+var_120]
0x1801ec6b6  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x1801ec6bb  nop
0x1801ec6bc  mov     rax, [rbp+400h+var_120]
0x1801ec6c3  test    rax, rax
0x1801ec6c6  jz      loc_1801ECB8E
0x1801ec6cc  cmp     byte ptr [rax+80h], 0
0x1801ec6d3  jz      loc_1801ECB8E
0x1801ec6d9  lea     rax, [rbp+400h+var_240]
0x1801ec6e0  mov     [rsp+500h+var_4B8], rax
0x1801ec6e5  xorps   xmm0, xmm0
0x1801ec6e8  movups  [rbp+400h+var_2E8], xmm0
0x1801ec6ef  xorps   xmm1, xmm1
0x1801ec6f2  movdqu  [rbp+400h+var_2D8], xmm1
0x1801ec6fa  mov     esi, 1
0x1801ec6ff  mov     r8d, esi
  ... truncated ...
```

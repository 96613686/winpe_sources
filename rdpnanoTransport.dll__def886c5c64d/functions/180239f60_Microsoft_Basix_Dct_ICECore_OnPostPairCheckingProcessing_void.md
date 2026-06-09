# Microsoft::Basix::Dct::ICECore::OnPostPairCheckingProcessing(void)

- ea: `0x180239f60`
- end: `0x18023ac80`
- name: `?OnPostPairCheckingProcessing@ICECore@Dct@Basix@Microsoft@@UEAAXXZ`
- size: `3360`
- prototype: `void __fastcall(Microsoft::Basix::Dct::ICECore *__hidden this)`
- caller_count: `0`
- callee_count: `33`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x1800191b4`
- `0x18001979c`
- `0x18001ab4c`
- `0x18001ae64`
- `0x18001db78`
- `0x18001dc00`
- `0x180024760`
- `0x180024c14`
- `0x180028820`
- `0x1800386d0`
- `0x1800c3524`
- `0x1800d210c`
- `0x1801066f8`
- `0x18018eb38`
- `0x18019e6e0`
- `0x1801ed524`
- `0x18020d3d0`
- `0x18021d380`
- `0x18021d868`
- `0x18021f8b0`
- `0x18023288c`
- `0x180239f60`
- `0x1802e9b68`
- `0x180311e54`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x180375c40`

## string_xrefs

- `0x18023a214`: `LinkAddedPhase`
- `0x18023a2aa`: `LinkAdded`
- `0x18023a2b6`: `LinkManagement`
- `0x18023a938`: `LinkManagement`
- `0x18023a044`: `No ICE Link Established`
- `0x18023a530`: `Checking any possible relay-relay link missed due to race condition between clonings for client and server`
- `0x18023a6a0`: `expectedNumLinks`
- `0x18023a7a3`: `actualNumLinks`
- `0x18023a92c`: `CheckForCloningCompletion`
- `0x18023aafd`: `Expected vs actual number of links in linkContextMap: expected=%d, actual=%d`
- `0x18023ab6f`: `All links after current cloning have been added into the linkContextMap as expected: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=65
void __fastcall Microsoft::Basix::Dct::ICECore::OnPostPairCheckingProcessing(Microsoft::Basix::Dct::ICECore *this)
{
  __int64 v2; // rdx
  signed __int32 v3; // eax
  signed __int32 v4; // ett
  unsigned __int128 v5; // kr00_16
  Microsoft::Basix::Dct::ICECore *v6; // r14
  __int64 v7; // rax
  const struct std::exception_ptr *v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  char v11; // al
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  volatile signed __int32 *v18; // rsi
  __int64 *v19; // rax
  __int128 *v20; // rax
  __int64 v21; // rdx
  signed __int32 v22; // eax
  signed __int32 v23; // ett
  __int64 v24; // rcx
  volatile signed __int32 *v25; // rbx
  volatile signed __int32 *v26; // rsi
  unsigned int v27; // r15d
  unsigned int v28; // r12d
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  volatile signed __int32 *v41; // rsi
  int v42; // r9d
  volatile signed __int32 *v43; // rbx
  char v44; // [rsp+50h] [rbp-B0h]
  __int64 *v45; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v46[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v47; // [rsp+70h] [rbp-90h]
  unsigned __int128 v48; // [rsp+80h] [rbp-80h]
  __int128 v49; // [rsp+90h] [rbp-70h] BYREF
  __int128 v50; // [rsp+A0h] [rbp-60h]
  __int128 v51; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v52; // [rsp+C0h] [rbp-40h]
  __int128 v53; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v54; // [rsp+E0h] [rbp-20h]
  _OWORD v55[2]; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v56[2]; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v57[2]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v58; // [rsp+150h] [rbp+50h] BYREF
  __int128 v59; // [rsp+160h] [rbp+60h]
  char v60; // [rsp+170h] [rbp+70h]
  __int128 *v61; // [rsp+178h] [rbp+78h]
  _OWORD v62[2]; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v63[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v64[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v65[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v66[4]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v67[4]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v68[4]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v69[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v70[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v71[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v72[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v73[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v74[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v75[32]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v76[32]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v77[128]; // [rsp+360h] [rbp+260h] BYREF
  int v78[4]; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int128 v79; // [rsp+3F0h] [rbp+2F0h]
  int v80[4]; // [rsp+400h] [rbp+300h] BYREF
  __int128 v81; // [rsp+410h] [rbp+310h]
  __int128 v82; // [rsp+420h] [rbp+320h] BYREF
  __int128 v83; // [rsp+430h] [rbp+330h]
  __int128 v84; // [rsp+440h] [rbp+340h] BYREF

  v48 = 0;
  v2 = *((_QWORD *)this + 18);
  if ( v2 )
  {
    v3 = *(_DWORD *)(v2 + 8);
    while ( v3 )
    {
      v4 = v3;
      v3 = _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 8), v3 + 1, v3);
      if ( v4 == v3 )
      {
        v9 = *((_QWORD *)this + 17);
        *(_QWORD *)&v48 = *((_QWORD *)this + 17);
        v10 = *((_QWORD *)this + 18);
        *((_QWORD *)&v48 + 1) = v10;
        v5 = __PAIR128__(v10, v9);
        goto LABEL_6;
      }
    }
  }
  v5 = v48;
LABEL_6:
  if ( (_QWORD)v5 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 80LL))(v5);
  v6 = (Microsoft::Basix::Dct::ICECore *)((char *)this - 16);
  Microsoft::Basix::Dct::ICECore::ClearBasesExceptLinkContext((Microsoft::Basix::Dct::ICECore *)((char *)this - 16));
  if ( *((_QWORD *)this + 67) )
  {
    if ( *((_DWORD *)v6 + 2270) )
    {
      LODWORD(v45) = 1;
      v11 = std::_Atomic_storage<enum Microsoft::Basix::Pattern::IThreadedObject::State,4>::compare_exchange_strong(
              (char *)this + 9040,
              &v45,
              2);
      *(_OWORD *)v78 = 0;
      if ( v11 )
      {
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v78);
        if ( *(_QWORD *)v78 && *(_BYTE *)(*(_QWORD *)v78 + 128LL) )
        {
          v49 = 0;
          v50 = 0;
          std::string::_Construct<1,char const *>(&v49, "\"", 1);
          v53 = 0;
          v54 = 0;
          std::string::_Construct<1,char const *>(&v53, "\"", 1);
          v51 = 0;
          v52 = 0;
          std::string::_Construct<1,char const *>(&v51, ":", 1);
          *(_OWORD *)v80 = 0;
          v81 = 0;
          std::string::_Construct<1,char const *>(v80, "\"", 1);
          v82 = 0;
          v83 = 0;
          std::string::_Construct<1,char const *>(&v82, "\"", 1);
          v12 = std::operator+<char>(v64, &v82, "LinkAddedPhase");
          LOBYTE(v13) = v44;
          std::string::string(v55, v13, v12, v80);
          LOBYTE(v14) = v44;
          std::string::string(v56, v14, v55, &v51);
          LOBYTE(v15) = v44;
          std::string::string(v57, v15, v56, &v53);
          v16 = std::operator+<char>(v65, v57, "All");
          LOBYTE(v17) = v44;
          std::string::string(v46, v17, v16, &v49);
          Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
            (int)v78,
            (int)"RD_CHECKPOINT",
            0,
            (int)"ICECore",
            "LinkManagement",
            "LinkAdded",
            (__int64)v46);
          std::string::_Tidy_deallocate(v65);
          std::string::_Tidy_deallocate(v57);
          std::string::_Tidy_deallocate(v56);
          std::string::_Tidy_deallocate(v55);
          std::string::_Tidy_deallocate(v64);
          std::string::_Tidy_deallocate(&v82);
          std::string::_Tidy_deallocate(v80);
          std::string::_Tidy_deallocate(&v51);
          std::string::_Tidy_deallocate(&v53);
          std::string::_Tidy_deallocate(&v49);
        }
        v18 = *(volatile signed __int32 **)&v78[2];
        if ( *(_QWORD *)&v78[2] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v78[2] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
            if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          }
        }
        v84 = 0;
        v19 = (__int64 *)operator new(0x20u);
        v45 = v19;
        if ( v19 )
          v19 = (__int64 *)__0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v19);
        *((_QWORD *)&v84 + 1) = v19;
        v58 = 0;
        v59 = 0;
        std::string::_Construct<1,char const *>(&v58, "control", 7);
        v60 = 46;
        v20 = &v58;
        if ( *((_QWORD *)&v59 + 1) > 0xFu )
          v20 = (__int128 *)v58;
        v61 = v20;
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned char>(
          &v84,
          &v58,
          &byte_18041D09A);
        std::string::_Tidy_deallocate(&v58);
        *(_OWORD *)v78 = 0;
        v21 = *((_QWORD *)this + 18);
        if ( v21 )
        {
          v22 = *(_DWORD *)(v21 + 8);
          while ( v22 )
          {
            v23 = v22;
            v22 = _InterlockedCompareExchange((volatile signed __int32 *)(v21 + 8), v22 + 1, v22);
            if ( v23 == v22 )
            {
              v24 = *((_QWORD *)this + 17);
              *(_QWORD *)v78 = v24;
              v25 = (volatile signed __int32 *)*((_QWORD *)this + 18);
              *(_QWORD *)&v78[2] = v25;
              goto LABEL_29;
            }
          }
        }
        v24 = *(_QWORD *)v78;
        v25 = *(volatile signed __int32 **)&v78[2];
LABEL_29:
        if ( v24 )
          (*(void (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v24 + 48LL))(v24, 2, &v84);
        Microsoft::Basix::Dct::ICECore::CheckForCloneStart(v6, 0);
        if ( v25 )
        {
          if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v84);
      }
      else
      {
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v78);
        if ( *(_QWORD *)v78 && *(_BYTE *)(*(_QWORD *)v78 + 128LL) )
        {
          v49 = 0;
          v50 = 0;
          std::string::_Construct<1,char const *>(
            &v49,
            "Checking any possible relay-relay link missed due to race condition between clonings for client and server",
            106);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
            v78,
            "BASIX_DCT",
            &v49);
          std::string::_Tidy_deallocate(&v49);
        }
        v26 = *(volatile signed __int32 **)&v78[2];
        if ( *(_QWORD *)&v78[2] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v78[2] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
            if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
          }
        }
        v82 = 0;
        *(_QWORD *)&v83 = 0;
        Microsoft::Basix::Dct::ICECore::CheckForMissingRelayLinks((char *)this - 16, &v82);
        v27 = *(_DWORD *)(*((_QWORD *)this + 15) + 724LL);
        v28 = *((_DWORD *)this + 134);
        *(_OWORD *)v80 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v80);
        if ( *(_QWORD *)v80 && *(_BYTE *)(*(_QWORD *)v80 + 128LL) )
        {
          v45 = v66;
          std::_Integral_to_string<char,unsigned int>(v65, v27);
          *(_OWORD *)v46 = 0;
          v47 = 0;
          std::string::_Construct<1,char const *>(v46, ":", 1);
          memset(v57, 0, sizeof(v57));
          std::string::_Construct<1,char const *>(v57, "\"", 1);
          memset(v56, 0, sizeof(v56));
          std::string::_Construct<1,char const *>(v56, "\"", 1);
          v29 = std::operator+<char>(&v58, v56, "expectedNumLinks");
          LOBYTE(v30) = v44;
          std::string::string(v64, v30, v29, v57);
          LOBYTE(v31) = v44;
          std::string::string(v74, v31, v64, v46);
          LOBYTE(v32) = v44;
          std::string::string(v66, v32, v74, v65);
          *(_QWORD *)&v84 = v67;
          std::_Integral_to_string<char,unsigned int>(v73, v28);
          memset(v55, 0, sizeof(v55));
          std::string::_Construct<1,char const *>(v55, ":", 1);
          memset(v63, 0, sizeof(v63));
          std::string::_Construct<1,char const *>(v63, "\"", 1);
          memset(v62, 0, sizeof(v62));
          std::string::_Construct<1,char const *>(v62, "\"", 1);
          v33 = std::operator+<char>(v76, v62, "actualNumLinks");
          LOBYTE(v34) = v44;
          std::string::string(v72, v34, v33, v63);
          LOBYTE(v35) = v44;
          std::string::string(v71, v35, v72, v55);
          LOBYTE(v36) = v44;
          std::string::string(v67, v36, v71, v73);
          std::_Integral_to_string<char,unsigned __int64>(v70, (__int64)(*((_QWORD *)&v82 + 1) - v82) >> 6);
          v51 = 0;
          v52 = 0;
          std::string::_Construct<1,char const *>(&v51, ":", 1);
          v53 = 0;
          v54 = 0;
          std::string::_Construct<1,char const *>(&v53, "\"", 1);
          v49 = 0;
          v50 = 0;
          std::string::_Construct<1,char const *>(&v49, "\"", 1);
          v37 = std::operator+<char>(v75, &v49, "MissingPairs");
          LOBYTE(v38) = v44;
          std::string::string(v69, v38, v37, &v53);
          LOBYTE(v39) = v44;
          std::string::string(v78, v39, v69, &v51);
          LOBYTE(v40) = v44;
          std::string::string(v68, v40, v78, v70);
          Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
            (int)v80,
            (int)"RD_CHECKPOINT",
            0,
            (int)"ICECore",
            "LinkManagement",
            "CheckForCloningCompletion",
            (__int64)v68,
            (__int64)v67,
            (__int64)v66);
          std::string::_Tidy_deallocate(v78);
          std::string::_Tidy_deallocate(v69);
          std::string::_Tidy_deallocate(v75);
          std::string::_Tidy_deallocate(&v49);
          std::string::_Tidy_deallocate(&v53);
          std::string::_Tidy_deallocate(&v51);
          std::string::_Tidy_deallocate(v70);
          std::string::_Tidy_deallocate(v71);
          std::string::_Tidy_deallocate(v72);
          std::string::_Tidy_deallocate(v76);
          std::string::_Tidy_deallocate(v62);
          std::string::_Tidy_deallocate(v63);
          std::string::_Tidy_deallocate(v55);
          std::string::_Tidy_deallocate(v73);
          std::string::_Tidy_deallocate(v74);
          std::string::_Tidy_deallocate(v64);
          std::string::_Tidy_deallocate(&v58);
          std::string::_Tidy_deallocate(v56);
          std::string::_Tidy_deallocate(v57);
          std::string::_Tidy_deallocate(v46);
          std::string::_Tidy_deallocate(v65);
        }
        v41 = *(volatile signed __int32 **)&v80[2];
        if ( *(_QWORD *)&v80[2] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v80[2] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
            if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
          }
        }
        if ( (_QWORD)v82 == *((_QWORD *)&v82 + 1) )
        {
          *(_OWORD *)v80 = 0;
          if ( v28 == v27 )
          {
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v80);
            if ( *(_QWORD *)v80 && *(_BYTE *)(*(_QWORD *)v80 + 128LL) )
            {
              *(_OWORD *)v46 = 0;
              v47 = 0;
              std::string::_Construct<1,char const *>(
                v46,
                "All links after current cloning have been added into the linkContextMap as expected: %d",
                87);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int>(
                v80,
                "BASIX_DCT",
                v46,
                v27);
              std::string::_Tidy_deallocate(v46);
            }
          }
          else
          {
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v80);
            if ( *(_QWORD *)v80 && *(_BYTE *)(*(_QWORD *)v80 + 128LL) )
            {
              *(_OWORD *)v46 = 0;
              v47 = 0;
              std::string::_Construct<1,char const *>(
                v46,
                "Expected vs actual number of links in linkContextMap: expected=%d, actual=%d",
                76,
                v42);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned int,unsigned int>(
                (unsigned int)v80,
                (unsigned int)"BASIX_DCT",
                (unsigned int)v46,
                v27,
                v28);
              std::string::_Tidy_deallocate(v46);
            }
          }
          v43 = *(volatile signed __int32 **)&v80[2];
          if ( *(_QWORD *)&v80[2] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v80[2] + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
              if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
            }
          }
          Microsoft::Basix::Dct::ICECore::OnCloneCompleted(v6);
        }
        else
        {
          Microsoft::Basix::Dct::ICE::Agent::CheckPairs(*((_QWORD *)this + 15), &v82);
        }
        std::vector<Microsoft::Basix::Dct::ICE::Agent::CandidatePair>::_Tidy(&v82);
      }
    }
  }
  else
  {
    *(_OWORD *)v78 = 0;
    v79 = 0;
    std::string::_Construct<1,char const *>(v78, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\icecore.cpp", 47);
    v82 = 0;
    v83 = 0;
    std::string::_Construct<1,char const *>(&v82, "No ICE Link Established", 23);
    v7 = Microsoft::Basix::Exception::Exception(v77, &v82, v78, 1790);
    v8 = (const struct std::exception_ptr *)std::make_exception_ptr<Microsoft::Basix::Exception>(v80, v7);
    Microsoft::Basix::Dct::ICECore::SetLastException((Microsoft::Basix::Dct::ICECore *)((char *)this - 16), v8);
    __ExceptionPtrDestroy(v80);
    std::string::_Tidy_deallocate(&v82);
    std::string::_Tidy_deallocate(v78);
    (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v6 + 32LL))((char *)this - 16, 0);
  }
  if ( *((_QWORD *)&v5 + 1) && !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v5 + 1) + 8LL)) )
  {
    (***((void (__fastcall ****)(_QWORD))&v5 + 1))(*((_QWORD *)&v5 + 1));
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v5 + 1) + 12LL)) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v5 + 1) + 8LL))(*((_QWORD *)&v5 + 1));
  }
}

```

## disassembly

```asm
0x180239f60  mov     [rsp-8+arg_8], rbx
0x180239f65  mov     [rsp-8+arg_10], rsi
0x180239f6a  push    rbp
0x180239f6b  push    rdi
0x180239f6c  push    r12
0x180239f6e  push    r14
0x180239f70  push    r15
0x180239f72  lea     rbp, [rsp-360h]
0x180239f7a  mov     eax, 460h
0x180239f7f  call    _alloca_probe
0x180239f84  sub     rsp, rax
0x180239f87  mov     rax, cs:__security_cookie
0x180239f8e  xor     rax, rsp
0x180239f91  mov     [rbp+380h+var_30], rax
0x180239f98  mov     rbx, rcx
0x180239f9b  xorps   xmm1, xmm1
0x180239f9e  movdqu  [rbp+380h+var_400], xmm1
0x180239fa3  mov     rdx, [rcx+90h]
0x180239faa  test    rdx, rdx
0x180239fad  jz      short loc_180239FC6
0x180239faf  mov     eax, [rdx+8]
0x180239fb2  jmp     short loc_180239FC2
0x180239fb4  lea     ecx, [rax+1]
0x180239fb7  lock cmpxchg [rdx+8], ecx
0x180239fbc  jz      loc_18023A0D1
0x180239fc2  test    eax, eax
0x180239fc4  jnz     short loc_180239FB4
0x180239fc6  mov     rcx, qword ptr [rbp+380h+var_400]
0x180239fca  mov     rdi, qword ptr [rbp+380h+var_400+8]
0x180239fce  test    rcx, rcx
0x180239fd1  jz      short loc_180239FE0
0x180239fd3  mov     rax, [rcx]
0x180239fd6  mov     rax, [rax+50h]
0x180239fda  call    cs:__guard_dispatch_icall_fptr
0x180239fe0  lea     r14, [rbx-10h]
0x180239fe4  mov     rcx, r14; this
0x180239fe7  call    ?ClearBasesExceptLinkContext@ICECore@Dct@Basix@Microsoft@@IEAAXXZ; Microsoft::Basix::Dct::ICECore::ClearBasesExceptLinkContext(void)
0x180239fec  or      r15d, 0FFFFFFFFh
0x180239ff0  cmp     qword ptr [rbx+218h], 0
0x180239ff8  jnz     loc_18023A0EC
0x180239ffe  xorps   xmm0, xmm0
0x18023a001  movups  xmmword ptr [rbp+380h+var_A0], xmm0
0x18023a008  xorps   xmm1, xmm1
0x18023a00b  movdqu  [rbp+380h+var_90], xmm1
0x18023a013  lea     r8d, [r15+30h]
0x18023a017  lea     rdx, aCW1SSrcLibbasi_59; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18023a01e  lea     rcx, [rbp+380h+var_A0]
0x18023a025  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023a02a  nop
0x18023a02b  xorps   xmm0, xmm0
0x18023a02e  movups  [rbp+380h+var_60], xmm0
0x18023a035  xorps   xmm1, xmm1
0x18023a038  movdqu  [rbp+380h+var_50], xmm1
0x18023a040  lea     r8d, [r15+18h]
0x18023a044  lea     rdx, aNoIceLinkEstab; "No ICE Link Established"
0x18023a04b  lea     rcx, [rbp+380h+var_60]
0x18023a052  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023a057  nop
0x18023a058  mov     r9d, 6FEh
0x18023a05e  lea     r8, [rbp+380h+var_A0]
0x18023a065  lea     rdx, [rbp+380h+var_60]
0x18023a06c  lea     rcx, [rbp+380h+var_120]
0x18023a073  call    ??0Exception@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0_K@Z; Microsoft::Basix::Exception::Exception(std::string const &,std::string const &,unsigned __int64)
0x18023a078  mov     rdx, rax
0x18023a07b  lea     rcx, [rbp+380h+var_80]
0x18023a082  call    ??$make_exception_ptr@VException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::Exception>(Microsoft::Basix::Exception)
0x18023a087  nop
0x18023a088  mov     rdx, rax; struct std::exception_ptr *
0x18023a08b  mov     rcx, r14; this
0x18023a08e  call    ?SetLastException@ICECore@Dct@Basix@Microsoft@@IEAAXAEBVexception_ptr@std@@@Z; Microsoft::Basix::Dct::ICECore::SetLastException(std::exception_ptr const &)
0x18023a093  nop
0x18023a094  lea     rcx, [rbp+380h+var_80]; void *
0x18023a09b  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18023a0a0  nop
0x18023a0a1  lea     rcx, [rbp+380h+var_60]
0x18023a0a8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a0ad  nop
0x18023a0ae  lea     rcx, [rbp+380h+var_A0]
0x18023a0b5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a0ba  mov     rax, [r14]
0x18023a0bd  xor     edx, edx
0x18023a0bf  mov     rcx, r14
0x18023a0c2  mov     rax, [rax+20h]
0x18023a0c6  call    cs:__guard_dispatch_icall_fptr
0x18023a0cc  jmp     loc_18023AC17
0x18023a0d1  mov     rcx, [rbx+88h]
0x18023a0d8  mov     qword ptr [rbp+380h+var_400], rcx
0x18023a0dc  mov     rdi, [rbx+90h]
0x18023a0e3  mov     qword ptr [rbp+380h+var_400+8], rdi
0x18023a0e7  jmp     loc_180239FCE
0x18023a0ec  cmp     dword ptr [r14+2378h], 0
0x18023a0f4  jz      loc_18023AC17
0x18023a0fa  mov     r12d, 1
0x18023a100  mov     dword ptr [rsp+480h+var_428], r12d
0x18023a105  lea     rcx, [rbx+2350h]
0x18023a10c  lea     r9d, [r12+4]
0x18023a111  lea     r8d, [r12+1]
0x18023a116  lea     rdx, [rsp+480h+var_428]
0x18023a11b  call    ?compare_exchange_strong@?$_Atomic_storage@W4State@IThreadedObject@Pattern@Basix@Microsoft@@$03@std@@QEAA_NAEAW4State@IThreadedObject@Pattern@Basix@Microsoft@@W434567@W4memory_order@2@@Z; std::_Atomic_storage<Microsoft::Basix::Pattern::IThreadedObject::State,4>::compare_exchange_strong(Microsoft::Basix::Pattern::IThreadedObject::State &,Microsoft::Basix::Pattern::IThreadedObject::State,std::memory_order)
0x18023a120  xorps   xmm0, xmm0
0x18023a123  lea     rcx, [rbp+380h+var_A0]
0x18023a12a  movups  xmmword ptr [rbp+380h+var_A0], xmm0
0x18023a131  test    al, al
0x18023a133  jz      loc_18023A500
0x18023a139  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x18023a13e  nop
0x18023a13f  mov     rax, qword ptr [rbp+380h+var_A0]
0x18023a146  test    rax, rax
0x18023a149  jz      loc_18023A350
0x18023a14f  cmp     byte ptr [rax+80h], 0
0x18023a156  jz      loc_18023A350
0x18023a15c  xorps   xmm0, xmm0
0x18023a15f  movups  [rbp+380h+var_3F0], xmm0
0x18023a163  xorps   xmm1, xmm1
0x18023a166  movdqu  [rbp+380h+var_3E0], xmm1
0x18023a16b  mov     r8d, r12d
0x18023a16e  lea     rsi, asc_1803D71C8; "\""
0x18023a175  mov     rdx, rsi
0x18023a178  lea     rcx, [rbp+380h+var_3F0]
0x18023a17c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023a181  nop
0x18023a182  xorps   xmm0, xmm0
0x18023a185  movups  [rbp+380h+var_3B0], xmm0
0x18023a189  xorps   xmm1, xmm1
0x18023a18c  movdqu  [rbp+380h+var_3A0], xmm1
0x18023a191  mov     r8d, r12d
0x18023a194  mov     rdx, rsi
0x18023a197  lea     rcx, [rbp+380h+var_3B0]
0x18023a19b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023a1a0  nop
0x18023a1a1  xorps   xmm0, xmm0
0x18023a1a4  movups  [rbp+380h+var_3D0], xmm0
0x18023a1a8  xorps   xmm1, xmm1
0x18023a1ab  movdqu  [rbp+380h+var_3C0], xmm1
0x18023a1b0  mov     r8d, r12d
0x18023a1b3  lea     rdx, asc_1803D71C4; ":"
0x18023a1ba  lea     rcx, [rbp+380h+var_3D0]
0x18023a1be  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023a1c3  nop
0x18023a1c4  xorps   xmm0, xmm0
0x18023a1c7  movups  xmmword ptr [rbp+380h+var_80], xmm0
0x18023a1ce  xorps   xmm1, xmm1
0x18023a1d1  movdqu  [rbp+380h+var_70], xmm1
0x18023a1d9  mov     r8d, r12d
0x18023a1dc  mov     rdx, rsi
0x18023a1df  lea     rcx, [rbp+380h+var_80]
0x18023a1e6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023a1eb  nop
0x18023a1ec  xorps   xmm0, xmm0
0x18023a1ef  movups  [rbp+380h+var_60], xmm0
0x18023a1f6  xorps   xmm1, xmm1
0x18023a1f9  movdqu  [rbp+380h+var_50], xmm1
0x18023a201  mov     r8d, r12d
0x18023a204  mov     rdx, rsi
0x18023a207  lea     rcx, [rbp+380h+var_60]
0x18023a20e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023a213  nop
0x18023a214  lea     r8, aLinkaddedphase; "LinkAddedPhase"
0x18023a21b  lea     rdx, [rbp+380h+var_60]
0x18023a222  lea     rcx, [rbp+380h+var_2C0]
0x18023a229  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18023a22e  nop
0x18023a22f  lea     r9, [rbp+380h+var_80]
0x18023a236  mov     r8, rax
0x18023a239  mov     dl, [rsp+480h+var_430]
0x18023a23d  lea     rcx, [rbp+380h+var_390]
0x18023a241  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18023a246  nop
0x18023a247  lea     r9, [rbp+380h+var_3D0]
0x18023a24b  lea     r8, [rbp+380h+var_390]
0x18023a24f  mov     dl, [rsp+480h+var_430]
0x18023a253  lea     rcx, [rbp+380h+var_370]
0x18023a257  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18023a25c  nop
0x18023a25d  lea     r9, [rbp+380h+var_3B0]
0x18023a261  lea     r8, [rbp+380h+var_370]
0x18023a265  mov     dl, [rsp+480h+var_430]
0x18023a269  lea     rcx, [rbp+380h+var_350]
0x18023a26d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18023a272  nop
0x18023a273  lea     r8, aAll; "All"
0x18023a27a  lea     rdx, [rbp+380h+var_350]
0x18023a27e  lea     rcx, [rbp+380h+var_2A0]
0x18023a285  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18023a28a  nop
0x18023a28b  lea     r9, [rbp+380h+var_3F0]
0x18023a28f  mov     r8, rax
0x18023a292  mov     dl, [rsp+480h+var_430]
0x18023a296  lea     rcx, [rsp+480h+var_420]
0x18023a29b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18023a2a0  lea     rax, [rsp+480h+var_420]
0x18023a2a5  mov     [rsp+480h+var_450], rax; __int64
0x18023a2aa  lea     rax, aLinkadded; "LinkAdded"
0x18023a2b1  mov     [rsp+480h+Str], rax; Str
0x18023a2b6  lea     rax, aLinkmanagement; "LinkManagement"
0x18023a2bd  mov     [rsp+480h+var_460], rax; char *
0x18023a2c2  lea     r9, aIcecore; "ICECore"
0x18023a2c9  xor     r8d, r8d; int
0x18023a2cc  lea     rdx, aRdCheckpoint; "RD_CHECKPOINT"
0x18023a2d3  lea     rcx, [rbp+380h+var_A0]; int
0x18023a2da  call    ??$TraceCheckpointMessage@VTraceCheckpoint@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDI111V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,char const *,uint,char const *,char const *,char const *,std::string)
0x18023a2df  nop
0x18023a2e0  lea     rcx, [rbp+380h+var_2A0]
0x18023a2e7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a2ec  nop
0x18023a2ed  lea     rcx, [rbp+380h+var_350]
0x18023a2f1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a2f6  nop
0x18023a2f7  lea     rcx, [rbp+380h+var_370]
0x18023a2fb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a300  nop
0x18023a301  lea     rcx, [rbp+380h+var_390]
0x18023a305  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a30a  nop
0x18023a30b  lea     rcx, [rbp+380h+var_2C0]
0x18023a312  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a317  nop
0x18023a318  lea     rcx, [rbp+380h+var_60]
0x18023a31f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a324  nop
0x18023a325  lea     rcx, [rbp+380h+var_80]
0x18023a32c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a331  nop
0x18023a332  lea     rcx, [rbp+380h+var_3D0]
0x18023a336  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a33b  nop
0x18023a33c  lea     rcx, [rbp+380h+var_3B0]
0x18023a340  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a345  nop
0x18023a346  lea     rcx, [rbp+380h+var_3F0]
0x18023a34a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a34f  nop
0x18023a350  mov     rsi, qword ptr [rbp+380h+var_A0+8]
0x18023a357  test    rsi, rsi
0x18023a35a  jz      short loc_18023A395
0x18023a35c  mov     eax, r15d
0x18023a35f  lock xadd [rsi+8], eax
0x18023a364  add     eax, r15d
0x18023a367  jnz     short loc_18023A395
0x18023a369  mov     rax, [rsi]
0x18023a36c  mov     rcx, rsi
0x18023a36f  mov     rax, [rax]
0x18023a372  call    cs:__guard_dispatch_icall_fptr
0x18023a378  mov     eax, r15d
0x18023a37b  lock xadd [rsi+0Ch], eax
0x18023a380  add     eax, r15d
0x18023a383  jnz     short loc_18023A395
0x18023a385  mov     rax, [rsi]
0x18023a388  mov     rcx, rsi
0x18023a38b  mov     rax, [rax+8]
0x18023a38f  call    cs:__guard_dispatch_icall_fptr
0x18023a395  xorps   xmm0, xmm0
0x18023a398  movups  [rbp+380h+var_40], xmm0
0x18023a39f  mov     qword ptr [rbp+380h+var_40], 0
0x18023a3aa  mov     ecx, 20h ; ' '; Size
0x18023a3af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18023a3b4  mov     [rsp+480h+var_428], rax
0x18023a3b9  test    rax, rax
0x18023a3bc  jz      short loc_18023A3C7
0x18023a3be  mov     rcx, rax
0x18023a3c1  call    ??0?$multi_index_container@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@U?$indexed_by@U?$sequenced@U?$tag@Una@mpl@boost@@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@@multi_index@boost@@@multi_index@boost@@U?$ordered_non_unique@U?$tag@Uby_name@subs@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@Una@mpl@5@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@@multi_index@boost@@U?$member@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@$0A@@23@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@23@Una@mpl@3@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@@multi_index@boost@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@multi_index@boost@@QEAA@XZ
0x18023a3c6  nop
0x18023a3c7  mov     qword ptr [rbp+380h+var_40+8], rax
0x18023a3ce  xorps   xmm0, xmm0
0x18023a3d1  movups  [rbp+380h+var_330], xmm0
0x18023a3d5  xorps   xmm1, xmm1
0x18023a3d8  movdqu  [rbp+380h+var_320], xmm1
0x18023a3dd  mov     r8d, 7
0x18023a3e3  lea     rdx, aControl; "control"
0x18023a3ea  lea     rcx, [rbp+380h+var_330]
0x18023a3ee  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023a3f3  mov     [rbp+380h+var_310], 2Eh ; '.'
0x18023a3f7  lea     rax, [rbp+380h+var_330]
0x18023a3fb  cmp     qword ptr [rbp+380h+var_320+8], 0Fh
0x18023a400  cmova   rax, qword ptr [rbp+380h+var_330]
0x18023a405  mov     [rbp+380h+var_308], rax
0x18023a409  lea     r8, byte_18041D09A
0x18023a410  lea     rdx, [rbp+380h+var_330]
0x18023a414  lea     rcx, [rbp+380h+var_40]
0x18023a41b  call    ??$put@E@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBE@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<uchar>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,uchar const &)
0x18023a420  nop
0x18023a421  lea     rcx, [rbp+380h+var_330]
0x18023a425  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023a42a  xorps   xmm1, xmm1
0x18023a42d  movdqu  xmmword ptr [rbp+380h+var_A0], xmm1
0x18023a435  mov     rdx, [rbx+90h]
0x18023a43c  test    rdx, rdx
0x18023a43f  jz      short loc_18023A458
0x18023a441  mov     eax, [rdx+8]
0x18023a444  jmp     short loc_18023A454
0x18023a446  lea     ecx, [rax+1]
0x18023a449  lock cmpxchg [rdx+8], ecx
0x18023a44e  jz      loc_18023A4DF
0x18023a454  test    eax, eax
0x18023a456  jnz     short loc_18023A446
0x18023a458  mov     rcx, qword ptr [rbp+380h+var_A0]
0x18023a45f  mov     rbx, qword ptr [rbp+380h+var_A0+8]
0x18023a466  test    rcx, rcx
0x18023a469  jz      short loc_18023A484
0x18023a46b  mov     rax, [rcx]
  ... truncated ...
```

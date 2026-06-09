# Microsoft::Basix::Dct::SmilesV3::ForceRemoveLinks(std::vector<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,uint,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::tuple<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,uint,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>> const &)

- ea: `0x18025ff00`
- end: `0x180261870`
- name: `?ForceRemoveLinks@SmilesV3@Dct@Basix@Microsoft@@UEAAXAEBV?$vector@V?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@IV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@V32@@std@@V?$allocator@V?$tuple@V?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@IV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@V32@@std@@@2@@std@@@Z`
- size: `6512`
- prototype: ``
- caller_count: `0`
- callee_count: `52`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017338`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x18001ab4c`
- `0x18001db78`
- `0x18001f8d4`
- `0x18001f970`
- `0x180021a00`
- `0x180024760`
- `0x180028100`
- `0x180028820`
- `0x18002a8ec`
- `0x18002a8f4`
- `0x1800334a8`
- `0x18004e1dc`
- `0x1800d34ac`
- `0x1800d621c`
- `0x1800ea630`
- `0x1801168d4`
- `0x1801171b8`
- `0x180118a9c`
- `0x1801ce1ac`
- `0x1801d43a4`
- `0x18024774c`
- `0x18024b320`
- `0x18024b594`
- `0x18024f938`
- `0x180251c80`
- `0x1802571d0`
- `0x18025ff00`
- `0x18026c8c8`
- `0x1802741d0`
- `0x18027c5e0`
- `0x18027c6c4`
- `0x18027d3e8`
- `0x18027e8d8`
- `0x180311d5c`
- `0x180311dbc`
- `0x180311e54`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x180313058`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f140`
- `0x180330b40`

## string_xrefs

- `0x180260a93`: `linkId`
- `0x18026173e`: `Smiles::ForceRemoveLink(): force remove all links, equivalent to shutting down smiles`
- `0x18026036c`: `Force Remove Link`
- `0x18026085c`: `errorCodeSymbolic`
- `0x180260b37`: `Force Link Remove Due to Exception`
- `0x180260b43`: `LinkRemoveDueToException`
- `0x180260dd6`: `SmilesV3: link(%d)%p force remove: isGracefullyClosedByPeer=%d`
- `0x180261004`: `SmilesV3: link(%d)%p force remove: isGracefullyClosedByPeer=%d`
- `0x180260f24`: `SmilesV3: link(%d)%p force remove already removed, ignore`
- `0x180261133`: `SmilesV3: link(%d)%p force remove already removed, ignore`

## pseudocode

```c
// Hidden C++ exception states: #wind=97
void __fastcall Microsoft::Basix::Dct::SmilesV3::ForceRemoveLinks(__int64 a1, __int64 **a2)
{
  int v3; // r15d
  __int64 *v4; // rdi
  __int64 v5; // rbx
  __m128i v6; // xmm6
  void *v7; // rsi
  void *v8; // r13
  volatile signed __int32 *v9; // rsi
  __int64 v10; // rsi
  void (__fastcall *v11)(__int64, void **, void **); // rdi
  char v12; // di
  __int64 v13; // rsi
  void (__fastcall *v14)(__int64, void **, void **); // rdi
  char v15; // si
  _OWORD *v16; // rax
  const struct std::nothrow_t *v17; // rdx
  const wchar_t *v18; // rcx
  __int64 *v19; // rdi
  const wchar_t *v20; // rcx
  const char *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  volatile signed __int32 *v42; // rdi
  __int64 v43; // rdx
  const void *v44; // r9
  int v45; // edi
  volatile signed __int32 *v46; // rdi
  const void *v47; // r9
  int v48; // edi
  volatile signed __int32 *v49; // rdi
  __int64 v50; // rdx
  const void *v51; // r9
  int v52; // edi
  volatile signed __int32 *v53; // rdi
  const void *v54; // r9
  int v55; // edi
  volatile signed __int32 *v56; // rdi
  __int64 v57; // rax
  volatile signed __int32 *v58; // r13
  volatile signed __int32 *v59; // r13
  __int64 v60; // rax
  void *v61; // r13
  volatile signed __int32 *v62; // rdi
  volatile signed __int32 *v63; // rsi
  volatile signed __int32 *v64; // rbx
  volatile signed __int32 *v65; // rsi
  volatile signed __int32 *v66; // r15
  __int64 v67; // rdx
  __int64 v68; // rax
  __int64 v69; // rdx
  volatile signed __int32 *v70; // rbx
  volatile signed __int32 *v71; // rbx
  int v72; // [rsp+20h] [rbp-E0h]
  char v73; // [rsp+60h] [rbp-A0h] BYREF
  char v74; // [rsp+61h] [rbp-9Fh] BYREF
  char v75; // [rsp+62h] [rbp-9Eh]
  __int64 *v76; // [rsp+68h] [rbp-98h]
  __int128 v77; // [rsp+70h] [rbp-90h] BYREF
  __int128 v78; // [rsp+80h] [rbp-80h]
  int v79; // [rsp+90h] [rbp-70h] BYREF
  volatile signed __int32 *v80; // [rsp+98h] [rbp-68h]
  __int64 *v81; // [rsp+A0h] [rbp-60h]
  __int64 *v82; // [rsp+A8h] [rbp-58h]
  __m128i v83; // [rsp+B0h] [rbp-50h] BYREF
  void *v84[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v85; // [rsp+D0h] [rbp-30h]
  _OWORD v86[2]; // [rsp+E0h] [rbp-20h] BYREF
  volatile signed __int32 *v87; // [rsp+100h] [rbp+0h]
  _OWORD *v88; // [rsp+108h] [rbp+8h]
  _OWORD *v89; // [rsp+118h] [rbp+18h]
  void *v90[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v91; // [rsp+130h] [rbp+30h]
  void *v92[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v93; // [rsp+150h] [rbp+50h]
  __int128 v94; // [rsp+160h] [rbp+60h] BYREF
  __int128 v95; // [rsp+170h] [rbp+70h] BYREF
  _Thrd_t pExceptionObject; // [rsp+180h] [rbp+80h] BYREF
  __int64 v97; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 *v98; // [rsp+1A8h] [rbp+A8h]
  __int64 *v99; // [rsp+1B0h] [rbp+B0h]
  __int128 v100; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v101; // [rsp+1C8h] [rbp+C8h] BYREF
  _OWORD v102[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  _OWORD v103[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  _OWORD v104[2]; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v105[2]; // [rsp+238h] [rbp+138h] BYREF
  _OWORD v106[2]; // [rsp+258h] [rbp+158h] BYREF
  _OWORD v107[2]; // [rsp+278h] [rbp+178h] BYREF
  _OWORD v108[2]; // [rsp+298h] [rbp+198h] BYREF
  _OWORD v109[2]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _OWORD v110[2]; // [rsp+2D8h] [rbp+1D8h] BYREF
  _OWORD v111[2]; // [rsp+2F8h] [rbp+1F8h] BYREF
  _OWORD v112[2]; // [rsp+318h] [rbp+218h] BYREF
  __int64 v113; // [rsp+338h] [rbp+238h]
  __int64 v114[4]; // [rsp+340h] [rbp+240h] BYREF
  __int64 v115[4]; // [rsp+360h] [rbp+260h] BYREF
  __int64 v116[4]; // [rsp+380h] [rbp+280h] BYREF
  __int64 v117[4]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v118[32]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v119[32]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v120[32]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v121[32]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v122[32]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v123[32]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v124[32]; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v125[32]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v126[32]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v127[32]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v128[32]; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v129[32]; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v130[32]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v131[32]; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v132[32]; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v133[32]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v134[32]; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v135[56]; // [rsp+5E0h] [rbp+4E0h] BYREF
  _BYTE *v136; // [rsp+618h] [rbp+518h]
  unsigned int v137[4]; // [rsp+620h] [rbp+520h] BYREF
  void *v138[2]; // [rsp+630h] [rbp+530h] BYREF
  size_t v139; // [rsp+640h] [rbp+540h]
  char v140; // [rsp+648h] [rbp+548h]
  _Thrd_t v141; // [rsp+650h] [rbp+550h] BYREF
  void *v142[2]; // [rsp+660h] [rbp+560h] BYREF
  __int128 v143; // [rsp+670h] [rbp+570h]
  void *v144[2]; // [rsp+680h] [rbp+580h] BYREF
  size_t v145; // [rsp+690h] [rbp+590h]
  char v146; // [rsp+698h] [rbp+598h]
  __int128 v147; // [rsp+6A0h] [rbp+5A0h] BYREF
  __int128 v148; // [rsp+6B0h] [rbp+5B0h]
  __int128 v149; // [rsp+6C0h] [rbp+5C0h] BYREF
  __int128 v150; // [rsp+6D0h] [rbp+5D0h]

  v3 = 0;
  v79 = 0;
  v4 = *a2;
  v76 = v4;
  v98 = a2[1];
  if ( v4 == v98 )
  {
    *(_OWORD *)v138 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v138);
    if ( v138[0] && *((_BYTE *)v138[0] + 128) )
    {
      v77 = 0;
      v78 = 0;
      std::string::_Construct<1,char const *>(
        &v77,
        "Smiles::ForceRemoveLink(): force remove all links, equivalent to shutting down smiles",
        85);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        v138,
        "BASIX_DCT",
        &v77);
      std::string::_Tidy_deallocate(&v77);
    }
    v71 = (volatile signed __int32 *)v138[1];
    if ( v138[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v138[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v71)(v71);
        if ( _InterlockedExchangeAdd(v71 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v71 + 8LL))(v71);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 - 1104) + 152LL))(a1 - 1104);
  }
  else
  {
    v94 = 0;
    v100 = 0;
    v101 = 0;
    v5 = a1 + 728;
    v113 = a1 + 728;
    do
    {
      v137[0] = *((_DWORD *)v4 + 16);
      v81 = v4 + 4;
      v6 = 0;
      v83 = 0;
      v149 = 0;
      v150 = 0;
      LOBYTE(a2) = 1;
      Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(&v149, a2, 0, &v100);
      v147 = 0;
      v148 = 0;
      Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(&v147, 0, 0, &v101);
      v75 = 0;
      v141 = 0;
      __ExceptionPtrCreate(&v141);
      if ( Mtx_lock((_Mtx_t)v5) )
        std::_Throw_Cpp_error(5);
      if ( *(_DWORD *)(v5 + 76) == 0x7FFFFFFF )
      {
        *(_DWORD *)(v5 + 76) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      *(_OWORD *)v144 = 0;
      Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
        v144,
        a1 + 424);
      *(_OWORD *)v138 = 0;
      v3 |= 0x300u;
      while ( 1 )
      {
        v7 = v144[0];
        if ( !v144[0] )
          break;
        v8 = v144[1];
        if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                                *(_QWORD *)v144[1] + 104LL,
                                v4 + 9) )
        {
          std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(&v83, v8);
          v6 = _mm_load_si128(&v83);
          break;
        }
        Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(v144);
      }
      if ( v7
        && _InterlockedExchangeAdd(
             (volatile signed __int32 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((__int64)v7 + 80),
             0xFFFFFFFF) == -1 )
      {
        std::runtime_error::runtime_error((std::runtime_error *)&pExceptionObject, "Unbalanced endIteration()");
        throw (std::runtime_error *)&pExceptionObject;
      }
      v9 = (volatile signed __int32 *)_mm_srli_si128(v6, 8).m128i_u64[0];
      v80 = v9;
      if ( v6.m128i_i64[0] )
      {
        *(_DWORD *)(v6.m128i_i64[0] + 288) = *(_DWORD *)(v6.m128i_i64[0] + 280);
        *(_DWORD *)(v6.m128i_i64[0] + 292) = *(_DWORD *)(v6.m128i_i64[0] + 284);
        v10 = *(_QWORD *)(v6.m128i_i64[0] + 104);
        v11 = *(void (__fastcall **)(__int64, void **, void **))(*(_QWORD *)(v10 + 40) + 8LL);
        *(_OWORD *)v84 = 0;
        v85 = 0;
        std::string::_Construct<1,char const *>(v84, "Microsoft::Basix::Dct.LastException", 35);
        v11(v10 + 40, v142, v84);
        std::string::_Tidy_deallocate(v84);
        if ( LOBYTE(v142[0]) )
        {
          *(_OWORD *)v138 = 0;
          __ExceptionPtrCreate(v138);
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
            *((_QWORD *)&v143 + 1),
            &v95,
            v138);
          v3 |= 0xC0u;
          __ExceptionPtrAssign(&v141, &v95);
          v12 = std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v141);
          __ExceptionPtrDestroy(&v95);
          __ExceptionPtrDestroy(v138);
          if ( v12 )
            (*(void (__fastcall **)(__int64, _Thrd_t *))(*(_QWORD *)(a1 - 1104) + 120LL))(a1 - 1104, &v141);
        }
        if ( LOBYTE(v142[0]) )
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v142[1]);
        v13 = *(_QWORD *)(v6.m128i_i64[0] + 104);
        v14 = *(void (__fastcall **)(__int64, void **, void **))(*(_QWORD *)(v13 + 40) + 8LL);
        *(_OWORD *)v84 = 0;
        v85 = 0;
        std::string::_Construct<1,char const *>(v84, "Microsoft::Basix::Dct.IsClosedGracefullyByPeer", 46);
        v14(v13 + 40, v142, v84);
        std::string::_Tidy_deallocate(v84);
        if ( LOBYTE(v142[0]) )
        {
          v74 = 0;
          v15 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
                  *((_QWORD *)&v143 + 1),
                  &v74);
          v75 = v15;
          v74 = v15;
          if ( v15 )
          {
            memset(v86, 0, sizeof(v86));
            std::string::_Construct<1,char const *>(v86, "Microsoft::Basix::Dct.IsClosedGracefullyByPeer", 46);
            LOBYTE(v87) = 46;
            v16 = v86;
            if ( *((_QWORD *)&v86[1] + 1) > 0xFu )
              v16 = *(_OWORD **)&v86[0];
            v88 = v16;
            boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<bool>(
              a1 - 144,
              v86,
              &v74);
            std::string::_Tidy_deallocate(v86);
            v15 = v74;
            v75 = v74;
          }
        }
        else
        {
          v15 = v75;
        }
        if ( LOBYTE(v142[0]) )
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v142[1]);
        if ( v15 )
        {
          v74 = 5;
        }
        else
        {
          if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v141) )
          {
            if ( *(_BYTE *)(a1 + 1584) )
            {
              LODWORD(v84[0]) = 2;
              v18 = &Str1;
              v84[1] = (void *)&Str1;
              *(_QWORD *)&v85 = 0;
              BYTE8(v85) = 0;
              v73 = 0;
              LODWORD(v142[0]) = 2;
              v142[1] = "Force Remove Link";
              *(_QWORD *)&v143 = 17;
              BYTE8(v143) = 0;
              LODWORD(v92[0]) = 2;
              v92[1] = "smiles";
              *(_QWORD *)&v93 = 6;
              BYTE8(v93) = 0;
              v19 = v76;
              if ( v76[2] )
              {
                v18 = (const wchar_t *)v76;
                if ( (unsigned __int64)v76[3] > 0xF )
                  v18 = (const wchar_t *)*v76;
              }
              LODWORD(v90[0]) = 2;
              v90[1] = (void *)v18;
              *(_QWORD *)&v91 = strlen((const char *)v18);
              BYTE8(v91) = 0;
              if ( v81[2] )
              {
                v20 = (const wchar_t *)v81;
                if ( (unsigned __int64)v76[7] > 0xF )
                  v20 = (const wchar_t *)*v81;
              }
              else
              {
                v20 = &Str1;
              }
              LODWORD(v144[0]) = 2;
              v144[1] = (void *)v20;
              v145 = strlen((const char *)v20);
              v146 = 0;
              v21 = "client";
              if ( *(_BYTE *)(a1 + 8) )
                v21 = "stack";
              LODWORD(v138[0]) = 2;
              v138[1] = (void *)v21;
              v139 = strlen(v21);
              v140 = 0;
              v3 |= 0x3Fu;
              v79 = *(_DWORD *)(v6.m128i_i64[0] + 152);
              Microsoft::Basix::Instrumentation::MultiLinkError::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
                a1 + 1712,
                a1 + 1592,
                (unsigned int)&v79,
                (unsigned int)v138,
                (__int64)v137,
                (__int64)v144,
                (__int64)v90,
                (__int64)v92,
                (__int64)v142,
                (__int64)&v73,
                (__int64)v84);
            }
            else
            {
              v19 = v76;
            }
            if ( (v3 & 0x20) != 0 )
            {
              v3 &= ~0x20u;
              if ( v140 )
                operator delete(v138[1], v17);
            }
            if ( (v3 & 0x10) != 0 )
            {
              v3 &= ~0x10u;
              if ( v146 )
                operator delete(v144[1], v17);
            }
            if ( (v3 & 8) != 0 )
            {
              v3 &= ~8u;
              if ( BYTE8(v91) )
                operator delete(v90[1], v17);
            }
            if ( (v3 & 4) != 0 )
            {
              v3 &= ~4u;
              if ( BYTE8(v93) )
                operator delete(v92[1], v17);
            }
            if ( (v3 & 2) != 0 )
            {
              v3 &= ~2u;
              if ( BYTE8(v143) )
                operator delete(v142[1], v17);
            }
            if ( (v3 & 1) != 0 )
            {
              v3 &= ~1u;
              if ( BYTE8(v85) )
                operator delete(v84[1], v17);
            }
            *(_OWORD *)v138 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v138);
            if ( v138[0] && *((_BYTE *)v138[0] + 128) )
            {
              v99 = v114;
              v77 = 0;
              v78 = 0;
              std::string::_Construct<1,char const *>(&v77, "\"", 1);
              v82 = v19;
              if ( (unsigned __int64)v19[3] > 0xF )
                v82 = (__int64 *)*v19;
              memset(v107, 0, sizeof(v107));
              std::string::_Construct<1,char const *>(v107, "\"", 1);
              memset(v106, 0, sizeof(v106));
              std::string::_Construct<1,char const *>(v106, ":", 1);
              memset(v105, 0, sizeof(v105));
              std::string::_Construct<1,char const *>(v105, "\"", 1);
              memset(v104, 0, sizeof(v104));
              std::string::_Construct<1,char const *>(v104, "\"", 1);
              v22 = std::operator+<char>(v86, v104, "errorMessage");
              LOBYTE(v23) = v73;
              std::string::string(v129, v23, v22, v105);
              LOBYTE(v24) = v73;
              std::string::string(v128, v24, v129, v106);
              LOBYTE(v25) = v73;
              std::string::string(v127, v25, v128, v107);
              v26 = std::operator+<char>(v134, v127, v82);
              LOBYTE(v27) = v73;
              std::string::string(v114, v27, v26, &v77);
              v82 = v115;
              memset(v103, 0, sizeof(v103));
              std::string::_Construct<1,char const *>(v103, "\"", 1);
              if ( (unsigned __int64)v19[7] > 0xF )
                v81 = (__int64 *)*v81;
              memset(v102, 0, sizeof(v102));
              std::string::_Construct<1,char const *>(v102, "\"", 1);
              memset(v112, 0, sizeof(v112));
              std::string::_Construct<1,char const *>(v112, ":", 1);
              memset(v111, 0, sizeof(v111));
              std::string::_Construct<1,char const *>(v111, "\"", 1);
              memset(v110, 0, sizeof(v110));
              std::string::_Construct<1,char const *>(v110, "\"", 1);
              v28 = std::operator+<char>(v133, v110, "errorCodeSymbolic");
              LOBYTE(v29) = v73;
              std::string::string(v126, v29, v28, v111);
              LOBYTE(v30) = v73;
              std::string::string(v125, v30, v126, v112);
              LOBYTE(v31) = v73;
              std::string::string(v124, v31, v125, v102);
              v32 = std::operator+<char>(v132, v124, v81);
              LOBYTE(v33) = v73;
              std::string::string(v115, v33, v32, v103);
              v81 = v116;
              std::_Integral_to_string<char,unsigned int>(v123, v137[0]);
              memset(v109, 0, sizeof(v109));
              std::string::_Construct<1,char const *>(v109, ":", 1);
              memset(v108, 0, sizeof(v108));
              std::string::_Construct<1,char const *>(v108, "\"", 1);
              *(_OWORD *)v90 = 0;
              v91 = 0;
              std::string::_Construct<1,char const *>(v90, "\"", 1);
              v34 = std::operator+<char>(v131, v90, "errorCode");
              LOBYTE(v35) = v73;
              std::string::string(v122, v35, v34, v108);
              LOBYTE(v36) = v73;
              std::string::string(v121, v36, v122, v109);
              LOBYTE(v37) = v73;
              std::string::string(v116, v37, v121, v123);
              std::_Integral_to_string<char,unsigned int>(v120, *(unsigned int *)(v6.m128i_i64[0] + 152));
              *(_OWORD *)v92 = 0;
              v93 = 0;
              std::string::_Construct<1,char const *>(v92, ":", 1);
              *(_OWORD *)v142 = 0;
              v143 = 0;
              std::string::_Construct<1,char const *>(v142, "\"", 1);
              *(_OWORD *)v84 = 0;
              v85 = 0;
              std::string::_Construct<1,char const *>(v84, "\"", 1);
              v38 = std::operator+<char>(v130, v84, "linkId");
              LOBYTE(v39) = v73;
              std::string::string(v119, v39, v38, v142);
              LOBYTE(v40) = v73;
              std::string::string(v118, v40, v119, v92);
              LOBYTE(v41) = v73;
              std::string::string(v117, v41, v118, v120);
              v3 |= 0x3FFFC00u;
              Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string>(
                (int)v138,
                (int)"RD_CHECKPOINT",
                0,
                (int)"Smiles",
                "LinkRemoveDueToException",
                "Force Link Remove Due to Exception",
                (__int64)v117,
                (__int64)v116,
                (__int64)v115,
                (__int64)v114);
              std::string::_Tidy_deallocate(v118);
              std::string::_Tidy_deallocate(v119);
              std::string::_Tidy_deallocate(v130);
              std::string::_Tidy_deallocate(v84);
              std::string::_Tidy_deallocate(v142);
              std::string::_Tidy_deallocate(v92);
              std::string::_Tidy_deallocate(v120);
              std::string::_Tidy_deallocate(v121);
              std::string::_Tidy_deallocate(v122);
              std::string::_Tidy_deallocate(v131);
              std::string::_Tidy_deallocate(v90);
              std::string::_Tidy_deallocate(v108);
              std::string::_Tidy_deallocate(v109);
              std::string::_Tidy_deallocate(v123);
              std::string::_Tidy_deallocate(v132);
              std::string::_Tidy_deallocate(v124);
              std::string::_Tidy_deallocate(v125);
              std::string::_Tidy_deallocate(v126);
              std::string::_Tidy_deallocate(v133);
              std::string::_Tidy_deallocate(v110);
              std::string::_Tidy_deallocate(v111);
              std::string::_Tidy_deallocate(v112);
              std::string::_Tidy_deallocate(v102);
              std::string::_Tidy_deallocate(v103);
              std::string::_Tidy_deallocate(v134);
              std::string::_Tidy_deallocate(v127);
              std::string::_Tidy_deallocate(v128);
              std::string::_Tidy_deallocate(v129);
              std::string::_Tidy_deallocate(v86);
              std::string::_Tidy_deallocate(v104);
              std::string::_Tidy_deallocate(v105);
              std::string::_Tidy_deallocate(v106);
              std::string::_Tidy_deallocate(v107);
              std::string::_Tidy_deallocate(&v77);
            }
            v42 = (volatile signed __int32 *)v138[1];
            if ( v138[1] )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v138[1] + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
                if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
              }
            }
          }
          v74 = (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v141) != 0
              ? 6
              : 3;
        }
        *(_OWORD *)v138 = 0;
        if ( *(_DWORD *)(v6.m128i_i64[0] + 288) == 2 )
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v138);
          if ( v138[0] && *((_BYTE *)v138[0] + 128) )
          {
            v48 = *(_DWORD *)(v6.m128i_i64[0] + 152);
            v77 = 0;
            v78 = 0;
            std::string::_Construct<1,char const *>(
              &v77,
              "SmilesV3: link(%d)%p force remove already removed, ignore",
              57,
              v47);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,Microsoft::Basix::Dct::SmilesDisabled *>(
              (unsigned int)v138,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v77,
              v48,
              v6.m128i_i64[0]);
            std::string::_Tidy_deallocate(&v77);
          }
          v49 = (volatile signed __int32 *)v138[1];
          if ( v138[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v138[1] + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
              if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
            }
          }
          v9 = v80;
        }
        else
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v138);
          if ( v138[0] && *((_BYTE *)v138[0] + 128) )
          {
            v45 = *(_DWORD *)(v6.m128i_i64[0] + 152);
            v77 = 0;
            v78 = 0;
            std::string::_Construct<1,char const *>(
              &v77,
              "SmilesV3: link(%d)%p force remove: isGracefullyClosedByPeer=%d",
              62,
              v44,
              v72);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,Microsoft::Basix::Dct::LinkDataV3 *,bool>(
              (unsigned int)v138,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v77,
              v45,
              v6.m128i_i64[0],
              v15);
            std::string::_Tidy_deallocate(&v77);
          }
          v46 = (volatile signed __int32 *)v138[1];
          if ( v138[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v138[1] + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
              if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
            }
          }
          v9 = v80;
          if ( v80 )
            _InterlockedIncrement(v80 + 2);
          *(__m128i *)v138 = v6;
          LOBYTE(v43) = v74;
          Microsoft::Basix::Dct::OperationOnLinkId::Set(&v149, v43, v138);
          std::deque<Microsoft::Basix::Dct::OperationOnLinkId>::_Emplace_back_internal<Microsoft::Basix::Dct::OperationOnLinkId const &>(
            a1 + 2016,
            &v149);
          if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                                  &v83,
                                  *(_QWORD *)(a1 + 720)) )
            std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(&v94, &v83);
          if ( !*(_DWORD *)(v6.m128i_i64[0] + 288) )
            Microsoft::Basix::Dct::SmilesV3::Summary::UpdateLinkStatus(
              a1 + 952,
              *(unsigned int *)(v6.m128i_i64[0] + 80),
              0);
          Microsoft::Basix::Dct::LinkDataV3::SetInRemoved((Microsoft::Basix::Dct::LinkDataV3 *)v6.m128i_i64[0]);
        }
        *(_OWORD *)v138 = 0;
        if ( *(_DWORD *)(v6.m128i_i64[0] + 292) == 2 )
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v138);
          if ( v138[0] && *((_BYTE *)v138[0] + 128) )
          {
            v55 = *(_DWORD *)(v6.m128i_i64[0] + 152);
            v77 = 0;
            v78 = 0;
            std::string::_Construct<1,char const *>(
              &v77,
              "SmilesV3: link(%d)%p force remove already removed, ignore",
              57,
              v54);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,Microsoft::Basix::Dct::SmilesDisabled *>(
              (unsigned int)v138,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v77,
              v55,
              v6.m128i_i64[0]);
            std::string::_Tidy_deallocate(&v77);
          }
          v56 = (volatile signed __int32 *)v138[1];
          if ( v138[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v138[1] + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
              if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
            }
          }
        }
        else
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v138);
          if ( v138[0] && *((_BYTE *)v138[0] + 128) )
          {
            v52 = *(_DWORD *)(v6.m128i_i64[0] + 152);
            v77 = 0;
            v78 = 0;
            std::string::_Construct<1,char const *>(
              &v77,
              "SmilesV3: link(%d)%p force remove: isGracefullyClosedByPeer=%d",
              62,
              v51,
              v72);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,Microsoft::Basix::Dct::LinkDataV3 *,bool>(
              (unsigned int)v138,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v77,
              v52,
              v6.m128i_i64[0],
              v75);
            std::string::_Tidy_deallocate(&v77);
          }
          v53 = (volatile signed __int32 *)v138[1];
          if ( v138[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v138[1] + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
              if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
            }
          }
          if ( v9 )
            _InterlockedIncrement(v9 + 2);
          *(__m128i *)v138 = v6;
          LOBYTE(v50) = v74;
          Microsoft::Basix::Dct::OperationOnLinkId::Set(&v147, v50, v138);
          if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                                  &v83,
                                  *(_QWORD *)(a1 + 712)) )
          {
            *(_OWORD *)v138 = 0;
            Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::ChangePrimary(a1 - 1104, v138, 0);
          }
          Microsoft::Basix::Dct::LinkDataV3::SetOutRemoved((Microsoft::Basix::Dct::LinkDataV3 *)v6.m128i_i64[0]);
        }
        v4 = v76;
      }
      if ( !*(_DWORD *)(a1 + 1104) )
      {
        *(_DWORD *)(a1 + 1104) = 2;
        v57 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::ITimerCallback>(
                a1 + *(int *)(*(_QWORD *)(a1 - 1096) + 4LL) - 1096LL,
                &pExceptionObject);
        v97 = 0;
        Microsoft::Basix::Timer::Setup(a1 + 1920, &v97, v57);
      }
      Mtx_unlock((_Mtx_t)v5);
      __ExceptionPtrDestroy(&v141);
      if ( v6.m128i_i64[0] )
      {
        if ( *((_QWORD *)&v149 + 1) )
          Microsoft::Basix::Dct::SmilesV3::ProcessLinkOperation(
            (Microsoft::Basix::Dct::SmilesV3 *)(a1 - 1104),
            (const struct Microsoft::Basix::Dct::OperationOnLinkId *)&v149);
        if ( *((_QWORD *)&v147 + 1) )
          Microsoft::Basix::Dct::SmilesV3::ProcessLinkOperation(
            (Microsoft::Basix::Dct::SmilesV3 *)(a1 - 1104),
            (const struct Microsoft::Basix::Dct::OperationOnLinkId *)&v147);
      }
      v58 = (volatile signed __int32 *)v148;
      if ( (_QWORD)v148 )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v148 + 8)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
          if ( !_InterlockedDecrement(v58 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
        }
      }
      v59 = (volatile signed __int32 *)v150;
      if ( (_QWORD)v150 )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v150 + 8)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
          if ( !_InterlockedDecrement(v59 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
        }
      }
      if ( v9 )
      {
        if ( !_InterlockedDecrement(v9 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
          if ( !_InterlockedDecrement(v9 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
      v4 += 11;
      v76 = v4;
    }
    while ( v4 != v98 );
    if ( (_QWORD)v94
      && (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                            &v94,
                            *(_QWORD *)(a1 + 720)) )
    {
      *(_OWORD *)v138 = 0;
      v144[0] = (void *)v5;
      if ( Mtx_lock((_Mtx_t)v5) )
        std::_Throw_Cpp_error(5);
      if ( *(_DWORD *)(v5 + 76) == 0x7FFFFFFF )
      {
        *(_DWORD *)(v5 + 76) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      LOBYTE(v86[0]) = 7;
      memset((char *)v86 + 8, 0, 24);
      LOWORD(v87) = 0;
      BYTE2(v87) = 0;
      v88 = 0;
      v95 = 0;
      v60 = Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(a1 - 1104, &pExceptionObject, v86, &v95);
      v61 = *(void **)v60;
      v62 = *(volatile signed __int32 **)(v60 + 8);
      *(_QWORD *)v60 = 0;
      *(_QWORD *)(v60 + 8) = 0;
      v138[0] = v61;
      v138[1] = (void *)v62;
      v63 = *(volatile signed __int32 **)&pExceptionObject._Id;
      if ( *(_QWORD *)&pExceptionObject._Id )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&pExceptionObject._Id + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
          if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
        }
      }
      std::vector<short>::_Tidy((char *)v86 + 8);
      Mtx_unlock((_Mtx_t)v5);
      if ( v61 )
      {
        v83 = 0;
        Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::Dct::SmilesV3>(
          a1 + *(int *)(*(_QWORD *)(a1 - 1096) + 4LL) - 1096LL,
          &v83);
        v64 = (volatile signed __int32 *)v83.m128i_i64[1];
        if ( v83.m128i_i64[1] )
          _InterlockedIncrement((volatile signed __int32 *)(v83.m128i_i64[1] + 8));
        *(_QWORD *)&v147 = v83.m128i_i64[0];
        v65 = v64;
        *((_QWORD *)&v147 + 1) = v64;
        if ( v62 )
          _InterlockedIncrement(v62 + 2);
        *(_QWORD *)&v148 = v61;
        *((_QWORD *)&v148 + 1) = v62;
        v89 = 0;
        v66 = v62;
        if ( (unsigned __int8)std::_Test_callable<_lambda_052e919cc0e5399df76dff3972c0cac1_>(&v147) )
        {
          *(_QWORD *)&v86[0] = &std::_Func_impl_no_alloc<_lambda_7a084d6c10af701ffead2c85ce5d90dc_,void,>::`vftable';
          *((_QWORD *)&v86[0] + 1) = v67;
          *(_QWORD *)&v86[1] = v64;
          v147 = 0;
          *((_QWORD *)&v86[1] + 1) = v61;
          v87 = v62;
          v148 = 0;
          v89 = v86;
          v66 = 0;
          v65 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        }
        v68 = Microsoft::Basix::Instrumentation::ActivityFunction<void>(v135, v86);
        std::thread::_Start<std::function<void (void)>,>(&v141, v68);
        if ( !v141._Id || (pExceptionObject = v141, Thrd_detach(&pExceptionObject)) )
          std::_Throw_Cpp_error(1);
        v141 = 0;
        if ( v136 )
        {
          LOBYTE(v69) = v136 != v135;
          (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v136 + 32LL))(v136, v69);
          v136 = 0;
        }
        if ( v66 )
        {
          if ( !_InterlockedDecrement(v66 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
            if ( !_InterlockedDecrement(v66 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
          }
        }
        if ( v65 )
        {
          if ( !_InterlockedDecrement(v65 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
            if ( !_InterlockedDecrement(v65 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
          }
        }
        if ( v64 )
        {
          if ( !_InterlockedDecrement(v64 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
            if ( !_InterlockedDecrement(v64 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
          }
        }
      }
      if ( v62 )
      {
        if ( !_InterlockedDecrement(v62 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
          if ( !_InterlockedDecrement(v62 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
        }
      }
    }
    v70 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
    if ( *((_QWORD *)&v94 + 1) && !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v70)(v70);
      if ( !_InterlockedDecrement(v70 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
    }
  }
}

```

## disassembly

```asm
0x18025ff00  mov     [rsp-8+arg_10], rbx
0x18025ff05  push    rbp
0x18025ff06  push    rsi
0x18025ff07  push    rdi
0x18025ff08  push    r12
0x18025ff0a  push    r13
0x18025ff0c  push    r14
0x18025ff0e  push    r15
0x18025ff10  lea     rbp, [rsp-600h]
0x18025ff18  mov     eax, 700h
0x18025ff1d  call    _alloca_probe
0x18025ff22  sub     rsp, rax
0x18025ff25  movaps  [rsp+730h+var_40], xmm6
0x18025ff2d  mov     rax, cs:__security_cookie
0x18025ff34  xor     rax, rsp
0x18025ff37  mov     [rbp+630h+var_50], rax
0x18025ff3e  mov     r12, rcx
0x18025ff41  xor     r13d, r13d
0x18025ff44  mov     r15d, r13d
0x18025ff47  mov     [rbp+630h+var_6A0], r13d
0x18025ff4b  mov     rdi, [rdx]
0x18025ff4e  mov     [rsp+730h+var_6C8], rdi
0x18025ff53  mov     rax, [rdx+8]
0x18025ff57  mov     [rbp+630h+var_588], rax
0x18025ff5e  xorps   xmm0, xmm0
0x18025ff61  cmp     rdi, rax
0x18025ff64  jz      loc_1802616FF
0x18025ff6a  xorps   xmm1, xmm1
0x18025ff6d  movdqu  [rbp+630h+var_5D0], xmm1
0x18025ff72  movdqu  [rbp+630h+var_578], xmm0
0x18025ff7a  movdqu  [rbp+630h+var_568], xmm1
0x18025ff82  lea     rbx, [rcx+2D8h]
0x18025ff89  mov     [rbp+630h+var_3F8], rbx
0x18025ff90  or      r14d, 0FFFFFFFFh
0x18025ff94  mov     eax, [rdi+40h]
0x18025ff97  mov     [rbp+630h+var_110], eax
0x18025ff9d  lea     rax, [rdi+20h]
0x18025ffa1  mov     [rbp+630h+var_690], rax
0x18025ffa5  xorps   xmm0, xmm0
0x18025ffa8  xorps   xmm6, xmm6
0x18025ffab  movdqa  [rbp+630h+var_680], xmm6
0x18025ffb0  movups  [rbp+630h+var_70], xmm0
0x18025ffb7  movups  [rbp+630h+var_60], xmm0
0x18025ffbe  lea     r9, [rbp+630h+var_578]
0x18025ffc5  xor     r8d, r8d
0x18025ffc8  mov     dl, 1
0x18025ffca  lea     rcx, [rbp+630h+var_70]
0x18025ffd1  call    ??0OperationOnLinkId@Dct@Basix@Microsoft@@QEAA@W4Direction@LinkData@123@W4Mode@0123@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(Microsoft::Basix::Dct::LinkData::Direction,Microsoft::Basix::Dct::OperationOnLinkId::Mode,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>)
0x18025ffd6  nop
0x18025ffd7  xorps   xmm0, xmm0
0x18025ffda  movups  [rbp+630h+var_90], xmm0
0x18025ffe1  movups  [rbp+630h+var_80], xmm0
0x18025ffe8  lea     r9, [rbp+630h+var_568]
0x18025ffef  xor     r8d, r8d
0x18025fff2  xor     edx, edx
0x18025fff4  lea     rcx, [rbp+630h+var_90]
0x18025fffb  call    ??0OperationOnLinkId@Dct@Basix@Microsoft@@QEAA@W4Direction@LinkData@123@W4Mode@0123@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(Microsoft::Basix::Dct::LinkData::Direction,Microsoft::Basix::Dct::OperationOnLinkId::Mode,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>)
0x180260000  nop
0x180260001  mov     [rsp+730h+var_6CE], r13b
0x180260006  xorps   xmm1, xmm1
0x180260009  movdqu  [rbp+630h+var_E0], xmm1
0x180260011  lea     rcx, [rbp+630h+var_E0]; void *
0x180260018  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18026001d  nop
0x18026001e  mov     rcx, rbx; _Mtx_t
0x180260021  call    _Mtx_lock
0x180260026  test    eax, eax
0x180260028  jnz     loc_180261804
0x18026002e  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180260035  jz      loc_18026185E
0x18026003b  xorps   xmm0, xmm0
0x18026003e  movups  xmmword ptr [rbp+630h+var_B0], xmm0
0x180260045  lea     rdx, [r12+1A8h]
0x18026004d  lea     rcx, [rbp+630h+var_B0]
0x180260054  call    ??0iterator@?$IterationSafeStore@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAA@PEBV1234@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>> const *)
0x180260059  bts     r15d, 9
0x18026005e  xorps   xmm1, xmm1
0x180260061  movdqu  xmmword ptr [rbp+630h+var_100], xmm1
0x180260069  bts     r15d, 8
0x18026006e  mov     rsi, [rbp+630h+var_B0]
0x180260075  test    rsi, rsi
0x180260078  jz      short loc_1802600B5
0x18026007a  mov     r13, [rbp+630h+var_B0+8]
0x180260081  mov     rcx, [r13+0]
0x180260085  add     rcx, 68h ; 'h'
0x180260089  lea     rdx, [rdi+48h]
0x18026008d  call    ??$?8U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@detail@multi_index@boost@@YA_NAEBV?$bidir_node_iterator@U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@012@0@Z; boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &,boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &)
0x180260092  test    al, al
0x180260094  jnz     short loc_1802600A4
0x180260096  lea     rcx, [rbp+630h+var_B0]
0x18026009d  call    ??Eiterator@?$IterationSafeStore@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@U?$owner_equals@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@@Algorithm@Basix@Microsoft@@@Containers@Basix@Microsoft@@QEAAAEAV01234@XZ; Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(void)
0x1802600a2  jmp     short loc_18026006E
0x1802600a4  mov     rdx, r13
0x1802600a7  lea     rcx, [rbp+630h+var_680]
0x1802600ab  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x1802600b0  movdqa  xmm6, [rbp+630h+var_680]
0x1802600b5  test    rsi, rsi
0x1802600b8  jz      short loc_1802600D3
0x1802600ba  lea     rcx, [rsi+50h]
0x1802600be  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x1802600c3  mov     ecx, r14d
0x1802600c6  lock xadd [rax], ecx
0x1802600ca  cmp     ecx, 0FFFFFFFFh
0x1802600cd  jz      loc_18026181A
0x1802600d3  movdqa  xmm0, xmm6
0x1802600d7  psrldq  xmm0, 8
0x1802600dc  movq    rsi, xmm0
0x1802600e1  mov     [rbp+630h+var_698], rsi
0x1802600e5  movq    r13, xmm6
0x1802600ea  test    r13, r13
0x1802600ed  jz      loc_1802611BB
0x1802600f3  mov     eax, [r13+118h]
0x1802600fa  mov     [r13+120h], eax
0x180260101  mov     eax, [r13+11Ch]
0x180260108  mov     [r13+124h], eax
0x18026010f  mov     rsi, [r13+68h]
0x180260113  mov     rax, [rsi+28h]
0x180260117  mov     rdi, [rax+8]
0x18026011b  xorps   xmm0, xmm0
0x18026011e  movups  xmmword ptr [rbp+630h+var_670], xmm0
0x180260122  xorps   xmm1, xmm1
0x180260125  movdqu  [rbp+630h+var_660], xmm1
0x18026012a  mov     r8d, 23h ; '#'
0x180260130  lea     rdx, aMicrosoftBasix_104; "Microsoft::Basix::Dct.LastException"
0x180260137  lea     rcx, [rbp+630h+var_670]
0x18026013b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180260140  nop
0x180260141  lea     r8, [rbp+630h+var_670]
0x180260145  lea     rdx, [rbp+630h+var_D0]
0x18026014c  lea     rcx, [rsi+28h]
0x180260150  mov     rax, rdi
0x180260153  call    cs:__guard_dispatch_icall_fptr
0x180260159  nop
0x18026015a  lea     rcx, [rbp+630h+var_670]
0x18026015e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180260163  xor     esi, esi
0x180260165  cmp     byte ptr [rbp+630h+var_D0], sil
0x18026016c  jz      loc_1802601FF
0x180260172  xorps   xmm0, xmm0
0x180260175  movdqu  xmmword ptr [rbp+630h+var_100], xmm0
0x18026017d  lea     rcx, [rbp+630h+var_100]; void *
0x180260184  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180260189  nop
0x18026018a  lea     r8, [rbp+630h+var_100]
0x180260191  lea     rdx, [rbp+630h+var_5C0]
0x180260195  mov     rcx, qword ptr [rbp+630h+var_C0+8]
0x18026019c  call    ??$get_value@Vexception_ptr@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AVexception_ptr@std@@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(std::exception_ptr const &)
0x1802601a1  or      r15d, 0C0h
0x1802601a8  lea     rdx, [rbp+630h+var_5C0]; void *
0x1802601ac  lea     rcx, [rbp+630h+var_E0]; void *
0x1802601b3  call    ?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1802601b8  lea     rcx, [rbp+630h+var_E0]
0x1802601bf  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x1802601c4  mov     dil, al
0x1802601c7  lea     rcx, [rbp+630h+var_5C0]; void *
0x1802601cb  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1802601d0  nop
0x1802601d1  lea     rcx, [rbp+630h+var_100]; void *
0x1802601d8  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1802601dd  test    dil, dil
0x1802601e0  jz      short loc_1802601FF
0x1802601e2  lea     rcx, [r12-450h]
0x1802601ea  mov     rax, [rcx]
0x1802601ed  lea     rdx, [rbp+630h+var_E0]
0x1802601f4  mov     rax, [rax+78h]
0x1802601f8  call    cs:__guard_dispatch_icall_fptr
0x1802601fe  nop
0x1802601ff  cmp     byte ptr [rbp+630h+var_D0], sil
0x180260206  jz      short loc_180260214
0x180260208  lea     rcx, [rbp+630h+var_D0+8]
0x18026020f  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180260214  mov     rsi, [r13+68h]
0x180260218  mov     rax, [rsi+28h]
0x18026021c  mov     rdi, [rax+8]
0x180260220  xorps   xmm0, xmm0
0x180260223  movups  xmmword ptr [rbp+630h+var_670], xmm0
0x180260227  xorps   xmm1, xmm1
0x18026022a  movdqu  [rbp+630h+var_660], xmm1
0x18026022f  mov     r8d, 2Eh ; '.'
0x180260235  lea     rdx, aMicrosoftBasix_131; "Microsoft::Basix::Dct.IsClosedGracefull"...
0x18026023c  lea     rcx, [rbp+630h+var_670]
0x180260240  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180260245  nop
0x180260246  lea     r8, [rbp+630h+var_670]
0x18026024a  lea     rdx, [rbp+630h+var_D0]
0x180260251  lea     rcx, [rsi+28h]
0x180260255  mov     rax, rdi
0x180260258  call    cs:__guard_dispatch_icall_fptr
0x18026025e  nop
0x18026025f  lea     rcx, [rbp+630h+var_670]
0x180260263  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180260268  xor     edi, edi
0x18026026a  cmp     byte ptr [rbp+630h+var_D0], dil
0x180260271  jz      loc_180260301
0x180260277  mov     [rsp+730h+var_6CF], dil
0x18026027c  lea     rdx, [rsp+730h+var_6CF]
0x180260281  mov     rcx, qword ptr [rbp+630h+var_C0+8]
0x180260288  call    ??$get_value@_N@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA_NAEB_N@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(bool const &)
0x18026028d  mov     sil, al
0x180260290  mov     [rsp+730h+var_6CE], al
0x180260294  mov     [rsp+730h+var_6CF], al
0x180260298  test    al, al
0x18026029a  jz      short loc_180260306
0x18026029c  xorps   xmm0, xmm0
0x18026029f  movups  [rbp+630h+var_650], xmm0
0x1802602a3  xorps   xmm1, xmm1
0x1802602a6  movdqu  [rbp+630h+var_640], xmm1
0x1802602ab  lea     r8d, [rdi+2Eh]
0x1802602af  lea     rdx, aMicrosoftBasix_131; "Microsoft::Basix::Dct.IsClosedGracefull"...
0x1802602b6  lea     rcx, [rbp+630h+var_650]
0x1802602ba  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802602bf  mov     byte ptr [rbp+630h+var_630], 2Eh ; '.'
0x1802602c3  lea     rax, [rbp+630h+var_650]
0x1802602c7  cmp     qword ptr [rbp+630h+var_640+8], 0Fh
0x1802602cc  cmova   rax, qword ptr [rbp+630h+var_650]
0x1802602d1  mov     [rbp+630h+var_628], rax
0x1802602d5  lea     r8, [rsp+730h+var_6CF]
0x1802602da  lea     rdx, [rbp+630h+var_650]
0x1802602de  lea     rcx, [r12-90h]
0x1802602e6  call    ??$put@_N@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEB_N@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<bool>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,bool const &)
0x1802602eb  nop
0x1802602ec  lea     rcx, [rbp+630h+var_650]
0x1802602f0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802602f5  mov     sil, [rsp+730h+var_6CF]
0x1802602fa  mov     [rsp+730h+var_6CE], sil
0x1802602ff  jmp     short loc_180260306
0x180260301  mov     sil, [rsp+730h+var_6CE]
0x180260306  cmp     byte ptr [rbp+630h+var_D0], dil
0x18026030d  jz      short loc_18026031B
0x18026030f  lea     rcx, [rbp+630h+var_D0+8]
0x180260316  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18026031b  test    sil, sil
0x18026031e  jnz     loc_180260D7A
0x180260324  lea     rcx, [rbp+630h+var_E0]
0x18026032b  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x180260330  test    al, al
0x180260332  jz      loc_180260D60
0x180260338  cmp     [r12+630h], dil
0x180260340  jz      loc_1802604CF
0x180260346  mov     edx, 2
0x18026034b  mov     dword ptr [rbp+630h+var_670], edx
0x18026034e  lea     rcx, Str1
0x180260355  mov     [rbp+630h+var_670+8], rcx
0x180260359  mov     qword ptr [rbp+630h+var_660], rdi
0x18026035d  mov     byte ptr [rbp+630h+var_660+8], dil
0x180260361  mov     [rsp+730h+var_6D0], dil
0x180260366  mov     dword ptr [rbp+630h+var_D0], edx
0x18026036c  lea     rax, aForceRemoveLin; "Force Remove Link"
0x180260373  mov     [rbp+630h+var_D0+8], rax
0x18026037a  mov     qword ptr [rbp+630h+var_C0], 11h
0x180260385  mov     byte ptr [rbp+630h+var_C0+8], dil
0x18026038c  mov     dword ptr [rbp+630h+var_5F0], edx
0x18026038f  lea     rax, aSmiles_0; "smiles"
0x180260396  mov     [rbp+630h+var_5F0+8], rax
0x18026039a  mov     qword ptr [rbp+630h+var_5E0], 6
0x1802603a2  mov     byte ptr [rbp+630h+var_5E0+8], dil
0x1802603a6  mov     rdi, [rsp+730h+var_6C8]
0x1802603ab  xor     eax, eax
0x1802603ad  cmp     [rdi+10h], rax
0x1802603b1  jz      short loc_1802603C0
0x1802603b3  mov     rcx, rdi
0x1802603b6  cmp     qword ptr [rdi+18h], 0Fh
0x1802603bb  jbe     short loc_1802603C0
0x1802603bd  mov     rcx, [rdi]; Str
0x1802603c0  mov     dword ptr [rbp+630h+var_610], edx
0x1802603c3  mov     [rbp+630h+var_610+8], rcx
0x1802603c7  call    strlen
0x1802603cc  mov     qword ptr [rbp+630h+var_600], rax
0x1802603d0  xor     ecx, ecx
0x1802603d2  mov     byte ptr [rbp+630h+var_600+8], cl
0x1802603d5  mov     rax, [rbp+630h+var_690]
0x1802603d9  cmp     [rax+10h], rcx
0x1802603dd  jnz     short loc_1802603E8
0x1802603df  lea     rcx, Str1
0x1802603e6  jmp     short loc_1802603F5
0x1802603e8  mov     rcx, rax
0x1802603eb  cmp     qword ptr [rdi+38h], 0Fh
0x1802603f0  jbe     short loc_1802603F5
0x1802603f2  mov     rcx, [rax]; Str
0x1802603f5  mov     dword ptr [rbp+630h+var_B0], 2
0x1802603ff  mov     [rbp+630h+var_B0+8], rcx
0x180260406  call    strlen
0x18026040b  mov     [rbp+630h+var_A0], rax
0x180260412  xor     edx, edx
0x180260414  mov     [rbp+630h+var_98], dl
0x18026041a  lea     rax, aStack; "stack"
0x180260421  lea     rcx, aClient_0; "client"
0x180260428  cmp     [r12+8], dl
0x18026042d  cmovnz  rcx, rax; Str
0x180260431  mov     dword ptr [rbp+630h+var_100], 2
0x18026043b  mov     [rbp+630h+var_100+8], rcx
0x180260442  call    strlen
0x180260447  mov     [rbp+630h+var_F0], rax
0x18026044e  xor     eax, eax
0x180260450  mov     [rbp+630h+var_E8], al
0x180260456  or      r15d, 3Fh
0x18026045a  mov     eax, [r13+98h]
0x180260461  mov     [rbp+630h+var_6A0], eax
0x180260464  lea     rdx, [r12+638h]
0x18026046c  lea     rax, [rbp+630h+var_670]
  ... truncated ...
```

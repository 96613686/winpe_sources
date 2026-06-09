# Microsoft::RdpNano::ClientHeartBeat::HeartBeatThread(std::weak_ptr<Microsoft::RdpNano::ClientHeartBeat>)

- ea: `0x180128424`
- end: `0x180129257`
- name: `?HeartBeatThread@ClientHeartBeat@RdpNano@Microsoft@@CAXV?$weak_ptr@VClientHeartBeat@RdpNano@Microsoft@@@std@@@Z`
- size: `3635`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180127770`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ab4c`
- `0x18001edb4`
- `0x180029d6c`
- `0x1800492b0`
- `0x1800c4ac4`
- `0x1800f64ec`
- `0x1800f7968`
- `0x1800f8ca0`
- `0x1800f9030`
- `0x1800f97c0`
- `0x1800f9864`
- `0x180107b8c`
- `0x180126db0`
- `0x180128424`
- `0x180129258`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x180312e30`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x180375c40`
- `0x180376380`

## string_xrefs

- `0x180128604`: `ClientHeartBeat::HeartBeatThread: owner destroyed, exiting after %d sends`
- `0x1801290e8`: `ClientHeartBeat::HeartBeatThread: uri empty or interval<=0, exiting after %d sends`
- `0x18012880c`: `ClientHeartBeat::HeartBeatThread: stopped externally, exiting after %d sends`
- `0x1801288b2`: `ClientHeartBeat::HeartBeatThread: woke up due to token update`
- `0x180128bc1`: `ClientHeartBeat: server returned empty URI, disabling heartbeat`

## pseudocode

```c
// Hidden C++ exception states: #wind=59 #try_helpers=1
__int64 __fastcall Microsoft::RdpNano::ClientHeartBeat::HeartBeatThread(__int64 *a1)
{
  __int64 v2; // rdx
  signed __int32 v3; // eax
  signed __int32 v4; // ett
  __int64 result; // rax
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 *v7; // rcx
  unsigned int v8; // r13d
  __m128i si128; // xmm6
  __int64 v10; // rdx
  signed __int32 v11; // eax
  signed __int32 v12; // ett
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rbx
  __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // r15
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v19; // rdx
  signed __int32 v20; // eax
  signed __int32 v21; // ett
  __int128 v22; // kr50_16
  _BYTE *v23; // rbx
  void *v24; // rax
  __int64 v25; // rax
  __int128 *v26; // rax
  volatile signed __int32 *v27; // rbx
  char v28; // bl
  __int128 *v29; // rax
  __int64 v30; // r9
  __int64 v31; // r15
  volatile signed __int32 *v32; // r15
  volatile signed __int32 *v33; // rbx
  __int128 v34; // [rsp+30h] [rbp-2C8h]
  unsigned int v35; // [rsp+40h] [rbp-2B8h]
  volatile signed __int32 **v36; // [rsp+68h] [rbp-290h]
  __int128 v37; // [rsp+70h] [rbp-288h] BYREF
  __int128 v38; // [rsp+80h] [rbp-278h]
  char v39; // [rsp+90h] [rbp-268h]
  __int128 *v40; // [rsp+98h] [rbp-260h]
  __int64 v41; // [rsp+A0h] [rbp-258h] BYREF
  char v42[40]; // [rsp+A8h] [rbp-250h] BYREF
  char v43[8]; // [rsp+D0h] [rbp-228h] BYREF
  __int128 v44; // [rsp+D8h] [rbp-220h] BYREF
  __int128 v45; // [rsp+E8h] [rbp-210h] BYREF
  __int128 v46; // [rsp+F8h] [rbp-200h]
  __int128 v47; // [rsp+108h] [rbp-1F0h] BYREF
  __int128 v48; // [rsp+118h] [rbp-1E0h]
  char v49; // [rsp+128h] [rbp-1D0h]
  __int128 *v50; // [rsp+130h] [rbp-1C8h]
  _OWORD v51[2]; // [rsp+138h] [rbp-1C0h] BYREF
  __int128 v52; // [rsp+158h] [rbp-1A0h] BYREF
  __int64 v53; // [rsp+168h] [rbp-190h]
  __int64 v54; // [rsp+170h] [rbp-188h]
  _OWORD v55[2]; // [rsp+178h] [rbp-180h] BYREF
  _OWORD v56[2]; // [rsp+198h] [rbp-160h] BYREF
  __int64 v57; // [rsp+1B8h] [rbp-140h]
  _QWORD v58[30]; // [rsp+1C0h] [rbp-138h] BYREF

  v2 = a1[1];
  if ( v2 )
  {
    v3 = *(_DWORD *)(v2 + 8);
    while ( v3 )
    {
      v4 = v3;
      v3 = _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 8), v3 + 1, v3);
      if ( v4 == v3 )
      {
        result = *a1;
        v6 = (volatile signed __int32 *)a1[1];
        goto LABEL_6;
      }
    }
  }
  v6 = 0;
  result = 0;
LABEL_6:
  if ( !result )
  {
    if ( v6 )
    {
      result = (unsigned int)_InterlockedDecrement(v6 + 2);
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        result = (unsigned int)_InterlockedDecrement(v6 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    v7 = (volatile signed __int32 *)a1[1];
    goto LABEL_126;
  }
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v8 = 0;
  v35 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v52 = 0;
    v53 = 0;
    v54 = 15;
    LOBYTE(v52) = 0;
    v34 = 0;
    v36 = (volatile signed __int32 **)(a1 + 1);
    v10 = a1[1];
    if ( v10 )
    {
      v11 = *(_DWORD *)(v10 + 8);
      while ( v11 )
      {
        v12 = v11;
        v11 = _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 8), v11 + 1, v11);
        if ( v12 == v11 )
        {
          v13 = *a1;
          v34 = *(_OWORD *)a1;
          goto LABEL_23;
        }
      }
    }
    v13 = 0;
LABEL_23:
    if ( !v13 )
    {
      v44 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v44);
      if ( (_QWORD)v44 && *(_BYTE *)(v44 + 128) )
      {
        v45 = 0;
        v46 = 0;
        std::string::_Construct<1,char const *>(
          &v45,
          "ClientHeartBeat::HeartBeatThread: owner destroyed, exiting after %d sends",
          73);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,enum Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode>(
          &v44,
          "RENDEZVOUS",
          &v45,
          v8);
        std::string::_Tidy_deallocate(&v45);
      }
      v14 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
      if ( *((_QWORD *)&v44 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      goto LABEL_121;
    }
    v15 = v13 + 184;
    v47 = (unsigned __int64)(v13 + 184);
    if ( Mtx_lock((_Mtx_t)(v13 + 184)) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v15 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v15 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v47) = 1;
    std::string::operator=(&v52, v34 + 8);
    v16 = *(_QWORD *)(v34 + 40);
    *(_QWORD *)&v51[0] = v16;
    if ( !v53 || v16 <= 0 )
    {
      v44 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v44);
      if ( (_QWORD)v44 && *(_BYTE *)(v44 + 128) )
      {
        memset(v55, 0, sizeof(v55));
        std::string::_Construct<1,char const *>(
          v55,
          "ClientHeartBeat::HeartBeatThread: uri empty or interval<=0, exiting after %d sends",
          82);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,enum Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode>(
          &v44,
          "RENDEZVOUS",
          v55,
          v8);
        std::string::_Tidy_deallocate(v55);
      }
LABEL_116:
      v33 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
      if ( *((_QWORD *)&v44 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
          if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
        }
      }
      Mtx_unlock((_Mtx_t)v15);
LABEL_121:
      if ( *((_QWORD *)&v34 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (***((void (__fastcall ****)(_QWORD))&v34 + 1))(*((_QWORD *)&v34 + 1));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 12LL), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v34 + 1) + 8LL))(*((_QWORD *)&v34 + 1));
        }
      }
      goto LABEL_125;
    }
    v17 = std::_To_absolute_time<__int64,std::ratio<1,1000>>(v42, v51);
    while ( !*(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v34 + 176)
         && !*(_BYTE *)(v34 + 177) )
    {
      if ( (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                           v34 + 264,
                           &v47,
                           v17) == 1 )
      {
        (*(void (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v34 + 176);
        break;
      }
    }
    if ( *(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v34 + 176) )
    {
      v44 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v44);
      if ( (_QWORD)v44 && *(_BYTE *)(v44 + 128) )
      {
        v45 = 0;
        v46 = 0;
        std::string::_Construct<1,char const *>(
          &v45,
          "ClientHeartBeat::HeartBeatThread: stopped externally, exiting after %d sends",
          76);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,enum Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode>(
          &v44,
          "RENDEZVOUS",
          &v45,
          v8);
        std::string::_Tidy_deallocate(&v45);
      }
      goto LABEL_116;
    }
    if ( *(_BYTE *)(v34 + 177) )
    {
      v51[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v51);
      if ( *(_QWORD *)&v51[0] && *(_BYTE *)(*(_QWORD *)&v51[0] + 128LL) )
      {
        v45 = 0;
        v46 = 0;
        std::string::_Construct<1,char const *>(
          &v45,
          "ClientHeartBeat::HeartBeatThread: woke up due to token update",
          61);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          v51,
          "RENDEZVOUS",
          &v45);
        std::string::_Tidy_deallocate(&v45);
      }
      v18 = (volatile signed __int32 *)*((_QWORD *)&v51[0] + 1);
      if ( *((_QWORD *)&v51[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v51[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
    }
    *(_BYTE *)(v34 + 177) = 0;
    Mtx_unlock((_Mtx_t)v15);
    if ( *((_QWORD *)&v34 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL)) )
      {
        (***((void (__fastcall ****)(_QWORD))&v34 + 1))(*((_QWORD *)&v34 + 1));
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 12LL)) )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v34 + 1) + 8LL))(*((_QWORD *)&v34 + 1));
      }
    }
    v19 = *v36;
    if ( *v36 )
    {
      v20 = *((_DWORD *)v19 + 2);
      while ( v20 )
      {
        v21 = v20;
        v20 = _InterlockedCompareExchange(v19 + 2, v20 + 1, v20);
        if ( v21 == v20 )
        {
          v22 = *(_OWORD *)a1;
          goto LABEL_63;
        }
      }
    }
    v22 = 0;
LABEL_63:
    if ( !(_QWORD)v22 )
      break;
    v23 = (_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v22 + 176);
    if ( *v23 )
      break;
    Microsoft::RdpNano::ClientHeartBeat::PerformHttpGet(v22, v55, &v52);
    v57 = 0;
    v56[0] = 0;
    v56[1] = si128;
    LOBYTE(v56[0]) = 0;
    v24 = operator new(0x20u);
    *(_QWORD *)&v51[0] = v24;
    if ( v24 )
      v25 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V12_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V12_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V12_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V12_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v24);
    else
      v25 = 0;
    v57 = v25;
    memset(v58, 0, sizeof(v58));
    std::istringstream::istringstream(v58, v55, 1);
    boost::property_tree::json_parser::read_json<boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>(
      v58,
      v56);
    v47 = 0;
    v48 = 0;
    std::string::_Construct<1,char const *>(&v47, (const char *)&Str1, 0);
    v37 = 0;
    v38 = 0;
    std::string::_Construct<1,char const *>(&v37, "uri", 3);
    v39 = 46;
    v26 = &v37;
    if ( *((_QWORD *)&v38 + 1) > 0xFu )
      v26 = (__int128 *)v37;
    v40 = v26;
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::string>(
      v56,
      &v45,
      &v37,
      &v47);
    std::string::_Tidy_deallocate(&v37);
    std::string::_Tidy_deallocate(&v47);
    v47 = 0;
    if ( !(_QWORD)v46 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v47);
      if ( (_QWORD)v47 && *(_BYTE *)(v47 + 128) )
      {
        memset(v51, 0, sizeof(v51));
        std::string::_Construct<1,char const *>(
          v51,
          "ClientHeartBeat: server returned empty URI, disabling heartbeat",
          63);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          &v47,
          "RENDEZVOUS",
          v51);
        std::string::_Tidy_deallocate(v51);
      }
      v27 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
      if ( *((_QWORD *)&v47 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( !_InterlockedDecrement(v27 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      v43[0] = 1;
      v28 = ((__int64 (__fastcall *)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data2)(v43);
      *(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v22 + 176) = v28;
      std::string::_Tidy_deallocate(&v45);
      std::istringstream::~istringstream(&v58[18]);
      v58[18] = &std::ios_base::`vftable';
      std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v58[18]);
      boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::~basic_ptree<std::string,std::string,std::less<std::string>>(v56);
      std::string::_Tidy_deallocate(v55);
      if ( *((_QWORD *)&v22 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (***((void (__fastcall ****)(_QWORD))&v22 + 1))(*((_QWORD *)&v22 + 1));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 12LL), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 8LL))(*((_QWORD *)&v22 + 1));
        }
      }
      goto LABEL_125;
    }
    *(_QWORD *)&v51[0] = 0;
    v48 = 0;
    std::string::_Construct<1,char const *>(&v47, "reportInTime", 12);
    v49 = 46;
    v29 = &v47;
    if ( *((_QWORD *)&v48 + 1) > 0xFu )
      v29 = (__int128 *)v47;
    v50 = v29;
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::get<std::chrono::duration<__int64,std::ratio<1,1000>>>(
      v56,
      &v41,
      &v47,
      v51);
    std::string::_Tidy_deallocate(&v47);
    if ( *v23 )
    {
      std::string::_Tidy_deallocate(&v45);
      std::istringstream::~istringstream(&v58[18]);
      v58[18] = &std::ios_base::`vftable';
      std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v58[18]);
      boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::~basic_ptree<std::string,std::string,std::less<std::string>>(v56);
      std::string::_Tidy_deallocate(v55);
      if ( *((_QWORD *)&v22 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (***((void (__fastcall ****)(_QWORD))&v22 + 1))(*((_QWORD *)&v22 + 1));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 12LL), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 8LL))(*((_QWORD *)&v22 + 1));
        }
      }
      goto LABEL_125;
    }
    ++v35;
    *(_QWORD *)&v51[0] = v22 + 184;
    if ( Mtx_lock((_Mtx_t)(v22 + 184)) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v22 + 260) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v22 + 260) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    std::string::operator=(v22 + 8, &v45);
    if ( v41 > 0 )
      *(_QWORD *)(v22 + 40) = v41;
    v47 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v47);
    if ( (_QWORD)v47 && *(_BYTE *)(v47 + 128) )
    {
      v31 = *(_QWORD *)(v22 + 40);
      v37 = 0;
      v38 = 0;
      std::string::_Construct<1,char const *>(&v37, "ClientHeartBeat: send #%d succeeded, nextIntervalMs=%lld", 56, v30);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int,__int64>(
        (unsigned int)&v47,
        (unsigned int)"RENDEZVOUS",
        (unsigned int)&v37,
        v35,
        v31);
      std::string::_Tidy_deallocate(&v37);
    }
    v32 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
    if ( *((_QWORD *)&v47 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    Mtx_unlock((_Mtx_t)(v22 + 184));
    std::string::_Tidy_deallocate(&v45);
    std::istringstream::~istringstream(&v58[18]);
    v58[18] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v58[18]);
    boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>::~basic_ptree<std::string,std::string,std::less<std::string>>(v56);
    std::string::_Tidy_deallocate(v55);
    if ( *((_QWORD *)&v22 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (***((void (__fastcall ****)(_QWORD))&v22 + 1))(*((_QWORD *)&v22 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 8LL))(*((_QWORD *)&v22 + 1));
      }
    }
    std::string::_Tidy_deallocate(&v52);
    v8 = v35;
  }
  if ( *((_QWORD *)&v22 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v22 + 1))(*((_QWORD *)&v22 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 8LL))(*((_QWORD *)&v22 + 1));
    }
  }
LABEL_125:
  result = std::string::_Tidy_deallocate(&v52);
  v7 = *v36;
LABEL_126:
  if ( v7 )
  {
    result = (unsigned int)_InterlockedDecrement(v7 + 3);
    if ( !(_DWORD)result )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
  }
  return result;
}

```

## disassembly

```asm
0x180128424  mov     [rsp+arg_8], rbx
0x180128429  mov     [rsp+arg_10], rsi
0x18012842e  push    rdi
0x18012842f  push    r12
0x180128431  push    r13
0x180128433  push    r14
0x180128435  push    r15
0x180128437  mov     eax, 2D0h
0x18012843c  call    _alloca_probe
0x180128441  sub     rsp, rax
0x180128444  movaps  [rsp+2F8h+var_38], xmm6
0x18012844c  mov     rax, cs:__security_cookie
0x180128453  xor     rax, rsp
0x180128456  mov     [rsp+2F8h+var_48], rax
0x18012845e  mov     r12, rcx
0x180128461  mov     [rsp+2F8h+var_2B0], rcx
0x180128466  xorps   xmm1, xmm1
0x180128469  movdqu  [rsp+2F8h+var_2A0], xmm1
0x18012846f  mov     rdx, [rcx+8]
0x180128473  xor     esi, esi
0x180128475  test    rdx, rdx
0x180128478  jz      short loc_18012848D
0x18012847a  mov     eax, [rdx+8]
0x18012847d  jmp     short loc_180128489
0x18012847f  lea     ecx, [rax+1]
0x180128482  lock cmpxchg [rdx+8], ecx
0x180128487  jz      short loc_1801284E4
0x180128489  test    eax, eax
0x18012848b  jnz     short loc_18012847F
0x18012848d  mov     rax, qword ptr [rsp+2F8h+var_2A0]
0x180128492  mov     rbx, qword ptr [rsp+2F8h+var_2A0+8]
0x180128497  test    rax, rax
0x18012849a  jnz     short loc_1801284EF
0x18012849c  or      edi, 0FFFFFFFFh
0x18012849f  test    rbx, rbx
0x1801284a2  jz      short loc_1801284DA
0x1801284a4  mov     eax, edi
0x1801284a6  lock xadd [rbx+8], eax
0x1801284ab  add     eax, edi
0x1801284ad  jnz     short loc_1801284DA
0x1801284af  mov     rax, [rbx]
0x1801284b2  mov     rcx, rbx
0x1801284b5  mov     rax, [rax]
0x1801284b8  call    cs:__guard_dispatch_icall_fptr
0x1801284be  mov     eax, edi
0x1801284c0  lock xadd [rbx+0Ch], eax
0x1801284c5  add     eax, edi
0x1801284c7  jnz     short loc_1801284DA
0x1801284c9  mov     rax, [rbx]
0x1801284cc  mov     rcx, rbx
0x1801284cf  mov     rax, [rax+8]
0x1801284d3  call    cs:__guard_dispatch_icall_fptr
0x1801284d9  nop
0x1801284da  mov     rcx, [r12+8]
0x1801284df  jmp     loc_1801291CD
0x1801284e4  mov     rax, [r12]
0x1801284e8  mov     rbx, [r12+8]
0x1801284ed  jmp     short loc_180128497
0x1801284ef  mov     rax, [rax+0A8h]
0x1801284f6  mov     [rsp+2F8h+var_2A8], rax
0x1801284fb  mov     qword ptr [rsp+2F8h+var_2A0], rsi
0x180128500  mov     qword ptr [rsp+2F8h+var_2A0+8], rsi
0x180128505  or      edi, 0FFFFFFFFh
0x180128508  test    rbx, rbx
0x18012850b  jz      short loc_180128542
0x18012850d  mov     eax, edi
0x18012850f  lock xadd [rbx+8], eax
0x180128514  add     eax, edi
0x180128516  jnz     short loc_180128542
0x180128518  mov     rax, [rbx]
0x18012851b  mov     rcx, rbx
0x18012851e  mov     rax, [rax]
0x180128521  call    cs:__guard_dispatch_icall_fptr
0x180128527  mov     eax, edi
0x180128529  lock xadd [rbx+0Ch], eax
0x18012852e  add     eax, edi
0x180128530  jnz     short loc_180128542
0x180128532  mov     rax, [rbx]
0x180128535  mov     rcx, rbx
0x180128538  mov     rax, [rax+8]
0x18012853c  call    cs:__guard_dispatch_icall_fptr
0x180128542  mov     r13d, esi
0x180128545  mov     [rsp+2F8h+var_2B8], esi
0x180128549  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x180128551  xorps   xmm0, xmm0
0x180128554  movups  [rsp+2F8h+var_1A0], xmm0
0x18012855c  mov     [rsp+2F8h+var_190], rsi
0x180128564  mov     [rsp+2F8h+var_188], 0Fh
0x180128570  mov     byte ptr [rsp+2F8h+var_1A0], sil
0x180128578  xorps   xmm1, xmm1
0x18012857b  movdqu  [rsp+2F8h+var_2C8], xmm1
0x180128581  lea     r8, [r12+8]
0x180128586  mov     [rsp+2F8h+var_290], r8
0x18012858b  mov     rdx, [r8]
0x18012858e  test    rdx, rdx
0x180128591  jz      short loc_1801285AA
0x180128593  mov     eax, [rdx+8]
0x180128596  jmp     short loc_1801285A6
0x180128598  lea     ecx, [rax+1]
0x18012859b  lock cmpxchg [rdx+8], ecx
0x1801285a0  jz      loc_18012869A
0x1801285a6  test    eax, eax
0x1801285a8  jnz     short loc_180128598
0x1801285aa  mov     rcx, qword ptr [rsp+2F8h+var_2C8]
0x1801285af  xorps   xmm0, xmm0
0x1801285b2  test    rcx, rcx
0x1801285b5  jnz     loc_1801286B0
0x1801285bb  movups  [rsp+2F8h+var_220], xmm0
0x1801285c3  lea     rcx, [rsp+2F8h+var_220]
0x1801285cb  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1801285d0  nop
0x1801285d1  mov     rax, qword ptr [rsp+2F8h+var_220]
0x1801285d9  test    rax, rax
0x1801285dc  jz      short loc_180128647
0x1801285de  cmp     [rax+80h], sil
0x1801285e5  jz      short loc_180128647
0x1801285e7  xorps   xmm0, xmm0
0x1801285ea  movups  [rsp+2F8h+var_210], xmm0
0x1801285f2  xorps   xmm1, xmm1
0x1801285f5  movdqu  [rsp+2F8h+var_200], xmm1
0x1801285fe  mov     r8d, 49h ; 'I'
0x180128604  lea     rdx, aClientheartbea_3; "ClientHeartBeat::HeartBeatThread: owner"...
0x18012860b  lea     rcx, [rsp+2F8h+var_210]
0x180128613  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180128618  nop
0x180128619  mov     r9d, r13d
0x18012861c  lea     r8, [rsp+2F8h+var_210]
0x180128624  lea     rdx, aRendezvous_1; "RENDEZVOUS"
0x18012862b  lea     rcx, [rsp+2F8h+var_220]
0x180128633  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@W4ErrorCode@WebsocketException@WebSocket@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@W4ErrorCode@WebsocketException@WebSocket@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode)
0x180128638  nop
0x180128639  lea     rcx, [rsp+2F8h+var_210]
0x180128641  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180128646  nop
0x180128647  mov     rbx, qword ptr [rsp+2F8h+var_220+8]
0x18012864f  test    rbx, rbx
0x180128652  jz      loc_180129177
0x180128658  mov     eax, edi
0x18012865a  lock xadd [rbx+8], eax
0x18012865f  add     eax, edi
0x180128661  jnz     loc_180129177
0x180128667  mov     rax, [rbx]
0x18012866a  mov     rcx, rbx
0x18012866d  mov     rax, [rax]
0x180128670  call    cs:__guard_dispatch_icall_fptr
0x180128676  mov     eax, edi
0x180128678  lock xadd [rbx+0Ch], eax
0x18012867d  add     eax, edi
0x18012867f  jnz     loc_180129177
0x180128685  mov     rax, [rbx]
0x180128688  mov     rcx, rbx
0x18012868b  mov     rax, [rax+8]
0x18012868f  call    cs:__guard_dispatch_icall_fptr
0x180128695  jmp     loc_180129177
0x18012869a  mov     rcx, [r12]
0x18012869e  mov     qword ptr [rsp+2F8h+var_2C8], rcx
0x1801286a3  mov     rax, [r8]
0x1801286a6  mov     qword ptr [rsp+2F8h+var_2C8+8], rax
0x1801286ab  jmp     loc_1801285AF
0x1801286b0  movups  [rsp+2F8h+var_1F0], xmm0
0x1801286b8  lea     r14, [rcx+0B8h]
0x1801286bf  mov     qword ptr [rsp+2F8h+var_1F0], r14
0x1801286c7  mov     byte ptr [rsp+2F8h+var_1F0+8], sil
0x1801286cf  mov     rcx, r14; _Mtx_t
0x1801286d2  call    _Mtx_lock
0x1801286d7  test    eax, eax
0x1801286d9  jnz     loc_18012921C
0x1801286df  cmp     dword ptr [r14+4Ch], 7FFFFFFFh
0x1801286e7  jz      loc_180129227
0x1801286ed  mov     byte ptr [rsp+2F8h+var_1F0+8], 1
0x1801286f5  mov     rdx, qword ptr [rsp+2F8h+var_2C8]
0x1801286fa  add     rdx, 8
0x1801286fe  lea     rcx, [rsp+2F8h+var_1A0]
0x180128706  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x18012870b  mov     rcx, qword ptr [rsp+2F8h+var_2C8]
0x180128710  mov     rax, [rcx+28h]
0x180128714  mov     qword ptr [rsp+2F8h+var_1C0], rax
0x18012871c  cmp     [rsp+2F8h+var_190], rsi
0x180128724  jz      loc_18012909C
0x18012872a  test    rax, rax
0x18012872d  jle     loc_18012909C
0x180128733  lea     rbx, [rcx+108h]
0x18012873a  lea     rdx, [rsp+2F8h+var_1C0]
0x180128742  lea     rcx, [rsp+2F8h+var_250]
0x18012874a  call    ??$_To_absolute_time@_JU?$ratio@$00$0DOI@@std@@@std@@YA?A_PAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@0@@Z
0x18012874f  mov     r15, rax
0x180128752  mov     rcx, qword ptr [rsp+2F8h+var_2C8]
0x180128757  add     rcx, 0B0h
0x18012875e  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180128763  mov     cl, [rax]
0x180128765  nop
0x180128766  test    cl, cl
0x180128768  jnz     short loc_1801287A4
0x18012876a  mov     rcx, qword ptr [rsp+2F8h+var_2C8]
0x18012876f  cmp     [rcx+0B1h], sil
0x180128776  jnz     short loc_1801287A4
0x180128778  mov     r8, r15
0x18012877b  lea     rdx, [rsp+2F8h+var_1F0]
0x180128783  mov     rcx, rbx
0x180128786  call    ??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x18012878b  cmp     eax, 1
0x18012878e  jnz     short loc_180128752
0x180128790  mov     rcx, qword ptr [rsp+2F8h+var_2C8]
0x180128795  add     rcx, 0B0h
0x18012879c  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x1801287a1  mov     cl, [rax]
0x1801287a3  nop
0x1801287a4  mov     rcx, qword ptr [rsp+2F8h+var_2C8]
0x1801287a9  add     rcx, 0B0h
0x1801287b0  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x1801287b5  mov     cl, [rax]
0x1801287b7  nop
0x1801287b8  test    cl, cl
0x1801287ba  jz      loc_180128854
0x1801287c0  xorps   xmm0, xmm0
0x1801287c3  movups  [rsp+2F8h+var_220], xmm0
0x1801287cb  lea     rcx, [rsp+2F8h+var_220]
0x1801287d3  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1801287d8  nop
0x1801287d9  mov     rax, qword ptr [rsp+2F8h+var_220]
0x1801287e1  test    rax, rax
0x1801287e4  jz      short loc_18012884F
0x1801287e6  cmp     [rax+80h], sil
0x1801287ed  jz      short loc_18012884F
0x1801287ef  xorps   xmm0, xmm0
0x1801287f2  movups  [rsp+2F8h+var_210], xmm0
0x1801287fa  xorps   xmm1, xmm1
0x1801287fd  movdqu  [rsp+2F8h+var_200], xmm1
0x180128806  mov     r8d, 4Ch ; 'L'
0x18012880c  lea     rdx, aClientheartbea_15; "ClientHeartBeat::HeartBeatThread: stopp"...
0x180128813  lea     rcx, [rsp+2F8h+var_210]
0x18012881b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180128820  nop
0x180128821  mov     r9d, r13d
0x180128824  lea     r8, [rsp+2F8h+var_210]
0x18012882c  lea     rdx, aRendezvous_1; "RENDEZVOUS"
0x180128833  lea     rcx, [rsp+2F8h+var_220]
0x18012883b  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@W4ErrorCode@WebsocketException@WebSocket@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@W4ErrorCode@WebsocketException@WebSocket@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode)
0x180128840  nop
0x180128841  lea     rcx, [rsp+2F8h+var_210]
0x180128849  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18012884e  nop
0x18012884f  jmp     loc_18012912B
0x180128854  mov     rax, qword ptr [rsp+2F8h+var_2C8]
0x180128859  cmp     [rax+0B1h], sil
0x180128860  jz      loc_180128934
0x180128866  xorps   xmm0, xmm0
0x180128869  movups  [rsp+2F8h+var_1C0], xmm0
0x180128871  lea     rcx, [rsp+2F8h+var_1C0]
0x180128879  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18012887e  nop
0x18012887f  mov     rax, qword ptr [rsp+2F8h+var_1C0]
0x180128887  test    rax, rax
0x18012888a  jz      short loc_1801288F2
0x18012888c  cmp     [rax+80h], sil
0x180128893  jz      short loc_1801288F2
0x180128895  xorps   xmm0, xmm0
0x180128898  movups  [rsp+2F8h+var_210], xmm0
0x1801288a0  xorps   xmm1, xmm1
0x1801288a3  movdqu  [rsp+2F8h+var_200], xmm1
0x1801288ac  mov     r8d, 3Dh ; '='
0x1801288b2  lea     rdx, aClientheartbea_0; "ClientHeartBeat::HeartBeatThread: woke "...
0x1801288b9  lea     rcx, [rsp+2F8h+var_210]
0x1801288c1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801288c6  nop
0x1801288c7  lea     r8, [rsp+2F8h+var_210]
0x1801288cf  lea     rdx, aRendezvous_1; "RENDEZVOUS"
0x1801288d6  lea     rcx, [rsp+2F8h+var_1C0]
0x1801288de  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x1801288e3  nop
0x1801288e4  lea     rcx, [rsp+2F8h+var_210]
0x1801288ec  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801288f1  nop
0x1801288f2  mov     rbx, qword ptr [rsp+2F8h+var_1C0+8]
0x1801288fa  test    rbx, rbx
0x1801288fd  jz      short loc_180128934
0x1801288ff  mov     eax, edi
0x180128901  lock xadd [rbx+8], eax
0x180128906  add     eax, edi
0x180128908  jnz     short loc_180128934
0x18012890a  mov     rax, [rbx]
0x18012890d  mov     rcx, rbx
0x180128910  mov     rax, [rax]
0x180128913  call    cs:__guard_dispatch_icall_fptr
0x180128919  mov     eax, edi
0x18012891b  lock xadd [rbx+0Ch], eax
0x180128920  add     eax, edi
0x180128922  jnz     short loc_180128934
0x180128924  mov     rax, [rbx]
0x180128927  mov     rcx, rbx
0x18012892a  mov     rax, [rax+8]
0x18012892e  call    cs:__guard_dispatch_icall_fptr
0x180128934  mov     rax, qword ptr [rsp+2F8h+var_2C8]
0x180128939  mov     [rax+0B1h], sil
0x180128940  mov     rcx, r14; _Mtx_t
0x180128943  call    _Mtx_unlock
0x180128948  nop
0x180128949  mov     rbx, qword ptr [rsp+2F8h+var_2C8+8]
0x18012894e  test    rbx, rbx
0x180128951  jz      short loc_180128989
  ... truncated ...
```

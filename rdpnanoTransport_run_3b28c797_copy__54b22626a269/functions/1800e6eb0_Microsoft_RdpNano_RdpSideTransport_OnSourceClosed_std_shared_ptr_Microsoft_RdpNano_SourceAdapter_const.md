# Microsoft::RdpNano::RdpSideTransport::OnSourceClosed(std::shared_ptr<Microsoft::RdpNano::SourceAdapter> const &)

- ea: `0x1800e6eb0`
- end: `0x1800e7961`
- name: `?OnSourceClosed@RdpSideTransport@RdpNano@Microsoft@@MEAAXAEBV?$shared_ptr@VSourceAdapter@RdpNano@Microsoft@@@std@@@Z`
- size: `2737`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017338`
- `0x18001902c`
- `0x18001ab4c`
- `0x18001f8d4`
- `0x180028820`
- `0x18002a8ec`
- `0x1800c2d04`
- `0x1800ca9a4`
- `0x1800e16a8`
- `0x1800e4cd4`
- `0x1800e6eb0`
- `0x180115a34`
- `0x1801162c8`
- `0x1801ad754`
- `0x1801b0ab4`
- `0x1801b3360`
- `0x180311d5c`
- `0x180311d64`
- `0x180311dbc`
- `0x180311e54`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1800e7010`: `RdpSideTransport::OnSourceClosed(): rendezvous source closed due to error`
- `0x1800e7260`: `RdpSideTransport::OnSourceClosed(): ice source closed due to error`
- `0x1800e7432`: `RdpSideTransport::OnSourceClosed(): ConnectorToListener source closed due to error`
- `0x1800e7779`: `RdpSideTransport::OnSourceClosed(): all sources are closed due to error, force closing side transport`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall Microsoft::RdpNano::RdpSideTransport::OnSourceClosed(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  char v4; // r14
  char v5; // r15
  __int64 v6; // rdx
  __int64 v7; // rax
  bool v8; // di
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  __int64 v11; // r12
  __int64 v12; // rax
  __int64 v13; // rdi
  volatile signed __int32 *v14; // r12
  __int64 Property; // rbx
  __int64 v16; // rdx
  __int64 v17; // rax
  bool v18; // di
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rbx
  volatile signed __int32 *v24; // rdi
  const void *LastException; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  bool v28; // di
  volatile signed __int32 *v29; // rbx
  volatile signed __int32 *v30; // rbx
  __int64 v31; // r14
  __int64 v32; // rax
  __int64 v33; // rdi
  volatile signed __int32 *v34; // r14
  __int64 v35; // rbx
  __int64 v36; // rbx
  __int64 v37; // rax
  volatile signed __int32 *v38; // rbx
  Microsoft::RdpNano::IceRestartAgent *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  volatile signed __int32 *v42; // rbx
  __int64 v43; // rcx
  __int64 v44; // rax
  volatile signed __int32 *v45; // rbx
  volatile signed __int32 *v46; // rbx
  Microsoft::RdpNano::IceRestartAgent *v47; // rcx
  __int64 v48; // rdx
  Microsoft::RdpNano::RdpSideTransport *v49; // rbx
  unsigned int DctChannelExceptionCode; // edi
  __int64 v51; // rdx
  signed __int32 v52; // eax
  signed __int32 v53; // ett
  __int128 v54; // rcx
  __int128 v55; // [rsp+20h] [rbp-79h] BYREF
  unsigned int v56; // [rsp+30h] [rbp-69h] BYREF
  __int128 v57; // [rsp+38h] [rbp-61h]
  __int128 v58; // [rsp+48h] [rbp-51h] BYREF
  __int128 v59; // [rsp+58h] [rbp-41h]
  __int128 v60; // [rsp+68h] [rbp-31h] BYREF
  __int128 v61; // [rsp+78h] [rbp-21h] BYREF
  __int128 v62; // [rsp+88h] [rbp-11h] BYREF
  __int128 v63; // [rsp+98h] [rbp-1h] BYREF
  __int128 v64; // [rsp+A8h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+B8h] [rbp+1Fh]

  v2 = a2;
  *(_QWORD *)&v57 = a2;
  v4 = 0;
  v56 = 0;
  v63 = 0;
  __ExceptionPtrCreate(&v63);
  v5 = 1;
  v60 = (unsigned __int64)(a1 + 232);
  if ( Mtx_lock((_Mtx_t)(a1 + 232)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 308) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 308) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v60) = 1;
  v6 = *(_QWORD *)(a1 + 104);
  v8 = 0;
  if ( v6 )
  {
    v7 = Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::RdpNano::SourceAdapter>(
           v6 + 112 + *(int *)(*(_QWORD *)(v6 + 112) + 4LL),
           &v55);
    v4 = 1;
    if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                            v2,
                            v7) )
      v8 = 1;
  }
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    v9 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
    if ( *((_QWORD *)&v55 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
  }
  if ( v8 )
  {
    v62 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v62);
    if ( (_QWORD)v62 && *(_BYTE *)(v62 + 128) )
    {
      v64 = 0;
      si128 = 0;
      std::string::_Construct<1,char const *>(
        &v64,
        "RdpSideTransport::OnSourceClosed(): rendezvous source closed due to error",
        73);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v62,
        "RDPNANO",
        &v64);
      std::string::_Tidy_deallocate(&v64);
    }
    v10 = (volatile signed __int32 *)*((_QWORD *)&v62 + 1);
    if ( *((_QWORD *)&v62 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v62 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v61 = 0;
    v11 = *(_QWORD *)(a1 + 104);
    v12 = *(_QWORD *)(v11 + 176);
    if ( v12 )
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
    *(_QWORD *)&v61 = *(_QWORD *)(v11 + 168);
    v13 = v61;
    v14 = *(volatile signed __int32 **)(v11 + 176);
    *((_QWORD *)&v61 + 1) = v14;
    v58 = 0;
    v59 = 0;
    std::string::_Construct<1,char const *>(&v58, "Microsoft::Basix::Dct.LastException", 35);
    Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v13 + 40, &v64, &v58);
    v62 = 0;
    __ExceptionPtrCreate(&v62);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
      *(_QWORD *)(Property + 16),
      &v55,
      &v62);
    v4 |= 0x18u;
    __ExceptionPtrAssign(&v63, &v55);
    __ExceptionPtrDestroy(&v55);
    __ExceptionPtrDestroy(&v62);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v64);
    std::string::_Tidy_deallocate(&v58);
    Microsoft::Basix::Dct::IChannelSourceImplNoProp::CloseAndStopCallbacks(v13);
    if ( v14 )
    {
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    v2 = v57;
  }
  v16 = *(_QWORD *)(a1 + 88);
  v18 = 0;
  if ( v16 )
  {
    v17 = Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::RdpNano::SourceAdapter>(
            v16 + 112 + *(int *)(*(_QWORD *)(v16 + 112) + 4LL),
            &v55);
    v4 |= 2u;
    if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                            v2,
                            v17) )
      v18 = 1;
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    v19 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
    if ( *((_QWORD *)&v55 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
  }
  if ( v18 )
  {
    v62 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v62);
    if ( (_QWORD)v62 && *(_BYTE *)(v62 + 128) )
    {
      v58 = 0;
      v59 = 0;
      std::string::_Construct<1,char const *>(
        &v58,
        "RdpSideTransport::OnSourceClosed(): ice source closed due to error",
        66);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v62,
        "RDPNANO",
        &v58);
      std::string::_Tidy_deallocate(&v58);
    }
    v20 = (volatile signed __int32 *)*((_QWORD *)&v62 + 1);
    if ( *((_QWORD *)&v62 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v62 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    v55 = 0;
    v21 = *(_QWORD *)(a1 + 88);
    v22 = *(_QWORD *)(v21 + 176);
    if ( v22 )
      _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
    v23 = *(_QWORD *)(v21 + 168);
    *(_QWORD *)&v55 = v23;
    v24 = *(volatile signed __int32 **)(v21 + 176);
    *((_QWORD *)&v55 + 1) = v24;
    LastException = (const void *)Microsoft::Basix::Dct::ICESource::GetLastException(v23, &v61);
    __ExceptionPtrAssign(&v63, LastException);
    __ExceptionPtrDestroy(&v61);
    Microsoft::Basix::Dct::IChannelSourceImplNoProp::CloseAndStopCallbacks(v23);
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
  }
  v26 = *(_QWORD *)(a1 + 120);
  v28 = 0;
  if ( v26 )
  {
    v27 = Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::RdpNano::SourceAdapter>(
            v26 + 112 + *(int *)(*(_QWORD *)(v26 + 112) + 4LL),
            &v55);
    v4 |= 4u;
    if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                            v2,
                            v27) )
      v28 = 1;
  }
  if ( (v4 & 4) != 0 )
  {
    v29 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
    if ( *((_QWORD *)&v55 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
  }
  if ( v28 )
  {
    v62 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v62);
    if ( (_QWORD)v62 && *(_BYTE *)(v62 + 128) )
    {
      v58 = 0;
      v59 = 0;
      std::string::_Construct<1,char const *>(
        &v58,
        "RdpSideTransport::OnSourceClosed(): ConnectorToListener source closed due to error",
        82);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v62,
        "RDPNANO",
        &v58);
      std::string::_Tidy_deallocate(&v58);
    }
    v30 = (volatile signed __int32 *)*((_QWORD *)&v62 + 1);
    if ( *((_QWORD *)&v62 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v62 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
        if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
      }
    }
    v55 = 0;
    v31 = *(_QWORD *)(a1 + 120);
    v32 = *(_QWORD *)(v31 + 176);
    if ( v32 )
      _InterlockedIncrement((volatile signed __int32 *)(v32 + 8));
    *(_QWORD *)&v55 = *(_QWORD *)(v31 + 168);
    v33 = v55;
    v34 = *(volatile signed __int32 **)(v31 + 176);
    *((_QWORD *)&v55 + 1) = v34;
    v58 = 0;
    v59 = 0;
    std::string::_Construct<1,char const *>(&v58, "Microsoft::Basix::Dct.LastException", 35);
    v35 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v33 + 40, &v64, &v58);
    v62 = 0;
    __ExceptionPtrCreate(&v62);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
      *(_QWORD *)(v35 + 16),
      &v61,
      &v62);
    __ExceptionPtrAssign(&v63, &v61);
    __ExceptionPtrDestroy(&v61);
    __ExceptionPtrDestroy(&v62);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v64);
    std::string::_Tidy_deallocate(&v58);
    Microsoft::Basix::Dct::IChannelSourceImplNoProp::CloseAndStopCallbacks(v33);
    if ( v34 )
    {
      if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
        if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
      }
    }
  }
  v36 = *(_QWORD *)(a1 + 88);
  if ( v36 )
  {
    v55 = 0;
    v37 = *(_QWORD *)(v36 + 176);
    if ( v37 )
      _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
    *(_QWORD *)&v55 = *(_QWORD *)(v36 + 168);
    v38 = *(volatile signed __int32 **)(v36 + 176);
    *((_QWORD *)&v55 + 1) = v38;
    if ( Microsoft::Basix::Dct::detail::BasicStateManagement::IsClosed((Microsoft::Basix::Dct::detail::BasicStateManagement *)v55) )
    {
      v39 = *(Microsoft::RdpNano::IceRestartAgent **)(a1 + 40);
      if ( v39 )
        Microsoft::RdpNano::IceRestartAgent::OnSourceClosed(v39);
    }
    else
    {
      v5 = 0;
    }
    if ( v38 )
    {
      if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
        if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      }
    }
  }
  v40 = *(_QWORD *)(a1 + 104);
  if ( v40 )
  {
    v41 = *(_QWORD *)(v40 + 176);
    if ( v41 )
      _InterlockedIncrement((volatile signed __int32 *)(v41 + 8));
    v42 = *(volatile signed __int32 **)(v40 + 176);
    v5 &= -Microsoft::Basix::Dct::detail::BasicStateManagement::IsClosed(*(Microsoft::Basix::Dct::detail::BasicStateManagement **)(v40 + 168));
    if ( v42 )
    {
      if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
        if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
      }
    }
  }
  v43 = *(_QWORD *)(a1 + 120);
  if ( v43 )
  {
    v44 = *(_QWORD *)(v43 + 176);
    if ( v44 )
      _InterlockedIncrement((volatile signed __int32 *)(v44 + 8));
    v45 = *(volatile signed __int32 **)(v43 + 176);
    v5 &= -Microsoft::Basix::Dct::detail::BasicStateManagement::IsClosed(*(Microsoft::Basix::Dct::detail::BasicStateManagement **)(v43 + 168));
    if ( v45 )
    {
      if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
  }
  Mtx_unlock((_Mtx_t)(a1 + 232));
  if ( v5 )
  {
    v62 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v62);
    if ( (_QWORD)v62 && *(_BYTE *)(v62 + 128) )
    {
      v58 = 0;
      v59 = 0;
      std::string::_Construct<1,char const *>(
        &v58,
        "RdpSideTransport::OnSourceClosed(): all sources are closed due to error, force closing side transport",
        101);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v62,
        "RDPNANO",
        &v58);
      std::string::_Tidy_deallocate(&v58);
    }
    v46 = (volatile signed __int32 *)*((_QWORD *)&v62 + 1);
    if ( *((_QWORD *)&v62 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v62 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
        if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
      }
    }
    v47 = *(Microsoft::RdpNano::IceRestartAgent **)(a1 + 40);
    if ( v47 )
      Microsoft::RdpNano::IceRestartAgent::Close(v47);
    v64 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v64) = 0;
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v63) )
    {
      v60 = 0;
      __ExceptionPtrCopy(&v60, &v63);
      LOBYTE(v48) = 1;
      v49 = (Microsoft::RdpNano::RdpSideTransport *)(a1 - 24);
      DctChannelExceptionCode = Microsoft::RdpNano::RdpSideTransport::GetDctChannelExceptionCode(
                                  a1 - 24,
                                  v48,
                                  &v60,
                                  &v64);
    }
    else
    {
      DctChannelExceptionCode = 0;
      v49 = (Microsoft::RdpNano::RdpSideTransport *)(a1 - 24);
    }
    v56 = 0;
    Microsoft::RdpNano::RdpSideTransport::CloseTransportStack(v49, &v56);
    v57 = 0;
    v51 = *(_QWORD *)(a1 + 64);
    if ( v51 )
    {
      v52 = *(_DWORD *)(v51 + 8);
      while ( v52 )
      {
        v53 = v52;
        v52 = _InterlockedCompareExchange((volatile signed __int32 *)(v51 + 8), v52 + 1, v52);
        if ( v53 == v52 )
        {
          *(_QWORD *)&v54 = *(_QWORD *)(a1 + 56);
          *(_QWORD *)&v57 = v54;
          *((_QWORD *)&v54 + 1) = *(_QWORD *)(a1 + 64);
          *((_QWORD *)&v57 + 1) = *((_QWORD *)&v54 + 1);
          goto LABEL_116;
        }
      }
    }
    v54 = v57;
LABEL_116:
    if ( (_QWORD)v54 )
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v54 + 8LL))(v54, DctChannelExceptionCode, v56);
    if ( *((_QWORD *)&v54 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v54 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (***((void (__fastcall ****)(_QWORD))&v54 + 1))(*((_QWORD *)&v54 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v54 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 8LL))(*((_QWORD *)&v54 + 1));
      }
    }
    std::string::_Tidy_deallocate(&v64);
  }
  __ExceptionPtrDestroy(&v63);
}

```

## disassembly

```asm
0x1800e6eb0  mov     rax, rsp
0x1800e6eb3  mov     [rax+10h], rbx
0x1800e6eb7  mov     [rax+18h], rsi
0x1800e6ebb  mov     [rax+20h], rdi
0x1800e6ebf  push    rbp
0x1800e6ec0  push    r12
0x1800e6ec2  push    r13
0x1800e6ec4  push    r14
0x1800e6ec6  push    r15
0x1800e6ec8  lea     rbp, [rax-5Fh]
0x1800e6ecc  mov     eax, 0D0h
0x1800e6ed1  call    _alloca_probe
0x1800e6ed6  sub     rsp, rax
0x1800e6ed9  mov     rax, cs:__security_cookie
0x1800e6ee0  xor     rax, rsp
0x1800e6ee3  mov     [rbp+57h+var_28], rax
0x1800e6ee7  mov     r12, rdx
0x1800e6eea  mov     qword ptr [rbp+57h+var_B8], rdx
0x1800e6eee  mov     rsi, rcx
0x1800e6ef1  xor     r14d, r14d
0x1800e6ef4  mov     [rbp+57h+var_C0], r14d
0x1800e6ef8  xorps   xmm1, xmm1
0x1800e6efb  movdqu  [rbp+57h+var_58], xmm1
0x1800e6f00  lea     rcx, [rbp+57h+var_58]; void *
0x1800e6f04  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800e6f09  nop
0x1800e6f0a  mov     r15b, 1
0x1800e6f0d  xorps   xmm0, xmm0
0x1800e6f10  movups  [rbp+57h+var_88], xmm0
0x1800e6f14  lea     r13, [rsi+0E8h]
0x1800e6f1b  mov     qword ptr [rbp+57h+var_88], r13
0x1800e6f1f  mov     byte ptr [rbp+57h+var_88+8], r14b
0x1800e6f23  mov     rcx, r13; _Mtx_t
0x1800e6f26  call    _Mtx_lock
0x1800e6f2b  test    eax, eax
0x1800e6f2d  jnz     loc_1800E7956
0x1800e6f33  cmp     dword ptr [r13+4Ch], 7FFFFFFFh
0x1800e6f3b  jz      loc_1800E7943
0x1800e6f41  mov     byte ptr [rbp+57h+var_88+8], r15b
0x1800e6f45  mov     rdx, [rsi+68h]
0x1800e6f49  test    rdx, rdx
0x1800e6f4c  jz      short loc_1800E6F80
0x1800e6f4e  mov     rax, [rdx+70h]
0x1800e6f52  movsxd  rcx, dword ptr [rax+4]
0x1800e6f56  add     rdx, 70h ; 'p'
0x1800e6f5a  add     rcx, rdx
0x1800e6f5d  lea     rdx, [rbp+57h+var_D0]
0x1800e6f61  call    ??$GetSharedPtr@VSourceAdapter@RdpNano@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$shared_ptr@VSourceAdapter@RdpNano@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::RdpNano::SourceAdapter>(void)
0x1800e6f66  mov     r14d, 1
0x1800e6f6c  mov     rdx, rax
0x1800e6f6f  mov     rcx, r12
0x1800e6f72  call    ??$?8U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@detail@multi_index@boost@@YA_NAEBV?$bidir_node_iterator@U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@012@0@Z; boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &,boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &)
0x1800e6f77  test    al, al
0x1800e6f79  jz      short loc_1800E6F80
0x1800e6f7b  mov     dil, r14b
0x1800e6f7e  jmp     short loc_1800E6F83
0x1800e6f80  xor     dil, dil
0x1800e6f83  test    r14b, 1
0x1800e6f87  jz      short loc_1800E6FCF
0x1800e6f89  and     r14d, 0FFFFFFFEh
0x1800e6f8d  mov     rbx, qword ptr [rbp+57h+var_D0+8]
0x1800e6f91  test    rbx, rbx
0x1800e6f94  jz      short loc_1800E6FCF
0x1800e6f96  or      eax, 0FFFFFFFFh
0x1800e6f99  lock xadd [rbx+8], eax
0x1800e6f9e  cmp     eax, 1
0x1800e6fa1  jnz     short loc_1800E6FCF
0x1800e6fa3  mov     rax, [rbx]
0x1800e6fa6  mov     rcx, rbx
0x1800e6fa9  mov     rax, [rax]
0x1800e6fac  call    cs:__guard_dispatch_icall_fptr
0x1800e6fb2  or      eax, 0FFFFFFFFh
0x1800e6fb5  lock xadd [rbx+0Ch], eax
0x1800e6fba  cmp     eax, 1
0x1800e6fbd  jnz     short loc_1800E6FCF
0x1800e6fbf  mov     rax, [rbx]
0x1800e6fc2  mov     rcx, rbx
0x1800e6fc5  mov     rax, [rax+8]
0x1800e6fc9  call    cs:__guard_dispatch_icall_fptr
0x1800e6fcf  test    dil, dil
0x1800e6fd2  jz      loc_1800E7197
0x1800e6fd8  xorps   xmm0, xmm0
0x1800e6fdb  movups  [rbp+57h+var_68], xmm0
0x1800e6fdf  lea     rcx, [rbp+57h+var_68]
0x1800e6fe3  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800e6fe8  nop
0x1800e6fe9  mov     rax, qword ptr [rbp+57h+var_68]
0x1800e6fed  test    rax, rax
0x1800e6ff0  jz      short loc_1800E7040
0x1800e6ff2  cmp     byte ptr [rax+80h], 0
0x1800e6ff9  jz      short loc_1800E7040
0x1800e6ffb  xorps   xmm0, xmm0
0x1800e6ffe  movups  [rbp+57h+var_48], xmm0
0x1800e7002  xorps   xmm1, xmm1
0x1800e7005  movdqu  [rbp+57h+var_38], xmm1
0x1800e700a  mov     r8d, 49h ; 'I'
0x1800e7010  lea     rdx, aRdpsidetranspo_10; "RdpSideTransport::OnSourceClosed(): ren"...
0x1800e7017  lea     rcx, [rbp+57h+var_48]
0x1800e701b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e7020  nop
0x1800e7021  lea     r8, [rbp+57h+var_48]
0x1800e7025  lea     rdx, aRdpnano; "RDPNANO"
0x1800e702c  lea     rcx, [rbp+57h+var_68]
0x1800e7030  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x1800e7035  nop
0x1800e7036  lea     rcx, [rbp+57h+var_48]
0x1800e703a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e703f  nop
0x1800e7040  mov     rbx, qword ptr [rbp+57h+var_68+8]
0x1800e7044  test    rbx, rbx
0x1800e7047  jz      short loc_1800E7081
0x1800e7049  or      edi, 0FFFFFFFFh
0x1800e704c  mov     eax, edi
0x1800e704e  lock xadd [rbx+8], eax
0x1800e7053  add     eax, edi
0x1800e7055  jnz     short loc_1800E7081
0x1800e7057  mov     rax, [rbx]
0x1800e705a  mov     rcx, rbx
0x1800e705d  mov     rax, [rax]
0x1800e7060  call    cs:__guard_dispatch_icall_fptr
0x1800e7066  mov     eax, edi
0x1800e7068  lock xadd [rbx+0Ch], eax
0x1800e706d  add     eax, edi
0x1800e706f  jnz     short loc_1800E7081
0x1800e7071  mov     rax, [rbx]
0x1800e7074  mov     rcx, rbx
0x1800e7077  mov     rax, [rax+8]
0x1800e707b  call    cs:__guard_dispatch_icall_fptr
0x1800e7081  xorps   xmm0, xmm0
0x1800e7084  movups  [rbp+57h+var_78], xmm0
0x1800e7088  mov     r12, [rsi+68h]
0x1800e708c  mov     rax, [r12+0B0h]
0x1800e7094  test    rax, rax
0x1800e7097  jz      short loc_1800E709D
0x1800e7099  lock inc dword ptr [rax+8]
0x1800e709d  mov     rdi, [r12+0A8h]
0x1800e70a5  mov     qword ptr [rbp+57h+var_78], rdi
0x1800e70a9  mov     r12, [r12+0B0h]
0x1800e70b1  mov     qword ptr [rbp+57h+var_78+8], r12
0x1800e70b5  movups  [rbp+57h+var_A8], xmm0
0x1800e70b9  xorps   xmm1, xmm1
0x1800e70bc  movdqu  [rbp+57h+var_98], xmm1
0x1800e70c1  mov     r8d, 23h ; '#'
0x1800e70c7  lea     rdx, aMicrosoftBasix_104; "Microsoft::Basix::Dct.LastException"
0x1800e70ce  lea     rcx, [rbp+57h+var_A8]
0x1800e70d2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e70d7  nop
0x1800e70d8  lea     r8, [rbp+57h+var_A8]
0x1800e70dc  lea     rdx, [rbp+57h+var_48]
0x1800e70e0  lea     rcx, [rdi+28h]
0x1800e70e4  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x1800e70e9  mov     rbx, rax
0x1800e70ec  xorps   xmm0, xmm0
0x1800e70ef  movdqu  [rbp+57h+var_68], xmm0
0x1800e70f4  lea     rcx, [rbp+57h+var_68]; void *
0x1800e70f8  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800e70fd  nop
0x1800e70fe  lea     r8, [rbp+57h+var_68]
0x1800e7102  lea     rdx, [rbp+57h+var_D0]
0x1800e7106  mov     rcx, [rbx+10h]
0x1800e710a  call    ??$get_value@Vexception_ptr@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AVexception_ptr@std@@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(std::exception_ptr const &)
0x1800e710f  or      r14d, 18h
0x1800e7113  lea     rdx, [rbp+57h+var_D0]; void *
0x1800e7117  lea     rcx, [rbp+57h+var_58]; void *
0x1800e711b  call    ?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800e7120  lea     rcx, [rbp+57h+var_D0]; void *
0x1800e7124  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800e7129  nop
0x1800e712a  lea     rcx, [rbp+57h+var_68]; void *
0x1800e712e  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800e7133  nop
0x1800e7134  lea     rcx, [rbp+57h+var_48]
0x1800e7138  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1800e713d  nop
0x1800e713e  lea     rcx, [rbp+57h+var_A8]
0x1800e7142  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e7147  mov     rcx, rdi
0x1800e714a  call    ?CloseAndStopCallbacks@IChannelSourceImplNoProp@Dct@Basix@Microsoft@@UEAA?AW4State@BasicStateManagement@detail@234@XZ; Microsoft::Basix::Dct::IChannelSourceImplNoProp::CloseAndStopCallbacks(void)
0x1800e714f  nop
0x1800e7150  test    r12, r12
0x1800e7153  jz      short loc_1800E7193
0x1800e7155  or      ebx, 0FFFFFFFFh
0x1800e7158  mov     eax, ebx
0x1800e715a  lock xadd [r12+8], eax
0x1800e7161  add     eax, ebx
0x1800e7163  jnz     short loc_1800E7193
0x1800e7165  mov     rax, [r12]
0x1800e7169  mov     rcx, r12
0x1800e716c  mov     rax, [rax]
0x1800e716f  call    cs:__guard_dispatch_icall_fptr
0x1800e7175  mov     eax, ebx
0x1800e7177  lock xadd [r12+0Ch], eax
0x1800e717e  add     eax, ebx
0x1800e7180  jnz     short loc_1800E7193
0x1800e7182  mov     rax, [r12]
0x1800e7186  mov     rcx, r12
0x1800e7189  mov     rax, [rax+8]
0x1800e718d  call    cs:__guard_dispatch_icall_fptr
0x1800e7193  mov     r12, qword ptr [rbp+57h+var_B8]
0x1800e7197  mov     rdx, [rsi+58h]
0x1800e719b  test    rdx, rdx
0x1800e719e  jz      short loc_1800E71D0
0x1800e71a0  mov     rax, [rdx+70h]
0x1800e71a4  movsxd  rcx, dword ptr [rax+4]
0x1800e71a8  add     rdx, 70h ; 'p'
0x1800e71ac  add     rcx, rdx
0x1800e71af  lea     rdx, [rbp+57h+var_D0]
0x1800e71b3  call    ??$GetSharedPtr@VSourceAdapter@RdpNano@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$shared_ptr@VSourceAdapter@RdpNano@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::RdpNano::SourceAdapter>(void)
0x1800e71b8  or      r14d, 2
0x1800e71bc  mov     rdx, rax
0x1800e71bf  mov     rcx, r12
0x1800e71c2  call    ??$?8U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@detail@multi_index@boost@@YA_NAEBV?$bidir_node_iterator@U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@012@0@Z; boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &,boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &)
0x1800e71c7  test    al, al
0x1800e71c9  jz      short loc_1800E71D0
0x1800e71cb  mov     dil, 1
0x1800e71ce  jmp     short loc_1800E71D3
0x1800e71d0  xor     dil, dil
0x1800e71d3  test    r14b, 2
0x1800e71d7  jz      short loc_1800E721F
0x1800e71d9  and     r14d, 0FFFFFFFDh
0x1800e71dd  mov     rbx, qword ptr [rbp+57h+var_D0+8]
0x1800e71e1  test    rbx, rbx
0x1800e71e4  jz      short loc_1800E721F
0x1800e71e6  or      eax, 0FFFFFFFFh
0x1800e71e9  lock xadd [rbx+8], eax
0x1800e71ee  cmp     eax, 1
0x1800e71f1  jnz     short loc_1800E721F
0x1800e71f3  mov     rax, [rbx]
0x1800e71f6  mov     rcx, rbx
0x1800e71f9  mov     rax, [rax]
0x1800e71fc  call    cs:__guard_dispatch_icall_fptr
0x1800e7202  or      eax, 0FFFFFFFFh
0x1800e7205  lock xadd [rbx+0Ch], eax
0x1800e720a  cmp     eax, 1
0x1800e720d  jnz     short loc_1800E721F
0x1800e720f  mov     rax, [rbx]
0x1800e7212  mov     rcx, rbx
0x1800e7215  mov     rax, [rax+8]
0x1800e7219  call    cs:__guard_dispatch_icall_fptr
0x1800e721f  test    dil, dil
0x1800e7222  jz      loc_1800E7369
0x1800e7228  xorps   xmm0, xmm0
0x1800e722b  movups  [rbp+57h+var_68], xmm0
0x1800e722f  lea     rcx, [rbp+57h+var_68]
0x1800e7233  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800e7238  nop
0x1800e7239  mov     rax, qword ptr [rbp+57h+var_68]
0x1800e723d  test    rax, rax
0x1800e7240  jz      short loc_1800E7290
0x1800e7242  cmp     byte ptr [rax+80h], 0
0x1800e7249  jz      short loc_1800E7290
0x1800e724b  xorps   xmm0, xmm0
0x1800e724e  movups  [rbp+57h+var_A8], xmm0
0x1800e7252  xorps   xmm1, xmm1
0x1800e7255  movdqu  [rbp+57h+var_98], xmm1
0x1800e725a  mov     r8d, 42h ; 'B'
0x1800e7260  lea     rdx, aRdpsidetranspo_13; "RdpSideTransport::OnSourceClosed(): ice"...
0x1800e7267  lea     rcx, [rbp+57h+var_A8]
0x1800e726b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e7270  nop
0x1800e7271  lea     r8, [rbp+57h+var_A8]
0x1800e7275  lea     rdx, aRdpnano; "RDPNANO"
0x1800e727c  lea     rcx, [rbp+57h+var_68]
0x1800e7280  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x1800e7285  nop
0x1800e7286  lea     rcx, [rbp+57h+var_A8]
0x1800e728a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e728f  nop
0x1800e7290  mov     rbx, qword ptr [rbp+57h+var_68+8]
0x1800e7294  test    rbx, rbx
0x1800e7297  jz      short loc_1800E72D1
0x1800e7299  or      edi, 0FFFFFFFFh
0x1800e729c  mov     eax, edi
0x1800e729e  lock xadd [rbx+8], eax
0x1800e72a3  add     eax, edi
0x1800e72a5  jnz     short loc_1800E72D1
0x1800e72a7  mov     rax, [rbx]
0x1800e72aa  mov     rcx, rbx
0x1800e72ad  mov     rax, [rax]
0x1800e72b0  call    cs:__guard_dispatch_icall_fptr
0x1800e72b6  mov     eax, edi
0x1800e72b8  lock xadd [rbx+0Ch], eax
0x1800e72bd  add     eax, edi
0x1800e72bf  jnz     short loc_1800E72D1
0x1800e72c1  mov     rax, [rbx]
0x1800e72c4  mov     rcx, rbx
0x1800e72c7  mov     rax, [rax+8]
0x1800e72cb  call    cs:__guard_dispatch_icall_fptr
0x1800e72d1  xorps   xmm0, xmm0
0x1800e72d4  movups  [rbp+57h+var_D0], xmm0
0x1800e72d8  mov     rdi, [rsi+58h]
0x1800e72dc  mov     rax, [rdi+0B0h]
0x1800e72e3  test    rax, rax
0x1800e72e6  jz      short loc_1800E72EC
0x1800e72e8  lock inc dword ptr [rax+8]
0x1800e72ec  mov     rbx, [rdi+0A8h]
0x1800e72f3  mov     qword ptr [rbp+57h+var_D0], rbx
0x1800e72f7  mov     rdi, [rdi+0B0h]
0x1800e72fe  mov     qword ptr [rbp+57h+var_D0+8], rdi
0x1800e7302  lea     rdx, [rbp+57h+var_78]
  ... truncated ...
```

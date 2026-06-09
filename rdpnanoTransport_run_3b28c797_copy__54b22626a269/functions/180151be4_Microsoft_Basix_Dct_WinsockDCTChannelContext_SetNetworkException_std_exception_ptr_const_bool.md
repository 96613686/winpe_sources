# Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(std::exception_ptr const &,bool)

- ea: `0x180151be4`
- end: `0x1801524ea`
- name: `?SetNetworkException@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAAXAEBVexception_ptr@std@@_N@Z`
- size: `2310`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinsockDCTChannelContext *__hidden this, const struct std::exception_ptr *, bool)`
- caller_count: `6`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801338a0`
- `0x180139a00`
- `0x18013a370`
- `0x18013d340`
- `0x18013dc30`
- `0x180152cc0`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018d1c`
- `0x18001902c`
- `0x18001ab4c`
- `0x18001f8d4`
- `0x180028820`
- `0x18002a8ec`
- `0x180105e60`
- `0x18013ade8`
- `0x18014e730`
- `0x180151be4`
- `0x1802ea40c`
- `0x180311dbc`
- `0x180311e54`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x180151c48`: `Microsoft::Basix::Dct.NetworkExceptionRead`
- `0x180151de6`: `Microsoft::Basix::Dct.NetworkExceptionRead`
- `0x180151f6a`: `Microsoft::Basix::Dct.NetworkExceptionRead`
- `0x180152041`: `Microsoft::Basix::Dct.NetworkExceptionWrite`
- `0x1801521dd`: `Microsoft::Basix::Dct.NetworkExceptionWrite`
- `0x180152356`: `Microsoft::Basix::Dct.NetworkExceptionWrite`
- `0x180151d15`: `WinsockDCTChannelContext::SetNetworkException: clear the read exception already set: %s`
- `0x180151ebc`: `WinsockDCTChannelContext::SetNetworkException: set the read exception for the first time: %s`
- `0x180151ff9`: `WinsockDCTChannelContext::SetNetworkException: read exception already set, ignoring new exception: %s`
- `0x18015210e`: `WinsockDCTChannelContext::SetNetworkException: clear the write exception already set: %s`
- `0x1801522a8`: `WinsockDCTChannelContext::SetNetworkException: set the write exception for the first time: %s`
- `0x1801523ed`: `WinsockDCTChannelContext::SetNetworkException: write exception already set, ignoring new exception: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
void __fastcall Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
        Microsoft::Basix::Dct::WinsockDCTChannelContext *this,
        const struct std::exception_ptr *a2,
        char a3)
{
  char v6; // al
  bool v7; // zf
  void (__fastcall *v8)(char *, __int128 *, __int128 *); // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  volatile signed __int32 *v11; // rdi
  char *v12; // rcx
  char v13; // bl
  volatile signed __int32 *v14; // rdi
  struct _Mtx_internal_imp_t *v15; // rbx
  _DWORD *v16; // rcx
  __int128 *v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  volatile signed __int32 *v22; // rdi
  char v23; // bl
  volatile signed __int32 *v24; // rdi
  _QWORD *v25; // rax
  _QWORD *v26; // rbx
  volatile signed __int32 *v27; // rdi
  __int128 v28; // [rsp+20h] [rbp-99h] BYREF
  __int128 v29; // [rsp+30h] [rbp-89h]
  __int128 v30; // [rsp+40h] [rbp-79h] BYREF
  __int128 v31; // [rsp+50h] [rbp-69h]
  char v32; // [rsp+60h] [rbp-59h]
  __int128 *v33; // [rsp+68h] [rbp-51h]
  __int128 v34; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v35[16]; // [rsp+80h] [rbp-39h] BYREF
  __int128 v36; // [rsp+90h] [rbp-29h] BYREF
  __int128 v37; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v38; // [rsp+B0h] [rbp-9h]
  __int128 v39; // [rsp+C0h] [rbp+7h] BYREF
  __int128 v40; // [rsp+D0h] [rbp+17h]

  v6 = std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(a2);
  v7 = a3 == 0;
  v8 = *(void (__fastcall **)(char *, __int128 *, __int128 *))(*((_QWORD *)this + 5) + 8LL);
  if ( !v7 )
  {
    if ( !v6 )
    {
      v39 = 0;
      v40 = 0;
      std::string::_Construct<1,char const *>(&v39, "Microsoft::Basix::Dct.NetworkExceptionRead", 42);
      v8((char *)this + 40, &v37, &v39);
      std::string::_Tidy_deallocate(&v39);
      if ( (_BYTE)v37 )
      {
        v36 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v36);
        if ( (_QWORD)v36 && *(_BYTE *)(v36 + 128) )
        {
          v34 = 0;
          __ExceptionPtrCreate(&v34);
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
            *((_QWORD *)&v38 + 1),
            v35,
            &v34);
          v9 = (_QWORD *)Microsoft::Basix::Exception::CreateDescription(&v30, v35);
          v10 = v9;
          if ( v9[3] > 0xFu )
            v10 = (_QWORD *)*v9;
          v28 = 0;
          v29 = 0;
          std::string::_Construct<1,char const *>(
            &v28,
            "WinsockDCTChannelContext::SetNetworkException: clear the read exception already set: %s",
            (const char *)0x57);
          ((void (__fastcall *)(__int128 *, const char *, __int128 *, _QWORD *))Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,char const *>)(
            &v36,
            "NANO_DCT",
            &v28,
            v10);
          std::string::_Tidy_deallocate(&v28);
          std::string::_Tidy_deallocate(&v30);
          __ExceptionPtrDestroy(v35);
          __ExceptionPtrDestroy(&v34);
        }
        v11 = (volatile signed __int32 *)*((_QWORD *)&v36 + 1);
        if ( *((_QWORD *)&v36 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v36 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
      }
      *(_QWORD *)&v36 = (char *)this + 976;
      if ( Mtx_lock((Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 976)) )
        std::_Throw_Cpp_error(5);
      if ( *((_DWORD *)this + 263) == 0x7FFFFFFF )
      {
        *((_DWORD *)this + 263) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      v28 = 0;
      v29 = 0;
      std::string::_Construct<1,char const *>(&v28, "Microsoft::Basix::Dct.NetworkExceptionRead", 42);
      _erase___ordered_index_impl_U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__multi_index_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std__U__nth_layer__01U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__detail_23_U__vector1_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___mpl_3_Uordered_non_unique_tag_723_Unull_augment_policy_723__detail_multi_index_boost__QEAA_KAEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___Z(
        *((_QWORD *)this + 121) + 17LL,
        &v28);
      std::string::_Tidy_deallocate(&v28);
      Mtx_unlock((Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 976));
      if ( (_BYTE)v37 )
      {
        v12 = (char *)&v37 + 8;
LABEL_53:
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v12);
        return;
      }
      return;
    }
    v37 = 0;
    v38 = 0;
    std::string::_Construct<1,char const *>(&v37, "Microsoft::Basix::Dct.NetworkExceptionRead", 42);
    v13 = *(_BYTE *)((__int64 (__fastcall *)(char *, __int128 *, __int128 *))v8)((char *)this + 40, &v28, &v37);
    if ( (_BYTE)v28 )
    {
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>((char *)&v28 + 8);
      LOBYTE(v28) = 0;
    }
    std::string::_Tidy_deallocate(&v37);
    v36 = 0;
    if ( !v13 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v36);
      if ( (_QWORD)v36 && *(_BYTE *)(v36 + 128) )
      {
        v37 = 0;
        v38 = 0;
        std::string::_Construct<1,char const *>(
          &v37,
          "WinsockDCTChannelContext::SetNetworkException: set the read exception for the first time: %s",
          (const char *)0x5C);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          &v36,
          "NANO_DCT",
          &v37);
        std::string::_Tidy_deallocate(&v37);
      }
      v14 = (volatile signed __int32 *)*((_QWORD *)&v36 + 1);
      if ( *((_QWORD *)&v36 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v36 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      v15 = (Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 976);
      *(_QWORD *)&v36 = (char *)this + 976;
      if ( !Mtx_lock((Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 976)) )
      {
        v16 = (_DWORD *)((char *)this + 1052);
        if ( *((_DWORD *)this + 263) != 0x7FFFFFFF )
        {
          v30 = 0;
          v31 = 0;
          std::string::_Construct<1,char const *>(&v30, "Microsoft::Basix::Dct.NetworkExceptionRead", 42);
          v32 = 46;
          v17 = &v30;
          if ( *((_QWORD *)&v31 + 1) > 0xFu )
            v17 = (__int128 *)v30;
LABEL_68:
          v33 = v17;
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::exception_ptr>(
            (char *)this + 960,
            &v30,
            a2);
          std::string::_Tidy_deallocate(&v30);
          Mtx_unlock(v15);
          return;
        }
        goto LABEL_79;
      }
      goto LABEL_84;
    }
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v36);
    if ( (_QWORD)v36 && *(_BYTE *)(v36 + 128) )
    {
      v18 = (_QWORD *)Microsoft::Basix::Exception::CreateDescription(&v30, a2);
      v19 = v18;
      if ( v18[3] > 0xFu )
        v19 = (_QWORD *)*v18;
      v37 = 0;
      v38 = 0;
      std::string::_Construct<1,char const *>(
        &v37,
        "WinsockDCTChannelContext::SetNetworkException: read exception already set, ignoring new exception: %s",
        (const char *)0x65);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,char const *>(
        &v36,
        "NANO_DCT",
        &v37,
        v19,
        v28);
      std::string::_Tidy_deallocate(&v37);
      std::string::_Tidy_deallocate(&v30);
    }
    goto LABEL_74;
  }
  v37 = 0;
  v38 = 0;
  if ( v6 )
  {
    std::string::_Construct<1,char const *>(&v37, "Microsoft::Basix::Dct.NetworkExceptionWrite", 43);
    v23 = *(_BYTE *)((__int64 (__fastcall *)(char *, __int128 *, __int128 *))v8)((char *)this + 40, &v28, &v37);
    if ( (_BYTE)v28 )
    {
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>((char *)&v28 + 8);
      LOBYTE(v28) = 0;
    }
    std::string::_Tidy_deallocate(&v37);
    v36 = 0;
    if ( !v23 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v36);
      if ( (_QWORD)v36 && *(_BYTE *)(v36 + 128) )
      {
        v37 = 0;
        v38 = 0;
        std::string::_Construct<1,char const *>(
          &v37,
          "WinsockDCTChannelContext::SetNetworkException: set the write exception for the first time: %s",
          (const char *)0x5D);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          &v36,
          "NANO_DCT",
          &v37);
        std::string::_Tidy_deallocate(&v37);
      }
      v24 = (volatile signed __int32 *)*((_QWORD *)&v36 + 1);
      if ( *((_QWORD *)&v36 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v36 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
          if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        }
      }
      v15 = (Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 976);
      *(_QWORD *)&v36 = (char *)this + 976;
      if ( !Mtx_lock((Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 976)) )
      {
        v16 = (_DWORD *)((char *)this + 1052);
        if ( *((_DWORD *)this + 263) != 0x7FFFFFFF )
        {
          v30 = 0;
          v31 = 0;
          std::string::_Construct<1,char const *>(&v30, "Microsoft::Basix::Dct.NetworkExceptionWrite", 43);
          v32 = 46;
          v17 = &v30;
          if ( *((_QWORD *)&v31 + 1) > 0xFu )
            v17 = (__int128 *)v30;
          goto LABEL_68;
        }
LABEL_79:
        *v16 = 2147483646;
        std::_Throw_Cpp_error(6);
      }
LABEL_84:
      std::_Throw_Cpp_error(5);
    }
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v36);
    if ( (_QWORD)v36 && *(_BYTE *)(v36 + 128) )
    {
      v25 = (_QWORD *)Microsoft::Basix::Exception::CreateDescription(&v30, a2);
      v26 = v25;
      if ( v25[3] > 0xFu )
        v26 = (_QWORD *)*v25;
      v37 = 0;
      v38 = 0;
      std::string::_Construct<1,char const *>(
        &v37,
        "WinsockDCTChannelContext::SetNetworkException: write exception already set, ignoring new exception: %s",
        (const char *)0x66);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,char const *>(
        &v36,
        "NANO_DCT",
        &v37,
        v26,
        v28);
      std::string::_Tidy_deallocate(&v37);
      std::string::_Tidy_deallocate(&v30);
    }
LABEL_74:
    v27 = (volatile signed __int32 *)*((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v36 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
        if ( !_InterlockedDecrement(v27 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
    return;
  }
  std::string::_Construct<1,char const *>(&v37, "Microsoft::Basix::Dct.NetworkExceptionWrite", 43);
  v8((char *)this + 40, &v39, &v37);
  std::string::_Tidy_deallocate(&v37);
  if ( (_BYTE)v39 )
  {
    v36 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v36);
    if ( (_QWORD)v36 && *(_BYTE *)(v36 + 128) )
    {
      v34 = 0;
      __ExceptionPtrCreate(&v34);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
        *((_QWORD *)&v40 + 1),
        v35,
        &v34);
      v20 = (_QWORD *)Microsoft::Basix::Exception::CreateDescription(&v30, v35);
      v21 = v20;
      if ( v20[3] > 0xFu )
        v21 = (_QWORD *)*v20;
      v28 = 0;
      v29 = 0;
      std::string::_Construct<1,char const *>(
        &v28,
        "WinsockDCTChannelContext::SetNetworkException: clear the write exception already set: %s",
        (const char *)0x58);
      ((void (__fastcall *)(__int128 *, const char *, __int128 *, _QWORD *))Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,char const *>)(
        &v36,
        "NANO_DCT",
        &v28,
        v21);
      std::string::_Tidy_deallocate(&v28);
      std::string::_Tidy_deallocate(&v30);
      __ExceptionPtrDestroy(v35);
      __ExceptionPtrDestroy(&v34);
    }
    v22 = (volatile signed __int32 *)*((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v36 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      }
    }
  }
  *(_QWORD *)&v36 = (char *)this + 976;
  if ( Mtx_lock((Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 976)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 263) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 263) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v37 = 0;
  v38 = 0;
  std::string::_Construct<1,char const *>(&v37, "Microsoft::Basix::Dct.NetworkExceptionWrite", 43);
  _erase___ordered_index_impl_U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__multi_index_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std__U__nth_layer__01U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__detail_23_U__vector1_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___mpl_3_Uordered_non_unique_tag_723_Unull_augment_policy_723__detail_multi_index_boost__QEAA_KAEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___Z(
    *((_QWORD *)this + 121) + 17LL,
    &v37);
  std::string::_Tidy_deallocate(&v37);
  Mtx_unlock((Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 976));
  if ( (_BYTE)v39 )
  {
    v12 = (char *)&v39 + 8;
    goto LABEL_53;
  }
}

```

## disassembly

```asm
0x180151be4  mov     [rsp-8+arg_10], rbx
0x180151be9  mov     [rsp-8+arg_18], rsi
0x180151bee  push    rbp
0x180151bef  push    rdi
0x180151bf0  push    r12
0x180151bf2  push    r14
0x180151bf4  push    r15
0x180151bf6  lea     rbp, [rsp-37h]
0x180151bfb  mov     eax, 0F0h
0x180151c00  call    _alloca_probe
0x180151c05  sub     rsp, rax
0x180151c08  mov     rax, cs:__security_cookie
0x180151c0f  xor     rax, rsp
0x180151c12  mov     [rbp+57h+var_30], rax
0x180151c16  mov     bl, r8b
0x180151c19  mov     r14, rdx
0x180151c1c  mov     rsi, rcx
0x180151c1f  xor     r12d, r12d
0x180151c22  mov     rcx, rdx
0x180151c25  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x180151c2a  lea     rdi, [rsi+28h]
0x180151c2e  mov     rcx, [rdi]
0x180151c31  test    bl, bl
0x180151c33  mov     rbx, [rcx+8]
0x180151c37  xorps   xmm0, xmm0
0x180151c3a  xorps   xmm1, xmm1
0x180151c3d  jz      loc_18015203B
0x180151c43  lea     r15d, [r12+2Ah]
0x180151c48  lea     rdx, aMicrosoftBasix_110; "Microsoft::Basix::Dct.NetworkExceptionR"...
0x180151c4f  mov     r8d, r15d
0x180151c52  test    al, al
0x180151c54  jnz     loc_180151E33
0x180151c5a  movups  [rbp+57h+var_50], xmm0
0x180151c5e  movdqu  [rbp+57h+var_40], xmm1
0x180151c63  lea     rcx, [rbp+57h+var_50]
0x180151c67  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180151c6c  nop
0x180151c6d  lea     r8, [rbp+57h+var_50]
0x180151c71  lea     rdx, [rbp+57h+var_70]
0x180151c75  mov     rcx, rdi
0x180151c78  mov     rax, rbx
0x180151c7b  call    cs:__guard_dispatch_icall_fptr
0x180151c81  nop
0x180151c82  lea     rcx, [rbp+57h+var_50]
0x180151c86  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180151c8b  cmp     byte ptr [rbp+57h+var_70], r12b
0x180151c8f  jz      loc_180151DAA
0x180151c95  xorps   xmm0, xmm0
0x180151c98  movups  [rbp+57h+var_80], xmm0
0x180151c9c  lea     rcx, [rbp+57h+var_80]
0x180151ca0  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x180151ca5  nop
0x180151ca6  mov     rax, qword ptr [rbp+57h+var_80]
0x180151caa  test    rax, rax
0x180151cad  jz      loc_180151D69
0x180151cb3  cmp     [rax+80h], r12b
0x180151cba  jz      loc_180151D69
0x180151cc0  xorps   xmm0, xmm0
0x180151cc3  movdqu  [rbp+57h+var_A0], xmm0
0x180151cc8  lea     rcx, [rbp+57h+var_A0]; void *
0x180151ccc  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180151cd1  nop
0x180151cd2  lea     r8, [rbp+57h+var_A0]
0x180151cd6  lea     rdx, [rbp+57h+var_90]
0x180151cda  mov     rcx, [rbp+57h+var_58]
0x180151cde  call    ??$get_value@Vexception_ptr@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AVexception_ptr@std@@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(std::exception_ptr const &)
0x180151ce3  nop
0x180151ce4  lea     rdx, [rbp+57h+var_90]
0x180151ce8  lea     rcx, [rbp+57h+var_D0]
0x180151cec  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception_ptr@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception_ptr const &)
0x180151cf1  mov     rbx, rax
0x180151cf4  cmp     qword ptr [rax+18h], 0Fh
0x180151cf9  jbe     short loc_180151CFE
0x180151cfb  mov     rbx, [rax]
0x180151cfe  xorps   xmm0, xmm0
0x180151d01  movups  [rsp+110h+var_F0], xmm0
0x180151d06  xorps   xmm1, xmm1
0x180151d09  movdqu  [rsp+110h+var_E0], xmm1
0x180151d0f  mov     r8d, 57h ; 'W'
0x180151d15  lea     rdx, aWinsockdctchan_3; "WinsockDCTChannelContext::SetNetworkExc"...
0x180151d1c  lea     rcx, [rsp+110h+var_F0]
0x180151d21  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180151d26  nop
0x180151d27  mov     r9, rbx
0x180151d2a  lea     r8, [rsp+110h+var_F0]
0x180151d2f  lea     rdx, aNanoDct; "NANO_DCT"
0x180151d36  lea     rcx, [rbp+57h+var_80]
0x180151d3a  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,char const *)
0x180151d3f  nop
0x180151d40  lea     rcx, [rsp+110h+var_F0]
0x180151d45  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180151d4a  nop
0x180151d4b  lea     rcx, [rbp+57h+var_D0]
0x180151d4f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180151d54  nop
0x180151d55  lea     rcx, [rbp+57h+var_90]; void *
0x180151d59  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180151d5e  nop
0x180151d5f  lea     rcx, [rbp+57h+var_A0]; void *
0x180151d63  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180151d68  nop
0x180151d69  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x180151d6d  test    rdi, rdi
0x180151d70  jz      short loc_180151DAA
0x180151d72  or      ebx, 0FFFFFFFFh
0x180151d75  mov     eax, ebx
0x180151d77  lock xadd [rdi+8], eax
0x180151d7c  add     eax, ebx
0x180151d7e  jnz     short loc_180151DAA
0x180151d80  mov     rax, [rdi]
0x180151d83  mov     rcx, rdi
0x180151d86  mov     rax, [rax]
0x180151d89  call    cs:__guard_dispatch_icall_fptr
0x180151d8f  mov     eax, ebx
0x180151d91  lock xadd [rdi+0Ch], eax
0x180151d96  add     eax, ebx
0x180151d98  jnz     short loc_180151DAA
0x180151d9a  mov     rax, [rdi]
0x180151d9d  mov     rcx, rdi
0x180151da0  mov     rax, [rax+8]
0x180151da4  call    cs:__guard_dispatch_icall_fptr
0x180151daa  lea     rbx, [rsi+3D0h]
0x180151db1  mov     qword ptr [rbp+57h+var_80], rbx
0x180151db5  mov     rcx, rbx; _Mtx_t
0x180151db8  call    _Mtx_lock
0x180151dbd  test    eax, eax
0x180151dbf  jnz     loc_1801524A5
0x180151dc5  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180151dcc  jz      loc_1801524B0
0x180151dd2  xorps   xmm0, xmm0
0x180151dd5  movups  [rsp+110h+var_F0], xmm0
0x180151dda  xorps   xmm1, xmm1
0x180151ddd  movdqu  [rsp+110h+var_E0], xmm1
0x180151de3  mov     r8, r15
0x180151de6  lea     rdx, aMicrosoftBasix_110; "Microsoft::Basix::Dct.NetworkExceptionR"...
0x180151ded  lea     rcx, [rsp+110h+var_F0]
0x180151df2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180151df7  mov     rcx, [rsi+3C8h]
0x180151dfe  add     rcx, 11h
0x180151e02  lea     rdx, [rsp+110h+var_F0]
0x180151e07  call    ?erase@?$ordered_index_impl@U?$member@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@$0A@@multi_index@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@U?$nth_layer@$01U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@U?$indexed_by@U?$sequenced@U?$tag@Una@mpl@boost@@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@U123@@multi_index@boost@@@multi_index@boost@@U?$ordered_non_unique@U?$tag@Uby_name@subs@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@Una@mpl@5@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@U675@@multi_index@boost@@U?$member@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@$0A@@23@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@23@Una@mpl@3@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@U563@@multi_index@boost@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@detail@23@U?$vector1@Uby_name@subs@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@mpl@3@Uordered_non_unique_tag@723@Unull_augment_policy@723@@detail@multi_index@boost@@QEAA_KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z
0x180151e0c  lea     rcx, [rsp+110h+var_F0]
0x180151e11  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180151e16  nop
0x180151e17  mov     rcx, rbx; _Mtx_t
0x180151e1a  call    _Mtx_unlock
0x180151e1f  nop
0x180151e20  cmp     byte ptr [rbp+57h+var_70], r12b
0x180151e24  jz      loc_18015246B
0x180151e2a  lea     rcx, [rbp+57h+var_70+8]
0x180151e2e  jmp     loc_180152222
0x180151e33  movups  [rbp+57h+var_70], xmm0
0x180151e37  movdqu  xmmword ptr [rbp-9], xmm1
0x180151e3c  lea     rcx, [rbp+57h+var_70]
0x180151e40  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180151e45  nop
0x180151e46  lea     r8, [rbp+57h+var_70]
0x180151e4a  lea     rdx, [rsp+110h+var_F0]
0x180151e4f  mov     rcx, rdi
0x180151e52  mov     rax, rbx
0x180151e55  call    cs:__guard_dispatch_icall_fptr
0x180151e5b  mov     bl, [rax]
0x180151e5d  cmp     byte ptr [rsp+110h+var_F0], r12b
0x180151e62  jz      short loc_180151E73
0x180151e64  lea     rcx, [rsp+110h+var_F0+8]
0x180151e69  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180151e6e  mov     byte ptr [rsp+110h+var_F0], r12b
0x180151e73  lea     rcx, [rbp+57h+var_70]
0x180151e77  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180151e7c  xorps   xmm0, xmm0
0x180151e7f  lea     rcx, [rbp+57h+var_80]
0x180151e83  movups  [rbp+57h+var_80], xmm0
0x180151e87  test    bl, bl
0x180151e89  jnz     loc_180151FB3
0x180151e8f  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180151e94  nop
0x180151e95  mov     rax, qword ptr [rbp+57h+var_80]
0x180151e99  test    rax, rax
0x180151e9c  jz      short loc_180151EEC
0x180151e9e  cmp     [rax+80h], r12b
0x180151ea5  jz      short loc_180151EEC
0x180151ea7  xorps   xmm0, xmm0
0x180151eaa  movups  [rbp+57h+var_70], xmm0
0x180151eae  xorps   xmm1, xmm1
0x180151eb1  movdqu  xmmword ptr [rbp-9], xmm1
0x180151eb6  mov     r8d, 5Ch ; '\'
0x180151ebc  lea     rdx, aWinsockdctchan_2; "WinsockDCTChannelContext::SetNetworkExc"...
0x180151ec3  lea     rcx, [rbp+57h+var_70]
0x180151ec7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180151ecc  nop
0x180151ecd  lea     r8, [rbp+57h+var_70]
0x180151ed1  lea     rdx, aNanoDct; "NANO_DCT"
0x180151ed8  lea     rcx, [rbp+57h+var_80]
0x180151edc  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x180151ee1  nop
0x180151ee2  lea     rcx, [rbp+57h+var_70]
0x180151ee6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180151eeb  nop
0x180151eec  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x180151ef0  test    rdi, rdi
0x180151ef3  jz      short loc_180151F2D
0x180151ef5  or      ebx, 0FFFFFFFFh
0x180151ef8  mov     eax, ebx
0x180151efa  lock xadd [rdi+8], eax
0x180151eff  add     eax, ebx
0x180151f01  jnz     short loc_180151F2D
0x180151f03  mov     rax, [rdi]
0x180151f06  mov     rcx, rdi
0x180151f09  mov     rax, [rax]
0x180151f0c  call    cs:__guard_dispatch_icall_fptr
0x180151f12  mov     eax, ebx
0x180151f14  lock xadd [rdi+0Ch], eax
0x180151f19  add     eax, ebx
0x180151f1b  jnz     short loc_180151F2D
0x180151f1d  mov     rax, [rdi]
0x180151f20  mov     rcx, rdi
0x180151f23  mov     rax, [rax+8]
0x180151f27  call    cs:__guard_dispatch_icall_fptr
0x180151f2d  lea     rbx, [rsi+3D0h]
0x180151f34  mov     qword ptr [rbp+57h+var_80], rbx
0x180151f38  mov     rcx, rbx; _Mtx_t
0x180151f3b  call    _Mtx_lock
0x180151f40  test    eax, eax
0x180151f42  jnz     loc_1801524DF
0x180151f48  lea     rcx, [rbx+4Ch]
0x180151f4c  cmp     dword ptr [rcx], 7FFFFFFFh
0x180151f52  jz      loc_180152493
0x180151f58  xorps   xmm0, xmm0
0x180151f5b  movups  [rbp+57h+var_D0], xmm0
0x180151f5f  xorps   xmm1, xmm1
0x180151f62  movdqu  [rbp+57h+var_C0], xmm1
0x180151f67  mov     r8, r15
0x180151f6a  lea     rdx, aMicrosoftBasix_110; "Microsoft::Basix::Dct.NetworkExceptionR"...
0x180151f71  lea     rcx, [rbp+57h+var_D0]
0x180151f75  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180151f7a  mov     [rbp+57h+var_B0], 2Eh ; '.'
0x180151f7e  lea     rax, [rbp+57h+var_D0]
0x180151f82  cmp     qword ptr [rbp+57h+var_C0+8], 0Fh
0x180151f87  cmova   rax, qword ptr [rbp+57h+var_D0]
0x180151f8c  mov     [rbp+57h+var_A8], rax
0x180151f90  lea     rcx, [rsi+3C0h]
0x180151f97  mov     r8, r14
0x180151f9a  lea     rdx, [rbp+57h+var_D0]
0x180151f9e  call    ??$put@Vexception_ptr@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBVexception_ptr@std@@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::exception_ptr>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::exception_ptr const &)
0x180151fa3  nop
0x180151fa4  lea     rcx, [rbp+57h+var_D0]
0x180151fa8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180151fad  nop
0x180151fae  jmp     loc_18015239A
0x180151fb3  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x180151fb8  nop
0x180151fb9  mov     rax, qword ptr [rbp+57h+var_80]
0x180151fbd  test    rax, rax
0x180151fc0  jz      short loc_180152036
0x180151fc2  cmp     [rax+80h], r12b
0x180151fc9  jz      short loc_180152036
0x180151fcb  mov     rdx, r14
0x180151fce  lea     rcx, [rbp+57h+var_D0]
0x180151fd2  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception_ptr@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception_ptr const &)
0x180151fd7  mov     rbx, rax
0x180151fda  cmp     qword ptr [rax+18h], 0Fh
0x180151fdf  jbe     short loc_180151FE4
0x180151fe1  mov     rbx, [rax]
0x180151fe4  xorps   xmm0, xmm0
0x180151fe7  movups  [rbp+57h+var_70], xmm0
0x180151feb  xorps   xmm1, xmm1
0x180151fee  movdqu  xmmword ptr [rbp-9], xmm1
0x180151ff3  mov     r8d, 65h ; 'e'
0x180151ff9  lea     rdx, aWinsockdctchan_9; "WinsockDCTChannelContext::SetNetworkExc"...
0x180152000  lea     rcx, [rbp+57h+var_70]
0x180152004  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180152009  nop
0x18015200a  mov     r9, rbx
0x18015200d  lea     r8, [rbp+57h+var_70]
0x180152011  lea     rdx, aNanoDct; "NANO_DCT"
0x180152018  lea     rcx, [rbp+57h+var_80]
0x18015201c  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,char const *)
0x180152021  nop
0x180152022  lea     rcx, [rbp+57h+var_70]
0x180152026  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18015202b  nop
0x18015202c  lea     rcx, [rbp+57h+var_D0]
0x180152030  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180152035  nop
0x180152036  jmp     loc_18015242A
0x18015203b  mov     r15d, 2Bh ; '+'
0x180152041  lea     rdx, aMicrosoftBasix_360; "Microsoft::Basix::Dct.NetworkExceptionW"...
0x180152048  lea     rcx, [rbp+57h+var_70]
0x18015204c  movups  [rbp+57h+var_70], xmm0
0x180152050  movdqu  xmmword ptr [rbp-9], xmm1
0x180152055  mov     r8d, r15d
0x180152058  test    al, al
0x18015205a  jnz     loc_18015222C
0x180152060  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180152065  nop
0x180152066  lea     r8, [rbp+57h+var_70]
0x18015206a  lea     rdx, [rbp+57h+var_50]
0x18015206e  mov     rcx, rdi
0x180152071  mov     rax, rbx
0x180152074  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```

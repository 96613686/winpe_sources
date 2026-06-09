# win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::DoDerecurse(void)

- ea: `0x18000f9c0`
- end: `0x18000fd7e`
- name: `?DoDerecurse@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@AEAAXXZ`
- size: `958`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001073c`

## callees

- `0x1800034d8`
- `0x18000531c`
- `0x18000df98`
- `0x18000f714`
- `0x18000f9a0`
- `0x18000f9c0`
- `0x1800117a8`
- `0x180011b14`
- `0x18003b5a4`
- `0x18003bf38`
- `0x180085e24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbdd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb10`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::DoDerecurse(
        __int64 a1)
{
  __int64 v2; // r13
  __int64 v3; // rsi
  __int64 v4; // r15
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  __int64 *v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // r12
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  _QWORD *v14; // rdi
  bool v15; // dl
  win_dox *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  char v19; // di
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 result; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  __int128 v28; // [rsp+28h] [rbp-58h] BYREF
  __int128 v29; // [rsp+38h] [rbp-48h] BYREF
  __int128 v30; // [rsp+48h] [rbp-38h] BYREF
  char v31[16]; // [rsp+58h] [rbp-28h] BYREF
  char v32[8]; // [rsp+68h] [rbp-18h] BYREF
  win_scope::counted_strong_weak_base *v33[2]; // [rsp+70h] [rbp-10h] BYREF

  v2 = a1 + 8;
  v3 = a1 + 8;
  do
  {
    while ( 1 )
    {
      if ( *(_QWORD *)(a1 + 392) )
      {
        v4 = v2;
        v5 = *(_QWORD *)(a1 + 384);
        v6 = *(_QWORD *)(a1 + 376);
        v29 = 0;
        v7 = v5 - v6;
        if ( v6 > v5 )
          v7 = v5;
        v8 = *(__int64 **)(*(_QWORD *)(a1 + 368) + 8 * v7);
        v9 = *v8;
        if ( *v8 )
        {
          v10 = v8[1];
          if ( _InterlockedIncrement((volatile signed __int32 *)(v9 + 8)) == 1 )
            _InterlockedIncrement((volatile signed __int32 *)(v9 + 12));
          *(_QWORD *)&v29 = v9;
          *((_QWORD *)&v29 + 1) = v10;
        }
        else
        {
          v10 = *((_QWORD *)&v29 + 1);
          v9 = v29;
        }
        v11 = *(_QWORD *)(a1 + 392);
        if ( v11 )
        {
          v12 = *(_QWORD *)(a1 + 384);
          v13 = *(_QWORD *)(a1 + 368);
          v14 = *(_QWORD **)(v13 + 8 * v12);
          if ( *v14 && v14[1] )
          {
            win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(*(_QWORD *)(v13 + 8 * v12));
            *v14 = 0;
            v14[1] = 0;
            v11 = *(_QWORD *)(a1 + 392);
          }
          if ( *(_QWORD *)(a1 + 376) <= ++*(_QWORD *)(a1 + 384) )
            *(_QWORD *)(a1 + 384) = 0;
          *(_QWORD *)(a1 + 392) = v11 - 1;
          if ( v11 == 1 )
            *(_QWORD *)(a1 + 384) = 0;
        }
        v28 = 0;
        if ( v9 )
        {
          if ( _InterlockedIncrement((volatile signed __int32 *)(v9 + 8)) == 1 )
            _InterlockedIncrement((volatile signed __int32 *)(v9 + 12));
          *(_QWORD *)&v28 = v9;
          *((_QWORD *)&v28 + 1) = v10;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 296));
        v16 = (win_dox *)*(unsigned int *)(v2 + 340);
        *(_DWORD *)(v2 + 340) = (_DWORD)v16 + 1;
        if ( !(_DWORD)v16 )
          *(_DWORD *)(v2 + 336) = GetCurrentThreadId();
        LOBYTE(v16) = *(_BYTE *)(v2 + 288);
        win_dox::ThrowIfFailed(v16, v15);
        v30 = 0;
        v17 = v28;
        if ( (_QWORD)v28 )
        {
          v18 = *((_QWORD *)&v28 + 1);
          if ( _InterlockedIncrement((volatile signed __int32 *)(v28 + 8)) == 1 )
            _InterlockedIncrement((volatile signed __int32 *)(v17 + 12));
          *(_QWORD *)&v30 = v17;
          *((_QWORD *)&v30 + 1) = v18;
        }
        v19 = win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>::ProcessMessage(
                v2,
                &v30);
        if ( !v19 )
        {
          if ( v2 )
            v20 = v2 + 56;
          else
            v20 = 0;
          v30 = 0;
          v21 = v28;
          if ( (_QWORD)v28 )
          {
            v22 = *((_QWORD *)&v28 + 1);
            if ( _InterlockedIncrement((volatile signed __int32 *)(v28 + 8)) == 1 )
              _InterlockedIncrement((volatile signed __int32 *)(v21 + 12));
            *(_QWORD *)&v30 = v21;
            *((_QWORD *)&v30 + 1) = v22;
          }
          v19 = win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::MessageHandlers<win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>::ProcessMessage(
                  v20,
                  &v30);
        }
        if ( (*(_DWORD *)(v2 + 340))-- == 1 )
          *(_DWORD *)(v2 + 336) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 296));
        if ( *((_QWORD *)&v28 + 1) && (_QWORD)v28 )
        {
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v28);
          v28 = 0;
        }
        if ( v19 )
        {
          v27 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
                  v31,
                  &v29);
          _RemoveMessage___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAAXV__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope___Z(
            v2,
            v27);
        }
        if ( v9 && v10 )
        {
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v29);
          v29 = 0;
        }
      }
      else
      {
        v4 = v3;
        v19 = 0;
      }
      if ( !v19 )
      {
        _ProcessAnEventHandler___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAA_AU__pair__NV__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope___std__XZ(
          v4,
          (__int64)v32);
        v19 = v32[0];
        if ( v32[0] )
        {
          v30 = 0;
          if ( v33[0] )
          {
            win_scope::counted_strong_weak_base::AddRef(v33[0]);
            *(_QWORD *)&v30 = v25;
            *((_QWORD *)&v30 + 1) = v26;
          }
          _RemoveMessage___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAAXV__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope___Z(
            v4,
            &v30);
        }
        if ( v33[1] && v33[0] )
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v33);
      }
      if ( *(_BYTE *)(a1 + 4)
        && !v19
        && (unsigned __int8)_EventQueueEmpty___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAA_NXZ(v4) )
      {
        break;
      }
      v3 = v4;
      if ( !v19 )
        goto LABEL_52;
    }
    if ( !*(_QWORD *)(a1 + 392) )
      _PurgeHandlers___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAAXXZ(v4);
LABEL_52:
    v3 = v4;
    result = _EventQueueEmpty___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAA_NXZ(v4);
  }
  while ( !(_BYTE)result || *(_QWORD *)(a1 + 392) );
  return result;
}

```

## disassembly

```asm
0x18000f9c0  mov     rax, rsp
0x18000f9c3  push    rbp
0x18000f9c4  push    rsi
0x18000f9c5  push    rdi
0x18000f9c6  push    r12
0x18000f9c8  push    r13
0x18000f9ca  push    r14
0x18000f9cc  push    r15
0x18000f9ce  mov     rbp, rsp
0x18000f9d1  sub     rsp, 80h
0x18000f9d8  mov     [rbp+var_60], 0FFFFFFFFFFFFFFFEh
0x18000f9e0  mov     [rax+20h], rbx
0x18000f9e4  mov     rbx, rcx
0x18000f9e7  lea     r13, [rcx+8]
0x18000f9eb  mov     rsi, r13
0x18000f9ee  xor     r14d, r14d
0x18000f9f1  cmp     [rbx+188h], r14
0x18000f9f8  jz      loc_18000FCD2
0x18000f9fe  mov     r15, r13
0x18000fa01  mov     rdx, [rbx+180h]
0x18000fa08  mov     rax, [rbx+178h]
0x18000fa0f  xorps   xmm0, xmm0
0x18000fa12  movdqu  [rbp+var_48], xmm0
0x18000fa17  mov     rcx, rdx
0x18000fa1a  sub     rcx, rax
0x18000fa1d  cmp     rax, rdx
0x18000fa20  cmova   rcx, rdx
0x18000fa24  mov     rax, [rbx+170h]
0x18000fa2b  mov     rdx, [rax+rcx*8]
0x18000fa2f  mov     rsi, [rdx]
0x18000fa32  test    rsi, rsi
0x18000fa35  jz      loc_18000FD53
0x18000fa3b  mov     r12, [rdx+8]
0x18000fa3f  mov     eax, 1
0x18000fa44  lock xadd [rsi+8], eax
0x18000fa49  inc     eax
0x18000fa4b  cmp     eax, 1
0x18000fa4e  jz      loc_18000FCB7
0x18000fa54  mov     qword ptr [rbp+var_48], rsi
0x18000fa58  mov     qword ptr [rbp+var_48+8], r12
0x18000fa5c  mov     rdx, [rbx+188h]
0x18000fa63  test    rdx, rdx
0x18000fa66  jz      short loc_18000FAD0
0x18000fa68  mov     rcx, [rbx+180h]
0x18000fa6f  mov     rax, [rbx+170h]
0x18000fa76  mov     rdi, [rax+rcx*8]
0x18000fa7a  cmp     [rdi], r14
0x18000fa7d  jz      short loc_18000FA9B
0x18000fa7f  cmp     [rdi+8], r14
0x18000fa83  jz      short loc_18000FA9B
0x18000fa85  mov     rcx, rdi
0x18000fa88  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18000fa8d  mov     [rdi], r14
0x18000fa90  mov     [rdi+8], r14
0x18000fa94  mov     rdx, [rbx+188h]
0x18000fa9b  inc     qword ptr [rbx+180h]
0x18000faa2  mov     rax, [rbx+180h]
0x18000faa9  cmp     [rbx+178h], rax
0x18000fab0  ja      short loc_18000FAB9
0x18000fab2  mov     [rbx+180h], r14
0x18000fab9  lea     rax, [rdx-1]
0x18000fabd  mov     [rbx+188h], rax
0x18000fac4  test    rax, rax
0x18000fac7  jnz     short loc_18000FAD0
0x18000fac9  mov     [rbx+180h], r14
0x18000fad0  xorps   xmm0, xmm0
0x18000fad3  movdqu  [rbp+var_58], xmm0
0x18000fad8  test    rsi, rsi
0x18000fadb  jz      short loc_18000FAFA
0x18000fadd  mov     eax, 1
0x18000fae2  lock xadd [rsi+8], eax
0x18000fae7  inc     eax
0x18000fae9  cmp     eax, 1
0x18000faec  jz      loc_18000FCC0
0x18000faf2  mov     qword ptr [rbp+var_58], rsi
0x18000faf6  mov     qword ptr [rbp+var_58+8], r12
0x18000fafa  lea     rax, [rbp+var_58]
0x18000fafe  mov     [rbp+arg_0], rax
0x18000fb02  lea     r14, [r13+128h]
0x18000fb09  mov     [rbp+arg_8], r14
0x18000fb0d  mov     rcx, r14; lpCriticalSection
0x18000fb10  call    cs:__imp_EnterCriticalSection
0x18000fb16  mov     ecx, [r14+2Ch]
0x18000fb1a  lea     eax, [rcx+1]
0x18000fb1d  mov     [r14+2Ch], eax
0x18000fb21  test    ecx, ecx
0x18000fb23  jnz     short loc_18000FB2F
0x18000fb25  call    cs:__imp_GetCurrentThreadId
0x18000fb2b  mov     [r14+28h], eax
0x18000fb2f  mov     cl, [r13+120h]; this
0x18000fb36  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x18000fb3b  xorps   xmm0, xmm0
0x18000fb3e  movdqu  [rbp+var_38], xmm0
0x18000fb43  mov     rcx, qword ptr [rbp+var_58]
0x18000fb47  test    rcx, rcx
0x18000fb4a  jz      short loc_18000FB6D
0x18000fb4c  mov     rdx, qword ptr [rbp+var_58+8]
0x18000fb50  mov     eax, 1
0x18000fb55  lock xadd [rcx+8], eax
0x18000fb5a  inc     eax
0x18000fb5c  cmp     eax, 1
0x18000fb5f  jz      loc_18000FCC9
0x18000fb65  mov     qword ptr [rbp+var_38], rcx
0x18000fb69  mov     qword ptr [rbp+var_38+8], rdx
0x18000fb6d  lea     rdx, [rbp+var_38]
0x18000fb71  mov     rcx, r13
0x18000fb74  call    ?ProcessMessage@?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@QEAA_NV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>::ProcessMessage(win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>)
0x18000fb79  mov     dil, al
0x18000fb7c  test    al, al
0x18000fb7e  jnz     short loc_18000FBCB
0x18000fb80  test    r13, r13
0x18000fb83  jz      loc_18000FCDD
0x18000fb89  lea     rcx, [r13+38h]
0x18000fb8d  xorps   xmm0, xmm0
0x18000fb90  movdqu  [rbp+var_38], xmm0
0x18000fb95  mov     rdx, qword ptr [rbp+var_58]
0x18000fb99  test    rdx, rdx
0x18000fb9c  jz      short loc_18000FBBF
0x18000fb9e  mov     r8, qword ptr [rbp+var_58+8]
0x18000fba2  mov     eax, 1
0x18000fba7  lock xadd [rdx+8], eax
0x18000fbac  inc     eax
0x18000fbae  cmp     eax, 1
0x18000fbb1  jz      loc_18000FCE4
0x18000fbb7  mov     qword ptr [rbp+var_38], rdx
0x18000fbbb  mov     qword ptr [rbp+var_38+8], r8
0x18000fbbf  lea     rdx, [rbp+var_38]
0x18000fbc3  call    ?ProcessMessage@?$MessageHandlers@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA_NV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::MessageHandlers<win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>::ProcessMessage(win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>)
0x18000fbc8  mov     dil, al
0x18000fbcb  add     dword ptr [r14+2Ch], 0FFFFFFFFh
0x18000fbd0  jnz     short loc_18000FBDA
0x18000fbd2  mov     dword ptr [r14+28h], 0
0x18000fbda  mov     rcx, r14; lpCriticalSection
0x18000fbdd  call    cs:__imp_LeaveCriticalSection
0x18000fbe3  nop
0x18000fbe4  xor     r14d, r14d
0x18000fbe7  cmp     qword ptr [rbp+var_58+8], r14
0x18000fbeb  jz      short loc_18000FC04
0x18000fbed  cmp     qword ptr [rbp+var_58], r14
0x18000fbf1  jz      short loc_18000FC04
0x18000fbf3  lea     rcx, [rbp+var_58]
0x18000fbf7  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18000fbfc  xorps   xmm0, xmm0
0x18000fbff  movdqu  [rbp+var_58], xmm0
0x18000fc04  test    dil, dil
0x18000fc07  jnz     loc_18000FD60
0x18000fc0d  test    rsi, rsi
0x18000fc10  jz      short loc_18000FC1B
0x18000fc12  test    r12, r12
0x18000fc15  jnz     loc_18000FCA1
0x18000fc1b  test    dil, dil
0x18000fc1e  jnz     short loc_18000FC50
0x18000fc20  lea     rdx, [rbp+var_18]
0x18000fc24  mov     rcx, r15
0x18000fc27  call    ?ProcessAnEventHandler@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA?AU?$pair@_NV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@XZ
0x18000fc2c  nop
0x18000fc2d  mov     dil, [rbp+var_18]
0x18000fc31  test    dil, dil
0x18000fc34  jnz     loc_18000FCED
0x18000fc3a  cmp     [rbp+var_8], r14
0x18000fc3e  jz      short loc_18000FC50
0x18000fc40  cmp     [rbp+var_10], r14
0x18000fc44  jz      short loc_18000FC50
0x18000fc46  lea     rcx, [rbp+var_10]
0x18000fc4a  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18000fc4f  nop
0x18000fc50  cmp     [rbx+4], r14b
0x18000fc54  jnz     loc_18000FD20
0x18000fc5a  mov     rsi, r15
0x18000fc5d  test    dil, dil
0x18000fc60  jnz     loc_18000F9F1
0x18000fc66  mov     rsi, r15
0x18000fc69  mov     rcx, r15
0x18000fc6c  call    ?EventQueueEmpty@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA_NXZ
0x18000fc71  test    al, al
0x18000fc73  jz      loc_18000F9F1
0x18000fc79  cmp     [rbx+188h], r14
0x18000fc80  jnz     loc_18000F9F1
0x18000fc86  mov     rbx, [rsp+80h+arg_18]
0x18000fc8e  add     rsp, 80h
0x18000fc95  pop     r15
0x18000fc97  pop     r14
0x18000fc99  pop     r13
0x18000fc9b  pop     r12
0x18000fc9d  pop     rdi
0x18000fc9e  pop     rsi
0x18000fc9f  pop     rbp
0x18000fca0  retn
0x18000fca1  lea     rcx, [rbp+var_48]
0x18000fca5  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18000fcaa  xorps   xmm0, xmm0
0x18000fcad  movdqu  [rbp+var_48], xmm0
0x18000fcb2  jmp     loc_18000FC1B
0x18000fcb7  lock inc dword ptr [rsi+0Ch]
0x18000fcbb  jmp     loc_18000FA54
0x18000fcc0  lock inc dword ptr [rsi+0Ch]
0x18000fcc4  jmp     loc_18000FAF2
0x18000fcc9  lock inc dword ptr [rcx+0Ch]
0x18000fccd  jmp     loc_18000FB65
0x18000fcd2  mov     r15, rsi
0x18000fcd5  mov     dil, r14b
0x18000fcd8  jmp     loc_18000FC1B
0x18000fcdd  xor     ecx, ecx
0x18000fcdf  jmp     loc_18000FB8D
0x18000fce4  lock inc dword ptr [rdx+0Ch]
0x18000fce8  jmp     loc_18000FBB7
0x18000fced  xorps   xmm0, xmm0
0x18000fcf0  movdqu  [rbp+var_38], xmm0
0x18000fcf5  mov     rcx, [rbp+var_10]; this
0x18000fcf9  test    rcx, rcx
0x18000fcfc  jz      short loc_18000FD0F
0x18000fcfe  mov     rdx, [rbp+var_8]
0x18000fd02  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x18000fd07  mov     qword ptr [rbp+var_38], rcx
0x18000fd0b  mov     qword ptr [rbp+var_38+8], rdx
0x18000fd0f  lea     rdx, [rbp+var_38]
0x18000fd13  mov     rcx, r15
0x18000fd16  call    ?RemoveMessage@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAAXV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z
0x18000fd1b  jmp     loc_18000FC3A
0x18000fd20  test    dil, dil
0x18000fd23  jnz     loc_18000FC5A
0x18000fd29  mov     rcx, r15
0x18000fd2c  call    ?EventQueueEmpty@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA_NXZ
0x18000fd31  test    al, al
0x18000fd33  jz      loc_18000FC5A
0x18000fd39  cmp     [rbx+188h], r14
0x18000fd40  jnz     loc_18000FC66
0x18000fd46  mov     rcx, r15
0x18000fd49  call    ?PurgeHandlers@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAAXXZ
0x18000fd4e  jmp     loc_18000FC66
0x18000fd53  mov     r12, qword ptr [rbp+var_48+8]
0x18000fd57  mov     rsi, qword ptr [rbp+var_48]
0x18000fd5b  jmp     loc_18000FA5C
0x18000fd60  lea     rdx, [rbp+var_48]
0x18000fd64  lea     rcx, [rbp+var_28]
0x18000fd68  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18000fd6d  mov     rdx, rax
0x18000fd70  mov     rcx, r13
0x18000fd73  call    ?RemoveMessage@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAAXV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z
0x18000fd78  jmp     loc_18000FC0D
```

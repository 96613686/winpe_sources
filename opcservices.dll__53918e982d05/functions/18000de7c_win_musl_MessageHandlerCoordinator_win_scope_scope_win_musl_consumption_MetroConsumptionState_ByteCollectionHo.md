# win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::MessageHandlers<win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>::EventQueueEmpty(void)

- ea: `0x18000de7c`
- end: `0x18000defe`
- name: `?EventQueueEmpty@?$MessageHandlers@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA_NXZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000df98`

## callees

- `0x18000de7c`
- `0x180011b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000deb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000deb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dee5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dee5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dea5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dea5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::MessageHandlers<win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>::EventQueueEmpty(
        __int64 a1)
{
  __int64 v2; // rbx
  win_dox *v3; // rcx
  int v4; // edx
  bool v5; // si

  v2 = a1 + 136;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 136));
  v4 = *(_DWORD *)(v2 + 44);
  *(_DWORD *)(v2 + 44) = v4 + 1;
  if ( !v4 )
    *(_DWORD *)(v2 + 40) = GetCurrentThreadId();
  LOBYTE(v3) = *(_BYTE *)(a1 + 128);
  win_dox::ThrowIfFailed(v3, v4);
  v5 = *(_QWORD *)(a1 + 120) == 0;
  if ( (*(_DWORD *)(v2 + 44))-- == 1 )
    *(_DWORD *)(v2 + 40) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v2);
  return v5;
}

```

## disassembly

```asm
0x18000de7c  mov     rax, rsp
0x18000de7f  push    rdi
0x18000de80  sub     rsp, 30h
0x18000de84  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18000de8c  mov     [rax+10h], rbx
0x18000de90  mov     [rax+18h], rsi
0x18000de94  mov     rsi, rcx
0x18000de97  lea     rbx, [rcx+88h]
0x18000de9e  mov     [rax+8], rbx
0x18000dea2  mov     rcx, rbx; lpCriticalSection
0x18000dea5  call    cs:__imp_EnterCriticalSection
0x18000deab  mov     edx, [rbx+2Ch]
0x18000deae  lea     eax, [rdx+1]
0x18000deb1  mov     [rbx+2Ch], eax
0x18000deb4  test    edx, edx
0x18000deb6  jnz     short loc_18000DEC1
0x18000deb8  call    cs:__imp_GetCurrentThreadId
0x18000debe  mov     [rbx+28h], eax
0x18000dec1  mov     cl, [rsi+80h]; this
0x18000dec7  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x18000decc  cmp     qword ptr [rsi+78h], 0
0x18000ded1  setz    sil
0x18000ded5  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x18000ded9  jnz     short loc_18000DEE2
0x18000dedb  mov     dword ptr [rbx+28h], 0
0x18000dee2  mov     rcx, rbx; lpCriticalSection
0x18000dee5  call    cs:__imp_LeaveCriticalSection
0x18000deeb  mov     al, sil
0x18000deee  mov     rbx, [rsp+38h+arg_8]
0x18000def3  mov     rsi, [rsp+38h+arg_10]
0x18000def8  add     rsp, 30h
0x18000defc  pop     rdi
0x18000defd  retn
```

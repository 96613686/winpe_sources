# Microsoft::IoT::Utility::MTAThreadPool::QueueMultiEventItem(std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>,std::allocator<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>> const &,Microsoft::IoT::Utility::IMTAThreadPoolEventCallback *)

- ea: `0x18000d82c`
- end: `0x18000da5b`
- name: `?QueueMultiEventItem@MTAThreadPool@Utility@IoT@Microsoft@@QEAAJAEBV?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@PEAUIMTAThreadPoolEventCallback@234@@Z`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f58c`

## callees

- `0x180002f1c`
- `0x180009ebc`
- `0x18000aad8`
- `0x18000c2bc`
- `0x18000c300`
- `0x18000ca50`
- `0x18000cc14`
- `0x18000cee0`
- `0x18000d130`
- `0x18000d1a8`
- `0x18000d2ac`
- `0x18000d410`
- `0x18000d7c8`
- `0x18000d82c`
- `0x18000dcb4`
- `0x18000dce4`
- `0x18000e718`
- `0x18000e740`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d86f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d967`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d86f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d967`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::IoT::Utility::MTAThreadPool::QueueMultiEventItem(
        __int64 a1,
        _QWORD *a2,
        struct Microsoft::IoT::Utility::MTAThreadPool *a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  unsigned int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rsi
  _QWORD *v11; // rax
  __int64 v12; // rcx
  void *v13; // rdx
  __int64 *v14; // rsi
  __int64 v15; // rcx
  _DWORD *v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  std::_Ref_count_base *v20; // rdi
  _DWORD *v21; // [rsp+20h] [rbp-20h] BYREF
  std::_Ref_count_base *v22; // [rsp+28h] [rbp-18h]
  __int64 v23; // [rsp+38h] [rbp-8h] BYREF
  struct Microsoft::IoT::Utility::MTAThreadPool *v24; // [rsp+68h] [rbp+28h] BYREF
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+78h] [rbp+38h] BYREF

  if ( (unsigned __int64)((__int64)(a2[1] - *a2) >> 4) > 0x3E )
    return 2147942487LL;
  v7 = (struct _RTL_CRITICAL_SECTION *)(a1 + 184);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  v25 = v7;
  if ( *(_BYTE *)(a1 + 272) )
  {
    v8 = 0;
  }
  else if ( *(_QWORD *)(a1 + 256) < 0x3Eu )
  {
    v24 = a3;
    Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(&v24);
    std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>(
      &v21,
      a2);
    Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(
      &v23,
      &v24);
    if ( *(_QWORD *)(a1 + 240) <= (unsigned __int64)(*(_QWORD *)(a1 + 256) + 1LL) )
      std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Growmap((_QWORD *)(a1 + 224));
    *(_QWORD *)(a1 + 248) &= *(_QWORD *)(a1 + 240) - 1LL;
    v9 = *(_QWORD *)(a1 + 256) + *(_QWORD *)(a1 + 248);
    v10 = std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Getblock(
            a1 + 224,
            v9);
    if ( !*(_QWORD *)(*(_QWORD *)(a1 + 232) + 8 * v10) )
      *(_QWORD *)(*(_QWORD *)(a1 + 232) + 8 * v10) = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
    v11 = (_QWORD *)std::_Deque_val<std::_Deque_simple_types<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>>::_Address_subscript(
                      a1 + 224,
                      v9);
    std::_Default_allocator_traits<std::allocator<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>>::construct<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>,std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(
      v12,
      v11,
      (__int64 *)&v21);
    ++*(_QWORD *)(a1 + 256);
    std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::~pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>((__int64)&v21);
    if ( v24 )
      (*(void (__fastcall **)(struct Microsoft::IoT::Utility::MTAThreadPool *))(*(_QWORD *)v24 + 16LL))(v24);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v25);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    v25 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
    v14 = (__int64 *)(a1 + 56);
    v15 = *(_QWORD *)(a1 + 64);
    if ( v15 == *(_QWORD *)(a1 + 56) )
    {
      v24 = (struct Microsoft::IoT::Utility::MTAThreadPool *)a1;
      v16 = operator new(0x40u);
      v21 = v16;
      *(_OWORD *)v16 = 0;
      v16[2] = 1;
      v16[3] = 1;
      *(_QWORD *)v16 = &std::_Ref_count_obj2<Microsoft::IoT::Utility::MTAEventThread>::`vftable';
      std::_Construct_in_place<Microsoft::IoT::Utility::MTAEventThread,Microsoft::IoT::Utility::MTAThreadPool *>(
        (Microsoft::IoT::Utility::MTAThread *)(v16 + 4),
        &v24);
      v21 = v16 + 4;
      v22 = (std::_Ref_count_base *)v16;
      v17 = v14[1];
      if ( v17 == v14[2] )
        std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Emplace_reallocate<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(
          v14,
          v17,
          &v21);
      else
        std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Emplace_back_with_unused_capacity<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(
          (__int64)v14,
          &v21);
      if ( v22 )
        std::_Ref_count_base::_Decref(v22);
      v18 = v14[1];
      v19 = *(_QWORD *)(v18 - 8);
      if ( v19 )
        _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
      v20 = *(std::_Ref_count_base **)(v18 - 8);
      v8 = Microsoft::IoT::Utility::MTAThread::Start(*(Microsoft::IoT::Utility::MTAThread **)(v18 - 16));
      if ( v20 )
        std::_Ref_count_base::_Decref(v20);
    }
    else
    {
      v8 = 0;
      wil::details::SetEvent(*(wil::details **)(*(_QWORD *)(v15 - 16) + 16LL), v13);
    }
  }
  else
  {
    v8 = -2147024809;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v25);
  return v8;
}

```

## disassembly

```asm
0x18000d82c  mov     [rsp-18h+arg_0], rbx
0x18000d831  mov     [rsp-18h+arg_10], rsi
0x18000d836  push    rbp
0x18000d837  push    rdi
0x18000d838  push    r14
0x18000d83a  mov     rbp, rsp
0x18000d83d  sub     rsp, 40h
0x18000d841  mov     r14, r8
0x18000d844  mov     rsi, rdx
0x18000d847  mov     rdi, rcx
0x18000d84a  mov     rax, [rdx+8]
0x18000d84e  sub     rax, [rdx]
0x18000d851  sar     rax, 4
0x18000d855  cmp     rax, 3Eh ; '>'
0x18000d859  jbe     short loc_18000D865
0x18000d85b  mov     eax, 80070057h
0x18000d860  jmp     loc_18000DA48
0x18000d865  lea     rbx, [rcx+0B8h]
0x18000d86c  mov     rcx, rbx; lpCriticalSection
0x18000d86f  call    cs:__imp_EnterCriticalSection
0x18000d875  mov     [rbp+arg_18], rbx
0x18000d879  cmp     byte ptr [rdi+110h], 0
0x18000d880  jz      short loc_18000D886
0x18000d882  xor     ebx, ebx
0x18000d884  jmp     short loc_18000D895
0x18000d886  cmp     qword ptr [rdi+100h], 3Eh ; '>'
0x18000d88e  jb      short loc_18000D89A
0x18000d890  mov     ebx, 80070057h
0x18000d895  jmp     loc_18000DA3D
0x18000d89a  lea     rbx, [rdi+0E0h]
0x18000d8a1  mov     [rbp+arg_8], r14
0x18000d8a5  lea     rcx, [rbp+arg_8]
0x18000d8a9  call    ?InternalAddRef@?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(void)
0x18000d8ae  nop
0x18000d8af  mov     rdx, rsi
0x18000d8b2  lea     rcx, [rbp+var_20]
0x18000d8b6  call    ??0?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>(std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>> const &)
0x18000d8bb  lea     rdx, [rbp+arg_8]
0x18000d8bf  lea     rcx, [rbp+var_8]
0x18000d8c3  call    ??0?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> &&)
0x18000d8c8  nop
0x18000d8c9  mov     rax, [rbx+20h]
0x18000d8cd  inc     rax
0x18000d8d0  cmp     [rbx+10h], rax
0x18000d8d4  ja      short loc_18000D8DE
0x18000d8d6  mov     rcx, rbx
0x18000d8d9  call    ?_Growmap@?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Growmap(unsigned __int64)
0x18000d8de  mov     rax, [rbx+10h]
0x18000d8e2  dec     rax
0x18000d8e5  and     [rbx+18h], rax
0x18000d8e9  mov     r14, [rbx+18h]
0x18000d8ed  add     r14, [rbx+20h]
0x18000d8f1  mov     rdx, r14
0x18000d8f4  mov     rcx, rbx
0x18000d8f7  call    ?_Getblock@?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@AEBA_J_K@Z; std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Getblock(unsigned __int64)
0x18000d8fc  mov     rsi, rax
0x18000d8ff  mov     rcx, [rbx+8]
0x18000d903  cmp     qword ptr [rcx+rax*8], 0
0x18000d908  jnz     short loc_18000D91C
0x18000d90a  mov     ecx, 20h ; ' '
0x18000d90f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d914  mov     rcx, [rbx+8]
0x18000d918  mov     [rcx+rsi*8], rax
0x18000d91c  mov     rdx, r14
0x18000d91f  mov     rcx, rbx
0x18000d922  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@2@_K@Z; std::_Deque_val<std::_Deque_simple_types<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>>::_Address_subscript(unsigned __int64)
0x18000d927  lea     r8, [rbp+var_20]
0x18000d92b  mov     rdx, rax
0x18000d92e  call    ??$construct@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@U12@@?$_Default_allocator_traits@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@@std@@SAXAEAV?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@1@QEAU?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@1@$$QEAU31@@Z
0x18000d933  inc     qword ptr [rbx+20h]
0x18000d937  lea     rcx, [rbp+var_20]
0x18000d93b  call    ??1?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::~pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>(void)
0x18000d940  nop
0x18000d941  mov     rcx, [rbp+arg_8]
0x18000d945  test    rcx, rcx
0x18000d948  jz      short loc_18000D957
0x18000d94a  mov     rax, [rcx]
0x18000d94d  mov     rax, [rax+10h]
0x18000d951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d956  nop
0x18000d957  lea     rcx, [rbp+arg_18]
0x18000d95b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000d960  lea     rbx, [rdi+10h]
0x18000d964  mov     rcx, rbx; lpCriticalSection
0x18000d967  call    cs:__imp_EnterCriticalSection
0x18000d96d  mov     [rbp+arg_18], rbx
0x18000d971  lea     rsi, [rdi+38h]
0x18000d975  mov     rcx, [rsi+8]
0x18000d979  cmp     rcx, [rsi]
0x18000d97c  jnz     loc_18000DA2D
0x18000d982  mov     [rbp+arg_8], rdi
0x18000d986  mov     ecx, 40h ; '@'; Size
0x18000d98b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d990  mov     rdi, rax
0x18000d993  mov     [rbp+var_20], rax
0x18000d997  xorps   xmm0, xmm0
0x18000d99a  movups  xmmword ptr [rax], xmm0
0x18000d99d  mov     dword ptr [rax+8], 1
0x18000d9a4  mov     dword ptr [rax+0Ch], 1
0x18000d9ab  lea     rax, ??_7?$_Ref_count_obj2@VMTAEventThread@Utility@IoT@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::IoT::Utility::MTAEventThread>::`vftable'
0x18000d9b2  mov     [rdi], rax
0x18000d9b5  lea     rbx, [rdi+10h]
0x18000d9b9  lea     rdx, [rbp+arg_8]
0x18000d9bd  mov     rcx, rbx
0x18000d9c0  call    ??$_Construct_in_place@VMTAEventThread@Utility@IoT@Microsoft@@PEAVMTAThreadPool@234@@std@@YAXAEAVMTAEventThread@Utility@IoT@Microsoft@@$$QEAPEAVMTAThreadPool@234@@Z; std::_Construct_in_place<Microsoft::IoT::Utility::MTAEventThread,Microsoft::IoT::Utility::MTAThreadPool *>(Microsoft::IoT::Utility::MTAEventThread &,Microsoft::IoT::Utility::MTAThreadPool * &&)
0x18000d9c5  nop
0x18000d9c6  mov     [rbp+var_20], rbx
0x18000d9ca  mov     [rbp+var_18], rdi
0x18000d9ce  mov     rdx, [rsi+8]
0x18000d9d2  mov     rcx, rsi
0x18000d9d5  cmp     rdx, [rsi+10h]
0x18000d9d9  jz      short loc_18000D9E6
0x18000d9db  lea     rdx, [rbp+var_20]
0x18000d9df  call    ??$_Emplace_back_with_unused_capacity@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@?$vector@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@2@@std@@AEAAAEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@1@$$QEAV21@@Z; std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Emplace_back_with_unused_capacity<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> &&)
0x18000d9e4  jmp     short loc_18000D9F0
0x18000d9e6  lea     r8, [rbp+var_20]
0x18000d9ea  call    ??$_Emplace_reallocate@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@?$vector@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Emplace_reallocate<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> * const,std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> &&)
0x18000d9ef  nop
0x18000d9f0  mov     rcx, [rbp+var_18]; this
0x18000d9f4  test    rcx, rcx
0x18000d9f7  jz      short loc_18000D9FE
0x18000d9f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d9fe  mov     rcx, [rsi+8]
0x18000da02  mov     rax, [rcx-8]
0x18000da06  test    rax, rax
0x18000da09  jz      short loc_18000DA0F
0x18000da0b  lock inc dword ptr [rax+8]
0x18000da0f  mov     rdi, [rcx-8]
0x18000da13  mov     rcx, [rcx-10h]; this
0x18000da17  call    ?Start@MTAThread@Utility@IoT@Microsoft@@QEAAJXZ; Microsoft::IoT::Utility::MTAThread::Start(void)
0x18000da1c  mov     ebx, eax
0x18000da1e  test    rdi, rdi
0x18000da21  jz      short loc_18000DA3D
0x18000da23  mov     rcx, rdi; this
0x18000da26  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000da2b  jmp     short loc_18000DA3D
0x18000da2d  xor     ebx, ebx
0x18000da2f  mov     rcx, [rcx-10h]
0x18000da33  mov     rcx, [rcx+10h]; this
0x18000da37  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000da3c  nop
0x18000da3d  lea     rcx, [rbp+arg_18]
0x18000da41  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000da46  mov     eax, ebx
0x18000da48  mov     rbx, [rsp+40h+arg_0]
0x18000da4d  mov     rsi, [rsp+40h+arg_10]
0x18000da52  add     rsp, 40h
0x18000da56  pop     r14
0x18000da58  pop     rdi
0x18000da59  pop     rbp
0x18000da5a  retn
```

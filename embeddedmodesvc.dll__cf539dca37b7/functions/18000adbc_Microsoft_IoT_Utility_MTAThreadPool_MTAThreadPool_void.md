# Microsoft::IoT::Utility::MTAThreadPool::~MTAThreadPool(void)

- ea: `0x18000adbc`
- end: `0x18000ae8c`
- name: `??1MTAThreadPool@Utility@IoT@Microsoft@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(Microsoft::IoT::Utility::MTAThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c3a0`

## callees

- `0x180009f7c`
- `0x18000a020`
- `0x18000aa10`
- `0x18000aa40`
- `0x18000aa70`
- `0x18000adbc`
- `0x18000dd80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000addd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000adf3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ae79`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000addd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000adf3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ae79`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::IoT::Utility::MTAThreadPool::~MTAThreadPool(Microsoft::IoT::Utility::MTAThreadPool *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  Microsoft::IoT::Utility::MTAThreadPool::Stop(this);
  __1__deque_U__pair_V__vector_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil__V__allocator_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil___std___std__V__ComPtr_UIMTAThreadPoolEventCallback_Utility_IoT_Microsoft___WRL_Microsoft___std__V__allocator_U__pair_V__vector_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil__V__allocator_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil___std___std__V__ComPtr_UIMTAThreadPoolEventCallback_Utility_IoT_Microsoft___WRL_Microsoft___std___2__std__QEAA_XZ((_QWORD **)this + 28);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::~deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>((_QWORD **)this + 18);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v2 = *((_QWORD *)this + 10);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(
      v2,
      *((_QWORD *)this + 11));
    std::_Deallocate<16>(
      *((_QWORD **)this + 10),
      (*((_QWORD *)this + 12) - *((_QWORD *)this + 10)) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
  }
  v3 = *((_QWORD *)this + 7);
  if ( v3 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(
      v3,
      *((_QWORD *)this + 8));
    std::_Deallocate<16>(
      *((_QWORD **)this + 7),
      (*((_QWORD *)this + 9) - *((_QWORD *)this + 7)) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>((__int64)this);
}

```

## disassembly

```asm
0x18000adbc  push    rbx
0x18000adbe  sub     rsp, 20h
0x18000adc2  mov     rbx, rcx
0x18000adc5  call    ?Stop@MTAThreadPool@Utility@IoT@Microsoft@@QEAAXXZ; Microsoft::IoT::Utility::MTAThreadPool::Stop(void)
0x18000adca  lea     rcx, [rbx+0E0h]
0x18000add1  call    ??1?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@QEAA@XZ
0x18000add6  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18000addd  call    cs:__imp_DeleteCriticalSection
0x18000ade3  lea     rcx, [rbx+90h]
0x18000adea  call    ??1?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::~deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>(void)
0x18000adef  lea     rcx, [rbx+68h]; lpCriticalSection
0x18000adf3  call    cs:__imp_DeleteCriticalSection
0x18000adf9  mov     rcx, [rbx+50h]
0x18000adfd  test    rcx, rcx
0x18000ae00  jz      short loc_18000AE37
0x18000ae02  mov     rdx, [rbx+58h]
0x18000ae06  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> *,std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> * const,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>> &)
0x18000ae0b  mov     rcx, [rbx+50h]
0x18000ae0f  mov     rdx, [rbx+60h]
0x18000ae13  sub     rdx, rcx
0x18000ae16  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000ae1a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000ae1f  mov     qword ptr [rbx+50h], 0
0x18000ae27  mov     qword ptr [rbx+58h], 0
0x18000ae2f  mov     qword ptr [rbx+60h], 0
0x18000ae37  mov     rcx, [rbx+38h]
0x18000ae3b  test    rcx, rcx
0x18000ae3e  jz      short loc_18000AE75
0x18000ae40  mov     rdx, [rbx+40h]
0x18000ae44  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> *,std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> * const,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>> &)
0x18000ae49  mov     rcx, [rbx+38h]
0x18000ae4d  mov     rdx, [rbx+48h]
0x18000ae51  sub     rdx, rcx
0x18000ae54  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000ae58  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000ae5d  mov     qword ptr [rbx+38h], 0
0x18000ae65  mov     qword ptr [rbx+40h], 0
0x18000ae6d  mov     qword ptr [rbx+48h], 0
0x18000ae75  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000ae79  call    cs:__imp_DeleteCriticalSection
0x18000ae7f  mov     rcx, rbx
0x18000ae82  add     rsp, 20h
0x18000ae86  pop     rbx
0x18000ae87  jmp     ??1?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>(void)
```

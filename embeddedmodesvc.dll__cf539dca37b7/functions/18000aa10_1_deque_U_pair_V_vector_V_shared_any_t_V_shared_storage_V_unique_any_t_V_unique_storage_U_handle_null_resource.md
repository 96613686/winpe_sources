# ??1?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@QEAA@XZ

- ea: `0x18000aa10`
- end: `0x18000aa37`
- name: `??1?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ab14`
- `0x18000adbc`
- `0x18000de50`

## callees

- `0x180009f7c`
- `0x18000c584`

## pseudocode

```c
void __fastcall __1__deque_U__pair_V__vector_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil__V__allocator_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil___std___std__V__ComPtr_UIMTAThreadPoolEventCallback_Utility_IoT_Microsoft___WRL_Microsoft___std__V__allocator_U__pair_V__vector_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil__V__allocator_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil___std___std__V__ComPtr_UIMTAThreadPoolEventCallback_Utility_IoT_Microsoft___WRL_Microsoft___std___2__std__QEAA_XZ(
        _QWORD **a1)
{
  _QWORD *v2; // rcx

  std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Tidy();
  v2 = *a1;
  *a1 = 0;
  std::_Deallocate<16>(v2, 0x10u);
}

```

## disassembly

```asm
0x18000aa10  push    rbx
0x18000aa12  sub     rsp, 20h
0x18000aa16  mov     rbx, rcx
0x18000aa19  call    ?_Tidy@?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@AEAAXXZ; std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Tidy(void)
0x18000aa1e  mov     rcx, [rbx]
0x18000aa21  mov     edx, 10h
0x18000aa26  mov     qword ptr [rbx], 0
0x18000aa2d  add     rsp, 20h
0x18000aa31  pop     rbx
0x18000aa32  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```

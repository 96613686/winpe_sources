# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)

- ea: `0x1800154fc`
- end: `0x1800155a1`
- name: `?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014e50`
- `0x18001bc90`

## callees

- `0x180002384`
- `0x180002390`
- `0x1800039fc`
- `0x180005d4c`
- `0x1800065f0`
- `0x180013da4`
- `0x1800154fc`
- `0x180015df0`
- `0x180015e2c`

## pseudocode

```c
bool __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::final_suspend_awaiter::await_suspend(
        RTL_SRWLOCK **a1,
        __int64 a2)
{
  RTL_SRWLOCK *v2; // rbx
  __int64 v4; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = a2;
  v2 = *a1;
  v6 = 0;
  WINRT_IMPL_AcquireSRWLockExclusive(v2 + 9);
  LODWORD(v7) = std::_Atomic_storage<unsigned int,4>::load(&v2[12], 0);
  if ( !(_DWORD)v7 )
  {
    LODWORD(v7) = 1;
    std::_Atomic_storage<enum winrt::Windows::Foundation::AsyncStatus,4>::store(v4, 1);
  }
  winrt::Windows::Foundation::IUnknown::operator=(&v6, &v2[10]);
  ReleaseSRWLockExclusive_0(v2 + 9);
  if ( v6 )
  {
    winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,enum winrt::Windows::Foundation::AsyncStatus>(
      &v6,
      v2,
      &v7);
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v6);
  }
  return (unsigned int)winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>::subtract_reference(*a1) != 0;
}

```

## disassembly

```asm
0x1800154fc  mov     rax, rsp
0x1800154ff  mov     [rax+18h], rbx
0x180015503  mov     [rax+20h], rsi
0x180015507  mov     [rax+10h], rdx
0x18001550b  push    rdi
0x18001550c  sub     rsp, 20h
0x180015510  mov     rbx, [rcx]
0x180015513  mov     rdi, rcx
0x180015516  mov     qword ptr [rax+8], 0
0x18001551e  lea     rcx, [rbx+48h]; SRWLock
0x180015522  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180015527  lea     rcx, [rbx+60h]
0x18001552b  xor     edx, edx
0x18001552d  call    ?load@?$_Atomic_storage@I$03@std@@QEBAIW4memory_order@2@@Z; std::_Atomic_storage<uint,4>::load(std::memory_order)
0x180015532  mov     dword ptr [rsp+28h+arg_8], eax
0x180015536  test    eax, eax
0x180015538  jnz     short loc_180015546
0x18001553a  lea     edx, [rax+1]
0x18001553d  mov     dword ptr [rsp+28h+arg_8], edx
0x180015541  call    ?store@?$_Atomic_storage@W4AsyncStatus@Foundation@Windows@winrt@@$03@std@@QEAAXW4AsyncStatus@Foundation@Windows@winrt@@W4memory_order@2@@Z; std::_Atomic_storage<winrt::Windows::Foundation::AsyncStatus,4>::store(winrt::Windows::Foundation::AsyncStatus,std::memory_order)
0x180015546  lea     rdx, [rbx+50h]
0x18001554a  lea     rcx, [rsp+28h+arg_0]
0x18001554f  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180015554  lea     rcx, [rbx+48h]; SRWLock
0x180015558  call    ReleaseSRWLockExclusive_0
0x18001555d  cmp     [rsp+28h+arg_0], 0
0x180015563  jz      short loc_180015581
0x180015565  lea     r8, [rsp+28h+arg_8]
0x18001556a  mov     rdx, rbx
0x18001556d  lea     rcx, [rsp+28h+arg_0]
0x180015572  call    ??$invoke@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x180015577  lea     rcx, [rsp+28h+arg_0]
0x18001557c  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180015581  mov     rcx, [rdi]
0x180015584  call    ?subtract_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>::subtract_reference(void)
0x180015589  test    eax, eax
0x18001558b  jnz     short loc_18001558E
0x18001558d  nop
0x18001558e  mov     rbx, [rsp+28h+arg_10]
0x180015593  setnz   al
0x180015596  mov     rsi, [rsp+28h+arg_18]
0x18001559b  add     rsp, 20h
0x18001559f  pop     rdi
0x1800155a0  retn
```

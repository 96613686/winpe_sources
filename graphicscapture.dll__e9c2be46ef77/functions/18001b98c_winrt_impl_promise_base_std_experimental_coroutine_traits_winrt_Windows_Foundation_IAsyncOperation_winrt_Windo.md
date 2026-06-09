# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::Completed(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> const &)

- ea: `0x18001b98c`
- end: `0x18001ba55`
- name: `?Completed@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXAEBU?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@3@@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c060`

## callees

- `0x1800022f2`
- `0x180002384`
- `0x180002390`
- `0x1800039fc`
- `0x1800058c4`
- `0x1800065f0`
- `0x180013da4`
- `0x18001419c`
- `0x18001b620`
- `0x18001b98c`

## pseudocode

```c
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::Completed(
        __int64 a1,
        _QWORD *a2)
{
  RTL_SRWLOCK *v4; // rdi
  __int64 v5; // rax
  const struct winrt::impl::slim_source_location *v6; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  v4 = (RTL_SRWLOCK *)(a1 + 72);
  v9 = a1 + 72;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  if ( *(_BYTE *)(a1 + 100) )
  {
    v6 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v8);
    winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(
      (winrt::hresult_illegal_delegate_assignment *)pExceptionObject,
      v6);
    throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
  }
  *(_BYTE *)(a1 + 100) = 1;
  LODWORD(v9) = *(_DWORD *)(a1 + 96);
  if ( (_DWORD)v9 )
  {
    ReleaseSRWLockExclusive_0(v4);
    if ( *a2 )
      winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,enum winrt::Windows::Foundation::AsyncStatus>(
        a2,
        a1,
        &v9);
  }
  else
  {
    v5 = winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>((winrt::Windows::Foundation::IUnknown *)&v9);
    winrt::Windows::Foundation::IUnknown::operator=(a1 + 80, v5);
    if ( v9 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v9);
    ReleaseSRWLockExclusive_0(v4);
  }
}

```

## disassembly

```asm
0x18001b98c  mov     [rsp+arg_8], rbx
0x18001b991  mov     [rsp+arg_10], rsi
0x18001b996  push    rdi
0x18001b997  sub     rsp, 50h
0x18001b99b  mov     rsi, rdx
0x18001b99e  mov     rbx, rcx
0x18001b9a1  lea     rdi, [rcx+48h]
0x18001b9a5  mov     [rsp+58h+arg_0], rdi
0x18001b9aa  mov     rcx, rdi; SRWLock
0x18001b9ad  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18001b9b2  nop
0x18001b9b3  cmp     byte ptr [rbx+64h], 0
0x18001b9b7  jnz     short loc_18001BA2C
0x18001b9b9  mov     byte ptr [rbx+64h], 1
0x18001b9bd  mov     eax, [rbx+60h]
0x18001b9c0  mov     dword ptr [rsp+58h+arg_0], eax
0x18001b9c4  test    eax, eax
0x18001b9c6  jnz     short loc_18001B9FE
0x18001b9c8  mov     rdx, rsi
0x18001b9cb  lea     rcx, [rsp+58h+arg_0]; this
0x18001b9d0  call    ??$make_agile_delegate@U?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@1@AEBU2341@@Z; winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> const &)
0x18001b9d5  lea     rcx, [rbx+50h]
0x18001b9d9  mov     rdx, rax
0x18001b9dc  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18001b9e1  cmp     [rsp+58h+arg_0], 0
0x18001b9e7  jz      short loc_18001B9F4
0x18001b9e9  lea     rcx, [rsp+58h+arg_0]
0x18001b9ee  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001b9f3  nop
0x18001b9f4  mov     rcx, rdi; SRWLock
0x18001b9f7  call    ReleaseSRWLockExclusive_0
0x18001b9fc  jmp     short loc_18001BA1C
0x18001b9fe  mov     rcx, rdi; SRWLock
0x18001ba01  call    ReleaseSRWLockExclusive_0
0x18001ba06  cmp     qword ptr [rsi], 0
0x18001ba0a  jz      short loc_18001BA1C
0x18001ba0c  lea     r8, [rsp+58h+arg_0]
0x18001ba11  mov     rdx, rbx
0x18001ba14  mov     rcx, rsi
0x18001ba17  call    ??$invoke@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x18001ba1c  mov     rbx, [rsp+58h+arg_8]
0x18001ba21  mov     rsi, [rsp+58h+arg_10]
0x18001ba26  add     rsp, 50h
0x18001ba2a  pop     rdi
0x18001ba2b  retn
0x18001ba2c  lea     rcx, [rsp+58h+var_20]
0x18001ba31  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001ba36  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001ba39  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001ba3e  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::impl::slim_source_location const &)
0x18001ba43  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18001ba4a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001ba4f  call    _CxxThrowException_0
```

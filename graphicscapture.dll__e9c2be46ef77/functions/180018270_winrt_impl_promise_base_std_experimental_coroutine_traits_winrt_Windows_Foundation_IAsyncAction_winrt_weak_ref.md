# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::Completed(winrt::Windows::Foundation::AsyncActionCompletedHandler const &)

- ea: `0x180018270`
- end: `0x180018339`
- name: `?Completed@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXAEBUAsyncActionCompletedHandler@Foundation@Windows@3@@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001af90`

## callees

- `0x1800022f2`
- `0x180002384`
- `0x180002390`
- `0x1800039fc`
- `0x1800058c4`
- `0x1800065f0`
- `0x180013da4`
- `0x18001419c`
- `0x18001711c`
- `0x180018270`

## pseudocode

```c
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::Completed(
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
    v5 = winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler>((winrt::Windows::Foundation::IUnknown *)&v9);
    winrt::Windows::Foundation::IUnknown::operator=(a1 + 80, v5);
    if ( v9 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v9);
    ReleaseSRWLockExclusive_0(v4);
  }
}

```

## disassembly

```asm
0x180018270  mov     [rsp+arg_8], rbx
0x180018275  mov     [rsp+arg_10], rsi
0x18001827a  push    rdi
0x18001827b  sub     rsp, 50h
0x18001827f  mov     rsi, rdx
0x180018282  mov     rbx, rcx
0x180018285  lea     rdi, [rcx+48h]
0x180018289  mov     [rsp+58h+arg_0], rdi
0x18001828e  mov     rcx, rdi; SRWLock
0x180018291  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180018296  nop
0x180018297  cmp     byte ptr [rbx+64h], 0
0x18001829b  jnz     short loc_180018310
0x18001829d  mov     byte ptr [rbx+64h], 1
0x1800182a1  mov     eax, [rbx+60h]
0x1800182a4  mov     dword ptr [rsp+58h+arg_0], eax
0x1800182a8  test    eax, eax
0x1800182aa  jnz     short loc_1800182E2
0x1800182ac  mov     rdx, rsi
0x1800182af  lea     rcx, [rsp+58h+arg_0]; this
0x1800182b4  call    ??$make_agile_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@@impl@winrt@@YA?AUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU2341@@Z; winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &)
0x1800182b9  lea     rcx, [rbx+50h]
0x1800182bd  mov     rdx, rax
0x1800182c0  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800182c5  cmp     [rsp+58h+arg_0], 0
0x1800182cb  jz      short loc_1800182D8
0x1800182cd  lea     rcx, [rsp+58h+arg_0]
0x1800182d2  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800182d7  nop
0x1800182d8  mov     rcx, rdi; SRWLock
0x1800182db  call    ReleaseSRWLockExclusive_0
0x1800182e0  jmp     short loc_180018300
0x1800182e2  mov     rcx, rdi; SRWLock
0x1800182e5  call    ReleaseSRWLockExclusive_0
0x1800182ea  cmp     qword ptr [rsi], 0
0x1800182ee  jz      short loc_180018300
0x1800182f0  lea     r8, [rsp+58h+arg_0]
0x1800182f5  mov     rdx, rbx
0x1800182f8  mov     rcx, rsi
0x1800182fb  call    ??$invoke@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x180018300  mov     rbx, [rsp+58h+arg_8]
0x180018305  mov     rsi, [rsp+58h+arg_10]
0x18001830a  add     rsp, 50h
0x18001830e  pop     rdi
0x18001830f  retn
0x180018310  lea     rcx, [rsp+58h+var_20]
0x180018315  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001831a  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001831d  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180018322  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::impl::slim_source_location const &)
0x180018327  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18001832e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018333  call    _CxxThrowException_0
```

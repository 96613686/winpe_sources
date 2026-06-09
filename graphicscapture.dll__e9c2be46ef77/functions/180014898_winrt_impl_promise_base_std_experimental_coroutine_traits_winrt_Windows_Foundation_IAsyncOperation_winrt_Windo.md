# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::Completed(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem> const &)

- ea: `0x180014898`
- end: `0x180014961`
- name: `?Completed@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXAEBU?$AsyncOperationCompletedHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@3@@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015970`

## callees

- `0x1800022f2`
- `0x180002384`
- `0x180002390`
- `0x1800039fc`
- `0x1800058c4`
- `0x1800065f0`
- `0x180013da4`
- `0x180013de4`
- `0x18001419c`
- `0x180014898`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::Completed(
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
    v5 = winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>>((winrt::Windows::Foundation::IUnknown *)&v9);
    winrt::Windows::Foundation::IUnknown::operator=(a1 + 80, v5);
    if ( v9 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v9);
    ReleaseSRWLockExclusive_0(v4);
  }
}

```

## disassembly

```asm
0x180014898  mov     [rsp+arg_8], rbx
0x18001489d  mov     [rsp+arg_10], rsi
0x1800148a2  push    rdi
0x1800148a3  sub     rsp, 50h
0x1800148a7  mov     rsi, rdx
0x1800148aa  mov     rbx, rcx
0x1800148ad  lea     rdi, [rcx+48h]
0x1800148b1  mov     [rsp+58h+arg_0], rdi
0x1800148b6  mov     rcx, rdi; SRWLock
0x1800148b9  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800148be  nop
0x1800148bf  cmp     byte ptr [rbx+64h], 0
0x1800148c3  jnz     short loc_180014938
0x1800148c5  mov     byte ptr [rbx+64h], 1
0x1800148c9  mov     eax, [rbx+60h]
0x1800148cc  mov     dword ptr [rsp+58h+arg_0], eax
0x1800148d0  test    eax, eax
0x1800148d2  jnz     short loc_18001490A
0x1800148d4  mov     rdx, rsi
0x1800148d7  lea     rcx, [rsp+58h+arg_0]; this
0x1800148dc  call    ??$make_agile_delegate@U?$AsyncOperationCompletedHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@1@AEBU2341@@Z; winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem> const &)
0x1800148e1  lea     rcx, [rbx+50h]
0x1800148e5  mov     rdx, rax
0x1800148e8  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800148ed  cmp     [rsp+58h+arg_0], 0
0x1800148f3  jz      short loc_180014900
0x1800148f5  lea     rcx, [rsp+58h+arg_0]
0x1800148fa  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800148ff  nop
0x180014900  mov     rcx, rdi; SRWLock
0x180014903  call    ReleaseSRWLockExclusive_0
0x180014908  jmp     short loc_180014928
0x18001490a  mov     rcx, rdi; SRWLock
0x18001490d  call    ReleaseSRWLockExclusive_0
0x180014912  cmp     qword ptr [rsi], 0
0x180014916  jz      short loc_180014928
0x180014918  lea     r8, [rsp+58h+arg_0]
0x18001491d  mov     rdx, rbx
0x180014920  mov     rcx, rsi
0x180014923  call    ??$invoke@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@U?$weak_ref@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@4@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::weak_ref<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x180014928  mov     rbx, [rsp+58h+arg_8]
0x18001492d  mov     rsi, [rsp+58h+arg_10]
0x180014932  add     rsp, 50h
0x180014936  pop     rdi
0x180014937  retn
0x180014938  lea     rcx, [rsp+58h+var_20]
0x18001493d  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180014942  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180014945  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001494a  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::impl::slim_source_location const &)
0x18001494f  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180014956  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001495b  call    _CxxThrowException_0
```

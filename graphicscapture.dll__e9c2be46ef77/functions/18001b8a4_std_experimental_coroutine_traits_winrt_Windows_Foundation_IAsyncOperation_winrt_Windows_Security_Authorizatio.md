# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type::promise_type(void)

- ea: `0x18001b8a4`
- end: `0x18001b93b`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@QEAA@XZ`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bedc`

## callees

- `0x180002da8`
- `0x1800134a4`
- `0x180014120`
- `0x18001b880`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001b8f6`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001b8f6`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type::promise_type(
        __int64 a1)
{
  __int64 result; // rax

  winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>>(a1 + 16);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(a1 + 8);
  *(_QWORD *)a1 = &winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::cancellable_promise::cancellable_promise((winrt::cancellable_promise *)(a1 + 32));
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  __ExceptionPtrCreate((void *)(a1 + 56));
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  std::atomic<unsigned int>::atomic<unsigned int>(a1 + 96);
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type::`vftable';
  result = a1;
  *(_DWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x18001b8a4  push    rbx
0x18001b8a6  sub     rsp, 20h
0x18001b8aa  mov     rbx, rcx
0x18001b8ad  add     rcx, 10h
0x18001b8b1  call    ??0?$producers_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@V?$tuple@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@234@@4@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>>::producers_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,std::tuple<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>>(void)
0x18001b8b6  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001b8bd  lea     rcx, [rbx+8]
0x18001b8c1  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18001b8c6  lea     rcx, ??_7?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@6B@; const winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18001b8cd  mov     [rbx], rcx
0x18001b8d0  lea     rcx, [rbx+20h]; this
0x18001b8d4  call    ??0cancellable_promise@winrt@@QEAA@XZ; winrt::cancellable_promise::cancellable_promise(void)
0x18001b8d9  lea     rcx, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::`vftable'
0x18001b8e0  mov     [rbx], rcx
0x18001b8e3  lea     rcx, [rbx+38h]
0x18001b8e7  mov     qword ptr [rcx], 0
0x18001b8ee  mov     qword ptr [rcx+8], 0
0x18001b8f6  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001b8fc  mov     qword ptr [rbx+48h], 0
0x18001b904  lea     rcx, [rbx+60h]
0x18001b908  mov     qword ptr [rbx+50h], 0
0x18001b910  mov     qword ptr [rbx+58h], 0
0x18001b918  call    ??$?0I$0A@@?$atomic@I@std@@QEAA@XZ; std::atomic<uint>::atomic<uint>(void)
0x18001b91d  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type::`vftable'
0x18001b924  mov     byte ptr [rbx+64h], 0
0x18001b928  mov     [rbx], rax
0x18001b92b  mov     rax, rbx
0x18001b92e  mov     dword ptr [rbx+68h], 0
0x18001b935  add     rsp, 20h
0x18001b939  pop     rbx
0x18001b93a  retn
```

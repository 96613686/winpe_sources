# winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x18001bbd8`
- end: `0x18001bc11`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bba0`
- `0x18001bbc0`

## callees

- `0x180005834`
- `0x18001bb60`
- `0x18001bbd8`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  __int64 *RuntimeClassName; // rax
  __int64 v4; // rcx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  RuntimeClassName = (__int64 *)winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(
                                  a1,
                                  (__int64)&v6);
  v4 = *RuntimeClassName;
  *RuntimeClassName = 0;
  *a2 = v4;
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v6);
  return 0;
}

```

## disassembly

```asm
0x18001bbd8  push    rbx
0x18001bbda  sub     rsp, 20h
0x18001bbde  mov     rbx, rdx
0x18001bbe1  lea     rdx, [rsp+28h+arg_10]
0x18001bbe6  call    ?GetRuntimeClassName@?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@EEBA?AUhstring@2@XZ; winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(void)
0x18001bbeb  mov     rcx, [rax]
0x18001bbee  mov     qword ptr [rax], 0
0x18001bbf5  mov     [rbx], rcx
0x18001bbf8  lea     rcx, [rsp+28h+arg_10]
0x18001bbfd  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001bc02  xor     eax, eax
0x18001bc04  jmp     short loc_18001BC0A
0x18001bc06  mov     eax, [rsp+28h+arg_10]
0x18001bc0a  add     rsp, 20h
0x18001bc0e  pop     rbx
0x18001bc0f  retn
```

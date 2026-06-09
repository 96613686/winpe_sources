# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::Release(void)

- ea: `0x180015378`
- end: `0x1800153b0`
- name: `?Release@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAAKXZ`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015340`
- `0x180015360`

## callees

- `0x180015378`
- `0x180015e2c`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::Release(
        __int64 a1)
{
  unsigned int v2; // ebx

  v2 = winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>::subtract_reference(a1);
  if ( !v2 )
  {
    *(_QWORD *)(a1 + 120) |= 1uLL;
    (*(void (__fastcall **)(__int64))(a1 + 112))(a1 + 112);
  }
  return v2;
}

```

## disassembly

```asm
0x180015378  mov     [rsp+arg_0], rbx
0x18001537d  push    rdi
0x18001537e  sub     rsp, 20h
0x180015382  mov     rdi, rcx
0x180015385  call    ?subtract_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Foundation::IAsyncInfo>::subtract_reference(void)
0x18001538a  mov     ebx, eax
0x18001538c  test    eax, eax
0x18001538e  jnz     short loc_1800153A3
0x180015390  nop
0x180015391  lea     rcx, [rdi+70h]
0x180015395  or      qword ptr [rdi+78h], 1
0x18001539a  mov     rax, [rdi+70h]
0x18001539e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153a3  mov     eax, ebx
0x1800153a5  mov     rbx, [rsp+28h+arg_0]
0x1800153aa  add     rsp, 20h
0x1800153ae  pop     rdi
0x1800153af  retn
```

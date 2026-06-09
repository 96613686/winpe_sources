# winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>::operator=(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>> &&)

- ea: `0x18000eea0`
- end: `0x18000eedb`
- name: `??4?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e058`
- `0x180012444`
- `0x1800128c0`

## callees

- `0x180006594`
- `0x18000eea0`

## pseudocode

```c
unsigned int **__fastcall winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>::operator=(
        unsigned int **a1,
        unsigned int **a2)
{
  unsigned int *v4; // rax

  if ( a1 != a2 )
  {
    if ( *a1 )
      winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(a1);
    v4 = *a2;
    *a2 = 0;
    *a1 = v4;
  }
  return a1;
}

```

## disassembly

```asm
0x18000eea0  mov     [rsp+arg_0], rbx
0x18000eea5  push    rdi
0x18000eea6  sub     rsp, 20h
0x18000eeaa  mov     rdi, rdx
0x18000eead  mov     rbx, rcx
0x18000eeb0  cmp     rcx, rdx
0x18000eeb3  jz      short loc_18000EECD
0x18000eeb5  cmp     qword ptr [rcx], 0
0x18000eeb9  jz      short loc_18000EEC0
0x18000eebb  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x18000eec0  mov     rax, [rdi]
0x18000eec3  mov     qword ptr [rdi], 0
0x18000eeca  mov     [rbx], rax
0x18000eecd  mov     rax, rbx
0x18000eed0  mov     rbx, [rsp+28h+arg_0]
0x18000eed5  add     rsp, 20h
0x18000eed9  pop     rdi
0x18000eeda  retn
```

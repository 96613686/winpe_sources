# winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>(uint)

- ea: `0x18000e2f8`
- end: `0x18000e37a`
- name: `??$make_event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@1@I@Z`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012444`
- `0x1800128c0`

## callees

- `0x180002158`
- `0x180002754`
- `0x180003290`
- `0x1800065f0`
- `0x18000d920`
- `0x18000e2f8`

## pseudocode

```c
winrt::impl::atomic_ref_count **__fastcall winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>(
        winrt::impl::atomic_ref_count **a1,
        unsigned int a2)
{
  unsigned int v2; // esi
  winrt::impl::atomic_ref_count *v4; // rdi
  unsigned int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rbx
  winrt::impl::atomic_ref_count **v9; // [rsp+60h] [rbp+8h] BYREF

  v9 = a1;
  v2 = a2;
  v4 = (winrt::impl::atomic_ref_count *)operator new(8LL * a2 + 8);
  winrt::impl::atomic_ref_count::atomic_ref_count(v4, v5);
  *(_DWORD *)(v6 + 4) = v2;
  v9 = 0;
  if ( v2 )
  {
    v7 = v6 + 8;
    do
    {
      std::_Construct_in_place<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> const &>(
        v7,
        &v9);
      v7 += 8;
      --v2;
    }
    while ( v2 );
    std::_Destroy_range<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *>(
      v7,
      v7);
    if ( v9 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)&v9);
  }
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x18000e2f8  mov     [rsp+arg_0], rcx
0x18000e2fd  push    rbx
0x18000e2fe  push    rsi
0x18000e2ff  push    rdi
0x18000e300  push    r14
0x18000e302  sub     rsp, 38h
0x18000e306  mov     esi, edx
0x18000e308  mov     r14, rcx
0x18000e30b  lea     rcx, ds:8[rsi*8]; Size
0x18000e313  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e318  mov     rcx, rax; this
0x18000e31b  mov     rdi, rax
0x18000e31e  call    ??0atomic_ref_count@impl@winrt@@QEAA@I@Z; winrt::impl::atomic_ref_count::atomic_ref_count(uint)
0x18000e323  mov     [rcx+4], esi
0x18000e326  mov     [rsp+58h+arg_0], 0
0x18000e32f  test    esi, esi
0x18000e331  jz      short loc_18000E36A
0x18000e333  lea     rbx, [rcx+8]
0x18000e337  lea     rdx, [rsp+58h+arg_0]
0x18000e33c  mov     rcx, rbx
0x18000e33f  call    ??$_Construct_in_place@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@AEBU1234@@std@@YAXAEAU?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@AEBU1234@@Z; std::_Construct_in_place<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> const &>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> &,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> const &)
0x18000e344  add     rbx, 8
0x18000e348  add     esi, 0FFFFFFFFh
0x18000e34b  jnz     short loc_18000E337
0x18000e34d  mov     rdx, rbx
0x18000e350  mov     rcx, rbx
0x18000e353  call    ??$_Destroy_range@PEAU?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@PEAU1234@@std@@YAXPEAU?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@QEAU1234@@Z; std::_Destroy_range<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> * const)
0x18000e358  cmp     [rsp+58h+arg_0], 0
0x18000e35e  jz      short loc_18000E36A
0x18000e360  lea     rcx, [rsp+58h+arg_0]
0x18000e365  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18000e36a  mov     [r14], rdi
0x18000e36d  mov     rax, r14
0x18000e370  add     rsp, 38h
0x18000e374  pop     r14
0x18000e376  pop     rdi
0x18000e377  pop     rsi
0x18000e378  pop     rbx
0x18000e379  retn
```

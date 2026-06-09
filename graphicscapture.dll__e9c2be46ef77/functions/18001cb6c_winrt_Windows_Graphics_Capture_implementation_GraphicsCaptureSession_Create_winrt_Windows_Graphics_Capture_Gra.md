# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::Create(winrt::Windows::Graphics::Capture::GraphicsCaptureItem const &,winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *)

- ea: `0x18001cb6c`
- end: `0x18001cc2a`
- name: `?Create@GraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@SA?AU?$com_ptr@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@6@AEBUGraphicsCaptureItem@3456@PEAUDirect3D11CaptureFramePool@23456@@Z`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f51c`

## callees

- `0x180002158`
- `0x1800065f0`
- `0x1800125ec`
- `0x18001c638`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession *__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::Create(
        winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession *a1,
        const struct winrt::Windows::Graphics::Capture::GraphicsCaptureItem *a2,
        struct winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *a3)
{
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession *v6; // rsi
  unsigned int v7; // eax
  int v9; // [rsp+28h] [rbp-30h] BYREF
  __int128 v10; // [rsp+30h] [rbp-28h]
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession *v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession *v13; // [rsp+78h] [rbp+20h] BYREF

  v11 = a1;
  v6 = (winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession *)operator new(0xA0u);
  v11 = v6;
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::GraphicsCaptureSession(v6, a2, a3);
  *(_QWORD *)v6 = &winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession2,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession3,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession4,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession5,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession6,winrt::Windows::Foundation::IClosable,winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureSessionInternal,winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>>'};
  *((_QWORD *)v6 + 9) = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession,winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession2,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession3,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession4,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession5,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession6,winrt::Windows::Foundation::IClosable,winrt::cloaked<winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureSessionInternal>,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>>'};
  v13 = v6;
  v12 = 0;
  v9 = 0;
  v10 = 0;
  v7 = ((__int64 (__fastcall *)(winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession *, __int64 *, __int64 *))winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession2,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession3,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession4,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession5,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession6,winrt::Windows::Foundation::IClosable,winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureSessionInternal,winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>>'})(
         v6,
         &winrt::impl::guid_v<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>,
         &v12);
  winrt::check_hresult(&v11, v7, &v9);
  *(_QWORD *)a1 = v12;
  winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)&v13);
  return a1;
}

```

## disassembly

```asm
0x18001cb6c  mov     [rsp+arg_10], rbx
0x18001cb71  mov     [rsp+arg_0], rcx
0x18001cb76  push    rsi
0x18001cb77  push    rdi
0x18001cb78  push    r14
0x18001cb7a  sub     rsp, 40h
0x18001cb7e  mov     rbx, r8
0x18001cb81  mov     rdi, rdx
0x18001cb84  mov     r14, rcx
0x18001cb87  mov     ecx, 0A0h; Size
0x18001cb8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cb91  mov     rsi, rax
0x18001cb94  mov     [rsp+58h+arg_0], rax
0x18001cb99  mov     r8, rbx; struct winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *
0x18001cb9c  mov     rdx, rdi; struct winrt::Windows::Graphics::Capture::GraphicsCaptureItem *
0x18001cb9f  mov     rcx, rax; this
0x18001cba2  call    ??0GraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@QEAA@AEBUGraphicsCaptureItem@2345@PEAUDirect3D11CaptureFramePool@12345@@Z; winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::GraphicsCaptureSession(winrt::Windows::Graphics::Capture::GraphicsCaptureItem const &,winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *)
0x18001cba7  lea     rax, ??_7GraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@6B?$producers_base@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UGraphicsCaptureSession@Capture@Graphics@Windows@winrt@@UIGraphicsCaptureSession2@2345@UIGraphicsCaptureSession3@2345@UIGraphicsCaptureSession4@2345@UIGraphicsCaptureSession5@2345@UIGraphicsCaptureSession6@2345@UIClosable@Foundation@45@UIGraphicsCaptureSessionInternal@23Internal@45@UIGraphicsCaptureSessionInternalImpl@implementation@2345@@std@@@impl@5@@; const winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession2,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession3,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession4,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession5,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession6,winrt::Windows::Foundation::IClosable,winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureSessionInternal,winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>>'}
0x18001cbae  mov     [rsi], rax
0x18001cbb1  lea     rax, ??_7?$heap_implements@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B?$root_implements@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@U13456@UIGraphicsCaptureSession2@3456@UIGraphicsCaptureSession3@3456@UIGraphicsCaptureSession4@3456@UIGraphicsCaptureSession5@3456@UIGraphicsCaptureSession6@3456@UIClosable@Foundation@56@U?$cloaked@UIGraphicsCaptureSessionInternal@Capture@Graphics@Internal@Windows@winrt@@@6@U?$cloaked@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@6@@12@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession,winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession2,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession3,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession4,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession5,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession6,winrt::Windows::Foundation::IClosable,winrt::cloaked<winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureSessionInternal>,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>>'}
0x18001cbb8  mov     [rsi+48h], rax
0x18001cbbc  mov     [rsp+58h+arg_18], rsi
0x18001cbc1  mov     [rsp+58h+arg_8], 0
0x18001cbca  mov     [rsp+58h+var_30], 0
0x18001cbd2  xorps   xmm0, xmm0
0x18001cbd5  movdqu  [rsp+58h+var_28], xmm0
0x18001cbdb  lea     r8, [rsp+58h+arg_8]
0x18001cbe0  lea     rdx, ??$guid_v@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>
0x18001cbe7  mov     rcx, rsi
0x18001cbea  mov     rax, cs:??_7GraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@6B?$producers_base@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UGraphicsCaptureSession@Capture@Graphics@Windows@winrt@@UIGraphicsCaptureSession2@2345@UIGraphicsCaptureSession3@2345@UIGraphicsCaptureSession4@2345@UIGraphicsCaptureSession5@2345@UIGraphicsCaptureSession6@2345@UIClosable@Foundation@45@UIGraphicsCaptureSessionInternal@23Internal@45@UIGraphicsCaptureSessionInternalImpl@implementation@2345@@std@@@impl@5@@; const winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession2,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession3,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession4,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession5,winrt::Windows::Graphics::Capture::IGraphicsCaptureSession6,winrt::Windows::Foundation::IClosable,winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureSessionInternal,winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>>'}
0x18001cbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbf6  lea     r8, [rsp+58h+var_30]
0x18001cbfb  mov     edx, eax
0x18001cbfd  lea     rcx, [rsp+58h+arg_0]
0x18001cc02  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001cc07  mov     rax, [rsp+58h+arg_8]
0x18001cc0c  mov     [r14], rax
0x18001cc0f  lea     rcx, [rsp+58h+arg_18]
0x18001cc14  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001cc19  mov     rax, r14
0x18001cc1c  mov     rbx, [rsp+58h+arg_10]
0x18001cc21  add     rsp, 40h
0x18001cc25  pop     r14
0x18001cc27  pop     rdi
0x18001cc28  pop     rsi
0x18001cc29  retn
```

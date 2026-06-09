# winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::PresentThread(void *)

- ea: `0x180010da0`
- end: `0x180010eac`
- name: `?PresentThread@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@SAKPEAX@Z`
- size: `268`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002435`
- `0x180002441`
- `0x1800058c4`
- `0x180005d5c`
- `0x1800065f0`
- `0x1800075cc`
- `0x18000f254`
- `0x18000fa68`
- `0x180010da0`
- `0x180010eb4`
- `0x180012340`
- `0x1800125ac`
- `0x180012b6c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180010e15`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180010e15`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::PresentThread(
        LPVOID lpThreadParameter)
{
  __int64 v2; // r8
  HRESULT v3; // eax
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *v4; // rbx
  DWORD v5; // eax
  __int64 v7; // rax
  int v8; // edx
  unsigned int v9; // eax
  __int64 v10; // rax
  unsigned int v11; // r8d
  HANDLE Handles[2]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v13[40]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *v15; // [rsp+70h] [rbp+18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetImpl'::`2'::impl) )
  {
    v3 = CoInitializeEx_0(0, 0);
    v2 = (unsigned int)v3;
    if ( v3 < 0 )
    {
      v10 = winrt::impl::slim_source_location::current(v13);
      winrt::throw_hresult(v11, v10);
    }
  }
  v15 = 0;
  winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::attach(
    &v15,
    lpThreadParameter,
    v2);
  v4 = v15;
  Handles[0] = *((HANDLE *)v15 + 33);
  Handles[1] = *((HANDLE *)v15 + 19);
  while ( 1 )
  {
    v5 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( !v5 )
      break;
    if ( v5 != 1 )
    {
      v7 = winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::operator->(&v15);
      *(_DWORD *)(v7 + 308) = v8;
      v9 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\api\\lib\\direct3d11captureframepool.cpp",
        (const char *)v9,
        (int)Handles[0]);
    }
    winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::ProcessFrame(v4);
  }
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::CloseInternal(v4);
  winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)&v15);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetImpl'::`2'::impl) )
    WINRT_IMPL_CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180010da0  push    rbx
0x180010da2  sub     rsp, 50h
0x180010da6  mov     rbx, rcx
0x180010da9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix> `wil::Feature<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetImpl(void)'::`2'::impl
0x180010db0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::__private_IsEnabled(void)
0x180010db5  test    al, al
0x180010db7  jz      short loc_180010DCD
0x180010db9  xor     edx, edx; dwCoInit
0x180010dbb  xor     ecx, ecx; pvReserved
0x180010dbd  call    CoInitializeEx_0
0x180010dc2  mov     r8d, eax
0x180010dc5  test    eax, eax
0x180010dc7  js      loc_180010E96
0x180010dcd  mov     [rsp+58h+arg_9], 1
0x180010dd2  mov     [rsp+58h+arg_10], 0
0x180010ddb  mov     rdx, rbx
0x180010dde  lea     rcx, [rsp+58h+arg_10]
0x180010de3  call    ?attach@?$com_ptr@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@winrt@@QEAAXPEAUDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@2@@Z; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::attach(winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *)
0x180010de8  mov     rbx, [rsp+58h+arg_10]
0x180010ded  mov     rax, [rbx+108h]
0x180010df4  mov     [rsp+58h+Handles], rax; int
0x180010df9  mov     rax, [rbx+98h]
0x180010e00  mov     [rsp+58h+var_30], rax
0x180010e05  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180010e09  xor     r8d, r8d; bWaitAll
0x180010e0c  lea     rdx, [rsp+58h+Handles]; lpHandles
0x180010e11  lea     ecx, [r8+2]; nCount
0x180010e15  call    cs:__imp_WaitForMultipleObjects
0x180010e1b  mov     edx, eax
0x180010e1d  test    eax, eax
0x180010e1f  jz      short loc_180010E30
0x180010e21  cmp     eax, 1
0x180010e24  jnz     short loc_180010E62
0x180010e26  mov     rcx, rbx; this
0x180010e29  call    ?ProcessFrame@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXXZ; winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::ProcessFrame(void)
0x180010e2e  jmp     short loc_180010E05
0x180010e30  mov     rcx, rbx; this
0x180010e33  call    ?CloseInternal@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXXZ; winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::CloseInternal(void)
0x180010e38  nop
0x180010e39  lea     rcx, [rsp+58h+arg_10]
0x180010e3e  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180010e43  nop
0x180010e44  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix> `wil::Feature<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetImpl(void)'::`2'::impl
0x180010e4b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::__private_IsEnabled(void)
0x180010e50  test    al, al
0x180010e52  jz      short loc_180010E5A
0x180010e54  call    WINRT_IMPL_CoUninitialize
0x180010e59  nop
0x180010e5a  xor     eax, eax
0x180010e5c  add     rsp, 50h
0x180010e60  pop     rbx
0x180010e61  retn
0x180010e62  lea     rcx, [rsp+58h+arg_10]
0x180010e67  call    ??C?$com_ptr@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@winrt@@QEBA@XZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::operator->(void)
0x180010e6c  mov     [rax+134h], edx
0x180010e72  mov     ecx, 8000FFFFh
0x180010e77  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180010e7c  mov     r9d, eax; char *
0x180010e7f  mov     rcx, [rsp+58h]; this
0x180010e84  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\capture\\api"...
0x180010e8b  mov     edx, 2CBh; void *
0x180010e90  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180010e96  lea     rcx, [rsp+58h+var_28]
0x180010e9b  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180010ea0  mov     rdx, rax
0x180010ea3  mov     ecx, r8d
0x180010ea6  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

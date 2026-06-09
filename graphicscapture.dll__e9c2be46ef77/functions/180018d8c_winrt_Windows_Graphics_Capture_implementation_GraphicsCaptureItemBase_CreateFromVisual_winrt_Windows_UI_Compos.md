# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateFromVisual(winrt::Windows::UI::Composition::Visual const &)

- ea: `0x180018d8c`
- end: `0x180018e30`
- name: `?CreateFromVisual@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@AEBUVisual@Composition@UI@56@@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800042ac`

## callees

- `0x180002158`
- `0x180006610`
- `0x1800125ec`
- `0x180017300`
- `0x180018d8c`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x180018dc1`
- `CoreMessaging!CoreUICreate` at `0x180018dc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateFromVisual(
        __int64 *a1,
        __int64 a2)
{
  unsigned int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rax
  int v8; // [rsp+28h] [rbp-20h] BYREF
  __int128 v9; // [rsp+30h] [rbp-18h]
  __int64 *v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  v10 = a1;
  v11 = 0;
  v8 = 0;
  v9 = 0;
  v4 = CoreUICreate(&v11);
  winrt::check_hresult(&v10, v4, &v8);
  v5 = v11;
  v10 = (__int64 *)operator new(0x80u);
  v6 = winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>(
         v10,
         v5,
         a2);
  *a1 = (v6 + 8) & -(__int64)(v6 != 0);
  if ( v11 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v11);
  return a1;
}

```

## disassembly

```asm
0x180018d8c  mov     rax, rsp
0x180018d8f  mov     [rax+18h], rbx
0x180018d93  mov     [rax+20h], rsi
0x180018d97  mov     [rax+8], rcx
0x180018d9b  push    rdi
0x180018d9c  sub     rsp, 40h
0x180018da0  mov     rdi, rdx
0x180018da3  mov     rsi, rcx
0x180018da6  mov     qword ptr [rax+10h], 0
0x180018dae  mov     dword ptr [rax-20h], 0
0x180018db5  xorps   xmm0, xmm0
0x180018db8  movdqu  xmmword ptr [rax-18h], xmm0
0x180018dbd  lea     rcx, [rax+10h]
0x180018dc1  call    cs:__imp_CoreUICreate
0x180018dc7  lea     r8, [rsp+48h+var_20]
0x180018dcc  mov     edx, eax
0x180018dce  lea     rcx, [rsp+48h+arg_0]
0x180018dd3  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018dd8  mov     rbx, [rsp+48h+arg_8]
0x180018ddd  mov     ecx, 80h; Size
0x180018de2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018de7  mov     [rsp+48h+arg_0], rax
0x180018dec  mov     r8, rdi
0x180018def  mov     rdx, rbx
0x180018df2  mov     rcx, rax
0x180018df5  call    ??0?$heap_implements@UVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@QEAA@PEAUIMessageSession@@AEBUVisual@Composition@UI@Windows@2@@Z; winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>(IMessageSession *,winrt::Windows::UI::Composition::Visual const &)
0x180018dfa  nop
0x180018dfb  lea     rcx, [rax+8]
0x180018dff  neg     rax
0x180018e02  sbb     rax, rax
0x180018e05  and     rax, rcx
0x180018e08  mov     [rsi], rax
0x180018e0b  cmp     [rsp+48h+arg_8], 0
0x180018e11  jz      short loc_180018E1D
0x180018e13  lea     rcx, [rsp+48h+arg_8]
0x180018e18  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180018e1d  mov     rax, rsi
0x180018e20  mov     rbx, [rsp+48h+arg_10]
0x180018e25  mov     rsi, [rsp+48h+arg_18]
0x180018e2a  add     rsp, 40h
0x180018e2e  pop     rdi
0x180018e2f  retn
```

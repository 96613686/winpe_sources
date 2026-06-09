# winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem(winrt::Windows::Graphics::Capture::Server::CapturableItem const &)

- ea: `0x180018340`
- end: `0x180018453`
- name: `?CreateApiItemFromServerItem@implementation@Capture@Graphics@Windows@winrt@@YA?AUGraphicsCaptureItem@2345@AEBUCapturableItem@Server@2345@@Z`
- size: `275`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014e50`
- `0x18001845c`
- `0x180018694`
- `0x1800188e4`
- `0x180018b34`
- `0x180019b6c`
- `0x180019c8c`

## callees

- `0x180006610`
- `0x1800125ec`
- `0x180016e90`
- `0x180016ef0`
- `0x180016f58`
- `0x180016fb8`
- `0x180018340`
- `0x180019598`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x180018373`
- `CoreMessaging!CoreUICreate` at `0x180018373`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem(
        __int64 a1,
        __int64 a2)
{
  unsigned int v4; // eax
  __int64 v6; // [rsp+28h] [rbp-38h] BYREF
  int v7; // [rsp+30h] [rbp-30h] BYREF
  __int64 v8; // [rsp+38h] [rbp-28h]
  int v9; // [rsp+40h] [rbp-20h] BYREF
  __int128 v10; // [rsp+48h] [rbp-18h]
  __int64 v11; // [rsp+80h] [rbp+20h] BYREF
  __int64 v12; // [rsp+88h] [rbp+28h] BYREF

  v12 = 0;
  v9 = 0;
  v10 = 0;
  v4 = CoreUICreate(&v12);
  winrt::check_hresult(&v11, v4, &v9);
  winrt::impl::consume_Windows_Graphics_Capture_Server_ICapturableItem<winrt::Windows::Graphics::Capture::Server::ICapturableItem>::ItemInfo(
    a2,
    &v7);
  if ( v7 )
  {
    if ( v7 == 1 || v7 == 2 || v7 == 3 )
    {
      v11 = v8;
      v6 = v12;
      winrt::make<winrt::Windows::Graphics::Capture::implementation::MonitorServerGraphicsCaptureItem,IMessageSession *,winrt::Windows::Graphics::Capture::Server::CapturableItem const &,HMONITOR__ *>(
        a1,
        &v6,
        a2,
        &v11);
    }
    else if ( v7 == 4 )
    {
      v11 = v8;
      v6 = v12;
      winrt::make<winrt::Windows::Graphics::Capture::implementation::WindowedSwapChainServerGraphicsCaptureItem,IMessageSession *,winrt::Windows::Graphics::Capture::Server::CapturableItem const &,HWND__ *>(
        a1,
        &v6,
        a2,
        &v11);
    }
    else
    {
      v11 = v12;
      winrt::make<winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem,IMessageSession *,winrt::Windows::Graphics::Capture::Server::CapturableItem const &>(
        a1,
        &v11,
        a2);
    }
  }
  else
  {
    v11 = v8;
    v6 = v12;
    winrt::make<winrt::Windows::Graphics::Capture::implementation::WindowServerGraphicsCaptureItem,IMessageSession *,winrt::Windows::Graphics::Capture::Server::CapturableItem const &,HWND__ *>(
      a1,
      &v6,
      a2,
      &v11);
  }
  if ( v12 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v12);
  return a1;
}

```

## disassembly

```asm
0x180018340  mov     [rsp-8+arg_0], rbx
0x180018345  mov     [rsp-8+arg_8], rdi
0x18001834a  push    rbp
0x18001834b  mov     rbp, rsp
0x18001834e  sub     rsp, 60h
0x180018352  mov     rdi, rdx
0x180018355  mov     rbx, rcx
0x180018358  mov     [rbp+arg_18], 0
0x180018360  mov     [rbp+var_20], 0
0x180018367  xorps   xmm0, xmm0
0x18001836a  movdqu  [rbp+var_18], xmm0
0x18001836f  lea     rcx, [rbp+arg_18]
0x180018373  call    cs:__imp_CoreUICreate
0x180018379  lea     r8, [rbp+var_20]
0x18001837d  mov     edx, eax
0x18001837f  lea     rcx, [rbp+arg_10]
0x180018383  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018388  lea     rdx, [rbp+var_30]
0x18001838c  mov     rcx, rdi
0x18001838f  call    ?ItemInfo@?$consume_Windows_Graphics_Capture_Server_ICapturableItem@UICapturableItem@Server@Capture@Graphics@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Graphics_Capture_Server_ICapturableItem<winrt::Windows::Graphics::Capture::Server::ICapturableItem>::ItemInfo(void)
0x180018394  mov     ecx, [rbp+var_30]
0x180018397  test    ecx, ecx
0x180018399  jz      short loc_18001840C
0x18001839b  sub     ecx, 1
0x18001839e  jz      short loc_1800183E7
0x1800183a0  sub     ecx, 1
0x1800183a3  jz      short loc_1800183E7
0x1800183a5  sub     ecx, 1
0x1800183a8  jz      short loc_1800183E7
0x1800183aa  mov     r8, rdi
0x1800183ad  cmp     ecx, 1
0x1800183b0  mov     rcx, rbx
0x1800183b3  jz      short loc_1800183C8
0x1800183b5  mov     rax, [rbp+arg_18]
0x1800183b9  mov     [rbp+arg_10], rax
0x1800183bd  lea     rdx, [rbp+arg_10]
0x1800183c1  call    ??$make@UServerGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@PEAUIMessageSession@@AEBUCapturableItem@Server@3456@@winrt@@YA?A_P$$QEAPEAUIMessageSession@@AEBUCapturableItem@Server@Capture@Graphics@Windows@0@@Z
0x1800183c6  jmp     short loc_180018430
0x1800183c8  mov     rax, [rbp+var_28]
0x1800183cc  mov     [rbp+arg_10], rax
0x1800183d0  mov     rax, [rbp+arg_18]
0x1800183d4  mov     [rbp+var_38], rax
0x1800183d8  lea     r9, [rbp+arg_10]
0x1800183dc  lea     rdx, [rbp+var_38]
0x1800183e0  call    ??$make@UWindowedSwapChainServerGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@PEAUIMessageSession@@AEBUCapturableItem@Server@3456@PEAUHWND__@@@winrt@@YA?A_P$$QEAPEAUIMessageSession@@AEBUCapturableItem@Server@Capture@Graphics@Windows@0@$$QEAPEAUHWND__@@@Z
0x1800183e5  jmp     short loc_180018430
0x1800183e7  mov     rax, [rbp+var_28]
0x1800183eb  mov     [rbp+arg_10], rax
0x1800183ef  mov     rax, [rbp+arg_18]
0x1800183f3  mov     [rbp+var_38], rax
0x1800183f7  lea     r9, [rbp+arg_10]
0x1800183fb  mov     r8, rdi
0x1800183fe  lea     rdx, [rbp+var_38]
0x180018402  mov     rcx, rbx
0x180018405  call    ??$make@UMonitorServerGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@PEAUIMessageSession@@AEBUCapturableItem@Server@3456@PEAUHMONITOR__@@@winrt@@YA?A_P$$QEAPEAUIMessageSession@@AEBUCapturableItem@Server@Capture@Graphics@Windows@0@$$QEAPEAUHMONITOR__@@@Z
0x18001840a  jmp     short loc_180018430
0x18001840c  mov     rax, [rbp+var_28]
0x180018410  mov     [rbp+arg_10], rax
0x180018414  mov     rax, [rbp+arg_18]
0x180018418  mov     [rbp+var_38], rax
0x18001841c  lea     r9, [rbp+arg_10]
0x180018420  mov     r8, rdi
0x180018423  lea     rdx, [rbp+var_38]
0x180018427  mov     rcx, rbx
0x18001842a  call    ??$make@UWindowServerGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@PEAUIMessageSession@@AEBUCapturableItem@Server@3456@PEAUHWND__@@@winrt@@YA?A_P$$QEAPEAUIMessageSession@@AEBUCapturableItem@Server@Capture@Graphics@Windows@0@$$QEAPEAUHWND__@@@Z
0x18001842f  nop
0x180018430  cmp     [rbp+arg_18], 0
0x180018435  jz      short loc_180018440
0x180018437  lea     rcx, [rbp+arg_18]
0x18001843b  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180018440  mov     rax, rbx
0x180018443  mov     rbx, [rsp+60h+arg_0]
0x180018448  mov     rdi, [rsp+60h+arg_8]
0x18001844d  add     rsp, 60h
0x180018451  pop     rbp
0x180018452  retn
```

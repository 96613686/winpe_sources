# winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::CreateCaptureSession(winrt::Windows::Graphics::Capture::GraphicsCaptureItem const &)

- ea: `0x18000f51c`
- end: `0x18000f669`
- name: `?CreateCaptureSession@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAA?AUGraphicsCaptureSession@3456@AEBUGraphicsCaptureItem@3456@@Z`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f4c0`

## callees

- `0x1800022f2`
- `0x180003330`
- `0x1800033c0`
- `0x1800058c4`
- `0x1800065f0`
- `0x180006610`
- `0x180007c08`
- `0x18000de90`
- `0x18000e0e8`
- `0x18000f11c`
- `0x18000f51c`
- `0x18001cb6c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f544`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f544`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::CreateCaptureSession(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int *v12; // rax
  __int64 v13; // [rsp+28h] [rbp-38h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v15[24]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v16; // [rsp+80h] [rbp+20h] BYREF
  __int64 v17; // [rsp+98h] [rbp+38h] BYREF

  v6 = a1 + 192;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  v17 = v6;
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::CheckClosed((winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *)a1);
  if ( *(_BYTE *)(a1 + 304) )
  {
LABEL_14:
    winrt::impl::slim_source_location::current(v15);
    v12 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v16, -2147418113);
    winrt::hresult_error::hresult_error(pExceptionObject, *v12);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  v7 = (__int64 *)(a1 + 296);
  v8 = *(_QWORD *)(a1 + 296);
  v16 = v8;
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v16);
    goto LABEL_14;
  }
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::Create(&v16, a3, a1);
  v13 = 0;
  winrt::weak_ref<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>::from_com_ref<winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl> const &>(
    &v13,
    &v16);
  if ( v7 == &v13 )
  {
    v10 = v13;
  }
  else
  {
    if ( *v7 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)(a1 + 296));
    v9 = v13;
    v10 = 0;
    v13 = 0;
    *v7 = v9;
  }
  if ( v10 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v13);
  *(_BYTE *)(a1 + 304) = 1;
  winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>::as<winrt::Windows::Graphics::Capture::GraphicsCaptureSession>(
    &v16,
    a2);
  if ( v16 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v16);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
  return a2;
}

```

## disassembly

```asm
0x18000f51c  mov     [rsp-18h+arg_8], rbx
0x18000f521  mov     [rsp-18h+arg_10], rsi
0x18000f526  push    rbp
0x18000f527  push    rdi
0x18000f528  push    r14
0x18000f52a  mov     rbp, rsp
0x18000f52d  sub     rsp, 60h
0x18000f531  mov     r14, r8
0x18000f534  mov     rsi, rdx
0x18000f537  mov     rdi, rcx
0x18000f53a  lea     rbx, [rcx+0C0h]
0x18000f541  mov     rcx, rbx; lpCriticalSection
0x18000f544  call    cs:__imp_EnterCriticalSection
0x18000f54a  mov     [rbp+arg_18], rbx
0x18000f54e  mov     rcx, rdi; this
0x18000f551  call    ?CheckClosed@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXXZ; winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::CheckClosed(void)
0x18000f556  cmp     byte ptr [rdi+130h], 0
0x18000f55d  jnz     loc_18000F633
0x18000f563  lea     rbx, [rdi+128h]
0x18000f56a  mov     rcx, [rbx]
0x18000f56d  mov     [rbp+arg_0], rcx
0x18000f571  test    rcx, rcx
0x18000f574  jnz     loc_18000F61E
0x18000f57a  mov     r8, rdi
0x18000f57d  mov     rdx, r14
0x18000f580  lea     rcx, [rbp+arg_0]
0x18000f584  call    ?Create@GraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@SA?AU?$com_ptr@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@6@AEBUGraphicsCaptureItem@3456@PEAUDirect3D11CaptureFramePool@23456@@Z; winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::Create(winrt::Windows::Graphics::Capture::GraphicsCaptureItem const &,winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *)
0x18000f589  nop
0x18000f58a  mov     [rbp+var_38], 0
0x18000f592  lea     rdx, [rbp+arg_0]
0x18000f596  lea     rcx, [rbp+var_38]
0x18000f59a  call    ??$from_com_ref@AEBU?$com_ptr@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@winrt@@@?$weak_ref@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXAEBU?$com_ptr@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@1@@Z; winrt::weak_ref<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>::from_com_ref<winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl> const &>(winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl> const &)
0x18000f59f  nop
0x18000f5a0  lea     rax, [rbp+var_38]
0x18000f5a4  cmp     rbx, rax
0x18000f5a7  jz      short loc_18000F5C6
0x18000f5a9  cmp     qword ptr [rbx], 0
0x18000f5ad  jz      short loc_18000F5B7
0x18000f5af  mov     rcx, rbx
0x18000f5b2  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18000f5b7  mov     rcx, [rbp+var_38]
0x18000f5bb  xor     eax, eax
0x18000f5bd  mov     [rbp+var_38], rax
0x18000f5c1  mov     [rbx], rcx
0x18000f5c4  jmp     short loc_18000F5CA
0x18000f5c6  mov     rax, [rbp+var_38]
0x18000f5ca  test    rax, rax
0x18000f5cd  jz      short loc_18000F5D8
0x18000f5cf  lea     rcx, [rbp+var_38]
0x18000f5d3  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18000f5d8  mov     byte ptr [rdi+130h], 1
0x18000f5df  mov     rdx, rsi
0x18000f5e2  lea     rcx, [rbp+arg_0]
0x18000f5e6  call    ??$as@UGraphicsCaptureSession@Capture@Graphics@Windows@winrt@@@?$com_ptr@UIGraphicsCaptureSessionInternalImpl@implementation@Capture@Graphics@Windows@winrt@@@winrt@@QEBA?A_PXZ
0x18000f5eb  nop
0x18000f5ec  cmp     [rbp+arg_0], 0
0x18000f5f1  jz      short loc_18000F5FD
0x18000f5f3  lea     rcx, [rbp+arg_0]
0x18000f5f7  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18000f5fc  nop
0x18000f5fd  lea     rcx, [rbp+arg_18]
0x18000f601  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000f606  mov     rax, rsi
0x18000f609  lea     r11, [rsp+60h+var_s0]
0x18000f60e  mov     rbx, [r11+28h]
0x18000f612  mov     rsi, [r11+30h]
0x18000f616  mov     rsp, r11
0x18000f619  pop     r14
0x18000f61b  pop     rdi
0x18000f61c  pop     rbp
0x18000f61d  retn
0x18000f61e  mov     rax, [rcx]
0x18000f621  mov     rax, [rax+8]
0x18000f625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f62a  lea     rcx, [rbp+arg_0]
0x18000f62e  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18000f633  lea     rcx, [rbp+var_18]
0x18000f637  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18000f63c  mov     r8, rax
0x18000f63f  mov     edx, 8000FFFFh; int
0x18000f644  lea     rcx, [rbp+arg_0]; this
0x18000f648  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18000f64d  mov     edx, [rax]
0x18000f64f  lea     rcx, [rbp+pExceptionObject]
0x18000f653  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000f658  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18000f65f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f663  call    _CxxThrowException_0
```

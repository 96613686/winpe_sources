# winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::FrameArrived(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> const &)

- ea: `0x18000fb98`
- end: `0x18000fcb2`
- name: `?FrameArrived@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAA?AUevent_token@6@AEBU?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@56@@Z`
- size: `282`
- prototype: `__int64 __fastcall(winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012400`

## callees

- `0x1800022f2`
- `0x180003330`
- `0x1800033c0`
- `0x1800058c4`
- `0x180006610`
- `0x180007c08`
- `0x18000e1f4`
- `0x18000f11c`
- `0x18000fb98`
- `0x180012444`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fbc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fbc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PVOID *__fastcall winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::FrameArrived(
        winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *this,
        PVOID *a2,
        void (__fastcall ****a3)(_QWORD, __int64 *, __int64 *))
{
  char v6; // di
  char *v7; // rbx
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v9; // rax
  char v10; // bl
  __int64 *v11; // rax
  unsigned int *v13; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v15[24]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+80h] [rbp+30h] BYREF
  char *v17; // [rsp+98h] [rbp+48h] BYREF

  v6 = 0;
  LODWORD(v16) = 0;
  v7 = (char *)this + 192;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v17 = v7;
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::CheckClosed(this);
  if ( *((_QWORD *)this + 7) )
  {
    v9 = v16;
    goto LABEL_7;
  }
  v8 = *a3;
  if ( *a3 )
  {
    v16 = 0;
    (**v8)(v8, winrt::impl::guid_v<IAgileObject>, &v16);
    v9 = v16;
    v6 = 1;
    if ( !v16 )
      goto LABEL_5;
LABEL_7:
    v10 = 0;
    goto LABEL_8;
  }
  v9 = 0;
  v16 = 0;
  v6 = 1;
LABEL_5:
  v10 = 1;
LABEL_8:
  if ( (v6 & 1) != 0 && v9 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v16);
  if ( v10 )
  {
    winrt::impl::slim_source_location::current(v15);
    v13 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v16, -2147483620);
    winrt::hresult_error::hresult_error(pExceptionObject, *v13);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  v11 = (__int64 *)winrt::impl::make_agile_delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>((winrt::Windows::Foundation::IUnknown *)&v16);
  winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>::add_agile(
    (RTL_SRWLOCK *)this + 12,
    a2,
    v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
  return a2;
}

```

## disassembly

```asm
0x18000fb98  mov     [rsp-28h+arg_8], rbx
0x18000fb9d  push    rbp
0x18000fb9e  push    rsi
0x18000fb9f  push    rdi
0x18000fba0  push    r14
0x18000fba2  push    r15
0x18000fba4  mov     rbp, rsp
0x18000fba7  sub     rsp, 50h
0x18000fbab  mov     r14, r8
0x18000fbae  mov     r15, rdx
0x18000fbb1  mov     rsi, rcx
0x18000fbb4  xor     edi, edi
0x18000fbb6  mov     dword ptr [rbp+arg_0], edi
0x18000fbb9  lea     rbx, [rcx+0C0h]
0x18000fbc0  mov     rcx, rbx; lpCriticalSection
0x18000fbc3  call    cs:__imp_EnterCriticalSection
0x18000fbc9  mov     [rbp+arg_18], rbx
0x18000fbcd  mov     rcx, rsi; this
0x18000fbd0  call    ?CheckClosed@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXXZ; winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::CheckClosed(void)
0x18000fbd5  cmp     [rsi+38h], rdi
0x18000fbd9  jnz     short loc_18000FC22
0x18000fbdb  mov     rcx, [r14]
0x18000fbde  test    rcx, rcx
0x18000fbe1  jnz     short loc_18000FBEE
0x18000fbe3  xor     eax, eax
0x18000fbe5  mov     [rbp+arg_0], rax
0x18000fbe9  lea     edi, [rcx+1]
0x18000fbec  jmp     short loc_18000FC1E
0x18000fbee  mov     [rbp+arg_0], 0
0x18000fbf6  mov     rax, [rcx]
0x18000fbf9  lea     r8, [rbp+arg_0]
0x18000fbfd  lea     rdx, ??$guid_v@UIAgileObject@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IAgileObject>
0x18000fc04  mov     rax, [rax]
0x18000fc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc0c  mov     rax, [rbp+arg_0]
0x18000fc10  mov     [rbp+arg_0], rax
0x18000fc14  mov     edi, 1
0x18000fc19  test    rax, rax
0x18000fc1c  jnz     short loc_18000FC26
0x18000fc1e  mov     bl, 1
0x18000fc20  jmp     short loc_18000FC28
0x18000fc22  mov     rax, [rbp+arg_0]
0x18000fc26  xor     bl, bl
0x18000fc28  test    dil, 1
0x18000fc2c  jz      short loc_18000FC3C
0x18000fc2e  test    rax, rax
0x18000fc31  jz      short loc_18000FC3C
0x18000fc33  lea     rcx, [rbp+arg_0]
0x18000fc37  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18000fc3c  test    bl, bl
0x18000fc3e  jnz     short loc_18000FC7C
0x18000fc40  mov     rdx, r14
0x18000fc43  lea     rcx, [rbp+arg_0]; this
0x18000fc47  call    ??$make_agile_delegate@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@1@AEBU2341@@Z; winrt::impl::make_agile_delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> const &)
0x18000fc4c  lea     rcx, [rsi+60h]
0x18000fc50  mov     r8, rax
0x18000fc53  mov     rdx, r15
0x18000fc56  call    ?add_agile@?$event@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@winrt@@AEAA?AUevent_token@2@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@2@@Z; winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>::add_agile(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>)
0x18000fc5b  nop
0x18000fc5c  lea     rcx, [rbp+arg_18]
0x18000fc60  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000fc65  mov     rax, r15
0x18000fc68  mov     rbx, [rsp+50h+arg_8]
0x18000fc70  add     rsp, 50h
0x18000fc74  pop     r15
0x18000fc76  pop     r14
0x18000fc78  pop     rdi
0x18000fc79  pop     rsi
0x18000fc7a  pop     rbp
0x18000fc7b  retn
0x18000fc7c  lea     rcx, [rbp+var_18]
0x18000fc80  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18000fc85  mov     r8, rax
0x18000fc88  mov     edx, 8000001Ch; int
0x18000fc8d  lea     rcx, [rbp+arg_0]; this
0x18000fc91  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18000fc96  mov     edx, [rax]
0x18000fc98  lea     rcx, [rbp+pExceptionObject]
0x18000fc9c  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000fca1  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18000fca8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000fcac  call    _CxxThrowException_0
```

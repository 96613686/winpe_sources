# winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore::SetBuffersAndLuid(std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &,_LUID)

- ea: `0x180023870`
- end: `0x180023b97`
- name: `?SetBuffersAndLuid@ServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@UEAAXAEBV?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@U_LUID@@@Z`
- size: `807`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002720`
- `0x180003580`
- `0x180003620`
- `0x180006610`
- `0x18000ec20`
- `0x180012328`
- `0x1800125ec`
- `0x180022368`
- `0x18002247c`
- `0x1800225ac`
- `0x180022df0`
- `0x180023870`
- `0x1800240d0`
- `0x180024184`
- `0x18002424c`
- `0x180028010`

## import_xrefs

- `dcomp!__imp_DCompositionCreateBufferCollection` at `0x18002398e`
- `dcomp!__imp_DCompositionCreateBufferCollection` at `0x18002398e`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore::SetBuffersAndLuid(
        __int64 a1,
        unsigned __int64 **a2,
        __int64 a3)
{
  __int64 v5; // rbx
  unsigned int v6; // eax
  unsigned __int64 *v7; // r14
  unsigned __int64 *i; // rsi
  unsigned __int64 v9; // rax
  unsigned int BufferCollection; // eax
  unsigned int v11; // eax
  unsigned int DuplicationProcessHandle; // eax
  unsigned __int64 v13; // rax
  unsigned __int64 *v14; // r14
  unsigned __int64 *j; // rbx
  unsigned __int64 v16; // rax
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 (__fastcall ***v20)(_QWORD, __int64 *, __int64 *); // [rsp+30h] [rbp-29h] BYREF
  __int64 v21; // [rsp+38h] [rbp-21h] BYREF
  __int128 v22; // [rsp+40h] [rbp-19h] BYREF
  __int64 v23; // [rsp+50h] [rbp-9h]
  __int64 *v24; // [rsp+58h] [rbp-1h] BYREF
  void *v25[2]; // [rsp+60h] [rbp+7h] BYREF
  int v26; // [rsp+70h] [rbp+17h] BYREF
  __int128 v27; // [rsp+78h] [rbp+1Fh]
  unsigned __int64 v28; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v29; // [rsp+D8h] [rbp+7Fh] BYREF

  winrt::agile_ref<winrt::Windows::Graphics::Capture::Server::CaptureSession>::get(a1 + 8, &v20);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetImpl'::`2'::impl) )
  {
    if ( v20 )
    {
      v21 = 0;
      LODWORD(v24) = 0;
      *(_OWORD *)v25 = 0;
      v6 = (**v20)(v20, winrt::impl::guid_v<ICaptureSessionCom>, &v21);
      winrt::check_hresult(&v28, v6, &v24);
      v5 = v21;
    }
    else
    {
      v5 = 0;
    }
    v21 = v5;
    v22 = 0;
    v23 = 0;
    std::vector<void *>::reserve(&v22, a2[1] - *a2);
    v7 = a2[1];
    for ( i = *a2; i != v7; ++i )
    {
      v9 = *i;
      v28 = *i;
      if ( *((_QWORD *)&v22 + 1) == v23 )
      {
        std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64>(&v22, *((_QWORD *)&v22 + 1), &v28);
      }
      else
      {
        **((_QWORD **)&v22 + 1) = v9;
        *((_QWORD *)&v22 + 1) += 8LL;
      }
    }
    v29 = 0;
    v26 = 0;
    v27 = 0;
    v24 = &v29;
    v25[0] = 0;
    LOBYTE(v25[1]) = 1;
    BufferCollection = DCompositionCreateBufferCollection((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3, v22, a3, v25);
    winrt::check_hresult(&v28, BufferCollection, &v26);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v24);
    v26 = 0;
    v27 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, v29);
    winrt::check_hresult(&v28, v11, &v26);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
    if ( (_QWORD)v22 )
    {
      std::_Deallocate<16>(v22, (v23 - v22) & 0xFFFFFFFFFFFFFFF8uLL);
      v22 = 0;
      v23 = 0;
    }
    if ( v5 )
LABEL_27:
      winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v21);
  }
  else
  {
    winrt::Windows::Foundation::IUnknown::as<ICaptureSessionCom_Old>(&v20, &v21);
    v29 = 0;
    v26 = 0;
    v27 = 0;
    v24 = &v29;
    v25[0] = 0;
    LOBYTE(v25[1]) = 1;
    DuplicationProcessHandle = CreateDuplicationProcessHandle(v25);
    winrt::check_hresult(&v28, DuplicationProcessHandle, &v26);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v24);
    v22 = 0;
    v23 = 0;
    v13 = a2[1] - *a2;
    v28 = v13;
    if ( v13 )
    {
      if ( v13 > 0x1FFFFFFFFFFFFFFFLL )
        std::vector<winrt::com_ptr<ID3D11Texture2D>>::_Xlength();
      std::vector<unsigned __int64>::_Reallocate<0>(&v22, &v28);
    }
    v14 = a2[1];
    for ( j = *a2; j != v14; ++j )
    {
      v16 = *j;
      v28 = *j;
      if ( *((_QWORD *)&v22 + 1) == v23 )
      {
        std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64>(&v22, *((_QWORD *)&v22 + 1), &v28);
      }
      else
      {
        **((_QWORD **)&v22 + 1) = v16;
        *((_QWORD *)&v22 + 1) += 8LL;
      }
    }
    v26 = 0;
    v27 = 0;
    v17 = v21;
    v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v21 + 24LL))(
            v21,
            v29,
            (__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3);
    winrt::check_hresult(&v28, v18, &v26);
    if ( (_QWORD)v22 )
    {
      std::_Deallocate<16>(v22, (v23 - v22) & 0xFFFFFFFFFFFFFFF8uLL);
      v22 = 0;
      v23 = 0;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
    if ( v17 )
      goto LABEL_27;
  }
  return winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v20);
}

```

## disassembly

```asm
0x180023870  mov     [rsp-8+arg_8], rbx
0x180023875  push    rbp
0x180023876  push    rsi
0x180023877  push    rdi
0x180023878  push    r14
0x18002387a  push    r15
0x18002387c  lea     rbp, [rsp-37h]
0x180023881  sub     rsp, 90h
0x180023888  mov     rdi, r8
0x18002388b  mov     rsi, rdx
0x18002388e  xor     r15d, r15d
0x180023891  add     rcx, 8
0x180023895  lea     rdx, [rbp+57h+var_80]
0x180023899  call    ?get@?$agile_ref@UCaptureSession@Server@Capture@Graphics@Windows@winrt@@@winrt@@QEBA?AUCaptureSession@Server@Capture@Graphics@Windows@2@XZ; winrt::agile_ref<winrt::Windows::Graphics::Capture::Server::CaptureSession>::get(void)
0x18002389e  nop
0x18002389f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_BufferCollection@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_BufferCollection@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection> `wil::Feature<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetImpl(void)'::`2'::impl
0x1800238a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_BufferCollection@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::__private_IsEnabled(void)
0x1800238ab  test    al, al
0x1800238ad  jz      loc_180023A22
0x1800238b3  mov     rcx, [rbp+57h+var_80]
0x1800238b7  test    rcx, rcx
0x1800238ba  jnz     short loc_1800238C1
0x1800238bc  mov     ebx, r15d
0x1800238bf  jmp     short loc_1800238FA
0x1800238c1  mov     [rbp+57h+var_78], r15
0x1800238c5  mov     dword ptr [rbp+57h+var_58], r15d
0x1800238c9  xorps   xmm0, xmm0
0x1800238cc  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x1800238d1  mov     rax, [rcx]
0x1800238d4  lea     r8, [rbp+57h+var_78]
0x1800238d8  lea     rdx, ??$guid_v@UICaptureSessionCom@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<ICaptureSessionCom>
0x1800238df  mov     rax, [rax]
0x1800238e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238e7  lea     r8, [rbp+57h+var_58]
0x1800238eb  mov     edx, eax
0x1800238ed  lea     rcx, [rbp+57h+arg_0]
0x1800238f1  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800238f6  mov     rbx, [rbp+57h+var_78]
0x1800238fa  mov     [rbp+57h+var_78], rbx
0x1800238fe  xorps   xmm0, xmm0
0x180023901  movdqu  [rbp+57h+var_70], xmm0
0x180023906  mov     [rbp+57h+var_60], r15
0x18002390a  mov     rdx, [rsi+8]
0x18002390e  sub     rdx, [rsi]
0x180023911  sar     rdx, 3
0x180023915  lea     rcx, [rbp+57h+var_70]
0x180023919  call    ?reserve@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX_K@Z; std::vector<void *>::reserve(unsigned __int64)
0x18002391e  mov     r14, [rsi+8]
0x180023922  mov     rsi, [rsi]
0x180023925  jmp     short loc_180023953
0x180023927  mov     rax, [rsi]
0x18002392a  mov     [rbp+57h+arg_0], rax
0x18002392e  mov     rdx, qword ptr [rbp+57h+var_70+8]
0x180023932  cmp     rdx, [rbp+57h+var_60]
0x180023936  jz      short loc_180023942
0x180023938  mov     [rdx], rax
0x18002393b  add     qword ptr [rbp+57h+var_70+8], 8
0x180023940  jmp     short loc_18002394F
0x180023942  lea     r8, [rbp+57h+arg_0]
0x180023946  lea     rcx, [rbp+57h+var_70]
0x18002394a  call    ??$_Emplace_reallocate@_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_K$$QEA_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64>(unsigned __int64 * const,unsigned __int64 &&)
0x18002394f  add     rsi, 8
0x180023953  cmp     rsi, r14
0x180023956  jnz     short loc_180023927
0x180023958  mov     [rbp+57h+arg_18], r15
0x18002395c  mov     [rbp+57h+var_40], r15d
0x180023960  xorps   xmm0, xmm0
0x180023963  movdqu  [rbp+57h+var_38], xmm0
0x180023968  lea     rax, [rbp+57h+arg_18]
0x18002396c  mov     [rbp+57h+var_58], rax
0x180023970  mov     [rbp+57h+var_50], r15
0x180023974  mov     byte ptr [rbp+57h+var_50+8], 1
0x180023978  mov     rdx, qword ptr [rbp+57h+var_70]
0x18002397c  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x180023980  sub     rcx, rdx
0x180023983  sar     rcx, 3
0x180023987  lea     r9, [rbp+57h+var_50]
0x18002398b  mov     r8, rdi
0x18002398e  call    cs:__imp_DCompositionCreateBufferCollection
0x180023994  lea     r8, [rbp+57h+var_40]
0x180023998  mov     edx, eax
0x18002399a  lea     rcx, [rbp+57h+arg_0]
0x18002399e  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800239a3  nop
0x1800239a4  lea     rcx, [rbp+57h+var_58]
0x1800239a8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800239ad  mov     [rbp+57h+var_40], r15d
0x1800239b1  xorps   xmm0, xmm0
0x1800239b4  movdqu  [rbp+57h+var_38], xmm0
0x1800239b9  mov     rax, [rbx]
0x1800239bc  mov     rdx, [rbp+57h+arg_18]
0x1800239c0  mov     rcx, rbx
0x1800239c3  mov     rax, [rax+18h]
0x1800239c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239cc  lea     r8, [rbp+57h+var_40]
0x1800239d0  mov     edx, eax
0x1800239d2  lea     rcx, [rbp+57h+arg_0]
0x1800239d6  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800239db  nop
0x1800239dc  lea     rcx, [rbp+57h+arg_18]
0x1800239e0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800239e5  nop
0x1800239e6  mov     rcx, qword ptr [rbp+57h+var_70]
0x1800239ea  test    rcx, rcx
0x1800239ed  jz      short loc_180023A0B
0x1800239ef  mov     rdx, [rbp+57h+var_60]
0x1800239f3  sub     rdx, rcx
0x1800239f6  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800239fa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800239ff  xorps   xmm0, xmm0
0x180023a02  movdqu  [rbp+57h+var_70], xmm0
0x180023a07  mov     [rbp+57h+var_60], r15
0x180023a0b  test    rbx, rbx
0x180023a0e  jz      loc_180023B71
0x180023a14  lea     rcx, [rbp+57h+var_78]
0x180023a18  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180023a1d  jmp     loc_180023B71
0x180023a22  lea     rdx, [rbp+57h+var_78]
0x180023a26  lea     rcx, [rbp+57h+var_80]
0x180023a2a  call    ??$as@UICaptureSessionCom_Old@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x180023a2f  nop
0x180023a30  mov     [rbp+57h+arg_18], r15
0x180023a34  mov     [rbp+57h+var_40], r15d
0x180023a38  xorps   xmm0, xmm0
0x180023a3b  movdqu  [rbp+57h+var_38], xmm0
0x180023a40  lea     rax, [rbp+57h+arg_18]
0x180023a44  mov     [rbp+57h+var_58], rax
0x180023a48  mov     [rbp+57h+var_50], r15
0x180023a4c  mov     byte ptr [rbp+57h+var_50+8], 1
0x180023a50  lea     rcx, [rbp+57h+var_50]; void **
0x180023a54  call    ?CreateDuplicationProcessHandle@@YAJPEAPEAX@Z; CreateDuplicationProcessHandle(void * *)
0x180023a59  lea     r8, [rbp+57h+var_40]
0x180023a5d  mov     edx, eax
0x180023a5f  lea     rcx, [rbp+57h+arg_0]
0x180023a63  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023a68  nop
0x180023a69  lea     rcx, [rbp+57h+var_58]
0x180023a6d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180023a72  xorps   xmm0, xmm0
0x180023a75  movdqu  [rbp+57h+var_70], xmm0
0x180023a7a  mov     [rbp+57h+var_60], r15
0x180023a7e  mov     rax, [rsi+8]
0x180023a82  sub     rax, [rsi]
0x180023a85  sar     rax, 3
0x180023a89  mov     [rbp+57h+arg_0], rax
0x180023a8d  test    rax, rax
0x180023a90  jz      short loc_180023AB2
0x180023a92  mov     rcx, 1FFFFFFFFFFFFFFFh
0x180023a9c  cmp     rax, rcx
0x180023a9f  ja      loc_180023B91
0x180023aa5  lea     rdx, [rbp+57h+arg_0]
0x180023aa9  lea     rcx, [rbp+57h+var_70]
0x180023aad  call    ??$_Reallocate@$0A@@?$vector@_KV?$allocator@_K@std@@@std@@AEAAXAEA_K@Z; std::vector<unsigned __int64>::_Reallocate<0>(unsigned __int64 &)
0x180023ab2  mov     r14, [rsi+8]
0x180023ab6  mov     rbx, [rsi]
0x180023ab9  jmp     short loc_180023AE7
0x180023abb  mov     rax, [rbx]
0x180023abe  mov     [rbp+57h+arg_0], rax
0x180023ac2  mov     rdx, qword ptr [rbp+57h+var_70+8]
0x180023ac6  cmp     rdx, [rbp+57h+var_60]
0x180023aca  jz      short loc_180023AD6
0x180023acc  mov     [rdx], rax
0x180023acf  add     qword ptr [rbp+57h+var_70+8], 8
0x180023ad4  jmp     short loc_180023AE3
0x180023ad6  lea     r8, [rbp+57h+arg_0]
0x180023ada  lea     rcx, [rbp+57h+var_70]
0x180023ade  call    ??$_Emplace_reallocate@_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_K$$QEA_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64>(unsigned __int64 * const,unsigned __int64 &&)
0x180023ae3  add     rbx, 8
0x180023ae7  cmp     rbx, r14
0x180023aea  jnz     short loc_180023ABB
0x180023aec  mov     [rbp+57h+var_40], r15d
0x180023af0  xorps   xmm0, xmm0
0x180023af3  movdqu  [rbp+57h+var_38], xmm0
0x180023af8  mov     rbx, [rbp+57h+var_78]
0x180023afc  mov     r9, qword ptr [rbp+57h+var_70]
0x180023b00  mov     rax, [rbx]
0x180023b03  mov     r8, qword ptr [rbp+57h+var_70+8]
0x180023b07  sub     r8, r9
0x180023b0a  sar     r8, 3
0x180023b0e  mov     [rsp+0B0h+var_90], rdi
0x180023b13  mov     rdx, [rbp+57h+arg_18]
0x180023b17  mov     rcx, rbx
0x180023b1a  mov     rax, [rax+18h]
0x180023b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b23  lea     r8, [rbp+57h+var_40]
0x180023b27  mov     edx, eax
0x180023b29  lea     rcx, [rbp+57h+arg_0]
0x180023b2d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023b32  nop
0x180023b33  mov     rcx, qword ptr [rbp+57h+var_70]
0x180023b37  test    rcx, rcx
0x180023b3a  jz      short loc_180023B58
0x180023b3c  mov     rdx, [rbp+57h+var_60]
0x180023b40  sub     rdx, rcx
0x180023b43  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180023b47  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180023b4c  xorps   xmm0, xmm0
0x180023b4f  movdqu  [rbp+57h+var_70], xmm0
0x180023b54  mov     [rbp+57h+var_60], r15
0x180023b58  lea     rcx, [rbp+57h+arg_18]
0x180023b5c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023b61  nop
0x180023b62  test    rbx, rbx
0x180023b65  jz      short loc_180023B71
0x180023b67  lea     rcx, [rbp+57h+var_78]
0x180023b6b  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180023b70  nop
0x180023b71  lea     rcx, [rbp+57h+var_80]
0x180023b75  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023b7a  mov     rbx, [rsp+0B0h+arg_8]
0x180023b82  add     rsp, 90h
0x180023b89  pop     r15
0x180023b8b  pop     r14
0x180023b8d  pop     rdi
0x180023b8e  pop     rsi
0x180023b8f  pop     rbp
0x180023b90  retn
0x180023b91  call    ?_Xlength@?$vector@U?$com_ptr@UID3D11Texture2D@@@winrt@@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@CAXXZ; std::vector<winrt::com_ptr<ID3D11Texture2D>>::_Xlength(void)
```

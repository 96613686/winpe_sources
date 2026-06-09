# winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::SetBuffersAndLuid(std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &,_LUID)

- ea: `0x180024f50`
- end: `0x1800250ec`
- name: `?SetBuffersAndLuid@DCompVisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@UEAAXAEBV?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@U_LUID@@@Z`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002720`
- `0x180003620`
- `0x18000ec20`
- `0x1800125ec`
- `0x180022368`
- `0x1800240d0`
- `0x18002424c`
- `0x180024f50`
- `0x180028010`

## import_xrefs

- `dcomp!__imp_DCompositionCreateBufferCollection` at `0x180025021`
- `dcomp!__imp_DCompositionCreateBufferCollection` at `0x180025021`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::SetBuffersAndLuid(
        __int64 a1,
        __int64 **a2,
        __int64 a3)
{
  __int64 *v5; // rdi
  __int64 *i; // rbx
  __int64 v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 result; // rax
  unsigned int v11; // eax
  __int128 v12; // [rsp+30h] [rbp-50h] BYREF
  __int64 v13; // [rsp+40h] [rbp-40h]
  __int64 *v14; // [rsp+48h] [rbp-38h] BYREF
  __int64 v15; // [rsp+50h] [rbp-30h] BYREF
  char v16; // [rsp+58h] [rbp-28h]
  int v17; // [rsp+60h] [rbp-20h] BYREF
  __int128 v18; // [rsp+68h] [rbp-18h]
  __int64 v19; // [rsp+A8h] [rbp+28h] BYREF
  __int64 v20; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+38h] BYREF

  v20 = a3;
  v12 = 0;
  v13 = 0;
  std::vector<void *>::reserve(&v12, a2[1] - *a2);
  v5 = a2[1];
  for ( i = *a2; i != v5; ++i )
  {
    v7 = *i;
    v19 = *i;
    if ( *((_QWORD *)&v12 + 1) == v13 )
    {
      std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64>(&v12, *((_QWORD *)&v12 + 1), &v19);
    }
    else
    {
      **((_QWORD **)&v12 + 1) = v7;
      *((_QWORD *)&v12 + 1) += 8LL;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetImpl'::`2'::impl) )
  {
    v21 = 0;
    v17 = 0;
    v18 = 0;
    v14 = &v21;
    v15 = 0;
    v16 = 1;
    v8 = DCompositionCreateBufferCollection((__int64)(*((_QWORD *)&v12 + 1) - v12) >> 3, v12, v20, &v15);
    winrt::check_hresult(&v19, v8, &v17);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v14);
    v17 = 0;
    v18 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 8) + 88LL))(*(_QWORD *)(a1 + 8), v21);
    winrt::check_hresult(&v19, v9, &v17);
    result = wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
  }
  else
  {
    v17 = 0;
    v18 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(**(_QWORD **)(a1 + 8) + 40LL))(
            *(_QWORD *)(a1 + 8),
            &v20,
            (__int64)(*((_QWORD *)&v12 + 1) - v12) >> 3);
    result = winrt::check_hresult(&v19, v11, &v17);
  }
  if ( (_QWORD)v12 )
    return std::_Deallocate<16>(v12, (v13 - v12) & 0xFFFFFFFFFFFFFFF8uLL);
  return result;
}

```

## disassembly

```asm
0x180024f50  mov     [rsp-18h+arg_0], rbx
0x180024f55  mov     [rsp-18h+arg_10], r8
0x180024f5a  push    rbp
0x180024f5b  push    rsi
0x180024f5c  push    rdi
0x180024f5d  mov     rbp, rsp
0x180024f60  sub     rsp, 80h
0x180024f67  mov     rbx, rdx
0x180024f6a  mov     rsi, rcx
0x180024f6d  xorps   xmm0, xmm0
0x180024f70  movdqu  [rbp+var_50], xmm0
0x180024f75  mov     [rbp+var_40], 0
0x180024f7d  mov     rdx, [rdx+8]
0x180024f81  sub     rdx, [rbx]
0x180024f84  sar     rdx, 3
0x180024f88  lea     rcx, [rbp+var_50]
0x180024f8c  call    ?reserve@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX_K@Z; std::vector<void *>::reserve(unsigned __int64)
0x180024f91  mov     rdi, [rbx+8]
0x180024f95  mov     rbx, [rbx]
0x180024f98  jmp     short loc_180024FC6
0x180024f9a  mov     rax, [rbx]
0x180024f9d  mov     [rbp+arg_8], rax
0x180024fa1  mov     rdx, qword ptr [rbp+var_50+8]
0x180024fa5  cmp     rdx, [rbp+var_40]
0x180024fa9  jz      short loc_180024FB5
0x180024fab  mov     [rdx], rax
0x180024fae  add     qword ptr [rbp+var_50+8], 8
0x180024fb3  jmp     short loc_180024FC2
0x180024fb5  lea     r8, [rbp+arg_8]
0x180024fb9  lea     rcx, [rbp+var_50]
0x180024fbd  call    ??$_Emplace_reallocate@_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_K$$QEA_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64>(unsigned __int64 * const,unsigned __int64 &&)
0x180024fc2  add     rbx, 8
0x180024fc6  cmp     rbx, rdi
0x180024fc9  jnz     short loc_180024F9A
0x180024fcb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_BufferCollection@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_BufferCollection@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection> `wil::Feature<__WilFeatureTraits_Feature_Capture_BufferCollection>::GetImpl(void)'::`2'::impl
0x180024fd2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_BufferCollection@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_BufferCollection>::__private_IsEnabled(void)
0x180024fd7  test    al, al
0x180024fd9  jz      loc_18002507E
0x180024fdf  mov     [rbp+arg_18], 0
0x180024fe7  mov     [rbp+var_20], 0
0x180024fee  xorps   xmm0, xmm0
0x180024ff1  movdqu  [rbp+var_18], xmm0
0x180024ff6  lea     rax, [rbp+arg_18]
0x180024ffa  mov     [rbp+var_38], rax
0x180024ffe  mov     [rbp+var_30], 0
0x180025006  mov     [rbp+var_28], 1
0x18002500a  mov     rdx, qword ptr [rbp+var_50]
0x18002500e  mov     rcx, qword ptr [rbp+var_50+8]
0x180025012  sub     rcx, rdx
0x180025015  sar     rcx, 3
0x180025019  lea     r9, [rbp+var_30]
0x18002501d  mov     r8, [rbp+arg_10]
0x180025021  call    cs:__imp_DCompositionCreateBufferCollection
0x180025027  lea     r8, [rbp+var_20]
0x18002502b  mov     edx, eax
0x18002502d  lea     rcx, [rbp+arg_8]
0x180025031  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180025036  nop
0x180025037  lea     rcx, [rbp+var_38]
0x18002503b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180025040  mov     [rbp+var_20], 0
0x180025047  xorps   xmm0, xmm0
0x18002504a  movdqu  [rbp+var_18], xmm0
0x18002504f  mov     rcx, [rsi+8]
0x180025053  mov     rax, [rcx]
0x180025056  mov     rdx, [rbp+arg_18]
0x18002505a  mov     rax, [rax+58h]
0x18002505e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025063  lea     r8, [rbp+var_20]
0x180025067  mov     edx, eax
0x180025069  lea     rcx, [rbp+arg_8]
0x18002506d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180025072  nop
0x180025073  lea     rcx, [rbp+arg_18]
0x180025077  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002507c  jmp     short loc_1800250C0
0x18002507e  mov     [rbp+var_20], 0
0x180025085  xorps   xmm0, xmm0
0x180025088  movdqu  [rbp+var_18], xmm0
0x18002508d  mov     rcx, [rsi+8]
0x180025091  mov     r9, qword ptr [rbp+var_50]
0x180025095  mov     rax, [rcx]
0x180025098  mov     r8, qword ptr [rbp+var_50+8]
0x18002509c  sub     r8, r9
0x18002509f  sar     r8, 3
0x1800250a3  lea     rdx, [rbp+arg_10]
0x1800250a7  mov     rax, [rax+28h]
0x1800250ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250b0  lea     r8, [rbp+var_20]
0x1800250b4  mov     edx, eax
0x1800250b6  lea     rcx, [rbp+arg_8]
0x1800250ba  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800250bf  nop
0x1800250c0  mov     rcx, qword ptr [rbp+var_50]
0x1800250c4  test    rcx, rcx
0x1800250c7  jz      short loc_1800250D9
0x1800250c9  mov     rdx, [rbp+var_40]
0x1800250cd  sub     rdx, rcx
0x1800250d0  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800250d4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800250d9  mov     rbx, [rsp+80h+arg_0]
0x1800250e1  add     rsp, 80h
0x1800250e8  pop     rdi
0x1800250e9  pop     rsi
0x1800250ea  pop     rbp
0x1800250eb  retn
```

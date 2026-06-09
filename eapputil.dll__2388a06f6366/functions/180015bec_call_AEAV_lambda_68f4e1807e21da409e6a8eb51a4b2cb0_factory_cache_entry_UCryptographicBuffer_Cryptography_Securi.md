# ??$call@AEAV_lambda_68f4e1807e21da409e6a8eb51a4b2cb0_@@@?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_68f4e1807e21da409e6a8eb51a4b2cb0_@@@Z

- ea: `0x180015bec`
- end: `0x180015dda`
- name: `??$call@AEAV_lambda_68f4e1807e21da409e6a8eb51a4b2cb0_@@@?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_68f4e1807e21da409e6a8eb51a4b2cb0_@@@Z`
- size: `494`
- prototype: `signed __int64 *__fastcall(signed __int64, signed __int64 *, __int64 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019c04`

## callees

- `0x1800039d1`
- `0x1800083ec`
- `0x180010e04`
- `0x180015bec`
- `0x180015de0`
- `0x180033010`

## string_xrefs

- `0x180015c1e`: `Windows.Security.Cryptography.CryptographicBuffer`

## pseudocode

```c
signed __int64 *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::call<_lambda_68f4e1807e21da409e6a8eb51a4b2cb0_ &>(
        signed __int64 a1,
        signed __int64 *a2,
        __int64 **a3)
{
  __int64 v5; // rsi
  signed __int64 v6; // rbx
  __int64 *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  __int64 *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  int v14; // [rsp+40h] [rbp-40h] BYREF
  __int128 v15; // [rsp+48h] [rbp-38h]
  _DWORD *v16; // [rsp+58h] [rbp-28h] BYREF
  _DWORD v17[4]; // [rsp+60h] [rbp-20h] BYREF
  const wchar_t *v18; // [rsp+70h] [rbp-10h]
  signed __int64 v19; // [rsp+A0h] [rbp+20h] BYREF
  signed __int64 v20; // [rsp+B8h] [rbp+38h] BYREF

  v19 = a1;
  v5 = 1;
  v17[0] = 1;
  v17[1] = 49;
  v18 = L"Windows.Security.Cryptography.CryptographicBuffer";
  v16 = v17;
  v20 = 0;
  v14 = 0;
  v15 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v19,
    &v16,
    winrt::impl::guid_v<winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>,
    &v20);
  if ( (int)v19 < 0 )
    winrt::throw_hresult((unsigned int)v19, &v14);
  v6 = v20;
  v19 = v20;
  if ( !v20
    || (v20 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, signed __int64 *))v6)(
          v6,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v20),
        !v20) )
  {
    v10 = *a3;
    v11 = *((unsigned int *)*a3 + 2);
    v20 = 0;
    v14 = 0;
    v15 = 0;
    if ( (_DWORD)v11 )
      v5 = *v10;
    v12 = (*(__int64 (__fastcall **)(signed __int64, __int64, __int64, signed __int64 *))(*(_QWORD *)v6 + 72LL))(
            v6,
            v11,
            v5,
            &v20);
    if ( v12 < 0 )
      winrt::throw_hresult((unsigned int)v12, &v14);
    *a2 = v20;
    goto LABEL_15;
  }
  winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v20);
  _InterlockedAdd64(&qword_180043E68, 1u);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>,
          v6,
          0) )
  {
    v6 = 0;
    v19 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
  }
  v7 = *a3;
  v8 = *((unsigned int *)*a3 + 2);
  v20 = 0;
  v14 = 0;
  v15 = 0;
  if ( (_DWORD)v8 )
    v5 = *v7;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, signed __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
                                                                              + 72LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>,
         v8,
         v5,
         &v20);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v14);
  *a2 = v20;
  _InterlockedDecrement64(&qword_180043E68);
  if ( v6 )
LABEL_15:
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v19);
  return a2;
}

```

## disassembly

```asm
0x180015bec  mov     [rsp-18h+arg_8], rbx
0x180015bf1  mov     [rsp-18h+arg_10], rsi
0x180015bf6  mov     [rsp-18h+arg_0], rcx
0x180015bfb  push    rbp
0x180015bfc  push    rdi
0x180015bfd  push    r14
0x180015bff  mov     rbp, rsp
0x180015c02  sub     rsp, 80h
0x180015c09  mov     r14, r8
0x180015c0c  mov     rdi, rdx
0x180015c0f  mov     esi, 1
0x180015c14  mov     [rbp+var_20], esi
0x180015c17  mov     [rbp+var_1C], 31h ; '1'
0x180015c1e  lea     rax, aWindowsSecurit; "Windows.Security.Cryptography.Cryptogra"...
0x180015c25  mov     [rbp+var_10], rax
0x180015c29  lea     rax, [rbp+var_20]
0x180015c2d  mov     [rbp+var_28], rax
0x180015c31  mov     [rbp+arg_18], 0
0x180015c39  mov     [rbp+var_40], 0
0x180015c40  xorps   xmm0, xmm0
0x180015c43  movdqu  [rbp+var_38], xmm0
0x180015c48  lea     r9, [rbp+arg_18]
0x180015c4c  lea     r8, ??$guid_v@UICryptographicBufferStatics@Cryptography@Security@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
0x180015c53  lea     rdx, [rbp+var_28]
0x180015c57  lea     rcx, [rbp+arg_0]
0x180015c5b  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180015c60  mov     ecx, dword ptr [rbp+arg_0]
0x180015c63  test    ecx, ecx
0x180015c65  js      loc_180015DC4
0x180015c6b  mov     rbx, [rbp+arg_18]
0x180015c6f  mov     [rbp+arg_0], rbx
0x180015c73  test    rbx, rbx
0x180015c76  jz      loc_180015D4F
0x180015c7c  mov     [rbp+arg_18], 0
0x180015c84  mov     rax, [rbx]
0x180015c87  lea     r8, [rbp+arg_18]
0x180015c8b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180015c92  mov     rcx, rbx
0x180015c95  mov     rax, [rax]
0x180015c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c9d  mov     rax, [rbp+arg_18]
0x180015ca1  mov     [rbp+arg_18], rax
0x180015ca5  test    rax, rax
0x180015ca8  jz      loc_180015D4F
0x180015cae  lea     rcx, [rbp+arg_18]
0x180015cb2  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180015cb7  lea     rax, qword_180043E68
0x180015cbe  mov     [rbp+var_48], rax
0x180015cc2  lock add cs:qword_180043E68, rsi
0x180015cca  xor     eax, eax
0x180015ccc  lock cmpxchg cs:??$factory_cache_entry_v@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::winrt::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
0x180015cd5  jnz     short loc_180015CF0
0x180015cd7  xor     ebx, ebx
0x180015cd9  mov     [rbp+arg_0], rbx
0x180015cdd  lea     rdx, ListEntry; ListEntry
0x180015ce4  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180015ceb  call    WINRT_IMPL_InterlockedPushEntrySList
0x180015cf0  mov     rcx, [r14]
0x180015cf3  mov     edx, [rcx+8]
0x180015cf6  mov     [rbp+arg_18], 0
0x180015cfe  mov     r10, cs:??$factory_cache_entry_v@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::winrt::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
0x180015d05  mov     [rbp+var_40], 0
0x180015d0c  xorps   xmm0, xmm0
0x180015d0f  movdqu  [rbp+var_38], xmm0
0x180015d14  mov     rax, [r10]
0x180015d17  test    edx, edx
0x180015d19  jz      short loc_180015D1E
0x180015d1b  mov     rsi, [rcx]
0x180015d1e  lea     r9, [rbp+arg_18]
0x180015d22  mov     r8, rsi
0x180015d25  mov     rcx, r10
0x180015d28  mov     rax, [rax+48h]
0x180015d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d31  test    eax, eax
0x180015d33  js      loc_180015DCE
0x180015d39  mov     rax, [rbp+arg_18]
0x180015d3d  mov     [rdi], rax
0x180015d40  lock dec cs:qword_180043E68
0x180015d48  test    rbx, rbx
0x180015d4b  jz      short loc_180015D9D
0x180015d4d  jmp     short loc_180015D94
0x180015d4f  mov     rcx, [r14]
0x180015d52  mov     edx, [rcx+8]
0x180015d55  mov     [rbp+arg_18], 0
0x180015d5d  mov     [rbp+var_40], 0
0x180015d64  xorps   xmm0, xmm0
0x180015d67  movdqu  [rbp+var_38], xmm0
0x180015d6c  mov     rax, [rbx]
0x180015d6f  test    edx, edx
0x180015d71  jz      short loc_180015D76
0x180015d73  mov     rsi, [rcx]
0x180015d76  lea     r9, [rbp+arg_18]
0x180015d7a  mov     r8, rsi
0x180015d7d  mov     rcx, rbx
0x180015d80  mov     rax, [rax+48h]
0x180015d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d89  test    eax, eax
0x180015d8b  js      short loc_180015DB8
0x180015d8d  mov     rax, [rbp+arg_18]
0x180015d91  mov     [rdi], rax
0x180015d94  lea     rcx, [rbp+arg_0]
0x180015d98  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180015d9d  mov     rax, rdi
0x180015da0  lea     r11, [rsp+80h+var_s0]
0x180015da8  mov     rbx, [r11+28h]
0x180015dac  mov     rsi, [r11+30h]
0x180015db0  mov     rsp, r11
0x180015db3  pop     r14
0x180015db5  pop     rdi
0x180015db6  pop     rbp
0x180015db7  retn
0x180015db8  lea     rdx, [rbp+var_40]
0x180015dbc  mov     ecx, eax
0x180015dbe  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180015dc4  lea     rdx, [rbp+var_40]
0x180015dc8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180015dce  lea     rdx, [rbp+var_40]
0x180015dd2  mov     ecx, eax
0x180015dd4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

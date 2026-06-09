# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>,void>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x1800124e0`
- end: `0x180012557`
- name: `?QueryInterface@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `119`
- prototype: `__int64 __fastcall(unsigned __int64, _QWORD *, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000def0`
- `0x1800124e0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>,void>::QueryInterface(
        unsigned __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  volatile signed __int64 *v5; // rbx
  __int64 v6; // rax
  signed __int64 v7; // rax
  signed __int64 v8; // rtt

  v5 = (volatile signed __int64 *)((a1 - 32) & ((unsigned __int128)-(__int128)a1 >> 64));
  v6 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*v5 + 48))(v5);
  *a3 = v6;
  if ( !v6 )
    return winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapTlsClientCertificateValidationArgs,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationArgsFactory>::query_interface_common(
             v5,
             a2,
             a3);
  v7 = *((_QWORD *)v5 + 1);
  while ( v7 >= 0 )
  {
    v8 = v7;
    v7 = _InterlockedCompareExchange64(v5 + 1, v7 + 1, v7);
    if ( v8 == v7 )
      return 0;
  }
  _InterlockedIncrement((volatile signed __int32 *)(2 * v7 + 24));
  return 0;
}

```

## disassembly

```asm
0x1800124e0  mov     [rsp+arg_0], rbx
0x1800124e5  mov     [rsp+arg_8], rsi
0x1800124ea  push    rdi
0x1800124eb  sub     rsp, 20h
0x1800124ef  lea     rax, [rcx-20h]
0x1800124f3  mov     rdi, r8
0x1800124f6  neg     rcx
0x1800124f9  mov     rsi, rdx
0x1800124fc  sbb     rbx, rbx
0x1800124ff  and     rbx, rax
0x180012502  mov     rcx, rbx
0x180012505  mov     rax, [rbx]
0x180012508  mov     rax, [rax+30h]
0x18001250c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012511  mov     [rdi], rax
0x180012514  test    rax, rax
0x180012517  jz      short loc_180012539
0x180012519  mov     rax, [rbx+8]
0x18001251d  test    rax, rax
0x180012520  js      short loc_180012530
0x180012522  lea     rcx, [rax+1]
0x180012526  lock cmpxchg [rbx+8], rcx
0x18001252c  jnz     short loc_18001251D
0x18001252e  jmp     short loc_180012535
0x180012530  lock inc dword ptr [rax+rax+18h]
0x180012535  xor     eax, eax
0x180012537  jmp     short loc_180012547
0x180012539  mov     r8, rdi
0x18001253c  mov     rdx, rsi
0x18001253f  mov     rcx, rbx
0x180012542  call    ?query_interface_common@?$root_implements@UEapTlsClientCertificateValidationArgs@factory_implementation@Utility@Eap@Internal@Windows@winrt@@UIActivationFactory@Foundation@67@UIEapTlsClientCertificateValidationArgsFactory@34567@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapTlsClientCertificateValidationArgs,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationArgsFactory>::query_interface_common(winrt::guid const &,void * *)
0x180012547  mov     rbx, [rsp+28h+arg_0]
0x18001254c  mov     rsi, [rsp+28h+arg_8]
0x180012551  add     rsp, 20h
0x180012555  pop     rdi
0x180012556  retn
```

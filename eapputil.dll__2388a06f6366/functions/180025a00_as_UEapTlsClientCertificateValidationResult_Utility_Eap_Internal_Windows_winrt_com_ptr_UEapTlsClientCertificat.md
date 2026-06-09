# ??$as@UEapTlsClientCertificateValidationResult@Utility@Eap@Internal@Windows@winrt@@@?$com_ptr@UEapTlsClientCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@QEBA?A_PXZ

- ea: `0x180025a00`
- end: `0x180025aab`
- name: `??$as@UEapTlsClientCertificateValidationResult@Utility@Eap@Internal@Windows@winrt@@@?$com_ptr@UEapTlsClientCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@QEBA?A_PXZ`
- size: `171`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026bb4`
- `0x18002a2a8`

## callees

- `0x18000def0`
- `0x180010e04`
- `0x180025a00`
- `0x180033010`

## pseudocode

```c
__int64 *__fastcall winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult>::as<winrt::Windows::Internal::Eap::Utility::EapTlsClientCertificateValidationResult>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v2; // rbx
  __int64 v4; // rax
  signed __int64 v5; // rax
  signed __int64 v6; // rtt
  int v8; // eax
  int v9; // [rsp+28h] [rbp-20h] BYREF
  __int128 v10; // [rsp+30h] [rbp-18h]
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = (_QWORD *)*a1;
  if ( *a1 )
  {
    v4 = *v2;
    v11 = 0;
    v9 = 0;
    v10 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v4 + 48))(
            v2,
            &winrt::impl::guid_v<winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationResult>);
    if ( v11 )
    {
      v5 = v2[1];
      while ( v5 >= 0 )
      {
        v6 = v5;
        v5 = _InterlockedCompareExchange64(v2 + 1, v5 + 1, v5);
        if ( v6 == v5 )
          goto LABEL_7;
      }
      _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
    }
    else
    {
      v8 = winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapTlsClientCertificateValidationArgs,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationArgsFactory>::query_interface_common(
             v2,
             &winrt::impl::guid_v<winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationResult>,
             &v11);
      if ( v8 < 0 )
        winrt::throw_hresult((unsigned int)v8, &v9);
    }
LABEL_7:
    *a2 = v11;
  }
  else
  {
    *a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180025a00  mov     [rsp+arg_8], rbx
0x180025a05  push    rdi
0x180025a06  sub     rsp, 40h
0x180025a0a  mov     rbx, [rcx]
0x180025a0d  mov     rdi, rdx
0x180025a10  test    rbx, rbx
0x180025a13  jnz     short loc_180025A1A
0x180025a15  mov     [rdx], rbx
0x180025a18  jmp     short loc_180025A71
0x180025a1a  mov     rax, [rbx]
0x180025a1d  lea     rdx, ??$guid_v@UIEapTlsClientCertificateValidationResult@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationResult>
0x180025a24  xorps   xmm0, xmm0
0x180025a27  mov     [rsp+48h+arg_0], 0
0x180025a30  mov     rcx, rbx
0x180025a33  mov     [rsp+48h+var_20], 0
0x180025a3b  movdqu  [rsp+48h+var_18], xmm0
0x180025a41  mov     rax, [rax+30h]
0x180025a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a4a  mov     [rsp+48h+arg_0], rax
0x180025a4f  test    rax, rax
0x180025a52  jz      short loc_180025A86
0x180025a54  mov     rax, [rbx+8]
0x180025a58  test    rax, rax
0x180025a5b  js      short loc_180025A7F
0x180025a5d  lea     rcx, [rax+1]
0x180025a61  lock cmpxchg [rbx+8], rcx
0x180025a67  jnz     short loc_180025A58
0x180025a69  mov     rax, [rsp+48h+arg_0]
0x180025a6e  mov     [rdi], rax
0x180025a71  mov     rbx, [rsp+48h+arg_8]
0x180025a76  mov     rax, rdi
0x180025a79  add     rsp, 40h
0x180025a7d  pop     rdi
0x180025a7e  retn
0x180025a7f  lock inc dword ptr [rax+rax+18h]
0x180025a84  jmp     short loc_180025A69
0x180025a86  lea     r8, [rsp+48h+arg_0]
0x180025a8b  mov     rcx, rbx
0x180025a8e  lea     rdx, ??$guid_v@UIEapTlsClientCertificateValidationResult@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationResult>
0x180025a95  call    ?query_interface_common@?$root_implements@UEapTlsClientCertificateValidationArgs@factory_implementation@Utility@Eap@Internal@Windows@winrt@@UIActivationFactory@Foundation@67@UIEapTlsClientCertificateValidationArgsFactory@34567@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapTlsClientCertificateValidationArgs,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationArgsFactory>::query_interface_common(winrt::guid const &,void * *)
0x180025a9a  test    eax, eax
0x180025a9c  jns     short loc_180025A69
0x180025a9e  lea     rdx, [rsp+48h+var_20]
0x180025aa3  mov     ecx, eax
0x180025aa5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

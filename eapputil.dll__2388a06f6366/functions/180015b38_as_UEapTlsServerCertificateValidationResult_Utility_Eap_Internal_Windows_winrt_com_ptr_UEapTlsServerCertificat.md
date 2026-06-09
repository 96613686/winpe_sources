# ??$as@UEapTlsServerCertificateValidationResult@Utility@Eap@Internal@Windows@winrt@@@?$com_ptr@UEapTlsServerCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@QEBA?A_PXZ

- ea: `0x180015b38`
- end: `0x180015be3`
- name: `??$as@UEapTlsServerCertificateValidationResult@Utility@Eap@Internal@Windows@winrt@@@?$com_ptr@UEapTlsServerCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@QEBA?A_PXZ`
- size: `171`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001eda4`

## callees

- `0x18000def0`
- `0x180010e04`
- `0x180015b38`
- `0x180033010`

## pseudocode

```c
__int64 *__fastcall winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>::as<winrt::Windows::Internal::Eap::Utility::EapTlsServerCertificateValidationResult>(
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
            &winrt::impl::guid_v<winrt::Windows::Internal::Eap::Utility::IEapTlsServerCertificateValidationResult>);
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
             &winrt::impl::guid_v<winrt::Windows::Internal::Eap::Utility::IEapTlsServerCertificateValidationResult>,
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
0x180015b38  mov     [rsp+arg_8], rbx
0x180015b3d  push    rdi
0x180015b3e  sub     rsp, 40h
0x180015b42  mov     rbx, [rcx]
0x180015b45  mov     rdi, rdx
0x180015b48  test    rbx, rbx
0x180015b4b  jnz     short loc_180015B52
0x180015b4d  mov     [rdx], rbx
0x180015b50  jmp     short loc_180015BA9
0x180015b52  mov     rax, [rbx]
0x180015b55  lea     rdx, ??$guid_v@UIEapTlsServerCertificateValidationResult@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::Eap::Utility::IEapTlsServerCertificateValidationResult>
0x180015b5c  xorps   xmm0, xmm0
0x180015b5f  mov     [rsp+48h+arg_0], 0
0x180015b68  mov     rcx, rbx
0x180015b6b  mov     [rsp+48h+var_20], 0
0x180015b73  movdqu  [rsp+48h+var_18], xmm0
0x180015b79  mov     rax, [rax+30h]
0x180015b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b82  mov     [rsp+48h+arg_0], rax
0x180015b87  test    rax, rax
0x180015b8a  jz      short loc_180015BBE
0x180015b8c  mov     rax, [rbx+8]
0x180015b90  test    rax, rax
0x180015b93  js      short loc_180015BB7
0x180015b95  lea     rcx, [rax+1]
0x180015b99  lock cmpxchg [rbx+8], rcx
0x180015b9f  jnz     short loc_180015B90
0x180015ba1  mov     rax, [rsp+48h+arg_0]
0x180015ba6  mov     [rdi], rax
0x180015ba9  mov     rbx, [rsp+48h+arg_8]
0x180015bae  mov     rax, rdi
0x180015bb1  add     rsp, 40h
0x180015bb5  pop     rdi
0x180015bb6  retn
0x180015bb7  lock inc dword ptr [rax+rax+18h]
0x180015bbc  jmp     short loc_180015BA1
0x180015bbe  lea     r8, [rsp+48h+arg_0]
0x180015bc3  mov     rcx, rbx
0x180015bc6  lea     rdx, ??$guid_v@UIEapTlsServerCertificateValidationResult@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::Eap::Utility::IEapTlsServerCertificateValidationResult>
0x180015bcd  call    ?query_interface_common@?$root_implements@UEapTlsClientCertificateValidationArgs@factory_implementation@Utility@Eap@Internal@Windows@winrt@@UIActivationFactory@Foundation@67@UIEapTlsClientCertificateValidationArgsFactory@34567@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapTlsClientCertificateValidationArgs,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationArgsFactory>::query_interface_common(winrt::guid const &,void * *)
0x180015bd2  test    eax, eax
0x180015bd4  jns     short loc_180015BA1
0x180015bd6  lea     rdx, [rsp+48h+var_20]
0x180015bdb  mov     ecx, eax
0x180015bdd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

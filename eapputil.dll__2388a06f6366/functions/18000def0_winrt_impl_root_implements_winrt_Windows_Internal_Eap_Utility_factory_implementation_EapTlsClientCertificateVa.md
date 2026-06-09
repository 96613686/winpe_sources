# winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapTlsClientCertificateValidationArgs,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationArgsFactory>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18000def0`
- end: `0x18000e06e`
- name: `?query_interface_common@?$root_implements@UEapTlsClientCertificateValidationArgs@factory_implementation@Utility@Eap@Internal@Windows@winrt@@UIActivationFactory@Foundation@67@UIEapTlsClientCertificateValidationArgsFactory@34567@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(volatile signed __int64 *, _QWORD *, __int64 *)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d780`
- `0x18000d800`
- `0x1800124e0`
- `0x180015b38`
- `0x180025a00`

## callees

- `0x180003820`
- `0x18000cf00`
- `0x18000ddfc`
- `0x18000def0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapTlsClientCertificateValidationArgs,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationArgsFactory>::query_interface_common(
        volatile signed __int64 *a1,
        _QWORD *a2,
        __int64 *a3)
{
  signed __int64 v5; // rax
  signed __int64 v6; // rtt
  signed __int64 v7; // rtt
  __int64 weak_ref; // rax
  bool v9; // cf
  signed __int64 v11; // rtt
  __int64 v12; // rbx
  void *v13; // rax
  __int64 v14; // rdx

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown> && a2[1] == 0x46000000000000C0LL )
  {
    *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
    v5 = *((_QWORD *)a1 + 1);
    while ( v5 >= 0 )
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange64(a1 + 1, v5 + 1, v5);
      if ( v6 == v5 )
        return 0;
    }
  }
  else
  {
    if ( *a2 != winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable> || a2[1] != 0x901E1065AAD75A9CuLL )
    {
      if ( *a2 == winrt::impl::guid_v<winrt::impl::IWeakReferenceSource> && a2[1] == 0x46000000000000C0LL )
      {
        weak_ref = winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapAttribute,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapAttributeFactory>::make_weak_ref();
        *a3 = weak_ref;
        v9 = weak_ref != 0;
      }
      else
      {
        if ( *a2 == winrt::impl::guid_v<winrt::impl::IAgileObject> && a2[1] == 0x905B8FCA64EEFFC0uLL )
        {
          *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
          v5 = *((_QWORD *)a1 + 1);
          while ( v5 >= 0 )
          {
            v11 = v5;
            v5 = _InterlockedCompareExchange64(a1 + 1, v5 + 1, v5);
            if ( v11 == v5 )
              return 0;
          }
          goto LABEL_23;
        }
        if ( *a2 != winrt::impl::guid_v<winrt::impl::IMarshal> || a2[1] != 0x46000000000000C0LL )
          return (**(__int64 (__fastcall ***)(volatile signed __int64 *))a1)(a1);
        v12 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
        v13 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
        v14 = 0;
        if ( v13 )
          v14 = `winrt::impl::make_marshaler'::`2'::marshaler::marshaler(v13, v12);
        *a3 = v14;
        v9 = v14 != 0;
      }
      return v9 ? 0 : 0x8007000E;
    }
    *a3 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 56))(a1);
    v5 = *((_QWORD *)a1 + 1);
    while ( v5 >= 0 )
    {
      v7 = v5;
      v5 = _InterlockedCompareExchange64(a1 + 1, v5 + 1, v5);
      if ( v7 == v5 )
        return 0;
    }
  }
LABEL_23:
  _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
  return 0;
}

```

## disassembly

```asm
0x18000def0  mov     [rsp+arg_0], rbx
0x18000def5  push    rdi
0x18000def6  sub     rsp, 20h
0x18000defa  mov     rax, [rdx]
0x18000defd  mov     rdi, r8
0x18000df00  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18000df07  mov     rbx, rcx
0x18000df0a  jnz     short loc_18000DF46
0x18000df0c  mov     rax, [rdx+8]
0x18000df10  cmp     rax, cs:qword_180037F58
0x18000df17  jnz     short loc_18000DF46
0x18000df19  mov     rax, [rcx]
0x18000df1c  mov     rax, [rax+18h]
0x18000df20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df25  mov     [rdi], rax
0x18000df28  mov     rax, [rbx+8]
0x18000df2c  test    rax, rax
0x18000df2f  js      loc_18000DFF6
0x18000df35  lea     rcx, [rax+1]
0x18000df39  lock cmpxchg [rbx+8], rcx
0x18000df3f  jnz     short loc_18000DF2C
0x18000df41  jmp     loc_18000DFFB
0x18000df46  mov     rax, [rdx]
0x18000df49  cmp     rax, cs:??$guid_v@UIInspectable@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IInspectable>
0x18000df50  jnz     short loc_18000DF85
0x18000df52  mov     rax, [rdx+8]
0x18000df56  cmp     rax, cs:qword_180037F18
0x18000df5d  jnz     short loc_18000DF85
0x18000df5f  mov     rax, [rcx]
0x18000df62  mov     rax, [rax+38h]
0x18000df66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df6b  mov     [rdi], rax
0x18000df6e  mov     rax, [rbx+8]
0x18000df72  test    rax, rax
0x18000df75  js      short loc_18000DFF6
0x18000df77  lea     rcx, [rax+1]
0x18000df7b  lock cmpxchg [rbx+8], rcx
0x18000df81  jnz     short loc_18000DF72
0x18000df83  jmp     short loc_18000DFFB
0x18000df85  mov     rax, [rdx]
0x18000df88  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x18000df8f  jnz     short loc_18000DFB7
0x18000df91  mov     rax, [rdx+8]
0x18000df95  cmp     rax, cs:qword_180037F38
0x18000df9c  jnz     short loc_18000DFB7
0x18000df9e  call    ?make_weak_ref@?$root_implements@UEapAttribute@factory_implementation@Utility@Eap@Internal@Windows@winrt@@UIActivationFactory@Foundation@67@UIEapAttributeFactory@34567@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapAttribute,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapAttributeFactory>::make_weak_ref(void)
0x18000dfa3  mov     [rdi], rax
0x18000dfa6  neg     rax
0x18000dfa9  sbb     eax, eax
0x18000dfab  not     eax
0x18000dfad  and     eax, 8007000Eh
0x18000dfb2  jmp     loc_18000E063
0x18000dfb7  mov     rax, [rdx]
0x18000dfba  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000dfc1  jnz     short loc_18000DFFF
0x18000dfc3  mov     rax, [rdx+8]
0x18000dfc7  cmp     rax, cs:qword_180037FB8
0x18000dfce  jnz     short loc_18000DFFF
0x18000dfd0  mov     rax, [rcx]
0x18000dfd3  mov     rax, [rax+18h]
0x18000dfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfdc  mov     [rdi], rax
0x18000dfdf  mov     rax, [rbx+8]
0x18000dfe3  test    rax, rax
0x18000dfe6  js      short loc_18000DFF6
0x18000dfe8  lea     rcx, [rax+1]
0x18000dfec  lock cmpxchg [rbx+8], rcx
0x18000dff2  jnz     short loc_18000DFE3
0x18000dff4  jmp     short loc_18000DFFB
0x18000dff6  lock inc dword ptr [rax+rax+18h]
0x18000dffb  xor     eax, eax
0x18000dffd  jmp     short loc_18000E063
0x18000dfff  mov     rax, [rdx]
0x18000e002  cmp     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18000e009  jnz     short loc_18000E058
0x18000e00b  mov     rax, [rdx+8]
0x18000e00f  cmp     rax, cs:qword_180037F48
0x18000e016  jnz     short loc_18000E058
0x18000e018  mov     rax, [rcx]
0x18000e01b  mov     rax, [rax+18h]
0x18000e01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e024  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e02b  mov     ecx, 20h ; ' '; unsigned __int64
0x18000e030  mov     rbx, rax
0x18000e033  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e038  xor     edx, edx
0x18000e03a  test    rax, rax
0x18000e03d  jz      short loc_18000E04D
0x18000e03f  mov     rdx, rbx
0x18000e042  mov     rcx, rax
0x18000e045  call    ??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z; `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x18000e04a  mov     rdx, rax
0x18000e04d  mov     [rdi], rdx
0x18000e050  neg     rdx
0x18000e053  jmp     loc_18000DFA9
0x18000e058  mov     rax, [rcx]
0x18000e05b  mov     rax, [rax]
0x18000e05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e063  mov     rbx, [rsp+28h+arg_0]
0x18000e068  add     rsp, 20h
0x18000e06c  pop     rdi
0x18000e06d  retn
```

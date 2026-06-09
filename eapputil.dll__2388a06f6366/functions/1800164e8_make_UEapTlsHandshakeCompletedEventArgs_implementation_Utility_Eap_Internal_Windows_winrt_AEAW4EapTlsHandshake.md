# ??$make@UEapTlsHandshakeCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAW4EapTlsHandshakeStatus@34567@UEapTlsConnectedPeerInformation@34567@@winrt@@YA?A_PAEAW4EapTlsHandshakeStatus@Utility@Eap@Internal@Windows@0@$$QEAUEapTlsConnectedPeerInformation@23450@@Z

- ea: `0x1800164e8`
- end: `0x18001657a`
- name: `??$make@UEapTlsHandshakeCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAW4EapTlsHandshakeStatus@34567@UEapTlsConnectedPeerInformation@34567@@winrt@@YA?A_PAEAW4EapTlsHandshakeStatus@Utility@Eap@Internal@Windows@0@$$QEAUEapTlsConnectedPeerInformation@23450@@Z`
- size: `146`
- prototype: `_QWORD *__fastcall(_QWORD *, int *, __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018e1c`
- `0x18001e330`
- `0x1800294d0`

## callees

- `0x1800037dc`
- `0x1800164e8`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs,enum winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus &,winrt::Windows::Internal::Eap::Utility::EapTlsConnectedPeerInformation>(
        _QWORD *a1,
        int *a2,
        __int64 *a3)
{
  _QWORD *v6; // rdi
  int v7; // edx
  __int64 v8; // rcx

  v6 = operator new(0x28u);
  v7 = *a2;
  v6[2] = &winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapAttribute,winrt::Windows::Internal::Eap::Utility::IEapAttribute>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v6[1] = 1;
  *v6 = &winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs::`vftable';
  v6[4] = 0;
  *((_DWORD *)v6 + 6) = v7;
  if ( v6 + 4 != a3 )
  {
    v8 = *a3;
    v6[4] = *a3;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  }
  *a1 = v6 + 2;
  *v6 = &winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs::`vftable';
  return a1;
}

```

## disassembly

```asm
0x1800164e8  push    rbx
0x1800164ea  push    rsi
0x1800164eb  push    rdi
0x1800164ec  push    r14
0x1800164ee  sub     rsp, 38h
0x1800164f2  mov     rsi, rcx
0x1800164f5  mov     r14, r8
0x1800164f8  mov     ecx, 28h ; '('; Size
0x1800164fd  mov     rbx, rdx
0x180016500  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016505  mov     [rsp+58h+arg_0], rax
0x18001650a  mov     rdi, rax
0x18001650d  mov     edx, [rbx]
0x18001650f  lea     rbx, [rax+10h]
0x180016513  lea     rax, ??_7?$produce@UEapAttribute@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapAttribute@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapAttribute,winrt::Windows::Internal::Eap::Utility::IEapAttribute>::`vftable'
0x18001651a  mov     [rbx], rax
0x18001651d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180016524  mov     qword ptr [rdi+8], 1
0x18001652c  lea     rax, ??_7EapTlsHandshakeCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@6B@; const winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs::`vftable'
0x180016533  mov     [rdi], rax
0x180016536  lea     rax, [rdi+20h]
0x18001653a  mov     qword ptr [rax], 0
0x180016541  mov     [rdi+18h], edx
0x180016544  cmp     rax, r14
0x180016547  jz      short loc_180016560
0x180016549  mov     rcx, [r14]
0x18001654c  mov     [rax], rcx
0x18001654f  test    rcx, rcx
0x180016552  jz      short loc_180016560
0x180016554  mov     rax, [rcx]
0x180016557  mov     rax, [rax+8]
0x18001655b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016560  lea     rax, ??_7EapTlsHandshakeCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@6B@; const winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs::`vftable'
0x180016567  mov     [rsi], rbx
0x18001656a  mov     [rdi], rax
0x18001656d  mov     rax, rsi
0x180016570  add     rsp, 38h
0x180016574  pop     r14
0x180016576  pop     rdi
0x180016577  pop     rsi
0x180016578  pop     rbx
0x180016579  retn
```

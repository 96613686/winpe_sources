# winrt::make_self<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult,>(void)

- ea: `0x180025ba8`
- end: `0x180025c16`
- name: `??$make_self@UEapTlsClientCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@$$V@winrt@@YA?AU?$com_ptr@UEapTlsClientCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@0@XZ`
- size: `110`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180026bb4`
- `0x18002a2a8`

## callees

- `0x1800037dc`

## pseudocode

```c
_QWORD *__fastcall winrt::make_self<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult,>(
        _QWORD *a1)
{
  _OWORD *v3; // [rsp+40h] [rbp+8h]

  v3 = operator new(0x30u);
  *v3 = 0;
  v3[1] = 0;
  v3[2] = 0;
  *((_QWORD *)v3 + 2) = &winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult,winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationResult>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)v3 + 1) = 1;
  *((_QWORD *)v3 + 3) = 0;
  *((_QWORD *)v3 + 4) = 0;
  *((_QWORD *)v3 + 5) = 0;
  *(_QWORD *)v3 = &winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult>::`vftable';
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x180025ba8  push    rbx
0x180025baa  sub     rsp, 30h
0x180025bae  mov     rbx, rcx
0x180025bb1  mov     ecx, 30h ; '0'; Size
0x180025bb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025bbb  mov     [rsp+38h+arg_0], rax
0x180025bc0  lea     rcx, ??_7?$produce@UEapTlsClientCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapTlsClientCertificateValidationResult@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult,winrt::Windows::Internal::Eap::Utility::IEapTlsClientCertificateValidationResult>::`vftable'
0x180025bc7  xorps   xmm0, xmm0
0x180025bca  movups  xmmword ptr [rax], xmm0
0x180025bcd  movups  xmmword ptr [rax+10h], xmm0
0x180025bd1  movups  xmmword ptr [rax+20h], xmm0
0x180025bd5  mov     [rax+10h], rcx
0x180025bd9  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180025be0  mov     qword ptr [rax+8], 1
0x180025be8  lea     rcx, ??_7?$heap_implements@UEapTlsClientCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsClientCertificateValidationResult>::`vftable'
0x180025bef  mov     qword ptr [rax+18h], 0
0x180025bf7  mov     qword ptr [rax+20h], 0
0x180025bff  mov     qword ptr [rax+28h], 0
0x180025c07  mov     [rax], rcx
0x180025c0a  mov     [rbx], rax
0x180025c0d  mov     rax, rbx
0x180025c10  add     rsp, 30h
0x180025c14  pop     rbx
0x180025c15  retn
```

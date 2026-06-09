# winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs_base<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs,>::GetRuntimeClassName(void)

- ea: `0x18001c160`
- end: `0x18001c1a3`
- name: `?GetRuntimeClassName@?$EapTlsHandshakeCompletedEventArgs_base@UEapTlsHandshakeCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@$$V@implementation@Utility@Eap@Internal@Windows@winrt@@UEBA?AUhstring@7@XZ`
- size: `67`
- prototype: `struct winrt::impl::shared_hstring_header **__fastcall(__int64, struct winrt::impl::shared_hstring_header **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007eac`
- `0x180008274`

## string_xrefs

- `0x18001c17c`: `Windows.Internal.Eap.Utility.EapTlsHandshakeCompletedEventArgs`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs_base<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rbx

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x3E, (unsigned int)a2);
  memcpy_s((char *)v3 + 28, 0x7Cu, L"Windows.Internal.Eap.Utility.EapTlsHandshakeCompletedEventArgs", 0x7Cu);
  *a2 = v3;
  return a2;
}

```

## disassembly

```asm
0x18001c160  mov     [rsp+arg_0], rbx
0x18001c165  push    rdi
0x18001c166  sub     rsp, 30h
0x18001c16a  mov     ecx, 3Eh ; '>'; this
0x18001c16f  mov     rdi, rdx
0x18001c172  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001c177  mov     edx, 7Ch ; '|'; DestinationSize
0x18001c17c  lea     r8, aWindowsInterna_14; "Windows.Internal.Eap.Utility.EapTlsHand"...
0x18001c183  mov     r9d, edx; SourceSize
0x18001c186  mov     rbx, rax
0x18001c189  lea     rcx, [rax+1Ch]; Destination
0x18001c18d  call    memcpy_s
0x18001c192  mov     [rdi], rbx
0x18001c195  mov     rax, rdi
0x18001c198  mov     rbx, [rsp+38h+arg_0]
0x18001c19d  add     rsp, 30h
0x18001c1a1  pop     rdi
0x18001c1a2  retn
```

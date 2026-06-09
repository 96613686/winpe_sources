# winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs_base<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs,>::GetRuntimeClassName(void)

- ea: `0x18000f480`
- end: `0x18000f4c3`
- name: `?GetRuntimeClassName@?$EapMethodRunnerAuthenticationCompletedEventArgs_base@UEapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@$$V@implementation@Utility@Eap@Internal@Windows@winrt@@UEBA?AUhstring@7@XZ`
- size: `67`
- prototype: `struct winrt::impl::shared_hstring_header **__fastcall(__int64, struct winrt::impl::shared_hstring_header **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007eac`
- `0x180008274`

## string_xrefs

- `0x18000f49c`: `Windows.Internal.Eap.Utility.EapMethodRunnerAuthenticationCompletedEventArgs`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs_base<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rbx

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x4C, (unsigned int)a2);
  memcpy_s(
    (char *)v3 + 28,
    0x98u,
    L"Windows.Internal.Eap.Utility.EapMethodRunnerAuthenticationCompletedEventArgs",
    0x98u);
  *a2 = v3;
  return a2;
}

```

## disassembly

```asm
0x18000f480  mov     [rsp+arg_0], rbx
0x18000f485  push    rdi
0x18000f486  sub     rsp, 30h
0x18000f48a  mov     ecx, 4Ch ; 'L'; this
0x18000f48f  mov     rdi, rdx
0x18000f492  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000f497  mov     edx, 98h; DestinationSize
0x18000f49c  lea     r8, aWindowsInterna_3; "Windows.Internal.Eap.Utility.EapMethodR"...
0x18000f4a3  mov     r9d, edx; SourceSize
0x18000f4a6  mov     rbx, rax
0x18000f4a9  lea     rcx, [rax+1Ch]; Destination
0x18000f4ad  call    memcpy_s
0x18000f4b2  mov     [rdi], rbx
0x18000f4b5  mov     rax, rdi
0x18000f4b8  mov     rbx, [rsp+38h+arg_0]
0x18000f4bd  add     rsp, 30h
0x18000f4c1  pop     rdi
0x18000f4c2  retn
```

# winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::AllocateMasterSessionKeyIfNeeded(uchar)

- ea: `0x18002f574`
- end: `0x18002f61d`
- name: `?AllocateMasterSessionKeyIfNeeded@EapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAA?AV?$span@E$0?0@gsl@@E@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002f008`

## callees

- `0x1800083ec`
- `0x180008d90`
- `0x18001cd3c`
- `0x18002dd5c`
- `0x18002e598`
- `0x18002f574`

## string_xrefs

- `0x18002f606`: `onecoreuap\net\eaphost\eapputil\lib\eapmethodrunnerauthenticationcompletedeventargs.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::AllocateMasterSessionKeyIfNeeded(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3)
{
  __int64 *v3; // rbx
  unsigned int v4; // edi
  __int64 *v6; // rdi
  __int64 v7; // rcx
  unsigned int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF

  v3 = (__int64 *)(a1 + 48);
  v4 = 2 * a3;
  if ( *(_QWORD *)(a1 + 48) )
  {
    if ( (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(a1 + 48) != v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapmethodrunnerauthenticationcompletedeventargs.cpp",
        (const char *)0x7A,
        v9);
  }
  else
  {
    v6 = (__int64 *)winrt::Windows::Internal::Eap::Utility::implementation::AllocateEmptyIBuffer(&v11, v4);
    if ( v3 != v6 )
    {
      if ( *v3 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v3);
      v7 = *v6;
      *v6 = 0;
      *v3 = v7;
    }
    if ( v11 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v11);
  }
  winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(a2, v3);
  return a2;
}

```

## disassembly

```asm
0x18002f574  mov     [rsp+arg_8], rbx
0x18002f579  mov     [rsp+arg_10], rsi
0x18002f57e  push    rdi; unsigned int
0x18002f57f  sub     rsp, 20h
0x18002f583  movzx   edi, r8b
0x18002f587  lea     rbx, [rcx+30h]
0x18002f58b  add     edi, edi
0x18002f58d  mov     rsi, rdx
0x18002f590  cmp     qword ptr [rbx], 0
0x18002f594  jnz     short loc_18002F5F5
0x18002f596  mov     edx, edi
0x18002f598  lea     rcx, [rsp+28h+arg_0]
0x18002f59d  call    ?AllocateEmptyIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@K@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateEmptyIBuffer(ulong)
0x18002f5a2  mov     rdi, rax
0x18002f5a5  cmp     rbx, rax
0x18002f5a8  jz      short loc_18002F5C5
0x18002f5aa  cmp     qword ptr [rbx], 0
0x18002f5ae  jz      short loc_18002F5B8
0x18002f5b0  mov     rcx, rbx
0x18002f5b3  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f5b8  mov     rcx, [rdi]
0x18002f5bb  mov     qword ptr [rdi], 0
0x18002f5c2  mov     [rbx], rcx
0x18002f5c5  cmp     [rsp+28h+arg_0], 0
0x18002f5cb  jz      short loc_18002F5D7
0x18002f5cd  lea     rcx, [rsp+28h+arg_0]
0x18002f5d2  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f5d7  mov     rdx, rbx
0x18002f5da  mov     rcx, rsi
0x18002f5dd  call    ?GetBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AV?$span@$$CBE$0?0@gsl@@AEBUIBuffer@Streams@Storage@56@@Z; winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(winrt::Windows::Storage::Streams::IBuffer const &)
0x18002f5e2  mov     rbx, [rsp+28h+arg_8]
0x18002f5e7  mov     rax, rsi
0x18002f5ea  mov     rsi, [rsp+28h+arg_10]
0x18002f5ef  add     rsp, 20h
0x18002f5f3  pop     rdi
0x18002f5f4  retn
0x18002f5f5  mov     rcx, rbx
0x18002f5f8  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(void)
0x18002f5fd  cmp     eax, edi
0x18002f5ff  jz      short loc_18002F5D7
0x18002f601  mov     rcx, [rsp+28h]; this
0x18002f606  lea     r8, aOnecoreuapNetE_7; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002f60d  mov     r9d, 7Ah ; 'z'; char *
0x18002f613  lea     edx, [r9-2]; void *
0x18002f617  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```

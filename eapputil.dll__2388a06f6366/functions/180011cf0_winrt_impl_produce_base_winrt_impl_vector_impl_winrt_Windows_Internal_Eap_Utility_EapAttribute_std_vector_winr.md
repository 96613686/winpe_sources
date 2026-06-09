# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x180011cf0`
- end: `0x180011d74`
- name: `?GetIids@?$produce_base@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IIterable@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `132`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002d23`
- `0x180003942`
- `0x180011cf0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>,void>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // eax
  void *v7; // rax
  unsigned int v9; // [rsp+20h] [rbp-18h] BYREF
  void *Src; // [rsp+28h] [rbp-10h]

  v5 = (a1 - 32) & -(__int64)(a1 != 0);
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 32LL))(v5, &v9);
  v6 = v9;
  if ( v9 )
  {
    *a2 = v9;
    v7 = WINRT_IMPL_CoTaskMemAlloc(16LL * v6);
    *a3 = v7;
    if ( !v7 )
      return 2147942414LL;
    memmove_0(v7, Src, 16LL * v9);
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180011cf0  mov     [rsp+arg_0], rbx
0x180011cf5  push    rdi
0x180011cf6  sub     rsp, 30h
0x180011cfa  lea     rax, [rcx-20h]
0x180011cfe  mov     rdi, rdx
0x180011d01  neg     rcx
0x180011d04  lea     rdx, [rsp+38h+var_18]
0x180011d09  mov     rbx, r8
0x180011d0c  sbb     rcx, rcx
0x180011d0f  and     rcx, rax
0x180011d12  mov     rax, [rcx]
0x180011d15  mov     rax, [rax+20h]
0x180011d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d1e  mov     eax, [rsp+38h+var_18]
0x180011d22  test    eax, eax
0x180011d24  jz      short loc_180011D5A
0x180011d26  mov     ecx, eax
0x180011d28  mov     [rdi], eax
0x180011d2a  shl     rcx, 4; cb
0x180011d2e  call    WINRT_IMPL_CoTaskMemAlloc
0x180011d33  mov     [rbx], rax
0x180011d36  test    rax, rax
0x180011d39  jnz     short loc_180011D42
0x180011d3b  mov     eax, 8007000Eh
0x180011d40  jmp     short loc_180011D69
0x180011d42  mov     r8d, [rsp+38h+var_18]
0x180011d47  mov     rcx, rax; void *
0x180011d4a  mov     rdx, [rsp+38h+Src]; Src
0x180011d4f  shl     r8, 4; Size
0x180011d53  call    memmove_0
0x180011d58  jmp     short loc_180011D67
0x180011d5a  mov     dword ptr [rdi], 0
0x180011d60  mov     qword ptr [rbx], 0
0x180011d67  xor     eax, eax
0x180011d69  mov     rbx, [rsp+38h+arg_0]
0x180011d6e  add     rsp, 30h
0x180011d72  pop     rdi
0x180011d73  retn
```

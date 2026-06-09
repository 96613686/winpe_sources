# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x18000d410`
- end: `0x18000d494`
- name: `?GetIids@?$produce_base@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVectorView@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `132`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002d23`
- `0x180003942`
- `0x18000d410`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,void>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // eax
  void *v7; // rax
  unsigned int v9; // [rsp+20h] [rbp-18h] BYREF
  void *Src; // [rsp+28h] [rbp-10h]

  v5 = (a1 - 24) & -(__int64)(a1 != 0);
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
0x18000d410  mov     [rsp+arg_0], rbx
0x18000d415  push    rdi
0x18000d416  sub     rsp, 30h
0x18000d41a  lea     rax, [rcx-18h]
0x18000d41e  mov     rdi, rdx
0x18000d421  neg     rcx
0x18000d424  lea     rdx, [rsp+38h+var_18]
0x18000d429  mov     rbx, r8
0x18000d42c  sbb     rcx, rcx
0x18000d42f  and     rcx, rax
0x18000d432  mov     rax, [rcx]
0x18000d435  mov     rax, [rax+20h]
0x18000d439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d43e  mov     eax, [rsp+38h+var_18]
0x18000d442  test    eax, eax
0x18000d444  jz      short loc_18000D47A
0x18000d446  mov     ecx, eax
0x18000d448  mov     [rdi], eax
0x18000d44a  shl     rcx, 4; cb
0x18000d44e  call    WINRT_IMPL_CoTaskMemAlloc
0x18000d453  mov     [rbx], rax
0x18000d456  test    rax, rax
0x18000d459  jnz     short loc_18000D462
0x18000d45b  mov     eax, 8007000Eh
0x18000d460  jmp     short loc_18000D489
0x18000d462  mov     r8d, [rsp+38h+var_18]
0x18000d467  mov     rcx, rax; void *
0x18000d46a  mov     rdx, [rsp+38h+Src]; Src
0x18000d46f  shl     r8, 4; Size
0x18000d473  call    memmove_0
0x18000d478  jmp     short loc_18000D487
0x18000d47a  mov     dword ptr [rdi], 0
0x18000d480  mov     qword ptr [rbx], 0
0x18000d487  xor     eax, eax
0x18000d489  mov     rbx, [rsp+38h+arg_0]
0x18000d48e  add     rsp, 30h
0x18000d492  pop     rdi
0x18000d493  retn
```

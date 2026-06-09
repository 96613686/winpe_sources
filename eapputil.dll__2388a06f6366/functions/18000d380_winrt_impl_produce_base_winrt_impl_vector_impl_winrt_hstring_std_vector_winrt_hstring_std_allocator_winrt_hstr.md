# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x18000d380`
- end: `0x18000d404`
- name: `?GetIids@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `132`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002d23`
- `0x180003942`
- `0x18000d380`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,void>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // eax
  void *v7; // rax
  unsigned int v9; // [rsp+20h] [rbp-18h] BYREF
  void *Src; // [rsp+28h] [rbp-10h]

  v5 = (a1 - 16) & -(__int64)(a1 != 0);
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
0x18000d380  mov     [rsp+arg_0], rbx
0x18000d385  push    rdi
0x18000d386  sub     rsp, 30h
0x18000d38a  lea     rax, [rcx-10h]
0x18000d38e  mov     rdi, rdx
0x18000d391  neg     rcx
0x18000d394  lea     rdx, [rsp+38h+var_18]
0x18000d399  mov     rbx, r8
0x18000d39c  sbb     rcx, rcx
0x18000d39f  and     rcx, rax
0x18000d3a2  mov     rax, [rcx]
0x18000d3a5  mov     rax, [rax+20h]
0x18000d3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3ae  mov     eax, [rsp+38h+var_18]
0x18000d3b2  test    eax, eax
0x18000d3b4  jz      short loc_18000D3EA
0x18000d3b6  mov     ecx, eax
0x18000d3b8  mov     [rdi], eax
0x18000d3ba  shl     rcx, 4; cb
0x18000d3be  call    WINRT_IMPL_CoTaskMemAlloc
0x18000d3c3  mov     [rbx], rax
0x18000d3c6  test    rax, rax
0x18000d3c9  jnz     short loc_18000D3D2
0x18000d3cb  mov     eax, 8007000Eh
0x18000d3d0  jmp     short loc_18000D3F9
0x18000d3d2  mov     r8d, [rsp+38h+var_18]
0x18000d3d7  mov     rcx, rax; void *
0x18000d3da  mov     rdx, [rsp+38h+Src]; Src
0x18000d3df  shl     r8, 4; Size
0x18000d3e3  call    memmove_0
0x18000d3e8  jmp     short loc_18000D3F7
0x18000d3ea  mov     dword ptr [rdi], 0
0x18000d3f0  mov     qword ptr [rbx], 0
0x18000d3f7  xor     eax, eax
0x18000d3f9  mov     rbx, [rsp+38h+arg_0]
0x18000d3fe  add     rsp, 30h
0x18000d402  pop     rdi
0x18000d403  retn
```

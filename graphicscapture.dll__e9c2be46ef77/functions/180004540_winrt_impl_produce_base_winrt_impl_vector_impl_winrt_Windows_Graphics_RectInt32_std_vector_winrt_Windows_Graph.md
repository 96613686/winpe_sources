# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Graphics::RectInt32>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x180004540`
- end: `0x1800045c6`
- name: `?GetIids@?$produce_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@U?$IIterable@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000241d`
- `0x180002844`
- `0x180004540`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Graphics::RectInt32>,void>::GetIids(
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
    std::_Copy_memmove<winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *>(
      Src,
      (__int64)Src + 16 * v9,
      v7);
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
0x180004540  mov     [rsp+arg_0], rbx
0x180004545  push    rdi
0x180004546  sub     rsp, 30h
0x18000454a  lea     rax, [rcx-20h]
0x18000454e  mov     rdi, rdx
0x180004551  neg     rcx
0x180004554  lea     rdx, [rsp+38h+var_18]
0x180004559  mov     rbx, r8
0x18000455c  sbb     rcx, rcx
0x18000455f  and     rcx, rax
0x180004562  mov     rax, [rcx]
0x180004565  mov     rax, [rax+20h]
0x180004569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000456e  mov     eax, [rsp+38h+var_18]
0x180004572  test    eax, eax
0x180004574  jz      short loc_1800045AC
0x180004576  mov     ecx, eax
0x180004578  mov     [rdi], eax
0x18000457a  shl     rcx, 4; cb
0x18000457e  call    WINRT_IMPL_CoTaskMemAlloc
0x180004583  mov     [rbx], rax
0x180004586  test    rax, rax
0x180004589  jnz     short loc_180004592
0x18000458b  mov     eax, 8007000Eh
0x180004590  jmp     short loc_1800045BB
0x180004592  mov     edx, [rsp+38h+var_18]
0x180004596  mov     r8, rax
0x180004599  mov     rcx, [rsp+38h+Src]; Src
0x18000459e  shl     rdx, 4
0x1800045a2  add     rdx, rcx
0x1800045a5  call    ??$_Copy_memmove@PEAURectInt32@Graphics@Windows@winrt@@PEAU1234@@std@@YAPEAURectInt32@Graphics@Windows@winrt@@PEAU1234@00@Z; std::_Copy_memmove<winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *>(winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *)
0x1800045aa  jmp     short loc_1800045B9
0x1800045ac  mov     dword ptr [rdi], 0
0x1800045b2  mov     qword ptr [rbx], 0
0x1800045b9  xor     eax, eax
0x1800045bb  mov     rbx, [rsp+38h+arg_0]
0x1800045c0  add     rsp, 30h
0x1800045c4  pop     rdi
0x1800045c5  retn
```

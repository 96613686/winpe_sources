# winrt::impl::produce_base<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x180004420`
- end: `0x1800044a6`
- name: `?GetIids@?$produce_base@Uiterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000241d`
- `0x180002844`
- `0x180004420`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>,void>::GetIids(
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
0x180004420  mov     [rsp+arg_0], rbx
0x180004425  push    rdi
0x180004426  sub     rsp, 30h
0x18000442a  lea     rax, [rcx-10h]
0x18000442e  mov     rdi, rdx
0x180004431  neg     rcx
0x180004434  lea     rdx, [rsp+38h+var_18]
0x180004439  mov     rbx, r8
0x18000443c  sbb     rcx, rcx
0x18000443f  and     rcx, rax
0x180004442  mov     rax, [rcx]
0x180004445  mov     rax, [rax+20h]
0x180004449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000444e  mov     eax, [rsp+38h+var_18]
0x180004452  test    eax, eax
0x180004454  jz      short loc_18000448C
0x180004456  mov     ecx, eax
0x180004458  mov     [rdi], eax
0x18000445a  shl     rcx, 4; cb
0x18000445e  call    WINRT_IMPL_CoTaskMemAlloc
0x180004463  mov     [rbx], rax
0x180004466  test    rax, rax
0x180004469  jnz     short loc_180004472
0x18000446b  mov     eax, 8007000Eh
0x180004470  jmp     short loc_18000449B
0x180004472  mov     edx, [rsp+38h+var_18]
0x180004476  mov     r8, rax
0x180004479  mov     rcx, [rsp+38h+Src]; Src
0x18000447e  shl     rdx, 4
0x180004482  add     rdx, rcx
0x180004485  call    ??$_Copy_memmove@PEAURectInt32@Graphics@Windows@winrt@@PEAU1234@@std@@YAPEAURectInt32@Graphics@Windows@winrt@@PEAU1234@00@Z; std::_Copy_memmove<winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *>(winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *)
0x18000448a  jmp     short loc_180004499
0x18000448c  mov     dword ptr [rdi], 0
0x180004492  mov     qword ptr [rbx], 0
0x180004499  xor     eax, eax
0x18000449b  mov     rbx, [rsp+38h+arg_0]
0x1800044a0  add     rsp, 30h
0x1800044a4  pop     rdi
0x1800044a5  retn
```

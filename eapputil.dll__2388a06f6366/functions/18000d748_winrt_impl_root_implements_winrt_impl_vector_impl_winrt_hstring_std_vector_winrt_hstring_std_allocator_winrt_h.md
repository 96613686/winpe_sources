# winrt::impl::root_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::NonDelegatingGetTrustLevel(winrt::Windows::Foundation::TrustLevel *)

- ea: `0x18000d748`
- end: `0x18000d76e`
- name: `?NonDelegatingGetTrustLevel@?$root_implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@Uhstring@winrt@@@5673@U?$IIterable@Uhstring@winrt@@@5673@@impl@winrt@@IEAAHPEAW4TrustLevel@Foundation@Windows@3@@Z`
- size: `38`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d590`
- `0x18000d5b0`
- `0x180012160`

## callees

- `0x18000d748`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::NonDelegatingGetTrustLevel(
        __int64 a1,
        _DWORD *a2)
{
  *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18000d748  push    rbx
0x18000d74a  sub     rsp, 20h
0x18000d74e  mov     rbx, rdx
0x18000d751  mov     rax, [rcx]
0x18000d754  mov     rax, [rax+10h]
0x18000d758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d75d  mov     [rbx], eax
0x18000d75f  xor     eax, eax
0x18000d761  jmp     short loc_18000D767
0x18000d763  mov     eax, [rsp+28h+arg_0]
0x18000d767  add     rsp, 20h
0x18000d76b  pop     rbx
0x18000d76c  retn
```

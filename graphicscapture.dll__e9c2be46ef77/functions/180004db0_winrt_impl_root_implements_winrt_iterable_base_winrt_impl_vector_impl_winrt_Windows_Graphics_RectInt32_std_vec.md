# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>::NonDelegatingGetTrustLevel(winrt::Windows::Foundation::TrustLevel *)

- ea: `0x180004db0`
- end: `0x180004dd6`
- name: `?NonDelegatingGetTrustLevel@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@IEAAHPEAW4TrustLevel@Foundation@Windows@3@@Z`
- size: `38`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800049f0`
- `0x180004a10`
- `0x180004a30`
- `0x180004a50`
- `0x1800219d4`

## callees

- `0x180004db0`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>::NonDelegatingGetTrustLevel(
        __int64 a1,
        _DWORD *a2)
{
  *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x180004db0  push    rbx
0x180004db2  sub     rsp, 20h
0x180004db6  mov     rbx, rdx
0x180004db9  mov     rax, [rcx]
0x180004dbc  mov     rax, [rax+10h]
0x180004dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc5  mov     [rbx], eax
0x180004dc7  xor     eax, eax
0x180004dc9  jmp     short loc_180004DCF
0x180004dcb  mov     eax, [rsp+28h+arg_0]
0x180004dcf  add     rsp, 20h
0x180004dd3  pop     rbx
0x180004dd4  retn
```

# winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(void)

- ea: `0x18000d038`
- end: `0x18000d0b8`
- name: `??1?$root_implements@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@U?$IIterable@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@@impl@winrt@@MEAA@XZ`
- size: `128`
- prototype: `void __fastcall(__int64)`
- caller_count: `18`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d0e0`
- `0x18000d120`
- `0x18000eac8`
- `0x18000ebb8`
- `0x18000ec20`
- `0x18000ed30`
- `0x180011780`
- `0x1800117d0`
- `0x180011840`
- `0x1800178dc`
- `0x180017a28`
- `0x180017aa8`
- `0x18002609c`
- `0x180026290`
- `0x180026320`
- `0x180026390`
- `0x18002b94c`
- `0x18002c460`

## callees

- `0x1800025a0`
- `0x18000d038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000d0b1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000d0b1`

## pseudocode

```c
void __fastcall winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(
        __int64 a1)
{
  signed __int64 v1; // rax
  signed __int64 v2; // rtt
  volatile signed __int32 *v3; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  while ( v1 >= 0 )
  {
    v2 = v1;
    v1 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v1 - 1, v1);
    if ( v2 == v1 )
      goto LABEL_10;
  }
  v3 = (volatile signed __int32 *)(2 * v1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(2 * v1 + 24), 0xFFFFFFFF) == 1
    && _InterlockedExchangeAdd(v3 + 7, 0xFFFFFFFF) == 1
    && v3 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      goto LABEL_11;
    operator delete((void *)v3, 0x20u);
  }
LABEL_10:
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
LABEL_11:
    abort();
}

```

## disassembly

```asm
0x18000d038  push    rbx
0x18000d03a  sub     rsp, 20h
0x18000d03e  mov     rax, [rcx+8]
0x18000d042  or      ebx, 0FFFFFFFFh
0x18000d045  test    rax, rax
0x18000d048  js      short loc_18000D058
0x18000d04a  lea     rdx, [rax-1]
0x18000d04e  lock cmpxchg [rcx+8], rdx
0x18000d054  jnz     short loc_18000D042
0x18000d056  jmp     short loc_18000D099
0x18000d058  lea     rcx, [rax+rax]; void *
0x18000d05c  mov     eax, ebx
0x18000d05e  lock xadd [rcx+18h], eax
0x18000d063  cmp     eax, 1
0x18000d066  jnz     short loc_18000D099
0x18000d068  mov     eax, ebx
0x18000d06a  lock xadd [rcx+1Ch], eax
0x18000d06f  cmp     eax, 1
0x18000d072  jnz     short loc_18000D099
0x18000d074  test    rcx, rcx
0x18000d077  jz      short loc_18000D099
0x18000d079  mov     eax, ebx
0x18000d07b  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000d083  sub     eax, 1
0x18000d086  jnz     short loc_18000D08B
0x18000d088  nop
0x18000d089  jmp     short loc_18000D08F
0x18000d08b  test    eax, eax
0x18000d08d  js      short loc_18000D0B1
0x18000d08f  mov     edx, 20h ; ' '; unsigned __int64
0x18000d094  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d099  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000d0a1  sub     ebx, 1
0x18000d0a4  jnz     short loc_18000D0AD
0x18000d0a6  nop
0x18000d0a7  add     rsp, 20h
0x18000d0ab  pop     rbx
0x18000d0ac  retn
0x18000d0ad  test    ebx, ebx
0x18000d0af  jns     short loc_18000D0A7
0x18000d0b1  call    cs:__imp_abort
```

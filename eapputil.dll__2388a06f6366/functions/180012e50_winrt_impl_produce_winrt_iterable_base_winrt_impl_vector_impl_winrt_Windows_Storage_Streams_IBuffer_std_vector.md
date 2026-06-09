# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::get_Current(void * *)

- ea: `0x180012e50`
- end: `0x180012f3a`
- name: `?get_Current@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000395a`
- `0x18000817c`
- `0x1800114d8`
- `0x18001151c`
- `0x180012e50`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::get_Current(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  const struct winrt::impl::slim_source_location *v11; // rax
  const struct winrt::impl::slim_source_location *v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-78h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v16[24]; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v17[40]; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+8h]

  *a2 = 0;
  v4 = a1 + 8;
  if ( !a1 )
    v4 = 24;
  v5 = a1 + 16;
  if ( !a1 )
    v5 = 32;
  if ( *(_DWORD *)(*(_QWORD *)v5 + 40LL) != *(_DWORD *)v4 )
  {
    v11 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v17);
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v11);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v13 = &v14;
      *((_DWORD *)v13 + 32) = *(_DWORD *)winrt::to_hresult(v13 + 16);
      return v18;
    }
  }
  v6 = a1 + 24;
  if ( !a1 )
    v6 = 40;
  v7 = *(__int64 **)v6;
  v8 = a1 + 32;
  if ( !a1 )
    v8 = 48;
  if ( v7 == *(__int64 **)v8 )
  {
    v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v17);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)v16, v12);
    throw (winrt::hresult_out_of_bounds *)v16;
  }
  v9 = *v7;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x180012e50  mov     [rsp+arg_8], rbx
0x180012e55  push    rdi
0x180012e56  sub     rsp, 70h
0x180012e5a  mov     rdi, rdx
0x180012e5d  mov     r9, rcx
0x180012e60  mov     qword ptr [rdx], 0
0x180012e67  lea     r8, [rcx+8]
0x180012e6b  mov     eax, 18h
0x180012e70  test    rcx, rcx
0x180012e73  cmovz   r8, rax
0x180012e77  lea     rax, [rcx+10h]
0x180012e7b  mov     ecx, 20h ; ' '
0x180012e80  cmovz   rax, rcx
0x180012e84  mov     rax, [rax]
0x180012e87  mov     ecx, [rax+28h]
0x180012e8a  nop
0x180012e8b  cmp     ecx, [r8]
0x180012e8e  jnz     short loc_180012EE8
0x180012e90  lea     rax, [r9+18h]
0x180012e94  mov     ecx, 28h ; '('
0x180012e99  test    r9, r9
0x180012e9c  cmovz   rax, rcx
0x180012ea0  mov     rbx, [rax]
0x180012ea3  lea     rax, [r9+20h]
0x180012ea7  mov     ecx, 30h ; '0'
0x180012eac  cmovz   rax, rcx
0x180012eb0  cmp     rbx, [rax]
0x180012eb3  jz      short loc_180012F10
0x180012eb5  mov     rbx, [rbx]
0x180012eb8  test    rbx, rbx
0x180012ebb  jz      short loc_180012ECC
0x180012ebd  mov     rax, [rbx]
0x180012ec0  mov     rcx, rbx
0x180012ec3  mov     rax, [rax+8]
0x180012ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ecc  mov     [rdi], rbx
0x180012ecf  xor     eax, eax
0x180012ed1  jmp     short loc_180012EDA
0x180012ed3  mov     eax, [rsp+78h+arg_0]
0x180012eda  mov     rbx, [rsp+78h+arg_8]
0x180012ee2  add     rsp, 70h
0x180012ee6  pop     rdi
0x180012ee7  retn
0x180012ee8  lea     rcx, [rsp+78h+var_28]
0x180012eed  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012ef2  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180012ef5  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180012efa  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x180012eff  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180012f06  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180012f0b  call    _CxxThrowException_0
0x180012f10  lea     rcx, [rsp+78h+var_28]
0x180012f15  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012f1a  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180012f1d  lea     rcx, [rsp+78h+var_40]; this
0x180012f22  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180012f27  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180012f2e  lea     rcx, [rsp+78h+var_40]; pExceptionObject
0x180012f33  call    _CxxThrowException_0
```

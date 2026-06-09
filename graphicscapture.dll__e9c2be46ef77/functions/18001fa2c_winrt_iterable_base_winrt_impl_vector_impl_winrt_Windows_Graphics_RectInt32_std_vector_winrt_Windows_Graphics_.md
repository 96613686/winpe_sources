# winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32,std::allocator<winrt::Windows::Graphics::RectInt32>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator::Current(void)

- ea: `0x18001fa2c`
- end: `0x18001fa95`
- name: `?Current@iterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@QEBA?AURectInt32@Graphics@Windows@3@XZ`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021c60`

## callees

- `0x1800022f2`
- `0x1800058c4`
- `0x18001f2c0`
- `0x18001fa2c`
- `0x1800219e0`

## pseudocode

```c
_OWORD *__fastcall winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator::Current(
        _QWORD *a1,
        _OWORD *a2)
{
  __int128 *v4; // rax
  __int128 v5; // xmm0
  _OWORD *result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF

  winrt::impl::collection_version::iterator_type::check_version(
    (winrt::impl::collection_version::iterator_type *)(a1 + 3),
    (const struct winrt::impl::collection_version *)(a1[4] + 40LL));
  v4 = (__int128 *)a1[5];
  if ( v4 == (__int128 *)a1[6] )
  {
    v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v9);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v7);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  v5 = *v4;
  result = a2;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x18001fa2c  mov     [rsp+arg_0], rbx
0x18001fa31  push    rdi
0x18001fa32  sub     rsp, 50h
0x18001fa36  mov     rdi, rdx
0x18001fa39  mov     rbx, rcx
0x18001fa3c  mov     rdx, [rcx+20h]
0x18001fa40  add     rcx, 18h; this
0x18001fa44  add     rdx, 28h ; '('; struct winrt::impl::collection_version *
0x18001fa48  call    ?check_version@iterator_type@collection_version@impl@winrt@@QEBAXAEBU234@@Z; winrt::impl::collection_version::iterator_type::check_version(winrt::impl::collection_version const &)
0x18001fa4d  mov     rax, [rbx+28h]
0x18001fa51  cmp     rax, [rbx+30h]
0x18001fa55  jz      short loc_18001FA6C
0x18001fa57  movups  xmm0, xmmword ptr [rax]
0x18001fa5a  mov     rbx, [rsp+58h+arg_0]
0x18001fa5f  mov     rax, rdi
0x18001fa62  movdqu  xmmword ptr [rdi], xmm0
0x18001fa66  add     rsp, 50h
0x18001fa6a  pop     rdi
0x18001fa6b  retn
0x18001fa6c  lea     rcx, [rsp+58h+var_20]
0x18001fa71  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001fa76  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001fa79  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001fa7e  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001fa83  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001fa8a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001fa8f  call    _CxxThrowException_0
```

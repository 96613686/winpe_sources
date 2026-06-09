# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::MoveNext(bool *)

- ea: `0x180012430`
- end: `0x1800124d4`
- name: `?MoveNext@?$produce@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEA_N@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, bool *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000395a`
- `0x18000817c`
- `0x1800114d8`
- `0x180012430`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::MoveNext(
        __int64 a1,
        bool *a2)
{
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // r9
  bool v9; // al
  const struct winrt::impl::slim_source_location *v11; // rax
  __int64 *v12; // rdx
  __int64 v13; // [rsp+0h] [rbp-58h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+60h] [rbp+8h]

  v3 = a1 + 8;
  if ( !a1 )
    v3 = 24;
  v4 = a1 + 16;
  if ( !a1 )
    v4 = 32;
  if ( *(_DWORD *)(*(_QWORD *)v4 + 40LL) != *(_DWORD *)v3 )
  {
    v11 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v15);
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v11);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v12 = &v13;
      *((_DWORD *)v12 + 24) = *(_DWORD *)winrt::to_hresult(v12 + 12);
      return v16;
    }
  }
  v5 = a1 + 24;
  if ( !a1 )
    v5 = 40;
  v6 = *(_QWORD *)v5;
  v7 = a1 + 32;
  if ( !a1 )
    v7 = 48;
  v8 = *(_QWORD *)v7;
  v9 = 0;
  if ( v6 != *(_QWORD *)v7 )
  {
    *(_QWORD *)v5 = v6 + 8;
    if ( v6 + 8 != v8 )
      v9 = 1;
  }
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x180012430  sub     rsp, 58h
0x180012434  mov     r9, rcx
0x180012437  lea     r8, [rcx+8]
0x18001243b  mov     eax, 18h
0x180012440  test    rcx, rcx
0x180012443  cmovz   r8, rax
0x180012447  lea     rax, [rcx+10h]
0x18001244b  mov     ecx, 20h ; ' '
0x180012450  cmovz   rax, rcx
0x180012454  mov     rax, [rax]
0x180012457  mov     ecx, [rax+28h]
0x18001245a  nop
0x18001245b  cmp     ecx, [r8]
0x18001245e  jnz     short loc_1800124AA
0x180012460  lea     rcx, [r9+18h]
0x180012464  mov     eax, 28h ; '('
0x180012469  test    r9, r9
0x18001246c  cmovz   rcx, rax
0x180012470  mov     r8, [rcx]
0x180012473  lea     rax, [r9+20h]
0x180012477  mov     r10d, 30h ; '0'
0x18001247d  cmovz   rax, r10
0x180012481  mov     r9, [rax]
0x180012484  cmp     r8, r9
0x180012487  jz      short loc_180012499
0x180012489  lea     rax, [r8+8]
0x18001248d  mov     [rcx], rax
0x180012490  cmp     rax, r9
0x180012493  jz      short loc_180012499
0x180012495  mov     al, 1
0x180012497  jmp     short loc_18001249B
0x180012499  xor     al, al
0x18001249b  mov     [rdx], al
0x18001249d  xor     eax, eax
0x18001249f  jmp     short loc_1800124A5
0x1800124a1  mov     eax, [rsp+58h+arg_0]
0x1800124a5  add     rsp, 58h
0x1800124a9  retn
0x1800124aa  lea     rcx, [rsp+58h+var_20]
0x1800124af  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800124b4  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800124b7  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800124bc  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x1800124c1  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x1800124c8  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800124cd  call    _CxxThrowException_0
```

# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::get_HasCurrent(bool *)

- ea: `0x180013060`
- end: `0x1800130f0`
- name: `?get_HasCurrent@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UIBuffer@Streams@Storage@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEA_N@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64, bool *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000395a`
- `0x18000817c`
- `0x1800114d8`
- `0x180013060`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Storage::Streams::IBuffer,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Storage::Streams::IBuffer>>::get_HasCurrent(
        __int64 a1,
        bool *a2)
{
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  const struct winrt::impl::slim_source_location *v8; // rax
  __int64 *v9; // rdx
  __int64 v10; // [rsp+0h] [rbp-58h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v12[32]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+60h] [rbp+8h]

  v3 = a1 + 8;
  if ( !a1 )
    v3 = 24;
  v4 = a1 + 16;
  if ( !a1 )
    v4 = 32;
  if ( *(_DWORD *)(*(_QWORD *)v4 + 40LL) != *(_DWORD *)v3 )
  {
    v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v12);
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject, v8);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v9 = &v10;
      *((_DWORD *)v9 + 24) = *(_DWORD *)winrt::to_hresult(v9 + 12);
      return v13;
    }
  }
  v5 = a1 + 32;
  if ( !a1 )
    v5 = 48;
  v6 = a1 + 24;
  if ( !a1 )
    v6 = 40;
  *a2 = *(_QWORD *)v6 != *(_QWORD *)v5;
  return 0;
}

```

## disassembly

```asm
0x180013060  sub     rsp, 58h
0x180013064  mov     r9, rcx
0x180013067  lea     r8, [rcx+8]
0x18001306b  mov     eax, 18h
0x180013070  test    rcx, rcx
0x180013073  cmovz   r8, rax
0x180013077  lea     rax, [rcx+10h]
0x18001307b  mov     ecx, 20h ; ' '
0x180013080  cmovz   rax, rcx
0x180013084  mov     rax, [rax]
0x180013087  mov     ecx, [rax+28h]
0x18001308a  nop
0x18001308b  cmp     ecx, [r8]
0x18001308e  jnz     short loc_1800130C6
0x180013090  lea     rax, [r9+20h]
0x180013094  mov     ecx, 30h ; '0'
0x180013099  test    r9, r9
0x18001309c  cmovz   rax, rcx
0x1800130a0  lea     rcx, [r9+18h]
0x1800130a4  mov     r8d, 28h ; '('
0x1800130aa  cmovz   rcx, r8
0x1800130ae  mov     rax, [rax]
0x1800130b1  cmp     [rcx], rax
0x1800130b4  setnz   al
0x1800130b7  mov     [rdx], al
0x1800130b9  xor     eax, eax
0x1800130bb  jmp     short loc_1800130C1
0x1800130bd  mov     eax, [rsp+58h+arg_0]
0x1800130c1  add     rsp, 58h
0x1800130c5  retn
0x1800130c6  lea     rcx, [rsp+58h+var_20]
0x1800130cb  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800130d0  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800130d3  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800130d8  call    ??0hresult_changed_state@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::impl::slim_source_location const &)
0x1800130dd  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x1800130e4  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800130e9  call    _CxxThrowException_0
```

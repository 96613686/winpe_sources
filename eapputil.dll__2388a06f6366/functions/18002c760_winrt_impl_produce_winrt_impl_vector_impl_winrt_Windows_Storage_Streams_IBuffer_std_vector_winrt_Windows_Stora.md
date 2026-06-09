# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Storage::Streams::IBuffer>>::InsertAt(uint,void *)

- ea: `0x18002c760`
- end: `0x18002c7fe`
- name: `?InsertAt@?$produce@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `158`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000395a`
- `0x18000817c`
- `0x18001151c`
- `0x18002c760`
- `0x18002cc5c`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Storage::Streams::IBuffer>>::InsertAt(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // r8
  __int64 v4; // rcx
  const struct winrt::impl::slim_source_location *v6; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-20h] BYREF
  char v9; // [rsp+60h] [rbp+8h] BYREF
  __int64 v10; // [rsp+70h] [rbp+18h] BYREF

  v10 = a3;
  v3 = (a1 - 16) & -(__int64)(a1 != 0);
  if ( a2 > (unsigned __int64)((__int64)(*(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x38)
                                       - *(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x30)) >> 3) )
  {
    v6 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v8);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v6);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 40));
  if ( v3 == -40 )
  {
    v3 = 0;
    v4 = 48;
  }
  else
  {
    v4 = v3 + 48;
  }
  std::vector<winrt::Windows::Storage::Streams::IBuffer>::insert(v4, &v9, *(_QWORD *)(v3 + 48) + 8LL * a2, &v10);
  return 0;
}

```

## disassembly

```asm
0x18002c760  mov     [rsp+arg_10], r8
0x18002c765  sub     rsp, 58h
0x18002c769  lea     rax, [rcx-10h]
0x18002c76d  neg     rcx
0x18002c770  sbb     r8, r8
0x18002c773  and     r8, rax
0x18002c776  lea     r9, [r8+28h]
0x18002c77a  mov     rax, r9
0x18002c77d  neg     rax
0x18002c780  sbb     rcx, rcx
0x18002c783  and     rcx, r8
0x18002c786  mov     r10d, edx
0x18002c789  mov     rax, [rcx+38h]
0x18002c78d  sub     rax, [rcx+30h]
0x18002c791  sar     rax, 3
0x18002c795  cmp     r10, rax
0x18002c798  ja      short loc_18002C7D4
0x18002c79a  lock inc dword ptr [r9]
0x18002c79e  test    r9, r9
0x18002c7a1  jz      short loc_18002C7A9
0x18002c7a3  lea     rcx, [r8+30h]
0x18002c7a7  jmp     short loc_18002C7B0
0x18002c7a9  xor     r8d, r8d
0x18002c7ac  lea     ecx, [r8+30h]
0x18002c7b0  mov     rax, [r8+30h]
0x18002c7b4  lea     r8, [rax+r10*8]
0x18002c7b8  lea     r9, [rsp+58h+arg_10]
0x18002c7bd  lea     rdx, [rsp+58h+arg_0]
0x18002c7c2  call    ?insert@?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@@2@AEBUIBuffer@Streams@Storage@Windows@winrt@@@Z; std::vector<winrt::Windows::Storage::Streams::IBuffer>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<winrt::Windows::Storage::Streams::IBuffer>>>,winrt::Windows::Storage::Streams::IBuffer const &)
0x18002c7c7  xor     eax, eax
0x18002c7c9  jmp     short loc_18002C7CF
0x18002c7cb  mov     eax, [rsp+58h+arg_8]
0x18002c7cf  add     rsp, 58h
0x18002c7d3  retn
0x18002c7d4  lea     rcx, [rsp+58h+var_20]
0x18002c7d9  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002c7de  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18002c7e1  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18002c7e6  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18002c7eb  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18002c7f2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002c7f7  call    _CxxThrowException_0
```

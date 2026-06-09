# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::InsertAt(uint,void *)

- ea: `0x180028830`
- end: `0x1800288ce`
- name: `?InsertAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `158`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000395a`
- `0x18000817c`
- `0x18001151c`
- `0x180028830`
- `0x18002b28c`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::InsertAt(
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
  std::vector<winrt::hstring>::insert(v4, &v9, *(_QWORD *)(v3 + 48) + 8LL * a2, &v10);
  return 0;
}

```

## disassembly

```asm
0x180028830  mov     [rsp+arg_10], r8
0x180028835  sub     rsp, 58h
0x180028839  lea     rax, [rcx-10h]
0x18002883d  neg     rcx
0x180028840  sbb     r8, r8
0x180028843  and     r8, rax
0x180028846  lea     r9, [r8+28h]
0x18002884a  mov     rax, r9
0x18002884d  neg     rax
0x180028850  sbb     rcx, rcx
0x180028853  and     rcx, r8
0x180028856  mov     r10d, edx
0x180028859  mov     rax, [rcx+38h]
0x18002885d  sub     rax, [rcx+30h]
0x180028861  sar     rax, 3
0x180028865  cmp     r10, rax
0x180028868  ja      short loc_1800288A4
0x18002886a  lock inc dword ptr [r9]
0x18002886e  test    r9, r9
0x180028871  jz      short loc_180028879
0x180028873  lea     rcx, [r8+30h]
0x180028877  jmp     short loc_180028880
0x180028879  xor     r8d, r8d
0x18002887c  lea     ecx, [r8+30h]
0x180028880  mov     rax, [r8+30h]
0x180028884  lea     r8, [rax+r10*8]
0x180028888  lea     r9, [rsp+58h+arg_10]
0x18002888d  lea     rdx, [rsp+58h+arg_0]
0x180028892  call    ?insert@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@Uhstring@winrt@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@Uhstring@winrt@@@std@@@std@@@2@AEBUhstring@winrt@@@Z; std::vector<winrt::hstring>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<winrt::hstring>>>,winrt::hstring const &)
0x180028897  xor     eax, eax
0x180028899  jmp     short loc_18002889F
0x18002889b  mov     eax, [rsp+58h+arg_8]
0x18002889f  add     rsp, 58h
0x1800288a3  retn
0x1800288a4  lea     rcx, [rsp+58h+var_20]
0x1800288a9  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800288ae  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800288b1  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800288b6  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800288bb  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800288c2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800288c7  call    _CxxThrowException_0
```

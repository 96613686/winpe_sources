# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::InsertAt(uint,void *)

- ea: `0x180012380`
- end: `0x18001241e`
- name: `?InsertAt@?$produce@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `158`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000395a`
- `0x18000817c`
- `0x18001151c`
- `0x180012380`
- `0x18001336c`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::InsertAt(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v3; // r8
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  __int64 result; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF
  char v10; // [rsp+60h] [rbp+8h] BYREF
  int v11; // [rsp+68h] [rbp+10h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = a3;
  v3 = (a1 - 16) & -(__int64)(a1 != 0);
  v4 = (__int64)(*(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x38) - *(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x30)) >> 3;
  if ( a2 > v4 )
  {
    v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v9);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v7);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 40));
  if ( v3 == -40 )
  {
    v3 = 0;
    v5 = 48;
  }
  else
  {
    v5 = v3 + 48;
  }
  try
  {
    std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>::insert(
      v5,
      &v10,
      *(_QWORD *)(v3 + 48) + 8LL * a2,
      &v12);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x180012380  mov     [rsp+arg_10], r8
0x180012385  sub     rsp, 58h
0x180012389  lea     rax, [rcx-10h]
0x18001238d  neg     rcx
0x180012390  sbb     r8, r8
0x180012393  and     r8, rax
0x180012396  lea     r9, [r8+28h]
0x18001239a  mov     rax, r9
0x18001239d  neg     rax
0x1800123a0  sbb     rcx, rcx
0x1800123a3  and     rcx, r8
0x1800123a6  mov     r10d, edx
0x1800123a9  mov     rax, [rcx+38h]
0x1800123ad  sub     rax, [rcx+30h]
0x1800123b1  sar     rax, 3
0x1800123b5  cmp     r10, rax
0x1800123b8  ja      short loc_1800123F4
0x1800123ba  lock inc dword ptr [r9]
0x1800123be  test    r9, r9
0x1800123c1  jz      short loc_1800123C9
0x1800123c3  lea     rcx, [r8+30h]
0x1800123c7  jmp     short loc_1800123D0
0x1800123c9  xor     r8d, r8d
0x1800123cc  lea     ecx, [r8+30h]
0x1800123d0  mov     rax, [r8+30h]
0x1800123d4  lea     r8, [rax+r10*8]
0x1800123d8  lea     r9, [rsp+58h+arg_10]
0x1800123dd  lea     rdx, [rsp+58h+arg_0]
0x1800123e2  call    ?insert@?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@@2@AEBUEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Z; std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<winrt::Windows::Internal::Eap::Utility::EapAttribute>>>,winrt::Windows::Internal::Eap::Utility::EapAttribute const &)
0x1800123e7  xor     eax, eax
0x1800123e9  jmp     short loc_1800123EF
0x1800123eb  mov     eax, [rsp+58h+arg_8]
0x1800123ef  add     rsp, 58h
0x1800123f3  retn
0x1800123f4  lea     rcx, [rsp+58h+var_20]
0x1800123f9  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800123fe  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180012401  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180012406  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x18001240b  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180012412  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180012417  call    _CxxThrowException_0
```

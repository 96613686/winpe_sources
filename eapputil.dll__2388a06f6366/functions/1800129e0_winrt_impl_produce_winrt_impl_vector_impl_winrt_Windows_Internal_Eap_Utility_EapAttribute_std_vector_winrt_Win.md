# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::SetAt(uint,void *)

- ea: `0x1800129e0`
- end: `0x180012af7`
- name: `?SetAt@?$produce@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAX@Z`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000395a`
- `0x18000817c`
- `0x1800083ec`
- `0x18001151c`
- `0x1800129e0`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::SetAt(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v4; // r9
  volatile signed __int32 *v5; // r8
  __int64 v6; // r10
  __int64 *v7; // rbx
  __int64 v8; // rax
  const struct winrt::impl::slim_source_location *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  char v13; // [rsp+28h] [rbp-40h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-20h] BYREF
  unsigned int v17; // [rsp+78h] [rbp+10h] BYREF
  char v18; // [rsp+80h] [rbp+18h] BYREF

  v4 = (a1 - 16) & -(__int64)(a1 != 0);
  v5 = (volatile signed __int32 *)(v4 + 40);
  v13 = 0;
  v6 = a2;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x38)
                                        - *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x30)) >> 3) )
  {
    v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v15);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v10);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v11 + 120) = *(_DWORD *)winrt::to_hresult(&v17);
      return v17;
    }
  }
  _InterlockedIncrement(v5);
  v7 = (__int64 *)(*(_QWORD *)((v4 & -(__int64)(v5 != 0)) + 0x30) + 8 * v6);
  v8 = *v7;
  *v7 = 0;
  v12 = v8;
  v13 = 1;
  if ( v7 != (__int64 *)&v18 )
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v7);
    *v7 = a3;
    if ( a3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  }
  if ( v13 && v12 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v12);
  return 0;
}

```

## disassembly

```asm
0x1800129e0  mov     [rsp+arg_0], rbx
0x1800129e5  push    rdi
0x1800129e6  sub     rsp, 60h
0x1800129ea  mov     rdi, r8
0x1800129ed  lea     rax, [rcx-10h]
0x1800129f1  neg     rcx
0x1800129f4  sbb     r9, r9
0x1800129f7  and     r9, rax
0x1800129fa  lea     r8, [r9+28h]
0x1800129fe  mov     [rsp+68h+var_40], 0
0x180012a03  mov     rax, r8
0x180012a06  neg     rax
0x180012a09  sbb     rcx, rcx
0x180012a0c  and     rcx, r9
0x180012a0f  mov     r10d, edx
0x180012a12  mov     rax, [rcx+38h]
0x180012a16  sub     rax, [rcx+30h]
0x180012a1a  sar     rax, 3
0x180012a1e  cmp     r10, rax
0x180012a21  jnb     loc_180012ACD
0x180012a27  lock inc dword ptr [r8]
0x180012a2b  neg     r8
0x180012a2e  sbb     rax, rax
0x180012a31  and     rax, r9
0x180012a34  mov     rax, [rax+30h]
0x180012a38  lea     rbx, [rax+r10*8]
0x180012a3c  cmp     [rsp+68h+var_40], 0
0x180012a41  jz      short loc_180012A5A
0x180012a43  cmp     [rsp+68h+var_48], 0
0x180012a49  jz      short loc_180012A55
0x180012a4b  lea     rcx, [rsp+68h+var_48]
0x180012a50  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012a55  mov     [rsp+68h+var_40], 0
0x180012a5a  mov     rax, [rbx]
0x180012a5d  mov     qword ptr [rbx], 0
0x180012a64  mov     [rsp+68h+var_48], rax
0x180012a69  mov     [rsp+68h+var_40], 1
0x180012a6e  lea     rax, [rsp+68h+arg_10]
0x180012a76  cmp     rbx, rax
0x180012a79  jz      short loc_180012AA1
0x180012a7b  cmp     qword ptr [rbx], 0
0x180012a7f  jz      short loc_180012A89
0x180012a81  mov     rcx, rbx
0x180012a84  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012a89  mov     [rbx], rdi
0x180012a8c  test    rdi, rdi
0x180012a8f  jz      short loc_180012AA1
0x180012a91  mov     rax, [rdi]
0x180012a94  mov     rcx, rdi
0x180012a97  mov     rax, [rax+8]
0x180012a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012aa0  nop
0x180012aa1  cmp     [rsp+68h+var_40], 0
0x180012aa6  jz      short loc_180012ABA
0x180012aa8  cmp     [rsp+68h+var_48], 0
0x180012aae  jz      short loc_180012ABA
0x180012ab0  lea     rcx, [rsp+68h+var_48]
0x180012ab5  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012aba  xor     eax, eax
0x180012abc  jmp     short loc_180012AC2
0x180012abe  mov     eax, [rsp+68h+arg_8]
0x180012ac2  mov     rbx, [rsp+68h+arg_0]
0x180012ac7  add     rsp, 60h
0x180012acb  pop     rdi
0x180012acc  retn
0x180012acd  lea     rcx, [rsp+68h+var_20]
0x180012ad2  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012ad7  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180012ada  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180012adf  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x180012ae4  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180012aeb  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180012af0  call    _CxxThrowException_0
```

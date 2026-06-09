# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::RemoveAt(uint)

- ea: `0x180012580`
- end: `0x1800126bd`
- name: `?RemoveAt@?$produce@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHI@Z`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000395a`
- `0x18000817c`
- `0x1800083ec`
- `0x18001151c`
- `0x180012580`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::RemoveAt(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r14
  volatile signed __int32 *v3; // rdi
  __int64 v4; // r8
  __int64 *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 *v8; // r14
  __int64 *i; // rdi
  __int64 v10; // rax
  __int64 *v11; // rcx
  const struct winrt::impl::slim_source_location *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // [rsp+20h] [rbp-68h] BYREF
  char v16; // [rsp+28h] [rbp-60h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-58h] BYREF
  char v18[64]; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v20; // [rsp+98h] [rbp+10h] BYREF

  v2 = (a1 - 16) & -(__int64)(a1 != 0);
  v3 = (volatile signed __int32 *)(v2 + 40);
  v16 = 0;
  v4 = a2;
  if ( a2 >= (unsigned __int64)((__int64)(*(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x38)
                                        - *(_QWORD *)((v2 & -(__int64)(v2 != -40)) + 0x30)) >> 3) )
  {
    v13 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current((__int64)v18);
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject, v13);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      *(_DWORD *)(v14 + 152) = *(_DWORD *)winrt::to_hresult(&v20);
      return v20;
    }
  }
  _InterlockedIncrement(v3);
  v5 = (__int64 *)(*(_QWORD *)((v2 & -(__int64)(v3 != 0)) + 0x30) + 8 * v4);
  v6 = *v5;
  *v5 = 0;
  v15 = v6;
  v16 = 1;
  v7 = v2 & ((unsigned __int128)-(__int128)(unsigned __int64)v3 >> 64);
  v8 = *(__int64 **)(v7 + 0x38);
  for ( i = v5 + 1; i != v8; ++i )
  {
    if ( v5 != i )
    {
      if ( *v5 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v5);
      v10 = *i;
      *i = 0;
      *v5 = v10;
    }
    ++v5;
  }
  v11 = (__int64 *)(*(_QWORD *)(v7 + 56) - 8LL);
  if ( *v11 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v11);
  *(_QWORD *)(v7 + 56) -= 8LL;
  if ( v16 && v15 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v15);
  return 0;
}

```

## disassembly

```asm
0x180012580  push    rbx
0x180012582  push    rsi
0x180012583  push    rdi
0x180012584  push    r14
0x180012586  sub     rsp, 68h
0x18001258a  lea     rax, [rcx-10h]
0x18001258e  neg     rcx
0x180012591  sbb     r14, r14
0x180012594  and     r14, rax
0x180012597  lea     rdi, [r14+28h]
0x18001259b  mov     [rsp+88h+var_60], 0
0x1800125a0  mov     rax, rdi
0x1800125a3  neg     rax
0x1800125a6  sbb     rcx, rcx
0x1800125a9  and     rcx, r14
0x1800125ac  mov     r8d, edx
0x1800125af  mov     rax, [rcx+38h]
0x1800125b3  sub     rax, [rcx+30h]
0x1800125b7  sar     rax, 3
0x1800125bb  cmp     r8, rax
0x1800125be  jnb     loc_180012693
0x1800125c4  lock inc dword ptr [rdi]
0x1800125c7  mov     rax, rdi
0x1800125ca  neg     rax
0x1800125cd  sbb     rax, rax
0x1800125d0  and     rax, r14
0x1800125d3  mov     rax, [rax+30h]
0x1800125d7  lea     rbx, [rax+r8*8]
0x1800125db  cmp     [rsp+88h+var_60], 0
0x1800125e0  jz      short loc_1800125F9
0x1800125e2  cmp     [rsp+88h+var_68], 0
0x1800125e8  jz      short loc_1800125F4
0x1800125ea  lea     rcx, [rsp+88h+var_68]
0x1800125ef  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800125f4  mov     [rsp+88h+var_60], 0
0x1800125f9  mov     rax, [rbx]
0x1800125fc  mov     qword ptr [rbx], 0
0x180012603  mov     [rsp+88h+var_68], rax
0x180012608  mov     [rsp+88h+var_60], 1
0x18001260d  neg     rdi
0x180012610  sbb     rsi, rsi
0x180012613  and     rsi, r14
0x180012616  mov     r14, [rsi+38h]
0x18001261a  lea     rdi, [rbx+8]
0x18001261e  jmp     short loc_180012648
0x180012620  cmp     rbx, rdi
0x180012623  jz      short loc_180012640
0x180012625  cmp     qword ptr [rbx], 0
0x180012629  jz      short loc_180012633
0x18001262b  mov     rcx, rbx
0x18001262e  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012633  mov     rax, [rdi]
0x180012636  mov     qword ptr [rdi], 0
0x18001263d  mov     [rbx], rax
0x180012640  add     rbx, 8
0x180012644  add     rdi, 8
0x180012648  cmp     rdi, r14
0x18001264b  jnz     short loc_180012620
0x18001264d  mov     rcx, [rsi+38h]
0x180012651  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180012655  cmp     qword ptr [rcx], 0
0x180012659  jz      short loc_180012660
0x18001265b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012660  add     qword ptr [rsi+38h], 0FFFFFFFFFFFFFFF8h
0x180012665  cmp     [rsp+88h+var_60], 0
0x18001266a  jz      short loc_18001267E
0x18001266c  cmp     [rsp+88h+var_68], 0
0x180012672  jz      short loc_18001267E
0x180012674  lea     rcx, [rsp+88h+var_68]
0x180012679  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001267e  xor     eax, eax
0x180012680  jmp     short loc_180012689
0x180012682  mov     eax, [rsp+88h+arg_8]
0x180012689  add     rsp, 68h
0x18001268d  pop     r14
0x18001268f  pop     rdi
0x180012690  pop     rsi
0x180012691  pop     rbx
0x180012692  retn
0x180012693  lea     rcx, [rsp+88h+var_40]
0x180012698  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001269d  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800126a0  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800126a5  call    ??0hresult_out_of_bounds@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::impl::slim_source_location const &)
0x1800126aa  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800126b1  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800126b6  call    _CxxThrowException_0
```

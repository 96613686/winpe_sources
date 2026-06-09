# ShellUIHostCoordinatorDataImpl::ShellUIHostCoordinatorDataImpl(std::weak_ptr<ShellUIHostCoordinator>)

- ea: `0x18006f230`
- end: `0x18006f565`
- name: `??0ShellUIHostCoordinatorDataImpl@@QEAA@V?$weak_ptr@VShellUIHostCoordinator@@@std@@@Z`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047e10`

## callees

- `0x180008390`
- `0x180016148`
- `0x18001ce5c`
- `0x18001fd00`
- `0x18002661c`
- `0x18002a8bc`
- `0x1800414e0`
- `0x18004a928`
- `0x18006f230`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006f4f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006f4f4`

## string_xrefs

- `0x18006f553`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall ShellUIHostCoordinatorDataImpl::ShellUIHostCoordinatorDataImpl(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  std::_Ref_count_base *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  HRESULT v11; // eax
  LPVOID v12; // rax
  __int64 v13; // rcx
  std::_Ref_count_base *v14; // rcx
  int ppv; // [rsp+20h] [rbp-28h]
  _BYTE v17[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  LPVOID v19; // [rsp+A8h] [rbp+60h] BYREF

  std::weak_ptr<ShellUIHostCoordinator>::weak_ptr<ShellUIHostCoordinator>(v17);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)a1 = &ShellUIHostCoordinatorData::`vftable';
  std::weak_ptr<ShellUIHostCoordinator>::weak_ptr<ShellUIHostCoordinator>(a1 + 24);
  v5 = *(std::_Ref_count_base **)(v4 + 8);
  if ( v5 )
    std::_Ref_count_base::_Decwref(v5);
  *(_QWORD *)a1 = &ShellUIHostCoordinatorDataImpl::`vftable';
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  v6 = operator new(0x70u);
  *v6 = v6;
  v6[1] = v6;
  *(_QWORD *)(a1 + 64) = v6;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 7;
  *(_QWORD *)(a1 + 112) = 8;
  *(_DWORD *)(a1 + 56) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(
    a1 + 80,
    16,
    *(_QWORD *)(a1 + 64));
  *(_DWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  v7 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(64);
  *v7 = v7;
  v7[1] = v7;
  *(_QWORD *)(a1 + 128) = v7;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 7;
  *(_QWORD *)(a1 + 176) = 8;
  *(_DWORD *)(a1 + 120) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(
    a1 + 144,
    16,
    *(_QWORD *)(a1 + 128));
  *(_DWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  v8 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(56);
  *v8 = v8;
  v8[1] = v8;
  *(_QWORD *)(a1 + 192) = v8;
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 7;
  *(_QWORD *)(a1 + 240) = 8;
  *(_DWORD *)(a1 + 184) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(
    a1 + 208,
    16,
    *(_QWORD *)(a1 + 192));
  *(_DWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  v9 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(64);
  *v9 = v9;
  v9[1] = v9;
  *(_QWORD *)(a1 + 256) = v9;
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = 7;
  *(_QWORD *)(a1 + 304) = 8;
  *(_DWORD *)(a1 + 248) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(
    a1 + 272,
    16,
    *(_QWORD *)(a1 + 256));
  std::unordered_map<std::wstring,std::shared_ptr<ThreadpoolTimer>>::unordered_map<std::wstring,std::shared_ptr<ThreadpoolTimer>>(a1 + 312);
  *(_DWORD *)(a1 + 376) = 0;
  *(_QWORD *)(a1 + 384) = 0;
  *(_QWORD *)(a1 + 392) = 0;
  v10 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(56);
  *v10 = v10;
  v10[1] = v10;
  *(_QWORD *)(a1 + 384) = v10;
  *(_QWORD *)(a1 + 400) = 0;
  *(_QWORD *)(a1 + 408) = 0;
  *(_QWORD *)(a1 + 416) = 0;
  *(_QWORD *)(a1 + 424) = 7;
  *(_QWORD *)(a1 + 432) = 8;
  *(_DWORD *)(a1 + 376) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(
    a1 + 400,
    16,
    *(_QWORD *)(a1 + 384));
  *(_QWORD *)(a1 + 440) = 0;
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 456) = 0;
  *(_QWORD *)(a1 + 464) = 0;
  *(_QWORD *)(a1 + 472) = 0;
  *(_QWORD *)(a1 + 480) = 0;
  *(_QWORD *)(a1 + 488) = 0;
  *(_WORD *)(a1 + 496) = 0;
  *(_BYTE *)(a1 + 498) = 0;
  *(_QWORD *)(a1 + 504) = 0;
  *(_QWORD *)(a1 + 512) = 0;
  v19 = 0;
  v11 = CoCreateInstance(
          &GUID_45ba127d_10a8_46ea_8ab7_56ea9078943c,
          0,
          1u,
          &GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d,
          &v19);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v11,
      ppv);
  v12 = v19;
  v19 = 0;
  v13 = *(_QWORD *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = v12;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v19);
  v14 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v14 )
    std::_Ref_count_base::_Decwref(v14);
  return a1;
}

```

## disassembly

```asm
0x18006f230  mov     [rsp-40h+arg_8], rdx
0x18006f235  mov     [rsp-40h+arg_0], rcx
0x18006f23a  push    rbp
0x18006f23b  push    rbx
0x18006f23c  push    rsi
0x18006f23d  push    rdi
0x18006f23e  push    r12
0x18006f240  push    r13
0x18006f242  push    r14
0x18006f244  push    r15
0x18006f246  mov     rbp, rsp
0x18006f249  sub     rsp, 48h
0x18006f24d  mov     rsi, rdx
0x18006f250  mov     rdi, rcx
0x18006f253  xor     r14d, r14d
0x18006f256  mov     dword ptr [rbp+arg_10], r14d
0x18006f25a  lea     rcx, [rbp+var_18]
0x18006f25e  call    ??0?$weak_ptr@VShellUIHostCoordinator@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<ShellUIHostCoordinator>::weak_ptr<ShellUIHostCoordinator>(std::weak_ptr<ShellUIHostCoordinator> const &)
0x18006f263  mov     rdx, rax
0x18006f266  mov     [rdi+8], r14
0x18006f26a  mov     [rdi+10h], r14
0x18006f26e  lea     rax, ??_7ShellUIHostCoordinatorData@@6B@; const ShellUIHostCoordinatorData::`vftable'
0x18006f275  mov     [rdi], rax
0x18006f278  lea     rcx, [rdi+18h]
0x18006f27c  call    ??0?$weak_ptr@VShellUIHostCoordinator@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<ShellUIHostCoordinator>::weak_ptr<ShellUIHostCoordinator>(std::weak_ptr<ShellUIHostCoordinator> const &)
0x18006f281  mov     rcx, [rdx+8]; this
0x18006f285  test    rcx, rcx
0x18006f288  jz      short loc_18006F290
0x18006f28a  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18006f28f  nop
0x18006f290  lea     rax, ??_7ShellUIHostCoordinatorDataImpl@@6B@; const ShellUIHostCoordinatorDataImpl::`vftable'
0x18006f297  mov     [rdi], rax
0x18006f29a  xor     eax, eax
0x18006f29c  mov     [rdi+28h], rax
0x18006f2a0  mov     [rdi+30h], r14
0x18006f2a4  lea     rbx, [rdi+38h]
0x18006f2a8  mov     [rbp+arg_10], rbx
0x18006f2ac  mov     [rbx], r14d
0x18006f2af  mov     [rbx+8], r14
0x18006f2b3  mov     [rbx+10h], r14
0x18006f2b7  lea     ecx, [rax+70h]; Size
0x18006f2ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006f2bf  mov     [rax], rax
0x18006f2c2  mov     [rax+8], rax
0x18006f2c6  mov     [rbx+8], rax
0x18006f2ca  lea     rcx, [rbx+18h]
0x18006f2ce  mov     [rcx], r14
0x18006f2d1  mov     [rcx+8], r14
0x18006f2d5  mov     [rcx+10h], r14
0x18006f2d9  mov     qword ptr [rbx+30h], 7
0x18006f2e1  mov     r15d, 8
0x18006f2e7  mov     [rbx+38h], r15
0x18006f2eb  mov     r13d, 3F800000h
0x18006f2f1  mov     [rbx], r13d
0x18006f2f4  mov     r8, [rbx+8]
0x18006f2f8  lea     r12d, [r15+8]
0x18006f2fc  mov     edx, r12d
0x18006f2ff  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>)
0x18006f304  nop
0x18006f305  lea     rbx, [rdi+78h]
0x18006f309  mov     [rbp+arg_10], rbx
0x18006f30d  mov     [rbx], r14d
0x18006f310  mov     [rbx+8], r14
0x18006f314  mov     [rbx+10h], r14
0x18006f318  lea     r14d, [r15+38h]
0x18006f31c  mov     ecx, r14d
0x18006f31f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18006f324  mov     [rax], rax
0x18006f327  mov     [rax+8], rax
0x18006f32b  mov     [rbx+8], rax
0x18006f32f  lea     rcx, [rbx+18h]
0x18006f333  xor     eax, eax
0x18006f335  mov     [rcx], rax
0x18006f338  mov     [rcx+8], rax
0x18006f33c  mov     [rcx+10h], rax
0x18006f340  mov     qword ptr [rbx+30h], 7
0x18006f348  mov     [rbx+38h], r15
0x18006f34c  mov     [rbx], r13d
0x18006f34f  mov     r8, [rbx+8]
0x18006f353  mov     edx, r12d
0x18006f356  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>)
0x18006f35b  nop
0x18006f35c  lea     rbx, [rdi+0B8h]
0x18006f363  mov     [rbp+arg_10], rbx
0x18006f367  xor     eax, eax
0x18006f369  mov     [rbx], eax
0x18006f36b  mov     [rbx+8], rax
0x18006f36f  mov     [rbx+10h], rax
0x18006f373  lea     r15d, [r12+28h]
0x18006f378  mov     ecx, r15d
0x18006f37b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18006f380  mov     [rax], rax
0x18006f383  mov     [rax+8], rax
0x18006f387  mov     [rbx+8], rax
0x18006f38b  lea     rcx, [rbx+18h]
0x18006f38f  xor     eax, eax
0x18006f391  mov     [rcx], rax
0x18006f394  mov     [rcx+8], rax
0x18006f398  mov     [rcx+10h], rax
0x18006f39c  mov     qword ptr [rbx+30h], 7
0x18006f3a4  mov     qword ptr [rbx+38h], 8
0x18006f3ac  mov     [rbx], r13d
0x18006f3af  mov     r8, [rbx+8]
0x18006f3b3  mov     edx, r12d
0x18006f3b6  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>)
0x18006f3bb  nop
0x18006f3bc  lea     rbx, [rdi+0F8h]
0x18006f3c3  mov     [rbp+arg_10], rbx
0x18006f3c7  xor     eax, eax
0x18006f3c9  mov     [rbx], eax
0x18006f3cb  mov     [rbx+8], rax
0x18006f3cf  mov     [rbx+10h], rax
0x18006f3d3  mov     ecx, r14d
0x18006f3d6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18006f3db  mov     [rax], rax
0x18006f3de  mov     [rax+8], rax
0x18006f3e2  mov     [rbx+8], rax
0x18006f3e6  lea     rcx, [rbx+18h]
0x18006f3ea  xor     eax, eax
0x18006f3ec  mov     [rcx], rax
0x18006f3ef  mov     [rcx+8], rax
0x18006f3f3  mov     [rcx+10h], rax
0x18006f3f7  mov     qword ptr [rbx+30h], 7
0x18006f3ff  lea     r14d, [r12-8]
0x18006f404  mov     [rbx+38h], r14
0x18006f408  mov     [rbx], r13d
0x18006f40b  mov     r8, [rbx+8]
0x18006f40f  mov     edx, r12d
0x18006f412  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>)
0x18006f417  nop
0x18006f418  lea     rcx, [rdi+138h]
0x18006f41f  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::shared_ptr<ThreadpoolTimer>>::unordered_map<std::wstring,std::shared_ptr<ThreadpoolTimer>>(void)
0x18006f424  nop
0x18006f425  lea     rbx, [rdi+178h]
0x18006f42c  mov     [rbp+arg_10], rbx
0x18006f430  xor     eax, eax
0x18006f432  mov     [rbx], eax
0x18006f434  mov     [rbx+8], rax
0x18006f438  mov     [rbx+10h], rax
0x18006f43c  mov     ecx, r15d
0x18006f43f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18006f444  mov     [rax], rax
0x18006f447  mov     [rax+8], rax
0x18006f44b  mov     [rbx+8], rax
0x18006f44f  lea     rcx, [rbx+18h]
0x18006f453  xor     r15d, r15d
0x18006f456  mov     [rcx], r15
0x18006f459  mov     [rcx+8], r15
0x18006f45d  mov     [rcx+10h], r15
0x18006f461  mov     qword ptr [rbx+30h], 7
0x18006f469  mov     [rbx+38h], r14
0x18006f46d  mov     [rbx], r13d
0x18006f470  mov     r8, [rbx+8]
0x18006f474  mov     edx, r12d
0x18006f477  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VThreadpoolTimer@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<ThreadpoolTimer>>>>>)
0x18006f47c  nop
0x18006f47d  mov     [rdi+1B8h], r15
0x18006f484  mov     [rdi+1C0h], r15
0x18006f48b  mov     [rdi+1C8h], r15
0x18006f492  mov     [rdi+1D0h], r15
0x18006f499  mov     [rdi+1D8h], r15
0x18006f4a0  mov     [rdi+1E0h], r15
0x18006f4a7  mov     [rdi+1E8h], r15
0x18006f4ae  mov     [rdi+1F0h], r15w
0x18006f4b6  mov     [rdi+1F2h], r15b
0x18006f4bd  mov     [rdi+1F8h], r15
0x18006f4c4  mov     [rdi+200h], r15
0x18006f4cb  mov     dword ptr [rbp+arg_10], 2
0x18006f4d2  mov     [rbp+arg_18], r15
0x18006f4d6  lea     rax, [rbp+arg_18]
0x18006f4da  mov     qword ptr [rsp+48h+ppv], rax; int
0x18006f4df  lea     r9, _GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d; riid
0x18006f4e6  xor     edx, edx; pUnkOuter
0x18006f4e8  lea     r8d, [r12-0Fh]; dwClsContext
0x18006f4ed  lea     rcx, _GUID_45ba127d_10a8_46ea_8ab7_56ea9078943c; rclsid
0x18006f4f4  call    cs:__imp_CoCreateInstance
0x18006f4fa  mov     rcx, [rbp+40h]; this
0x18006f4fe  test    eax, eax
0x18006f500  js      short loc_18006F550
0x18006f502  mov     rax, [rbp+arg_18]
0x18006f506  mov     [rbp+arg_18], r15
0x18006f50a  mov     rcx, [rdi+30h]
0x18006f50e  mov     [rdi+30h], rax
0x18006f512  test    rcx, rcx
0x18006f515  jz      short loc_18006F524
0x18006f517  mov     rax, [rcx]
0x18006f51a  mov     rax, [rax+10h]
0x18006f51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f523  nop
0x18006f524  lea     rcx, [rbp+arg_18]
0x18006f528  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18006f52d  nop
0x18006f52e  mov     rcx, [rsi+8]; this
0x18006f532  test    rcx, rcx
0x18006f535  jz      short loc_18006F53C
0x18006f537  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18006f53c  mov     rax, rdi
0x18006f53f  add     rsp, 48h
0x18006f543  pop     r15
0x18006f545  pop     r14
0x18006f547  pop     r13
0x18006f549  pop     r12
0x18006f54b  pop     rdi
0x18006f54c  pop     rsi
0x18006f54d  pop     rbx
0x18006f54e  pop     rbp
0x18006f54f  retn
0x18006f550  mov     r9d, eax; char *
0x18006f553  lea     r8, aOnecoreInterna_16; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006f55a  mov     edx, 1CBEh; void *
0x18006f55f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

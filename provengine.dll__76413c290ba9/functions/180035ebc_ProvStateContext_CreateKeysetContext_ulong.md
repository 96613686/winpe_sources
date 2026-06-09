# ProvStateContext::CreateKeysetContext(ulong)

- ea: `0x180035ebc`
- end: `0x180035faa`
- name: `?CreateKeysetContext@ProvStateContext@@QEAAPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@K@Z`
- size: `238`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001f730`

## callees

- `0x1800021b4`
- `0x180010308`
- `0x180020bf4`
- `0x180035bc0`
- `0x180035ebc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180035f68`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035f93`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035f68`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035f93`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ProvStateContext::CreateKeysetContext(__int64 a1, unsigned int a2)
{
  __int64 *v2; // rsi
  __int64 result; // rax
  void **v4; // rax
  void **v5; // rbx
  void ***v6; // r14
  void **v7; // rdi
  __int64 v8; // rdi
  void **v9; // [rsp+20h] [rbp-28h] BYREF
  void **v10; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = a2;
  LODWORD(v10) = a2;
  v2 = (__int64 *)(a1 + 80);
  if ( (unsigned __int64)a2 >= *(_QWORD *)(a1 + 88)
    || (result = *__A__map_KV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std__U__less_K_2_V__allocator_U__pair___CBKV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std___std___2__std__QEAAAEAV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__1_AEBK_Z(
                    (__int64 *)(a1 + 80),
                    (unsigned int *)&v10)) == 0 )
  {
    v4 = (void **)operator new(0x10u);
    v5 = v4;
    v10 = v4;
    if ( v4 )
    {
      *v4 = 0;
      v4[1] = 0;
      *v4 = (void *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>>::_Buyheadnode();
    }
    else
    {
      v5 = 0;
    }
    v9 = v5;
    v6 = (void ***)__A__map_KV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std__U__less_K_2_V__allocator_U__pair___CBKV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std___std___2__std__QEAAAEAV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__1_AEBK_Z(
                     v2,
                     &v11);
    if ( v6 != &v9 )
    {
      v9 = 0;
      v7 = *v6;
      if ( v5 != *v6 )
      {
        if ( v7 )
        {
          std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>,0>>(*v6);
          operator delete(v7);
        }
        *v6 = v5;
      }
      v5 = 0;
    }
    v8 = *__A__map_KV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std__U__less_K_2_V__allocator_U__pair___CBKV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std___std___2__std__QEAAAEAV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__1_AEBK_Z(
            v2,
            &v11);
    if ( v5 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>,0>>(v5);
      operator delete(v5);
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180035ebc  mov     [rsp+arg_10], rbx
0x180035ec1  mov     [rsp+arg_8], edx
0x180035ec5  push    rsi
0x180035ec6  push    rdi
0x180035ec7  push    r14
0x180035ec9  sub     rsp, 30h
0x180035ecd  mov     dword ptr [rsp+48h+arg_0], edx
0x180035ed1  lea     rsi, [rcx+50h]
0x180035ed5  mov     eax, edx
0x180035ed7  cmp     rax, [rcx+58h]
0x180035edb  jnb     short loc_180035EF6
0x180035edd  lea     rdx, [rsp+48h+arg_0]
0x180035ee2  mov     rcx, rsi
0x180035ee5  call    ??A?$map@KV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@1@AEBK@Z
0x180035eea  mov     rax, [rax]
0x180035eed  test    rax, rax
0x180035ef0  jnz     loc_180035F9C
0x180035ef6  mov     ecx, 10h; Size
0x180035efb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035f00  mov     rbx, rax
0x180035f03  mov     [rsp+48h+arg_0], rax
0x180035f08  test    rax, rax
0x180035f0b  jz      short loc_180035F26
0x180035f0d  mov     qword ptr [rax], 0
0x180035f14  mov     qword ptr [rax+8], 0
0x180035f1c  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>>::_Buyheadnode(void)
0x180035f21  mov     [rbx], rax
0x180035f24  jmp     short loc_180035F28
0x180035f26  xor     ebx, ebx
0x180035f28  mov     [rsp+48h+var_28], rbx
0x180035f2d  lea     rdx, [rsp+48h+arg_8]
0x180035f32  mov     rcx, rsi
0x180035f35  call    ??A?$map@KV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@1@AEBK@Z
0x180035f3a  mov     r14, rax
0x180035f3d  lea     rax, [rsp+48h+var_28]
0x180035f42  cmp     r14, rax
0x180035f45  jz      short loc_180035F73
0x180035f47  mov     [rsp+48h+var_28], 0
0x180035f50  mov     rdi, [r14]
0x180035f53  cmp     rbx, rdi
0x180035f56  jz      short loc_180035F71
0x180035f58  test    rdi, rdi
0x180035f5b  jz      short loc_180035F6E
0x180035f5d  mov     rcx, rdi
0x180035f60  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>(void)
0x180035f65  mov     rcx, rdi
0x180035f68  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180035f6e  mov     [r14], rbx
0x180035f71  xor     ebx, ebx
0x180035f73  lea     rdx, [rsp+48h+arg_8]
0x180035f78  mov     rcx, rsi
0x180035f7b  call    ??A?$map@KV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@1@AEBK@Z
0x180035f80  mov     rdi, [rax]
0x180035f83  test    rbx, rbx
0x180035f86  jz      short loc_180035F99
0x180035f88  mov     rcx, rbx
0x180035f8b  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>(void)
0x180035f90  mov     rcx, rbx
0x180035f93  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180035f99  mov     rax, rdi
0x180035f9c  mov     rbx, [rsp+48h+arg_10]
0x180035fa1  add     rsp, 30h
0x180035fa5  pop     r14
0x180035fa7  pop     rdi
0x180035fa8  pop     rsi
0x180035fa9  retn
```

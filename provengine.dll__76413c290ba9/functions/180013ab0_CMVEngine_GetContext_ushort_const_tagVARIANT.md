# CMVEngine::GetContext(ushort const *,tagVARIANT *)

- ea: `0x180013ab0`
- end: `0x180013c83`
- name: `?GetContext@CMVEngine@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `467`
- prototype: `HRESULT __fastcall(CMVEngine *this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000b030`
- `0x180013ab0`
- `0x180022660`
- `0x180035bc0`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013b9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013c22`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013b9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013c22`
- `OLEAUT32!__imp_VariantInit` at `0x180013bad`
- `OLEAUT32!__imp_VariantInit` at `0x180013c36`
- `OLEAUT32!__imp_VariantInit` at `0x180013bad`
- `OLEAUT32!__imp_VariantInit` at `0x180013c36`
- `OLEAUT32!__imp_VariantCopy` at `0x180013bba`
- `OLEAUT32!__imp_VariantCopy` at `0x180013c43`
- `OLEAUT32!__imp_VariantCopy` at `0x180013bba`
- `OLEAUT32!__imp_VariantCopy` at `0x180013c43`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall CMVEngine::GetContext(CMVEngine *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  __int64 v6; // rdx
  _QWORD *v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 v12; // [rsp+20h] [rbp-68h] BYREF
  void *v13[2]; // [rsp+28h] [rbp-60h] BYREF
  __int64 v14; // [rsp+38h] [rbp-50h]
  unsigned __int64 v15; // [rsp+40h] [rbp-48h]

  if ( !a2 || !a3 )
    return -2147024809;
  v6 = *((_QWORD *)this + 26);
  if ( v6
    && ((v6 + 40) & -(__int64)(*(_DWORD *)(v6 + 44) != 0)) != 0
    && ((LODWORD(v12) = *(_DWORD *)((v6 + 40) & -(__int64)(*(_DWORD *)(v6 + 44) != 0)),
         (unsigned __int64)(unsigned int)v12 >= *(_QWORD *)(v6 + 88))
      ? (v7 = 0)
      : (v7 = *(_QWORD **)__A__map_KV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std__U__less_K_2_V__allocator_U__pair___CBKV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std___std___2__std__QEAAAEAV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__1_AEBK_Z(
                            v6 + 80,
                            &v12)),
        v7) )
  {
    v15 = 7;
    v14 = 0;
    LOWORD(v13[0]) = 0;
    v8 = -1;
    if ( *a2 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a2[v9] );
    }
    std::wstring::assign(v13, a2);
    std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::find(
      v7,
      &v12,
      v13);
    if ( v15 >= 8 )
      operator delete(v13[0]);
    v10 = v12;
    if ( *v7 != v12 )
      goto LABEL_15;
  }
  else
  {
    v8 = -1;
  }
  v15 = 7;
  v14 = 0;
  LOWORD(v13[0]) = 0;
  if ( *a2 )
  {
    do
      ++v8;
    while ( a2[v8] );
  }
  std::wstring::assign(v13, a2);
  std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::find(
    (char *)this + 80,
    &v12,
    v13);
  if ( v15 >= 8 )
    operator delete(v13[0]);
  v10 = v12;
  if ( *((_QWORD *)this + 10) != v12 )
  {
LABEL_15:
    VariantInit(a3);
    return VariantCopy(a3, (const VARIANTARG *)(v10 + 64));
  }
  return -2147024894;
}

```

## disassembly

```asm
0x180013ab0  push    rbx
0x180013ab2  push    rsi
0x180013ab3  push    rdi
0x180013ab4  push    r12
0x180013ab6  push    r13
0x180013ab8  push    r14
0x180013aba  push    r15
0x180013abc  sub     rsp, 50h
0x180013ac0  mov     rax, cs:__security_cookie
0x180013ac7  xor     rax, rsp
0x180013aca  mov     [rsp+88h+var_40], rax
0x180013acf  mov     r15, r8
0x180013ad2  mov     r14, rdx
0x180013ad5  mov     r13, rcx
0x180013ad8  xor     r12d, r12d
0x180013adb  test    rdx, rdx
0x180013ade  jz      loc_180013C60
0x180013ae4  test    r8, r8
0x180013ae7  jz      loc_180013C60
0x180013aed  mov     rdx, [rcx+0D0h]
0x180013af4  test    rdx, rdx
0x180013af7  jz      loc_180013BC5
0x180013afd  mov     eax, [rdx+2Ch]
0x180013b00  lea     rcx, [rdx+28h]
0x180013b04  neg     eax
0x180013b06  sbb     r8, r8
0x180013b09  and     r8, rcx
0x180013b0c  jz      loc_180013BC5
0x180013b12  mov     eax, [r8]
0x180013b15  mov     dword ptr [rsp+88h+var_68], eax
0x180013b19  cmp     rax, [rdx+58h]
0x180013b1d  jnb     short loc_180013B32
0x180013b1f  lea     rcx, [rdx+50h]
0x180013b23  lea     rdx, [rsp+88h+var_68]
0x180013b28  call    ??A?$map@KV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@1@AEBK@Z
0x180013b2d  mov     rsi, [rax]
0x180013b30  jmp     short loc_180013B35
0x180013b32  mov     rsi, r12
0x180013b35  test    rsi, rsi
0x180013b38  jz      loc_180013BC5
0x180013b3e  mov     [rsp+88h+var_48], 7
0x180013b47  mov     [rsp+88h+var_50], r12
0x180013b4c  mov     word ptr [rsp+88h+var_60], r12w
0x180013b52  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013b56  cmp     [r14], r12w
0x180013b5a  jnz     short loc_180013B61
0x180013b5c  mov     r8, r12
0x180013b5f  jmp     short loc_180013B6E
0x180013b61  mov     r8, rdi
0x180013b64  inc     r8
0x180013b67  cmp     [r14+r8*2], r12w
0x180013b6c  jnz     short loc_180013B64
0x180013b6e  mov     rdx, r14; Src
0x180013b71  lea     rcx, [rsp+88h+var_60]; void *
0x180013b76  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180013b7b  lea     r8, [rsp+88h+var_60]
0x180013b80  lea     rdx, [rsp+88h+var_68]
0x180013b85  mov     rcx, rsi
0x180013b88  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::find(std::wstring const &)
0x180013b8d  cmp     [rsp+88h+var_48], 8
0x180013b93  jb      short loc_180013BA0
0x180013b95  mov     rcx, [rsp+88h+var_60]
0x180013b9a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013ba0  mov     rbx, [rsp+88h+var_68]
0x180013ba5  cmp     [rsi], rbx
0x180013ba8  jz      short loc_180013BC9
0x180013baa  mov     rcx, r15; pvarg
0x180013bad  call    cs:__imp_VariantInit
0x180013bb3  lea     rdx, [rbx+40h]; pvargSrc
0x180013bb7  mov     rcx, r15; pvargDest
0x180013bba  call    cs:__imp_VariantCopy
0x180013bc0  jmp     loc_180013C65
0x180013bc5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013bc9  mov     [rsp+88h+var_48], 7
0x180013bd2  mov     [rsp+88h+var_50], r12
0x180013bd7  mov     word ptr [rsp+88h+var_60], r12w
0x180013bdd  cmp     [r14], r12w
0x180013be1  jnz     short loc_180013BE8
0x180013be3  mov     rdi, r12
0x180013be6  jmp     short loc_180013BF2
0x180013be8  inc     rdi
0x180013beb  cmp     [r14+rdi*2], r12w
0x180013bf0  jnz     short loc_180013BE8
0x180013bf2  mov     r8, rdi
0x180013bf5  mov     rdx, r14; Src
0x180013bf8  lea     rcx, [rsp+88h+var_60]; void *
0x180013bfd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180013c02  lea     r8, [rsp+88h+var_60]
0x180013c07  lea     rdx, [rsp+88h+var_68]
0x180013c0c  lea     rcx, [r13+50h]
0x180013c10  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::find(std::wstring const &)
0x180013c15  cmp     [rsp+88h+var_48], 8
0x180013c1b  jb      short loc_180013C28
0x180013c1d  mov     rcx, [rsp+88h+var_60]
0x180013c22  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013c28  mov     rbx, [rsp+88h+var_68]
0x180013c2d  cmp     [r13+50h], rbx
0x180013c31  jz      short loc_180013C4B
0x180013c33  mov     rcx, r15; pvarg
0x180013c36  call    cs:__imp_VariantInit
0x180013c3c  lea     rdx, [rbx+40h]; pvargSrc
0x180013c40  mov     rcx, r15; pvargDest
0x180013c43  call    cs:__imp_VariantCopy
0x180013c49  jmp     short loc_180013C65
0x180013c4b  mov     eax, 80070002h
0x180013c50  jmp     short loc_180013C65
0x180013c52  mov     eax, 8007000Eh
0x180013c57  jmp     short loc_180013C5E
0x180013c59  mov     eax, 80004005h
0x180013c5e  jmp     short loc_180013C65
0x180013c60  mov     eax, 80070057h
0x180013c65  mov     rcx, [rsp+88h+var_40]
0x180013c6a  xor     rcx, rsp; StackCookie
0x180013c6d  call    __security_check_cookie
0x180013c72  add     rsp, 50h
0x180013c76  pop     r15
0x180013c78  pop     r14
0x180013c7a  pop     r13
0x180013c7c  pop     r12
0x180013c7e  pop     rdi
0x180013c7f  pop     rsi
0x180013c80  pop     rbx
0x180013c81  retn
```

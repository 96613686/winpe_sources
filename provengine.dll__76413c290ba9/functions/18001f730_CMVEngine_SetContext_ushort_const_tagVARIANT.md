# CMVEngine::SetContext(ushort const *,tagVARIANT *)

- ea: `0x18001f730`
- end: `0x18001f953`
- name: `?SetContext@CMVEngine@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `547`
- prototype: `int(CMVEngine *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x1800098dc`
- `0x18000b030`
- `0x18000c2ac`
- `0x18000e838`
- `0x18001f730`
- `0x180022660`
- `0x180035bc0`
- `0x180035ebc`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001f8b8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f8b8`
- `OLEAUT32!__imp_VariantInit` at `0x18001f7a1`
- `OLEAUT32!__imp_VariantInit` at `0x18001f7b8`
- `OLEAUT32!__imp_VariantInit` at `0x18001f7a1`
- `OLEAUT32!__imp_VariantInit` at `0x18001f7b8`
- `OLEAUT32!__imp_VariantClear` at `0x18001f7ad`
- `OLEAUT32!__imp_VariantClear` at `0x18001f7f4`
- `OLEAUT32!__imp_VariantClear` at `0x18001f91f`
- `OLEAUT32!__imp_VariantClear` at `0x18001f7ad`
- `OLEAUT32!__imp_VariantClear` at `0x18001f7f4`
- `OLEAUT32!__imp_VariantClear` at `0x18001f91f`
- `OLEAUT32!__imp_VariantCopy` at `0x18001f7c6`
- `OLEAUT32!__imp_VariantCopy` at `0x18001f7c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMVEngine::SetContext(CMVEngine *this, char *a2, struct tagVARIANT *a3)
{
  __int64 v6; // rdx
  __int64 result; // rax
  HRESULT v8; // eax
  unsigned int v9; // ebx
  __int64 KeysetContext; // r8
  __int64 v11; // rdx
  unsigned int *v12; // rbx
  _QWORD *v13; // rbx
  unsigned __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // r8d
  __int128 v18; // xmm2
  IRecordInfo *v19; // xmm3_8
  const char *v20; // r9
  int v21; // [rsp+20h] [rbp-88h]
  __int64 v22; // [rsp+30h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-58h] BYREF
  void *v25[3]; // [rsp+60h] [rbp-48h] BYREF
  unsigned __int64 v26; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v24[0] = a2;
  if ( !a2 )
  {
    v6 = 2797;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v6 = 2798;
    goto LABEL_3;
  }
  VariantInit(&pvarg);
  VariantClear(&pvarg);
  VariantInit(&pvarg);
  v8 = VariantCopy(&pvarg, a3);
  v9 = v8;
  if ( v8 >= 0 )
  {
    try
    {
      KeysetContext = 0;
      v11 = *((_QWORD *)this + 26);
      if ( v11 )
      {
        v12 = (unsigned int *)((v11 + 40) & -(__int64)(*(_DWORD *)(v11 + 44) != 0));
        if ( v12 )
        {
          LODWORD(v22) = *v12;
          if ( (unsigned __int64)(unsigned int)v22 >= *(_QWORD *)(v11 + 88)
            || (KeysetContext = *__A__map_KV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std__U__less_K_2_V__allocator_U__pair___CBKV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__std___std___2__std__QEAAAEAV__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil__U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unique_struct_UtagVARIANT__P6AJPEAU1__Z_1_VariantClear__YAJ0_ZP6AX0_Z_1_VariantInit__YAX0_Z_wil___std___2__std___2__1_AEBK_Z(
                                   (__int64 *)(v11 + 80),
                                   (unsigned int *)&v22)) == 0 )
          {
            KeysetContext = ProvStateContext::CreateKeysetContext(*((_QWORD *)this + 26), *v12);
          }
        }
      }
      v13 = (_QWORD *)((char *)this + 80);
      if ( KeysetContext )
        v13 = (_QWORD *)KeysetContext;
      v26 = 7;
      v25[2] = 0;
      LOWORD(v25[0]) = 0;
      if ( *(_WORD *)a2 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)&a2[2 * v14] );
      }
      else
      {
        v14 = 0;
      }
      std::wstring::assign(v25, a2, v14);
      std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::find(
        v13,
        &v22,
        v25);
      if ( v26 >= 8 )
        operator delete(v25[0]);
      v15 = v22;
      if ( v22 == *v13 )
      {
        v16 = std::_Tree_buy<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>::_Buynode<unsigned short const * &,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>(
                v13,
                v24,
                &pvarg);
        std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>,0>>::_Insert_nohint<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>> &,std::_Tree_node<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>,void *> *>(
          (_DWORD)v13,
          (unsigned int)v24,
          v17,
          v16 + 32,
          v16);
      }
      else
      {
        v18 = *(_OWORD *)(v22 + 64);
        v19 = *(IRecordInfo **)(v22 + 80);
        *(_OWORD *)(v22 + 64) = *(_OWORD *)&pvarg.vt;
        *(_QWORD *)(v15 + 80) = pvarg.pRecInfo;
        *(_OWORD *)&pvarg.vt = v18;
        pvarg.pRecInfo = v19;
      }
      VariantClear(&pvarg);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xB13,
                             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                             v20);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF3,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)(unsigned int)v8,
      v21);
    VariantClear(&pvarg);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x18001f730  mov     [rsp+arg_18], rbx
0x18001f735  push    rsi
0x18001f736  push    rdi
0x18001f737  push    r14
0x18001f739  sub     rsp, 90h
0x18001f740  mov     rax, cs:__security_cookie
0x18001f747  xor     rax, rsp
0x18001f74a  mov     [rsp+0A8h+var_28], rax
0x18001f752  mov     rbx, r8
0x18001f755  mov     rdi, rdx
0x18001f758  mov     rsi, rcx
0x18001f75b  mov     [rsp+0A8h+var_58], rdx
0x18001f760  xor     r14d, r14d
0x18001f763  test    rdx, rdx
0x18001f766  jnz     short loc_18001F790
0x18001f768  mov     edx, 0AEDh; void *
0x18001f76d  mov     ebx, 80070057h
0x18001f772  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001f779  mov     r9d, ebx; char *
0x18001f77c  mov     rcx, [rsp+0A8h]; this
0x18001f784  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f789  mov     eax, ebx
0x18001f78b  jmp     loc_18001F92E
0x18001f790  test    rbx, rbx
0x18001f793  jnz     short loc_18001F79C
0x18001f795  mov     edx, 0AEEh
0x18001f79a  jmp     short loc_18001F76D
0x18001f79c  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18001f7a1  call    cs:__imp_VariantInit
0x18001f7a7  nop
0x18001f7a8  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18001f7ad  call    cs:__imp_VariantClear
0x18001f7b3  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18001f7b8  call    cs:__imp_VariantInit
0x18001f7be  mov     rdx, rbx; pvargSrc
0x18001f7c1  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x18001f7c6  call    cs:__imp_VariantCopy
0x18001f7cc  mov     ebx, eax
0x18001f7ce  test    eax, eax
0x18001f7d0  jns     short loc_18001F801
0x18001f7d2  mov     rcx, [rsp+0A8h]; this
0x18001f7da  mov     r9d, eax; char *
0x18001f7dd  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001f7e4  mov     edx, 0AF3h; void *
0x18001f7e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f7ee  nop
0x18001f7ef  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18001f7f4  call    cs:__imp_VariantClear
0x18001f7fa  mov     eax, ebx
0x18001f7fc  jmp     loc_18001F92E
0x18001f801  mov     r8, r14
0x18001f804  mov     rdx, [rsi+0D0h]
0x18001f80b  test    rdx, rdx
0x18001f80e  jz      short loc_18001F854
0x18001f810  mov     eax, [rdx+2Ch]
0x18001f813  lea     rcx, [rdx+28h]
0x18001f817  neg     eax
0x18001f819  sbb     rbx, rbx
0x18001f81c  and     rbx, rcx
0x18001f81f  jz      short loc_18001F854
0x18001f821  mov     eax, [rbx]
0x18001f823  mov     dword ptr [rsp+0A8h+var_78], eax
0x18001f827  cmp     rax, [rdx+58h]
0x18001f82b  jnb     short loc_18001F843
0x18001f82d  lea     rcx, [rdx+50h]
0x18001f831  lea     rdx, [rsp+0A8h+var_78]
0x18001f836  call    ??A?$map@KV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@@2@@1@AEBK@Z
0x18001f83b  mov     r8, [rax]
0x18001f83e  test    r8, r8
0x18001f841  jnz     short loc_18001F854
0x18001f843  mov     edx, [rbx]
0x18001f845  mov     rcx, [rsi+0D0h]
0x18001f84c  call    ?CreateKeysetContext@ProvStateContext@@QEAAPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@K@Z; ProvStateContext::CreateKeysetContext(ulong)
0x18001f851  mov     r8, rax
0x18001f854  lea     rbx, [rsi+50h]
0x18001f858  test    r8, r8
0x18001f85b  cmovnz  rbx, r8
0x18001f85f  mov     [rsp+0A8h+var_30], 7
0x18001f868  mov     [rsp+0A8h+var_38], r14
0x18001f86d  mov     word ptr [rsp+0A8h+var_48], r14w
0x18001f873  cmp     [rdi], r14w
0x18001f877  jnz     short loc_18001F87E
0x18001f879  mov     r8, r14
0x18001f87c  jmp     short loc_18001F88C
0x18001f87e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f882  inc     r8
0x18001f885  cmp     [rdi+r8*2], r14w
0x18001f88a  jnz     short loc_18001F882
0x18001f88c  mov     rdx, rdi; Src
0x18001f88f  lea     rcx, [rsp+0A8h+var_48]; void *
0x18001f894  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001f899  lea     r8, [rsp+0A8h+var_48]
0x18001f89e  lea     rdx, [rsp+0A8h+var_78]
0x18001f8a3  mov     rcx, rbx
0x18001f8a6  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_CategoryNode@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_CategoryNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CategoryNode>>,0>>::find(std::wstring const &)
0x18001f8ab  cmp     [rsp+0A8h+var_30], 8
0x18001f8b1  jb      short loc_18001F8BE
0x18001f8b3  mov     rcx, [rsp+0A8h+var_48]
0x18001f8b8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f8be  mov     rax, [rsp+0A8h+var_78]
0x18001f8c3  cmp     rax, [rbx]
0x18001f8c6  jnz     short loc_18001F8F2
0x18001f8c8  lea     r8, [rsp+0A8h+pvarg]
0x18001f8cd  lea     rdx, [rsp+0A8h+var_58]
0x18001f8d2  mov     rcx, rbx
0x18001f8d5  call    ??$_Buynode@AEAPEBGV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@PEAX@1@AEAPEBG$$QEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; std::_Tree_buy<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>::_Buynode<ushort const * &,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>(ushort const * &,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &&)
0x18001f8da  lea     r9, [rax+20h]
0x18001f8de  mov     qword ptr [rsp+0A8h+var_88], rax
0x18001f8e3  lea     rdx, [rsp+0A8h+var_58]
0x18001f8e8  mov     rcx, rbx
0x18001f8eb  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@PEAX@1@@Z
0x18001f8f0  jmp     short loc_18001F91A
0x18001f8f2  movups  xmm2, xmmword ptr [rax+40h]
0x18001f8f6  movsd   xmm3, qword ptr [rax+50h]
0x18001f8fb  movups  xmm0, xmmword ptr [rsp+0A8h+pvarg]
0x18001f900  movups  xmmword ptr [rax+40h], xmm0
0x18001f904  movsd   xmm1, qword ptr [rsp+0A8h+pvarg+10h]
0x18001f90a  movsd   qword ptr [rax+50h], xmm1
0x18001f90f  movups  xmmword ptr [rsp+0A8h+pvarg], xmm2
0x18001f914  movsd   qword ptr [rsp+0A8h+pvarg+10h], xmm3
0x18001f91a  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18001f91f  call    cs:__imp_VariantClear
0x18001f925  nop
0x18001f926  xor     eax, eax
0x18001f928  jmp     short loc_18001F92E
0x18001f92a  mov     eax, dword ptr [rsp+0A8h+var_78]
0x18001f92e  mov     rcx, [rsp+0A8h+var_28]
0x18001f936  xor     rcx, rsp; StackCookie
0x18001f939  call    __security_check_cookie
0x18001f93e  mov     rbx, [rsp+0A8h+arg_18]
0x18001f946  add     rsp, 90h
0x18001f94d  pop     r14
0x18001f94f  pop     rdi
0x18001f950  pop     rsi
0x18001f951  retn
```

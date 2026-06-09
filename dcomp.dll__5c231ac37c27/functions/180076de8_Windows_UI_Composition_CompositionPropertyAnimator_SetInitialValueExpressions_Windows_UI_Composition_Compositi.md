# Windows::UI::Composition::CompositionPropertyAnimator::SetInitialValueExpressions(Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::UI::Composition::ParameterOverrideEntry,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Windows::UI::Composition::ParameterOverrideEntry>>> *)

- ea: `0x180076de8`
- end: `0x180076eff`
- name: `?SetInitialValueExpressions@CompositionPropertyAnimator@Composition@UI@Windows@@IEAAJPEAVCompositionAnimation@234@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct Windows::UI::Composition::ProxyObject *, Windows::UI::Composition::CompositionAnimation *this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800772f4`
- `0x1800adc24`

## callees

- `0x180006590`
- `0x180006700`
- `0x18000bc00`
- `0x180016a08`
- `0x18002f2a0`
- `0x180030f60`
- `0x1800333b8`
- `0x180038c10`
- `0x18006c5b0`
- `0x180076de8`
- `0x180077258`
- `0x18009a988`
- `0x1800a6bec`
- `0x1800a8058`
- `0x1800c8bbc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f5aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f6b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f5aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f6b4`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionPropertyAnimator::SetInitialValueExpressions(
        struct Windows::UI::Composition::ProxyObject *a1,
        Windows::UI::Composition::CompositionAnimation *this,
        __int64 a3)
{
  Windows::UI::Composition::CompositionAnimation *v6; // rcx
  __int64 v7; // r9
  void *v8; // rbx
  unsigned int v9; // edi
  void *v11; // rcx
  int InitialValueExpressions; // eax
  __int64 v13; // rbx
  Windows::UI::Composition::CompositorCommon *v14; // rcx
  HSTRING v15; // r8
  Windows::UI::Composition::AnimationBindingManager *v16; // rcx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  int v21; // eax
  HSTRING string; // [rsp+40h] [rbp-29h] BYREF
  struct Windows::UI::Composition::InitialValueExpressionCollection *v23; // [rsp+48h] [rbp-21h] BYREF
  __int64 v24; // [rsp+50h] [rbp-19h] BYREF
  __int64 v25; // [rsp+58h] [rbp-11h] BYREF
  __int64 v26; // [rsp+60h] [rbp-9h] BYREF
  int v27; // [rsp+68h] [rbp-1h]
  struct SubchannelMaskInfo *v28; // [rsp+70h] [rbp+7h] BYREF
  __int64 i; // [rsp+78h] [rbp+Fh] BYREF
  void *lpMem[2]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v31; // [rsp+90h] [rbp+27h]
  unsigned int v32; // [rsp+98h] [rbp+2Fh]
  unsigned int v33; // [rsp+E8h] [rbp+7Fh] BYREF

  v32 = 0;
  v31 = 0;
  *(_OWORD *)lpMem = 0;
  if ( Windows::UI::Composition::CompositionAnimation::HasInitialValueExpressions(this) )
  {
    v23 = 0;
    InitialValueExpressions = Windows::UI::Composition::CompositionAnimation::GetInitialValueExpressions(v6, &v23);
    v9 = InitialValueExpressions;
    if ( InitialValueExpressions < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801C56D8, 3u, InitialValueExpressions, 0x182u, 0);
    }
    else
    {
      v13 = **((_QWORD **)v23 + 21);
      for ( i = v13; ; v13 = i )
      {
        if ( *(_BYTE *)(v13 + 25) )
        {
          Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(&v23);
          v7 = v32;
          goto LABEL_2;
        }
        v14 = (Windows::UI::Composition::CompositorCommon *)*((_QWORD *)a1 + 3);
        v24 = 0;
        v28 = 0;
        v26 = 0;
        v27 = 2;
        v33 = 0;
        string = 0;
        Windows::UI::Composition::CompositorCommon::GetBindingManager(v14);
        WindowsDeleteString(string);
        v15 = *(HSTRING *)(v13 + 32);
        string = 0;
        v17 = Windows::UI::Composition::AnimationBindingManager::SplitTargetPropertyNameAndMask(
                v16,
                a1,
                v15,
                &string,
                (struct ExpressionObjectPropertyInfo *)&v26,
                (enum DCOMPOSITION_EXPRESSION_TYPE *)&v33,
                &v28);
        v9 = v17;
        if ( v17 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801C56D8, 3u, v17, 0x19Bu, 0);
          goto LABEL_22;
        }
        v18 = Windows::UI::Composition::CompositionPropertyAnimator::GenerateExpressionInstance(
                a1,
                this,
                *(_QWORD *)(v13 + 40),
                v33,
                a3,
                &v24);
        v9 = v18;
        if ( v18 < 0 )
          break;
        v19 = v24;
        v20 = Windows::UI::Composition::CompositionPropertyAnimator::SetTarget(v24, &v26, v33, v28);
        v9 = v20;
        if ( v20 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801C56D8, 3u, v20, 0x1A9u, 0);
          goto LABEL_22;
        }
        LODWORD(v25) = *(_DWORD *)(v19 + 144);
        v21 = DynArray<unsigned int,0>::AddMultipleAndSet(lpMem, &v25);
        v9 = v21;
        if ( v21 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801C56D8, 3u, v21, 0x1AAu, 0);
          goto LABEL_22;
        }
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v24);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionAnimation>>>>,std::_Iterator_base0>::operator++(&i);
      }
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801C56D8, 3u, v18, 0x1A7u, 0);
LABEL_22:
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v24);
    }
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(&v23);
    v11 = (void *)*((_QWORD *)a1 + 31);
    if ( v11 != *((void **)a1 + 32) )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>>>(v11);
      *((_QWORD *)a1 + 32) = *((_QWORD *)a1 + 31);
    }
    v8 = lpMem[0];
  }
  else
  {
LABEL_2:
    v8 = lpMem[0];
    if ( (_DWORD)v7 )
      Windows::UI::Composition::ProxyObject::SetReferenceArrayProperty(a1, 8, lpMem[0], v7);
    v9 = 0;
  }
  if ( v8 != lpMem[1] )
    operator delete(v8);
  return v9;
}

```

## disassembly

```asm
0x180076de8  mov     [rsp-8+arg_0], rbx
0x180076ded  mov     [rsp-8+arg_8], rsi
0x180076df2  push    rbp
0x180076df3  push    rdi
0x180076df4  push    r12
0x180076df6  push    r14
0x180076df8  push    r15
0x180076dfa  lea     rbp, [rsp-37h]
0x180076dff  sub     rsp, 0A0h
0x180076e06  xor     r12d, r12d
0x180076e09  mov     rsi, rcx
0x180076e0c  mov     r9d, r12d
0x180076e0f  xorps   xmm0, xmm0
0x180076e12  mov     rcx, rdx; this
0x180076e15  mov     [rbp+57h+var_28], r9d
0x180076e19  mov     r15, r8
0x180076e1c  mov     [rbp+57h+var_30], r12
0x180076e20  mov     r14, rdx
0x180076e23  movdqu  xmmword ptr [rbp+57h+lpMem], xmm0
0x180076e28  call    ?HasInitialValueExpressions@CompositionAnimation@Composition@UI@Windows@@QEBA_NXZ; Windows::UI::Composition::CompositionAnimation::HasInitialValueExpressions(void)
0x180076e2d  test    al, al
0x180076e2f  jnz     loc_180076EBF
0x180076e35  mov     rbx, [rbp+57h+lpMem]
0x180076e39  test    r9d, r9d
0x180076e3c  jnz     loc_180076EEA
0x180076e42  mov     edi, r12d
0x180076e45  cmp     rbx, [rbp+57h+lpMem+8]
0x180076e49  jz      short loc_180076E53
0x180076e4b  mov     rcx, rbx; lpMem
0x180076e4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180076e53  lea     r11, [rsp+0C0h+var_20]
0x180076e5b  mov     eax, edi
0x180076e5d  mov     rbx, [r11+30h]
0x180076e61  mov     rsi, [r11+38h]
0x180076e65  mov     rsp, r11
0x180076e68  pop     r15
0x180076e6a  pop     r14
0x180076e6c  pop     r12
0x180076e6e  pop     rdi
0x180076e6f  pop     rbp
0x180076e70  retn
0x180076e71  cmp     [rbx+19h], r12b
0x180076e75  jz      loc_18017F582
0x180076e7b  lea     rcx, [rbp+57h+var_78]
0x180076e7f  call    ?InternalUnlock@?$RefPtr@VNaturalMotionAnimation@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(void)
0x180076e84  mov     r9d, [rbp+57h+var_28]
0x180076e88  jmp     short loc_180076E35
0x180076e8a  lea     rcx, [rbp+57h+var_78]
0x180076e8e  call    ?InternalUnlock@?$RefPtr@VNaturalMotionAnimation@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(void)
0x180076e93  mov     rdx, [rsi+100h]
0x180076e9a  mov     rcx, [rsi+0F8h]; void *
0x180076ea1  cmp     rcx, rdx
0x180076ea4  jz      short loc_180076EB9
0x180076ea6  call    ??$_Destroy_range@V?$allocator@V?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@@std@@@std@@YAXPEAV?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@QEAV123@AEAV?$allocator@V?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>>>(Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator> *,Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator> * const,std::allocator<Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>> &)
0x180076eab  mov     rax, [rsi+0F8h]
0x180076eb2  mov     [rsi+100h], rax
0x180076eb9  mov     rbx, [rbp+57h+lpMem]
0x180076ebd  jmp     short loc_180076E45
0x180076ebf  lea     rdx, [rbp+57h+var_78]; struct Windows::UI::Composition::InitialValueExpressionCollection **
0x180076ec3  mov     [rbp+57h+var_78], r12
0x180076ec7  call    ?GetInitialValueExpressions@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAPEAVInitialValueExpressionCollection@234@@Z; Windows::UI::Composition::CompositionAnimation::GetInitialValueExpressions(Windows::UI::Composition::InitialValueExpressionCollection * *)
0x180076ecc  mov     edi, eax
0x180076ece  test    eax, eax
0x180076ed0  js      loc_18017F6EB
0x180076ed6  mov     rax, [rbp+57h+var_78]
0x180076eda  mov     rbx, [rax+0A8h]
0x180076ee1  mov     rbx, [rbx]
0x180076ee4  mov     [rbp+57h+var_48], rbx
0x180076ee8  jmp     short loc_180076E71
0x180076eea  mov     r8, rbx
0x180076eed  mov     edx, 8
0x180076ef2  mov     rcx, rsi
0x180076ef5  call    ?SetReferenceArrayProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@PEBI_K@Z; Windows::UI::Composition::ProxyObject::SetReferenceArrayProperty(DCOMPOSITION_PROPERTY_ID,uint const *,unsigned __int64)
0x180076efa  jmp     loc_180076E42
0x18017f582  mov     rcx, [rsi+18h]; this
0x18017f586  mov     [rbp+57h+var_70], r12
0x18017f58a  mov     [rbp+57h+var_50], r12
0x18017f58e  mov     [rbp+57h+var_60], r12
0x18017f592  mov     [rbp+57h+var_58], 2
0x18017f599  mov     [rbp+57h+arg_18], r12d
0x18017f59d  mov     [rbp+57h+string], r12
0x18017f5a1  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x18017f5a6  mov     rcx, [rbp+57h+string]; string
0x18017f5aa  call    cs:__imp_WindowsDeleteString
0x18017f5b0  mov     r8, [rbx+20h]; HSTRING
0x18017f5b4  lea     rax, [rbp+57h+var_50]
0x18017f5b8  mov     [rsp+0C0h+var_90], rax; struct SubchannelMaskInfo **
0x18017f5bd  lea     r9, [rbp+57h+string]; HSTRING *
0x18017f5c1  lea     rax, [rbp+57h+arg_18]
0x18017f5c5  mov     [rbp+57h+string], r12
0x18017f5c9  mov     [rsp+0C0h+var_98], rax; enum DCOMPOSITION_EXPRESSION_TYPE *
0x18017f5ce  mov     rdx, rsi; struct Windows::UI::Composition::ProxyObject *
0x18017f5d1  lea     rax, [rbp+57h+var_60]
0x18017f5d5  mov     [rsp+0C0h+var_A0], rax; struct ExpressionObjectPropertyInfo *
0x18017f5da  call    ?SplitTargetPropertyNameAndMask@AnimationBindingManager@Composition@UI@Windows@@QEAAJPEAVProxyObject@234@PEAUHSTRING__@@PEAPEAU6@PEAVExpressionObjectPropertyInfo@@PEAW4DCOMPOSITION_EXPRESSION_TYPE@@PEAPEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::AnimationBindingManager::SplitTargetPropertyNameAndMask(Windows::UI::Composition::ProxyObject *,HSTRING__ *,HSTRING__ * *,ExpressionObjectPropertyInfo *,DCOMPOSITION_EXPRESSION_TYPE *,SubchannelMaskInfo * *)
0x18017f5df  mov     edi, eax
0x18017f5e1  test    eax, eax
0x18017f5e3  js      loc_18017F68A
0x18017f5e9  mov     r9d, [rbp+57h+arg_18]
0x18017f5ed  lea     rax, [rbp+57h+var_70]
0x18017f5f1  mov     r8, [rbx+28h]
0x18017f5f5  mov     rdx, r14
0x18017f5f8  mov     [rsp+0C0h+var_98], rax
0x18017f5fd  mov     rcx, rsi
0x18017f600  mov     [rsp+0C0h+var_A0], r15
0x18017f605  call    ?GenerateExpressionInstance@CompositionPropertyAnimator@Composition@UI@Windows@@IEAAJPEAVCompositionAnimation@234@PEAVExpressionAnimation@234@W4DCOMPOSITION_EXPRESSION_TYPE@@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@PEAPEAV1234@@Z; Windows::UI::Composition::CompositionPropertyAnimator::GenerateExpressionInstance(Windows::UI::Composition::CompositionAnimation *,Windows::UI::Composition::ExpressionAnimation *,DCOMPOSITION_EXPRESSION_TYPE,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry> *,Windows::UI::Composition::CompositionPropertyAnimator * *)
0x18017f60a  mov     edi, eax
0x18017f60c  test    eax, eax
0x18017f60e  js      loc_18017F6DC
0x18017f614  mov     rbx, [rbp+57h+var_70]
0x18017f618  lea     rdx, [rbp+57h+var_60]
0x18017f61c  mov     r9, [rbp+57h+var_50]
0x18017f620  mov     rcx, rbx
0x18017f623  mov     r8d, [rbp+57h+arg_18]
0x18017f627  call    ?SetTarget@CompositionPropertyAnimator@Composition@UI@Windows@@QEAAJPEAVExpressionObjectPropertyInfo@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::CompositionPropertyAnimator::SetTarget(ExpressionObjectPropertyInfo *,DCOMPOSITION_EXPRESSION_TYPE,SubchannelMaskInfo *)
0x18017f62c  mov     edi, eax
0x18017f62e  test    eax, eax
0x18017f630  js      loc_18017F6CD
0x18017f636  mov     eax, [rbx+90h]
0x18017f63c  lea     rdx, [rbp+57h+var_68]
0x18017f640  lea     rcx, [rbp+57h+lpMem]
0x18017f644  mov     dword ptr [rbp+57h+var_68], eax
0x18017f647  call    ?AddMultipleAndSet@?$DynArray@I$0A@@@QEAAJPEFBII@Z; DynArray<uint,0>::AddMultipleAndSet(uint const *,uint)
0x18017f64c  mov     edi, eax
0x18017f64e  test    eax, eax
0x18017f650  js      short loc_18017F67B
0x18017f652  mov     rcx, [rbp+57h+string]; string
0x18017f656  call    cs:__imp_WindowsDeleteString
0x18017f65c  lea     rcx, [rbp+57h+var_70]; void *
0x18017f660  mov     [rbp+57h+string], r12
0x18017f664  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18017f669  lea     rcx, [rbp+57h+var_48]
0x18017f66d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$RefPtr@VCompositionAnimation@Composition@UI@Windows@@@WRL2@4@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionAnimation>>>>,std::_Iterator_base0>::operator++(void)
0x18017f672  mov     rbx, [rbp+57h+var_48]
0x18017f676  jmp     loc_180076E71
0x18017f67b  mov     [rsp+0C0h+var_98], r12
0x18017f680  mov     dword ptr [rsp+0C0h+var_A0], 1AAh
0x18017f688  jmp     short loc_18017F697
0x18017f68a  mov     [rsp+0C0h+var_98], r12; void *
0x18017f68f  mov     dword ptr [rsp+0C0h+var_A0], 19Bh; unsigned int
0x18017f697  mov     r8d, 3; unsigned int
0x18017f69d  lea     rdx, qword_1801C56D8; int *
0x18017f6a4  mov     r9d, eax; int
0x18017f6a7  lea     ecx, [r8+1]; unsigned int
0x18017f6ab  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18017f6b0  mov     rcx, [rbp+57h+string]; string
0x18017f6b4  call    cs:__imp_WindowsDeleteString
0x18017f6ba  lea     rcx, [rbp+57h+var_70]; void *
0x18017f6be  mov     [rbp+57h+string], r12
0x18017f6c2  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18017f6c7  nop
0x18017f6c8  jmp     loc_180076E8A
0x18017f6cd  mov     [rsp+0C0h+var_98], r12
0x18017f6d2  mov     dword ptr [rsp+0C0h+var_A0], 1A9h
0x18017f6da  jmp     short loc_18017F697
0x18017f6dc  mov     [rsp+0C0h+var_98], r12
0x18017f6e1  mov     dword ptr [rsp+0C0h+var_A0], 1A7h
0x18017f6e9  jmp     short loc_18017F697
0x18017f6eb  mov     r8d, 3; unsigned int
0x18017f6f1  mov     [rsp+0C0h+var_98], r12; void *
0x18017f6f6  mov     r9d, eax; int
0x18017f6f9  mov     dword ptr [rsp+0C0h+var_A0], 182h; unsigned int
0x18017f701  lea     rdx, qword_1801C56D8; int *
0x18017f708  lea     ecx, [r8+1]; unsigned int
0x18017f70c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18017f711  nop
0x18017f712  jmp     loc_180076E8A
```

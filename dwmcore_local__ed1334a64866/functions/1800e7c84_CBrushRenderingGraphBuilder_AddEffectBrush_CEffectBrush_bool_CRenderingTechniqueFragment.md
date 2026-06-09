# CBrushRenderingGraphBuilder::AddEffectBrush(CEffectBrush *,bool,CRenderingTechniqueFragment * *)

- ea: `0x1800e7c84`
- end: `0x1800e81c2`
- name: `?AddEffectBrush@CBrushRenderingGraphBuilder@@AEAAJPEAVCEffectBrush@@_NPEAPEAVCRenderingTechniqueFragment@@@Z`
- size: `1342`
- prototype: `__int64 __fastcall(CBrushRenderingGraphBuilder *__hidden this, struct CEffectBrush *, bool, struct CRenderingTechniqueFragment **)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1800e745c`

## callees

- `0x180042de0`
- `0x180044220`
- `0x1800d5b30`
- `0x1800e5208`
- `0x1800e5aa8`
- `0x1800e6fb4`
- `0x1800e745c`
- `0x1800e75d4`
- `0x1800e7654`
- `0x1800e76b0`
- `0x1800e79d0`
- `0x1800e7b6c`
- `0x1800e7ba4`
- `0x1800e7c84`
- `0x1801ae174`
- `0x1801c6b5c`
- `0x1801c8c40`
- `0x1801d17a0`
- `0x1801ed270`
- `0x180200468`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e7cee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e7cee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800e7ce4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800e7ce4`

## pseudocode

```c
__int64 __fastcall CBrushRenderingGraphBuilder::AddEffectBrush(
        CBrushRenderingGraphBuilder *this,
        struct CEffectBrush *a2,
        char a3,
        struct CRenderingTechniqueFragment **a4)
{
  CCompiledEffectTemplate *v4; // rdi
  char v5; // r12
  struct CRenderingTechniqueFragment *v7; // rbx
  __int64 v8; // r15
  const struct Windows::UI::Composition::ICompiledEffect *CompiledEffectNoRef; // rax
  __int64 v10; // rdi
  const struct Windows::UI::Composition::ICompiledEffect *v11; // r14
  struct _TP_WORK *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // r15d
  unsigned int v15; // esi
  unsigned int v16; // edi
  int v17; // r13d
  bool v18; // r12
  void *v19; // rax
  __int64 v20; // rdi
  struct CRenderingTechniqueFragment *v21; // rdx
  unsigned int v22; // eax
  unsigned int i; // r15d
  __int64 v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // edi
  unsigned int v27; // eax
  __int64 v28; // r8
  _QWORD *v29; // rdx
  struct CBrush *Input; // rax
  struct CBrush *v31; // r14
  bool v32; // r8
  int v33; // edi
  __int64 v34; // r8
  _QWORD *v35; // rdx
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  int v41; // r9d
  unsigned int v43[2]; // [rsp+28h] [rbp-A9h]
  unsigned int v44; // [rsp+28h] [rbp-A9h]
  int v45; // [rsp+30h] [rbp-A1h]
  int v46; // [rsp+38h] [rbp-99h] BYREF
  int v47; // [rsp+3Ch] [rbp-95h] BYREF
  unsigned int v48; // [rsp+40h] [rbp-91h]
  unsigned int v49; // [rsp+44h] [rbp-8Dh]
  __int64 v50; // [rsp+48h] [rbp-89h] BYREF
  struct CRenderingTechniqueFragment *v51; // [rsp+50h] [rbp-81h] BYREF
  __int128 v52; // [rsp+58h] [rbp-79h] BYREF
  __int64 v53; // [rsp+68h] [rbp-69h]
  const struct Windows::UI::Composition::ICompiledEffect *v54; // [rsp+70h] [rbp-61h]
  struct CBrush *v55; // [rsp+78h] [rbp-59h] BYREF
  struct CRenderingTechniqueFragment *v56[2]; // [rsp+80h] [rbp-51h] BYREF
  struct CRenderingTechniqueFragment *v57; // [rsp+90h] [rbp-41h]
  __int64 v58; // [rsp+98h] [rbp-39h] BYREF
  __int64 v59; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-19h]
  __int64 v63; // [rsp+C0h] [rbp-11h]
  int v64; // [rsp+C8h] [rbp-9h]
  __int64 v65; // [rsp+D0h] [rbp-1h] BYREF
  int v66; // [rsp+D8h] [rbp+7h]
  _QWORD v67[9]; // [rsp+E0h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  v4 = (CCompiledEffectTemplate *)*((_QWORD *)a2 + 14);
  v5 = a3;
  v7 = 0;
  v8 = *(_QWORD *)(*((_QWORD *)v4 + 10) + 56LL);
  v63 = v8;
  CompiledEffectNoRef = CCompiledEffectTemplate::GetCompiledEffectNoRef(v4);
  v10 = *((_QWORD *)v4 + 10);
  v11 = CompiledEffectNoRef;
  v54 = CompiledEffectNoRef;
  v12 = *(struct _TP_WORK **)(v10 + 64);
  if ( v12 )
  {
    WaitForThreadpoolWorkCallbacks(v12, 0);
    CloseThreadpoolWork(*(PTP_WORK *)(v10 + 64));
    *(_QWORD *)(v10 + 64) = 0;
  }
  v62 = *(_QWORD *)(v10 + 80);
  v57 = (struct CRenderingTechniqueFragment *)*((_QWORD *)a2 + 20);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 32LL))(v8);
  v49 = v13;
  v52 = 0;
  v53 = 0;
  v14 = v13 - 1;
  v48 = v13 - 1;
  if ( v13 != 1 )
  {
    std::vector<CBrushRenderingGraphBuilder::SubgraphOutput>::_Resize_reallocate<std::_Value_init_tag>(&v52, v13 - 1);
    v13 = v49;
  }
  v15 = 0;
  while ( 2 )
  {
    if ( v15 >= v13 )
    {
      v33 = 0;
      v51 = 0;
      *a4 = v7;
    }
    else
    {
      v16 = (*(__int64 (__fastcall **)(const struct Windows::UI::Composition::ICompiledEffect *, _QWORD))(*(_QWORD *)v11 + 40LL))(
              v11,
              v15);
      v17 = v16 & 8;
      v18 = v5 && (v15 == v14 || (v16 & 8) != 0);
      v19 = MIDL_user_allocate(0x78u);
      if ( v19 )
      {
        LOBYTE(v45) = v18;
        v43[0] = v16;
        v20 = CRenderingTechniqueFragment::CRenderingTechniqueFragment(v19, v57, v62, v15, *(_QWORD *)v43, v45);
      }
      else
      {
        v20 = 0;
      }
      v21 = v7;
      v7 = (struct CRenderingTechniqueFragment *)v20;
      v51 = (struct CRenderingTechniqueFragment *)v20;
      if ( v21 )
        std::default_delete<CRenderingTechniqueFragment>::operator()();
      if ( v20 )
      {
        v22 = (*(__int64 (__fastcall **)(const struct Windows::UI::Composition::ICompiledEffect *, _QWORD))(*(_QWORD *)v11 + 32LL))(
                v11,
                v15);
        v47 = v22;
        for ( i = 0; i < v22; ++i )
        {
          v24 = *(_QWORD *)v11;
          LOBYTE(v46) = 0;
          v25 = (*(__int64 (__fastcall **)(const struct Windows::UI::Composition::ICompiledEffect *, _QWORD, _QWORD, int *))(v24 + 48))(
                  v11,
                  v15,
                  i,
                  &v46);
          v26 = v25;
          if ( (_BYTE)v46 )
          {
            if ( v25 >= (unsigned __int64)((__int64)(*((_QWORD *)&v52 + 1) - v52) >> 4) )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xFA,
                (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\brushrenderinggraphbuilder.cpp",
                (const char *)retaddr);
            v27 = *(_DWORD *)(v52 + 16LL * v25);
            if ( v27 == -1 )
            {
              v28 = *(_QWORD *)(v52 + 16LL * v26 + 8);
              *(_QWORD *)(v52 + 16LL * v26 + 8) = 0;
              v29 = (_QWORD *)*((_QWORD *)v7 + 5);
              v59 = v28;
              if ( v29 == *((_QWORD **)v7 + 6) )
              {
                std::vector<CRenderingTechniqueFragment::FragmentInput>::_Emplace_reallocate<CRenderingTechniqueFragment::FragmentInput>(
                  (char *)v7 + 32,
                  v29,
                  &v58);
              }
              else
              {
                v59 = 0;
                *v29 = v58;
                v29[1] = v28;
                *((_QWORD *)v7 + 5) += 16LL;
              }
              std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v59);
            }
            else
            {
              CRenderingTechniqueFragment::AddIntermediateInput(v7, v27);
            }
          }
          else
          {
            Input = CEffectBrush::GetInput(a2, v25);
            v31 = Input;
            if ( Input && *((_BYTE *)Input + 96) )
            {
              v32 = v18
                 || (*(unsigned __int8 (__fastcall **)(const struct Windows::UI::Composition::ICompiledEffect *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v54 + 56LL))(
                      v54,
                      v15,
                      i,
                      0,
                      0);
              v55 = (struct CBrush *)&v50;
              v50 = 0;
              v56[0] = 0;
              LOBYTE(v56[1]) = 1;
              v33 = CBrushRenderingGraphBuilder::AddBrush(this, v31, v32, v56);
              wil::details::out_param_t<std::unique_ptr<CRenderingTechniqueFragment>>::~out_param_t<std::unique_ptr<CRenderingTechniqueFragment>>(&v55);
              if ( v33 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0x11Du, 0);
                std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v50);
                goto LABEL_61;
              }
              v34 = v50;
              v50 = 0;
              v35 = (_QWORD *)*((_QWORD *)v7 + 5);
              v61 = v34;
              if ( v35 == *((_QWORD **)v7 + 6) )
              {
                std::vector<CRenderingTechniqueFragment::FragmentInput>::_Emplace_reallocate<CRenderingTechniqueFragment::FragmentInput>(
                  (char *)v7 + 32,
                  v35,
                  &v60);
              }
              else
              {
                v61 = 0;
                *v35 = v60;
                v35[1] = v34;
                *((_QWORD *)v7 + 5) += 16LL;
              }
              std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v61);
              std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v50);
            }
            else
            {
              v55 = Input;
              *(_OWORD *)v56 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v63 + 48LL))(v63, v26) )
              {
                v56[0] = v57;
                LODWORD(v56[1]) = v26;
              }
              else
              {
                v56[0] = 0;
                LODWORD(v56[1]) = 0;
              }
              CBrushRenderingGraphBuilder::AddNamedInputToFragment(
                this,
                v7,
                (const struct CBrushRenderingGraph::GraphInputParameters *)&v55);
            }
            v11 = v54;
          }
          v22 = v47;
        }
        v14 = v48;
        if ( v15 == v48 )
        {
LABEL_52:
          v13 = v49;
          ++v15;
          v5 = a3;
          continue;
        }
        v36 = CBrushRenderingGraphBuilder::CheckFragmentSize(this, v7);
        v33 = v36;
        if ( v36 < 0 )
        {
          v44 = 315;
        }
        else
        {
          if ( v17 )
          {
            v67[0] = v7;
            v39 = v52;
            v40 = 16LL * v15;
            v7 = 0;
            v66 = -1;
            *(_DWORD *)(v40 + v52) = -1;
            std::unique_ptr<CRenderingTechniqueFragment>::operator=<std::default_delete<CRenderingTechniqueFragment>,0>(
              v39 + 8 + v40,
              v67);
            std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(v67);
            goto LABEL_51;
          }
          v47 = 0;
          v36 = CBrushRenderingGraphBuilder::CreateTechniqueForFragment(this, &v51, &v47);
          v33 = v36;
          if ( v36 >= 0 )
          {
            v37 = v52;
            v64 = v47;
            v38 = 16LL * v15;
            v65 = 0;
            *(_DWORD *)(v38 + v52) = v47;
            std::unique_ptr<CRenderingTechniqueFragment>::operator=<std::default_delete<CRenderingTechniqueFragment>,0>(
              v37 + 8 + v38,
              &v65);
            std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v65);
            v7 = v51;
LABEL_51:
            v14 = v48;
            goto LABEL_52;
          }
          v44 = 320;
        }
        v41 = v36;
      }
      else
      {
        v33 = -2147024882;
        v41 = -2147024882;
        v44 = 234;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v41, v44, 0);
    }
    break;
  }
LABEL_61:
  if ( (_QWORD)v52 )
  {
    std::_Destroy_range<std::allocator<CBrushRenderingGraphBuilder::SubgraphOutput>>(v52, *((_QWORD *)&v52 + 1));
    std::_Deallocate<16>(v52, (v53 - v52) & 0xFFFFFFFFFFFFFFF0uLL);
    v53 = 0;
    v52 = 0;
  }
  std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v51);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x1800e7c84  mov     rax, rsp
0x1800e7c87  mov     [rax+20h], r9
0x1800e7c8b  mov     [rax+18h], r8b
0x1800e7c8f  mov     [rax+10h], rdx
0x1800e7c93  mov     [rax+8], rcx
0x1800e7c97  push    rbp
0x1800e7c98  push    rbx
0x1800e7c99  push    rsi
0x1800e7c9a  push    rdi
0x1800e7c9b  push    r12
0x1800e7c9d  push    r13
0x1800e7c9f  push    r14
0x1800e7ca1  push    r15
0x1800e7ca3  lea     rbp, [rax-5Fh]
0x1800e7ca7  sub     rsp, 0E8h
0x1800e7cae  mov     rdi, [rdx+70h]
0x1800e7cb2  mov     r12b, r8b
0x1800e7cb5  mov     rcx, rdi; this
0x1800e7cb8  mov     rsi, rdx
0x1800e7cbb  xor     ebx, ebx
0x1800e7cbd  mov     rax, [rdi+50h]
0x1800e7cc1  mov     r15, [rax+38h]
0x1800e7cc5  mov     [rbp+57h+var_68], r15
0x1800e7cc9  call    ?GetCompiledEffectNoRef@CCompiledEffectTemplate@@QEBAPEBUICompiledEffect@Composition@UI@Windows@@XZ; CCompiledEffectTemplate::GetCompiledEffectNoRef(void)
0x1800e7cce  mov     rdi, [rdi+50h]
0x1800e7cd2  mov     r14, rax
0x1800e7cd5  mov     [rbp+57h+var_B8], rax
0x1800e7cd9  mov     rcx, [rdi+40h]; pwk
0x1800e7cdd  test    rcx, rcx
0x1800e7ce0  jz      short loc_1800E7CF8
0x1800e7ce2  xor     edx, edx; fCancelPendingCallbacks
0x1800e7ce4  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800e7cea  mov     rcx, [rdi+40h]; pwk
0x1800e7cee  call    cs:__imp_CloseThreadpoolWork
0x1800e7cf4  mov     [rdi+40h], rbx
0x1800e7cf8  mov     rax, [rdi+50h]
0x1800e7cfc  mov     rcx, r15
0x1800e7cff  mov     [rbp+57h+var_70], rax
0x1800e7d03  mov     rax, [rsi+0A0h]
0x1800e7d0a  mov     [rbp+57h+var_98], rax
0x1800e7d0e  mov     rax, [r15]
0x1800e7d11  mov     rax, [rax+20h]
0x1800e7d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7d1a  xorps   xmm0, xmm0
0x1800e7d1d  mov     dword ptr [rsp+120h+var_E8+4], eax
0x1800e7d21  movdqu  [rbp+57h+var_D0], xmm0
0x1800e7d26  mov     [rbp+57h+var_C0], rbx
0x1800e7d2a  lea     r15d, [rax-1]
0x1800e7d2e  mov     dword ptr [rsp+120h+var_E8], r15d
0x1800e7d33  mov     edx, r15d
0x1800e7d36  test    r15d, r15d
0x1800e7d39  jz      short loc_1800E7D48
0x1800e7d3b  lea     rcx, [rbp+57h+var_D0]
0x1800e7d3f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@USubgraphOutput@CBrushRenderingGraphBuilder@@V?$allocator@USubgraphOutput@CBrushRenderingGraphBuilder@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<CBrushRenderingGraphBuilder::SubgraphOutput>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800e7d44  mov     eax, dword ptr [rsp+120h+var_E8+4]
0x1800e7d48  xor     esi, esi
0x1800e7d4a  cmp     esi, eax
0x1800e7d4c  jnb     loc_1800E815A
0x1800e7d52  mov     rax, [r14]
0x1800e7d55  mov     edx, esi
0x1800e7d57  mov     rcx, r14
0x1800e7d5a  mov     rax, [rax+28h]
0x1800e7d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7d63  mov     r13d, eax
0x1800e7d66  mov     edi, eax
0x1800e7d68  and     r13d, 8
0x1800e7d6c  test    r12b, r12b
0x1800e7d6f  jz      short loc_1800E7D80
0x1800e7d71  cmp     esi, r15d
0x1800e7d74  jz      short loc_1800E7D7B
0x1800e7d76  test    r13d, r13d
0x1800e7d79  jz      short loc_1800E7D80
0x1800e7d7b  mov     r12b, 1
0x1800e7d7e  jmp     short loc_1800E7D83
0x1800e7d80  xor     r12b, r12b
0x1800e7d83  mov     ecx, 78h ; 'x'; size
0x1800e7d88  call    MIDL_user_allocate
0x1800e7d8d  test    rax, rax
0x1800e7d90  jz      short loc_1800E7DB3
0x1800e7d92  mov     r8, [rbp+57h+var_70]
0x1800e7d96  mov     r9d, esi
0x1800e7d99  mov     rdx, [rbp+57h+var_98]
0x1800e7d9d  mov     rcx, rax
0x1800e7da0  mov     byte ptr [rsp+120h+var_F8], r12b
0x1800e7da5  mov     [rsp+120h+var_100], edi
0x1800e7da9  call    ??0CRenderingTechniqueFragment@@QEAA@PEAUIEffectInstance@Composition@UI@Windows@@PEAVCShaderCache@@IW4Enum@CompiledEffectSubgraphFlags@234@_N@Z; CRenderingTechniqueFragment::CRenderingTechniqueFragment(Windows::UI::Composition::IEffectInstance *,CShaderCache *,uint,Windows::UI::Composition::CompiledEffectSubgraphFlags::Enum,bool)
0x1800e7dae  mov     rdi, rax
0x1800e7db1  jmp     short loc_1800E7DB5
0x1800e7db3  xor     edi, edi
0x1800e7db5  mov     rdx, rbx
0x1800e7db8  mov     rbx, rdi
0x1800e7dbb  mov     [rsp+120h+var_D8], rbx
0x1800e7dc0  test    rdx, rdx
0x1800e7dc3  jz      short loc_1800E7DCA
0x1800e7dc5  call    ??R?$default_delete@VCRenderingTechniqueFragment@@@std@@QEBAXPEAVCRenderingTechniqueFragment@@@Z; std::default_delete<CRenderingTechniqueFragment>::operator()(CRenderingTechniqueFragment *)
0x1800e7dca  test    rdi, rdi
0x1800e7dcd  jz      loc_1800E8132
0x1800e7dd3  mov     rax, [r14]
0x1800e7dd6  mov     edx, esi
0x1800e7dd8  mov     rcx, r14
0x1800e7ddb  mov     rax, [rax+20h]
0x1800e7ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7de4  mov     [rsp+120h+var_EC], eax
0x1800e7de8  xor     r15d, r15d
0x1800e7deb  cmp     r15d, eax
0x1800e7dee  jnb     loc_1800E7FF5
0x1800e7df4  mov     rcx, [r14]
0x1800e7df7  lea     r9, [rsp+120h+var_F0]
0x1800e7dfc  mov     r8d, r15d
0x1800e7dff  mov     byte ptr [rsp+120h+var_F0], 0
0x1800e7e04  mov     edx, esi
0x1800e7e06  mov     rax, [rcx+30h]
0x1800e7e0a  mov     rcx, r14
0x1800e7e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7e12  cmp     byte ptr [rsp+120h+var_F0], 0
0x1800e7e17  mov     edi, eax
0x1800e7e19  jz      loc_1800E7EA8
0x1800e7e1f  mov     rax, qword ptr [rbp+57h+var_D0+8]
0x1800e7e23  mov     ecx, edi
0x1800e7e25  mov     rdx, qword ptr [rbp+57h+var_D0]
0x1800e7e29  mov     r9, [rbp+5Fh]; char *
0x1800e7e2d  sub     rax, rdx
0x1800e7e30  sar     rax, 4
0x1800e7e34  cmp     rdi, rax
0x1800e7e37  jnb     loc_1800E80C7
0x1800e7e3d  add     rcx, rcx
0x1800e7e40  mov     eax, [rdx+rcx*8]
0x1800e7e43  cmp     eax, 0FFFFFFFFh
0x1800e7e46  jnz     short loc_1800E7E99
0x1800e7e48  mov     r8, [rdx+rcx*8+8]
0x1800e7e4d  mov     qword ptr [rdx+rcx*8+8], 0
0x1800e7e56  mov     rdx, [rbx+28h]
0x1800e7e5a  mov     [rbp+57h+var_88], r8
0x1800e7e5e  cmp     rdx, [rbx+30h]
0x1800e7e62  jz      short loc_1800E7E7E
0x1800e7e64  mov     rax, [rbp+57h+var_90]
0x1800e7e68  mov     [rbp+57h+var_88], 0
0x1800e7e70  mov     [rdx], rax
0x1800e7e73  mov     [rdx+8], r8
0x1800e7e77  add     qword ptr [rbx+28h], 10h
0x1800e7e7c  jmp     short loc_1800E7E8B
0x1800e7e7e  lea     r8, [rbp+57h+var_90]
0x1800e7e82  lea     rcx, [rbx+20h]
0x1800e7e86  call    ??$_Emplace_reallocate@UFragmentInput@CRenderingTechniqueFragment@@@?$vector@UFragmentInput@CRenderingTechniqueFragment@@V?$allocator@UFragmentInput@CRenderingTechniqueFragment@@@std@@@std@@AEAAPEAUFragmentInput@CRenderingTechniqueFragment@@QEAU23@$$QEAU23@@Z; std::vector<CRenderingTechniqueFragment::FragmentInput>::_Emplace_reallocate<CRenderingTechniqueFragment::FragmentInput>(CRenderingTechniqueFragment::FragmentInput * const,CRenderingTechniqueFragment::FragmentInput &&)
0x1800e7e8b  lea     rcx, [rbp+57h+var_88]
0x1800e7e8f  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e7e94  jmp     loc_1800E7FE9
0x1800e7e99  mov     edx, eax; unsigned int
0x1800e7e9b  mov     rcx, rbx; this
0x1800e7e9e  call    ?AddIntermediateInput@CRenderingTechniqueFragment@@QEAAXI@Z; CRenderingTechniqueFragment::AddIntermediateInput(uint)
0x1800e7ea3  jmp     loc_1800E7FE9
0x1800e7ea8  mov     rcx, [rbp+57h+arg_8]; this
0x1800e7eac  mov     edx, edi; unsigned int
0x1800e7eae  call    ?GetInput@CEffectBrush@@QEBAPEAVCBrush@@I@Z; CEffectBrush::GetInput(uint)
0x1800e7eb3  mov     r14, rax
0x1800e7eb6  test    rax, rax
0x1800e7eb9  jz      loc_1800E7F97
0x1800e7ebf  cmp     byte ptr [rax+60h], 0
0x1800e7ec3  jz      loc_1800E7F97
0x1800e7ec9  test    r12b, r12b
0x1800e7ecc  jnz     short loc_1800E7EFB
0x1800e7ece  mov     r10, [rbp+57h+var_B8]
0x1800e7ed2  xor     r9d, r9d
0x1800e7ed5  mov     r8d, r15d
0x1800e7ed8  mov     qword ptr [rsp+120h+var_100], 0
0x1800e7ee1  mov     edx, esi
0x1800e7ee3  mov     rcx, [r10]
0x1800e7ee6  mov     rax, [rcx+38h]
0x1800e7eea  mov     rcx, r10
0x1800e7eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7ef2  test    al, al
0x1800e7ef4  jnz     short loc_1800E7EFB
0x1800e7ef6  xor     r8b, r8b
0x1800e7ef9  jmp     short loc_1800E7EFE
0x1800e7efb  mov     r8b, 1; bool
0x1800e7efe  mov     rcx, [rbp+57h+arg_0]; this
0x1800e7f02  lea     rax, [rsp+120h+var_E0]
0x1800e7f07  lea     r9, [rbp+57h+var_A8]; struct CRenderingTechniqueFragment **
0x1800e7f0b  mov     [rbp+57h+var_B0], rax
0x1800e7f0f  mov     rdx, r14; struct CBrush *
0x1800e7f12  mov     [rsp+120h+var_E0], 0
0x1800e7f1b  mov     [rbp+57h+var_A8], 0
0x1800e7f23  mov     byte ptr [rbp+57h+var_A8+8], 1
0x1800e7f27  call    ?AddBrush@CBrushRenderingGraphBuilder@@AEAAJPEAVCBrush@@_NPEAPEAVCRenderingTechniqueFragment@@@Z; CBrushRenderingGraphBuilder::AddBrush(CBrush *,bool,CRenderingTechniqueFragment * *)
0x1800e7f2c  lea     rcx, [rbp+57h+var_B0]
0x1800e7f30  mov     edi, eax
0x1800e7f32  call    ??1?$out_param_t@V?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<CRenderingTechniqueFragment>>::~out_param_t<std::unique_ptr<CRenderingTechniqueFragment>>(void)
0x1800e7f37  test    edi, edi
0x1800e7f39  js      loc_1800E80DC
0x1800e7f3f  mov     r8, [rsp+120h+var_E0]
0x1800e7f44  lea     rcx, [rbx+20h]
0x1800e7f48  mov     [rsp+120h+var_E0], 0
0x1800e7f51  mov     rdx, [rcx+8]
0x1800e7f55  mov     [rbp+57h+var_78], r8
0x1800e7f59  cmp     rdx, [rcx+10h]
0x1800e7f5d  jz      short loc_1800E7F79
0x1800e7f5f  mov     rax, [rbp+57h+var_80]
0x1800e7f63  mov     [rbp+57h+var_78], 0
0x1800e7f6b  mov     [rdx], rax
0x1800e7f6e  mov     [rdx+8], r8
0x1800e7f72  add     qword ptr [rcx+8], 10h
0x1800e7f77  jmp     short loc_1800E7F82
0x1800e7f79  lea     r8, [rbp+57h+var_80]
0x1800e7f7d  call    ??$_Emplace_reallocate@UFragmentInput@CRenderingTechniqueFragment@@@?$vector@UFragmentInput@CRenderingTechniqueFragment@@V?$allocator@UFragmentInput@CRenderingTechniqueFragment@@@std@@@std@@AEAAPEAUFragmentInput@CRenderingTechniqueFragment@@QEAU23@$$QEAU23@@Z; std::vector<CRenderingTechniqueFragment::FragmentInput>::_Emplace_reallocate<CRenderingTechniqueFragment::FragmentInput>(CRenderingTechniqueFragment::FragmentInput * const,CRenderingTechniqueFragment::FragmentInput &&)
0x1800e7f82  lea     rcx, [rbp+57h+var_78]
0x1800e7f86  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e7f8b  lea     rcx, [rsp+120h+var_E0]
0x1800e7f90  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e7f95  jmp     short loc_1800E7FE5
0x1800e7f97  mov     rcx, [rbp+57h+var_68]
0x1800e7f9b  xorps   xmm0, xmm0
0x1800e7f9e  mov     edx, edi
0x1800e7fa0  mov     [rbp+57h+var_B0], r14
0x1800e7fa4  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800e7fa9  mov     rax, [rcx]
0x1800e7fac  mov     rax, [rax+30h]
0x1800e7fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7fb5  test    al, al
0x1800e7fb7  jnz     short loc_1800E7FCA
0x1800e7fb9  mov     [rbp+57h+var_A8], 0
0x1800e7fc1  mov     dword ptr [rbp+57h+var_A8+8], 0
0x1800e7fc8  jmp     short loc_1800E7FD5
0x1800e7fca  mov     rax, [rbp+57h+var_98]
0x1800e7fce  mov     [rbp+57h+var_A8], rax
0x1800e7fd2  mov     dword ptr [rbp+57h+var_A8+8], edi
0x1800e7fd5  mov     rcx, [rbp+57h+arg_0]; this
0x1800e7fd9  lea     r8, [rbp+57h+var_B0]; struct CBrushRenderingGraph::GraphInputParameters *
0x1800e7fdd  mov     rdx, rbx; struct CRenderingTechniqueFragment *
0x1800e7fe0  call    ?AddNamedInputToFragment@CBrushRenderingGraphBuilder@@IEAAXPEAVCRenderingTechniqueFragment@@AEBUGraphInputParameters@CBrushRenderingGraph@@@Z; CBrushRenderingGraphBuilder::AddNamedInputToFragment(CRenderingTechniqueFragment *,CBrushRenderingGraph::GraphInputParameters const &)
0x1800e7fe5  mov     r14, [rbp+57h+var_B8]
0x1800e7fe9  mov     eax, [rsp+120h+var_EC]
0x1800e7fed  inc     r15d
0x1800e7ff0  jmp     loc_1800E7DEB
0x1800e7ff5  mov     r15d, dword ptr [rsp+120h+var_E8]
0x1800e7ffa  cmp     esi, r15d
0x1800e7ffd  jz      loc_1800E80B8
0x1800e8003  mov     r15, [rbp+57h+arg_0]
0x1800e8007  mov     rdx, rbx; struct CRenderingTechniqueFragment *
0x1800e800a  mov     rcx, r15; this
0x1800e800d  call    ?CheckFragmentSize@CBrushRenderingGraphBuilder@@IEAAJPEAVCRenderingTechniqueFragment@@@Z; CBrushRenderingGraphBuilder::CheckFragmentSize(CRenderingTechniqueFragment *)
0x1800e8012  mov     edi, eax
0x1800e8014  test    eax, eax
0x1800e8016  js      loc_1800E811C
0x1800e801c  test    r13d, r13d
0x1800e801f  jnz     short loc_1800E807E
0x1800e8021  lea     r8, [rsp+120h+var_EC]
0x1800e8026  mov     [rsp+120h+var_EC], r13d
0x1800e802b  lea     rdx, [rsp+120h+var_D8]
0x1800e8030  mov     rcx, r15
0x1800e8033  call    ?CreateTechniqueForFragment@CBrushRenderingGraphBuilder@@IEAAJ$$QEAV?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@PEAI@Z; CBrushRenderingGraphBuilder::CreateTechniqueForFragment(std::unique_ptr<CRenderingTechniqueFragment> &&,uint *)
0x1800e8038  mov     edi, eax
0x1800e803a  test    eax, eax
0x1800e803c  js      loc_1800E8109
0x1800e8042  mov     rax, qword ptr [rbp+57h+var_D0]
0x1800e8046  mov     edx, [rsp+120h+var_EC]
0x1800e804a  mov     [rbp+57h+var_60], edx
0x1800e804d  mov     ecx, esi
0x1800e804f  shl     rcx, 4
0x1800e8053  mov     [rbp+57h+var_58], 0
0x1800e805b  mov     [rcx+rax], edx
0x1800e805e  add     rax, 8
0x1800e8062  add     rcx, rax
0x1800e8065  lea     rdx, [rbp+57h+var_58]
0x1800e8069  call    ??$?4U?$default_delete@VCRenderingTechniqueFragment@@@std@@$0A@@?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CRenderingTechniqueFragment>::operator=<std::default_delete<CRenderingTechniqueFragment>,0>(std::unique_ptr<CRenderingTechniqueFragment> &&)
0x1800e806e  lea     rcx, [rbp+57h+var_58]
0x1800e8072  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e8077  mov     rbx, [rsp+120h+var_D8]
0x1800e807c  jmp     short loc_1800E80B3
0x1800e807e  mov     rax, rbx
0x1800e8081  mov     ecx, esi
0x1800e8083  mov     [rbp+57h+var_48], rax
0x1800e8087  lea     rdx, [rbp+57h+var_48]
0x1800e808b  mov     rax, qword ptr [rbp+57h+var_D0]
0x1800e808f  or      edi, 0FFFFFFFFh
0x1800e8092  shl     rcx, 4
0x1800e8096  xor     ebx, ebx
0x1800e8098  mov     [rbp+57h+var_50], edi
0x1800e809b  mov     [rcx+rax], edi
0x1800e809e  add     rax, 8
0x1800e80a2  add     rcx, rax
0x1800e80a5  call    ??$?4U?$default_delete@VCRenderingTechniqueFragment@@@std@@$0A@@?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CRenderingTechniqueFragment>::operator=<std::default_delete<CRenderingTechniqueFragment>,0>(std::unique_ptr<CRenderingTechniqueFragment> &&)
0x1800e80aa  lea     rcx, [rbp+57h+var_48]
0x1800e80ae  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e80b3  mov     r15d, dword ptr [rsp+120h+var_E8]
0x1800e80b8  mov     eax, dword ptr [rsp+120h+var_E8+4]
0x1800e80bc  inc     esi
0x1800e80be  mov     r12b, [rbp+57h+arg_10]
0x1800e80c2  jmp     loc_1800E7D4A
0x1800e80c7  lea     r8, aOnecoreuapWind_74; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1800e80ce  mov     edx, 0FAh; void *
0x1800e80d3  mov     rcx, r9; this
0x1800e80d6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800e80dc  xor     edx, edx; int *
0x1800e80de  mov     [rsp+120h+var_F8], 0; void *
0x1800e80e7  mov     r9d, edi; int
0x1800e80ea  mov     [rsp+120h+var_100], 11Dh; unsigned int
0x1800e80f2  xor     r8d, r8d; unsigned int
0x1800e80f5  lea     ecx, [rdx+14h]; unsigned int
0x1800e80f8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800e80fd  lea     rcx, [rsp+120h+var_E0]
  ... truncated ...
```

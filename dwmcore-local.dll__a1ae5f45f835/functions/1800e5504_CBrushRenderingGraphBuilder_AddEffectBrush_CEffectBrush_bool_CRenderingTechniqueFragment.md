# CBrushRenderingGraphBuilder::AddEffectBrush(CEffectBrush *,bool,CRenderingTechniqueFragment * *)

- ea: `0x1800e5504`
- end: `0x1800e5a42`
- name: `?AddEffectBrush@CBrushRenderingGraphBuilder@@AEAAJPEAVCEffectBrush@@_NPEAPEAVCRenderingTechniqueFragment@@@Z`
- size: `1342`
- prototype: `__int64 __fastcall(CBrushRenderingGraphBuilder *__hidden this, struct CEffectBrush *, bool, struct CRenderingTechniqueFragment **)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1800e4cdc`

## callees

- `0x180050270`
- `0x1800516b0`
- `0x1800d32c0`
- `0x1800e2a88`
- `0x1800e3328`
- `0x1800e4834`
- `0x1800e4cdc`
- `0x1800e4e54`
- `0x1800e4ed4`
- `0x1800e4f30`
- `0x1800e5250`
- `0x1800e53ec`
- `0x1800e5424`
- `0x1800e5504`
- `0x1801af614`
- `0x1801c834c`
- `0x1801cabf0`
- `0x1801d3340`
- `0x1801ecc34`
- `0x180200488`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e556e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e556e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800e5564`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800e5564`

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
  int v16; // edi
  int v17; // r13d
  bool v18; // r12
  void *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdi
  struct CRenderingTechniqueFragment *v22; // rdx
  unsigned int v23; // eax
  unsigned int i; // r15d
  __int64 v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // edi
  unsigned int v28; // eax
  __int64 v29; // r8
  _QWORD *v30; // rdx
  struct CBrush *Input; // rax
  struct CBrush *v32; // r14
  bool v33; // r8
  int v34; // edi
  __int64 v35; // r8
  _QWORD *v36; // rdx
  int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  int v42; // r9d
  int v44; // [rsp+28h] [rbp-A9h]
  unsigned int v45; // [rsp+28h] [rbp-A9h]
  int v46; // [rsp+30h] [rbp-A1h]
  int v47; // [rsp+38h] [rbp-99h] BYREF
  int v48; // [rsp+3Ch] [rbp-95h] BYREF
  unsigned int v49; // [rsp+40h] [rbp-91h]
  unsigned int v50; // [rsp+44h] [rbp-8Dh]
  __int64 v51; // [rsp+48h] [rbp-89h] BYREF
  struct CRenderingTechniqueFragment *v52; // [rsp+50h] [rbp-81h] BYREF
  __int128 v53; // [rsp+58h] [rbp-79h] BYREF
  __int64 v54; // [rsp+68h] [rbp-69h]
  const struct Windows::UI::Composition::ICompiledEffect *v55; // [rsp+70h] [rbp-61h]
  struct CBrush *v56; // [rsp+78h] [rbp-59h] BYREF
  struct CRenderingTechniqueFragment *v57[2]; // [rsp+80h] [rbp-51h] BYREF
  struct CRenderingTechniqueFragment *v58; // [rsp+90h] [rbp-41h]
  __int64 v59; // [rsp+98h] [rbp-39h] BYREF
  __int64 v60; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v61; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-19h]
  __int64 v64; // [rsp+C0h] [rbp-11h]
  int v65; // [rsp+C8h] [rbp-9h]
  __int64 v66; // [rsp+D0h] [rbp-1h] BYREF
  int v67; // [rsp+D8h] [rbp+7h]
  _QWORD v68[9]; // [rsp+E0h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  v4 = (CCompiledEffectTemplate *)*((_QWORD *)a2 + 14);
  v5 = a3;
  v7 = 0;
  v8 = *(_QWORD *)(*((_QWORD *)v4 + 10) + 56LL);
  v64 = v8;
  CompiledEffectNoRef = CCompiledEffectTemplate::GetCompiledEffectNoRef(v4);
  v10 = *((_QWORD *)v4 + 10);
  v11 = CompiledEffectNoRef;
  v55 = CompiledEffectNoRef;
  v12 = *(struct _TP_WORK **)(v10 + 64);
  if ( v12 )
  {
    WaitForThreadpoolWorkCallbacks(v12, 0);
    CloseThreadpoolWork(*(PTP_WORK *)(v10 + 64));
    *(_QWORD *)(v10 + 64) = 0;
  }
  v63 = *(_QWORD *)(v10 + 80);
  v58 = (struct CRenderingTechniqueFragment *)*((_QWORD *)a2 + 20);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 32LL))(v8);
  v50 = v13;
  v53 = 0;
  v54 = 0;
  v14 = v13 - 1;
  v49 = v13 - 1;
  if ( v13 != 1 )
  {
    std::vector<CBrushRenderingGraphBuilder::SubgraphOutput>::_Resize_reallocate<std::_Value_init_tag>(&v53, v13 - 1);
    v13 = v50;
  }
  v15 = 0;
  while ( 2 )
  {
    if ( v15 >= v13 )
    {
      v34 = 0;
      v52 = 0;
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
        LOBYTE(v46) = v18;
        v44 = v16;
        v21 = CRenderingTechniqueFragment::CRenderingTechniqueFragment(v19, v58, v63, v15);
      }
      else
      {
        v21 = 0;
      }
      v22 = v7;
      v7 = (struct CRenderingTechniqueFragment *)v21;
      v52 = (struct CRenderingTechniqueFragment *)v21;
      if ( v22 )
        std::default_delete<CRenderingTechniqueFragment>::operator()(v20);
      if ( v21 )
      {
        v23 = (*(__int64 (__fastcall **)(const struct Windows::UI::Composition::ICompiledEffect *, _QWORD))(*(_QWORD *)v11 + 32LL))(
                v11,
                v15);
        v48 = v23;
        for ( i = 0; i < v23; ++i )
        {
          v25 = *(_QWORD *)v11;
          LOBYTE(v47) = 0;
          v26 = (*(__int64 (__fastcall **)(const struct Windows::UI::Composition::ICompiledEffect *, _QWORD, _QWORD, int *, int))(v25 + 48))(
                  v11,
                  v15,
                  i,
                  &v47,
                  v44);
          v27 = v26;
          if ( (_BYTE)v47 )
          {
            if ( v26 >= (unsigned __int64)((__int64)(*((_QWORD *)&v53 + 1) - v53) >> 4) )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xFA,
                (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\brushrenderinggraphbuilder.cpp",
                (const char *)retaddr);
            v28 = *(_DWORD *)(v53 + 16LL * v26);
            if ( v28 == -1 )
            {
              v29 = *(_QWORD *)(v53 + 16LL * v27 + 8);
              *(_QWORD *)(v53 + 16LL * v27 + 8) = 0;
              v30 = (_QWORD *)*((_QWORD *)v7 + 5);
              v60 = v29;
              if ( v30 == *((_QWORD **)v7 + 6) )
              {
                std::vector<CRenderingTechniqueFragment::FragmentInput>::_Emplace_reallocate<CRenderingTechniqueFragment::FragmentInput>(
                  (char *)v7 + 32,
                  v30,
                  &v59);
              }
              else
              {
                v60 = 0;
                *v30 = v59;
                v30[1] = v29;
                *((_QWORD *)v7 + 5) += 16LL;
              }
              std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v60);
            }
            else
            {
              CRenderingTechniqueFragment::AddIntermediateInput(v7, v28);
            }
          }
          else
          {
            Input = CEffectBrush::GetInput(a2, v26);
            v32 = Input;
            if ( Input && *((_BYTE *)Input + 96) )
            {
              v33 = v18
                 || (*(unsigned __int8 (__fastcall **)(const struct Windows::UI::Composition::ICompiledEffect *, _QWORD, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)v55 + 56LL))(
                      v55,
                      v15,
                      i,
                      0,
                      0,
                      v46);
              v56 = (struct CBrush *)&v51;
              v51 = 0;
              v57[0] = 0;
              LOBYTE(v57[1]) = 1;
              v34 = CBrushRenderingGraphBuilder::AddBrush(this, v32, v33, v57);
              wil::details::out_param_t<std::unique_ptr<CRenderingTechniqueFragment>>::~out_param_t<std::unique_ptr<CRenderingTechniqueFragment>>(&v56);
              if ( v34 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v34, 0x11Du, 0);
                std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v51);
                goto LABEL_61;
              }
              v35 = v51;
              v51 = 0;
              v36 = (_QWORD *)*((_QWORD *)v7 + 5);
              v62 = v35;
              if ( v36 == *((_QWORD **)v7 + 6) )
              {
                std::vector<CRenderingTechniqueFragment::FragmentInput>::_Emplace_reallocate<CRenderingTechniqueFragment::FragmentInput>(
                  (char *)v7 + 32,
                  v36,
                  &v61);
              }
              else
              {
                v62 = 0;
                *v36 = v61;
                v36[1] = v35;
                *((_QWORD *)v7 + 5) += 16LL;
              }
              std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v62);
              std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v51);
            }
            else
            {
              v56 = Input;
              *(_OWORD *)v57 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v64 + 48LL))(v64, v27) )
              {
                v57[0] = v58;
                LODWORD(v57[1]) = v27;
              }
              else
              {
                v57[0] = 0;
                LODWORD(v57[1]) = 0;
              }
              CBrushRenderingGraphBuilder::AddNamedInputToFragment(
                this,
                v7,
                (const struct CBrushRenderingGraph::GraphInputParameters *)&v56);
            }
            v11 = v55;
          }
          v23 = v48;
        }
        v14 = v49;
        if ( v15 == v49 )
        {
LABEL_52:
          v13 = v50;
          ++v15;
          v5 = a3;
          continue;
        }
        v37 = CBrushRenderingGraphBuilder::CheckFragmentSize(this, v7);
        v34 = v37;
        if ( v37 < 0 )
        {
          v45 = 315;
        }
        else
        {
          if ( v17 )
          {
            v68[0] = v7;
            v40 = v53;
            v41 = 16LL * v15;
            v7 = 0;
            v67 = -1;
            *(_DWORD *)(v41 + v53) = -1;
            std::unique_ptr<CRenderingTechniqueFragment>::operator=<std::default_delete<CRenderingTechniqueFragment>,0>(
              v40 + 8 + v41,
              v68);
            std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(v68);
            goto LABEL_51;
          }
          v48 = 0;
          v37 = CBrushRenderingGraphBuilder::CreateTechniqueForFragment(this, &v52, &v48);
          v34 = v37;
          if ( v37 >= 0 )
          {
            v38 = v53;
            v65 = v48;
            v39 = 16LL * v15;
            v66 = 0;
            *(_DWORD *)(v39 + v53) = v48;
            std::unique_ptr<CRenderingTechniqueFragment>::operator=<std::default_delete<CRenderingTechniqueFragment>,0>(
              v38 + 8 + v39,
              &v66);
            std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v66);
            v7 = v52;
LABEL_51:
            v14 = v49;
            goto LABEL_52;
          }
          v45 = 320;
        }
        v42 = v37;
      }
      else
      {
        v34 = -2147024882;
        v42 = -2147024882;
        v45 = 234;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v42, v45, 0);
    }
    break;
  }
LABEL_61:
  if ( (_QWORD)v53 )
  {
    std::_Destroy_range<std::allocator<CBrushRenderingGraphBuilder::SubgraphOutput>>(v53, *((_QWORD *)&v53 + 1));
    std::_Deallocate<16>(v53, (v54 - v53) & 0xFFFFFFFFFFFFFFF0uLL);
    v54 = 0;
    v53 = 0;
  }
  std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(&v52);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x1800e5504  mov     rax, rsp
0x1800e5507  mov     [rax+20h], r9
0x1800e550b  mov     [rax+18h], r8b
0x1800e550f  mov     [rax+10h], rdx
0x1800e5513  mov     [rax+8], rcx
0x1800e5517  push    rbp
0x1800e5518  push    rbx
0x1800e5519  push    rsi
0x1800e551a  push    rdi
0x1800e551b  push    r12
0x1800e551d  push    r13
0x1800e551f  push    r14
0x1800e5521  push    r15
0x1800e5523  lea     rbp, [rax-5Fh]
0x1800e5527  sub     rsp, 0E8h
0x1800e552e  mov     rdi, [rdx+70h]
0x1800e5532  mov     r12b, r8b
0x1800e5535  mov     rcx, rdi; this
0x1800e5538  mov     rsi, rdx
0x1800e553b  xor     ebx, ebx
0x1800e553d  mov     rax, [rdi+50h]
0x1800e5541  mov     r15, [rax+38h]
0x1800e5545  mov     [rbp+57h+var_68], r15
0x1800e5549  call    ?GetCompiledEffectNoRef@CCompiledEffectTemplate@@QEBAPEBUICompiledEffect@Composition@UI@Windows@@XZ; CCompiledEffectTemplate::GetCompiledEffectNoRef(void)
0x1800e554e  mov     rdi, [rdi+50h]
0x1800e5552  mov     r14, rax
0x1800e5555  mov     [rbp+57h+var_B8], rax
0x1800e5559  mov     rcx, [rdi+40h]; pwk
0x1800e555d  test    rcx, rcx
0x1800e5560  jz      short loc_1800E5578
0x1800e5562  xor     edx, edx; fCancelPendingCallbacks
0x1800e5564  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800e556a  mov     rcx, [rdi+40h]; pwk
0x1800e556e  call    cs:__imp_CloseThreadpoolWork
0x1800e5574  mov     [rdi+40h], rbx
0x1800e5578  mov     rax, [rdi+50h]
0x1800e557c  mov     rcx, r15
0x1800e557f  mov     [rbp+57h+var_70], rax
0x1800e5583  mov     rax, [rsi+0A0h]
0x1800e558a  mov     [rbp+57h+var_98], rax
0x1800e558e  mov     rax, [r15]
0x1800e5591  mov     rax, [rax+20h]
0x1800e5595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e559a  xorps   xmm0, xmm0
0x1800e559d  mov     dword ptr [rsp+120h+var_E8+4], eax
0x1800e55a1  movdqu  [rbp+57h+var_D0], xmm0
0x1800e55a6  mov     [rbp+57h+var_C0], rbx
0x1800e55aa  lea     r15d, [rax-1]
0x1800e55ae  mov     dword ptr [rsp+120h+var_E8], r15d
0x1800e55b3  mov     edx, r15d
0x1800e55b6  test    r15d, r15d
0x1800e55b9  jz      short loc_1800E55C8
0x1800e55bb  lea     rcx, [rbp+57h+var_D0]
0x1800e55bf  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@USubgraphOutput@CBrushRenderingGraphBuilder@@V?$allocator@USubgraphOutput@CBrushRenderingGraphBuilder@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<CBrushRenderingGraphBuilder::SubgraphOutput>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800e55c4  mov     eax, dword ptr [rsp+120h+var_E8+4]
0x1800e55c8  xor     esi, esi
0x1800e55ca  cmp     esi, eax
0x1800e55cc  jnb     loc_1800E59DA
0x1800e55d2  mov     rax, [r14]
0x1800e55d5  mov     edx, esi
0x1800e55d7  mov     rcx, r14
0x1800e55da  mov     rax, [rax+28h]
0x1800e55de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e55e3  mov     r13d, eax
0x1800e55e6  mov     edi, eax
0x1800e55e8  and     r13d, 8
0x1800e55ec  test    r12b, r12b
0x1800e55ef  jz      short loc_1800E5600
0x1800e55f1  cmp     esi, r15d
0x1800e55f4  jz      short loc_1800E55FB
0x1800e55f6  test    r13d, r13d
0x1800e55f9  jz      short loc_1800E5600
0x1800e55fb  mov     r12b, 1
0x1800e55fe  jmp     short loc_1800E5603
0x1800e5600  xor     r12b, r12b
0x1800e5603  mov     ecx, 78h ; 'x'; size
0x1800e5608  call    MIDL_user_allocate
0x1800e560d  test    rax, rax
0x1800e5610  jz      short loc_1800E5633
0x1800e5612  mov     r8, [rbp+57h+var_70]
0x1800e5616  mov     r9d, esi
0x1800e5619  mov     rdx, [rbp+57h+var_98]
0x1800e561d  mov     rcx, rax
0x1800e5620  mov     byte ptr [rsp+120h+var_F8], r12b
0x1800e5625  mov     [rsp+120h+var_100], edi
0x1800e5629  call    ??0CRenderingTechniqueFragment@@QEAA@PEAUIEffectInstance@Composition@UI@Windows@@PEAVCShaderCache@@IW4Enum@CompiledEffectSubgraphFlags@234@_N@Z; CRenderingTechniqueFragment::CRenderingTechniqueFragment(Windows::UI::Composition::IEffectInstance *,CShaderCache *,uint,Windows::UI::Composition::CompiledEffectSubgraphFlags::Enum,bool)
0x1800e562e  mov     rdi, rax
0x1800e5631  jmp     short loc_1800E5635
0x1800e5633  xor     edi, edi
0x1800e5635  mov     rdx, rbx
0x1800e5638  mov     rbx, rdi
0x1800e563b  mov     [rsp+120h+var_D8], rbx
0x1800e5640  test    rdx, rdx
0x1800e5643  jz      short loc_1800E564A
0x1800e5645  call    ??R?$default_delete@VCRenderingTechniqueFragment@@@std@@QEBAXPEAVCRenderingTechniqueFragment@@@Z; std::default_delete<CRenderingTechniqueFragment>::operator()(CRenderingTechniqueFragment *)
0x1800e564a  test    rdi, rdi
0x1800e564d  jz      loc_1800E59B2
0x1800e5653  mov     rax, [r14]
0x1800e5656  mov     edx, esi
0x1800e5658  mov     rcx, r14
0x1800e565b  mov     rax, [rax+20h]
0x1800e565f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5664  mov     [rsp+120h+var_EC], eax
0x1800e5668  xor     r15d, r15d
0x1800e566b  cmp     r15d, eax
0x1800e566e  jnb     loc_1800E5875
0x1800e5674  mov     rcx, [r14]
0x1800e5677  lea     r9, [rsp+120h+var_F0]
0x1800e567c  mov     r8d, r15d
0x1800e567f  mov     byte ptr [rsp+120h+var_F0], 0
0x1800e5684  mov     edx, esi
0x1800e5686  mov     rax, [rcx+30h]
0x1800e568a  mov     rcx, r14
0x1800e568d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5692  cmp     byte ptr [rsp+120h+var_F0], 0
0x1800e5697  mov     edi, eax
0x1800e5699  jz      loc_1800E5728
0x1800e569f  mov     rax, qword ptr [rbp+57h+var_D0+8]
0x1800e56a3  mov     ecx, edi
0x1800e56a5  mov     rdx, qword ptr [rbp+57h+var_D0]
0x1800e56a9  mov     r9, [rbp+5Fh]; char *
0x1800e56ad  sub     rax, rdx
0x1800e56b0  sar     rax, 4
0x1800e56b4  cmp     rdi, rax
0x1800e56b7  jnb     loc_1800E5947
0x1800e56bd  add     rcx, rcx
0x1800e56c0  mov     eax, [rdx+rcx*8]
0x1800e56c3  cmp     eax, 0FFFFFFFFh
0x1800e56c6  jnz     short loc_1800E5719
0x1800e56c8  mov     r8, [rdx+rcx*8+8]
0x1800e56cd  mov     qword ptr [rdx+rcx*8+8], 0
0x1800e56d6  mov     rdx, [rbx+28h]
0x1800e56da  mov     [rbp+57h+var_88], r8
0x1800e56de  cmp     rdx, [rbx+30h]
0x1800e56e2  jz      short loc_1800E56FE
0x1800e56e4  mov     rax, [rbp+57h+var_90]
0x1800e56e8  mov     [rbp+57h+var_88], 0
0x1800e56f0  mov     [rdx], rax
0x1800e56f3  mov     [rdx+8], r8
0x1800e56f7  add     qword ptr [rbx+28h], 10h
0x1800e56fc  jmp     short loc_1800E570B
0x1800e56fe  lea     r8, [rbp+57h+var_90]
0x1800e5702  lea     rcx, [rbx+20h]
0x1800e5706  call    ??$_Emplace_reallocate@UFragmentInput@CRenderingTechniqueFragment@@@?$vector@UFragmentInput@CRenderingTechniqueFragment@@V?$allocator@UFragmentInput@CRenderingTechniqueFragment@@@std@@@std@@AEAAPEAUFragmentInput@CRenderingTechniqueFragment@@QEAU23@$$QEAU23@@Z; std::vector<CRenderingTechniqueFragment::FragmentInput>::_Emplace_reallocate<CRenderingTechniqueFragment::FragmentInput>(CRenderingTechniqueFragment::FragmentInput * const,CRenderingTechniqueFragment::FragmentInput &&)
0x1800e570b  lea     rcx, [rbp+57h+var_88]
0x1800e570f  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e5714  jmp     loc_1800E5869
0x1800e5719  mov     edx, eax; unsigned int
0x1800e571b  mov     rcx, rbx; this
0x1800e571e  call    ?AddIntermediateInput@CRenderingTechniqueFragment@@QEAAXI@Z; CRenderingTechniqueFragment::AddIntermediateInput(uint)
0x1800e5723  jmp     loc_1800E5869
0x1800e5728  mov     rcx, [rbp+57h+arg_8]; this
0x1800e572c  mov     edx, edi; unsigned int
0x1800e572e  call    ?GetInput@CEffectBrush@@QEBAPEAVCBrush@@I@Z; CEffectBrush::GetInput(uint)
0x1800e5733  mov     r14, rax
0x1800e5736  test    rax, rax
0x1800e5739  jz      loc_1800E5817
0x1800e573f  cmp     byte ptr [rax+60h], 0
0x1800e5743  jz      loc_1800E5817
0x1800e5749  test    r12b, r12b
0x1800e574c  jnz     short loc_1800E577B
0x1800e574e  mov     r10, [rbp+57h+var_B8]
0x1800e5752  xor     r9d, r9d
0x1800e5755  mov     r8d, r15d
0x1800e5758  mov     qword ptr [rsp+120h+var_100], 0
0x1800e5761  mov     edx, esi
0x1800e5763  mov     rcx, [r10]
0x1800e5766  mov     rax, [rcx+38h]
0x1800e576a  mov     rcx, r10
0x1800e576d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5772  test    al, al
0x1800e5774  jnz     short loc_1800E577B
0x1800e5776  xor     r8b, r8b
0x1800e5779  jmp     short loc_1800E577E
0x1800e577b  mov     r8b, 1; bool
0x1800e577e  mov     rcx, [rbp+57h+arg_0]; this
0x1800e5782  lea     rax, [rsp+120h+var_E0]
0x1800e5787  lea     r9, [rbp+57h+var_A8]; struct CRenderingTechniqueFragment **
0x1800e578b  mov     [rbp+57h+var_B0], rax
0x1800e578f  mov     rdx, r14; struct CBrush *
0x1800e5792  mov     [rsp+120h+var_E0], 0
0x1800e579b  mov     [rbp+57h+var_A8], 0
0x1800e57a3  mov     byte ptr [rbp+57h+var_A8+8], 1
0x1800e57a7  call    ?AddBrush@CBrushRenderingGraphBuilder@@AEAAJPEAVCBrush@@_NPEAPEAVCRenderingTechniqueFragment@@@Z; CBrushRenderingGraphBuilder::AddBrush(CBrush *,bool,CRenderingTechniqueFragment * *)
0x1800e57ac  lea     rcx, [rbp+57h+var_B0]
0x1800e57b0  mov     edi, eax
0x1800e57b2  call    ??1?$out_param_t@V?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<CRenderingTechniqueFragment>>::~out_param_t<std::unique_ptr<CRenderingTechniqueFragment>>(void)
0x1800e57b7  test    edi, edi
0x1800e57b9  js      loc_1800E595C
0x1800e57bf  mov     r8, [rsp+120h+var_E0]
0x1800e57c4  lea     rcx, [rbx+20h]
0x1800e57c8  mov     [rsp+120h+var_E0], 0
0x1800e57d1  mov     rdx, [rcx+8]
0x1800e57d5  mov     [rbp+57h+var_78], r8
0x1800e57d9  cmp     rdx, [rcx+10h]
0x1800e57dd  jz      short loc_1800E57F9
0x1800e57df  mov     rax, [rbp+57h+var_80]
0x1800e57e3  mov     [rbp+57h+var_78], 0
0x1800e57eb  mov     [rdx], rax
0x1800e57ee  mov     [rdx+8], r8
0x1800e57f2  add     qword ptr [rcx+8], 10h
0x1800e57f7  jmp     short loc_1800E5802
0x1800e57f9  lea     r8, [rbp+57h+var_80]
0x1800e57fd  call    ??$_Emplace_reallocate@UFragmentInput@CRenderingTechniqueFragment@@@?$vector@UFragmentInput@CRenderingTechniqueFragment@@V?$allocator@UFragmentInput@CRenderingTechniqueFragment@@@std@@@std@@AEAAPEAUFragmentInput@CRenderingTechniqueFragment@@QEAU23@$$QEAU23@@Z; std::vector<CRenderingTechniqueFragment::FragmentInput>::_Emplace_reallocate<CRenderingTechniqueFragment::FragmentInput>(CRenderingTechniqueFragment::FragmentInput * const,CRenderingTechniqueFragment::FragmentInput &&)
0x1800e5802  lea     rcx, [rbp+57h+var_78]
0x1800e5806  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e580b  lea     rcx, [rsp+120h+var_E0]
0x1800e5810  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e5815  jmp     short loc_1800E5865
0x1800e5817  mov     rcx, [rbp+57h+var_68]
0x1800e581b  xorps   xmm0, xmm0
0x1800e581e  mov     edx, edi
0x1800e5820  mov     [rbp+57h+var_B0], r14
0x1800e5824  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800e5829  mov     rax, [rcx]
0x1800e582c  mov     rax, [rax+30h]
0x1800e5830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5835  test    al, al
0x1800e5837  jnz     short loc_1800E584A
0x1800e5839  mov     [rbp+57h+var_A8], 0
0x1800e5841  mov     dword ptr [rbp+57h+var_A8+8], 0
0x1800e5848  jmp     short loc_1800E5855
0x1800e584a  mov     rax, [rbp+57h+var_98]
0x1800e584e  mov     [rbp+57h+var_A8], rax
0x1800e5852  mov     dword ptr [rbp+57h+var_A8+8], edi
0x1800e5855  mov     rcx, [rbp+57h+arg_0]; this
0x1800e5859  lea     r8, [rbp+57h+var_B0]; struct CBrushRenderingGraph::GraphInputParameters *
0x1800e585d  mov     rdx, rbx; struct CRenderingTechniqueFragment *
0x1800e5860  call    ?AddNamedInputToFragment@CBrushRenderingGraphBuilder@@IEAAXPEAVCRenderingTechniqueFragment@@AEBUGraphInputParameters@CBrushRenderingGraph@@@Z; CBrushRenderingGraphBuilder::AddNamedInputToFragment(CRenderingTechniqueFragment *,CBrushRenderingGraph::GraphInputParameters const &)
0x1800e5865  mov     r14, [rbp+57h+var_B8]
0x1800e5869  mov     eax, [rsp+120h+var_EC]
0x1800e586d  inc     r15d
0x1800e5870  jmp     loc_1800E566B
0x1800e5875  mov     r15d, dword ptr [rsp+120h+var_E8]
0x1800e587a  cmp     esi, r15d
0x1800e587d  jz      loc_1800E5938
0x1800e5883  mov     r15, [rbp+57h+arg_0]
0x1800e5887  mov     rdx, rbx; struct CRenderingTechniqueFragment *
0x1800e588a  mov     rcx, r15; this
0x1800e588d  call    ?CheckFragmentSize@CBrushRenderingGraphBuilder@@IEAAJPEAVCRenderingTechniqueFragment@@@Z; CBrushRenderingGraphBuilder::CheckFragmentSize(CRenderingTechniqueFragment *)
0x1800e5892  mov     edi, eax
0x1800e5894  test    eax, eax
0x1800e5896  js      loc_1800E599C
0x1800e589c  test    r13d, r13d
0x1800e589f  jnz     short loc_1800E58FE
0x1800e58a1  lea     r8, [rsp+120h+var_EC]
0x1800e58a6  mov     [rsp+120h+var_EC], r13d
0x1800e58ab  lea     rdx, [rsp+120h+var_D8]
0x1800e58b0  mov     rcx, r15
0x1800e58b3  call    ?CreateTechniqueForFragment@CBrushRenderingGraphBuilder@@IEAAJ$$QEAV?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@PEAI@Z; CBrushRenderingGraphBuilder::CreateTechniqueForFragment(std::unique_ptr<CRenderingTechniqueFragment> &&,uint *)
0x1800e58b8  mov     edi, eax
0x1800e58ba  test    eax, eax
0x1800e58bc  js      loc_1800E5989
0x1800e58c2  mov     rax, qword ptr [rbp+57h+var_D0]
0x1800e58c6  mov     edx, [rsp+120h+var_EC]
0x1800e58ca  mov     [rbp+57h+var_60], edx
0x1800e58cd  mov     ecx, esi
0x1800e58cf  shl     rcx, 4
0x1800e58d3  mov     [rbp+57h+var_58], 0
0x1800e58db  mov     [rcx+rax], edx
0x1800e58de  add     rax, 8
0x1800e58e2  add     rcx, rax
0x1800e58e5  lea     rdx, [rbp+57h+var_58]
0x1800e58e9  call    ??$?4U?$default_delete@VCRenderingTechniqueFragment@@@std@@$0A@@?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CRenderingTechniqueFragment>::operator=<std::default_delete<CRenderingTechniqueFragment>,0>(std::unique_ptr<CRenderingTechniqueFragment> &&)
0x1800e58ee  lea     rcx, [rbp+57h+var_58]
0x1800e58f2  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e58f7  mov     rbx, [rsp+120h+var_D8]
0x1800e58fc  jmp     short loc_1800E5933
0x1800e58fe  mov     rax, rbx
0x1800e5901  mov     ecx, esi
0x1800e5903  mov     [rbp+57h+var_48], rax
0x1800e5907  lea     rdx, [rbp+57h+var_48]
0x1800e590b  mov     rax, qword ptr [rbp+57h+var_D0]
0x1800e590f  or      edi, 0FFFFFFFFh
0x1800e5912  shl     rcx, 4
0x1800e5916  xor     ebx, ebx
0x1800e5918  mov     [rbp+57h+var_50], edi
0x1800e591b  mov     [rcx+rax], edi
0x1800e591e  add     rax, 8
0x1800e5922  add     rcx, rax
0x1800e5925  call    ??$?4U?$default_delete@VCRenderingTechniqueFragment@@@std@@$0A@@?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CRenderingTechniqueFragment>::operator=<std::default_delete<CRenderingTechniqueFragment>,0>(std::unique_ptr<CRenderingTechniqueFragment> &&)
0x1800e592a  lea     rcx, [rbp+57h+var_48]
0x1800e592e  call    ??1?$unique_ptr@VCRenderingTechniqueFragment@@U?$default_delete@VCRenderingTechniqueFragment@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRenderingTechniqueFragment>::~unique_ptr<CRenderingTechniqueFragment>(void)
0x1800e5933  mov     r15d, dword ptr [rsp+120h+var_E8]
0x1800e5938  mov     eax, dword ptr [rsp+120h+var_E8+4]
0x1800e593c  inc     esi
0x1800e593e  mov     r12b, [rbp+57h+arg_10]
0x1800e5942  jmp     loc_1800E55CA
0x1800e5947  lea     r8, aOnecoreuapWind_74; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1800e594e  mov     edx, 0FAh; void *
0x1800e5953  mov     rcx, r9; this
0x1800e5956  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800e595c  xor     edx, edx; int *
0x1800e595e  mov     [rsp+120h+var_F8], 0; void *
0x1800e5967  mov     r9d, edi; int
0x1800e596a  mov     [rsp+120h+var_100], 11Dh; unsigned int
0x1800e5972  xor     r8d, r8d; unsigned int
0x1800e5975  lea     ecx, [rdx+14h]; unsigned int
0x1800e5978  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800e597d  lea     rcx, [rsp+120h+var_E0]
  ... truncated ...
```

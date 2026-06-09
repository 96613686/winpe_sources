# CExpression::ResolveReference(ExpressionReferenceInfo const &,CExpressionValue *)

- ea: `0x180053750`
- end: `0x180053a1b`
- name: `?ResolveReference@CExpression@@AEBAJAEBUExpressionReferenceInfo@@PEAVCExpressionValue@@@Z`
- size: `715`
- prototype: `int(CExpression *__hidden this, const struct ExpressionReferenceInfo *, struct CExpressionValue *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801f95f0`

## callees

- `0x18004fce4`
- `0x180050270`
- `0x180052264`
- `0x1800533a0`
- `0x180053440`
- `0x180053750`
- `0x180053c90`
- `0x18014d268`
- `0x1801635a0`
- `0x18016e080`
- `0x180200488`
- `0x180204120`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800537c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005384a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800537c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005384a`

## pseudocode

```c
__int64 __fastcall CExpression::ResolveReference(
        CExpression *this,
        const struct ExpressionReferenceInfo *a2,
        struct CExpressionValue *a3,
        const char *a4)
{
  __int64 v4; // rbx
  __int64 v8; // r12
  unsigned int v9; // eax
  __int64 v10; // rbp
  struct CResource *v11; // r15
  int v12; // ebp
  int v13; // r12d
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rbx
  struct CResource *v18; // rdx
  __int64 v20; // rdx
  float v21; // xmm6_4
  __int64 Elapsed; // rax
  unsigned int v23; // [rsp+20h] [rbp-48h]
  unsigned int v24; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v26; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  v26 = 0;
  if ( *((_DWORD *)this + 55) || CCommonRegistryData::LogExpressionPerfStats )
  {
    v8 = *(_QWORD *)(*((_QWORD *)this + 3) + 816LL) + 128LL;
    QpcStopwatch::Start((QpcStopwatch *)&v26);
    v4 = v26;
  }
  else
  {
    v8 = 0;
  }
  v9 = *((_DWORD *)a2 + 4);
  if ( v9 >= *((_DWORD *)this + 80) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x571,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\expression.cpp",
      a4);
  v10 = *(_QWORD *)(*((_QWORD *)this + 37) + 8LL * v9);
  if ( !v10 )
    goto LABEL_21;
  if ( !g_pComposition
    || GetCurrentThreadId() != CComposition::s_compositionThreadId
    && !CTreeLock::IsLockedByCurrentThread((CComposition *)((char *)g_pComposition + 5696)) )
  {
    ModuleFailFastForHRESULT(-2003304313, retaddr);
  }
  v11 = *(struct CResource **)(v10 + 64);
  if ( v11 )
  {
    if ( v4 )
    {
      Elapsed = QpcStopwatch::GetElapsed((QpcStopwatch *)&v26);
      CExpressionPerformanceCounter::AddDurationSample(v8, 3, Elapsed);
    }
    v12 = *(_DWORD *)a2;
    v13 = *((_DWORD *)a2 + 3);
    v14 = *(unsigned int *)a2;
    LODWORD(v14) = v14 & 0x7FFFFFFF;
    v15 = (*(__int64 (__fastcall **)(struct CResource *, __int64, struct CExpressionValue *))(*(_QWORD *)v11 + 136LL))(
            v11,
            v14,
            a3);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AC,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\resource.cpp",
        (const char *)(unsigned int)v15,
        v23);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B0,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\baseexpression.cpp",
        (const char *)v16,
        v24);
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D41E8, 2u, v16, 0x589u, 0);
    }
    else
    {
      if ( v12 < 0 && *((_DWORD *)a3 + 16) == 18 )
      {
        v21 = *(float *)a3;
        CExpressionValue::DestroyCurrent(a3);
        *((_DWORD *)a3 + 16) = 18;
        *(float *)a3 = v21 * 57.295776;
      }
      if ( v13 == 1 )
      {
        v20 = *((_QWORD *)this + 24);
        if ( v20 )
        {
          if ( *(_BYTE *)(v20 + 4) )
            CExpressionValue::ApplyMaskToValue(a3, (const struct SubchannelMaskInfo *)v20);
        }
      }
      v17 = *((_QWORD *)this + 23);
      if ( v17 )
      {
        if ( !g_pComposition
          || GetCurrentThreadId() != CComposition::s_compositionThreadId
          && !CTreeLock::IsLockedByCurrentThread((CComposition *)((char *)g_pComposition + 5696)) )
        {
          ModuleFailFastForHRESULT(-2003304313, retaddr);
        }
        v18 = *(struct CResource **)(v17 + 64);
      }
      else
      {
        v18 = 0;
      }
      CInteractionTrackerBase::CheckTargetsForInteractionSource(a2, v18, v11);
      return 0;
    }
  }
  else
  {
LABEL_21:
    v16 = -2147467259;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D41E8, 2u, -2147467259, 0x57Cu, 0);
  }
  return v16;
}

```

## disassembly

```asm
0x180053750  push    rbx
0x180053752  push    rsi
0x180053753  push    rdi
0x180053754  push    r12
0x180053756  push    r14
0x180053758  sub     rsp, 40h
0x18005375c  xor     ebx, ebx
0x18005375e  mov     r14, r8
0x180053761  mov     rsi, rdx
0x180053764  mov     rdi, rcx
0x180053767  mov     [rsp+68h+arg_0], rbx
0x18005376c  cmp     [rcx+0DCh], ebx
0x180053772  jnz     loc_180053910
0x180053778  cmp     cs:?LogExpressionPerfStats@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B, bl; details::CRegistryKey<bool,bool> const CCommonRegistryData::LogExpressionPerfStats
0x18005377e  jnz     loc_180053910
0x180053784  xor     r12d, r12d
0x180053787  mov     eax, [rsi+10h]
0x18005378a  cmp     eax, [rdi+140h]
0x180053790  jnb     loc_180053933
0x180053796  mov     ecx, eax
0x180053798  mov     [rsp+68h+arg_8], rbp
0x18005379d  mov     rax, [rdi+128h]
0x1800537a4  mov     [rsp+68h+arg_10], r15
0x1800537ac  mov     rbp, [rax+rcx*8]
0x1800537b0  test    rbp, rbp
0x1800537b3  jz      loc_18005389A
0x1800537b9  cmp     cs:?g_pComposition@@3PEAVCComposition@@EA, 0; CComposition * g_pComposition
0x1800537c1  jz      loc_18005388A
0x1800537c7  call    cs:__imp_GetCurrentThreadId
0x1800537cd  cmp     eax, cs:?s_compositionThreadId@CComposition@@0KA; ulong CComposition::s_compositionThreadId
0x1800537d3  jnz     loc_18005386F
0x1800537d9  mov     r15, [rbp+40h]
0x1800537dd  test    r15, r15
0x1800537e0  jz      loc_18005389A
0x1800537e6  test    rbx, rbx
0x1800537e9  jnz     loc_1800539FC
0x1800537ef  mov     rax, [r15]
0x1800537f2  mov     r8, r14
0x1800537f5  mov     ebp, [rsi]
0x1800537f7  mov     rcx, r15
0x1800537fa  mov     r12d, [rsi+0Ch]
0x1800537fe  mov     edx, ebp
0x180053800  btr     edx, 1Fh
0x180053804  mov     rax, [rax+88h]
0x18005380b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053810  mov     ebx, eax
0x180053812  test    eax, eax
0x180053814  js      loc_18005394A
0x18005381a  test    ebp, ebp
0x18005381c  js      loc_1800539B9
0x180053822  cmp     r12d, 1
0x180053826  jz      loc_180053992
0x18005382c  mov     rbx, [rdi+0B8h]
0x180053833  test    rbx, rbx
0x180053836  jz      loc_1800539F5
0x18005383c  cmp     cs:?g_pComposition@@3PEAVCComposition@@EA, 0; CComposition * g_pComposition
0x180053844  jz      loc_180053900
0x18005384a  call    cs:__imp_GetCurrentThreadId
0x180053850  cmp     eax, cs:?s_compositionThreadId@CComposition@@0KA; ulong CComposition::s_compositionThreadId
0x180053856  jnz     loc_1800538E5
0x18005385c  mov     rdx, [rbx+40h]; struct CResource *
0x180053860  mov     r8, r15; struct CResource *
0x180053863  mov     rcx, rsi; struct ExpressionReferenceInfo *
0x180053866  call    ?CheckTargetsForInteractionSource@CInteractionTrackerBase@@SAXPEBUExpressionReferenceInfo@@PEAVCResource@@1@Z; CInteractionTrackerBase::CheckTargetsForInteractionSource(ExpressionReferenceInfo const *,CResource *,CResource *)
0x18005386b  xor     ebx, ebx
0x18005386d  jmp     short loc_1800538CA
0x18005386f  mov     rcx, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180053876  add     rcx, 1640h; this
0x18005387d  call    ?IsLockedByCurrentThread@CTreeLock@@QEBA_NXZ; CTreeLock::IsLockedByCurrentThread(void)
0x180053882  test    al, al
0x180053884  jnz     loc_1800537D9
0x18005388a  mov     rdx, [rsp+68h]; void *
0x18005388f  mov     ecx, 88980087h; int
0x180053894  call    ModuleFailFastForHRESULT
0x18005389a  mov     [rsp+68h+var_40], 0; void *
0x1800538a3  mov     ebx, 80004005h
0x1800538a8  mov     [rsp+68h+var_48], 57Ch; unsigned int
0x1800538b0  mov     r9d, ebx; int
0x1800538b3  lea     rdx, qword_1802D41E8; int *
0x1800538ba  mov     r8d, 2; unsigned int
0x1800538c0  mov     ecx, 14h; unsigned int
0x1800538c5  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800538ca  mov     rbp, [rsp+68h+arg_8]
0x1800538cf  mov     eax, ebx
0x1800538d1  mov     r15, [rsp+68h+arg_10]
0x1800538d9  add     rsp, 40h
0x1800538dd  pop     r14
0x1800538df  pop     r12
0x1800538e1  pop     rdi
0x1800538e2  pop     rsi
0x1800538e3  pop     rbx
0x1800538e4  retn
0x1800538e5  mov     rcx, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800538ec  add     rcx, 1640h; this
0x1800538f3  call    ?IsLockedByCurrentThread@CTreeLock@@QEBA_NXZ; CTreeLock::IsLockedByCurrentThread(void)
0x1800538f8  test    al, al
0x1800538fa  jnz     loc_18005385C
0x180053900  mov     rdx, [rsp+68h]; void *
0x180053905  mov     ecx, 88980087h; int
0x18005390a  call    ModuleFailFastForHRESULT
0x180053910  mov     rax, [rcx+18h]
0x180053914  lea     rcx, [rsp+68h+arg_0]; this
0x180053919  mov     r12, [rax+330h]
0x180053920  sub     r12, 0FFFFFFFFFFFFFF80h
0x180053924  call    ?Start@QpcStopwatch@@QEAAXXZ; QpcStopwatch::Start(void)
0x180053929  mov     rbx, [rsp+68h+arg_0]
0x18005392e  jmp     loc_180053787
0x180053933  mov     rcx, [rsp+68h]; this
0x180053938  lea     r8, aOnecoreuapWind_88; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x18005393f  mov     edx, 571h; void *
0x180053944  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005394a  mov     rcx, [rsp+68h]; this
0x18005394f  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x180053956  mov     r9d, ebx; char *
0x180053959  mov     edx, 2ACh; void *
0x18005395e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053963  mov     rcx, [rsp+68h]; this
0x180053968  lea     r8, aOnecoreuapWind_172; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x18005396f  mov     r9d, ebx; char *
0x180053972  mov     edx, 7B0h; void *
0x180053977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005397c  mov     [rsp+68h+var_40], 0
0x180053985  mov     [rsp+68h+var_48], 589h
0x18005398d  jmp     loc_1800538B0
0x180053992  mov     rdx, [rdi+0C0h]; struct SubchannelMaskInfo *
0x180053999  test    rdx, rdx
0x18005399c  jz      loc_18005382C
0x1800539a2  cmp     byte ptr [rdx+4], 0
0x1800539a6  jbe     loc_18005382C
0x1800539ac  mov     rcx, r14; this
0x1800539af  call    ?ApplyMaskToValue@CExpressionValue@@QEAAJPEBVSubchannelMaskInfo@@@Z; CExpressionValue::ApplyMaskToValue(SubchannelMaskInfo const *)
0x1800539b4  jmp     loc_18005382C
0x1800539b9  cmp     dword ptr [r14+40h], 12h
0x1800539be  jnz     loc_180053822
0x1800539c4  movaps  [rsp+68h+var_38], xmm6
0x1800539c9  mov     rcx, r14; this
0x1800539cc  movss   xmm6, dword ptr [r14]
0x1800539d1  call    ?DestroyCurrent@CExpressionValue@@AEAAXXZ; CExpressionValue::DestroyCurrent(void)
0x1800539d6  mulss   xmm6, cs:__real@42652ee0
0x1800539de  mov     dword ptr [r14+40h], 12h
0x1800539e6  movss   dword ptr [r14], xmm6
0x1800539eb  movaps  xmm6, [rsp+68h+var_38]
0x1800539f0  jmp     loc_180053822
0x1800539f5  xor     edx, edx
0x1800539f7  jmp     loc_180053860
0x1800539fc  lea     rcx, [rsp+68h+arg_0]; this
0x180053a01  call    ?GetElapsed@QpcStopwatch@@QEAA_JXZ; QpcStopwatch::GetElapsed(void)
0x180053a06  mov     r8, rax
0x180053a09  mov     edx, 3
0x180053a0e  mov     rcx, r12
0x180053a11  call    ?AddDurationSample@CExpressionPerformanceCounter@@QEAAXW4ExpressionPerformanceLabel@@_J@Z; CExpressionPerformanceCounter::AddDurationSample(ExpressionPerformanceLabel,__int64)
0x180053a16  jmp     loc_1800537EF
```

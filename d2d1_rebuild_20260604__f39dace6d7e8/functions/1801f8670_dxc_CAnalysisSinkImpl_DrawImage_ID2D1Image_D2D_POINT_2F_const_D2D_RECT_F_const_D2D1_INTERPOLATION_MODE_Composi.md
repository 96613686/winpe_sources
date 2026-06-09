# dxc::CAnalysisSinkImpl::DrawImage(ID2D1Image *,D2D_POINT_2F const *,D2D_RECT_F const *,D2D1_INTERPOLATION_MODE,CompositeOrBlendMode)

- ea: `0x1801f8670`
- end: `0x1801f8a45`
- name: `?DrawImage@CAnalysisSinkImpl@dxc@@UEAAJPEAUID2D1Image@@PEBUD2D_POINT_2F@@PEBUD2D_RECT_F@@W4D2D1_INTERPOLATION_MODE@@VCompositeOrBlendMode@@@Z`
- size: `981`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800172a0`
- `0x180165c50`
- `0x1801ef9c8`
- `0x1801f1890`
- `0x1801f7fbc`
- `0x1801f8670`
- `0x18025b100`
- `0x18029b254`
- `0x18029b684`
- `0x18029fc54`
- `0x18029fee0`
- `0x1802a7d1c`
- `0x1802a7f30`
- `0x180307010`

## string_xrefs

- `0x1801f8771`: `D2D1_COMPOSITE_MODE_DESTINATION_IN not supported natively by print system`
- `0x1801f877a`: `D2D1_COMPOSITE_MODE_SOURCE_IN not supported natively by print system`
- `0x1801f8768`: `D2D1_COMPOSITE_MODE_SOURCE_OUT not supported natively by print system`
- `0x1801f878c`: `D2D1_COMPOSITE_MODE_DESTINATION_ATOP not supported natively by print system`
- `0x1801f8783`: `D2D1_COMPOSITE_MODE_DESTINATION_OVER not supported natively by print system`
- `0x1801f875c`: `D2D1_COMPOSITE_MODE_DESTINATION_OUT not supported natively by print system`
- `0x1801f8750`: `D2D1_COMPOSITE_MODE_SOURCE_ATOP not supported natively by print system`
- `0x1801f87c6`: `D2D1_COMPOSITE_MODE_SOURCE_COPY not supported natively by print system`
- `0x1801f87bd`: `D2D1_COMPOSITE_MODE_BOUNDED_SOURCE_COPY not supported natively by print system`
- `0x1801f87ae`: `D2D1_COMPOSITE_MODE_MASK_INVERT not supported natively by print system`
- `0x1801f87ed`: `D2D1_COMPOSITE_MODE_XOR not supported natively by print system`
- `0x1801f87e4`: `D2D1_COMPOSITE_MODE_PLUS not supported natively by print system`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall dxc::CAnalysisSinkImpl::DrawImage(
        __int64 a1,
        struct ID2D1Image *a2,
        struct D2D_POINT_2F *a3,
        struct D2D_RECT_F *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v9; // rcx
  unsigned __int64 v11; // r13
  char v12; // r14
  const wchar_t *v13; // r8
  const wchar_t *v14; // r8
  bool v15; // r15
  int *v16; // rbx
  int v17; // eax
  unsigned int v18; // esi
  int v19; // eax
  const struct D2D_RECT_F *v20; // rdx
  bool v21; // [rsp+30h] [rbp-48h] BYREF
  int v22; // [rsp+34h] [rbp-44h] BYREF
  struct D2D_POINT_2F v23; // [rsp+38h] [rbp-40h] BYREF
  struct D2D_RECT_F *v24[2]; // [rsp+40h] [rbp-38h]
  struct D2D_RECT_F v25; // [rsp+50h] [rbp-28h] BYREF

  v24[0] = a4;
  *(_QWORD *)&v25.left = a2;
  if ( !HIDWORD(a6) )
    dxc::SQMCollector::RecordCompositeMode((enum D2D1_COMPOSITE_MODE)a6);
  v9 = *(_QWORD *)(a1 + 16);
  if ( *(_DWORD *)(v9 + 400) )
    return 0;
  v22 = 0;
  if ( *(_DWORD *)(a1 + 8) == 8 )
    v11 = -1;
  else
    v11 = dxc::ActionRecorder::RecordCall(v9 + 408, 15);
  v21 = 0;
  if ( dxc::CAnalysisSinkImpl::DetectComplexAndReturn((dxc::CAnalysisSinkImpl *)a1, 0, &v21, &v22, 0) )
    return (unsigned int)v22;
  v12 = 1;
  if ( HIDWORD(a6) )
  {
    v13 = (const wchar_t *)L"D2D1_BLEND_MODE not supported natively by print system";
    goto LABEL_39;
  }
  if ( (int)a6 > 7 )
  {
    if ( (_DWORD)a6 == 8 )
    {
      v13 = L"D2D1_COMPOSITE_MODE_XOR not supported natively by print system";
      goto LABEL_39;
    }
    if ( (_DWORD)a6 == 9 )
    {
      v13 = L"D2D1_COMPOSITE_MODE_PLUS not supported natively by print system";
      goto LABEL_39;
    }
    if ( (_DWORD)a6 != 10 )
    {
      if ( (_DWORD)a6 == 11 )
      {
        v13 = L"D2D1_COMPOSITE_MODE_BOUNDED_SOURCE_COPY not supported natively by print system";
        goto LABEL_39;
      }
      if ( (_DWORD)a6 == 12 )
      {
        v13 = L"D2D1_COMPOSITE_MODE_MASK_INVERT not supported natively by print system";
        goto LABEL_39;
      }
      goto LABEL_32;
    }
    v14 = (const wchar_t *)L"D2D1_COMPOSITE_MODE_SOURCE_COPY not supported natively by print system";
LABEL_35:
    *(_DWORD *)(a1 + 12) |= 0x20u;
    v15 = 1;
    dxc::OutputDebugMessage(*(dxc **)(a1 + 16), (const struct dxc::RenderState *)0x4CB, (unsigned int)v14);
    goto LABEL_41;
  }
  switch ( (_DWORD)a6 )
  {
    case 7:
      v14 = L"D2D1_COMPOSITE_MODE_DESTINATION_ATOP not supported natively by print system";
      goto LABEL_35;
    case 1:
      v14 = L"D2D1_COMPOSITE_MODE_DESTINATION_OVER not supported natively by print system";
      goto LABEL_35;
    case 2:
      v14 = L"D2D1_COMPOSITE_MODE_SOURCE_IN not supported natively by print system";
      goto LABEL_35;
    case 3:
      v14 = L"D2D1_COMPOSITE_MODE_DESTINATION_IN not supported natively by print system";
      goto LABEL_35;
    case 4:
      v14 = L"D2D1_COMPOSITE_MODE_SOURCE_OUT not supported natively by print system";
      goto LABEL_35;
    case 5:
      v13 = L"D2D1_COMPOSITE_MODE_DESTINATION_OUT not supported natively by print system";
      goto LABEL_39;
  }
  if ( (_DWORD)a6 != 6 )
  {
LABEL_32:
    v15 = v21;
    goto LABEL_40;
  }
  v13 = L"D2D1_COMPOSITE_MODE_SOURCE_ATOP not supported natively by print system";
LABEL_39:
  v15 = 1;
  dxc::OutputDebugMessage(*(dxc **)(a1 + 16), (const struct dxc::RenderState *)0x4CB, (unsigned int)v13);
LABEL_40:
  if ( !v15 )
  {
    v17 = *(_DWORD *)(a1 + 12);
    v16 = (int *)(a1 + 12);
    goto LABEL_44;
  }
LABEL_41:
  v16 = (int *)(a1 + 12);
  v17 = *(_DWORD *)(a1 + 12);
  if ( (v17 & 4) != 0 )
  {
    *v16 = v17 | 2;
LABEL_50:
    v18 = -2142108160;
    goto LABEL_51;
  }
LABEL_44:
  if ( *(_DWORD *)(a1 + 8) != 8 )
  {
    if ( v15 )
    {
      *v16 = v17 | 1;
      if ( *(_DWORD *)(a1 + 8) == 4 )
      {
        v12 = 0;
        std::vector<dxc::_MethodIDAction,NonThrowingNewStlAllocator<dxc::_MethodIDAction>>::resize(
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 456LL),
          v11 + 1);
        v18 = -2142108160;
      }
      else
      {
        v18 = v22;
      }
      goto LABEL_67;
    }
    v23 = 0;
    win_scope::detail::scope_helper<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v23,
      0);
    v23 = 0;
    if ( (**(int (__fastcall ***)(struct ID2D1Image *, GUID *, struct D2D_POINT_2F *))a2)(
           a2,
           &GUID_b4f34a19_2383_4d76_94f6_ec343657c3dc,
           &v23) >= 0 )
    {
      v19 = dxc::CAnalysisSinkImpl::AnalyzeNestedD2DCommandList((dxc::CAnalysisSinkImpl *)a1, v24[0]);
      if ( v19 )
      {
        v15 = 1;
        if ( (v19 & 4) == 0 )
        {
          if ( (v19 & 2) != 0 )
          {
            v12 = 0;
            v18 = -2142108160;
            *v16 |= 2u;
            goto LABEL_65;
          }
          if ( (v19 & 1) != 0 )
          {
            *v16 |= 1u;
            std::vector<dxc::_MethodIDAction,NonThrowingNewStlAllocator<dxc::_MethodIDAction>>::resize(
              *(_QWORD *)(*(_QWORD *)(a1 + 16) + 456LL),
              v11 + 1);
          }
        }
      }
      else
      {
        v12 = 0;
      }
    }
    v18 = v22;
LABEL_65:
    if ( v23 )
      (*(void (__fastcall **)(struct D2D_POINT_2F))(**(_QWORD **)&v23 + 16LL))(v23);
    goto LABEL_67;
  }
  v16 = (int *)(a1 + 12);
  if ( v17 || v15 || dxc::CAnalysisSinkImpl::IsComplexD2DImage((dxc::CAnalysisSinkImpl *)a1, a2) )
  {
    v15 = 1;
    goto LABEL_50;
  }
  v18 = v22;
LABEL_51:
  v12 = 0;
LABEL_67:
  if ( v15 && (*v16 |= 8u, (*v16 & 4) != 0) )
  {
    *v16 |= 2u;
    v18 = -2142108160;
  }
  else if ( v12 )
  {
    v23 = 0;
    if ( a3 )
      v23 = *a3;
    dxc::CBoundsFinder::DetermineBoundsAndAdjustOffset(
      (dxc::CBoundsFinder *)(*(_QWORD *)(a1 + 16) + 80LL),
      &v25,
      *(struct ID2D1Image **)&v25.left,
      v24[0],
      &v23);
    if ( !dxc::RectEmpty((dxc *)&v25, v20) )
    {
      v24[0] = (struct D2D_RECT_F *)v23;
      *(float *)&v24[1] = (float)(v25.right - v25.left) + v23.x;
      *((float *)&v24[1] + 1) = (float)(v25.bottom - v25.top) + v23.y;
      v25.left = v23.x;
      LODWORD(v25.top) = _mm_shuffle_ps(*(__m128 *)v24, *(__m128 *)v24, 85).m128_u32[0];
      LODWORD(v25.right) = _mm_shuffle_ps(*(__m128 *)v24, *(__m128 *)v24, 170).m128_u32[0];
      LODWORD(v25.bottom) = _mm_shuffle_ps(*(__m128 *)v24, *(__m128 *)v24, 255).m128_u32[0];
    }
    dxc::CAnalysisSinkImpl::AddVisual((dxc::CAnalysisSinkImpl *)a1, v15, v11, &v25);
  }
  *v16 &= ~0x20u;
  return v18;
}

```

## disassembly

```asm
0x1801f8670  push    rbp
0x1801f8672  push    rbx
0x1801f8673  push    rsi
0x1801f8674  push    rdi
0x1801f8675  push    r12
0x1801f8677  push    r13
0x1801f8679  push    r14
0x1801f867b  push    r15
0x1801f867d  mov     rbp, rsp
0x1801f8680  sub     rsp, 78h
0x1801f8684  mov     rax, cs:__security_cookie
0x1801f868b  xor     rax, rsp
0x1801f868e  mov     [rbp+var_18], rax
0x1801f8692  mov     [rbp+var_38], r9
0x1801f8696  mov     r12, r8
0x1801f8699  mov     rsi, rdx
0x1801f869c  mov     qword ptr [rbp+var_28.left], rdx
0x1801f86a0  mov     rdi, rcx
0x1801f86a3  mov     rbx, qword ptr [rbp+arg_28]
0x1801f86a7  mov     rax, rbx
0x1801f86aa  shr     rax, 20h
0x1801f86ae  xor     r15d, r15d
0x1801f86b1  test    eax, eax
0x1801f86b3  jnz     short loc_1801F86BC
0x1801f86b5  mov     ecx, ebx; enum D2D1_COMPOSITE_MODE
0x1801f86b7  call    ?RecordCompositeMode@SQMCollector@dxc@@SAXW4D2D1_COMPOSITE_MODE@@@Z; dxc::SQMCollector::RecordCompositeMode(D2D1_COMPOSITE_MODE)
0x1801f86bc  mov     rcx, [rdi+10h]
0x1801f86c0  cmp     [rcx+190h], r15d
0x1801f86c7  jbe     short loc_1801F86D0
0x1801f86c9  xor     eax, eax
0x1801f86cb  jmp     loc_1801F8A28
0x1801f86d0  mov     [rbp+var_44], r15d
0x1801f86d4  cmp     dword ptr [rdi+8], 8
0x1801f86d8  jz      short loc_1801F86F0
0x1801f86da  add     rcx, 198h
0x1801f86e1  mov     edx, 0Fh
0x1801f86e6  call    ?RecordCall@ActionRecorder@dxc@@QEAA_KW4EMethodId@2@@Z; dxc::ActionRecorder::RecordCall(dxc::EMethodId)
0x1801f86eb  mov     r13, rax
0x1801f86ee  jmp     short loc_1801F86F4
0x1801f86f0  or      r13, 0FFFFFFFFFFFFFFFFh
0x1801f86f4  mov     [rbp+var_48], r15b
0x1801f86f8  mov     byte ptr [rsp+78h+var_58], r15b; bool
0x1801f86fd  lea     r9, [rbp+var_44]; int *
0x1801f8701  lea     r8, [rbp+var_48]; bool *
0x1801f8705  xor     edx, edx; struct ID2D1Brush *
0x1801f8707  mov     rcx, rdi; this
0x1801f870a  call    ?DetectComplexAndReturn@CAnalysisSinkImpl@dxc@@AEAA_NPEAUID2D1Brush@@PEA_NPEAJ_N@Z; dxc::CAnalysisSinkImpl::DetectComplexAndReturn(ID2D1Brush *,bool *,long *,bool)
0x1801f870f  test    al, al
0x1801f8711  jz      short loc_1801F871B
0x1801f8713  mov     eax, [rbp+var_44]
0x1801f8716  jmp     loc_1801F8A28
0x1801f871b  mov     r14d, 1
0x1801f8721  cmp     [rbp+74h], r15d
0x1801f8725  jnz     loc_1801F87F6
0x1801f872b  cmp     ebx, 7
0x1801f872e  jg      short loc_1801F8795
0x1801f8730  jz      short loc_1801F878C
0x1801f8732  sub     ebx, r14d
0x1801f8735  jz      short loc_1801F8783
0x1801f8737  sub     ebx, r14d
0x1801f873a  jz      short loc_1801F877A
0x1801f873c  sub     ebx, r14d
0x1801f873f  jz      short loc_1801F8771
0x1801f8741  sub     ebx, r14d
0x1801f8744  jz      short loc_1801F8768
0x1801f8746  sub     ebx, r14d
0x1801f8749  jz      short loc_1801F875C
0x1801f874b  cmp     ebx, r14d
0x1801f874e  jnz     short loc_1801F87B7
0x1801f8750  lea     r8, aD2d1CompositeM; "D2D1_COMPOSITE_MODE_SOURCE_ATOP not sup"...
0x1801f8757  jmp     loc_1801F87FD
0x1801f875c  lea     r8, aD2d1CompositeM_9; "D2D1_COMPOSITE_MODE_DESTINATION_OUT not"...
0x1801f8763  jmp     loc_1801F87FD
0x1801f8768  lea     r8, aD2d1CompositeM_1; "D2D1_COMPOSITE_MODE_SOURCE_OUT not supp"...
0x1801f876f  jmp     short loc_1801F87CD
0x1801f8771  lea     r8, aD2d1CompositeM_8; "D2D1_COMPOSITE_MODE_DESTINATION_IN not "...
0x1801f8778  jmp     short loc_1801F87CD
0x1801f877a  lea     r8, aD2d1CompositeM_2; "D2D1_COMPOSITE_MODE_SOURCE_IN not suppo"...
0x1801f8781  jmp     short loc_1801F87CD
0x1801f8783  lea     r8, aD2d1CompositeM_4; "D2D1_COMPOSITE_MODE_DESTINATION_OVER no"...
0x1801f878a  jmp     short loc_1801F87CD
0x1801f878c  lea     r8, aD2d1CompositeM_6; "D2D1_COMPOSITE_MODE_DESTINATION_ATOP no"...
0x1801f8793  jmp     short loc_1801F87CD
0x1801f8795  sub     ebx, 8
0x1801f8798  jz      short loc_1801F87ED
0x1801f879a  sub     ebx, r14d
0x1801f879d  jz      short loc_1801F87E4
0x1801f879f  sub     ebx, r14d
0x1801f87a2  jz      short loc_1801F87C6
0x1801f87a4  sub     ebx, r14d
0x1801f87a7  jz      short loc_1801F87BD
0x1801f87a9  cmp     ebx, r14d
0x1801f87ac  jnz     short loc_1801F87B7
0x1801f87ae  lea     r8, aD2d1CompositeM_10; "D2D1_COMPOSITE_MODE_MASK_INVERT not sup"...
0x1801f87b5  jmp     short loc_1801F87FD
0x1801f87b7  mov     r15b, [rbp+var_48]
0x1801f87bb  jmp     short loc_1801F880E
0x1801f87bd  lea     r8, aD2d1CompositeM_3; "D2D1_COMPOSITE_MODE_BOUNDED_SOURCE_COPY"...
0x1801f87c4  jmp     short loc_1801F87FD
0x1801f87c6  lea     r8, aD2d1CompositeM_5; "D2D1_COMPOSITE_MODE_SOURCE_COPY not sup"...
0x1801f87cd  or      dword ptr [rdi+0Ch], 20h
0x1801f87d1  mov     r15b, r14b
0x1801f87d4  mov     edx, 4CBh; struct dxc::RenderState *
0x1801f87d9  mov     rcx, [rdi+10h]; this
0x1801f87dd  call    ?OutputDebugMessage@dxc@@YAXPEBURenderState@1@IZZ; dxc::OutputDebugMessage(dxc::RenderState const *,uint,...)
0x1801f87e2  jmp     short loc_1801F8813
0x1801f87e4  lea     r8, aD2d1CompositeM_7; "D2D1_COMPOSITE_MODE_PLUS not supported "...
0x1801f87eb  jmp     short loc_1801F87FD
0x1801f87ed  lea     r8, aD2d1CompositeM_0; "D2D1_COMPOSITE_MODE_XOR not supported n"...
0x1801f87f4  jmp     short loc_1801F87FD
0x1801f87f6  lea     r8, aD2d1BlendModeN; "D2D1_BLEND_MODE not supported natively "...
0x1801f87fd  mov     r15b, r14b
0x1801f8800  mov     edx, 4CBh; struct dxc::RenderState *
0x1801f8805  mov     rcx, [rdi+10h]; this
0x1801f8809  call    ?OutputDebugMessage@dxc@@YAXPEBURenderState@1@IZZ; dxc::OutputDebugMessage(dxc::RenderState const *,uint,...)
0x1801f880e  test    r15b, r15b
0x1801f8811  jz      short loc_1801F8824
0x1801f8813  lea     rbx, [rdi+0Ch]
0x1801f8817  mov     eax, [rbx]
0x1801f8819  test    al, 4
0x1801f881b  jz      short loc_1801F882B
0x1801f881d  or      eax, 2
0x1801f8820  mov     [rbx], eax
0x1801f8822  jmp     short loc_1801F8855
0x1801f8824  mov     eax, [rdi+0Ch]
0x1801f8827  lea     rbx, [rdi+0Ch]
0x1801f882b  cmp     dword ptr [rdi+8], 8
0x1801f882f  jnz     short loc_1801F8862
0x1801f8831  lea     rbx, [rdi+0Ch]
0x1801f8835  test    eax, eax
0x1801f8837  jnz     short loc_1801F8852
0x1801f8839  test    r15b, r15b
0x1801f883c  jnz     short loc_1801F8852
0x1801f883e  mov     rdx, rsi; struct ID2D1Image *
0x1801f8841  mov     rcx, rdi; this
0x1801f8844  call    ?IsComplexD2DImage@CAnalysisSinkImpl@dxc@@AEAA_NPEAUID2D1Image@@@Z; dxc::CAnalysisSinkImpl::IsComplexD2DImage(ID2D1Image *)
0x1801f8849  test    al, al
0x1801f884b  jnz     short loc_1801F8852
0x1801f884d  mov     esi, [rbp+var_44]
0x1801f8850  jmp     short loc_1801F885A
0x1801f8852  mov     r15b, r14b
0x1801f8855  mov     esi, 80520600h
0x1801f885a  xor     r14b, r14b
0x1801f885d  jmp     loc_1801F8940
0x1801f8862  test    r15b, r15b
0x1801f8865  jz      short loc_1801F889B
0x1801f8867  or      eax, r14d
0x1801f886a  mov     [rbx], eax
0x1801f886c  cmp     dword ptr [rdi+8], 4
0x1801f8870  jnz     short loc_1801F8893
0x1801f8872  xor     r14b, r14b
0x1801f8875  lea     rdx, [r13+1]
0x1801f8879  mov     rcx, [rdi+10h]
0x1801f887d  mov     rcx, [rcx+1C8h]
0x1801f8884  call    ?resize@?$vector@U_MethodIDAction@dxc@@V?$NonThrowingNewStlAllocator@U_MethodIDAction@dxc@@@@@std@@QEAAX_K@Z; std::vector<dxc::_MethodIDAction,NonThrowingNewStlAllocator<dxc::_MethodIDAction>>::resize(unsigned __int64)
0x1801f8889  mov     esi, 80520600h
0x1801f888e  jmp     loc_1801F8940
0x1801f8893  mov     esi, [rbp+var_44]
0x1801f8896  jmp     loc_1801F8940
0x1801f889b  mov     qword ptr [rbp+var_40.x], 0
0x1801f88a3  xor     edx, edx
0x1801f88a5  lea     rcx, [rbp+var_40]
0x1801f88a9  call    ?reset@?$scope_helper@PEAVIDeviceInternal@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAVIDeviceInternal@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAVIDeviceInternal@@@Z; win_scope::detail::scope_helper<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>> &,IDeviceInternal *)
0x1801f88ae  mov     qword ptr [rbp+var_40.x], 0
0x1801f88b6  mov     rax, [rsi]
0x1801f88b9  lea     r8, [rbp+var_40]
0x1801f88bd  lea     rdx, _GUID_b4f34a19_2383_4d76_94f6_ec343657c3dc
0x1801f88c4  mov     rcx, rsi
0x1801f88c7  mov     rax, [rax]
0x1801f88ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f88cf  test    eax, eax
0x1801f88d1  js      short loc_1801F8928
0x1801f88d3  mov     rax, [rbp+var_38]
0x1801f88d7  mov     [rsp+78h+var_58], rax; struct D2D_RECT_F *
0x1801f88dc  mov     r9, r12
0x1801f88df  lea     rdx, [rbp+var_40]
0x1801f88e3  mov     rcx, rdi; this
0x1801f88e6  call    ?AnalyzeNestedD2DCommandList@CAnalysisSinkImpl@dxc@@AEAA?AW4Enum@AnalysisFlags@2@AEAV?$scope@PEAUID2D1CommandList@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@_KPEBUD2D_POINT_2F@@PEBUD2D_RECT_F@@@Z; dxc::CAnalysisSinkImpl::AnalyzeNestedD2DCommandList(win_scope::scope<ID2D1CommandList *,win_scope::const_policies<win_scope::com_policies>> &,unsigned __int64,D2D_POINT_2F const *,D2D_RECT_F const *)
0x1801f88eb  test    eax, eax
0x1801f88ed  jnz     short loc_1801F88F4
0x1801f88ef  xor     r14b, r14b
0x1801f88f2  jmp     short loc_1801F8928
0x1801f88f4  mov     r15b, r14b
0x1801f88f7  test    al, 4
0x1801f88f9  jnz     short loc_1801F8928
0x1801f88fb  test    al, 2
0x1801f88fd  jz      short loc_1801F890C
0x1801f88ff  xor     r14b, r14b
0x1801f8902  mov     esi, 80520600h
0x1801f8907  or      dword ptr [rbx], 2
0x1801f890a  jmp     short loc_1801F892B
0x1801f890c  test    r14b, al
0x1801f890f  jz      short loc_1801F8928
0x1801f8911  or      [rbx], r14d
0x1801f8914  lea     rdx, [r13+1]
0x1801f8918  mov     rcx, [rdi+10h]
0x1801f891c  mov     rcx, [rcx+1C8h]
0x1801f8923  call    ?resize@?$vector@U_MethodIDAction@dxc@@V?$NonThrowingNewStlAllocator@U_MethodIDAction@dxc@@@@@std@@QEAAX_K@Z; std::vector<dxc::_MethodIDAction,NonThrowingNewStlAllocator<dxc::_MethodIDAction>>::resize(unsigned __int64)
0x1801f8928  mov     esi, [rbp+var_44]
0x1801f892b  mov     rcx, qword ptr [rbp+var_40.x]
0x1801f892f  test    rcx, rcx
0x1801f8932  jz      short loc_1801F8940
0x1801f8934  mov     rax, [rcx]
0x1801f8937  mov     rax, [rax+10h]
0x1801f893b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8940  test    r15b, r15b
0x1801f8943  jz      short loc_1801F895D
0x1801f8945  or      dword ptr [rbx], 8
0x1801f8948  mov     eax, [rbx]
0x1801f894a  test    al, 4
0x1801f894c  jz      short loc_1801F895D
0x1801f894e  or      eax, 2
0x1801f8951  mov     [rbx], eax
0x1801f8953  mov     esi, 80520600h
0x1801f8958  jmp     loc_1801F8A23
0x1801f895d  test    r14b, r14b
0x1801f8960  jz      loc_1801F8A23
0x1801f8966  mov     qword ptr [rbp+var_40.x], 0
0x1801f896e  test    r12, r12
0x1801f8971  jz      short loc_1801F897E
0x1801f8973  movsd   xmm0, qword ptr [r12]
0x1801f8979  movsd   qword ptr [rbp+var_40.x], xmm0
0x1801f897e  mov     rcx, [rdi+10h]
0x1801f8982  add     rcx, 50h ; 'P'; this
0x1801f8986  lea     rax, [rbp+var_40]
0x1801f898a  mov     [rsp+78h+var_58], rax; struct D2D_POINT_2F *
0x1801f898f  mov     r9, [rbp+var_38]; struct D2D_RECT_F *
0x1801f8993  mov     r8, qword ptr [rbp+var_28.left]; struct ID2D1Image *
0x1801f8997  lea     rdx, [rbp+var_28]; retstr
0x1801f899b  call    ?DetermineBoundsAndAdjustOffset@CBoundsFinder@dxc@@QEAA?AUD2D_RECT_F@@PEAUID2D1Image@@PEBU3@PEAUD2D_POINT_2F@@@Z; dxc::CBoundsFinder::DetermineBoundsAndAdjustOffset(ID2D1Image *,D2D_RECT_F const *,D2D_POINT_2F *)
0x1801f89a0  lea     rcx, [rbp+var_28]; this
0x1801f89a4  call    ?RectEmpty@dxc@@YA_NAEBUD2D_RECT_F@@@Z; dxc::RectEmpty(D2D_RECT_F const &)
0x1801f89a9  test    al, al
0x1801f89ab  jnz     short loc_1801F8A11
0x1801f89ad  movss   xmm1, [rbp+var_40.x]
0x1801f89b2  movss   dword ptr [rbp+var_38], xmm1
0x1801f89b7  movss   xmm2, [rbp+var_40.y]
0x1801f89bc  movss   dword ptr [rbp+var_38+4], xmm2
0x1801f89c1  movss   xmm0, [rbp+var_28.right]
0x1801f89c6  subss   xmm0, [rbp+var_28.left]
0x1801f89cb  addss   xmm0, xmm1
0x1801f89cf  movss   dword ptr [rbp+var_38+8], xmm0
0x1801f89d4  movss   xmm1, [rbp+var_28.bottom]
0x1801f89d9  subss   xmm1, [rbp+var_28.top]
0x1801f89de  addss   xmm1, xmm2
0x1801f89e2  movss   dword ptr [rbp+var_38+0Ch], xmm1
0x1801f89e7  movups  xmm3, xmmword ptr [rbp+var_38]
0x1801f89eb  movss   [rbp+var_28.left], xmm3
0x1801f89f0  movaps  xmm0, xmm3
0x1801f89f3  shufps  xmm0, xmm3, 55h ; 'U'
0x1801f89f7  movss   [rbp+var_28.top], xmm0
0x1801f89fc  movaps  xmm1, xmm3
0x1801f89ff  shufps  xmm1, xmm3, 0AAh
0x1801f8a03  movss   [rbp+var_28.right], xmm1
0x1801f8a08  shufps  xmm3, xmm3, 0FFh
0x1801f8a0c  movss   [rbp+var_28.bottom], xmm3
0x1801f8a11  lea     r9, [rbp+var_28]; struct D2D_RECT_F *
0x1801f8a15  mov     r8, r13; unsigned __int64
0x1801f8a18  mov     dl, r15b; bool
0x1801f8a1b  mov     rcx, rdi; this
0x1801f8a1e  call    ?AddVisual@CAnalysisSinkImpl@dxc@@AEAAX_N_KPEBUD2D_RECT_F@@@Z; dxc::CAnalysisSinkImpl::AddVisual(bool,unsigned __int64,D2D_RECT_F const *)
0x1801f8a23  and     dword ptr [rbx], 0FFFFFFDFh
0x1801f8a26  mov     eax, esi
0x1801f8a28  mov     rcx, [rbp+var_18]
0x1801f8a2c  xor     rcx, rsp; StackCookie
0x1801f8a2f  call    __security_check_cookie
0x1801f8a34  add     rsp, 78h
0x1801f8a38  pop     r15
0x1801f8a3a  pop     r14
0x1801f8a3c  pop     r13
0x1801f8a3e  pop     r12
0x1801f8a40  pop     rdi
0x1801f8a41  pop     rsi
0x1801f8a42  pop     rbx
0x1801f8a43  pop     rbp
0x1801f8a44  retn
```

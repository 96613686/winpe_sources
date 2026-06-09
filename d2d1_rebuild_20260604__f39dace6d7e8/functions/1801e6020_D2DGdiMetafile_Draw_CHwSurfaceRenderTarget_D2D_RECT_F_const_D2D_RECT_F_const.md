# D2DGdiMetafile::Draw(CHwSurfaceRenderTarget *,D2D_RECT_F const *,D2D_RECT_F const *)

- ea: `0x1801e6020`
- end: `0x1801e673f`
- name: `?Draw@D2DGdiMetafile@@UEAAJPEAVCHwSurfaceRenderTarget@@PEBUD2D_RECT_F@@1@Z`
- size: `1823`
- prototype: `__int64 __fastcall(D2DGdiMetafile *__hidden this, struct CHwSurfaceRenderTarget *, const struct D2D_RECT_F *, const struct D2D_RECT_F *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000de60`
- `0x1800152a0`
- `0x180015420`
- `0x18001fd58`
- `0x180068150`
- `0x180084f70`
- `0x1800969a0`
- `0x1800ca6f0`
- `0x1800cce70`
- `0x180122aa4`
- `0x18013e570`
- `0x1801430d0`
- `0x180148c84`
- `0x180167480`
- `0x1801e58c4`
- `0x1801e6020`
- `0x1801e6748`
- `0x1801e6784`
- `0x18025b100`
- `0x18026a0a0`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e6330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e66f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e6330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e66f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801e61e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801e62be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801e61e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801e62be`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e62cf`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e62cf`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801e61c6`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801e61c6`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e6630`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e66ef`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e6630`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e66ef`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801e627b`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801e627b`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e62ae`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e62ae`

## pseudocode

```c
__int64 __fastcall D2DGdiMetafile::Draw(
        D2DGdiMetafile *this,
        struct CHwSurfaceRenderTarget *a2,
        const struct D2D_RECT_F *a3,
        const struct D2D_RECT_F *a4)
{
  signed int v7; // ebx
  const struct D2D_RECT_F *v8; // r9
  HDC CompatibleDC; // r12
  unsigned int v10; // esi
  unsigned int v11; // r15d
  __int64 v12; // r14
  HBITMAP v13; // rax
  HGDIOBJ *v14; // rbx
  __int64 v15; // rcx
  struct D2D_RECT_F *v16; // rdx
  signed int LastError; // eax
  unsigned int v18; // ebx
  unsigned int i; // r14d
  __int64 v20; // r12
  int v21; // ecx
  int v22; // eax
  unsigned int v23; // edx
  unsigned int v24; // ecx
  __int64 v25; // rbx
  struct D2D_SIZE_U MinAllocationSize; // rax
  int v27; // edx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  __m128 v31; // xmm1
  __m128 v32; // xmm0
  int v33; // eax
  HGDIOBJ v34; // rbx
  int v35; // eax
  signed int v36; // esi
  signed int v38; // eax
  HANDLE hSection; // [rsp+20h] [rbp-E0h]
  DWORD offset[2]; // [rsp+28h] [rbp-D8h]
  __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  struct D2D_RECT_F v42; // [rsp+48h] [rbp-B8h] BYREF
  HGDIOBJ ho; // [rsp+58h] [rbp-A8h] BYREF
  int v44; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v45[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+80h] [rbp-80h] BYREF
  struct D2D_RECT_F *v48; // [rsp+88h] [rbp-78h] BYREF
  HDC v49; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v50; // [rsp+98h] [rbp-68h]
  unsigned int v51; // [rsp+9Ch] [rbp-64h]
  __int64 v52; // [rsp+A0h] [rbp-60h]
  __int128 v53; // [rsp+A8h] [rbp-58h] BYREF
  D2D_SIZE_F v54[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct D2D_RECT_F v55; // [rsp+C8h] [rbp-38h] BYREF
  BITMAPINFO pbmi; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v57; // [rsp+108h] [rbp+8h] BYREF

  *(_OWORD *)&v54[0].width = 0;
  if ( a4 )
  {
    *(struct D2D_RECT_F *)&v54[0].width = *a4;
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, D2D_SIZE_F *))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2), v54);
    if ( v7 < 0 )
      goto LABEL_58;
  }
  if ( a3 )
  {
    v55 = *a3;
  }
  else
  {
    *(_QWORD *)&v42.left = 0;
    v42.right = RectUtil::GetWidth<D2D_RECT_F>(v54);
    v42.bottom = RectUtil::GetHeight<TMilRect_<float,D2D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>>(v54);
    v55 = v42;
  }
  v42 = 0;
  MILMatrix3x2::Transform2DBounds((struct CHwSurfaceRenderTarget *)((char *)a2 + 248), &v55, &v42);
  v48 = 0;
  (*(void (__fastcall **)(_QWORD, struct D2D_RECT_F **, char *))(**((_QWORD **)this + 2) + 40LL))(
    *((_QWORD *)this + 2),
    &v48,
    (char *)&v48 + 4);
  v57 = (__int128)*RectUtil::DipsToPixels((RectUtil *)&v53, v48, (struct D2D_SIZE_F)v54, v8);
  if ( !(unsigned __int8)RectUtil::IsWellOrdered<TMilRect_<float,D2D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>>(&v57) )
    return 0;
  if ( !(unsigned __int8)RectUtil::IsWellOrdered<TMilRect_<float,D2D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>>(&v42) )
    return 0;
  *(float *)&v46 = v42.left - 1.0;
  *((float *)&v46 + 2) = v42.right + 1.0;
  *((float *)&v46 + 1) = v42.top - 1.0;
  *((float *)&v46 + 3) = v42.bottom + 1.0;
  v53 = v46;
  v46 = *(_OWORD *)RectUtil::Inflate<tagRECT>(&v42, &v53);
  if ( !(unsigned __int8)TMilRect<int,tagRECT,RectUniqueness::_CMILSurfaceRect_>::Intersect(&v46, (char *)a2 + 208) )
    return 0;
  v47 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v49 = CompatibleDC;
  win_scope::detail::scope_helper<HDC__ *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(HDC__ *),&int DeleteDC(HDC__ *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_nothrow>>>::reset(
    &v47,
    0);
  SetLastError(0);
  if ( CompatibleDC )
  {
    v10 = DWORD2(v46) - v46;
    v11 = HIDWORD(v46) - DWORD1(v46);
    `vector constructor iterator'(
      &v53,
      8u,
      2u,
      win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>);
    v12 = 0;
    v42 = 0;
    while ( (unsigned int)v12 < 2 )
    {
      pbmi.bmiHeader.biSize = 40;
      pbmi.bmiHeader.biWidth = v10;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      pbmi.bmiHeader.biHeight = -v11;
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      v13 = CreateDIBSection(0, &pbmi, 0, (void **)&v42 + v12, 0, 0);
      ho = 0;
      *(_QWORD *)v45 = v13;
      v14 = (HGDIOBJ *)&v54[v12 - 2];
      win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
        &ho,
        v14);
      if ( ho )
        DeleteObject(ho);
      *v14 = *(HGDIOBJ *)v45;
      SetLastError(0);
      if ( !*v14 )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2003238887;
        DoStackCapture(v7);
LABEL_53:
        `vector destructor iterator'(
          &v53,
          8u,
          2u,
          win_scope::scope<HBITMAP__ *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int DeleteObject(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<5>,win_scope::report_policy_nothrow>>>::~scope<HBITMAP__ *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int DeleteObject(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<5>,win_scope::report_policy_nothrow>>>);
        DeleteDC(CompatibleDC);
        return (unsigned int)v7;
      }
      SelectObject(CompatibleDC, *v14);
      v15 = *((_QWORD *)this + 2);
      v47 = v46;
      v16 = &v55;
      LOBYTE(v16) = -((_DWORD)v12 != 0);
      (*(void (__fastcall **)(__int64, struct D2D_RECT_F *, char *, __int64 *, struct D2D_RECT_F *, __int128 *, HDC))(*(_QWORD *)v15 + 24LL))(
        v15,
        v16,
        (char *)a2 + 248,
        &v47,
        &v55,
        &v57,
        CompatibleDC);
      v12 = (unsigned int)(v12 + 1);
    }
    v18 = 0;
    if ( v11 )
    {
      do
      {
        for ( i = 0; i < v10; ++i )
        {
          v20 = i + v10 * v18;
          v52 = *(_QWORD *)&v42.left;
          v21 = *(_DWORD *)(*(_QWORD *)&v42.left + 4 * v20);
          v22 = *(_DWORD *)(*(_QWORD *)&v42.right + 4 * v20);
          LODWORD(ho) = v22;
          v44 = v21;
          if ( (unsigned __int8)v22 < (unsigned __int8)v21 || BYTE1(v22) < BYTE1(v21) || BYTE2(v22) < BYTE2(v21) )
          {
            v23 = 127 * ((unsigned int)(unsigned __int8)v21 + 1) / 0xFF;
            v24 = 127 * (BYTE1(v44) + 1);
            *(_BYTE *)(*(_QWORD *)&v42.left + 4 * v20) = v23;
            *(_BYTE *)(*(_QWORD *)&v42.left + 4 * v20 + 1) = v24 / 0xFF;
            *(_BYTE *)(*(_QWORD *)&v42.left + 4 * v20 + 2) = 127 * ((unsigned int)BYTE2(v44) + 1) / 0xFF;
            *(_BYTE *)(*(_QWORD *)&v42.left + 4 * v20 + 3) = 127;
          }
          else
          {
            v45[0] = 0;
            BuildRGBAFromBW(&ho, &v44, v45);
            *(_DWORD *)(v52 + 4 * v20) = Premultiply(v45[0]);
          }
        }
        ++v18;
      }
      while ( v18 < v11 );
      CompatibleDC = v49;
    }
    v25 = *(_QWORD *)a2;
    ho = 0;
    v41 = 0;
    (*(void (__fastcall **)(struct CHwSurfaceRenderTarget *))(v25 + 616))(a2);
    MinAllocationSize = GetMinAllocationSize(*(struct D2D_SIZE_U *)((char *)a2 + 148));
    *(_QWORD *)v45 = __PAIR64__(v11, v10);
    offset[0] = 1;
    LODWORD(hSection) = v27;
    v28 = (*(__int64 (__fastcall **)(struct CHwSurfaceRenderTarget *, unsigned __int64, __int64, struct D2D_SIZE_U, HANDLE, DWORD *, __int64 *))(v25 + 528))(
            a2,
            __PAIR64__(v11, v10),
            87,
            MinAllocationSize,
            hSection,
            *(DWORD **)offset,
            &v41);
    v7 = v28;
    if ( v28 < 0
      || (v29 = (*(__int64 (__fastcall **)(struct CHwSurfaceRenderTarget *))(*(_QWORD *)a2 + 624LL))(a2),
          v49 = 0,
          v30 = *(_QWORD *)(v29 + 5640),
          v50 = v10,
          v51 = v11,
          v28 = BitmapRealization::CopyFromMemoryInternal(
                  v41,
                  &v49,
                  *(_QWORD *)&v42.left,
                  4 * v10,
                  0,
                  *(_DWORD *)(v30 + 192) == 32902),
          v7 = v28,
          v28 < 0) )
    {
      DoStackCapture(v28);
      if ( v41 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
        v41 = 0;
      }
      goto LABEL_53;
    }
    v31 = 0;
    v32 = 0;
    v31.m128_f32[0] = (float)(int)*(_QWORD *)(v41 + 84);
    v32.m128_f32[0] = (float)(int)HIDWORD(*(_QWORD *)(v41 + 84));
    v33 = D2DBitmap::Create(*((_QWORD *)a2 + 6), v41, 1, _mm_unpacklo_ps(v31, v32).m128_u32[0], 0, 0, 0, (__int64)&ho);
    v7 = v33;
    if ( v33 < 0 )
    {
      DoStackCapture(v33);
      if ( v41 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
        v41 = 0;
      }
      if ( ho )
        (*(void (__fastcall **)(HGDIOBJ))(*(_QWORD *)ho + 16LL))(ho);
      goto LABEL_53;
    }
    v34 = ho;
    v35 = CHwSurfaceRenderTarget::BlendMetafile(a2);
    v36 = v35;
    if ( v35 < 0 )
    {
      DoStackCapture(v35);
      if ( v41 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
        v41 = 0;
      }
      if ( v34 )
        (*(void (__fastcall **)(HGDIOBJ))(*(_QWORD *)v34 + 16LL))(v34);
      v7 = v36;
      goto LABEL_53;
    }
    (*(void (__fastcall **)(struct CHwSurfaceRenderTarget *, __int64, __int64, _QWORD))(*(_QWORD *)a2 + 648LL))(
      a2,
      v41,
      1,
      0);
    if ( v41 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
      v41 = 0;
    }
    if ( v34 )
      (*(void (__fastcall **)(HGDIOBJ))(*(_QWORD *)v34 + 16LL))(v34);
    `vector destructor iterator'(
      &v53,
      8u,
      2u,
      win_scope::scope<HBITMAP__ *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int DeleteObject(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<5>,win_scope::report_policy_nothrow>>>::~scope<HBITMAP__ *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int DeleteObject(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<5>,win_scope::report_policy_nothrow>>>);
    DeleteDC(CompatibleDC);
    return 0;
  }
  v38 = GetLastError();
  v7 = v38;
  if ( v38 > 0 )
    v7 = (unsigned __int16)v38 | 0x80070000;
  if ( v7 >= 0 )
    v7 = -2003238887;
LABEL_58:
  DoStackCapture(v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801e6020  push    rbp
0x1801e6022  push    rbx
0x1801e6023  push    rsi
0x1801e6024  push    rdi
0x1801e6025  push    r12
0x1801e6027  push    r13
0x1801e6029  push    r14
0x1801e602b  push    r15
0x1801e602d  lea     rbp, [rsp-28h]
0x1801e6032  sub     rsp, 128h
0x1801e6039  mov     rax, cs:__security_cookie
0x1801e6040  xor     rax, rsp
0x1801e6043  mov     [rbp+60h+var_48], rax
0x1801e6047  xorps   xmm0, xmm0
0x1801e604a  mov     rsi, r8
0x1801e604d  mov     rdi, rdx
0x1801e6050  mov     r13, rcx
0x1801e6053  movups  xmmword ptr [rbp+60h+var_A8.width], xmm0
0x1801e6057  test    r9, r9
0x1801e605a  jz      short loc_1801E6067
0x1801e605c  movups  xmm0, xmmword ptr [r9]
0x1801e6060  movdqu  xmmword ptr [rbp+60h+var_A8.width], xmm0
0x1801e6065  jmp     short loc_1801E6085
0x1801e6067  mov     rcx, [rcx+10h]
0x1801e606b  lea     rdx, [rbp+60h+var_A8]
0x1801e606f  mov     rax, [rcx]
0x1801e6072  mov     rax, [rax+20h]
0x1801e6076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e607b  mov     ebx, eax
0x1801e607d  test    eax, eax
0x1801e607f  js      loc_1801E6716
0x1801e6085  test    rsi, rsi
0x1801e6088  jz      short loc_1801E6094
0x1801e608a  movups  xmm0, xmmword ptr [rsi]
0x1801e608d  movdqu  xmmword ptr [rbp+60h+var_98.left], xmm0
0x1801e6092  jmp     short loc_1801E60C4
0x1801e6094  lea     rcx, [rbp+60h+var_A8]
0x1801e6098  mov     qword ptr [rsp+160h+var_118.left], 0
0x1801e60a1  call    ??$GetWidth@UD2D_RECT_F@@@RectUtil@@YAMAEBUD2D_RECT_F@@@Z; RectUtil::GetWidth<D2D_RECT_F>(D2D_RECT_F const &)
0x1801e60a6  lea     rcx, [rbp+60h+var_A8]
0x1801e60aa  movss   [rsp+160h+var_118.right], xmm0
0x1801e60b0  call    ??$GetHeight@V?$TMilRect_@MUD2D_RECT_F@@UMilPointAndSizeF@@UNotNeeded@RectUniqueness@@@@@RectUtil@@YAMAEBV?$TMilRect_@MUD2D_RECT_F@@UMilPointAndSizeF@@UNotNeeded@RectUniqueness@@@@@Z; RectUtil::GetHeight<TMilRect_<float,D2D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>>(TMilRect_<float,D2D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded> const &)
0x1801e60b5  movss   [rsp+160h+var_118.bottom], xmm0
0x1801e60bb  movups  xmm2, xmmword ptr [rsp+160h+var_118.left]
0x1801e60c0  movups  xmmword ptr [rbp+60h+var_98.left], xmm2
0x1801e60c4  xorps   xmm0, xmm0
0x1801e60c7  lea     rcx, [rdi+0F8h]; this
0x1801e60ce  lea     r8, [rsp+160h+var_118]; struct D2D_RECT_F *
0x1801e60d3  lea     rdx, [rbp+60h+var_98]; struct D2D_RECT_F *
0x1801e60d7  movups  xmmword ptr [rsp+160h+var_118.left], xmm0
0x1801e60dc  call    ?Transform2DBounds@MILMatrix3x2@@QEBAXAEBUD2D_RECT_F@@PEAU2@@Z; MILMatrix3x2::Transform2DBounds(D2D_RECT_F const &,D2D_RECT_F *)
0x1801e60e1  xor     ecx, ecx
0x1801e60e3  lea     r8, [rbp+60h+var_D8+4]
0x1801e60e7  mov     [rbp-78h], rcx
0x1801e60eb  lea     rdx, [rbp+60h+var_D8]
0x1801e60ef  mov     rcx, [r13+10h]
0x1801e60f3  mov     rax, [rcx]
0x1801e60f6  mov     rax, [rax+28h]
0x1801e60fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e60ff  mov     rdx, [rbp+60h+var_D8]; retstr
0x1801e6103  lea     r8, [rbp+60h+var_A8]; struct D2D_SIZE_F
0x1801e6107  lea     rcx, [rbp+60h+var_B8]; this
0x1801e610b  call    ?DipsToPixels@RectUtil@@YA?AUD2D_RECT_F@@UD2D_SIZE_F@@AEBU2@@Z; RectUtil::DipsToPixels(D2D_SIZE_F,D2D_RECT_F const &)
0x1801e6110  lea     rcx, [rbp+60h+var_58]
0x1801e6114  movups  xmm4, xmmword ptr [rax]
0x1801e6117  movdqu  [rbp+60h+var_58], xmm4
0x1801e611c  call    ??$IsWellOrdered@V?$TMilRect_@MUD2D_RECT_F@@UMilPointAndSizeF@@UNotNeeded@RectUniqueness@@@@@RectUtil@@YA_NAEBV?$TMilRect_@MUD2D_RECT_F@@UMilPointAndSizeF@@UNotNeeded@RectUniqueness@@@@@Z; RectUtil::IsWellOrdered<TMilRect_<float,D2D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>>(TMilRect_<float,D2D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded> const &)
0x1801e6121  test    al, al
0x1801e6123  jz      loc_1801E6636
0x1801e6129  lea     rcx, [rsp+160h+var_118]
0x1801e612e  call    ??$IsWellOrdered@V?$TMilRect_@MUD2D_RECT_F@@UMilPointAndSizeF@@UNotNeeded@RectUniqueness@@@@@RectUtil@@YA_NAEBV?$TMilRect_@MUD2D_RECT_F@@UMilPointAndSizeF@@UNotNeeded@RectUniqueness@@@@@Z; RectUtil::IsWellOrdered<TMilRect_<float,D2D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>>(TMilRect_<float,D2D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded> const &)
0x1801e6133  test    al, al
0x1801e6135  jz      loc_1801E6636
0x1801e613b  movss   xmm2, cs:__real@3f800000
0x1801e6143  lea     rdx, [rbp+60h+var_B8]
0x1801e6147  movss   xmm0, [rsp+160h+var_118.left]
0x1801e614d  lea     rcx, [rsp+160h+var_118]
0x1801e6152  movss   xmm1, [rsp+160h+var_118.right]
0x1801e6158  subss   xmm0, xmm2
0x1801e615c  addss   xmm1, xmm2
0x1801e6160  movss   dword ptr [rsp+160h+var_F0], xmm0
0x1801e6166  movss   xmm0, [rsp+160h+var_118.top]
0x1801e616c  subss   xmm0, xmm2
0x1801e6170  movss   dword ptr [rsp+160h+var_F0+8], xmm1
0x1801e6176  movss   dword ptr [rsp+160h+var_F0+4], xmm0
0x1801e617c  movss   xmm0, [rsp+160h+var_118.bottom]
0x1801e6182  addss   xmm0, xmm2
0x1801e6186  movss   dword ptr [rsp+160h+var_F0+0Ch], xmm0
0x1801e618c  movups  xmm0, [rsp+160h+var_F0]
0x1801e6191  movups  [rbp+60h+var_B8], xmm0
0x1801e6195  call    ??$Inflate@UtagRECT@@@RectUtil@@YA?AUtagRECT@@AEBUD2D_RECT_F@@@Z; RectUtil::Inflate<tagRECT>(D2D_RECT_F const &)
0x1801e619a  lea     rdx, [rdi+0D0h]
0x1801e61a1  lea     rcx, [rsp+160h+var_F0]
0x1801e61a6  movups  xmm4, xmmword ptr [rax]
0x1801e61a9  movdqu  [rsp+160h+var_F0], xmm4
0x1801e61af  call    ?Intersect@?$TMilRect@HUtagRECT@@U_CMILSurfaceRect_@RectUniqueness@@@@QEAA_NAEBV1@@Z; TMilRect<int,tagRECT,RectUniqueness::_CMILSurfaceRect_>::Intersect(TMilRect<int,tagRECT,RectUniqueness::_CMILSurfaceRect_> const &)
0x1801e61b4  test    al, al
0x1801e61b6  jz      loc_1801E6636
0x1801e61bc  xor     ecx, ecx; hdc
0x1801e61be  mov     [rbp+60h+var_E0], 0
0x1801e61c6  call    cs:__imp_CreateCompatibleDC
0x1801e61cc  xor     edx, edx
0x1801e61ce  lea     rcx, [rbp+60h+var_E0]
0x1801e61d2  mov     r12, rax
0x1801e61d5  mov     [rbp+60h+var_D0], rax
0x1801e61d9  call    ?reset@?$scope_helper@PEAUHDC__@@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAUHDC__@@@Z$1?DeleteDC@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_nothrow@2@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUHDC__@@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAUHDC__@@@Z$1?DeleteDC@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_nothrow@2@@win_scope@@@win_scope@@@3@PEAUHDC__@@@Z; win_scope::detail::scope_helper<HDC__ *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(HDC__ *),&DeleteDC(HDC__ *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_nothrow>>>::reset(win_scope::scope<HDC__ *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(HDC__ *),&DeleteDC(HDC__ *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_nothrow>>> &,HDC__ *)
0x1801e61de  xor     ecx, ecx; dwErrCode
0x1801e61e0  call    cs:__imp_SetLastError
0x1801e61e6  test    r12, r12
0x1801e61e9  jz      loc_1801E66F7
0x1801e61ef  mov     esi, dword ptr [rsp+160h+var_F0+8]
0x1801e61f3  lea     r9, ??0?$unique_object@PEAVCHwVertexBufferWriter@@@win_scope@@QEAA@XZ; void *(*)(void *)
0x1801e61fa  mov     r15d, dword ptr [rsp+160h+var_F0+0Ch]
0x1801e61ff  lea     rcx, [rbp+60h+var_B8]; void *
0x1801e6203  sub     esi, dword ptr [rsp+160h+var_F0]
0x1801e6207  mov     edx, 8; unsigned __int64
0x1801e620c  sub     r15d, dword ptr [rsp+160h+var_F0+4]
0x1801e6211  lea     r8d, [rdx-6]; unsigned __int64
0x1801e6215  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1801e621a  xor     r14d, r14d
0x1801e621d  xorps   xmm0, xmm0
0x1801e6220  movups  xmmword ptr [rsp+160h+var_118.left], xmm0
0x1801e6225  lea     r10d, [r14+1]
0x1801e6229  cmp     r14d, 2
0x1801e622d  jnb     loc_1801E635B
0x1801e6233  xor     eax, eax
0x1801e6235  mov     [rbp+60h+pbmi.bmiHeader.biSize], 28h ; '('
0x1801e623c  mov     qword ptr [rbp+60h+pbmi.bmiHeader.biClrImportant], rax
0x1801e6240  lea     r9, [rsp+160h+var_118]
0x1801e6245  xorps   xmm0, xmm0
0x1801e6248  lea     r9, [r9+r14*8]; ppvBits
0x1801e624c  movups  xmmword ptr [rbp+60h+pbmi.bmiHeader.biWidth], xmm0
0x1801e6250  mov     eax, r15d
0x1801e6253  mov     [rbp+60h+pbmi.bmiHeader.biWidth], esi
0x1801e6256  neg     eax
0x1801e6258  mov     qword ptr [rbp+60h+pbmi.bmiHeader.biPlanes], 200001h
0x1801e6260  mov     [rbp+60h+pbmi.bmiHeader.biHeight], eax
0x1801e6263  lea     rdx, [rbp+60h+pbmi]; pbmi
0x1801e6267  xor     eax, eax
0x1801e6269  xor     r8d, r8d; usage
0x1801e626c  mov     [rsp+160h+offset], eax; offset
0x1801e6270  xor     ecx, ecx; hdc
0x1801e6272  mov     [rsp+160h+hSection], rax; hSection
0x1801e6277  movups  xmmword ptr [rbp+60h+pbmi.bmiHeader.biSizeImage], xmm0
0x1801e627b  call    cs:__imp_CreateDIBSection
0x1801e6281  lea     rcx, [rsp+160h+ho]
0x1801e6286  mov     [rsp+160h+ho], 0
0x1801e628f  mov     qword ptr [rsp+160h+var_F8], rax
0x1801e6294  lea     rax, [rbp+60h+var_B8]
0x1801e6298  lea     rbx, [rax+r14*8]
0x1801e629c  mov     rdx, rbx
0x1801e629f  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801e62a4  mov     rcx, [rsp+160h+ho]; ho
0x1801e62a9  test    rcx, rcx
0x1801e62ac  jz      short loc_1801E62B4
0x1801e62ae  call    cs:__imp_DeleteObject
0x1801e62b4  mov     rax, qword ptr [rsp+160h+var_F8]
0x1801e62b9  xor     ecx, ecx; dwErrCode
0x1801e62bb  mov     [rbx], rax
0x1801e62be  call    cs:__imp_SetLastError
0x1801e62c4  mov     rdx, [rbx]; h
0x1801e62c7  test    rdx, rdx
0x1801e62ca  jz      short loc_1801E6330
0x1801e62cc  mov     rcx, r12; hdc
0x1801e62cf  call    cs:__imp_SelectObject
0x1801e62d5  mov     eax, dword ptr [rsp+160h+var_F0]
0x1801e62d9  lea     r9, [rbp+60h+var_E0]
0x1801e62dd  mov     rcx, [r13+10h]
0x1801e62e1  lea     r8, [rdi+0F8h]
0x1801e62e8  mov     dword ptr [rbp+60h+var_E0], eax
0x1801e62eb  mov     eax, dword ptr [rsp+160h+var_F0+4]
0x1801e62ef  mov     dword ptr [rbp+60h+var_E0+4], eax
0x1801e62f2  xor     eax, eax
0x1801e62f4  mov     rdx, [rcx]
0x1801e62f7  sub     eax, r14d
0x1801e62fa  neg     eax
0x1801e62fc  mov     [rsp+160h+var_130], r12
0x1801e6301  sbb     r10b, r10b
0x1801e6304  mov     rax, [rdx+18h]
0x1801e6308  lea     rdx, [rbp+60h+var_58]
0x1801e630c  mov     qword ptr [rsp+160h+offset], rdx
0x1801e6311  lea     rdx, [rbp+60h+var_98]
0x1801e6315  mov     [rsp+160h+hSection], rdx
0x1801e631a  mov     dl, r10b
0x1801e631d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6322  mov     r10d, 1
0x1801e6328  add     r14d, r10d
0x1801e632b  jmp     loc_1801E6229
0x1801e6330  call    cs:__imp_GetLastError
0x1801e6336  mov     ebx, eax
0x1801e6338  test    eax, eax
0x1801e633a  jle     short loc_1801E6345
0x1801e633c  movzx   ebx, ax
0x1801e633f  or      ebx, 80070000h
0x1801e6345  test    ebx, ebx
0x1801e6347  mov     eax, 88990019h
0x1801e634c  cmovns  ebx, eax
0x1801e634f  mov     ecx, ebx; int
0x1801e6351  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801e6356  jmp     loc_1801E66D3
0x1801e635b  xor     r13d, r13d
0x1801e635e  mov     ebx, r13d
0x1801e6361  test    r15d, r15d
0x1801e6364  jz      loc_1801E6473
0x1801e636a  mov     r14d, r13d
0x1801e636d  test    esi, esi
0x1801e636f  jz      loc_1801E6463
0x1801e6375  mov     r13d, ebx
0x1801e6378  imul    r13d, esi
0x1801e637c  mov     r9, qword ptr [rsp+160h+var_118.left]
0x1801e6381  lea     r12d, [r14+r13]
0x1801e6385  mov     rax, qword ptr [rsp+160h+var_118.right]
0x1801e638a  mov     [rbp+60h+var_C0], r9
0x1801e638e  mov     ecx, [r9+r12*4]
0x1801e6392  mov     eax, [rax+r12*4]
0x1801e6396  mov     dword ptr [rsp+160h+ho], eax
0x1801e639a  mov     [rsp+160h+var_100], ecx
0x1801e639e  cmp     al, cl
0x1801e63a0  jb      short loc_1801E63F4
0x1801e63a2  mov     r8d, ecx
0x1801e63a5  mov     edx, eax
0x1801e63a7  shr     r8d, 8
0x1801e63ab  shr     edx, 8
0x1801e63ae  cmp     dl, r8b
0x1801e63b1  jb      short loc_1801E63F4
0x1801e63b3  mov     edx, ecx
0x1801e63b5  shr     eax, 10h
0x1801e63b8  shr     edx, 10h
0x1801e63bb  cmp     al, dl
0x1801e63bd  jb      short loc_1801E63F4
0x1801e63bf  lea     r8, [rsp+160h+var_F8]
0x1801e63c4  mov     [rsp+160h+var_F8], 0
0x1801e63cc  lea     rdx, [rsp+160h+var_100]
0x1801e63d1  lea     rcx, [rsp+160h+ho]
0x1801e63d6  call    BuildRGBAFromBW
0x1801e63db  mov     ecx, [rsp+160h+var_F8]; unsigned int
0x1801e63df  call    ?Premultiply@@YAII@Z; Premultiply(uint)
0x1801e63e4  mov     rcx, [rbp+60h+var_C0]
0x1801e63e8  mov     r10d, 1
0x1801e63ee  mov     [rcx+r12*4], eax
0x1801e63f2  jmp     short loc_1801E6454
0x1801e63f4  movzx   eax, cl
0x1801e63f7  add     eax, r10d
0x1801e63fa  imul    ecx, eax, 7Fh
0x1801e63fd  mov     eax, 80808081h
0x1801e6402  mul     ecx
0x1801e6404  movzx   eax, byte ptr [rsp+160h+var_100+1]
0x1801e6409  add     eax, r10d
0x1801e640c  shr     edx, 7
0x1801e640f  imul    ecx, eax, 7Fh
0x1801e6412  mov     eax, 80808081h
0x1801e6417  mov     [r9+r12*4], dl
0x1801e641b  mul     ecx
0x1801e641d  mov     rax, qword ptr [rsp+160h+var_118.left]
0x1801e6422  shr     edx, 7
0x1801e6425  mov     [rax+r12*4+1], dl
0x1801e642a  movzx   eax, byte ptr [rsp+160h+var_100+2]
0x1801e642f  add     eax, r10d
0x1801e6432  imul    ecx, eax, 7Fh
0x1801e6435  mov     eax, 80808081h
0x1801e643a  mul     ecx
0x1801e643c  mov     rax, qword ptr [rsp+160h+var_118.left]
0x1801e6441  shr     edx, 7
0x1801e6444  mov     [rax+r12*4+2], dl
0x1801e6449  mov     rax, qword ptr [rsp+160h+var_118.left]
0x1801e644e  mov     byte ptr [rax+r12*4+3], 7Fh
0x1801e6454  add     r14d, r10d
0x1801e6457  cmp     r14d, esi
0x1801e645a  jb      loc_1801E637C
0x1801e6460  xor     r13d, r13d
0x1801e6463  add     ebx, r10d
0x1801e6466  cmp     ebx, r15d
0x1801e6469  jb      loc_1801E636A
0x1801e646f  mov     r12, [rbp+60h+var_D0]
0x1801e6473  mov     rbx, [rdi]
0x1801e6476  mov     rcx, rdi
0x1801e6479  mov     [rsp+160h+ho], r13
0x1801e647e  mov     [rsp+160h+var_120], r13
0x1801e6483  mov     rax, [rbx+268h]
0x1801e648a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e648f  mov     rcx, [rdi+94h]; struct D2D_SIZE_U
0x1801e6496  mov     edx, eax
0x1801e6498  call    ?GetMinAllocationSize@@YA?AUD2D_SIZE_U@@U1@@Z; GetMinAllocationSize(D2D_SIZE_U)
0x1801e649d  lea     rcx, [rsp+160h+var_120]
0x1801e64a2  mov     [rsp+160h+var_F8], esi
0x1801e64a6  mov     [rsp+160h+var_130], rcx
0x1801e64ab  mov     r14d, 1
0x1801e64b1  mov     r9, rax
0x1801e64b4  mov     [rsp+160h+offset], r14d
0x1801e64b9  mov     rax, [rbx+210h]
0x1801e64c0  mov     rcx, rdi
0x1801e64c3  mov     dword ptr [rsp+160h+hSection], edx
0x1801e64c7  mov     [rsp+160h+var_F8+4], r15d
0x1801e64cc  lea     r8d, [r14+56h]
0x1801e64d0  mov     rdx, qword ptr [rsp+160h+var_F8]
0x1801e64d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e64da  mov     ebx, eax
0x1801e64dc  test    eax, eax
0x1801e64de  js      loc_1801E66B1
0x1801e64e4  mov     rax, [rdi]
  ... truncated ...
```

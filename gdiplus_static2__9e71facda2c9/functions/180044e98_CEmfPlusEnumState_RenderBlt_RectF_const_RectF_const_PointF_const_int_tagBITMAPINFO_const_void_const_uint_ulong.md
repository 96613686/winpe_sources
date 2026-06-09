# CEmfPlusEnumState::RenderBlt(RectF const &,RectF const &,PointF const *,int,tagBITMAPINFO const *,void * const,uint,ulong)

- ea: `0x180044e98`
- end: `0x180045748`
- name: `?RenderBlt@CEmfPlusEnumState@@IEAAHAEBVRectF@@0PEBVPointF@@HPEBUtagBITMAPINFO@@QEAXIK@Z`
- size: `2224`
- prototype: `__int64 __fastcall(CEmfPlusEnumState *__hidden this, const struct RectF *, const struct RectF *, const struct PointF *, int, const struct tagBITMAPINFO *, void *const, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180046674`
- `0x18012cf1c`
- `0x1801302f4`

## callees

- `0x180005810`
- `0x18000584c`
- `0x180006698`
- `0x18000be94`
- `0x180015f54`
- `0x180016704`
- `0x180019610`
- `0x180044c4c`
- `0x180044e98`
- `0x1800458f4`
- `0x1800459a0`
- `0x180045eb8`
- `0x1800599b0`
- `0x180063cd8`
- `0x1800647fc`
- `0x18006483c`
- `0x1800659ec`
- `0x180080604`
- `0x1800e423c`
- `0x1800fe5fc`
- `0x180105d40`
- `0x1801066d0`
- `0x18012d7c8`
- `0x18012e63c`
- `0x180172010`

## import_xrefs

- `GDI32!StretchDIBits` at `0x180045261`
- `GDI32!StretchDIBits` at `0x180045261`
- `GDI32!CreateDIBSection` at `0x180045130`
- `GDI32!CreateDIBSection` at `0x180045130`
- `GDI32!DeleteDC` at `0x180045270`
- `GDI32!DeleteDC` at `0x180045686`
- `GDI32!DeleteDC` at `0x180045270`
- `GDI32!DeleteDC` at `0x180045686`
- `GDI32!SelectObject` at `0x18004516a`
- `GDI32!SelectObject` at `0x18004516a`
- `GDI32!CreateCompatibleDC` at `0x18004514b`
- `GDI32!CreateCompatibleDC` at `0x18004514b`
- `GDI32!DeleteObject` at `0x180045696`
- `GDI32!DeleteObject` at `0x180045696`

## pseudocode

```c
__int64 __fastcall CEmfPlusEnumState::RenderBlt(
        CEmfPlusEnumState *this,
        const struct RectF *a2,
        const struct RectF *a3,
        const struct PointF *a4,
        int a5,
        struct tagBITMAPINFO *a6,
        void *const a7,
        unsigned int a8,
        unsigned int a9)
{
  struct tagBITMAPINFO *v11; // r15
  __int64 v12; // r8
  unsigned int v13; // r12d
  unsigned int v14; // esi
  struct tagBITMAPINFO *BmpInfoFromPalette; // r13
  GpBitmap *v16; // rax
  int v17; // r9d
  const struct PointF *v18; // rax
  struct tagBITMAPINFO *v20; // rdx
  GpBitmap *v21; // rax
  struct GpBitmap *v22; // r13
  __int64 v23; // rcx
  unsigned int v24; // edx
  const BITMAPINFO *v25; // rdx
  HDC CompatibleDC; // rax
  HDC v27; // rsi
  struct GpGraphics *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  unsigned int v32; // edx
  const BITMAPINFO *lpbmi; // rax
  GpBitmap *v34; // rax
  int v35; // r9d
  GpBitmap *v36; // rax
  GpBitmap *v37; // rsi
  __int64 v38; // rcx
  bool v39; // r15
  __m128 v40; // xmm1
  int v41; // eax
  __m128 v42; // xmm1
  int v43; // eax
  __m128 v44; // xmm1
  int v45; // eax
  __m128 v46; // xmm1
  int v47; // eax
  const struct RectF *v48; // rax
  __m128 v49; // xmm1
  __m128 v50; // xmm1
  __m128 v51; // xmm1
  float v52; // xmm0_4
  CEmfPlusEnumState *v53; // rcx
  __m128 v54; // xmm1
  int v55; // eax
  struct GpBitmap *v56; // r8
  char *v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rax
  struct GpObject *v61; // rax
  __int64 v62; // rax
  __int64 v63; // rbx
  _BYTE *v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rdx
  struct GpBrush *v67; // rax
  GpGraphics *v68; // [rsp+78h] [rbp-90h] BYREF
  const struct PointF *v69; // [rsp+80h] [rbp-88h] BYREF
  HGDIOBJ h; // [rsp+88h] [rbp-80h]
  void *ppvBits; // [rsp+90h] [rbp-78h] BYREF
  const struct RectF *v72; // [rsp+98h] [rbp-70h]
  void *lpBits; // [rsp+A0h] [rbp-68h] BYREF
  int v74; // [rsp+A8h] [rbp-60h]
  int v75; // [rsp+ACh] [rbp-5Ch]
  _DWORD v76[2]; // [rsp+B0h] [rbp-58h] BYREF
  volatile signed __int32 *v77; // [rsp+B8h] [rbp-50h]
  _QWORD v78[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v79; // [rsp+D0h] [rbp-38h]
  GpRecolor *v80; // [rsp+D8h] [rbp-30h]
  __int64 v81; // [rsp+E4h] [rbp-24h]
  int v82; // [rsp+ECh] [rbp-1Ch]
  _BYTE v83[384]; // [rsp+F8h] [rbp-10h] BYREF

  v11 = a6;
  v12 = a8;
  v13 = 1;
  lpBits = a7;
  v69 = a4;
  v72 = a2;
  v14 = a9 & 0xFF0000;
  if ( (a9 & 0xFF0000) == 0 || v14 == 16711680 )
  {
    LODWORD(v68) = v14 != 0 ? -1 : -16777216;
    GpSolidFill::GpSolidFill((GpSolidFill *)v83, (const struct GpRuntime::GpColor *)&v68);
    v65 = *((_QWORD *)this + 299);
    v64 = v83;
    goto LABEL_80;
  }
  if ( ((a9 ^ (4 * a9)) & 0xCCCC0000) == 0 )
  {
    v66 = 15728640;
    if ( ((a9 ^ (16 * a9)) & 0xF00000) == 0 )
      return v13;
    v57 = (char *)this + 2520;
    v58 = *(_QWORD *)v57;
    if ( !*(_QWORD *)v57 || !*(_QWORD *)(v58 + 8) )
      return v13;
    switch ( v14 )
    {
      case 0x5A0000u:
        v59 = *((_QWORD *)this + 535);
        if ( v59 && *(_QWORD *)(v59 + 8) )
        {
          v69 = 0;
        }
        else
        {
          if ( !*(_QWORD *)(v58 + 8) )
            return v13;
          v60 = ((__int64 (*)(void))CSmartGpObject::operator GpBrush *)();
          v61 = (struct GpObject *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 64LL))(v60);
          CSmartGpObject::CSmartGpObject((CSmartGpObject *)&v69, v61);
        }
        CSmartGpObject::operator=((char *)this + 4280, &v69);
        CSmartGpObject::Release((CSmartGpObject *)&v69);
        return v13;
      case 0xA00000u:
        v62 = *((_QWORD *)this + 535);
        if ( v62 && *(_QWORD *)(v62 + 8) )
        {
          v67 = (struct GpBrush *)CSmartGpObject::operator GpBrush *(v57, 15728640, a8);
          if ( !(unsigned int)CEmfPlusEnumState::GetAlphaBrush(this, v67) )
            return v13;
          v57 = (char *)this + 4280;
          goto LABEL_79;
        }
        break;
      case 0xF00000u:
LABEL_79:
        v63 = *((_QWORD *)this + 299);
        v64 = (_BYTE *)CSmartGpObject::operator GpBrush *(v57, v66, v12);
        v65 = v63;
LABEL_80:
        GpGraphics::FillRects(v65, v64, a3, 1);
        return v13;
    }
    *((_DWORD *)this + 1075) |= 1u;
    goto LABEL_79;
  }
  BmpInfoFromPalette = CEmfPlusEnumState::GetBmpInfoFromPalette(this, a6, a8);
  if ( v14 != 13369344 && ((a9 ^ (2 * a9)) & 0xAA0000) == 0 )
  {
    v25 = a6;
    ppvBits = 0;
    if ( BmpInfoFromPalette )
      v25 = BmpInfoFromPalette;
    h = CreateDIBSection(0, v25, 0, &ppvBits, 0, 0);
    if ( h )
    {
      CompatibleDC = CreateCompatibleDC(0);
      v27 = CompatibleDC;
      if ( CompatibleDC )
      {
        if ( SelectObject(CompatibleDC, h) )
        {
          if ( ((a9 ^ (16 * a9)) & 0xF00000) != 0 )
          {
            v28 = GpGraphics::GetFromHdc(v27, 0);
            v68 = v28;
            if ( v28 )
            {
              GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)v76, (struct GpGraphics *)((char *)v28 + 16));
              v31 = CSmartGpObject::operator GpBrush *((char *)this + 2520, v29, v30);
              GpGraphics::FillRect(v68, v31);
              _InterlockedDecrement(v77);
              GpGraphics::`scalar deleting destructor'(v68, v32);
            }
          }
          lpbmi = a6;
          if ( BmpInfoFromPalette )
            lpbmi = BmpInfoFromPalette;
          StretchDIBits(
            v27,
            0,
            0,
            a6->bmiHeader.biWidth,
            a6->bmiHeader.biHeight,
            0,
            0,
            a6->bmiHeader.biWidth,
            a6->bmiHeader.biHeight,
            lpBits,
            lpbmi,
            0,
            a9 & 0xA00000 | (16 * (a9 & 0x50000)) | ((a9 & 0xA00000 | (16 * (a9 & 0x50000))) >> 4));
          DeleteDC(v27);
          v34 = (GpBitmap *)GpMallocEx(1504, 0);
          if ( v34 )
          {
            if ( BmpInfoFromPalette )
              v11 = BmpInfoFromPalette;
            v36 = GpBitmap::GpBitmap(v34, v11, ppvBits, v35);
            v37 = v36;
            if ( v36 )
            {
              if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v36 + 8LL))(v36) )
              {
                GpImageAttributes::GpImageAttributes((GpImageAttributes *)v78);
                v38 = *((_QWORD *)this + 299);
                v81 = 3;
                v82 = 0;
                v79 = 0;
                GpGraphics::DrawImage(v38, v37, v69);
                GpImageAttributes::~GpImageAttributes((GpImageAttributes *)v78);
              }
              (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v37 + 56LL))(v37);
            }
          }
        }
        else
        {
          DeleteDC(v27);
        }
      }
      DeleteObject(h);
    }
    return v13;
  }
  v16 = (GpBitmap *)GpMallocEx(1504, 0);
  if ( !v16 )
    return 0;
  v20 = a6;
  if ( BmpInfoFromPalette )
    v20 = BmpInfoFromPalette;
  v21 = GpBitmap::GpBitmap(v16, v20, lpBits, v17);
  v22 = v21;
  if ( !v21 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v21 + 8LL))(v21) )
  {
    v13 = 0;
LABEL_23:
    (*(void (__fastcall **)(struct GpBitmap *))(*(_QWORD *)v22 + 56LL))(v22);
    return v13;
  }
  if ( v14 != 15597568 )
  {
    if ( v14 != 8912896 )
    {
LABEL_18:
      if ( !*((_QWORD *)this + 527) )
      {
LABEL_19:
        if ( ((a9 ^ (2 * a9)) & 0xAA0000) != 0 )
          *((_DWORD *)this + 1075) |= 1u;
        GpImageAttributes::GpImageAttributes((GpImageAttributes *)v78);
        v23 = *((_QWORD *)this + 299);
        v81 = 3;
        v82 = 0;
        v79 = 0;
        GpGraphics::DrawImage(v23, v22, v69);
        v78[0] = &GpImageAttributes::`vftable';
        if ( v80 )
          GpRecolor::`scalar deleting destructor'(v80, v24);
        goto LABEL_23;
      }
LABEL_91:
      if ( v14 == 8912896 )
      {
        if ( (*((_DWORD *)this + 1056) & 0xFF0000) != 0xEE0000 )
        {
LABEL_96:
          CEmfPlusEnumState::DrawMaskBmp(this);
          goto LABEL_19;
        }
      }
      else if ( v14 != 6684672 || (*((_DWORD *)this + 1056) & 0xFF0000) != 0x880000 )
      {
        goto LABEL_96;
      }
      v39 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v40 = (__m128)*((unsigned int *)this + 1066);
      v40.m128_f32[0] = v40.m128_f32[0] + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        v41 = (int)_mm_round_ss(v40, v40, 9).m128_f32[0];
      else
        v41 = (int)floor(v40.m128_f32[0]);
      v42 = (__m128)*((unsigned int *)this + 1065);
      LODWORD(v68) = v41;
      v42.m128_f32[0] = v42.m128_f32[0] + 0.5;
      if ( v39 )
        v43 = (int)_mm_round_ss(v42, v42, 9).m128_f32[0];
      else
        v43 = (int)floor(v42.m128_f32[0]);
      v44 = (__m128)*((unsigned int *)this + 1064);
      LODWORD(ppvBits) = v43;
      v44.m128_f32[0] = v44.m128_f32[0] + 0.5;
      if ( v39 )
        v45 = (int)_mm_round_ss(v44, v44, 9).m128_f32[0];
      else
        v45 = (int)floor(v44.m128_f32[0]);
      v46 = (__m128)*((unsigned int *)this + 1063);
      LODWORD(h) = v45;
      v46.m128_f32[0] = v46.m128_f32[0] + 0.5;
      if ( v39 )
        v47 = (int)_mm_round_ss(v46, v46, 9).m128_f32[0];
      else
        v47 = (int)floor(v46.m128_f32[0]);
      lpBits = (void *)__PAIR64__((unsigned int)h, v47);
      v74 = (int)ppvBits;
      v75 = (int)v68;
      v48 = v72;
      v49 = (__m128)*((unsigned int *)v72 + 3);
      v49.m128_f32[0] = v49.m128_f32[0] + 0.5;
      if ( v39 )
      {
        LODWORD(h) = (int)_mm_round_ss(v49, v49, 9).m128_f32[0];
      }
      else
      {
        LODWORD(h) = (int)floor(v49.m128_f32[0]);
        v48 = v72;
      }
      v50 = (__m128)*((unsigned int *)v48 + 2);
      v50.m128_f32[0] = v50.m128_f32[0] + 0.5;
      if ( v39 )
      {
        LODWORD(ppvBits) = (int)_mm_round_ss(v50, v50, 9).m128_f32[0];
      }
      else
      {
        LODWORD(ppvBits) = (int)floor(v50.m128_f32[0]);
        v48 = v72;
      }
      v51 = (__m128)*((unsigned int *)v48 + 1);
      v51.m128_f32[0] = v51.m128_f32[0] + 0.5;
      if ( v39 )
      {
        v52 = _mm_round_ss(v51, v51, 9).m128_f32[0];
        v53 = (CEmfPlusEnumState *)(unsigned int)(int)v52;
        LODWORD(v68) = (int)v52;
      }
      else
      {
        LODWORD(v68) = (int)floor(v51.m128_f32[0]);
        v48 = v72;
      }
      v54 = (__m128)*(unsigned int *)v48;
      v54.m128_f32[0] = v54.m128_f32[0] + 0.5;
      if ( v39 )
        v55 = (int)_mm_round_ss(v54, v54, 9).m128_f32[0];
      else
        v55 = (int)floor(v54.m128_f32[0]);
      v56 = (struct GpBitmap *)*((_QWORD *)this + 527);
      v76[0] = v55;
      v76[1] = (_DWORD)v68;
      v77 = (volatile signed __int32 *)__PAIR64__((unsigned int)h, (unsigned int)ppvBits);
      CEmfPlusEnumState::MergeImageAndMask(
        v53,
        v22,
        v56,
        (const struct GpRuntime::GpRect *)v76,
        (const struct GpRuntime::GpRect *)&lpBits,
        v14 == 6684672);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 527) + 56LL))(*((_QWORD *)this + 527));
      *((_QWORD *)this + 527) = 0;
      goto LABEL_19;
    }
    if ( *((_QWORD *)this + 527) )
      goto LABEL_91;
  }
  if ( a6->bmiHeader.biBitCount != 1 )
    goto LABEL_18;
  if ( *((_QWORD *)this + 527) )
    CEmfPlusEnumState::DrawMaskBmp(this);
  v18 = v69;
  *(_OWORD *)((char *)this + 4252) = *(_OWORD *)v72;
  *(_QWORD *)((char *)this + 4228) = *(_QWORD *)v18;
  *(_QWORD *)((char *)this + 4236) = *((_QWORD *)v18 + 1);
  *(_QWORD *)((char *)this + 4244) = *((_QWORD *)v18 + 2);
  GpMatrix::Transform((CEmfPlusEnumState *)((char *)this + 2752), (CEmfPlusEnumState *)((char *)this + 4228), 3);
  *((_DWORD *)this + 1056) = a9;
  *((_QWORD *)this + 527) = v22;
  return v13;
}

```

## disassembly

```asm
0x180044e98  mov     rax, rsp
0x180044e9b  mov     [rax+20h], rbx
0x180044e9f  push    rbp
0x180044ea0  push    rsi
0x180044ea1  push    rdi
0x180044ea2  push    r12
0x180044ea4  push    r13
0x180044ea6  push    r14
0x180044ea8  push    r15
0x180044eaa  lea     rbp, [rax-1D8h]
0x180044eb1  sub     rsp, 2A0h
0x180044eb8  movaps  xmmword ptr [rax-48h], xmm6
0x180044ebc  movaps  xmmword ptr [rax-58h], xmm7
0x180044ec0  mov     rax, cs:__security_cookie
0x180044ec7  xor     rax, rsp
0x180044eca  mov     [rbp+1D0h+var_60], rax
0x180044ed1  mov     rax, [rbp+1D0h+arg_30]
0x180044ed8  mov     r13, r8
0x180044edb  mov     r14d, [rbp+1D0h+arg_40]
0x180044ee2  mov     rdi, rcx
0x180044ee5  mov     r15, [rbp+1D0h+arg_28]
0x180044eec  mov     esi, r14d
0x180044eef  mov     r8d, [rbp+1D0h+arg_38]; unsigned int
0x180044ef6  mov     r12d, 1
0x180044efc  mov     [rbp+1D0h+var_238], rax
0x180044f00  mov     eax, 0FF0000h
0x180044f05  mov     [rsp+2D0h+var_258], r9
0x180044f0a  mov     [rbp+1D0h+var_240], rdx
0x180044f0e  and     esi, eax
0x180044f10  jz      loc_180045716
0x180044f16  cmp     esi, eax
0x180044f18  jz      loc_180045716
0x180044f1e  lea     eax, ds:0[r14*4]
0x180044f26  xor     eax, r14d
0x180044f29  test    eax, 0CCCC0000h
0x180044f2e  jz      loc_180045631
0x180044f34  mov     rdx, r15; struct tagBITMAPINFO *
0x180044f37  call    ?GetBmpInfoFromPalette@CEmfPlusEnumState@@IEAAPEAUtagBITMAPINFO@@PEBU2@I@Z; CEmfPlusEnumState::GetBmpInfoFromPalette(tagBITMAPINFO const *,uint)
0x180044f3c  mov     r13, rax
0x180044f3f  cmp     esi, 0CC0000h
0x180044f45  jnz     loc_1800450FC
0x180044f4b  xor     edx, edx
0x180044f4d  mov     ecx, 5E0h
0x180044f52  call    GpMallocEx
0x180044f57  xor     ebx, ebx
0x180044f59  test    rax, rax
0x180044f5c  jnz     loc_180045014
0x180044f62  mov     r12d, ebx
0x180044f65  jmp     short loc_180044FDC
0x180044f67  cmp     [r15+0Eh], r12w
0x180044f6c  jnz     loc_180045067
0x180044f72  cmp     [rdi+1078h], rbx
0x180044f79  jnz     loc_1800456CD
0x180044f7f  mov     rax, [rbp+1D0h+var_240]
0x180044f83  lea     rdx, [rdi+1084h]; struct PointF *
0x180044f8a  lea     rcx, [rdi+0AC0h]; this
0x180044f91  mov     r8d, 3; int
0x180044f97  movups  xmm0, xmmword ptr [rax]
0x180044f9a  mov     rax, [rsp+2D0h+var_258]
0x180044f9f  movdqu  xmmword ptr [rdi+109Ch], xmm0
0x180044fa7  movsd   xmm1, qword ptr [rax]
0x180044fab  movsd   qword ptr [rdx], xmm1
0x180044faf  movsd   xmm0, qword ptr [rax+8]
0x180044fb4  movsd   qword ptr [rdi+108Ch], xmm0
0x180044fbc  movsd   xmm1, qword ptr [rax+10h]
0x180044fc1  movsd   qword ptr [rdi+1094h], xmm1
0x180044fc9  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x180044fce  mov     [rdi+1080h], r14d
0x180044fd5  mov     [rdi+1078h], r13
0x180044fdc  mov     eax, r12d
0x180044fdf  mov     rcx, [rbp+1D0h+var_60]
0x180044fe6  xor     rcx, rsp; StackCookie
0x180044fe9  call    __security_check_cookie
0x180044fee  lea     r11, [rsp+2D0h+var_30]
0x180044ff6  mov     rbx, [r11+58h]
0x180044ffa  movaps  xmm6, xmmword ptr [r11-10h]
0x180044fff  movaps  xmm7, xmmword ptr [r11-20h]
0x180045004  mov     rsp, r11
0x180045007  pop     r15
0x180045009  pop     r14
0x18004500b  pop     r13
0x18004500d  pop     r12
0x18004500f  pop     rdi
0x180045010  pop     rsi
0x180045011  pop     rbp
0x180045012  retn
0x180045014  mov     r8, [rbp+1D0h+var_238]; void *
0x180045018  test    r13, r13
0x18004501b  mov     rdx, r15
0x18004501e  mov     rcx, rax; this
0x180045021  cmovnz  rdx, r13; struct tagBITMAPINFO *
0x180045025  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x18004502a  mov     r13, rax
0x18004502d  test    rax, rax
0x180045030  jz      loc_180044F62
0x180045036  mov     rax, [rax]
0x180045039  mov     rcx, r13
0x18004503c  mov     rax, [rax+8]
0x180045040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045045  test    eax, eax
0x180045047  jz      loc_18004570E
0x18004504d  mov     edx, 0EE0000h
0x180045052  mov     ecx, 880000h
0x180045057  cmp     esi, edx
0x180045059  jz      loc_180044F67
0x18004505f  cmp     esi, ecx
0x180045061  jz      loc_1800456A7
0x180045067  cmp     [rdi+1078h], rbx
0x18004506e  jnz     loc_1800456B4
0x180045074  lea     eax, [r14+r14]
0x180045078  xor     eax, r14d
0x18004507b  test    eax, 0AA0000h
0x180045080  jnz     loc_180045702
0x180045086  lea     rcx, [rbp+1D0h+var_218]; this
0x18004508a  call    ??0GpImageAttributes@@QEAA@XZ; GpImageAttributes::GpImageAttributes(void)
0x18004508f  mov     r8, [rsp+2D0h+var_258]
0x180045094  lea     rax, [rbp+1D0h+var_218]
0x180045098  mov     rcx, [rdi+958h]
0x18004509f  mov     r9d, 3
0x1800450a5  mov     qword ptr [rsp+2D0h+ySrc], rax
0x1800450aa  mov     rdx, r13
0x1800450ad  mov     rax, [rbp+1D0h+var_240]
0x1800450b1  mov     [rsp+2D0h+offset], 2
0x1800450b9  mov     [rsp+2D0h+hSection], rax
0x1800450be  mov     [rbp+1D0h+var_1F4], r9
0x1800450c2  mov     [rbp+1D0h+var_1EC], ebx
0x1800450c5  mov     [rbp+1D0h+var_208], rbx
0x1800450c9  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@PEBVPointF@@HAEBVRectF@@W4Unit@@PEBVGpImageAttributes@@@Z; GpGraphics::DrawImage(GpImage *,PointF const *,int,RectF const &,Unit,GpImageAttributes const *)
0x1800450ce  mov     rcx, [rbp+1D0h+var_200]; this
0x1800450d2  lea     rax, ??_7GpImageAttributes@@6B@; const GpImageAttributes::`vftable'
0x1800450d9  mov     [rbp+1D0h+var_218], rax
0x1800450dd  test    rcx, rcx
0x1800450e0  jz      short loc_1800450E7
0x1800450e2  call    ??_GGpRecolor@@QEAAPEAXI@Z; GpRecolor::`scalar deleting destructor'(uint)
0x1800450e7  mov     rax, [r13+0]
0x1800450eb  mov     rcx, r13
0x1800450ee  mov     rax, [rax+38h]
0x1800450f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450f7  jmp     loc_180044FDC
0x1800450fc  lea     eax, [r14+r14]
0x180045100  xor     eax, r14d
0x180045103  test    eax, 0AA0000h
0x180045108  jnz     loc_180044F4B
0x18004510e  xor     ebx, ebx
0x180045110  lea     r9, [rbp+1D0h+ppvBits]; ppvBits
0x180045114  test    r13, r13
0x180045117  mov     [rsp+2D0h+offset], ebx; offset
0x18004511b  mov     rdx, r15
0x18004511e  mov     [rbp+1D0h+ppvBits], rbx
0x180045122  cmovnz  rdx, r13; pbmi
0x180045126  mov     [rsp+2D0h+hSection], rbx; hSection
0x18004512b  xor     r8d, r8d; usage
0x18004512e  xor     ecx, ecx; hdc
0x180045130  call    cs:__imp_CreateDIBSection
0x180045137  nop     dword ptr [rax+rax+00h]
0x18004513c  mov     [rbp+1D0h+h], rax
0x180045140  test    rax, rax
0x180045143  jz      loc_180044FDC
0x180045149  xor     ecx, ecx; hdc
0x18004514b  call    cs:__imp_CreateCompatibleDC
0x180045152  nop     dword ptr [rax+rax+00h]
0x180045157  mov     rsi, rax
0x18004515a  test    rax, rax
0x18004515d  jz      loc_180045692
0x180045163  mov     rdx, [rbp+1D0h+h]; h
0x180045167  mov     rcx, rax; hdc
0x18004516a  call    cs:__imp_SelectObject
0x180045171  nop     dword ptr [rax+rax+00h]
0x180045176  test    rax, rax
0x180045179  jz      loc_180045683
0x18004517f  mov     ecx, r14d
0x180045182  mov     edx, 0F00000h
0x180045187  shl     ecx, 4
0x18004518a  xor     ecx, r14d
0x18004518d  test    edx, ecx
0x18004518f  jz      short loc_180045200
0x180045191  xor     edx, edx; void *
0x180045193  mov     rcx, rsi; HDC
0x180045196  call    ?GetFromHdc@GpGraphics@@SAPEAV1@PEAUHDC__@@PEAX@Z; GpGraphics::GetFromHdc(HDC__ *,void *)
0x18004519b  mov     [rsp+2D0h+var_260], rax
0x1800451a0  test    rax, rax
0x1800451a3  jz      short loc_180045200
0x1800451a5  lea     rdx, [rax+10h]; struct GpRuntime::GpLockable *
0x1800451a9  lea     rcx, [rbp+1D0h+var_228]; this
0x1800451ad  call    ??0GpLock@GpRuntime@@QEAA@PEAVGpLockable@1@@Z; GpRuntime::GpLock::GpLock(GpRuntime::GpLockable *)
0x1800451b2  movd    xmm6, dword ptr [r15+8]
0x1800451b8  lea     rcx, [rdi+9D8h]
0x1800451bf  movd    xmm7, dword ptr [r15+4]
0x1800451c5  cvtdq2ps xmm6, xmm6
0x1800451c8  cvtdq2ps xmm7, xmm7
0x1800451cb  call    ??BCSmartGpObject@@QEBAPEAVGpBrush@@XZ; CSmartGpObject::operator GpBrush *(void)
0x1800451d0  mov     rcx, [rsp+2D0h+var_260]
0x1800451d5  mov     rdx, rax
0x1800451d8  movss   [rsp+2D0h+offset], xmm6
0x1800451de  xorps   xmm3, xmm3
0x1800451e1  xorps   xmm2, xmm2
0x1800451e4  movss   dword ptr [rsp+2D0h+hSection], xmm7
0x1800451ea  call    ?FillRect@GpGraphics@@QEAA?AW4Status@@PEAVGpBrush@@MMMM@Z; GpGraphics::FillRect(GpBrush *,float,float,float,float)
0x1800451ef  mov     rax, [rbp+1D0h+var_220]
0x1800451f3  mov     rcx, [rsp+2D0h+var_260]; this
0x1800451f8  lock dec dword ptr [rax]
0x1800451fb  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x180045200  mov     ecx, [r15+8]
0x180045204  mov     eax, r14d
0x180045207  mov     r8, [rbp+1D0h+var_238]
0x18004520b  and     eax, 50000h
0x180045210  mov     r9d, [r15+4]; DestWidth
0x180045214  and     r14d, 0A00000h
0x18004521b  shl     eax, 4
0x18004521e  or      eax, r14d
0x180045221  mov     edx, eax
0x180045223  shr     edx, 4
0x180045226  or      edx, eax
0x180045228  mov     rax, r15
0x18004522b  mov     [rsp+2D0h+rop], edx; rop
0x18004522f  test    r13, r13
0x180045232  mov     [rsp+2D0h+iUsage], ebx; iUsage
0x180045236  cmovnz  rax, r13
0x18004523a  xor     edx, edx; xDest
0x18004523c  mov     [rsp+2D0h+lpbmi], rax; lpbmi
0x180045241  mov     [rsp+2D0h+lpBits], r8; lpBits
0x180045246  xor     r8d, r8d; yDest
0x180045249  mov     [rsp+2D0h+SrcHeight], ecx; SrcHeight
0x18004524d  mov     [rsp+2D0h+SrcWidth], r9d; SrcWidth
0x180045252  mov     [rsp+2D0h+ySrc], ebx; ySrc
0x180045256  mov     [rsp+2D0h+offset], ebx; xSrc
0x18004525a  mov     dword ptr [rsp+2D0h+hSection], ecx; DestHeight
0x18004525e  mov     rcx, rsi; hdc
0x180045261  call    cs:__imp_StretchDIBits
0x180045268  nop     dword ptr [rax+rax+00h]
0x18004526d  mov     rcx, rsi; hdc
0x180045270  call    cs:__imp_DeleteDC
0x180045277  nop     dword ptr [rax+rax+00h]
0x18004527c  xor     edx, edx
0x18004527e  mov     ecx, 5E0h
0x180045283  call    GpMallocEx
0x180045288  test    rax, rax
0x18004528b  jz      loc_180045692
0x180045291  mov     r8, [rbp+1D0h+ppvBits]; void *
0x180045295  test    r13, r13
0x180045298  mov     rcx, rax; this
0x18004529b  cmovnz  r15, r13
0x18004529f  mov     rdx, r15; struct tagBITMAPINFO *
0x1800452a2  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x1800452a7  mov     rsi, rax
0x1800452aa  test    rax, rax
0x1800452ad  jz      loc_180045692
0x1800452b3  mov     rax, [rax]
0x1800452b6  mov     rcx, rsi
0x1800452b9  mov     rax, [rax+8]
0x1800452bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452c2  test    eax, eax
0x1800452c4  jz      short loc_180045317
0x1800452c6  lea     rcx, [rbp+1D0h+var_218]; this
0x1800452ca  call    ??0GpImageAttributes@@QEAA@XZ; GpImageAttributes::GpImageAttributes(void)
0x1800452cf  mov     r8, [rsp+2D0h+var_258]
0x1800452d4  lea     rax, [rbp+1D0h+var_218]
0x1800452d8  mov     rcx, [rdi+958h]
0x1800452df  mov     r9d, 3
0x1800452e5  mov     qword ptr [rsp+2D0h+ySrc], rax
0x1800452ea  mov     rdx, rsi
0x1800452ed  mov     rax, [rbp+1D0h+var_240]
0x1800452f1  mov     [rsp+2D0h+offset], 2
0x1800452f9  mov     [rsp+2D0h+hSection], rax
0x1800452fe  mov     [rbp+1D0h+var_1F4], r9
0x180045302  mov     [rbp+1D0h+var_1EC], ebx
0x180045305  mov     [rbp+1D0h+var_208], rbx
0x180045309  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@PEBVPointF@@HAEBVRectF@@W4Unit@@PEBVGpImageAttributes@@@Z; GpGraphics::DrawImage(GpImage *,PointF const *,int,RectF const &,Unit,GpImageAttributes const *)
0x18004530e  lea     rcx, [rbp+1D0h+var_218]; this
0x180045312  call    ??1GpImageAttributes@@UEAA@XZ; GpImageAttributes::~GpImageAttributes(void)
0x180045317  mov     rax, [rsi]
0x18004531a  mov     rcx, rsi
0x18004531d  mov     rax, [rax+38h]
0x180045321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045326  jmp     loc_180045692
0x18004532b  mov     r15b, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180045332  movss   xmm1, dword ptr [rdi+10A8h]
0x18004533a  movss   xmm6, cs:__real@3f000000
0x180045342  addss   xmm1, xmm6
0x180045346  test    r15b, r15b
0x180045349  jz      loc_1800454CB
0x18004534f  movaps  xmm0, xmm1
0x180045352  roundss xmm0, xmm0, 9
0x180045358  cvttss2si eax, xmm0
0x18004535c  movss   xmm1, dword ptr [rdi+10A4h]
0x180045364  mov     dword ptr [rsp+2D0h+var_260], eax
0x180045368  addss   xmm1, xmm6
0x18004536c  test    r15b, r15b
0x18004536f  jz      loc_1800454DC
0x180045375  movaps  xmm0, xmm1
0x180045378  roundss xmm0, xmm0, 9
0x18004537e  cvttss2si eax, xmm0
0x180045382  movss   xmm1, dword ptr [rdi+10A0h]
0x18004538a  mov     dword ptr [rbp+1D0h+ppvBits], eax
0x18004538d  addss   xmm1, xmm6
0x180045391  test    r15b, r15b
0x180045394  jz      loc_1800454ED
0x18004539a  movaps  xmm0, xmm1
0x18004539d  roundss xmm0, xmm0, 9
0x1800453a3  cvttss2si eax, xmm0
  ... truncated ...
```

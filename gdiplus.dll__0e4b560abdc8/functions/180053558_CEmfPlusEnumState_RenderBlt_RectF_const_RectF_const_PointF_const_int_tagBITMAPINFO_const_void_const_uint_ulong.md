# CEmfPlusEnumState::RenderBlt(RectF const &,RectF const &,PointF const *,int,tagBITMAPINFO const *,void * const,uint,ulong)

- ea: `0x180053558`
- end: `0x180053d7a`
- name: `?RenderBlt@CEmfPlusEnumState@@IEAAHAEBVRectF@@0PEBVPointF@@HPEBUtagBITMAPINFO@@QEAXIK@Z`
- size: `2082`
- prototype: `__int64 __fastcall(CEmfPlusEnumState *__hidden this, const struct RectF *, const struct RectF *, const struct PointF *, int, const struct tagBITMAPINFO *, void *const, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800532b0`
- `0x180118a2c`
- `0x18011c814`

## callees

- `0x18000390c`
- `0x180003b38`
- `0x18000e6d0`
- `0x180040ee0`
- `0x18004ab14`
- `0x180053558`
- `0x180060528`
- `0x180060564`
- `0x180060ab0`
- `0x180063298`
- `0x1800634b4`
- `0x180064e70`
- `0x18006f7c4`
- `0x180071a04`
- `0x1800a370c`
- `0x1800cfd64`
- `0x1800e1f38`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea080`
- `0x180119338`
- `0x18011a104`
- `0x18011a7fc`
- `0x180175010`

## import_xrefs

- `GDI32!StretchDIBits` at `0x180053865`
- `GDI32!StretchDIBits` at `0x180053865`
- `GDI32!CreateDIBSection` at `0x18005373c`
- `GDI32!CreateDIBSection` at `0x18005373c`
- `GDI32!DeleteDC` at `0x180053874`
- `GDI32!DeleteDC` at `0x180053930`
- `GDI32!DeleteDC` at `0x180053874`
- `GDI32!DeleteDC` at `0x180053930`
- `GDI32!SelectObject` at `0x180053776`
- `GDI32!SelectObject` at `0x180053776`
- `GDI32!CreateCompatibleDC` at `0x180053757`
- `GDI32!CreateCompatibleDC` at `0x180053757`
- `GDI32!DeleteObject` at `0x180053940`
- `GDI32!DeleteObject` at `0x180053940`

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
  struct tagBITMAPINFO *v11; // r13
  __int64 v12; // r8
  unsigned int v13; // r12d
  unsigned int v14; // r14d
  char *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  struct GpObject *v19; // rax
  __int64 v20; // rax
  struct GpBrush *v21; // rax
  __int64 v22; // rbx
  _BYTE *v23; // rdx
  __int64 v24; // rcx
  struct tagBITMAPINFO *BmpInfoFromPalette; // r15
  const BITMAPINFO *v26; // rdx
  HDC CompatibleDC; // rax
  HDC v28; // r14
  struct GpGraphics *v29; // rax
  __int64 v30; // rax
  GpGraphics *v31; // rcx
  unsigned int v32; // edx
  const BITMAPINFO *lpbmi; // rax
  GpBitmap *v34; // rax
  GpBitmap *v35; // rax
  GpBitmap *v36; // rsi
  __int64 v37; // rcx
  GpBitmap *v38; // rax
  struct tagBITMAPINFO *v39; // rdx
  GpBitmap *v40; // rax
  struct GpBitmap *v41; // r15
  const struct PointF *v42; // rax
  __int64 v43; // rcx
  bool v44; // r14
  __m128 v45; // xmm0
  int v46; // eax
  __m128 v47; // xmm0
  int v48; // eax
  __m128 v49; // xmm0
  int v50; // r13d
  __m128 v51; // xmm0
  int v52; // eax
  const struct RectF *v53; // r13
  __m128 v54; // xmm0
  int v55; // eax
  __m128 v56; // xmm0
  int v57; // eax
  __m128 v58; // xmm0
  int v59; // eax
  __m128 v60; // xmm0
  int v61; // eax
  struct GpBitmap *v62; // r8
  const struct RectF *v64; // [rsp+78h] [rbp-90h] BYREF
  const struct PointF *v65; // [rsp+80h] [rbp-88h] BYREF
  void *ppvBits; // [rsp+88h] [rbp-80h] BYREF
  GpGraphics *v67; // [rsp+90h] [rbp-78h]
  HGDIOBJ h; // [rsp+98h] [rbp-70h] BYREF
  int v69; // [rsp+A0h] [rbp-68h]
  int v70; // [rsp+A4h] [rbp-64h]
  void *lpBits; // [rsp+A8h] [rbp-60h] BYREF
  int v72; // [rsp+B0h] [rbp-58h]
  int v73; // [rsp+B4h] [rbp-54h]
  _BYTE v74[16]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v75; // [rsp+C8h] [rbp-40h]
  __int64 v76; // [rsp+DCh] [rbp-2Ch]
  int v77; // [rsp+E4h] [rbp-24h]
  _BYTE v78[8]; // [rsp+F0h] [rbp-18h] BYREF
  volatile signed __int32 *v79; // [rsp+F8h] [rbp-10h]
  _BYTE v80[384]; // [rsp+108h] [rbp+0h] BYREF

  v11 = a6;
  v12 = a8;
  v13 = 1;
  lpBits = a7;
  v65 = a4;
  v64 = a2;
  v14 = a9 & 0xFF0000;
  if ( (a9 & 0xFF0000) == 0 || v14 == 16711680 )
  {
    LODWORD(v64) = v14 != 0 ? -1 : -16777216;
    GpSolidFill::GpSolidFill((GpSolidFill *)v80, (const struct GpRuntime::GpColor *)&v64);
    v24 = *((_QWORD *)this + 299);
    v23 = v80;
    goto LABEL_93;
  }
  if ( ((a9 ^ (4 * a9)) & 0xCCCC0000) != 0 )
  {
    BmpInfoFromPalette = CEmfPlusEnumState::GetBmpInfoFromPalette(this, a6, a8);
    if ( v14 != 13369344 && ((a9 ^ (2 * a9)) & 0xAA0000) == 0 )
    {
      v26 = a6;
      ppvBits = 0;
      if ( BmpInfoFromPalette )
        v26 = BmpInfoFromPalette;
      h = CreateDIBSection(0, v26, 0, &ppvBits, 0, 0);
      if ( h )
      {
        CompatibleDC = CreateCompatibleDC(0);
        v28 = CompatibleDC;
        if ( CompatibleDC )
        {
          if ( SelectObject(CompatibleDC, h) )
          {
            if ( ((a9 ^ (16 * a9)) & 0xF00000) != 0 )
            {
              v29 = GpGraphics::GetFromHdc(v28, 0);
              v67 = v29;
              if ( v29 )
              {
                GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)v78, (struct GpGraphics *)((char *)v29 + 16));
                v30 = CSmartGpObject::operator GpBrush *((char *)this + 2520);
                GpGraphics::FillRect(v67, v30);
                v31 = v67;
                _InterlockedDecrement(v79);
                GpGraphics::`scalar deleting destructor'(v31, v32);
              }
            }
            lpbmi = a6;
            if ( BmpInfoFromPalette )
              lpbmi = BmpInfoFromPalette;
            StretchDIBits(
              v28,
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
            DeleteDC(v28);
            v34 = (GpBitmap *)GpMallocEx(1504, 0);
            if ( v34 )
            {
              if ( BmpInfoFromPalette )
                v11 = BmpInfoFromPalette;
              v35 = GpBitmap::GpBitmap(v34, v11, ppvBits);
              v36 = v35;
              if ( v35 )
              {
                if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v35 + 8LL))(v35) )
                {
                  GpImageAttributes::GpImageAttributes((GpImageAttributes *)v74);
                  v37 = *((_QWORD *)this + 299);
                  v76 = 3;
                  v77 = 0;
                  v75 = 0;
                  GpGraphics::DrawImage(v37, v36, v65);
                  GpImageAttributes::~GpImageAttributes((GpImageAttributes *)v74);
                }
                (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v36 + 56LL))(v36);
              }
            }
          }
          else
          {
            DeleteDC(v28);
          }
        }
        DeleteObject(h);
      }
      return v13;
    }
    v38 = (GpBitmap *)GpMallocEx(1504, 0);
    if ( !v38 )
      return 0;
    v39 = a6;
    if ( BmpInfoFromPalette )
      v39 = BmpInfoFromPalette;
    v40 = GpBitmap::GpBitmap(v38, v39, lpBits);
    v41 = v40;
    if ( !v40 )
      return 0;
    if ( !(*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v40 + 8LL))(v40) )
    {
      v13 = 0;
LABEL_90:
      (*(void (__fastcall **)(struct GpBitmap *))(*(_QWORD *)v41 + 56LL))(v41);
      return v13;
    }
    if ( v14 != 15597568 )
    {
      if ( v14 != 8912896 )
        goto LABEL_55;
      if ( *((_QWORD *)this + 527) )
        goto LABEL_56;
    }
    if ( a6->bmiHeader.biBitCount == 1 )
    {
      if ( *((_QWORD *)this + 527) )
        CEmfPlusEnumState::DrawMaskBmp(this);
      v42 = v65;
      *(_OWORD *)((char *)this + 4252) = *(_OWORD *)v64;
      *(_QWORD *)((char *)this + 4228) = *(_QWORD *)v42;
      *(_QWORD *)((char *)this + 4236) = *((_QWORD *)v42 + 1);
      *(_QWORD *)((char *)this + 4244) = *((_QWORD *)v42 + 2);
      GpMatrix::Transform((CEmfPlusEnumState *)((char *)this + 2752), (CEmfPlusEnumState *)((char *)this + 4228), 3);
      *((_DWORD *)this + 1056) = a9;
      *((_QWORD *)this + 527) = v41;
      return v13;
    }
LABEL_55:
    if ( !*((_QWORD *)this + 527) )
    {
LABEL_59:
      if ( ((a9 ^ (2 * a9)) & 0xAA0000) != 0 )
        *((_DWORD *)this + 1075) |= 1u;
      GpImageAttributes::GpImageAttributes((GpImageAttributes *)v74);
      v43 = *((_QWORD *)this + 299);
      v76 = 3;
      v77 = 0;
      v75 = 0;
      GpGraphics::DrawImage(v43, v41, v65);
      GpImageAttributes::~GpImageAttributes((GpImageAttributes *)v74);
      goto LABEL_90;
    }
LABEL_56:
    if ( (a9 & 0xFF0000) == 0x880000 )
    {
      if ( (*((_DWORD *)this + 1056) & 0xFF0000) != 0xEE0000 )
      {
LABEL_58:
        CEmfPlusEnumState::DrawMaskBmp(this);
        goto LABEL_59;
      }
    }
    else if ( (a9 & 0xFF0000) != 0x660000 || (*((_DWORD *)this + 1056) & 0xFF0000) != 0x880000 )
    {
      goto LABEL_58;
    }
    v44 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v45 = (__m128)*((unsigned int *)this + 1066);
    v45.m128_f32[0] = v45.m128_f32[0] + 0.5;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
      v46 = (int)_mm_round_ss(v45, v45, 9).m128_f32[0];
    else
      v46 = (int)floor(v45.m128_f32[0]);
    v47 = (__m128)*((unsigned int *)this + 1065);
    LODWORD(v67) = v46;
    v47.m128_f32[0] = v47.m128_f32[0] + 0.5;
    if ( v44 )
      v48 = (int)_mm_round_ss(v47, v47, 9).m128_f32[0];
    else
      v48 = (int)floor(v47.m128_f32[0]);
    v49 = (__m128)*((unsigned int *)this + 1064);
    LODWORD(ppvBits) = v48;
    v49.m128_f32[0] = v49.m128_f32[0] + 0.5;
    if ( v44 )
      v50 = (int)_mm_round_ss(v49, v49, 9).m128_f32[0];
    else
      v50 = (int)floor(v49.m128_f32[0]);
    v51 = (__m128)*((unsigned int *)this + 1063);
    v51.m128_f32[0] = v51.m128_f32[0] + 0.5;
    if ( v44 )
      v52 = (int)_mm_round_ss(v51, v51, 9).m128_f32[0];
    else
      v52 = (int)floor(v51.m128_f32[0]);
    lpBits = (void *)__PAIR64__(v50, v52);
    v53 = v64;
    v72 = (int)ppvBits;
    v73 = (int)v67;
    v54 = (__m128)*((unsigned int *)v64 + 3);
    v54.m128_f32[0] = v54.m128_f32[0] + 0.5;
    if ( v44 )
      v55 = (int)_mm_round_ss(v54, v54, 9).m128_f32[0];
    else
      v55 = (int)floor(v54.m128_f32[0]);
    v56 = (__m128)*((unsigned int *)v64 + 2);
    LODWORD(v64) = v55;
    v56.m128_f32[0] = v56.m128_f32[0] + 0.5;
    if ( v44 )
      v57 = (int)_mm_round_ss(v56, v56, 9).m128_f32[0];
    else
      v57 = (int)floor(v56.m128_f32[0]);
    v58 = (__m128)*((unsigned int *)v53 + 1);
    LODWORD(ppvBits) = v57;
    v58.m128_f32[0] = v58.m128_f32[0] + 0.5;
    if ( v44 )
      v59 = (int)_mm_round_ss(v58, v58, 9).m128_f32[0];
    else
      v59 = (int)floor(v58.m128_f32[0]);
    v60 = (__m128)*(unsigned int *)v53;
    LODWORD(v67) = v59;
    v60.m128_f32[0] = v60.m128_f32[0] + 0.5;
    if ( v44 )
      v61 = (int)_mm_round_ss(v60, v60, 9).m128_f32[0];
    else
      v61 = (int)floor(v60.m128_f32[0]);
    v62 = (struct GpBitmap *)*((_QWORD *)this + 527);
    h = (HGDIOBJ)__PAIR64__((unsigned int)v67, v61);
    v69 = (int)ppvBits;
    v70 = (int)v64;
    CEmfPlusEnumState::MergeImageAndMask(
      (CEmfPlusEnumState *)((a9 & 0xFF0000) == 6684672),
      v41,
      v62,
      (const struct GpRuntime::GpRect *)&h,
      (const struct GpRuntime::GpRect *)&lpBits,
      (a9 & 0xFF0000) == 6684672);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 527) + 56LL))(*((_QWORD *)this + 527));
    *((_QWORD *)this + 527) = 0;
    goto LABEL_59;
  }
  if ( ((a9 ^ (16 * a9)) & 0xF00000) == 0 )
    return v13;
  v15 = (char *)this + 2520;
  v16 = *(_QWORD *)v15;
  if ( !*(_QWORD *)v15 || !*(_QWORD *)(v16 + 8) )
    return v13;
  if ( v14 != 5898240 )
  {
    if ( v14 == 10485760 )
    {
      v20 = *((_QWORD *)this + 535);
      if ( v20 && *(_QWORD *)(v20 + 8) )
      {
        v21 = (struct GpBrush *)CSmartGpObject::operator GpBrush *(v15);
        if ( !(unsigned int)CEmfPlusEnumState::GetAlphaBrush(this, v21) )
          return v13;
        v15 = (char *)this + 4280;
        goto LABEL_19;
      }
    }
    else if ( v14 == 15728640 )
    {
LABEL_19:
      v22 = *((_QWORD *)this + 299);
      v23 = (_BYTE *)CSmartGpObject::operator GpBrush *(v15);
      v24 = v22;
LABEL_93:
      GpGraphics::FillRects(v24, v23, a3, 1);
      return v13;
    }
    *((_DWORD *)this + 1075) |= 1u;
    goto LABEL_19;
  }
  v17 = *((_QWORD *)this + 535);
  if ( v17 && *(_QWORD *)(v17 + 8) )
  {
    v65 = 0;
  }
  else
  {
    if ( !*(_QWORD *)(v16 + 8) )
      return v13;
    v18 = CSmartGpObject::operator GpBrush *(v15);
    v19 = (struct GpObject *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 64LL))(v18);
    CSmartGpObject::CSmartGpObject((CSmartGpObject *)&v65, v19);
  }
  CSmartGpObject::operator=((char *)this + 4280, &v65, v12);
  CSmartGpObject::Release((CSmartGpObject *)&v65);
  return v13;
}

```

## disassembly

```asm
0x180053558  mov     rax, rsp
0x18005355b  mov     [rax+20h], rbx
0x18005355f  push    rbp
0x180053560  push    rsi
0x180053561  push    rdi
0x180053562  push    r12
0x180053564  push    r13
0x180053566  push    r14
0x180053568  push    r15
0x18005356a  lea     rbp, [rax-1E8h]
0x180053571  sub     rsp, 2B0h
0x180053578  movaps  xmmword ptr [rax-48h], xmm6
0x18005357c  movaps  xmmword ptr [rax-58h], xmm7
0x180053580  mov     rax, cs:__security_cookie
0x180053587  xor     rax, rsp
0x18005358a  mov     [rbp+1E0h+var_60], rax
0x180053591  mov     rax, [rbp+1E0h+arg_30]
0x180053598  mov     r15, r8
0x18005359b  mov     esi, [rbp+1E0h+arg_40]
0x1800535a1  mov     rdi, rcx
0x1800535a4  mov     r13, [rbp+1E0h+arg_28]
0x1800535ab  mov     r14d, esi
0x1800535ae  mov     r8d, [rbp+1E0h+arg_38]; unsigned int
0x1800535b5  mov     r12d, 1
0x1800535bb  mov     [rbp+1E0h+var_240], rax
0x1800535bf  mov     eax, 0FF0000h
0x1800535c4  mov     [rsp+2E0h+var_268], r9
0x1800535c9  mov     [rsp+2E0h+var_270], rdx
0x1800535ce  and     r14d, eax
0x1800535d1  jz      loc_180053D09
0x1800535d7  cmp     r14d, eax
0x1800535da  jz      loc_180053D09
0x1800535e0  lea     eax, ds:0[rsi*4]
0x1800535e7  xor     eax, esi
0x1800535e9  test    eax, 0CCCC0000h
0x1800535ee  jnz     loc_1800536F2
0x1800535f4  mov     eax, esi
0x1800535f6  mov     edx, 0F00000h
0x1800535fb  shl     eax, 4
0x1800535fe  xor     eax, esi
0x180053600  test    edx, eax
0x180053602  jz      loc_180053D42
0x180053608  add     rcx, 9D8h
0x18005360f  xor     ebx, ebx
0x180053611  mov     rax, [rcx]
0x180053614  test    rax, rax
0x180053617  jz      loc_180053D42
0x18005361d  cmp     [rax+8], rbx
0x180053621  jz      loc_180053D42
0x180053627  cmp     r14d, 5A0000h
0x18005362e  jnz     short loc_180053694
0x180053630  mov     rdx, [rdi+10B8h]
0x180053637  test    rdx, rdx
0x18005363a  jz      short loc_180053667
0x18005363c  cmp     [rdx+8], rbx
0x180053640  jz      short loc_180053667
0x180053642  mov     [rsp+2E0h+var_268], rbx
0x180053647  lea     rdx, [rsp+2E0h+var_268]
0x18005364c  lea     rcx, [rdi+10B8h]
0x180053653  call    ??4CSmartGpObject@@QEAAAEBV0@AEBV0@@Z; CSmartGpObject::operator=(CSmartGpObject const &)
0x180053658  lea     rcx, [rsp+2E0h+var_268]; this
0x18005365d  call    ?Release@CSmartGpObject@@AEAAXXZ; CSmartGpObject::Release(void)
0x180053662  jmp     loc_180053D42
0x180053667  cmp     [rax+8], rbx
0x18005366b  jz      loc_180053D42
0x180053671  call    ??BCSmartGpObject@@QEBAPEAVGpBrush@@XZ; CSmartGpObject::operator GpBrush *(void)
0x180053676  mov     rcx, rax
0x180053679  mov     rax, [rax]
0x18005367c  mov     rax, [rax+40h]
0x180053680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053685  mov     rdx, rax; struct GpObject *
0x180053688  lea     rcx, [rsp+2E0h+var_268]; this
0x18005368d  call    ??0CSmartGpObject@@QEAA@PEAVGpObject@@@Z; CSmartGpObject::CSmartGpObject(GpObject *)
0x180053692  jmp     short loc_180053647
0x180053694  cmp     r14d, 0A00000h
0x18005369b  jnz     short loc_1800536E4
0x18005369d  lea     rsi, [rdi+10B8h]
0x1800536a4  mov     rax, [rsi]
0x1800536a7  test    rax, rax
0x1800536aa  jz      short loc_1800536E9
0x1800536ac  cmp     [rax+8], rbx
0x1800536b0  jz      short loc_1800536E9
0x1800536b2  call    ??BCSmartGpObject@@QEBAPEAVGpBrush@@XZ; CSmartGpObject::operator GpBrush *(void)
0x1800536b7  mov     rdx, rax; struct GpBrush *
0x1800536ba  mov     rcx, rdi; this
0x1800536bd  call    ?GetAlphaBrush@CEmfPlusEnumState@@IEAAHPEAVGpBrush@@@Z; CEmfPlusEnumState::GetAlphaBrush(GpBrush *)
0x1800536c2  test    eax, eax
0x1800536c4  jz      loc_180053D42
0x1800536ca  mov     rcx, rsi
0x1800536cd  mov     rbx, [rdi+958h]
0x1800536d4  call    ??BCSmartGpObject@@QEBAPEAVGpBrush@@XZ; CSmartGpObject::operator GpBrush *(void)
0x1800536d9  mov     rdx, rax
0x1800536dc  mov     rcx, rbx; this
0x1800536df  jmp     loc_180053D37
0x1800536e4  cmp     r14d, edx
0x1800536e7  jz      short loc_1800536CD
0x1800536e9  or      [rdi+10CCh], r12d
0x1800536f0  jmp     short loc_1800536CD
0x1800536f2  mov     rdx, r13; struct tagBITMAPINFO *
0x1800536f5  call    ?GetBmpInfoFromPalette@CEmfPlusEnumState@@IEAAPEAUtagBITMAPINFO@@PEBU2@I@Z; CEmfPlusEnumState::GetBmpInfoFromPalette(tagBITMAPINFO const *,uint)
0x1800536fa  mov     r15, rax
0x1800536fd  cmp     r14d, 0CC0000h
0x180053704  jz      loc_180053951
0x18005370a  lea     eax, [rsi+rsi]
0x18005370d  xor     eax, esi
0x18005370f  test    eax, 0AA0000h
0x180053714  jnz     loc_180053951
0x18005371a  xor     ebx, ebx
0x18005371c  lea     r9, [rbp+1E0h+ppvBits]; ppvBits
0x180053720  test    r15, r15
0x180053723  mov     [rsp+2E0h+offset], ebx; offset
0x180053727  mov     rdx, r13
0x18005372a  mov     [rbp+1E0h+ppvBits], rbx
0x18005372e  cmovnz  rdx, r15; pbmi
0x180053732  mov     [rsp+2E0h+hSection], rbx; hSection
0x180053737  xor     r8d, r8d; usage
0x18005373a  xor     ecx, ecx; hdc
0x18005373c  call    cs:__imp_CreateDIBSection
0x180053743  nop     dword ptr [rax+rax+00h]
0x180053748  mov     [rbp+1E0h+h], rax
0x18005374c  test    rax, rax
0x18005374f  jz      loc_180053D42
0x180053755  xor     ecx, ecx; hdc
0x180053757  call    cs:__imp_CreateCompatibleDC
0x18005375e  nop     dword ptr [rax+rax+00h]
0x180053763  mov     r14, rax
0x180053766  test    rax, rax
0x180053769  jz      loc_18005393C
0x18005376f  mov     rdx, [rbp+1E0h+h]; h
0x180053773  mov     rcx, rax; hdc
0x180053776  call    cs:__imp_SelectObject
0x18005377d  nop     dword ptr [rax+rax+00h]
0x180053782  test    rax, rax
0x180053785  jz      loc_18005392D
0x18005378b  mov     ecx, esi
0x18005378d  mov     edx, 0F00000h
0x180053792  shl     ecx, 4
0x180053795  xor     ecx, esi
0x180053797  test    edx, ecx
0x180053799  jz      short loc_180053807
0x18005379b  xor     edx, edx; void *
0x18005379d  mov     rcx, r14; hdc
0x1800537a0  call    ?GetFromHdc@GpGraphics@@SAPEAV1@PEAUHDC__@@PEAX@Z; GpGraphics::GetFromHdc(HDC__ *,void *)
0x1800537a5  mov     [rbp+1E0h+var_258], rax
0x1800537a9  test    rax, rax
0x1800537ac  jz      short loc_180053807
0x1800537ae  lea     rdx, [rax+10h]; struct GpRuntime::GpLockable *
0x1800537b2  lea     rcx, [rbp+1E0h+var_1F8]; this
0x1800537b6  call    ??0GpLock@GpRuntime@@QEAA@PEAVGpLockable@1@@Z; GpRuntime::GpLock::GpLock(GpRuntime::GpLockable *)
0x1800537bb  movd    xmm6, dword ptr [r13+8]
0x1800537c1  lea     rcx, [rdi+9D8h]
0x1800537c8  movd    xmm7, dword ptr [r13+4]
0x1800537ce  cvtdq2ps xmm6, xmm6
0x1800537d1  cvtdq2ps xmm7, xmm7
0x1800537d4  call    ??BCSmartGpObject@@QEBAPEAVGpBrush@@XZ; CSmartGpObject::operator GpBrush *(void)
0x1800537d9  mov     rcx, [rbp+1E0h+var_258]
0x1800537dd  mov     rdx, rax
0x1800537e0  movss   [rsp+2E0h+offset], xmm6
0x1800537e6  xorps   xmm3, xmm3
0x1800537e9  xorps   xmm2, xmm2
0x1800537ec  movss   dword ptr [rsp+2E0h+hSection], xmm7
0x1800537f2  call    ?FillRect@GpGraphics@@QEAA?AW4Status@@PEAVGpBrush@@MMMM@Z; GpGraphics::FillRect(GpBrush *,float,float,float,float)
0x1800537f7  mov     rax, [rbp+1E0h+var_1F0]
0x1800537fb  mov     rcx, [rbp+1E0h+var_258]; this
0x1800537ff  lock dec dword ptr [rax]
0x180053802  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x180053807  mov     ecx, [r13+8]
0x18005380b  mov     eax, esi
0x18005380d  mov     r8, [rbp+1E0h+var_240]
0x180053811  and     eax, 50000h
0x180053816  mov     r9d, [r13+4]; DestWidth
0x18005381a  and     esi, 0A00000h
0x180053820  shl     eax, 4
0x180053823  or      eax, esi
0x180053825  mov     edx, eax
0x180053827  shr     edx, 4
0x18005382a  or      edx, eax
0x18005382c  mov     rax, r13
0x18005382f  mov     [rsp+2E0h+rop], edx; rop
0x180053833  test    r15, r15
0x180053836  mov     [rsp+2E0h+iUsage], ebx; iUsage
0x18005383a  cmovnz  rax, r15
0x18005383e  xor     edx, edx; xDest
0x180053840  mov     [rsp+2E0h+lpbmi], rax; lpbmi
0x180053845  mov     [rsp+2E0h+lpBits], r8; lpBits
0x18005384a  xor     r8d, r8d; yDest
0x18005384d  mov     [rsp+2E0h+SrcHeight], ecx; SrcHeight
0x180053851  mov     [rsp+2E0h+SrcWidth], r9d; SrcWidth
0x180053856  mov     [rsp+2E0h+ySrc], ebx; ySrc
0x18005385a  mov     [rsp+2E0h+offset], ebx; xSrc
0x18005385e  mov     dword ptr [rsp+2E0h+hSection], ecx; DestHeight
0x180053862  mov     rcx, r14; hdc
0x180053865  call    cs:__imp_StretchDIBits
0x18005386c  nop     dword ptr [rax+rax+00h]
0x180053871  mov     rcx, r14; hdc
0x180053874  call    cs:__imp_DeleteDC
0x18005387b  nop     dword ptr [rax+rax+00h]
0x180053880  xor     edx, edx
0x180053882  mov     ecx, 5E0h
0x180053887  call    GpMallocEx
0x18005388c  test    rax, rax
0x18005388f  jz      loc_18005393C
0x180053895  mov     r8, [rbp+1E0h+ppvBits]; void *
0x180053899  test    r15, r15
0x18005389c  mov     rcx, rax; this
0x18005389f  cmovnz  r13, r15
0x1800538a3  mov     rdx, r13; struct tagBITMAPINFO *
0x1800538a6  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x1800538ab  mov     rsi, rax
0x1800538ae  test    rax, rax
0x1800538b1  jz      loc_18005393C
0x1800538b7  mov     rax, [rax]
0x1800538ba  mov     rcx, rsi
0x1800538bd  mov     rax, [rax+8]
0x1800538c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538c6  test    eax, eax
0x1800538c8  jz      short loc_18005391C
0x1800538ca  lea     rcx, [rbp+1E0h+var_230]; this
0x1800538ce  call    ??0GpImageAttributes@@QEAA@XZ; GpImageAttributes::GpImageAttributes(void)
0x1800538d3  mov     r8, [rsp+2E0h+var_268]
0x1800538d8  lea     rax, [rbp+1E0h+var_230]
0x1800538dc  mov     rcx, [rdi+958h]
0x1800538e3  mov     r9d, 3
0x1800538e9  mov     qword ptr [rsp+2E0h+ySrc], rax
0x1800538ee  mov     rdx, rsi
0x1800538f1  mov     rax, [rsp+2E0h+var_270]
0x1800538f6  mov     [rsp+2E0h+offset], 2
0x1800538fe  mov     [rsp+2E0h+hSection], rax
0x180053903  mov     [rbp+1E0h+var_20C], r9
0x180053907  mov     [rbp+1E0h+var_204], ebx
0x18005390a  mov     [rbp+1E0h+var_220], rbx
0x18005390e  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@PEBVPointF@@HAEBVRectF@@W4Unit@@PEBVGpImageAttributes@@@Z; GpGraphics::DrawImage(GpImage *,PointF const *,int,RectF const &,Unit,GpImageAttributes const *)
0x180053913  lea     rcx, [rbp+1E0h+var_230]; this
0x180053917  call    ??1GpImageAttributes@@UEAA@XZ; GpImageAttributes::~GpImageAttributes(void)
0x18005391c  mov     rax, [rsi]
0x18005391f  mov     rcx, rsi
0x180053922  mov     rax, [rax+38h]
0x180053926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005392b  jmp     short loc_18005393C
0x18005392d  mov     rcx, r14; hdc
0x180053930  call    cs:__imp_DeleteDC
0x180053937  nop     dword ptr [rax+rax+00h]
0x18005393c  mov     rcx, [rbp+1E0h+h]; ho
0x180053940  call    cs:__imp_DeleteObject
0x180053947  nop     dword ptr [rax+rax+00h]
0x18005394c  jmp     loc_180053D42
0x180053951  xor     edx, edx
0x180053953  mov     ecx, 5E0h
0x180053958  call    GpMallocEx
0x18005395d  xor     ebx, ebx
0x18005395f  test    rax, rax
0x180053962  jz      loc_180053D04
0x180053968  mov     r8, [rbp+1E0h+var_240]; void *
0x18005396c  test    r15, r15
0x18005396f  mov     rdx, r13
0x180053972  mov     rcx, rax; this
0x180053975  cmovnz  rdx, r15; struct tagBITMAPINFO *
0x180053979  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x18005397e  mov     r15, rax
0x180053981  test    rax, rax
0x180053984  jz      loc_180053D04
0x18005398a  mov     rax, [rax]
0x18005398d  mov     rcx, r15
0x180053990  mov     rax, [rax+8]
0x180053994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053999  test    eax, eax
0x18005399b  jz      loc_180053CF0
0x1800539a1  mov     r8d, 0EE0000h
0x1800539a7  mov     edx, 880000h
0x1800539ac  cmp     r14d, r8d
0x1800539af  jz      short loc_1800539C7
0x1800539b1  cmp     r14d, edx
0x1800539b4  jnz     loc_180053A41
0x1800539ba  cmp     [rdi+1078h], rbx
0x1800539c1  jnz     loc_180053A4A
0x1800539c7  cmp     [r13+0Eh], r12w
0x1800539cc  jnz     short loc_180053A41
0x1800539ce  cmp     [rdi+1078h], rbx
0x1800539d5  jz      short loc_1800539DF
0x1800539d7  mov     rcx, rdi; this
0x1800539da  call    ?DrawMaskBmp@CEmfPlusEnumState@@IEAAHXZ; CEmfPlusEnumState::DrawMaskBmp(void)
0x1800539df  mov     rax, [rsp+2E0h+var_270]
0x1800539e4  lea     rdx, [rdi+1084h]; struct PointF *
0x1800539eb  lea     rcx, [rdi+0AC0h]; this
0x1800539f2  mov     r8d, 3; int
0x1800539f8  movups  xmm0, xmmword ptr [rax]
0x1800539fb  mov     rax, [rsp+2E0h+var_268]
0x180053a00  movdqu  xmmword ptr [rdi+109Ch], xmm0
0x180053a08  movsd   xmm1, qword ptr [rax]
0x180053a0c  movsd   qword ptr [rdx], xmm1
0x180053a10  movsd   xmm0, qword ptr [rax+8]
0x180053a15  movsd   qword ptr [rdi+108Ch], xmm0
0x180053a1d  movsd   xmm1, qword ptr [rax+10h]
0x180053a22  movsd   qword ptr [rdi+1094h], xmm1
0x180053a2a  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x180053a2f  mov     [rdi+1080h], esi
0x180053a35  mov     [rdi+1078h], r15
0x180053a3c  jmp     loc_180053D42
0x180053a41  cmp     [rdi+1078h], rbx
0x180053a48  jz      short loc_180053A74
  ... truncated ...
```

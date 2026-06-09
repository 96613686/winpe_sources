# CEmfPlusEnumState::RenderBlt(RectF const &,RectF const &,PointF const *,int,tagBITMAPINFO const *,void * const,uint,ulong)

- ea: `0x18000abfc`
- end: `0x18000b48a`
- name: `?RenderBlt@CEmfPlusEnumState@@IEAAHAEBVRectF@@0PEBVPointF@@HPEBUtagBITMAPINFO@@QEAXIK@Z`
- size: `2190`
- prototype: `__int64 __fastcall(CEmfPlusEnumState *__hidden this, const struct RectF *, const struct RectF *, const struct PointF *, int, const struct tagBITMAPINFO *, void *const, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c090`
- `0x180124d44`
- `0x1801280c0`

## callees

- `0x1800067bc`
- `0x1800067dc`
- `0x180009eb8`
- `0x18000abfc`
- `0x18000b490`
- `0x18000bf58`
- `0x18000c84c`
- `0x18000c88c`
- `0x18001196c`
- `0x1800139c0`
- `0x1800139fc`
- `0x180013a54`
- `0x180019f9c`
- `0x180023f70`
- `0x180024714`
- `0x18002739c`
- `0x180076f28`
- `0x18008e8c0`
- `0x1800abe80`
- `0x1800f719c`
- `0x1800fe680`
- `0x1800fefe0`
- `0x1801255e8`
- `0x18012641c`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000acbe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000acbe`
- `GDI32!StretchDIBits` at `0x18000afbb`
- `GDI32!StretchDIBits` at `0x18000afbb`
- `GDI32!CreateDIBSection` at `0x18000ae9c`
- `GDI32!CreateDIBSection` at `0x18000ae9c`
- `GDI32!DeleteDC` at `0x18000afc4`
- `GDI32!DeleteDC` at `0x18000b3d4`
- `GDI32!DeleteDC` at `0x18000afc4`
- `GDI32!DeleteDC` at `0x18000b3d4`
- `GDI32!SelectObject` at `0x18000aeca`
- `GDI32!SelectObject` at `0x18000aeca`
- `GDI32!CreateCompatibleDC` at `0x18000aeb1`
- `GDI32!CreateCompatibleDC` at `0x18000aeb1`
- `GDI32!DeleteObject` at `0x18000b3de`
- `GDI32!DeleteObject` at `0x18000b3de`

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
  unsigned int v12; // r12d
  unsigned int v13; // esi
  struct tagBITMAPINFO *BmpInfoFromPalette; // r13
  GpBitmap *v15; // rax
  int v16; // r9d
  const struct PointF *v17; // rax
  struct tagBITMAPINFO *v19; // rdx
  GpBitmap *v20; // rax
  struct GpBitmap *v21; // r13
  __int64 v22; // rcx
  unsigned int v23; // edx
  const BITMAPINFO *v24; // rdx
  HDC CompatibleDC; // rax
  HDC v26; // rsi
  struct GpGraphics *v27; // rax
  __int64 v28; // rax
  unsigned int v29; // edx
  const BITMAPINFO *lpbmi; // rax
  GpBitmap *v31; // rax
  int v32; // r9d
  GpBitmap *v33; // rax
  GpBitmap *v34; // rsi
  __int64 v35; // rcx
  bool v36; // r15
  __m128 v37; // xmm1
  int v38; // eax
  __m128 v39; // xmm1
  int v40; // eax
  __m128 v41; // xmm1
  int v42; // eax
  __m128 v43; // xmm1
  int v44; // eax
  const struct RectF *v45; // rax
  __m128 v46; // xmm1
  __m128 v47; // xmm1
  __m128 v48; // xmm1
  float v49; // xmm0_4
  CEmfPlusEnumState *v50; // rcx
  __m128 v51; // xmm1
  int v52; // eax
  struct GpBitmap *v53; // r8
  char *v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rax
  struct GpObject *v58; // rax
  __int64 v59; // rax
  __int64 v60; // rbx
  _BYTE *v61; // rdx
  __int64 v62; // rcx
  struct GpBrush *v63; // rax
  GpGraphics *v64; // [rsp+78h] [rbp-90h] BYREF
  const struct PointF *v65; // [rsp+80h] [rbp-88h] BYREF
  HGDIOBJ h; // [rsp+88h] [rbp-80h]
  void *ppvBits; // [rsp+90h] [rbp-78h] BYREF
  const struct RectF *v68; // [rsp+98h] [rbp-70h]
  void *lpBits; // [rsp+A0h] [rbp-68h] BYREF
  int v70; // [rsp+A8h] [rbp-60h]
  int v71; // [rsp+ACh] [rbp-5Ch]
  _DWORD v72[2]; // [rsp+B0h] [rbp-58h] BYREF
  volatile signed __int32 *v73; // [rsp+B8h] [rbp-50h]
  _QWORD v74[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v75; // [rsp+D0h] [rbp-38h]
  GpRecolor *v76; // [rsp+D8h] [rbp-30h]
  __int64 v77; // [rsp+E4h] [rbp-24h]
  int v78; // [rsp+ECh] [rbp-1Ch]
  _BYTE v79[384]; // [rsp+F8h] [rbp-10h] BYREF

  v11 = a6;
  v12 = 1;
  lpBits = a7;
  v65 = a4;
  v68 = a2;
  v13 = a9 & 0xFF0000;
  if ( (a9 & 0xFF0000) == 0 || v13 == 16711680 )
  {
    LODWORD(v64) = v13 != 0 ? -1 : -16777216;
    GpSolidFill::GpSolidFill((GpSolidFill *)v79, (const struct GpRuntime::GpColor *)&v64);
    v62 = *((_QWORD *)this + 299);
    v61 = v79;
    goto LABEL_80;
  }
  if ( ((a9 ^ (4 * a9)) & 0xCCCC0000) == 0 )
  {
    if ( ((a9 ^ (16 * a9)) & 0xF00000) == 0 )
      return v12;
    v54 = (char *)this + 2520;
    v55 = *(_QWORD *)v54;
    if ( !*(_QWORD *)v54 || !*(_QWORD *)(v55 + 8) )
      return v12;
    switch ( v13 )
    {
      case 0x5A0000u:
        v56 = *((_QWORD *)this + 535);
        if ( v56 && *(_QWORD *)(v56 + 8) )
        {
          v65 = 0;
        }
        else
        {
          if ( !*(_QWORD *)(v55 + 8) )
            return v12;
          v57 = CSmartGpObject::operator GpBrush *(v54);
          v58 = (struct GpObject *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 64LL))(v57);
          CSmartGpObject::CSmartGpObject((CSmartGpObject *)&v65, v58);
        }
        CSmartGpObject::operator=((char *)this + 4280, &v65);
        CSmartGpObject::Release((CSmartGpObject *)&v65);
        return v12;
      case 0xA00000u:
        v59 = *((_QWORD *)this + 535);
        if ( v59 && *(_QWORD *)(v59 + 8) )
        {
          v63 = (struct GpBrush *)CSmartGpObject::operator GpBrush *(v54);
          if ( !(unsigned int)CEmfPlusEnumState::GetAlphaBrush(this, v63) )
            return v12;
          v54 = (char *)this + 4280;
          goto LABEL_79;
        }
        break;
      case 0xF00000u:
LABEL_79:
        v60 = *((_QWORD *)this + 299);
        v61 = (_BYTE *)CSmartGpObject::operator GpBrush *(v54);
        v62 = v60;
LABEL_80:
        GpGraphics::FillRects(v62, v61, a3, 1);
        return v12;
    }
    *((_DWORD *)this + 1075) |= 1u;
    goto LABEL_79;
  }
  BmpInfoFromPalette = CEmfPlusEnumState::GetBmpInfoFromPalette(this, a6, a8);
  if ( v13 != 13369344 && ((a9 ^ (2 * a9)) & 0xAA0000) == 0 )
  {
    v24 = a6;
    ppvBits = 0;
    if ( BmpInfoFromPalette )
      v24 = BmpInfoFromPalette;
    h = CreateDIBSection(0, v24, 0, &ppvBits, 0, 0);
    if ( h )
    {
      CompatibleDC = CreateCompatibleDC(0);
      v26 = CompatibleDC;
      if ( CompatibleDC )
      {
        if ( SelectObject(CompatibleDC, h) )
        {
          if ( ((a9 ^ (16 * a9)) & 0xF00000) != 0 )
          {
            v27 = GpGraphics::GetFromHdc(v26, 0);
            v64 = v27;
            if ( v27 )
            {
              GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)v72, (struct GpGraphics *)((char *)v27 + 16));
              v28 = CSmartGpObject::operator GpBrush *((char *)this + 2520);
              GpGraphics::FillRect(v64, v28);
              _InterlockedDecrement(v73);
              GpGraphics::`scalar deleting destructor'(v64, v29);
            }
          }
          lpbmi = a6;
          if ( BmpInfoFromPalette )
            lpbmi = BmpInfoFromPalette;
          StretchDIBits(
            v26,
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
          DeleteDC(v26);
          v31 = (GpBitmap *)GpMallocEx(1504, 0);
          if ( v31 )
          {
            if ( BmpInfoFromPalette )
              v11 = BmpInfoFromPalette;
            v33 = GpBitmap::GpBitmap(v31, v11, ppvBits, v32);
            v34 = v33;
            if ( v33 )
            {
              if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v33 + 8LL))(v33) )
              {
                GpImageAttributes::GpImageAttributes((GpImageAttributes *)v74);
                v35 = *((_QWORD *)this + 299);
                v77 = 3;
                v78 = 0;
                v75 = 0;
                GpGraphics::DrawImage(v35, v34, v65);
                GpImageAttributes::~GpImageAttributes((GpImageAttributes *)v74);
              }
              (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v34 + 56LL))(v34);
            }
          }
        }
        else
        {
          DeleteDC(v26);
        }
      }
      DeleteObject(h);
    }
    return v12;
  }
  v15 = (GpBitmap *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x5E0u);
  if ( !v15 )
    return 0;
  v19 = a6;
  if ( BmpInfoFromPalette )
    v19 = BmpInfoFromPalette;
  v20 = GpBitmap::GpBitmap(v15, v19, lpBits, v16);
  v21 = v20;
  if ( !v20 )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v20 + 8LL))(v20) )
  {
    v12 = 0;
LABEL_23:
    (*(void (__fastcall **)(struct GpBitmap *))(*(_QWORD *)v21 + 56LL))(v21);
    return v12;
  }
  if ( v13 != 15597568 )
  {
    if ( v13 != 8912896 )
    {
LABEL_18:
      if ( !*((_QWORD *)this + 527) )
      {
LABEL_19:
        if ( ((a9 ^ (2 * a9)) & 0xAA0000) != 0 )
          *((_DWORD *)this + 1075) |= 1u;
        GpImageAttributes::GpImageAttributes((GpImageAttributes *)v74);
        v22 = *((_QWORD *)this + 299);
        v77 = 3;
        v78 = 0;
        v75 = 0;
        GpGraphics::DrawImage(v22, v21, v65);
        v74[0] = &GpImageAttributes::`vftable';
        if ( v76 )
          GpRecolor::`scalar deleting destructor'(v76, v23);
        goto LABEL_23;
      }
LABEL_91:
      if ( v13 == 8912896 )
      {
        if ( (*((_DWORD *)this + 1056) & 0xFF0000) != 0xEE0000 )
        {
LABEL_96:
          CEmfPlusEnumState::DrawMaskBmp(this);
          goto LABEL_19;
        }
      }
      else if ( v13 != 6684672 || (*((_DWORD *)this + 1056) & 0xFF0000) != 0x880000 )
      {
        goto LABEL_96;
      }
      v36 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v37 = (__m128)*((unsigned int *)this + 1066);
      v37.m128_f32[0] = v37.m128_f32[0] + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        v38 = (int)_mm_round_ss(v37, v37, 9).m128_f32[0];
      else
        v38 = (int)floor(v37.m128_f32[0]);
      v39 = (__m128)*((unsigned int *)this + 1065);
      LODWORD(v64) = v38;
      v39.m128_f32[0] = v39.m128_f32[0] + 0.5;
      if ( v36 )
        v40 = (int)_mm_round_ss(v39, v39, 9).m128_f32[0];
      else
        v40 = (int)floor(v39.m128_f32[0]);
      v41 = (__m128)*((unsigned int *)this + 1064);
      LODWORD(ppvBits) = v40;
      v41.m128_f32[0] = v41.m128_f32[0] + 0.5;
      if ( v36 )
        v42 = (int)_mm_round_ss(v41, v41, 9).m128_f32[0];
      else
        v42 = (int)floor(v41.m128_f32[0]);
      v43 = (__m128)*((unsigned int *)this + 1063);
      LODWORD(h) = v42;
      v43.m128_f32[0] = v43.m128_f32[0] + 0.5;
      if ( v36 )
        v44 = (int)_mm_round_ss(v43, v43, 9).m128_f32[0];
      else
        v44 = (int)floor(v43.m128_f32[0]);
      lpBits = (void *)__PAIR64__((unsigned int)h, v44);
      v70 = (int)ppvBits;
      v71 = (int)v64;
      v45 = v68;
      v46 = (__m128)*((unsigned int *)v68 + 3);
      v46.m128_f32[0] = v46.m128_f32[0] + 0.5;
      if ( v36 )
      {
        LODWORD(h) = (int)_mm_round_ss(v46, v46, 9).m128_f32[0];
      }
      else
      {
        LODWORD(h) = (int)floor(v46.m128_f32[0]);
        v45 = v68;
      }
      v47 = (__m128)*((unsigned int *)v45 + 2);
      v47.m128_f32[0] = v47.m128_f32[0] + 0.5;
      if ( v36 )
      {
        LODWORD(ppvBits) = (int)_mm_round_ss(v47, v47, 9).m128_f32[0];
      }
      else
      {
        LODWORD(ppvBits) = (int)floor(v47.m128_f32[0]);
        v45 = v68;
      }
      v48 = (__m128)*((unsigned int *)v45 + 1);
      v48.m128_f32[0] = v48.m128_f32[0] + 0.5;
      if ( v36 )
      {
        v49 = _mm_round_ss(v48, v48, 9).m128_f32[0];
        v50 = (CEmfPlusEnumState *)(unsigned int)(int)v49;
        LODWORD(v64) = (int)v49;
      }
      else
      {
        LODWORD(v64) = (int)floor(v48.m128_f32[0]);
        v45 = v68;
      }
      v51 = (__m128)*(unsigned int *)v45;
      v51.m128_f32[0] = v51.m128_f32[0] + 0.5;
      if ( v36 )
        v52 = (int)_mm_round_ss(v51, v51, 9).m128_f32[0];
      else
        v52 = (int)floor(v51.m128_f32[0]);
      v53 = (struct GpBitmap *)*((_QWORD *)this + 527);
      v72[0] = v52;
      v72[1] = (_DWORD)v64;
      v73 = (volatile signed __int32 *)__PAIR64__((unsigned int)h, (unsigned int)ppvBits);
      CEmfPlusEnumState::MergeImageAndMask(
        v50,
        v21,
        v53,
        (const struct GpRuntime::GpRect *)v72,
        (const struct GpRuntime::GpRect *)&lpBits,
        v13 == 6684672);
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
  v17 = v65;
  *(_OWORD *)((char *)this + 4252) = *(_OWORD *)v68;
  *(_QWORD *)((char *)this + 4228) = *(_QWORD *)v17;
  *(_QWORD *)((char *)this + 4236) = *((_QWORD *)v17 + 1);
  *(_QWORD *)((char *)this + 4244) = *((_QWORD *)v17 + 2);
  GpMatrix::Transform((CEmfPlusEnumState *)((char *)this + 2752), (CEmfPlusEnumState *)((char *)this + 4228), 3);
  *((_DWORD *)this + 1056) = a9;
  *((_QWORD *)this + 527) = v21;
  return v12;
}

```

## disassembly

```asm
0x18000abfc  mov     rax, rsp
0x18000abff  mov     [rax+20h], rbx
0x18000ac03  push    rbp
0x18000ac04  push    rsi
0x18000ac05  push    rdi
0x18000ac06  push    r12
0x18000ac08  push    r13
0x18000ac0a  push    r14
0x18000ac0c  push    r15
0x18000ac0e  lea     rbp, [rax-1D8h]
0x18000ac15  sub     rsp, 2A0h
0x18000ac1c  movaps  xmmword ptr [rax-48h], xmm6
0x18000ac20  movaps  xmmword ptr [rax-58h], xmm7
0x18000ac24  mov     rax, cs:__security_cookie
0x18000ac2b  xor     rax, rsp
0x18000ac2e  mov     [rbp+1D0h+var_60], rax
0x18000ac35  mov     rax, [rbp+1D0h+arg_30]
0x18000ac3c  mov     r13, r8
0x18000ac3f  mov     r14d, [rbp+1D0h+arg_40]
0x18000ac46  mov     rdi, rcx
0x18000ac49  mov     r15, [rbp+1D0h+arg_28]
0x18000ac50  mov     esi, r14d
0x18000ac53  mov     r8d, [rbp+1D0h+arg_38]; unsigned int
0x18000ac5a  mov     r12d, 1
0x18000ac60  mov     [rbp+1D0h+var_238], rax
0x18000ac64  mov     eax, 0FF0000h
0x18000ac69  mov     [rsp+2D0h+var_258], r9
0x18000ac6e  mov     [rbp+1D0h+var_240], rdx
0x18000ac72  and     esi, eax
0x18000ac74  jz      loc_18000B458
0x18000ac7a  cmp     esi, eax
0x18000ac7c  jz      loc_18000B458
0x18000ac82  lea     eax, ds:0[r14*4]
0x18000ac8a  xor     eax, r14d
0x18000ac8d  test    eax, 0CCCC0000h
0x18000ac92  jz      loc_18000B37F
0x18000ac98  mov     rdx, r15; struct tagBITMAPINFO *
0x18000ac9b  call    ?GetBmpInfoFromPalette@CEmfPlusEnumState@@IEAAPEAUtagBITMAPINFO@@PEBU2@I@Z; CEmfPlusEnumState::GetBmpInfoFromPalette(tagBITMAPINFO const *,uint)
0x18000aca0  mov     r13, rax
0x18000aca3  cmp     esi, 0CC0000h
0x18000aca9  jnz     loc_18000AE68
0x18000acaf  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18000acb6  xor     edx, edx; dwFlags
0x18000acb8  mov     r8d, 5E0h; dwBytes
0x18000acbe  call    cs:__imp_HeapAlloc
0x18000acc4  xor     ebx, ebx
0x18000acc6  test    rax, rax
0x18000acc9  jnz     loc_18000AD80
0x18000accf  mov     r12d, ebx
0x18000acd2  jmp     short loc_18000AD49
0x18000acd4  cmp     [r15+0Eh], r12w
0x18000acd9  jnz     loc_18000ADD3
0x18000acdf  cmp     [rdi+1078h], rbx
0x18000ace6  jnz     loc_18000B40F
0x18000acec  mov     rax, [rbp+1D0h+var_240]
0x18000acf0  lea     rdx, [rdi+1084h]; struct PointF *
0x18000acf7  lea     rcx, [rdi+0AC0h]; this
0x18000acfe  mov     r8d, 3; int
0x18000ad04  movups  xmm0, xmmword ptr [rax]
0x18000ad07  mov     rax, [rsp+2D0h+var_258]
0x18000ad0c  movdqu  xmmword ptr [rdi+109Ch], xmm0
0x18000ad14  movsd   xmm1, qword ptr [rax]
0x18000ad18  movsd   qword ptr [rdx], xmm1
0x18000ad1c  movsd   xmm0, qword ptr [rax+8]
0x18000ad21  movsd   qword ptr [rdi+108Ch], xmm0
0x18000ad29  movsd   xmm1, qword ptr [rax+10h]
0x18000ad2e  movsd   qword ptr [rdi+1094h], xmm1
0x18000ad36  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x18000ad3b  mov     [rdi+1080h], r14d
0x18000ad42  mov     [rdi+1078h], r13
0x18000ad49  mov     eax, r12d
0x18000ad4c  mov     rcx, [rbp+1D0h+var_60]
0x18000ad53  xor     rcx, rsp; StackCookie
0x18000ad56  call    __security_check_cookie
0x18000ad5b  lea     r11, [rsp+2D0h+var_30]
0x18000ad63  mov     rbx, [r11+58h]
0x18000ad67  movaps  xmm6, xmmword ptr [r11-10h]
0x18000ad6c  movaps  xmm7, xmmword ptr [r11-20h]
0x18000ad71  mov     rsp, r11
0x18000ad74  pop     r15
0x18000ad76  pop     r14
0x18000ad78  pop     r13
0x18000ad7a  pop     r12
0x18000ad7c  pop     rdi
0x18000ad7d  pop     rsi
0x18000ad7e  pop     rbp
0x18000ad7f  retn
0x18000ad80  mov     r8, [rbp+1D0h+var_238]; void *
0x18000ad84  test    r13, r13
0x18000ad87  mov     rdx, r15
0x18000ad8a  mov     rcx, rax; this
0x18000ad8d  cmovnz  rdx, r13; struct tagBITMAPINFO *
0x18000ad91  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x18000ad96  mov     r13, rax
0x18000ad99  test    rax, rax
0x18000ad9c  jz      loc_18000ACCF
0x18000ada2  mov     rax, [rax]
0x18000ada5  mov     rcx, r13
0x18000ada8  mov     rax, [rax+8]
0x18000adac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb1  test    eax, eax
0x18000adb3  jz      loc_18000B450
0x18000adb9  mov     edx, 0EE0000h
0x18000adbe  mov     ecx, 880000h
0x18000adc3  cmp     esi, edx
0x18000adc5  jz      loc_18000ACD4
0x18000adcb  cmp     esi, ecx
0x18000adcd  jz      loc_18000B3E9
0x18000add3  cmp     [rdi+1078h], rbx
0x18000adda  jnz     loc_18000B3F6
0x18000ade0  lea     eax, [r14+r14]
0x18000ade4  xor     eax, r14d
0x18000ade7  test    eax, 0AA0000h
0x18000adec  jnz     loc_18000B444
0x18000adf2  lea     rcx, [rbp+1D0h+var_218]; this
0x18000adf6  call    ??0GpImageAttributes@@QEAA@XZ; GpImageAttributes::GpImageAttributes(void)
0x18000adfb  mov     r8, [rsp+2D0h+var_258]
0x18000ae00  lea     rax, [rbp+1D0h+var_218]
0x18000ae04  mov     rcx, [rdi+958h]
0x18000ae0b  mov     r9d, 3
0x18000ae11  mov     qword ptr [rsp+2D0h+ySrc], rax
0x18000ae16  mov     rdx, r13
0x18000ae19  mov     rax, [rbp+1D0h+var_240]
0x18000ae1d  mov     [rsp+2D0h+offset], 2
0x18000ae25  mov     [rsp+2D0h+hSection], rax
0x18000ae2a  mov     [rbp+1D0h+var_1F4], r9
0x18000ae2e  mov     [rbp+1D0h+var_1EC], ebx
0x18000ae31  mov     [rbp+1D0h+var_208], rbx
0x18000ae35  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@PEBVPointF@@HAEBVRectF@@W4Unit@@PEBVGpImageAttributes@@@Z; GpGraphics::DrawImage(GpImage *,PointF const *,int,RectF const &,Unit,GpImageAttributes const *)
0x18000ae3a  mov     rcx, [rbp+1D0h+var_200]; this
0x18000ae3e  lea     rax, ??_7GpImageAttributes@@6B@; const GpImageAttributes::`vftable'
0x18000ae45  mov     [rbp+1D0h+var_218], rax
0x18000ae49  test    rcx, rcx
0x18000ae4c  jz      short loc_18000AE53
0x18000ae4e  call    ??_GGpRecolor@@QEAAPEAXI@Z; GpRecolor::`scalar deleting destructor'(uint)
0x18000ae53  mov     rax, [r13+0]
0x18000ae57  mov     rcx, r13
0x18000ae5a  mov     rax, [rax+38h]
0x18000ae5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae63  jmp     loc_18000AD49
0x18000ae68  lea     eax, [r14+r14]
0x18000ae6c  xor     eax, r14d
0x18000ae6f  test    eax, 0AA0000h
0x18000ae74  jnz     loc_18000ACAF
0x18000ae7a  xor     ebx, ebx
0x18000ae7c  lea     r9, [rbp+1D0h+ppvBits]; ppvBits
0x18000ae80  test    r13, r13
0x18000ae83  mov     [rsp+2D0h+offset], ebx; offset
0x18000ae87  mov     rdx, r15
0x18000ae8a  mov     [rbp+1D0h+ppvBits], rbx
0x18000ae8e  cmovnz  rdx, r13; pbmi
0x18000ae92  mov     [rsp+2D0h+hSection], rbx; hSection
0x18000ae97  xor     r8d, r8d; usage
0x18000ae9a  xor     ecx, ecx; hdc
0x18000ae9c  call    cs:__imp_CreateDIBSection
0x18000aea2  mov     [rbp+1D0h+h], rax
0x18000aea6  test    rax, rax
0x18000aea9  jz      loc_18000AD49
0x18000aeaf  xor     ecx, ecx; hdc
0x18000aeb1  call    cs:__imp_CreateCompatibleDC
0x18000aeb7  mov     rsi, rax
0x18000aeba  test    rax, rax
0x18000aebd  jz      loc_18000B3DA
0x18000aec3  mov     rdx, [rbp+1D0h+h]; h
0x18000aec7  mov     rcx, rax; hdc
0x18000aeca  call    cs:__imp_SelectObject
0x18000aed0  test    rax, rax
0x18000aed3  jz      loc_18000B3D1
0x18000aed9  mov     ecx, r14d
0x18000aedc  mov     edx, 0F00000h
0x18000aee1  shl     ecx, 4
0x18000aee4  xor     ecx, r14d
0x18000aee7  test    edx, ecx
0x18000aee9  jz      short loc_18000AF5A
0x18000aeeb  xor     edx, edx; void *
0x18000aeed  mov     rcx, rsi; hdc
0x18000aef0  call    ?GetFromHdc@GpGraphics@@SAPEAV1@PEAUHDC__@@PEAX@Z; GpGraphics::GetFromHdc(HDC__ *,void *)
0x18000aef5  mov     [rsp+2D0h+var_260], rax
0x18000aefa  test    rax, rax
0x18000aefd  jz      short loc_18000AF5A
0x18000aeff  lea     rdx, [rax+10h]; struct GpRuntime::GpLockable *
0x18000af03  lea     rcx, [rbp+1D0h+var_228]; this
0x18000af07  call    ??0GpLock@GpRuntime@@QEAA@PEAVGpLockable@1@@Z; GpRuntime::GpLock::GpLock(GpRuntime::GpLockable *)
0x18000af0c  movd    xmm6, dword ptr [r15+8]
0x18000af12  lea     rcx, [rdi+9D8h]
0x18000af19  movd    xmm7, dword ptr [r15+4]
0x18000af1f  cvtdq2ps xmm6, xmm6
0x18000af22  cvtdq2ps xmm7, xmm7
0x18000af25  call    ??BCSmartGpObject@@QEBAPEAVGpBrush@@XZ; CSmartGpObject::operator GpBrush *(void)
0x18000af2a  mov     rcx, [rsp+2D0h+var_260]
0x18000af2f  mov     rdx, rax
0x18000af32  movss   [rsp+2D0h+offset], xmm6
0x18000af38  xorps   xmm3, xmm3
0x18000af3b  xorps   xmm2, xmm2
0x18000af3e  movss   dword ptr [rsp+2D0h+hSection], xmm7
0x18000af44  call    ?FillRect@GpGraphics@@QEAA?AW4Status@@PEAVGpBrush@@MMMM@Z; GpGraphics::FillRect(GpBrush *,float,float,float,float)
0x18000af49  mov     rax, [rbp+1D0h+var_220]
0x18000af4d  mov     rcx, [rsp+2D0h+var_260]; this
0x18000af52  lock dec dword ptr [rax]
0x18000af55  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x18000af5a  mov     ecx, [r15+8]
0x18000af5e  mov     eax, r14d
0x18000af61  mov     r8, [rbp+1D0h+var_238]
0x18000af65  and     eax, 50000h
0x18000af6a  mov     r9d, [r15+4]; DestWidth
0x18000af6e  and     r14d, 0A00000h
0x18000af75  shl     eax, 4
0x18000af78  or      eax, r14d
0x18000af7b  mov     edx, eax
0x18000af7d  shr     edx, 4
0x18000af80  or      edx, eax
0x18000af82  mov     rax, r15
0x18000af85  mov     [rsp+2D0h+rop], edx; rop
0x18000af89  test    r13, r13
0x18000af8c  mov     [rsp+2D0h+iUsage], ebx; iUsage
0x18000af90  cmovnz  rax, r13
0x18000af94  xor     edx, edx; xDest
0x18000af96  mov     [rsp+2D0h+lpbmi], rax; lpbmi
0x18000af9b  mov     [rsp+2D0h+lpBits], r8; lpBits
0x18000afa0  xor     r8d, r8d; yDest
0x18000afa3  mov     [rsp+2D0h+SrcHeight], ecx; SrcHeight
0x18000afa7  mov     [rsp+2D0h+SrcWidth], r9d; SrcWidth
0x18000afac  mov     [rsp+2D0h+ySrc], ebx; ySrc
0x18000afb0  mov     [rsp+2D0h+offset], ebx; xSrc
0x18000afb4  mov     dword ptr [rsp+2D0h+hSection], ecx; DestHeight
0x18000afb8  mov     rcx, rsi; hdc
0x18000afbb  call    cs:__imp_StretchDIBits
0x18000afc1  mov     rcx, rsi; hdc
0x18000afc4  call    cs:__imp_DeleteDC
0x18000afca  xor     edx, edx
0x18000afcc  mov     ecx, 5E0h
0x18000afd1  call    GpMallocEx
0x18000afd6  test    rax, rax
0x18000afd9  jz      loc_18000B3DA
0x18000afdf  mov     r8, [rbp+1D0h+ppvBits]; void *
0x18000afe3  test    r13, r13
0x18000afe6  mov     rcx, rax; this
0x18000afe9  cmovnz  r15, r13
0x18000afed  mov     rdx, r15; struct tagBITMAPINFO *
0x18000aff0  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x18000aff5  mov     rsi, rax
0x18000aff8  test    rax, rax
0x18000affb  jz      loc_18000B3DA
0x18000b001  mov     rax, [rax]
0x18000b004  mov     rcx, rsi
0x18000b007  mov     rax, [rax+8]
0x18000b00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b010  test    eax, eax
0x18000b012  jz      short loc_18000B065
0x18000b014  lea     rcx, [rbp+1D0h+var_218]; this
0x18000b018  call    ??0GpImageAttributes@@QEAA@XZ; GpImageAttributes::GpImageAttributes(void)
0x18000b01d  mov     r8, [rsp+2D0h+var_258]
0x18000b022  lea     rax, [rbp+1D0h+var_218]
0x18000b026  mov     rcx, [rdi+958h]
0x18000b02d  mov     r9d, 3
0x18000b033  mov     qword ptr [rsp+2D0h+ySrc], rax
0x18000b038  mov     rdx, rsi
0x18000b03b  mov     rax, [rbp+1D0h+var_240]
0x18000b03f  mov     [rsp+2D0h+offset], 2
0x18000b047  mov     [rsp+2D0h+hSection], rax
0x18000b04c  mov     [rbp+1D0h+var_1F4], r9
0x18000b050  mov     [rbp+1D0h+var_1EC], ebx
0x18000b053  mov     [rbp+1D0h+var_208], rbx
0x18000b057  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@PEBVPointF@@HAEBVRectF@@W4Unit@@PEBVGpImageAttributes@@@Z; GpGraphics::DrawImage(GpImage *,PointF const *,int,RectF const &,Unit,GpImageAttributes const *)
0x18000b05c  lea     rcx, [rbp+1D0h+var_218]; this
0x18000b060  call    ??1GpImageAttributes@@UEAA@XZ; GpImageAttributes::~GpImageAttributes(void)
0x18000b065  mov     rax, [rsi]
0x18000b068  mov     rcx, rsi
0x18000b06b  mov     rax, [rax+38h]
0x18000b06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b074  jmp     loc_18000B3DA
0x18000b079  mov     r15b, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18000b080  movss   xmm1, dword ptr [rdi+10A8h]
0x18000b088  movss   xmm6, cs:__real@3f000000
0x18000b090  addss   xmm1, xmm6
0x18000b094  test    r15b, r15b
0x18000b097  jz      loc_18000B219
0x18000b09d  movaps  xmm0, xmm1
0x18000b0a0  roundss xmm0, xmm0, 9
0x18000b0a6  cvttss2si eax, xmm0
0x18000b0aa  movss   xmm1, dword ptr [rdi+10A4h]
0x18000b0b2  mov     dword ptr [rsp+2D0h+var_260], eax
0x18000b0b6  addss   xmm1, xmm6
0x18000b0ba  test    r15b, r15b
0x18000b0bd  jz      loc_18000B22A
0x18000b0c3  movaps  xmm0, xmm1
0x18000b0c6  roundss xmm0, xmm0, 9
0x18000b0cc  cvttss2si eax, xmm0
0x18000b0d0  movss   xmm1, dword ptr [rdi+10A0h]
0x18000b0d8  mov     dword ptr [rbp+1D0h+ppvBits], eax
0x18000b0db  addss   xmm1, xmm6
0x18000b0df  test    r15b, r15b
0x18000b0e2  jz      loc_18000B23B
0x18000b0e8  movaps  xmm0, xmm1
0x18000b0eb  roundss xmm0, xmm0, 9
0x18000b0f1  cvttss2si eax, xmm0
0x18000b0f5  movss   xmm1, dword ptr [rdi+109Ch]
0x18000b0fd  mov     dword ptr [rbp+1D0h+h], eax
0x18000b100  addss   xmm1, xmm6
0x18000b104  test    r15b, r15b
  ... truncated ...
```

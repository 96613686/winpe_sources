# XHDC::DrawImage(int,int,int,int,Gdiplus::Bitmap *,int,int,int,int,int,int)

- ea: `0x180b45dd4`
- end: `0x180b464bf`
- name: `?DrawImage@XHDC@@QEBAHHHHHPEAVBitmap@Gdiplus@@HHHHHH@Z`
- size: `1771`
- prototype: `__int64 __fastcall(XHDC *__hidden this, int, int, int, int, struct Gdiplus::Bitmap *, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1807ff9b8`

## callees

- `0x1805cfe20`
- `0x180b43c68`
- `0x180b45c0c`
- `0x180b45dd4`
- `0x180b46be8`
- `0x180b46d74`
- `0x180b474c0`
- `0x180b47570`
- `0x180b4764c`
- `0x180b4769c`
- `0x180b4a458`
- `0x180b4a5d0`
- `0x180b4a620`
- `0x1810cac8c`
- `0x1810f649e`
- `0x1810f64ce`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180b463af`
- `KERNEL32!GetTickCount` at `0x180b4641e`
- `KERNEL32!GetTickCount` at `0x180b463af`
- `KERNEL32!GetTickCount` at `0x180b4641e`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipCreateImageAttributes` at `0x180b46229`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipCreateImageAttributes` at `0x180b46229`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDisposeImageAttributes` at `0x180b4645a`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDisposeImageAttributes` at `0x180b4647f`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDisposeImageAttributes` at `0x180b4645a`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDisposeImageAttributes` at `0x180b4647f`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetPixelOffsetMode` at `0x180b46274`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetPixelOffsetMode` at `0x180b46274`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDeleteGraphics` at `0x180b4644a`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDeleteGraphics` at `0x180b4646f`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDeleteGraphics` at `0x180b4644a`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDeleteGraphics` at `0x180b4646f`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetCompositingQuality` at `0x180b462b2`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetCompositingQuality` at `0x180b462b2`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipRotateWorldTransform` at `0x180b46376`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipRotateWorldTransform` at `0x180b46376`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetInterpolationMode` at `0x180b46307`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetInterpolationMode` at `0x180b46307`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetCompositingMode` at `0x180b46293`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetCompositingMode` at `0x180b46293`

## pseudocode

```c
_BOOL8 __fastcall XHDC::DrawImage(
        HDC *this,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        struct Gdiplus::Bitmap *a6,
        int a7,
        float a8,
        int a9,
        int a10,
        unsigned int a11,
        int a12)
{
  int v14; // r12d
  int v15; // r15d
  unsigned int v16; // r14d
  int v17; // r13d
  const struct tagSIZE *OffsetOnly; // rax
  LONG cx; // ecx
  LONG cy; // eax
  unsigned int v21; // r8d
  int v22; // edi
  int v23; // r13d
  int v24; // ecx
  int v25; // edx
  int v26; // esi
  CWorldTransform *v27; // rcx
  float v28; // xmm6_4
  float v29; // xmm0_4
  float v30; // xmm7_4
  float v31; // xmm9_4
  float v32; // xmm10_4
  int v33; // r8d
  int v34; // eax
  unsigned int v35; // r10d
  int v36; // r11d
  int v37; // r14d
  int v38; // esi
  int v39; // eax
  int v40; // r10d
  int v41; // edi
  int v42; // r11d
  int v43; // ebx
  float v44; // xmm2_4
  float v45; // xmm6_4
  float v46; // xmm0_4
  int v47; // r12d
  float v48; // xmm0_4
  int v49; // r15d
  __int64 v50; // rdx
  float v51; // xmm6_4
  float v52; // xmm7_4
  int v53; // eax
  __int64 v54; // rdx
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  int v58; // eax
  __int64 v59; // rdx
  unsigned int v60; // eax
  __int64 v61; // rdx
  unsigned int v62; // eax
  DWORD TickCount; // ebx
  int v64; // edi
  DWORD v65; // eax
  unsigned int v66; // ecx
  float v68[2]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v69; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v70; // [rsp+78h] [rbp-90h]
  int v71; // [rsp+7Ch] [rbp-8Ch]
  int v72; // [rsp+80h] [rbp-88h] BYREF
  int v73; // [rsp+84h] [rbp-84h]
  int v74; // [rsp+88h] [rbp-80h]
  int v75; // [rsp+8Ch] [rbp-7Ch] BYREF
  unsigned __int64 v76; // [rsp+90h] [rbp-78h] BYREF
  int v77; // [rsp+98h] [rbp-70h]
  int v78; // [rsp+9Ch] [rbp-6Ch]
  unsigned __int64 v79; // [rsp+A0h] [rbp-68h]
  int v80; // [rsp+A8h] [rbp-60h]
  int TrivialRotationAngle; // [rsp+ACh] [rbp-5Ch]
  __int64 v82; // [rsp+B0h] [rbp-58h] BYREF
  int v83; // [rsp+B8h] [rbp-50h]
  unsigned __int64 v84; // [rsp+C0h] [rbp-48h] BYREF
  int v85; // [rsp+C8h] [rbp-40h]
  int v86; // [rsp+CCh] [rbp-3Ch]

  v14 = a4;
  v15 = a5;
  v16 = a2 + a4;
  v17 = a3 + a5;
  v77 = a2 + a4;
  v78 = a3 + a5;
  v76 = __PAIR64__(a3, a2);
  if ( a4 <= 0 || a5 <= 0 )
    return 0;
  OffsetOnly = XHDC::GetOffsetOnly((XHDC *)this);
  if ( OffsetOnly )
  {
    cx = OffsetOnly->cx;
    TrivialRotationAngle = 0;
    cy = OffsetOnly->cy;
    v21 = cx + a2;
    *(float *)&v72 = a8;
    v22 = a10;
    v23 = cx + v16;
    v24 = a3 + a5;
    v25 = cy + a3;
    LODWORD(v69) = v21;
    v26 = a9;
    v75 = v25;
    v80 = cy + v24;
    v73 = a9;
    v79 = __PAIR64__(v25, v21);
    LODWORD(v68[0]) = a10;
    v74 = a7;
  }
  else
  {
    v27 = (CWorldTransform *)this[14];
    v69 = __PAIR64__(a3, a2);
    v70 = v16;
    v71 = v17;
    v68[0] = 1.0;
    *(float *)&v72 = 1.0;
    CWorldTransform::GetScales(v27, v68, (float *)&v72);
    v28 = v68[0];
    v29 = floorf_0((float)((float)a7 * v68[0]) + 0.5);
    v30 = *(float *)&v72;
    v31 = v29;
    v32 = floorf_0((float)((float)SLODWORD(a8) * *(float *)&v72) + 0.5);
    v26 = (int)floorf_0((float)((float)a9 * v28) + 0.5);
    if ( v26 < 1 )
      v26 = 1;
    v73 = v26;
    v22 = (int)floorf_0((float)((float)a10 * v30) + 0.5);
    if ( v22 < 1 )
      v22 = 1;
    LODWORD(v68[0]) = v22;
    v14 = (int)floorf_0((float)((float)v14 * v28) + 0.5);
    if ( v14 < 1 )
      v14 = 1;
    v15 = (int)floorf_0((float)((float)a5 * v30) + 0.5);
    if ( v15 < 1 )
      v15 = 1;
    XHDC::TransformRect((XHDC *)this, (struct CRect *)&v69);
    if ( !(unsigned int)XHDC::TransformRect((XHDC *)this, (struct CRect *)&v76) )
      return 0;
    v23 = v77;
    v33 = v78;
    v79 = v76;
    v74 = (int)v31;
    v72 = (int)v32;
    if ( (int)v76 + 1 > v77 )
      v23 = v76 + 1;
    if ( HIDWORD(v76) + 1 > v78 )
      v33 = HIDWORD(v76) + 1;
    v80 = v33;
    TrivialRotationAngle = XHDC::GetTrivialRotationAngle((XHDC *)this);
    v75 = HIDWORD(v69);
  }
  if ( !v26 || !v22 || !v14 || !a11 || !a12 )
    return 0;
  v34 = GreatestCommonDivisor<int>(a11, (unsigned int)v26);
  v37 = v36 / v34;
  v38 = v26 / v34;
  v39 = GreatestCommonDivisor<int>(v35, (unsigned int)v22);
  v41 = v40 / v39;
  v43 = SLODWORD(v68[0]) / v39;
  v44 = (float)v73 / (float)v42;
  v45 = (float)SLODWORD(v68[0]) / (float)v40;
  v73 = (int)(float)((float)v74 / v44) - (int)(float)((float)v74 / v44) % v37;
  LODWORD(v68[0]) = (int)(float)((float)v72 / v45) - (int)(float)((float)v72 / v45) % (v40 / v39);
  v46 = ceilf_0((float)v73 * v44);
  v47 = v37 * ((v14 + v38 - (int)v46 + v74 - 1) / v38);
  v48 = ceilf_0((float)SLODWORD(v68[0]) * v45);
  v82 = 0;
  v49 = v41 * ((v15 + v43 - (int)v48 + v72 - 1) / v43);
  *(float *)&v76 = (float)((int)v69 + v73 * v38 / v37 - v74);
  *((float *)&v76 + 1) = (float)(v75 + LODWORD(v68[0]) * v43 / v41 - v72);
  v50 = (unsigned int)(v49 >> 31);
  LODWORD(v50) = v49 % v41;
  v51 = (float)(v38 * (v47 / v37));
  *(float *)&v77 = v51;
  v52 = (float)(v43 * (v49 / v41));
  *(float *)&v78 = v52;
  v53 = GdipCreateImageAttributes(&v82, v50);
  v75 = -16777216;
  v83 = v53;
  Gdiplus::ImageAttributes::SetWrapMode(&v82, v54, &v75);
  Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v69, this[4]);
  Gdiplus::Graphics::SetPageUnit(&v69);
  v55 = GdipSetPixelOffsetMode(v69, 4);
  Gdiplus::Graphics::SetStatus(&v69, v55);
  v56 = GdipSetCompositingMode(v69, 0);
  Gdiplus::Graphics::SetStatus(&v69, v56);
  v57 = GdipSetCompositingQuality(v69, 4);
  Gdiplus::Graphics::SetStatus(&v69, v57);
  v58 = *((_DWORD *)this + 56);
  v59 = 5;
  if ( (v58 & 1) != 0 && (v51 != (float)v47 || v52 != (float)v49) )
    v59 = (2 * (~(_BYTE)v58 & 2)) | 3u;
  v60 = GdipSetInterpolationMode(v69, v59);
  Gdiplus::Graphics::SetStatus(&v69, v60);
  v84 = v79;
  v86 = v80 - HIDWORD(v79);
  v85 = v23 - v79;
  Gdiplus::Graphics::SetClip(&v69, &v84);
  if ( TrivialRotationAngle )
  {
    Gdiplus::Graphics::TranslateTransform(&v69);
    v62 = GdipRotateWorldTransform(v69, v61, 0);
    Gdiplus::Graphics::SetStatus(&v69, v62);
    v76 = 0;
  }
  if ( !XHDC::ValidateImageDestArea((XHDC *)this, (int)v51, (int)v52) )
  {
    GdipDeleteGraphics(v69);
    GdipDisposeImageAttributes(v82);
    return 0;
  }
  TickCount = GetTickCount();
  do
  {
    v64 = Gdiplus::Graphics::DrawImage(&v69, a6, &v76);
    if ( v64 != 4 )
      break;
    v65 = GetTickCount();
    v66 = v65 - TickCount - 1;
    if ( v65 >= TickCount )
      v66 = v65 - TickCount;
  }
  while ( v66 < 0xFA0 );
  GdipDeleteGraphics(v69);
  GdipDisposeImageAttributes(v82);
  return v64 == 0;
}

```

## disassembly

```asm
0x180b45dd4  mov     rax, rsp
0x180b45dd7  mov     [rax+20h], r9d
0x180b45ddb  mov     [rax+18h], r8d
0x180b45ddf  mov     [rax+10h], edx
0x180b45de2  mov     [rax+8], rcx
0x180b45de6  push    rbp
0x180b45de7  push    rbx
0x180b45de8  push    rsi
0x180b45de9  push    rdi
0x180b45dea  push    r12
0x180b45dec  push    r13
0x180b45dee  push    r14
0x180b45df0  push    r15
0x180b45df2  lea     rbp, [rax-68h]
0x180b45df6  sub     rsp, 128h
0x180b45dfd  mov     edi, [rbp+60h+arg_8]
0x180b45e00  mov     esi, [rbp+60h+arg_10]
0x180b45e06  mov     r12d, [rbp+60h+arg_18]
0x180b45e0d  mov     r15d, [rbp+60h+arg_20]
0x180b45e14  movaps  xmmword ptr [rax-58h], xmm6
0x180b45e18  movaps  xmmword ptr [rax-68h], xmm7
0x180b45e1c  movaps  xmmword ptr [rax-78h], xmm8
0x180b45e21  lea     r14d, [rdi+r12]
0x180b45e25  movaps  xmmword ptr [rax-88h], xmm9
0x180b45e2d  lea     r13d, [rsi+r15]
0x180b45e31  mov     [rbp+60h+var_D0], r14d
0x180b45e35  mov     [rbp+60h+var_CC], r13d
0x180b45e39  movaps  xmmword ptr [rax-98h], xmm10
0x180b45e41  mov     dword ptr [rbp+60h+var_D8], edi
0x180b45e44  mov     dword ptr [rbp+60h+var_D8+4], esi
0x180b45e47  test    r12d, r12d
0x180b45e4a  jle     loc_180B4648B
0x180b45e50  test    r15d, r15d
0x180b45e53  jle     loc_180B4648B
0x180b45e59  mov     rbx, [rbp+60h+arg_0]
0x180b45e5d  mov     rcx, rbx; this
0x180b45e60  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b45e65  mov     rdx, rax
0x180b45e68  test    rax, rax
0x180b45e6b  jz      short loc_180B45ECA
0x180b45e6d  mov     ecx, [rdx]
0x180b45e6f  xor     eax, eax
0x180b45e71  mov     r10d, [rbp+60h+arg_38]
0x180b45e78  mov     [rbp+60h+var_BC], eax
0x180b45e7b  mov     eax, [rdx+4]
0x180b45e7e  lea     r8d, [rcx+rdi]
0x180b45e82  mov     [rsp+160h+var_E8], r10d
0x180b45e87  mov     edi, [rbp+60h+arg_48]
0x180b45e8d  lea     r13d, [rcx+r14]
0x180b45e91  mov     r10d, [rbp+60h+arg_30]
0x180b45e98  lea     ecx, [rsi+r15]
0x180b45e9c  lea     edx, [rax+rsi]
0x180b45e9f  mov     [rsp+160h+var_F8], r8d
0x180b45ea4  mov     esi, [rbp+60h+arg_40]
0x180b45eaa  add     ecx, eax
0x180b45eac  mov     [rbp+60h+var_DC], edx
0x180b45eaf  mov     dword ptr [rbp+60h+var_C8+4], edx
0x180b45eb2  mov     [rbp+60h+var_C0], ecx
0x180b45eb5  mov     [rsp+160h+var_E4], esi
0x180b45eb9  mov     dword ptr [rbp+60h+var_C8], r8d
0x180b45ebd  mov     [rsp+160h+var_100], edi
0x180b45ec1  mov     [rbp+60h+var_E0], r10d
0x180b45ec5  jmp     loc_180B46070
0x180b45eca  mov     rcx, [rbx+70h]; this
0x180b45ece  lea     r8, [rsp+160h+var_E8]; float *
0x180b45ed3  lea     rdx, [rsp+160h+var_100]; float *
0x180b45ed8  mov     [rsp+160h+var_F8], edi
0x180b45edc  mov     [rsp+160h+var_F4], esi
0x180b45ee0  mov     [rsp+160h+var_F0], r14d
0x180b45ee5  mov     [rsp+160h+var_EC], r13d
0x180b45eea  mov     [rsp+160h+var_100], 3F800000h
0x180b45ef2  mov     [rsp+160h+var_E8], 3F800000h
0x180b45efa  call    ?GetScales@CWorldTransform@@QEBAXPEAM0@Z; CWorldTransform::GetScales(float *,float *)
0x180b45eff  movd    xmm0, [rbp+60h+arg_30]
0x180b45f07  movss   xmm6, [rsp+160h+var_100]
0x180b45f0d  movss   xmm8, cs:__real@3f000000
0x180b45f16  cvtdq2ps xmm0, xmm0
0x180b45f19  mulss   xmm0, xmm6
0x180b45f1d  addss   xmm0, xmm8; X
0x180b45f22  call    floorf_0
0x180b45f27  movss   xmm7, [rsp+160h+var_E8]
0x180b45f2d  movaps  xmm9, xmm0
0x180b45f31  movd    xmm0, [rbp+60h+arg_38]
0x180b45f39  cvtdq2ps xmm0, xmm0
0x180b45f3c  mulss   xmm0, xmm7
0x180b45f40  addss   xmm0, xmm8; X
0x180b45f45  call    floorf_0
0x180b45f4a  movaps  xmm10, xmm0
0x180b45f4e  movd    xmm0, [rbp+60h+arg_40]
0x180b45f56  cvtdq2ps xmm0, xmm0
0x180b45f59  mulss   xmm0, xmm6
0x180b45f5d  addss   xmm0, xmm8; X
0x180b45f62  call    floorf_0
0x180b45f67  cvttss2si esi, xmm0
0x180b45f6b  mov     r14d, 1
0x180b45f71  movd    xmm0, [rbp+60h+arg_48]
0x180b45f79  cvtdq2ps xmm0, xmm0
0x180b45f7c  cmp     esi, r14d
0x180b45f7f  cmovl   esi, r14d
0x180b45f83  mov     [rsp+160h+var_E4], esi
0x180b45f87  mulss   xmm0, xmm7
0x180b45f8b  addss   xmm0, xmm8; X
0x180b45f90  call    floorf_0
0x180b45f95  cvttss2si edi, xmm0
0x180b45f99  movd    xmm0, r12d
0x180b45f9e  cvtdq2ps xmm0, xmm0
0x180b45fa1  cmp     edi, r14d
0x180b45fa4  cmovl   edi, r14d
0x180b45fa8  mov     [rsp+160h+var_100], edi
0x180b45fac  mulss   xmm0, xmm6
0x180b45fb0  addss   xmm0, xmm8; X
0x180b45fb5  call    floorf_0
0x180b45fba  cvttss2si r12d, xmm0
0x180b45fbf  movd    xmm0, r15d
0x180b45fc4  cvtdq2ps xmm0, xmm0
0x180b45fc7  cmp     r12d, r14d
0x180b45fca  cmovl   r12d, r14d
0x180b45fce  mulss   xmm0, xmm7
0x180b45fd2  addss   xmm0, xmm8; X
0x180b45fd7  call    floorf_0
0x180b45fdc  cvttss2si r15d, xmm0
0x180b45fe1  lea     rdx, [rsp+160h+var_F8]; struct CRect *
0x180b45fe6  mov     rcx, rbx; this
0x180b45fe9  cmp     r15d, r14d
0x180b45fec  cmovl   r15d, r14d
0x180b45ff0  call    ?TransformRect@XHDC@@IEBAHPEAVCRect@@@Z; XHDC::TransformRect(CRect *)
0x180b45ff5  mov     rax, qword ptr [rsp+160h+var_F8]
0x180b45ffa  lea     rdx, [rbp+60h+var_D8]; struct CRect *
0x180b45ffe  mov     rcx, rbx; this
0x180b46001  mov     qword ptr [rsp+160h+var_F8], rax
0x180b46006  call    ?TransformRect@XHDC@@IEBAHPEAVCRect@@@Z; XHDC::TransformRect(CRect *)
0x180b4600b  test    eax, eax
0x180b4600d  jz      loc_180B4648B
0x180b46013  mov     r9d, dword ptr [rbp+60h+var_D8]
0x180b46017  mov     rcx, rbx; this
0x180b4601a  mov     r13d, [rbp+60h+var_D0]
0x180b4601e  mov     r8d, [rbp+60h+var_CC]
0x180b46022  cvttss2si eax, xmm9
0x180b46027  mov     dword ptr [rbp+60h+var_C8], r9d
0x180b4602b  mov     [rbp+60h+var_E0], eax
0x180b4602e  cvttss2si eax, xmm10
0x180b46033  mov     [rsp+160h+var_E8], eax
0x180b46037  lea     eax, [r9+1]
0x180b4603b  mov     r9d, dword ptr [rbp+60h+var_D8+4]
0x180b4603f  cmp     eax, r13d
0x180b46042  mov     dword ptr [rbp+60h+var_C8+4], r9d
0x180b46046  cmovg   r13d, eax
0x180b4604a  lea     eax, [r9+1]
0x180b4604e  cmp     eax, r8d
0x180b46051  cmovg   r8d, eax
0x180b46055  mov     [rbp+60h+var_C0], r8d
0x180b46059  call    ?GetTrivialRotationAngle@XHDC@@QEBAHXZ; XHDC::GetTrivialRotationAngle(void)
0x180b4605e  mov     [rbp+60h+var_BC], eax
0x180b46061  mov     eax, [rsp+160h+var_F4]
0x180b46065  mov     [rbp+60h+var_DC], eax
0x180b46068  mov     eax, [rsp+160h+var_F8]
0x180b4606c  mov     [rsp+160h+var_F8], eax
0x180b46070  test    esi, esi
0x180b46072  jz      loc_180B4648B
0x180b46078  test    edi, edi
0x180b4607a  jz      loc_180B4648B
0x180b46080  test    r12d, r12d
0x180b46083  jz      loc_180B4648B
0x180b46089  test    r15d, r15d
0x180b4608c  jz      loc_180B4648B
0x180b46092  mov     r11d, [rbp+60h+arg_50]
0x180b46099  test    r11d, r11d
0x180b4609c  jz      loc_180B4648B
0x180b460a2  mov     r10d, [rbp+60h+arg_58]
0x180b460a9  test    r10d, r10d
0x180b460ac  jz      loc_180B4648B
0x180b460b2  mov     edx, esi
0x180b460b4  mov     ecx, r11d
0x180b460b7  call    ??$GreatestCommonDivisor@H@@YAHHH@Z; GreatestCommonDivisor<int>(int,int)
0x180b460bc  mov     r9d, eax
0x180b460bf  mov     ecx, r10d
0x180b460c2  mov     eax, r11d
0x180b460c5  cdq
0x180b460c6  idiv    r9d
0x180b460c9  mov     r14d, eax
0x180b460cc  mov     eax, esi
0x180b460ce  cdq
0x180b460cf  idiv    r9d
0x180b460d2  mov     edx, edi
0x180b460d4  mov     esi, eax
0x180b460d6  call    ??$GreatestCommonDivisor@H@@YAHHH@Z; GreatestCommonDivisor<int>(int,int)
0x180b460db  mov     ecx, [rsp+160h+var_100]
0x180b460df  mov     r9d, eax
0x180b460e2  movd    xmm2, [rsp+160h+var_E4]
0x180b460e8  mov     eax, r10d
0x180b460eb  movd    xmm1, [rbp+60h+var_E0]
0x180b460f0  cdq
0x180b460f1  idiv    r9d
0x180b460f4  movd    xmm6, ecx
0x180b460f8  mov     edi, eax
0x180b460fa  movd    xmm0, r11d
0x180b460ff  cvtdq2ps xmm0, xmm0
0x180b46102  mov     eax, ecx
0x180b46104  cdq
0x180b46105  idiv    r9d
0x180b46108  cvtdq2ps xmm2, xmm2
0x180b4610b  mov     ebx, eax
0x180b4610d  cvtdq2ps xmm1, xmm1
0x180b46110  divss   xmm2, xmm0
0x180b46114  movd    xmm0, r10d
0x180b46119  cvtdq2ps xmm0, xmm0
0x180b4611c  divss   xmm1, xmm2
0x180b46120  cvtdq2ps xmm6, xmm6
0x180b46123  cvttss2si ecx, xmm1
0x180b46127  divss   xmm6, xmm0
0x180b4612b  mov     eax, ecx
0x180b4612d  cdq
0x180b4612e  movd    xmm0, [rsp+160h+var_E8]
0x180b46134  idiv    r14d
0x180b46137  cvtdq2ps xmm0, xmm0
0x180b4613a  sub     ecx, edx
0x180b4613c  mov     [rsp+160h+var_E4], ecx
0x180b46140  divss   xmm0, xmm6
0x180b46144  cvttss2si r8d, xmm0
0x180b46149  movd    xmm0, ecx
0x180b4614d  mov     eax, r8d
0x180b46150  cdq
0x180b46151  idiv    edi
0x180b46153  cvtdq2ps xmm0, xmm0
0x180b46156  sub     r8d, edx
0x180b46159  mov     [rsp+160h+var_100], r8d
0x180b4615e  mulss   xmm0, xmm2; X
0x180b46162  call    ceilf_0
0x180b46167  cvttss2si eax, xmm0
0x180b4616b  mov     ecx, esi
0x180b4616d  movd    xmm0, [rsp+160h+var_100]
0x180b46173  sub     ecx, eax
0x180b46175  mov     eax, [rbp+60h+var_E0]
0x180b46178  dec     eax
0x180b4617a  add     ecx, r12d
0x180b4617d  add     eax, ecx
0x180b4617f  cdq
0x180b46180  idiv    esi
0x180b46182  cvtdq2ps xmm0, xmm0
0x180b46185  mov     r12d, eax
0x180b46188  imul    r12d, r14d
0x180b4618c  mulss   xmm0, xmm6; X
0x180b46190  call    ceilf_0
0x180b46195  cvttss2si ecx, xmm0
0x180b46199  mov     edx, ebx
0x180b4619b  sub     edx, ecx
0x180b4619d  mov     ecx, [rsp+160h+var_E8]
0x180b461a1  add     edx, r15d
0x180b461a4  lea     eax, [rcx-1]
0x180b461a7  add     eax, edx
0x180b461a9  cdq
0x180b461aa  idiv    ebx
0x180b461ac  mov     r15d, eax
0x180b461af  mov     [rbp+60h+var_B8], 0
0x180b461b7  mov     eax, esi
0x180b461b9  imul    r15d, edi
0x180b461bd  imul    eax, [rsp+160h+var_E4]
0x180b461c2  cdq
0x180b461c3  idiv    r14d
0x180b461c6  sub     eax, [rbp+60h+var_E0]
0x180b461c9  add     eax, [rsp+160h+var_F8]
0x180b461cd  movd    xmm8, eax
0x180b461d2  mov     eax, ebx
0x180b461d4  imul    eax, [rsp+160h+var_100]
0x180b461d9  cvtdq2ps xmm8, xmm8
0x180b461dd  cdq
0x180b461de  idiv    edi
0x180b461e0  movss   dword ptr [rbp+60h+var_D8], xmm8
0x180b461e6  sub     eax, ecx
0x180b461e8  lea     rcx, [rbp+60h+var_B8]
0x180b461ec  add     eax, [rbp+60h+var_DC]
0x180b461ef  movd    xmm9, eax
0x180b461f4  mov     eax, r12d
0x180b461f7  cdq
0x180b461f8  idiv    r14d
0x180b461fb  cvtdq2ps xmm9, xmm9
0x180b461ff  imul    eax, esi
0x180b46202  movss   dword ptr [rbp+60h+var_D8+4], xmm9
0x180b46208  movd    xmm6, eax
0x180b4620c  mov     eax, r15d
0x180b4620f  cdq
0x180b46210  idiv    edi
0x180b46212  cvtdq2ps xmm6, xmm6
0x180b46215  imul    eax, ebx
0x180b46218  movss   [rbp+60h+var_D0], xmm6
0x180b4621d  movd    xmm7, eax
0x180b46221  cvtdq2ps xmm7, xmm7
0x180b46224  movss   [rbp+60h+var_CC], xmm7
0x180b46229  call    cs:__imp_GdipCreateImageAttributes
0x180b46230  nop     dword ptr [rax+rax+00h]
0x180b46235  lea     r8, [rbp+60h+var_DC]
0x180b46239  mov     [rbp+60h+var_DC], 0FF000000h
0x180b46240  lea     rcx, [rbp+60h+var_B8]
0x180b46244  mov     [rbp+60h+var_B0], eax
0x180b46247  call    ?SetWrapMode@ImageAttributes@Gdiplus@@QEAA?AW4Status@2@W4WrapMode@2@AEBVColor@2@H@Z; Gdiplus::ImageAttributes::SetWrapMode(Gdiplus::WrapMode,Gdiplus::Color const &,int)
0x180b4624c  mov     rbx, [rbp+60h+arg_0]
0x180b46250  lea     rcx, [rsp+160h+var_F8]; this
0x180b46255  mov     rdx, [rbx+20h]; HDC
0x180b46259  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x180b4625e  lea     rcx, [rsp+160h+var_F8]
  ... truncated ...
```

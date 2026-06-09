# CDrawingManager::DrawLineA(double,double,double,double,ulong)

- ea: `0x18005b500`
- end: `0x18005bf90`
- name: `?DrawLineA@CDrawingManager@@QEAAXNNNNK@Z`
- size: `2704`
- prototype: `void __fastcall(CDrawingManager *this, long double x1, long double y1, long double x2, long double y2, unsigned int clrLine)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18001d090`
- `0x180058150`
- `0x18005b500`
- `0x18005dd50`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b64d`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b669`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b68a`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b69e`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b6b0`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b6cc`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b6f4`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b716`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b736`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b74a`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b75c`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b778`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005bd54`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005bd66`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b64d`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b669`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b68a`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b69e`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b6b0`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b6cc`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b6f4`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b716`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b736`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b74a`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b75c`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005b778`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005bd54`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005bd66`
- `api-ms-win-crt-math-l1-1-0!fabs` at `0x18005b5c8`
- `api-ms-win-crt-math-l1-1-0!fabs` at `0x18005b5d5`
- `api-ms-win-crt-math-l1-1-0!fabs` at `0x18005b5c8`
- `api-ms-win-crt-math-l1-1-0!fabs` at `0x18005b5d5`
- `GDI32!DeleteDC` at `0x18005bf24`
- `GDI32!DeleteDC` at `0x18005bf24`
- `GDI32!CreateCompatibleBitmap` at `0x18005b903`
- `GDI32!CreateCompatibleBitmap` at `0x18005b903`
- `GDI32!DeleteObject` at `0x18005becb`
- `GDI32!DeleteObject` at `0x18005becb`
- `GDI32!SelectObject` at `0x18005b93e`
- `GDI32!SelectObject` at `0x18005b988`
- `GDI32!SelectObject` at `0x18005beb9`
- `GDI32!SelectObject` at `0x18005b93e`
- `GDI32!SelectObject` at `0x18005b988`
- `GDI32!SelectObject` at `0x18005beb9`
- `GDI32!CreateCompatibleDC` at `0x18005b8ca`
- `GDI32!CreateCompatibleDC` at `0x18005b8ca`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=3
void __fastcall CDrawingManager::DrawLineA(
        CDrawingManager *this,
        double x1,
        double y1,
        double x2,
        double y2,
        unsigned int clrLine)
{
  double v6; // xmm10_8
  double v7; // xmm12_8
  double v8; // xmm11_8
  double v9; // xmm7_8
  double v10; // xmm13_8
  double v11; // xmm9_8
  char v12; // di
  double v13; // xmm6_8
  double v14; // xmm0_8
  double v15; // xmm9_8
  double v16; // xmm9_8
  double v17; // xmm14_8
  double v18; // xmm7_8
  double v19; // xmm12_8
  double v20; // xmm14_8
  double v21; // xmm15_8
  double v22; // xmm7_8
  int v23; // r13d
  double v24; // xmm13_8
  double v25; // xmm15_8
  int v26; // r9d
  int v27; // r12d
  int v28; // r15d
  int v29; // r11d
  int v30; // esi
  int v31; // ebx
  int v32; // r10d
  int v33; // edx
  int v34; // r8d
  int v35; // eax
  int v36; // esi
  int v37; // ebx
  int v38; // esi
  CDrawingManager *v39; // r13
  CDC *m_dc; // rax
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v44; // rax
  HBITMAP__ *v45; // rax
  _DWORD *v46; // r13
  int v47; // r10d
  int v48; // r11d
  int cy; // ebx
  double v50; // xmm10_8
  double v51; // xmm8_8
  double v52; // xmm11_8
  double v53; // xmm0_8
  int cx; // r14d
  double v55; // xmm2_8
  __int64 v56; // r8
  int v57; // r10d
  __int64 v58; // r8
  int v59; // r8d
  __int64 v60; // r9
  int v61; // r8d
  __int64 v62; // r9
  int v63; // r8d
  double v64; // xmm6_8
  int v65; // edx
  int v66; // ecx
  int v67; // eax
  double v68; // xmm6_8
  int v69; // ebx
  int v70; // esi
  __int64 v71; // r8
  __int64 v72; // rcx
  int v73; // edx
  HGDIOBJ v74; // rax
  bool v75; // zf
  HDC v76; // rax
  int v77; // [rsp+38h] [rbp-D0h]
  int v78; // [rsp+38h] [rbp-D0h]
  int v79; // [rsp+40h] [rbp-C8h]
  int size; // [rsp+48h] [rbp-C0h]
  int sizea; // [rsp+48h] [rbp-C0h]
  CSize v82; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v83; // [rsp+58h] [rbp-B0h]
  _BYTE rect[24]; // [rsp+60h] [rbp-A8h] OVERLAPPED BYREF
  CBitmap bmpMem; // [rsp+78h] [rbp-90h] BYREF
  CDC dcMem; // [rsp+88h] [rbp-80h] BYREF
  unsigned int *pBits; // [rsp+A8h] [rbp-60h]
  void *v88; // [rsp+B0h] [rbp-58h] BYREF
  CDrawingManager *v89; // [rsp+B8h] [rbp-50h]
  CGdiObject *v90; // [rsp+C0h] [rbp-48h]
  HGDIOBJ ho; // [rsp+C8h] [rbp-40h]
  CRect rectSrc; // [rsp+D0h] [rbp-38h] BYREF

  v6 = x2;
  v7 = y1;
  v8 = x1;
  v89 = this;
  if ( clrLine != -1 )
  {
    v9 = x2 - x1;
    v10 = y2;
    v11 = y2 - y1;
    if ( x2 - x1 != 0.0 || v11 != 0.0 )
    {
      v12 = 0;
      v13 = fabs(v9);
      if ( fabs(v11) >= v13 )
      {
        v12 = 1;
        v8 = y1;
        v7 = x1;
        v6 = y2;
        v10 = x2;
        v9 = y2 - y1;
        v11 = x2 - x1;
      }
      if ( v8 > v6 )
      {
        v14 = v8;
        v8 = v6;
        v6 = v14;
        v15 = v7;
        v7 = v10;
        v10 = v15;
        v9 = v14 - v8;
        v11 = v15 - v7;
      }
      v16 = v11 / v9;
      v17 = (floor(v8 + 0.5) - v8) * v16 + v7;
      v18 = 1.0 - (v8 + 0.5 - floor(v8 + 0.5));
      LODWORD(v83) = (int)floor(v8 + 0.5);
      LODWORD(bmpMem.__vftable) = (int)floor(v17);
      v19 = (1.0 - (v17 - floor(v17))) * v18;
      *(double *)&rectSrc.left = (v17 - floor(v17)) * v18;
      v20 = v17 + v16;
      v21 = (floor(v6 + 0.5) - v6) * v16 + v10;
      v22 = 1.0 - (v6 - 0.5 - floor(v6 - 0.5));
      v23 = (int)floor(v6 + 0.5);
      v77 = v23;
      *(_DWORD *)rect = (int)floor(v21);
      v24 = (1.0 - (v21 - floor(v21))) * v22;
      v25 = (v21 - floor(v21)) * v22;
      v26 = v83;
      v27 = v83;
      *(_DWORD *)&rect[8] = v83;
      v28 = (int)bmpMem.__vftable;
      *(_DWORD *)&rect[12] = bmpMem.__vftable;
      v79 = v23;
      size = *(_DWORD *)rect;
      v29 = v83;
      v30 = v83;
      if ( v12 )
      {
        *(_DWORD *)&rect[8] = bmpMem.__vftable;
        *(_DWORD *)&rect[12] = v83;
        *(_DWORD *)&rect[16] = *(_DWORD *)rect;
        *(_DWORD *)&rect[20] = v23;
        v29 = (int)bmpMem.__vftable;
        v30 = (int)bmpMem.__vftable;
        size = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&rect[8], 12));
        v79 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&rect[8], 8));
        v28 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&rect[8], 4));
        v27 = _mm_cvtsi128_si32(*(__m128i *)&rect[8]);
      }
      v31 = v23;
      if ( !v12 )
        v31 = *(_DWORD *)rect;
      v32 = *(_DWORD *)rect;
      if ( !v12 )
        v32 = v23;
      v33 = v83;
      if ( !v12 )
        v33 = (int)bmpMem.__vftable;
      v34 = v23;
      if ( !v12 )
      {
        v34 = *(_DWORD *)rect;
        v26 = (int)bmpMem.__vftable;
      }
      v35 = *(_DWORD *)rect;
      if ( !v12 )
        v35 = v23;
      if ( v29 <= v35 )
      {
        v30 = v32;
      }
      else
      {
        v27 = v79;
        *(_DWORD *)&rect[8] = v79;
        *(_DWORD *)&rect[16] = v30;
      }
      if ( v26 > v34 )
      {
        v28 = size;
        *(_DWORD *)&rect[12] = size;
        v31 = v33;
      }
      v36 = v30 + 1;
      *(_DWORD *)&rect[16] = v36;
      *(_DWORD *)&rect[20] = v31 + 1;
      if ( v12 )
        *(_DWORD *)&rect[16] = ++v36;
      else
        *(_DWORD *)&rect[20] = v31 + 2;
      if ( !v12 )
        ++v31;
      v37 = v31 - v28 + 1;
      v38 = v36 - v27;
      v82.cx = v38;
      v82.cy = v37;
      if ( v38 )
      {
        if ( v37 )
        {
          dcMem.m_hDC = (HDC__ *)CDC::`vftable';
          *(_OWORD *)&dcMem.m_hAttribDC = 0;
          LODWORD(pBits) = 0;
          v39 = v89;
          m_dc = v89->m_dc;
          if ( m_dc )
            m_hDC = m_dc->m_hDC;
          else
            m_hDC = 0;
          CompatibleDC = CreateCompatibleDC(m_hDC);
          if ( CDC::Attach((CDC *)&dcMem.m_hDC, CompatibleDC) )
          {
            dcMem.__vftable = 0;
            bmpMem.m_hObject = (void *)CBitmap::`vftable';
            CompatibleBitmap = CreateCompatibleBitmap(v39->m_dc->m_hDC, v38, v37);
            if ( CGdiObject::Attach((CGdiObject *)&bmpMem.m_hObject, CompatibleBitmap) )
            {
              v44 = SelectObject(dcMem.m_hAttribDC, dcMem.__vftable);
              v90 = CGdiObject::FromHandle(v44);
              if ( !v90 )
                AfxThrowInvalidArgException();
              v45 = CDrawingManager::CreateBitmap_32(&v82, &v88);
              ho = v45;
              if ( v45 )
              {
                v46 = v88;
                if ( v88 )
                {
                  SelectObject(dcMem.m_hAttribDC, v45);
                  sizea = BYTE1(clrLine);
                  LODWORD(v88) = BYTE2(clrLine);
                  v47 = (int)(v19 * 255.0) << 16;
                  v48 = v83;
                  cy = v82.cy;
                  v50 = (double)sizea;
                  v51 = (double)(unsigned __int8)clrLine;
                  v52 = (double)BYTE2(clrLine);
                  v53 = (double)sizea * v19;
                  cx = v82.cx;
                  v55 = *(double *)&rectSrc.left;
                  if ( v12 )
                  {
                    v56 = LODWORD(bmpMem.__vftable) - v27 + (__int64)(v82.cx * (v28 - (int)v83 + v82.cy - 1));
                    v46[v56] = (unsigned __int8)(int)(v52 * v19)
                             | ((unsigned __int8)(int)(v51 * v19) << 16)
                             | ((v47 | (unsigned __int8)(int)v53) << 8);
                    v46[v56 + 1] = (unsigned __int8)(int)(v52 * v55)
                                 | ((unsigned __int8)(int)(v51 * v55) << 16)
                                 | ((((int)(v55 * 255.0) << 16) | (unsigned __int8)(int)(v50 * v55)) << 8);
                    v57 = v77;
                    v58 = *(_DWORD *)rect - v27 + (__int64)(cx * (v28 - v77 + cy - 1));
                    v46[v58] = (unsigned __int8)(int)(v52 * v24)
                             | ((unsigned __int8)(int)(v51 * v24) << 16)
                             | ((((int)(v24 * 255.0) << 16) | (unsigned __int8)(int)(v50 * v24)) << 8);
                    v46[v58 + 1] = (unsigned __int8)(int)(v52 * v25)
                                 | ((unsigned __int8)(int)(v51 * v25) << 16)
                                 | ((((int)(v25 * 255.0) << 16) | (unsigned __int8)(int)(v50 * v25)) << 8);
                  }
                  else
                  {
                    v59 = v28 - LODWORD(bmpMem.__vftable);
                    v60 = (int)v83 - v27;
                    v46[v60 + v82.cx * (v28 - LODWORD(bmpMem.__vftable) + v82.cy - 1)] = (unsigned __int8)(int)(v52 * v19)
                                                                                       | ((unsigned __int8)(int)(v51 * v19) << 16)
                                                                                       | ((v47
                                                                                         | (unsigned __int8)(int)v53) << 8);
                    v46[v60 + cx * (v59 + cy - 2)] = (unsigned __int8)(int)(v52 * v55)
                                                   | ((unsigned __int8)(int)(v51 * v55) << 16)
                                                   | ((((int)(v55 * 255.0) << 16) | (unsigned __int8)(int)(v50 * v55)) << 8);
                    v61 = v28 - *(_DWORD *)rect;
                    v57 = v77;
                    v62 = v77 - v27;
                    v46[v62 + cx * (v61 + cy - 1)] = (unsigned __int8)(int)(v52 * v24)
                                                   | ((unsigned __int8)(int)(v51 * v24) << 16)
                                                   | ((((int)(v24 * 255.0) << 16) | (unsigned __int8)(int)(v50 * v24)) << 8);
                    v46[v62 + cx * (v61 + cy - 2)] = (unsigned __int8)(int)(v52 * v25)
                                                   | ((unsigned __int8)(int)(v51 * v25) << 16)
                                                   | ((((int)(v25 * 255.0) << 16) | (unsigned __int8)(int)(v50 * v25)) << 8);
                  }
                  v63 = v48 + 1;
                  if ( v48 + 1 <= v57 - 1 )
                  {
                    v83 = v63 - v27;
                    *(_QWORD *)rect = cx * (cy + v28 - v63 - 1);
                    bmpMem.__vftable = (CBitmap_vtbl *)-cx;
                    *(_QWORD *)&rectSrc.left = (unsigned int)(v57 - 1 - v48);
                    do
                    {
                      v64 = v20 - floor(v20);
                      v78 = (int)floor(v20);
                      v65 = (int)(v52 * v64);
                      v66 = (int)(v50 * v64);
                      v67 = (int)(v51 * v64);
                      v68 = v64 * 255.0;
                      v69 = (unsigned __int8)v65
                          | ((unsigned __int8)v67 << 16)
                          | (((unsigned __int8)v66 | ((int)v68 << 16)) << 8);
                      v70 = (unsigned __int8)((_BYTE)v88 - v65)
                          | ((unsigned __int8)(clrLine - v67) << 16)
                          | ((unsigned __int8)(sizea - v66) << 8)
                          | (-16777216 - ((int)v68 << 24));
                      v71 = v83;
                      if ( v12 )
                      {
                        v72 = *(_QWORD *)rect + v78 - v27;
                        v46[v72] = v70;
                        v46[v72 + 1] = v69;
                      }
                      else
                      {
                        v73 = v82.cy + v28 - v78;
                        v46[v83 + cx * (v73 - 1)] = v70;
                        v46[v71 + cx * (v73 - 2)] = v69;
                      }
                      v20 = v20 + v16;
                      *(_QWORD *)rect += bmpMem.__vftable;
                      v83 = v71 + 1;
                      --*(_QWORD *)&rectSrc.left;
                    }
                    while ( *(_QWORD *)&rectSrc.left );
                  }
                  *(_QWORD *)&rectSrc.left = 0;
                  rectSrc.right = cx;
                  rectSrc.bottom = v82.cy;
                  CDrawingManager::DrawAlpha(v89, v89->m_dc, (const CRect *)&rect[8], (CDC *)&dcMem.m_hDC, &rectSrc);
                  v74 = SelectObject(dcMem.m_hAttribDC, v90->m_hObject);
                  CGdiObject::FromHandle(v74);
                  DeleteObject(ho);
                  bmpMem.m_hObject = (void *)CBitmap::`vftable';
                  CGdiObject::~CGdiObject((CGdiObject *)&bmpMem.m_hObject);
                  v75 = dcMem.m_hAttribDC == 0;
                  goto LABEL_53;
                }
              }
              bmpMem.m_hObject = (void *)CBitmap::`vftable';
              CGdiObject::~CGdiObject((CGdiObject *)&bmpMem.m_hObject);
            }
            else
            {
              bmpMem.m_hObject = (void *)CBitmap::`vftable';
              CGdiObject::~CGdiObject((CGdiObject *)&bmpMem.m_hObject);
            }
          }
          v75 = dcMem.m_hAttribDC == 0;
LABEL_53:
          dcMem.m_hDC = (HDC__ *)CDC::`vftable';
          if ( !v75 )
          {
            v76 = CDC::Detach((CDC *)&dcMem.m_hDC);
            DeleteDC(v76);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18005b500  mov     rax, rsp
0x18005b503  push    rbp
0x18005b504  push    rbx
0x18005b505  push    rsi
0x18005b506  push    rdi
0x18005b507  push    r12
0x18005b509  push    r13
0x18005b50b  push    r14
0x18005b50d  push    r15
0x18005b50f  lea     rbp, [rax-0C8h]
0x18005b516  sub     rsp, 188h
0x18005b51d  movaps  xmmword ptr [rax-58h], xmm6
0x18005b521  movaps  xmmword ptr [rax-68h], xmm7
0x18005b525  movaps  xmmword ptr [rax-78h], xmm8
0x18005b52a  movaps  xmmword ptr [rax-88h], xmm9
0x18005b532  movaps  xmmword ptr [rax-98h], xmm10
0x18005b53a  movaps  xmmword ptr [rax-0A8h], xmm11
0x18005b542  movaps  xmmword ptr [rax-0B8h], xmm12
0x18005b54a  movaps  xmmword ptr [rax-0C8h], xmm13
0x18005b552  movaps  xmmword ptr [rax-0D8h], xmm14
0x18005b55a  movaps  xmmword ptr [rax-0E8h], xmm15
0x18005b562  mov     rax, cs:__security_cookie
0x18005b569  xor     rax, rsp
0x18005b56c  mov     [rbp+0C0h+var_E8], rax
0x18005b570  movaps  xmm10, xmm3
0x18005b574  movaps  xmm12, xmm2
0x18005b578  movaps  xmm11, xmm1
0x18005b57c  mov     [rbp+0C0h+var_110], this
0x18005b580  mov     r14d, [rbp+0C0h+arg_28]
0x18005b587  cmp     r14d, 0FFFFFFFFh
0x18005b58b  jz      loc_18005BF2B
0x18005b591  movaps  xmm7, xmm3
0x18005b594  subsd   xmm7, xmm1
0x18005b598  movsd   xmm13, [rbp+0C0h+arg_20]
0x18005b5a1  movaps  xmm9, xmm13
0x18005b5a5  subsd   xmm9, xmm2
0x18005b5aa  xorps   xmm0, xmm0
0x18005b5ad  ucomisd xmm7, xmm0
0x18005b5b1  jp      short loc_18005B5C2
0x18005b5b3  jnz     short loc_18005B5C2
0x18005b5b5  ucomisd xmm9, xmm0
0x18005b5ba  jp      short loc_18005B5C2
0x18005b5bc  jz      loc_18005BF2B
0x18005b5c2  xor     dil, dil
0x18005b5c5  movaps  xmm0, xmm7; X
0x18005b5c8  call    cs:__imp_fabs
0x18005b5ce  movaps  xmm6, xmm0
0x18005b5d1  movaps  xmm0, xmm9; X
0x18005b5d5  call    cs:__imp_fabs
0x18005b5db  comisd  xmm0, xmm6
0x18005b5df  jb      short loc_18005B607
0x18005b5e1  mov     dil, 1
0x18005b5e4  movaps  xmm0, xmm11
0x18005b5e8  movaps  xmm11, xmm12
0x18005b5ec  movaps  xmm12, xmm0
0x18005b5f0  movaps  xmm1, xmm10
0x18005b5f4  movaps  xmm10, xmm13
0x18005b5f8  movaps  xmm13, xmm1
0x18005b5fc  movaps  xmm0, xmm7
0x18005b5ff  movaps  xmm7, xmm9
0x18005b603  movaps  xmm9, xmm0
0x18005b607  comisd  xmm11, xmm10
0x18005b60c  jbe     short loc_18005B633
0x18005b60e  movaps  xmm0, xmm11
0x18005b612  movaps  xmm11, xmm10
0x18005b616  movaps  xmm10, xmm0
0x18005b61a  movaps  xmm9, xmm12
0x18005b61e  movaps  xmm12, xmm13
0x18005b622  movaps  xmm13, xmm9
0x18005b626  movaps  xmm7, xmm0
0x18005b629  subsd   xmm7, xmm11
0x18005b62e  subsd   xmm9, xmm12
0x18005b633  divsd   xmm9, xmm7
0x18005b638  movaps  xmm6, xmm11
0x18005b63c  movsd   xmm8, cs:__real@3fe0000000000000
0x18005b645  addsd   xmm6, xmm8
0x18005b64a  movaps  xmm0, xmm6; X
0x18005b64d  call    cs:__imp_floor
0x18005b653  movaps  xmm14, xmm0
0x18005b657  subsd   xmm14, xmm11
0x18005b65c  mulsd   xmm14, xmm9
0x18005b661  addsd   xmm14, xmm12
0x18005b666  movaps  xmm0, xmm6; X
0x18005b669  call    cs:__imp_floor
0x18005b66f  movaps  xmm1, xmm6
0x18005b672  subsd   xmm1, xmm0
0x18005b676  movsd   xmm12, cs:__real@3ff0000000000000
0x18005b67f  movaps  xmm7, xmm12
0x18005b683  subsd   xmm7, xmm1
0x18005b687  movaps  xmm0, xmm6; X
0x18005b68a  call    cs:__imp_floor
0x18005b690  cvttsd2si r11d, xmm0
0x18005b695  mov     dword ptr [rsp+1C0h+var_170], r11d
0x18005b69a  movaps  xmm0, xmm14; X
0x18005b69e  call    cs:__imp_floor
0x18005b6a4  cvttsd2si ecx, xmm0
0x18005b6a8  mov     dword ptr [rsp+1C0h+bmpMem.__vftable], ecx
0x18005b6ac  movaps  xmm0, xmm14; X
0x18005b6b0  call    cs:__imp_floor
0x18005b6b6  movaps  xmm1, xmm14
0x18005b6ba  subsd   xmm1, xmm0
0x18005b6be  subsd   xmm12, xmm1
0x18005b6c3  mulsd   xmm12, xmm7
0x18005b6c8  movaps  xmm0, xmm14; X
0x18005b6cc  call    cs:__imp_floor
0x18005b6d2  movaps  xmm1, xmm14
0x18005b6d6  subsd   xmm1, xmm0
0x18005b6da  mulsd   xmm1, xmm7
0x18005b6de  movsd   qword ptr [rbp+0C0h+var_F8.left], xmm1
0x18005b6e3  addsd   xmm14, xmm9
0x18005b6e8  movaps  xmm6, xmm10
0x18005b6ec  addsd   xmm6, xmm8
0x18005b6f1  movaps  xmm0, xmm6; X
0x18005b6f4  call    cs:__imp_floor
0x18005b6fa  movaps  xmm15, xmm0
0x18005b6fe  subsd   xmm15, xmm10
0x18005b703  mulsd   xmm15, xmm9
0x18005b708  addsd   xmm15, xmm13
0x18005b70d  subsd   xmm10, xmm8
0x18005b712  movaps  xmm0, xmm10; X
0x18005b716  call    cs:__imp_floor
0x18005b71c  subsd   xmm10, xmm0
0x18005b721  movsd   xmm13, cs:__real@3ff0000000000000
0x18005b72a  movaps  xmm7, xmm13
0x18005b72e  subsd   xmm7, xmm10
0x18005b733  movaps  xmm0, xmm6; X
0x18005b736  call    cs:__imp_floor
0x18005b73c  cvttsd2si r13d, xmm0
0x18005b741  mov     [rsp+1C0h+var_190], r13d
0x18005b746  movaps  xmm0, xmm15; X
0x18005b74a  call    cs:__imp_floor
0x18005b750  cvttsd2si ecx, xmm0
0x18005b754  mov     [rsp+1C0h+rect.left], ecx
0x18005b758  movaps  xmm0, xmm15; X
0x18005b75c  call    cs:__imp_floor
0x18005b762  movaps  xmm1, xmm15
0x18005b766  subsd   xmm1, xmm0
0x18005b76a  subsd   xmm13, xmm1
0x18005b76f  mulsd   xmm13, xmm7
0x18005b774  movaps  xmm0, xmm15; X
0x18005b778  call    cs:__imp_floor
0x18005b77e  subsd   xmm15, xmm0
0x18005b783  mulsd   xmm15, xmm7
0x18005b788  mov     r9d, dword ptr [rsp+1C0h+var_170]
0x18005b78d  mov     r12d, r9d
0x18005b790  mov     [rsp+1C0h+rect.right], r9d
0x18005b795  mov     eax, dword ptr [rsp+1C0h+bmpMem.__vftable]
0x18005b799  mov     r15d, eax
0x18005b79c  mov     [rsp+1C0h+rect.bottom], eax
0x18005b7a0  mov     [rsp+1C0h+var_188], r13d
0x18005b7a5  mov     ecx, [rsp+1C0h+rect.left]
0x18005b7a9  mov     [rsp+1C0h+size.cx], ecx
0x18005b7ad  mov     r11d, r9d
0x18005b7b0  mov     esi, r9d
0x18005b7b3  test    dil, dil
0x18005b7b6  jz      short loc_18005B80A
0x18005b7b8  mov     [rsp+1C0h+rect.right], eax
0x18005b7bc  mov     [rsp+1C0h+rect.bottom], r9d
0x18005b7c1  mov     dword ptr [rsp+1C0h+var_158], ecx
0x18005b7c5  mov     dword ptr [rsp+1C0h+var_158+4], r13d
0x18005b7ca  movaps  xmm2, xmmword ptr [rsp+1C0h+rect.right]
0x18005b7cf  movaps  xmmword ptr [rsp+1C0h+rect.right], xmm2
0x18005b7d4  mov     r11d, eax
0x18005b7d7  mov     esi, eax
0x18005b7d9  movdqa  xmm0, xmm2
0x18005b7dd  psrldq  xmm0, 0Ch
0x18005b7e2  movd    [rsp+1C0h+size.cx], xmm0
0x18005b7e8  movdqa  xmm1, xmm2
0x18005b7ec  psrldq  xmm1, 8
0x18005b7f1  movd    [rsp+1C0h+var_188], xmm1
0x18005b7f7  movdqa  xmm0, xmm2
0x18005b7fb  psrldq  xmm0, 4
0x18005b800  movd    r15d, xmm0
0x18005b805  movd    r12d, xmm2
0x18005b80a  mov     ebx, r13d
0x18005b80d  test    dil, dil
0x18005b810  cmovz   ebx, ecx
0x18005b813  mov     r10d, ecx
0x18005b816  cmovz   r10d, r13d
0x18005b81a  mov     edx, r9d
0x18005b81d  cmovz   edx, eax
0x18005b820  mov     r8d, r13d
0x18005b823  cmovz   r8d, ecx
0x18005b827  cmovz   r9d, eax
0x18005b82b  mov     eax, ecx
0x18005b82d  cmovz   eax, r13d
0x18005b831  cmp     r11d, eax
0x18005b834  jle     short loc_18005B844
0x18005b836  mov     r12d, [rsp+1C0h+var_188]
0x18005b83b  mov     [rsp+1C0h+rect.right], r12d
0x18005b840  mov     dword ptr [rsp+1C0h+var_158], esi
0x18005b844  cmovle  esi, r10d
0x18005b848  cmp     r9d, r8d
0x18005b84b  jle     short loc_18005B859
0x18005b84d  mov     r15d, [rsp+1C0h+size.cx]
0x18005b852  mov     [rsp+1C0h+rect.bottom], r15d
0x18005b857  mov     ebx, edx
0x18005b859  inc     esi
0x18005b85b  mov     dword ptr [rsp+1C0h+var_158], esi
0x18005b85f  lea     ecx, [rbx+1]
0x18005b862  mov     dword ptr [rsp+1C0h+var_158+4], ecx
0x18005b866  test    dil, dil
0x18005b869  jz      short loc_18005B873
0x18005b86b  inc     esi
0x18005b86d  mov     dword ptr [rsp+1C0h+var_158], esi
0x18005b871  jmp     short loc_18005B87A
0x18005b873  lea     eax, [this+1]
0x18005b876  mov     dword ptr [rsp+1C0h+var_158+4], eax
0x18005b87a  test    dil, dil
0x18005b87d  cmovz   ebx, ecx
0x18005b880  sub     ebx, r15d
0x18005b883  inc     ebx
0x18005b885  sub     esi, r12d
0x18005b888  mov     [rsp+1C0h+var_178.cx], esi
0x18005b88c  mov     [rsp+1C0h+var_178.cy], ebx
0x18005b890  jz      loc_18005BF2B
0x18005b896  test    ebx, ebx
0x18005b898  jz      loc_18005BF2B
0x18005b89e  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18005b8a5  mov     [rbp+0C0h+dcMem.m_hDC], rax
0x18005b8a9  xorps   xmm0, xmm0
0x18005b8ac  movdqu  xmmword ptr [rbp+0C0h+dcMem.m_hAttribDC], xmm0
0x18005b8b1  and     dword ptr [rbp+0C0h+pBits], 0
0x18005b8b5  mov     r13, [rbp+0C0h+var_110]
0x18005b8b9  mov     rax, [r13+8]
0x18005b8bd  test    rax, rax
0x18005b8c0  jnz     short loc_18005B8C6
0x18005b8c2  xor     ecx, ecx
0x18005b8c4  jmp     short loc_18005B8CA
0x18005b8c6  mov     this, [rax+8]; hdc
0x18005b8ca  call    cs:__imp_CreateCompatibleDC
0x18005b8d0  mov     rdx, rax; hDC
0x18005b8d3  lea     this, [rbp+0C0h+dcMem.m_hDC]; this
0x18005b8d7  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18005b8dc  test    eax, eax
0x18005b8de  jnz     short loc_18005B8E5
0x18005b8e0  jmp     loc_18005BF06
0x18005b8e5  and     [rbp+0C0h+dcMem.__vftable], 0
0x18005b8ea  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005b8f1  mov     [rsp+1C0h+bmpMem.m_hObject], rax
0x18005b8f6  mov     this, [r13+8]
0x18005b8fa  mov     r8d, ebx; cy
0x18005b8fd  mov     edx, esi; cx
0x18005b8ff  mov     this, [this+8]; hdc
0x18005b903  call    cs:__imp_CreateCompatibleBitmap
0x18005b909  mov     rdx, rax; hObject
0x18005b90c  lea     this, [rsp+1C0h+bmpMem.m_hObject]; this
0x18005b911  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18005b916  test    eax, eax
0x18005b918  jnz     short loc_18005B936
0x18005b91a  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005b921  mov     [rsp+1C0h+bmpMem.m_hObject], rax
0x18005b926  lea     this, [rsp+1C0h+bmpMem.m_hObject]; this
0x18005b92b  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005b930  nop
0x18005b931  jmp     loc_18005BF06
0x18005b936  mov     rdx, [rbp+0C0h+dcMem.__vftable]; h
0x18005b93a  mov     this, [rbp+0C0h+dcMem.m_hAttribDC]; hdc
0x18005b93e  call    cs:__imp_SelectObject
0x18005b944  mov     this, rax; h
0x18005b947  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18005b94c  mov     [rbp+0C0h+var_108], rax
0x18005b950  test    rax, rax
0x18005b953  jz      loc_18005BF8A
0x18005b959  lea     rdx, [rbp+0C0h+var_118]; pBits
0x18005b95d  lea     this, [rsp+1C0h+var_178]; size
0x18005b962  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x18005b967  mov     [rbp+0C0h+ho], rax
0x18005b96b  test    rax, rax
0x18005b96e  jz      loc_18005BEEF
0x18005b974  mov     r13, [rbp+0C0h+var_118]
0x18005b978  test    r13, r13
0x18005b97b  jz      loc_18005BEEF
0x18005b981  mov     rdx, rax; h
0x18005b984  mov     this, [rbp+0C0h+dcMem.m_hAttribDC]; hdc
0x18005b988  call    cs:__imp_SelectObject
0x18005b98e  movzx   r9d, r14b
0x18005b992  mov     [rsp+1C0h+var_188], r9d
0x18005b997  movzx   edx, r14w
0x18005b99b  shr     edx, 8
0x18005b99e  mov     [rsp+1C0h+size.cx], edx
0x18005b9a2  shr     r14d, 10h
0x18005b9a6  movzx   esi, r14b
0x18005b9aa  mov     dword ptr [rbp+0C0h+var_118], esi
0x18005b9ad  movaps  xmm0, xmm12
0x18005b9b1  movsd   xmm7, cs:__real@406fe00000000000
0x18005b9b9  mulsd   xmm0, xmm7
0x18005b9bd  cvttsd2si r10d, xmm0
0x18005b9c2  shl     r10d, 10h
0x18005b9c6  mov     r11d, dword ptr [rsp+1C0h+var_170]
0x18005b9cb  mov     ebx, [rsp+1C0h+var_178.cy]
0x18005b9cf  movd    xmm10, edx
0x18005b9d4  movd    xmm8, r9d
0x18005b9d9  movd    xmm11, esi
0x18005b9de  cvtdq2pd xmm10, xmm10
0x18005b9e3  cvtdq2pd xmm8, xmm8
0x18005b9e8  cvtdq2pd xmm11, xmm11
0x18005b9ed  movaps  xmm0, xmm10
0x18005b9f1  mulsd   xmm0, xmm12
0x18005b9f6  mov     r14d, [rsp+1C0h+var_178.cx]
  ... truncated ...
```

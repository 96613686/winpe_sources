# CMFCToolBarImages::SmoothResize(double)

- ea: `0x180178c70`
- end: `0x180179372`
- name: `?SmoothResize@CMFCToolBarImages@@QEAAHN@Z`
- size: `1794`
- prototype: `int __fastcall(CMFCToolBarImages *this, long double dblImageScale)`
- caller_count: `12`
- callee_count: `8`
- tags: ``

## callers

- `0x180034060`
- `0x180091d20`
- `0x180092260`
- `0x1800eefc0`
- `0x1800f1440`
- `0x1801119f0`
- `0x180117530`
- `0x180117970`
- `0x1801542f0`
- `0x180155bf0`
- `0x180174b20`
- `0x1801a3320`

## callees

- `0x1800027e0`
- `0x180058150`
- `0x180058220`
- `0x180171cf0`
- `0x180172050`
- `0x1801720ac`
- `0x180178c70`
- `0x180231d70`

## import_xrefs

- `VCRUNTIME140!memset` at `0x180179089`
- `VCRUNTIME140!memset` at `0x1801790d0`
- `VCRUNTIME140!memset` at `0x180179089`
- `VCRUNTIME140!memset` at `0x1801790d0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801792c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801792cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801792c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801792cd`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x180178d8f`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x180178e64`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x180178d8f`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x180178e64`
- `GDI32!DeleteObject` at `0x180178e75`
- `GDI32!DeleteObject` at `0x1801792d7`
- `GDI32!DeleteObject` at `0x180179324`
- `GDI32!DeleteObject` at `0x180178e75`
- `GDI32!DeleteObject` at `0x1801792d7`
- `GDI32!DeleteObject` at `0x180179324`
- `GDI32!GetObjectW` at `0x180178d7e`
- `GDI32!GetObjectW` at `0x180178d7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMFCToolBarImages::SmoothResize(CMFCToolBarImages *this, double dblImageScale)
{
  CMFCToolBarImages *v2; // rsi
  HBITMAP__ *m_hbmImageWell; // rcx
  int v4; // r12d
  int v5; // r15d
  int v6; // r13d
  int m_iCount; // r14d
  int v8; // eax
  BOOL v9; // edi
  unsigned __int64 v10; // rbx
  int v11; // ecx
  CMFCZoomKernel::XFilterType ft; // edi
  double *v14; // rdi
  int v15; // r9d
  int v16; // r10d
  int v17; // ecx
  int v18; // r11d
  unsigned int v19; // ebx
  int v20; // edx
  __int64 v21; // r8
  unsigned int v22; // eax
  unsigned int v23; // ecx
  unsigned __int8 *m_line; // r8
  unsigned int v25; // esi
  size_t v26; // r15
  double *v27; // r14
  unsigned __int8 *v28; // rbx
  char *v29; // rdi
  unsigned int v30; // r12d
  void *v31; // r13
  int v32; // esi
  __int64 v33; // rcx
  double v34; // xmm6_8
  unsigned int v35; // r9d
  unsigned __int8 *v36; // r10
  __int64 v37; // rdx
  unsigned __int8 *v38; // r8
  double v39; // xmm1_8
  double *v40; // rcx
  unsigned __int64 v41; // rdx
  double *v42; // rax
  unsigned __int64 v43; // rdx
  double *v44; // rcx
  unsigned __int64 v45; // rdx
  unsigned __int8 *v46; // r8
  double v47; // xmm0_8
  int v48; // edi
  HBITMAP__ *v49; // rcx
  int v50; // [rsp+38h] [rbp-D0h]
  unsigned int v51; // [rsp+3Ch] [rbp-CCh]
  unsigned int v52; // [rsp+40h] [rbp-C8h]
  int v53; // [rsp+44h] [rbp-C4h]
  int cy; // [rsp+48h] [rbp-C0h]
  int v55; // [rsp+4Ch] [rbp-BCh]
  int v56; // [rsp+50h] [rbp-B8h]
  int v57; // [rsp+54h] [rbp-B4h]
  unsigned __int64 sizeNew; // [rsp+58h] [rbp-B0h]
  unsigned __int64 v59; // [rsp+60h] [rbp-A8h]
  void *Block; // [rsp+68h] [rbp-A0h]
  int v61; // [rsp+70h] [rbp-98h]
  unsigned int v62; // [rsp+74h] [rbp-94h]
  int v63; // [rsp+78h] [rbp-90h]
  double *v64; // [rsp+80h] [rbp-88h]
  HBITMAP__ *ho; // [rsp+88h] [rbp-80h]
  unsigned __int8 *v66; // [rsp+90h] [rbp-78h]
  unsigned __int8 *v67; // [rsp+98h] [rbp-70h]
  __int64 v68; // [rsp+A0h] [rbp-68h]
  tagBITMAP bmp; // [rsp+A8h] [rbp-60h] BYREF
  CMFCZoomKernel KernelY; // [rsp+C8h] [rbp-40h] BYREF
  CMFCScanlinerBitmap ms; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v72; // [rsp+120h] [rbp+18h]
  unsigned __int8 *v73; // [rsp+128h] [rbp+20h]
  CMFCScanlinerBitmap md; // [rsp+130h] [rbp+28h] BYREF
  __int64 v75; // [rsp+170h] [rbp+68h]
  CSize sizeNewIW; // [rsp+1F8h] [rbp+F0h] BYREF
  int cx; // [rsp+200h] [rbp+F8h]

  v2 = this;
  m_hbmImageWell = this->m_hbmImageWell;
  v4 = 0;
  if ( !m_hbmImageWell || v2->m_nBitsPerPixel < 24 || dblImageScale == 0.0 )
    return 0;
  if ( dblImageScale != 1.0 )
  {
    v5 = (int)((double)v2->m_sizeImage.cy * dblImageScale + 0.5);
    v61 = v5;
    v6 = (int)((double)v2->m_sizeImage.cx * dblImageScale + 0.5);
    v59 = __PAIR64__(v5, v6);
    if ( __PAIR64__(v5, v6) != *(_QWORD *)&v2->m_sizeImage
      && v2->m_sizeImage.cx > 0
      && v2->m_sizeImage.cy > 0
      && v6 > 0
      && v5 > 0 )
    {
      m_iCount = v2->m_iCount;
      if ( m_iCount )
      {
        if ( !GetObjectW(m_hbmImageWell, 32, &bmp.bmHeight) )
          return 0;
        v8 = labs(*(int *)&bmp.bmPlanes);
        v9 = *(int *)&bmp.bmPlanes < 0;
        v2->m_dblScale = dblImageScale * v2->m_dblScale;
        cx = v2->m_sizeImage.cx;
        cy = 0;
        v55 = 0;
        if ( m_iCount == 1 && v8 > v2->m_sizeImage.cy )
        {
          m_iCount = v8 / v2->m_sizeImage.cy;
          cy = v2->m_sizeImage.cy;
          cx = 0;
        }
        ho = CDrawingManager::CreateBitmap_32(v2->m_hbmImageWell, v2->m_clrTransparent);
        if ( !ho )
          return 0;
        v10 = __PAIR64__(v5, v6);
        sizeNewIW = (CSize)__PAIR64__(v5, v6);
        if ( cx <= 0 )
        {
          v11 = v5 * m_iCount;
          sizeNewIW.cy = v5 * m_iCount;
          v4 = v5;
        }
        else
        {
          sizeNewIW.cx = v6 * m_iCount;
          v55 = v6;
          v11 = sizeNewIW.cy;
        }
        if ( v9 )
          sizeNewIW.cy = -v11;
        *(_QWORD *)&bmp.bmType = CDrawingManager::CreateBitmap_32(&sizeNewIW, 0);
        labs(sizeNewIW.cy);
        if ( !*(_QWORD *)&bmp.bmType )
        {
          DeleteObject(ho);
          return 0;
        }
        ft = (dblImageScale >= 1.0) + 5;
        memset(&ms.m_line_begin, 0, 52);
        v72 = 0;
        sizeNewIW = 0;
        CMFCScanlinerBitmap::attach((CMFCScanlinerBitmap *)&ms.m_line_begin, ho, (const CPoint *)&sizeNewIW);
        memset(&md.m_line_begin, 0, 52);
        v75 = 0;
        sizeNewIW = 0;
        CMFCScanlinerBitmap::attach(
          (CMFCScanlinerBitmap *)&md.m_line_begin,
          *(HBITMAP__ **)&bmp.bmType,
          (const CPoint *)&sizeNewIW);
        *(_QWORD *)&bmp.bmHeight = CMFCZoomKernel::`vftable';
        *(_DWORD *)&bmp.bmPlanes = 0;
        bmp.bmBits = 0;
        CMFCZoomKernel::Create((CMFCZoomKernel *)&bmp.bmHeight, v2->m_sizeImage.cx, v6, 0, v2->m_sizeImage.cx, ft);
        *(_QWORD *)&KernelY.m_Size = CMFCZoomKernel::`vftable';
        LODWORD(KernelY.m_List) = 0;
        ms.m_line = 0;
        CMFCZoomKernel::Create((CMFCZoomKernel *)&KernelY.m_Size, v2->m_sizeImage.cy, v5, 0, v2->m_sizeImage.cy, ft);
        sizeNew = BYTE4(ms.m_height);
        v14 = (double *)operator new(saturated_mul(BYTE4(ms.m_height), 8u));
        v64 = v14;
        Block = operator new(saturated_mul(sizeNew, 8u));
        v15 = 0;
        v50 = 0;
        v16 = 0;
        sizeNewIW.cx = 0;
        v17 = 0;
        v56 = 0;
        if ( m_iCount > 0 )
        {
          v18 = BYTE4(ms.m_height);
          v19 = 8 * BYTE4(ms.m_height);
          v62 = v19;
          v20 = 0;
          v57 = 0;
          v63 = v4 * LODWORD(md.m_height);
          v21 = (unsigned int)m_iCount;
          v68 = (unsigned int)m_iCount;
          while ( 1 )
          {
            v22 = v18 * v17;
            v23 = 0;
            v52 = 0;
            if ( !v5 )
              goto LABEL_58;
            m_line = (unsigned __int8 *)v22;
            md.m_line = (unsigned __int8 *)v22;
            v53 = v20;
            do
            {
              v66 = &ms.m_line[16 * v23];
              v67 = &m_line[(unsigned __int64)&md.m_line_end[v20]];
              v25 = 0;
              v51 = 0;
              if ( !v6 )
                goto LABEL_56;
              v26 = v19;
              v27 = v64;
              v28 = &ms.m_line[16 * v23];
              do
              {
                v29 = (char *)bmp.bmBits + 16 * (int)v25;
                memset(v27, 0, v26);
                v30 = 0;
                if ( *(_DWORD *)v28 )
                {
                  v31 = Block;
                  v32 = sizeNewIW.cx;
                  do
                  {
                    v33 = *((_QWORD *)v28 + 1) + 16LL * v30;
                    v73 = &ms.m_line_end[LODWORD(ms.m_height) * (v32 + *(_DWORD *)v33)];
                    v34 = *(double *)(v33 + 8);
                    memset(v31, 0, v26);
                    v35 = 0;
                    v18 = BYTE4(ms.m_height);
                    if ( *(_DWORD *)v29 )
                    {
                      v36 = v73;
                      do
                      {
                        v37 = *((_QWORD *)v29 + 1) + 16LL * v35;
                        v38 = &v36[v18 * (v50 + *(_DWORD *)v37)];
                        v39 = *(double *)(v37 + 8);
                        if ( v18 )
                        {
                          v40 = (double *)Block;
                          v41 = sizeNew;
                          do
                          {
                            *v40 = (double)*v38++ * v39 + *v40;
                            ++v40;
                            --v41;
                          }
                          while ( v41 );
                        }
                        ++v35;
                      }
                      while ( v35 < *(_DWORD *)v29 );
                      v27 = v64;
                      v28 = v66;
                      v31 = Block;
                      v32 = sizeNewIW.cx;
                    }
                    if ( v18 )
                    {
                      v42 = v27;
                      v43 = sizeNew;
                      do
                      {
                        *v42 = v34 * *(double *)((char *)v42 + (_BYTE *)v31 - (_BYTE *)v27) + *v42;
                        ++v42;
                        --v43;
                      }
                      while ( v43 );
                    }
                    ++v30;
                  }
                  while ( v30 < *(_DWORD *)v28 );
                  v6 = v59;
                  v25 = v51;
                }
                else
                {
                  v18 = BYTE4(ms.m_height);
                }
                if ( v18 == 4 )
                {
                  *v27 = fmin(*v27, v27[3]);
                  v27[1] = fmin(v27[1], v27[3]);
                  v27[2] = fmin(v27[2], v27[3]);
                }
                else if ( !v18 )
                {
                  goto LABEL_54;
                }
                v44 = v27;
                v45 = sizeNew;
                v46 = v67;
                do
                {
                  if ( *v44 >= 0.0 )
                    v47 = fmin(255.0, *v44);
                  else
                    v47 = 0.0;
                  *v46++ = (int)v47;
                  ++v44;
                  --v45;
                }
                while ( v45 );
                v67 = v46;
LABEL_54:
                v51 = ++v25;
              }
              while ( v25 < v6 );
              v5 = v61;
              v23 = v52;
              v20 = v53;
              m_line = md.m_line;
              v19 = v62;
LABEL_56:
              v52 = ++v23;
              v20 += LODWORD(md.m_height);
              v53 = v20;
            }
            while ( v23 < v5 );
            v20 = v57;
            v21 = v68;
            v15 = v50;
            v16 = sizeNewIW.cx;
LABEL_58:
            v15 += cx;
            v50 = v15;
            v16 += cy;
            sizeNewIW.cx = v16;
            v17 = v55 + v56;
            v56 += v55;
            v20 += v63;
            v57 = v20;
            v68 = --v21;
            if ( !v21 )
            {
              v10 = v59;
              v2 = this;
              v14 = v64;
              break;
            }
          }
        }
        free(v14);
        free(Block);
        DeleteObject(ho);
        v48 = v2->m_iCount;
        if ( !v2->m_sizeImageOriginal.cx && !v2->m_sizeImageOriginal.cy )
          v2->m_sizeImageOriginal = v2->m_sizeImage;
        v2->m_sizeImage = (CSize)v10;
        v2->m_clrTransparentOriginal = v2->m_clrTransparent;
        v2->m_clrTransparent = -1;
        if ( !v2->m_bIsTemporary )
        {
          if ( v2 == (CMFCToolBarImages *)-160LL )
            AfxThrowInvalidArgException();
          v49 = v2->m_hbmImageWell;
          if ( v49 )
            DeleteObject(v49);
        }
        v2->m_hbmImageWell = *(HBITMAP__ **)&bmp.bmType;
        v2->m_iCount = v48;
        v2->m_nBitsPerPixel = 32;
        *(_QWORD *)&KernelY.m_Size = CMFCZoomKernel::`vftable';
        CMFCZoomKernel::Empty((CMFCZoomKernel *)&KernelY.m_Size);
        *(_QWORD *)&bmp.bmHeight = CMFCZoomKernel::`vftable';
        CMFCZoomKernel::Empty((CMFCZoomKernel *)&bmp.bmHeight);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180178c70  mov     rax, rsp
0x180178c73  mov     [rax+10h], rbx
0x180178c77  mov     [rax+8], this
0x180178c7b  push    rbp
0x180178c7c  push    rsi
0x180178c7d  push    rdi
0x180178c7e  push    r12
0x180178c80  push    r13
0x180178c82  push    r14
0x180178c84  push    r15
0x180178c86  lea     rbp, [rax-0D8h]
0x180178c8d  sub     rsp, 1A0h
0x180178c94  movaps  xmmword ptr [rax-48h], xmm6
0x180178c98  movaps  xmmword ptr [rax-58h], xmm7
0x180178c9c  movaps  xmmword ptr [rax-68h], xmm8
0x180178ca1  movaps  xmm6, xmm1
0x180178ca4  mov     rsi, this
0x180178ca7  mov     this, [this+0A0h]; h
0x180178cae  xor     r12d, r12d
0x180178cb1  test    this, this
0x180178cb4  jz      loc_180178E7B
0x180178cba  cmp     dword ptr [rsi+0Ch], 18h
0x180178cbe  jl      loc_180178E7B
0x180178cc4  xorps   xmm8, xmm8
0x180178cc8  ucomisd xmm1, xmm8
0x180178ccd  jp      short loc_180178CD5
0x180178ccf  jz      loc_180178E7B
0x180178cd5  movsd   xmm7, cs:__real@3ff0000000000000
0x180178cdd  ucomisd xmm6, xmm7
0x180178ce1  jp      short loc_180178CE9
0x180178ce3  jz      loc_180179362
0x180178ce9  movd    xmm0, dword ptr [rsi+6Ch]
0x180178cee  cvtdq2pd xmm0, xmm0
0x180178cf2  mulsd   xmm0, xmm6
0x180178cf6  addsd   xmm0, cs:__real@3fe0000000000000
0x180178cfe  cvttsd2si r15d, xmm0
0x180178d03  mov     [rsp+1D0h+var_168], r15d
0x180178d08  movd    xmm0, dword ptr [rsi+68h]
0x180178d0d  cvtdq2pd xmm0, xmm0
0x180178d11  mulsd   xmm0, xmm6
0x180178d15  addsd   xmm0, cs:__real@3fe0000000000000
0x180178d1d  cvttsd2si r13d, xmm0
0x180178d22  mov     dword ptr [rsp+1D0h+var_178], r13d
0x180178d27  mov     dword ptr [rsp+1D0h+var_178+4], r15d
0x180178d2c  mov     rax, [rsi+68h]
0x180178d30  cmp     r13d, eax
0x180178d33  jnz     short loc_180178D42
0x180178d35  shr     rax, 20h
0x180178d39  cmp     r15d, eax
0x180178d3c  jz      loc_180179362
0x180178d42  cmp     [rsi+68h], r12d
0x180178d46  jle     loc_180179362
0x180178d4c  cmp     [rsi+6Ch], r12d
0x180178d50  jle     loc_180179362
0x180178d56  test    r13d, r13d
0x180178d59  jle     loc_180179362
0x180178d5f  test    r15d, r15d
0x180178d62  jle     loc_180179362
0x180178d68  mov     r14d, [rsi+8]
0x180178d6c  test    r14d, r14d
0x180178d6f  jz      loc_180179362
0x180178d75  lea     r8, [rbp+0D0h+bmp.bmHeight]; pv
0x180178d79  mov     edx, 20h ; ' '; c
0x180178d7e  call    cs:__imp_GetObjectW
0x180178d84  test    eax, eax
0x180178d86  jz      loc_180178E7B
0x180178d8c  mov     ecx, dword ptr [rbp+0D0h+bmp.bmPlanes]; Number
0x180178d8f  call    cs:__imp_labs
0x180178d95  mov     edi, r12d
0x180178d98  cmp     dword ptr [rbp+0D0h+bmp.bmPlanes], r12d
0x180178d9c  setl    dil
0x180178da0  movaps  xmm0, xmm6
0x180178da3  mulsd   xmm0, qword ptr [rsi+0E8h]
0x180178dab  movsd   qword ptr [rsi+0E8h], xmm0
0x180178db3  mov     ebx, [rsi+68h]
0x180178db6  mov     [rbp+0D0h+arg_18], ebx
0x180178dbc  mov     [rsp+1D0h+var_190], r12d
0x180178dc1  mov     [rsp+1D0h+var_18C], r12d
0x180178dc6  cmp     r14d, 1
0x180178dca  jnz     short loc_180178DE6
0x180178dcc  cmp     eax, [rsi+6Ch]
0x180178dcf  jle     short loc_180178DE6
0x180178dd1  cdq
0x180178dd2  idiv    dword ptr [rsi+6Ch]
0x180178dd5  mov     r14d, eax
0x180178dd8  mov     eax, [rsi+6Ch]
0x180178ddb  mov     [rsp+1D0h+var_190], eax
0x180178ddf  and     [rbp+0D0h+arg_18], r12d
0x180178de6  mov     edx, [rsi+0D8h]; clrTransparent
0x180178dec  mov     this, [rsi+0A0h]; bitmap
0x180178df3  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@PEAU2@K@Z; CDrawingManager::CreateBitmap_32(HBITMAP__ *,ulong)
0x180178df8  mov     [rbp+0D0h+ho], rax
0x180178dfc  test    rax, rax
0x180178dff  jz      short loc_180178E7B
0x180178e01  mov     rbx, [rsp+1D0h+var_178]
0x180178e06  mov     qword ptr [rbp+0D0h+sizeNewIW.cx], rbx
0x180178e0d  mov     ecx, r14d
0x180178e10  cmp     [rbp+0D0h+arg_18], r12d
0x180178e17  jle     short loc_180178E30
0x180178e19  imul    ecx, r13d
0x180178e1d  mov     [rbp+0D0h+sizeNewIW.cx], ecx
0x180178e23  mov     [rsp+1D0h+var_18C], r13d
0x180178e28  mov     ecx, [rbp+0D0h+sizeNewIW.cy]
0x180178e2e  jmp     short loc_180178E3D
0x180178e30  imul    ecx, r15d
0x180178e34  mov     [rbp+0D0h+sizeNewIW.cy], ecx
0x180178e3a  mov     r12d, r15d
0x180178e3d  test    edi, edi
0x180178e3f  jz      short loc_180178E49
0x180178e41  neg     ecx
0x180178e43  mov     [rbp+0D0h+sizeNewIW.cy], ecx
0x180178e49  xor     edx, edx; pBits
0x180178e4b  lea     this, [rbp+0D0h+sizeNewIW]; size
0x180178e52  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x180178e57  mov     rdi, rax
0x180178e5a  mov     qword ptr [rbp+0D0h+bmp.bmType], rax
0x180178e5e  mov     ecx, [rbp+0D0h+sizeNewIW.cy]; Number
0x180178e64  call    cs:__imp_labs
0x180178e6a  xor     eax, eax
0x180178e6c  test    rdi, rdi
0x180178e6f  jnz     short loc_180178EA7
0x180178e71  mov     this, [rbp+0D0h+ho]; ho
0x180178e75  call    cs:__imp_DeleteObject
0x180178e7b  xor     eax, eax
0x180178e7d  lea     r11, [rsp+1D0h+var_30]
0x180178e85  mov     rbx, [r11+48h]
0x180178e89  movaps  xmm6, xmmword ptr [r11-10h]
0x180178e8e  movaps  xmm7, xmmword ptr [r11-20h]
0x180178e93  movaps  xmm8, xmmword ptr [r11-30h]
0x180178e98  mov     rsp, r11
0x180178e9b  pop     r15
0x180178e9d  pop     r14
0x180178e9f  pop     r13
0x180178ea1  pop     r12
0x180178ea3  pop     rdi
0x180178ea4  pop     rsi
0x180178ea5  pop     rbp
0x180178ea6  retn
0x180178ea7  mov     edi, eax
0x180178ea9  comisd  xmm7, xmm6
0x180178ead  setbe   dil
0x180178eb1  add     edi, 5
0x180178eb4  mov     [rbp+0D0h+ms.m_line_begin], rax
0x180178eb8  mov     qword ptr [rbp+0D0h+ms.m_start_row], rax
0x180178ebc  mov     qword ptr [rbp+0D0h+ms.m_rows], rax
0x180178ec0  mov     qword ptr [rbp+0D0h+ms.m_offset], rax
0x180178ec4  mov     dword ptr [rbp+0D0h+ms.m_height], eax
0x180178ec7  mov     [rbp+0D0h+var_B8], rax
0x180178ecb  mov     [rbp+0D0h+ms.m_line_end], rax
0x180178ecf  mov     [rbp+0D0h+ms.m_pitch], rax
0x180178ed3  mov     qword ptr [rbp+0D0h+sizeNewIW.cx], rax
0x180178eda  lea     r8, [rbp+0D0h+sizeNewIW]; ptBegin
0x180178ee1  mov     rdx, [rbp+0D0h+ho]; bitmap
0x180178ee5  lea     this, [rbp+0D0h+ms.m_line_begin]; this
0x180178ee9  call    ?attach@CMFCScanlinerBitmap@@QEAAXPEAUHBITMAP__@@AEBVCPoint@@@Z; CMFCScanlinerBitmap::attach(HBITMAP__ *,CPoint const &)
0x180178eee  xor     eax, eax
0x180178ef0  mov     [rbp+0D0h+md.m_line_begin], rax
0x180178ef4  mov     qword ptr [rbp+0D0h+md.m_start_row], rax
0x180178ef8  mov     qword ptr [rbp+0D0h+md.m_rows], rax
0x180178efc  mov     qword ptr [rbp+0D0h+md.m_offset], rax
0x180178f00  mov     dword ptr [rbp+0D0h+md.m_height], eax
0x180178f03  mov     [rbp+0D0h+var_68], rax
0x180178f07  mov     [rbp+0D0h+md.m_line_end], rax
0x180178f0b  mov     [rbp+0D0h+md.m_pitch], rax
0x180178f0f  mov     qword ptr [rbp+0D0h+sizeNewIW.cx], rax
0x180178f16  lea     r8, [rbp+0D0h+sizeNewIW]; ptBegin
0x180178f1d  mov     rdx, qword ptr [rbp+0D0h+bmp.bmType]; bitmap
0x180178f21  lea     this, [rbp+0D0h+md.m_line_begin]; this
0x180178f25  call    ?attach@CMFCScanlinerBitmap@@QEAAXPEAUHBITMAP__@@AEBVCPoint@@@Z; CMFCScanlinerBitmap::attach(HBITMAP__ *,CPoint const &)
0x180178f2a  lea     rax, ??_7CMFCZoomKernel@@6B@; const CMFCZoomKernel::`vftable'
0x180178f31  mov     qword ptr [rbp+0D0h+bmp.bmHeight], rax
0x180178f35  and     dword ptr [rbp+0D0h+bmp.bmPlanes], 0
0x180178f39  and     [rbp+0D0h+bmp.bmBits], 0
0x180178f3e  mov     edx, [rsi+68h]; sizeSrc
0x180178f41  mov     [rsp+1D0h+ft], edi; ft
0x180178f45  mov     [rsp+1D0h+widthSrc], edx; widthSrc
0x180178f49  xor     r9d, r9d; originSrc
0x180178f4c  mov     r8d, r13d; sizeDst
0x180178f4f  lea     this, [rbp+0D0h+bmp.bmHeight]; this
0x180178f53  call    ?Create@CMFCZoomKernel@@QEAAXJJJJW4XFilterType@1@@Z; CMFCZoomKernel::Create(long,long,long,long,CMFCZoomKernel::XFilterType)
0x180178f58  lea     rax, ??_7CMFCZoomKernel@@6B@; const CMFCZoomKernel::`vftable'
0x180178f5f  mov     qword ptr [rbp+0D0h+KernelY.m_Size], rax
0x180178f63  and     dword ptr [rbp+0D0h+KernelY.m_List], 0
0x180178f67  and     [rbp+0D0h+ms.m_line], 0
0x180178f6c  mov     edx, [rsi+6Ch]; sizeSrc
0x180178f6f  mov     [rsp+1D0h+ft], edi; ft
0x180178f73  mov     [rsp+1D0h+widthSrc], edx; widthSrc
0x180178f77  xor     r9d, r9d; originSrc
0x180178f7a  mov     r8d, r15d; sizeDst
0x180178f7d  lea     this, [rbp+0D0h+KernelY.m_Size]; this
0x180178f81  call    ?Create@CMFCZoomKernel@@QEAAXJJJJW4XFilterType@1@@Z; CMFCZoomKernel::Create(long,long,long,long,CMFCZoomKernel::XFilterType)
0x180178f86  movzx   ecx, byte ptr [rbp+0D0h+ms.m_height+4]
0x180178f8a  mov     qword ptr [rsp+1D0h+sizeNew.cx], this
0x180178f8f  mov     eax, 8
0x180178f94  mul     this
0x180178f97  mov     this, 0FFFFFFFFFFFFFFFFh
0x180178f9e  cmovb   rax, this
0x180178fa2  mov     this, rax; nSize
0x180178fa5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180178faa  mov     rdi, rax
0x180178fad  mov     [rsp+1D0h+var_158], rax
0x180178fb2  mov     eax, 8
0x180178fb7  mul     qword ptr [rsp+1D0h+sizeNew.cx]
0x180178fbc  mov     this, 0FFFFFFFFFFFFFFFFh
0x180178fc3  cmovb   rax, this
0x180178fc7  mov     this, rax; nSize
0x180178fca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180178fcf  mov     [rsp+1D0h+Block], rax
0x180178fd4  xor     r9d, r9d
0x180178fd7  mov     [rsp+1D0h+var_1A0], r9d
0x180178fdc  xor     r10d, r10d
0x180178fdf  mov     [rbp+0D0h+sizeNewIW.cx], r10d
0x180178fe6  xor     ecx, ecx
0x180178fe8  mov     dword ptr [rsp+1D0h+var_188], ecx
0x180178fec  test    r14d, r14d
0x180178fef  jle     loc_1801792BF
0x180178ff5  movzx   r11d, byte ptr [rbp+0D0h+ms.m_height+4]
0x180178ffa  lea     ebx, ds:0[r11*8]
0x180179002  mov     [rsp+1D0h+var_164], ebx
0x180179006  xor     edx, edx
0x180179008  mov     dword ptr [rsp+1D0h+var_188+4], edx
0x18017900c  mov     eax, dword ptr [rbp+0D0h+md.m_height]
0x18017900f  imul    eax, r12d
0x180179013  mov     dword ptr [rsp+1D0h+var_160], eax
0x180179017  mov     r8d, r14d
0x18017901a  mov     [rbp+0D0h+var_138], r8
0x18017901e  mov     eax, ecx
0x180179020  imul    eax, r11d
0x180179024  xor     ecx, ecx
0x180179026  mov     [rsp+1D0h+var_198], ecx
0x18017902a  test    r15d, r15d
0x18017902d  jz      loc_180179274
0x180179033  mov     r8d, eax
0x180179036  mov     [rbp+0D0h+md.m_line], r8
0x18017903a  mov     [rsp+1D0h+var_194], edx
0x18017903e  movsxd  rax, ecx
0x180179041  shl     rax, 4
0x180179045  add     rax, [rbp+0D0h+ms.m_line]
0x180179049  mov     [rbp+0D0h+var_148], rax
0x18017904d  movsxd  rax, edx
0x180179050  add     rax, [rbp+0D0h+md.m_line_end]
0x180179054  add     rax, r8
0x180179057  mov     [rbp+0D0h+var_140], rax
0x18017905b  xor     esi, esi
0x18017905d  mov     [rsp+1D0h+var_19C], esi
0x180179061  test    r13d, r13d
0x180179064  jz      loc_18017924A
0x18017906a  mov     r15d, ebx
0x18017906d  mov     r14, [rsp+1D0h+var_158]
0x180179072  mov     rbx, [rbp+0D0h+var_148]
0x180179076  movsxd  rdi, esi
0x180179079  shl     rdi, 4
0x18017907d  add     rdi, [rbp+0D0h+bmp.bmBits]
0x180179081  mov     r8, r15; Size
0x180179084  xor     edx, edx; Val
0x180179086  mov     this, r14; void *
0x180179089  call    cs:__imp_memset
0x18017908f  xor     r12d, r12d
0x180179092  cmp     [rbx], r12d
0x180179095  jbe     loc_1801791A3
0x18017909b  mov     r13, [rsp+1D0h+Block]
0x1801790a0  mov     esi, [rbp+0D0h+sizeNewIW.cx]
0x1801790a6  mov     ecx, r12d
0x1801790a9  shl     this, 4
0x1801790ad  add     this, [rbx+8]
0x1801790b1  mov     eax, [this]
0x1801790b3  add     eax, esi
0x1801790b5  imul    eax, dword ptr [rbp+0D0h+ms.m_height]
0x1801790b9  cdqe
0x1801790bb  add     rax, [rbp+0D0h+ms.m_line_end]
0x1801790bf  mov     [rbp+0D0h+var_B0], rax
0x1801790c3  movsd   xmm6, qword ptr [this+8]
0x1801790c8  mov     r8, r15; Size
0x1801790cb  xor     edx, edx; Val
0x1801790cd  mov     this, r13; void *
0x1801790d0  call    cs:__imp_memset
0x1801790d6  xor     r9d, r9d
0x1801790d9  movzx   r11d, byte ptr [rbp+0D0h+ms.m_height+4]
0x1801790de  cmp     [rdi], r9d
0x1801790e1  jbe     short loc_18017915F
0x1801790e3  mov     r10, [rbp+0D0h+var_B0]
0x1801790e7  mov     rbx, [rsp+1D0h+Block]
0x1801790ec  mov     r14d, [rsp+1D0h+var_1A0]
0x1801790f1  mov     rsi, qword ptr [rsp+1D0h+sizeNew.cx]
0x1801790f6  mov     edx, r9d
0x1801790f9  shl     rdx, 4
0x1801790fd  add     rdx, [rdi+8]
0x180179101  mov     r8d, [rdx]
0x180179104  add     r8d, r14d
0x180179107  imul    r8d, r11d
0x18017910b  add     r8, r10
0x18017910e  movsd   xmm1, qword ptr [rdx+8]
0x180179113  test    r11d, r11d
0x180179116  jz      short loc_180179143
0x180179118  mov     this, rbx
0x18017911b  mov     rdx, rsi
0x18017911e  movzx   eax, byte ptr [r8]
0x180179122  movd    xmm0, eax
0x180179126  cvtdq2pd xmm0, xmm0
0x18017912a  mulsd   xmm0, xmm1
  ... truncated ...
```

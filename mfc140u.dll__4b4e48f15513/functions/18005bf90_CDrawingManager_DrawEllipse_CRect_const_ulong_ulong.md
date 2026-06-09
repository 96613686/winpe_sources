# CDrawingManager::DrawEllipse(CRect const &,ulong,ulong)

- ea: `0x18005bf90`
- end: `0x18005ccd3`
- name: `?DrawEllipse@CDrawingManager@@QEAAXAEBVCRect@@KK@Z`
- size: `3395`
- prototype: `void __fastcall(CDrawingManager *this, const CRect *rect, unsigned int clrFill, unsigned int clrLine)`
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1801936e0`
- `0x1801938d0`
- `0x180195aa0`
- `0x18019feb0`

## callees

- `0x18001d090`
- `0x180058150`
- `0x18005bf90`
- `0x18005dd50`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802aef40`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c28f`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c316`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c3d0`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c48b`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c7ee`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005ca35`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c28f`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c316`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c3d0`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c48b`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005c7ee`
- `api-ms-win-crt-math-l1-1-0!ceil` at `0x18005ca35`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c2fb`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c3aa`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c473`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c7da`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c85a`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c2fb`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c3aa`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c473`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c7da`
- `api-ms-win-crt-math-l1-1-0!sqrt` at `0x18005c85a`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c2a2`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c32e`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c3bb`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c401`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c652`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c802`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c874`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c2a2`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c32e`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c3bb`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c401`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c652`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c802`
- `api-ms-win-crt-math-l1-1-0!floor` at `0x18005c874`
- `GDI32!DeleteDC` at `0x18005cc67`
- `GDI32!DeleteDC` at `0x18005cc67`
- `GDI32!CreateCompatibleBitmap` at `0x18005c0dc`
- `GDI32!CreateCompatibleBitmap` at `0x18005c0dc`
- `GDI32!DeleteObject` at `0x18005cc0a`
- `GDI32!DeleteObject` at `0x18005cc0a`
- `GDI32!SelectObject` at `0x18005c117`
- `GDI32!SelectObject` at `0x18005c163`
- `GDI32!SelectObject` at `0x18005cbf8`
- `GDI32!SelectObject` at `0x18005c117`
- `GDI32!SelectObject` at `0x18005c163`
- `GDI32!SelectObject` at `0x18005cbf8`
- `GDI32!CreateCompatibleDC` at `0x18005c0a4`
- `GDI32!CreateCompatibleDC` at `0x18005c0a4`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=3
void __fastcall CDrawingManager::DrawEllipse(
        CDrawingManager *this,
        const CRect *rect,
        unsigned int clrFill,
        unsigned int clrLine)
{
  unsigned int v5; // ebx
  int v8; // edx
  int v9; // esi
  int v10; // eax
  int v11; // ecx
  int v12; // edi
  int v13; // eax
  int v14; // edi
  int v15; // esi
  CDC *m_dc; // rax
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v20; // rax
  HBITMAP__ *v21; // rax
  CSize v22; // rsi
  unsigned int v23; // ecx
  int v24; // r13d
  int v25; // edi
  double v26; // xmm2_8
  __int64 cx; // r14
  double v28; // xmm7_8
  double v29; // xmm3_8
  double v30; // xmm8_8
  bool v31; // cf
  double v32; // xmm0_8
  double v33; // xmm1_8
  double v34; // xmm11_8
  double v35; // xmm13_8
  double v36; // xmm7_8
  double v37; // xmm8_8
  int v38; // r15d
  __int64 v39; // r12
  __int64 v40; // r13
  __int64 v41; // rdi
  int v42; // eax
  double v43; // xmm0_8
  double v44; // xmm0_8
  double v45; // xmm6_8
  double v46; // xmm0_8
  int v47; // edi
  int v48; // edx
  unsigned int *v49; // rax
  __int64 v50; // rcx
  double v51; // xmm9_8
  double v52; // xmm6_8
  int v53; // r12d
  __int64 v54; // rbx
  int v55; // r15d
  __int64 v56; // rax
  int v57; // r12d
  int v58; // ecx
  __int64 v59; // rcx
  unsigned int *v60; // rdi
  double v61; // xmm0_8
  double v62; // xmm12_8
  int v63; // r9d
  double v64; // xmm3_8
  double v65; // xmm13_8
  int v66; // edi
  double v67; // xmm14_8
  int v68; // r11d
  int v69; // r13d
  int v70; // r10d
  double v71; // xmm2_8
  double v72; // xmm3_8
  unsigned int v73; // r8d
  int v74; // edx
  __int64 v75; // rax
  int v76; // r9d
  double v77; // xmm6_8
  int v78; // edi
  int v79; // r11d
  int v80; // eax
  int v81; // r10d
  unsigned int v82; // r8d
  int v83; // edx
  __int64 v84; // rax
  double v85; // xmm9_8
  int v86; // r12d
  __int64 v87; // rbx
  int v88; // r15d
  __int64 v89; // rax
  double v90; // xmm0_8
  double v91; // xmm9_8
  int v92; // r9d
  double v93; // xmm6_8
  int v94; // edi
  int v95; // r11d
  int v96; // r13d
  int v97; // r10d
  double v98; // xmm15_8
  double v99; // xmm2_8
  double v100; // xmm6_8
  unsigned int v101; // r8d
  int v102; // edx
  __int64 v103; // rax
  int v104; // r9d
  double v105; // xmm2_8
  int v106; // edi
  int v107; // r11d
  int v108; // eax
  int v109; // r10d
  unsigned int v110; // r8d
  int v111; // edx
  __int64 v112; // rax
  HGDIOBJ v113; // rax
  HDC v114; // rax
  bool v115; // [rsp+38h] [rbp-D0h]
  int v116; // [rsp+3Ch] [rbp-CCh]
  char v117; // [rsp+3Ch] [rbp-CCh]
  char v118; // [rsp+3Ch] [rbp-CCh]
  int v119; // [rsp+40h] [rbp-C8h]
  int v120; // [rsp+44h] [rbp-C4h]
  int v121; // [rsp+48h] [rbp-C0h]
  __int64 v122; // [rsp+50h] [rbp-B8h]
  __int64 v123; // [rsp+50h] [rbp-B8h]
  __int64 v124; // [rsp+50h] [rbp-B8h]
  int v125; // [rsp+58h] [rbp-B0h]
  int v126; // [rsp+5Ch] [rbp-ACh]
  int pBits; // [rsp+60h] [rbp-A8h]
  CSize size; // [rsp+68h] [rbp-A0h] BYREF
  CSize v130; // [rsp+70h] [rbp-98h] BYREF
  CBitmap bmpMem; // [rsp+78h] [rbp-90h] BYREF
  CDC dcMem; // [rsp+88h] [rbp-80h] BYREF
  _BYTE rt[24]; // [rsp+A8h] [rbp-60h] OVERLAPPED BYREF
  double v134; // [rsp+C0h] [rbp-48h]
  double v135; // [rsp+C8h] [rbp-40h]
  CDrawingManager *v136; // [rsp+D0h] [rbp-38h]
  CGdiObject *v137; // [rsp+D8h] [rbp-30h]
  HGDIOBJ ho; // [rsp+E0h] [rbp-28h]
  CRect X; // [rsp+E8h] [rbp-20h] BYREF

  v5 = clrFill;
  v136 = this;
  if ( clrFill != -1 || clrLine != -1 )
  {
    *(CRect *)&rt[8] = *rect;
    v8 = _mm_cvtsi128_si32(*(__m128i *)&rt[8]);
    v9 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&rt[8], 8));
    if ( v8 > v9 )
    {
      v10 = v8;
      v8 = v9;
      *(_DWORD *)&rt[8] = v9;
      v9 = v10;
      *(_DWORD *)&rt[16] = v10;
    }
    v11 = *(_DWORD *)&rt[12];
    v12 = *(_DWORD *)&rt[20];
    if ( *(int *)&rt[12] > *(int *)&rt[20] )
    {
      v13 = *(_DWORD *)&rt[12];
      v11 = *(_DWORD *)&rt[20];
      *(_DWORD *)&rt[12] = *(_DWORD *)&rt[20];
      v12 = v13;
      *(_DWORD *)&rt[20] = v13;
    }
    v14 = v12 - v11;
    v15 = v9 - v8;
    v130.cx = v15;
    v130.cy = v14;
    if ( v15 )
    {
      if ( v14 )
      {
        dcMem.m_hDC = (HDC__ *)CDC::`vftable';
        *(_OWORD *)&dcMem.m_hAttribDC = 0;
        *(_DWORD *)rt = 0;
        m_dc = this->m_dc;
        m_hDC = 0;
        if ( m_dc )
          m_hDC = m_dc->m_hDC;
        CompatibleDC = CreateCompatibleDC(m_hDC);
        if ( !CDC::Attach((CDC *)&dcMem.m_hDC, CompatibleDC) )
          goto LABEL_82;
        dcMem.__vftable = 0;
        bmpMem.m_hObject = (void *)CBitmap::`vftable';
        CompatibleBitmap = CreateCompatibleBitmap(this->m_dc->m_hDC, v15, v14);
        if ( !CGdiObject::Attach((CGdiObject *)&bmpMem.m_hObject, CompatibleBitmap) )
        {
          bmpMem.m_hObject = (void *)CBitmap::`vftable';
          CGdiObject::~CGdiObject((CGdiObject *)&bmpMem.m_hObject);
          goto LABEL_82;
        }
        v20 = SelectObject(dcMem.m_hAttribDC, dcMem.__vftable);
        v137 = CGdiObject::FromHandle(v20);
        if ( !v137 )
          AfxThrowInvalidArgException();
        v21 = CDrawingManager::CreateBitmap_32(&v130, (void **)&size);
        ho = v21;
        if ( !v21 || (v22 = size, *(double *)&size == 0.0) )
        {
          bmpMem.m_hObject = (void *)CBitmap::`vftable';
          CGdiObject::~CGdiObject((CGdiObject *)&bmpMem.m_hObject);
LABEL_82:
          dcMem.m_hDC = (HDC__ *)CDC::`vftable';
          if ( dcMem.m_hAttribDC )
          {
            v114 = CDC::Detach((CDC *)&dcMem.m_hDC);
            DeleteDC(v114);
          }
          return;
        }
        SelectObject(dcMem.m_hAttribDC, v21);
        v23 = v5;
        if ( clrLine != -1 )
          v23 = clrLine;
        v121 = (unsigned __int8)v23;
        v24 = BYTE1(v23);
        v119 = v24;
        v25 = BYTE2(v23);
        v120 = BYTE2(v23);
        v125 = (unsigned __int8)v5;
        v126 = BYTE1(v5);
        pBits = BYTE2(v5);
        if ( v5 != -1 )
          v5 = BYTE2(v5) | ((v5 | 0xFFFFFF00) << 16) | (BYTE1(v5) << 8);
        v26 = 0.0;
        cx = v130.cx;
        v28 = (double)(v130.cx - 1);
        v29 = 0.0;
        v30 = (double)(v130.cy - 1);
        if ( v28 < 0.0 )
        {
          v26 = (double)(v130.cx - 1);
          v28 = 0.0;
        }
        if ( v30 < 0.0 )
        {
          v29 = (double)(v130.cy - 1);
          v30 = 0.0;
        }
        v31 = v28 - v26 < v30 - v29;
        if ( v28 - v26 >= v30 - v29 )
        {
          v32 = v26;
          v26 = v29;
          v29 = v32;
          v33 = v28;
          v28 = v30;
          v30 = v33;
        }
        v115 = !v31;
        v34 = (v28 - v26) * 0.5;
        v35 = (v30 - v29) * 0.5;
        *(double *)&bmpMem.__vftable = v35;
        v36 = (v28 + v26) * 0.5;
        v37 = (v30 + v29) * 0.5;
        if ( clrFill != -1 )
        {
          v38 = (int)ceil(v36 - v34);
          v116 = (int)floor(v36 + v34);
          if ( v38 <= v116 )
          {
            v39 = v38;
            v122 = v38;
            v40 = (int)cx * v38;
            v41 = cx;
            v42 = v116;
            while ( 1 )
            {
              v43 = 1.0 - ((double)v38 - v36) / v34 * (((double)v38 - v36) / v34);
              if ( v43 >= 0.0 )
                break;
LABEL_37:
              ++v38;
              v122 = ++v39;
              v40 += v41;
              if ( v38 > v42 )
              {
                v24 = v119;
                v25 = v120;
                goto LABEL_39;
              }
            }
            v44 = sqrt(v43);
            v45 = v44 * v35 + v37;
            v46 = ceil(v37 - v44 * v35);
            if ( v115 )
            {
              v57 = (int)v46;
              v58 = (int)floor(v45);
              if ( v57 > v58 )
              {
                v39 = v122;
                goto LABEL_36;
              }
              v59 = v58 - v57 + 1;
              v60 = (unsigned int *)(*(_QWORD *)&v22 + 4 * (v40 + v57));
              while ( v59 )
              {
                *v60++ = v5;
                --v59;
              }
              v39 = v122;
            }
            else
            {
              v47 = (int)v46;
              v48 = (int)floor(v45);
              v49 = (unsigned int *)(*(_QWORD *)&v22 + 4 * (v39 + (int)cx * v47));
              if ( v47 <= v48 )
              {
                v50 = (unsigned int)(v48 - v47 + 1);
                do
                {
                  *v49 = v5;
                  v49 += cx;
                  --v50;
                }
                while ( v50 );
              }
            }
            v41 = cx;
LABEL_36:
            v42 = v116;
            goto LABEL_37;
          }
        }
LABEL_39:
        v51 = v35 * v35;
        *(double *)&X.left = v35 * v35 + v34 * v34;
        v52 = v34 * v34 / sqrt(*(double *)&X.left);
        v53 = (int)floor(v36 - v52);
        v54 = v53;
        v123 = (int)ceil(v52 + v36);
        if ( v53 <= v123 )
        {
          v55 = cx * v53;
          v56 = v123;
          while ( 1 )
          {
            v61 = 1.0 - ((double)v53 - v36) / v34 * (((double)v53 - v36) / v34);
            if ( v61 >= 0.0 )
            {
              v62 = sqrt(v61) * v35;
              v63 = (int)ceil(v62 + v37);
              v64 = (double)v63 - v37 - v62;
              v65 = (double)v25;
              v66 = (int)((double)v25 * v64);
              v67 = (double)v24;
              v68 = (int)((double)v24 * v64);
              v69 = (int)((double)v121 * v64);
              v70 = (int)(v64 * 255.0);
              v134 = (double)v125;
              v135 = (double)v126;
              if ( clrFill == -1 )
              {
                v73 = (unsigned __int8)v66 | ((unsigned __int8)v69 << 16) | (((unsigned __int8)v68 | (v70 << 16)) << 8);
                v72 = (double)pBits;
              }
              else
              {
                v71 = 1.0 - v64;
                v72 = (double)pBits;
                v73 = (unsigned __int8)(int)((double)pBits * v71 + (double)v66)
                    | (((int)((double)v125 * v71 + (double)v69) | 0xFFFFFF00) << 16)
                    | ((unsigned __int8)(int)((double)v126 * v71 + (double)v68) << 8);
              }
              *(double *)&size = v72;
              v74 = (unsigned __int8)(v120 - v66)
                  | ((unsigned __int8)(v121 - v69) << 16)
                  | ((unsigned __int8)(v119 - v68) << 8)
                  | (-16777216 - (v70 << 24));
              if ( v115 )
              {
                v75 = v55 + (__int64)v63;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * v75) = v74;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * v75 - 4) = v73;
              }
              else
              {
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * (v54 + (int)cx * v63)) = v74;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * (v54 + (int)cx * (v63 - 1))) = v73;
              }
              v76 = (int)floor(v37 - v62);
              v77 = v37 - v62 - (double)v76;
              v78 = (int)(v65 * v77);
              v79 = (int)(v67 * v77);
              v80 = (int)((double)v121 * v77);
              v117 = v80;
              v81 = (int)(v77 * 255.0);
              if ( clrFill == -1 )
              {
                v82 = (unsigned __int8)v78 | ((unsigned __int8)v80 << 16) | (((unsigned __int8)v79 | (v81 << 16)) << 8);
                v117 = v80;
              }
              else
              {
                v82 = (unsigned __int8)(int)(*(double *)&size * (1.0 - v77) + (double)v78)
                    | ((unsigned __int8)(int)(v135 * (1.0 - v77) + (double)v79) << 8)
                    | (((int)(v134 * (1.0 - v77) + (double)v80) | 0xFFFFFF00) << 16);
              }
              v83 = (unsigned __int8)(v120 - v78)
                  | ((unsigned __int8)(v121 - v117) << 16)
                  | ((unsigned __int8)(v119 - v79) << 8)
                  | (-16777216 - (v81 << 24));
              v35 = *(double *)&bmpMem.__vftable;
              if ( v115 )
              {
                v84 = v55 + (__int64)v76;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * v84) = v83;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * v84 + 4) = v82;
              }
              else
              {
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * (v54 + (int)cx * v76)) = v83;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * (v54 + (int)cx * (v76 + 1))) = v82;
              }
              v56 = v123;
            }
            ++v53;
            v55 += cx;
            if ( ++v54 > v56 )
              break;
            v24 = v119;
            v25 = v120;
          }
        }
        v85 = v51 / sqrt(*(double *)&X.left);
        v86 = (int)ceil(v37 - v85);
        v87 = v86;
        v124 = (int)floor(v85 + v37);
        if ( v86 <= v124 )
        {
          v88 = cx * v86;
          v89 = v124;
          do
          {
            v90 = 1.0 - ((double)v86 - v37) / v35 * (((double)v86 - v37) / v35);
            if ( v90 >= 0.0 )
            {
              v91 = sqrt(v90) * v34;
              v92 = (int)floor(v36 - v91);
              v93 = v36 - v91 - (double)v92;
              v94 = (int)((double)v120 * v93);
              v95 = (int)((double)v119 * v93);
              v96 = (int)((double)v121 * v93);
              v97 = (int)(v93 * 255.0);
              v98 = (double)v126;
              *(double *)&size = (double)pBits;
              if ( clrFill == -1 )
              {
                v101 = (unsigned __int8)v94 | ((unsigned __int8)v96 << 16) | (((unsigned __int8)v95 | (v97 << 16)) << 8);
                v100 = (double)v125;
              }
              else
              {
                v99 = 1.0 - v93;
                v100 = (double)v125;
                v101 = (unsigned __int8)(int)((double)pBits * v99 + (double)v94)
                     | (((int)((double)v125 * v99 + (double)v96) | 0xFFFFFF00) << 16)
                     | ((unsigned __int8)(int)(v98 * v99 + (double)v95) << 8);
              }
              v102 = (unsigned __int8)(v120 - v94)
                   | ((unsigned __int8)(v121 - v96) << 16)
                   | ((unsigned __int8)(v119 - v95) << 8)
                   | (-16777216 - (v97 << 24));
              if ( v115 )
              {
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * (v87 + (int)cx * v92)) = v102;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * (v87 + (int)cx * (v92 + 1))) = v101;
              }
              else
              {
                v103 = v88 + (__int64)v92;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * v103) = v102;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * v103 + 4) = v101;
              }
              v104 = (int)ceil(v91 + v36);
              v105 = (double)v104 - v36 - v91;
              v106 = (int)((double)v120 * v105);
              v107 = (int)((double)v119 * v105);
              v108 = (int)((double)v121 * v105);
              v118 = v108;
              v109 = (int)(v105 * 255.0);
              if ( clrFill == -1 )
              {
                v110 = (unsigned __int8)v106
                     | ((unsigned __int8)v108 << 16)
                     | (((unsigned __int8)v107 | (v109 << 16)) << 8);
                v118 = v108;
              }
              else
              {
                v110 = (unsigned __int8)(int)(*(double *)&size * (1.0 - v105) + (double)v106)
                     | ((unsigned __int8)(int)(v98 * (1.0 - v105) + (double)v107) << 8)
                     | (((int)(v100 * (1.0 - v105) + (double)v108) | 0xFFFFFF00) << 16);
              }
              v111 = (unsigned __int8)(v120 - v106)
                   | ((unsigned __int8)(v121 - v118) << 16)
                   | ((unsigned __int8)(v119 - v107) << 8)
                   | (-16777216 - (v109 << 24));
              v35 = *(double *)&bmpMem.__vftable;
              if ( v115 )
              {
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * (v87 + (int)cx * v104)) = v111;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * (v87 + (int)cx * (v104 - 1))) = v110;
              }
              else
              {
                v112 = v88 + (__int64)v104;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * v112) = v111;
                *(_DWORD *)(*(_QWORD *)&v22 + 4 * v112 - 4) = v110;
              }
              v89 = v124;
            }
            ++v86;
            v88 += cx;
            ++v87;
          }
          while ( v87 <= v89 );
        }
        *(_QWORD *)&X.left = 0;
        X.right = cx;
        X.bottom = v130.cy;
        CDrawingManager::DrawAlpha(v136, v136->m_dc, (const CRect *)&rt[8], (CDC *)&dcMem.m_hDC, &X);
        v113 = SelectObject(dcMem.m_hAttribDC, v137->m_hObject);
        CGdiObject::FromHandle(v113);
        DeleteObject(ho);
        bmpMem.m_hObject = (void *)CBitmap::`vftable';
        CGdiObject::~CGdiObject((CGdiObject *)&bmpMem.m_hObject);
        CDC::~CDC((CDC *)&dcMem.m_hDC);
      }
    }
  }
}

```

## disassembly

```asm
0x18005bf90  mov     rax, rsp
0x18005bf93  mov     [rax+18h], rbx
0x18005bf97  push    rbp
0x18005bf98  push    rsi
0x18005bf99  push    rdi
0x18005bf9a  push    r12
0x18005bf9c  push    r13
0x18005bf9e  push    r14
0x18005bfa0  push    r15
0x18005bfa2  lea     rbp, [rax-0D8h]
0x18005bfa9  sub     rsp, 1A0h
0x18005bfb0  movaps  xmmword ptr [rax-48h], xmm6
0x18005bfb4  movaps  xmmword ptr [rax-58h], xmm7
0x18005bfb8  movaps  xmmword ptr [rax-68h], xmm8
0x18005bfbd  movaps  xmmword ptr [rax-78h], xmm9
0x18005bfc2  movaps  xmmword ptr [rax-88h], xmm10
0x18005bfca  movaps  xmmword ptr [rax-98h], xmm11
0x18005bfd2  movaps  xmmword ptr [rax-0A8h], xmm12
0x18005bfda  movaps  xmmword ptr [rax-0B8h], xmm13
0x18005bfe2  movaps  xmmword ptr [rax-0C8h], xmm14
0x18005bfea  movaps  xmmword ptr [rax-0D8h], xmm15
0x18005bff2  mov     rax, cs:__security_cookie
0x18005bff9  xor     rax, rsp
0x18005bffc  mov     [rbp+0D0h+var_E0], rax
0x18005c000  mov     r14d, clrLine
0x18005c003  mov     ebx, clrFill
0x18005c006  mov     r15, this
0x18005c009  mov     [rbp+0D0h+var_108], this
0x18005c00d  mov     r12d, clrFill
0x18005c010  mov     dword ptr [rsp+1D0h+pBits+4], clrFill
0x18005c015  or      eax, 0FFFFFFFFh
0x18005c018  cmp     clrFill, eax
0x18005c01b  jnz     short loc_18005C026
0x18005c01d  cmp     clrLine, eax
0x18005c020  jz      loc_18005CC6E
0x18005c026  movups  xmm0, xmmword ptr [rect]
0x18005c029  movups  xmmword ptr [rbp+0D0h+rt.right], xmm0
0x18005c02d  movd    edx, xmm0
0x18005c031  psrldq  xmm0, 8
0x18005c036  movd    esi, xmm0
0x18005c03a  cmp     edx, esi
0x18005c03c  jle     short loc_18005C04A
0x18005c03e  mov     eax, edx
0x18005c040  mov     edx, esi
0x18005c042  mov     [rbp+0D0h+rt.right], edx
0x18005c045  mov     esi, eax
0x18005c047  mov     [rbp+0D0h+var_120], eax
0x18005c04a  mov     ecx, [rbp+0D0h+rt.bottom]
0x18005c04d  mov     edi, [rbp+0D0h+var_11C]
0x18005c050  cmp     ecx, edi
0x18005c052  jle     short loc_18005C060
0x18005c054  mov     eax, ecx
0x18005c056  mov     ecx, edi
0x18005c058  mov     [rbp+0D0h+rt.bottom], ecx
0x18005c05b  mov     edi, eax
0x18005c05d  mov     [rbp+0D0h+var_11C], eax
0x18005c060  sub     edi, ecx
0x18005c062  sub     esi, edx
0x18005c064  mov     [rsp+1D0h+var_168.cx], esi
0x18005c068  mov     [rsp+1D0h+var_168.cy], edi
0x18005c06c  jz      loc_18005CC6E
0x18005c072  xor     r13d, r13d
0x18005c075  test    edi, edi
0x18005c077  jz      loc_18005CC6E
0x18005c07d  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18005c084  mov     [rbp+0D0h+dcMem.m_hDC], rax
0x18005c088  xorps   xmm0, xmm0
0x18005c08b  movdqu  xmmword ptr [rbp+0D0h+dcMem.m_hAttribDC], xmm0
0x18005c090  mov     [rbp+0D0h+rt.left], r13d
0x18005c094  mov     rax, [r15+8]
0x18005c098  test    rax, rax
0x18005c09b  mov     ecx, r13d
0x18005c09e  jz      short loc_18005C0A4
0x18005c0a0  mov     this, [rax+8]; hdc
0x18005c0a4  call    cs:__imp_CreateCompatibleDC
0x18005c0aa  mov     rect, rax; hDC
0x18005c0ad  lea     this, [rbp+0D0h+dcMem.m_hDC]; this
0x18005c0b1  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18005c0b6  test    eax, eax
0x18005c0b8  jnz     short loc_18005C0BF
0x18005c0ba  jmp     loc_18005CC4A
0x18005c0bf  mov     [rbp+0D0h+dcMem.__vftable], r13
0x18005c0c3  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005c0ca  mov     [rsp+1D0h+bmpMem.m_hObject], rax
0x18005c0cf  mov     this, [r15+8]
0x18005c0d3  mov     clrFill, edi; cy
0x18005c0d6  mov     edx, esi; cx
0x18005c0d8  mov     this, [this+8]; hdc
0x18005c0dc  call    cs:__imp_CreateCompatibleBitmap
0x18005c0e2  mov     rect, rax; hObject
0x18005c0e5  lea     this, [rsp+1D0h+bmpMem.m_hObject]; this
0x18005c0ea  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18005c0ef  test    eax, eax
0x18005c0f1  jnz     short loc_18005C10F
0x18005c0f3  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005c0fa  mov     [rsp+1D0h+bmpMem.m_hObject], rax
0x18005c0ff  lea     this, [rsp+1D0h+bmpMem.m_hObject]; this
0x18005c104  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005c109  nop
0x18005c10a  jmp     loc_18005CC4A
0x18005c10f  mov     rect, [rbp+0D0h+dcMem.__vftable]; h
0x18005c113  mov     this, [rbp+0D0h+dcMem.m_hAttribDC]; hdc
0x18005c117  call    cs:__imp_SelectObject
0x18005c11d  mov     this, rax; h
0x18005c120  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18005c125  mov     [rbp+0D0h+var_100], rax
0x18005c129  test    rax, rax
0x18005c12c  jz      loc_18005CCCD
0x18005c132  lea     rect, [rsp+1D0h+size]; pBits
0x18005c137  lea     this, [rsp+1D0h+var_168]; size
0x18005c13c  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x18005c141  mov     [rbp+0D0h+ho], rax
0x18005c145  test    rax, rax
0x18005c148  jz      loc_18005CC33
0x18005c14e  mov     rsi, qword ptr [rsp+1D0h+size.cx]
0x18005c153  test    rsi, rsi
0x18005c156  jz      loc_18005CC33
0x18005c15c  mov     rect, rax; h
0x18005c15f  mov     this, [rbp+0D0h+dcMem.m_hAttribDC]; hdc
0x18005c163  call    cs:__imp_SelectObject
0x18005c169  mov     ecx, ebx
0x18005c16b  or      clrLine, 0FFFFFFFFh
0x18005c16f  cmp     r14d, clrLine
0x18005c172  cmovnz  ecx, r14d
0x18005c176  movzx   eax, cl
0x18005c179  mov     dword ptr [rsp+1D0h+var_190], eax
0x18005c17d  movzx   r13d, cx
0x18005c181  shr     r13d, 8
0x18005c185  mov     [rsp+1D0h+var_198], r13d
0x18005c18a  shr     ecx, 10h
0x18005c18d  movzx   edi, cl
0x18005c190  mov     [rsp+1D0h+var_194], edi
0x18005c194  movzx   edx, bl
0x18005c197  mov     [rsp+1D0h+var_180], edx
0x18005c19b  movzx   ecx, bx
0x18005c19e  shr     ecx, 8
0x18005c1a1  mov     [rsp+1D0h+var_17C], ecx
0x18005c1a5  mov     eax, ebx
0x18005c1a7  shr     eax, 10h
0x18005c1aa  movzx   clrFill, al
0x18005c1ae  mov     dword ptr [rsp+1D0h+pBits], clrFill
0x18005c1b3  cmp     ebx, clrLine
0x18005c1b6  jz      short loc_18005C1CC
0x18005c1b8  mov     ebx, ecx
0x18005c1ba  shl     ebx, 8
0x18005c1bd  mov     eax, edx
0x18005c1bf  or      eax, 0FFFFFF00h
0x18005c1c4  shl     eax, 10h
0x18005c1c7  or      ebx, eax
0x18005c1c9  or      ebx, clrFill
0x18005c1cc  xorps   xmm10, xmm10
0x18005c1d0  xorps   xmm2, xmm2
0x18005c1d3  movsxd  r14, [rsp+1D0h+var_168.cx]
0x18005c1d8  lea     eax, [r14-1]
0x18005c1dc  movd    xmm7, eax
0x18005c1e0  cvtdq2pd xmm7, xmm7
0x18005c1e4  xorps   xmm3, xmm3
0x18005c1e7  mov     eax, [rsp+1D0h+var_168.cy]
0x18005c1eb  dec     eax
0x18005c1ed  movd    xmm8, eax
0x18005c1f2  cvtdq2pd xmm8, xmm8
0x18005c1f7  comisd  xmm10, xmm7
0x18005c1fc  jbe     short loc_18005C204
0x18005c1fe  movaps  xmm2, xmm7
0x18005c201  xorps   xmm7, xmm7
0x18005c204  comisd  xmm10, xmm8
0x18005c209  jbe     short loc_18005C213
0x18005c20b  movaps  xmm3, xmm8
0x18005c20f  xorps   xmm8, xmm8
0x18005c213  movaps  xmm4, xmm8
0x18005c217  subsd   xmm4, xmm3
0x18005c21b  movaps  xmm5, xmm7
0x18005c21e  subsd   xmm5, xmm2
0x18005c222  comisd  xmm5, xmm4
0x18005c226  jb      short loc_18005C23C
0x18005c228  movaps  xmm0, xmm2
0x18005c22b  movaps  xmm2, xmm3
0x18005c22e  movaps  xmm3, xmm0
0x18005c231  movaps  xmm1, xmm7
0x18005c234  movaps  xmm7, xmm8
0x18005c238  movaps  xmm8, xmm1
0x18005c23c  setnb   byte ptr [rsp+1D0h+var_1A0]
0x18005c241  movaps  xmm11, xmm7
0x18005c245  subsd   xmm11, xmm2
0x18005c24a  movsd   xmm0, cs:__real@3fe0000000000000
0x18005c252  mulsd   xmm11, xmm0
0x18005c257  movaps  xmm13, xmm8
0x18005c25b  subsd   xmm13, xmm3
0x18005c260  mulsd   xmm13, xmm0
0x18005c265  movsd   [rsp+1D0h+bmpMem.__vftable], xmm13
0x18005c26c  addsd   xmm7, xmm2
0x18005c270  mulsd   xmm7, xmm0
0x18005c274  addsd   xmm8, xmm3
0x18005c279  mulsd   xmm8, xmm0
0x18005c27e  cmp     r12d, clrLine
0x18005c281  jz      loc_18005C38B
0x18005c287  movaps  xmm0, xmm7
0x18005c28a  subsd   xmm0, xmm11; X
0x18005c28f  call    cs:__imp_ceil
0x18005c295  cvttsd2si r15d, xmm0
0x18005c29a  movaps  xmm0, xmm7
0x18005c29d  addsd   xmm0, xmm11; X
0x18005c2a2  call    cs:__imp_floor
0x18005c2a8  cvttsd2si eax, xmm0
0x18005c2ac  mov     [rsp+1D0h+var_19C], eax
0x18005c2b0  cmp     r15d, eax
0x18005c2b3  jg      loc_18005C38B
0x18005c2b9  movsxd  r12, r15d
0x18005c2bc  mov     [rsp+1D0h+var_188], r12
0x18005c2c1  mov     eax, r15d
0x18005c2c4  imul    eax, r14d
0x18005c2c8  movsxd  r13, eax
0x18005c2cb  mov     rdi, r14
0x18005c2ce  mov     eax, [rsp+1D0h+var_19C]
0x18005c2d2  movd    xmm1, r15d
0x18005c2d7  cvtdq2pd xmm1, xmm1
0x18005c2db  subsd   xmm1, xmm7
0x18005c2df  divsd   xmm1, xmm11
0x18005c2e4  mulsd   xmm1, xmm1
0x18005c2e8  movsd   xmm0, cs:__real@3ff0000000000000
0x18005c2f0  subsd   xmm0, xmm1; X
0x18005c2f4  comisd  xmm10, xmm0
0x18005c2f9  ja      short loc_18005C36B
0x18005c2fb  call    cs:__imp_sqrt
0x18005c301  movaps  xmm6, xmm0
0x18005c304  mulsd   xmm6, xmm13
0x18005c309  movaps  xmm0, xmm8
0x18005c30d  subsd   xmm0, xmm6; X
0x18005c311  addsd   xmm6, xmm8
0x18005c316  call    cs:__imp_ceil
0x18005c31c  cmp     byte ptr [rsp+1D0h+var_1A0], 0
0x18005c321  jnz     loc_18005C3F9
0x18005c327  cvttsd2si edi, xmm0
0x18005c32b  movaps  xmm0, xmm6; X
0x18005c32e  call    cs:__imp_floor
0x18005c334  cvttsd2si edx, xmm0
0x18005c338  mov     eax, edi
0x18005c33a  imul    eax, r14d
0x18005c33e  movsxd  this, eax
0x18005c341  add     this, r12
0x18005c344  lea     rax, [rsi+this*4]
0x18005c348  cmp     edi, edx
0x18005c34a  jg      short loc_18005C364
0x18005c34c  lea     r8, ds:0[r14*4]
0x18005c354  sub     edx, edi
0x18005c356  lea     ecx, [rect+1]
0x18005c359  mov     [rax], ebx
0x18005c35b  add     rax, r8
0x18005c35e  sub     this, 1
0x18005c362  jnz     short loc_18005C359
0x18005c364  mov     rdi, r14
0x18005c367  mov     eax, [rsp+1D0h+var_19C]
0x18005c36b  inc     r15d
0x18005c36e  inc     r12
0x18005c371  mov     [rsp+1D0h+var_188], r12
0x18005c376  add     r13, rdi
0x18005c379  cmp     r15d, eax
0x18005c37c  jle     loc_18005C2D2
0x18005c382  mov     r13d, [rsp+1D0h+var_198]
0x18005c387  mov     edi, [rsp+1D0h+var_194]
0x18005c38b  movaps  xmm6, xmm11
0x18005c38f  mulsd   xmm6, xmm11
0x18005c394  movaps  xmm9, xmm13
0x18005c398  mulsd   xmm9, xmm13
0x18005c39d  movaps  xmm0, xmm9
0x18005c3a1  addsd   xmm0, xmm6; X
0x18005c3a5  movsd   [rbp+0D0h+X], xmm0
0x18005c3aa  call    cs:__imp_sqrt
0x18005c3b0  divsd   xmm6, xmm0
0x18005c3b4  movaps  xmm0, xmm7
0x18005c3b7  subsd   xmm0, xmm6; X
0x18005c3bb  call    cs:__imp_floor
0x18005c3c1  cvttsd2si r12d, xmm0
0x18005c3c6  movsxd  rbx, r12d
0x18005c3c9  addsd   xmm6, xmm7
0x18005c3cd  movaps  xmm0, xmm6; X
0x18005c3d0  call    cs:__imp_ceil
0x18005c3d6  cvttsd2si eax, xmm0
0x18005c3da  movsxd  r15, eax
0x18005c3dd  mov     [rsp+1D0h+var_188], r15
0x18005c3e2  cmp     rbx, r15
0x18005c3e5  jg      loc_18005C7D5
0x18005c3eb  mov     r15d, r12d
0x18005c3ee  imul    r15d, r14d
0x18005c3f2  mov     rax, [rsp+1D0h+var_188]
0x18005c3f7  jmp     short loc_18005C446
0x18005c3f9  cvttsd2si r12d, xmm0
0x18005c3fe  movaps  xmm0, xmm6; X
0x18005c401  call    cs:__imp_floor
0x18005c407  cvttsd2si ecx, xmm0
0x18005c40b  movsxd  rax, r12d
0x18005c40e  add     rax, r13
0x18005c411  lea     rect, [rsi+rax*4]
0x18005c415  cmp     r12d, ecx
0x18005c418  jg      short loc_18005C433
0x18005c41a  sub     ecx, r12d
0x18005c41d  inc     ecx
0x18005c41f  movsxd  this, ecx
0x18005c422  mov     eax, ebx
0x18005c424  mov     rdi, rect
  ... truncated ...
```

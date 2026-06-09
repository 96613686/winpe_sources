# GpFaceRealization::GetGlyphPos(int,int,ushort const *,GpRuntime::GpGlyphPos *,PointF const *,int *,IDWriteGlyphBitmapArray *,int)

- ea: `0x1800e2c40`
- end: `0x1800e39de`
- name: `?GetGlyphPos@GpFaceRealization@@QEBAHHHPEBGPEAVGpGlyphPos@GpRuntime@@PEBVPointF@@PEAHPEAUIDWriteGlyphBitmapArray@@H@Z`
- size: `3486`
- prototype: `__int64 __fastcall(GpFaceRealization *this, int, int, const unsigned __int16 *, struct GpRuntime::GpGlyphPos *, const struct PointF *, int *, struct IDWriteGlyphBitmapArray *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x18003e980`

## callees

- `0x180048ac0`
- `0x18004bb6c`
- `0x1800724ac`
- `0x1800b6d00`
- `0x1800e2c40`
- `0x1800e9380`
- `0x1800e9774`
- `0x1800ea080`
- `0x1800ea08c`
- `0x1800ea0ec`
- `0x1801740cc`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e31fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e3245`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e36a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e31fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e3245`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e36a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e2ffe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e302d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e3059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e38f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e3927`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e394b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e2ffe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e302d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e3059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e38f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e3927`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e394b`

## pseudocode

```c
__int64 __fastcall GpFaceRealization::GetGlyphPos(
        GpFaceRealization *this,
        int a2,
        int a3,
        const unsigned __int16 *a4,
        struct GpRuntime::GpGlyphPos *a5,
        const struct PointF *a6,
        int *a7,
        struct IDWriteGlyphBitmapArray *a8)
{
  int *v8; // r14
  int v9; // r10d
  struct GpRuntime::GpGlyphPos *v10; // r12
  GpFaceRealization *v11; // rsi
  const struct PointF *v12; // r15
  int v13; // r11d
  struct IDWriteGlyphBitmapArray *v14; // r8
  int v15; // ecx
  int v16; // edx
  __int64 v17; // rax
  __int64 v18; // r13
  __int64 v19; // rdi
  bool v20; // bl
  __m128d v21; // xmm0
  __m128 v22; // xmm1
  int v23; // esi
  __m128d v24; // xmm0
  __m128 v25; // xmm1
  int v26; // eax
  int v27; // r14d
  PointF *v28; // rbx
  int v29; // esi
  __int64 v30; // rdi
  _QWORD *v31; // rcx
  __int64 v32; // rdi
  _BYTE *v33; // r8
  __int64 v34; // rax
  bool v35; // zf
  __int64 v36; // rax
  float v37; // xmm2_4
  int (__fastcall *v38)(struct IDWriteGlyphBitmapArray *, _QWORD); // rbx
  float v39; // xmm2_4
  int v40; // r8d
  int v41; // r15d
  int v42; // ecx
  __int64 v43; // rax
  unsigned __int64 v44; // rdx
  size_t v45; // r14
  __int64 v46; // r12
  size_t v47; // rdi
  unsigned __int8 *v48; // rax
  unsigned __int8 *v49; // rsi
  unsigned __int8 *v50; // rbx
  char *v51; // r13
  char *v52; // rax
  char *v53; // rcx
  __int64 v54; // r14
  double v55; // xmm0_8
  int v56; // r9d
  _QWORD *v57; // rdx
  size_t v58; // r10
  _WORD *v59; // rax
  struct IDWriteGlyphBitmapArray *v60; // r8
  int (__fastcall *v61)(struct IDWriteGlyphBitmapArray *, _QWORD); // r14
  __int64 v62; // rcx
  __int64 v63; // rcx
  const void *v64; // rdx
  __int64 v65; // r14
  struct DWriteCacheFaceRealization **v66; // r8
  __int16 *v67; // rdx
  unsigned __int8 *v68; // rcx
  __int64 v69; // rax
  unsigned int v70; // ecx
  unsigned __int64 v71; // rax
  _BYTE *v72; // r15
  unsigned __int64 v73; // r8
  char *v74; // r14
  _BYTE *v75; // rdi
  unsigned __int16 v76; // r9
  _BYTE *v77; // r11
  __int64 v78; // rsi
  char v79; // cl
  unsigned __int8 v80; // dl
  char v81; // cl
  unsigned __int16 v82; // r10
  __int64 v83; // r14
  void *v84; // r15
  size_t v85; // rsi
  void *v86; // rdi
  const void *v87; // rdx
  double v88; // xmm0_8
  double v89; // xmm0_8
  __int16 *v90; // rdi
  unsigned __int64 v91; // rax
  unsigned __int64 v92; // r11
  unsigned __int8 *v93; // r10
  unsigned int v94; // r8d
  unsigned int v95; // r9d
  char v96; // cl
  __int64 v97; // r14
  unsigned __int8 *v98; // rdx
  __int64 v99; // rax
  __int64 v100; // r14
  __int64 v102; // [rsp+38h] [rbp-C8h]
  int v103; // [rsp+50h] [rbp-B0h]
  unsigned int v104; // [rsp+54h] [rbp-ACh]
  __int64 v105; // [rsp+58h] [rbp-A8h]
  char *v108; // [rsp+70h] [rbp-90h]
  unsigned __int64 v110; // [rsp+80h] [rbp-80h]
  __int64 v111; // [rsp+90h] [rbp-70h]
  void *v112; // [rsp+A0h] [rbp-60h] BYREF
  size_t Size; // [rsp+A8h] [rbp-58h]
  __int64 v114; // [rsp+B0h] [rbp-50h]
  struct IDWriteGlyphBitmapArray *v115; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v116; // [rsp+C0h] [rbp-40h]
  unsigned int v117; // [rsp+C8h] [rbp-38h]
  int v118; // [rsp+CCh] [rbp-34h]
  char *v119; // [rsp+D0h] [rbp-30h]
  unsigned int v120[2]; // [rsp+D8h] [rbp-28h]
  char *v121; // [rsp+E0h] [rbp-20h]
  int *v122; // [rsp+E8h] [rbp-18h]
  unsigned __int8 *v123; // [rsp+F0h] [rbp-10h]
  __int64 v124; // [rsp+F8h] [rbp-8h]
  __int128 v125; // [rsp+100h] [rbp+0h] BYREF
  __int64 v126; // [rsp+110h] [rbp+10h]
  int v127; // [rsp+118h] [rbp+18h]
  char v128; // [rsp+11Ch] [rbp+1Ch]
  void **v129; // [rsp+120h] [rbp+20h] BYREF
  int v130; // [rsp+128h] [rbp+28h]
  __int64 v131; // [rsp+130h] [rbp+30h]
  int v132; // [rsp+138h] [rbp+38h]
  LPVOID v133; // [rsp+140h] [rbp+40h]
  _BYTE *v134; // [rsp+148h] [rbp+48h]
  int v135; // [rsp+150h] [rbp+50h]
  __int64 v136; // [rsp+154h] [rbp+54h]
  _BYTE v137[16]; // [rsp+160h] [rbp+60h] BYREF
  LPVOID v138; // [rsp+170h] [rbp+70h]
  _BYTE *v139; // [rsp+178h] [rbp+78h]
  int v140; // [rsp+180h] [rbp+80h]
  __int64 v141; // [rsp+184h] [rbp+84h]
  _BYTE v142[128]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v143; // [rsp+210h] [rbp+110h]
  int v144; // [rsp+220h] [rbp+120h]
  int v145; // [rsp+228h] [rbp+128h]
  int v146; // [rsp+22Ch] [rbp+12Ch]
  __int64 v147; // [rsp+230h] [rbp+130h]
  __int64 v148; // [rsp+238h] [rbp+138h]
  LPVOID lpMem; // [rsp+248h] [rbp+148h]
  _BYTE *v150; // [rsp+250h] [rbp+150h]
  int v151; // [rsp+258h] [rbp+158h]
  __int64 v152; // [rsp+25Ch] [rbp+15Ch]
  _BYTE v153[40]; // [rsp+268h] [rbp+168h] BYREF

  v8 = a7;
  v9 = a3;
  v10 = a5;
  v11 = this;
  v12 = a6;
  v13 = *(_DWORD *)(*(_QWORD *)this + 20LL);
  v14 = a8;
  v15 = *(_DWORD *)(*(_QWORD *)this + 16LL);
  v16 = 0;
  v118 = v13;
  *a7 = 0;
  v116 = a4;
  v122 = a7;
  v115 = a8;
  v104 = 0;
  v103 = 0;
  if ( v9 > 0 )
  {
    v17 = 1;
    v18 = 0;
    if ( !v15 )
      v17 = (unsigned int)v9;
    v19 = 0;
    v124 = v17;
    v105 = 0;
    v111 = 0;
    while ( 1 )
    {
      if ( v19 >= v17 )
        return v104;
      if ( a4[v18] == 0xFFFF )
        goto LABEL_123;
      if ( v13 == 1 )
        break;
      v35 = *(_DWORD *)(*(_QWORD *)v11 + 28LL) == 5;
      if ( *(int *)(*(_QWORD *)v11 + 28LL) > 5 )
        return v104;
      v36 = *(_QWORD *)v14;
      v37 = *((float *)v12 + 2 * v18);
      v125 = 0;
      v38 = *(int (__fastcall **)(struct IDWriteGlyphBitmapArray *, _QWORD))(v36 + 32);
      if ( v35 )
      {
        v39 = (float)(v37 * 6.0) + 0.5;
        if ( !Feature_GdiPlusOptimizations_Misc_IsEnabled )
        {
          floor(v39);
          v16 = v103;
          v14 = v115;
        }
      }
      if ( v38(v14, (unsigned int)(a2 + v16)) < 0 )
        return v104;
      v40 = DWORD1(v125);
      v41 = HIDWORD(v125) - DWORD1(v125);
      v42 = DWORD2(v125) - v125;
      if ( SDWORD1(v125) > SHIDWORD(v125) || (int)v125 > SDWORD2(v125) || v42 <= 0 || v41 <= 0 )
        goto LABEL_122;
      v43 = 32 * v19;
      v114 = v43;
      *(_QWORD *)v120 = v42;
      *(_DWORD *)((char *)v10 + v43) = v125;
      v44 = v42;
      *(_DWORD *)((char *)v10 + v43 + 4) = v40;
      *(_DWORD *)((char *)v10 + v43 + 8) = v42;
      *(_DWORD *)((char *)v10 + v43 + 12) = v41;
      v45 = 0;
      Size = 0;
      switch ( *(_DWORD *)(*(_QWORD *)v11 + 28LL) )
      {
        case 1:
        case 2:
          v44 = v42 + 31LL;
          break;
        case 3:
        case 4:
          v45 = v41 * v42;
          Size = v45;
          v44 = (16LL * v42 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
          break;
        case 5:
          Size = v41 * v42;
          v45 = Size;
          v44 = (6LL * v42 + 35) & 0xFFFFFFFFFFFFFFE0uLL;
          break;
      }
      v46 = v41;
      v47 = (v44 >> 3) * v41;
      v110 = v44 >> 3;
      if ( v44 < v42 )
        return v104;
      if ( v42 * (__int64)v41 > (unsigned __int64)(v41 * v42) )
        return v104;
      v48 = (unsigned __int8 *)HeapAlloc(GpRuntime::GpMemHeap, 0, (v44 >> 3) * v41);
      v49 = v48;
      if ( !v48 )
        return v104;
      v123 = v48;
      v50 = v48;
      memset_0(v48, 0, v47);
      v119 = 0;
      v51 = 0;
      v108 = 0;
      if ( v45 )
      {
        v52 = (char *)HeapAlloc(GpRuntime::GpMemHeap, 0, v45);
        v53 = 0;
        v119 = v52;
        v51 = v52;
        if ( !v52 )
          goto LABEL_137;
        operator delete(0, 1u);
        v108 = v51;
        memset_0(v51, 0, v45);
      }
      v54 = *(_QWORD *)this;
      if ( *(_DWORD *)(*(_QWORD *)this + 28LL) != 5 )
        goto LABEL_57;
      v55 = o_fmod_0();
      v56 = (int)floor(v55 * 6.0 + 0.5);
      v57 = *(_QWORD **)(v54 + 8 * (v116[v105] % 0xAuLL) + 224);
      if ( !v57 )
        goto LABEL_57;
      v58 = Size;
      while ( 1 )
      {
        v59 = (_WORD *)*v57;
        if ( *(_WORD *)*v57 == v116[v105] && *((_BYTE *)v59 + 2) == (_BYTE)v56 && *((_DWORD *)v59 + 1) == (_DWORD)Size )
          break;
        v57 = (_QWORD *)v57[1];
        if ( !v57 )
          goto LABEL_57;
      }
      v62 = *((_QWORD *)v59 + 3);
      if ( v62 )
      {
        *(_QWORD *)(v62 + 16) = *((_QWORD *)v59 + 2);
        if ( !*(_QWORD *)(*v57 + 16LL) )
          *(_QWORD *)(v54 + 208) = *(_QWORD *)(*v57 + 24LL);
        v63 = *(_QWORD *)(*v57 + 16LL);
        if ( v63 )
          *(_QWORD *)(v63 + 24) = *(_QWORD *)(*v57 + 24LL);
        *(_QWORD *)(*v57 + 24LL) = 0;
        *(_QWORD *)(*v57 + 16LL) = *(_QWORD *)(v54 + 200);
        *(_QWORD *)(*(_QWORD *)(v54 + 200) + 24LL) = *v57;
        *(_QWORD *)(v54 + 200) = *v57;
      }
      v64 = *(const void **)(*v57 + 8LL);
      if ( !v64 )
      {
LABEL_57:
        v60 = v115;
        v61 = *(int (__fastcall **)(struct IDWriteGlyphBitmapArray *, _QWORD))(*(_QWORD *)v115 + 40LL);
        if ( *(_DWORD *)(*(_QWORD *)this + 28LL) == 5 && !Feature_GdiPlusOptimizations_Misc_IsEnabled )
        {
          floor((float)((float)(*((float *)a6 + 2 * v105) * 6.0) + 0.5));
          v60 = v115;
        }
        HIDWORD(v102) = HIDWORD(v49);
        if ( v61(v60, (unsigned int)(v103 + a2)) < 0 )
        {
          v53 = v108;
LABEL_137:
          operator delete(v53, 1u);
          operator delete(v49, 1u);
          return v104;
        }
        v66 = (struct DWriteCacheFaceRealization **)this;
        if ( *(_DWORD *)(*(_QWORD *)this + 28LL) == 1 || *(_DWORD *)(*(_QWORD *)this + 28LL) == 2 )
        {
          if ( v47 )
          {
            v98 = v49;
            do
            {
              v99 = *v98++;
              *(v98 - 1) = *((_BYTE *)qword_1801871D0 + v99);
              --v47;
            }
            while ( v47 );
          }
          v100 = v114;
          v10 = a5;
          v50 = 0;
          *(_QWORD *)((char *)a5 + v114 + 24) = v49;
          *(_DWORD *)((char *)a5 + v100 + 16) = 1;
          goto LABEL_118;
        }
        if ( *(_DWORD *)(*(_QWORD *)this + 28LL) != 3 )
        {
          LODWORD(v67) = *(_DWORD *)(*(_QWORD *)this + 28LL) - 4;
          if ( *(_DWORD *)(*(_QWORD *)this + 28LL) != 4 )
          {
            if ( *(_DWORD *)(*(_QWORD *)this + 28LL) == 5 )
            {
              if ( v47 )
              {
                v68 = v49;
                v67 = &_ImageBase;
                do
                {
                  v69 = *v68++;
                  *(v68 - 1) = *((_BYTE *)qword_1801871D0 + v69);
                  --v47;
                }
                while ( v47 );
              }
              v70 = DWORD2(v125) - v125;
              v117 = DWORD2(v125) - v125;
              v71 = (unsigned int)(HIDWORD(v125) - DWORD1(v125));
              if ( HIDWORD(v125) != DWORD1(v125) )
              {
                v67 = *(__int16 **)v120;
                v72 = v49 + 1;
                v73 = v110;
                v121 = (char *)(v49 + 1);
                v112 = (void *)(unsigned int)(HIDWORD(v125) - DWORD1(v125));
                do
                {
                  v74 = v51;
                  v75 = v72 - 1;
                  v76 = 2;
                  if ( v70 )
                  {
                    v77 = v72;
                    v78 = v70;
                    do
                    {
                      v79 = 0;
                      if ( (__int16)(2 - v76) >= 0 )
                        v79 = 2 - v76;
                      v80 = (unsigned __int8)(*v75 & *((_BYTE *)qword_18018B378 + v76)) >> v79;
                      v81 = v76 - 2;
                      if ( (__int16)(2 - v76) >= 0 )
                        v81 = 0;
                      v82 = v80 << v81;
                      if ( v77 < &v72[v73 - 1] )
                        v82 += (unsigned __int8)(*v77 >> (10 - v76));
                      v76 += 6;
                      *v74++ = *((_BYTE *)&qword_18018B378[1] + v82);
                      if ( v76 >= 8u )
                      {
                        v76 &= 7u;
                        ++v75;
                        ++v77;
                      }
                      --v78;
                    }
                    while ( v78 );
                    v72 = v121;
                    v51 = v119;
                    v70 = v117;
                    v71 = (unsigned __int64)v112;
                    v67 = *(__int16 **)v120;
                    v73 = v110;
                  }
                  v72 += v73;
                  v51 = &v51[(_QWORD)v67];
                  --v71;
                  v121 = v72;
                  v112 = (void *)v71;
                  v119 = v51;
                }
                while ( v71 );
                v50 = v123;
                v66 = (struct DWriteCacheFaceRealization **)this;
              }
              v83 = v114;
              v84 = 0;
              v10 = a5;
              *(_QWORD *)((char *)a5 + v114 + 24) = v108;
              if ( v108 )
                *(_DWORD *)((char *)a5 + v83 + 16) = 1;
              ulClearTypeFilter((struct GpRuntime::GpGlyphPos *)((char *)a5 + 32 * (int)v104), (unsigned int)v67, *v66);
              v85 = Size;
              v86 = HeapAlloc(GpRuntime::GpMemHeap, 0, Size);
              if ( v86 )
              {
                operator delete(0, 1u);
                v112 = v86;
                if ( *(_DWORD *)((char *)a5 + v83 + 20) )
                  v87 = *(const void **)((char *)a5 + v83 + 24);
                else
                  v87 = 0;
                memcpy_0(v86, v87, v85);
                v18 = v105;
                v88 = o_fmod_0();
                v89 = floor(v88 * 6.0 + 0.5);
                DWriteCacheFaceRealization::GpClearTypeGlyphDataCache::Insert(
                  *(_DWORD *)this + 200,
                  v116[v105],
                  (int)v89,
                  (unsigned int)&v112,
                  v85);
                v84 = v112;
                goto LABEL_120;
              }
LABEL_119:
              v18 = v105;
              goto LABEL_120;
            }
            v10 = a5;
LABEL_118:
            v84 = v108;
            goto LABEL_119;
          }
        }
        v90 = *(__int16 **)v120;
        v91 = v110;
        do
        {
          v92 = 0;
          if ( v90 )
          {
            v93 = v49;
            do
            {
              v94 = v93[1];
              v95 = *v93;
              v93 += 2;
              v96 = 15;
              if ( (unsigned __int8)(*((_BYTE *)qword_180186350 + (v95 & 0xF))
                                   + *((_BYTE *)qword_180186350 + (v94 & 0xF))
                                   + *((_BYTE *)qword_180186350 + ((unsigned __int64)v95 >> 4))
                                   + *((_BYTE *)qword_180186350 + ((unsigned __int64)v94 >> 4))) < 0xFu )
                v96 = *((_BYTE *)qword_180186350 + (v95 & 0xF))
                    + *((_BYTE *)qword_180186350 + (v94 & 0xF))
                    + *((_BYTE *)qword_180186350 + ((unsigned __int64)v95 >> 4))
                    + *((_BYTE *)qword_180186350 + ((unsigned __int64)v94 >> 4));
              v51[v92++] = v96;
            }
            while ( v92 < (unsigned __int64)v90 );
            v91 = v110;
          }
          v49 += v91;
          v51 = &v51[(_QWORD)v90];
          --v46;
        }
        while ( v46 );
        v97 = v114;
        v84 = 0;
        v10 = a5;
        v18 = v105;
        *(_QWORD *)((char *)a5 + v114 + 24) = v108;
        if ( v108 )
          *(_DWORD *)((char *)a5 + v97 + 16) = 1;
LABEL_120:
        operator delete(v84, 1u);
        operator delete(v50, 1u);
        v32 = v111;
LABEL_121:
        ++v104;
        v8 = v122;
        v19 = v32 + 1;
        v111 = v19;
LABEL_122:
        v9 = a3;
        v16 = v103;
LABEL_123:
        ++*v8;
        goto LABEL_124;
      }
      memcpy_0(v51, v64, v58);
      v65 = v114;
      v10 = a5;
      *(_QWORD *)((char *)a5 + v114 + 24) = v108;
      if ( v108 )
        *(_DWORD *)((char *)a5 + v65 + 16) = 1;
      v8 = v122;
      v19 = v111 + 1;
      ++v104;
      ++v111;
      ++*v122;
      operator delete(0, 1u);
      operator delete(v49, 1u);
      v16 = v103;
      v9 = a3;
      v18 = v105;
LABEL_124:
      ++v16;
      ++v18;
      v103 = v16;
      v105 = v18;
      if ( v16 >= v9 )
        return v104;
      v11 = this;
      v12 = a6;
      v14 = v115;
      a4 = v116;
      v13 = v118;
      v17 = v124;
    }
    v20 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v21 = _mm_cvtps_pd((__m128)*((unsigned int *)v12 + 2 * v18));
    v21.m128d_f64[0] = v21.m128d_f64[0] * 16.0;
    v22 = _mm_cvtpd_ps(v21);
    v22.m128_f32[0] = v22.m128_f32[0] + 0.5;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
      v23 = (int)_mm_round_ss(v22, v22, 9).m128_f32[0];
    else
      v23 = (int)floor(v22.m128_f32[0]);
    v24 = _mm_cvtps_pd((__m128)*((unsigned int *)v12 + 2 * v18 + 1));
    v24.m128d_f64[0] = v24.m128d_f64[0] * 16.0;
    v25 = _mm_cvtpd_ps(v24);
    v25.m128_f32[0] = v25.m128_f32[0] + 0.5;
    if ( v20 )
      v26 = (int)_mm_round_ss(v25, v25, 9).m128_f32[0];
    else
      v26 = (int)floor(v25.m128_f32[0]);
    v130 = 1279869254;
    v27 = (v26 + 8) >> 4;
    v129 = &DpPath::`vftable';
    v28 = (PointF *)v142;
    v135 = 16;
    v134 = v137;
    v29 = (v23 + 8) >> 4;
    v133 = v137;
    v131 = 0;
    v139 = v142;
    v138 = v142;
    v136 = 16;
    v30 = 16;
    v140 = 16;
    v141 = 16;
    do
    {
      PointF::PointF(v28);
      v28 = (PointF *)((char *)v28 + 8);
      --v30;
    }
    while ( v30 );
    v129 = &GpPath::`vftable';
    v145 = -1;
    v150 = v153;
    v148 = 0;
    lpMem = v153;
    *(_QWORD *)&v125 = &GeometryAdapterSink::`vftable';
    *((_QWORD *)&v125 + 1) = &v129;
    v147 = 0;
    v151 = 3;
    v152 = 3;
    v31 = *(_QWORD **)this;
    v132 = 0;
    v143 = 0;
    v144 = 1;
    HIDWORD(v136) = 0;
    HIDWORD(v141) = 0;
    v131 = 0;
    v146 = 0;
    v130 = 1752453169;
    v126 = 0;
    v128 = 0;
    v127 = 0;
    LODWORD(v102) = 0;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, _QWORD, int, _DWORD, __int64, __int128 *))(*(_QWORD *)*v31 + 112LL))(
           *v31,
           *(unsigned __int16 *)(v31[8] + 112LL),
           &v116[v103],
           0,
           0,
           1,
           0,
           v102,
           &v125) < 0 )
    {
      if ( lpMem != v150 && lpMem )
        HeapFree(GpRuntime::GpMemHeap, 0, lpMem);
      v129 = &DpPath::`vftable';
      if ( v138 != v139 && v138 )
        HeapFree(GpRuntime::GpMemHeap, 0, v138);
      if ( v133 != v134 && v133 )
        HeapFree(GpRuntime::GpMemHeap, 0, v133);
      return v104;
    }
    if ( v130 != 1752453169 )
    {
      GpPath::~GpPath((GpPath *)&v129);
      return v104;
    }
    v32 = v111;
    v33 = lpMem;
    v34 = 32 * v111;
    *(_DWORD *)((char *)v10 + v34) = v29;
    *(_DWORD *)((char *)v10 + v34 + 4) = v27;
    *(_DWORD *)((char *)v10 + v34 + 8) = 1;
    *(_DWORD *)((char *)v10 + v34 + 12) = 1;
    *(_QWORD *)((char *)v10 + v34 + 24) = &v129;
    *(_DWORD *)((char *)v10 + v34 + 20) = 0;
    if ( v33 != v150 && v33 )
      HeapFree(GpRuntime::GpMemHeap, 0, v33);
    v129 = &DpPath::`vftable';
    if ( v138 != v139 && v138 )
      HeapFree(GpRuntime::GpMemHeap, 0, v138);
    if ( v133 != v134 && v133 )
      HeapFree(GpRuntime::GpMemHeap, 0, v133);
    goto LABEL_121;
  }
  return v104;
}

```

## disassembly

```asm
0x1800e2c40  push    rbp
0x1800e2c42  push    rbx
0x1800e2c43  push    rsi
0x1800e2c44  push    r12
0x1800e2c46  push    r14
0x1800e2c48  push    r15
0x1800e2c4a  lea     rbp, [rsp-208h]
0x1800e2c52  sub     rsp, 308h
0x1800e2c59  mov     rax, cs:__security_cookie
0x1800e2c60  xor     rax, rsp
0x1800e2c63  mov     [rbp+230h+var_A0], rax
0x1800e2c6a  mov     rax, [rcx]
0x1800e2c6d  xor     ebx, ebx
0x1800e2c6f  mov     r14, [rbp+230h+arg_30]
0x1800e2c76  mov     r10d, r8d
0x1800e2c79  mov     r12, [rbp+230h+arg_20]
0x1800e2c80  mov     rsi, rcx
0x1800e2c83  mov     r15, [rbp+230h+arg_28]
0x1800e2c8a  mov     r11d, [rax+14h]
0x1800e2c8e  mov     [rsp+330h+var_2D0], r8d
0x1800e2c93  mov     r8, [rbp+230h+arg_38]
0x1800e2c9a  mov     [rsp+330h+var_2C8], rcx
0x1800e2c9f  mov     ecx, [rax+10h]
0x1800e2ca2  mov     [rsp+330h+var_2B8], edx
0x1800e2ca6  mov     edx, ebx
0x1800e2ca8  mov     [rbp+230h+var_264], r11d
0x1800e2cac  mov     [r14], ebx
0x1800e2caf  mov     [rbp+230h+var_270], r9
0x1800e2cb3  mov     [rbp+230h+var_2A8], r12
0x1800e2cb7  mov     [rbp+230h+var_298], r15
0x1800e2cbb  mov     [rbp+230h+var_248], r14
0x1800e2cbf  mov     [rbp+230h+var_278], r8
0x1800e2cc3  mov     [rsp+330h+var_2DC], ebx
0x1800e2cc7  mov     [rsp+330h+var_2E0], ebx
0x1800e2ccb  test    r10d, r10d
0x1800e2cce  jle     loc_1800E39B9
0x1800e2cd4  mov     [rsp+330h+arg_10], rdi
0x1800e2cdc  mov     eax, 1
0x1800e2ce1  mov     [rsp+330h+var_30], r13
0x1800e2ce9  test    ecx, ecx
0x1800e2ceb  movaps  [rsp+330h+var_40], xmm6
0x1800e2cf3  mov     r13d, ebx
0x1800e2cf6  movss   xmm6, cs:__real@3f000000
0x1800e2cfe  cmovz   eax, r10d
0x1800e2d02  movaps  [rsp+330h+var_50], xmm7
0x1800e2d0a  mov     edi, ebx
0x1800e2d0c  movss   xmm7, cs:__real@40c00000
0x1800e2d14  movaps  [rsp+330h+var_60], xmm8
0x1800e2d1d  movsd   xmm8, cs:__real@4030000000000000
0x1800e2d26  movaps  [rsp+330h+var_70], xmm9
0x1800e2d2f  movsd   xmm9, cs:__real@3ff0000000000000
0x1800e2d38  movaps  [rsp+330h+var_80], xmm10
0x1800e2d41  movsd   xmm10, cs:__real@4018000000000000
0x1800e2d4a  movaps  [rsp+330h+var_90], xmm11
0x1800e2d53  movsd   xmm11, cs:__real@3fe0000000000000
0x1800e2d5c  mov     [rbp+230h+var_238], rax
0x1800e2d60  mov     [rsp+330h+var_2D8], rbx
0x1800e2d65  mov     [rbp+230h+var_2A0], rbx
0x1800e2d69  mov     ebx, 0FFFFh
0x1800e2d6e  cmp     rdi, rax
0x1800e2d71  jge     loc_1800E3975
0x1800e2d77  cmp     [r9+r13*2], bx
0x1800e2d7c  jz      loc_1800E3898
0x1800e2d82  cmp     r11d, 1
0x1800e2d86  jnz     loc_1800E306A
0x1800e2d8c  movss   xmm0, dword ptr [r15+r13*8]
0x1800e2d92  movzx   ebx, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800e2d99  cvtps2pd xmm0, xmm0
0x1800e2d9c  mulsd   xmm0, xmm8
0x1800e2da1  cvtpd2ps xmm1, xmm0
0x1800e2da5  addss   xmm1, xmm6
0x1800e2da9  test    bl, bl
0x1800e2dab  jz      short loc_1800E2DBF
0x1800e2dad  movaps  xmm0, xmm1
0x1800e2db0  movaps  xmm1, xmm0
0x1800e2db3  roundss xmm1, xmm1, 9
0x1800e2db9  cvttss2si esi, xmm1
0x1800e2dbd  jmp     short loc_1800E2DCB
0x1800e2dbf  cvtps2pd xmm0, xmm1; X
0x1800e2dc2  call    floor
0x1800e2dc7  cvttsd2si esi, xmm0
0x1800e2dcb  movss   xmm0, dword ptr [r15+r13*8+4]
0x1800e2dd2  cvtps2pd xmm0, xmm0
0x1800e2dd5  mulsd   xmm0, xmm8
0x1800e2dda  cvtpd2ps xmm1, xmm0
0x1800e2dde  addss   xmm1, xmm6
0x1800e2de2  test    bl, bl
0x1800e2de4  jz      short loc_1800E2DF8
0x1800e2de6  movaps  xmm0, xmm1
0x1800e2de9  movaps  xmm1, xmm0
0x1800e2dec  roundss xmm1, xmm1, 9
0x1800e2df2  cvttss2si eax, xmm1
0x1800e2df6  jmp     short loc_1800E2E04
0x1800e2df8  cvtps2pd xmm0, xmm1; X
0x1800e2dfb  call    floor
0x1800e2e00  cvttsd2si eax, xmm0
0x1800e2e04  lea     r14d, [rax+8]
0x1800e2e08  mov     [rbp+230h+var_208], 4C494146h
0x1800e2e0f  lea     rax, ??_7DpPath@@6B@; const DpPath::`vftable'
0x1800e2e16  sar     r14d, 4
0x1800e2e1a  mov     [rbp+230h+var_210], rax
0x1800e2e1e  lea     rbx, [rbp+230h+var_1A0]
0x1800e2e25  lea     rax, [rbp+230h+var_1D0]
0x1800e2e29  mov     [rbp+230h+var_1E0], 10h
0x1800e2e30  mov     [rbp+230h+var_1E8], rax
0x1800e2e34  add     esi, 8
0x1800e2e37  lea     rax, [rbp+230h+var_1D0]
0x1800e2e3b  sar     esi, 4
0x1800e2e3e  mov     [rbp+230h+var_1F0], rax
0x1800e2e42  xor     r15d, r15d
0x1800e2e45  lea     rax, [rbp+230h+var_1A0]
0x1800e2e4c  mov     [rbp+230h+var_200], r15
0x1800e2e50  mov     [rbp+230h+var_1B8], rax
0x1800e2e54  lea     rax, [rbp+230h+var_1A0]
0x1800e2e5b  mov     [rbp+230h+var_1C0], rax
0x1800e2e5f  mov     [rbp+230h+var_1DC], 10h
0x1800e2e67  lea     edi, [r15+10h]
0x1800e2e6b  mov     [rbp+230h+var_1B0], 10h
0x1800e2e75  mov     [rbp+230h+var_1AC], 10h
0x1800e2e80  mov     rcx, rbx; this
0x1800e2e83  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x1800e2e88  add     rbx, 8
0x1800e2e8c  sub     rdi, 1
0x1800e2e90  jnz     short loc_1800E2E80
0x1800e2e92  mov     r8, [rbp+230h+var_270]
0x1800e2e96  lea     rax, ??_7GpPath@@6B@; const GpPath::`vftable'
0x1800e2e9d  mov     [rbp+230h+var_210], rax
0x1800e2ea1  xorps   xmm0, xmm0
0x1800e2ea4  mov     [rbp+230h+var_108], 0FFFFFFFFh
0x1800e2eae  lea     rax, [rbp+230h+var_C8]
0x1800e2eb5  mov     [rbp+230h+var_E0], rax
0x1800e2ebc  xor     r9d, r9d
0x1800e2ebf  mov     [rbp+230h+var_F8], r15
0x1800e2ec6  lea     rax, [rbp+230h+var_C8]
0x1800e2ecd  mov     [rbp+230h+lpMem], rax
0x1800e2ed4  lea     rax, ??_7GeometryAdapterSink@@6B@; const GeometryAdapterSink::`vftable'
0x1800e2edb  mov     qword ptr [rbp+230h+var_230], rax
0x1800e2edf  lea     rax, [rbp+230h+var_210]
0x1800e2ee3  mov     qword ptr [rbp+230h+var_230+8], rax
0x1800e2ee7  mov     rax, [rsp+330h+var_2C8]
0x1800e2eec  mov     [rbp+230h+var_100], r15
0x1800e2ef3  mov     [rbp+230h+var_D8], 3
0x1800e2efd  mov     [rbp+230h+var_D4], 3
0x1800e2f08  mov     rcx, [rax]
0x1800e2f0b  mov     [rbp+230h+var_1F8], r15d
0x1800e2f0f  movdqu  [rbp+230h+var_120], xmm0
0x1800e2f17  mov     [rbp+230h+var_110], 1
0x1800e2f21  mov     dword ptr [rbp+230h+var_1DC+4], r15d
0x1800e2f25  mov     dword ptr [rbp+230h+var_1AC+4], r15d
0x1800e2f2c  mov     [rbp+230h+var_200], r15
0x1800e2f30  mov     [rbp+230h+var_104], r15d
0x1800e2f37  mov     [rbp+230h+var_208], 68745031h
0x1800e2f3e  mov     [rbp+230h+var_220], r15
0x1800e2f42  mov     [rbp+230h+var_214], r15b
0x1800e2f46  mov     [rbp+230h+var_218], r15d
0x1800e2f4a  mov     r11, [rcx]
0x1800e2f4d  mov     rax, [r11]
0x1800e2f50  mov     r10, [rax+70h]
0x1800e2f54  mov     rax, [rcx+40h]
0x1800e2f58  mov     rcx, r11
0x1800e2f5b  movzx   edx, word ptr [rax+70h]
0x1800e2f5f  movsxd  rax, [rsp+330h+var_2E0]
0x1800e2f64  movd    xmm1, edx
0x1800e2f68  lea     r8, [r8+rax*2]
0x1800e2f6c  lea     rax, [rbp+230h+var_230]
0x1800e2f70  mov     [rsp+330h+var_2F0], rax
0x1800e2f75  mov     rax, r10
0x1800e2f78  mov     dword ptr [rsp+330h+var_2F8], r15d
0x1800e2f7d  mov     [rsp+330h+var_300], r15d
0x1800e2f82  cvtdq2ps xmm1, xmm1
0x1800e2f85  mov     [rsp+330h+var_308], 1
0x1800e2f8d  mov     [rsp+330h+var_310], r15
0x1800e2f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2f97  test    eax, eax
0x1800e2f99  js      loc_1800E38DA
0x1800e2f9f  cmp     [rbp+230h+var_208], 68745031h
0x1800e2fa6  lea     rcx, [rbp+230h+var_210]; this
0x1800e2faa  jnz     loc_1800E38D0
0x1800e2fb0  mov     rdi, [rbp+230h+var_2A0]
0x1800e2fb4  mov     r8, [rbp+230h+lpMem]; lpMem
0x1800e2fbb  mov     rax, rdi
0x1800e2fbe  shl     rax, 5
0x1800e2fc2  mov     [rax+r12], esi
0x1800e2fc6  mov     [rax+r12+4], r14d
0x1800e2fcb  mov     dword ptr [rax+r12+8], 1
0x1800e2fd4  mov     dword ptr [rax+r12+0Ch], 1
0x1800e2fdd  mov     [rax+r12+18h], rcx
0x1800e2fe2  mov     [rax+r12+14h], r15d
0x1800e2fe7  cmp     r8, [rbp+230h+var_E0]
0x1800e2fee  jz      short loc_1800E300A
0x1800e2ff0  test    r8, r8
0x1800e2ff3  jz      short loc_1800E300A
0x1800e2ff5  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800e2ffc  xor     edx, edx; dwFlags
0x1800e2ffe  call    cs:__imp_HeapFree
0x1800e3005  nop     dword ptr [rax+rax+00h]
0x1800e300a  mov     r8, [rbp+230h+var_1C0]; lpMem
0x1800e300e  lea     rax, ??_7DpPath@@6B@; const DpPath::`vftable'
0x1800e3015  mov     [rbp+230h+var_210], rax
0x1800e3019  cmp     r8, [rbp+230h+var_1B8]
0x1800e301d  jz      short loc_1800E3039
0x1800e301f  test    r8, r8
0x1800e3022  jz      short loc_1800E3039
0x1800e3024  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800e302b  xor     edx, edx; dwFlags
0x1800e302d  call    cs:__imp_HeapFree
0x1800e3034  nop     dword ptr [rax+rax+00h]
0x1800e3039  mov     r8, [rbp+230h+var_1F0]; lpMem
0x1800e303d  cmp     r8, [rbp+230h+var_1E8]
0x1800e3041  jz      loc_1800E3880
0x1800e3047  test    r8, r8
0x1800e304a  jz      loc_1800E3880
0x1800e3050  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800e3057  xor     edx, edx; dwFlags
0x1800e3059  call    cs:__imp_HeapFree
0x1800e3060  nop     dword ptr [rax+rax+00h]
0x1800e3065  jmp     loc_1800E3880
0x1800e306a  mov     rax, [rsi]
0x1800e306d  cmp     dword ptr [rax+1Ch], 5
0x1800e3071  jg      loc_1800E3975
0x1800e3077  mov     rax, [r8]
0x1800e307a  xorps   xmm0, xmm0
0x1800e307d  movss   xmm2, dword ptr [r15+r13*8]
0x1800e3083  movups  [rbp+230h+var_230], xmm0
0x1800e3087  mov     rbx, [rax+20h]
0x1800e308b  jnz     short loc_1800E30CF
0x1800e308d  cmp     cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA, 0; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800e3094  mulss   xmm2, xmm7
0x1800e3098  addss   xmm2, xmm6
0x1800e309c  jz      short loc_1800E30B0
0x1800e309e  movaps  xmm0, xmm2
0x1800e30a1  movaps  xmm1, xmm0
0x1800e30a4  roundss xmm1, xmm1, 9
0x1800e30aa  cvttss2si eax, xmm1
0x1800e30ae  jmp     short loc_1800E30C4
0x1800e30b0  cvtps2pd xmm0, xmm2; X
0x1800e30b3  call    floor
0x1800e30b8  mov     edx, [rsp+330h+var_2E0]
0x1800e30bc  mov     r8, [rbp+230h+var_278]
0x1800e30c0  cvttsd2si eax, xmm0
0x1800e30c4  movd    xmm2, eax
0x1800e30c8  cvtdq2ps xmm2, xmm2
0x1800e30cb  divss   xmm2, xmm7
0x1800e30cf  add     edx, [rsp+330h+var_2B8]
0x1800e30d3  lea     rcx, [rbp+230h+var_230]
0x1800e30d7  movss   xmm3, dword ptr [r15+r13*8+4]
0x1800e30de  mov     rax, rbx
0x1800e30e1  mov     [rsp+330h+var_310], rcx
0x1800e30e6  mov     rcx, r8
0x1800e30e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e30ee  test    eax, eax
0x1800e30f0  js      loc_1800E3975
0x1800e30f6  mov     r8d, dword ptr [rbp+230h+var_230+4]
0x1800e30fa  mov     r9d, dword ptr [rbp+230h+var_230+8]
0x1800e30fe  mov     ecx, r9d
0x1800e3101  mov     r15d, dword ptr [rbp+230h+var_230+0Ch]
0x1800e3105  mov     edx, dword ptr [rbp+230h+var_230]
0x1800e3108  sub     r15d, r8d
0x1800e310b  sub     ecx, edx
0x1800e310d  cmp     r8d, dword ptr [rbp+230h+var_230+0Ch]
0x1800e3111  jg      loc_1800E388F
0x1800e3117  cmp     edx, r9d
0x1800e311a  jg      loc_1800E388F
0x1800e3120  test    ecx, ecx
0x1800e3122  jle     loc_1800E388F
0x1800e3128  test    r15d, r15d
0x1800e312b  jle     loc_1800E388F
0x1800e3131  movsxd  r10, ecx
0x1800e3134  mov     rax, rdi
0x1800e3137  shl     rax, 5
0x1800e313b  mov     [rbp+230h+var_280], rax
0x1800e313f  mov     qword ptr [rbp+230h+var_258], r10
0x1800e3143  mov     [rax+r12], edx
0x1800e3147  mov     rdx, r10
0x1800e314a  mov     [rax+r12+4], r8d
0x1800e314f  mov     [rax+r12+8], ecx
0x1800e3154  imul    ecx, r15d
0x1800e3158  mov     [rax+r12+0Ch], r15d
0x1800e315d  xor     eax, eax
0x1800e315f  mov     r14d, eax
0x1800e3162  mov     [rbp+230h+Size], rax
0x1800e3166  movsxd  r9, ecx
0x1800e3169  mov     rcx, [rsi]
0x1800e316c  mov     r8d, [rcx+1Ch]
0x1800e3170  sub     r8d, 1
0x1800e3174  jz      short loc_1800E31BC
0x1800e3176  sub     r8d, 1
0x1800e317a  jz      short loc_1800E31BC
0x1800e317c  sub     r8d, 1
0x1800e3180  jz      short loc_1800E31A7
0x1800e3182  sub     r8d, 1
0x1800e3186  jz      short loc_1800E31A7
0x1800e3188  cmp     r8d, 1
0x1800e318c  jnz     short loc_1800E31C0
0x1800e318e  lea     rax, [r10+r10*2]
0x1800e3192  mov     [rbp+230h+Size], r9
0x1800e3196  lea     rdx, ds:23h[rax*2]
0x1800e319e  mov     r14, r9
0x1800e31a1  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800e31a5  jmp     short loc_1800E31C0
  ... truncated ...
```

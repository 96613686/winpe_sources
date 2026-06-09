# NDXGI::CDevice::Blt(IDXGIResource *,tagRECT const *,tagRECT const *,uint,IDXGIResource *,tagRECT const *,SUBRESOURCE_BLT_MAP const *,unsigned __int64,uint,uint)

- ea: `0x18001ec00`
- end: `0x18001fa89`
- name: `?Blt@CDevice@NDXGI@@UEAAJPEAUIDXGIResource@@PEBUtagRECT@@1I01PEBUSUBRESOURCE_BLT_MAP@@_KII@Z`
- size: `3721`
- prototype: `int(NDXGI::CDevice *__hidden this, struct IDXGIResource *, const struct tagRECT *, const struct tagRECT *, unsigned int, struct IDXGIResource *, const struct tagRECT *, const struct SUBRESOURCE_BLT_MAP *, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180009660`
- `0x18001de44`
- `0x18001ec00`
- `0x18001fa90`
- `0x18001faa4`
- `0x18001fd1c`
- `0x180022400`
- `0x18002d0f0`
- `0x18002e160`
- `0x18002fc40`
- `0x180043ae0`
- `0x180071af4`
- `0x18009d94c`
- `0x18009da0c`
- `0x18009f7e8`
- `0x1800a9d20`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f818`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f818`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f8d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f8d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f80a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f86f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f80a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f86f`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall NDXGI::CDevice::Blt(
        NDXGI::CDevice *this,
        struct IDXGIResource *a2,
        const struct tagRECT *a3,
        __m128i *a4,
        unsigned int a5,
        struct IDXGIResource *a6,
        const struct tagRECT *a7,
        const struct SUBRESOURCE_BLT_MAP *a8,
        struct IDXGIResource *a9,
        char a10,
        unsigned int a11)
{
  int v12; // ebx
  LONG v13; // r15d
  LONG v14; // r12d
  int v15; // esi
  int v16; // r14d
  int v17; // ebx
  unsigned int v18; // edi
  int v19; // eax
  __int64 v20; // rax
  unsigned int *v21; // rbx
  unsigned int v22; // r11d
  __int64 v23; // r8
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rdi
  unsigned __int128 v26; // kr10_16
  int v27; // ebx
  unsigned int v28; // edi
  int v29; // esi
  int v30; // r14d
  int v31; // edx
  unsigned int v32; // r12d
  float v33; // xmm6_4
  float v34; // xmm8_4
  const struct SUBRESOURCE_BLT_MAP **v35; // r8
  bool v36; // al
  GUID *v37; // rdx
  NDXGI::CDevice *v38; // rcx
  NDXGI::CDevice *v39; // rcx
  unsigned int NonOpaquePlaneCount; // eax
  unsigned int v41; // r9d
  const struct SUBRESOURCE_BLT_MAP *v42; // r10
  __int64 v43; // r14
  unsigned int v44; // r15d
  unsigned int v45; // r9d
  unsigned int v46; // r8d
  unsigned int v47; // ecx
  unsigned int v48; // eax
  unsigned int v49; // ebx
  void (__fastcall ***v50)(_QWORD, GUID *, const struct SUBRESOURCE_BLT_MAP **); // rcx
  __int64 result; // rax
  NDXGI::CDevice *v52; // rbx
  int v53; // eax
  _QWORD *v54; // rsi
  _QWORD *v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rdx
  _QWORD *v59; // rax
  __int64 v60; // rax
  __int64 v61; // rdx
  NDXGI::CDevice *v62; // r14
  RTL_SRWLOCK *v63; // rdi
  char v64; // [rsp+50h] [rbp-258h]
  char v65; // [rsp+50h] [rbp-258h]
  char v66; // [rsp+51h] [rbp-257h]
  unsigned int v67; // [rsp+54h] [rbp-254h]
  int ParentFormat; // [rsp+54h] [rbp-254h]
  int v69; // [rsp+54h] [rbp-254h]
  int v70; // [rsp+58h] [rbp-250h]
  int v71; // [rsp+58h] [rbp-250h]
  unsigned int bottom; // [rsp+5Ch] [rbp-24Ch]
  int v73; // [rsp+60h] [rbp-248h]
  unsigned int v74; // [rsp+60h] [rbp-248h]
  LONG left; // [rsp+64h] [rbp-244h]
  int v76; // [rsp+64h] [rbp-244h]
  __int64 v77; // [rsp+68h] [rbp-240h] BYREF
  unsigned int top; // [rsp+70h] [rbp-238h]
  unsigned int right; // [rsp+74h] [rbp-234h]
  unsigned int v80; // [rsp+78h] [rbp-230h]
  const struct SUBRESOURCE_BLT_MAP *v81; // [rsp+80h] [rbp-228h] BYREF
  unsigned int v82; // [rsp+88h] [rbp-220h]
  unsigned int v83; // [rsp+8Ch] [rbp-21Ch]
  unsigned int v84; // [rsp+90h] [rbp-218h] BYREF
  NDXGI::CDevice *v85; // [rsp+98h] [rbp-210h]
  void (__fastcall ***v86)(_QWORD, GUID *, const struct SUBRESOURCE_BLT_MAP **); // [rsp+A0h] [rbp-208h] BYREF
  NDXGI::CResource *v87; // [rsp+A8h] [rbp-200h] BYREF
  NDXGI::CResource *v88; // [rsp+B0h] [rbp-1F8h]
  struct IDXGIResource *v89; // [rsp+B8h] [rbp-1F0h] BYREF
  __int64 v90; // [rsp+C0h] [rbp-1E8h] BYREF
  int v91; // [rsp+C8h] [rbp-1E0h]
  __int64 v92; // [rsp+CCh] [rbp-1DCh]
  int v93; // [rsp+D4h] [rbp-1D4h]
  __m128i *p_si128; // [rsp+D8h] [rbp-1D0h]
  const struct tagRECT *v95; // [rsp+E0h] [rbp-1C8h]
  __m128i si128; // [rsp+E8h] [rbp-1C0h] BYREF
  __int64 v97; // [rsp+F8h] [rbp-1B0h]
  __int64 v98; // [rsp+100h] [rbp-1A8h]
  _com_error *v99; // [rsp+108h] [rbp-1A0h] BYREF
  void **pExceptionObject; // [rsp+110h] [rbp-198h] BYREF
  int v101; // [rsp+118h] [rbp-190h]
  __int128 v102; // [rsp+120h] [rbp-188h]
  void **v103; // [rsp+130h] [rbp-178h] BYREF
  int v104; // [rsp+138h] [rbp-170h]
  __int128 v105; // [rsp+140h] [rbp-168h]
  __m128i v106; // [rsp+150h] [rbp-158h] BYREF
  __int32 v107; // [rsp+160h] [rbp-148h]
  int v108; // [rsp+164h] [rbp-144h]
  __int128 v109; // [rsp+168h] [rbp-140h] BYREF
  _OWORD v110[2]; // [rsp+178h] [rbp-130h] BYREF
  __int64 v111; // [rsp+1A0h] [rbp-108h] BYREF
  unsigned __int64 v112; // [rsp+1A8h] [rbp-100h]
  __int64 v113; // [rsp+1B0h] [rbp-F8h]
  __int64 v114; // [rsp+1B8h] [rbp-F0h]
  __int64 v115; // [rsp+1C0h] [rbp-E8h]
  unsigned __int64 v116; // [rsp+1C8h] [rbp-E0h]
  __int64 v117; // [rsp+1D0h] [rbp-D8h]
  unsigned int v118; // [rsp+1D8h] [rbp-D0h]
  int v119; // [rsp+1DCh] [rbp-CCh]
  _QWORD v120[2]; // [rsp+1E0h] [rbp-C8h] BYREF
  unsigned int v121; // [rsp+1F0h] [rbp-B8h]
  int v122; // [rsp+1F4h] [rbp-B4h]
  __int64 v123; // [rsp+1F8h] [rbp-B0h]
  int v124; // [rsp+200h] [rbp-A8h]
  int v125; // [rsp+204h] [rbp-A4h]
  unsigned __int64 v126; // [rsp+208h] [rbp-A0h]
  int v127; // [rsp+210h] [rbp-98h]
  __int32 v128; // [rsp+214h] [rbp-94h]
  __int32 v129; // [rsp+218h] [rbp-90h]
  __int32 v130; // [rsp+21Ch] [rbp-8Ch]
  __int32 v131; // [rsp+220h] [rbp-88h]
  int v132; // [rsp+224h] [rbp-84h]
  unsigned int v133; // [rsp+228h] [rbp-80h]
  int v134; // [rsp+22Ch] [rbp-7Ch]

  p_si128 = a4;
  v95 = a3;
  v85 = this;
  v80 = a5;
  v89 = a6;
  v81 = a8;
  v88 = 0;
  try
  {
    ((void (*)(void))a2->lpVtbl->QueryInterface)();
    v87 = 0;
    ((void (__fastcall *)(struct IDXGIResource *, GUID *, NDXGI::CResource **))a6->lpVtbl->QueryInterface)(
      a6,
      &GUID_00000040_1bbe_4d12_afbf_8fdf7e0a87c7,
      &v87);
    left = 0;
    top = 0;
    right = 1;
    bottom = 1;
    if ( *((_DWORD *)v87 + 28) == 2 )
    {
      v77 = 0;
      (**(void (__fastcall ***)(NDXGI::CResource *, GUID *, __int64 *))v87)(
        v87,
        &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c,
        &v77);
      v109 = 0;
      memset(v110, 0, 28);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v77 + 80LL))(v77, &v109);
      bottom = DWORD1(v109);
      right = v109;
      v67 = v110[0];
      if ( a7 )
      {
        left = a7->left;
        top = a7->top;
        right = a7->right;
        bottom = a7->bottom;
      }
      v73 = HIDWORD(v109) * DWORD2(v109);
      v12 = DWORD1(v110[0]);
      if ( v77 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    }
    else
    {
      v73 = 0;
      v67 = 0;
      v12 = 0;
      ThrowFailure(-2147467263);
    }
    v13 = 0;
    v90 = 0;
    v14 = 0;
    v91 = 0;
    v15 = 1;
    v92 = 0x100000001LL;
    v16 = 1;
    v93 = 1;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v64 = 0;
    v66 = 0;
    if ( *((_DWORD *)v88 + 28) == 2 )
    {
      v77 = 0;
      (**(void (__fastcall ***)(NDXGI::CResource *, GUID *, __int64 *))v88)(
        v88,
        &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c,
        &v77);
      v109 = 0;
      memset(v110, 0, 28);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v77 + 80LL))(v77, &v109);
      if ( HIDWORD(v110[0]) == 1 )
      {
        pExceptionObject = &_com_error::`vftable';
        v101 = -2147024809;
        v102 = 0;
        throw (_com_error *)&pExceptionObject;
      }
      if ( (v110[1] & 0x40) != 0 )
      {
        v103 = &_com_error::`vftable';
        v104 = -2147467263;
        v105 = 0;
        throw (_com_error *)&v103;
      }
      v83 = v109;
      v15 = v109;
      v82 = DWORD1(v109);
      v92 = v109;
      v16 = DWORD1(v109);
      v18 = v110[0];
      if ( v95 )
      {
        v13 = v95->left;
        LODWORD(v90) = v95->left;
        v14 = v95->top;
        HIDWORD(v90) = v14;
        v15 = v95->right;
        LODWORD(v92) = v15;
        v16 = v95->bottom;
        HIDWORD(v92) = v16;
      }
      if ( !a5 )
      {
        si128.m128i_i64[0] = __PAIR64__(v14, v13);
        si128.m128i_i64[1] = __PAIR64__(v16, v15);
        p_si128 = &si128;
        a5 = 1;
      }
      v19 = DWORD1(v110[0]);
      if ( DWORD1(v110[0]) > 1 && v12 == 1 )
      {
        v64 = 1;
      }
      else if ( DWORD1(v110[0]) != v12 )
      {
        ThrowFailure(-2005270527);
        v19 = DWORD1(v110[0]);
      }
      if ( v19 != 1 || v12 != 1 )
        v66 = 1;
      v17 = HIDWORD(v109) * DWORD2(v109);
      if ( v77 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    }
    else
    {
      v17 = 0;
      v83 = 0;
      v82 = 0;
      ThrowFailure(-2147467263);
      v18 = 0;
    }
    if ( v17 != v73 )
      ThrowFailure(-2005270527);
    v20 = *((_QWORD *)v85 + 7);
    v21 = *(unsigned int **)(v20 + 1080);
    ParentFormat = CD3D11FormatHelper::GetParentFormat(v67, v21[930], *(unsigned int *)(v20 + 1116));
    v70 = CD3D11FormatHelper::GetParentFormat(v18, v22, v23);
    CDevCtxInterface::CDevCtxInterface((CDevCtxInterface *)&v109, (struct CContext *)v21, 1, 0, 0);
    v84 = 0;
    v86 = 0;
    __SET_PAIR__(v25, v24, v110[0]);
    v26 = v110[0];
    v97 = v26 >> 64;
    v98 = v26;
    (*(void (__fastcall **)(_QWORD, _QWORD, unsigned int *))(*(_QWORD *)&v110[0] + 688LL))(
      *((_QWORD *)&v110[0] + 1),
      &v86,
      &v84);
    if ( v86 )
      (*(void (__fastcall **)(unsigned __int64, _QWORD, _QWORD))(v24 + 240))(v25, 0, v84);
    v111 = *((_QWORD *)v85 + 82);
    v112 = NDXGI::CResource::DDIHandle(v87);
    v27 = 0;
    v113 = 0;
    v114 = 0;
    v115 = 0;
    v116 = NDXGI::CResource::DDIHandle(v88);
    v117 = 0;
    v28 = a11;
    v118 = a11;
    v119 = 0;
    if ( v64 )
    {
      v27 = 1;
      HIDWORD(v117) = 1;
    }
    if ( ParentFormat != v70 )
    {
      v27 |= 2u;
      HIDWORD(v117) = v27;
    }
    v29 = v15 - v13;
    v30 = v16 - v14;
    if ( a11 == 2 || (v31 = v29, a11 == 4) )
    {
      v31 = v30;
      v30 = v29;
    }
    v32 = left;
    if ( right - left != v31 || (v33 = FLOAT_1_0, v34 = FLOAT_1_0, bottom - top != v30) )
    {
      v33 = (float)(int)(right - left) / (float)v31;
      v34 = (float)(int)(bottom - top) / (float)v30;
      v27 |= 4u;
      HIDWORD(v117) = v27;
    }
    NDXGI::RotateRect<D3D11_BOX>(&v90, v83, v82, a11);
    v36 = v27 || v66 || a11 != 1;
    v65 = v36;
    v37 = (GUID *)v80;
    if ( (a10 & 1) != 0 )
    {
      v76 = *(_DWORD *)v81 - 1;
      v69 = a5 - 1;
      v38 = v85;
      if ( (*((_BYTE *)v85 + 896) & 2) != 0 && v80 )
      {
        v65 = 1;
        v27 |= 0xC0000000;
        HIDWORD(v117) = v27;
LABEL_89:
        if ( (v95 || v80) && (*((_BYTE *)v38 + 896) & 4) == 0 )
        {
          v49 = -2147467263;
          goto LABEL_93;
        }
LABEL_39:
        LODWORD(v95) = NDXGI::CDevice::GetNonOpaquePlaneCount(v38, v89);
        NonOpaquePlaneCount = NDXGI::CDevice::GetNonOpaquePlaneCount(v39, a2);
        v37 = (GUID *)NonOpaquePlaneCount;
        LODWORD(v77) = NonOpaquePlaneCount;
        v43 = 0;
        while ( (unsigned int)v43 < *(_DWORD *)v42 )
        {
          v74 = *((_DWORD *)v42 + 2 * v43 + 2) * (_DWORD)v35;
          v71 = *((_DWORD *)v42 + 2 * v43 + 1) * (_DWORD)v37;
          v44 = 0;
          while ( v44 < v41 )
          {
            v106 = p_si128[v44];
            NDXGI::RotateRect<tagRECT>(&v106, v83, v82, v28);
            v45 = v32 + (int)(float)((float)((float)(v106.m128i_i32[0] - v90) * v33) + 0.5);
            v46 = top + (int)(float)((float)((float)(v106.m128i_i32[1] - HIDWORD(v90)) * v34) + 0.5);
            v47 = v32 + (int)(float)((float)((float)(v106.m128i_i32[2] - v90) * v33) + 0.5);
            v48 = top + (int)(float)((float)((float)(v106.m128i_i32[3] - HIDWORD(v90)) * v34) + 0.5);
            if ( right < v45 )
              v45 = right;
            if ( v45 < v32 )
              v45 = v32;
            HIDWORD(v113) = v45;
            if ( bottom < v46 )
              v46 = bottom;
            if ( v46 < top )
              v46 = top;
            LODWORD(v114) = v46;
            if ( right < v47 )
              v47 = right;
            if ( v47 < v32 )
              v47 = v32;
            HIDWORD(v114) = v47;
            if ( bottom < v48 )
              v48 = bottom;
            if ( v48 < top )
              v48 = top;
            LODWORD(v115) = v48;
            if ( v76 == (_DWORD)v43 && v69 == v44 )
            {
              v27 |= 8u;
              HIDWORD(v117) = v27;
            }
            if ( v65 || (v27 & 8) != 0 )
            {
              v52 = v85;
              NDXGI::CDevice::AcquireResource(v85, v89);
              if ( *((int *)v52 + 308) >= 0 )
              {
                LODWORD(v113) = v74;
                LODWORD(v117) = v71;
                if ( v80 )
                {
                  v120[0] = v111;
                  v120[1] = v112;
                  v121 = v74;
                  v122 = HIDWORD(v113);
                  v123 = v114;
                  v124 = v115;
                  v125 = 0;
                  v126 = v116;
                  v127 = v71;
                  v128 = p_si128[v44].m128i_i32[0];
                  v129 = p_si128[v44].m128i_i32[1];
                  v130 = p_si128[v44].m128i_i32[2];
                  v131 = p_si128[v44].m128i_i32[3];
                  v132 = HIDWORD(v117);
                  v133 = v118;
                  v134 = 0;
                  HIDWORD(v117) &= ~0x40000000u;
                  v53 = (*((__int64 (__fastcall **)(_QWORD *))v52 + 91))(v120);
                }
                else
                {
                  v53 = (*((__int64 (__fastcall **)(__int64 *))v52 + 89))(&v111);
                }
                if ( v53 == -2005530512 )
                {
                  (*(void (__fastcall **)(NDXGI::CDevice *, __int64))(*(_QWORD *)v52 + 264LL))(v52, 2289696773LL);
                }
                else if ( v53 )
                {
                  NDXGI::CDevice::DriverInternalError((NDXGI::CDevice *)((char *)v52 - 16), v53);
                }
              }
            }
            else
            {
              v106.m128i_i64[0] = p_si128[v44].m128i_i64[0];
              v106.m128i_i32[2] = 0;
              v106.m128i_i32[3] = p_si128[v44].m128i_i32[2];
              v107 = p_si128[v44].m128i_i32[3];
              v108 = 1;
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v98 + 368))(v97, *((_QWORD *)v87 + 4), v74);
            }
            ++v44;
            v28 = v118;
            v27 = HIDWORD(v117);
            v41 = a5;
          }
          v43 = (unsigned int)(v43 + 1);
          v35 = (const struct SUBRESOURCE_BLT_MAP **)(unsigned int)v95;
          v37 = (GUID *)(unsigned int)v77;
          v42 = v81;
        }
        if ( (a10 & 1) != 0 )
        {
          v89 = a9;
          v62 = v85;
          v63 = (RTL_SRWLOCK *)((char *)v85 + 1480);
          if ( *((_BYTE *)v85 + 882) )
          {
            v55 = 0;
            *((_QWORD *)v85 + 194) = &v89;
            v54 = (_QWORD *)((char *)v62 + 1488);
          }
          else
          {
            v81 = (NDXGI::CDevice *)((char *)v85 + 1480);
            AcquireSRWLockExclusive((PSRWLOCK)v85 + 185);
            v54 = (_QWORD *)((char *)v62 + 1488);
            v106.m128i_i32[0] = GetCurrentThreadId();
            v106.m128i_i64[1] = (__int64)&v89;
            std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SRenderCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SRenderCBThreadLocalData *>>,0>>::emplace<std::pair<unsigned long,NDXGI::CDevice::SRenderCBThreadLocalData *>>(
              (char *)v62 + 1488,
              &si128,
              &v106);
            v55 = (_QWORD *)si128.m128i_i64[0];
            if ( v63 )
              ReleaseSRWLockExclusive(v63);
          }
          NDXGI::CDevice::Flush(v62, 1u);
          if ( *((_BYTE *)v62 + 882) )
          {
            *((_QWORD *)v62 + 194) = 0;
          }
          else
          {
            AcquireSRWLockExclusive(v63);
            v56 = std::_Conditionally_enabled_hash<unsigned long,1>::operator()(v55 + 2);
            v57 = 2 * (v56 & v54[6]);
            v58 = v54[3];
            v59 = *(_QWORD **)(v58 + 16 * (v56 & v54[6]));
            if ( *(_QWORD **)(v58 + 8 * v57 + 8) == v55 )
            {
              if ( v59 == v55 )
              {
                v60 = v54[1];
                *(_QWORD *)(v58 + 8 * v57) = v60;
              }
              else
              {
                v60 = v55[1];
              }
              *(_QWORD *)(v58 + 8 * v57 + 8) = v60;
            }
            else if ( v59 == v55 )
            {
              *(_QWORD *)(v58 + 8 * v57) = *v55;
            }
            v61 = *v55;
            --v54[2];
            *(_QWORD *)v55[1] = v61;
            *(_QWORD *)(v61 + 8) = v55[1];
            std::_Deallocate<16>(v55, 32);
            if ( v63 )
              ReleaseSRWLockExclusive(v63);
          }
        }
        v49 = 0;
        v50 = v86;
        if ( !v86 )
          goto LABEL_67;
        v81 = 0;
        (**v86)(v86, &GUID_ffffffff_1bbe_4d12_afbf_8fdf7e0a87c7, &v81);
        (*(void (__fastcall **)(__int64, const struct SUBRESOURCE_BLT_MAP *, _QWORD))(v98 + 240))(v97, v81, v84);
        if ( v81 )
          (*(void (__fastcall **)(const struct SUBRESOURCE_BLT_MAP *))(*(_QWORD *)v81 + 16LL))(v81);
LABEL_93:
        v50 = v86;
LABEL_67:
        if ( v50 )
          (*v50)[2](v50, v37, v35);
        CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)&v109);
        if ( v87 )
          (*(void (__fastcall **)(NDXGI::CResource *))(*(_QWORD *)v87 + 16LL))(v87);
        if ( v88 )
          (*(void (__fastcall **)(NDXGI::CResource *))(*(_QWORD *)v88 + 16LL))(v88);
        return v49;
      }
    }
    else
    {
      v76 = -1;
      v69 = -1;
      v38 = v85;
    }
    if ( !v36 && (a10 & 1) == 0 )
      goto LABEL_39;
    goto LABEL_89;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( _com_error *v99 )
  {
    return *((unsigned int *)v99 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x18001ec00  mov     rax, rsp
0x18001ec03  push    rbx
0x18001ec04  push    rsi
0x18001ec05  push    rdi
0x18001ec06  push    r12
0x18001ec08  push    r13
0x18001ec0a  push    r14
0x18001ec0c  push    r15
0x18001ec0e  sub     rsp, 270h
0x18001ec15  movaps  xmmword ptr [rax-48h], xmm6
0x18001ec19  movaps  xmmword ptr [rax-58h], xmm7
0x18001ec1d  movaps  xmmword ptr [rax-68h], xmm8
0x18001ec22  mov     rax, cs:__security_cookie
0x18001ec29  xor     rax, rsp
0x18001ec2c  mov     [rsp+2A8h+var_78], rax
0x18001ec34  mov     [rsp+2A8h+var_1D0], r9
0x18001ec3c  mov     [rsp+2A8h+var_1C8], r8
0x18001ec44  mov     r13, rdx
0x18001ec47  mov     [rsp+2A8h+var_210], rcx
0x18001ec4f  mov     eax, [rsp+2A8h+arg_20]
0x18001ec56  mov     [rsp+2A8h+var_230], eax
0x18001ec5a  mov     rdi, [rsp+2A8h+arg_28]
0x18001ec62  mov     [rsp+2A8h+var_1F0], rdi
0x18001ec6a  mov     rbx, [rsp+2A8h+arg_30]
0x18001ec72  mov     rax, [rsp+2A8h+arg_38]
0x18001ec7a  mov     [rsp+2A8h+var_228], rax
0x18001ec82  xor     esi, esi
0x18001ec84  mov     [rsp+2A8h+var_1F8], rsi
0x18001ec8c  mov     rax, [rdx]
0x18001ec8f  lea     r8, [rsp+2A8h+var_1F8]
0x18001ec97  lea     rdx, _GUID_00000040_1bbe_4d12_afbf_8fdf7e0a87c7
0x18001ec9e  mov     rcx, r13
0x18001eca1  mov     rax, [rax]
0x18001eca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eca9  mov     [rsp+2A8h+var_200], rsi
0x18001ecb1  mov     rax, [rdi]
0x18001ecb4  lea     r8, [rsp+2A8h+var_200]
0x18001ecbc  lea     rdx, _GUID_00000040_1bbe_4d12_afbf_8fdf7e0a87c7
0x18001ecc3  mov     rcx, rdi
0x18001ecc6  mov     rax, [rax]
0x18001ecc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecce  mov     [rsp+2A8h+var_244], esi
0x18001ecd2  mov     [rsp+2A8h+var_238], esi
0x18001ecd6  mov     [rsp+2A8h+var_234], 1
0x18001ecde  mov     [rsp+2A8h+var_24C], 1
0x18001ece6  mov     rcx, [rsp+2A8h+var_200]
0x18001ecee  mov     edx, [rcx+70h]
0x18001ecf1  cmp     edx, 2
0x18001ecf4  jz      loc_18001F4A7
0x18001ecfa  mov     [rsp+2A8h+var_248], esi
0x18001ecfe  mov     [rsp+2A8h+var_254], esi
0x18001ed02  mov     ebx, esi
0x18001ed04  mov     edi, 80004001h
0x18001ed09  mov     ecx, edi; int
0x18001ed0b  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18001ed10  mov     r15d, esi
0x18001ed13  mov     [rsp+2A8h+var_1E8], rsi
0x18001ed1b  mov     r12d, esi
0x18001ed1e  mov     [rsp+2A8h+var_1E0], esi
0x18001ed25  mov     esi, 1
0x18001ed2a  mov     [rsp+2A8h+var_1DC], esi
0x18001ed31  mov     r14d, esi
0x18001ed34  mov     [rsp+2A8h+var_1D8], esi
0x18001ed3b  mov     [rsp+2A8h+var_1D4], esi
0x18001ed42  movdqa  xmm0, cs:__xmm@00000001000000010000000000000000
0x18001ed4a  movdqu  [rsp+2A8h+var_1C0], xmm0
0x18001ed53  mov     [rsp+2A8h+var_258], r12b
0x18001ed58  mov     [rsp+2A8h+var_257], r12b
0x18001ed5d  mov     rcx, [rsp+2A8h+var_1F8]
0x18001ed65  mov     edx, [rcx+70h]
0x18001ed68  cmp     edx, 2
0x18001ed6b  jnz     loc_18001EE09
0x18001ed71  mov     [rsp+2A8h+var_240], r12
0x18001ed76  mov     rax, [rcx]
0x18001ed79  lea     r8, [rsp+2A8h+var_240]
0x18001ed7e  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x18001ed85  mov     rax, [rax]
0x18001ed88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed8d  xorps   xmm0, xmm0
0x18001ed90  movups  [rsp+2A8h+var_140], xmm0
0x18001ed98  movups  [rsp+2A8h+var_130], xmm0
0x18001eda0  movups  [rsp+2A8h+var_130+0Ch], xmm0
0x18001eda8  mov     rcx, [rsp+2A8h+var_240]
0x18001edad  mov     rax, [rcx]
0x18001edb0  lea     rdx, [rsp+2A8h+var_140]
0x18001edb8  mov     rax, [rax+50h]
0x18001edbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edc1  cmp     dword ptr [rsp+2A8h+var_130+0Ch], esi
0x18001edc8  jnz     loc_18001F58D
0x18001edce  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001edd5  mov     [rsp+2A8h+pExceptionObject], rax
0x18001eddd  mov     [rsp+2A8h+var_190], 80070057h
0x18001ede8  xorps   xmm0, xmm0
0x18001edeb  movdqu  [rsp+2A8h+var_188], xmm0
0x18001edf4  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18001edfb  lea     rcx, [rsp+2A8h+pExceptionObject]; pExceptionObject
0x18001ee03  call    _CxxThrowException_0
0x18001ee09  xor     ebx, ebx
0x18001ee0b  mov     [rsp+2A8h+var_21C], ebx
0x18001ee12  mov     [rsp+2A8h+var_220], ebx
0x18001ee19  mov     ecx, edi; int
0x18001ee1b  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18001ee20  mov     edi, ebx
0x18001ee22  jmp     loc_18001EF2A
0x18001ee27  mov     eax, dword ptr [rsp+2A8h+var_140]
0x18001ee2e  mov     [rsp+2A8h+var_21C], eax
0x18001ee35  mov     esi, eax
0x18001ee37  mov     [rsp+2A8h+var_1DC], eax
0x18001ee3e  mov     eax, dword ptr [rsp+2A8h+var_140+4]
0x18001ee45  mov     [rsp+2A8h+var_220], eax
0x18001ee4c  mov     r14d, eax
0x18001ee4f  mov     [rsp+2A8h+var_1D8], eax
0x18001ee56  mov     edi, dword ptr [rsp+2A8h+var_130]
0x18001ee5d  mov     rax, [rsp+2A8h+var_1C8]
0x18001ee65  test    rax, rax
0x18001ee68  jz      short loc_18001EE97
0x18001ee6a  mov     r15d, [rax]
0x18001ee6d  mov     dword ptr [rsp+2A8h+var_1E8], r15d
0x18001ee75  mov     r12d, [rax+4]
0x18001ee79  mov     dword ptr [rsp+2A8h+var_1E8+4], r12d
0x18001ee81  mov     esi, [rax+8]
0x18001ee84  mov     [rsp+2A8h+var_1DC], esi
0x18001ee8b  mov     r14d, [rax+0Ch]
0x18001ee8f  mov     [rsp+2A8h+var_1D8], r14d
0x18001ee97  cmp     [rsp+2A8h+arg_20], 0
0x18001ee9f  jnz     short loc_18001EEDB
0x18001eea1  mov     dword ptr [rsp+2A8h+var_1C0], r15d
0x18001eea9  mov     dword ptr [rsp+2A8h+var_1C0+4], r12d
0x18001eeb1  mov     dword ptr [rsp+2A8h+var_1C0+8], esi
0x18001eeb8  mov     dword ptr [rsp+2A8h+var_1C0+0Ch], r14d
0x18001eec0  lea     rax, [rsp+2A8h+var_1C0]
0x18001eec8  mov     [rsp+2A8h+var_1D0], rax
0x18001eed0  mov     [rsp+2A8h+arg_20], 1
0x18001eedb  mov     eax, dword ptr [rsp+2A8h+var_130+4]
0x18001eee2  cmp     eax, 1
0x18001eee5  ja      loc_18001F57B
0x18001eeeb  cmp     eax, ebx
0x18001eeed  jnz     loc_18001F8F7
0x18001eef3  cmp     eax, 1
0x18001eef6  jnz     loc_18001F784
0x18001eefc  cmp     ebx, eax
0x18001eefe  jnz     loc_18001F784
0x18001ef04  mov     ebx, dword ptr [rsp+2A8h+var_140+8]
0x18001ef0b  imul    ebx, dword ptr [rsp+2A8h+var_140+0Ch]
0x18001ef13  mov     rcx, [rsp+2A8h+var_240]
0x18001ef18  test    rcx, rcx
0x18001ef1b  jz      short loc_18001EF2A
0x18001ef1d  mov     rax, [rcx]
0x18001ef20  mov     rax, [rax+10h]
0x18001ef24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef29  nop
0x18001ef2a  cmp     ebx, [rsp+2A8h+var_248]
0x18001ef2e  jnz     loc_18001F90D
0x18001ef34  mov     rax, [rsp+2A8h+var_210]
0x18001ef3c  mov     rax, [rax+38h]
0x18001ef40  mov     r8d, [rax+45Ch]
0x18001ef47  mov     rbx, [rax+438h]
0x18001ef4e  mov     r11d, [rbx+0E88h]
0x18001ef55  mov     edx, r11d
0x18001ef58  mov     ecx, [rsp+2A8h+var_254]
0x18001ef5c  call    ?GetParentFormat@CD3D11FormatHelper@@SA?AW4DXGI_FORMAT@@W42@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@1@@Z; CD3D11FormatHelper::GetParentFormat(DXGI_FORMAT,D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures)
0x18001ef61  mov     [rsp+2A8h+var_254], eax
0x18001ef65  mov     edx, r11d
0x18001ef68  mov     ecx, edi
0x18001ef6a  call    ?GetParentFormat@CD3D11FormatHelper@@SA?AW4DXGI_FORMAT@@W42@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@1@@Z; CD3D11FormatHelper::GetParentFormat(DXGI_FORMAT,D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures)
0x18001ef6f  mov     [rsp+2A8h+var_250], eax
0x18001ef73  mov     [rsp+2A8h+var_288], 0; bool
0x18001ef78  xor     r9d, r9d; bool
0x18001ef7b  mov     r8b, 1; bool
0x18001ef7e  mov     rdx, rbx; struct CContext *
0x18001ef81  lea     rcx, [rsp+2A8h+var_140]; this
0x18001ef89  call    ??$?0VCContext@@@CDevCtxInterface@@QEAA@PEAVCContext@@_N11@Z; CDevCtxInterface::CDevCtxInterface(CContext *,bool,bool,bool)
0x18001ef8e  nop
0x18001ef8f  xor     eax, eax
0x18001ef91  mov     [rsp+2A8h+var_218], eax
0x18001ef98  mov     [rsp+2A8h+var_208], rax
0x18001efa0  mov     rbx, qword ptr [rsp+2A8h+var_130]
0x18001efa8  mov     [rsp+2A8h+var_1A8], rbx
0x18001efb0  lea     r8, [rsp+2A8h+var_218]
0x18001efb8  lea     rdx, [rsp+2A8h+var_208]
0x18001efc0  mov     rdi, qword ptr [rsp+2A8h+var_130+8]
0x18001efc8  mov     [rsp+2A8h+var_1B0], rdi
0x18001efd0  mov     rcx, rdi
0x18001efd3  mov     rax, [rbx+2B0h]
0x18001efda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efdf  cmp     [rsp+2A8h+var_208], 0
0x18001efe8  jnz     loc_18001F91C
0x18001efee  mov     rax, [rsp+2A8h+var_210]
0x18001eff6  mov     rax, [rax+290h]
0x18001effd  mov     [rsp+2A8h+var_108], rax
0x18001f005  mov     rcx, [rsp+2A8h+var_200]; this
0x18001f00d  call    ?DDIHandle@CResource@NDXGI@@QEBA_KXZ; NDXGI::CResource::DDIHandle(void)
0x18001f012  mov     [rsp+2A8h+var_100], rax
0x18001f01a  xor     ebx, ebx
0x18001f01c  mov     [rsp+2A8h+var_F8], rbx
0x18001f024  mov     [rsp+2A8h+var_F0], rbx
0x18001f02c  mov     [rsp+2A8h+var_E8], rbx
0x18001f034  mov     rcx, [rsp+2A8h+var_1F8]; this
0x18001f03c  call    ?DDIHandle@CResource@NDXGI@@QEBA_KXZ; NDXGI::CResource::DDIHandle(void)
0x18001f041  mov     [rsp+2A8h+var_E0], rax
0x18001f049  mov     [rsp+2A8h+var_D8], rbx
0x18001f051  mov     edi, [rsp+2A8h+arg_50]
0x18001f058  mov     [rsp+2A8h+var_D0], edi
0x18001f05f  xor     eax, eax
0x18001f061  mov     [rsp+2A8h+var_CC], eax
0x18001f068  cmp     [rsp+2A8h+var_258], al
0x18001f06c  jz      short loc_18001F078
0x18001f06e  or      ebx, 1
0x18001f071  mov     dword ptr [rsp+2A8h+var_D8+4], ebx
0x18001f078  mov     eax, [rsp+2A8h+var_250]
0x18001f07c  cmp     [rsp+2A8h+var_254], eax
0x18001f080  jz      short loc_18001F08C
0x18001f082  or      ebx, 2
0x18001f085  mov     dword ptr [rsp+2A8h+var_D8+4], ebx
0x18001f08c  sub     esi, r15d
0x18001f08f  sub     r14d, r12d
0x18001f092  cmp     edi, 2
0x18001f095  jz      loc_18001F93A
0x18001f09b  mov     edx, esi
0x18001f09d  cmp     edi, 4
0x18001f0a0  jz      loc_18001F93A
0x18001f0a6  mov     ecx, [rsp+2A8h+var_234]
0x18001f0aa  mov     r12d, [rsp+2A8h+var_244]
0x18001f0af  sub     ecx, r12d
0x18001f0b2  mov     r9d, [rsp+2A8h+var_24C]
0x18001f0b7  mov     r8d, [rsp+2A8h+var_238]
0x18001f0bc  cmp     ecx, edx
0x18001f0be  jnz     loc_18001F945
0x18001f0c4  movss   xmm6, cs:__real@3f800000
0x18001f0cc  movaps  xmm8, xmm6
0x18001f0d0  mov     eax, r9d
0x18001f0d3  sub     eax, r8d
0x18001f0d6  cmp     eax, r14d
0x18001f0d9  jnz     loc_18001F945
0x18001f0df  mov     r9d, edi
0x18001f0e2  mov     r8d, [rsp+2A8h+var_220]
0x18001f0ea  mov     edx, [rsp+2A8h+var_21C]
0x18001f0f1  lea     rcx, [rsp+2A8h+var_1E8]
0x18001f0f9  call    ??$RotateRect@UD3D11_BOX@@@NDXGI@@YAXAEAUD3D11_BOX@@IIW4DXGI_DDI_MODE_ROTATION@@@Z; NDXGI::RotateRect<D3D11_BOX>(D3D11_BOX &,uint,uint,DXGI_DDI_MODE_ROTATION)
0x18001f0fe  test    ebx, ebx
0x18001f100  jnz     loc_18001F64C
0x18001f106  cmp     [rsp+2A8h+var_257], bl
0x18001f10a  jnz     loc_18001F64C
0x18001f110  cmp     edi, 1
0x18001f113  jnz     loc_18001F64C
0x18001f119  xor     al, al
0x18001f11b  mov     [rsp+2A8h+var_258], al
0x18001f11f  mov     esi, dword ptr [rsp+2A8h+arg_48]
0x18001f126  and     esi, 1
0x18001f129  mov     r10, [rsp+2A8h+var_228]
0x18001f131  mov     r9d, [rsp+2A8h+arg_20]
0x18001f139  mov     edx, [rsp+2A8h+var_230]
0x18001f13d  jnz     loc_18001F98B
0x18001f143  mov     ecx, 0FFFFFFFFh
0x18001f148  mov     [rsp+2A8h+var_244], ecx
0x18001f14c  mov     [rsp+2A8h+var_254], ecx
0x18001f150  mov     rcx, [rsp+2A8h+var_210]; this
0x18001f158  test    al, al
0x18001f15a  jnz     loc_18001F653
0x18001f160  test    esi, esi
0x18001f162  jnz     loc_18001F653
0x18001f168  mov     rdx, [rsp+2A8h+var_1F0]; struct IDXGIResource *
0x18001f170  call    ?GetNonOpaquePlaneCount@CDevice@NDXGI@@IEBAIPEAUIDXGIResource@@@Z; NDXGI::CDevice::GetNonOpaquePlaneCount(IDXGIResource *)
0x18001f175  mov     r8d, eax
0x18001f178  mov     dword ptr [rsp+2A8h+var_1C8], eax
0x18001f17f  mov     rdx, r13; struct IDXGIResource *
0x18001f182  call    ?GetNonOpaquePlaneCount@CDevice@NDXGI@@IEBAIPEAUIDXGIResource@@@Z; NDXGI::CDevice::GetNonOpaquePlaneCount(IDXGIResource *)
0x18001f187  mov     edx, eax
0x18001f189  mov     dword ptr [rsp+2A8h+var_240], eax
0x18001f18d  xor     r14d, r14d
0x18001f190  movss   xmm7, cs:__real@3f000000
0x18001f198  cmp     r14d, [r10]
0x18001f19b  jnb     loc_18001F401
0x18001f1a1  mov     eax, r8d
0x18001f1a4  imul    eax, [r10+r14*8+8]
0x18001f1aa  mov     [rsp+2A8h+var_248], eax
0x18001f1ae  mov     eax, edx
0x18001f1b0  imul    eax, [r10+r14*8+4]
0x18001f1b6  mov     [rsp+2A8h+var_250], eax
0x18001f1ba  xor     r15d, r15d
0x18001f1bd  cmp     r15d, r9d
0x18001f1c0  jnb     loc_18001F3E5
0x18001f1c6  mov     r13d, r15d
0x18001f1c9  add     r13, r13
0x18001f1cc  mov     rax, [rsp+2A8h+var_1D0]
0x18001f1d4  movups  xmm0, xmmword ptr [rax+r13*8]
0x18001f1d9  movups  [rsp+2A8h+var_158], xmm0
0x18001f1e1  mov     r9d, edi
0x18001f1e4  mov     r8d, [rsp+2A8h+var_220]
0x18001f1ec  mov     edx, [rsp+2A8h+var_21C]
0x18001f1f3  lea     rcx, [rsp+2A8h+var_158]
0x18001f1fb  call    ??$RotateRect@UtagRECT@@@NDXGI@@YAXAEAUtagRECT@@IIW4DXGI_DDI_MODE_ROTATION@@@Z; NDXGI::RotateRect<tagRECT>(tagRECT &,uint,uint,DXGI_DDI_MODE_ROTATION)
0x18001f200  mov     eax, dword ptr [rsp+2A8h+var_158]
0x18001f207  sub     eax, dword ptr [rsp+2A8h+var_1E8]
0x18001f20e  xorps   xmm0, xmm0
0x18001f211  cvtsi2ss xmm0, rax
0x18001f216  mulss   xmm0, xmm6
0x18001f21a  addss   xmm0, xmm7
0x18001f21e  cvttss2si r9d, xmm0
0x18001f223  add     r9d, r12d
  ... truncated ...
```

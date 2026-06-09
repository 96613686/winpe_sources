# XPerfAddIn::CDMABufferInfoSource::RealOnEvent<ulong>(XPerfCore::ICursor const *,_GUID const *,_EVENT_RECORD const *)

- ea: `0x18005080c`
- end: `0x18005264b`
- name: `??$RealOnEvent@K@CDMABufferInfoSource@XPerfAddIn@@QEAAJPEBUICursor@XPerfCore@@PEBU_GUID@@PEBU_EVENT_RECORD@@@Z`
- size: `7743`
- prototype: ``
- caller_count: `2`
- callee_count: `40`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180098810`
- `0x180098a70`

## callees

- `0x180007fe4`
- `0x180011e00`
- `0x180039528`
- `0x18004ad28`
- `0x1800504c4`
- `0x180050544`
- `0x180050610`
- `0x180050638`
- `0x1800506e0`
- `0x1800507bc`
- `0x18005080c`
- `0x180052654`
- `0x180070af8`
- `0x180079458`
- `0x180079614`
- `0x1800874bc`
- `0x180090990`
- `0x180091bec`
- `0x180094d4c`
- `0x1800974b8`
- `0x1800974e8`
- `0x18009766c`
- `0x180097e44`
- `0x180097ee4`
- `0x180097fa8`
- `0x18009803c`
- `0x180098148`
- `0x180098228`
- `0x18009995c`
- `0x180099b4c`
- `0x180099b98`
- `0x180099ffc`
- `0x18009a5a8`
- `0x18009a670`
- `0x18009a708`
- `0x18009a864`
- `0x18009a9b0`
- `0x1800cf032`
- `0x1800cf080`
- `0x1800d6010`

## string_xrefs

- `0x1800513ca`: `allocation reference listing for never-created dma buffer %lld`
- `0x180051594`: `unrecognized context %lld during submition`
- `0x180051536`: `submission of non-created dma buffer %lld`
- `0x180051a51`: `Completion of never-submitted fenceID %lld`
- `0x1800516c1`: `unrecognized context %lld during completion`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall XPerfAddIn::CDMABufferInfoSource::RealOnEvent<unsigned long>(
        TimeStamp a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  TimeStamp v7; // rsi
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  __int64 result; // rax
  __m128i v16; // xmm1
  __int64 v17; // rcx
  unsigned int *v18; // rcx
  const __m128i *v19; // roff
  unsigned int *v20; // rcx
  const __m128i *v21; // rdi
  __int32 v22; // r13d
  int v23; // eax
  __int64 v24; // rcx
  unsigned __int16 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rax
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int *v34; // rcx
  unsigned int *v35; // rcx
  BOOL v36; // eax
  unsigned int *v37; // rcx
  unsigned int v38; // eax
  unsigned int *v39; // rcx
  unsigned int *v40; // rcx
  char v41; // r13
  _BYTE *v42; // rax
  _BYTE *v43; // r11
  _BYTE *v44; // rax
  unsigned __int8 *QuadPart; // rcx
  _BYTE *v46; // rax
  _BYTE *v47; // rax
  _BYTE *v48; // rdi
  __int64 v49; // r14
  __int64 (__fastcall *v50)(__int64, TimeStamp *, _QWORD, _QWORD); // r13
  unsigned int v51; // ebx
  __int64 v52; // r14
  __int64 v53; // rbx
  _QWORD *v54; // rax
  TimeStamp *v55; // rbx
  _QWORD *v56; // rax
  __int64 v57; // rdi
  XPerfAddIn::CDMABufferInfoSource *v58; // rcx
  __int64 v59; // rbx
  __int64 v60; // rax
  _BYTE *v61; // rdi
  __int64 v62; // r12
  unsigned int v63; // r13d
  __int64 v64; // r12
  __int64 v65; // rdi
  _QWORD *v66; // rax
  _QWORD *v67; // rax
  _QWORD *v68; // rax
  _BYTE *v69; // rbx
  _QWORD *v70; // r12
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // rdi
  _QWORD *v74; // rax
  __int64 v75; // r14
  __int64 v76; // rdi
  int v77; // eax
  _QWORD *v78; // rbx
  __int64 v79; // rax
  __int64 v80; // r13
  __int64 v81; // r8
  __int64 v82; // r9
  __int64 v83; // r13
  _QWORD *v84; // rdi
  TimeStamp v85; // rdx
  __int64 v86; // r8
  __int64 v87; // rcx
  int v88; // ebx
  __int64 v89; // rax
  TimeStamp v90; // rcx
  __int64 i; // rbx
  _QWORD *v92; // r12
  _QWORD *j; // rbx
  int v94; // r12d
  __int64 v95; // rdi
  __int64 v96; // rbx
  __int64 v97; // r8
  __int64 v98; // r9
  __int64 v99; // rcx
  __int64 k; // rax
  _BYTE *v101; // rdi
  TimeStamp v102; // r12
  XPerfAddIn::CDMABufferInfoSource *v103; // rcx
  __int64 v104; // rdi
  __int64 (__fastcall *v105)(__int64, _QWORD *, _QWORD, _QWORD); // r14
  unsigned int v106; // ebx
  __int64 v107; // rbx
  __int64 *v108; // rax
  TimeStamp v109; // rbx
  __int64 v110; // r8
  __int64 v111; // r9
  _QWORD *v112; // rbx
  __int64 v113; // rdx
  __int64 v114; // rdx
  _BYTE *v115; // rdi
  TimeStamp **v116; // r13
  __int64 v117; // r13
  _QWORD *v118; // rax
  __int64 v119; // r13
  XPerfAddIn::CDMABufferInfoSource *v120; // rcx
  _QWORD *v121; // rax
  __int64 v122; // rax
  char v123; // al
  __int64 v124; // r12
  __int64 (__fastcall *v125)(__int64, _QWORD *, _QWORD, _QWORD); // r13
  unsigned int v126; // ebx
  __int64 v127; // r9
  _QWORD *v128; // rbx
  _QWORD *v129; // rcx
  unsigned __int64 v130; // r8
  int v131; // ecx
  __int64 v132; // rax
  __int64 v133; // rax
  _QWORD *v134; // rdi
  unsigned __int8 v135; // al
  int v136; // r14d
  _BYTE *v137; // r13
  unsigned __int8 v138; // al
  __int64 v139; // r9
  __int64 v140; // rdi
  __int64 *v141; // rax
  __int64 v142; // rbx
  __int64 v143; // rax
  unsigned __int64 v144; // r8
  __int64 v145; // r15
  __int64 v146; // r8
  __int64 v147; // r8
  __int64 v148; // r9
  __int64 v149; // r8
  __int64 v150; // r8
  __int64 v151; // rcx
  _QWORD *m; // rax
  __int64 *v153; // r14
  __int64 v154; // r12
  __int64 (__fastcall *v155)(__int64, _QWORD *, _QWORD, _QWORD); // r13
  unsigned int v156; // ebx
  __int64 v157; // r12
  __int64 v158; // rbx
  _QWORD *v159; // rax
  TimeStamp v160; // [rsp+30h] [rbp-CD8h] BYREF
  unsigned __int8 v161; // [rsp+38h] [rbp-CD0h]
  _QWORD *v162; // [rsp+40h] [rbp-CC8h] BYREF
  _BYTE *v163; // [rsp+48h] [rbp-CC0h] BYREF
  _QWORD v164[2]; // [rsp+50h] [rbp-CB8h] BYREF
  unsigned __int64 v165; // [rsp+60h] [rbp-CA8h]
  __int128 v166; // [rsp+68h] [rbp-CA0h] BYREF
  __int128 v167; // [rsp+78h] [rbp-C90h]
  __int128 v168; // [rsp+88h] [rbp-C80h]
  __int64 v169; // [rsp+98h] [rbp-C70h]
  _BYTE v170[3072]; // [rsp+A0h] [rbp-C68h] BYREF

  v7 = a1;
  v160 = a1;
  memset_0(v170, 0, 0xC18u);
  if ( a3 == (__int64 *)&DxgkControlGuid )
  {
    v8 = *(unsigned __int16 *)(a4 + 40);
    if ( v8 > 0x2B )
    {
      v28 = v8 - 50;
      if ( v28 )
      {
        v29 = v28 - 116;
        if ( !v29 )
        {
          if ( *(_WORD *)(a4 + 86) < 0x48u )
            return 262403;
          *(_QWORD *)&v170[8] = *(unsigned int *)(*(_QWORD *)(a4 + 96) + 4LL);
          a3 = ETWGUID_DXGKBLT;
          goto LABEL_78;
        }
        v30 = v29 - 2;
        if ( !v30 )
        {
          if ( *(_WORD *)(a4 + 86) < 0x18u )
            return 262403;
          v40 = *(unsigned int **)(a4 + 96);
          *(_QWORD *)v170 = *v40;
          *(_DWORD *)&v170[8] = v40[1];
          *(_QWORD *)&v170[12] = v40[2];
          *(_DWORD *)&v170[20] = v40[3];
          v170[24] = v40[4] != 0;
          v170[25] = v40[5] != 0;
          a3 = (__int64 *)&ETWGUID_DXGKFLIP;
          goto LABEL_78;
        }
        v31 = v30 - 1;
        if ( !v31 )
        {
          if ( *(_WORD *)(a4 + 86) < 4u )
            return 262403;
          *(_QWORD *)v170 = **(unsigned int **)(a4 + 96);
          a3 = ETWGUID_DXGKRENDER;
          goto LABEL_78;
        }
        v32 = v31 - 6;
        if ( v32 )
        {
          v33 = v32 - 2;
          if ( v33 )
          {
            if ( v33 == 4 )
            {
              if ( *(_WORD *)(a4 + 86) < 0x10u )
                return 262403;
              v34 = *(unsigned int **)(a4 + 96);
              *(_QWORD *)v170 = *v34;
              *(_DWORD *)&v170[8] = v34[1];
              *(_QWORD *)&v170[12] = *((_QWORD *)v34 + 1);
              a3 = ETWGUID_DXGKSCHEDULER_VSYNC_INTERRUPT;
            }
            goto LABEL_78;
          }
          if ( *(_BYTE *)(a4 + 42) )
          {
            if ( *(_WORD *)(a4 + 86) < 0x2Cu )
              return 262403;
            v35 = *(unsigned int **)(a4 + 96);
            *(_QWORD *)v170 = *v35;
            *(_DWORD *)&v170[8] = v35[1];
            *(_QWORD *)&v170[12] = *((_QWORD *)v35 + 1);
            *(_DWORD *)&v170[20] = v35[4];
            v36 = v35[5] == 2;
          }
          else
          {
            if ( *(_WORD *)(a4 + 86) < 0x1Cu )
              return 262403;
            v35 = *(unsigned int **)(a4 + 96);
            *(_QWORD *)v170 = *v35;
            *(_DWORD *)&v170[8] = v35[1];
            *(_QWORD *)&v170[12] = *((_QWORD *)v35 + 1);
            *(_DWORD *)&v170[20] = v35[4];
            v36 = v35[5] != 0;
          }
          *(_DWORD *)&v170[24] = v36;
          *(_DWORD *)&v170[28] = v35[6];
        }
        else
        {
          if ( *(_BYTE *)(a4 + 42) )
          {
            if ( *(_WORD *)(a4 + 86) < 0x20u )
              return 262403;
            v39 = *(unsigned int **)(a4 + 96);
            *(_QWORD *)v170 = *v39;
            *(_DWORD *)&v170[8] = v39[2];
            *(_QWORD *)&v170[12] = *(_QWORD *)(v39 + 3);
            *(_DWORD *)&v170[20] = v39[5];
            *(_QWORD *)&v170[24] = v39[6];
            v38 = v39[7];
          }
          else
          {
            if ( *(_WORD *)(a4 + 86) < 0x1Cu )
              return 262403;
            v37 = *(unsigned int **)(a4 + 96);
            *(_QWORD *)v170 = *v37;
            *(_DWORD *)&v170[8] = v37[1];
            *(_QWORD *)&v170[12] = *((_QWORD *)v37 + 1);
            *(_DWORD *)&v170[20] = v37[4];
            *(_QWORD *)&v170[24] = v37[5];
            v38 = v37[6];
          }
          *(_DWORD *)&v170[32] = v38;
        }
        a3 = (__int64 *)&ETWGUID_DXGKSCHEDULER_DMAPACKET;
        goto LABEL_78;
      }
      if ( *(_WORD *)(a4 + 86) < 0x20u )
        return 262403;
      v17 = *(_QWORD *)(a4 + 96);
      *(_QWORD *)&v170[16] = *(unsigned int *)(v17 + 8);
      *(_OWORD *)&v170[24] = *(_OWORD *)(v17 + 12);
      *(_DWORD *)&v170[40] = *(_DWORD *)(v17 + 28);
      a3 = ETWGUID_DXGKMEMORYTRANSFER;
    }
    else
    {
      if ( v8 == 43 )
      {
        if ( *(_WORD *)(a4 + 86) < 0xCu )
          return 262403;
        v21 = *(const __m128i **)(a4 + 96);
        *(__m128i *)v170 = _mm_unpacklo_epi32(_mm_loadl_epi64(v21), (__m128i)0LL);
        v22 = v21->m128i_i32[2];
        *(_DWORD *)&v170[16] = v22;
        if ( !a2 )
          return 262400;
        v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 80LL))(a2);
        v24 = v21->m128i_u32[2];
        v25 = 0;
        if ( v23 == 4 )
        {
          *(_DWORD *)&v170[20] = 4;
          if ( v22 )
          {
            do
            {
              *(_DWORD *)&v170[4 * v25 + 24] = v21->m128i_i32[v25 + 3]
                                             ^ (v21->m128i_i32[v24 + 3 + v25]
                                              ^ v21->m128i_i32[v25 + 3])
                                             & 1;
              ++v25;
            }
            while ( (unsigned int)v25 < *(_DWORD *)&v170[16] );
          }
        }
        else
        {
          *(_DWORD *)&v170[20] = 12;
          if ( v22 )
          {
            do
            {
              v26 = 3LL * v25;
              v27 = *(__int64 *)((char *)&v21->m128i_i64[v25 + 1] + 4);
              *(_QWORD *)&v170[4 * v26 + 24] = v27;
              *(_DWORD *)&v170[4 * v26 + 24] ^= (v21->m128i_i32[2 * v24 + 3 + v25++] ^ v27) & 1;
            }
            while ( (unsigned int)v25 < *(_DWORD *)&v170[16] );
          }
        }
        a3 = ETWGUID_DXGKREFERENCEALLOCATIONS;
        goto LABEL_78;
      }
      v9 = v8 - 17;
      if ( !v9 )
      {
        if ( *(_WORD *)(a4 + 86) < 0x30u )
          return 262403;
        v20 = *(unsigned int **)(a4 + 96);
        *(_QWORD *)v170 = *v20;
        *(_DWORD *)&v170[8] = v20[1];
        *(_QWORD *)&v170[12] = *((_QWORD *)v20 + 1);
        *(_DWORD *)&v170[20] = v20[4];
        *(_DWORD *)&v170[24] = v20[5];
        *(_QWORD *)&v170[28] = *((_QWORD *)v20 + 3);
        *(_QWORD *)&v170[36] = v20[8];
        *(_DWORD *)&v170[44] = v20[9];
        a3 = (__int64 *)&ETWGUID_DXGKSCHEDULER_VSYNC_DPC;
        goto LABEL_78;
      }
      v10 = v9 - 10;
      if ( !v10 || (v11 = v10 - 2) == 0 )
      {
        if ( *(_WORD *)(a4 + 86) < 0x10u )
          return 262403;
        v19 = *(const __m128i **)(a4 + 96);
        *(__m128i *)v170 = _mm_unpacklo_epi32(_mm_loadl_epi64(v19), (__m128i)0LL);
        *(_DWORD *)&v170[16] = v19->m128i_i32[2];
        *(_QWORD *)&v170[20] = v19->m128i_u32[3];
        a3 = ETWGUID_DXGKDEVICE;
        goto LABEL_78;
      }
      v12 = v11 - 1;
      if ( !v12 || (v13 = v12 - 2) == 0 )
      {
        if ( *(_WORD *)(a4 + 86) < 0x28u )
          return 262403;
        v18 = *(unsigned int **)(a4 + 96);
        *(_QWORD *)v170 = *v18;
        *(_QWORD *)&v170[8] = *(_QWORD *)(v18 + 1);
        *(_QWORD *)&v170[16] = *(_QWORD *)(v18 + 3);
        *(_DWORD *)&v170[24] = v18[5];
        *(_QWORD *)&v170[28] = *((_QWORD *)v18 + 3);
        *(_DWORD *)&v170[36] = v18[8];
        *(_QWORD *)&v170[40] = v18[9];
        a3 = ETWGUID_DXGKCONTEXT;
        goto LABEL_78;
      }
      v14 = v13 - 9;
      if ( v14 )
      {
        if ( v14 == 1 )
        {
          if ( *(_WORD *)(a4 + 86) < 0xCu )
            return 262403;
          v16 = _mm_loadl_epi64((const __m128i *)*(_QWORD *)(a4 + 96));
          *(_DWORD *)&v170[16] = *(_DWORD *)(*(_QWORD *)(a4 + 96) + 8LL);
          a3 = ETWGUID_DXGKUNLOCKALLOCATION;
          goto LABEL_77;
        }
LABEL_78:
        v41 = 1;
        goto LABEL_80;
      }
      if ( *(_WORD *)(a4 + 86) < 0x10u )
        return 262403;
      v17 = *(_QWORD *)(a4 + 96);
      *(_QWORD *)&v170[16] = *(_QWORD *)(v17 + 8);
      a3 = (__int64 *)&ETWGUID_DXGKLOCKALLOCATION;
    }
    v16 = _mm_loadl_epi64((const __m128i *)v17);
LABEL_77:
    *(__m128i *)v170 = _mm_unpacklo_epi32(v16, (__m128i)0LL);
    goto LABEL_78;
  }
  v41 = 0;
  v7 = v160;
LABEL_80:
  if ( a3 == ETWGUID_DXGKCONTEXT )
  {
    if ( v41 )
    {
      v42 = v170;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x30u )
        return 262403;
      v42 = *(_BYTE **)(a4 + 96);
    }
    v163 = v42;
    v162 = v42 + 40;
    v160.QuadPart = std::map<unsigned __int64,unsigned int>::operator[](v7.LowPart + 208);
    v43 = v163;
    *(_BYTE *)(v160.QuadPart + 1) = v163[8] + 1;
    *(_BYTE *)v160.QuadPart = XPerfAddIn::CDMABufferInfoSource::getHighestSetBitIndex<unsigned int>(*((unsigned int *)v43 + 3))
                            + 1;
    v44 = (_BYTE *)std::map<unsigned __int64,unsigned char>::operator[](v7.LowPart + 344);
    QuadPart = (unsigned __int8 *)v160.QuadPart;
    *(_BYTE *)(v160.QuadPart + 2) = *v44;
    QuadPart[3] = 0;
    if ( (~(1 << (*QuadPart - 1)) & *((_DWORD *)v163 + 3)) != 0 )
      XPerfAddIn::warner::warn<XPerfCore::TimeStamp>(
        v7.QuadPart + 32,
        XPerfCore::TimeStamp::Min,
        L"context %lld has multiple engine affinities (0x%x) -- assuming %d",
        *v162,
        *((_DWORD *)v163 + 3),
        *QuadPart);
  }
  else if ( a3 == ETWGUID_DXGKDEVICE )
  {
    if ( v41 )
    {
      v46 = v170;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x1Cu )
        return 262403;
      v46 = *(_BYTE **)(a4 + 96);
    }
    v160.QuadPart = (LONGLONG)v46;
    v47 = v46 + 20;
    v163 = v47;
    if ( a2 )
    {
      v163 = v47;
    }
    else if ( std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
                v7.QuadPart + 344,
                v47,
                24,
                ETWGUID_DXGKRENDER) )
    {
      return 262400;
    }
    v161 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v7.QuadPart + 96) + 32LL))(
             *(_QWORD *)(v7.QuadPart + 96),
             *(_QWORD *)(v160.QuadPart + 8));
    *(_BYTE *)std::map<unsigned __int64,unsigned char>::operator[](v7.LowPart + 344) = v161;
  }
  if ( !a2 )
    return 262400;
  if ( a3 == ETWGUID_DXGKRENDER || a3 == ETWGUID_DXGKRENDERKM )
  {
    if ( v41 )
    {
      v153 = (__int64 *)v170;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 8u )
        return 262403;
      v153 = *(__int64 **)(a4 + 96);
    }
    v154 = *(_QWORD *)(v7.QuadPart + 80);
    v155 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v154 + 48LL);
    v156 = *(_DWORD *)(a4 + 8);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
    v157 = v155(v154, v164, v156, 0);
    v158 = *v153;
    v159 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, TimeStamp *))(*(_QWORD *)a2 + 72LL))(a2, &v160);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))XPerfAddIn::CDMABufferInfoSource::addDMA)(
      (TimeStamp)v7.QuadPart,
      *v159,
      ETWGUID_DXGKRENDER != a3 ? 4 : 0,
      v158,
      v157);
    return 0;
  }
  if ( a3 == ETWGUID_DXGKBLT )
  {
    if ( v41 )
    {
      v48 = v170;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x58u )
        return 262403;
      v48 = *(_BYTE **)(a4 + 96);
    }
    v49 = *(_QWORD *)(v7.QuadPart + 80);
    v50 = *(__int64 (__fastcall **)(__int64, TimeStamp *, _QWORD, _QWORD))(*(_QWORD *)v49 + 48LL);
    v51 = *(_DWORD *)(a4 + 8);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v160);
    v52 = v50(v49, &v160, v51, 0);
    v53 = *((_QWORD *)v48 + 1);
    v54 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 72LL))(a2, v164);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))XPerfAddIn::CDMABufferInfoSource::addDMA)(
      (TimeStamp)v7.QuadPart,
      *v54,
      1,
      v53,
      v52);
    return 0;
  }
  if ( a3 == ETWGUID_DXGKMEMORYTRANSFER )
  {
    if ( v41 )
    {
      v55 = (TimeStamp *)v170;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x2Cu )
        return 262403;
      v55 = *(TimeStamp **)(a4 + 96);
    }
    if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
            v7.QuadPart + 128,
            &v55[2],
            24,
            ETWGUID_DXGKRENDER) )
    {
      v160 = v55[2];
      v56 = (_QWORD *)XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))XPerfAddIn::CDMABufferInfoSource::addDMA)(
        (TimeStamp)v7.QuadPart,
        *v56,
        2,
        (TimeStamp)v160.QuadPart,
        0);
    }
    v57 = *(unsigned int *)std::map<unsigned __int64,unsigned int>::operator[](v7.LowPart + 128);
    v160.QuadPart = (*(__int64 (__fastcall **)(_QWORD, TimeStamp, _QWORD))(**(_QWORD **)(v7.QuadPart + 88) + 40LL))(
                      *(_QWORD *)(v7.QuadPart + 88),
                      v55[1],
                      XPerfCore::TimeStamp::Max);
    if ( !v160.QuadPart )
    {
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v160);
      XPerfAddIn::CDMABufferInfoSource::reportBadAllocationHandle(
        v58,
        v55[1].QuadPart,
        "memory transfer",
        (const struct TimeStamp *)&v160,
        1);
      return 262400;
    }
    std::vector<XPerfAddIn::DX::IAllocationInfoSource::Allocation const *>::push_back(
      296 * v57 + *(_QWORD *)(v7.QuadPart + 144) + 176LL,
      &v160);
    std::vector<XPerfAddIn::DX::IAllocationInfoSource::Allocation const *>::push_back(
      296 * v57 + *(_QWORD *)(v7.QuadPart + 144) + 200LL,
      &v160);
    v160.QuadPart = 0;
    std::vector<unsigned __int64>::push_back(296 * v57 + *(_QWORD *)(v7.QuadPart + 144) + 224LL, &v160);
    v160.QuadPart = 0;
    std::vector<unsigned __int64>::push_back(296 * v57 + *(_QWORD *)(v7.QuadPart + 144) + 248LL, &v160);
    v59 = *(_QWORD *)(v7.QuadPart + 144) + 296 * v57;
    v60 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 72LL))(a2, v164);
    std::vector<XPerfAddIn::CDriverDelayInfoSource::CDelayDataPtr>::push_back(v59 + 272, v60);
    return 0;
  }
  if ( a3 != ETWGUID_DXGKREFERENCEALLOCATIONS )
  {
    if ( a3 == (__int64 *)&ETWGUID_DXGKSCHEDULER_DMAPACKET )
    {
      if ( *(_BYTE *)(a4 + 45) == 1 )
      {
        if ( v41 )
        {
          v69 = v170;
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x24u )
            return 262403;
          v69 = *(_BYTE **)(a4 + 96);
        }
        if ( *((_DWORD *)v69 + 2) == 3 )
          return 0;
        v70 = v69 + 24;
        if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
                v7.QuadPart + 128,
                v69 + 24,
                24,
                ETWGUID_DXGKRENDER) )
        {
          if ( !*(_BYTE *)(v7.QuadPart + 120) )
            XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
              v7.QuadPart + 32,
              a2,
              L"submission of non-created dma buffer %lld",
              *v70);
          v73 = *v70;
          v74 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 72LL))(a2, v164);
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))XPerfAddIn::CDMABufferInfoSource::addDMA)(
            (TimeStamp)v7.QuadPart,
            *v74,
            5,
            v73,
            0);
        }
        if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
                v7.QuadPart + 208,
                v69,
                v71,
                v72) )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            v7.QuadPart + 32,
            a2,
            L"unrecognized context %lld during submition",
            *(_QWORD *)v69);
          return 262403;
        }
        v75 = *(unsigned int *)std::map<unsigned __int64,unsigned int>::operator[](v7.LowPart + 128);
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v160);
        v76 = 296 * v75;
        *(TimeStamp *)(v76 + *(_QWORD *)(v7.QuadPart + 144) + 8) = v160;
        *(_QWORD *)(v76 + *(_QWORD *)(v7.QuadPart + 144) + 32) = *(_QWORD *)(v69 + 12);
        *(_DWORD *)(v76 + *(_QWORD *)(v7.QuadPart + 144) + 60) = *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[](v7.LowPart + 208);
        v77 = std::map<XPerfAddIn::DX::IDMABufferInfoSource::FullEngineId,XPerfAddIn::CDMABufferInfoSource::EngineState>::operator[](
                v7.QuadPart + 224,
                296 * v75 + *(_QWORD *)(v7.QuadPart + 144) + 60LL);
        *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[](v77) = v75;
        std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::erase(
          v7.QuadPart + 128,
          v69 + 24);
        return 0;
      }
      if ( !*(_BYTE *)(a4 + 45) || v41 && *(_WORD *)(a4 + 40) == 177 )
      {
        if ( v41 )
        {
          v78 = v170;
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x20u )
            return 262403;
          v78 = *(_QWORD **)(a4 + 96);
        }
        if ( *((_DWORD *)v78 + 2) == 3 )
          return 0;
        if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
                v7.QuadPart + 208,
                v78,
                24,
                ETWGUID_DXGKRENDER) )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            v7.QuadPart + 32,
            a2,
            L"unrecognized context %lld during completion",
            *v78);
          return 262403;
        }
        v79 = std::map<unsigned __int64,unsigned int>::operator[](v7.LowPart + 208);
        v80 = std::map<XPerfAddIn::DX::IDMABufferInfoSource::FullEngineId,XPerfAddIn::CDMABufferInfoSource::EngineState>::operator[](
                v7.QuadPart + 224,
                v79);
        v163 = (_BYTE *)v80;
        if ( std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
               v80,
               (char *)v78 + 12,
               v81,
               v82) )
        {
          v83 = *(unsigned int *)std::map<unsigned __int64,unsigned int>::operator[](v80);
          XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v162);
          v84 = (_QWORD *)(v7.QuadPart + 144);
          v85.QuadPart = 296 * v83;
          v160 = v85;
          *(_QWORD *)(v85.QuadPart + *(_QWORD *)(v7.QuadPart + 144) + 24) = v162;
          v86 = *(_QWORD *)(v7.QuadPart + 144);
          v87 = *(_QWORD *)(v86 + 296 * v83 + 24) - *(_QWORD *)(v86 + 296 * v83);
          if ( *(_QWORD *)(v7.QuadPart + 384) > v87 )
            v87 = *(_QWORD *)(v7.QuadPart + 384);
          *(_QWORD *)(v7.QuadPart + 384) = v87;
          if ( *(_QWORD *)(v86 + v85.QuadPart + 16) == XPerfCore::TimeStamp::Min )
            *(_QWORD *)(v86 + v85.QuadPart + 16) = *(_QWORD *)(v86 + v85.QuadPart + 8);
          std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::erase(
            v163,
            (char *)v78 + 12);
          if ( *(_DWORD *)(296 * v83 + *(_QWORD *)(v7.QuadPart + 144) + 56) != 5 )
            *(_BYTE *)(v7.QuadPart + 120) = 0;
          if ( *((_DWORD *)v78 + 6) )
          {
            std::vector<XPerfAddIn::CDMABufferInfoSource::CDMABuffer>::push_back(v7.QuadPart + 144);
            *(_BYTE *)(*v84 + v160.QuadPart + 168) = 1;
            *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 152) - 288LL) = XPerfCore::TimeStamp::Min;
            *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 152) - 280LL) = XPerfCore::TimeStamp::Min;
            *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 152) - 272LL) = XPerfCore::TimeStamp::Min;
            v88 = -1857283155 * ((__int64)(*(_QWORD *)(v7.QuadPart + 152) - *(_QWORD *)(v7.QuadPart + 144)) >> 3) - 1;
            *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[](v7.LowPart + 128) = v88;
            LODWORD(v162) = v83;
            if ( std::_Tree<std::_Tmap_traits<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>,std::less<int>,std::allocator<std::pair<int const,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>,0>>::count(
                   v7.QuadPart + 288,
                   &v162) )
            {
              LODWORD(v162) = v83;
              v164[0] = std::map<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>::operator[](
                          v7.QuadPart + 288,
                          &v162);
              LODWORD(v162) = -1857283155
                            * ((__int64)(*(_QWORD *)(v7.QuadPart + 152) - *(_QWORD *)(v7.QuadPart + 144)) >> 3)
                            - 1;
              v89 = std::map<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>::operator[](
                      v7.QuadPart + 288,
                      &v162);
              std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::operator=(v89, v164[0]);
              LODWORD(v162) = v83;
              std::_Tree<std::_Tmap_traits<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>,std::less<int>,std::allocator<std::pair<int const,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>,0>>::erase(
                v7.QuadPart + 288,
                &v162);
            }
            v90 = v160;
            for ( i = *(_QWORD *)(*v84 + v160.QuadPart + 248); i != *(_QWORD *)(*v84 + v90.QuadPart + 256); i += 8 )
            {
              if ( *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[](v7.LowPart + 304) == (_DWORD)v83 )
              {
                LODWORD(v162) = -1857283155
                              * ((__int64)(*(_QWORD *)(v7.QuadPart + 152) - *(_QWORD *)(v7.QuadPart + 144)) >> 3)
                              - 1;
                *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[](v7.LowPart + 304) = (_DWORD)v162;
              }
              v90 = v160;
            }
          }
          else
          {
            LODWORD(v162) = v83;
            if ( std::_Tree<std::_Tmap_traits<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>,std::less<int>,std::allocator<std::pair<int const,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>,0>>::count(
                   v7.QuadPart + 288,
                   &v162) )
            {
              LODWORD(v162) = v83;
              v92 = (_QWORD *)std::map<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>::operator[](
                                v7.QuadPart + 288,
                                &v162);
              for ( j = (_QWORD *)*v92;
                    ;
                    std::deque<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::push_back(
                      *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 320) + 40LL * *(unsigned __int8 *)(j[2] + 48LL) - 40)
                    - 40LL
                    + 56LL * *(unsigned __int8 *)(j[2] + 49LL),
                      j + 2) )
              {
                j = (_QWORD *)*j;
                if ( j == (_QWORD *)*v92 )
                  break;
                XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
                *(_QWORD *)(j[2] + 8LL) = v164[0];
              }
              LODWORD(v162) = v83;
              std::_Tree<std::_Tmap_traits<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>,std::less<int>,std::allocator<std::pair<int const,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>,0>>::erase(
                v7.QuadPart + 288,
                &v162);
            }
          }
          v80 = (__int64)v163;
        }
        else if ( !*(_BYTE *)(v7.QuadPart + 120) )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            v7.QuadPart + 32,
            a2,
            L"Completion of never-submitted fenceID %lld",
            *v78);
        }
        if ( *(_QWORD *)(v80 + 8) )
        {
          v94 = -1;
          v95 = XPerfCore::TimeStamp::Max;
          v96 = **(_QWORD **)v80;
          while ( v96 != *(_QWORD *)v80 )
          {
            v97 = 296LL * *(unsigned int *)(v96 + 40);
            v98 = *(_QWORD *)(v7.QuadPart + 144);
            v99 = *(_QWORD *)(v97 + v98 + 16);
            if ( v99 == XPerfCore::TimeStamp::Min )
            {
              if ( *(_QWORD *)(v97 + v98 + 8) < v95 )
              {
                v95 = *(_QWORD *)(v97 + v98 + 8);
                v94 = *(_DWORD *)(v96 + 40);
              }
              if ( !*(_BYTE *)(v96 + 25) )
              {
                if ( *(_BYTE *)(*(_QWORD *)(v96 + 16) + 25LL) )
                {
                  for ( k = *(_QWORD *)(v96 + 8); !*(_BYTE *)(k + 25) && v96 == *(_QWORD *)(k + 16); k = *(_QWORD *)(k + 8) )
                    v96 = k;
                }
                else
                {
                  k = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>>>::_Min();
                }
                v96 = k;
              }
            }
            else
            {
              XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
                v7.QuadPart + 32,
                a2,
                L"Buffer fenceid %lld remains in queue after starting at %lld -- dropping",
                *(_QWORD *)(v97 + v98 + 32),
                v99 / 1000);
              v96 = *(_QWORD *)std::_Tree<std::_Tset_traits<XPerfAddIn::IProcessInfoSource::ThreadData const *,std::less<XPerfAddIn::IProcessInfoSource::ThreadData const *>,std::allocator<XPerfAddIn::IProcessInfoSource::ThreadData const *>,0>>::erase(
                                 v80,
                                 v164,
                                 v96);
            }
          }
          if ( v94 != -1 )
          {
            XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
            *(_QWORD *)(296LL * v94 + *(_QWORD *)(v7.QuadPart + 144) + 16) = v164[0];
          }
        }
        return 0;
      }
    }
    if ( a3 == (__int64 *)&ETWGUID_DXGKLOCKALLOCATION )
    {
      if ( v41 )
      {
        v101 = v170;
      }
      else
      {
        if ( *(_WORD *)(a4 + 86) < 0x18u )
          return 262403;
        v101 = *(_BYTE **)(a4 + 96);
      }
      if ( (*((_DWORD *)v101 + 5) & 0x1D2) != 0 )
        return 0;
      v102.QuadPart = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v7.QuadPart + 88) + 32LL))(
                        *(_QWORD *)(v7.QuadPart + 88),
                        *((_QWORD *)v101 + 1),
                        *(unsigned int *)(a4 + 12),
                        XPerfCore::TimeStamp::Max);
      v160 = v102;
      if ( !v102.QuadPart )
        goto LABEL_214;
      if ( *(_QWORD *)(v7.QuadPart + 184) == *(_QWORD *)(v7.QuadPart + 176) )
        return 2147549183LL;
      v167 = 0;
      *(_QWORD *)&v166 = XPerfCore::TimeStamp::Min;
      *((_QWORD *)&v166 + 1) = XPerfCore::TimeStamp::Max;
      std::vector<XPerfAddIn::DX::IDMABufferInfoSource::LockUnLock>::push_back(v7.QuadPart + 168, &v166);
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
      *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 176) - 32LL) = v164[0];
      *(TimeStamp *)(*(_QWORD *)(v7.QuadPart + 176) - 16LL) = v102;
      v104 = *(_QWORD *)(v7.QuadPart + 80);
      v105 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v104 + 48LL);
      v106 = *(_DWORD *)(a4 + 8);
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
      *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 176) - 8LL) = v105(v104, v164, v106, 0);
      v107 = *(_QWORD *)(v7.QuadPart + 176) - 32LL;
      v108 = (__int64 *)std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::operator[](v7.LowPart + 192);
LABEL_269:
      *v108 = v107;
      return 0;
    }
    if ( a3 == ETWGUID_DXGKUNLOCKALLOCATION )
    {
      if ( v41 )
      {
        v101 = v170;
      }
      else
      {
        if ( *(_WORD *)(a4 + 86) < 0x14u )
          return 262403;
        v101 = *(_BYTE **)(a4 + 96);
      }
      v109.QuadPart = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v7.QuadPart + 88) + 32LL))(
                        *(_QWORD *)(v7.QuadPart + 88),
                        *((_QWORD *)v101 + 1),
                        *(unsigned int *)(a4 + 12),
                        XPerfCore::TimeStamp::Max);
      v160 = v109;
      if ( v109.QuadPart )
      {
        if ( std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
               v7.QuadPart + 192,
               &v160,
               v110,
               v111) )
        {
          v112 = *(_QWORD **)std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::operator[](v7.LowPart + 192);
          XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
          v113 = v164[0];
          v112[1] = v164[0];
          v114 = v113 - *v112;
          if ( *(_QWORD *)(v7.QuadPart + 400) > v114 )
            v114 = *(_QWORD *)(v7.QuadPart + 400);
          *(_QWORD *)(v7.QuadPart + 400) = v114;
          std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::erase(
            v7.QuadPart + 192,
            &v160);
        }
        else if ( !*(_BYTE *)(v7.QuadPart + 120) )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            v7.QuadPart + 32,
            a2,
            L"Unlock of allocation %lld which was never locked",
            *(_QWORD *)(v109.QuadPart + 16));
        }
        return 0;
      }
LABEL_214:
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
      XPerfAddIn::CDMABufferInfoSource::reportBadAllocationHandle(
        v103,
        *((_QWORD *)v101 + 1),
        "unlock allocation",
        (const struct TimeStamp *)v164,
        0);
      return 262400;
    }
    if ( a3 != (__int64 *)&ETWGUID_DXGKFLIP )
    {
      if ( a3 == ETWGUID_DXGKSCHEDULER_VSYNC_INTERRUPT )
      {
        if ( v41 )
        {
          v134 = v170;
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x14u )
            return 262403;
          v134 = *(_QWORD **)(a4 + 96);
        }
        v135 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**(_QWORD **)(v7.QuadPart + 96) + 32LL))(
                 *(_QWORD *)(v7.QuadPart + 96),
                 *v134,
                 24,
                 ETWGUID_DXGKRENDER);
        if ( !v135 )
          return 262400;
        v136 = v135;
        if ( v135 > 0xCCCCCCCCCCCCCCCDuLL
                  * ((__int64)(*(_QWORD *)(v7.QuadPart + 328) - *(_QWORD *)(v7.QuadPart + 320)) >> 3) )
          return 262400;
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
        v107 = v164[0];
        v108 = (__int64 *)std::map<unsigned int,XPerfCore::TimeStamp>::operator[]((unsigned int)*(_QWORD *)(v7.QuadPart + 320) + 8 * (v136 + 4 * v136 - 2));
        goto LABEL_269;
      }
      if ( a3 != (__int64 *)&ETWGUID_DXGKSCHEDULER_VSYNC_DPC )
        return 0;
      if ( v41 )
      {
        v137 = v170;
      }
      else
      {
        if ( *(_WORD *)(a4 + 86) < 0x38u )
          return 262403;
        v137 = *(_BYTE **)(a4 + 96);
      }
      v138 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**(_QWORD **)(v7.QuadPart + 96) + 32LL))(
               *(_QWORD *)(v7.QuadPart + 96),
               *(_QWORD *)v137,
               24,
               ETWGUID_DXGKRENDER);
      v161 = v138;
      if ( !v138 )
        return 262400;
      v139 = *(_QWORD *)(v7.QuadPart + 320);
      if ( v138 > 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(v7.QuadPart + 328) - v139) >> 3) )
        return 262400;
      v140 = 5LL * v138;
      v141 = (__int64 *)std::map<unsigned int,XPerfCore::TimeStamp>::operator[](v139 - 16 + 40 * v138);
      v142 = *v141;
      if ( *v141 == XPerfCore::TimeStamp::Min )
      {
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(v7.QuadPart + 32, a2, L"VSync DPC without ISR");
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
        v142 = v164[0];
      }
      v143 = *(_QWORD *)(v7.QuadPart + 320);
      v144 = *((unsigned int *)v137 + 5);
      if ( v144 < 0x6DB6DB6DB6DB6DB7LL
                * ((__int64)(*(_QWORD *)(v143 + 8 * v140 - 32) - *(_QWORD *)(v143 + 8 * v140 - 40)) >> 3) )
      {
        v145 = *(_QWORD *)(v143 + 8 * v140 - 40) + 56 * v144;
        if ( *(_QWORD *)(v145 + 48) )
        {
          std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
            v164,
            *(_QWORD *)(v145 + 40),
            v145 + 16);
          if ( v164[0] )
            v146 = *(_QWORD *)v164[0];
          else
            v146 = 0;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v146 + 8) + 8 * ((v165 >> 1) & (*(_QWORD *)(v146 + 16) - 1LL)))
                                + 8 * (v165 & 1))
                    + 24LL) = v142;
          std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
            v164,
            *(_QWORD *)(v145 + 40),
            v145 + 16);
          if ( v164[0] )
            v147 = *(_QWORD *)v164[0];
          else
            v147 = 0;
          v164[0] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v147 + 8) + 8 * ((v165 >> 1) & (*(_QWORD *)(v147 + 16) - 1LL)))
                              + 8 * (v165 & 1));
          std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
            &v166,
            *(_QWORD *)(v145 + 40),
            v145 + 16);
          if ( (_QWORD)v166 )
            v148 = *(_QWORD *)v166;
          else
            v148 = 0;
          v149 = *(_QWORD *)(v7.QuadPart + 392);
          if ( v149 <= *(_QWORD *)(v164[0] + 24LL)
                     - **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v148 + 8)
                                               + 8 * (((unsigned __int64)v167 >> 1) & (*(_QWORD *)(v148 + 16) - 1LL)))
                                   + 8 * (v167 & 1)) )
          {
            std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
              &v166,
              *(_QWORD *)(v145 + 40),
              v145 + 16);
            if ( (_QWORD)v166 )
              v150 = *(_QWORD *)v166;
            else
              v150 = 0;
            v164[0] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v150 + 8)
                                            + 8 * (((unsigned __int64)v167 >> 1) & (*(_QWORD *)(v150 + 16) - 1LL)))
                                + 8 * (v167 & 1));
            std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
              &v166,
              *(_QWORD *)(v145 + 40),
              v145 + 16);
            if ( (_QWORD)v166 )
              v151 = *(_QWORD *)v166;
            else
              v151 = 0;
            v149 = *(_QWORD *)(v164[0] + 24LL)
                 - **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v151 + 8)
                                           + 8 * (((unsigned __int64)v167 >> 1) & (*(_QWORD *)(v151 + 16) - 1LL)))
                               + 8 * (v167 & 1));
          }
          *(_QWORD *)(v7.QuadPart + 392) = v149;
          std::deque<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::pop_front(v145 + 16);
        }
        for ( m = *(_QWORD **)v145; ; *(_QWORD *)(m[2] + 16LL) = v142 )
        {
          m = (_QWORD *)*m;
          if ( m == *(_QWORD **)v145 )
            break;
        }
        std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::clear(v145);
      }
      if ( *(_QWORD *)(v7.QuadPart + 376) == *(_QWORD *)(v7.QuadPart + 368) )
        return 2147549183LL;
      v164[1] = 0;
      v164[0] = 0;
      std::vector<XPerfAddIn::DX::Warning>::push_back(v7.QuadPart + 360, v164);
      *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 368) - 16LL) = v142;
      *(_BYTE *)(*(_QWORD *)(v7.QuadPart + 368) - 8LL) = v161;
      *(_BYTE *)(*(_QWORD *)(v7.QuadPart + 368) - 7LL) = v137[20] + 1;
      v133 = *(_QWORD *)(v7.QuadPart + 368);
LABEL_259:
      *(_DWORD *)(v133 - 6) = 0;
      *(_WORD *)(v133 - 2) = 0;
      return 0;
    }
    if ( v41 )
    {
      v115 = v170;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x1Au )
        return 262403;
      v115 = *(_BYTE **)(a4 + 96);
    }
    if ( *(_QWORD *)v115 )
    {
      v116 = *(TimeStamp ***)(v7.QuadPart + 80);
      v160 = (*v116)[6];
      LODWORD(v162) = *(_DWORD *)(a4 + 8);
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
      v160.QuadPart = ((__int64 (__fastcall *)(TimeStamp **, _QWORD *, _QWORD, _QWORD))v160.QuadPart)(
                        v116,
                        v164,
                        (unsigned int)v162,
                        0);
      v117 = *(_QWORD *)v115;
      v118 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)a2 + 72LL))(a2, &v163);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))XPerfAddIn::CDMABufferInfoSource::addDMA)(
        (TimeStamp)v7.QuadPart,
        *v118,
        3,
        v117,
        (TimeStamp)v160.QuadPart);
    }
    if ( *(_QWORD *)(v7.QuadPart + 280) == *(_QWORD *)(v7.QuadPart + 272) )
      return 2147549183LL;
    v160 = *(TimeStamp *)(v115 + 12);
    v119 = (*(__int64 (__fastcall **)(_QWORD, TimeStamp, _QWORD, _QWORD))(**(_QWORD **)(v7.QuadPart + 88) + 32LL))(
             *(_QWORD *)(v7.QuadPart + 88),
             v160,
             *(unsigned int *)(a4 + 12),
             XPerfCore::TimeStamp::Max);
    if ( !v119 )
    {
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
      XPerfAddIn::CDMABufferInfoSource::reportBadAllocationHandle(
        v120,
        *(_QWORD *)(v115 + 12),
        "flip",
        (const struct TimeStamp *)v164,
        0);
      return 262400;
    }
    v168 = 0;
    v169 = 0;
    v166 = 0;
    v167 = 0;
    std::vector<XPerfAddIn::DX::IDMABufferInfoSource::Flip>::push_back(v7.QuadPart + 264, &v166);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
    *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 272) - 56LL) = v164[0];
    *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 272) - 24LL) = v119;
    v121 = (_QWORD *)XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
    v122 = XPerfAddIn::Alloc_SegmentAt(v119, *v121);
    if ( !v122 || (*(_BYTE *)(v122 + 8) & 1) != 0 )
    {
      XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
        v7.QuadPart + 32,
        a2,
        L"Flip of allocation %llx from system memory",
        *(_QWORD *)(v119 + 16));
      v123 = *(_BYTE *)(v119 + 108);
    }
    else
    {
      v123 = *(_BYTE *)(v122 + 12);
    }
    *(_BYTE *)(*(_QWORD *)(v7.QuadPart + 272) - 8LL) = v123;
    *(_BYTE *)(*(_QWORD *)(v7.QuadPart + 272) - 7LL) = v115[8] + 1;
    v124 = *(_QWORD *)(v7.QuadPart + 80);
    v125 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v124 + 48LL);
    v126 = *(_DWORD *)(a4 + 8);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
    *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 272) - 16LL) = v125(v124, v164, v126, 0);
    v128 = (_QWORD *)(v7.QuadPart + 320);
    if ( *(unsigned __int8 *)(*(_QWORD *)(v7.QuadPart + 272) - 8LL) > 0xCCCCCCCCCCCCCCCDuLL
                                                                    * ((__int64)(*(_QWORD *)(v7.QuadPart + 328)
                                                                               - *(_QWORD *)(v7.QuadPart + 320)) >> 3) )
      std::vector<XPerfAddIn::CDMABufferInfoSource::AdapterState>::resize(v7.QuadPart + 320);
    v129 = (_QWORD *)(*v128 + 40 * (*(unsigned __int8 *)(*(_QWORD *)(v7.QuadPart + 272) - 8LL) - 1LL));
    v130 = *((unsigned int *)v115 + 2);
    if ( v130 >= 0x6DB6DB6DB6DB6DB7LL * ((__int64)(v129[1] - *v129) >> 3) )
      std::vector<XPerfAddIn::CDMABufferInfoSource::AdapterState::MonitorState>::resize(v129, (unsigned int)(v130 + 1));
    if ( *(_QWORD *)v115 )
    {
      v131 = v7.LowPart + 128;
    }
    else
    {
      if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
              v7.QuadPart + 304,
              &v160,
              v130,
              v127)
        || *(_QWORD *)(296LL * *(unsigned int *)std::map<unsigned __int64,unsigned int>::operator[](v7.LowPart + 304)
                     + *(_QWORD *)(v7.QuadPart + 144)
                     + 24) != XPerfCore::TimeStamp::Min )
      {
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
        *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 272) - 48LL) = v164[0];
        v164[0] = *(_QWORD *)(v7.QuadPart + 272) - 56LL;
        std::deque<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::push_back(
          *(_QWORD *)(*v128 + 40LL * *(unsigned __int8 *)(v164[0] + 48LL) - 40)
        + 16LL
        + 56LL * *((unsigned int *)v115 + 2),
          v164);
        goto LABEL_258;
      }
      v131 = v7.LowPart + 304;
    }
    LODWORD(v162) = *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[](v131);
    v132 = std::map<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>::operator[](v7.QuadPart + 288, &v162);
    v164[0] = *(_QWORD *)(v7.QuadPart + 272) - 56LL;
    std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::push_back(v132, v164);
LABEL_258:
    v164[0] = *(_QWORD *)(v7.QuadPart + 272) - 56LL;
    std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::push_back(
      *(_QWORD *)(*v128 + 40LL * *(unsigned __int8 *)(v164[0] + 48LL) - 40) + 56LL * *((unsigned int *)v115 + 2),
      v164);
    v133 = *(_QWORD *)(v7.QuadPart + 272);
    goto LABEL_259;
  }
  if ( *(_WORD *)(a4 + 86) < 0x18u )
    return 262403;
  v61 = v170;
  if ( !v41 )
    v61 = *(_BYTE **)(a4 + 96);
  if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
          v7.QuadPart + 128,
          v61 + 8,
          24,
          ETWGUID_DXGKRENDER) )
  {
    if ( !*(_BYTE *)(v7.QuadPart + 120) )
      XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
        v7.QuadPart + 32,
        a2,
        L"allocation reference listing for never-created dma buffer %lld",
        *((_QWORD *)v61 + 1));
    v62 = *(_QWORD *)(v7.QuadPart + 80);
    v163 = *(_BYTE **)(*(_QWORD *)v62 + 48LL);
    v63 = *(_DWORD *)(a4 + 8);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v160);
    v64 = ((__int64 (__fastcall *)(__int64, TimeStamp *, _QWORD, _QWORD))v163)(v62, &v160, v63, 0);
    v65 = *((_QWORD *)v61 + 1);
    v66 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 72LL))(a2, v164);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))XPerfAddIn::CDMABufferInfoSource::addDMA)(
      (TimeStamp)v7.QuadPart,
      *v66,
      5,
      v65,
      v64);
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 80LL))(a2) == 4 )
  {
    v67 = (_QWORD *)XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
    result = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))XPerfAddIn::CDMABufferInfoSource::handleReferences<_DXGKETW_REFERENCEALLOCATIONRECORD32>)(
               (TimeStamp)v7.QuadPart,
               a4,
               *v67);
    if ( (int)result < 0 )
      return result;
    return 0;
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 80LL))(a2) != 8 )
    return 2147549183LL;
  v68 = (_QWORD *)XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v164);
  result = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))XPerfAddIn::CDMABufferInfoSource::handleReferences<_DXGKETW_REFERECENALLOCATIONRECORD64>)(
             (TimeStamp)v7.QuadPart,
             a4,
             *v68);
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18005080c  push    rbx
0x18005080e  push    rsi
0x18005080f  push    rdi
0x180050810  push    r12
0x180050812  push    r13
0x180050814  push    r14
0x180050816  push    r15
0x180050818  sub     rsp, 0CD0h
0x18005081f  mov     rax, cs:__security_cookie
0x180050826  xor     rax, rsp
0x180050829  mov     [rsp+0D08h+var_48], rax
0x180050831  mov     rbx, r9
0x180050834  mov     rdi, r8
0x180050837  mov     r15, rdx
0x18005083a  mov     rsi, rcx
0x18005083d  mov     qword ptr [rsp+0D08h+var_CD8], rcx
0x180050842  xor     edx, edx; Val
0x180050844  mov     r8d, 0C18h; Size
0x18005084a  lea     rcx, [rsp+0D08h+var_C68]; void *
0x180050852  call    memset_0
0x180050857  lea     rax, DxgkControlGuid
0x18005085e  cmp     rdi, rax
0x180050861  jnz     loc_180050F6A
0x180050867  movzx   ecx, word ptr [rbx+28h]
0x18005086b  cmp     ecx, 2Bh ; '+'
0x18005086e  ja      loc_180050B8D
0x180050874  jz      loc_180050A68
0x18005087a  sub     ecx, 11h
0x18005087d  jz      loc_1800509F2
0x180050883  sub     ecx, 0Ah
0x180050886  jz      loc_18005099E
0x18005088c  sub     ecx, 2
0x18005088f  jz      loc_18005099E
0x180050895  sub     ecx, 1
0x180050898  jz      short loc_180050915
0x18005089a  sub     ecx, 2
0x18005089d  jz      short loc_180050915
0x18005089f  sub     ecx, 9
0x1800508a2  jz      short loc_1800508E0
0x1800508a4  cmp     ecx, 1
0x1800508a7  jnz     loc_180050F30
0x1800508ad  lea     r12d, [rcx+0Bh]
0x1800508b1  cmp     [rbx+56h], r12w
0x1800508b6  jnb     short loc_1800508C2
0x1800508b8  mov     eax, 40103h
0x1800508bd  jmp     loc_180052627
0x1800508c2  mov     rax, [rbx+60h]
0x1800508c6  movq    xmm1, qword ptr [rax]
0x1800508ca  mov     eax, [rax+8]
0x1800508cd  mov     dword ptr [rsp+0D08h+var_C58], eax
0x1800508d4  lea     rdi, ETWGUID_DXGKUNLOCKALLOCATION
0x1800508db  jmp     loc_180050F20
0x1800508e0  cmp     word ptr [rbx+56h], 10h
0x1800508e5  jnb     short loc_1800508F1
0x1800508e7  mov     eax, 40103h
0x1800508ec  jmp     loc_180052627
0x1800508f1  mov     rcx, [rbx+60h]
0x1800508f5  mov     eax, [rcx+8]
0x1800508f8  mov     dword ptr [rsp+0D08h+var_C58], eax
0x1800508ff  mov     eax, [rcx+0Ch]
0x180050902  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180050909  lea     rdi, ETWGUID_DXGKLOCKALLOCATION
0x180050910  jmp     loc_180050F1C
0x180050915  cmp     word ptr [rbx+56h], 28h ; '('
0x18005091a  jnb     short loc_180050926
0x18005091c  mov     eax, 40103h
0x180050921  jmp     loc_180052627
0x180050926  mov     rcx, [rbx+60h]
0x18005092a  mov     eax, [rcx]
0x18005092c  mov     qword ptr [rsp+0D08h+var_C68], rax
0x180050934  mov     eax, [rcx+4]
0x180050937  mov     dword ptr [rsp+0D08h+var_C68+8], eax
0x18005093e  mov     eax, [rcx+8]
0x180050941  mov     dword ptr [rsp+0D08h+var_C68+0Ch], eax
0x180050948  mov     eax, [rcx+0Ch]
0x18005094b  mov     dword ptr [rsp+0D08h+var_C58], eax
0x180050952  mov     eax, [rcx+10h]
0x180050955  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x18005095c  mov     eax, [rcx+14h]
0x18005095f  mov     [rsp+0B8h], eax
0x180050966  mov     eax, [rcx+18h]
0x180050969  mov     [rsp+0BCh], eax
0x180050970  mov     eax, [rcx+1Ch]
0x180050973  mov     [rsp+0C0h], eax
0x18005097a  mov     eax, [rcx+20h]
0x18005097d  mov     dword ptr [rsp+0D08h+var_C44], eax
0x180050984  mov     eax, [rcx+24h]
0x180050987  mov     [rsp+0D08h+var_C44+4], rax
0x18005098f  lea     rax, ETWGUID_DXGKCONTEXT
0x180050996  mov     rdi, rax
0x180050999  jmp     loc_180050F37
0x18005099e  cmp     word ptr [rbx+56h], 10h
0x1800509a3  jnb     short loc_1800509AF
0x1800509a5  mov     eax, 40103h
0x1800509aa  jmp     loc_180052627
0x1800509af  mov     rcx, [rbx+60h]
0x1800509b3  movq    xmm1, qword ptr [rcx]
0x1800509b7  xorps   xmm0, xmm0
0x1800509ba  punpckldq xmm1, xmm0
0x1800509be  movdqa  [rsp+0D08h+var_C68], xmm1
0x1800509c7  mov     eax, [rcx+8]
0x1800509ca  mov     dword ptr [rsp+0D08h+var_C58], eax
0x1800509d1  mov     eax, [rcx+0Ch]
0x1800509d4  mov     [rsp+0D08h+var_C58+4], rax
0x1800509dc  lea     rcx, ETWGUID_DXGKDEVICE
0x1800509e3  mov     rdi, rcx
0x1800509e6  lea     rax, ETWGUID_DXGKCONTEXT
0x1800509ed  jmp     loc_180050F3E
0x1800509f2  cmp     word ptr [rbx+56h], 30h ; '0'
0x1800509f7  jnb     short loc_180050A03
0x1800509f9  mov     eax, 40103h
0x1800509fe  jmp     loc_180052627
0x180050a03  mov     rcx, [rbx+60h]
0x180050a07  mov     eax, [rcx]
0x180050a09  mov     qword ptr [rsp+0D08h+var_C68], rax
0x180050a11  mov     eax, [rcx+4]
0x180050a14  mov     dword ptr [rsp+0D08h+var_C68+8], eax
0x180050a1b  mov     rax, [rcx+8]
0x180050a1f  mov     qword ptr [rsp+0D08h+var_C68+0Ch], rax
0x180050a27  mov     eax, [rcx+10h]
0x180050a2a  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180050a31  mov     eax, [rcx+14h]
0x180050a34  mov     [rsp+0B8h], eax
0x180050a3b  mov     rax, [rcx+18h]
0x180050a3f  mov     [rsp+0BCh], rax
0x180050a47  mov     eax, [rcx+20h]
0x180050a4a  mov     [rsp+0D08h+var_C44], rax
0x180050a52  mov     eax, [rcx+24h]
0x180050a55  mov     [rsp+0D08h+var_C3C], eax
0x180050a5c  lea     rdi, ETWGUID_DXGKSCHEDULER_VSYNC_DPC
0x180050a63  jmp     loc_180050F30
0x180050a68  mov     r12d, 0Ch
0x180050a6e  cmp     [rbx+56h], r12w
0x180050a73  jnb     short loc_180050A7F
0x180050a75  mov     eax, 40103h
0x180050a7a  jmp     loc_180052627
0x180050a7f  mov     rdi, [rbx+60h]
0x180050a83  movq    xmm1, qword ptr [rdi]
0x180050a87  xorps   xmm0, xmm0
0x180050a8a  punpckldq xmm1, xmm0
0x180050a8e  movdqa  [rsp+0D08h+var_C68], xmm1
0x180050a97  mov     r13d, [rdi+8]
0x180050a9b  mov     dword ptr [rsp+0D08h+var_C58], r13d
0x180050aa3  xor     r14d, r14d
0x180050aa6  test    r15, r15
0x180050aa9  jnz     short loc_180050AB5
0x180050aab  mov     eax, 40100h
0x180050ab0  jmp     loc_180052627
0x180050ab5  mov     rax, [r15]
0x180050ab8  mov     rcx, r15
0x180050abb  mov     rax, [rax+50h]
0x180050abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ac4  mov     ecx, [rdi+8]
0x180050ac7  mov     edx, 4
0x180050acc  movzx   r8d, r14w
0x180050ad0  cmp     eax, edx
0x180050ad2  jnz     short loc_180050B1A
0x180050ad4  mov     dword ptr [rsp+0D08h+var_C58+4], edx
0x180050adb  lea     r9, [rdi+rcx*4]
0x180050adf  test    r13d, r13d
0x180050ae2  jz      loc_180050B6D
0x180050ae8  lea     r12d, [rdx-3]
0x180050aec  movzx   ecx, r8w
0x180050af0  mov     eax, [rdi+rcx*4+0Ch]
0x180050af4  xor     eax, [r9+rcx*4+0Ch]
0x180050af9  and     eax, r12d
0x180050afc  xor     eax, [rdi+rcx*4+0Ch]
0x180050b00  mov     [rsp+rcx*4+0B8h], eax
0x180050b07  add     r8w, r12w
0x180050b0b  movzx   eax, r8w
0x180050b0f  cmp     eax, dword ptr [rsp+0D08h+var_C58]
0x180050b16  jb      short loc_180050AEC
0x180050b18  jmp     short loc_180050B73
0x180050b1a  mov     dword ptr [rsp+0D08h+var_C58+4], r12d
0x180050b22  lea     r9, [rdi+rcx*8]
0x180050b26  test    r13d, r13d
0x180050b29  jz      short loc_180050B6D
0x180050b2b  mov     r12d, 1
0x180050b31  movzx   ecx, r8w
0x180050b35  lea     rdx, [rcx+rcx*2]
0x180050b39  mov     rax, [rdi+rcx*8+0Ch]
0x180050b3e  mov     [rsp+rdx*4+0B8h], rax
0x180050b46  xor     eax, [r9+rcx*4+0Ch]
0x180050b4b  and     eax, r12d
0x180050b4e  xor     [rsp+rdx*4+0B8h], eax
0x180050b55  add     r8w, r12w
0x180050b59  movzx   eax, r8w
0x180050b5d  cmp     eax, dword ptr [rsp+0D08h+var_C58]
0x180050b64  jb      short loc_180050B31
0x180050b66  mov     edx, 4
0x180050b6b  jmp     short loc_180050B73
0x180050b6d  mov     r12d, 1
0x180050b73  lea     rdi, ETWGUID_DXGKREFERENCEALLOCATIONS
0x180050b7a  lea     rax, ETWGUID_DXGKCONTEXT
0x180050b81  lea     rcx, ETWGUID_DXGKDEVICE
0x180050b88  jmp     loc_180050F4A
0x180050b8d  sub     ecx, 32h ; '2'
0x180050b90  jz      loc_180050ED3
0x180050b96  sub     ecx, 74h ; 't'
0x180050b99  jz      loc_180050E79
0x180050b9f  sub     ecx, 2
0x180050ba2  jz      loc_180050DEA
0x180050ba8  sub     ecx, 1
0x180050bab  jz      loc_180050D9C
0x180050bb1  sub     ecx, 6
0x180050bb4  jz      loc_180050CEB
0x180050bba  sub     ecx, 2
0x180050bbd  jz      short loc_180050C17
0x180050bbf  mov     edx, 4
0x180050bc4  cmp     ecx, edx
0x180050bc6  jnz     short loc_180050C04
0x180050bc8  cmp     word ptr [rbx+56h], 10h
0x180050bcd  jnb     short loc_180050BD9
0x180050bcf  mov     eax, 40103h
0x180050bd4  jmp     loc_180052627
0x180050bd9  mov     rcx, [rbx+60h]
0x180050bdd  mov     eax, [rcx]
0x180050bdf  mov     qword ptr [rsp+0D08h+var_C68], rax
0x180050be7  mov     eax, [rcx+4]
0x180050bea  mov     dword ptr [rsp+0D08h+var_C68+8], eax
0x180050bf1  mov     rax, [rcx+8]
0x180050bf5  mov     qword ptr [rsp+0D08h+var_C68+0Ch], rax
0x180050bfd  lea     rdi, ETWGUID_DXGKSCHEDULER_VSYNC_INTERRUPT
0x180050c04  lea     rax, ETWGUID_DXGKCONTEXT
0x180050c0b  lea     rcx, ETWGUID_DXGKDEVICE
0x180050c12  jmp     loc_180050F43
0x180050c17  xor     r14d, r14d
0x180050c1a  cmp     [rbx+2Ah], r14b
0x180050c1e  jnz     short loc_180050C6B
0x180050c20  cmp     word ptr [rbx+56h], 1Ch
0x180050c25  jnb     short loc_180050C31
0x180050c27  mov     eax, 40103h
0x180050c2c  jmp     loc_180052627
0x180050c31  mov     rcx, [rbx+60h]
0x180050c35  mov     eax, [rcx]
0x180050c37  mov     qword ptr [rsp+0D08h+var_C68], rax
0x180050c3f  mov     eax, [rcx+4]
0x180050c42  mov     dword ptr [rsp+0D08h+var_C68+8], eax
0x180050c49  mov     rax, [rcx+8]
0x180050c4d  mov     qword ptr [rsp+0D08h+var_C68+0Ch], rax
0x180050c55  mov     eax, [rcx+10h]
0x180050c58  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180050c5f  mov     eax, r14d
0x180050c62  cmp     [rcx+14h], r14d
0x180050c66  setnz   al
0x180050c69  jmp     short loc_180050CB4
0x180050c6b  cmp     word ptr [rbx+56h], 2Ch ; ','
0x180050c70  jnb     short loc_180050C7C
0x180050c72  mov     eax, 40103h
0x180050c77  jmp     loc_180052627
0x180050c7c  mov     rcx, [rbx+60h]
0x180050c80  mov     eax, [rcx]
0x180050c82  mov     qword ptr [rsp+0D08h+var_C68], rax
0x180050c8a  mov     eax, [rcx+4]
0x180050c8d  mov     dword ptr [rsp+0D08h+var_C68+8], eax
0x180050c94  mov     rax, [rcx+8]
0x180050c98  mov     qword ptr [rsp+0D08h+var_C68+0Ch], rax
0x180050ca0  mov     eax, [rcx+10h]
0x180050ca3  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180050caa  mov     eax, r14d
0x180050cad  cmp     dword ptr [rcx+14h], 2
0x180050cb1  setz    al
0x180050cb4  mov     [rsp+0B8h], eax
0x180050cbb  mov     eax, [rcx+18h]
0x180050cbe  mov     [rsp+0BCh], eax
0x180050cc5  lea     r10, ETWGUID_DXGKSCHEDULER_DMAPACKET
0x180050ccc  mov     rdi, r10
0x180050ccf  lea     rax, ETWGUID_DXGKCONTEXT
0x180050cd6  lea     rcx, ETWGUID_DXGKDEVICE
0x180050cdd  mov     edx, 4
0x180050ce2  lea     r12d, [rdx-3]
0x180050ce6  jmp     loc_180050F51
0x180050ceb  xor     r14d, r14d
0x180050cee  cmp     [rbx+2Ah], r14b
0x180050cf2  jnz     short loc_180050D43
0x180050cf4  cmp     word ptr [rbx+56h], 1Ch
0x180050cf9  jnb     short loc_180050D05
0x180050cfb  mov     eax, 40103h
0x180050d00  jmp     loc_180052627
0x180050d05  mov     rcx, [rbx+60h]
0x180050d09  mov     eax, [rcx]
0x180050d0b  mov     qword ptr [rsp+0D08h+var_C68], rax
0x180050d13  mov     eax, [rcx+4]
0x180050d16  mov     dword ptr [rsp+0D08h+var_C68+8], eax
0x180050d1d  mov     rax, [rcx+8]
0x180050d21  mov     qword ptr [rsp+0D08h+var_C68+0Ch], rax
0x180050d29  mov     eax, [rcx+10h]
0x180050d2c  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180050d33  mov     eax, [rcx+14h]
0x180050d36  mov     [rsp+0B8h], rax
0x180050d3e  mov     eax, [rcx+18h]
0x180050d41  jmp     short loc_180050D90
0x180050d43  cmp     word ptr [rbx+56h], 20h ; ' '
0x180050d48  jnb     short loc_180050D54
0x180050d4a  mov     eax, 40103h
0x180050d4f  jmp     loc_180052627
0x180050d54  mov     rcx, [rbx+60h]
0x180050d58  mov     eax, [rcx]
0x180050d5a  mov     qword ptr [rsp+0D08h+var_C68], rax
0x180050d62  mov     eax, [rcx+8]
  ... truncated ...
```

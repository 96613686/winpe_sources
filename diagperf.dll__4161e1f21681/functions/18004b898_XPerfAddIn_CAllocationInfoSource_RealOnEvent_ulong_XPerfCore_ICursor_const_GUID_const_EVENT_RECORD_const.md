# XPerfAddIn::CAllocationInfoSource::RealOnEvent<ulong>(XPerfCore::ICursor const *,_GUID const *,_EVENT_RECORD const *)

- ea: `0x18004b898`
- end: `0x18004c970`
- name: `??$RealOnEvent@K@CAllocationInfoSource@XPerfAddIn@@QEAAJPEBUICursor@XPerfCore@@PEBU_GUID@@PEBU_EVENT_RECORD@@@Z`
- size: `4312`
- prototype: `__int64 __fastcall(XPerfAddIn::CAllocationInfoSource *this, struct XPerfCore::ICursor *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config`

## callers

- `0x180090dd0`
- `0x1800910e0`

## callees

- `0x180011e00`
- `0x18004b898`
- `0x18004dac4`
- `0x18004db68`
- `0x180050544`
- `0x180055fac`
- `0x180056c14`
- `0x180057df8`
- `0x180079458`
- `0x18008f9fc`
- `0x18008fad8`
- `0x18009016c`
- `0x1800908e4`
- `0x180090990`
- `0x180091bec`
- `0x1800923b8`
- `0x1800923f4`
- `0x180092444`
- `0x18009249c`
- `0x180092550`
- `0x1800925dc`
- `0x180092678`
- `0x1800cf032`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `msvcrt!fprintf` at `0x18004c630`
- `msvcrt!fprintf` at `0x18004c630`

## string_xrefs

- `0x18004c01f`: `destroying never-created allocation with global handle %lld`
- `0x18004c569`: `opening nonexistent target %lld (as %lld by %lld)`
- `0x18004c49f`: `opening already open local handle %lld (previously open at %lld) by PID %lld -- autoclosing`
- `0x18004c3eb`: `closing already-closed allocation`
- `0x18004c3c4`: `closing never-opened allocation (%lld)`
- `0x18004c928`: `alloc %lld which was in %d/%d moved from %d/%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall XPerfAddIn::CAllocationInfoSource::RealOnEvent<unsigned long>(
        XPerfAddIn::CAllocationInfoSource *this,
        struct XPerfCore::ICursor *a2,
        __int64 *a3,
        __int64 a4)
{
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  const struct _GUID *v15; // r9
  __int64 *v16; // rcx
  unsigned __int64 v17; // rdi
  __int64 *v18; // r8
  char v19; // r10
  __int64 v21; // rcx
  const __m128i *v22; // roff
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // roff
  _BYTE *v32; // r15
  char v33; // di
  unsigned int *v34; // r12
  XPerfAddIn::CAllocationInfoSource::CAllocation *v35; // r15
  __int64 v36; // rbx
  __int64 v37; // r15
  __int64 v38; // rax
  unsigned int v39; // ebx
  _QWORD *v40; // rbx
  __int64 v41; // rdx
  int v42; // r14d
  __int64 v43; // r8
  __int64 v44; // rax
  __int64 v45; // rdx
  _QWORD *v46; // rdx
  __int64 v47; // rax
  __int64 v48; // xmm1_8
  __int64 v49; // rax
  _QWORD *v50; // r12
  _QWORD *v51; // rax
  _QWORD *v52; // r15
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rbx
  __int64 v56; // rax
  __int64 v57; // r13
  __int64 v58; // rdx
  unsigned __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rcx
  _BYTE *v62; // rbx
  __int64 v63; // r12
  XPerfAddIn::CAllocationInfoSource::CAllocation *v64; // r15
  _BYTE *v65; // rax
  __int64 v66; // r8
  _BYTE *v67; // rdx
  __int64 v68; // rbx
  FILE *v69; // rax
  __int64 v70; // rax
  unsigned int *v71; // rbx
  int v72; // r12d
  __int64 v73; // rcx
  __int64 v74; // r15
  XPerfAddIn::CAllocationInfoSource::CAllocation *v75; // r13
  XPerfAddIn::CAllocationInfoSource::CAllocation *v76; // r15
  const struct XPerfAddIn::DX::ISegmentInfoSource::Segment *Segment; // r13
  __int64 v78; // rax
  const struct XPerfAddIn::DX::ISegmentInfoSource::Segment *v79; // r15
  XPerfAddIn::CAllocationInfoSource::CAllocation *v80; // rbx
  const struct XPerfAddIn::DX::ISegmentInfoSource::Segment *v81; // rax
  int v82; // r8d
  int v83; // ecx
  int v84; // eax
  int v85; // edx
  XPerfAddIn::CAllocationInfoSource::CAllocation *v86; // [rsp+40h] [rbp-198h] BYREF
  __int64 v87; // [rsp+48h] [rbp-190h] BYREF
  __int64 v88; // [rsp+50h] [rbp-188h]
  __int64 v89; // [rsp+58h] [rbp-180h]
  __int64 v90; // [rsp+60h] [rbp-178h] BYREF
  int v91; // [rsp+68h] [rbp-170h]
  _BYTE v92[56]; // [rsp+80h] [rbp-158h] BYREF
  int v93; // [rsp+B8h] [rbp-120h]
  _BYTE v94[20]; // [rsp+BCh] [rbp-11Ch]
  __int64 v95; // [rsp+D0h] [rbp-108h]
  int v96; // [rsp+D8h] [rbp-100h]
  int v97; // [rsp+DCh] [rbp-FCh]
  int v98; // [rsp+E0h] [rbp-F8h]
  int v99; // [rsp+E4h] [rbp-F4h]
  int v100; // [rsp+E8h] [rbp-F0h]
  int v101; // [rsp+ECh] [rbp-ECh]
  int v102; // [rsp+F0h] [rbp-E8h]
  int v103; // [rsp+F4h] [rbp-E4h]
  int v104; // [rsp+F8h] [rbp-E0h]
  int v105; // [rsp+FCh] [rbp-DCh]
  _QWORD v106[6]; // [rsp+100h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+130h] [rbp-A8h]
  __m128i v108; // [rsp+140h] [rbp-98h]
  __int64 v109; // [rsp+150h] [rbp-88h]
  void *Block[2]; // [rsp+170h] [rbp-68h]
  __int64 v111; // [rsp+180h] [rbp-58h]

  memset_0(v92, 0, 0x80u);
  if ( a3 == (__int64 *)&DxgkControlGuid )
  {
    v8 = *(unsigned __int16 *)(a4 + 40);
    if ( v8 > 0x50 )
      goto LABEL_13;
    if ( v8 == 80 )
    {
      if ( *(_WORD *)(a4 + 86) < 0x28u )
        return 262403;
      v31 = *(_QWORD *)(a4 + 96);
      *(__m128i *)v92 = _mm_unpacklo_epi32(_mm_loadl_epi64((const __m128i *)v31), (__m128i)0LL);
      *(_QWORD *)&v92[16] = *(unsigned int *)(v31 + 8);
      v17 = 0;
      *(_DWORD *)&v92[24] = (*(_DWORD *)(v31 + 12) != 0) | (*(_DWORD *)(v31 + 16) != 0 ? 2 : 0);
      *(_QWORD *)&v92[28] = *(_QWORD *)(v31 + 20);
      *(_DWORD *)&v92[36] = *(_DWORD *)(v31 + 28);
      *(_QWORD *)&v92[40] = *(_QWORD *)(v31 + 32);
      a3 = ETWGUID_DXGKREPORTALLOCATION;
      v15 = &ETWGUID_DXGKCREATEALLOCATION;
      v16 = ETWGUID_DXGKDEVICE;
      v18 = ETWGUID_DXGKOPENALLOCATION;
      goto LABEL_17;
    }
    if ( v8 > 0x25 )
    {
      v23 = v8 - 38;
      if ( v23 )
      {
        v24 = v23 - 15;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( v25 )
          {
            v26 = v25 - 1;
            if ( v26 )
            {
              v27 = v26 - 3;
              if ( v27 )
              {
                if ( v27 != 1 )
                  goto LABEL_13;
                if ( *(_WORD *)(a4 + 86) < 0x28u )
                  return 262403;
                v28 = *(_QWORD *)(a4 + 96);
                *(_DWORD *)v92 = 6;
                v17 = 0;
                *(_DWORD *)&v92[20] = *(_DWORD *)(v28 + 8) != 0;
                *(_QWORD *)&v92[24] = *(unsigned int *)(v28 + 12);
                *(_DWORD *)&v92[32] = *(_DWORD *)(v28 + 16);
                *(_OWORD *)&v92[36] = *(_OWORD *)(v28 + 20);
                v29 = 2 * (*(_DWORD *)(v28 + 36) & 1);
              }
              else
              {
                if ( *(_WORD *)(a4 + 86) < 0x2Cu )
                  return 262403;
                v28 = *(_QWORD *)(a4 + 96);
                *(_DWORD *)v92 = 5;
                v17 = 0;
                *(_DWORD *)&v92[20] = *(_DWORD *)(v28 + 8) != 0;
                *(_QWORD *)&v92[24] = *(unsigned int *)(v28 + 12);
                *(_DWORD *)&v92[32] = *(_DWORD *)(v28 + 16);
                *(_QWORD *)&v92[36] = *(_QWORD *)(v28 + 20);
                *(_QWORD *)&v92[44] = *(_QWORD *)(v28 + 28);
                v29 = *(_DWORD *)(v28 + 36) ^ (*(_DWORD *)(v28 + 36) ^ (2 * *(_DWORD *)(v28 + 40))) & 2;
              }
              *(_DWORD *)&v92[52] = v29;
            }
            else
            {
              if ( *(_WORD *)(a4 + 86) < 0x20u )
                return 262403;
              v28 = *(_QWORD *)(a4 + 96);
              *(_DWORD *)v92 = 2;
              v17 = 0;
              *(_DWORD *)&v92[20] = *(_DWORD *)(v28 + 8) != 0;
              *(_QWORD *)&v92[24] = *(unsigned int *)(v28 + 12);
              *(_DWORD *)&v92[32] = *(_DWORD *)(v28 + 16);
              *(_DWORD *)&v92[36] = *(_DWORD *)(v28 + 20);
              *(_QWORD *)&v92[40] = *(_QWORD *)(v28 + 24);
            }
          }
          else
          {
            if ( *(_WORD *)(a4 + 86) < 0x28u )
              return 262403;
            v28 = *(_QWORD *)(a4 + 96);
            *(_DWORD *)v92 = 1;
            v17 = 0;
            *(_DWORD *)&v92[20] = *(_DWORD *)(v28 + 8) != 0;
            *(_QWORD *)&v92[24] = *(unsigned int *)(v28 + 12);
            *(_QWORD *)&v92[32] = *(_QWORD *)(v28 + 16);
            *(_DWORD *)&v92[40] = *(_DWORD *)(v28 + 24);
            *(_DWORD *)&v92[44] = *(_DWORD *)(v28 + 28);
            *(_QWORD *)&v92[48] = *(_QWORD *)(v28 + 32);
          }
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x38u )
            return 262403;
          v28 = *(_QWORD *)(a4 + 96);
          v17 = 0;
          *(_DWORD *)&v92[20] = *(_DWORD *)(v28 + 8) != 0;
          *(_QWORD *)&v92[24] = *(unsigned int *)(v28 + 12);
          *(_DWORD *)&v92[32] = *(_DWORD *)(v28 + 16);
          *(_QWORD *)&v92[36] = *(_QWORD *)(v28 + 20);
          *(_DWORD *)&v92[44] = *(_DWORD *)(v28 + 28);
          *(_QWORD *)&v92[48] = *(_QWORD *)(v28 + 32);
          v93 = *(_DWORD *)(v28 + 40);
          *(_QWORD *)v94 = *(_QWORD *)(v28 + 44);
          *(_DWORD *)&v94[8] = *(_DWORD *)(v28 + 52);
        }
        *(__m128i *)&v92[4] = _mm_unpacklo_epi32(_mm_loadl_epi64((const __m128i *)v28), (__m128i)0LL);
        a3 = ETWGUID_DXGKPAGINGOPERATION;
        v15 = &ETWGUID_DXGKCREATEALLOCATION;
        v16 = ETWGUID_DXGKDEVICE;
        goto LABEL_16;
      }
    }
    else if ( v8 != 37 )
    {
      v9 = v8 - 27;
      if ( !v9 || (v10 = v9 - 1) == 0 || (v11 = v10 - 1) == 0 )
      {
        if ( *(_WORD *)(a4 + 86) < 0x10u )
          return 262403;
        v22 = *(const __m128i **)(a4 + 96);
        *(__m128i *)v92 = _mm_unpacklo_epi32(_mm_loadl_epi64(v22), (__m128i)0LL);
        *(_DWORD *)&v92[16] = v22->m128i_i32[2];
        *(_QWORD *)&v92[20] = v22->m128i_u32[3];
        v16 = ETWGUID_DXGKDEVICE;
        a3 = ETWGUID_DXGKDEVICE;
        v15 = &ETWGUID_DXGKCREATEALLOCATION;
        goto LABEL_15;
      }
      v12 = v11 - 4;
      if ( !v12 || (v13 = v12 - 1) == 0 || (v14 = v13 - 1) == 0 )
      {
        if ( *(_WORD *)(a4 + 86) < 0x68u )
          return 262403;
        v21 = *(_QWORD *)(a4 + 96);
        *(__m128i *)v92 = _mm_unpacklo_epi32(_mm_loadl_epi64((const __m128i *)v21), (__m128i)0LL);
        *(_QWORD *)&v92[16] = *(unsigned int *)(v21 + 8);
        *(_DWORD *)&v92[24] = *(_DWORD *)(v21 + 12);
        *(_OWORD *)&v92[28] = *(_OWORD *)(v21 + 16);
        *(_DWORD *)&v92[44] = *(_DWORD *)(v21 + 32);
        *(_DWORD *)&v92[48] = *(_DWORD *)(v21 + 36);
        *(_DWORD *)&v92[52] = *(_DWORD *)(v21 + 40);
        v93 = *(_DWORD *)(v21 + 44);
        *(_DWORD *)v94 = *(_DWORD *)(v21 + 48);
        *(__m128i *)&v94[4] = _mm_unpacklo_epi32(_mm_loadl_epi64((const __m128i *)(v21 + 52)), (__m128i)0LL);
        v95 = *(unsigned int *)(v21 + 60);
        v96 = *(_DWORD *)(v21 + 64);
        v97 = *(_DWORD *)(v21 + 68);
        v98 = *(_DWORD *)(v21 + 72);
        v99 = *(_DWORD *)(v21 + 76);
        v100 = *(_DWORD *)(v21 + 80);
        v101 = *(_DWORD *)(v21 + 84);
        v102 = *(_DWORD *)(v21 + 88);
        v103 = *(_DWORD *)(v21 + 92);
        v104 = *(_DWORD *)(v21 + 96);
        v105 = *(_DWORD *)(v21 + 100);
        v15 = &ETWGUID_DXGKCREATEALLOCATION;
        a3 = (__int64 *)&ETWGUID_DXGKCREATEALLOCATION;
        goto LABEL_14;
      }
      if ( v14 != 1 )
      {
LABEL_13:
        v15 = &ETWGUID_DXGKCREATEALLOCATION;
LABEL_14:
        v16 = ETWGUID_DXGKDEVICE;
LABEL_15:
        v17 = 0;
LABEL_16:
        v18 = ETWGUID_DXGKOPENALLOCATION;
LABEL_17:
        v19 = 1;
        goto LABEL_54;
      }
    }
    if ( *(_WORD *)(a4 + 86) < 0x28u )
      return 262403;
    v30 = *(_QWORD *)(a4 + 96);
    *(__m128i *)v92 = _mm_unpacklo_epi32(_mm_loadl_epi64((const __m128i *)v30), (__m128i)0LL);
    *(__m128i *)&v92[16] = _mm_unpacklo_epi32(_mm_loadl_epi64((const __m128i *)(v30 + 8)), (__m128i)0LL);
    *(__m128i *)&v92[32] = _mm_unpacklo_epi32(_mm_loadl_epi64((const __m128i *)(v30 + 16)), (__m128i)0LL);
    *(_QWORD *)&v92[48] = *(unsigned int *)(v30 + 24);
    v93 = *(_DWORD *)(v30 + 28);
    *(_DWORD *)v94 = *(_DWORD *)(v30 + 32);
    *(_QWORD *)&v94[4] = *(unsigned int *)(v30 + 36);
    v18 = ETWGUID_DXGKOPENALLOCATION;
    a3 = ETWGUID_DXGKOPENALLOCATION;
    v15 = &ETWGUID_DXGKCREATEALLOCATION;
    v16 = ETWGUID_DXGKDEVICE;
    v17 = 0;
    goto LABEL_17;
  }
  v17 = 0;
  v19 = 0;
  v15 = &ETWGUID_DXGKCREATEALLOCATION;
  v16 = ETWGUID_DXGKDEVICE;
  v18 = ETWGUID_DXGKOPENALLOCATION;
LABEL_54:
  if ( a3 == ETWGUID_DXGKDEVICE )
  {
    if ( v19 )
    {
      v32 = v92;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x1Cu )
        return 262403;
      v32 = *(_BYTE **)(a4 + 96);
    }
    if ( a2
      || !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
            (char *)this + 80,
            v32 + 20,
            ETWGUID_DXGKOPENALLOCATION,
            &ETWGUID_DXGKCREATEALLOCATION) )
    {
      v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, const struct _GUID *))(**((_QWORD **)this + 24) + 32LL))(
              *((_QWORD *)this + 24),
              *((_QWORD *)v32 + 1),
              v18,
              v15);
      *(_BYTE *)std::map<unsigned __int64,unsigned char>::operator[]((int)this + 80) = v33;
    }
    return 0;
  }
  if ( a3 == (__int64 *)&ETWGUID_DXGKCREATEALLOCATION )
  {
    if ( *(_BYTE *)(a4 + 45) == 3 )
    {
      if ( a2 )
        return 0;
    }
    else if ( !a2 )
    {
      return 262400;
    }
    if ( v19 )
    {
      v34 = (unsigned int *)v92;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x80u )
        return 262403;
      v34 = *(unsigned int **)(a4 + 96);
    }
    if ( *((_QWORD *)v34 + 8) != v34[16] )
      *((_BYTE *)this + 168) = 1;
    LOBYTE(v16) = *(_BYTE *)(a4 + 45);
    if ( (((_BYTE)v16 - 1) & 0xFD) != 0 )
    {
      if ( (_BYTE)v16 == 2 )
      {
        v90 = XPerfCore::TimeStamp::Max;
        v35 = (XPerfAddIn::CAllocationInfoSource::CAllocation *)*((_QWORD *)v34 + 8);
        v86 = v35;
        v36 = XPerfAddIn::CAllocationInfoSource::QueryAllocationByHandle<unsigned __int64,XPerfAddIn::CAllocationInfoSource::CAllocation *>(
                v16,
                &v86,
                &v90,
                (char *)this + 120);
        if ( !v36 )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            (char *)this + 32,
            a2,
            L"destroying never-created allocation with global handle %lld",
            v35);
          return 0;
        }
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v90);
        *(_QWORD *)(v36 + 8) = v90;
      }
    }
    else
    {
      if ( 0xF0F0F0F0F0F0F0F1uLL * ((__int64)(*((_QWORD *)this + 13) - *((_QWORD *)this + 12)) >> 3) >= 0xF0F0F0F0F0F0F0F1uLL * ((__int64)(*((_QWORD *)this + 14) - *((_QWORD *)this + 12)) >> 3) )
        return 2147549183LL;
      memset_0(v106, 0, 0x88u);
      v106[0] = XPerfCore::TimeStamp::Min;
      v106[1] = XPerfCore::TimeStamp::Max;
      v106[5] = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v108 = _mm_load_si128((const __m128i *)&_xmm);
      v109 = 0;
      *(_OWORD *)Block = 0;
      v111 = 0;
      std::vector<XPerfAddIn::CAllocationInfoSource::CAllocation>::push_back((char *)this + 96, v106);
      if ( Block[0] )
        operator delete(Block[0]);
      v37 = *((_QWORD *)this + 13) - 136LL;
      v87 = v37;
      if ( *(_BYTE *)(a4 + 45) == 1 )
      {
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v90);
        v38 = v90;
      }
      else
      {
        v38 = XPerfCore::TimeStamp::Min;
      }
      *(_QWORD *)v37 = v38;
      *(_QWORD *)(v37 + 8) = XPerfCore::TimeStamp::Max;
      *(_QWORD *)(v37 + 16) = *((_QWORD *)v34 + 8);
      *(_QWORD *)(v37 + 24) = *(_QWORD *)(v34 + 7);
      *(_QWORD *)(v37 + 32) = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 22)
                                                                                         + 32LL))(
                                *((_QWORD *)this + 22),
                                v37,
                                *v34,
                                0);
      *(_DWORD *)(v37 + 88) = v34[24];
      *(_DWORD *)(v37 + 92) = v34[27];
      *(_DWORD *)(v37 + 96) = v34[28];
      *(_DWORD *)(v37 + 100) = v34[6];
      *(_DWORD *)(v37 + 104) = v34[23];
      *(_BYTE *)(v37 + 108) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 24) + 32LL))(
                                *((_QWORD *)this + 24),
                                *((_QWORD *)v34 + 2));
      if ( v34[23] && ((*((_BYTE *)v34 + 92) ^ (unsigned __int8)(v34[6] >> 6)) & 2) != 0 )
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"Allocation %lld is both swizzled and not swizzled",
          *((_QWORD *)v34 + 8));
      v39 = v34[12];
      if ( v39 )
      {
        LODWORD(v86) = v34[12];
        std::_Tree<std::_Tmap_traits<unsigned long,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>::find(
          (char *)this + 152,
          &v90,
          &v86);
        if ( v90 == *((_QWORD *)this + 19) )
        {
          LODWORD(v86) = v39;
          v40 = (_QWORD *)std::map<unsigned long,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>::operator[](
                            (char *)this + 152,
                            &v86);
          std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>::resize(v40);
          while ( v17 < 5 )
          {
            v41 = 6 * v17;
            v42 = (v34[12] >> (6 * v17 + 5)) & 1;
            v43 = v34[12] >> (6 * v17);
            LOBYTE(v43) = v43 & 0x1F;
            LOBYTE(v41) = *(_BYTE *)(v37 + 108);
            v44 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 24) + 40LL))(
                    *((_QWORD *)this + 24),
                    v41,
                    v43);
            v45 = 2 * v17;
            *(_QWORD *)(*v40 + 8 * v45) = v44;
            *(_DWORD *)(*v40 + 8 * v45 + 8) = v42;
            ++v17;
          }
          v46 = v40;
        }
        else
        {
          v46 = (_QWORD *)(v90 + 40);
        }
        v47 = XPerfCore::adapter_from_vector<XPerfAddIn::DX::Warning,XPerfAddIn::DX::Warning>(&v90, v46);
        v48 = *(_QWORD *)(v47 + 16);
        *(_OWORD *)(v37 + 40) = *(_OWORD *)v47;
        *(_QWORD *)(v37 + 56) = v48;
      }
      else
      {
        *(_QWORD *)(v37 + 40) = 0;
        *(_QWORD *)(v37 + 48) = 16;
        *(_QWORD *)(v37 + 56) = 0;
      }
      *(_WORD *)(v37 + 109) = 0;
      *(_BYTE *)(v37 + 111) = 0;
      v49 = std::map<unsigned __int64,std::vector<XPerfAddIn::CAllocationInfoSource::CAllocation *>>::operator[](
              (char *)this + 120,
              v37 + 16);
      std::vector<XPerfAddIn::DX::IAllocationInfoSource::Allocation const *>::push_back(v49, &v87);
    }
    return 0;
  }
  if ( a3 == ETWGUID_DXGKOPENALLOCATION )
  {
    if ( *(_BYTE *)(a4 + 45) == 3 )
    {
      if ( a2 )
        return 0;
    }
    else if ( !a2 )
    {
      return 262400;
    }
    if ( v19 )
    {
      v50 = v92;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x48u )
        return 262403;
      v50 = *(_QWORD **)(a4 + 96);
    }
    if ( v50[3] != *((_DWORD *)v50 + 6) )
      *((_BYTE *)this + 168) = 1;
    v87 = v50[3];
    LODWORD(v88) = *(_DWORD *)v50;
    v51 = (_QWORD *)std::map<std::pair<unsigned __int64,unsigned long>,std::vector<XPerfAddIn::CAllocationInfoSource::Assignment>>::operator[](
                      (char *)this + 136,
                      &v87,
                      ETWGUID_DXGKOPENALLOCATION,
                      &ETWGUID_DXGKCREATEALLOCATION);
    v52 = v51;
    LOBYTE(v53) = *(_BYTE *)(a4 + 45) - 1;
    if ( (v53 & 0xFD) != 0 )
    {
      v54 = v51[1];
      if ( v54 == *v51 )
      {
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"closing never-opened allocation (%lld)",
          v50[3]);
        return 0;
      }
      if ( *(_QWORD *)(v54 - 16) != XPerfCore::TimeStamp::Max )
      {
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"closing already-closed allocation");
        return 0;
      }
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v87);
      *(_QWORD *)(v52[1] - 16LL) = v87;
    }
    else
    {
      v55 = XPerfCore::TimeStamp::Max;
      v87 = XPerfCore::TimeStamp::Max;
      v90 = v50[4];
      v56 = XPerfAddIn::CAllocationInfoSource::QueryAllocationByHandle<unsigned __int64,XPerfAddIn::CAllocationInfoSource::CAllocation *>(
              v53,
              &v90,
              &v87,
              (char *)this + 120);
      v57 = v56;
      v58 = v52[1];
      if ( v58 != *v52 && *(_QWORD *)(v58 - 16) == v55 )
      {
        if ( v56 == *(_QWORD *)(v58 - 8) )
          return 0;
        v59 = (__int64)((unsigned __int128)(*(__int64 *)(v58 - 24) * (__int128)0x20C49BA5E353F7CFLL) >> 64) >> 7;
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"opening already open local handle %lld (previously open at %lld) by PID %lld -- autoclosing",
          v50[3],
          (v59 >> 63) + v59,
          *v50);
        if ( a2 )
        {
          XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v87);
          v60 = v87;
        }
        else
        {
          v60 = XPerfCore::TimeStamp::Min;
        }
        *(_QWORD *)(v52[1] - 16LL) = v60;
        v55 = XPerfCore::TimeStamp::Max;
      }
      v89 = 0;
      v87 = XPerfCore::TimeStamp::Min;
      v88 = v55;
      std::vector<XPerfAddIn::CAutoLeaf<XPerfAddIn::ISuspendInfoSource::DriverRecord>>::push_back(v52, &v87);
      if ( a2 )
      {
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v87);
        v61 = v87;
      }
      else
      {
        v61 = XPerfCore::TimeStamp::Min;
      }
      *(_QWORD *)(v52[1] - 24LL) = v61;
      *(_QWORD *)(v52[1] - 16LL) = XPerfCore::TimeStamp::Max;
      *(_QWORD *)(v52[1] - 8LL) = v57;
      if ( !*(_QWORD *)(v52[1] - 8LL) )
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"opening nonexistent target %lld (as %lld by %lld)",
          v50[4],
          v50[3],
          *v50);
    }
    return 0;
  }
  if ( a3 == ETWGUID_DXGKREPORTALLOCATION )
  {
    if ( v19 )
    {
      v62 = v92;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x30u )
        return 262403;
      v62 = *(_BYTE **)(a4 + 96);
    }
    v87 = XPerfCore::TimeStamp::Max;
    v63 = *((_QWORD *)v62 + 2);
    v90 = v63;
    v91 = *(_DWORD *)v62;
    v64 = (XPerfAddIn::CAllocationInfoSource::CAllocation *)XPerfAddIn::CAllocationInfoSource::QueryAllocationByHandle<std::pair<unsigned __int64,unsigned long>,XPerfAddIn::CAllocationInfoSource::Assignment>(
                                                              ETWGUID_DXGKDEVICE,
                                                              &v90,
                                                              &v87,
                                                              (char *)this + 136);
    if ( !v64 )
    {
      XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
        (char *)this + 32,
        a2,
        L"report made for unknown local handle %lld",
        v63);
      return 0;
    }
    v65 = (_BYTE *)std::map<unsigned __int64,unsigned char>::operator[]((int)this + 80);
    v67 = v65;
    if ( !*v65 )
    {
      v68 = *((_QWORD *)v62 + 1);
      v69 = _acrt_iob_func(2u);
      fprintf(v69, "ERROR: no adapter for device %lld", v68);
      return 262400;
    }
    LOBYTE(v66) = v62[36];
    LOBYTE(v67) = *v65;
    v70 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)this + 24) + 40LL))(
            *((_QWORD *)this + 24),
            v67,
            v66);
    if ( !v70 )
    {
      XPerfAddIn::CAllocationInfoSource::reportBadSegmentId(0, *((_DWORD *)v62 + 9), L"allocation report", a2);
      return 262400;
    }
    v87 = *(_QWORD *)v64;
    v89 = v70;
    v88 = *((_QWORD *)v62 + 5);
    XPerfAddIn::CAllocationInfoSource::CAllocation::insertPlacement(
      v64,
      (const struct XPerfAddIn::DX::IAllocationInfoSource::SegmentPlacement *)&v87);
    return 0;
  }
  if ( a3 != ETWGUID_DXGKPAGINGOPERATION )
    return 0;
  if ( !a2 )
    return 262400;
  if ( v19 )
  {
    v71 = (unsigned int *)v92;
  }
  else
  {
    if ( *(_WORD *)(a4 + 86) < 0x50u )
      return 262403;
    v71 = *(unsigned int **)(a4 + 96);
  }
  if ( v71[5] )
    return 262400;
  v72 = 0;
  v90 = 0;
  v73 = *v71;
  if ( !(_DWORD)v73 )
  {
    v72 = v71[14];
    v90 = *(_QWORD *)(v71 + 15);
    goto LABEL_166;
  }
  v73 = (unsigned int)(v73 - 1);
  if ( !(_DWORD)v73 )
  {
    v72 = v71[11];
    v74 = *((_QWORD *)v71 + 6);
    goto LABEL_164;
  }
  v73 = (unsigned int)(v73 - 1);
  if ( !(_DWORD)v73 )
    goto LABEL_166;
  v73 = (unsigned int)(v73 - 3);
  if ( !(_DWORD)v73 )
  {
    v72 = v71[8];
    v74 = *((_QWORD *)this + 27) * *(_QWORD *)(v71 + 9);
LABEL_164:
    v90 = v74;
    goto LABEL_166;
  }
  if ( (_DWORD)v73 != 1 )
  {
    XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
      (char *)this + 32,
      a2,
      L"unhandled pagingOperation %d maybe for %lld",
      *v71,
      *((_QWORD *)v71 + 3));
    return 262400;
  }
LABEL_166:
  v75 = (XPerfAddIn::CAllocationInfoSource::CAllocation *)*((_QWORD *)v71 + 3);
  v87 = XPerfCore::TimeStamp::Max;
  v86 = v75;
  v76 = (XPerfAddIn::CAllocationInfoSource::CAllocation *)XPerfAddIn::CAllocationInfoSource::QueryAllocationByHandle<unsigned __int64,XPerfAddIn::CAllocationInfoSource::CAllocation *>(
                                                            v73,
                                                            &v86,
                                                            &v87,
                                                            (char *)this + 120);
  v86 = v76;
  if ( !v76 )
  {
    XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
      (char *)this + 32,
      a2,
      L"paging operation on unknown global handle %lld",
      v75);
    return 262400;
  }
  Segment = XPerfAddIn::CAllocationInfoSource::getSegment(this, *(_QWORD *)(v71 + 1), v72);
  v78 = *((_QWORD *)v76 + 15);
  if ( v78 == *((_QWORD *)v76 + 14) )
    v79 = 0;
  else
    v79 = *(const struct XPerfAddIn::DX::ISegmentInfoSource::Segment **)(v78 - 8);
  if ( !*v71 )
  {
    v81 = XPerfAddIn::CAllocationInfoSource::getSegment(this, *(_QWORD *)(v71 + 1), *((_BYTE *)v71 + 44));
    if ( v79 != v81 )
    {
      if ( v81 )
      {
        v82 = *((unsigned __int8 *)v81 + 12);
        v83 = *((unsigned __int8 *)v81 + 13);
        v84 = -1;
      }
      else
      {
        v84 = -1;
        v82 = -1;
        v83 = -1;
      }
      if ( v79 )
      {
        v84 = *((unsigned __int8 *)v79 + 12);
        v85 = *((unsigned __int8 *)v79 + 13);
      }
      else
      {
        v85 = -1;
      }
      v80 = v86;
      XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
        (char *)this + 32,
        a2,
        L"alloc %lld which was in %d/%d moved from %d/%d",
        *((_QWORD *)v86 + 2),
        v84,
        v85,
        v82,
        v83);
      goto LABEL_185;
    }
    goto LABEL_184;
  }
  if ( *v71 != 1 )
  {
    if ( *v71 == 5 )
    {
      if ( v79 )
        return 0;
      if ( !Segment )
      {
        XPerfAddIn::CAllocationInfoSource::reportBadSegmentId(
          (XPerfAddIn::CAllocationInfoSource *)(*v71 - 5),
          v72,
          L"Aperture Mapping",
          a2);
        return 262400;
      }
      if ( (*((_BYTE *)Segment + 8) & 1) == 0 )
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"aperture-mapping to segment %d/%d which is not aperture",
          *((unsigned __int8 *)Segment + 12),
          *((unsigned __int8 *)Segment + 13));
    }
    else if ( *v71 == 6 && (!v79 || (*((_BYTE *)v79 + 8) & 1) == 0) )
    {
      return 262400;
    }
    goto LABEL_184;
  }
  if ( Segment )
  {
LABEL_184:
    v80 = v86;
LABEL_185:
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v87);
    v89 = (__int64)Segment;
    v88 = v90;
    XPerfAddIn::CAllocationInfoSource::CAllocation::pushBackPlacement(
      v80,
      (const struct XPerfAddIn::DX::IAllocationInfoSource::SegmentPlacement *)&v87);
    return 0;
  }
  XPerfAddIn::CAllocationInfoSource::reportBadSegmentId(
    (XPerfAddIn::CAllocationInfoSource *)(*v71 - 1),
    v72,
    L"Paging Fill Operation",
    a2);
  return 262400;
}

```

## disassembly

```asm
0x18004b898  push    rbx
0x18004b89a  push    rsi
0x18004b89b  push    rdi
0x18004b89c  push    r12
0x18004b89e  push    r13
0x18004b8a0  push    r14
0x18004b8a2  push    r15
0x18004b8a4  sub     rsp, 1A0h
0x18004b8ab  mov     rax, cs:__security_cookie
0x18004b8b2  xor     rax, rsp
0x18004b8b5  mov     [rsp+1D8h+var_48], rax
0x18004b8bd  mov     rbx, r9
0x18004b8c0  mov     r15, r8
0x18004b8c3  mov     r14, rdx
0x18004b8c6  mov     rsi, rcx
0x18004b8c9  mov     r12d, 80h
0x18004b8cf  mov     r8d, r12d; Size
0x18004b8d2  xor     edx, edx; Val
0x18004b8d4  lea     rcx, [rsp+1D8h+var_158]; void *
0x18004b8dc  call    memset_0
0x18004b8e1  lea     rax, DxgkControlGuid
0x18004b8e8  lea     r11d, [r12-30h]
0x18004b8ed  cmp     r15, rax
0x18004b8f0  jnz     loc_18004BED4
0x18004b8f6  movzx   ecx, word ptr [rbx+28h]
0x18004b8fa  cmp     ecx, r11d
0x18004b8fd  ja      short loc_18004B947
0x18004b8ff  jz      loc_18004BE32
0x18004b905  cmp     ecx, 25h ; '%'
0x18004b908  ja      loc_18004BAF4
0x18004b90e  jz      loc_18004BD8F
0x18004b914  sub     ecx, 1Bh
0x18004b917  jz      loc_18004BA9A
0x18004b91d  sub     ecx, 1
0x18004b920  jz      loc_18004BA9A
0x18004b926  sub     ecx, 1
0x18004b929  jz      loc_18004BA9A
0x18004b92f  sub     ecx, 4
0x18004b932  jz      short loc_18004B97A
0x18004b934  sub     ecx, 1
0x18004b937  jz      short loc_18004B97A
0x18004b939  sub     ecx, 1
0x18004b93c  jz      short loc_18004B97A
0x18004b93e  cmp     ecx, 1
0x18004b941  jz      loc_18004BD8F
0x18004b947  lea     r9, ETWGUID_DXGKCREATEALLOCATION
0x18004b94e  lea     rcx, ETWGUID_DXGKDEVICE
0x18004b955  mov     r13d, 10h
0x18004b95b  xor     edi, edi
0x18004b95d  lea     rax, ETWGUID_DXGKPAGINGOPERATION
0x18004b964  lea     r8, ETWGUID_DXGKOPENALLOCATION
0x18004b96b  lea     rdx, ETWGUID_DXGKREPORTALLOCATION
0x18004b972  mov     r10b, 1
0x18004b975  jmp     loc_18004BF00
0x18004b97a  cmp     word ptr [rbx+56h], 68h ; 'h'
0x18004b97f  jnb     short loc_18004B98B
0x18004b981  mov     eax, 40103h
0x18004b986  jmp     loc_18004C94C
0x18004b98b  mov     rcx, [rbx+60h]
0x18004b98f  movq    xmm1, qword ptr [rcx]
0x18004b993  xorps   xmm0, xmm0
0x18004b996  punpckldq xmm1, xmm0
0x18004b99a  movdqa  [rsp+1D8h+var_158], xmm1
0x18004b9a3  mov     eax, [rcx+8]
0x18004b9a6  mov     qword ptr [rsp+1D8h+var_148], rax
0x18004b9ae  mov     eax, [rcx+0Ch]
0x18004b9b1  mov     dword ptr [rsp+1D8h+var_148+8], eax
0x18004b9b8  mov     rax, [rcx+10h]
0x18004b9bc  mov     qword ptr [rsp+1D8h+var_148+0Ch], rax
0x18004b9c4  mov     eax, [rcx+18h]
0x18004b9c7  mov     dword ptr [rsp+1D8h+var_138+4], eax
0x18004b9ce  mov     eax, [rcx+1Ch]
0x18004b9d1  mov     dword ptr [rsp+1D8h+var_138+8], eax
0x18004b9d8  mov     eax, [rcx+20h]
0x18004b9db  mov     dword ptr [rsp+1D8h+var_138+0Ch], eax
0x18004b9e2  mov     eax, [rcx+24h]
0x18004b9e5  mov     dword ptr [rsp+1D8h+var_138+10h], eax
0x18004b9ec  mov     eax, [rcx+28h]
0x18004b9ef  mov     [rsp+1D8h+var_124], eax
0x18004b9f6  mov     eax, [rcx+2Ch]
0x18004b9f9  mov     [rsp+1D8h+var_120], eax
0x18004ba00  mov     eax, [rcx+30h]
0x18004ba03  mov     dword ptr [rsp+1D8h+var_11C], eax
0x18004ba0a  movq    xmm1, qword ptr [rcx+34h]
0x18004ba0f  punpckldq xmm1, xmm0
0x18004ba13  movdqa  xmmword ptr [rsp+1D8h+var_11C+4], xmm1
0x18004ba1c  mov     eax, [rcx+3Ch]
0x18004ba1f  mov     [rsp+1D8h+var_108], rax
0x18004ba27  mov     eax, [rcx+40h]
0x18004ba2a  mov     [rsp+1D8h+var_100], eax
0x18004ba31  mov     eax, [rcx+44h]
0x18004ba34  mov     [rsp+1D8h+var_FC], eax
0x18004ba3b  mov     eax, [rcx+48h]
0x18004ba3e  mov     [rsp+1D8h+var_F8], eax
0x18004ba45  mov     eax, [rcx+4Ch]
0x18004ba48  mov     [rsp+1D8h+var_F4], eax
0x18004ba4f  mov     eax, [rcx+50h]
0x18004ba52  mov     [rsp+1D8h+var_F0], eax
0x18004ba59  mov     eax, [rcx+54h]
0x18004ba5c  mov     [rsp+1D8h+var_EC], eax
0x18004ba63  mov     eax, [rcx+58h]
0x18004ba66  mov     [rsp+1D8h+var_E8], eax
0x18004ba6d  mov     eax, [rcx+5Ch]
0x18004ba70  mov     [rsp+1D8h+var_E4], eax
0x18004ba77  mov     eax, [rcx+60h]
0x18004ba7a  mov     [rsp+1D8h+var_E0], eax
0x18004ba81  mov     eax, [rcx+64h]
0x18004ba84  mov     [rsp+1D8h+var_DC], eax
0x18004ba8b  lea     r9, ETWGUID_DXGKCREATEALLOCATION
0x18004ba92  mov     r15, r9
0x18004ba95  jmp     loc_18004B94E
0x18004ba9a  mov     r13d, 10h
0x18004baa0  cmp     [rbx+56h], r13w
0x18004baa5  jnb     short loc_18004BAB1
0x18004baa7  mov     eax, 40103h
0x18004baac  jmp     loc_18004C94C
0x18004bab1  mov     rcx, [rbx+60h]
0x18004bab5  movq    xmm1, qword ptr [rcx]
0x18004bab9  xorps   xmm0, xmm0
0x18004babc  punpckldq xmm1, xmm0
0x18004bac0  movdqa  [rsp+1D8h+var_158], xmm1
0x18004bac9  mov     eax, [rcx+8]
0x18004bacc  mov     dword ptr [rsp+1D8h+var_148], eax
0x18004bad3  mov     eax, [rcx+0Ch]
0x18004bad6  mov     qword ptr [rsp+1D8h+var_148+4], rax
0x18004bade  lea     rcx, ETWGUID_DXGKDEVICE
0x18004bae5  mov     r15, rcx
0x18004bae8  lea     r9, ETWGUID_DXGKCREATEALLOCATION
0x18004baef  jmp     loc_18004B95B
0x18004baf4  sub     ecx, 26h ; '&'
0x18004baf7  jz      loc_18004BD8F
0x18004bafd  sub     ecx, 0Fh
0x18004bb00  jz      loc_18004BD0D
0x18004bb06  sub     ecx, 1
0x18004bb09  jz      loc_18004BCA0
0x18004bb0f  sub     ecx, 1
0x18004bb12  jz      loc_18004BC3F
0x18004bb18  sub     ecx, 3
0x18004bb1b  jz      loc_18004BBCE
0x18004bb21  cmp     ecx, 1
0x18004bb24  jnz     loc_18004B947
0x18004bb2a  cmp     word ptr [rbx+56h], 28h ; '('
0x18004bb2f  jnb     short loc_18004BB3B
0x18004bb31  mov     eax, 40103h
0x18004bb36  jmp     loc_18004C94C
0x18004bb3b  mov     rcx, [rbx+60h]
0x18004bb3f  mov     dword ptr [rsp+1D8h+var_158], 6
0x18004bb4a  xor     edi, edi
0x18004bb4c  mov     eax, edi
0x18004bb4e  cmp     [rcx+8], edi
0x18004bb51  setnz   al
0x18004bb54  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004bb5b  mov     eax, [rcx+0Ch]
0x18004bb5e  mov     qword ptr [rsp+1D8h+var_148+8], rax
0x18004bb66  mov     eax, [rcx+10h]
0x18004bb69  mov     dword ptr [rsp+1D8h+var_138], eax
0x18004bb70  mov     rax, [rcx+14h]
0x18004bb74  mov     qword ptr [rsp+1D8h+var_138+4], rax
0x18004bb7c  mov     rax, [rcx+1Ch]
0x18004bb80  mov     qword ptr [rsp+1D8h+var_138+0Ch], rax
0x18004bb88  mov     eax, [rcx+24h]
0x18004bb8b  and     eax, 1
0x18004bb8e  add     eax, eax
0x18004bb90  mov     [rsp+1D8h+var_124], eax
0x18004bb97  xorps   xmm0, xmm0
0x18004bb9a  movq    xmm1, qword ptr [rcx]
0x18004bb9e  punpckldq xmm1, xmm0
0x18004bba2  movdqu  [rsp+1D8h+var_158+4], xmm1
0x18004bbab  lea     rax, ETWGUID_DXGKPAGINGOPERATION
0x18004bbb2  mov     r15, rax
0x18004bbb5  lea     r9, ETWGUID_DXGKCREATEALLOCATION
0x18004bbbc  mov     r13d, 10h
0x18004bbc2  lea     rcx, ETWGUID_DXGKDEVICE
0x18004bbc9  jmp     loc_18004B964
0x18004bbce  cmp     word ptr [rbx+56h], 2Ch ; ','
0x18004bbd3  jnb     short loc_18004BBDF
0x18004bbd5  mov     eax, 40103h
0x18004bbda  jmp     loc_18004C94C
0x18004bbdf  mov     rcx, [rbx+60h]
0x18004bbe3  mov     dword ptr [rsp+1D8h+var_158], 5
0x18004bbee  xor     edi, edi
0x18004bbf0  mov     eax, edi
0x18004bbf2  cmp     [rcx+8], edi
0x18004bbf5  setnz   al
0x18004bbf8  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004bbff  mov     eax, [rcx+0Ch]
0x18004bc02  mov     qword ptr [rsp+1D8h+var_148+8], rax
0x18004bc0a  mov     eax, [rcx+10h]
0x18004bc0d  mov     dword ptr [rsp+1D8h+var_138], eax
0x18004bc14  mov     rax, [rcx+14h]
0x18004bc18  mov     qword ptr [rsp+1D8h+var_138+4], rax
0x18004bc20  mov     rax, [rcx+1Ch]
0x18004bc24  mov     qword ptr [rsp+1D8h+var_138+0Ch], rax
0x18004bc2c  mov     eax, [rcx+28h]
0x18004bc2f  add     eax, eax
0x18004bc31  xor     eax, [rcx+24h]
0x18004bc34  and     eax, 2
0x18004bc37  xor     eax, [rcx+24h]
0x18004bc3a  jmp     loc_18004BB90
0x18004bc3f  cmp     word ptr [rbx+56h], 20h ; ' '
0x18004bc44  jnb     short loc_18004BC50
0x18004bc46  mov     eax, 40103h
0x18004bc4b  jmp     loc_18004C94C
0x18004bc50  mov     rcx, [rbx+60h]
0x18004bc54  mov     dword ptr [rsp+1D8h+var_158], 2
0x18004bc5f  xor     edi, edi
0x18004bc61  mov     eax, edi
0x18004bc63  cmp     [rcx+8], edi
0x18004bc66  setnz   al
0x18004bc69  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004bc70  mov     eax, [rcx+0Ch]
0x18004bc73  mov     qword ptr [rsp+1D8h+var_148+8], rax
0x18004bc7b  mov     eax, [rcx+10h]
0x18004bc7e  mov     dword ptr [rsp+1D8h+var_138], eax
0x18004bc85  mov     eax, [rcx+14h]
0x18004bc88  mov     dword ptr [rsp+1D8h+var_138+4], eax
0x18004bc8f  mov     rax, [rcx+18h]
0x18004bc93  mov     qword ptr [rsp+1D8h+var_138+8], rax
0x18004bc9b  jmp     loc_18004BB97
0x18004bca0  cmp     word ptr [rbx+56h], 28h ; '('
0x18004bca5  jnb     short loc_18004BCB1
0x18004bca7  mov     eax, 40103h
0x18004bcac  jmp     loc_18004C94C
0x18004bcb1  mov     rcx, [rbx+60h]
0x18004bcb5  mov     dword ptr [rsp+1D8h+var_158], 1
0x18004bcc0  xor     edi, edi
0x18004bcc2  mov     eax, edi
0x18004bcc4  cmp     [rcx+8], edi
0x18004bcc7  setnz   al
0x18004bcca  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004bcd1  mov     eax, [rcx+0Ch]
0x18004bcd4  mov     qword ptr [rsp+1D8h+var_148+8], rax
0x18004bcdc  mov     rax, [rcx+10h]
0x18004bce0  mov     qword ptr [rsp+1D8h+var_138], rax
0x18004bce8  mov     eax, [rcx+18h]
0x18004bceb  mov     dword ptr [rsp+1D8h+var_138+8], eax
0x18004bcf2  mov     eax, [rcx+1Ch]
0x18004bcf5  mov     dword ptr [rsp+1D8h+var_138+0Ch], eax
0x18004bcfc  mov     rax, [rcx+20h]
0x18004bd00  mov     qword ptr [rsp+1D8h+var_138+10h], rax
0x18004bd08  jmp     loc_18004BB97
0x18004bd0d  cmp     word ptr [rbx+56h], 38h ; '8'
0x18004bd12  jnb     short loc_18004BD1E
0x18004bd14  mov     eax, 40103h
0x18004bd19  jmp     loc_18004C94C
0x18004bd1e  mov     rcx, [rbx+60h]
0x18004bd22  xor     edi, edi
0x18004bd24  mov     eax, edi
0x18004bd26  cmp     [rcx+8], edi
0x18004bd29  setnz   al
0x18004bd2c  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004bd33  mov     eax, [rcx+0Ch]
0x18004bd36  mov     qword ptr [rsp+1D8h+var_148+8], rax
0x18004bd3e  mov     eax, [rcx+10h]
0x18004bd41  mov     dword ptr [rsp+1D8h+var_138], eax
0x18004bd48  mov     rax, [rcx+14h]
0x18004bd4c  mov     qword ptr [rsp+1D8h+var_138+4], rax
0x18004bd54  mov     eax, [rcx+1Ch]
0x18004bd57  mov     dword ptr [rsp+1D8h+var_138+0Ch], eax
0x18004bd5e  mov     rax, [rcx+20h]
0x18004bd62  mov     qword ptr [rsp+1D8h+var_138+10h], rax
0x18004bd6a  mov     eax, [rcx+28h]
0x18004bd6d  mov     [rsp+1D8h+var_120], eax
0x18004bd74  mov     rax, [rcx+2Ch]
0x18004bd78  mov     [rsp+1D8h+var_11C], rax
0x18004bd80  mov     eax, [rcx+34h]
0x18004bd83  mov     [rsp+1D8h+var_114], eax
0x18004bd8a  jmp     loc_18004BB97
0x18004bd8f  cmp     word ptr [rbx+56h], 28h ; '('
0x18004bd94  jnb     short loc_18004BDA0
0x18004bd96  mov     eax, 40103h
0x18004bd9b  jmp     loc_18004C94C
0x18004bda0  mov     rcx, [rbx+60h]
0x18004bda4  movq    xmm1, qword ptr [rcx]
0x18004bda8  xorps   xmm0, xmm0
0x18004bdab  punpckldq xmm1, xmm0
0x18004bdaf  movdqa  [rsp+1D8h+var_158], xmm1
0x18004bdb8  movq    xmm2, qword ptr [rcx+8]
0x18004bdbd  punpckldq xmm2, xmm0
0x18004bdc1  movdqa  [rsp+1D8h+var_148], xmm2
0x18004bdca  movq    xmm1, qword ptr [rcx+10h]
0x18004bdcf  punpckldq xmm1, xmm0
0x18004bdd3  movdqa  xmmword ptr [rsp+1D8h+var_138], xmm1
0x18004bddc  mov     eax, [rcx+18h]
0x18004bddf  mov     [rsp+0B0h], rax
0x18004bde7  mov     eax, [rcx+1Ch]
0x18004bdea  mov     [rsp+1D8h+var_120], eax
0x18004bdf1  mov     eax, [rcx+20h]
0x18004bdf4  mov     dword ptr [rsp+1D8h+var_11C], eax
0x18004bdfb  mov     eax, [rcx+24h]
0x18004bdfe  mov     [rsp+1D8h+var_11C+4], rax
0x18004be06  lea     r8, ETWGUID_DXGKOPENALLOCATION
0x18004be0d  mov     r15, r8
0x18004be10  lea     r9, ETWGUID_DXGKCREATEALLOCATION
0x18004be17  mov     r13d, 10h
0x18004be1d  lea     rcx, ETWGUID_DXGKDEVICE
0x18004be24  xor     edi, edi
0x18004be26  lea     rax, ETWGUID_DXGKPAGINGOPERATION
0x18004be2d  jmp     loc_18004B96B
0x18004be32  cmp     word ptr [rbx+56h], 28h ; '('
  ... truncated ...
```

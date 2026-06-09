# XPerfAddIn::CAllocationInfoSource::RealOnEvent<unsigned __int64>(XPerfCore::ICursor const *,_GUID const *,_EVENT_RECORD const *)

- ea: `0x18004c978`
- end: `0x18004dabc`
- name: `??$RealOnEvent@_K@CAllocationInfoSource@XPerfAddIn@@QEAAJPEBUICursor@XPerfCore@@PEBU_GUID@@PEBU_EVENT_RECORD@@@Z`
- size: `4420`
- prototype: `__int64 __fastcall(XPerfAddIn::CAllocationInfoSource *this, struct XPerfCore::ICursor *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config`

## callers

- `0x180090dd0`
- `0x1800910e0`

## callees

- `0x180011e00`
- `0x18004c978`
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

- `msvcrt!fprintf` at `0x18004d77c`
- `msvcrt!fprintf` at `0x18004d77c`

## string_xrefs

- `0x18004d167`: `destroying never-created allocation with global handle %lld`
- `0x18004d6b5`: `opening nonexistent target %lld (as %lld by %lld)`
- `0x18004d5eb`: `opening already open local handle %lld (previously open at %lld) by PID %lld -- autoclosing`
- `0x18004d537`: `closing already-closed allocation`
- `0x18004d510`: `closing never-opened allocation (%lld)`
- `0x18004da74`: `alloc %lld which was in %d/%d moved from %d/%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall XPerfAddIn::CAllocationInfoSource::RealOnEvent<unsigned __int64>(
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
  __int64 v22; // rcx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rdx
  _BYTE *v36; // r15
  char v37; // di
  unsigned int *v38; // r12
  XPerfAddIn::CAllocationInfoSource::CAllocation *v39; // r15
  __int64 v40; // rbx
  __int64 v41; // r15
  __int64 v42; // rax
  unsigned int v43; // ebx
  _QWORD *v44; // rbx
  __int64 v45; // rdx
  int v46; // r14d
  __int64 v47; // r8
  __int64 v48; // rax
  __int64 v49; // rdx
  _QWORD *v50; // rdx
  __int64 v51; // rax
  __int64 v52; // xmm1_8
  __int64 v53; // rax
  _QWORD *v54; // r12
  _QWORD *v55; // rax
  _QWORD *v56; // r15
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rbx
  __int64 v60; // rax
  __int64 v61; // r13
  __int64 v62; // rdx
  unsigned __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // rcx
  _BYTE *v66; // rbx
  __int64 v67; // r12
  XPerfAddIn::CAllocationInfoSource::CAllocation *v68; // r15
  _BYTE *v69; // rax
  __int64 v70; // r8
  _BYTE *v71; // rdx
  __int64 v72; // rbx
  FILE *v73; // rax
  __int64 v74; // rax
  unsigned int *v75; // rbx
  int v76; // r12d
  __int64 v77; // rcx
  __int64 v78; // r15
  XPerfAddIn::CAllocationInfoSource::CAllocation *v79; // r13
  XPerfAddIn::CAllocationInfoSource::CAllocation *v80; // r15
  const struct XPerfAddIn::DX::ISegmentInfoSource::Segment *Segment; // r13
  __int64 v82; // rax
  const struct XPerfAddIn::DX::ISegmentInfoSource::Segment *v83; // r15
  XPerfAddIn::CAllocationInfoSource::CAllocation *v84; // rbx
  const struct XPerfAddIn::DX::ISegmentInfoSource::Segment *v85; // rax
  int v86; // r8d
  int v87; // ecx
  int v88; // eax
  int v89; // edx
  XPerfAddIn::CAllocationInfoSource::CAllocation *v90; // [rsp+40h] [rbp-198h] BYREF
  __int64 v91; // [rsp+48h] [rbp-190h] BYREF
  __int64 v92; // [rsp+50h] [rbp-188h]
  __int64 v93; // [rsp+58h] [rbp-180h]
  __int64 v94; // [rsp+60h] [rbp-178h] BYREF
  int v95; // [rsp+68h] [rbp-170h]
  _BYTE v96[56]; // [rsp+80h] [rbp-158h] BYREF
  int v97; // [rsp+B8h] [rbp-120h]
  _BYTE v98[12]; // [rsp+BCh] [rbp-11Ch]
  __int64 v99; // [rsp+C8h] [rbp-110h]
  __int64 v100; // [rsp+D0h] [rbp-108h]
  int v101; // [rsp+D8h] [rbp-100h]
  int v102; // [rsp+DCh] [rbp-FCh]
  int v103; // [rsp+E0h] [rbp-F8h]
  int v104; // [rsp+E4h] [rbp-F4h]
  int v105; // [rsp+E8h] [rbp-F0h]
  int v106; // [rsp+ECh] [rbp-ECh]
  int v107; // [rsp+F0h] [rbp-E8h]
  int v108; // [rsp+F4h] [rbp-E4h]
  int v109; // [rsp+F8h] [rbp-E0h]
  int v110; // [rsp+FCh] [rbp-DCh]
  _QWORD v111[6]; // [rsp+100h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+130h] [rbp-A8h]
  __m128i v113; // [rsp+140h] [rbp-98h]
  __int64 v114; // [rsp+150h] [rbp-88h]
  void *Block[2]; // [rsp+170h] [rbp-68h]
  __int64 v116; // [rsp+180h] [rbp-58h]

  memset_0(v96, 0, 0x80u);
  if ( a3 == (__int64 *)&DxgkControlGuid )
  {
    v8 = *(unsigned __int16 *)(a4 + 40);
    if ( v8 > 0x50 )
      goto LABEL_13;
    if ( v8 == 80 )
    {
      if ( *(_WORD *)(a4 + 86) < 0x34u )
        return 262403;
      v35 = *(_QWORD *)(a4 + 96);
      *(_QWORD *)v96 = *(_QWORD *)v35;
      *(_QWORD *)&v96[8] = *(_QWORD *)(v35 + 8);
      *(_QWORD *)&v96[16] = *(_QWORD *)(v35 + 16);
      v17 = 0;
      *(_DWORD *)&v96[24] = (*(_DWORD *)(v35 + 24) != 0) | (*(_DWORD *)(v35 + 28) != 0 ? 2 : 0);
      *(_QWORD *)&v96[28] = *(_QWORD *)(v35 + 32);
      *(_DWORD *)&v96[36] = *(_DWORD *)(v35 + 40);
      *(_QWORD *)&v96[40] = *(_QWORD *)(v35 + 44);
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
                if ( *(_WORD *)(a4 + 86) < 0x34u )
                  return 262403;
                v28 = *(_QWORD *)(a4 + 96);
                *(_DWORD *)v96 = 6;
                *(_OWORD *)&v96[4] = *(_OWORD *)v28;
                v17 = 0;
                *(_DWORD *)&v96[20] = *(_DWORD *)(v28 + 16) != 0;
                *(_QWORD *)&v96[24] = *(_QWORD *)(v28 + 20);
                *(_DWORD *)&v96[32] = *(_DWORD *)(v28 + 28);
                *(_OWORD *)&v96[36] = *(_OWORD *)(v28 + 32);
                v29 = 2 * (*(_DWORD *)(v28 + 48) & 1);
              }
              else
              {
                if ( *(_WORD *)(a4 + 86) < 0x38u )
                  return 262403;
                v30 = *(_QWORD *)(a4 + 96);
                *(_DWORD *)v96 = 5;
                *(_QWORD *)&v96[4] = *(_QWORD *)v30;
                *(_QWORD *)&v96[12] = *(_QWORD *)(v30 + 8);
                v17 = 0;
                *(_DWORD *)&v96[20] = *(_DWORD *)(v30 + 16) != 0;
                *(_QWORD *)&v96[24] = *(_QWORD *)(v30 + 20);
                *(_DWORD *)&v96[32] = *(_DWORD *)(v30 + 28);
                *(_QWORD *)&v96[36] = *(_QWORD *)(v30 + 32);
                *(_QWORD *)&v96[44] = *(_QWORD *)(v30 + 40);
                v29 = *(_DWORD *)(v30 + 48) ^ (*(_DWORD *)(v30 + 48) ^ (2 * *(_DWORD *)(v30 + 52))) & 2;
              }
              *(_DWORD *)&v96[52] = v29;
            }
            else
            {
              if ( *(_WORD *)(a4 + 86) < 0x2Cu )
                return 262403;
              v31 = *(_QWORD *)(a4 + 96);
              *(_DWORD *)v96 = 2;
              *(_QWORD *)&v96[4] = *(_QWORD *)v31;
              *(_QWORD *)&v96[12] = *(_QWORD *)(v31 + 8);
              v17 = 0;
              *(_DWORD *)&v96[20] = *(_DWORD *)(v31 + 16) != 0;
              *(_QWORD *)&v96[24] = *(_QWORD *)(v31 + 20);
              *(_DWORD *)&v96[32] = *(_DWORD *)(v31 + 28);
              *(_DWORD *)&v96[36] = *(_DWORD *)(v31 + 32);
              *(_QWORD *)&v96[40] = *(_QWORD *)(v31 + 36);
            }
          }
          else
          {
            if ( *(_WORD *)(a4 + 86) < 0x34u )
              return 262403;
            v32 = *(_QWORD *)(a4 + 96);
            *(_DWORD *)v96 = 1;
            *(_QWORD *)&v96[4] = *(_QWORD *)v32;
            *(_QWORD *)&v96[12] = *(_QWORD *)(v32 + 8);
            v17 = 0;
            *(_DWORD *)&v96[20] = *(_DWORD *)(v32 + 16) != 0;
            *(_QWORD *)&v96[24] = *(_QWORD *)(v32 + 20);
            *(_QWORD *)&v96[32] = *(_QWORD *)(v32 + 28);
            *(_DWORD *)&v96[40] = *(_DWORD *)(v32 + 36);
            *(_DWORD *)&v96[44] = *(_DWORD *)(v32 + 40);
            *(_QWORD *)&v96[48] = *(_QWORD *)(v32 + 44);
          }
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x44u )
            return 262403;
          v33 = *(_QWORD *)(a4 + 96);
          *(_QWORD *)&v96[4] = *(_QWORD *)v33;
          *(_QWORD *)&v96[12] = *(_QWORD *)(v33 + 8);
          v17 = 0;
          *(_DWORD *)&v96[20] = *(_DWORD *)(v33 + 16) != 0;
          *(_QWORD *)&v96[24] = *(_QWORD *)(v33 + 20);
          *(_DWORD *)&v96[32] = *(_DWORD *)(v33 + 28);
          *(_QWORD *)&v96[36] = *(_QWORD *)(v33 + 32);
          *(_DWORD *)&v96[44] = *(_DWORD *)(v33 + 40);
          *(_QWORD *)&v96[48] = *(_QWORD *)(v33 + 44);
          v97 = *(_DWORD *)(v33 + 52);
          *(_QWORD *)v98 = *(_QWORD *)(v33 + 56);
          *(_DWORD *)&v98[8] = *(_DWORD *)(v33 + 64);
        }
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
        if ( *(_WORD *)(a4 + 86) < 0x1Cu )
          return 262403;
        v22 = *(_QWORD *)(a4 + 96);
        *(_QWORD *)v96 = *(_QWORD *)v22;
        *(_QWORD *)&v96[8] = *(_QWORD *)(v22 + 8);
        *(_DWORD *)&v96[16] = *(_DWORD *)(v22 + 16);
        *(_QWORD *)&v96[20] = *(_QWORD *)(v22 + 20);
        v16 = ETWGUID_DXGKDEVICE;
        a3 = ETWGUID_DXGKDEVICE;
        v15 = &ETWGUID_DXGKCREATEALLOCATION;
        goto LABEL_15;
      }
      v12 = v11 - 4;
      if ( !v12 || (v13 = v12 - 1) == 0 || (v14 = v13 - 1) == 0 )
      {
        if ( *(_WORD *)(a4 + 86) < 0x80u )
          return 262403;
        v21 = *(_QWORD *)(a4 + 96);
        *(_QWORD *)v96 = *(_QWORD *)v21;
        *(_QWORD *)&v96[8] = *(_QWORD *)(v21 + 8);
        *(_QWORD *)&v96[16] = *(_QWORD *)(v21 + 16);
        *(_DWORD *)&v96[24] = *(_DWORD *)(v21 + 24);
        *(_QWORD *)&v96[28] = *(_QWORD *)(v21 + 28);
        *(_DWORD *)&v96[36] = *(_DWORD *)(v21 + 36);
        *(_QWORD *)&v96[40] = *(_QWORD *)(v21 + 40);
        *(_DWORD *)&v96[48] = *(_DWORD *)(v21 + 48);
        *(_DWORD *)&v96[52] = *(_DWORD *)(v21 + 52);
        v97 = *(_DWORD *)(v21 + 56);
        *(_DWORD *)v98 = *(_DWORD *)(v21 + 60);
        *(_QWORD *)&v98[4] = *(_QWORD *)(v21 + 64);
        v99 = *(_QWORD *)(v21 + 72);
        v100 = *(_QWORD *)(v21 + 80);
        v101 = *(_DWORD *)(v21 + 88);
        v102 = *(_DWORD *)(v21 + 92);
        v103 = *(_DWORD *)(v21 + 96);
        v104 = *(_DWORD *)(v21 + 100);
        v105 = *(_DWORD *)(v21 + 104);
        v106 = *(_DWORD *)(v21 + 108);
        v107 = *(_DWORD *)(v21 + 112);
        v108 = *(_DWORD *)(v21 + 116);
        v109 = *(_DWORD *)(v21 + 120);
        v110 = *(_DWORD *)(v21 + 124);
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
    if ( *(_WORD *)(a4 + 86) < 0x50u )
      return 262403;
    v34 = *(_QWORD *)(a4 + 96);
    *(_QWORD *)v96 = *(_QWORD *)v34;
    *(_QWORD *)&v96[8] = *(_QWORD *)(v34 + 8);
    *(_QWORD *)&v96[16] = *(_QWORD *)(v34 + 16);
    *(_QWORD *)&v96[24] = *(_QWORD *)(v34 + 24);
    *(_QWORD *)&v96[32] = *(_QWORD *)(v34 + 32);
    *(_QWORD *)&v96[40] = *(_QWORD *)(v34 + 40);
    *(_QWORD *)&v96[48] = *(_QWORD *)(v34 + 48);
    v97 = *(_DWORD *)(v34 + 56);
    *(_DWORD *)v98 = *(_DWORD *)(v34 + 64);
    *(_QWORD *)&v98[4] = *(_QWORD *)(v34 + 72);
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
      v36 = v96;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x1Cu )
        return 262403;
      v36 = *(_BYTE **)(a4 + 96);
    }
    if ( a2
      || !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
            (char *)this + 80,
            v36 + 20,
            ETWGUID_DXGKOPENALLOCATION,
            &ETWGUID_DXGKCREATEALLOCATION) )
    {
      v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, const struct _GUID *))(**((_QWORD **)this + 24) + 32LL))(
              *((_QWORD *)this + 24),
              *((_QWORD *)v36 + 1),
              v18,
              v15);
      *(_BYTE *)std::map<unsigned __int64,unsigned char>::operator[]((int)this + 80) = v37;
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
      v38 = (unsigned int *)v96;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x80u )
        return 262403;
      v38 = *(unsigned int **)(a4 + 96);
    }
    if ( *((_QWORD *)v38 + 8) != v38[16] )
      *((_BYTE *)this + 168) = 1;
    LOBYTE(v16) = *(_BYTE *)(a4 + 45);
    if ( (((_BYTE)v16 - 1) & 0xFD) != 0 )
    {
      if ( (_BYTE)v16 == 2 )
      {
        v94 = XPerfCore::TimeStamp::Max;
        v39 = (XPerfAddIn::CAllocationInfoSource::CAllocation *)*((_QWORD *)v38 + 8);
        v90 = v39;
        v40 = XPerfAddIn::CAllocationInfoSource::QueryAllocationByHandle<unsigned __int64,XPerfAddIn::CAllocationInfoSource::CAllocation *>(
                v16,
                &v90,
                &v94,
                (char *)this + 120);
        if ( !v40 )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            (char *)this + 32,
            a2,
            L"destroying never-created allocation with global handle %lld",
            v39);
          return 0;
        }
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v94);
        *(_QWORD *)(v40 + 8) = v94;
      }
    }
    else
    {
      if ( 0xF0F0F0F0F0F0F0F1uLL * ((__int64)(*((_QWORD *)this + 13) - *((_QWORD *)this + 12)) >> 3) >= 0xF0F0F0F0F0F0F0F1uLL * ((__int64)(*((_QWORD *)this + 14) - *((_QWORD *)this + 12)) >> 3) )
        return 2147549183LL;
      memset_0(v111, 0, 0x88u);
      v111[0] = XPerfCore::TimeStamp::Min;
      v111[1] = XPerfCore::TimeStamp::Max;
      v111[5] = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v113 = _mm_load_si128((const __m128i *)&_xmm);
      v114 = 0;
      *(_OWORD *)Block = 0;
      v116 = 0;
      std::vector<XPerfAddIn::CAllocationInfoSource::CAllocation>::push_back((char *)this + 96, v111);
      if ( Block[0] )
        operator delete(Block[0]);
      v41 = *((_QWORD *)this + 13) - 136LL;
      v91 = v41;
      if ( *(_BYTE *)(a4 + 45) == 1 )
      {
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v94);
        v42 = v94;
      }
      else
      {
        v42 = XPerfCore::TimeStamp::Min;
      }
      *(_QWORD *)v41 = v42;
      *(_QWORD *)(v41 + 8) = XPerfCore::TimeStamp::Max;
      *(_QWORD *)(v41 + 16) = *((_QWORD *)v38 + 8);
      *(_QWORD *)(v41 + 24) = *(_QWORD *)(v38 + 7);
      *(_QWORD *)(v41 + 32) = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 22)
                                                                                         + 32LL))(
                                *((_QWORD *)this + 22),
                                v41,
                                *v38,
                                0);
      *(_DWORD *)(v41 + 88) = v38[24];
      *(_DWORD *)(v41 + 92) = v38[27];
      *(_DWORD *)(v41 + 96) = v38[28];
      *(_DWORD *)(v41 + 100) = v38[6];
      *(_DWORD *)(v41 + 104) = v38[23];
      *(_BYTE *)(v41 + 108) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 24) + 32LL))(
                                *((_QWORD *)this + 24),
                                *((_QWORD *)v38 + 2));
      if ( v38[23] && ((*((_BYTE *)v38 + 92) ^ (unsigned __int8)(v38[6] >> 6)) & 2) != 0 )
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"Allocation %lld is both swizzled and not swizzled",
          *((_QWORD *)v38 + 8));
      v43 = v38[12];
      if ( v43 )
      {
        LODWORD(v90) = v38[12];
        std::_Tree<std::_Tmap_traits<unsigned long,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>>,0>>::find(
          (char *)this + 152,
          &v94,
          &v90);
        if ( v94 == *((_QWORD *)this + 19) )
        {
          LODWORD(v90) = v43;
          v44 = (_QWORD *)std::map<unsigned long,std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>>::operator[](
                            (char *)this + 152,
                            &v90);
          std::vector<XPerfAddIn::DX::IAllocationInfoSource::SegmentPreference>::resize(v44);
          while ( v17 < 5 )
          {
            v45 = 6 * v17;
            v46 = (v38[12] >> (6 * v17 + 5)) & 1;
            v47 = v38[12] >> (6 * v17);
            LOBYTE(v47) = v47 & 0x1F;
            LOBYTE(v45) = *(_BYTE *)(v41 + 108);
            v48 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 24) + 40LL))(
                    *((_QWORD *)this + 24),
                    v45,
                    v47);
            v49 = 2 * v17;
            *(_QWORD *)(*v44 + 8 * v49) = v48;
            *(_DWORD *)(*v44 + 8 * v49 + 8) = v46;
            ++v17;
          }
          v50 = v44;
        }
        else
        {
          v50 = (_QWORD *)(v94 + 40);
        }
        v51 = XPerfCore::adapter_from_vector<XPerfAddIn::DX::Warning,XPerfAddIn::DX::Warning>(&v94, v50);
        v52 = *(_QWORD *)(v51 + 16);
        *(_OWORD *)(v41 + 40) = *(_OWORD *)v51;
        *(_QWORD *)(v41 + 56) = v52;
      }
      else
      {
        *(_QWORD *)(v41 + 40) = 0;
        *(_QWORD *)(v41 + 48) = 16;
        *(_QWORD *)(v41 + 56) = 0;
      }
      *(_WORD *)(v41 + 109) = 0;
      *(_BYTE *)(v41 + 111) = 0;
      v53 = std::map<unsigned __int64,std::vector<XPerfAddIn::CAllocationInfoSource::CAllocation *>>::operator[](
              (char *)this + 120,
              v41 + 16);
      std::vector<XPerfAddIn::DX::IAllocationInfoSource::Allocation const *>::push_back(v53, &v91);
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
      v54 = v96;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x48u )
        return 262403;
      v54 = *(_QWORD **)(a4 + 96);
    }
    if ( v54[3] != *((_DWORD *)v54 + 6) )
      *((_BYTE *)this + 168) = 1;
    v91 = v54[3];
    LODWORD(v92) = *(_DWORD *)v54;
    v55 = (_QWORD *)std::map<std::pair<unsigned __int64,unsigned long>,std::vector<XPerfAddIn::CAllocationInfoSource::Assignment>>::operator[](
                      (char *)this + 136,
                      &v91,
                      ETWGUID_DXGKOPENALLOCATION,
                      &ETWGUID_DXGKCREATEALLOCATION);
    v56 = v55;
    LOBYTE(v57) = *(_BYTE *)(a4 + 45) - 1;
    if ( (v57 & 0xFD) != 0 )
    {
      v58 = v55[1];
      if ( v58 == *v55 )
      {
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"closing never-opened allocation (%lld)",
          v54[3]);
        return 0;
      }
      if ( *(_QWORD *)(v58 - 16) != XPerfCore::TimeStamp::Max )
      {
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"closing already-closed allocation");
        return 0;
      }
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v91);
      *(_QWORD *)(v56[1] - 16LL) = v91;
    }
    else
    {
      v59 = XPerfCore::TimeStamp::Max;
      v91 = XPerfCore::TimeStamp::Max;
      v94 = v54[4];
      v60 = XPerfAddIn::CAllocationInfoSource::QueryAllocationByHandle<unsigned __int64,XPerfAddIn::CAllocationInfoSource::CAllocation *>(
              v57,
              &v94,
              &v91,
              (char *)this + 120);
      v61 = v60;
      v62 = v56[1];
      if ( v62 != *v56 && *(_QWORD *)(v62 - 16) == v59 )
      {
        if ( v60 == *(_QWORD *)(v62 - 8) )
          return 0;
        v63 = (__int64)((unsigned __int128)(*(__int64 *)(v62 - 24) * (__int128)0x20C49BA5E353F7CFLL) >> 64) >> 7;
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"opening already open local handle %lld (previously open at %lld) by PID %lld -- autoclosing",
          v54[3],
          (v63 >> 63) + v63,
          *v54);
        if ( a2 )
        {
          XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v91);
          v64 = v91;
        }
        else
        {
          v64 = XPerfCore::TimeStamp::Min;
        }
        *(_QWORD *)(v56[1] - 16LL) = v64;
        v59 = XPerfCore::TimeStamp::Max;
      }
      v93 = 0;
      v91 = XPerfCore::TimeStamp::Min;
      v92 = v59;
      std::vector<XPerfAddIn::CAutoLeaf<XPerfAddIn::ISuspendInfoSource::DriverRecord>>::push_back(v56, &v91);
      if ( a2 )
      {
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v91);
        v65 = v91;
      }
      else
      {
        v65 = XPerfCore::TimeStamp::Min;
      }
      *(_QWORD *)(v56[1] - 24LL) = v65;
      *(_QWORD *)(v56[1] - 16LL) = XPerfCore::TimeStamp::Max;
      *(_QWORD *)(v56[1] - 8LL) = v61;
      if ( !*(_QWORD *)(v56[1] - 8LL) )
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
          (char *)this + 32,
          a2,
          L"opening nonexistent target %lld (as %lld by %lld)",
          v54[4],
          v54[3],
          *v54);
    }
    return 0;
  }
  if ( a3 == ETWGUID_DXGKREPORTALLOCATION )
  {
    if ( v19 )
    {
      v66 = v96;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x30u )
        return 262403;
      v66 = *(_BYTE **)(a4 + 96);
    }
    v91 = XPerfCore::TimeStamp::Max;
    v67 = *((_QWORD *)v66 + 2);
    v94 = v67;
    v95 = *(_DWORD *)v66;
    v68 = (XPerfAddIn::CAllocationInfoSource::CAllocation *)XPerfAddIn::CAllocationInfoSource::QueryAllocationByHandle<std::pair<unsigned __int64,unsigned long>,XPerfAddIn::CAllocationInfoSource::Assignment>(
                                                              ETWGUID_DXGKDEVICE,
                                                              &v94,
                                                              &v91,
                                                              (char *)this + 136);
    if ( !v68 )
    {
      XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
        (char *)this + 32,
        a2,
        L"report made for unknown local handle %lld",
        v67);
      return 0;
    }
    v69 = (_BYTE *)std::map<unsigned __int64,unsigned char>::operator[]((int)this + 80);
    v71 = v69;
    if ( !*v69 )
    {
      v72 = *((_QWORD *)v66 + 1);
      v73 = _acrt_iob_func(2u);
      fprintf(v73, "ERROR: no adapter for device %lld", v72);
      return 262400;
    }
    LOBYTE(v70) = v66[36];
    LOBYTE(v71) = *v69;
    v74 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)this + 24) + 40LL))(
            *((_QWORD *)this + 24),
            v71,
            v70);
    if ( !v74 )
    {
      XPerfAddIn::CAllocationInfoSource::reportBadSegmentId(0, *((_DWORD *)v66 + 9), L"allocation report", a2);
      return 262400;
    }
    v91 = *(_QWORD *)v68;
    v93 = v74;
    v92 = *((_QWORD *)v66 + 5);
    XPerfAddIn::CAllocationInfoSource::CAllocation::insertPlacement(
      v68,
      (const struct XPerfAddIn::DX::IAllocationInfoSource::SegmentPlacement *)&v91);
    return 0;
  }
  if ( a3 != ETWGUID_DXGKPAGINGOPERATION )
    return 0;
  if ( !a2 )
    return 262400;
  if ( v19 )
  {
    v75 = (unsigned int *)v96;
  }
  else
  {
    if ( *(_WORD *)(a4 + 86) < 0x50u )
      return 262403;
    v75 = *(unsigned int **)(a4 + 96);
  }
  if ( v75[5] )
    return 262400;
  v76 = 0;
  v94 = 0;
  v77 = *v75;
  if ( !(_DWORD)v77 )
  {
    v76 = v75[14];
    v94 = *(_QWORD *)(v75 + 15);
    goto LABEL_166;
  }
  v77 = (unsigned int)(v77 - 1);
  if ( !(_DWORD)v77 )
  {
    v76 = v75[11];
    v78 = *((_QWORD *)v75 + 6);
    goto LABEL_164;
  }
  v77 = (unsigned int)(v77 - 1);
  if ( !(_DWORD)v77 )
    goto LABEL_166;
  v77 = (unsigned int)(v77 - 3);
  if ( !(_DWORD)v77 )
  {
    v76 = v75[8];
    v78 = *((_QWORD *)this + 27) * *(_QWORD *)(v75 + 9);
LABEL_164:
    v94 = v78;
    goto LABEL_166;
  }
  if ( (_DWORD)v77 != 1 )
  {
    XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
      (char *)this + 32,
      a2,
      L"unhandled pagingOperation %d maybe for %lld",
      *v75,
      *((_QWORD *)v75 + 3));
    return 262400;
  }
LABEL_166:
  v79 = (XPerfAddIn::CAllocationInfoSource::CAllocation *)*((_QWORD *)v75 + 3);
  v91 = XPerfCore::TimeStamp::Max;
  v90 = v79;
  v80 = (XPerfAddIn::CAllocationInfoSource::CAllocation *)XPerfAddIn::CAllocationInfoSource::QueryAllocationByHandle<unsigned __int64,XPerfAddIn::CAllocationInfoSource::CAllocation *>(
                                                            v77,
                                                            &v90,
                                                            &v91,
                                                            (char *)this + 120);
  v90 = v80;
  if ( !v80 )
  {
    XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
      (char *)this + 32,
      a2,
      L"paging operation on unknown global handle %lld",
      v79);
    return 262400;
  }
  Segment = XPerfAddIn::CAllocationInfoSource::getSegment(this, *(_QWORD *)(v75 + 1), v76);
  v82 = *((_QWORD *)v80 + 15);
  if ( v82 == *((_QWORD *)v80 + 14) )
    v83 = 0;
  else
    v83 = *(const struct XPerfAddIn::DX::ISegmentInfoSource::Segment **)(v82 - 8);
  if ( !*v75 )
  {
    v85 = XPerfAddIn::CAllocationInfoSource::getSegment(this, *(_QWORD *)(v75 + 1), *((_BYTE *)v75 + 44));
    if ( v83 != v85 )
    {
      if ( v85 )
      {
        v86 = *((unsigned __int8 *)v85 + 12);
        v87 = *((unsigned __int8 *)v85 + 13);
        v88 = -1;
      }
      else
      {
        v88 = -1;
        v86 = -1;
        v87 = -1;
      }
      if ( v83 )
      {
        v88 = *((unsigned __int8 *)v83 + 12);
        v89 = *((unsigned __int8 *)v83 + 13);
      }
      else
      {
        v89 = -1;
      }
      v84 = v90;
      XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
        (char *)this + 32,
        a2,
        L"alloc %lld which was in %d/%d moved from %d/%d",
        *((_QWORD *)v90 + 2),
        v88,
        v89,
        v86,
        v87);
      goto LABEL_185;
    }
    goto LABEL_184;
  }
  if ( *v75 != 1 )
  {
    if ( *v75 == 5 )
    {
      if ( v83 )
        return 0;
      if ( !Segment )
      {
        XPerfAddIn::CAllocationInfoSource::reportBadSegmentId(
          (XPerfAddIn::CAllocationInfoSource *)(*v75 - 5),
          v76,
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
    else if ( *v75 == 6 && (!v83 || (*((_BYTE *)v83 + 8) & 1) == 0) )
    {
      return 262400;
    }
    goto LABEL_184;
  }
  if ( Segment )
  {
LABEL_184:
    v84 = v90;
LABEL_185:
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v91);
    v93 = (__int64)Segment;
    v92 = v94;
    XPerfAddIn::CAllocationInfoSource::CAllocation::pushBackPlacement(
      v84,
      (const struct XPerfAddIn::DX::IAllocationInfoSource::SegmentPlacement *)&v91);
    return 0;
  }
  XPerfAddIn::CAllocationInfoSource::reportBadSegmentId(
    (XPerfAddIn::CAllocationInfoSource *)(*v75 - 1),
    v76,
    L"Paging Fill Operation",
    a2);
  return 262400;
}

```

## disassembly

```asm
0x18004c978  push    rbx
0x18004c97a  push    rsi
0x18004c97b  push    rdi
0x18004c97c  push    r12
0x18004c97e  push    r13
0x18004c980  push    r14
0x18004c982  push    r15
0x18004c984  sub     rsp, 1A0h
0x18004c98b  mov     rax, cs:__security_cookie
0x18004c992  xor     rax, rsp
0x18004c995  mov     [rsp+1D8h+var_48], rax
0x18004c99d  mov     rbx, r9
0x18004c9a0  mov     r15, r8
0x18004c9a3  mov     r14, rdx
0x18004c9a6  mov     rsi, rcx
0x18004c9a9  mov     r12d, 80h
0x18004c9af  mov     r8d, r12d; Size
0x18004c9b2  xor     edx, edx; Val
0x18004c9b4  lea     rcx, [rsp+1D8h+var_158]; void *
0x18004c9bc  call    memset_0
0x18004c9c1  lea     rax, DxgkControlGuid
0x18004c9c8  lea     r11d, [r12-30h]
0x18004c9cd  cmp     r15, rax
0x18004c9d0  jnz     loc_18004D020
0x18004c9d6  movzx   ecx, word ptr [rbx+28h]
0x18004c9da  cmp     ecx, r11d
0x18004c9dd  ja      short loc_18004CA27
0x18004c9df  jz      loc_18004CF7E
0x18004c9e5  cmp     ecx, 25h ; '%'
0x18004c9e8  ja      loc_18004CBD7
0x18004c9ee  jz      loc_18004CED0
0x18004c9f4  sub     ecx, 1Bh
0x18004c9f7  jz      loc_18004CB7F
0x18004c9fd  sub     ecx, 1
0x18004ca00  jz      loc_18004CB7F
0x18004ca06  sub     ecx, 1
0x18004ca09  jz      loc_18004CB7F
0x18004ca0f  sub     ecx, 4
0x18004ca12  jz      short loc_18004CA54
0x18004ca14  sub     ecx, 1
0x18004ca17  jz      short loc_18004CA54
0x18004ca19  sub     ecx, 1
0x18004ca1c  jz      short loc_18004CA54
0x18004ca1e  cmp     ecx, 1
0x18004ca21  jz      loc_18004CED0
0x18004ca27  lea     r9, ETWGUID_DXGKCREATEALLOCATION
0x18004ca2e  lea     rcx, ETWGUID_DXGKDEVICE
0x18004ca35  xor     edi, edi
0x18004ca37  lea     rax, ETWGUID_DXGKPAGINGOPERATION
0x18004ca3e  lea     r8, ETWGUID_DXGKOPENALLOCATION
0x18004ca45  lea     rdx, ETWGUID_DXGKREPORTALLOCATION
0x18004ca4c  mov     r10b, 1
0x18004ca4f  jmp     loc_18004D048
0x18004ca54  cmp     [rbx+56h], r12w
0x18004ca59  jnb     short loc_18004CA65
0x18004ca5b  mov     eax, 40103h
0x18004ca60  jmp     loc_18004DA98
0x18004ca65  mov     rcx, [rbx+60h]
0x18004ca69  mov     rax, [rcx]
0x18004ca6c  mov     [rsp+1D8h+var_158], rax
0x18004ca74  mov     rax, [rcx+8]
0x18004ca78  mov     [rsp+88h], rax
0x18004ca80  mov     rax, [rcx+10h]
0x18004ca84  mov     [rsp+1D8h+var_148], rax
0x18004ca8c  mov     eax, [rcx+18h]
0x18004ca8f  mov     dword ptr [rsp+1D8h+var_140], eax
0x18004ca96  mov     rax, [rcx+1Ch]
0x18004ca9a  mov     [rsp+1D8h+var_140+4], rax
0x18004caa2  mov     eax, [rcx+24h]
0x18004caa5  mov     dword ptr [rsp+1D8h+var_138+4], eax
0x18004caac  mov     eax, [rcx+28h]
0x18004caaf  mov     dword ptr [rsp+1D8h+var_138+8], eax
0x18004cab6  mov     eax, [rcx+2Ch]
0x18004cab9  mov     dword ptr [rsp+1D8h+var_138+0Ch], eax
0x18004cac0  mov     eax, [rcx+30h]
0x18004cac3  mov     dword ptr [rsp+1D8h+var_138+10h], eax
0x18004caca  mov     eax, [rcx+34h]
0x18004cacd  mov     [rsp+1D8h+var_124], eax
0x18004cad4  mov     eax, [rcx+38h]
0x18004cad7  mov     [rsp+1D8h+var_120], eax
0x18004cade  mov     eax, [rcx+3Ch]
0x18004cae1  mov     dword ptr [rsp+1D8h+var_11C], eax
0x18004cae8  mov     rax, [rcx+40h]
0x18004caec  mov     [rsp+1D8h+var_11C+4], rax
0x18004caf4  mov     rax, [rcx+48h]
0x18004caf8  mov     [rsp+1D8h+var_110], rax
0x18004cb00  mov     rax, [rcx+50h]
0x18004cb04  mov     [rsp+1D8h+var_108], rax
0x18004cb0c  mov     eax, [rcx+58h]
0x18004cb0f  mov     [rsp+1D8h+var_100], eax
0x18004cb16  mov     eax, [rcx+5Ch]
0x18004cb19  mov     [rsp+1D8h+var_FC], eax
0x18004cb20  mov     eax, [rcx+60h]
0x18004cb23  mov     [rsp+1D8h+var_F8], eax
0x18004cb2a  mov     eax, [rcx+64h]
0x18004cb2d  mov     [rsp+1D8h+var_F4], eax
0x18004cb34  mov     eax, [rcx+68h]
0x18004cb37  mov     [rsp+1D8h+var_F0], eax
0x18004cb3e  mov     eax, [rcx+6Ch]
0x18004cb41  mov     [rsp+1D8h+var_EC], eax
0x18004cb48  mov     eax, [rcx+70h]
0x18004cb4b  mov     [rsp+1D8h+var_E8], eax
0x18004cb52  mov     eax, [rcx+74h]
0x18004cb55  mov     [rsp+1D8h+var_E4], eax
0x18004cb5c  mov     eax, [rcx+78h]
0x18004cb5f  mov     [rsp+1D8h+var_E0], eax
0x18004cb66  mov     eax, [rcx+7Ch]
0x18004cb69  mov     [rsp+1D8h+var_DC], eax
0x18004cb70  lea     r9, ETWGUID_DXGKCREATEALLOCATION
0x18004cb77  mov     r15, r9
0x18004cb7a  jmp     loc_18004CA2E
0x18004cb7f  cmp     word ptr [rbx+56h], 1Ch
0x18004cb84  jnb     short loc_18004CB90
0x18004cb86  mov     eax, 40103h
0x18004cb8b  jmp     loc_18004DA98
0x18004cb90  mov     rcx, [rbx+60h]
0x18004cb94  mov     rax, [rcx]
0x18004cb97  mov     [rsp+1D8h+var_158], rax
0x18004cb9f  mov     rax, [rcx+8]
0x18004cba3  mov     [rsp+88h], rax
0x18004cbab  mov     eax, [rcx+10h]
0x18004cbae  mov     dword ptr [rsp+1D8h+var_148], eax
0x18004cbb5  mov     rax, [rcx+14h]
0x18004cbb9  mov     [rsp+1D8h+var_148+4], rax
0x18004cbc1  lea     rcx, ETWGUID_DXGKDEVICE
0x18004cbc8  mov     r15, rcx
0x18004cbcb  lea     r9, ETWGUID_DXGKCREATEALLOCATION
0x18004cbd2  jmp     loc_18004CA35
0x18004cbd7  sub     ecx, 26h ; '&'
0x18004cbda  jz      loc_18004CED0
0x18004cbe0  sub     ecx, 0Fh
0x18004cbe3  jz      loc_18004CE36
0x18004cbe9  sub     ecx, 1
0x18004cbec  jz      loc_18004CDB1
0x18004cbf2  sub     ecx, 1
0x18004cbf5  jz      loc_18004CD38
0x18004cbfb  sub     ecx, 3
0x18004cbfe  jz      loc_18004CCAF
0x18004cc04  cmp     ecx, 1
0x18004cc07  jnz     loc_18004CA27
0x18004cc0d  cmp     word ptr [rbx+56h], 34h ; '4'
0x18004cc12  jnb     short loc_18004CC1E
0x18004cc14  mov     eax, 40103h
0x18004cc19  jmp     loc_18004DA98
0x18004cc1e  mov     rcx, [rbx+60h]
0x18004cc22  mov     dword ptr [rsp+1D8h+var_158], 6
0x18004cc2d  mov     rax, [rcx]
0x18004cc30  mov     [rsp+1D8h+var_158+4], rax
0x18004cc38  mov     rax, [rcx+8]
0x18004cc3c  mov     [rsp+8Ch], rax
0x18004cc44  xor     edi, edi
0x18004cc46  mov     eax, edi
0x18004cc48  cmp     [rcx+10h], edi
0x18004cc4b  setnz   al
0x18004cc4e  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004cc55  mov     rax, [rcx+14h]
0x18004cc59  mov     [rsp+1D8h+var_140], rax
0x18004cc61  mov     eax, [rcx+1Ch]
0x18004cc64  mov     dword ptr [rsp+1D8h+var_138], eax
0x18004cc6b  mov     rax, [rcx+20h]
0x18004cc6f  mov     qword ptr [rsp+1D8h+var_138+4], rax
0x18004cc77  mov     rax, [rcx+28h]
0x18004cc7b  mov     qword ptr [rsp+1D8h+var_138+0Ch], rax
0x18004cc83  mov     eax, [rcx+30h]
0x18004cc86  and     eax, 1
0x18004cc89  add     eax, eax
0x18004cc8b  mov     [rsp+1D8h+var_124], eax
0x18004cc92  lea     rax, ETWGUID_DXGKPAGINGOPERATION
0x18004cc99  mov     r15, rax
0x18004cc9c  lea     r9, ETWGUID_DXGKCREATEALLOCATION
0x18004cca3  lea     rcx, ETWGUID_DXGKDEVICE
0x18004ccaa  jmp     loc_18004CA3E
0x18004ccaf  cmp     word ptr [rbx+56h], 38h ; '8'
0x18004ccb4  jnb     short loc_18004CCC0
0x18004ccb6  mov     eax, 40103h
0x18004ccbb  jmp     loc_18004DA98
0x18004ccc0  mov     rcx, [rbx+60h]
0x18004ccc4  mov     dword ptr [rsp+1D8h+var_158], 5
0x18004cccf  mov     rax, [rcx]
0x18004ccd2  mov     [rsp+1D8h+var_158+4], rax
0x18004ccda  mov     rax, [rcx+8]
0x18004ccde  mov     [rsp+8Ch], rax
0x18004cce6  xor     edi, edi
0x18004cce8  mov     eax, edi
0x18004ccea  cmp     [rcx+10h], edi
0x18004cced  setnz   al
0x18004ccf0  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004ccf7  mov     rax, [rcx+14h]
0x18004ccfb  mov     [rsp+1D8h+var_140], rax
0x18004cd03  mov     eax, [rcx+1Ch]
0x18004cd06  mov     dword ptr [rsp+1D8h+var_138], eax
0x18004cd0d  mov     rax, [rcx+20h]
0x18004cd11  mov     qword ptr [rsp+1D8h+var_138+4], rax
0x18004cd19  mov     rax, [rcx+28h]
0x18004cd1d  mov     qword ptr [rsp+1D8h+var_138+0Ch], rax
0x18004cd25  mov     eax, [rcx+34h]
0x18004cd28  add     eax, eax
0x18004cd2a  xor     eax, [rcx+30h]
0x18004cd2d  and     eax, 2
0x18004cd30  xor     eax, [rcx+30h]
0x18004cd33  jmp     loc_18004CC8B
0x18004cd38  cmp     word ptr [rbx+56h], 2Ch ; ','
0x18004cd3d  jnb     short loc_18004CD49
0x18004cd3f  mov     eax, 40103h
0x18004cd44  jmp     loc_18004DA98
0x18004cd49  mov     rcx, [rbx+60h]
0x18004cd4d  mov     dword ptr [rsp+1D8h+var_158], 2
0x18004cd58  mov     rax, [rcx]
0x18004cd5b  mov     [rsp+1D8h+var_158+4], rax
0x18004cd63  mov     rax, [rcx+8]
0x18004cd67  mov     [rsp+8Ch], rax
0x18004cd6f  xor     edi, edi
0x18004cd71  mov     eax, edi
0x18004cd73  cmp     [rcx+10h], edi
0x18004cd76  setnz   al
0x18004cd79  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004cd80  mov     rax, [rcx+14h]
0x18004cd84  mov     [rsp+1D8h+var_140], rax
0x18004cd8c  mov     eax, [rcx+1Ch]
0x18004cd8f  mov     dword ptr [rsp+1D8h+var_138], eax
0x18004cd96  mov     eax, [rcx+20h]
0x18004cd99  mov     dword ptr [rsp+1D8h+var_138+4], eax
0x18004cda0  mov     rax, [rcx+24h]
0x18004cda4  mov     qword ptr [rsp+1D8h+var_138+8], rax
0x18004cdac  jmp     loc_18004CC92
0x18004cdb1  cmp     word ptr [rbx+56h], 34h ; '4'
0x18004cdb6  jnb     short loc_18004CDC2
0x18004cdb8  mov     eax, 40103h
0x18004cdbd  jmp     loc_18004DA98
0x18004cdc2  mov     rcx, [rbx+60h]
0x18004cdc6  mov     dword ptr [rsp+1D8h+var_158], 1
0x18004cdd1  mov     rax, [rcx]
0x18004cdd4  mov     [rsp+1D8h+var_158+4], rax
0x18004cddc  mov     rax, [rcx+8]
0x18004cde0  mov     [rsp+8Ch], rax
0x18004cde8  xor     edi, edi
0x18004cdea  mov     eax, edi
0x18004cdec  cmp     [rcx+10h], edi
0x18004cdef  setnz   al
0x18004cdf2  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004cdf9  mov     rax, [rcx+14h]
0x18004cdfd  mov     [rsp+1D8h+var_140], rax
0x18004ce05  mov     rax, [rcx+1Ch]
0x18004ce09  mov     qword ptr [rsp+1D8h+var_138], rax
0x18004ce11  mov     eax, [rcx+24h]
0x18004ce14  mov     dword ptr [rsp+1D8h+var_138+8], eax
0x18004ce1b  mov     eax, [rcx+28h]
0x18004ce1e  mov     dword ptr [rsp+1D8h+var_138+0Ch], eax
0x18004ce25  mov     rax, [rcx+2Ch]
0x18004ce29  mov     qword ptr [rsp+1D8h+var_138+10h], rax
0x18004ce31  jmp     loc_18004CC92
0x18004ce36  cmp     word ptr [rbx+56h], 44h ; 'D'
0x18004ce3b  jnb     short loc_18004CE47
0x18004ce3d  mov     eax, 40103h
0x18004ce42  jmp     loc_18004DA98
0x18004ce47  mov     rcx, [rbx+60h]
0x18004ce4b  mov     rax, [rcx]
0x18004ce4e  mov     [rsp+1D8h+var_158+4], rax
0x18004ce56  mov     rax, [rcx+8]
0x18004ce5a  mov     [rsp+8Ch], rax
0x18004ce62  xor     edi, edi
0x18004ce64  mov     eax, edi
0x18004ce66  cmp     [rcx+10h], edi
0x18004ce69  setnz   al
0x18004ce6c  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x18004ce73  mov     rax, [rcx+14h]
0x18004ce77  mov     [rsp+1D8h+var_140], rax
0x18004ce7f  mov     eax, [rcx+1Ch]
0x18004ce82  mov     dword ptr [rsp+1D8h+var_138], eax
0x18004ce89  mov     rax, [rcx+20h]
0x18004ce8d  mov     qword ptr [rsp+1D8h+var_138+4], rax
0x18004ce95  mov     eax, [rcx+28h]
0x18004ce98  mov     dword ptr [rsp+1D8h+var_138+0Ch], eax
0x18004ce9f  mov     rax, [rcx+2Ch]
0x18004cea3  mov     qword ptr [rsp+1D8h+var_138+10h], rax
0x18004ceab  mov     eax, [rcx+34h]
0x18004ceae  mov     [rsp+1D8h+var_120], eax
0x18004ceb5  mov     rax, [rcx+38h]
0x18004ceb9  mov     [rsp+1D8h+var_11C], rax
0x18004cec1  mov     eax, [rcx+40h]
0x18004cec4  mov     [rsp+1D8h+var_114], eax
0x18004cecb  jmp     loc_18004CC92
0x18004ced0  cmp     [rbx+56h], r11w
0x18004ced5  jnb     short loc_18004CEE1
0x18004ced7  mov     eax, 40103h
0x18004cedc  jmp     loc_18004DA98
0x18004cee1  mov     rcx, [rbx+60h]
0x18004cee5  mov     rax, [rcx]
0x18004cee8  mov     [rsp+1D8h+var_158], rax
0x18004cef0  mov     rax, [rcx+8]
0x18004cef4  mov     [rsp+88h], rax
0x18004cefc  mov     rax, [rcx+10h]
0x18004cf00  mov     [rsp+1D8h+var_148], rax
0x18004cf08  mov     rax, [rcx+18h]
0x18004cf0c  mov     [rsp+1D8h+var_140], rax
0x18004cf14  mov     rax, [rcx+20h]
0x18004cf18  mov     qword ptr [rsp+1D8h+var_138], rax
0x18004cf20  mov     rax, [rcx+28h]
0x18004cf24  mov     qword ptr [rsp+1D8h+var_138+8], rax
0x18004cf2c  mov     rax, [rcx+30h]
  ... truncated ...
```

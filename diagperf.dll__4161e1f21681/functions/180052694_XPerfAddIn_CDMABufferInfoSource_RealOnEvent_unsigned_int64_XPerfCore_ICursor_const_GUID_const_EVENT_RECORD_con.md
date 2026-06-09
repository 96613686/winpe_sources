# XPerfAddIn::CDMABufferInfoSource::RealOnEvent<unsigned __int64>(XPerfCore::ICursor const *,_GUID const *,_EVENT_RECORD const *)

- ea: `0x180052694`
- end: `0x1800544fe`
- name: `??$RealOnEvent@_K@CDMABufferInfoSource@XPerfAddIn@@QEAAJPEBUICursor@XPerfCore@@PEBU_GUID@@PEBU_EVENT_RECORD@@@Z`
- size: `7786`
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
- `0x180052654`
- `0x180052694`
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

- `0x180053279`: `allocation reference listing for never-created dma buffer %lld`
- `0x18005343d`: `unrecognized context %lld during submition`
- `0x1800533df`: `submission of non-created dma buffer %lld`
- `0x1800538ff`: `Completion of never-submitted fenceID %lld`
- `0x18005356a`: `unrecognized context %lld during completion`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall XPerfAddIn::CDMABufferInfoSource::RealOnEvent<unsigned __int64>(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 v7; // rsi
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  __int64 result; // rax
  __int64 *v16; // rcx
  __int64 *v17; // rcx
  __int64 *v18; // rcx
  __int64 *v19; // rcx
  __int64 *v20; // rcx
  __int64 *v21; // r12
  int v22; // edi
  int v23; // eax
  __int64 v24; // rcx
  unsigned __int16 v25; // dx
  unsigned __int16 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  __int64 *v35; // rcx
  __int64 *v36; // rcx
  BOOL v37; // eax
  __int64 *v38; // rcx
  int v39; // eax
  __int64 *v40; // rcx
  __int64 *v41; // rcx
  __int64 *v42; // rcx
  char v43; // r13
  __int64 *v44; // rax
  _QWORD *v45; // r11
  _BYTE *v46; // rax
  unsigned __int8 *v47; // rcx
  __int64 *v48; // rax
  char *v49; // rax
  __int64 *v50; // r14
  __int64 v51; // r12
  __int64 (__fastcall *v52)(__int64, __int64 *, _QWORD, _QWORD); // r13
  unsigned int v53; // ebx
  __int64 v54; // r12
  __int64 v55; // rbx
  _QWORD *v56; // rax
  __int64 *v57; // rbx
  _QWORD *v58; // rax
  __int64 v59; // r12
  XPerfAddIn::CDMABufferInfoSource *v60; // rcx
  __int64 v61; // rbx
  __int64 v62; // rax
  __int64 *v63; // rdi
  __int64 v64; // r12
  unsigned int v65; // r13d
  __int64 v66; // r12
  __int64 v67; // rdi
  _QWORD *v68; // rax
  _QWORD *v69; // rax
  _QWORD *v70; // rax
  __int64 *v71; // rbx
  _QWORD *v72; // r12
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rdi
  _QWORD *v76; // rax
  __int64 v77; // r14
  __int64 v78; // rdi
  int v79; // eax
  __int64 *v80; // rbx
  __int64 v81; // rax
  __int64 v82; // r12
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // r13
  _QWORD *v86; // r12
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // rcx
  int v90; // ebx
  __int64 v91; // rax
  __int64 v92; // rcx
  __int64 i; // rbx
  _QWORD *v94; // r12
  _QWORD *j; // rbx
  int v96; // r13d
  __int64 v97; // rdi
  __int64 v98; // rbx
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 v101; // rcx
  __int64 k; // rax
  __int64 *v103; // rdi
  __int64 v104; // r12
  XPerfAddIn::CDMABufferInfoSource *v105; // rcx
  __int64 v106; // rdi
  __int64 (__fastcall *v107)(__int64, _QWORD *, _QWORD, _QWORD); // r14
  unsigned int v108; // ebx
  __int64 v109; // rbx
  __int64 *v110; // rax
  __int64 v111; // rbx
  __int64 v112; // r8
  __int64 v113; // r9
  _QWORD *v114; // rbx
  __int64 v115; // rdx
  __int64 v116; // rdx
  __int64 *v117; // r12
  __int64 v118; // r13
  __int64 v119; // r13
  _QWORD *v120; // rax
  __int64 v121; // r13
  XPerfAddIn::CDMABufferInfoSource *v122; // rcx
  _QWORD *v123; // rax
  __int64 v124; // rax
  char v125; // al
  __int64 v126; // rdi
  __int64 (__fastcall *v127)(__int64, _QWORD *, _QWORD, _QWORD); // r13
  unsigned int v128; // ebx
  __int64 v129; // r9
  _QWORD *v130; // rbx
  _QWORD *v131; // rcx
  unsigned __int64 v132; // r8
  int v133; // ecx
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 *v136; // rdi
  unsigned __int8 v137; // al
  int v138; // r14d
  __int64 *v139; // r13
  unsigned __int8 v140; // al
  __int64 v141; // r9
  __int64 v142; // r12
  __int64 *v143; // rax
  __int64 v144; // rbx
  __int64 v145; // rax
  __int64 v146; // r8
  unsigned __int64 v147; // r9
  __int64 v148; // r12
  __int64 v149; // r8
  __int64 v150; // r8
  __int64 v151; // r9
  __int64 v152; // r8
  __int64 v153; // r8
  __int64 v154; // rcx
  _QWORD *m; // rax
  __int64 *v156; // r14
  unsigned int v157; // edi
  __int64 v158; // r12
  __int64 (__fastcall *v159)(__int64, _QWORD *, _QWORD, _QWORD); // r13
  unsigned int v160; // ebx
  __int64 v161; // r12
  __int64 v162; // rbx
  _QWORD *v163; // rax
  __int64 v164; // [rsp+30h] [rbp-CD8h] BYREF
  unsigned __int8 v165; // [rsp+38h] [rbp-CD0h]
  _QWORD *v166; // [rsp+40h] [rbp-CC8h] BYREF
  _QWORD *v167; // [rsp+48h] [rbp-CC0h] BYREF
  _QWORD v168[2]; // [rsp+50h] [rbp-CB8h] BYREF
  unsigned __int64 v169; // [rsp+60h] [rbp-CA8h]
  __int128 v170; // [rsp+68h] [rbp-CA0h] BYREF
  __int128 v171; // [rsp+78h] [rbp-C90h]
  __int128 v172; // [rsp+88h] [rbp-C80h]
  __int64 v173; // [rsp+98h] [rbp-C70h]
  __int64 v174; // [rsp+A0h] [rbp-C68h] BYREF
  _BYTE v175[3080]; // [rsp+A8h] [rbp-C60h]

  v7 = a1;
  v164 = a1;
  memset_0(&v174, 0, 0xC18u);
  if ( a3 == (__int64 *)&DxgkControlGuid )
  {
    v8 = *(unsigned __int16 *)(a4 + 40);
    if ( v8 > 0x2B )
    {
      v29 = v8 - 50;
      if ( !v29 )
      {
        if ( *(_WORD *)(a4 + 86) < 0x2Cu )
          return 262403;
        v42 = *(__int64 **)(a4 + 96);
        v174 = *v42;
        *(_QWORD *)v175 = v42[1];
        *(_QWORD *)&v175[8] = v42[2];
        *(_OWORD *)&v175[16] = *(_OWORD *)(v42 + 3);
        *(_DWORD *)&v175[32] = *((_DWORD *)v42 + 10);
        a3 = ETWGUID_DXGKMEMORYTRANSFER;
        goto LABEL_76;
      }
      v30 = v29 - 116;
      if ( !v30 )
      {
        if ( *(_WORD *)(a4 + 86) < 0x58u )
          return 262403;
        *(_QWORD *)v175 = *(_QWORD *)(*(_QWORD *)(a4 + 96) + 8LL);
        a3 = ETWGUID_DXGKBLT;
        goto LABEL_76;
      }
      v31 = v30 - 2;
      if ( !v31 )
      {
        if ( *(_WORD *)(a4 + 86) < 0x20u )
          return 262403;
        v41 = *(__int64 **)(a4 + 96);
        v174 = *v41;
        *(_DWORD *)v175 = *((_DWORD *)v41 + 2);
        *(_QWORD *)&v175[4] = *(__int64 *)((char *)v41 + 12);
        *(_DWORD *)&v175[12] = *((_DWORD *)v41 + 5);
        v175[16] = *((_DWORD *)v41 + 6) != 0;
        v175[17] = *((_DWORD *)v41 + 7) != 0;
        a3 = (__int64 *)&ETWGUID_DXGKFLIP;
        goto LABEL_76;
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
        if ( *(_WORD *)(a4 + 86) < 8u )
          return 262403;
        v174 = **(_QWORD **)(a4 + 96);
        a3 = ETWGUID_DXGKRENDER;
        goto LABEL_76;
      }
      v33 = v32 - 6;
      if ( v33 )
      {
        v34 = v33 - 2;
        if ( v34 )
        {
          if ( v34 == 4 )
          {
            if ( *(_WORD *)(a4 + 86) < 0x14u )
              return 262403;
            v35 = *(__int64 **)(a4 + 96);
            v174 = *v35;
            *(_DWORD *)v175 = *((_DWORD *)v35 + 2);
            *(_QWORD *)&v175[4] = *(__int64 *)((char *)v35 + 12);
            a3 = ETWGUID_DXGKSCHEDULER_VSYNC_INTERRUPT;
          }
          goto LABEL_76;
        }
        if ( *(_BYTE *)(a4 + 42) )
        {
          if ( *(_WORD *)(a4 + 86) < 0x34u )
            return 262403;
          v36 = *(__int64 **)(a4 + 96);
          v174 = *v36;
          *(_DWORD *)v175 = *((_DWORD *)v36 + 2);
          *(_QWORD *)&v175[4] = *(__int64 *)((char *)v36 + 12);
          *(_DWORD *)&v175[12] = *((_DWORD *)v36 + 5);
          v37 = *((_DWORD *)v36 + 6) == 2;
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x20u )
            return 262403;
          v36 = *(__int64 **)(a4 + 96);
          v174 = *v36;
          *(_DWORD *)v175 = *((_DWORD *)v36 + 2);
          *(_QWORD *)&v175[4] = *(__int64 *)((char *)v36 + 12);
          *(_DWORD *)&v175[12] = *((_DWORD *)v36 + 5);
          v37 = *((_DWORD *)v36 + 6) != 0;
        }
        *(_DWORD *)&v175[16] = v37;
        *(_DWORD *)&v175[20] = *((_DWORD *)v36 + 7);
      }
      else
      {
        if ( *(_BYTE *)(a4 + 42) )
        {
          if ( *(_WORD *)(a4 + 86) < 0x2Cu )
            return 262403;
          v40 = *(__int64 **)(a4 + 96);
          v174 = *v40;
          *(_DWORD *)v175 = *((_DWORD *)v40 + 4);
          *(_QWORD *)&v175[4] = *(__int64 *)((char *)v40 + 20);
          *(_DWORD *)&v175[12] = *((_DWORD *)v40 + 7);
          *(_QWORD *)&v175[16] = v40[4];
          v39 = *((_DWORD *)v40 + 10);
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x24u )
            return 262403;
          v38 = *(__int64 **)(a4 + 96);
          v174 = *v38;
          *(_DWORD *)v175 = *((_DWORD *)v38 + 2);
          *(_QWORD *)&v175[4] = *(__int64 *)((char *)v38 + 12);
          *(_DWORD *)&v175[12] = *((_DWORD *)v38 + 5);
          *(_QWORD *)&v175[16] = v38[3];
          v39 = *((_DWORD *)v38 + 8);
        }
        *(_DWORD *)&v175[24] = v39;
      }
      a3 = (__int64 *)&ETWGUID_DXGKSCHEDULER_DMAPACKET;
    }
    else if ( v8 == 43 )
    {
      if ( *(_WORD *)(a4 + 86) < 0x14u )
        return 262403;
      v21 = *(__int64 **)(a4 + 96);
      v174 = *v21;
      *(_QWORD *)v175 = v21[1];
      v22 = *((_DWORD *)v21 + 4);
      *(_DWORD *)&v175[8] = v22;
      if ( !a2 )
        return 262400;
      v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 80LL))(a2);
      v24 = *((unsigned int *)v21 + 4);
      if ( v23 == 4 )
      {
        *(_DWORD *)&v175[12] = 4;
        v25 = 0;
        if ( v22 )
        {
          do
          {
            *(_DWORD *)&v175[4 * v25 + 16] = *((_DWORD *)v21 + v25 + 5)
                                           ^ (*((_DWORD *)v21 + v24 + v25 + 5)
                                            ^ *((_DWORD *)v21 + v25 + 5))
                                           & 1;
            ++v25;
          }
          while ( (unsigned int)v25 < *(_DWORD *)&v175[8] );
        }
      }
      else
      {
        *(_DWORD *)&v175[12] = 12;
        v26 = 0;
        if ( v22 )
        {
          do
          {
            v27 = 3LL * v26;
            v28 = *(__int64 *)((char *)&v21[v26 + 2] + 4);
            *(_QWORD *)&v175[4 * v27 + 16] = v28;
            *(_DWORD *)&v175[4 * v27 + 16] ^= (*((_DWORD *)&v21[v24 + 2] + ++v26) ^ v28) & 1;
          }
          while ( (unsigned int)v26 < *(_DWORD *)&v175[8] );
        }
      }
      a3 = ETWGUID_DXGKREFERENCEALLOCATIONS;
    }
    else
    {
      v9 = v8 - 17;
      if ( v9 )
      {
        v10 = v9 - 10;
        if ( v10 && (v11 = v10 - 2) != 0 )
        {
          v12 = v11 - 1;
          if ( v12 && (v13 = v12 - 2) != 0 )
          {
            v14 = v13 - 9;
            if ( v14 )
            {
              if ( v14 == 1 )
              {
                if ( *(_WORD *)(a4 + 86) < 0x14u )
                  return 262403;
                v16 = *(__int64 **)(a4 + 96);
                v174 = *v16;
                *(_QWORD *)v175 = v16[1];
                *(_DWORD *)&v175[8] = *((_DWORD *)v16 + 4);
                a3 = ETWGUID_DXGKUNLOCKALLOCATION;
              }
            }
            else
            {
              if ( *(_WORD *)(a4 + 86) < 0x18u )
                return 262403;
              v17 = *(__int64 **)(a4 + 96);
              v174 = *v17;
              *(_QWORD *)v175 = v17[1];
              *(_QWORD *)&v175[8] = v17[2];
              a3 = (__int64 *)&ETWGUID_DXGKLOCKALLOCATION;
            }
          }
          else
          {
            if ( *(_WORD *)(a4 + 86) < 0x30u )
              return 262403;
            v18 = *(__int64 **)(a4 + 96);
            v174 = *v18;
            *(_QWORD *)v175 = v18[1];
            *(_QWORD *)&v175[8] = v18[2];
            *(_DWORD *)&v175[16] = *((_DWORD *)v18 + 6);
            *(_QWORD *)&v175[20] = *(__int64 *)((char *)v18 + 28);
            *(_DWORD *)&v175[28] = *((_DWORD *)v18 + 9);
            *(_QWORD *)&v175[32] = v18[5];
            a3 = ETWGUID_DXGKCONTEXT;
          }
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x1Cu )
            return 262403;
          v19 = *(__int64 **)(a4 + 96);
          v174 = *v19;
          *(_QWORD *)v175 = v19[1];
          *(_DWORD *)&v175[8] = *((_DWORD *)v19 + 4);
          *(_QWORD *)&v175[12] = *(__int64 *)((char *)v19 + 20);
          a3 = ETWGUID_DXGKDEVICE;
        }
      }
      else
      {
        if ( *(_WORD *)(a4 + 86) < 0x38u )
          return 262403;
        v20 = *(__int64 **)(a4 + 96);
        v174 = *v20;
        *(_DWORD *)v175 = *((_DWORD *)v20 + 2);
        *(_QWORD *)&v175[4] = *(__int64 *)((char *)v20 + 12);
        *(_DWORD *)&v175[12] = *((_DWORD *)v20 + 5);
        *(_DWORD *)&v175[16] = *((_DWORD *)v20 + 6);
        *(_QWORD *)&v175[20] = *(__int64 *)((char *)v20 + 28);
        *(_QWORD *)&v175[28] = *(__int64 *)((char *)v20 + 36);
        *(_DWORD *)&v175[36] = *((_DWORD *)v20 + 11);
        a3 = (__int64 *)&ETWGUID_DXGKSCHEDULER_VSYNC_DPC;
      }
    }
LABEL_76:
    v43 = 1;
    goto LABEL_78;
  }
  v43 = 0;
  v7 = v164;
LABEL_78:
  if ( a3 == ETWGUID_DXGKCONTEXT )
  {
    if ( v43 )
    {
      v44 = &v174;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x30u )
        return 262403;
      v44 = *(__int64 **)(a4 + 96);
    }
    v167 = v44;
    v166 = v44 + 5;
    v164 = std::map<unsigned __int64,unsigned int>::operator[]((int)v7 + 208);
    v45 = v167;
    *(_BYTE *)(v164 + 1) = *((_BYTE *)v167 + 8) + 1;
    *(_BYTE *)v164 = XPerfAddIn::CDMABufferInfoSource::getHighestSetBitIndex<unsigned int>(*((unsigned int *)v45 + 3))
                   + 1;
    v46 = (_BYTE *)std::map<unsigned __int64,unsigned char>::operator[]((int)v7 + 344);
    v47 = (unsigned __int8 *)v164;
    *(_BYTE *)(v164 + 2) = *v46;
    v47[3] = 0;
    if ( (~(1 << (*v47 - 1)) & *((_DWORD *)v167 + 3)) != 0 )
      XPerfAddIn::warner::warn<XPerfCore::TimeStamp>(
        v7 + 32,
        XPerfCore::TimeStamp::Min,
        L"context %lld has multiple engine affinities (0x%x) -- assuming %d",
        *v166,
        *((_DWORD *)v167 + 3),
        *v47);
  }
  else if ( a3 == ETWGUID_DXGKDEVICE )
  {
    if ( v43 )
    {
      v48 = &v174;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x1Cu )
        return 262403;
      v48 = *(__int64 **)(a4 + 96);
    }
    v164 = (__int64)v48;
    v49 = (char *)v48 + 20;
    v167 = v49;
    if ( a2 )
    {
      v167 = v49;
    }
    else if ( std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
                v7 + 344,
                v49,
                56,
                ETWGUID_DXGKRENDER) )
    {
      return 262400;
    }
    v165 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v7 + 96) + 32LL))(
             *(_QWORD *)(v7 + 96),
             *(_QWORD *)(v164 + 8));
    *(_BYTE *)std::map<unsigned __int64,unsigned char>::operator[]((int)v7 + 344) = v165;
  }
  if ( !a2 )
    return 262400;
  if ( a3 == ETWGUID_DXGKRENDER || a3 == ETWGUID_DXGKRENDERKM )
  {
    if ( v43 )
    {
      v156 = &v174;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 8u )
        return 262403;
      v156 = *(__int64 **)(a4 + 96);
    }
    v157 = ETWGUID_DXGKRENDER != a3 ? 4 : 0;
    v158 = *(_QWORD *)(v7 + 80);
    v159 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v158 + 48LL);
    v160 = *(_DWORD *)(a4 + 8);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
    v161 = v159(v158, v168, v160, 0);
    v162 = *v156;
    v163 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v164);
    XPerfAddIn::CDMABufferInfoSource::addDMA(v7, *v163, v157, v162, v161);
    return 0;
  }
  if ( a3 == ETWGUID_DXGKBLT )
  {
    if ( v43 )
    {
      v50 = &v174;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x58u )
        return 262403;
      v50 = *(__int64 **)(a4 + 96);
    }
    v51 = *(_QWORD *)(v7 + 80);
    v52 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v51 + 48LL);
    v53 = *(_DWORD *)(a4 + 8);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v164);
    v54 = v52(v51, &v164, v53, 0);
    v55 = v50[1];
    v56 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 72LL))(a2, v168);
    XPerfAddIn::CDMABufferInfoSource::addDMA(v7, *v56, 1, v55, v54);
    return 0;
  }
  if ( a3 == ETWGUID_DXGKMEMORYTRANSFER )
  {
    if ( v43 )
    {
      v57 = &v174;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x2Cu )
        return 262403;
      v57 = *(__int64 **)(a4 + 96);
    }
    if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
            v7 + 128,
            v57 + 2,
            56,
            ETWGUID_DXGKRENDER) )
    {
      v164 = v57[2];
      v58 = (_QWORD *)XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
      XPerfAddIn::CDMABufferInfoSource::addDMA(v7, *v58, 2, v164, 0);
    }
    v59 = *(unsigned int *)std::map<unsigned __int64,unsigned int>::operator[]((int)v7 + 128);
    v164 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v7 + 88) + 40LL))(
             *(_QWORD *)(v7 + 88),
             v57[1],
             XPerfCore::TimeStamp::Max);
    if ( !v164 )
    {
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v164);
      XPerfAddIn::CDMABufferInfoSource::reportBadAllocationHandle(
        v60,
        v57[1],
        "memory transfer",
        (const struct TimeStamp *)&v164,
        1);
      return 262400;
    }
    std::vector<XPerfAddIn::DX::IAllocationInfoSource::Allocation const *>::push_back(
      296 * v59 + *(_QWORD *)(v7 + 144) + 176LL,
      &v164);
    std::vector<XPerfAddIn::DX::IAllocationInfoSource::Allocation const *>::push_back(
      296 * v59 + *(_QWORD *)(v7 + 144) + 200LL,
      &v164);
    v164 = 0;
    std::vector<unsigned __int64>::push_back(296 * v59 + *(_QWORD *)(v7 + 144) + 224LL, &v164);
    v164 = 0;
    std::vector<unsigned __int64>::push_back(296 * v59 + *(_QWORD *)(v7 + 144) + 248LL, &v164);
    v61 = *(_QWORD *)(v7 + 144) + 296 * v59;
    v62 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 72LL))(a2, v168);
    std::vector<XPerfAddIn::CDriverDelayInfoSource::CDelayDataPtr>::push_back(v61 + 272, v62);
    return 0;
  }
  if ( a3 != ETWGUID_DXGKREFERENCEALLOCATIONS )
  {
    if ( a3 == (__int64 *)&ETWGUID_DXGKSCHEDULER_DMAPACKET )
    {
      if ( *(_BYTE *)(a4 + 45) == 1 )
      {
        if ( v43 )
        {
          v71 = &v174;
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x24u )
            return 262403;
          v71 = *(__int64 **)(a4 + 96);
        }
        if ( *((_DWORD *)v71 + 2) == 3 )
          return 0;
        v72 = v71 + 3;
        if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
                v7 + 128,
                v71 + 3,
                56,
                ETWGUID_DXGKRENDER) )
        {
          if ( !*(_BYTE *)(v7 + 120) )
            XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
              v7 + 32,
              a2,
              L"submission of non-created dma buffer %lld",
              *v72);
          v75 = *v72;
          v76 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 72LL))(a2, v168);
          XPerfAddIn::CDMABufferInfoSource::addDMA(v7, *v76, 5, v75, 0);
        }
        if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
                v7 + 208,
                v71,
                v73,
                v74) )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            v7 + 32,
            a2,
            L"unrecognized context %lld during submition",
            *v71);
          return 262403;
        }
        v77 = *(unsigned int *)std::map<unsigned __int64,unsigned int>::operator[]((int)v7 + 128);
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v164);
        v78 = 296 * v77;
        *(_QWORD *)(*(_QWORD *)(v7 + 144) + v78 + 8) = v164;
        *(_QWORD *)(*(_QWORD *)(v7 + 144) + v78 + 32) = *(__int64 *)((char *)v71 + 12);
        *(_DWORD *)(*(_QWORD *)(v7 + 144) + v78 + 60) = *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[]((int)v7 + 208);
        v79 = std::map<XPerfAddIn::DX::IDMABufferInfoSource::FullEngineId,XPerfAddIn::CDMABufferInfoSource::EngineState>::operator[](
                v7 + 224,
                296 * v77 + *(_QWORD *)(v7 + 144) + 60LL);
        *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[](v79) = v77;
        std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::erase(
          v7 + 128,
          v71 + 3);
        return 0;
      }
      if ( !*(_BYTE *)(a4 + 45) || v43 && *(_WORD *)(a4 + 40) == 177 )
      {
        if ( v43 )
        {
          v80 = &v174;
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x20u )
            return 262403;
          v80 = *(__int64 **)(a4 + 96);
        }
        if ( *((_DWORD *)v80 + 2) == 3 )
          return 0;
        if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
                v7 + 208,
                v80,
                56,
                ETWGUID_DXGKRENDER) )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            v7 + 32,
            a2,
            L"unrecognized context %lld during completion",
            *v80);
          return 262403;
        }
        v81 = std::map<unsigned __int64,unsigned int>::operator[]((int)v7 + 208);
        v82 = std::map<XPerfAddIn::DX::IDMABufferInfoSource::FullEngineId,XPerfAddIn::CDMABufferInfoSource::EngineState>::operator[](
                v7 + 224,
                v81);
        v167 = (_QWORD *)v82;
        if ( std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
               v82,
               (char *)v80 + 12,
               v83,
               v84) )
        {
          v85 = *(unsigned int *)std::map<unsigned __int64,unsigned int>::operator[](v82);
          XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v166);
          v86 = (_QWORD *)(v7 + 144);
          v87 = 296 * v85;
          v164 = v87;
          *(_QWORD *)(*(_QWORD *)(v7 + 144) + v87 + 24) = v166;
          v88 = *(_QWORD *)(v7 + 144);
          v89 = *(_QWORD *)(v88 + 296 * v85 + 24) - *(_QWORD *)(v88 + 296 * v85);
          if ( *(_QWORD *)(v7 + 384) > v89 )
            v89 = *(_QWORD *)(v7 + 384);
          *(_QWORD *)(v7 + 384) = v89;
          if ( *(_QWORD *)(v88 + v87 + 16) == XPerfCore::TimeStamp::Min )
            *(_QWORD *)(v88 + v87 + 16) = *(_QWORD *)(v88 + v87 + 8);
          std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::erase(
            v167,
            (char *)v80 + 12);
          if ( *(_DWORD *)(296 * v85 + *(_QWORD *)(v7 + 144) + 56) != 5 )
            *(_BYTE *)(v7 + 120) = 0;
          if ( *((_DWORD *)v80 + 6) )
          {
            std::vector<XPerfAddIn::CDMABufferInfoSource::CDMABuffer>::push_back(v7 + 144);
            *(_BYTE *)(*v86 + v164 + 168) = 1;
            *(_QWORD *)(*(_QWORD *)(v7 + 152) - 288LL) = XPerfCore::TimeStamp::Min;
            *(_QWORD *)(*(_QWORD *)(v7 + 152) - 280LL) = XPerfCore::TimeStamp::Min;
            *(_QWORD *)(*(_QWORD *)(v7 + 152) - 272LL) = XPerfCore::TimeStamp::Min;
            v90 = -1857283155 * ((__int64)(*(_QWORD *)(v7 + 152) - *(_QWORD *)(v7 + 144)) >> 3) - 1;
            *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[]((int)v7 + 128) = v90;
            LODWORD(v166) = v85;
            if ( std::_Tree<std::_Tmap_traits<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>,std::less<int>,std::allocator<std::pair<int const,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>,0>>::count(
                   v7 + 288,
                   &v166) )
            {
              LODWORD(v166) = v85;
              v168[0] = std::map<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>::operator[](
                          v7 + 288,
                          &v166);
              LODWORD(v166) = -1857283155 * ((__int64)(*(_QWORD *)(v7 + 152) - *(_QWORD *)(v7 + 144)) >> 3) - 1;
              v91 = std::map<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>::operator[](v7 + 288, &v166);
              std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::operator=(v91, v168[0]);
              LODWORD(v166) = v85;
              std::_Tree<std::_Tmap_traits<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>,std::less<int>,std::allocator<std::pair<int const,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>,0>>::erase(
                v7 + 288,
                &v166);
            }
            v92 = v164;
            for ( i = *(_QWORD *)(*v86 + v164 + 248); i != *(_QWORD *)(*v86 + v92 + 256); i += 8 )
            {
              if ( *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[]((int)v7 + 304) == (_DWORD)v85 )
              {
                LODWORD(v166) = -1857283155 * ((__int64)(*(_QWORD *)(v7 + 152) - *(_QWORD *)(v7 + 144)) >> 3) - 1;
                *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[]((int)v7 + 304) = (_DWORD)v166;
              }
              v92 = v164;
            }
          }
          else
          {
            LODWORD(v166) = v85;
            if ( std::_Tree<std::_Tmap_traits<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>,std::less<int>,std::allocator<std::pair<int const,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>,0>>::count(
                   v7 + 288,
                   &v166) )
            {
              LODWORD(v166) = v85;
              v94 = (_QWORD *)std::map<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>::operator[](
                                v7 + 288,
                                &v166);
              for ( j = (_QWORD *)*v94;
                    ;
                    std::deque<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::push_back(
                      *(_QWORD *)(*(_QWORD *)(v7 + 320) + 40LL * *(unsigned __int8 *)(j[2] + 48LL) - 40)
                    - 40LL
                    + 56LL * *(unsigned __int8 *)(j[2] + 49LL),
                      j + 2) )
              {
                j = (_QWORD *)*j;
                if ( j == (_QWORD *)*v94 )
                  break;
                XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
                *(_QWORD *)(j[2] + 8LL) = v168[0];
              }
              LODWORD(v166) = v85;
              std::_Tree<std::_Tmap_traits<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>,std::less<int>,std::allocator<std::pair<int const,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>,0>>::erase(
                v7 + 288,
                &v166);
            }
          }
          v82 = (__int64)v167;
        }
        else if ( !*(_BYTE *)(v7 + 120) )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            v7 + 32,
            a2,
            L"Completion of never-submitted fenceID %lld",
            *v80);
        }
        if ( *(_QWORD *)(v82 + 8) )
        {
          v96 = -1;
          v97 = XPerfCore::TimeStamp::Max;
          v98 = **(_QWORD **)v82;
          while ( v98 != *(_QWORD *)v82 )
          {
            v99 = 296LL * *(unsigned int *)(v98 + 40);
            v100 = *(_QWORD *)(v7 + 144);
            v101 = *(_QWORD *)(v99 + v100 + 16);
            if ( v101 == XPerfCore::TimeStamp::Min )
            {
              if ( *(_QWORD *)(v99 + v100 + 8) < v97 )
              {
                v97 = *(_QWORD *)(v99 + v100 + 8);
                v96 = *(_DWORD *)(v98 + 40);
              }
              if ( !*(_BYTE *)(v98 + 25) )
              {
                if ( *(_BYTE *)(*(_QWORD *)(v98 + 16) + 25LL) )
                {
                  for ( k = *(_QWORD *)(v98 + 8); !*(_BYTE *)(k + 25) && v98 == *(_QWORD *)(k + 16); k = *(_QWORD *)(k + 8) )
                    v98 = k;
                }
                else
                {
                  k = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::set<XPerfAddIn::IProcessInfoSource::VARange *>>>>::_Min();
                }
                v98 = k;
              }
            }
            else
            {
              XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
                v7 + 32,
                a2,
                L"Buffer fenceid %lld remains in queue after starting at %lld -- dropping",
                *(_QWORD *)(v99 + v100 + 32),
                v101 / 1000);
              v98 = *(_QWORD *)std::_Tree<std::_Tset_traits<XPerfAddIn::IProcessInfoSource::ThreadData const *,std::less<XPerfAddIn::IProcessInfoSource::ThreadData const *>,std::allocator<XPerfAddIn::IProcessInfoSource::ThreadData const *>,0>>::erase(
                                 v82,
                                 v168,
                                 v98);
            }
          }
          if ( v96 != -1 )
          {
            XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
            *(_QWORD *)(296LL * v96 + *(_QWORD *)(v7 + 144) + 16) = v168[0];
          }
        }
        return 0;
      }
    }
    if ( a3 == (__int64 *)&ETWGUID_DXGKLOCKALLOCATION )
    {
      if ( v43 )
      {
        v103 = &v174;
      }
      else
      {
        if ( *(_WORD *)(a4 + 86) < 0x18u )
          return 262403;
        v103 = *(__int64 **)(a4 + 96);
      }
      if ( (*((_DWORD *)v103 + 5) & 0x1D2) != 0 )
        return 0;
      v104 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)(v7 + 88) + 32LL))(
               *(_QWORD *)(v7 + 88),
               v103[1],
               *(unsigned int *)(a4 + 12),
               XPerfCore::TimeStamp::Max);
      v164 = v104;
      if ( !v104 )
        goto LABEL_212;
      if ( *(_QWORD *)(v7 + 184) == *(_QWORD *)(v7 + 176) )
        return 2147549183LL;
      v171 = 0;
      *(_QWORD *)&v170 = XPerfCore::TimeStamp::Min;
      *((_QWORD *)&v170 + 1) = XPerfCore::TimeStamp::Max;
      std::vector<XPerfAddIn::DX::IDMABufferInfoSource::LockUnLock>::push_back(v7 + 168, &v170);
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
      *(_QWORD *)(*(_QWORD *)(v7 + 176) - 32LL) = v168[0];
      *(_QWORD *)(*(_QWORD *)(v7 + 176) - 16LL) = v104;
      v106 = *(_QWORD *)(v7 + 80);
      v107 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v106 + 48LL);
      v108 = *(_DWORD *)(a4 + 8);
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
      *(_QWORD *)(*(_QWORD *)(v7 + 176) - 8LL) = v107(v106, v168, v108, 0);
      v109 = *(_QWORD *)(v7 + 176) - 32LL;
      v110 = (__int64 *)std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::operator[]((int)v7 + 192);
LABEL_267:
      *v110 = v109;
      return 0;
    }
    if ( a3 == ETWGUID_DXGKUNLOCKALLOCATION )
    {
      if ( v43 )
      {
        v103 = &v174;
      }
      else
      {
        if ( *(_WORD *)(a4 + 86) < 0x14u )
          return 262403;
        v103 = *(__int64 **)(a4 + 96);
      }
      v111 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)(v7 + 88) + 32LL))(
               *(_QWORD *)(v7 + 88),
               v103[1],
               *(unsigned int *)(a4 + 12),
               XPerfCore::TimeStamp::Max);
      v164 = v111;
      if ( v111 )
      {
        if ( std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
               v7 + 192,
               &v164,
               v112,
               v113) )
        {
          v114 = *(_QWORD **)std::map<XPerfAddIn::IProcessInfoSource::ThreadData const *,XPerfCore::TimeStampDelta>::operator[]((int)v7 + 192);
          XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
          v115 = v168[0];
          v114[1] = v168[0];
          v116 = v115 - *v114;
          if ( *(_QWORD *)(v7 + 400) > v116 )
            v116 = *(_QWORD *)(v7 + 400);
          *(_QWORD *)(v7 + 400) = v116;
          std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::erase(
            v7 + 192,
            &v164);
        }
        else if ( !*(_BYTE *)(v7 + 120) )
        {
          XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
            v7 + 32,
            a2,
            L"Unlock of allocation %lld which was never locked",
            *(_QWORD *)(v111 + 16));
        }
        return 0;
      }
LABEL_212:
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
      XPerfAddIn::CDMABufferInfoSource::reportBadAllocationHandle(
        v105,
        v103[1],
        "unlock allocation",
        (const struct TimeStamp *)v168,
        0);
      return 262400;
    }
    if ( a3 != (__int64 *)&ETWGUID_DXGKFLIP )
    {
      if ( a3 == ETWGUID_DXGKSCHEDULER_VSYNC_INTERRUPT )
      {
        if ( v43 )
        {
          v136 = &v174;
        }
        else
        {
          if ( *(_WORD *)(a4 + 86) < 0x14u )
            return 262403;
          v136 = *(__int64 **)(a4 + 96);
        }
        v137 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v7 + 96) + 32LL))(
                 *(_QWORD *)(v7 + 96),
                 *v136,
                 56);
        if ( !v137 )
          return 262400;
        v138 = v137;
        if ( v137 > 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v7 + 328) - *(_QWORD *)(v7 + 320)) >> 3) )
          return 262400;
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
        v109 = v168[0];
        v110 = (__int64 *)std::map<unsigned int,XPerfCore::TimeStamp>::operator[]((unsigned int)*(_QWORD *)(v7 + 320) + 8 * (v138 + 4 * v138 - 2));
        goto LABEL_267;
      }
      if ( a3 != (__int64 *)&ETWGUID_DXGKSCHEDULER_VSYNC_DPC )
        return 0;
      if ( v43 )
      {
        v139 = &v174;
      }
      else
      {
        if ( *(_WORD *)(a4 + 86) < 0x38u )
          return 262403;
        v139 = *(__int64 **)(a4 + 96);
      }
      v140 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v7 + 96) + 32LL))(
               *(_QWORD *)(v7 + 96),
               *v139,
               56);
      v165 = v140;
      if ( !v140 )
        return 262400;
      v141 = *(_QWORD *)(v7 + 320);
      if ( v140 > 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(v7 + 328) - v141) >> 3) )
        return 262400;
      v142 = 5LL * v140;
      v143 = (__int64 *)std::map<unsigned int,XPerfCore::TimeStamp>::operator[](v141 - 16 + 40 * v140);
      v144 = *v143;
      if ( *v143 == XPerfCore::TimeStamp::Min )
      {
        XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(v7 + 32, a2, L"VSync DPC without ISR");
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
        v144 = v168[0];
      }
      v145 = *(_QWORD *)(v7 + 320);
      v146 = *(_QWORD *)(v145 + 8 * v142 - 40);
      v147 = *((unsigned int *)v139 + 5);
      if ( v147 < 0x6DB6DB6DB6DB6DB7LL * ((*(_QWORD *)(v145 + 8 * v142 - 32) - v146) >> 3) )
      {
        v148 = v146 + 56 * v147;
        if ( *(_QWORD *)(v148 + 48) )
        {
          std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
            v168,
            *(_QWORD *)(v148 + 40),
            v148 + 16);
          if ( v168[0] )
            v149 = *(_QWORD *)v168[0];
          else
            v149 = 0;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v149 + 8) + 8 * ((v169 >> 1) & (*(_QWORD *)(v149 + 16) - 1LL)))
                                + 8 * (v169 & 1))
                    + 24LL) = v144;
          std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
            v168,
            *(_QWORD *)(v148 + 40),
            v148 + 16);
          if ( v168[0] )
            v150 = *(_QWORD *)v168[0];
          else
            v150 = 0;
          v168[0] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v150 + 8) + 8 * ((v169 >> 1) & (*(_QWORD *)(v150 + 16) - 1LL)))
                              + 8 * (v169 & 1));
          std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
            &v170,
            *(_QWORD *)(v148 + 40),
            v148 + 16);
          if ( (_QWORD)v170 )
            v151 = *(_QWORD *)v170;
          else
            v151 = 0;
          v152 = *(_QWORD *)(v7 + 392);
          if ( v152 <= *(_QWORD *)(v168[0] + 24LL)
                     - **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v151 + 8)
                                               + 8 * (((unsigned __int64)v171 >> 1) & (*(_QWORD *)(v151 + 16) - 1LL)))
                                   + 8 * (v171 & 1)) )
          {
            std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
              &v170,
              *(_QWORD *)(v148 + 40),
              v148 + 16);
            if ( (_QWORD)v170 )
              v153 = *(_QWORD *)v170;
            else
              v153 = 0;
            v168[0] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v153 + 8)
                                            + 8 * (((unsigned __int64)v171 >> 1) & (*(_QWORD *)(v153 + 16) - 1LL)))
                                + 8 * (v171 & 1));
            std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>>(
              &v170,
              *(_QWORD *)(v148 + 40),
              v148 + 16);
            if ( (_QWORD)v170 )
              v154 = *(_QWORD *)v170;
            else
              v154 = 0;
            v152 = *(_QWORD *)(v168[0] + 24LL)
                 - **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v154 + 8)
                                           + 8 * (((unsigned __int64)v171 >> 1) & (*(_QWORD *)(v154 + 16) - 1LL)))
                               + 8 * (v171 & 1));
          }
          *(_QWORD *)(v7 + 392) = v152;
          std::deque<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::pop_front(v148 + 16);
        }
        for ( m = *(_QWORD **)v148; ; *(_QWORD *)(m[2] + 16LL) = v144 )
        {
          m = (_QWORD *)*m;
          if ( m == *(_QWORD **)v148 )
            break;
        }
        std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::clear(v148);
      }
      if ( *(_QWORD *)(v7 + 376) == *(_QWORD *)(v7 + 368) )
        return 2147549183LL;
      v168[1] = 0;
      v168[0] = 0;
      std::vector<XPerfAddIn::DX::Warning>::push_back(v7 + 360, v168);
      *(_QWORD *)(*(_QWORD *)(v7 + 368) - 16LL) = v144;
      *(_BYTE *)(*(_QWORD *)(v7 + 368) - 8LL) = v165;
      *(_BYTE *)(*(_QWORD *)(v7 + 368) - 7LL) = *((_BYTE *)v139 + 20) + 1;
      v135 = *(_QWORD *)(v7 + 368);
LABEL_257:
      *(_DWORD *)(v135 - 6) = 0;
      *(_WORD *)(v135 - 2) = 0;
      return 0;
    }
    if ( v43 )
    {
      v117 = &v174;
    }
    else
    {
      if ( *(_WORD *)(a4 + 86) < 0x1Au )
        return 262403;
      v117 = *(__int64 **)(a4 + 96);
    }
    if ( *v117 )
    {
      v118 = *(_QWORD *)(v7 + 80);
      v164 = *(_QWORD *)(*(_QWORD *)v118 + 48LL);
      LODWORD(v166) = *(_DWORD *)(a4 + 8);
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
      v164 = ((__int64 (__fastcall *)(__int64, _QWORD *, _QWORD, _QWORD))v164)(v118, v168, (unsigned int)v166, 0);
      v119 = *v117;
      v120 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)a2 + 72LL))(a2, &v167);
      XPerfAddIn::CDMABufferInfoSource::addDMA(v7, *v120, 3, v119, v164);
    }
    if ( *(_QWORD *)(v7 + 280) == *(_QWORD *)(v7 + 272) )
      return 2147549183LL;
    v164 = *(__int64 *)((char *)v117 + 12);
    v121 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)(v7 + 88) + 32LL))(
             *(_QWORD *)(v7 + 88),
             v164,
             *(unsigned int *)(a4 + 12),
             XPerfCore::TimeStamp::Max);
    if ( !v121 )
    {
      XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
      XPerfAddIn::CDMABufferInfoSource::reportBadAllocationHandle(
        v122,
        *(__int64 *)((char *)v117 + 12),
        "flip",
        (const struct TimeStamp *)v168,
        0);
      return 262400;
    }
    v172 = 0;
    v173 = 0;
    v170 = 0;
    v171 = 0;
    std::vector<XPerfAddIn::DX::IDMABufferInfoSource::Flip>::push_back(v7 + 264, &v170);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
    *(_QWORD *)(*(_QWORD *)(v7 + 272) - 56LL) = v168[0];
    *(_QWORD *)(*(_QWORD *)(v7 + 272) - 24LL) = v121;
    v123 = (_QWORD *)XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
    v124 = XPerfAddIn::Alloc_SegmentAt(v121, *v123);
    if ( !v124 || (*(_BYTE *)(v124 + 8) & 1) != 0 )
    {
      XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
        v7 + 32,
        a2,
        L"Flip of allocation %llx from system memory",
        *(_QWORD *)(v121 + 16));
      v125 = *(_BYTE *)(v121 + 108);
    }
    else
    {
      v125 = *(_BYTE *)(v124 + 12);
    }
    *(_BYTE *)(*(_QWORD *)(v7 + 272) - 8LL) = v125;
    *(_BYTE *)(*(_QWORD *)(v7 + 272) - 7LL) = *((_BYTE *)v117 + 8) + 1;
    v126 = *(_QWORD *)(v7 + 80);
    v127 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v126 + 48LL);
    v128 = *(_DWORD *)(a4 + 8);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
    *(_QWORD *)(*(_QWORD *)(v7 + 272) - 16LL) = v127(v126, v168, v128, 0);
    v130 = (_QWORD *)(v7 + 320);
    if ( *(unsigned __int8 *)(*(_QWORD *)(v7 + 272) - 8LL) > 0xCCCCCCCCCCCCCCCDuLL
                                                           * ((__int64)(*(_QWORD *)(v7 + 328) - *(_QWORD *)(v7 + 320)) >> 3) )
      std::vector<XPerfAddIn::CDMABufferInfoSource::AdapterState>::resize(v7 + 320);
    v131 = (_QWORD *)(*v130 + 40 * (*(unsigned __int8 *)(*(_QWORD *)(v7 + 272) - 8LL) - 1LL));
    v132 = *((unsigned int *)v117 + 2);
    if ( v132 >= 0x6DB6DB6DB6DB6DB7LL * ((__int64)(v131[1] - *v131) >> 3) )
      std::vector<XPerfAddIn::CDMABufferInfoSource::AdapterState::MonitorState>::resize(v131, (unsigned int)(v132 + 1));
    if ( *v117 )
    {
      v133 = v7 + 128;
    }
    else
    {
      if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
              v7 + 304,
              &v164,
              v132,
              v129)
        || *(_QWORD *)(296LL * *(unsigned int *)std::map<unsigned __int64,unsigned int>::operator[]((int)v7 + 304)
                     + *(_QWORD *)(v7 + 144)
                     + 24) != XPerfCore::TimeStamp::Min )
      {
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
        *(_QWORD *)(*(_QWORD *)(v7 + 272) - 48LL) = v168[0];
        v168[0] = *(_QWORD *)(v7 + 272) - 56LL;
        std::deque<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::push_back(
          *(_QWORD *)(*v130 + 40LL * *(unsigned __int8 *)(v168[0] + 48LL) - 40)
        + 16LL
        + 56LL * *((unsigned int *)v117 + 2),
          v168);
        goto LABEL_256;
      }
      v133 = v7 + 304;
    }
    LODWORD(v166) = *(_DWORD *)std::map<unsigned __int64,unsigned int>::operator[](v133);
    v134 = std::map<int,std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>>::operator[](v7 + 288, &v166);
    v168[0] = *(_QWORD *)(v7 + 272) - 56LL;
    std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::push_back(v134, v168);
LABEL_256:
    v168[0] = *(_QWORD *)(v7 + 272) - 56LL;
    std::list<XPerfAddIn::DX::IDMABufferInfoSource::Flip *>::push_back(
      *(_QWORD *)(*v130 + 40LL * *(unsigned __int8 *)(v168[0] + 48LL) - 40) + 56LL * *((unsigned int *)v117 + 2),
      v168);
    v135 = *(_QWORD *)(v7 + 272);
    goto LABEL_257;
  }
  if ( *(_WORD *)(a4 + 86) < 0x18u )
    return 262403;
  v63 = &v174;
  if ( !v43 )
    v63 = *(__int64 **)(a4 + 96);
  if ( !std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned int,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned int>>,0>>::count(
          v7 + 128,
          v63 + 1,
          56,
          ETWGUID_DXGKRENDER) )
  {
    if ( !*(_BYTE *)(v7 + 120) )
      XPerfAddIn::warner::warn<XPerfCore::ICursor const *>(
        v7 + 32,
        a2,
        L"allocation reference listing for never-created dma buffer %lld",
        v63[1]);
    v64 = *(_QWORD *)(v7 + 80);
    v167 = *(_QWORD **)(*(_QWORD *)v64 + 48LL);
    v65 = *(_DWORD *)(a4 + 8);
    XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, &v164);
    v66 = ((__int64 (__fastcall *)(__int64, __int64 *, _QWORD, _QWORD))v167)(v64, &v164, v65, 0);
    v67 = v63[1];
    v68 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 72LL))(a2, v168);
    XPerfAddIn::CDMABufferInfoSource::addDMA(v7, *v68, 5, v67, v66);
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 80LL))(a2) == 4 )
  {
    v69 = (_QWORD *)XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
    result = XPerfAddIn::CDMABufferInfoSource::handleReferences<_DXGKETW_REFERENCEALLOCATIONRECORD32>(v7, a4, *v69);
    if ( (int)result < 0 )
      return result;
    return 0;
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 80LL))(a2) != 8 )
    return 2147549183LL;
  v70 = (_QWORD *)XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v168);
  result = XPerfAddIn::CDMABufferInfoSource::handleReferences<_DXGKETW_REFERECENALLOCATIONRECORD64>(v7, a4, *v70);
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180052694  push    rbx
0x180052696  push    rsi
0x180052697  push    rdi
0x180052698  push    r12
0x18005269a  push    r13
0x18005269c  push    r14
0x18005269e  push    r15
0x1800526a0  sub     rsp, 0CD0h
0x1800526a7  mov     rax, cs:__security_cookie
0x1800526ae  xor     rax, rsp
0x1800526b1  mov     [rsp+0D08h+var_48], rax
0x1800526b9  mov     rbx, r9
0x1800526bc  mov     r12, r8
0x1800526bf  mov     r15, rdx
0x1800526c2  mov     rsi, rcx
0x1800526c5  mov     [rsp+0D08h+var_CD8], rcx
0x1800526ca  xor     edx, edx; Val
0x1800526cc  mov     r8d, 0C18h; Size
0x1800526d2  lea     rcx, [rsp+0D08h+var_C68]; void *
0x1800526da  call    memset_0
0x1800526df  lea     rax, DxgkControlGuid
0x1800526e6  cmp     r12, rax
0x1800526e9  jnz     loc_180052E18
0x1800526ef  movzx   ecx, word ptr [rbx+28h]
0x1800526f3  cmp     ecx, 2Bh ; '+'
0x1800526f6  ja      loc_180052A72
0x1800526fc  jz      loc_18005294D
0x180052702  sub     ecx, 11h
0x180052705  jz      loc_1800528BC
0x18005270b  sub     ecx, 0Ah
0x18005270e  jz      loc_18005285F
0x180052714  sub     ecx, 2
0x180052717  jz      loc_18005285F
0x18005271d  sub     ecx, 1
0x180052720  jz      loc_1800527CF
0x180052726  sub     ecx, 2
0x180052729  jz      loc_1800527CF
0x18005272f  sub     ecx, 9
0x180052732  jz      short loc_18005277F
0x180052734  cmp     ecx, 1
0x180052737  jnz     loc_180052DDE
0x18005273d  cmp     word ptr [rbx+56h], 14h
0x180052742  jnb     short loc_18005274E
0x180052744  mov     eax, 40103h
0x180052749  jmp     loc_1800544DA
0x18005274e  mov     rcx, [rbx+60h]
0x180052752  mov     rax, [rcx]
0x180052755  mov     [rsp+0D08h+var_C68], rax
0x18005275d  mov     rax, [rcx+8]
0x180052761  mov     [rsp+0D08h+var_C60], rax
0x180052769  mov     eax, [rcx+10h]
0x18005276c  mov     dword ptr [rsp+0D08h+var_C58], eax
0x180052773  lea     r12, ETWGUID_DXGKUNLOCKALLOCATION
0x18005277a  jmp     loc_180052DDE
0x18005277f  mov     edx, 18h
0x180052784  cmp     [rbx+56h], dx
0x180052788  jnb     short loc_180052794
0x18005278a  mov     eax, 40103h
0x18005278f  jmp     loc_1800544DA
0x180052794  mov     rcx, [rbx+60h]
0x180052798  mov     rax, [rcx]
0x18005279b  mov     [rsp+0D08h+var_C68], rax
0x1800527a3  mov     rax, [rcx+8]
0x1800527a7  mov     [rsp+0D08h+var_C60], rax
0x1800527af  mov     eax, [rcx+10h]
0x1800527b2  mov     dword ptr [rsp+0D08h+var_C58], eax
0x1800527b9  mov     eax, [rcx+14h]
0x1800527bc  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x1800527c3  lea     r12, ETWGUID_DXGKLOCKALLOCATION
0x1800527ca  jmp     loc_180052DE3
0x1800527cf  cmp     word ptr [rbx+56h], 30h ; '0'
0x1800527d4  jnb     short loc_1800527E0
0x1800527d6  mov     eax, 40103h
0x1800527db  jmp     loc_1800544DA
0x1800527e0  mov     rcx, [rbx+60h]
0x1800527e4  mov     rax, [rcx]
0x1800527e7  mov     [rsp+0D08h+var_C68], rax
0x1800527ef  mov     eax, [rcx+8]
0x1800527f2  mov     dword ptr [rsp+0D08h+var_C60], eax
0x1800527f9  mov     eax, [rcx+0Ch]
0x1800527fc  mov     dword ptr [rsp+0D08h+var_C60+4], eax
0x180052803  mov     eax, [rcx+10h]
0x180052806  mov     dword ptr [rsp+0D08h+var_C58], eax
0x18005280d  mov     eax, [rcx+14h]
0x180052810  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180052817  mov     eax, [rcx+18h]
0x18005281a  mov     [rsp+0B8h], eax
0x180052821  mov     eax, [rcx+1Ch]
0x180052824  mov     [rsp+0BCh], eax
0x18005282b  mov     eax, [rcx+20h]
0x18005282e  mov     [rsp+0C0h], eax
0x180052835  mov     eax, [rcx+24h]
0x180052838  mov     dword ptr [rsp+0D08h+var_C44], eax
0x18005283f  mov     rax, [rcx+28h]
0x180052843  mov     [rsp+0D08h+var_C44+4], rax
0x18005284b  lea     rcx, ETWGUID_DXGKCONTEXT
0x180052852  mov     r12, rcx
0x180052855  mov     edx, 18h
0x18005285a  jmp     loc_180052DEA
0x18005285f  cmp     word ptr [rbx+56h], 1Ch
0x180052864  jnb     short loc_180052870
0x180052866  mov     eax, 40103h
0x18005286b  jmp     loc_1800544DA
0x180052870  mov     rcx, [rbx+60h]
0x180052874  mov     rax, [rcx]
0x180052877  mov     [rsp+0D08h+var_C68], rax
0x18005287f  mov     rax, [rcx+8]
0x180052883  mov     [rsp+0D08h+var_C60], rax
0x18005288b  mov     eax, [rcx+10h]
0x18005288e  mov     dword ptr [rsp+0D08h+var_C58], eax
0x180052895  mov     rax, [rcx+14h]
0x180052899  mov     [rsp+0D08h+var_C58+4], rax
0x1800528a1  lea     rax, ETWGUID_DXGKDEVICE
0x1800528a8  mov     r12, rax
0x1800528ab  mov     edx, 18h
0x1800528b0  lea     rcx, ETWGUID_DXGKCONTEXT
0x1800528b7  jmp     loc_180052DF1
0x1800528bc  mov     r8d, 38h ; '8'
0x1800528c2  cmp     [rbx+56h], r8w
0x1800528c7  jnb     short loc_1800528D3
0x1800528c9  mov     eax, 40103h
0x1800528ce  jmp     loc_1800544DA
0x1800528d3  mov     rcx, [rbx+60h]
0x1800528d7  mov     rax, [rcx]
0x1800528da  mov     [rsp+0D08h+var_C68], rax
0x1800528e2  mov     eax, [rcx+8]
0x1800528e5  mov     dword ptr [rsp+0D08h+var_C60], eax
0x1800528ec  mov     rax, [rcx+0Ch]
0x1800528f0  mov     [rsp+0D08h+var_C60+4], rax
0x1800528f8  mov     eax, [rcx+14h]
0x1800528fb  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180052902  mov     eax, [rcx+18h]
0x180052905  mov     [rsp+0B8h], eax
0x18005290c  mov     rax, [rcx+1Ch]
0x180052910  mov     [rsp+0BCh], rax
0x180052918  mov     rax, [rcx+24h]
0x18005291c  mov     [rsp+0D08h+var_C44], rax
0x180052924  mov     eax, [rcx+2Ch]
0x180052927  mov     [rsp+0D08h+var_C3C], eax
0x18005292e  lea     r12, ETWGUID_DXGKSCHEDULER_VSYNC_DPC
0x180052935  mov     edx, 18h
0x18005293a  lea     rcx, ETWGUID_DXGKCONTEXT
0x180052941  lea     rax, ETWGUID_DXGKDEVICE
0x180052948  jmp     loc_180052DF7
0x18005294d  cmp     word ptr [rbx+56h], 14h
0x180052952  jnb     short loc_18005295E
0x180052954  mov     eax, 40103h
0x180052959  jmp     loc_1800544DA
0x18005295e  mov     r12, [rbx+60h]
0x180052962  mov     rax, [r12]
0x180052966  mov     [rsp+0D08h+var_C68], rax
0x18005296e  mov     rax, [r12+8]
0x180052973  mov     [rsp+0D08h+var_C60], rax
0x18005297b  mov     edi, [r12+10h]
0x180052980  mov     dword ptr [rsp+0D08h+var_C58], edi
0x180052987  xor     r14d, r14d
0x18005298a  test    r15, r15
0x18005298d  jnz     short loc_180052999
0x18005298f  mov     eax, 40100h
0x180052994  jmp     loc_1800544DA
0x180052999  mov     rax, [r15]
0x18005299c  mov     rcx, r15
0x18005299f  mov     rax, [rax+50h]
0x1800529a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529a8  mov     ecx, [r12+10h]
0x1800529ad  cmp     eax, 4
0x1800529b0  jnz     short loc_1800529F8
0x1800529b2  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x1800529b9  lea     r8, [r12+rcx*4]
0x1800529bd  movzx   edx, r14w
0x1800529c1  test    edi, edi
0x1800529c3  jz      loc_180052A4A
0x1800529c9  lea     edi, [rax-3]
0x1800529cc  movzx   ecx, dx
0x1800529cf  mov     eax, [r12+rcx*4+14h]
0x1800529d4  xor     eax, [r8+rcx*4+14h]
0x1800529d9  and     eax, edi
0x1800529db  xor     eax, [r12+rcx*4+14h]
0x1800529e0  mov     [rsp+rcx*4+0B8h], eax
0x1800529e7  add     dx, di
0x1800529ea  movzx   eax, dx
0x1800529ed  cmp     eax, dword ptr [rsp+0D08h+var_C58]
0x1800529f4  jb      short loc_1800529CC
0x1800529f6  jmp     short loc_180052A4F
0x1800529f8  mov     dword ptr [rsp+0D08h+var_C58+4], 0Ch
0x180052a03  lea     r9, [r12+rcx*8]
0x180052a07  movzx   r8d, r14w
0x180052a0b  test    edi, edi
0x180052a0d  jz      short loc_180052A4A
0x180052a0f  mov     edi, 1
0x180052a14  movzx   ecx, r8w
0x180052a18  lea     rdx, [rcx+rcx*2]
0x180052a1c  mov     rax, [r12+rcx*8+14h]
0x180052a21  mov     [rsp+rdx*4+0B8h], rax
0x180052a29  xor     eax, [r9+rcx*4+14h]
0x180052a2e  and     eax, edi
0x180052a30  xor     [rsp+rdx*4+0B8h], eax
0x180052a37  add     r8w, di
0x180052a3b  movzx   eax, r8w
0x180052a3f  cmp     eax, dword ptr [rsp+0D08h+var_C58]
0x180052a46  jb      short loc_180052A14
0x180052a48  jmp     short loc_180052A4F
0x180052a4a  mov     edi, 1
0x180052a4f  lea     r12, ETWGUID_DXGKREFERENCEALLOCATIONS
0x180052a56  mov     edx, 18h
0x180052a5b  lea     rcx, ETWGUID_DXGKCONTEXT
0x180052a62  lea     rax, ETWGUID_DXGKDEVICE
0x180052a69  lea     r8d, [rdx+20h]
0x180052a6d  jmp     loc_180052DFF
0x180052a72  sub     ecx, 32h ; '2'
0x180052a75  jz      loc_180052D7D
0x180052a7b  sub     ecx, 74h ; 't'
0x180052a7e  jz      loc_180052D53
0x180052a84  sub     ecx, 2
0x180052a87  jz      loc_180052CD6
0x180052a8d  sub     ecx, 1
0x180052a90  jz      loc_180052C7D
0x180052a96  sub     ecx, 6
0x180052a99  jz      loc_180052BC8
0x180052a9f  sub     ecx, 2
0x180052aa2  jz      short loc_180052AEF
0x180052aa4  cmp     ecx, 4
0x180052aa7  jnz     loc_180052DDE
0x180052aad  cmp     word ptr [rbx+56h], 14h
0x180052ab2  jnb     short loc_180052ABE
0x180052ab4  mov     eax, 40103h
0x180052ab9  jmp     loc_1800544DA
0x180052abe  mov     rcx, [rbx+60h]
0x180052ac2  mov     rax, [rcx]
0x180052ac5  mov     [rsp+0D08h+var_C68], rax
0x180052acd  mov     eax, [rcx+8]
0x180052ad0  mov     dword ptr [rsp+0D08h+var_C60], eax
0x180052ad7  mov     rax, [rcx+0Ch]
0x180052adb  mov     [rsp+0D08h+var_C60+4], rax
0x180052ae3  lea     r12, ETWGUID_DXGKSCHEDULER_VSYNC_INTERRUPT
0x180052aea  jmp     loc_180052DDE
0x180052aef  xor     r14d, r14d
0x180052af2  cmp     [rbx+2Ah], r14b
0x180052af6  jnz     short loc_180052B44
0x180052af8  cmp     word ptr [rbx+56h], 20h ; ' '
0x180052afd  jnb     short loc_180052B09
0x180052aff  mov     eax, 40103h
0x180052b04  jmp     loc_1800544DA
0x180052b09  mov     rcx, [rbx+60h]
0x180052b0d  mov     rax, [rcx]
0x180052b10  mov     [rsp+0D08h+var_C68], rax
0x180052b18  mov     eax, [rcx+8]
0x180052b1b  mov     dword ptr [rsp+0D08h+var_C60], eax
0x180052b22  mov     rax, [rcx+0Ch]
0x180052b26  mov     [rsp+0D08h+var_C60+4], rax
0x180052b2e  mov     eax, [rcx+14h]
0x180052b31  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180052b38  mov     eax, r14d
0x180052b3b  cmp     [rcx+18h], r14d
0x180052b3f  setnz   al
0x180052b42  jmp     short loc_180052B8E
0x180052b44  cmp     word ptr [rbx+56h], 34h ; '4'
0x180052b49  jnb     short loc_180052B55
0x180052b4b  mov     eax, 40103h
0x180052b50  jmp     loc_1800544DA
0x180052b55  mov     rcx, [rbx+60h]
0x180052b59  mov     rax, [rcx]
0x180052b5c  mov     [rsp+0D08h+var_C68], rax
0x180052b64  mov     eax, [rcx+8]
0x180052b67  mov     dword ptr [rsp+0D08h+var_C60], eax
0x180052b6e  mov     rax, [rcx+0Ch]
0x180052b72  mov     [rsp+0D08h+var_C60+4], rax
0x180052b7a  mov     eax, [rcx+14h]
0x180052b7d  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180052b84  mov     eax, r14d
0x180052b87  cmp     dword ptr [rcx+18h], 2
0x180052b8b  setz    al
0x180052b8e  mov     [rsp+0B8h], eax
0x180052b95  mov     eax, [rcx+1Ch]
0x180052b98  mov     [rsp+0BCh], eax
0x180052b9f  lea     r11, ETWGUID_DXGKSCHEDULER_DMAPACKET
0x180052ba6  mov     r12, r11
0x180052ba9  mov     edx, 18h
0x180052bae  lea     rcx, ETWGUID_DXGKCONTEXT
0x180052bb5  lea     rax, ETWGUID_DXGKDEVICE
0x180052bbc  lea     edi, [rdx-17h]
0x180052bbf  lea     r8d, [rdx+20h]
0x180052bc3  jmp     loc_180052E06
0x180052bc8  xor     r14d, r14d
0x180052bcb  cmp     [rbx+2Ah], r14b
0x180052bcf  jnz     short loc_180052C22
0x180052bd1  cmp     word ptr [rbx+56h], 24h ; '$'
0x180052bd6  jnb     short loc_180052BE2
0x180052bd8  mov     eax, 40103h
0x180052bdd  jmp     loc_1800544DA
0x180052be2  mov     rcx, [rbx+60h]
0x180052be6  mov     rax, [rcx]
0x180052be9  mov     [rsp+0D08h+var_C68], rax
0x180052bf1  mov     eax, [rcx+8]
0x180052bf4  mov     dword ptr [rsp+0D08h+var_C60], eax
0x180052bfb  mov     rax, [rcx+0Ch]
0x180052bff  mov     [rsp+0D08h+var_C60+4], rax
0x180052c07  mov     eax, [rcx+14h]
0x180052c0a  mov     dword ptr [rsp+0D08h+var_C58+4], eax
0x180052c11  mov     rax, [rcx+18h]
  ... truncated ...
```

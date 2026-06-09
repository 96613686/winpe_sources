# layout::TextLayout::update_layout

- ea: `0x1800474a0`
- end: `0x18004821e`
- name: `layout::TextLayout::update_layout`
- size: `3454`
- prototype: ``
- caller_count: `10`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180019820`
- `0x18001bff0`
- `0x18001c2b0`
- `0x18001c460`
- `0x18001df30`
- `0x18001e9d0`
- `0x18001f4b0`
- `0x18001f8d0`
- `0x180021240`
- `0x180021e20`

## callees

- `0x180046410`
- `0x180046ca0`
- `0x1800474a0`
- `0x18004a5f0`
- `0x18004cde0`
- `0x1800532a0`
- `0x1800534f0`
- `0x1800dc910`
- `0x18021e1b6`
- `0x180316190`
- `0x180316255`
- `0x180316a30`
- `0x180316ce0`
- `0x180316d00`
- `0x18031716c`

## import_xrefs

- `kernel32!HeapFree` at `0x180047857`
- `kernel32!HeapFree` at `0x1800480e8`
- `kernel32!HeapFree` at `0x180047857`
- `kernel32!HeapFree` at `0x1800480e8`
- `kernel32!GetProcessHeap` at `0x180047849`
- `kernel32!GetProcessHeap` at `0x1800480da`
- `kernel32!GetProcessHeap` at `0x180047849`
- `kernel32!GetProcessHeap` at `0x1800480da`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall layout::TextLayout::update_layout(__int64 a1)
{
  int v2; // edx
  __int64 v3; // r8
  int v4; // edx
  __int64 v5; // r13
  __int64 v6; // r12
  char *v7; // r15
  __int64 v8; // rdi
  int v9; // r14d
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  char v13; // bl
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // r11
  int v17; // ecx
  char v18; // r15
  int v19; // edx
  unsigned __int64 v20; // rcx
  void (*v21)(void); // rax
  __int64 v22; // rdi
  __int64 v23; // rbx
  _QWORD *v24; // rdi
  char *v25; // r12
  const void **v26; // rdx
  __int64 *v27; // r8
  __int64 v28; // rdi
  const void *v29; // r15
  __int64 v30; // rbx
  void *v31; // r14
  HANDLE ProcessHeap; // rax
  __int64 v33; // r14
  __int64 v34; // rax
  __int64 v35; // rcx
  char *v36; // rdi
  char *v37; // r15
  __int64 v38; // rax
  unsigned __int64 v39; // r13
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 *v42; // r12
  unsigned __int64 v43; // rax
  char *v44; // rax
  __int128 v45; // xmm7
  unsigned __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rcx
  __int128 v49; // xmm1
  __int128 v50; // xmm2
  unsigned __int64 v51; // r14
  unsigned __int64 v52; // rax
  __int128 v53; // xmm8
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // r10
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rdi
  __int64 v61; // rdx
  __int64 v62; // rcx
  void (*v63)(void); // rax
  unsigned __int64 v64; // rax
  float v65; // xmm0_4
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rdx
  int v69; // xmm7_4
  int v70; // xmm8_4
  char v71; // al
  char v72; // r14
  char v73; // bl
  char v74; // cl
  unsigned __int8 v75; // dl
  int v76; // xmm9_4
  __int64 *v77; // r12
  __int64 v78; // r12
  __int64 v79; // r10
  __int64 v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rbx
  __int64 v83; // rax
  __int64 v84; // rcx
  __int128 v85; // xmm1
  __int128 v86; // xmm2
  void *v87; // rdi
  char *v88; // rbx
  _QWORD *v89; // r14
  HANDLE v90; // rax
  __int128 v91; // [rsp+50h] [rbp-30h] BYREF
  __int128 v92; // [rsp+60h] [rbp-20h]
  __int128 v93; // [rsp+70h] [rbp-10h]
  __int128 v94; // [rsp+80h] [rbp+0h]
  __int128 v95; // [rsp+90h] [rbp+10h]
  __int128 v96; // [rsp+A0h] [rbp+20h]
  __int64 v97; // [rsp+B0h] [rbp+30h]
  __int128 *v98; // [rsp+C0h] [rbp+40h]
  __int64 *v99; // [rsp+C8h] [rbp+48h]
  __int64 v100; // [rsp+D0h] [rbp+50h]
  __int64 v101; // [rsp+D8h] [rbp+58h]
  __int64 v102; // [rsp+E0h] [rbp+60h]
  int v103; // [rsp+E8h] [rbp+68h]
  __int64 v104; // [rsp+F0h] [rbp+70h]
  __int64 v105; // [rsp+F8h] [rbp+78h]
  __int64 *v106; // [rsp+100h] [rbp+80h]
  __int64 v107; // [rsp+108h] [rbp+88h] BYREF
  __int64 v108; // [rsp+110h] [rbp+90h] BYREF
  __int64 v109; // [rsp+118h] [rbp+98h]
  __int64 v110; // [rsp+120h] [rbp+A0h]
  __int64 v111; // [rsp+128h] [rbp+A8h]
  __int128 v112; // [rsp+130h] [rbp+B0h] BYREF
  _BYTE v113[80]; // [rsp+140h] [rbp+C0h] BYREF
  __int64 v114; // [rsp+190h] [rbp+110h]
  char *v115; // [rsp+198h] [rbp+118h] BYREF
  LPVOID lpMem; // [rsp+1A0h] [rbp+120h]
  char *v117; // [rsp+1A8h] [rbp+128h]
  char *v118; // [rsp+1B0h] [rbp+130h]
  __int64 v119; // [rsp+1B8h] [rbp+138h]
  unsigned __int64 v120; // [rsp+1C0h] [rbp+140h]
  __int64 v121; // [rsp+1C8h] [rbp+148h]
  char v122; // [rsp+1D3h] [rbp+153h]
  char v123; // [rsp+1D4h] [rbp+154h]
  unsigned __int8 v124; // [rsp+1D5h] [rbp+155h]
  char v125; // [rsp+1D6h] [rbp+156h]
  char v126; // [rsp+1D7h] [rbp+157h]
  __int64 v127; // [rsp+1D8h] [rbp+158h]

  v127 = -2;
  if ( (*(_BYTE *)(a1 + 825) & 1) == 0 )
  {
    layout::TextLayout::ensure_shaping_runs_valid((_BYTE *)a1);
    if ( !v2 )
    {
      layout::TextLayout::ensure_lines_valid(a1);
      if ( !v4 )
      {
        v115 = 0;
        lpMem = (LPVOID)8;
        v117 = 0;
        v5 = *(_QWORD *)(a1 + 304);
        v6 = v5 + 120LL * *(_QWORD *)(a1 + 312);
        v7 = 0;
        v8 = 8;
        v9 = 0;
LABEL_6:
        v121 = 3LL * (_QWORD)v7;
        v11 = v8 + 24LL * (_QWORD)v7;
        v12 = v11 - 24;
        LOBYTE(v3) = v7 == 0 || v11 == 24;
        while ( 1 )
        {
          v14 = v5;
          v5 += 120;
          if ( v14 == v6 )
            break;
          if ( (_BYTE)v3 )
          {
            v13 = *(_BYTE *)(v14 + 109);
LABEL_19:
            v118 = v7;
            v17 = v9 | 0x1000;
            if ( (v13 & 1) == 0 )
              v17 = v9;
            v18 = *(_BYTE *)(v14 + 110);
            v19 = v17 | 0x2000;
            if ( !v18 )
              v19 = v17;
            v20 = *(_QWORD *)(v14 + 56);
            v9 = v19 | 0x4000;
            v119 = *(unsigned int *)(v14 + 112);
            if ( v20 )
            {
              v21 = *(void (**)(void))(*(_QWORD *)v20 + 8LL);
              v120 = v20;
              v21();
            }
            else
            {
              v9 = v19;
              v120 = 0;
            }
            if ( v118 == v115 )
            {
              alloc::raw_vec::RawVec_layout::impl_8::initialize_output_runs::EffectRange_alloc::alloc::Global_::grow_one_layout::impl_8::initialize_output_runs::EffectRange_alloc::alloc::Global_(&v115);
              v8 = (__int64)lpMem;
            }
            v10 = v121;
            *(_QWORD *)(v8 + 8 * v121) = v119;
            *(_QWORD *)(v8 + 8 * v10 + 8) = v120;
            *(_BYTE *)(v8 + 8 * v10 + 16) = v13;
            *(_BYTE *)(v8 + 8 * v10 + 17) = v18;
            *(_DWORD *)(v8 + 8 * v10 + 18) = v112;
            *(_WORD *)(v8 + 8 * v10 + 22) = WORD2(v112);
            v7 = v118 + 1;
            v117 = v118 + 1;
            goto LABEL_6;
          }
          v13 = *(_BYTE *)(v14 + 109);
          if ( *(_BYTE *)(v11 - 8) != v13 )
            goto LABEL_19;
          if ( *(_BYTE *)(v11 - 7) != *(_BYTE *)(v14 + 110) )
          {
            v13 = *(_BYTE *)(v11 - 8);
            goto LABEL_19;
          }
          v15 = *(_QWORD *)(v11 - 16);
          v16 = *(_QWORD *)(v14 + 56);
          if ( v15 && v16 )
          {
            v13 = *(_BYTE *)(v11 - 8);
            if ( v15 != v16 )
              goto LABEL_19;
          }
          else
          {
            v13 = *(_BYTE *)(v11 - 8);
            if ( v16 | v15 )
              goto LABEL_19;
          }
          *(_QWORD *)v12 = *(unsigned int *)(v14 + 112);
        }
        *(_DWORD *)(a1 + 824) = v9 | *(_DWORD *)(a1 + 824) & 0x70FF;
        v22 = *(_QWORD *)(a1 + 688);
        v23 = *(_QWORD *)(a1 + 696);
        *(_QWORD *)(a1 + 696) = 0;
        if ( v23 )
        {
          v24 = (_QWORD *)(v22 + 16);
          do
          {
            if ( *v24 )
              (*(void (__fastcall **)(_QWORD, unsigned __int64, __int64))(*(_QWORD *)*v24 + 16LL))(*v24, v12, v3);
            v24 += 10;
            --v23;
          }
          while ( v23 );
        }
        if ( v9 )
        {
          v25 = v7;
          v26 = (const void **)(a1 + 720);
          v27 = (__int64 *)(a1 + 728);
          if ( __OFSUB__(0, *(_QWORD *)(a1 + 712)) )
          {
            v27 = (__int64 *)(a1 + 504);
            v26 = (const void **)(a1 + 496);
          }
          v28 = *v27;
          v29 = *v26;
          if ( __OFSUB__(0, *(_QWORD *)(a1 + 736)) )
          {
            v108 = *v27;
            v107 = *(_QWORD *)(a1 + 16);
            if ( v28 != v107 )
            {
              *(_QWORD *)&v112 = 0;
              core::panicking::assert_failed_usize_usize_(&v108, &v107, &v112, &off_180339900);
            }
            if ( v28 )
            {
              v30 = std::sys::alloc::windows::process_heap_alloc(0, 2 * v28);
              if ( !v30 )
                alloc::alloc::handle_alloc_error(2, 2 * v28);
            }
            else
            {
              v30 = 2;
            }
            memcpy_0((void *)v30, v29, 2 * v28);
            if ( 2LL * *(_QWORD *)(a1 + 736) )
            {
              v31 = *(void **)(a1 + 744);
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v31);
            }
            *(_QWORD *)(a1 + 736) = v28;
            v109 = v30;
            *(_QWORD *)(a1 + 744) = v30;
            *(_QWORD *)(a1 + 752) = v28;
            v110 = v28;
          }
          else
          {
            v108 = *(_QWORD *)(a1 + 752);
            v107 = v28;
            if ( v108 != v28 )
            {
              *(_QWORD *)&v112 = 0;
              core::panicking::assert_failed_usize_usize_(&v108, &v107, &v112, &off_1803398E8);
            }
            memcpy_0(*(void **)(a1 + 744), v29, 2 * v28);
            v109 = *(_QWORD *)(a1 + 744);
            v110 = *(_QWORD *)(a1 + 752);
          }
          v33 = a1 + 456;
          v34 = a1 + 456;
          if ( !*(_QWORD *)(a1 + 472) )
            v34 = a1 + 424;
          v35 = *(_QWORD *)(a1 + 16);
          *(_QWORD *)&v112 = v34;
          v105 = (__int64)v29;
          *((_QWORD *)&v112 + 1) = v29;
          v104 = v28;
          *(_QWORD *)v113 = v28;
          memset(&v113[8], 0, 72);
          v114 = v35;
          layout::cluster_iterator::ClusterIterator::set_text_pos(&v112, 0);
          v97 = v114;
          v96 = *(_OWORD *)&v113[64];
          v95 = *(_OWORD *)&v113[48];
          v94 = *(_OWORD *)&v113[32];
          v93 = *(_OWORD *)&v113[16];
          v92 = *(_OWORD *)v113;
          v91 = v112;
          if ( !v25 )
            core::option::unwrap_failed(&off_180339918);
          v111 = a1 + 680;
          v36 = (char *)lpMem;
          v118 = (char *)lpMem + 8 * v121;
          if ( !*(_QWORD *)(a1 + 472) )
            v33 = a1 + 424;
          v37 = (char *)lpMem + 24;
          v38 = 10LL * *(_QWORD *)(v33 + 16);
          v106 = *(__int64 **)(v33 + 8);
          v99 = &v106[v38];
          v39 = 0;
          while ( 1 )
          {
            v42 = v106;
            if ( v106 == v99 )
              break;
            v106 += 10;
            v43 = v39;
            v39 = *((unsigned int *)v42 + 18);
            v120 = v43;
            if ( v43 >= *(_QWORD *)v36 )
            {
              v44 = v37 + 24;
              if ( v37 == v118 )
                core::option::unwrap_failed(&off_180339930);
            }
            else
            {
              v44 = v37;
              v37 = v36;
            }
            v45 = *((unsigned int *)v42 + 11);
            LODWORD(v119) = *((_DWORD *)v42 + 12);
            if ( (v119 & 1) != 0 )
              *(float *)&v45 = *(float *)&v45 + *((float *)v42 + 9);
            v98 = (__int128 *)(v42 + 6);
            v36 = v37;
            v46 = v120;
            while ( 1 )
            {
              v37 = v44;
              v12 = *(_QWORD *)v36;
              if ( *(_QWORD *)v36 >= v39 )
                break;
              layout::cluster_iterator::ClusterIterator::set_text_pos(&v91, v12);
              v51 = *((_QWORD *)&v92 + 1);
              if ( v46 < *((_QWORD *)&v92 + 1) )
              {
                layout::split_shaping_run_simple(
                  (unsigned int)&v112,
                  (_DWORD)v42,
                  v120,
                  v39,
                  v46,
                  *((__int64 *)&v92 + 1),
                  v105,
                  v104,
                  v109,
                  v110);
                v3 = *((_QWORD *)&v112 + 1) - v112;
                if ( *((_QWORD *)&v112 + 1) < (unsigned __int64)v112 )
                {
                  v125 = 1;
                  core::slice::index::slice_index_order_fail(v112, *((_QWORD *)&v112 + 1), &off_180339960);
                }
                v52 = *(_QWORD *)(a1 + 576);
                if ( *((_QWORD *)&v112 + 1) > v52 )
                {
                  v125 = 1;
                  core::slice::index::slice_end_index_len_fail(*((_QWORD *)&v112 + 1), v52, &off_180339960);
                }
                v53 = LODWORD(FLOAT_N0_0);
                if ( (_QWORD)v112 != *((_QWORD *)&v112 + 1) )
                {
                  v54 = *(_QWORD *)(a1 + 568);
                  v55 = 4 * v112;
                  if ( (_QWORD)v112 - *((_QWORD *)&v112 + 1) <= 0xFFFFFFFFFFFFFFF8uLL )
                  {
                    v56 = 0;
                    v53 = LODWORD(FLOAT_N0_0);
                    do
                    {
                      v57 = v54 + v55 + 28;
                      *(float *)&v53 = (float)((float)((float)((float)((float)((float)((float)(*(float *)&v53
                                                                                             + *(float *)(v57 + 4 * v56 - 28))
                                                                                     + *(float *)(v57 + 4 * v56 - 24))
                                                                             + *(float *)(v57 + 4 * v56 - 20))
                                                                     + *(float *)(v57 + 4 * v56 - 16))
                                                             + *(float *)(v57 + 4 * v56 - 12))
                                                     + *(float *)(v57 + 4 * v56 - 8))
                                             + *(float *)(v57 + 4 * v56 - 4))
                                     + *(float *)(v57 + 4 * v56);
                      v56 += 8;
                    }
                    while ( (v3 & 0xFFFFFFFFFFFFFFF8uLL) != v56 );
                  }
                  else
                  {
                    v56 = 0;
                    v53 = LODWORD(FLOAT_N0_0);
                  }
                  v3 &= 7u;
                  if ( (_DWORD)v3 )
                  {
                    v58 = v55 + 4 * v56 + v54;
                    v59 = 0;
                    do
                      *(float *)&v53 = *(float *)&v53 + *(float *)(v58 + 4 * v59++);
                    while ( (unsigned int)v3 != v59 );
                  }
                }
                *(_DWORD *)&v113[20] = v53;
                if ( (v119 & 1) != 0 )
                {
                  *(float *)&v45 = *(float *)&v45 - *(float *)&v53;
                  v53 = v45;
                }
                else
                {
                  *(float *)&v53 = *(float *)&v53 + *(float *)&v45;
                }
                *(_DWORD *)&v113[28] = v45;
                if ( !v113[49] && v113[53] != 1 && !v113[54] && !v113[52] )
                  *(_WORD *)&v113[50] = *((_WORD *)v36 + 8);
                v121 = *(_QWORD *)v113;
                v60 = *(_QWORD *)(a1 + 696);
                if ( v60 == *(_QWORD *)(a1 + 680) )
                  alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_(
                    v111,
                    &off_180338A80);
                v47 = *(_QWORD *)(a1 + 688);
                v48 = 80 * v60;
                *(_OWORD *)(v47 + v48) = v112;
                *(_QWORD *)(v47 + v48 + 16) = v121;
                v49 = *(_OWORD *)&v113[24];
                v50 = *(_OWORD *)&v113[40];
                *(_OWORD *)(v47 + v48 + 24) = *(_OWORD *)&v113[8];
                *(_OWORD *)(v47 + v48 + 40) = v49;
                *(_OWORD *)(v47 + v48 + 56) = v50;
                *(_DWORD *)(v47 + v48 + 72) = v51;
                *(_QWORD *)(a1 + 696) = v60 + 1;
                v45 = v53;
              }
              v44 = v37 + 24;
              v36 = v37;
              v46 = v51;
              if ( v37 == v118 )
                core::option::unwrap_failed(&off_180339978);
            }
            if ( v46 == v120 )
            {
              v61 = v42[1];
              v62 = v42[2];
              v100 = *v42;
              v101 = v61;
              if ( v62 )
              {
                v63 = *(void (**)(void))(*(_QWORD *)v62 + 8LL);
                v119 = v62;
                v63();
              }
              else
              {
                v119 = 0;
              }
              v69 = *((_DWORD *)v42 + 9);
              v70 = *((_DWORD *)v42 + 10);
              v71 = *((_BYTE *)v42 + 64);
              v72 = *((_BYTE *)v42 + 65);
              LOBYTE(v121) = *((_BYTE *)v42 + 66);
              LOBYTE(v120) = *((_BYTE *)v42 + 67);
              v73 = *((_BYTE *)v42 + 68);
              v74 = *((_BYTE *)v42 + 69);
              v75 = *((_BYTE *)v42 + 70);
              v76 = *((_DWORD *)v42 + 11);
              v122 = v71;
              if ( !v72 && !v74 && !v75 && !v73 )
              {
                LOBYTE(v121) = v36[16];
                LOBYTE(v120) = v36[17];
              }
              v124 = v75;
              v123 = v74;
              v77 = v42 + 3;
              v103 = *((_DWORD *)v77 + 2);
              v102 = *v77;
              v112 = *v98;
              v78 = *(_QWORD *)(a1 + 696);
              if ( v78 == *(_QWORD *)(a1 + 680) )
                alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_(
                  v111,
                  &off_180338A80);
              v40 = *(_QWORD *)(a1 + 688);
              v41 = 80 * v78;
              *(_QWORD *)(v40 + v41) = v100;
              *(_QWORD *)(v40 + v41 + 8) = v101;
              *(_QWORD *)(v40 + v41 + 16) = v119;
              *(_QWORD *)(v40 + v41 + 24) = v102;
              *(_DWORD *)(v40 + v41 + 32) = v103;
              *(_DWORD *)(v40 + v41 + 36) = v69;
              *(_DWORD *)(v40 + v41 + 40) = v70;
              *(_DWORD *)(v40 + v41 + 44) = v76;
              *(_OWORD *)(v40 + v41 + 48) = v112;
              *(_BYTE *)(v40 + v41 + 64) = v122;
              *(_BYTE *)(v40 + v41 + 65) = v72;
              *(_BYTE *)(v40 + v41 + 66) = v121;
              *(_BYTE *)(v40 + v41 + 67) = v120;
              *(_BYTE *)(v40 + v41 + 68) = v73;
              *(_BYTE *)(v40 + v41 + 69) = v123;
              v12 = v124;
              *(_BYTE *)(v40 + v41 + 70) = v124;
              *(_DWORD *)(v40 + v41 + 72) = v39;
              *(_QWORD *)(a1 + 696) = v78 + 1;
            }
            else if ( v46 < v39 )
            {
              layout::split_shaping_run_simple(
                (unsigned int)&v112,
                (_DWORD)v42,
                v120,
                v39,
                v46,
                v39,
                v105,
                v104,
                v109,
                v110);
              v3 = *((_QWORD *)&v112 + 1) - v112;
              if ( *((_QWORD *)&v112 + 1) < (unsigned __int64)v112 )
              {
                v126 = 1;
                core::slice::index::slice_index_order_fail(v112, *((_QWORD *)&v112 + 1), &off_180339948);
              }
              v64 = *(_QWORD *)(a1 + 576);
              if ( *((_QWORD *)&v112 + 1) > v64 )
              {
                v126 = 1;
                core::slice::index::slice_end_index_len_fail(*((_QWORD *)&v112 + 1), v64, &off_180339948);
              }
              v65 = FLOAT_N0_0;
              if ( (_QWORD)v112 != *((_QWORD *)&v112 + 1) )
              {
                v66 = *(_QWORD *)(a1 + 568);
                v67 = 4 * v112;
                if ( (_QWORD)v112 - *((_QWORD *)&v112 + 1) <= 0xFFFFFFFFFFFFFFF8uLL )
                {
                  v68 = 0;
                  v65 = FLOAT_N0_0;
                  do
                  {
                    v79 = v66 + v67 + 28;
                    v65 = (float)((float)((float)((float)((float)((float)((float)(v65 + *(float *)(v79 + 4 * v68 - 28))
                                                                        + *(float *)(v79 + 4 * v68 - 24))
                                                                + *(float *)(v79 + 4 * v68 - 20))
                                                        + *(float *)(v79 + 4 * v68 - 16))
                                                + *(float *)(v79 + 4 * v68 - 12))
                                        + *(float *)(v79 + 4 * v68 - 8))
                                + *(float *)(v79 + 4 * v68 - 4))
                        + *(float *)(v79 + 4 * v68);
                    v68 += 8;
                  }
                  while ( (v3 & 0xFFFFFFFFFFFFFFF8uLL) != v68 );
                }
                else
                {
                  v68 = 0;
                  v65 = FLOAT_N0_0;
                }
                v3 &= 7u;
                if ( (_DWORD)v3 )
                {
                  v80 = v67 + 4 * v68 + v66;
                  v81 = 0;
                  do
                    v65 = v65 + *(float *)(v80 + 4 * v81++);
                  while ( (unsigned int)v3 != v81 );
                }
              }
              *(float *)&v113[20] = v65;
              if ( (v119 & 1) != 0 )
                *(float *)&v45 = *(float *)&v45 - v65;
              *(_DWORD *)&v113[28] = v45;
              if ( !v113[49] && v113[53] != 1 && !v113[54] && !v113[52] )
                *(_WORD *)&v113[50] = *((_WORD *)v36 + 8);
              v121 = *(_QWORD *)v113;
              v82 = *(_QWORD *)(a1 + 696);
              if ( v82 == *(_QWORD *)(a1 + 680) )
                alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_(
                  v111,
                  &off_180338A80);
              v83 = *(_QWORD *)(a1 + 688);
              v84 = 80 * v82;
              *(_OWORD *)(v83 + v84) = v112;
              *(_QWORD *)(v83 + v84 + 16) = v121;
              v12 = (unsigned __int64)&v113[8];
              v85 = *(_OWORD *)&v113[24];
              v86 = *(_OWORD *)&v113[40];
              *(_OWORD *)(v83 + v84 + 24) = *(_OWORD *)&v113[8];
              *(_OWORD *)(v83 + v84 + 40) = v85;
              *(_OWORD *)(v83 + v84 + 56) = v86;
              *(_DWORD *)(v83 + v84 + 72) = v39;
              *(_QWORD *)(a1 + 696) = v82 + 1;
            }
          }
        }
        v87 = lpMem;
        v88 = v117;
        if ( v117 )
        {
          v89 = (char *)lpMem + 8;
          do
          {
            if ( *v89 )
              (*(void (__fastcall **)(_QWORD, unsigned __int64, __int64))(*(_QWORD *)*v89 + 16LL))(*v89, v12, v3);
            v89 += 3;
            --v88;
          }
          while ( v88 );
        }
        if ( v115 )
        {
          v90 = GetProcessHeap();
          HeapFree(v90, 0, v87);
        }
        *(_BYTE *)(a1 + 825) |= 1u;
      }
    }
  }
}

```

## disassembly

```asm
0x1800474a0  push    rbp
0x1800474a1  push    r15
0x1800474a3  push    r14
0x1800474a5  push    r13
0x1800474a7  push    r12
0x1800474a9  push    rsi
0x1800474aa  push    rdi
0x1800474ab  push    rbx
0x1800474ac  sub     rsp, 228h
0x1800474b3  lea     rbp, [rsp+80h]
0x1800474bb  movaps  [rbp+1E0h+var_50], xmm9
0x1800474c3  movaps  [rbp+1E0h+var_60], xmm8
0x1800474cb  movaps  [rbp+1E0h+var_70], xmm7
0x1800474d2  movaps  [rbp+1E0h+var_80], xmm6
0x1800474d9  mov     [rbp+1E0h+var_88], 0FFFFFFFFFFFFFFFEh
0x1800474e4  test    byte ptr [rcx+339h], 1
0x1800474eb  jnz     loc_1800480F5
0x1800474f1  mov     rsi, rcx
0x1800474f4  call    layout__TextLayout__ensure_shaping_runs_valid
0x1800474f9  test    edx, edx
0x1800474fb  jnz     loc_1800480F7
0x180047501  mov     rcx, rsi
0x180047504  call    layout__TextLayout__ensure_lines_valid
0x180047509  test    edx, edx
0x18004750b  jnz     loc_1800480F7
0x180047511  mov     [rbp+1E0h+var_C8], 0
0x18004751c  mov     [rbp+1E0h+lpMem], 8
0x180047527  mov     [rbp+1E0h+var_B8], 0
0x180047532  mov     r13, [rsi+130h]
0x180047539  imul    r12, [rsi+138h], 78h ; 'x'
0x180047541  add     r12, r13
0x180047544  xor     r15d, r15d
0x180047547  mov     edi, 8
0x18004754c  xor     r14d, r14d
0x18004754f  jmp     short loc_1800475AE
0x180047560  mov     rcx, [rbp+1E0h+var_98]
0x180047567  mov     rax, [rbp+1E0h+var_A8]
0x18004756e  mov     [rdi+rcx*8], rax
0x180047572  mov     rax, [rbp+1E0h+var_A0]
0x180047579  mov     [rdi+rcx*8+8], rax
0x18004757e  mov     [rdi+rcx*8+10h], bl
0x180047582  mov     [rdi+rcx*8+11h], r15b
0x180047587  mov     eax, dword ptr [rbp+1E0h+var_130]
0x18004758d  mov     [rdi+rcx*8+12h], eax
0x180047591  movzx   eax, word ptr [rbp+1E0h+var_130+4]
0x180047598  mov     [rdi+rcx*8+16h], ax
0x18004759d  mov     r15, [rbp+1E0h+var_B0]
0x1800475a4  inc     r15
0x1800475a7  mov     [rbp+1E0h+var_B8], r15
0x1800475ae  test    r15, r15
0x1800475b1  setz    al
0x1800475b4  lea     rcx, [r15+r15*2]
0x1800475b8  mov     [rbp+1E0h+var_98], rcx
0x1800475bf  lea     rcx, [rdi+rcx*8]
0x1800475c3  mov     rdx, rcx
0x1800475c6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800475ca  setz    r8b
0x1800475ce  or      r8b, al
0x1800475d1  jmp     short loc_1800475EE
0x1800475e0  or      r10, r11
0x1800475e3  mov     ebx, r9d
0x1800475e6  jnz     short loc_180047645
0x1800475e8  mov     eax, [rax+70h]
0x1800475eb  mov     [rdx], rax
0x1800475ee  mov     rax, r13
0x1800475f1  add     r13, 78h ; 'x'
0x1800475f5  cmp     rax, r12
0x1800475f8  cmovz   r13, rax
0x1800475fc  jz      loc_1800476DD
0x180047602  test    r8b, r8b
0x180047605  jnz     short loc_18004763C
0x180047607  movzx   r9d, byte ptr [rcx-8]
0x18004760c  movzx   ebx, byte ptr [rax+6Dh]
0x180047610  cmp     r9b, bl
0x180047613  jnz     short loc_180047645
0x180047615  movzx   r10d, byte ptr [rcx-7]
0x18004761a  cmp     r10b, [rax+6Eh]
0x18004761e  jnz     short loc_180047642
0x180047620  mov     r10, [rcx-10h]
0x180047624  mov     r11, [rax+38h]
0x180047628  test    r10, r10
0x18004762b  jz      short loc_1800475E0
0x18004762d  test    r11, r11
0x180047630  jz      short loc_1800475E0
0x180047632  mov     ebx, r9d
0x180047635  cmp     r10, r11
0x180047638  jz      short loc_1800475E8
0x18004763a  jmp     short loc_180047645
0x18004763c  movzx   ebx, byte ptr [rax+6Dh]
0x180047640  jmp     short loc_180047645
0x180047642  mov     ebx, r9d
0x180047645  mov     [rbp+1E0h+var_B0], r15
0x18004764c  mov     ecx, r14d
0x18004764f  or      ecx, 1000h
0x180047655  test    bl, 1
0x180047658  cmovz   ecx, r14d
0x18004765c  movzx   r15d, byte ptr [rax+6Eh]
0x180047661  mov     edx, ecx
0x180047663  or      edx, 2000h
0x180047669  test    r15b, r15b
0x18004766c  cmovz   edx, ecx
0x18004766f  mov     rcx, [rax+38h]
0x180047673  mov     r14d, edx
0x180047676  or      r14d, 4000h
0x18004767d  mov     eax, [rax+70h]
0x180047680  mov     [rbp+1E0h+var_A8], rax
0x180047687  test    rcx, rcx
0x18004768a  cmovz   r14d, edx
0x18004768e  jz      short loc_1800476A6
0x180047690  mov     rax, [rcx]
0x180047693  mov     rax, [rax+8]
0x180047697  mov     [rbp+1E0h+var_A0], rcx
0x18004769e  call    cs:__guard_dispatch_icall_fptr
0x1800476a4  jmp     short loc_1800476B1
0x1800476a6  mov     [rbp+1E0h+var_A0], 0
0x1800476b1  mov     rax, [rbp+1E0h+var_B0]
0x1800476b8  cmp     rax, [rbp+1E0h+var_C8]
0x1800476bf  jnz     loc_180047560
0x1800476c5  lea     rcx, [rbp+1E0h+var_C8]
0x1800476cc  call    alloc__raw_vec__RawVec_layout__impl$8__initialize_output_runs__EffectRange_alloc__alloc__Global___grow_one_layout__impl$8__initialize_output_runs__EffectRange_alloc__alloc__Global_
0x1800476d1  mov     rdi, [rbp+1E0h+lpMem]
0x1800476d8  jmp     loc_180047560
0x1800476dd  mov     eax, 70FFh
0x1800476e2  and     eax, [rsi+338h]
0x1800476e8  or      eax, r14d
0x1800476eb  mov     [rsi+338h], eax
0x1800476f1  mov     rdi, [rsi+2B0h]
0x1800476f8  mov     rbx, [rsi+2B8h]
0x1800476ff  mov     qword ptr [rsi+2B8h], 0
0x18004770a  test    rbx, rbx
0x18004770d  jz      short loc_180047740
0x18004770f  add     rdi, 10h
0x180047713  jmp     short loc_180047729
0x180047720  add     rdi, 50h ; 'P'
0x180047724  dec     rbx
0x180047727  jz      short loc_180047740
0x180047729  mov     rcx, [rdi]
0x18004772c  test    rcx, rcx
0x18004772f  jz      short loc_180047720
0x180047731  mov     rax, [rcx]
0x180047734  mov     rax, [rax+10h]
0x180047738  call    cs:__guard_dispatch_icall_fptr
0x18004773e  jmp     short loc_180047720
0x180047740  test    r14d, r14d
0x180047743  jz      loc_18004808E
0x180047749  mov     r12, r15
0x18004774c  lea     rax, [rsi+1F0h]
0x180047753  lea     rcx, [rsi+1F8h]
0x18004775a  lea     rdx, [rsi+2D0h]
0x180047761  lea     r8, [rsi+2D8h]
0x180047768  xor     r9d, r9d
0x18004776b  cmp     r9, [rsi+2C8h]
0x180047772  cmovo   r8, rcx
0x180047776  cmovo   rdx, rax
0x18004777a  mov     rdi, [r8]
0x18004777d  mov     r15, [rdx]
0x180047780  cmp     r9, [rsi+2E0h]
0x180047787  jno     short loc_1800477D1
0x180047789  mov     [rbp+1E0h+var_150], rdi
0x180047790  mov     rax, [rsi+10h]
0x180047794  mov     [rbp+1E0h+var_158], rax
0x18004779b  cmp     rdi, rax
0x18004779e  jnz     loc_1800481C2
0x1800477a4  lea     r14, [rdi+rdi]
0x1800477a8  test    rdi, rdi
0x1800477ab  jz      short loc_180047820
0x1800477ad  xor     ecx, ecx
0x1800477af  mov     rdx, r14
0x1800477b2  call    std__sys__alloc__windows__process_heap_alloc
0x1800477b7  mov     rbx, rax
0x1800477ba  test    rax, rax
0x1800477bd  jnz     short loc_180047825
0x1800477bf  mov     ecx, 2
0x1800477c4  mov     rdx, r14
0x1800477c7  call    alloc__alloc__handle_alloc_error
0x1800477cc  jmp     loc_18004821C
0x1800477d1  mov     rax, [rsi+2F0h]
0x1800477d8  mov     [rbp+1E0h+var_150], rax
0x1800477df  mov     [rbp+1E0h+var_158], rdi
0x1800477e6  cmp     rax, rdi
0x1800477e9  jnz     loc_1800481F0
0x1800477ef  mov     rcx, [rsi+2E8h]; void *
0x1800477f6  lea     r8, [rdi+rdi]; Size
0x1800477fa  mov     rdx, r15; Src
0x1800477fd  call    memcpy_0
0x180047802  mov     rax, [rsi+2E8h]
0x180047809  mov     [rbp+1E0h+var_148], rax
0x180047810  mov     rax, [rsi+2F0h]
0x180047817  mov     [rbp+1E0h+var_140], rax
0x18004781e  jmp     short loc_180047880
0x180047820  mov     ebx, 2
0x180047825  mov     rcx, rbx; void *
0x180047828  mov     rdx, r15; Src
0x18004782b  mov     r8, r14; Size
0x18004782e  call    memcpy_0
0x180047833  mov     rax, [rsi+2E0h]
0x18004783a  shl     rax, 1
0x18004783d  test    rax, rax
0x180047840  jz      short loc_18004785D
0x180047842  mov     r14, [rsi+2E8h]
0x180047849  call    cs:__imp_GetProcessHeap
0x18004784f  mov     rcx, rax; hHeap
0x180047852  xor     edx, edx; dwFlags
0x180047854  mov     r8, r14; lpMem
0x180047857  call    cs:__imp_HeapFree
0x18004785d  mov     [rsi+2E0h], rdi
0x180047864  mov     [rbp+1E0h+var_148], rbx
0x18004786b  mov     [rsi+2E8h], rbx
0x180047872  mov     [rsi+2F0h], rdi
0x180047879  mov     [rbp+1E0h+var_140], rdi
0x180047880  lea     rbx, [rsi+1A8h]
0x180047887  cmp     qword ptr [rsi+1D8h], 0
0x18004788f  lea     r14, [rsi+1C8h]
0x180047896  mov     rax, r14
0x180047899  cmovz   rax, rbx
0x18004789d  mov     rcx, [rsi+10h]
0x1800478a1  mov     qword ptr [rbp+1E0h+var_130], rax
0x1800478a8  mov     [rbp+1E0h+var_168], r15
0x1800478ac  mov     qword ptr [rbp+1E0h+var_130+8], r15
0x1800478b3  mov     [rbp+1E0h+var_170], rdi
0x1800478b7  mov     qword ptr [rbp+1E0h+var_120], rdi
0x1800478be  xorps   xmm0, xmm0
0x1800478c1  movups  [rbp+1E0h+var_120+8], xmm0
0x1800478c8  movups  [rbp+1E0h+var_108], xmm0
0x1800478cf  movups  [rbp+1E0h+var_F8], xmm0
0x1800478d6  movups  [rbp+1E0h+var_E8], xmm0
0x1800478dd  mov     [rbp+1E0h+var_D8], 0
0x1800478e8  mov     [rbp+1E0h+var_D0], rcx
0x1800478ef  lea     rcx, [rbp+1E0h+var_130]
0x1800478f6  xor     edx, edx
0x1800478f8  call    layout__cluster_iterator__ClusterIterator__set_text_pos
0x1800478fd  mov     rax, [rbp+1E0h+var_D0]
0x180047904  mov     [rbp+1E0h+var_1B0], rax
0x180047908  movups  xmm0, [rbp+1E0h+var_E8+8]
0x18004790f  movaps  [rbp+1E0h+var_1C0], xmm0
0x180047913  movups  xmm0, [rbp+1E0h+var_F8+8]
0x18004791a  movaps  [rbp+1E0h+var_1D0], xmm0
0x18004791e  movups  xmm0, [rbp+1E0h+var_130]
0x180047925  movups  xmm1, [rbp+1E0h+var_120]
0x18004792c  movups  xmm2, xmmword ptr [rbp+0D0h]
0x180047933  movups  xmm3, [rbp+1E0h+var_108+8]
0x18004793a  movaps  [rbp+1E0h+var_1E0], xmm3
0x18004793e  movaps  [rbp+1E0h+var_1F0], xmm2
0x180047942  movaps  [rbp+1E0h+var_200], xmm1
0x180047946  movaps  [rbp+1E0h+var_210], xmm0
0x18004794a  test    r12, r12
0x18004794d  jz      loc_1800481B4
0x180047953  lea     rax, [rsi+2A8h]
0x18004795a  mov     [rbp+1E0h+var_138], rax
0x180047961  mov     rdi, [rbp+1E0h+lpMem]
0x180047968  mov     rax, [rbp+1E0h+var_98]
0x18004796f  lea     rax, [rdi+rax*8]
0x180047973  mov     [rbp+1E0h+var_B0], rax
0x18004797a  cmp     qword ptr [rsi+1D8h], 0
0x180047982  cmovz   r14, rbx
0x180047986  lea     r15, [rdi+18h]
0x18004798a  mov     rcx, [r14+8]
0x18004798e  mov     rax, [r14+10h]
0x180047992  lea     rax, [rax+rax*4]
0x180047996  shl     rax, 4
0x18004799a  mov     [rbp+1E0h+var_160], rcx
0x1800479a1  add     rax, rcx
0x1800479a4  mov     [rbp+1E0h+var_198], rax
0x1800479a8  xor     r13d, r13d
0x1800479ab  movss   xmm6, cs:__real@80000000
0x1800479b3  jmp     loc_180047A6B
0x1800479c0  mov     rax, [rsi+2B0h]
0x1800479c7  lea     rcx, [r12+r12*4]
0x1800479cb  shl     rcx, 4
0x1800479cf  mov     rdx, [rbp+1E0h+var_190]
0x1800479d3  mov     [rax+rcx], rdx
0x1800479d7  mov     rdx, [rbp+1E0h+var_188]
0x1800479db  mov     [rax+rcx+8], rdx
0x1800479e0  mov     rdx, [rbp+1E0h+var_A8]
0x1800479e7  mov     [rax+rcx+10h], rdx
0x1800479ec  mov     rdx, [rbp+1E0h+var_180]
0x1800479f0  mov     [rax+rcx+18h], rdx
0x1800479f5  mov     edx, [rbp+1E0h+var_178]
0x1800479f8  mov     [rax+rcx+20h], edx
0x1800479fc  movss   dword ptr [rax+rcx+24h], xmm7
0x180047a02  movss   dword ptr [rax+rcx+28h], xmm8
0x180047a09  movss   dword ptr [rax+rcx+2Ch], xmm9
0x180047a10  movaps  xmm0, [rbp+1E0h+var_130]
0x180047a17  movups  xmmword ptr [rax+rcx+30h], xmm0
0x180047a1c  movzx   edx, [rbp+1E0h+var_8D]
0x180047a23  mov     [rax+rcx+40h], dl
0x180047a27  mov     [rax+rcx+41h], r14b
0x180047a2c  movzx   edx, byte ptr [rbp+1E0h+var_98]
0x180047a33  mov     [rax+rcx+42h], dl
0x180047a37  movzx   edx, byte ptr [rbp+1E0h+var_A0]
0x180047a3e  mov     [rax+rcx+43h], dl
0x180047a42  mov     [rax+rcx+44h], bl
0x180047a46  movzx   edx, [rbp+1E0h+var_8C]
0x180047a4d  mov     [rax+rcx+45h], dl
0x180047a51  movzx   edx, [rbp+1E0h+var_8B]
0x180047a58  mov     [rax+rcx+46h], dl
0x180047a5c  mov     [rax+rcx+48h], r13d
0x180047a61  inc     r12
0x180047a64  mov     [rsi+2B8h], r12
0x180047a6b  mov     r12, [rbp+1E0h+var_160]
  ... truncated ...
```

# CMSPolyPhaseResizer::ResizeWidth_SSE2(int,int,int)

- ea: `0x1800022f0`
- end: `0x180002aed`
- name: `?ResizeWidth_SSE2@CMSPolyPhaseResizer@@AEAAXHHH@Z`
- size: `2045`
- prototype: `void __fastcall(CMSPolyPhaseResizer *__hidden this, int, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800022f0`
- `0x180002b00`
- `0x180013618`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x1800025b2`
- `MFPlat!MFCopyImage` at `0x18000270e`
- `MFPlat!MFCopyImage` at `0x18000283d`
- `MFPlat!MFCopyImage` at `0x1800025b2`
- `MFPlat!MFCopyImage` at `0x18000270e`
- `MFPlat!MFCopyImage` at `0x18000283d`

## pseudocode

```c
void __fastcall CMSPolyPhaseResizer::ResizeWidth_SSE2(CMSPolyPhaseResizer *this, int a2, int a3, int a4)
{
  __int64 v5; // rax
  __int64 v7; // r9
  unsigned int v8; // r8d
  int v9; // r12d
  int v10; // r13d
  char v11; // cl
  int v12; // esi
  __int64 v13; // r8
  __int64 v14; // r10
  __int64 v15; // rdx
  const BYTE *v16; // rdi
  BYTE *v17; // r13
  BYTE *v18; // r12
  __int64 v19; // r8
  unsigned int v20; // ebx
  unsigned int v21; // r11d
  unsigned int v22; // edx
  __int64 v23; // r10
  unsigned int v24; // r8d
  unsigned __int8 *v25; // rbx
  int v26; // edx
  __int64 v27; // r15
  signed int dwLines; // ebp
  int v29; // r14d
  signed int i; // r8d
  BYTE v31; // cl
  BYTE *v32; // rax
  BYTE v33; // dl
  int v34; // ebx
  int v35; // edi
  CMSPolyPhaseResizer *v36; // r15
  signed int v37; // esi
  unsigned __int8 *v38; // rbx
  LONG v39; // ebp
  __int64 v40; // rdi
  signed int j; // r8d
  BYTE v42; // cl
  BYTE *v43; // rax
  BYTE v44; // dl
  signed int v45; // ebx
  int v46; // ebp
  __int64 v47; // rdi
  unsigned __int8 *v48; // rbx
  signed int k; // r8d
  BYTE v50; // cl
  BYTE *v51; // rax
  BYTE v52; // dl
  signed int m; // ebx
  __int64 v54; // rdi
  unsigned int v55; // ebp
  int v56; // r14d
  unsigned __int8 *v57; // r15
  unsigned __int8 *v58; // rsi
  int lSrcStride; // [rsp+60h] [rbp-D8h]
  int v60; // [rsp+64h] [rbp-D4h]
  signed int v61; // [rsp+68h] [rbp-D0h]
  char v62; // [rsp+6Ch] [rbp-CCh]
  int v63; // [rsp+6Ch] [rbp-CCh]
  int v64; // [rsp+70h] [rbp-C8h]
  DWORD dwWidthInBytes; // [rsp+74h] [rbp-C4h]
  unsigned int v66; // [rsp+78h] [rbp-C0h]
  signed int v67; // [rsp+78h] [rbp-C0h]
  LONG lDestStride; // [rsp+7Ch] [rbp-BCh]
  int v69; // [rsp+80h] [rbp-B8h]
  int v70; // [rsp+88h] [rbp-B0h]
  unsigned __int8 *v71; // [rsp+90h] [rbp-A8h]
  unsigned __int8 *v72; // [rsp+98h] [rbp-A0h]
  unsigned __int8 *v73; // [rsp+A0h] [rbp-98h]
  __int64 v74; // [rsp+B0h] [rbp-88h]
  unsigned __int8 *v75; // [rsp+C0h] [rbp-78h]
  int v76; // [rsp+C0h] [rbp-78h]
  __int64 v77; // [rsp+D0h] [rbp-68h]
  int v78; // [rsp+D8h] [rbp-60h]
  __int64 v79; // [rsp+E0h] [rbp-58h]
  __int64 v80; // [rsp+E8h] [rbp-50h]
  CMSPolyPhaseResizer *v82; // [rsp+140h] [rbp+8h]

  v5 = a2;
  if ( *(_BYTE *)this )
  {
    v7 = *((int *)this + 104);
    v8 = *((_DWORD *)this + 103);
    dwWidthInBytes = *((_DWORD *)this + 102);
    v9 = *((_DWORD *)this + 116);
    v10 = *((_DWORD *)this + 115);
    v11 = v10;
    v66 = v8 >> v9;
    lSrcStride = (int)v7 >> v10;
    v12 = a3 >> v9;
    v70 = *((_DWORD *)this + 105) >> v10;
    v60 = a2 >> v9;
    v13 = *((_QWORD *)this + 3);
    v61 = dwWidthInBytes >> v10;
    v14 = *((int *)this + 108);
    v15 = *((int *)this + 109);
    v62 = v9;
    v77 = v7;
    v69 = a3 >> v9;
    lDestStride = dwWidthInBytes + 16;
    v64 = (dwWidthInBytes >> v10) + 16;
    v16 = (const BYTE *)(v13 + v14 + v7 * (v5 + v15));
    v75 = (unsigned __int8 *)v16;
    v17 = (BYTE *)((v14 >> v10)
                 + ((int)v7 >> v10) * (((int)v5 >> v9) + ((int)v15 >> v9))
                 + v13
                 + v7 * *((unsigned int *)this + 112));
    v80 = (int)v7 >> v11;
    v18 = &v17[v80 * (int)(*((_DWORD *)this + 112) >> v9)];
    v19 = *((_QWORD *)this + 8);
    v20 = *((_DWORD *)this + 103);
    v71 = (unsigned __int8 *)(v19 + v5 * (int)(dwWidthInBytes + 16));
    v21 = v66;
    v72 = (unsigned __int8 *)(v19 + (int)(dwWidthInBytes + 16) * (unsigned __int64)v20 + v60 * v64);
    v73 = &v72[v64 * (__int64)(int)v66];
    if ( *((_BYTE *)this + 1) )
    {
      v22 = v20 + 16;
      v23 = *((_QWORD *)this + 43);
      v24 = (*((_DWORD *)this + 105) + 7) & 0xFFFFFFF8;
      v63 = v24;
      v25 = v71 + 8;
      v26 = v24 * v22;
      v67 = (v70 + 7) & 0xFFFFFFF8;
      v76 = v23 + 2 * (v26 + v67 * (v60 + 8));
      v27 = *((_QWORD *)this + 44);
      dwLines = a3 - a2;
      v79 = *((_QWORD *)this + 41);
      v29 = v23 + 2 * (v26 + v67 * (v60 + v21 + 24));
      v78 = v23 + 2 * v24 * (a2 + 8);
      MFCopyImage(v71 + 8, lDestStride, v16, *((_DWORD *)this + 104), dwWidthInBytes, dwLines);
      for ( i = 0; i < dwLines; v32[7] = v33 )
      {
        v31 = *v16;
        v32 = &v25[dwWidthInBytes];
        v33 = v16[dwWidthInBytes - 1];
        ++i;
        *(v25 - 8) = *v16;
        v16 += v77;
        *(v25 - 7) = v31;
        *(v25 - 6) = v31;
        *(v25 - 5) = v31;
        *(v25 - 4) = v31;
        *(v25 - 3) = v31;
        *(v25 - 2) = v31;
        *(v25 - 1) = v31;
        *v32 = v33;
        v32[1] = v33;
        v32[2] = v33;
        v25 += (int)(dwWidthInBytes + 16);
        v32[3] = v33;
        v32[4] = v33;
        v32[5] = v33;
        v32[6] = v33;
      }
      v34 = 0;
      if ( v63 > 0 )
      {
        v35 = v78;
        do
        {
          FilterHorizontal8To16_SSE2((_DWORD)v71 + 5, v35, v27, v79, dwLines, lDestStride, 2 * v63);
          v35 += 16;
          LODWORD(v27) = v27 + 32;
          v34 += 8;
        }
        while ( v34 < v63 );
        v12 = v69;
      }
      v36 = this;
      v37 = v12 - v60;
      v38 = v72 + 8;
      v39 = v64;
      v40 = *((_QWORD *)this + 44);
      v74 = *((_QWORD *)this + 41);
      MFCopyImage(v72 + 8, v64, v17, lSrcStride, v61, v37);
      for ( j = 0; j < v37; v43[7] = v44 )
      {
        v42 = *v17;
        v43 = &v38[v61];
        v44 = v17[v61 - 1];
        ++j;
        *(v38 - 8) = *v17;
        v17 += v80;
        *(v38 - 7) = v42;
        *(v38 - 6) = v42;
        *(v38 - 5) = v42;
        *(v38 - 4) = v42;
        *(v38 - 3) = v42;
        *(v38 - 2) = v42;
        *(v38 - 1) = v42;
        *v43 = v44;
        v43[1] = v44;
        v43[2] = v44;
        v38 += v64;
        v43[3] = v44;
        v43[4] = v44;
        v43[5] = v44;
        v43[6] = v44;
      }
      v45 = 0;
      if ( v67 > 0 )
      {
        v46 = v76;
        do
        {
          FilterHorizontal8To16_SSE2((_DWORD)v72 + 5, v46, v40, v74, v37, v64, 2 * v67);
          v46 += 16;
          LODWORD(v40) = v40 + 32;
          v45 += 8;
        }
        while ( v45 < v67 );
        v39 = v64;
        v36 = this;
      }
      v47 = *((_QWORD *)v36 + 44);
      v48 = v73 + 8;
      v82 = (CMSPolyPhaseResizer *)*((_QWORD *)v36 + 41);
      MFCopyImage(v73 + 8, v39, v18, lSrcStride, v61, v37);
      for ( k = 0; k < v37; v51[7] = v52 )
      {
        v50 = *v18;
        v51 = &v48[v61];
        v52 = v18[v61 - 1];
        ++k;
        *(v48 - 8) = *v18;
        v18 += lSrcStride;
        *(v48 - 7) = v50;
        *(v48 - 6) = v50;
        *(v48 - 5) = v50;
        *(v48 - 4) = v50;
        *(v48 - 3) = v50;
        *(v48 - 2) = v50;
        *(v48 - 1) = v50;
        *v51 = v52;
        v51[1] = v52;
        v51[2] = v52;
        v48 += v39;
        v51[3] = v52;
        v51[4] = v52;
        v51[5] = v52;
        v51[6] = v52;
      }
      for ( m = 0; m < v67; m += 8 )
      {
        FilterHorizontal8To16_SSE2((_DWORD)v73 + 5, v29, v47, (_DWORD)v82, v37, v64, 2 * v67);
        v29 += 16;
        LODWORD(v47) = v47 + 32;
      }
    }
    else
    {
      v54 = *((int *)this + 107);
      v55 = *((_DWORD *)this + 113);
      v56 = *((int *)this + 107) >> *((_DWORD *)this + 115);
      v57 = (unsigned __int8 *)*((_QWORD *)this + a4 + 9);
      v58 = (unsigned __int8 *)(v56 * (v60 + (*((int *)this + 111) >> v62))
                              + *((_QWORD *)this + 4)
                              + ((__int64)*((int *)this + 110) >> *((_BYTE *)this + 460))
                              + v54 * v55);
      CMSPolyPhaseResizer::ResizeWidth1D_SSE2(
        this,
        v75,
        (unsigned __int8 *)(*((int *)this + 110) + *((_QWORD *)this + 4) + v54 * (*((_DWORD *)this + 111) + a2)),
        v71,
        v57,
        *((int **)this + 44),
        dwWidthInBytes,
        *((_DWORD *)this + 104),
        *((_DWORD *)this + 105),
        *((_DWORD *)this + 107),
        a2,
        a3);
      CMSPolyPhaseResizer::ResizeWidth1D_SSE2(
        this,
        v17,
        v58,
        v72,
        v57,
        *((int **)this + 44),
        v61,
        lSrcStride,
        v70,
        v56,
        v60,
        v69);
      CMSPolyPhaseResizer::ResizeWidth1D_SSE2(
        this,
        v18,
        &v58[v56 * (__int64)(int)(v55 >> v62)],
        v73,
        v57,
        *((int **)this + 44),
        v61,
        lSrcStride,
        v70,
        v56,
        v60,
        v69);
    }
  }
}

```

## disassembly

```asm
0x1800022f0  mov     r11, rsp
0x1800022f3  mov     [r11+20h], r9d
0x1800022f7  mov     [r11+18h], r8d
0x1800022fb  mov     [rsp+arg_8], edx
0x1800022ff  mov     [r11+8], rcx
0x180002303  push    rbp
0x180002304  push    rdi
0x180002305  sub     rsp, 128h
0x18000230c  cmp     byte ptr [rcx], 0
0x18000230f  mov     ebp, r8d
0x180002312  movsxd  rax, edx
0x180002315  mov     rdi, rcx
0x180002318  jz      loc_180002933
0x18000231e  mov     edx, [rcx+198h]
0x180002324  mov     r10d, edx
0x180002327  movsxd  r9, dword ptr [rdi+1A0h]
0x18000232e  mov     r8d, [rdi+19Ch]
0x180002335  mov     [r11-18h], rbx
0x180002339  mov     rbx, r9
0x18000233c  mov     [rsp+138h+var_C4], edx
0x180002340  mov     [r11-20h], rsi
0x180002344  mov     esi, ebp
0x180002346  mov     [r11-28h], r12
0x18000234a  mov     r12d, [rdi+1D0h]
0x180002351  mov     [r11-30h], r13
0x180002355  mov     r13d, [rcx+1CCh]
0x18000235c  mov     ecx, r13d
0x18000235f  shr     r10d, cl
0x180002362  mov     ecx, r12d
0x180002365  shr     r8d, cl
0x180002368  mov     ecx, r13d
0x18000236b  mov     [rsp+138h+var_C0], r8d
0x180002370  mov     r8d, r9d
0x180002373  sar     r8d, cl
0x180002376  mov     [rsp+138h+lSrcStride], r8d
0x18000237b  mov     r8d, [rdi+1A4h]
0x180002382  shr     r8d, cl
0x180002385  mov     ecx, r12d
0x180002388  sar     esi, cl
0x18000238a  mov     [rsp+138h+var_B0], r8d
0x180002392  mov     r8d, eax
0x180002395  sar     r8d, cl
0x180002398  mov     [r11-38h], r14
0x18000239c  lea     r14d, [r10+10h]
0x1800023a0  mov     [rsp+138h+var_D4], r8d
0x1800023a5  mov     r8, [rdi+18h]
0x1800023a9  mov     [rsp+138h+var_D0], r10d
0x1800023ae  movsxd  r10, dword ptr [rdi+1B0h]
0x1800023b5  mov     [r11-40h], r15
0x1800023b9  lea     r15d, [rdx+10h]
0x1800023bd  movsxd  rdx, dword ptr [rdi+1B4h]
0x1800023c4  mov     r11, rax
0x1800023c7  mov     [rsp+138h+var_CC], r12d
0x1800023cc  mov     [rsp+138h+var_68], rbx
0x1800023d4  mov     [rsp+138h+var_B8], esi
0x1800023db  lea     rdi, [rax+rdx]
0x1800023df  mov     [rsp+138h+lDestStride], r15d
0x1800023e4  mov     rax, [rsp+138h+arg_0]
0x1800023ec  sar     edx, cl
0x1800023ee  movzx   ecx, r13b
0x1800023f2  add     edx, [rsp+138h+var_D4]
0x1800023f6  imul    edx, [rsp+138h+lSrcStride]
0x1800023fb  imul    rdi, r9
0x1800023ff  mov     r9d, [rax+1C0h]
0x180002406  movsxd  rax, edx
0x180002409  add     rdi, r10
0x18000240c  sar     r10, cl
0x18000240f  mov     edx, r9d
0x180002412  mov     ecx, r12d
0x180002415  mov     [rsp+138h+var_C8], r14d
0x18000241a  imul    rdx, rbx
0x18000241e  shr     r9d, cl
0x180002421  add     rdi, r8
0x180002424  add     rdx, r8
0x180002427  movsxd  rcx, r15d
0x18000242a  movsxd  r12, r9d
0x18000242d  mov     [rsp+138h+var_78], rdi
0x180002435  mov     [rsp+138h+var_90], rcx
0x18000243d  lea     r13, [rax+rdx]
0x180002441  movsxd  rax, [rsp+138h+lSrcStride]
0x180002446  imul    r12, rax
0x18000244a  add     r13, r10
0x18000244d  mov     [rsp+138h+var_50], rax
0x180002455  mov     r10, [rsp+138h+arg_0]
0x18000245d  add     r12, r13
0x180002460  mov     rax, rcx
0x180002463  mov     [rsp+138h+var_88], r13
0x18000246b  imul    rax, r11
0x18000246f  mov     r8, [r10+40h]
0x180002473  mov     ebx, [r10+19Ch]
0x18000247a  add     rax, r8
0x18000247d  mov     [rsp+138h+var_A8], rax
0x180002485  mov     edx, ebx
0x180002487  mov     [rsp+138h+var_70], r12
0x18000248f  mov     r15d, [rsp+138h+var_D4]
0x180002494  mov     eax, r14d
0x180002497  movsxd  r11, [rsp+138h+var_C0]
0x18000249c  imul    rdx, rcx
0x1800024a0  imul    eax, r15d
0x1800024a4  movsxd  rcx, eax
0x1800024a7  lea     rax, [r8+rdx]
0x1800024ab  add     rcx, rax
0x1800024ae  mov     rdx, r11
0x1800024b1  movsxd  rax, r14d
0x1800024b4  imul    rdx, rax
0x1800024b8  mov     [rsp+138h+var_A0], rcx
0x1800024c0  add     rdx, rcx
0x1800024c3  mov     [rsp+138h+var_80], rax
0x1800024cb  cmp     byte ptr [r10+1], 0
0x1800024d0  mov     [rsp+138h+var_98], rdx
0x1800024d8  jz      loc_18000293D
0x1800024de  mov     eax, [r10+1A4h]
0x1800024e5  lea     edx, [rbx+10h]
0x1800024e8  mov     r10, [r10+158h]
0x1800024ef  add     eax, 7
0x1800024f2  mov     r9d, [rsp+138h+var_B0]
0x1800024fa  and     eax, 0FFFFFFF8h
0x1800024fd  mov     rbx, [rsp+138h+var_A8]
0x180002505  add     r9d, 7
0x180002509  movsxd  r8, eax
0x18000250c  and     r9d, 0FFFFFFF8h
0x180002510  mov     [rsp+138h+var_CC], eax
0x180002514  add     rbx, 8
0x180002518  imul    rdx, r8
0x18000251c  lea     eax, [r15+8]
0x180002520  mov     [rsp+138h+var_C0], r9d
0x180002525  imul    eax, r9d
0x180002529  movsxd  rcx, eax
0x18000252c  add     rcx, rdx
0x18000252f  lea     rax, [r10+rcx*2]
0x180002533  mov     [rsp+138h+var_78], rax
0x18000253b  lea     eax, [r11+18h]
0x18000253f  add     eax, r15d
0x180002542  imul    eax, r9d
0x180002546  mov     r9, [rsp+138h+arg_0]
0x18000254e  mov     r15, [r9+160h]
0x180002555  movsxd  rcx, eax
0x180002558  mov     rax, [r9+148h]
0x18000255f  add     rcx, rdx
0x180002562  mov     edx, [rsp+138h+arg_8]
0x180002569  sub     ebp, edx
0x18000256b  mov     r9d, [r9+1A0h]; lSrcStride
0x180002572  mov     [rsp+138h+var_58], rax
0x18000257a  lea     r14, [r10+rcx*2]
0x18000257e  mov     [rsp+138h+dwLines], ebp; dwLines
0x180002582  lea     eax, [rdx+8]
0x180002585  mov     qword ptr [rsp+138h+var_B0], r14
0x18000258d  mov     edx, [rsp+138h+lDestStride]; lDestStride
0x180002591  movsxd  rcx, eax
0x180002594  imul    rcx, r8
0x180002598  mov     r8, rdi; pSrc
0x18000259b  lea     rax, [r10+rcx*2]
0x18000259f  mov     rcx, rbx; pDest
0x1800025a2  mov     [rsp+138h+var_60], rax
0x1800025aa  mov     eax, [rsp+138h+var_C4]
0x1800025ae  mov     [rsp+138h+dwWidthInBytes], eax; dwWidthInBytes
0x1800025b2  call    cs:__imp_MFCopyImage
0x1800025b8  xor     r8d, r8d
0x1800025bb  test    ebp, ebp
0x1800025bd  jle     short loc_180002630
0x1800025bf  movsxd  r9, [rsp+138h+var_C4]
0x1800025c4  mov     r10, [rsp+138h+var_68]
0x1800025cc  mov     r11, [rsp+138h+var_90]
0x1800025d4  nop     dword ptr [rax+00h]
0x1800025d8  nop     dword ptr [rax+rax+00000000h]
0x1800025e0  movzx   ecx, byte ptr [rdi]
0x1800025e3  lea     rax, [r9+rbx]
0x1800025e7  movzx   edx, byte ptr [r9+rdi-1]
0x1800025ed  inc     r8d
0x1800025f0  mov     [rbx-8], cl
0x1800025f3  add     rdi, r10
0x1800025f6  mov     [rbx-7], cl
0x1800025f9  mov     [rbx-6], cl
0x1800025fc  mov     [rbx-5], cl
0x1800025ff  mov     [rbx-4], cl
0x180002602  mov     [rbx-3], cl
0x180002605  mov     [rbx-2], cl
0x180002608  mov     [rbx-1], cl
0x18000260b  mov     [r9+rbx], dl
0x18000260f  mov     [r9+rbx+1], dl
0x180002614  mov     [r9+rbx+2], dl
0x180002619  add     rbx, r11
0x18000261c  mov     [rax+3], dl
0x18000261f  mov     [rax+4], dl
0x180002622  mov     [rax+5], dl
0x180002625  mov     [rax+6], dl
0x180002628  mov     [rax+7], dl
0x18000262b  cmp     r8d, ebp
0x18000262e  jl      short loc_1800025E0
0x180002630  mov     rax, [rsp+138h+var_A8]
0x180002638  xor     ebx, ebx
0x18000263a  add     rax, 5
0x18000263e  mov     [rsp+138h+var_90], rax
0x180002646  mov     eax, [rsp+138h+var_CC]
0x18000264a  test    eax, eax
0x18000264c  jle     short loc_1800026C3
0x18000264e  mov     rdi, [rsp+138h+var_60]
0x180002656  lea     r12d, [rax+rax]
0x18000265a  mov     rsi, [rsp+138h+var_90]
0x180002662  mov     r14d, eax
0x180002665  mov     r13d, [rsp+138h+lDestStride]
0x18000266a  nop     word ptr [rax+rax+00h]
0x180002670  mov     r9, [rsp+138h+var_58]
0x180002678  mov     r8, r15
0x18000267b  mov     [rsp+138h+var_108], r12d
0x180002680  mov     rdx, rdi
0x180002683  mov     [rsp+138h+dwLines], r13d
0x180002688  mov     rcx, rsi
0x18000268b  mov     [rsp+138h+dwWidthInBytes], ebp
0x18000268f  call    FilterHorizontal8To16_SSE2
0x180002694  add     rdi, 10h
0x180002698  add     r15, 20h ; ' '
0x18000269c  add     ebx, 8
0x18000269f  cmp     ebx, r14d
0x1800026a2  jl      short loc_180002670
0x1800026a4  mov     r12, [rsp+138h+var_70]
0x1800026ac  mov     r13, [rsp+138h+var_88]
0x1800026b4  mov     esi, [rsp+138h+var_B8]
0x1800026bb  mov     r14, qword ptr [rsp+138h+var_B0]
0x1800026c3  mov     r15, [rsp+138h+arg_0]
0x1800026cb  mov     r8, r13; pSrc
0x1800026ce  mov     rbx, [rsp+138h+var_A0]
0x1800026d6  sub     esi, [rsp+138h+var_D4]
0x1800026da  add     rbx, 8
0x1800026de  mov     ebp, [rsp+138h+var_C8]
0x1800026e2  mov     rcx, rbx; pDest
0x1800026e5  mov     rax, [r15+148h]
0x1800026ec  mov     edx, ebp; lDestStride
0x1800026ee  mov     r9d, [rsp+138h+lSrcStride]; lSrcStride
0x1800026f3  mov     rdi, [r15+160h]
0x1800026fa  mov     [rsp+138h+var_88], rax
0x180002702  mov     eax, [rsp+138h+var_D0]
0x180002706  mov     [rsp+138h+dwLines], esi; dwLines
0x18000270a  mov     [rsp+138h+dwWidthInBytes], eax; dwWidthInBytes
0x18000270e  call    cs:__imp_MFCopyImage
0x180002714  xor     r8d, r8d
0x180002717  test    esi, esi
0x180002719  jle     short loc_180002782
0x18000271b  movsxd  r9, [rsp+138h+var_D0]
0x180002720  mov     r10, [rsp+138h+var_50]
0x180002728  mov     r11, [rsp+138h+var_80]
0x180002730  movzx   ecx, byte ptr [r13+0]
0x180002735  lea     rax, [r9+rbx]
0x180002739  movzx   edx, byte ptr [r9+r13-1]
0x18000273f  inc     r8d
0x180002742  mov     [rbx-8], cl
0x180002745  add     r13, r10
0x180002748  mov     [rbx-7], cl
0x18000274b  mov     [rbx-6], cl
0x18000274e  mov     [rbx-5], cl
0x180002751  mov     [rbx-4], cl
0x180002754  mov     [rbx-3], cl
0x180002757  mov     [rbx-2], cl
0x18000275a  mov     [rbx-1], cl
0x18000275d  mov     [r9+rbx], dl
0x180002761  mov     [r9+rbx+1], dl
0x180002766  mov     [r9+rbx+2], dl
0x18000276b  add     rbx, r11
0x18000276e  mov     [rax+3], dl
0x180002771  mov     [rax+4], dl
0x180002774  mov     [rax+5], dl
0x180002777  mov     [rax+6], dl
0x18000277a  mov     [rax+7], dl
0x18000277d  cmp     r8d, esi
0x180002780  jl      short loc_180002730
0x180002782  mov     r13d, [rsp+138h+var_C0]
0x180002787  xor     ebx, ebx
0x180002789  mov     rax, [rsp+138h+var_A0]
0x180002791  test    r13d, r13d
0x180002794  jle     short loc_180002800
0x180002796  mov     rbp, [rsp+138h+var_78]
0x18000279e  lea     r15d, ds:0[r13*2]
0x1800027a6  mov     r12d, [rsp+138h+var_C8]
0x1800027ab  lea     r14, [rax+5]
0x1800027af  nop
0x1800027b0  mov     r9, [rsp+138h+var_88]
0x1800027b8  mov     r8, rdi
0x1800027bb  mov     [rsp+138h+var_108], r15d
0x1800027c0  mov     rdx, rbp
0x1800027c3  mov     [rsp+138h+dwLines], r12d
0x1800027c8  mov     rcx, r14
0x1800027cb  mov     [rsp+138h+dwWidthInBytes], esi
0x1800027cf  call    FilterHorizontal8To16_SSE2
0x1800027d4  add     rbp, 10h
0x1800027d8  add     rdi, 20h ; ' '
0x1800027dc  add     ebx, 8
0x1800027df  cmp     ebx, r13d
0x1800027e2  jl      short loc_1800027B0
0x1800027e4  mov     r12, [rsp+138h+var_70]
0x1800027ec  mov     r14, qword ptr [rsp+138h+var_B0]
0x1800027f4  mov     ebp, [rsp+138h+var_C8]
0x1800027f8  mov     r15, [rsp+138h+arg_0]
0x180002800  mov     rax, [r15+148h]
0x180002807  mov     r8, r12; pSrc
0x18000280a  mov     rdi, [r15+160h]
0x180002811  mov     edx, ebp; lDestStride
0x180002813  mov     rbx, [rsp+138h+var_98]
0x18000281b  movsxd  r15, [rsp+138h+var_D0]
0x180002820  add     rbx, 8
0x180002824  mov     r9d, [rsp+138h+lSrcStride]; lSrcStride
  ... truncated ...
```

# CDisplayML::UpdateView(CRchTxtPtr const &,long,long)

- ea: `0x1800200d0`
- end: `0x180020939`
- name: `?UpdateView@CDisplayML@@UEAAHAEBVCRchTxtPtr@@JJ@Z`
- size: `2153`
- prototype: `__int64 __fastcall(CDisplayML *__hidden this, const struct CRchTxtPtr *, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update`

## callees

- `0x18000c260`
- `0x18000f800`
- `0x18001e3e0`
- `0x18001e720`
- `0x18001e8f8`
- `0x18001f770`
- `0x18001ff28`
- `0x1800200d0`
- `0x180020940`
- `0x180021980`
- `0x18003eca0`
- `0x1800466f0`
- `0x180057358`
- `0x180058b1c`
- `0x180093c00`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CDisplayML::UpdateView(CDisplayML *this, const struct CRchTxtPtr *a2, int a3, int a4)
{
  int v4; // r15d
  __int64 v6; // r9
  int v10; // ecx
  __int64 v11; // rcx
  __int64 v12; // r13
  unsigned int v13; // r12d
  unsigned int v14; // eax
  int v15; // r13d
  int v16; // eax
  __int64 v17; // rcx
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // edi
  __int64 v23; // r9
  int v24; // eax
  bool v25; // zf
  __int64 v26; // rax
  int v27; // edi
  int v28; // eax
  int v29; // edi
  int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rcx
  bool i; // sf
  int v34; // eax
  int v35; // r10d
  int v36; // edi
  int v37; // r11d
  int v38; // r9d
  int v39; // r10d
  LONG v40; // r10d
  int v41; // edi
  int v42; // ecx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  int v47; // edi
  int v48; // r9d
  __int64 v50; // rsi
  int v51; // eax
  CArrayBase *v52; // rsi
  int v53; // r14d
  int v54; // edx
  CLine *v55; // rax
  int v56; // eax
  int v57; // eax
  int v58; // edx
  __int64 v59; // rax
  int v60; // edx
  int v61; // eax
  int v62; // eax
  int v63; // eax
  int v64; // edx
  _DWORD *v65; // rax
  __int64 v66; // rcx
  COleObject *v67; // rcx
  struct tagRECT *v68; // rdx
  __int64 v69; // rcx
  int v70; // edx
  CLine *v71; // rax
  int Height; // eax
  int v73; // r9d
  int v74; // [rsp+50h] [rbp-B0h]
  int v75; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v76; // [rsp+5Ch] [rbp-A4h]
  int v77; // [rsp+60h] [rbp-A0h]
  int v78; // [rsp+64h] [rbp-9Ch]
  int v79; // [rsp+68h] [rbp-98h]
  int v80; // [rsp+6Ch] [rbp-94h]
  int v81; // [rsp+70h] [rbp-90h]
  int v82; // [rsp+74h] [rbp-8Ch]
  int v83; // [rsp+78h] [rbp-88h]
  int v84; // [rsp+80h] [rbp-80h]
  int v85; // [rsp+84h] [rbp-7Ch]
  int v86; // [rsp+88h] [rbp-78h]
  CArrayBase *v87; // [rsp+90h] [rbp-70h] BYREF
  HDC v88; // [rsp+98h] [rbp-68h]
  CDisplayML *v89; // [rsp+A0h] [rbp-60h]
  __int64 v90; // [rsp+A8h] [rbp-58h]
  struct tagRECT v91; // [rsp+B0h] [rbp-50h] BYREF
  struct tagRECT v92; // [rsp+C0h] [rbp-40h] BYREF
  struct tagRECT v93; // [rsp+D0h] [rbp-30h] BYREF
  struct tagRECT v94; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v95; // [rsp+F0h] [rbp-10h] BYREF

  v4 = *((_DWORD *)this + 42);
  v6 = *((_QWORD *)this + 2);
  v74 = v4;
  v93 = 0;
  v92 = 0;
  if ( (*(_BYTE *)(v6 + 180) & 1) == 0 )
  {
    v54 = *((_DWORD *)this + 28);
    if ( v54 )
    {
      v55 = (CLine *)CArrayBase::Elem((CDisplayML *)((char *)this + 104), v54 - 1);
      if ( *((_BYTE *)v55 + 20) )
        v74 = v4 + CLine::GetHeight(v55);
    }
  }
  v10 = *((_DWORD *)this + 14);
  if ( (v10 & 0x20) != 0 )
    return 1;
  v84 = *((_DWORD *)a2 + 8);
  if ( v84 > *((_DWORD *)this + 32) || (v10 & 0x80u) != 0 )
    return 1;
  v11 = *(_QWORD *)(v6 + 48);
  v86 = *((_DWORD *)this + 41);
  v85 = *((_DWORD *)this + 36);
  v12 = *(_QWORD *)(v6 + 296);
  (*(void (__fastcall **)(__int64, struct tagRECT *))(*(_QWORD *)v11 + 192LL))(v11, &v93);
  CDisplay::GetViewRect(this, &v92, &v93);
  if ( v12 && (*(_BYTE *)(v12 + 136) & 0x20) == 0 )
    *(_DWORD *)(v12 + 144) = 0;
  v13 = 1;
  v14 = *((_DWORD *)this + 14) & 0xFFFFFBFF;
  *((_DWORD *)this + 34) = -1;
  v15 = 0;
  *((_DWORD *)this + 14) = v14 | 2;
  *((_DWORD *)this + 35) = *((_DWORD *)this + 36) + *((_DWORD *)this + 16);
  v16 = CDisplayML::RecalcLines(this, a2, a3, a4, 0, 1, (struct CLed *)&v75);
  v17 = *((_QWORD *)this + 2);
  if ( !v16 )
  {
    *((_DWORD *)this + 18) = 0;
    *((_QWORD *)this + 18) = 0;
    *((_DWORD *)this + 38) = 0;
    v13 = 0;
    *((_DWORD *)this + 43) = 0;
    *((_DWORD *)this + 20) = 0;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v17 + 48) + 72LL))(*(_QWORD *)(v17 + 48), 0, 0);
    return v13;
  }
  if ( !*(_DWORD *)(v17 + 272) )
  {
    if ( (*(unsigned int (__fastcall **)(CDisplayML *))(*(_QWORD *)this + 184LL))(this) )
      CArrayBase::Clear((char *)this + 104, 2);
    CDisplayML::CreateEmptyLine(this);
  }
  if ( *((_DWORD *)this + 41) <= *((__int16 *)this + 30) )
  {
    if ( *((_DWORD *)this + 18) )
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 48LL) + 72LL))(
        *(_QWORD *)(*((_QWORD *)this + 2) + 48LL),
        0,
        0);
    *((_DWORD *)this + 18) = 0;
  }
  v18 = *((_DWORD *)this + 36);
  if ( v77 >= v18 + *((_DWORD *)this + 16) )
  {
LABEL_50:
    v48 = *((_DWORD *)this + 42);
    if ( v4 != v48 )
      goto LABEL_51;
    if ( (*(_BYTE *)(*((_QWORD *)this + 2) + 180LL) & 1) == 0 )
    {
      v70 = *((_DWORD *)this + 28);
      if ( v70 )
      {
        v71 = (CLine *)CArrayBase::Elem((CDisplayML *)((char *)this + 104), v70 - 1);
        if ( *((_BYTE *)v71 + 20) )
        {
          Height = CLine::GetHeight(v71);
          v48 = Height + v73;
        }
      }
    }
    if ( v74 != v48 || v86 != *((_DWORD *)this + 41) )
    {
LABEL_51:
      if ( (int)CDisplay::RequestResize(this) < 0 )
        CCallMgr::SetOutOfMemory(*(CCallMgr **)(*((_QWORD *)this + 2) + 144LL));
    }
    if ( (unsigned int)CDisplayML::DoDeferredUpdateScrollBar(this) )
    {
      if ( (int)CDisplay::RequestResize(this) < 0 )
        CCallMgr::SetOutOfMemory(*(CCallMgr **)(*((_QWORD *)this + 2) + 144LL));
      CDisplayML::DoDeferredUpdateScrollBar(this);
    }
    return v13;
  }
  v19 = v83;
  v20 = v18 + *((_DWORD *)this + 37);
  v21 = v80;
  if ( v83 <= v20 && v80 <= v20 )
  {
    v56 = *((_DWORD *)this + 42);
    if ( v18 < v56 )
    {
      v47 = 0;
      if ( v56 )
      {
        v57 = v81;
        *((_DWORD *)this + 36) = v83 + v18 - v80;
        v58 = *((_DWORD *)this + 38) + v82 - v79;
        if ( v58 <= 0 )
          v58 = 0;
        *((_DWORD *)this + 20) += v57 - v78;
        v59 = *((_QWORD *)this + 2);
        *((_DWORD *)this + 38) = v58;
        v60 = *(_DWORD *)(v59 + 272);
        v61 = 0;
        if ( v60 >= *((_DWORD *)this + 20) )
          v60 = *((_DWORD *)this + 20);
        if ( v60 < 0 )
          v60 = 0;
      }
      else
      {
        v61 = 1;
        *((_DWORD *)this + 36) = 0;
        *((_DWORD *)this + 38) = 0;
        v60 = 0;
      }
      *((_DWORD *)this + 20) = v60;
      if ( !v61 )
        goto LABEL_50;
      goto LABEL_47;
    }
  }
  v22 = *((_DWORD *)this + 20);
  v23 = v76;
  v91 = v93;
  v95 = 0;
  if ( v84 <= v22 || (v62 = *((_DWORD *)this + 38), v79 <= v62) || v82 <= v62 || (int)v76 <= v62 )
  {
    v24 = *((_DWORD *)this + 38) - 1;
    *(_QWORD *)((char *)this + 148) = 0;
    v25 = v24 == (_DWORD)v23;
    *((_DWORD *)this + 20) = 0;
    v26 = *(_QWORD *)this;
    if ( v25 )
      v22 = v75;
    *((_DWORD *)this + 36) = 0;
    (*(void (__fastcall **)(CDisplayML *, _QWORD, __int64))(v26 + 264))(this, (unsigned int)v22, 0xFFFFFFFFLL);
    v87 = 0;
    v88 = 0;
    v89 = this;
    v90 = 0;
    (*(void (__fastcall **)(CDisplayML *, CArrayBase **))(*(_QWORD *)this + 24LL))(this, &v87);
    CLinePtr::RpSetCp((CLinePtr *)&v87, v22, 0);
    v27 = (int)v88;
    if ( !(*(unsigned int (__fastcall **)(CDisplayML *, _QWORD))(*(_QWORD *)this + 272LL))(this, (unsigned int)v88) )
    {
      v27 = *((_DWORD *)this + 28) - 1;
      if ( v27 <= 0 )
        v27 = 0;
    }
    v28 = *((_DWORD *)this + 38);
    v29 = v27 - v28;
    v30 = *((_DWORD *)this + 28);
    if ( v30 > 0 && v28 < v30 && (v31 = *((_QWORD *)this + 13)) != 0 && v28 >= 0 )
      v32 = v31 + *((_DWORD *)this + 30) * v28;
    else
      v32 = 0;
    v18 = *((_DWORD *)this + 36) + *((_DWORD *)this + 37);
    for ( i = v29 < 0; v29 > 0; i = v29 < 0 )
    {
      v34 = 0;
      if ( (*(_BYTE *)(v32 + 23) & 0x10) == 0 )
        v34 = *(__int16 *)(v32 + 12);
      v18 += v34;
      --v29;
      v32 += 24;
    }
    if ( i )
    {
      do
      {
        v63 = CLine::GetHeight((CLine *)(v32 - 24));
        v18 = v64 - v63;
        ++v29;
      }
      while ( v29 < 0 );
    }
    v35 = (int)v88;
    v36 = (int)v88;
    v37 = HIDWORD(v88);
    v38 = HIDWORD(v88);
    *((_DWORD *)this + 36) = v18;
    if ( v35 )
    {
      v65 = CArrayBase::Elem(v87, v35);
      do
      {
        v65 = (_DWORD *)((char *)v65 - *(int *)(v66 + 16));
        v38 += *v65;
        --v36;
      }
      while ( v36 );
      v18 = *((_DWORD *)this + 36);
    }
    v19 = v83;
    v21 = v80;
    *((_DWORD *)this + 20) = v38 - v37;
    v23 = v76;
    *((_DWORD *)this + 38) = v35;
  }
  v39 = *((_DWORD *)this + 16);
  if ( v21 < v39 + v85 && v19 < v39 + v18 )
  {
    v40 = v21 + v92.top - v85;
    v91.top = v40;
    if ( v40 >= v91.bottom )
    {
      v91.top = v19 + v92.top - v18;
    }
    else
    {
      v41 = v85 + v19 - v18 - v21;
      if ( !v41 )
      {
LABEL_31:
        v18 = *((_DWORD *)this + 36);
        if ( v19 > v21 )
          v21 = v19;
        v91.bottom = v92.top + v21 - v18;
        goto LABEL_34;
      }
      v50 = *((_QWORD *)this + 2);
      v51 = *(_DWORD *)(v50 + 180);
      if ( (v51 & 0x400) != 0 )
      {
        v94 = v91;
        v68 = &v94;
        v94.top = v40 + v41;
        v69 = *(_QWORD *)(v50 + 48);
LABEL_115:
        (*(void (__fastcall **)(__int64, struct tagRECT *, _QWORD, __int64))(*(_QWORD *)v69 + 72LL))(v69, v68, 0, v23);
LABEL_69:
        LODWORD(v23) = v76;
        v21 = v80;
        v19 = v83;
        goto LABEL_31;
      }
      if ( (v51 & 8) != 0 )
      {
        CMagellanBMPStateWrap::CMagellanBMPStateWrap((CMagellanBMPStateWrap *)&v87, *((struct CTxtEdit **)this + 2), 0);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, struct tagRECT *, struct tagRECT *, _QWORD, __int128 *, _DWORD))(**(_QWORD **)(v50 + 48) + 128LL))(
          *(_QWORD *)(v50 + 48),
          0,
          (unsigned int)v41,
          &v91,
          &v92,
          0,
          &v95,
          0);
        v52 = *(CArrayBase **)(v50 + 136);
        if ( v52 )
        {
          v94 = 0;
          v53 = *((_DWORD *)v52 + 2);
          if ( v53 > 0 )
          {
            do
            {
              v67 = *(COleObject **)CArrayBase::Elem(v52, v15);
              if ( v67 )
                COleObject::ScrollObject(v67, 0, v41, &v91);
              ++v15;
            }
            while ( v15 < v53 );
          }
        }
        CMagellan::InvertMagellanDownBMP((HGDIOBJ *)v89 + 3, *((struct CDisplay **)v89 + 8), (int)v87, v88);
      }
      (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 2) + 48LL) + 72LL))(
        *(_QWORD *)(*((_QWORD *)this + 2) + 48LL),
        &v95,
        0,
        v23);
      if ( v41 >= 0 )
        goto LABEL_69;
      v91.top = v41 + v91.bottom;
    }
    v68 = &v91;
    v69 = *(_QWORD *)(*((_QWORD *)this + 2) + 48LL);
    goto LABEL_115;
  }
LABEL_34:
  v42 = *((_DWORD *)this + 28);
  v91.top = v77 + v92.top - v18;
  if ( (int)v23 < v42 && (*(_DWORD *)(*((_QWORD *)this + 2) + 180LL) & 0x400) == 0 )
  {
    if ( v42 > 0 && (v43 = *((_QWORD *)this + 13)) != 0 && (int)v23 >= 0 )
      v44 = v43 + *((_DWORD *)this + 30) * (int)v23;
    else
      v44 = 0;
    if ( (*(_BYTE *)(v44 + 21) & 0x20) == 0 )
    {
      if ( v42 > 0 && (v45 = *((_QWORD *)this + 13)) != 0 && (int)v23 >= 0 )
        v46 = v45 + *((_DWORD *)this + 30) * (int)v23;
      else
        v46 = 0;
      *(_BYTE *)(v46 + 21) |= 0x60u;
    }
  }
  (*(void (__fastcall **)(_QWORD, struct tagRECT *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 48LL) + 72LL))(
    *(_QWORD *)(*((_QWORD *)this + 2) + 48LL),
    &v91,
    0);
  v47 = 1;
LABEL_47:
  v13 = (*(__int64 (__fastcall **)(CDisplayML *))(*(_QWORD *)this + 280LL))(this);
  if ( v13 )
  {
    if ( v47 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 48LL) + 80LL))(
        *(_QWORD *)(*((_QWORD *)this + 2) + 48LL),
        0);
    goto LABEL_50;
  }
  return 0;
}

```

## disassembly

```asm
0x1800200d0  push    rbp
0x1800200d2  push    rbx
0x1800200d3  push    rsi
0x1800200d4  push    rdi
0x1800200d5  push    r14
0x1800200d7  push    r15
0x1800200d9  lea     rbp, [rsp-28h]
0x1800200de  sub     rsp, 128h
0x1800200e5  mov     rax, cs:__security_cookie
0x1800200ec  xor     rax, rsp
0x1800200ef  mov     [rbp+50h+var_50], rax
0x1800200f3  mov     r15d, [rcx+0A8h]
0x1800200fa  mov     r14d, r9d
0x1800200fd  mov     r9, [rcx+10h]
0x180020101  xorps   xmm0, xmm0
0x180020104  xorps   xmm1, xmm1
0x180020107  mov     [rsp+150h+var_100], r15d
0x18002010c  movups  xmmword ptr [rbp+50h+var_80.left], xmm0
0x180020110  mov     esi, r8d
0x180020113  mov     rdi, rdx
0x180020116  movups  xmmword ptr [rbp+50h+var_90.left], xmm1
0x18002011a  test    byte ptr [r9+0B4h], 1
0x180020122  mov     rbx, rcx
0x180020125  jz      loc_1800206BE
0x18002012b  mov     ecx, [rbx+38h]
0x18002012e  mov     [rsp+150h+var_30], r12
0x180020136  test    cl, 20h
0x180020139  jnz     loc_1800205BA
0x18002013f  mov     eax, [rdi+20h]
0x180020142  mov     [rbp+50h+var_D0], eax
0x180020145  cmp     eax, [rbx+80h]
0x18002014b  jg      loc_1800205BA
0x180020151  test    cl, cl
0x180020153  js      loc_1800205BA
0x180020159  mov     eax, [rbx+0A4h]
0x18002015f  lea     rdx, [rbp+50h+var_80]
0x180020163  mov     rcx, [r9+30h]
0x180020167  mov     [rbp+50h+var_C8], eax
0x18002016a  mov     eax, [rbx+90h]
0x180020170  mov     [rbp+50h+var_CC], eax
0x180020173  mov     rax, [rcx]
0x180020176  mov     [rsp+150h+var_38], r13
0x18002017e  mov     r13, [r9+128h]
0x180020185  mov     rax, [rax+0C0h]
0x18002018c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020191  lea     r8, [rbp+50h+var_80]; struct tagRECT *
0x180020195  mov     rcx, rbx; this
0x180020198  lea     rdx, [rbp+50h+var_90]; struct tagRECT *
0x18002019c  call    ?GetViewRect@CDisplay@@QEAAXAEAUtagRECT@@PEBU2@@Z; CDisplay::GetViewRect(tagRECT &,tagRECT const *)
0x1800201a1  test    r13, r13
0x1800201a4  jnz     loc_18002056C
0x1800201aa  mov     eax, [rbx+38h]
0x1800201ad  mov     r12d, 1
0x1800201b3  btr     eax, 0Ah
0x1800201b7  mov     dword ptr [rbx+88h], 0FFFFFFFFh
0x1800201c1  or      eax, 2
0x1800201c4  xor     r13d, r13d
0x1800201c7  mov     [rbx+38h], eax
0x1800201ca  mov     r9d, r14d; int
0x1800201cd  mov     eax, [rbx+40h]
0x1800201d0  mov     r8d, esi; int
0x1800201d3  add     eax, [rbx+90h]
0x1800201d9  mov     rdx, rdi; struct CRchTxtPtr *
0x1800201dc  mov     [rbx+8Ch], eax
0x1800201e2  mov     rcx, rbx; this
0x1800201e5  lea     rax, [rsp+150h+var_F8]
0x1800201ea  mov     [rsp+150h+var_120], rax; struct CLed *
0x1800201ef  mov     [rsp+150h+var_128], r12d; int
0x1800201f4  mov     [rsp+150h+var_130], r13d; int
0x1800201f9  call    ?RecalcLines@CDisplayML@@AEAAHAEBVCRchTxtPtr@@JJHHPEAVCLed@@@Z; CDisplayML::RecalcLines(CRchTxtPtr const &,long,long,int,int,CLed *)
0x1800201fe  mov     rcx, [rbx+10h]
0x180020202  test    eax, eax
0x180020204  jz      loc_180020535
0x18002020a  cmp     [rcx+110h], r13d
0x180020211  jz      loc_1800206F2
0x180020217  movsx   eax, word ptr [rbx+3Ch]
0x18002021b  cmp     [rbx+0A4h], eax
0x180020221  jle     loc_180020723
0x180020227  mov     ecx, [rbx+40h]
0x18002022a  mov     edx, [rbx+90h]
0x180020230  add     ecx, edx
0x180020232  cmp     [rsp+150h+var_F0], ecx
0x180020236  jge     loc_1800204D5
0x18002023c  mov     r9d, [rbx+94h]
0x180020243  mov     r8d, [rsp+150h+var_D8]
0x180020248  add     r9d, edx
0x18002024b  mov     ecx, [rsp+150h+var_E4]
0x18002024f  cmp     r8d, r9d
0x180020252  jle     loc_18002074B
0x180020258  movaps  xmm0, xmmword ptr [rbp+50h+var_80.left]
0x18002025c  xorps   xmm1, xmm1
0x18002025f  mov     edi, [rbx+50h]
0x180020262  mov     r9d, [rsp+150h+var_F4]
0x180020267  movdqa  xmmword ptr [rbp+50h+var_A0.left], xmm0
0x18002026c  movups  [rbp+50h+var_60], xmm1
0x180020270  cmp     [rbp+50h+var_D0], edi
0x180020273  jg      loc_1800207D1
0x180020279  mov     eax, [rbx+98h]
0x18002027f  mov     r8d, 0FFFFFFFFh
0x180020285  dec     eax
0x180020287  mov     [rbx+94h], r13
0x18002028e  cmp     eax, r9d
0x180020291  mov     [rbx+50h], r13d
0x180020295  mov     rax, [rbx]
0x180020298  mov     rcx, rbx
0x18002029b  cmovz   edi, [rsp+150h+var_F8]
0x1800202a0  mov     edx, edi
0x1800202a2  mov     [rbx+90h], r13d
0x1800202a9  mov     rax, [rax+108h]
0x1800202b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202b5  mov     [rbp+50h+var_C0], r13
0x1800202b9  lea     rdx, [rbp+50h+var_C0]
0x1800202bd  mov     [rbp+50h+var_B8], r13
0x1800202c1  mov     rcx, rbx
0x1800202c4  mov     [rbp+50h+var_B0], rbx
0x1800202c8  mov     [rbp+50h+var_A8], r13
0x1800202cc  mov     rax, [rbx]
0x1800202cf  mov     rax, [rax+18h]
0x1800202d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202d8  xor     r8d, r8d; int
0x1800202db  lea     rcx, [rbp+50h+var_C0]; this
0x1800202df  mov     edx, edi; int
0x1800202e1  call    ?RpSetCp@CLinePtr@@QEAAHJH@Z; CLinePtr::RpSetCp(long,int)
0x1800202e6  mov     rax, [rbx]
0x1800202e9  mov     rcx, rbx
0x1800202ec  mov     edi, dword ptr [rbp+50h+var_B8]
0x1800202ef  mov     edx, edi
0x1800202f1  mov     rax, [rax+110h]
0x1800202f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202fd  test    eax, eax
0x1800202ff  jz      loc_1800207F9
0x180020305  mov     eax, [rbx+98h]
0x18002030b  sub     edi, eax
0x18002030d  mov     ecx, [rbx+70h]
0x180020310  test    ecx, ecx
0x180020312  jle     loc_180020696
0x180020318  cmp     eax, ecx
0x18002031a  jge     loc_180020696
0x180020320  mov     rdx, [rbx+68h]
0x180020324  test    rdx, rdx
0x180020327  jz      loc_180020696
0x18002032d  test    eax, eax
0x18002032f  js      loc_180020696
0x180020335  imul    eax, [rbx+78h]
0x180020339  movsxd  rcx, eax
0x18002033c  add     rcx, rdx
0x18002033f  mov     edx, [rbx+94h]
0x180020345  add     edx, [rbx+90h]
0x18002034b  test    edi, edi
0x18002034d  jle     short loc_180020369
0x18002034f  nop
0x180020350  test    byte ptr [rcx+17h], 10h
0x180020354  mov     eax, r13d
0x180020357  jnz     short loc_18002035D
0x180020359  movsx   eax, word ptr [rcx+0Ch]
0x18002035d  add     edx, eax
0x18002035f  dec     edi
0x180020361  add     rcx, 18h
0x180020365  test    edi, edi
0x180020367  jg      short loc_180020350
0x180020369  js      loc_180020809
0x18002036f  mov     r10d, dword ptr [rbp+50h+var_B8]
0x180020373  mov     edi, r10d
0x180020376  mov     r11d, dword ptr [rbp+50h+var_B8+4]
0x18002037a  mov     r9d, r11d
0x18002037d  mov     [rbx+90h], edx
0x180020383  test    r10d, r10d
0x180020386  jnz     loc_18002081E
0x18002038c  mov     r8d, [rsp+150h+var_D8]
0x180020391  sub     r9d, r11d
0x180020394  mov     ecx, [rsp+150h+var_E4]
0x180020398  mov     [rbx+50h], r9d
0x18002039c  mov     r9d, [rsp+150h+var_F4]
0x1800203a1  mov     [rbx+98h], r10d
0x1800203a8  mov     r10d, [rbx+40h]
0x1800203ac  mov     r11d, [rbp+50h+var_CC]
0x1800203b0  lea     eax, [r10+r11]
0x1800203b4  cmp     ecx, eax
0x1800203b6  jge     short loc_1800203FE
0x1800203b8  lea     eax, [r10+rdx]
0x1800203bc  cmp     r8d, eax
0x1800203bf  jge     short loc_1800203FE
0x1800203c1  mov     r10d, [rbp+50h+var_90.top]
0x1800203c5  sub     r10d, r11d
0x1800203c8  add     r10d, ecx
0x1800203cb  mov     [rbp+50h+var_A0.top], r10d
0x1800203cf  cmp     r10d, [rbp+50h+var_A0.bottom]
0x1800203d3  jge     loc_180020899
0x1800203d9  mov     edi, r8d
0x1800203dc  sub     edi, edx
0x1800203de  sub     edi, ecx
0x1800203e0  add     edi, r11d
0x1800203e3  jnz     loc_1800205C4
0x1800203e9  mov     edx, [rbx+90h]
0x1800203ef  cmp     r8d, ecx
0x1800203f2  cmovg   ecx, r8d
0x1800203f6  sub     ecx, edx
0x1800203f8  add     ecx, [rbp+50h+var_90.top]
0x1800203fb  mov     [rbp+50h+var_A0.bottom], ecx
0x1800203fe  mov     eax, [rbp+50h+var_90.top]
0x180020401  mov     ecx, [rbx+70h]
0x180020404  sub     eax, edx
0x180020406  add     eax, [rsp+150h+var_F0]
0x18002040a  mov     [rbp+50h+var_A0.top], eax
0x18002040d  cmp     r9d, ecx
0x180020410  jge     short loc_180020480
0x180020412  mov     rax, [rbx+10h]
0x180020416  test    dword ptr [rax+0B4h], 400h
0x180020420  jnz     short loc_180020480
0x180020422  test    ecx, ecx
0x180020424  jle     loc_18002069E
0x18002042a  mov     r8, [rbx+68h]
0x18002042e  test    r8, r8
0x180020431  jz      loc_18002069E
0x180020437  test    r9d, r9d
0x18002043a  js      loc_18002069E
0x180020440  mov     eax, r9d
0x180020443  imul    eax, [rbx+78h]
0x180020447  movsxd  rdx, eax
0x18002044a  add     rdx, r8
0x18002044d  test    byte ptr [rdx+15h], 20h
0x180020451  jnz     short loc_180020480
0x180020453  test    ecx, ecx
0x180020455  jle     loc_1800206A6
0x18002045b  mov     rcx, [rbx+68h]
0x18002045f  test    rcx, rcx
0x180020462  jz      loc_1800206A6
0x180020468  test    r9d, r9d
0x18002046b  js      loc_1800206A6
0x180020471  imul    r9d, [rbx+78h]
0x180020476  movsxd  rax, r9d
0x180020479  add     rax, rcx
0x18002047c  or      byte ptr [rax+15h], 60h
0x180020480  mov     rax, [rbx+10h]
0x180020484  lea     rdx, [rbp+50h+var_A0]
0x180020488  xor     r8d, r8d
0x18002048b  mov     rcx, [rax+30h]
0x18002048f  mov     rax, [rcx]
0x180020492  mov     rax, [rax+48h]
0x180020496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002049b  mov     edi, r12d
0x18002049e  mov     rax, [rbx]
0x1800204a1  mov     rcx, rbx
0x1800204a4  mov     rax, [rax+118h]
0x1800204ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204b0  mov     r12d, eax
0x1800204b3  test    eax, eax
0x1800204b5  jz      loc_1800208C4
0x1800204bb  test    edi, edi
0x1800204bd  jz      short loc_1800204D5
0x1800204bf  mov     rax, [rbx+10h]
0x1800204c3  xor     edx, edx
0x1800204c5  mov     rcx, [rax+30h]
0x1800204c9  mov     rax, [rcx]
0x1800204cc  mov     rax, [rax+50h]
0x1800204d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204d5  mov     r9d, [rbx+0A8h]
0x1800204dc  cmp     r15d, r9d
0x1800204df  jz      loc_18002058A
0x1800204e5  mov     rcx, rbx; this
0x1800204e8  call    ?RequestResize@CDisplay@@QEAAJXZ; CDisplay::RequestResize(void)
0x1800204ed  test    eax, eax
0x1800204ef  js      loc_1800208FB
0x1800204f5  mov     rcx, rbx; this
0x1800204f8  call    ?DoDeferredUpdateScrollBar@CDisplayML@@AEAAHXZ; CDisplayML::DoDeferredUpdateScrollBar(void)
0x1800204fd  test    eax, eax
0x1800204ff  jnz     loc_180020910
0x180020505  mov     eax, r12d
0x180020508  mov     r13, [rsp+150h+var_38]
0x180020510  mov     r12, [rsp+150h+var_30]
0x180020518  mov     rcx, [rbp+50h+var_50]
0x18002051c  xor     rcx, rsp; StackCookie
0x18002051f  call    __security_check_cookie
0x180020524  add     rsp, 128h
0x18002052b  pop     r15
0x18002052d  pop     r14
0x18002052f  pop     rdi
0x180020530  pop     rsi
0x180020531  pop     rbx
0x180020532  pop     rbp
0x180020533  retn
0x180020535  mov     [rbx+48h], r13d
0x180020539  xor     r8d, r8d
0x18002053c  mov     [rbx+90h], r13
0x180020543  xor     edx, edx
0x180020545  mov     [rbx+98h], r13d
0x18002054c  mov     r12d, r13d
0x18002054f  mov     [rbx+0ACh], r13d
0x180020556  mov     [rbx+50h], r13d
0x18002055a  mov     rcx, [rcx+30h]
0x18002055e  mov     rax, [rcx]
0x180020561  mov     rax, [rax+48h]
0x180020565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002056a  jmp     short loc_180020505
0x18002056c  test    byte ptr [r13+88h], 20h
0x180020574  jnz     loc_1800201AA
0x18002057a  mov     dword ptr [r13+90h], 0
0x180020585  jmp     loc_1800201AA
0x18002058a  mov     rax, [rbx+10h]
0x18002058e  test    byte ptr [rax+0B4h], 1
  ... truncated ...
```

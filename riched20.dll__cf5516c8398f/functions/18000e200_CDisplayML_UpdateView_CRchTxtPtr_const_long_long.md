# CDisplayML::UpdateView(CRchTxtPtr const &,long,long)

- ea: `0x18000e200`
- end: `0x18000ea68`
- name: `?UpdateView@CDisplayML@@UEAAHAEBVCRchTxtPtr@@JJ@Z`
- size: `2152`
- prototype: `__int64 __fastcall(CDisplayML *__hidden this, const struct CRchTxtPtr *, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update`

## callees

- `0x18000cf50`
- `0x18000e200`
- `0x18000ea70`
- `0x180010a6c`
- `0x180027f70`
- `0x180037740`
- `0x18003aeb0`
- `0x18003b054`
- `0x18003dcd0`
- `0x18003e054`
- `0x18004098c`
- `0x1800455c4`
- `0x180055df4`
- `0x18005756c`
- `0x180091140`
- `0x180092010`

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
0x18000e200  push    rbp
0x18000e202  push    rbx
0x18000e203  push    rsi
0x18000e204  push    rdi
0x18000e205  push    r14
0x18000e207  push    r15
0x18000e209  lea     rbp, [rsp-28h]
0x18000e20e  sub     rsp, 128h
0x18000e215  mov     rax, cs:__security_cookie
0x18000e21c  xor     rax, rsp
0x18000e21f  mov     [rbp+50h+var_50], rax
0x18000e223  mov     r15d, [rcx+0A8h]
0x18000e22a  mov     r14d, r9d
0x18000e22d  mov     r9, [rcx+10h]
0x18000e231  xorps   xmm0, xmm0
0x18000e234  xorps   xmm1, xmm1
0x18000e237  mov     [rsp+150h+var_100], r15d
0x18000e23c  movups  xmmword ptr [rbp+50h+var_80.left], xmm0
0x18000e240  mov     esi, r8d
0x18000e243  mov     rdi, rdx
0x18000e246  movups  xmmword ptr [rbp+50h+var_90.left], xmm1
0x18000e24a  test    byte ptr [r9+0B4h], 1
0x18000e252  mov     rbx, rcx
0x18000e255  jz      loc_18000E7ED
0x18000e25b  mov     ecx, [rbx+38h]
0x18000e25e  mov     [rsp+150h+var_30], r12
0x18000e266  test    cl, 20h
0x18000e269  jnz     loc_18000E6E9
0x18000e26f  mov     eax, [rdi+20h]
0x18000e272  mov     [rbp+50h+var_D0], eax
0x18000e275  cmp     eax, [rbx+80h]
0x18000e27b  jg      loc_18000E6E9
0x18000e281  test    cl, cl
0x18000e283  js      loc_18000E6E9
0x18000e289  mov     eax, [rbx+0A4h]
0x18000e28f  lea     rdx, [rbp+50h+var_80]
0x18000e293  mov     rcx, [r9+30h]
0x18000e297  mov     [rbp+50h+var_C8], eax
0x18000e29a  mov     eax, [rbx+90h]
0x18000e2a0  mov     [rbp+50h+var_CC], eax
0x18000e2a3  mov     rax, [rcx]
0x18000e2a6  mov     [rsp+150h+var_38], r13
0x18000e2ae  mov     r13, [r9+128h]
0x18000e2b5  mov     rax, [rax+0C0h]
0x18000e2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2c1  lea     r8, [rbp+50h+var_80]; struct tagRECT *
0x18000e2c5  mov     rcx, rbx; this
0x18000e2c8  lea     rdx, [rbp+50h+var_90]; struct tagRECT *
0x18000e2cc  call    ?GetViewRect@CDisplay@@QEAAXAEAUtagRECT@@PEBU2@@Z; CDisplay::GetViewRect(tagRECT &,tagRECT const *)
0x18000e2d1  test    r13, r13
0x18000e2d4  jnz     loc_18000E69B
0x18000e2da  mov     eax, [rbx+38h]
0x18000e2dd  mov     r12d, 1
0x18000e2e3  btr     eax, 0Ah
0x18000e2e7  mov     dword ptr [rbx+88h], 0FFFFFFFFh
0x18000e2f1  or      eax, 2
0x18000e2f4  xor     r13d, r13d
0x18000e2f7  mov     [rbx+38h], eax
0x18000e2fa  mov     r9d, r14d; int
0x18000e2fd  mov     eax, [rbx+40h]
0x18000e300  mov     r8d, esi; int
0x18000e303  add     eax, [rbx+90h]
0x18000e309  mov     rdx, rdi; struct CRchTxtPtr *
0x18000e30c  mov     [rbx+8Ch], eax
0x18000e312  mov     rcx, rbx; this
0x18000e315  lea     rax, [rsp+150h+var_F8]
0x18000e31a  mov     [rsp+150h+var_120], rax; struct CLed *
0x18000e31f  mov     [rsp+150h+var_128], r12d; int
0x18000e324  mov     [rsp+150h+var_130], r13d; int
0x18000e329  call    ?RecalcLines@CDisplayML@@AEAAHAEBVCRchTxtPtr@@JJHHPEAVCLed@@@Z; CDisplayML::RecalcLines(CRchTxtPtr const &,long,long,int,int,CLed *)
0x18000e32e  mov     rcx, [rbx+10h]
0x18000e332  test    eax, eax
0x18000e334  jz      loc_18000E664
0x18000e33a  cmp     [rcx+110h], r13d
0x18000e341  jz      loc_18000E821
0x18000e347  movsx   eax, word ptr [rbx+3Ch]
0x18000e34b  cmp     [rbx+0A4h], eax
0x18000e351  jle     loc_18000E852
0x18000e357  mov     ecx, [rbx+40h]
0x18000e35a  mov     edx, [rbx+90h]
0x18000e360  add     ecx, edx
0x18000e362  cmp     [rsp+150h+var_F0], ecx
0x18000e366  jge     loc_18000E605
0x18000e36c  mov     r9d, [rbx+94h]
0x18000e373  mov     r8d, [rsp+150h+var_D8]
0x18000e378  add     r9d, edx
0x18000e37b  mov     ecx, [rsp+150h+var_E4]
0x18000e37f  cmp     r8d, r9d
0x18000e382  jle     loc_18000E87A
0x18000e388  movaps  xmm0, xmmword ptr [rbp+50h+var_80.left]
0x18000e38c  xorps   xmm1, xmm1
0x18000e38f  mov     edi, [rbx+50h]
0x18000e392  mov     r9d, [rsp+150h+var_F4]
0x18000e397  movdqa  xmmword ptr [rbp+50h+var_A0.left], xmm0
0x18000e39c  movups  [rbp+50h+var_60], xmm1
0x18000e3a0  cmp     [rbp+50h+var_D0], edi
0x18000e3a3  jg      loc_18000E900
0x18000e3a9  mov     eax, [rbx+98h]
0x18000e3af  mov     r8d, 0FFFFFFFFh
0x18000e3b5  dec     eax
0x18000e3b7  mov     [rbx+94h], r13
0x18000e3be  cmp     eax, r9d
0x18000e3c1  mov     [rbx+50h], r13d
0x18000e3c5  mov     rax, [rbx]
0x18000e3c8  mov     rcx, rbx
0x18000e3cb  cmovz   edi, [rsp+150h+var_F8]
0x18000e3d0  mov     edx, edi
0x18000e3d2  mov     [rbx+90h], r13d
0x18000e3d9  mov     rax, [rax+108h]
0x18000e3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3e5  mov     [rbp+50h+var_C0], r13
0x18000e3e9  lea     rdx, [rbp+50h+var_C0]
0x18000e3ed  mov     [rbp+50h+var_B8], r13
0x18000e3f1  mov     rcx, rbx
0x18000e3f4  mov     [rbp+50h+var_B0], rbx
0x18000e3f8  mov     [rbp+50h+var_A8], r13
0x18000e3fc  mov     rax, [rbx]
0x18000e3ff  mov     rax, [rax+18h]
0x18000e403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e408  xor     r8d, r8d; int
0x18000e40b  lea     rcx, [rbp+50h+var_C0]; this
0x18000e40f  mov     edx, edi; int
0x18000e411  call    ?RpSetCp@CLinePtr@@QEAAHJH@Z; CLinePtr::RpSetCp(long,int)
0x18000e416  mov     rax, [rbx]
0x18000e419  mov     rcx, rbx
0x18000e41c  mov     edi, dword ptr [rbp+50h+var_B8]
0x18000e41f  mov     edx, edi
0x18000e421  mov     rax, [rax+110h]
0x18000e428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e42d  test    eax, eax
0x18000e42f  jz      loc_18000E928
0x18000e435  mov     eax, [rbx+98h]
0x18000e43b  sub     edi, eax
0x18000e43d  mov     ecx, [rbx+70h]
0x18000e440  test    ecx, ecx
0x18000e442  jle     loc_18000E7C5
0x18000e448  cmp     eax, ecx
0x18000e44a  jge     loc_18000E7C5
0x18000e450  mov     rdx, [rbx+68h]
0x18000e454  test    rdx, rdx
0x18000e457  jz      loc_18000E7C5
0x18000e45d  test    eax, eax
0x18000e45f  js      loc_18000E7C5
0x18000e465  imul    eax, [rbx+78h]
0x18000e469  movsxd  rcx, eax
0x18000e46c  add     rcx, rdx
0x18000e46f  mov     edx, [rbx+94h]
0x18000e475  add     edx, [rbx+90h]
0x18000e47b  test    edi, edi
0x18000e47d  jle     short loc_18000E499
0x18000e47f  nop
0x18000e480  test    byte ptr [rcx+17h], 10h
0x18000e484  mov     eax, r13d
0x18000e487  jnz     short loc_18000E48D
0x18000e489  movsx   eax, word ptr [rcx+0Ch]
0x18000e48d  add     edx, eax
0x18000e48f  dec     edi
0x18000e491  add     rcx, 18h
0x18000e495  test    edi, edi
0x18000e497  jg      short loc_18000E480
0x18000e499  js      loc_18000E938
0x18000e49f  mov     r10d, dword ptr [rbp+50h+var_B8]
0x18000e4a3  mov     edi, r10d
0x18000e4a6  mov     r11d, dword ptr [rbp+50h+var_B8+4]
0x18000e4aa  mov     r9d, r11d
0x18000e4ad  mov     [rbx+90h], edx
0x18000e4b3  test    r10d, r10d
0x18000e4b6  jnz     loc_18000E94D
0x18000e4bc  mov     r8d, [rsp+150h+var_D8]
0x18000e4c1  sub     r9d, r11d
0x18000e4c4  mov     ecx, [rsp+150h+var_E4]
0x18000e4c8  mov     [rbx+50h], r9d
0x18000e4cc  mov     r9d, [rsp+150h+var_F4]
0x18000e4d1  mov     [rbx+98h], r10d
0x18000e4d8  mov     r10d, [rbx+40h]
0x18000e4dc  mov     r11d, [rbp+50h+var_CC]
0x18000e4e0  lea     eax, [r10+r11]
0x18000e4e4  cmp     ecx, eax
0x18000e4e6  jge     short loc_18000E52E
0x18000e4e8  lea     eax, [r10+rdx]
0x18000e4ec  cmp     r8d, eax
0x18000e4ef  jge     short loc_18000E52E
0x18000e4f1  mov     r10d, [rbp+50h+var_90.top]
0x18000e4f5  sub     r10d, r11d
0x18000e4f8  add     r10d, ecx
0x18000e4fb  mov     [rbp+50h+var_A0.top], r10d
0x18000e4ff  cmp     r10d, [rbp+50h+var_A0.bottom]
0x18000e503  jge     loc_18000E9C8
0x18000e509  mov     edi, r8d
0x18000e50c  sub     edi, edx
0x18000e50e  sub     edi, ecx
0x18000e510  add     edi, r11d
0x18000e513  jnz     loc_18000E6F3
0x18000e519  mov     edx, [rbx+90h]
0x18000e51f  cmp     r8d, ecx
0x18000e522  cmovg   ecx, r8d
0x18000e526  sub     ecx, edx
0x18000e528  add     ecx, [rbp+50h+var_90.top]
0x18000e52b  mov     [rbp+50h+var_A0.bottom], ecx
0x18000e52e  mov     eax, [rbp+50h+var_90.top]
0x18000e531  mov     ecx, [rbx+70h]
0x18000e534  sub     eax, edx
0x18000e536  add     eax, [rsp+150h+var_F0]
0x18000e53a  mov     [rbp+50h+var_A0.top], eax
0x18000e53d  cmp     r9d, ecx
0x18000e540  jge     short loc_18000E5B0
0x18000e542  mov     rax, [rbx+10h]
0x18000e546  test    dword ptr [rax+0B4h], 400h
0x18000e550  jnz     short loc_18000E5B0
0x18000e552  test    ecx, ecx
0x18000e554  jle     loc_18000E7CD
0x18000e55a  mov     r8, [rbx+68h]
0x18000e55e  test    r8, r8
0x18000e561  jz      loc_18000E7CD
0x18000e567  test    r9d, r9d
0x18000e56a  js      loc_18000E7CD
0x18000e570  mov     eax, r9d
0x18000e573  imul    eax, [rbx+78h]
0x18000e577  movsxd  rdx, eax
0x18000e57a  add     rdx, r8
0x18000e57d  test    byte ptr [rdx+15h], 20h
0x18000e581  jnz     short loc_18000E5B0
0x18000e583  test    ecx, ecx
0x18000e585  jle     loc_18000E7D5
0x18000e58b  mov     rcx, [rbx+68h]
0x18000e58f  test    rcx, rcx
0x18000e592  jz      loc_18000E7D5
0x18000e598  test    r9d, r9d
0x18000e59b  js      loc_18000E7D5
0x18000e5a1  imul    r9d, [rbx+78h]
0x18000e5a6  movsxd  rax, r9d
0x18000e5a9  add     rax, rcx
0x18000e5ac  or      byte ptr [rax+15h], 60h
0x18000e5b0  mov     rax, [rbx+10h]
0x18000e5b4  lea     rdx, [rbp+50h+var_A0]
0x18000e5b8  xor     r8d, r8d
0x18000e5bb  mov     rcx, [rax+30h]
0x18000e5bf  mov     rax, [rcx]
0x18000e5c2  mov     rax, [rax+48h]
0x18000e5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5cb  mov     edi, r12d
0x18000e5ce  mov     rax, [rbx]
0x18000e5d1  mov     rcx, rbx
0x18000e5d4  mov     rax, [rax+118h]
0x18000e5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5e0  mov     r12d, eax
0x18000e5e3  test    eax, eax
0x18000e5e5  jz      loc_18000E9F3
0x18000e5eb  test    edi, edi
0x18000e5ed  jz      short loc_18000E605
0x18000e5ef  mov     rax, [rbx+10h]
0x18000e5f3  xor     edx, edx
0x18000e5f5  mov     rcx, [rax+30h]
0x18000e5f9  mov     rax, [rcx]
0x18000e5fc  mov     rax, [rax+50h]
0x18000e600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e605  mov     r9d, [rbx+0A8h]
0x18000e60c  cmp     r15d, r9d
0x18000e60f  jz      loc_18000E6B9
0x18000e615  mov     rcx, rbx; this
0x18000e618  call    ?RequestResize@CDisplay@@QEAAJXZ; CDisplay::RequestResize(void)
0x18000e61d  test    eax, eax
0x18000e61f  js      loc_18000EA2A
0x18000e625  mov     rcx, rbx; this
0x18000e628  call    ?DoDeferredUpdateScrollBar@CDisplayML@@AEAAHXZ; CDisplayML::DoDeferredUpdateScrollBar(void)
0x18000e62d  test    eax, eax
0x18000e62f  jnz     loc_18000EA3F
0x18000e635  mov     eax, r12d
0x18000e638  mov     r13, [rsp+150h+var_38]
0x18000e640  mov     r12, [rsp+150h+var_30]
0x18000e648  mov     rcx, [rbp+50h+var_50]
0x18000e64c  xor     rcx, rsp; StackCookie
0x18000e64f  call    __security_check_cookie
0x18000e654  add     rsp, 128h
0x18000e65b  pop     r15
0x18000e65d  pop     r14
0x18000e65f  pop     rdi
0x18000e660  pop     rsi
0x18000e661  pop     rbx
0x18000e662  pop     rbp
0x18000e663  retn
0x18000e664  mov     [rbx+48h], r13d
0x18000e668  xor     r8d, r8d
0x18000e66b  mov     [rbx+90h], r13
0x18000e672  xor     edx, edx
0x18000e674  mov     [rbx+98h], r13d
0x18000e67b  mov     r12d, r13d
0x18000e67e  mov     [rbx+0ACh], r13d
0x18000e685  mov     [rbx+50h], r13d
0x18000e689  mov     rcx, [rcx+30h]
0x18000e68d  mov     rax, [rcx]
0x18000e690  mov     rax, [rax+48h]
0x18000e694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e699  jmp     short loc_18000E635
0x18000e69b  test    byte ptr [r13+88h], 20h
0x18000e6a3  jnz     loc_18000E2DA
0x18000e6a9  mov     dword ptr [r13+90h], 0
0x18000e6b4  jmp     loc_18000E2DA
0x18000e6b9  mov     rax, [rbx+10h]
0x18000e6bd  test    byte ptr [rax+0B4h], 1
  ... truncated ...
```

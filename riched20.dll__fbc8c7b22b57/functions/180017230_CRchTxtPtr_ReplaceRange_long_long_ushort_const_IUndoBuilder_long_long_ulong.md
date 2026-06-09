# CRchTxtPtr::ReplaceRange(long,long,ushort const *,IUndoBuilder *,long,long *,ulong)

- ea: `0x180017230`
- end: `0x180017aca`
- name: `?ReplaceRange@CRchTxtPtr@@QEAAJJJPEBGPEAVIUndoBuilder@@JPEAJK@Z`
- size: `2202`
- prototype: `__int64 __usercall@<rax>(CRchTxtPtr *__hidden this@<rcx>, int@<edx>, int@<r8d>, const unsigned __int16 *@<r9>, struct IUndoBuilder *, int, int *, unsigned int)`
- caller_count: `10`
- callee_count: `33`
- tags: `loader_planting`

## callers

- `0x180016470`
- `0x18004e110`
- `0x180054028`
- `0x180054a88`
- `0x180056160`
- `0x18006024c`
- `0x1800711d0`
- `0x180073374`
- `0x180073890`
- `0x180076678`

## callees

- `0x180006370`
- `0x180006570`
- `0x1800066b0`
- `0x180009970`
- `0x18000f280`
- `0x180010260`
- `0x180015448`
- `0x180017230`
- `0x1800182a0`
- `0x180018330`
- `0x180018380`
- `0x180019e4c`
- `0x18001e3e0`
- `0x18001eae0`
- `0x18001f120`
- `0x18001f230`
- `0x18001f980`
- `0x180022ad4`
- `0x1800267a0`
- `0x180026e30`
- `0x18002ee70`
- `0x18002f428`
- `0x1800301a0`
- `0x180037e20`
- `0x180038208`
- `0x1800393c0`
- `0x18003ccbc`
- `0x180040214`
- `0x180042a6c`
- `0x18005d214`
- `0x180071d44`
- `0x180093bbe`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CRchTxtPtr::ReplaceRange(
        CRchTxtPtr *this,
        int a2,
        unsigned int a3,
        unsigned __int16 *a4,
        struct IUndoBuilder *a5,
        int a6,
        int *a7,
        char a8)
{
  unsigned int v8; // r13d
  __int64 v9; // r15
  int v11; // esi
  unsigned int v12; // edi
  CDisplay *v13; // rcx
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rax
  CNotifyMgr *v18; // r12
  CRchTxtPtr *v19; // rbx
  unsigned int v20; // r12d
  int v21; // ecx
  int v22; // eax
  int v23; // edi
  int v24; // ebx
  unsigned int v25; // edi
  unsigned __int16 *v26; // r9
  int *v27; // r10
  int v28; // ebx
  int v29; // r11d
  CRchTxtPtr *v30; // rbx
  unsigned int v31; // r12d
  unsigned int v32; // r15d
  int v33; // edx
  int v34; // eax
  int v36; // edx
  int v37; // edx
  CRunPtrBase *v38; // rcx
  int v39; // r8d
  __int64 v40; // rdx
  __int64 *v41; // rax
  int IsValid; // ebx
  CRunPtrBase *v43; // rcx
  int v44; // edx
  struct IAntiEvent *v45; // rax
  struct IAntiEvent *v46; // r9
  int v47; // ecx
  int v48; // eax
  int v49; // ecx
  int v50; // ebx
  __int64 v51; // rcx
  struct IAntiEvent *v52; // rax
  char *v53; // r9
  __int64 v54; // rax
  int v55; // edx
  __int128 v56; // xmm1
  __int128 v57; // xmm0
  int v58; // ebx
  __int16 Format; // ax
  unsigned __int16 v60; // di
  __int16 v61; // ax
  unsigned int v62; // eax
  int v63; // r8d
  int v64; // r9d
  __int16 v65; // di
  bool v66; // zf
  CObjectMgr *ObjectMgr; // rax
  int TextLength; // eax
  int v69; // r8d
  int v70; // [rsp+60h] [rbp-81h]
  void *Src; // [rsp+68h] [rbp-79h] BYREF
  int v72; // [rsp+70h] [rbp-71h]
  int v73; // [rsp+74h] [rbp-6Dh] BYREF
  unsigned int v74; // [rsp+78h] [rbp-69h]
  int v75; // [rsp+7Ch] [rbp-65h]
  unsigned int v76; // [rsp+80h] [rbp-61h]
  struct IAntiEvent *v77; // [rsp+88h] [rbp-59h] BYREF
  __int128 v78; // [rsp+90h] [rbp-51h] BYREF
  __int128 v79; // [rsp+A0h] [rbp-41h]
  struct IAntiEvent *v80; // [rsp+B0h] [rbp-31h] BYREF
  __int64 v81; // [rsp+B8h] [rbp-29h]
  CDisplay *v82; // [rsp+C0h] [rbp-21h]
  _OWORD v83[5]; // [rsp+C8h] [rbp-19h] BYREF
  int v84; // [rsp+130h] [rbp+4Fh]
  unsigned int v85; // [rsp+130h] [rbp+4Fh]
  int v86; // [rsp+138h] [rbp+57h]
  int v87; // [rsp+138h] [rbp+57h]
  int EOP; // [rsp+138h] [rbp+57h]

  v8 = *((_DWORD *)this + 8);
  v9 = *((_QWORD *)this + 5);
  v11 = a2;
  v73 = 0;
  v70 = 0;
  v12 = v8;
  v86 = a2;
  v13 = *(CDisplay **)(v9 + 64);
  v72 = 0;
  v74 = v8;
  v76 = v8;
  v75 = 0;
  v81 = v9;
  v77 = 0;
  v80 = 0;
  v82 = v13;
  CDisplay::Freeze(v13);
  v14 = *((_QWORD *)this + 5);
  if ( v14 )
    v15 = *(_DWORD *)(*((_QWORD *)this + 2) + 24LL);
  else
    v15 = 0;
  v16 = v15 - *((_DWORD *)this + 8);
  if ( v11 < 0 || v11 > v16 )
    v11 = v16;
  if ( (*(_BYTE *)(v14 + 180) & 1) != 0 && v11 == v16 )
  {
    v36 = ((*(_DWORD *)(v9 + 180) & 0x80000) != 0) + 1;
    v84 = v36;
    if ( v36 <= v11 )
      v11 -= v36;
    if ( (unsigned int)CRunPtrBase::IsValid((CRchTxtPtr *)((char *)this + 64)) )
    {
      CRunPtrBase::AdjustBackward(v38);
      if ( (*((_WORD *)CRchTxtPtr::GetPF(this) + 1) & 0x4000) != 0 )
        v84 = 0;
    }
    else
    {
      v84 = v37;
    }
  }
  else
  {
    v17 = *((_QWORD *)this + 8);
    v84 = 0;
    if ( v17 && *(_DWORD *)(v17 + 8) )
    {
      CRunPtrBase::AdjustForward((CRchTxtPtr *)((char *)this + 64));
      if ( v11 )
      {
        v56 = *((_OWORD *)this + 1);
        v83[0] = *((_OWORD *)this + 4);
        v57 = *((_OWORD *)this + 2);
        v78 = v56;
        v79 = v57;
        CTxtPtr::AdvanceCp((CTxtPtr *)&v78, v11);
        CRunPtrBase::AdvanceCp((CRunPtrBase *)v83, v11);
        LODWORD(Src) = 0;
        if ( (unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)&v78) )
        {
          LODWORD(Src) = -(int)CTxtPtr::BackupCpCRLF((CTxtPtr *)&v78, 1);
          CTxtPtr::AdvanceCp((CTxtPtr *)&v78, (int)Src);
        }
        EOP = CTxtPtr::FindEOP((CTxtPtr *)&v78, 0x3FFFFFFF, 0);
        if ( !*((_DWORD *)this + 8) || (unsigned int)CTxtPtr::IsAfterEOP((CRchTxtPtr *)((char *)this + 16)) )
        {
          v58 = 1;
          CTxtPtr::AdvanceCp((CTxtPtr *)&v78, *((_DWORD *)this + 8) - v79);
          v86 = v11 + EOP;
        }
        else
        {
          v58 = 0;
          if ( (_DWORD)Src != v11 )
            goto LABEL_110;
          if ( (a8 & 8) == 0 )
          {
            Format = CFormatRunPtr::GetFormat((CFormatRunPtr *)v83);
            v60 = *((_WORD *)CTxtArray::GetParaFormat((CTxtArray *)(v9 + 248), Format) + 1);
            v61 = CFormatRunPtr::GetFormat((CRchTxtPtr *)((char *)this + 64));
            if ( ((*((_WORD *)CTxtArray::GetParaFormat((CTxtArray *)(v9 + 248), v61) + 1) | v60) & 0x4000) != 0 )
            {
LABEL_71:
              CDisplay::Thaw(v82);
              return 0;
            }
            v12 = v8;
          }
          if ( HIDWORD(v83[0]) )
          {
LABEL_110:
            v86 = v11 + EOP;
          }
          else
          {
            v70 = EOP;
            v62 = EOP + v8;
            v86 = v11 + EOP;
            v76 = v62;
          }
          CTxtPtr::AdvanceCp((CTxtPtr *)&v78, *((_DWORD *)this + 8) - v79);
          v72 = CTxtPtr::FindEOP((CTxtPtr *)&v78, -1073741823, 0);
        }
        CFormatRunPtr::GetFormat((CFormatRunPtr *)v83);
        LODWORD(Src) = CFormatRunPtr::GetFormat((CRchTxtPtr *)((char *)this + 64));
        if ( v63 != (_DWORD)Src )
        {
          if ( !v58 && !v70 )
          {
            v70 = v64;
            v74 = v64 + v8;
          }
          v65 = *((_WORD *)CTxtArray::GetParaFormat((CTxtArray *)(v9 + 248), v63) + 1);
          v66 = ((*((_BYTE *)CTxtArray::GetParaFormat((CTxtArray *)(v9 + 248), (int)Src) + 2) ^ (unsigned __int8)v65) & 1) == 0;
          v12 = v74;
          if ( !v66 )
            v75 = 1;
        }
      }
      else
      {
        v40 = (unsigned int)CFormatRunPtr::GetFormat((CRchTxtPtr *)((char *)this + 64));
        Src = 0;
        if ( (int)v40 < 0 )
          v40 = (unsigned int)*(__int16 *)(v9 + 278);
        if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, void **))(*(_QWORD *)qword_1800A72C8 + 32LL))(
               qword_1800A72C8,
               v40,
               &Src) >= 0 )
        {
          v41 = (__int64 *)Src;
        }
        else
        {
          v41 = g_defaultPF;
          Src = g_defaultPF;
        }
        if ( (*((_WORD *)v41 + 1) & 0x4000) != 0
          && (unsigned int)CTxtPtr::IsAtEOP((CRchTxtPtr *)((char *)this + 16))
          && (a8 & 8) == 0 )
        {
          goto LABEL_71;
        }
      }
    }
  }
  if ( !(v11 + a3) )
  {
    if ( a7 )
      *a7 = 0;
    goto LABEL_71;
  }
  v18 = (CNotifyMgr *)(v9 + 128);
  if ( v9 != -128 )
  {
    v19 = *(CRchTxtPtr **)v18;
    if ( *(_QWORD *)v18 )
    {
      v20 = v76;
      do
      {
        if ( v19 != this )
          (**(void (__fastcall ***)(CRchTxtPtr *, _QWORD, _QWORD, _QWORD, unsigned int, int))v19)(
            v19,
            v8,
            (unsigned int)v11,
            a3,
            v12,
            v20 + v11);
        v19 = (CRchTxtPtr *)*((_QWORD *)v19 + 1);
      }
      while ( v19 );
      v9 = v81;
      v18 = (CNotifyMgr *)(v81 + 128);
    }
  }
  if ( a6 >= 0 )
    CRchTxtPtr::Check_rpCF(this);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + 32LL))(*((_QWORD *)this + 5) + 8LL) )
  {
    ObjectMgr = CTxtEdit::GetObjectMgr((CTxtEdit *)v9);
    CObjectMgr::ReplaceRange(ObjectMgr, v8, v11, a5);
  }
  if ( (*(_BYTE *)(v9 + 192) & 1) != 0 )
  {
    v39 = 0;
    if ( v75 )
      v39 = v70;
    v23 = v11 + v84;
    v22 = CRchTxtPtr::ExpandRangeFormatting(this, v11 + v84, v39, &v73);
    v21 = v84;
  }
  else
  {
    v21 = v84;
    v22 = 0;
    v23 = v84 + v11;
  }
  v24 = CRchTxtPtr::ReplaceRangeFormatting(this, v23, v21 + a3, a6, a5, &v77, &v80, v70, v72, v86, v22, v73);
  if ( v84 )
  {
    CRunPtrBase::AdvanceCp((CRchTxtPtr *)((char *)this + 48), -v84);
    CRunPtrBase::AdvanceCp((CRchTxtPtr *)((char *)this + 64), -v84);
  }
  v25 = 0;
  if ( v24 >= 0 )
  {
    v26 = a4;
    v27 = (int *)((char *)this + 16);
    v28 = a3;
    Src = a4;
    v85 = a3;
    if ( v11 < 0 )
    {
      TextLength = CTxtPtr::GetTextLength((CRchTxtPtr *)((char *)this + 16));
      v29 = TextLength - v27[4];
      v87 = v29;
    }
    else
    {
      v29 = v11;
      v87 = v11;
    }
    if ( a5 )
    {
      CTxtPtr::HandleReplaceRangeUndo((CTxtPtr *)v27, v29, a3, a5, v77, v80);
      v29 = v87;
      v27 = (int *)((char *)this + 16);
      v26 = (unsigned __int16 *)Src;
    }
    if ( v29 <= 0 )
    {
LABEL_30:
      if ( v28 <= 0 )
      {
        if ( v29 > 0 )
LABEL_80:
          CTxtPtr::DeleteRange((CTxtPtr *)v27, v29);
      }
      else
      {
LABEL_31:
        v25 += CTxtPtr::InsertRange((CTxtPtr *)v27, v28, v26);
      }
      if ( v25 != a3 )
      {
        if ( v18 )
          CNotifyMgr::NotifyPreReplaceRange(v18, 0, -2, 0, 0, 0, 0);
        CTxtStory::DeleteFormatRuns((CTxtStory *)(v9 + 248));
      }
      goto LABEL_33;
    }
    while ( 1 )
    {
      if ( v28 <= 0 )
        goto LABEL_80;
      v45 = (struct IAntiEvent *)CArrayBase::Elem(*(CArrayBase **)v27, v27[2]);
      v77 = v45;
      if ( !v45 )
        goto LABEL_31;
      CTxtBlk::MoveGap(v45, v27[3]);
      v29 = v87;
      v27 = (int *)((char *)this + 16);
      v46 = v77;
      v47 = *(_DWORD *)v77 - *((_DWORD *)this + 7);
      if ( v87 < v47 )
        v47 = v87;
      if ( v47 > 0 )
      {
        v29 = v87 - v47;
        *(_DWORD *)v77 -= v47;
        v87 -= v47;
        *(_DWORD *)(*(_QWORD *)v27 + 24LL) -= v47;
      }
      v48 = *((_DWORD *)v46 + 5) / 2 - *(_DWORD *)v46;
      v49 = v48 - 128;
      if ( v48 <= 128 )
        v49 = *((_DWORD *)v46 + 5) / 2 - *(_DWORD *)v46;
      v73 = v49;
      if ( v49 > v28 )
        break;
      if ( v49 > 0 )
        goto LABEL_91;
      v26 = (unsigned __int16 *)Src;
LABEL_92:
      v55 = v27[2];
      if ( v55 < *(_DWORD *)(*(_QWORD *)v27 + 8LL) - 1 )
      {
        if ( v29 )
        {
          *((_QWORD *)v27 + 1) = (unsigned int)(v55 + 1);
          if ( v29 > 0 )
            continue;
        }
      }
      goto LABEL_30;
    }
    v49 = v28;
    v73 = v28;
LABEL_91:
    v50 = 2 * v49;
    memmove_0((void *)(*((_QWORD *)v46 + 1) + 2LL * *((int *)this + 7)), Src, 2 * v49);
    v51 = (unsigned int)v73;
    v27 = (int *)((char *)this + 16);
    v52 = v77;
    v25 += v73;
    *((_DWORD *)this + 8) += v73;
    *((_DWORD *)this + 7) += v51;
    v53 = (char *)Src;
    *((_DWORD *)v52 + 4) += v50;
    *(_DWORD *)v52 += v51;
    v85 -= v51;
    v54 = *((_QWORD *)this + 2);
    v26 = (unsigned __int16 *)&v53[2 * v51];
    v28 = v85;
    v29 = v87;
    Src = v26;
    *(_DWORD *)(v54 + 24) += v51;
    goto LABEL_92;
  }
LABEL_33:
  if ( (*(_BYTE *)(v9 + 192) & 1) != 0 && (signed int)v8 <= *(_DWORD *)(v9 + 220) && (v11 || v25) )
  {
    IsValid = CRunPtrBase::IsValid((CRchTxtPtr *)((char *)this + 48));
    CTxtEdit::SetContextDirection((CTxtEdit *)v9, 0);
    if ( !IsValid )
    {
      if ( (unsigned int)CRunPtrBase::IsValid((CRchTxtPtr *)((char *)this + 48)) )
      {
        v44 = *((_DWORD *)this + 8);
        *((_QWORD *)v43 + 1) = 0;
        CRunPtrBase::AdvanceCp(v43, v44);
      }
    }
  }
  if ( v18 )
  {
    v30 = *(CRchTxtPtr **)v18;
    if ( *(_QWORD *)v18 )
    {
      v31 = v74;
      v32 = v76;
      do
      {
        if ( v30 != this )
          (*(void (__fastcall **)(CRchTxtPtr *, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int))(*(_QWORD *)v30 + 8LL))(
            v30,
            v8,
            (unsigned int)v11,
            v25,
            v31,
            v32 + v11);
        v30 = (CRchTxtPtr *)*((_QWORD *)v30 + 1);
      }
      while ( v30 );
      v9 = v81;
    }
  }
  CCallMgr::SetChangeEvent(*(_QWORD *)(v9 + 144), 1);
  v33 = v75;
  if ( a7 )
  {
    v34 = 0;
    if ( v75 )
      v34 = v70;
    *a7 = v34;
  }
  if ( (*(_DWORD *)(v9 + 192) & 0x61086013) != 0 )
  {
    if ( (a8 & 2) == 0 && ((*(_DWORD *)(v9 + 180) & 0x10000) == 0 || a4 && *a4 == 0xFFFC) )
    {
      v69 = 0;
      if ( v33 )
        v69 = v70;
      CRchTxtPtr::ItemizeReplaceRange(this, a3, v69, a5, 0);
    }
    else
    {
      *(_WORD *)(v9 + 188) |= 8u;
    }
  }
  CDisplay::Thaw(v82);
  return v25;
}

```

## disassembly

```asm
0x180017230  mov     [rsp-8+arg_18], r9
0x180017235  mov     [rsp-8+arg_10], r8d
0x18001723a  push    rbp
0x18001723b  push    rbx
0x18001723c  push    rsi
0x18001723d  push    rdi
0x18001723e  push    r12
0x180017240  push    r13
0x180017242  push    r14
0x180017244  push    r15
0x180017246  lea     rbp, [rsp-7]
0x18001724b  sub     rsp, 0E8h
0x180017252  mov     r13d, [rcx+20h]
0x180017256  xor     r12d, r12d
0x180017259  mov     r15, [rcx+28h]
0x18001725d  mov     r14, rcx
0x180017260  mov     esi, edx
0x180017262  mov     [rbp+3Fh+var_AC], r12d
0x180017266  mov     [rsp+120h+var_C0], r12d
0x18001726b  mov     edi, r13d
0x18001726e  mov     [rbp+3Fh+arg_8], edx
0x180017271  mov     rax, [r15+40h]
0x180017275  mov     rcx, rax; this
0x180017278  mov     [rbp+3Fh+var_B0], r12d
0x18001727c  mov     [rbp+3Fh+var_A8], r13d
0x180017280  mov     [rbp+3Fh+var_A0], r13d
0x180017284  mov     [rbp+3Fh+var_A4], r12d
0x180017288  mov     [rbp+3Fh+var_68], r15
0x18001728c  mov     [rbp+3Fh+var_98], r12
0x180017290  mov     [rbp+3Fh+var_70], r12
0x180017294  mov     [rbp+3Fh+var_60], rax
0x180017298  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18001729d  mov     rdx, [r14+28h]
0x1800172a1  test    rdx, rdx
0x1800172a4  jz      loc_1800177CA
0x1800172aa  mov     rax, [r14+10h]
0x1800172ae  mov     ecx, [rax+18h]
0x1800172b1  sub     ecx, [r14+20h]
0x1800172b5  test    esi, esi
0x1800172b7  js      loc_1800177F7
0x1800172bd  cmp     esi, ecx
0x1800172bf  jg      loc_1800177F7
0x1800172c5  test    byte ptr [rdx+0B4h], 1
0x1800172cc  jnz     loc_18001753B
0x1800172d2  mov     rax, [r14+40h]
0x1800172d6  mov     [rbp+3Fh+arg_0], r12d
0x1800172da  test    rax, rax
0x1800172dd  jz      short loc_1800172E9
0x1800172df  cmp     [rax+8], r12d
0x1800172e3  jnz     loc_1800175A0
0x1800172e9  mov     eax, [rbp+3Fh+arg_10]
0x1800172ec  add     eax, esi
0x1800172ee  jz      loc_180017621
0x1800172f4  lea     r12, [r15+80h]
0x1800172fb  test    r12, r12
0x1800172fe  jz      short loc_18001734D
0x180017300  mov     rbx, [r12]
0x180017304  test    rbx, rbx
0x180017307  jz      short loc_18001734D
0x180017309  mov     r12d, [rbp+3Fh+var_A0]
0x18001730d  mov     r15d, [rbp+3Fh+arg_10]
0x180017311  cmp     rbx, r14
0x180017314  jz      short loc_180017339
0x180017316  mov     rax, [rbx]
0x180017319  lea     ecx, [r12+rsi]
0x18001731d  mov     dword ptr [rsp+120h+var_F8], ecx
0x180017321  mov     r9d, r15d
0x180017324  mov     r8d, esi
0x180017327  mov     dword ptr [rsp+120h+var_100], edi
0x18001732b  mov     edx, r13d
0x18001732e  mov     rcx, rbx
0x180017331  mov     rax, [rax]
0x180017334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017339  mov     rbx, [rbx+8]
0x18001733d  test    rbx, rbx
0x180017340  jnz     short loc_180017311
0x180017342  mov     r15, [rbp+3Fh+var_68]
0x180017346  lea     r12, [r15+80h]
0x18001734d  mov     ebx, [rbp+3Fh+arg_28]
0x180017350  test    ebx, ebx
0x180017352  js      short loc_18001735C
0x180017354  mov     rcx, r14; this
0x180017357  call    ?Check_rpCF@CRchTxtPtr@@QEAAHXZ; CRchTxtPtr::Check_rpCF(void)
0x18001735c  mov     rcx, [r14+28h]
0x180017360  add     rcx, 8
0x180017364  mov     rax, [rcx]
0x180017367  mov     rax, [rax+20h]
0x18001736b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017370  test    eax, eax
0x180017372  jnz     loc_1800179CA
0x180017378  test    byte ptr [r15+0C0h], 1
0x180017380  jnz     loc_180017578
0x180017386  mov     ecx, [rbp+3Fh+arg_0]
0x180017389  xor     eax, eax
0x18001738b  lea     edi, [rcx+rsi]
0x18001738e  mov     r8d, [rbp+3Fh+arg_10]
0x180017392  mov     r9d, ebx; int
0x180017395  add     r8d, ecx; int
0x180017398  mov     edx, edi; int
0x18001739a  mov     ecx, [rbp+3Fh+var_AC]
0x18001739d  mov     [rsp+120h+var_C8], ecx; int
0x1800173a1  mov     rcx, r14; this
0x1800173a4  mov     [rsp+120h+var_D0], eax; int
0x1800173a8  mov     eax, [rbp+3Fh+arg_8]
0x1800173ab  mov     [rsp+120h+var_D8], eax; int
0x1800173af  mov     eax, [rbp+3Fh+var_B0]
0x1800173b2  mov     [rsp+120h+var_E0], eax; int
0x1800173b6  mov     eax, [rsp+120h+var_C0]
0x1800173ba  mov     [rsp+120h+var_E8], eax; int
0x1800173be  lea     rax, [rbp+3Fh+var_70]
0x1800173c2  mov     [rsp+120h+var_F0], rax; struct IAntiEvent **
0x1800173c7  lea     rax, [rbp+3Fh+var_98]
0x1800173cb  mov     [rsp+120h+var_F8], rax; struct IAntiEvent **
0x1800173d0  mov     rax, [rbp+3Fh+arg_20]
0x1800173d4  mov     [rsp+120h+var_100], rax; struct IUndoBuilder *
0x1800173d9  call    ?ReplaceRangeFormatting@CRchTxtPtr@@AEAAJJJJPEAVIUndoBuilder@@PEAPEAVIAntiEvent@@1JJJJJ@Z; CRchTxtPtr::ReplaceRangeFormatting(long,long,long,IUndoBuilder *,IAntiEvent * *,IAntiEvent * *,long,long,long,long,long)
0x1800173de  mov     edi, [rbp+3Fh+arg_0]
0x1800173e1  mov     ebx, eax
0x1800173e3  test    edi, edi
0x1800173e5  jnz     loc_1800179E9
0x1800173eb  xor     edi, edi
0x1800173ed  test    ebx, ebx
0x1800173ef  js      short loc_180017447
0x1800173f1  mov     r9, [rbp+3Fh+arg_18]
0x1800173f5  lea     r10, [r14+10h]
0x1800173f9  mov     ebx, [rbp+3Fh+arg_10]
0x1800173fc  mov     [rbp+3Fh+Src], r9
0x180017400  mov     [rbp+3Fh+arg_0], ebx
0x180017403  test    esi, esi
0x180017405  js      loc_180017A06
0x18001740b  mov     r11d, esi
0x18001740e  mov     [rbp+3Fh+arg_8], esi
0x180017411  mov     rcx, [rbp+3Fh+arg_20]
0x180017415  test    rcx, rcx
0x180017418  jnz     loc_180017A1E
0x18001741e  test    r11d, r11d
0x180017421  jg      loc_1800176C0
0x180017427  test    ebx, ebx
0x180017429  jle     loc_1800176A1
0x18001742f  mov     r8, r9; unsigned __int16 *
0x180017432  mov     edx, ebx; int
0x180017434  mov     rcx, r10; this
0x180017437  call    ?InsertRange@CTxtPtr@@AEAAJJPEBG@Z; CTxtPtr::InsertRange(long,ushort const *)
0x18001743c  add     edi, eax
0x18001743e  cmp     edi, [rbp+3Fh+arg_10]
0x180017441  jnz     loc_180017A64
0x180017447  test    byte ptr [r15+0C0h], 1
0x18001744f  jnz     loc_180017644
0x180017455  test    r12, r12
0x180017458  jz      short loc_1800174A7
0x18001745a  mov     rbx, [r12]
0x18001745e  test    rbx, rbx
0x180017461  jz      short loc_1800174A7
0x180017463  mov     r12d, [rbp+3Fh+var_A8]
0x180017467  mov     r15d, [rbp+3Fh+var_A0]
0x18001746b  nop     dword ptr [rax+rax+00h]
0x180017470  cmp     rbx, r14
0x180017473  jz      short loc_18001749A
0x180017475  mov     rax, [rbx]
0x180017478  lea     ecx, [r15+rsi]
0x18001747c  mov     dword ptr [rsp+120h+var_F8], ecx
0x180017480  mov     r9d, edi
0x180017483  mov     r8d, esi
0x180017486  mov     dword ptr [rsp+120h+var_100], r12d
0x18001748b  mov     edx, r13d
0x18001748e  mov     rcx, rbx
0x180017491  mov     rax, [rax+8]
0x180017495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001749a  mov     rbx, [rbx+8]
0x18001749e  test    rbx, rbx
0x1800174a1  jnz     short loc_180017470
0x1800174a3  mov     r15, [rbp+3Fh+var_68]
0x1800174a7  mov     rcx, [r15+90h]
0x1800174ae  mov     edx, 1
0x1800174b3  call    ?SetChangeEvent@CCallMgr@@QEAAXW4CHANGETYPE@@@Z; CCallMgr::SetChangeEvent(CHANGETYPE)
0x1800174b8  mov     r9, [rbp+3Fh+arg_30]
0x1800174bc  mov     edx, [rbp+3Fh+var_A4]
0x1800174bf  mov     ecx, [rsp+120h+var_C0]
0x1800174c3  test    r9, r9
0x1800174c6  jz      short loc_1800174D2
0x1800174c8  xor     eax, eax
0x1800174ca  test    edx, edx
0x1800174cc  cmovnz  eax, ecx
0x1800174cf  mov     [r9], eax
0x1800174d2  test    dword ptr [r15+0C0h], 61086013h
0x1800174dd  jz      short loc_18001751B
0x1800174df  test    byte ptr [rbp+3Fh+arg_38], 2
0x1800174e6  jnz     short loc_180017512
0x1800174e8  test    dword ptr [r15+0B4h], 10000h
0x1800174f3  jz      loc_180017AA5
0x1800174f9  mov     rax, [rbp+3Fh+arg_18]
0x1800174fd  test    rax, rax
0x180017500  jz      short loc_180017512
0x180017502  mov     r8d, 0FFFCh
0x180017508  cmp     [rax], r8w
0x18001750c  jz      loc_180017AA5
0x180017512  or      word ptr [r15+0BCh], 8
0x18001751b  mov     rcx, [rbp+3Fh+var_60]; this
0x18001751f  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x180017524  mov     eax, edi
0x180017526  add     rsp, 0E8h
0x18001752d  pop     r15
0x18001752f  pop     r14
0x180017531  pop     r13
0x180017533  pop     r12
0x180017535  pop     rdi
0x180017536  pop     rsi
0x180017537  pop     rbx
0x180017538  pop     rbp
0x180017539  retn
0x18001753b  cmp     esi, ecx
0x18001753d  jnz     loc_1800172D2
0x180017543  test    dword ptr [r15+0B4h], 80000h
0x18001754e  mov     edx, r12d
0x180017551  setnz   dl
0x180017554  inc     edx
0x180017556  mov     [rbp+3Fh+arg_0], edx
0x180017559  cmp     edx, esi
0x18001755b  jg      short loc_18001755F
0x18001755d  sub     esi, edx
0x18001755f  lea     rcx, [r14+40h]; this
0x180017563  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x180017568  test    eax, eax
0x18001756a  jnz     loc_1800177D2
0x180017570  mov     [rbp+3Fh+arg_0], edx
0x180017573  jmp     loc_1800172E9
0x180017578  mov     edi, [rbp+3Fh+arg_0]
0x18001757b  lea     r9, [rbp+3Fh+var_AC]; int *
0x18001757f  xor     r8d, r8d
0x180017582  mov     rcx, r14; this
0x180017585  cmp     [rbp+3Fh+var_A4], r8d
0x180017589  cmovnz  r8d, [rsp+120h+var_C0]; int
0x18001758f  add     edi, esi
0x180017591  mov     edx, edi; int
0x180017593  call    ?ExpandRangeFormatting@CRchTxtPtr@@QEAAJJJAEAJ@Z; CRchTxtPtr::ExpandRangeFormatting(long,long,long &)
0x180017598  mov     ecx, [rbp+3Fh+arg_0]
0x18001759b  jmp     loc_18001738E
0x1800175a0  lea     rcx, [r14+40h]; this
0x1800175a4  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x1800175a9  test    esi, esi
0x1800175ab  jnz     loc_1800177FE
0x1800175b1  lea     rcx, [r14+40h]; this
0x1800175b5  call    ?GetFormat@CFormatRunPtr@@QEBAFXZ; CFormatRunPtr::GetFormat(void)
0x1800175ba  movsx   edx, ax
0x1800175bd  mov     [rbp+3Fh+Src], r12
0x1800175c1  test    edx, edx
0x1800175c3  jns     short loc_1800175CD
0x1800175c5  movsx   edx, word ptr [r15+116h]
0x1800175cd  mov     rcx, cs:qword_1800A72C8
0x1800175d4  lea     r8, [rbp+3Fh+Src]
0x1800175d8  mov     rax, [rcx]
0x1800175db  mov     rax, [rax+20h]
0x1800175df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175e4  test    eax, eax
0x1800175e6  jns     short loc_18001763E
0x1800175e8  lea     rax, ?g_defaultPF@@3VCParaFormat@@A; CParaFormat g_defaultPF
0x1800175ef  mov     [rbp+3Fh+Src], rax
0x1800175f3  mov     ecx, 4000h
0x1800175f8  test    [rax+2], cx
0x1800175fc  jz      loc_1800172E9
0x180017602  lea     rcx, [r14+10h]; this
0x180017606  call    ?IsAtEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAtEOP(void)
0x18001760b  test    eax, eax
0x18001760d  jz      loc_1800172E9
0x180017613  test    byte ptr [rbp+3Fh+arg_38], 8
0x18001761a  jz      short loc_18001762E
0x18001761c  jmp     loc_1800172E9
0x180017621  mov     rax, [rbp+3Fh+arg_30]
0x180017625  test    rax, rax
0x180017628  jnz     loc_1800179C2
0x18001762e  mov     rcx, [rbp+3Fh+var_60]; this
0x180017632  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x180017637  xor     eax, eax
0x180017639  jmp     loc_180017526
0x18001763e  mov     rax, [rbp+3Fh+Src]
0x180017642  jmp     short loc_1800175F3
0x180017644  cmp     r13d, [r15+0DCh]
0x18001764b  jg      loc_180017455
0x180017651  test    esi, esi
0x180017653  jnz     short loc_18001765D
0x180017655  test    edi, edi
0x180017657  jz      loc_180017455
0x18001765d  lea     rcx, [r14+30h]; this
0x180017661  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x180017666  xor     edx, edx; int
0x180017668  mov     rcx, r15; this
0x18001766b  mov     ebx, eax
0x18001766d  call    ?SetContextDirection@CTxtEdit@@QEAAXH@Z; CTxtEdit::SetContextDirection(int)
0x180017672  test    ebx, ebx
0x180017674  jnz     loc_180017455
0x18001767a  lea     rcx, [r14+30h]; this
0x18001767e  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x180017683  test    eax, eax
0x180017685  jz      loc_180017455
0x18001768b  mov     edx, [r14+20h]; int
0x18001768f  mov     qword ptr [rcx+8], 0
0x180017697  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18001769c  jmp     loc_180017455
0x1800176a1  test    r11d, r11d
0x1800176a4  jle     loc_18001743E
  ... truncated ...
```

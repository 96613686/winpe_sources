# CTxtSelection::Update(int)

- ea: `0x180035230`
- end: `0x1800357e3`
- name: `?Update@CTxtSelection@@UEAAHH@Z`
- size: `1459`
- prototype: `__int64 __fastcall(CTxtSelection *__hidden this, int)`
- caller_count: `0`
- callee_count: `30`
- tags: `installer_update`

## callees

- `0x180006570`
- `0x180009970`
- `0x18000c840`
- `0x18000dad0`
- `0x18000f280`
- `0x18000fe40`
- `0x180015448`
- `0x180016700`
- `0x180016d90`
- `0x180019940`
- `0x18001eae0`
- `0x1800267a0`
- `0x180035230`
- `0x1800357ec`
- `0x180035878`
- `0x180035b04`
- `0x180037b10`
- `0x18003cc90`
- `0x180045000`
- `0x180045164`
- `0x180048e94`
- `0x18004ae60`
- `0x18004b1dc`
- `0x18004b234`
- `0x1800612c4`
- `0x1800613b8`
- `0x180061404`
- `0x1800614b8`
- `0x180073f38`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CTxtSelection::Update(CTxtSelection *this, int a2)
{
  int v3; // ecx
  CTxtPtr *v4; // r14
  int v5; // esi
  __int64 v6; // rbx
  unsigned int v7; // r13d
  int v8; // r13d
  int v9; // edx
  __int16 Format; // ax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 v13; // xmm0_8
  int v14; // eax
  int v15; // edx
  int v16; // ebx
  int v17; // r13d
  __int16 v18; // cx
  int v19; // esi
  int *v20; // r8
  int *v21; // r9
  int v22; // r14d
  int IsCollapsed; // r12d
  int v24; // esi
  int CchLeft; // eax
  int v26; // eax
  int v27; // edx
  int v28; // r12d
  int ExpandedBackward; // ebx
  int v30; // r14d
  int v31; // edx
  int v32; // ecx
  __int128 v33; // xmm0
  int v34; // esi
  int v35; // ebx
  int UnhiddenForward; // ebx
  int v37; // edx
  int v38; // ecx
  unsigned int v39; // ebx
  __int64 v40; // rax
  int v41; // ecx
  int v43; // [rsp+30h] [rbp-38h]
  int v44; // [rsp+34h] [rbp-34h]
  __int64 v45; // [rsp+38h] [rbp-30h]
  __int128 v46; // [rsp+40h] [rbp-28h] BYREF
  __int64 v47; // [rsp+50h] [rbp-18h]
  int v48; // [rsp+B0h] [rbp+48h] BYREF
  int v49; // [rsp+B8h] [rbp+50h]
  int v50; // [rsp+C0h] [rbp+58h]
  int v51; // [rsp+C8h] [rbp+60h] BYREF

  v49 = a2;
  v3 = *((_DWORD *)this + 22);
  v44 = v3;
  v4 = (CTxtSelection *)((char *)this + 24);
  if ( *((_QWORD *)this + 6) )
    v5 = *(_DWORD *)(*(_QWORD *)v4 + 24LL);
  else
    v5 = 0;
  v6 = *((_QWORD *)this + 6);
  v7 = *((unsigned __int16 *)this + 49);
  v45 = v6;
  v50 = v5;
  v51 = 0;
  v48 = 0;
  if ( !v3 )
    CTxtSelection::UpdateForAutoWord(this);
  if ( (*(_DWORD *)(v6 + 180) & 0x10008) != 8 )
    return 1;
  v8 = (v7 >> 6) & 1;
  v43 = v8;
  if ( *((_DWORD *)this + 22) )
  {
    if ( (*((_WORD *)this + 49) & 0x180) != 0 )
    {
      if ( (*((_WORD *)CTxtSelection::GetPF(this) + 1) & 0x4000) != 0
        || (v9 = -*((_DWORD *)this + 22),
            v46 = *(_OWORD *)((char *)this + 72),
            CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v9),
            Format = CFormatRunPtr::GetFormat((CFormatRunPtr *)&v46),
            (*((_WORD *)CTxtArray::GetParaFormat((CTxtArray *)(v6 + 248), Format) + 1) & 0x4000) != 0) )
      {
        CTxtRange::Expander(this, (~(unsigned __int8)*((_WORD *)this + 49) & 0x80 | 0x40u) >> 4, 1, 0, &v51, &v48);
      }
    }
  }
  if ( (*(_WORD *)(*((_QWORD *)this + 6) + 184LL) & 0x2000) != 0
    && (*(_DWORD *)(v6 + 180) & 0x200) == 0
    && (unsigned int)CRunPtrBase::IsValid((CTxtSelection *)((char *)this + 72)) )
  {
    v13 = *v12;
    DWORD2(v46) = *((_DWORD *)v12 + 2);
    v14 = *((_DWORD *)v12 + 3);
    v47 = v11;
    *(_QWORD *)&v46 = v13;
    HIDWORD(v46) = v14;
    CTxtRange::GetRange(this, &v51, &v48);
    v15 = *((_DWORD *)this + 22);
    if ( !v15 )
    {
      v28 = v50;
      goto LABEL_44;
    }
    v16 = v51;
    v17 = v48;
    if ( !v51 && v48 >= v5 )
    {
      v28 = v50;
LABEL_43:
      v8 = v43;
LABEL_44:
      if ( !*((_DWORD *)this + 22) && (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
      {
        if ( v8 )
          ExpandedBackward = CPFRunPtr::FindExpandedBackward((CPFRunPtr *)&v46);
        else
          ExpandedBackward = 0;
        if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
          ExpandedBackward = CPFRunPtr::FindExpanded((CPFRunPtr *)&v46);
        *((_WORD *)this + 49) &= ~1u;
        CTxtRange::Advance(this, ExpandedBackward);
        CRunPtrBase::AdjustForward((CRunPtrBase *)&v46);
        if ( ExpandedBackward <= 0
          && (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46)
          && (unsigned int)CTxtPtr::IsAfterEOP(v4) )
        {
          CTxtRange::BackupCRLF(this, 1);
        }
        *((_DWORD *)this + 34) &= ~1u;
      }
      goto LABEL_59;
    }
    v18 = *((_WORD *)this + 49);
    v19 = *((_DWORD *)this + 10);
    if ( (v18 & 0x80u) != 0 )
    {
      v20 = &v51;
      v21 = &v48;
      if ( ((v18 & 0x40) != 0) != v15 < 0 )
      {
        if ( (v18 & 0x40) != 0 )
          v21 = 0;
        else
          v20 = 0;
      }
      CTxtRange::Expander(this, 4, 1, 0, v20, v21);
      v16 = v51;
      v17 = v48;
    }
    v22 = v16;
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v16 - v19);
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
      v16 += CPFRunPtr::FindExpandedBackward((CPFRunPtr *)&v46);
    CRunPtrBase::AdjustForward((CRunPtrBase *)&v46);
    IsCollapsed = CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46);
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v48 - v16);
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
    {
      v24 = 0;
      do
      {
        if ( !(unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
          break;
        CchLeft = CRunPtrBase::GetCchLeft((CRunPtrBase *)&v46);
        HIDWORD(v46) += CchLeft;
        v24 += CchLeft;
      }
      while ( (unsigned int)CRunPtrBase::NextRun((CRunPtrBase *)&v46) );
      v48 += v24;
    }
    if ( IsCollapsed )
    {
      v28 = v50;
    }
    else
    {
      v26 = CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46);
      v27 = v48;
      v28 = v50;
      if ( !v26 || v48 >= v50 )
        goto LABEL_39;
    }
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
    {
      CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v16 - v48);
      CRunPtrBase::AdjustForward((CRunPtrBase *)&v46);
      v27 = v16;
      v48 = v16;
    }
    else
    {
      v27 = v48;
      v16 = v48;
    }
LABEL_39:
    if ( v16 != v22 || v27 != v17 )
      CTxtRange::Set(this, v27, v27 - v16);
    v4 = (CTxtSelection *)((char *)this + 24);
    goto LABEL_43;
  }
  v28 = v50;
LABEL_59:
  v30 = *((_DWORD *)this + 10);
  v31 = v30;
  v32 = *((_DWORD *)this + 22);
  v33 = *(_OWORD *)((char *)this + 56);
  v47 = *((_QWORD *)this + 6);
  v34 = v30 - v32;
  v46 = v33;
  if ( v32 < 0 )
  {
    v31 = v30 - v32;
    v34 = v30;
  }
  v48 = v31;
  if ( v32 && (v34 || v31 < v28) )
  {
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v34 - v30);
    v35 = CCFRunPtr::IsInHidden((CCFRunPtr *)&v46);
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v48 - v34);
    if ( v35 || (unsigned int)CCFRunPtr::IsInHidden((CCFRunPtr *)&v46) && v48 < v28 )
      CTxtRange::Collapser(this, 0);
  }
  if ( !*((_DWORD *)this + 22) && v30 && (unsigned int)CCFRunPtr::IsInHidden((CCFRunPtr *)&v46) )
  {
    if ( !v8
      || (UnhiddenForward = CCFRunPtr::FindUnhiddenBackward((CCFRunPtr *)&v46),
          (unsigned int)CCFRunPtr::IsMask(&v46, 256)) )
    {
      UnhiddenForward = CCFRunPtr::FindUnhiddenForward((CCFRunPtr *)&v46);
      if ( (unsigned int)CCFRunPtr::IsMask(&v46, 256) )
        UnhiddenForward = CCFRunPtr::FindUnhiddenBackward((CCFRunPtr *)&v46);
    }
    *((_WORD *)this + 49) &= ~1u;
    CTxtRange::Advance(this, UnhiddenForward);
    *((_DWORD *)this + 34) &= ~1u;
  }
  v37 = *((_DWORD *)this + 22);
  if ( (v44 ^ v37) < 0 )
  {
    CRchTxtPtr::Advance((CTxtSelection *)((char *)this + 8), -v37);
    v37 = -*((_DWORD *)this + 22);
    *((_DWORD *)this + 22) = v37;
  }
  if ( !v37 && v44 )
  {
    CTxtRange::Update_iFormat(this, -1);
    *((_DWORD *)this + 34) &= ~1u;
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 13) + 264LL))(
          *((_QWORD *)this + 13),
          *((unsigned int *)this + 10),
          0xFFFFFFFFLL) )
    CTxtRange::Set(this, 0, 0);
  v38 = *(_DWORD *)(v45 + 180) >> 7;
  v39 = v38 & 1;
  if ( ((*((_DWORD *)this + 34) >> 3) & 1) != v39 )
  {
    v40 = *((_QWORD *)this + 6);
    v41 = *((_DWORD *)this + 34) ^ ((unsigned __int8)*((_DWORD *)this + 34) ^ (unsigned __int8)(8 * v38)) & 8;
    *((_DWORD *)this + 34) = v41;
    if ( (*(_DWORD *)(v40 + 180) & 0x8000080) != 0 )
    {
      if ( v39 )
      {
        if ( (v41 & 0x100) == 0 )
          CTxtSelection::CreateCaret(this);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 6) + 48LL) + 96LL))(
        *(_QWORD *)(*((_QWORD *)this + 6) + 48LL),
        v39);
    }
  }
  CTxtSelection::UpdateCaret(this, v49, 0);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v45 + 48) + 96LL))(*(_QWORD *)(v45 + 48), 0);
  CTxtSelection::UpdateSelection(this);
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v45 + 48) + 96LL))(*(_QWORD *)(v45 + 48), 1);
  return 1;
}

```

## disassembly

```asm
0x180035230  mov     [rsp-40h+arg_8], edx
0x180035234  push    rbp
0x180035235  push    rbx
0x180035236  push    rsi
0x180035237  push    rdi
0x180035238  push    r12
0x18003523a  push    r13
0x18003523c  push    r14
0x18003523e  push    r15
0x180035240  mov     rbp, rsp
0x180035243  sub     rsp, 68h
0x180035247  mov     rdi, rcx
0x18003524a  xor     r12d, r12d
0x18003524d  mov     ecx, [rcx+58h]
0x180035250  mov     [rbp+var_34], ecx
0x180035253  lea     r14, [rdi+18h]
0x180035257  cmp     [r14+18h], r12
0x18003525b  jz      short loc_180035265
0x18003525d  mov     rax, [r14]
0x180035260  mov     esi, [rax+18h]
0x180035263  jmp     short loc_180035268
0x180035265  mov     esi, r12d
0x180035268  mov     rbx, [rdi+30h]
0x18003526c  movzx   r13d, word ptr [rdi+62h]
0x180035271  mov     [rbp+var_30], rbx
0x180035275  mov     [rbp+arg_10], esi
0x180035278  mov     [rbp+arg_18], r12d
0x18003527c  mov     [rbp+arg_0], r12d
0x180035280  test    ecx, ecx
0x180035282  jnz     short loc_18003528C
0x180035284  mov     rcx, rdi; this
0x180035287  call    ?UpdateForAutoWord@CTxtSelection@@IEAAXXZ; CTxtSelection::UpdateForAutoWord(void)
0x18003528c  mov     eax, [rbx+0B4h]
0x180035292  and     eax, 10008h
0x180035297  cmp     eax, 8
0x18003529a  jnz     loc_1800357CC
0x1800352a0  shr     r13d, 6
0x1800352a4  lea     r15d, [rax-7]
0x1800352a8  and     r13d, r15d
0x1800352ab  mov     [rbp+var_38], r13d
0x1800352af  cmp     [rdi+58h], r12d
0x1800352b3  jz      loc_180035348
0x1800352b9  mov     eax, 180h
0x1800352be  test    [rdi+62h], ax
0x1800352c2  jz      loc_180035348
0x1800352c8  mov     rcx, rdi; this
0x1800352cb  call    ?GetPF@CTxtSelection@@QEAAPEBVCParaFormat@@XZ; CTxtSelection::GetPF(void)
0x1800352d0  mov     ecx, 4000h
0x1800352d5  test    [rax+2], cx
0x1800352d9  jnz     short loc_180035315
0x1800352db  mov     edx, [rdi+58h]
0x1800352de  lea     rcx, [rbp+var_28]; this
0x1800352e2  movups  xmm0, xmmword ptr [rdi+48h]
0x1800352e6  neg     edx; int
0x1800352e8  movdqu  [rbp+var_28], xmm0
0x1800352ed  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x1800352f2  lea     rcx, [rbp+var_28]; this
0x1800352f6  call    ?GetFormat@CFormatRunPtr@@QEBAFXZ; CFormatRunPtr::GetFormat(void)
0x1800352fb  movsx   edx, ax; int
0x1800352fe  lea     rcx, [rbx+0F8h]; this
0x180035305  call    ?GetParaFormat@CTxtArray@@QEAAPEBVCParaFormat@@J@Z; CTxtArray::GetParaFormat(long)
0x18003530a  mov     ecx, 4000h
0x18003530f  test    [rax+2], cx
0x180035313  jz      short loc_180035348
0x180035315  movzx   edx, word ptr [rdi+62h]
0x180035319  lea     rax, [rbp+arg_0]
0x18003531d  not     dx
0x180035320  mov     [rsp+68h+var_40], rax; int *
0x180035325  and     edx, 80h
0x18003532b  lea     rax, [rbp+arg_18]
0x18003532f  or      edx, 40h
0x180035332  mov     [rsp+68h+var_48], rax; int *
0x180035337  shr     edx, 4; int
0x18003533a  xor     r9d, r9d; int *
0x18003533d  mov     r8d, r15d; int
0x180035340  mov     rcx, rdi; this
0x180035343  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x180035348  mov     rdx, [rdi+30h]
0x18003534c  mov     eax, 2000h
0x180035351  test    [rdx+0B8h], ax
0x180035358  jz      loc_1800355B9
0x18003535e  test    dword ptr [rbx+0B4h], 200h
0x180035368  jnz     loc_1800355B9
0x18003536e  lea     rcx, [rdi+48h]; this
0x180035372  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x180035377  test    eax, eax
0x180035379  jz      loc_1800355B9
0x18003537f  mov     eax, [rcx+8]
0x180035382  lea     r8, [rbp+arg_0]; int *
0x180035386  movsd   xmm0, qword ptr [rcx]
0x18003538a  mov     dword ptr [rbp+var_28+8], eax
0x18003538d  mov     eax, [rcx+0Ch]
0x180035390  mov     rcx, rdi; this
0x180035393  mov     [rbp+var_18], rdx
0x180035397  lea     rdx, [rbp+arg_18]; int *
0x18003539b  movsd   qword ptr [rbp+var_28], xmm0
0x1800353a0  mov     dword ptr [rbp+var_28+0Ch], eax
0x1800353a3  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x1800353a8  mov     edx, [rdi+58h]
0x1800353ab  test    edx, edx
0x1800353ad  jz      loc_18003554C
0x1800353b3  mov     ebx, [rbp+arg_18]
0x1800353b6  mov     r13d, [rbp+arg_0]
0x1800353ba  test    ebx, ebx
0x1800353bc  jnz     short loc_1800353C7
0x1800353be  cmp     r13d, esi
0x1800353c1  jge     loc_180035546
0x1800353c7  movzx   ecx, word ptr [rdi+62h]
0x1800353cb  mov     esi, [rdi+28h]
0x1800353ce  test    cl, cl
0x1800353d0  jns     short loc_180035419
0x1800353d2  mov     eax, ecx
0x1800353d4  shr     edx, 1Fh
0x1800353d7  shr     eax, 6
0x1800353da  lea     r8, [rbp+arg_18]
0x1800353de  and     eax, r15d
0x1800353e1  lea     r9, [rbp+arg_0]
0x1800353e5  cmp     al, dl
0x1800353e7  jz      short loc_1800353F6
0x1800353e9  test    cl, 40h
0x1800353ec  jz      short loc_1800353F3
0x1800353ee  mov     r9, r12
0x1800353f1  jmp     short loc_1800353F6
0x1800353f3  mov     r8, r12
0x1800353f6  mov     [rsp+68h+var_40], r9; int *
0x1800353fb  mov     rcx, rdi; this
0x1800353fe  xor     r9d, r9d; int *
0x180035401  mov     [rsp+68h+var_48], r8; int *
0x180035406  mov     r8d, r15d; int
0x180035409  lea     edx, [r9+4]; int
0x18003540d  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x180035412  mov     ebx, [rbp+arg_18]
0x180035415  mov     r13d, [rbp+arg_0]
0x180035419  mov     edx, ebx
0x18003541b  lea     rcx, [rbp+var_28]; this
0x18003541f  sub     edx, esi; int
0x180035421  mov     r14d, ebx
0x180035424  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x180035429  lea     rcx, [rbp+var_28]; this
0x18003542d  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x180035432  test    eax, eax
0x180035434  jz      short loc_180035445
0x180035436  lea     rcx, [rbp+var_28]; this
0x18003543a  call    ?FindExpandedBackward@CPFRunPtr@@QEAAJXZ; CPFRunPtr::FindExpandedBackward(void)
0x18003543f  add     ebx, eax
0x180035441  mov     esi, ebx
0x180035443  jmp     short loc_180035448
0x180035445  mov     esi, r14d
0x180035448  lea     rcx, [rbp+var_28]; this
0x18003544c  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x180035451  lea     rcx, [rbp+var_28]; this
0x180035455  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18003545a  mov     edx, [rbp+arg_0]
0x18003545d  lea     rcx, [rbp+var_28]; this
0x180035461  sub     edx, esi; int
0x180035463  mov     r12d, eax
0x180035466  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18003546b  lea     rcx, [rbp+var_28]; this
0x18003546f  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x180035474  test    eax, eax
0x180035476  jz      short loc_1800354A5
0x180035478  xor     esi, esi
0x18003547a  lea     rcx, [rbp+var_28]; this
0x18003547e  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x180035483  test    eax, eax
0x180035485  jz      short loc_1800354A2
0x180035487  lea     rcx, [rbp+var_28]; this
0x18003548b  call    ?GetCchLeft@CRunPtrBase@@QEBAJXZ; CRunPtrBase::GetCchLeft(void)
0x180035490  add     dword ptr [rbp+var_28+0Ch], eax
0x180035493  lea     rcx, [rbp+var_28]; this
0x180035497  add     esi, eax
0x180035499  call    ?NextRun@CRunPtrBase@@QEAAHXZ; CRunPtrBase::NextRun(void)
0x18003549e  test    eax, eax
0x1800354a0  jnz     short loc_18003547A
0x1800354a2  add     [rbp+arg_0], esi
0x1800354a5  test    r12d, r12d
0x1800354a8  jnz     short loc_1800354C5
0x1800354aa  lea     rcx, [rbp+var_28]; this
0x1800354ae  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x1800354b3  mov     edx, [rbp+arg_0]
0x1800354b6  mov     r12d, [rbp+arg_10]
0x1800354ba  test    eax, eax
0x1800354bc  jz      short loc_1800354F9
0x1800354be  cmp     edx, r12d
0x1800354c1  jl      short loc_1800354C9
0x1800354c3  jmp     short loc_1800354F9
0x1800354c5  mov     r12d, [rbp+arg_10]
0x1800354c9  lea     rcx, [rbp+var_28]; this
0x1800354cd  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x1800354d2  test    eax, eax
0x1800354d4  jz      short loc_1800354F4
0x1800354d6  mov     edx, ebx
0x1800354d8  lea     rcx, [rbp+var_28]; this
0x1800354dc  sub     edx, [rbp+arg_0]; int
0x1800354df  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x1800354e4  lea     rcx, [rbp+var_28]; this
0x1800354e8  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x1800354ed  mov     edx, ebx
0x1800354ef  mov     [rbp+arg_0], ebx
0x1800354f2  jmp     short loc_1800354F9
0x1800354f4  mov     edx, [rbp+arg_0]; int
0x1800354f7  mov     ebx, edx
0x1800354f9  cmp     ebx, r14d
0x1800354fc  jnz     short loc_180035503
0x1800354fe  cmp     edx, r13d
0x180035501  jz      short loc_180035511
0x180035503  mov     r8d, edx
0x180035506  mov     rcx, rdi; this
0x180035509  sub     r8d, ebx; int
0x18003550c  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180035511  lea     r14, [rdi+18h]
0x180035515  mov     r13d, [rbp+var_38]
0x180035519  cmp     dword ptr [rdi+58h], 0
0x18003551d  jnz     loc_1800355BD
0x180035523  lea     rcx, [rbp+var_28]; this
0x180035527  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18003552c  test    eax, eax
0x18003552e  jz      loc_1800355BD
0x180035534  test    r13d, r13d
0x180035537  jz      short loc_180035552
0x180035539  lea     rcx, [rbp+var_28]; this
0x18003553d  call    ?FindExpandedBackward@CPFRunPtr@@QEAAJXZ; CPFRunPtr::FindExpandedBackward(void)
0x180035542  mov     ebx, eax
0x180035544  jmp     short loc_180035554
0x180035546  mov     r12d, [rbp+arg_10]
0x18003554a  jmp     short loc_180035515
0x18003554c  mov     r12d, [rbp+arg_10]
0x180035550  jmp     short loc_180035519
0x180035552  xor     ebx, ebx
0x180035554  lea     rcx, [rbp+var_28]; this
0x180035558  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18003555d  test    eax, eax
0x18003555f  jz      short loc_18003556C
0x180035561  lea     rcx, [rbp+var_28]; this
0x180035565  call    ?FindExpanded@CPFRunPtr@@QEAAJXZ; CPFRunPtr::FindExpanded(void)
0x18003556a  mov     ebx, eax
0x18003556c  mov     eax, 0FFFEh
0x180035571  mov     edx, ebx; int
0x180035573  and     [rdi+62h], ax
0x180035577  mov     rcx, rdi; this
0x18003557a  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18003557f  lea     rcx, [rbp+var_28]; this
0x180035583  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x180035588  test    ebx, ebx
0x18003558a  jg      short loc_1800355B0
0x18003558c  lea     rcx, [rbp+var_28]; this
0x180035590  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x180035595  test    eax, eax
0x180035597  jz      short loc_1800355B0
0x180035599  mov     rcx, r14; this
0x18003559c  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x1800355a1  test    eax, eax
0x1800355a3  jz      short loc_1800355B0
0x1800355a5  mov     edx, r15d; int
0x1800355a8  mov     rcx, rdi; this
0x1800355ab  call    ?BackupCRLF@CTxtRange@@QEAAJH@Z; CTxtRange::BackupCRLF(int)
0x1800355b0  and     dword ptr [rdi+88h], 0FFFFFFFEh
0x1800355b7  jmp     short loc_1800355BD
0x1800355b9  mov     r12d, [rbp+arg_10]
0x1800355bd  mov     r14d, [rdi+28h]
0x1800355c1  mov     edx, r14d
0x1800355c4  mov     rax, [rdi+30h]
0x1800355c8  mov     ecx, [rdi+58h]
0x1800355cb  movups  xmm0, xmmword ptr [rdi+38h]
0x1800355cf  mov     [rbp+var_18], rax
0x1800355d3  mov     eax, r14d
0x1800355d6  sub     eax, ecx
0x1800355d8  test    ecx, ecx
0x1800355da  mov     esi, eax
0x1800355dc  movdqu  [rbp+var_28], xmm0
0x1800355e1  cmovs   edx, eax
0x1800355e4  cmovs   esi, r14d
0x1800355e8  mov     [rbp+arg_0], edx
0x1800355eb  jz      short loc_18003563E
0x1800355ed  test    esi, esi
0x1800355ef  jnz     short loc_1800355F6
0x1800355f1  cmp     edx, r12d
0x1800355f4  jge     short loc_18003563E
0x1800355f6  mov     edx, esi
0x1800355f8  lea     rcx, [rbp+var_28]; this
0x1800355fc  sub     edx, r14d; int
0x1800355ff  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x180035604  lea     rcx, [rbp+var_28]; this
0x180035608  call    ?IsInHidden@CCFRunPtr@@QEAAHXZ; CCFRunPtr::IsInHidden(void)
0x18003560d  mov     edx, [rbp+arg_0]
0x180035610  lea     rcx, [rbp+var_28]; this
0x180035614  sub     edx, esi; int
0x180035616  mov     ebx, eax
0x180035618  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18003561d  test    ebx, ebx
0x18003561f  jnz     short loc_180035634
0x180035621  lea     rcx, [rbp+var_28]; this
0x180035625  call    ?IsInHidden@CCFRunPtr@@QEAAHXZ; CCFRunPtr::IsInHidden(void)
0x18003562a  test    eax, eax
0x18003562c  jz      short loc_18003563E
0x18003562e  cmp     [rbp+arg_0], r12d
0x180035632  jge     short loc_18003563E
0x180035634  xor     edx, edx; int
0x180035636  mov     rcx, rdi; this
0x180035639  call    ?Collapser@CTxtRange@@QEAAXJ@Z; CTxtRange::Collapser(long)
  ... truncated ...
```

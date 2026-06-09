# CRTFRead::ReadRtf(void)

- ea: `0x1800020c4`
- end: `0x180002733`
- name: `?ReadRtf@CRTFRead@@QEAAJXZ`
- size: `1647`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, installer_update`

## callers

- `0x1800238dc`

## callees

- `0x1800014f0`
- `0x180001544`
- `0x180001618`
- `0x1800016b0`
- `0x180001cd0`
- `0x1800020c4`
- `0x180002740`
- `0x180015448`
- `0x180016700`
- `0x180016d90`
- `0x180017cdc`
- `0x180019e4c`
- `0x18001c13c`
- `0x180022ad4`
- `0x1800230e0`
- `0x18002720c`
- `0x1800274a0`
- `0x18002c58c`
- `0x18002d8e4`
- `0x18002f428`
- `0x1800301a0`
- `0x18003c554`
- `0x18003ebc4`
- `0x180046484`
- `0x1800466f0`
- `0x180046fd8`
- `0x180047400`
- `0x180049e74`
- `0x18004a10c`
- `0x18004b234`
- `0x18004c6f0`
- `0x18004e39c`
- `0x180073f6c`
- `0x180076940`
- `0x180078a64`
- `0x1800866e4`
- `0x180086710`
- `0x180086794`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CRTFRead::ReadRtf(CRTFRead *this)
{
  __int64 v1; // r15
  CTxtEdit **v3; // rdi
  void *v4; // rax
  unsigned int v5; // eax
  int v6; // eax
  const struct CParaFormat *PF; // rax
  __int64 v8; // xmm1_8
  _OWORD *v9; // r14
  __int128 v10; // xmm1
  int v11; // r12d
  unsigned __int8 *v12; // rax
  unsigned __int8 v13; // dl
  __int64 v14; // rcx
  unsigned __int16 Keyword; // ax
  __int16 v16; // cx
  __int128 v17; // xmm1
  int EOP; // eax
  struct CDocInfo *DocInfo; // rsi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // edx
  int v23; // edi
  __int128 v24; // xmm1
  int v25; // esi
  __int64 v26; // rdi
  __int64 v27; // rdi
  int v28; // r8d
  void **v29; // rsi
  int *v30; // r14
  CTxtEdit **v31; // rdi
  CTxtEdit *v32; // rax
  int v33; // ecx
  int v34; // esi
  _DWORD *v35; // rdx
  _DWORD *v36; // rcx
  __int64 v37; // rdx
  _BYTE v39[36]; // [rsp+30h] [rbp-38h] BYREF

  v1 = *((_QWORD *)this + 8);
  *((_DWORD *)this + 172) = *(_DWORD *)(v1 + 40);
  if ( !(unsigned int)CRTFRead::InitLex(this) )
    goto LABEL_78;
  v3 = (CTxtEdit **)((char *)this + 56);
  if ( (*((_DWORD *)this + 20) & 0x8000) == 0 )
    CTxtEdit::InitDocInfo(*v3);
  *(_WORD *)(v1 + 98) |= 8u;
  v4 = CW32System::PvAlloc(0x402u, 0x40u);
  *((_QWORD *)this + 84) = v4;
  if ( v4 )
  {
    v5 = *((_DWORD *)this + 20);
    *((_DWORD *)this + 170) = 513;
    if ( (v5 & 0x20) != 0 )
      v6 = HIWORD(v5);
    else
      v6 = -1;
    *((_DWORD *)this + 147) = v6;
    PF = CRchTxtPtr::GetPF((CRchTxtPtr *)(v1 + 8));
    *(_OWORD *)((char *)this + 244) = *(_OWORD *)PF;
    *(_OWORD *)((char *)this + 260) = *((_OWORD *)PF + 1);
    *(_OWORD *)((char *)this + 276) = *((_OWORD *)PF + 2);
    v8 = *((_QWORD *)PF + 6);
    *((_WORD *)this + 236) &= ~0x400u;
    *(_QWORD *)((char *)this + 292) = v8;
    LOWORD(PF) = (*((_WORD *)this + 123) >> 4) & 0x400;
    *((_DWORD *)this + 75) = -671089153;
    *((_WORD *)this + 236) |= (unsigned __int16)PF;
    *((_WORD *)this + 131) = -1;
    CRTFRead::GetChar(this);
    CRTFRead::UngetChar(this);
    if ( !(unsigned int)IsRTF(*((char **)this + 23)) )
    {
      if ( (*((_DWORD *)*v3 + 45) & 0x80000) == 0 )
      {
        *((_DWORD *)this + 12) = 16;
        goto LABEL_67;
      }
      *((_WORD *)this + 236) |= 0x200u;
    }
    v9 = (_OWORD *)(v1 + 24);
    *((_DWORD *)this + 58) = *((_DWORD *)this + 172);
    if ( !(unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)(v1 + 24)) )
    {
      v10 = *(_OWORD *)(v1 + 40);
      *(_OWORD *)v39 = *v9;
      *(_OWORD *)&v39[16] = v10;
      CTxtPtr::FindEOP((CTxtPtr *)v39, -1073741823, 0);
      *((_DWORD *)this + 58) = *(_DWORD *)&v39[16];
    }
    v11 = *((_DWORD *)this + 58);
    do
    {
      *((_WORD *)this + 67) = *((_WORD *)this + 66);
      *((_WORD *)this + 66) = 260;
      while ( *((_QWORD *)this + 23) != *((_QWORD *)this + 24) || (unsigned int)CRTFRead::FillBuffer(this) )
      {
        v12 = (unsigned __int8 *)*((_QWORD *)this + 23);
        v13 = *v12;
        *((_QWORD *)this + 23) = v12 + 1;
        if ( !v13 )
          goto LABEL_27;
        if ( v13 != 10 && v13 != 13 )
        {
          if ( v13 != 92 )
          {
            if ( v13 == 123 )
            {
              *((_WORD *)this + 66) = 261;
              goto LABEL_38;
            }
            if ( v13 == 125 )
            {
              *((_WORD *)this + 66) = 262;
              goto LABEL_38;
            }
            goto LABEL_29;
          }
          Keyword = CRTFRead::TokenGetKeyword(this);
LABEL_34:
          *((_WORD *)this + 66) = Keyword;
          goto LABEL_38;
        }
      }
      *((_DWORD *)this + 12) = 15;
LABEL_27:
      if ( *((_DWORD *)this + 12) == 15 )
        continue;
      v13 = 32;
LABEL_29:
      v14 = *((_QWORD *)this + 27);
      if ( v14 )
      {
        v16 = *(_WORD *)(v14 + 10);
        if ( (unsigned __int16)(v16 - 7) > 1u )
        {
          Keyword = CRTFRead::TokenGetText(this, v13);
          goto LABEL_34;
        }
        *((_WORD *)this + 66) = v16 + 256;
        CRTFRead::UngetChar(this);
      }
      else if ( (*((_DWORD *)*v3 + 45) & 0x80000) != 0 )
      {
        *((_DWORD *)this + 12) = 16;
      }
LABEL_38:
      ;
    }
    while ( (unsigned __int16)(*((_WORD *)this + 66) - 259) > 1u
         && !(unsigned int)CRTFRead::HandleToken(this)
         && *((_QWORD *)this + 27) );
    if ( *((_DWORD *)this + 79) && *((_DWORD *)this + 12) == 18 )
    {
      v17 = *(_OWORD *)(v1 + 40);
      *(_OWORD *)v39 = *v9;
      *(_OWORD *)&v39[16] = v17;
      EOP = CTxtPtr::FindEOP((CTxtPtr *)v39, -1073741823, 0);
      CTxtRange::Set((CTxtRange *)v1, *(_DWORD *)(v1 + 40), -EOP);
      CTxtRange::Delete(v1, 0, 0);
    }
    *((_QWORD *)this + 39) = 0;
    *(_WORD *)(v1 + 98) &= ~8u;
    CTxtRange::Update_iFormat((CTxtRange *)v1, -1);
    if ( (*((_DWORD *)this + 20) & 0x8000) == 0 )
    {
      if ( *(_DWORD *)(v1 + 40) == (unsigned int)CTxtEdit::GetAdjustedTextLength(*v3) )
      {
        *((_DWORD *)this + 75) &= 0xFFFFE7FF;
        CRTFRead::Apply_PF(this);
        CRchTxtPtr::ExtendFormattingCRLF((CRchTxtPtr *)(v1 + 8));
      }
      DocInfo = CTxtEdit::GetDocInfo(*v3);
      if ( !DocInfo )
      {
        *((_DWORD *)this + 12) = 9;
        goto LABEL_67;
      }
      if ( !*((_DWORD *)this + 12) )
        CTxtRange::DeleteTerminatingEOP((CTxtRange *)v1, 0);
      v20 = *((_DWORD *)this + 147);
      if ( v20 == -1 )
        LOWORD(v20) = -1;
      *((_WORD *)DocInfo + 9) = v20;
      if ( (_WORD)v20 == 0xFDE9 )
        *((_WORD *)DocInfo + 9) = 1252;
      v21 = 65534;
      v22 = 65534;
      if ( *((_WORD *)this + 240) != 0xFFFF )
        v22 = *((unsigned __int16 *)this + 240);
      CTxtEdit::SetDefaultLCID(*v3, v22);
      if ( *((_WORD *)this + 241) != 0xFFFF )
        v21 = *((unsigned __int16 *)this + 241);
      CTxtEdit::SetDefaultLCIDFE(*v3, v21);
      (*(void (__fastcall **)(__int64))(*((_QWORD *)*v3 + 2) + 112LL))((__int64)*v3 + 16);
      CTxtEdit::SetDocumentType(*v3, *((unsigned __int8 *)this + 474));
    }
    if ( (*((_DWORD *)*v3 + 48) & 0x61086013) != 0 )
    {
      v23 = *(_DWORD *)(v1 + 40);
      if ( v23 > v11 )
      {
        if ( (unsigned int)CTxtPtr::IsAtEOP((CTxtPtr *)(v1 + 24)) )
        {
          v25 = v23;
        }
        else
        {
          v24 = *(_OWORD *)(v1 + 40);
          *(_OWORD *)v39 = *(_OWORD *)(v1 + 24);
          *(_OWORD *)&v39[16] = v24;
          CTxtPtr::FindEOP((CTxtPtr *)v39, 0x3FFFFFFF, 0);
          v25 = *(_DWORD *)&v39[16];
          CTxtRange::Advance((CTxtRange *)v1, *(_DWORD *)&v39[16] - v23);
        }
        CRchTxtPtr::ItemizeReplaceRange((CRchTxtPtr *)(v1 + 8), v25 - v11, 0, 0, 0);
        if ( v25 != v23 )
          CTxtRange::SetCp((CTxtRange *)v1, v23);
      }
    }
    goto LABEL_67;
  }
  CCallMgr::SetOutOfMemory(*((CCallMgr **)*v3 + 18));
  *((_DWORD *)this + 12) = 9;
LABEL_67:
  CRTFRead::FreeRtfObject(this);
  v26 = *((_QWORD *)this + 27);
  if ( v26 )
  {
    if ( !*((_DWORD *)this + 12) )
      *((_DWORD *)this + 12) = 12;
    while ( *(_QWORD *)(v26 + 40) )
    {
      v26 = *(_QWORD *)(v26 + 40);
      ReleaseFormats(*(__int16 *)(v26 + 2), -1);
    }
  }
  v27 = *((_QWORD *)this + 28);
  if ( v27 )
  {
    while ( *(_QWORD *)(v27 + 40) )
    {
      STATE::DeletePF((STATE *)v27);
      v27 = *(_QWORD *)(v27 + 40);
      CW32System::FreePv(*(void **)(v27 + 32));
    }
    STATE::DeletePF((STATE *)v27);
  }
  CW32System::FreePv((void *)v27);
  CW32System::FreePv(*((void **)this + 84));
  CW32System::FreePv(*((void **)this + 75));
  CW32System::FreePv(*((void **)this + 77));
LABEL_78:
  CRTFRead::DeinitLex(this);
  v29 = (void **)((char *)this + 696);
  v30 = (int *)*((_QWORD *)this + 87);
  v31 = (CTxtEdit **)((char *)this + 56);
  if ( v30 )
  {
    v32 = *v31;
    if ( (*((_DWORD *)*v31 + 44) & 0x2000000) != 0 )
    {
      v33 = *((_DWORD *)this + 177);
      if ( v33 > 0 )
      {
        memset(v39, 0, 24);
        *(_DWORD *)&v39[24] = v33;
        *(_QWORD *)&v39[28] = v30;
        if ( (*((_DWORD *)v32 + 45) & 0x80000) != 0 )
        {
          v34 = 0;
          do
          {
            *v30 = CTxtEdit::GetAcpFromCp(*v31, *v30, v28);
            ++v34;
            ++v30;
          }
          while ( v34 < *((_DWORD *)this + 177) );
          v31 = (CTxtEdit **)((char *)this + 56);
          v29 = (void **)((char *)this + 696);
        }
        CTxtEdit::TxNotify(*v31, 0x70Au, v39);
      }
    }
    CW32System::FreePv(*v29);
    *v29 = 0;
  }
  v35 = (_DWORD *)((char *)this + 48);
  if ( *((_DWORD *)this + 12) )
  {
    if ( *v35 == 18 )
    {
      CCallMgr::SetMaxText(*((CCallMgr **)*v31 + 18));
      v36 = (_DWORD *)((char *)this + 48);
      *(_DWORD *)(*((_QWORD *)this + 9) + 8LL) = -2147286928;
    }
    else
    {
      v36 = (_DWORD *)((char *)this + 48);
    }
    if ( *v35 == 15 )
      *(_DWORD *)(*((_QWORD *)this + 9) + 8LL) = -2147024858;
    else
      v36 = v35;
    v37 = *((_QWORD *)this + 9);
    if ( !*(_DWORD *)(v37 + 8) && *v36 != 21 )
      *(_DWORD *)(v37 + 8) = -*v36;
  }
  return (unsigned int)(*(_DWORD *)(v1 + 40) - *((_DWORD *)this + 172));
}

```

## disassembly

```asm
0x1800020c4  push    rbp
0x1800020c6  push    rbx
0x1800020c7  push    rsi
0x1800020c8  push    rdi
0x1800020c9  push    r12
0x1800020cb  push    r13
0x1800020cd  push    r14
0x1800020cf  push    r15
0x1800020d1  mov     rbp, rsp
0x1800020d4  sub     rsp, 68h
0x1800020d8  mov     r15, [rcx+40h]
0x1800020dc  mov     rbx, rcx
0x1800020df  mov     eax, [r15+28h]
0x1800020e3  mov     [rcx+2B0h], eax
0x1800020e9  call    ?InitLex@CRTFRead@@AEAAHXZ; CRTFRead::InitLex(void)
0x1800020ee  mov     r12d, 1
0x1800020f4  test    eax, eax
0x1800020f6  jz      loc_18000261E
0x1800020fc  test    dword ptr [rbx+50h], 8000h
0x180002103  lea     rdi, [rbx+38h]
0x180002107  jnz     short loc_180002111
0x180002109  mov     rcx, [rdi]; this
0x18000210c  call    ?InitDocInfo@CTxtEdit@@QEAAJXZ; CTxtEdit::InitDocInfo(void)
0x180002111  or      word ptr [r15+62h], 8
0x180002117  mov     edx, 40h ; '@'; unsigned int
0x18000211c  mov     ecx, 402h; unsigned int
0x180002121  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x180002126  or      esi, 0FFFFFFFFh
0x180002129  mov     [rbx+2A0h], rax
0x180002130  test    rax, rax
0x180002133  jnz     short loc_180002150
0x180002135  mov     rcx, [rdi]
0x180002138  mov     rcx, [rcx+90h]; this
0x18000213f  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x180002144  mov     dword ptr [rbx+30h], 9
0x18000214b  jmp     loc_180002586
0x180002150  mov     eax, [rbx+50h]
0x180002153  mov     dword ptr [rbx+2A8h], 201h
0x18000215d  test    al, 20h
0x18000215f  jz      short loc_180002166
0x180002161  shr     eax, 10h
0x180002164  jmp     short loc_180002169
0x180002166  or      eax, 0FFFFFFFFh
0x180002169  lea     rcx, [r15+8]; this
0x18000216d  mov     [rbx+24Ch], eax
0x180002173  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x180002178  mov     ecx, 400h
0x18000217d  movups  xmm0, xmmword ptr [rax]
0x180002180  movups  xmmword ptr [rbx+0F4h], xmm0
0x180002187  movups  xmm1, xmmword ptr [rax+10h]
0x18000218b  movups  xmmword ptr [rbx+104h], xmm1
0x180002192  movups  xmm0, xmmword ptr [rax+20h]
0x180002196  movups  xmmword ptr [rbx+114h], xmm0
0x18000219d  movsd   xmm1, qword ptr [rax+30h]
0x1800021a2  mov     eax, 0FBFFh
0x1800021a7  and     [rbx+1D8h], ax
0x1800021ae  movsd   qword ptr [rbx+124h], xmm1
0x1800021b6  movzx   eax, word ptr [rbx+0F6h]
0x1800021bd  shr     ax, 4
0x1800021c1  and     ax, cx
0x1800021c4  mov     dword ptr [rbx+12Ch], 0D7FFFDFFh
0x1800021ce  or      [rbx+1D8h], ax
0x1800021d5  mov     rcx, rbx; this
0x1800021d8  mov     [rbx+106h], si
0x1800021df  call    ?GetChar@CRTFRead@@AEAAEXZ; CRTFRead::GetChar(void)
0x1800021e4  mov     rcx, rbx; this
0x1800021e7  call    ?UngetChar@CRTFRead@@AEAAHXZ; CRTFRead::UngetChar(void)
0x1800021ec  mov     rcx, [rbx+0B8h]; char *
0x1800021f3  call    ?IsRTF@@YAHPEAD@Z; IsRTF(char *)
0x1800021f8  test    eax, eax
0x1800021fa  jnz     short loc_18000221B
0x1800021fc  mov     rax, [rdi]
0x1800021ff  test    dword ptr [rax+0B4h], 80000h
0x180002209  jz      loc_1800022E0
0x18000220f  mov     eax, 200h
0x180002214  or      [rbx+1D8h], ax
0x18000221b  mov     eax, [rbx+2B0h]
0x180002221  lea     r14, [r15+18h]
0x180002225  mov     rcx, r14; this
0x180002228  mov     [rbx+0E8h], eax
0x18000222e  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x180002233  test    eax, eax
0x180002235  jnz     short loc_180002262
0x180002237  movups  xmm0, xmmword ptr [r14]
0x18000223b  xor     r8d, r8d; int *
0x18000223e  mov     edx, 0C0000001h; int
0x180002243  movups  xmm1, xmmword ptr [r14+10h]
0x180002248  lea     rcx, [rbp+var_38]; this
0x18000224c  movups  [rbp+var_38], xmm0
0x180002250  movups  [rbp+var_28], xmm1
0x180002254  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x180002259  mov     eax, dword ptr [rbp+var_28]
0x18000225c  mov     [rbx+0E8h], eax
0x180002262  mov     r12d, [rbx+0E8h]
0x180002269  mov     r13d, 1
0x18000226f  movzx   eax, word ptr [rbx+84h]
0x180002276  mov     [rbx+86h], ax
0x18000227d  mov     word ptr [rbx+84h], 104h
0x180002286  mov     rax, [rbx+0C0h]
0x18000228d  cmp     [rbx+0B8h], rax
0x180002294  jnz     short loc_1800022A2
0x180002296  mov     rcx, rbx; this
0x180002299  call    ?FillBuffer@CRTFRead@@AEAAJXZ; CRTFRead::FillBuffer(void)
0x18000229e  test    eax, eax
0x1800022a0  jz      short loc_1800022EC
0x1800022a2  mov     rax, [rbx+0B8h]
0x1800022a9  mov     dl, [rax]
0x1800022ab  inc     rax
0x1800022ae  mov     [rbx+0B8h], rax
0x1800022b5  test    dl, dl
0x1800022b7  jz      short loc_1800022F3
0x1800022b9  cmp     dl, 0Ah
0x1800022bc  jz      short loc_180002286
0x1800022be  cmp     dl, 0Dh
0x1800022c1  jz      short loc_180002286
0x1800022c3  cmp     dl, 5Ch ; '\'
0x1800022c6  jz      short loc_18000232A
0x1800022c8  cmp     dl, 7Bh ; '{'
0x1800022cb  jz      short loc_18000231F
0x1800022cd  cmp     dl, 7Dh ; '}'
0x1800022d0  jnz     short loc_1800022FB
0x1800022d2  mov     word ptr [rbx+84h], 106h
0x1800022db  jmp     loc_180002369
0x1800022e0  mov     dword ptr [rbx+30h], 10h
0x1800022e7  jmp     loc_180002586
0x1800022ec  mov     dword ptr [rbx+30h], 0Fh
0x1800022f3  cmp     dword ptr [rbx+30h], 0Fh
0x1800022f7  jz      short loc_180002369
0x1800022f9  mov     dl, 20h ; ' '; unsigned __int8
0x1800022fb  mov     rcx, [rbx+0D8h]
0x180002302  test    rcx, rcx
0x180002305  jnz     short loc_18000233B
0x180002307  mov     rax, [rdi]
0x18000230a  test    dword ptr [rax+0B4h], 80000h
0x180002314  jz      short loc_180002369
0x180002316  mov     dword ptr [rbx+30h], 10h
0x18000231d  jmp     short loc_180002369
0x18000231f  mov     word ptr [rbx+84h], 105h
0x180002328  jmp     short loc_180002369
0x18000232a  mov     rcx, rbx; this
0x18000232d  call    ?TokenGetKeyword@CRTFRead@@AEAAGXZ; CRTFRead::TokenGetKeyword(void)
0x180002332  mov     [rbx+84h], ax
0x180002339  jmp     short loc_180002369
0x18000233b  movzx   ecx, word ptr [rcx+0Ah]
0x18000233f  lea     eax, [rcx-7]
0x180002342  cmp     ax, r13w
0x180002346  jbe     short loc_180002352
0x180002348  mov     rcx, rbx; this
0x18000234b  call    ?TokenGetText@CRTFRead@@AEAAGE@Z; CRTFRead::TokenGetText(uchar)
0x180002350  jmp     short loc_180002332
0x180002352  mov     eax, 100h
0x180002357  add     cx, ax
0x18000235a  mov     [rbx+84h], cx
0x180002361  mov     rcx, rbx; this
0x180002364  call    ?UngetChar@CRTFRead@@AEAAHXZ; CRTFRead::UngetChar(void)
0x180002369  movzx   eax, word ptr [rbx+84h]
0x180002370  mov     ecx, 103h
0x180002375  sub     ax, cx
0x180002378  cmp     ax, r13w
0x18000237c  jbe     short loc_180002398
0x18000237e  mov     rcx, rbx; this
0x180002381  call    ?HandleToken@CRTFRead@@AEAAHXZ; CRTFRead::HandleToken(void)
0x180002386  test    eax, eax
0x180002388  jnz     short loc_180002398
0x18000238a  cmp     qword ptr [rbx+0D8h], 0
0x180002392  jnz     loc_18000226F
0x180002398  cmp     dword ptr [rbx+13Ch], 0
0x18000239f  jz      short loc_1800023E7
0x1800023a1  cmp     dword ptr [rbx+30h], 12h
0x1800023a5  jnz     short loc_1800023E7
0x1800023a7  movups  xmm0, xmmword ptr [r14]
0x1800023ab  xor     r8d, r8d; int *
0x1800023ae  mov     edx, 0C0000001h; int
0x1800023b3  movups  xmm1, xmmword ptr [r14+10h]
0x1800023b8  lea     rcx, [rbp+var_38]; this
0x1800023bc  movups  [rbp+var_38], xmm0
0x1800023c0  movups  [rbp+var_28], xmm1
0x1800023c4  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x1800023c9  mov     edx, [r15+28h]; int
0x1800023cd  neg     eax
0x1800023cf  mov     r8d, eax; int
0x1800023d2  mov     rcx, r15; this
0x1800023d5  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x1800023da  xor     r8d, r8d
0x1800023dd  xor     edx, edx
0x1800023df  mov     rcx, r15
0x1800023e2  call    ?Delete@CTxtRange@@QEAAXPEAVIUndoBuilder@@W4SELRR@@@Z; CTxtRange::Delete(IUndoBuilder *,SELRR)
0x1800023e7  mov     eax, 0FFF7h
0x1800023ec  mov     qword ptr [rbx+138h], 0
0x1800023f7  and     [r15+62h], ax
0x1800023fc  mov     edx, esi; int
0x1800023fe  mov     rcx, r15; this
0x180002401  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x180002406  test    dword ptr [rbx+50h], 8000h
0x18000240d  jnz     loc_1800024FF
0x180002413  mov     rcx, [rdi]; this
0x180002416  call    ?GetAdjustedTextLength@CTxtEdit@@QEAAJXZ; CTxtEdit::GetAdjustedTextLength(void)
0x18000241b  cmp     [r15+28h], eax
0x18000241f  jnz     short loc_18000243C
0x180002421  and     dword ptr [rbx+12Ch], 0FFFFE7FFh
0x18000242b  mov     rcx, rbx; this
0x18000242e  call    ?Apply_PF@CRTFRead@@AEAAXXZ; CRTFRead::Apply_PF(void)
0x180002433  lea     rcx, [r15+8]; this
0x180002437  call    ?ExtendFormattingCRLF@CRchTxtPtr@@QEAAXXZ; CRchTxtPtr::ExtendFormattingCRLF(void)
0x18000243c  mov     rcx, [rdi]; this
0x18000243f  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x180002444  mov     rsi, rax
0x180002447  test    rax, rax
0x18000244a  jnz     short loc_180002458
0x18000244c  mov     dword ptr [rbx+30h], 9
0x180002453  jmp     loc_180002583
0x180002458  cmp     dword ptr [rbx+30h], 0
0x18000245c  jnz     short loc_180002468
0x18000245e  xor     edx, edx; struct IUndoBuilder *
0x180002460  mov     rcx, r15; this
0x180002463  call    ?DeleteTerminatingEOP@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::DeleteTerminatingEOP(IUndoBuilder *)
0x180002468  mov     eax, [rbx+24Ch]
0x18000246e  or      edx, 0FFFFFFFFh
0x180002471  cmp     eax, edx
0x180002473  mov     ecx, 0FFFFh
0x180002478  cmovz   eax, ecx
0x18000247b  mov     ecx, 0FDE9h
0x180002480  mov     [rsi+12h], ax
0x180002484  cmp     ax, cx
0x180002487  jnz     short loc_18000248F
0x180002489  mov     word ptr [rsi+12h], 4E4h
0x18000248f  movzx   eax, word ptr [rbx+1E0h]
0x180002496  mov     esi, 0FFFEh
0x18000249b  cmp     ax, dx
0x18000249e  mov     edx, esi
0x1800024a0  jz      short loc_1800024A4
0x1800024a2  mov     edx, eax; unsigned int
0x1800024a4  mov     rcx, [rdi]; this
0x1800024a7  call    ?SetDefaultLCID@CTxtEdit@@QEAAJK@Z; CTxtEdit::SetDefaultLCID(ulong)
0x1800024ac  movzx   eax, word ptr [rbx+1E2h]
0x1800024b3  or      ecx, 0FFFFFFFFh
0x1800024b6  cmp     ax, cx
0x1800024b9  jz      short loc_1800024BD
0x1800024bb  mov     esi, eax
0x1800024bd  mov     rcx, [rdi]; this
0x1800024c0  mov     edx, esi; unsigned int
0x1800024c2  call    ?SetDefaultLCIDFE@CTxtEdit@@QEAAJK@Z; CTxtEdit::SetDefaultLCIDFE(ulong)
0x1800024c7  movsx   eax, word ptr [rbx+1E4h]
0x1800024ce  mov     rcx, [rdi]
0x1800024d1  add     rcx, 10h
0x1800024d5  movd    xmm1, eax
0x1800024d9  cvtdq2ps xmm1, xmm1
0x1800024dc  mov     rdx, [rcx]
0x1800024df  mov     rax, [rdx+70h]
0x1800024e3  mulss   xmm1, cs:__real@3d4ccccd
0x1800024eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f0  movzx   edx, byte ptr [rbx+1DAh]; int
0x1800024f7  mov     rcx, [rdi]; this
0x1800024fa  call    ?SetDocumentType@CTxtEdit@@QEAAJJ@Z; CTxtEdit::SetDocumentType(long)
0x1800024ff  mov     rax, [rdi]
0x180002502  test    dword ptr [rax+0C0h], 61086013h
0x18000250c  jz      short loc_180002583
0x18000250e  mov     edi, [r15+28h]
0x180002512  cmp     edi, r12d
0x180002515  jle     short loc_180002583
0x180002517  mov     rcx, r14; this
0x18000251a  call    ?IsAtEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAtEOP(void)
0x18000251f  test    eax, eax
0x180002521  jnz     short loc_180002557
0x180002523  movups  xmm0, xmmword ptr [r15+18h]
0x180002528  xor     r8d, r8d; int *
0x18000252b  mov     edx, 3FFFFFFFh; int
0x180002530  movups  xmm1, xmmword ptr [r15+28h]
0x180002535  lea     rcx, [rbp+var_38]; this
0x180002539  movups  [rbp+var_38], xmm0
0x18000253d  movups  [rbp+var_28], xmm1
0x180002541  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x180002546  mov     esi, dword ptr [rbp+var_28]
0x180002549  mov     rcx, r15; this
0x18000254c  mov     edx, esi
0x18000254e  sub     edx, edi; int
0x180002550  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x180002555  jmp     short loc_180002559
0x180002557  mov     esi, edi
0x180002559  mov     edx, esi
0x18000255b  mov     [rsp+68h+var_48], 0; int
0x180002563  sub     edx, r12d; int
0x180002566  lea     rcx, [r15+8]; this
0x18000256a  xor     r9d, r9d; struct IUndoBuilder *
0x18000256d  xor     r8d, r8d; int
0x180002570  call    ?ItemizeReplaceRange@CRchTxtPtr@@QEAAHJJPEAVIUndoBuilder@@H@Z; CRchTxtPtr::ItemizeReplaceRange(long,long,IUndoBuilder *,int)
0x180002575  cmp     esi, edi
0x180002577  jz      short loc_180002583
0x180002579  mov     edx, edi; int
0x18000257b  mov     rcx, r15; this
0x18000257e  call    ?SetCp@CTxtRange@@QEAAJJ@Z; CTxtRange::SetCp(long)
0x180002583  mov     r12d, r13d
0x180002586  mov     rcx, rbx; this
0x180002589  call    ?FreeRtfObject@CRTFRead@@AEAAXXZ; CRTFRead::FreeRtfObject(void)
0x18000258e  mov     rdi, [rbx+0D8h]
0x180002595  xor     r13d, r13d
0x180002598  test    rdi, rdi
0x18000259b  jz      short loc_1800025C2
0x18000259d  cmp     [rbx+30h], r13d
0x1800025a1  jnz     short loc_1800025BC
  ... truncated ...
```

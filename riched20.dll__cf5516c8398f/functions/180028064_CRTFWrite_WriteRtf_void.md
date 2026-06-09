# CRTFWrite::WriteRtf(void)

- ea: `0x180028064`
- end: `0x1800288c3`
- name: `?WriteRtf@CRTFWrite@@QEAAJXZ`
- size: `2143`
- prototype: `__int64 __fastcall(CRTFWrite *__hidden this)`
- caller_count: `1`
- callee_count: `36`
- tags: ``

## callers

- `0x1800415e0`

## callees

- `0x1800064d0`
- `0x180008f80`
- `0x1800110b0`
- `0x1800165c0`
- `0x18001d8b0`
- `0x18001db20`
- `0x18001f750`
- `0x180020eb0`
- `0x180022780`
- `0x180023010`
- `0x180023ba8`
- `0x180024910`
- `0x180028064`
- `0x1800288d0`
- `0x180028bc4`
- `0x180028e40`
- `0x180028e88`
- `0x1800295bc`
- `0x180029a40`
- `0x180029d60`
- `0x18002a144`
- `0x18002a1e8`
- `0x18002a2d8`
- `0x18002a3cc`
- `0x1800442dc`
- `0x1800455c4`
- `0x180045f54`
- `0x180046c4c`
- `0x180047da8`
- `0x180048ba0`
- `0x18005bb98`
- `0x18005fd10`
- `0x18006fb00`
- `0x180072948`
- `0x18007e258`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CRTFWrite::WriteRtf(CCallMgr ***this)
{
  CRTFWrite *v1; // rbx
  struct CDocInfo *DocInfo; // r13
  __int64 v3; // rcx
  int v4; // edx
  int v5; // r14d
  int v6; // r15d
  int v7; // r12d
  __int64 v8; // rcx
  int v9; // esi
  int v10; // edi
  int EOP; // eax
  unsigned __int16 *v12; // rax
  unsigned int *v13; // rdi
  unsigned __int16 *v14; // r12
  char *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // r14d
  int v18; // r8d
  CTxtEdit *v19; // rdi
  int v20; // ecx
  CTxtEdit *v21; // rdi
  int v22; // ecx
  CTxtEdit *v23; // rdi
  char v24; // cl
  int v25; // r8d
  int v26; // r9d
  int i; // edi
  _WORD *v28; // rax
  unsigned int v29; // r14d
  __int16 v30; // di
  int CchLeftRunPF; // eax
  int v32; // r12d
  int CchLeftRunCF; // eax
  int v34; // edi
  const struct CCharFormat *v35; // r13
  int CodePage; // r14d
  int v37; // ecx
  int v38; // edx
  int Text; // eax
  int v40; // r13d
  unsigned __int16 *v41; // rdx
  int v42; // edi
  int v43; // r12d
  int v44; // ecx
  const unsigned __int16 *v45; // r8
  __int16 v46; // ax
  int v47; // ecx
  int v48; // r12d
  CObjectMgr *ObjectMgr; // rax
  struct COleObject *ObjectFromCp; // rax
  int v51; // eax
  __int64 v52; // rcx
  unsigned __int16 *v54; // [rsp+30h] [rbp-99h]
  __int128 v55; // [rsp+38h] [rbp-91h] BYREF
  int v56; // [rsp+48h] [rbp-81h]
  int v57; // [rsp+4Ch] [rbp-7Dh]
  __int64 v58; // [rsp+50h] [rbp-79h]
  unsigned __int16 *v59; // [rsp+58h] [rbp-71h]
  const struct CCharFormat *CF; // [rsp+60h] [rbp-69h]
  _BYTE v61[16]; // [rsp+70h] [rbp-59h] BYREF
  __int128 v62; // [rsp+80h] [rbp-49h] BYREF
  int v63; // [rsp+90h] [rbp-39h]
  int v64; // [rsp+94h] [rbp-35h]
  __int64 v65; // [rsp+98h] [rbp-31h]
  char v66[16]; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v67; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v68; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v69; // [rsp+D0h] [rbp+7h]
  int v71; // [rsp+138h] [rbp+6Fh] BYREF
  CCallMgr **v72; // [rsp+140h] [rbp+77h]
  struct COleObject *v73; // [rsp+148h] [rbp+7Fh]

  v1 = (CRTFWrite *)this;
  v72 = this[7];
  DocInfo = CTxtEdit::GetDocInfo((CTxtEdit *)v72);
  CRchTxtPtr::CRchTxtPtr((CRchTxtPtr *)v61, (const struct CRchTxtPtr *)(*((_QWORD *)v1 + 8) + 8LL));
  v3 = *((_QWORD *)v1 + 8);
  v4 = *(_DWORD *)(v3 + 88);
  v5 = *(_DWORD *)(v3 + 40);
  if ( v4 < 0 )
    v5 = *(_DWORD *)(v3 + 40) - v4;
  v6 = -v4;
  if ( v4 > 0 )
    v6 = *(_DWORD *)(v3 + 88);
  v7 = *(_DWORD *)(v3 + 40) - v4;
  if ( v4 < 0 )
    v7 = *(_DWORD *)(v3 + 40);
  CRchTxtPtr::SetCp((CRchTxtPtr *)v61, v7);
  v8 = *((_QWORD *)v1 + 8);
  v9 = 1;
  *((_BYTE *)v1 + 145) = *(_BYTE *)(v8 + 98) >> 7;
  if ( (*(_BYTE *)(v8 + 98) & 2) == 0 )
  {
    v68 = v67;
    v69 = v65;
    v56 = v63;
    v58 = v65;
    v55 = v62;
    v57 = v64;
    v71 = 0;
    *((_BYTE *)v1 + 145) = CTxtPtr::IsAtEOP((CTxtPtr *)&v55);
    if ( (unsigned int)CTxtPtr::FindEOP((CTxtPtr *)&v55, v6, &v71) )
      *((_BYTE *)v1 + 145) = 1;
    if ( (unsigned int)CRchTxtPtr::InTable((CRchTxtPtr *)v61) )
    {
      CTxtPtr::AdvanceCp((CTxtPtr *)&v55, v7 - v56);
      if ( *((_BYTE *)v1 + 145) )
      {
        if ( !(unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)&v55) )
        {
          EOP = CTxtPtr::FindEOP((CTxtPtr *)&v55, -1073741823, 0);
          CRchTxtPtr::Advance((CRchTxtPtr *)v61, EOP);
          v6 += v7 - v63;
        }
      }
      else if ( (v71 & 0x100) != 0 )
      {
        while ( 1 )
        {
          v10 = v56;
          if ( v56 >= v5 )
            goto LABEL_20;
          if ( CTxtPtr::GetChar((CTxtPtr *)&v55) == 9 )
          {
            v6 = v10 - v7;
            goto LABEL_20;
          }
          CTxtPtr::AdvanceCp((CTxtPtr *)&v55, 1);
        }
      }
    }
    v10 = v56;
LABEL_20:
    if ( *((_BYTE *)v1 + 145) )
    {
      CRunPtrBase::AdvanceCp((CRunPtrBase *)&v68, v5 - v7);
      if ( (unsigned int)CPFRunPtr::InTable((CPFRunPtr *)&v68) )
      {
        CTxtPtr::AdvanceCp((CTxtPtr *)&v55, v5 - v10);
        v6 += CTxtPtr::FindEOP((CTxtPtr *)&v55, 0x3FFFFFFF, 0);
      }
    }
  }
  v12 = (unsigned __int16 *)CW32System::PvAlloc(0x3001u, 0);
  v54 = v12;
  v13 = (unsigned int *)((char *)v1 + 132);
  v14 = v12;
  if ( !v12 )
  {
    v9 = 0;
    goto LABEL_26;
  }
  v15 = (char *)(v12 + 4096);
  *((_DWORD *)v1 + 32) = 0;
  *((_QWORD *)v1 + 19) = v15;
  *((_QWORD *)v1 + 21) = v15;
  *v13 = 0;
  if ( !DocInfo )
  {
LABEL_26:
    CCallMgr::SetOutOfMemory(v72[18]);
    *((_DWORD *)v1 + 12) = 9;
    if ( !v9 )
      goto LABEL_122;
    goto LABEL_121;
  }
  v71 = 0;
  if ( (unsigned int)CRTFWrite::BuildTables(v1, (struct CFormatRunPtr *)v66, (struct CFormatRunPtr *)&v67, v6, &v71) )
    goto LABEL_121;
  v16 = *((_DWORD *)v1 + 20);
  if ( (v16 & 0x20) != 0 )
    v17 = HIWORD(v16);
  else
    LOWORD(v17) = *((_WORD *)DocInfo + 9);
  if ( v71 )
  {
    if ( (_WORD)v17 != 0xFDE9 )
      goto LABEL_37;
    LOWORD(v17) = *((_WORD *)DocInfo + 9);
    v16 &= ~0x20u;
    *((_DWORD *)v1 + 20) = v16;
  }
  if ( (_WORD)v17 == 0xFDE9 )
  {
    v18 = 249;
    goto LABEL_38;
  }
LABEL_37:
  v18 = (v16 & 0x800) != 0 ? 181 : 194;
LABEL_38:
  if ( (unsigned int)CRTFWrite::PutCtrlWord(v1, 4, v18, 1)
    && (((_BYTE)v72[24] & 1) == 0 || (unsigned int)CRTFWrite::Puts(v1, "\\fbidis", 7))
    && (unsigned int)CRTFWrite::PutCtrlWord(v1, 0, 3, 0) )
  {
    if ( (unsigned __int16)(v17 - 1) > 0xFFFDu )
      goto LABEL_131;
    if ( (_WORD)v17 == 0xFDE9 )
      LOWORD(v17) = *((_WORD *)DocInfo + 9);
    if ( (unsigned int)CRTFWrite::PutCtrlWord(v1, 1, 4, (unsigned __int16)v17) )
    {
LABEL_131:
      if ( (unsigned int)CRTFWrite::printF(v1, "\\deff0") )
      {
        v19 = (CTxtEdit *)*((_QWORD *)v1 + 7);
        if ( !CTxtEdit::GetDocInfo(v19)
          || (v20 = *(_DWORD *)(*((_QWORD *)v19 + 20) + 24LL), v20 == 65534)
          || !(_WORD)v20
          || (unsigned int)CRTFWrite::PutCtrlWord(v1, 1, 56, (unsigned __int16)v20) )
        {
          v21 = (CTxtEdit *)*((_QWORD *)v1 + 7);
          if ( !CTxtEdit::GetDocInfo(v21)
            || (v22 = *(_DWORD *)(*((_QWORD *)v21 + 20) + 28LL), v22 == 65534)
            || !(_WORD)v22
            || (unsigned int)CRTFWrite::PutCtrlWord(v1, 1, 57, (unsigned __int16)v22) )
          {
            v23 = (CTxtEdit *)*((_QWORD *)v1 + 7);
            if ( !CTxtEdit::GetDocInfo(v23) )
              goto LABEL_61;
            v24 = *(_BYTE *)(*((_QWORD *)v23 + 20) + 57LL);
            if ( !v24 || (*(_BYTE *)(*((_QWORD *)v1 + 7) + 192LL) & 1) == 0 )
              goto LABEL_61;
            v25 = 196;
            if ( v24 != 2 )
              v25 = 119;
            if ( (unsigned int)CRTFWrite::PutCtrlWord(v1, 0, v25, 0) )
            {
LABEL_61:
              v26 = *((_DWORD *)DocInfo + 5);
              if ( (!v26 || v26 == 720 || (unsigned int)CRTFWrite::PutCtrlWord(v1, 1, 58, v26))
                && !(unsigned int)CRTFWrite::WriteFontTable(v1)
                && !(unsigned int)CRTFWrite::WriteColorTable(v1) )
              {
                if ( !*((_DWORD *)v1 + 54) )
                {
LABEL_74:
                  v28 = (_WORD *)*((_QWORD *)v1 + 7);
                  v29 = 100;
                  v30 = v28[92];
                  if ( v28[101] && v28[102] )
                    v29 = 100 * (unsigned int)(unsigned __int16)v28[101] / (unsigned __int16)v28[102];
                  if ( !(unsigned int)CRTFWrite::WriteInfo(v1)
                    && (!*((_BYTE *)v1 + 145)
                     || (unsigned int)CRTFWrite::PutCtrlWord(v1, 1, 251, (v30 & 0x2000) != 0 ? 2 : 4))
                    && ((*((_DWORD *)v1 + 20) & 0x2000) == 0
                     || v29 == 100
                     || (unsigned int)CRTFWrite::PutCtrlWord(v1, 1, 252, v29))
                    && (unsigned int)CRTFWrite::PutCtrlWord(v1, 1, 236, 1)
                    && v6 > 0 )
                  {
                    do
                    {
                      CchLeftRunPF = CRchTxtPtr::GetCchLeftRunPF((CRchTxtPtr *)v61);
                      v32 = v6;
                      if ( CchLeftRunPF < v6 )
                        v32 = CchLeftRunPF;
                      LODWORD(v72) = v32;
                      if ( (unsigned int)CRTFWrite::WriteParaFormat(v1, (const struct CRchTxtPtr *)v61) )
                        break;
                      while ( v32 > 0 )
                      {
                        CchLeftRunCF = CRchTxtPtr::GetCchLeftRunCF((CRchTxtPtr *)v61);
                        v34 = v32;
                        if ( CchLeftRunCF < v32 )
                          v34 = CchLeftRunCF;
                        v71 = v34;
                        CF = CRchTxtPtr::GetCF((CRchTxtPtr *)v61);
                        v35 = CF;
                        if ( (unsigned int)CRTFWrite::WriteCharFormat(v1, CF) )
                          goto LABEL_120;
                        CodePage = 65001;
                        if ( (*((_DWORD *)v1 + 20) & 0xFFFF0020) != 0xFDE90020 )
                        {
                          v37 = *((unsigned __int8 *)v35 + 4);
                          if ( (unsigned int)(v37 - 120) > 7 )
                          {
                            CodePage = CW32System::GetCodePage(v37);
                            if ( !CodePage && (*((_BYTE *)v1 + 80) & 0x20) != 0 )
                              CodePage = HIWORD(*((_DWORD *)v1 + 20));
                          }
                          else
                          {
                            CodePage = 1252;
                          }
                        }
                        while ( v34 > 0 )
                        {
                          v38 = v34;
                          if ( v34 > 4096 )
                            v38 = 4096;
                          Text = CTxtPtr::GetText((CTxtPtr *)&v62, v38, v54);
                          v40 = Text;
                          if ( Text > 0 )
                          {
                            v41 = v54;
                            v42 = Text;
                            v43 = v63;
                            while ( v42 > 0 )
                            {
                              v44 = v42;
                              v45 = v41;
                              do
                              {
                                v46 = *v41++;
                                if ( v46 == -4 )
                                  break;
                                --v42;
                              }
                              while ( v42 > 0 );
                              v1 = (CRTFWrite *)this;
                              v47 = v44 - v42;
                              LODWORD(v73) = v47;
                              v59 = v41;
                              if ( v47 )
                              {
                                if ( (unsigned int)CRTFWrite::WriteText(
                                                     (CRTFWrite *)this,
                                                     v47,
                                                     v45,
                                                     CodePage,
                                                     *(_DWORD *)CF & 0x40000) )
                                  goto LABEL_120;
                                v47 = (int)v73;
                              }
                              v48 = v47 + v43;
                              if ( v42 <= 0 )
                                break;
                              ObjectMgr = CTxtEdit::GetObjectMgr((CTxtEdit *)this[7]);
                              ObjectFromCp = CObjectMgr::GetObjectFromCp(ObjectMgr, v48);
                              v73 = ObjectFromCp;
                              if ( !ObjectFromCp )
                                goto LABEL_120;
                              (*(void (__fastcall **)(struct COleObject *))(*(_QWORD *)ObjectFromCp + 72LL))(ObjectFromCp);
                              if ( *((_BYTE *)this + 143) )
                              {
                                CRTFWrite::WriteObject((CRTFWrite *)this, v48, (HGLOBAL *)v73);
                              }
                              else if ( !(unsigned int)CRTFWrite::Puts((CRTFWrite *)this, "\\objattph\\'20", 13) )
                              {
                                goto LABEL_120;
                              }
                              v41 = v59;
                              v43 = v48 + 1;
                              --v42;
                            }
                            v34 = v71;
                            v32 = (int)v72;
                          }
                          CRchTxtPtr::Advance((CRchTxtPtr *)v61, v40);
                          v34 -= v40;
                          v32 -= v40;
                          v71 = v34;
                          v6 -= v40;
                          LODWORD(v72) = v32;
                        }
                      }
                    }
                    while ( v6 > 0 );
LABEL_120:
                    v14 = v54;
                  }
                  goto LABEL_121;
                }
                if ( (unsigned int)CRTFWrite::PutCtrlWord(v1, 2, 211, 0)
                  && (unsigned int)CRTFWrite::printF(v1, "{ Normal;}") )
                {
                  for ( i = 1; i < -*((_DWORD *)v1 + 54); ++i )
                  {
                    if ( !(unsigned int)CRTFWrite::printF(v1, "{\\s%d heading %d;}", i, i) )
                      goto LABEL_121;
                  }
                  CRTFWrite::Puts(v1, &szEndGroupCRLF, 3);
                  goto LABEL_74;
                }
              }
            }
          }
        }
      }
    }
LABEL_121:
    CRTFWrite::Puts(v1, &szEndGroupCRLF, 4);
    CRTFWrite::FlushBuffer(v1);
    v13 = (unsigned int *)((char *)v1 + 132);
  }
LABEL_122:
  CW32System::FreePv(v14);
  v51 = *((_DWORD *)v1 + 12);
  if ( v51 )
  {
    v52 = *((_QWORD *)v1 + 9);
    if ( !*(_DWORD *)(v52 + 8) )
    {
      if ( v51 < 0 )
        v51 = -v51;
      *(_DWORD *)(v52 + 8) = -v51;
    }
    v13 = (unsigned int *)((char *)v1 + 132);
    *((_DWORD *)v1 + 33) = 0;
  }
  return *v13;
}

```

## disassembly

```asm
0x180028064  mov     [rsp-8+arg_0], rcx
0x180028069  push    rbp
0x18002806a  push    rbx
0x18002806b  push    rsi
0x18002806c  push    rdi
0x18002806d  push    r12
0x18002806f  push    r13
0x180028071  push    r14
0x180028073  push    r15
0x180028075  lea     rbp, [rsp-1Fh]
0x18002807a  sub     rsp, 0E8h
0x180028081  mov     rax, [rcx+38h]
0x180028085  mov     rbx, rcx
0x180028088  mov     rcx, rax; this
0x18002808b  mov     [rbp+57h+arg_10], rax
0x18002808f  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x180028094  mov     rdx, [rbx+40h]
0x180028098  lea     rcx, [rbp+57h+var_B0]; this
0x18002809c  add     rdx, 8; struct CRchTxtPtr *
0x1800280a0  mov     r13, rax
0x1800280a3  call    ??0CRchTxtPtr@@QEAA@AEBV0@@Z; CRchTxtPtr::CRchTxtPtr(CRchTxtPtr const &)
0x1800280a8  mov     rcx, [rbx+40h]
0x1800280ac  xor     edi, edi
0x1800280ae  mov     edx, [rcx+58h]
0x1800280b1  mov     r15d, edx
0x1800280b4  mov     r8d, [rcx+28h]
0x1800280b8  mov     eax, r8d
0x1800280bb  sub     eax, edx
0x1800280bd  lea     rcx, [rbp+57h+var_B0]; this
0x1800280c1  test    edx, edx
0x1800280c3  mov     r14d, r8d
0x1800280c6  mov     r12d, r8d
0x1800280c9  cmovs   r14d, eax
0x1800280cd  neg     r15d
0x1800280d0  cmovs   r15d, edx
0x1800280d4  sub     r12d, edx
0x1800280d7  test    edx, edx
0x1800280d9  cmovs   r12d, r8d
0x1800280dd  mov     edx, r12d; int
0x1800280e0  call    ?SetCp@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::SetCp(long)
0x1800280e5  mov     rcx, [rbx+40h]
0x1800280e9  lea     esi, [rdi+1]
0x1800280ec  mov     al, [rcx+62h]
0x1800280ef  shr     al, 7
0x1800280f2  and     al, sil
0x1800280f5  mov     [rbx+91h], al
0x1800280fb  test    byte ptr [rcx+62h], 2
0x1800280ff  jnz     loc_180028249
0x180028105  mov     rcx, [rbp+57h+var_88]
0x180028109  movaps  xmm0, [rbp+57h+var_70]
0x18002810d  mov     eax, [rbp+57h+var_90]
0x180028110  movdqu  [rbp+57h+var_60], xmm0
0x180028115  mov     [rbp+57h+var_50], rcx
0x180028119  movaps  xmm0, [rbp+57h+var_A0]
0x18002811d  mov     [rsp+120h+var_D8], eax
0x180028121  mov     eax, [rbp+57h+var_8C]
0x180028124  mov     [rbp+57h+var_D0], rcx
0x180028128  lea     rcx, [rsp+120h+var_E8]; this
0x18002812d  movdqu  [rsp+120h+var_E8], xmm0
0x180028133  mov     [rbp+57h+var_D4], eax
0x180028136  mov     [rbp+57h+arg_8], edi
0x180028139  call    ?IsAtEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAtEOP(void)
0x18002813e  lea     r8, [rbp+57h+arg_8]; int *
0x180028142  mov     [rbx+91h], al
0x180028148  mov     edx, r15d; int
0x18002814b  lea     rcx, [rsp+120h+var_E8]; this
0x180028150  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x180028155  test    eax, eax
0x180028157  jz      short loc_180028160
0x180028159  mov     [rbx+91h], sil
0x180028160  lea     rcx, [rbp+57h+var_B0]; this
0x180028164  call    ?InTable@CRchTxtPtr@@QEBAHXZ; CRchTxtPtr::InTable(void)
0x180028169  test    eax, eax
0x18002816b  jz      loc_1800281FB
0x180028171  mov     edx, r12d
0x180028174  lea     rcx, [rsp+120h+var_E8]; this
0x180028179  sub     edx, [rsp+120h+var_D8]; int
0x18002817d  call    ?AdvanceCp@CTxtPtr@@QEAAJJ@Z; CTxtPtr::AdvanceCp(long)
0x180028182  cmp     [rbx+91h], dil
0x180028189  jnz     short loc_1800281C7
0x18002818b  test    [rbp+57h+arg_8], 100h
0x180028192  jz      short loc_1800281FB
0x180028194  mov     edi, [rsp+120h+var_D8]
0x180028198  cmp     edi, r14d
0x18002819b  jge     short loc_1800281FF
0x18002819d  lea     rcx, [rsp+120h+var_E8]; this
0x1800281a2  call    ?GetChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetChar(void)
0x1800281a7  mov     ecx, 9
0x1800281ac  cmp     ax, cx
0x1800281af  jz      short loc_1800281BF
0x1800281b1  mov     edx, esi; int
0x1800281b3  lea     rcx, [rsp+120h+var_E8]; this
0x1800281b8  call    ?AdvanceCp@CTxtPtr@@QEAAJJ@Z; CTxtPtr::AdvanceCp(long)
0x1800281bd  jmp     short loc_180028194
0x1800281bf  mov     r15d, edi
0x1800281c2  sub     r15d, r12d
0x1800281c5  jmp     short loc_1800281FF
0x1800281c7  lea     rcx, [rsp+120h+var_E8]; this
0x1800281cc  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x1800281d1  test    eax, eax
0x1800281d3  jnz     short loc_1800281FB
0x1800281d5  xor     r8d, r8d; int *
0x1800281d8  lea     rcx, [rsp+120h+var_E8]; this
0x1800281dd  mov     edx, 0C0000001h; int
0x1800281e2  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x1800281e7  mov     edx, eax; int
0x1800281e9  lea     rcx, [rbp+57h+var_B0]; this
0x1800281ed  call    ?Advance@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Advance(long)
0x1800281f2  mov     eax, r12d
0x1800281f5  sub     eax, [rbp+57h+var_90]
0x1800281f8  add     r15d, eax
0x1800281fb  mov     edi, [rsp+120h+var_D8]
0x1800281ff  cmp     byte ptr [rbx+91h], 0
0x180028206  jz      short loc_180028249
0x180028208  mov     edx, r14d
0x18002820b  lea     rcx, [rbp+57h+var_60]; this
0x18002820f  sub     edx, r12d; int
0x180028212  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x180028217  lea     rcx, [rbp+57h+var_60]; this
0x18002821b  call    ?InTable@CPFRunPtr@@QEAAHXZ; CPFRunPtr::InTable(void)
0x180028220  test    eax, eax
0x180028222  jz      short loc_180028249
0x180028224  sub     r14d, edi
0x180028227  lea     rcx, [rsp+120h+var_E8]; this
0x18002822c  mov     edx, r14d; int
0x18002822f  call    ?AdvanceCp@CTxtPtr@@QEAAJJ@Z; CTxtPtr::AdvanceCp(long)
0x180028234  xor     r8d, r8d; int *
0x180028237  lea     rcx, [rsp+120h+var_E8]; this
0x18002823c  mov     edx, 3FFFFFFFh; int
0x180028241  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x180028246  add     r15d, eax
0x180028249  xor     edx, edx; unsigned int
0x18002824b  mov     ecx, 3001h; unsigned int
0x180028250  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x180028255  xor     r14d, r14d
0x180028258  mov     [rsp+120h+var_F0], rax
0x18002825d  lea     rdi, [rbx+84h]
0x180028264  mov     r12, rax
0x180028267  test    rax, rax
0x18002826a  jnz     short loc_180028271
0x18002826c  mov     esi, r14d
0x18002826f  jmp     short loc_180028294
0x180028271  add     rax, 2000h
0x180028277  mov     [rbx+80h], r14d
0x18002827e  mov     [rbx+98h], rax
0x180028285  mov     [rbx+0A8h], rax
0x18002828c  mov     [rdi], r14d
0x18002828f  test    r13, r13
0x180028292  jnz     short loc_1800282B8
0x180028294  mov     rax, [rbp+57h+arg_10]
0x180028298  mov     rcx, [rax+90h]; this
0x18002829f  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x1800282a4  mov     dword ptr [rbx+30h], 9
0x1800282ab  test    esi, esi
0x1800282ad  jz      loc_18002887F
0x1800282b3  jmp     loc_18002885B
0x1800282b8  lea     rax, [rbp+57h+arg_8]
0x1800282bc  mov     [rbp+57h+arg_8], r14d
0x1800282c0  mov     r9d, r15d; int
0x1800282c3  mov     [rsp+120h+var_100], rax; int *
0x1800282c8  lea     r8, [rbp+57h+var_70]; struct CFormatRunPtr *
0x1800282cc  mov     rcx, rbx; this
0x1800282cf  lea     rdx, [rbp+57h+var_80]; struct CFormatRunPtr *
0x1800282d3  call    ?BuildTables@CRTFWrite@@AEAAHAEAVCFormatRunPtr@@0JAEAH@Z; CRTFWrite::BuildTables(CFormatRunPtr &,CFormatRunPtr &,long,int &)
0x1800282d8  test    eax, eax
0x1800282da  jnz     loc_18002885B
0x1800282e0  mov     eax, [rbx+50h]
0x1800282e3  test    al, 20h
0x1800282e5  jz      short loc_1800282F0
0x1800282e7  mov     r14d, eax
0x1800282ea  shr     r14d, 10h
0x1800282ee  jmp     short loc_1800282F5
0x1800282f0  movzx   r14d, word ptr [r13+12h]
0x1800282f5  cmp     [rbp+57h+arg_8], 0
0x1800282f9  mov     ecx, 0FDE9h
0x1800282fe  jz      short loc_180028311
0x180028300  cmp     r14w, cx
0x180028304  jnz     short loc_18002831F
0x180028306  movzx   r14d, word ptr [r13+12h]
0x18002830b  and     eax, 0FFFFFFDFh
0x18002830e  mov     [rbx+50h], eax
0x180028311  cmp     r14w, cx
0x180028315  jnz     short loc_18002831F
0x180028317  mov     r8d, 0F9h
0x18002831d  jmp     short loc_180028334
0x18002831f  and     eax, 800h
0x180028324  neg     eax
0x180028326  sbb     r8d, r8d
0x180028329  and     r8d, 0FFFFFFF3h
0x18002832d  add     r8d, 0C2h; int
0x180028334  mov     r9d, esi; int
0x180028337  mov     edx, 4; int
0x18002833c  mov     rcx, rbx; this
0x18002833f  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180028344  test    eax, eax
0x180028346  jz      loc_18002887F
0x18002834c  mov     rax, [rbp+57h+arg_10]
0x180028350  test    [rax+0C0h], sil
0x180028357  jz      short loc_180028376
0x180028359  mov     r8d, 7; int
0x18002835f  lea     rdx, aFbidis; "\\fbidis"
0x180028366  mov     rcx, rbx; this
0x180028369  call    ?Puts@CRTFWrite@@AEAAHPEBDJ@Z; CRTFWrite::Puts(char const *,long)
0x18002836e  test    eax, eax
0x180028370  jz      loc_18002887F
0x180028376  xor     r9d, r9d; int
0x180028379  xor     edx, edx; int
0x18002837b  mov     rcx, rbx; this
0x18002837e  lea     r8d, [r9+3]; int
0x180028382  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180028387  test    eax, eax
0x180028389  jz      loc_18002887F
0x18002838f  movzx   eax, r14w
0x180028393  mov     ecx, 0FFFDh
0x180028398  sub     ax, si
0x18002839b  cmp     ax, cx
0x18002839e  ja      short loc_1800283D0
0x1800283a0  mov     eax, 0FDE9h
0x1800283a5  cmp     r14w, ax
0x1800283a9  jnz     short loc_1800283B0
0x1800283ab  movzx   r14d, word ptr [r13+12h]
0x1800283b0  movzx   r9d, r14w; int
0x1800283b4  mov     r8d, 4; int
0x1800283ba  mov     edx, esi; int
0x1800283bc  mov     rcx, rbx; this
0x1800283bf  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800283c4  xor     r14d, r14d
0x1800283c7  test    eax, eax
0x1800283c9  jnz     short loc_1800283D3
0x1800283cb  jmp     loc_18002885B
0x1800283d0  xor     r14d, r14d
0x1800283d3  lea     rdx, Format; "\\deff0"
0x1800283da  mov     rcx, rbx; this
0x1800283dd  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x1800283e2  test    eax, eax
0x1800283e4  jz      loc_18002885B
0x1800283ea  mov     rdi, [rbx+38h]
0x1800283ee  mov     rcx, rdi; this
0x1800283f1  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x1800283f6  test    rax, rax
0x1800283f9  jz      short loc_18002842E
0x1800283fb  mov     rax, [rdi+0A0h]
0x180028402  mov     ecx, [rax+18h]
0x180028405  cmp     ecx, 0FFFEh
0x18002840b  jz      short loc_18002842E
0x18002840d  test    cx, cx
0x180028410  jz      short loc_18002842E
0x180028412  movzx   r9d, cx; int
0x180028416  mov     r8d, 38h ; '8'; int
0x18002841c  mov     rcx, rbx; this
0x18002841f  mov     edx, esi; int
0x180028421  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180028426  test    eax, eax
0x180028428  jz      loc_18002885B
0x18002842e  mov     rdi, [rbx+38h]
0x180028432  mov     rcx, rdi; this
0x180028435  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x18002843a  test    rax, rax
0x18002843d  jz      short loc_180028472
0x18002843f  mov     rax, [rdi+0A0h]
0x180028446  mov     ecx, [rax+1Ch]
0x180028449  cmp     ecx, 0FFFEh
0x18002844f  jz      short loc_180028472
0x180028451  test    cx, cx
0x180028454  jz      short loc_180028472
0x180028456  movzx   r9d, cx; int
0x18002845a  mov     r8d, 39h ; '9'; int
0x180028460  mov     rcx, rbx; this
0x180028463  mov     edx, esi; int
0x180028465  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18002846a  test    eax, eax
0x18002846c  jz      loc_18002885B
0x180028472  mov     rdi, [rbx+38h]
0x180028476  mov     rcx, rdi; this
0x180028479  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x18002847e  test    rax, rax
0x180028481  jz      short loc_1800284C3
0x180028483  mov     rax, [rdi+0A0h]
0x18002848a  mov     cl, [rax+39h]
0x18002848d  test    cl, cl
0x18002848f  jz      short loc_1800284C3
0x180028491  mov     rax, [rbx+38h]
0x180028495  test    [rax+0C0h], sil
0x18002849c  jz      short loc_1800284C3
0x18002849e  mov     eax, 77h ; 'w'
0x1800284a3  cmp     cl, 2
0x1800284a6  mov     rcx, rbx; this
0x1800284a9  lea     r8d, [rax+4Dh]
0x1800284ad  cmovnz  r8d, eax; int
0x1800284b1  xor     r9d, r9d; int
0x1800284b4  xor     edx, edx; int
0x1800284b6  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800284bb  test    eax, eax
0x1800284bd  jz      loc_18002885B
0x1800284c3  mov     r9d, [r13+14h]; int
0x1800284c7  test    r9d, r9d
0x1800284ca  jz      short loc_1800284ED
0x1800284cc  cmp     r9d, 2D0h
0x1800284d3  jz      short loc_1800284ED
0x1800284d5  mov     r8d, 3Ah ; ':'; int
  ... truncated ...
```

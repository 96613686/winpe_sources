# CRTFWrite::WriteRtf(void)

- ea: `0x18001c5e4`
- end: `0x18001ce44`
- name: `?WriteRtf@CRTFWrite@@QEAAJXZ`
- size: `2144`
- prototype: `__int64 __fastcall(CRTFWrite *__hidden this)`
- caller_count: `1`
- callee_count: `36`
- tags: ``

## callers

- `0x180041fe8`

## callees

- `0x180006570`
- `0x180009070`
- `0x18000fe40`
- `0x180015448`
- `0x18001c1d4`
- `0x18001c200`
- `0x18001c5e4`
- `0x18001ce50`
- `0x18001d14c`
- `0x18001d3c8`
- `0x18001d414`
- `0x18001db58`
- `0x18001dfe0`
- `0x18001f230`
- `0x18001f4a0`
- `0x180021f78`
- `0x180023884`
- `0x18002720c`
- `0x1800274a0`
- `0x18002f428`
- `0x1800301a0`
- `0x180037b78`
- `0x18003d330`
- `0x18003e9f4`
- `0x1800453dc`
- `0x1800466f0`
- `0x180046fd8`
- `0x180047cdc`
- `0x180048ed0`
- `0x180049a08`
- `0x18005d214`
- `0x180061480`
- `0x180071974`
- `0x180074878`
- `0x180080698`
- `0x180095010`

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
                                CRTFWrite::WriteObject((CRTFWrite *)this, v48, v73);
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
0x18001c5e4  mov     [rsp-8+arg_0], rcx
0x18001c5e9  push    rbp
0x18001c5ea  push    rbx
0x18001c5eb  push    rsi
0x18001c5ec  push    rdi
0x18001c5ed  push    r12
0x18001c5ef  push    r13
0x18001c5f1  push    r14
0x18001c5f3  push    r15
0x18001c5f5  lea     rbp, [rsp-1Fh]
0x18001c5fa  sub     rsp, 0E8h
0x18001c601  mov     rax, [rcx+38h]
0x18001c605  mov     rbx, rcx
0x18001c608  mov     rcx, rax; this
0x18001c60b  mov     [rbp+57h+arg_10], rax
0x18001c60f  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x18001c614  mov     rdx, [rbx+40h]
0x18001c618  lea     rcx, [rbp+57h+var_B0]; this
0x18001c61c  add     rdx, 8; struct CRchTxtPtr *
0x18001c620  mov     r13, rax
0x18001c623  call    ??0CRchTxtPtr@@QEAA@AEBV0@@Z; CRchTxtPtr::CRchTxtPtr(CRchTxtPtr const &)
0x18001c628  mov     rcx, [rbx+40h]
0x18001c62c  xor     edi, edi
0x18001c62e  mov     edx, [rcx+58h]
0x18001c631  mov     r15d, edx
0x18001c634  mov     r8d, [rcx+28h]
0x18001c638  mov     eax, r8d
0x18001c63b  sub     eax, edx
0x18001c63d  lea     rcx, [rbp+57h+var_B0]; this
0x18001c641  test    edx, edx
0x18001c643  mov     r14d, r8d
0x18001c646  mov     r12d, r8d
0x18001c649  cmovs   r14d, eax
0x18001c64d  neg     r15d
0x18001c650  cmovs   r15d, edx
0x18001c654  sub     r12d, edx
0x18001c657  test    edx, edx
0x18001c659  cmovs   r12d, r8d
0x18001c65d  mov     edx, r12d; int
0x18001c660  call    ?SetCp@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::SetCp(long)
0x18001c665  mov     rcx, [rbx+40h]
0x18001c669  lea     esi, [rdi+1]
0x18001c66c  mov     al, [rcx+62h]
0x18001c66f  shr     al, 7
0x18001c672  and     al, sil
0x18001c675  mov     [rbx+91h], al
0x18001c67b  test    byte ptr [rcx+62h], 2
0x18001c67f  jnz     loc_18001C7C9
0x18001c685  mov     rcx, [rbp+57h+var_88]
0x18001c689  movaps  xmm0, [rbp+57h+var_70]
0x18001c68d  mov     eax, [rbp+57h+var_90]
0x18001c690  movdqu  [rbp+57h+var_60], xmm0
0x18001c695  mov     [rbp+57h+var_50], rcx
0x18001c699  movaps  xmm0, [rbp+57h+var_A0]
0x18001c69d  mov     [rsp+120h+var_D8], eax
0x18001c6a1  mov     eax, [rbp+57h+var_8C]
0x18001c6a4  mov     [rbp+57h+var_D0], rcx
0x18001c6a8  lea     rcx, [rsp+120h+var_E8]; this
0x18001c6ad  movdqu  [rsp+120h+var_E8], xmm0
0x18001c6b3  mov     [rbp+57h+var_D4], eax
0x18001c6b6  mov     [rbp+57h+arg_8], edi
0x18001c6b9  call    ?IsAtEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAtEOP(void)
0x18001c6be  lea     r8, [rbp+57h+arg_8]; int *
0x18001c6c2  mov     [rbx+91h], al
0x18001c6c8  mov     edx, r15d; int
0x18001c6cb  lea     rcx, [rsp+120h+var_E8]; this
0x18001c6d0  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x18001c6d5  test    eax, eax
0x18001c6d7  jz      short loc_18001C6E0
0x18001c6d9  mov     [rbx+91h], sil
0x18001c6e0  lea     rcx, [rbp+57h+var_B0]; this
0x18001c6e4  call    ?InTable@CRchTxtPtr@@QEBAHXZ; CRchTxtPtr::InTable(void)
0x18001c6e9  test    eax, eax
0x18001c6eb  jz      loc_18001C77B
0x18001c6f1  mov     edx, r12d
0x18001c6f4  lea     rcx, [rsp+120h+var_E8]; this
0x18001c6f9  sub     edx, [rsp+120h+var_D8]; int
0x18001c6fd  call    ?AdvanceCp@CTxtPtr@@QEAAJJ@Z; CTxtPtr::AdvanceCp(long)
0x18001c702  cmp     [rbx+91h], dil
0x18001c709  jnz     short loc_18001C747
0x18001c70b  test    [rbp+57h+arg_8], 100h
0x18001c712  jz      short loc_18001C77B
0x18001c714  mov     edi, [rsp+120h+var_D8]
0x18001c718  cmp     edi, r14d
0x18001c71b  jge     short loc_18001C77F
0x18001c71d  lea     rcx, [rsp+120h+var_E8]; this
0x18001c722  call    ?GetChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetChar(void)
0x18001c727  mov     ecx, 9
0x18001c72c  cmp     ax, cx
0x18001c72f  jz      short loc_18001C73F
0x18001c731  mov     edx, esi; int
0x18001c733  lea     rcx, [rsp+120h+var_E8]; this
0x18001c738  call    ?AdvanceCp@CTxtPtr@@QEAAJJ@Z; CTxtPtr::AdvanceCp(long)
0x18001c73d  jmp     short loc_18001C714
0x18001c73f  mov     r15d, edi
0x18001c742  sub     r15d, r12d
0x18001c745  jmp     short loc_18001C77F
0x18001c747  lea     rcx, [rsp+120h+var_E8]; this
0x18001c74c  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x18001c751  test    eax, eax
0x18001c753  jnz     short loc_18001C77B
0x18001c755  xor     r8d, r8d; int *
0x18001c758  lea     rcx, [rsp+120h+var_E8]; this
0x18001c75d  mov     edx, 0C0000001h; int
0x18001c762  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x18001c767  mov     edx, eax; int
0x18001c769  lea     rcx, [rbp+57h+var_B0]; this
0x18001c76d  call    ?Advance@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Advance(long)
0x18001c772  mov     eax, r12d
0x18001c775  sub     eax, [rbp+57h+var_90]
0x18001c778  add     r15d, eax
0x18001c77b  mov     edi, [rsp+120h+var_D8]
0x18001c77f  cmp     byte ptr [rbx+91h], 0
0x18001c786  jz      short loc_18001C7C9
0x18001c788  mov     edx, r14d
0x18001c78b  lea     rcx, [rbp+57h+var_60]; this
0x18001c78f  sub     edx, r12d; int
0x18001c792  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18001c797  lea     rcx, [rbp+57h+var_60]; this
0x18001c79b  call    ?InTable@CPFRunPtr@@QEAAHXZ; CPFRunPtr::InTable(void)
0x18001c7a0  test    eax, eax
0x18001c7a2  jz      short loc_18001C7C9
0x18001c7a4  sub     r14d, edi
0x18001c7a7  lea     rcx, [rsp+120h+var_E8]; this
0x18001c7ac  mov     edx, r14d; int
0x18001c7af  call    ?AdvanceCp@CTxtPtr@@QEAAJJ@Z; CTxtPtr::AdvanceCp(long)
0x18001c7b4  xor     r8d, r8d; int *
0x18001c7b7  lea     rcx, [rsp+120h+var_E8]; this
0x18001c7bc  mov     edx, 3FFFFFFFh; int
0x18001c7c1  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x18001c7c6  add     r15d, eax
0x18001c7c9  xor     edx, edx; unsigned int
0x18001c7cb  mov     ecx, 3001h; unsigned int
0x18001c7d0  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18001c7d5  xor     r14d, r14d
0x18001c7d8  mov     [rsp+120h+var_F0], rax
0x18001c7dd  lea     rdi, [rbx+84h]
0x18001c7e4  mov     r12, rax
0x18001c7e7  test    rax, rax
0x18001c7ea  jnz     short loc_18001C7F1
0x18001c7ec  mov     esi, r14d
0x18001c7ef  jmp     short loc_18001C814
0x18001c7f1  add     rax, 2000h
0x18001c7f7  mov     [rbx+80h], r14d
0x18001c7fe  mov     [rbx+98h], rax
0x18001c805  mov     [rbx+0A8h], rax
0x18001c80c  mov     [rdi], r14d
0x18001c80f  test    r13, r13
0x18001c812  jnz     short loc_18001C838
0x18001c814  mov     rax, [rbp+57h+arg_10]
0x18001c818  mov     rcx, [rax+90h]; this
0x18001c81f  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x18001c824  mov     dword ptr [rbx+30h], 9
0x18001c82b  test    esi, esi
0x18001c82d  jz      loc_18001CDFF
0x18001c833  jmp     loc_18001CDDB
0x18001c838  lea     rax, [rbp+57h+arg_8]
0x18001c83c  mov     [rbp+57h+arg_8], r14d
0x18001c840  mov     r9d, r15d; int
0x18001c843  mov     [rsp+120h+var_100], rax; int *
0x18001c848  lea     r8, [rbp+57h+var_70]; struct CFormatRunPtr *
0x18001c84c  mov     rcx, rbx; this
0x18001c84f  lea     rdx, [rbp+57h+var_80]; struct CFormatRunPtr *
0x18001c853  call    ?BuildTables@CRTFWrite@@AEAAHAEAVCFormatRunPtr@@0JAEAH@Z; CRTFWrite::BuildTables(CFormatRunPtr &,CFormatRunPtr &,long,int &)
0x18001c858  test    eax, eax
0x18001c85a  jnz     loc_18001CDDB
0x18001c860  mov     eax, [rbx+50h]
0x18001c863  test    al, 20h
0x18001c865  jz      short loc_18001C870
0x18001c867  mov     r14d, eax
0x18001c86a  shr     r14d, 10h
0x18001c86e  jmp     short loc_18001C875
0x18001c870  movzx   r14d, word ptr [r13+12h]
0x18001c875  cmp     [rbp+57h+arg_8], 0
0x18001c879  mov     ecx, 0FDE9h
0x18001c87e  jz      short loc_18001C891
0x18001c880  cmp     r14w, cx
0x18001c884  jnz     short loc_18001C89F
0x18001c886  movzx   r14d, word ptr [r13+12h]
0x18001c88b  and     eax, 0FFFFFFDFh
0x18001c88e  mov     [rbx+50h], eax
0x18001c891  cmp     r14w, cx
0x18001c895  jnz     short loc_18001C89F
0x18001c897  mov     r8d, 0F9h
0x18001c89d  jmp     short loc_18001C8B4
0x18001c89f  and     eax, 800h
0x18001c8a4  neg     eax
0x18001c8a6  sbb     r8d, r8d
0x18001c8a9  and     r8d, 0FFFFFFF3h
0x18001c8ad  add     r8d, 0C2h; int
0x18001c8b4  mov     r9d, esi; int
0x18001c8b7  mov     edx, 4; int
0x18001c8bc  mov     rcx, rbx; this
0x18001c8bf  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18001c8c4  test    eax, eax
0x18001c8c6  jz      loc_18001CDFF
0x18001c8cc  mov     rax, [rbp+57h+arg_10]
0x18001c8d0  test    [rax+0C0h], sil
0x18001c8d7  jz      short loc_18001C8F6
0x18001c8d9  mov     r8d, 7; int
0x18001c8df  lea     rdx, aFbidis; "\\fbidis"
0x18001c8e6  mov     rcx, rbx; this
0x18001c8e9  call    ?Puts@CRTFWrite@@AEAAHPEBDJ@Z; CRTFWrite::Puts(char const *,long)
0x18001c8ee  test    eax, eax
0x18001c8f0  jz      loc_18001CDFF
0x18001c8f6  xor     r9d, r9d; int
0x18001c8f9  xor     edx, edx; int
0x18001c8fb  mov     rcx, rbx; this
0x18001c8fe  lea     r8d, [r9+3]; int
0x18001c902  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18001c907  test    eax, eax
0x18001c909  jz      loc_18001CDFF
0x18001c90f  movzx   eax, r14w
0x18001c913  mov     ecx, 0FFFDh
0x18001c918  sub     ax, si
0x18001c91b  cmp     ax, cx
0x18001c91e  ja      short loc_18001C950
0x18001c920  mov     eax, 0FDE9h
0x18001c925  cmp     r14w, ax
0x18001c929  jnz     short loc_18001C930
0x18001c92b  movzx   r14d, word ptr [r13+12h]
0x18001c930  movzx   r9d, r14w; int
0x18001c934  mov     r8d, 4; int
0x18001c93a  mov     edx, esi; int
0x18001c93c  mov     rcx, rbx; this
0x18001c93f  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18001c944  xor     r14d, r14d
0x18001c947  test    eax, eax
0x18001c949  jnz     short loc_18001C953
0x18001c94b  jmp     loc_18001CDDB
0x18001c950  xor     r14d, r14d
0x18001c953  lea     rdx, Format; "\\deff0"
0x18001c95a  mov     rcx, rbx; this
0x18001c95d  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x18001c962  test    eax, eax
0x18001c964  jz      loc_18001CDDB
0x18001c96a  mov     rdi, [rbx+38h]
0x18001c96e  mov     rcx, rdi; this
0x18001c971  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x18001c976  test    rax, rax
0x18001c979  jz      short loc_18001C9AE
0x18001c97b  mov     rax, [rdi+0A0h]
0x18001c982  mov     ecx, [rax+18h]
0x18001c985  cmp     ecx, 0FFFEh
0x18001c98b  jz      short loc_18001C9AE
0x18001c98d  test    cx, cx
0x18001c990  jz      short loc_18001C9AE
0x18001c992  movzx   r9d, cx; int
0x18001c996  mov     r8d, 38h ; '8'; int
0x18001c99c  mov     rcx, rbx; this
0x18001c99f  mov     edx, esi; int
0x18001c9a1  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18001c9a6  test    eax, eax
0x18001c9a8  jz      loc_18001CDDB
0x18001c9ae  mov     rdi, [rbx+38h]
0x18001c9b2  mov     rcx, rdi; this
0x18001c9b5  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x18001c9ba  test    rax, rax
0x18001c9bd  jz      short loc_18001C9F2
0x18001c9bf  mov     rax, [rdi+0A0h]
0x18001c9c6  mov     ecx, [rax+1Ch]
0x18001c9c9  cmp     ecx, 0FFFEh
0x18001c9cf  jz      short loc_18001C9F2
0x18001c9d1  test    cx, cx
0x18001c9d4  jz      short loc_18001C9F2
0x18001c9d6  movzx   r9d, cx; int
0x18001c9da  mov     r8d, 39h ; '9'; int
0x18001c9e0  mov     rcx, rbx; this
0x18001c9e3  mov     edx, esi; int
0x18001c9e5  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18001c9ea  test    eax, eax
0x18001c9ec  jz      loc_18001CDDB
0x18001c9f2  mov     rdi, [rbx+38h]
0x18001c9f6  mov     rcx, rdi; this
0x18001c9f9  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x18001c9fe  test    rax, rax
0x18001ca01  jz      short loc_18001CA43
0x18001ca03  mov     rax, [rdi+0A0h]
0x18001ca0a  mov     cl, [rax+39h]
0x18001ca0d  test    cl, cl
0x18001ca0f  jz      short loc_18001CA43
0x18001ca11  mov     rax, [rbx+38h]
0x18001ca15  test    [rax+0C0h], sil
0x18001ca1c  jz      short loc_18001CA43
0x18001ca1e  mov     eax, 77h ; 'w'
0x18001ca23  cmp     cl, 2
0x18001ca26  mov     rcx, rbx; this
0x18001ca29  lea     r8d, [rax+4Dh]
0x18001ca2d  cmovnz  r8d, eax; int
0x18001ca31  xor     r9d, r9d; int
0x18001ca34  xor     edx, edx; int
0x18001ca36  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18001ca3b  test    eax, eax
0x18001ca3d  jz      loc_18001CDDB
0x18001ca43  mov     r9d, [r13+14h]; int
0x18001ca47  test    r9d, r9d
0x18001ca4a  jz      short loc_18001CA6D
0x18001ca4c  cmp     r9d, 2D0h
0x18001ca53  jz      short loc_18001CA6D
0x18001ca55  mov     r8d, 3Ah ; ':'; int
  ... truncated ...
```

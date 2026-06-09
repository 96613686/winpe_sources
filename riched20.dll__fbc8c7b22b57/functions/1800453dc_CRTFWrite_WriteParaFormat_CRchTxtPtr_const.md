# CRTFWrite::WriteParaFormat(CRchTxtPtr const *)

- ea: `0x1800453dc`
- end: `0x180045c33`
- name: `?WriteParaFormat@CRTFWrite@@AEAAHPEBVCRchTxtPtr@@@Z`
- size: `2135`
- prototype: `__int64 __fastcall(CRTFWrite *__hidden this, const struct CRchTxtPtr *)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x18001c5e4`

## callees

- `0x180006570`
- `0x180009970`
- `0x18001c1d4`
- `0x18001d3c8`
- `0x18001dfe0`
- `0x18001f980`
- `0x180022ad4`
- `0x180025b38`
- `0x1800301a0`
- `0x180035b80`
- `0x18003fa40`
- `0x18003faf4`
- `0x18003fb94`
- `0x18004374c`
- `0x1800453dc`
- `0x180045fe4`
- `0x18004c8f4`
- `0x18007f990`
- `0x180093c00`

## pseudocode

```c
__int64 __fastcall CRTFWrite::WriteParaFormat(CRTFWrite *this, const struct CRchTxtPtr *a2)
{
  const struct CParaFormat *v2; // rbp
  const struct CParaFormat *PF; // rax
  int *v6; // rsi
  __int16 v7; // r15
  unsigned __int8 v8; // r13
  signed int v9; // ebx
  int v10; // r14d
  signed int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // edx
  __int16 v18; // bp
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  int EOP; // eax
  __int16 Format; // ax
  unsigned __int8 *CharFormat; // rbx
  int v24; // eax
  int v25; // r15d
  int v26; // r8d
  int v27; // r13d
  unsigned __int16 v28; // bx
  const char *v29; // r8
  unsigned __int16 v30; // r15
  int v31; // r15d
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  const char *v34; // r8
  int v35; // ebp
  int v36; // r9d
  int v37; // r9d
  int v38; // r9d
  int v39; // r9d
  int v40; // r9d
  int v41; // ebx
  int v42; // ebx
  int v43; // ebp
  int v44; // r15d
  const int *v45; // r13
  signed int v46; // r14d
  int v47; // r12d
  unsigned __int8 v49; // [rsp+30h] [rbp-B8h]
  signed int v50; // [rsp+34h] [rbp-B4h]
  int v51; // [rsp+38h] [rbp-B0h]
  __int16 v52; // [rsp+3Ch] [rbp-ACh]
  __int128 v53; // [rsp+40h] [rbp-A8h] BYREF
  _OWORD v54[2]; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int16 v55[24]; // [rsp+70h] [rbp-78h] BYREF

  v2 = (const struct CParaFormat *)*((_QWORD *)this + 29);
  PF = CRchTxtPtr::GetPF(a2);
  *((_QWORD *)this + 29) = PF;
  v6 = (int *)PF;
  v7 = *((_WORD *)PF + 1) & 0x4000;
  v8 = *((_BYTE *)PF + 34);
  v9 = *((unsigned __int8 *)PF + 17);
  v10 = *((_DWORD *)PF + 7);
  v52 = v7;
  v49 = v8;
  CRTFWrite::CheckInTable(this, 0);
  v11 = 0;
  if ( !v7 )
    v11 = v9;
  v50 = v11;
  if ( ((*((_BYTE *)this + 84) & 0x10) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 180, 0))
    && (unsigned int)CRTFWrite::PutCtrlWord(this, 0, 150, 0)
    && ((*((_BYTE *)this + 84) & 0x10) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 0, 180, 0)) )
  {
    if ( v7 )
    {
      if ( *((_BYTE *)this + 145) && !(unsigned int)CRTFWrite::PutCtrlWord(this, 0, 107, 0) )
        return *((unsigned int *)this + 12);
    }
    else if ( (unsigned int)CRTFWrite::PutBorders(this, 0) )
    {
      return *((unsigned int *)this + 12);
    }
    if ( !*((_WORD *)v6 + 19)
      || ((v12 = *((unsigned __int16 *)v6 + 19), v13 = *((_WORD *)v6 + 19) & 0xF, (unsigned int)(v13 - 1) > 0xB)
       || (unsigned int)CRTFWrite::PutCtrlWord(this, 0, (unsigned __int8)aFbidis[v13 + 7], 0))
      && (((v12 >> 6) & 0x1F) == 0
       || (v14 = CRTFWrite::LookupColor(this, *((_DWORD *)&g_Colors + ((((v12 >> 6) & 0x1F) - 1) & 0xF))),
           (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 45, v14 + 1)))
      && ((v15 = v12 >> 11) == 0
       || (v16 = CRTFWrite::LookupColor(this, *((_DWORD *)&g_Colors + (((_BYTE)v15 - 1) & 0xF))),
           (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 41, v16 + 1))) )
    {
      if ( !*((_WORD *)v6 + 18) || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 207, *((unsigned __int16 *)v6 + 18)) )
      {
        v17 = *((_DWORD *)this + 55);
        *((_WORD *)this + 70) = 0;
        *((_DWORD *)this + 55) = CParaFormat::UpdateNumber((CParaFormat *)v6, v17, v2);
        if ( *(_WORD *)v6 )
        {
          v18 = *((_WORD *)v6 + 21) & 0xF00;
          if ( (unsigned int)*(unsigned __int16 *)v6 - 2 > 5 )
          {
            v33 = *((_DWORD *)this + 44);
            if ( !(unsigned int)CRTFWrite::printF(this, "{\\pntext\\f%d\\'B7\\tab}", v33) )
              return *((unsigned int *)this + 12);
            v34 = "cont";
            if ( v18 != 1024 )
              v34 = "blt";
            if ( !(unsigned int)CRTFWrite::printF(
                                  this,
                                  "{\\*\\pn\\pnlvl%s\\pnf%d\\pnindent%d{\\pntxtb\\'B7}}",
                                  v34,
                                  v33,
                                  *((unsigned __int16 *)v6 + 22)) )
              return *((unsigned int *)this + 12);
          }
          else
          {
            v19 = *((_OWORD *)a2 + 2);
            v54[0] = *((_OWORD *)a2 + 1);
            v20 = *((_OWORD *)a2 + 3);
            v54[1] = v19;
            v53 = v20;
            EOP = CTxtPtr::FindEOP((CTxtPtr *)v54, 0x3FFFFFFF, 0);
            CRunPtrBase::AdvanceCp((CRunPtrBase *)&v53, EOP);
            CRunPtrBase::AdjustBackward((CRunPtrBase *)&v53);
            Format = CFormatRunPtr::GetFormat((CFormatRunPtr *)&v53);
            CharFormat = (unsigned __int8 *)CTxtArray::GetCharFormat(
                                              (CTxtArray *)(*((_QWORD *)this + 7) + 248LL),
                                              Format);
            v24 = CRTFWrite::LookupFont(this, (const struct CCharFormat *)CharFormat);
            v25 = 0;
            if ( v24 >= 0 )
              v25 = v24;
            *((_DWORD *)this + 56) = v25;
            v51 = v25;
            *((_DWORD *)this + 57) = CW32System::GetCodePage(CharFormat[4]);
            v27 = v26;
            if ( *(_WORD *)v6 <= 6u )
              v27 = *(unsigned __int16 *)v6 - 2;
            if ( (v18 & 0xFEFF) != 0 )
            {
              v28 = 46;
              if ( v18 != 512 )
                v28 = v26;
            }
            else
            {
              v28 = 41;
            }
            if ( v18 != 1024 )
            {
              CParaFormat::NumToStr((CParaFormat *)v6, v55, *((_DWORD *)this + 55), 1u);
              if ( !(unsigned int)CRTFWrite::printF(this, "{\\pntext\\f%d ", v25)
                || (unsigned int)CRTFWrite::WritePcData(this, v55, *((_DWORD *)this + 57), 0)
                || !(unsigned int)CRTFWrite::printF(this, "\\tab}") )
              {
                return *((unsigned int *)this + 12);
              }
            }
            v29 = "cont";
            v30 = *((_WORD *)v6 + 21);
            if ( v18 != 1024 )
              v29 = "body";
            if ( !(unsigned int)CRTFWrite::printF(
                                  this,
                                  "{\\*\\pn\\pnlvl%s\\pnf%d\\pnindent%d\\pnstart%d",
                                  v29,
                                  v51,
                                  *((unsigned __int16 *)v6 + 22),
                                  *((unsigned __int16 *)v6 + 20)) )
              return *((unsigned int *)this + 12);
            v31 = v30 & 3;
            if ( (unsigned int)(v31 - 1) <= 1
              && !(unsigned int)CRTFWrite::PutCtrlWord(this, 0, (unsigned int)(v31 != 1) + 172, 0) )
            {
              return *((unsigned int *)this + 12);
            }
            if ( !(unsigned int)CRTFWrite::PutCtrlWord(this, 0, *((unsigned __int8 *)qword_18009CD10 + v27), 0)
              || v18 == 256 && !(unsigned int)CRTFWrite::printF(this, "{\\pntxtb(}")
              || v28 && !(unsigned int)CRTFWrite::printF(this, "{\\pntxta%c}", v28)
              || !(unsigned int)CRTFWrite::printF(this, &szEndGroupCRLF) )
            {
              return *((unsigned int *)this + 12);
            }
            v7 = v52;
            v8 = v49;
          }
          *((_BYTE *)this + 140) = 1;
        }
        v32 = *((_WORD *)v6 + 1) & 0x1FF;
        if ( (*(_BYTE *)(*((_QWORD *)this + 7) + 192LL) & 1) == 0
          || (*((_BYTE *)v6 + 2) & 1) != 0
          || (unsigned int)CRTFWrite::PutCtrlWord(this, 0, 121, 0) )
        {
          v35 = 9;
          while ( v32 && v35 )
          {
            --v35;
            if ( (v32 & 1) != 0
              && !(unsigned int)CRTFWrite::PutCtrlWord(
                                  this,
                                  v35 == 2,
                                  *((unsigned __int8 *)&qword_18009CD10[6] + v35),
                                  0) )
            {
              return *((unsigned int *)this + 12);
            }
            v32 >>= 1;
          }
          if ( ((unsigned __int16)(*((_WORD *)v6 + 16) + 10) > 8u
             || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 199, ~*((__int16 *)v6 + 16)))
            && (v7
             || ((v36 = v6[3]) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 75, -v36))
             && ((v37 = v6[3] + v6[1]) == 0
              || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, (*((_BYTE *)v6 + 2) & 1) != 0 ? 191 : 114, v37))
             && ((v38 = v6[2]) == 0
              || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, (*((_BYTE *)v6 + 2) & 1) != 0 ? 114 : 191, v38))
             && ((v39 = v6[5]) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 201, v39))
             && ((v40 = v6[6]) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 200, v40))) )
          {
            if ( !v8 )
              goto LABEL_107;
            v41 = 0;
            if ( v8 == 4 )
            {
              if ( v10 < 0 )
                v10 = -v10;
              v10 = -v10;
            }
            else if ( v8 == 5 )
            {
              v41 = 1;
              v10 *= 12;
            }
            else if ( v8 != 3 && v10 > 0 )
            {
              v41 = 1;
              if ( v8 <= 2u )
                v10 = 120 * (v8 + 2);
            }
            if ( (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 208, v10)
              && (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 209, v41) )
            {
LABEL_107:
              if ( v7
                || (unsigned int)*((unsigned __int8 *)v6 + 16) - 2 > 2
                || (unsigned int)CRTFWrite::PutCtrlWord(
                                   this,
                                   0,
                                   *((unsigned __int8 *)&qword_18009CD10[2] + *((unsigned __int8 *)v6 + 16) + 3),
                                   0) )
              {
                v42 = 0;
                v43 = 0;
                v44 = 0;
                v45 = CTabsArray::Deref(qword_1800A72C0, *((__int16 *)v6 + 9));
                v46 = 0;
                if ( v50 )
                {
                  do
                  {
                    if ( v46 < (unsigned int)*((unsigned __int8 *)v6 + 17) )
                    {
                      _mm_lfence();
                      v42 = (v45[v46] >> 24) & 0xF;
                      v44 = v45[v46] & 0xFFFFFF;
                      v43 = v45[v46] >> 28;
                    }
                    v47 = 215;
                    if ( v42 != 4 )
                    {
                      v47 = 234;
                      if ( v42 )
                      {
                        if ( !(unsigned int)CRTFWrite::PutCtrlWord(
                                              this,
                                              0,
                                              *((unsigned __int8 *)&qword_18009CD10[1] + v42 + 7),
                                              0) )
                          break;
                      }
                    }
                    if ( v43
                      && !(unsigned int)CRTFWrite::PutCtrlWord(
                                          this,
                                          0,
                                          *((unsigned __int8 *)qword_18009CD10 + v43 + 7),
                                          0) )
                    {
                      break;
                    }
                    if ( !(unsigned int)CRTFWrite::PutCtrlWord(this, 1, v47, v44) )
                      break;
                    ++v46;
                  }
                  while ( v46 < v50 );
                }
              }
            }
          }
        }
      }
    }
  }
  return *((unsigned int *)this + 12);
}

```

## disassembly

```asm
0x1800453dc  mov     [rsp+arg_10], rbx
0x1800453e1  push    rbp
0x1800453e2  push    rsi
0x1800453e3  push    rdi
0x1800453e4  push    r12
0x1800453e6  push    r13
0x1800453e8  push    r14
0x1800453ea  push    r15
0x1800453ec  sub     rsp, 0B0h
0x1800453f3  mov     rax, cs:__security_cookie
0x1800453fa  xor     rax, rsp
0x1800453fd  mov     [rsp+0E8h+var_48], rax
0x180045405  mov     rbp, [rcx+0E8h]
0x18004540c  mov     rdi, rcx
0x18004540f  mov     rcx, rdx; this
0x180045412  mov     r12, rdx
0x180045415  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18004541a  mov     [rdi+0E8h], rax
0x180045421  mov     r15d, 4000h
0x180045427  xor     edx, edx; int
0x180045429  mov     rcx, rdi; this
0x18004542c  mov     rsi, rax
0x18004542f  and     r15w, [rax+2]
0x180045434  mov     r13b, [rax+22h]
0x180045438  movzx   ebx, byte ptr [rax+11h]
0x18004543c  mov     r14d, [rax+1Ch]
0x180045440  mov     [rsp+0E8h+var_AC], r15d
0x180045445  mov     [rsp+0E8h+var_B8], r13b
0x18004544a  call    ?CheckInTable@CRTFWrite@@AEAAHH@Z; CRTFWrite::CheckInTable(int)
0x18004544f  xor     ecx, ecx
0x180045451  test    r15w, r15w
0x180045455  mov     eax, ecx
0x180045457  cmovz   eax, ebx
0x18004545a  test    byte ptr [rdi+54h], 10h
0x18004545e  mov     [rsp+0E8h+var_B4], eax
0x180045462  jz      short loc_180045483
0x180045464  lea     edx, [rcx+1]; int
0x180045467  xor     r9d, r9d; int
0x18004546a  mov     rcx, rdi; this
0x18004546d  mov     r8d, 0B4h; int
0x180045473  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180045478  xor     ebx, ebx
0x18004547a  test    eax, eax
0x18004547c  jnz     short loc_180045485
0x18004547e  jmp     loc_180045C04
0x180045483  xor     ebx, ebx
0x180045485  xor     r9d, r9d; int
0x180045488  xor     edx, edx; int
0x18004548a  mov     r8d, 96h; int
0x180045490  mov     rcx, rdi; this
0x180045493  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180045498  test    eax, eax
0x18004549a  jz      loc_180045C04
0x1800454a0  test    byte ptr [rdi+54h], 10h
0x1800454a4  jz      short loc_1800454C1
0x1800454a6  xor     r9d, r9d; int
0x1800454a9  xor     edx, edx; int
0x1800454ab  mov     r8d, 0B4h; int
0x1800454b1  mov     rcx, rdi; this
0x1800454b4  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800454b9  test    eax, eax
0x1800454bb  jz      loc_180045C04
0x1800454c1  test    r15w, r15w
0x1800454c5  jz      short loc_1800454E9
0x1800454c7  cmp     [rdi+91h], bl
0x1800454cd  jz      short loc_1800454FB
0x1800454cf  xor     r9d, r9d; int
0x1800454d2  xor     edx, edx; int
0x1800454d4  mov     rcx, rdi; this
0x1800454d7  lea     r8d, [r9+6Bh]; int
0x1800454db  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800454e0  test    eax, eax
0x1800454e2  jnz     short loc_1800454FB
0x1800454e4  jmp     loc_180045C04
0x1800454e9  xor     edx, edx; int
0x1800454eb  mov     rcx, rdi; this
0x1800454ee  call    ?PutBorders@CRTFWrite@@AEAAHH@Z; CRTFWrite::PutBorders(int)
0x1800454f3  test    eax, eax
0x1800454f5  jnz     loc_180045C04
0x1800454fb  lea     r8, cs:180000000h
0x180045502  cmp     [rsi+26h], bx
0x180045506  jz      loc_1800455C6
0x18004550c  movzx   ebx, word ptr [rsi+26h]
0x180045510  mov     ecx, ebx
0x180045512  and     ecx, 0Fh
0x180045515  lea     eax, [rcx-1]
0x180045518  cmp     eax, 0Bh
0x18004551b  ja      short loc_180045542
0x18004551d  movzx   r8d, byte ptr [rcx+r8+9CCE7h]; int
0x180045526  xor     r9d, r9d; int
0x180045529  mov     rcx, rdi; this
0x18004552c  xor     edx, edx; int
0x18004552e  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180045533  test    eax, eax
0x180045535  jz      loc_180045C04
0x18004553b  lea     r8, cs:180000000h
0x180045542  mov     eax, ebx
0x180045544  shr     eax, 6
0x180045547  and     eax, 1Fh
0x18004554a  jz      short loc_180045580
0x18004554c  lea     rdx, [rax-1]
0x180045550  mov     rcx, rdi; this
0x180045553  and     edx, 0Fh
0x180045556  mov     edx, ds:rva ?g_Colors@@3QBKB[r8+rdx*4]; unsigned int
0x18004555e  call    ?LookupColor@CRTFWrite@@AEAAJK@Z; CRTFWrite::LookupColor(ulong)
0x180045563  mov     edx, 1; int
0x180045568  mov     rcx, rdi; this
0x18004556b  lea     r9d, [rax+1]; int
0x18004556f  lea     r8d, [rdx+2Ch]; int
0x180045573  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180045578  test    eax, eax
0x18004557a  jz      loc_180045C04
0x180045580  shr     ebx, 0Bh
0x180045583  test    ebx, ebx
0x180045585  jz      short loc_1800455C4
0x180045587  lea     rdx, [rbx-1]
0x18004558b  mov     rcx, rdi; this
0x18004558e  and     edx, 0Fh
0x180045591  lea     rax, cs:180000000h
0x180045598  mov     edx, ds:rva ?g_Colors@@3QBKB[rax+rdx*4]; unsigned int
0x18004559f  call    ?LookupColor@CRTFWrite@@AEAAJK@Z; CRTFWrite::LookupColor(ulong)
0x1800455a4  mov     edx, 1; int
0x1800455a9  mov     rcx, rdi; this
0x1800455ac  lea     r9d, [rax+1]; int
0x1800455b0  lea     r8d, [rdx+28h]; int
0x1800455b4  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800455b9  xor     ebx, ebx
0x1800455bb  test    eax, eax
0x1800455bd  jnz     short loc_1800455C6
0x1800455bf  jmp     loc_180045C04
0x1800455c4  xor     ebx, ebx
0x1800455c6  cmp     [rsi+24h], bx
0x1800455ca  jz      short loc_1800455EC
0x1800455cc  movzx   r9d, word ptr [rsi+24h]; int
0x1800455d1  mov     edx, 1; int
0x1800455d6  mov     r8d, 0CFh; int
0x1800455dc  mov     rcx, rdi; this
0x1800455df  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800455e4  test    eax, eax
0x1800455e6  jz      loc_180045C04
0x1800455ec  mov     edx, [rdi+0DCh]; int
0x1800455f2  mov     r8, rbp; struct CParaFormat *
0x1800455f5  mov     rcx, rsi; this
0x1800455f8  mov     word ptr [rdi+8Ch], 0
0x180045601  call    ?UpdateNumber@CParaFormat@@QEBAJJPEBV1@@Z; CParaFormat::UpdateNumber(long,CParaFormat const *)
0x180045606  mov     [rdi+0DCh], eax
0x18004560c  cmp     [rsi], bx
0x18004560f  jz      loc_180045884
0x180045615  movzx   eax, word ptr [rsi]
0x180045618  mov     ebp, 0F00h
0x18004561d  and     bp, [rsi+2Ah]
0x180045621  sub     eax, 2
0x180045624  cmp     eax, 5
0x180045627  ja      loc_1800458C5
0x18004562d  movups  xmm0, xmmword ptr [r12+10h]
0x180045633  xor     r8d, r8d; int *
0x180045636  mov     edx, 3FFFFFFFh; int
0x18004563b  movups  xmm1, xmmword ptr [r12+20h]
0x180045641  lea     rcx, [rsp+0E8h+var_98]; this
0x180045646  movups  [rsp+0E8h+var_98], xmm0
0x18004564b  movups  xmm0, xmmword ptr [r12+30h]
0x180045651  movups  [rsp+0E8h+var_88], xmm1
0x180045656  movdqu  [rsp+0E8h+var_A8], xmm0
0x18004565c  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x180045661  mov     edx, eax; int
0x180045663  lea     rcx, [rsp+0E8h+var_A8]; this
0x180045668  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18004566d  lea     rcx, [rsp+0E8h+var_A8]; this
0x180045672  call    ?AdjustBackward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustBackward(void)
0x180045677  lea     rcx, [rsp+0E8h+var_A8]; this
0x18004567c  call    ?GetFormat@CFormatRunPtr@@QEBAFXZ; CFormatRunPtr::GetFormat(void)
0x180045681  mov     rcx, [rdi+38h]
0x180045685  add     rcx, 0F8h; this
0x18004568c  movsx   edx, ax; int
0x18004568f  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x180045694  mov     rdx, rax; struct CCharFormat *
0x180045697  mov     rcx, rdi; this
0x18004569a  mov     rbx, rax
0x18004569d  call    ?LookupFont@CRTFWrite@@AEAAJPEBVCCharFormat@@@Z; CRTFWrite::LookupFont(CCharFormat const *)
0x1800456a2  xor     r8d, r8d
0x1800456a5  test    eax, eax
0x1800456a7  mov     r15d, r8d
0x1800456aa  cmovns  r15d, eax
0x1800456ae  mov     [rdi+0E0h], r15d
0x1800456b5  mov     cl, [rbx+4]; unsigned __int8
0x1800456b8  mov     [rsp+0E8h+var_B0], r15d
0x1800456bd  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x1800456c2  mov     [rdi+0E4h], eax
0x1800456c8  mov     r13d, r8d
0x1800456cb  cmp     word ptr [rsi], 6
0x1800456cf  ja      short loc_1800456D9
0x1800456d1  movzx   r13d, word ptr [rsi]
0x1800456d5  sub     r13d, 2
0x1800456d9  mov     eax, 0FEFFh
0x1800456de  test    ax, bp
0x1800456e1  jz      short loc_1800456F7
0x1800456e3  mov     ecx, 200h
0x1800456e8  mov     ebx, 2Eh ; '.'
0x1800456ed  cmp     bp, cx
0x1800456f0  cmovnz  bx, r8w
0x1800456f5  jmp     short loc_1800456FC
0x1800456f7  mov     ebx, 29h ; ')'
0x1800456fc  mov     r12d, 400h
0x180045702  cmp     bp, r12w
0x180045706  jz      short loc_180045775
0x180045708  mov     r8d, [rdi+0DCh]; int
0x18004570f  lea     rdx, [rsp+0E8h+var_78]; unsigned __int16 *
0x180045714  mov     r9d, 1; unsigned int
0x18004571a  mov     rcx, rsi; this
0x18004571d  call    ?NumToStr@CParaFormat@@QEBAJPEAGJK@Z; CParaFormat::NumToStr(ushort *,long,ulong)
0x180045722  mov     r8d, r15d
0x180045725  lea     rdx, aPntextFD; "{\\pntext\\f%d "
0x18004572c  mov     rcx, rdi; this
0x18004572f  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x180045734  xor     r15d, r15d
0x180045737  test    eax, eax
0x180045739  jz      loc_180045C04
0x18004573f  mov     r8d, [rdi+0E4h]; unsigned int
0x180045746  lea     rdx, [rsp+0E8h+var_78]; unsigned __int16 *
0x18004574b  xor     r9d, r9d; int
0x18004574e  mov     rcx, rdi; this
0x180045751  call    ?WritePcData@CRTFWrite@@AEAAHPEBGHH@Z; CRTFWrite::WritePcData(ushort const *,int,int)
0x180045756  test    eax, eax
0x180045758  jnz     loc_180045C04
0x18004575e  lea     rdx, aTab_0; "\\tab}"
0x180045765  mov     rcx, rdi; this
0x180045768  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x18004576d  test    eax, eax
0x18004576f  jz      loc_180045C04
0x180045775  movzx   ecx, word ptr [rsi+2Ch]
0x180045779  lea     rdx, aBody; "body"
0x180045780  movzx   eax, word ptr [rsi+28h]
0x180045784  lea     r8, aCont; "cont"
0x18004578b  mov     r9d, [rsp+0E8h+var_B0]
0x180045790  cmp     bp, r12w
0x180045794  movzx   r15d, word ptr [rsi+2Ah]
0x180045799  mov     [rsp+0E8h+var_C0], eax
0x18004579d  cmovnz  r8, rdx
0x1800457a1  mov     [rsp+0E8h+var_C8], ecx
0x1800457a5  lea     rdx, aPnPnlvlSPnfDPn; "{\\*\\pn\\pnlvl%s\\pnf%d\\pnindent%d\\p"...
0x1800457ac  mov     rcx, rdi; this
0x1800457af  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x1800457b4  xor     r12d, r12d
0x1800457b7  test    eax, eax
0x1800457b9  jz      loc_180045C04
0x1800457bf  and     r15d, 3
0x1800457c3  lea     eax, [r15-1]
0x1800457c7  cmp     eax, 1
0x1800457ca  ja      short loc_1800457F3
0x1800457cc  mov     r8d, r12d
0x1800457cf  cmp     r15d, 1
0x1800457d3  mov     rcx, rdi; this
0x1800457d6  setnz   r8b
0x1800457da  xor     r9d, r9d; int
0x1800457dd  add     r8d, 0ACh; int
0x1800457e4  xor     edx, edx; int
0x1800457e6  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800457eb  test    eax, eax
0x1800457ed  jz      loc_180045C04
0x1800457f3  movsxd  rax, r13d
0x1800457f6  lea     rcx, cs:180000000h
0x1800457fd  xor     r9d, r9d; int
0x180045800  xor     edx, edx; int
0x180045802  movzx   r8d, byte ptr [rax+rcx+9CD10h]; int
0x18004580b  mov     rcx, rdi; this
0x18004580e  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180045813  test    eax, eax
0x180045815  jz      loc_180045C04
0x18004581b  mov     eax, 100h
0x180045820  cmp     bp, ax
0x180045823  jnz     short loc_18004583C
0x180045825  lea     rdx, aPntxtb_0; "{\\pntxtb(}"
0x18004582c  mov     rcx, rdi; this
0x18004582f  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x180045834  test    eax, eax
0x180045836  jz      loc_180045C04
0x18004583c  test    bx, bx
0x18004583f  jz      short loc_18004585C
0x180045841  movzx   r8d, bx
0x180045845  lea     rdx, aPntxtaC; "{\\pntxta%c}"
0x18004584c  mov     rcx, rdi; this
0x18004584f  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x180045854  test    eax, eax
0x180045856  jz      loc_180045C04
0x18004585c  lea     rdx, ?szEndGroupCRLF@@3QBDB; Format
0x180045863  mov     rcx, rdi; this
0x180045866  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x18004586b  test    eax, eax
0x18004586d  jz      loc_180045C04
0x180045873  mov     r15d, [rsp+0E8h+var_AC]
0x180045878  mov     r13b, [rsp+0E8h+var_B8]
0x18004587d  mov     byte ptr [rdi+8Ch], 1
0x180045884  mov     rax, [rdi+38h]
0x180045888  movzx   ebx, word ptr [rsi+2]
0x18004588c  and     ebx, 1FFh
0x180045892  test    byte ptr [rax+0C0h], 1
0x180045899  jz      loc_180045928
0x18004589f  test    bl, 1
0x1800458a2  jnz     loc_180045928
0x1800458a8  xor     r9d, r9d; int
  ... truncated ...
```

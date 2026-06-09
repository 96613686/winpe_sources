# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800061ec`
- end: `0x180006585`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `921`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006018`

## callees

- `0x180004340`
- `0x180005b44`
- `0x1800061ec`
- `0x180007d08`
- `0x180014dc2`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800064d7`
- `msvcrt!memmove_s` at `0x1800064d7`
- `msvcrt!memcpy_s` at `0x1800062f7`
- `msvcrt!memcpy_s` at `0x180006396`
- `msvcrt!memcpy_s` at `0x180006548`
- `msvcrt!memcpy_s` at `0x1800062f7`
- `msvcrt!memcpy_s` at `0x180006396`
- `msvcrt!memcpy_s` at `0x180006548`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rbx
  unsigned __int8 *v11; // r8
  unsigned __int8 *v12; // rbx
  char v13; // al
  bool v14; // al
  unsigned __int64 v15; // r12
  int v16; // ecx
  unsigned __int8 *v17; // rsi
  unsigned __int64 v18; // rax
  unsigned int v19; // edx
  rsize_t v20; // r9
  unsigned int *p_Source; // r8
  unsigned int v22; // esi
  unsigned int v23; // eax
  bool v24; // zf
  rsize_t v25; // r9
  unsigned int *v26; // r8
  rsize_t v27; // rdx
  unsigned __int8 *v28; // r8
  bool v29; // si
  __int64 v30; // rcx
  __int64 v32; // rax
  char v33; // dl
  unsigned __int64 v34; // rdx
  __int64 v35; // rsi
  unsigned __int64 v36; // r9
  __int16 v37; // r8
  rsize_t v38; // r9
  rsize_t v39; // rdx
  unsigned int *v40; // r8
  __int16 v41; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int16 v43; // [rsp+40h] [rbp-59h] BYREF
  char v44; // [rsp+42h] [rbp-57h]
  unsigned int Source; // [rsp+44h] [rbp-55h] BYREF
  unsigned __int16 v46; // [rsp+48h] [rbp-51h]
  void *Buf2[2]; // [rsp+50h] [rbp-49h]
  __int16 v48; // [rsp+60h] [rbp-39h] BYREF
  char v49; // [rsp+62h] [rbp-37h]
  unsigned int v50; // [rsp+64h] [rbp-35h]
  __int16 v51; // [rsp+68h] [rbp-31h]
  __int64 v52; // [rsp+70h] [rbp-29h]
  void *v53; // [rsp+78h] [rbp-21h]
  __int16 v54; // [rsp+80h] [rbp-19h] BYREF
  char v55; // [rsp+82h] [rbp-17h]
  int v56; // [rsp+84h] [rbp-15h]
  __int16 v57; // [rsp+88h] [rbp-11h]
  __int128 v58; // [rsp+90h] [rbp-9h]
  __int16 v59; // [rsp+F0h] [rbp+57h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v11 = (unsigned __int8 *)*((_QWORD *)this + 4);
  v12 = (unsigned __int8 *)(v6 + 10);
  v43 = *((_WORD *)this + 1);
  v13 = *((_BYTE *)this + 4);
  Source = 0;
  v46 = 0;
  LOBYTE(v59) = 0;
  v44 = v13;
  InsertionPointOrIncrement = v12;
  *(_OWORD *)Buf2 = 0;
  v14 = wil::details_abi::UsageIndexProperty::Read(
          (wil::details_abi::UsageIndexProperty *)&v43,
          &InsertionPointOrIncrement,
          v11);
  v15 = a5;
  while ( 1 )
  {
    v29 = v14;
    if ( !v14 )
    {
      v12 = InsertionPointOrIncrement;
      goto LABEL_30;
    }
    v16 = Size == v46 ? memcmp_0(Buf1, Buf2[1], Size) : Size - v46;
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v43,
                                    InsertionPointOrIncrement,
                                    a4,
                                    v15,
                                    a6);
      v12 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        LOBYTE(v59) = 1;
        goto LABEL_38;
      }
      return 1;
    }
    v12 = InsertionPointOrIncrement;
    if ( *((_QWORD *)this + 2) )
    {
      v17 = InsertionPointOrIncrement;
      v18 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
      v19 = Source;
      if ( Source > v18 && Source != (_DWORD)v18 )
      {
        v19 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
        Source = v19;
        if ( v44 == 1 )
        {
          v41 = v18;
          v20 = 2;
          p_Source = (unsigned int *)&v41;
          goto LABEL_15;
        }
        if ( v44 == 2 )
        {
          v20 = 4;
          p_Source = &Source;
LABEL_15:
          memcpy_s(Buf2[0], v20, p_Source, v20);
          v19 = Source;
        }
      }
      v12 = &v17[*((_QWORD *)this + 2) * v19];
      goto LABEL_27;
    }
    v54 = *((_WORD *)this + 3);
    v22 = 0;
    v55 = *((_BYTE *)this + 8);
    v23 = Source;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    if ( Source )
    {
      do
      {
        v24 = !wil::details_abi::UsageIndexProperty::Read(
                 (wil::details_abi::UsageIndexProperty *)&v54,
                 &InsertionPointOrIncrement,
                 *((unsigned __int8 **)this + 4));
        v23 = Source;
        if ( v24 )
          break;
        ++v22;
      }
      while ( v22 < Source );
      v12 = InsertionPointOrIncrement;
    }
    if ( v23 != v22 )
    {
      Source = v22;
      if ( v44 == 1 )
      {
        v41 = v22;
        v25 = 2;
        v26 = (unsigned int *)&v41;
        v27 = 2;
      }
      else
      {
        if ( v44 != 2 )
          goto LABEL_27;
        v27 = 4;
        v26 = &Source;
        v25 = 4;
      }
      memcpy_s(Buf2[0], v27, v26, v25);
    }
LABEL_27:
    v28 = (unsigned __int8 *)*((_QWORD *)this + 4);
    InsertionPointOrIncrement = v12;
    v14 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v43,
            &InsertionPointOrIncrement,
            v28);
  }
  InsertionPointOrIncrement = v12;
LABEL_38:
  if ( !v29 )
LABEL_30:
    *((_QWORD *)this + 4) = v12;
  v30 = 0;
  if ( !(_BYTE)v59 )
  {
    Source = 1;
    v46 = Size;
    Buf2[0] = 0;
    Buf2[1] = Buf1;
    if ( v43 )
      v30 = v43;
    else
      v30 = (unsigned __int16)Size + 2LL;
    if ( v44 == 1 )
    {
      v30 += 2;
    }
    else if ( v44 == 2 )
    {
      v30 += 4;
    }
  }
  v32 = *((unsigned __int16 *)this + 3);
  v33 = *((_BYTE *)this + 8);
  v48 = v32;
  v49 = v33;
  v50 = a6;
  v51 = v15;
  v52 = 0;
  v53 = a4;
  if ( !(_WORD)v32 )
    v32 = (unsigned __int16)v15 + 2LL;
  if ( v33 == 1 )
  {
    v32 += 2;
  }
  else if ( v33 == 2 )
  {
    v32 += 4;
  }
  v34 = *((_QWORD *)this + 5);
  v35 = v32 + v30;
  v36 = *((_QWORD *)this + 4);
  if ( ((v34 - v36) & -(__int64)(v36 < v34)) >= v32 + v30 )
  {
    memmove_s(&v12[v35], v34 - v35 - (_QWORD)v12, v12, v36 - (_QWORD)v12);
    *((_QWORD *)this + 4) += v35;
    if ( !(_BYTE)v59 )
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v43,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
LABEL_61:
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v48,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
    if ( !v44 )
      goto LABEL_61;
    v37 = Source + 1;
    if ( Source == Source + 1 )
      goto LABEL_61;
    ++Source;
    if ( v44 == 1 )
    {
      v38 = 2;
      v59 = v37;
      v39 = 2;
      v40 = (unsigned int *)&v59;
    }
    else
    {
      if ( v44 != 2 )
        goto LABEL_61;
      v40 = &Source;
      v38 = 4;
      v39 = 4;
    }
    memcpy_s(Buf2[0], v39, v40, v38);
    goto LABEL_61;
  }
  return 0;
}

```

## disassembly

```asm
0x1800061ec  push    rbp
0x1800061ee  push    rbx
0x1800061ef  push    rsi
0x1800061f0  push    rdi
0x1800061f1  push    r12
0x1800061f3  push    r13
0x1800061f5  push    r14
0x1800061f7  push    r15
0x1800061f9  lea     rbp, [rsp-0Fh]
0x1800061fe  sub     rsp, 0A8h
0x180006205  mov     rbx, [rcx+18h]
0x180006209  mov     rdi, rcx
0x18000620c  xor     ecx, ecx
0x18000620e  mov     r13, r9
0x180006211  mov     r14, r8
0x180006214  mov     r15, rdx
0x180006217  test    rbx, rbx
0x18000621a  jz      loc_18000656E
0x180006220  movzx   eax, word ptr [rdi+2]
0x180006224  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006228  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000622c  add     rbx, 0Ah
0x180006230  mov     [rbp+47h+var_A0], ax
0x180006234  xorps   xmm0, xmm0
0x180006237  mov     al, [rdi+4]
0x18000623a  mov     [rbp+47h+Source], ecx
0x18000623d  mov     [rbp+47h+var_98], cx
0x180006241  mov     byte ptr [rbp+47h+arg_0], cl
0x180006244  lea     rcx, [rbp+47h+var_A0]; this
0x180006248  mov     [rbp+47h+var_9E], al
0x18000624b  mov     [rbp+47h+var_A8], rbx
0x18000624f  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180006254  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006259  mov     r12, [rbp+47h+arg_20]
0x18000625d  jmp     loc_1800063B7
0x180006262  movzx   eax, [rbp+47h+var_98]
0x180006266  cmp     r14, rax
0x180006269  jnz     short loc_180006281
0x18000626b  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000626f  mov     r8, r14; Size
0x180006272  mov     rcx, r15; Buf1
0x180006275  call    memcmp_0
0x18000627a  mov     ecx, eax
0x18000627c  xor     r9d, r9d
0x18000627f  jmp     short loc_18000628A
0x180006281  movzx   eax, [rbp+47h+var_98]
0x180006285  mov     ecx, r14d
0x180006288  sub     ecx, eax
0x18000628a  test    ecx, ecx
0x18000628c  js      loc_18000643C
0x180006292  jz      loc_180006401
0x180006298  mov     rbx, [rbp+47h+var_A8]
0x18000629c  mov     [rbp+47h+var_A8], rbx
0x1800062a0  cmp     [rdi+10h], r9
0x1800062a4  jbe     short loc_180006315
0x1800062a6  mov     rax, [rdi+20h]
0x1800062aa  xor     edx, edx
0x1800062ac  sub     rax, [rdi+18h]
0x1800062b0  mov     rsi, rbx
0x1800062b3  div     qword ptr [rdi+10h]
0x1800062b7  mov     edx, [rbp+47h+Source]
0x1800062ba  cmp     rdx, rax
0x1800062bd  jbe     short loc_180006306
0x1800062bf  cmp     edx, eax
0x1800062c1  jz      short loc_180006306
0x1800062c3  mov     edx, eax
0x1800062c5  mov     [rbp+47h+Source], eax
0x1800062c8  mov     al, [rbp+47h+var_9E]
0x1800062cb  cmp     al, 1
0x1800062cd  jnz     short loc_1800062E2
0x1800062cf  movzx   eax, dx
0x1800062d2  mov     [rbp+47h+var_B0], dx
0x1800062d6  mov     r9d, 2
0x1800062dc  lea     r8, [rbp+47h+var_B0]
0x1800062e0  jmp     short loc_1800062F0
0x1800062e2  cmp     al, 2
0x1800062e4  jnz     short loc_180006306
0x1800062e6  mov     r9d, 4; SourceSize
0x1800062ec  lea     r8, [rbp+47h+Source]; Source
0x1800062f0  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800062f4  mov     rdx, r9; DestinationSize
0x1800062f7  call    cs:__imp_memcpy_s
0x1800062fe  nop     dword ptr [rax+rax+00h]
0x180006303  mov     edx, [rbp+47h+Source]
0x180006306  mov     ebx, edx
0x180006308  imul    rbx, [rdi+10h]
0x18000630d  add     rbx, rsi
0x180006310  jmp     loc_1800063A2
0x180006315  movzx   eax, word ptr [rdi+6]
0x180006319  xorps   xmm0, xmm0
0x18000631c  mov     [rbp+47h+var_60], ax
0x180006320  mov     esi, r9d
0x180006323  mov     al, [rdi+8]
0x180006326  mov     [rbp+47h+var_5E], al
0x180006329  mov     eax, [rbp+47h+Source]
0x18000632c  mov     [rbp+47h+var_5C], r9d
0x180006330  mov     [rbp+47h+var_58], r9w
0x180006335  movdqu  [rbp+47h+var_50], xmm0
0x18000633a  test    eax, eax
0x18000633c  jz      short loc_180006360
0x18000633e  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006342  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006346  lea     rcx, [rbp+47h+var_60]; this
0x18000634a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000634f  test    al, al
0x180006351  mov     eax, [rbp+47h+Source]
0x180006354  jz      short loc_18000635C
0x180006356  inc     esi
0x180006358  cmp     esi, eax
0x18000635a  jb      short loc_18000633E
0x18000635c  mov     rbx, [rbp+47h+var_A8]
0x180006360  cmp     eax, esi
0x180006362  jz      short loc_1800063A2
0x180006364  mov     al, [rbp+47h+var_9E]
0x180006367  mov     [rbp+47h+Source], esi
0x18000636a  cmp     al, 1
0x18000636c  jnz     short loc_180006382
0x18000636e  mov     eax, 2
0x180006373  mov     [rbp+47h+var_B0], si
0x180006377  mov     r9d, eax
0x18000637a  lea     r8, [rbp+47h+var_B0]
0x18000637e  mov     edx, eax
0x180006380  jmp     short loc_180006392
0x180006382  cmp     al, 2
0x180006384  jnz     short loc_1800063A2
0x180006386  mov     edx, 4; DestinationSize
0x18000638b  lea     r8, [rbp+47h+Source]; Source
0x18000638f  mov     r9d, edx; SourceSize
0x180006392  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006396  call    cs:__imp_memcpy_s
0x18000639d  nop     dword ptr [rax+rax+00h]
0x1800063a2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800063a6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800063aa  lea     rcx, [rbp+47h+var_A0]; this
0x1800063ae  mov     [rbp+47h+var_A8], rbx
0x1800063b2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800063b7  xor     r9d, r9d
0x1800063ba  mov     sil, al
0x1800063bd  test    al, al
0x1800063bf  jnz     loc_180006262
0x1800063c5  mov     rbx, [rbp+47h+var_A8]
0x1800063c9  mov     [rdi+20h], rbx
0x1800063cd  mov     rcx, r9
0x1800063d0  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1800063d4  jnz     loc_18000645F
0x1800063da  movzx   eax, [rbp+47h+var_A0]
0x1800063de  mov     [rbp+47h+Source], 1
0x1800063e5  mov     [rbp+47h+var_98], r14w
0x1800063ea  mov     [rbp+47h+Buf2], r9
0x1800063ee  mov     [rbp+47h+Buf2+8], r15
0x1800063f2  test    ax, ax
0x1800063f5  jnz     short loc_180006447
0x1800063f7  movzx   ecx, r14w
0x1800063fb  add     rcx, 2
0x1800063ff  jmp     short loc_18000644A
0x180006401  mov     eax, [rbp+47h+arg_28]
0x180006404  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180006408  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000640c  mov     r9, r13; void *
0x18000640f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180006413  mov     rcx, rdi; this
0x180006416  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000641b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180006420  xor     r9d, r9d
0x180006423  mov     [rbp+47h+var_A8], rax
0x180006427  mov     rbx, rax
0x18000642a  test    rax, rax
0x18000642d  jnz     short loc_180006436
0x18000642f  mov     al, 1
0x180006431  jmp     loc_180006570
0x180006436  mov     byte ptr [rbp+47h+arg_0], 1
0x18000643a  jmp     short loc_180006440
0x18000643c  mov     [rbp+47h+var_A8], rbx
0x180006440  test    sil, sil
0x180006443  jnz     short loc_1800063CD
0x180006445  jmp     short loc_1800063C9
0x180006447  mov     rcx, rax
0x18000644a  mov     al, [rbp+47h+var_9E]
0x18000644d  cmp     al, 1
0x18000644f  jnz     short loc_180006457
0x180006451  add     rcx, 2
0x180006455  jmp     short loc_18000645F
0x180006457  cmp     al, 2
0x180006459  jnz     short loc_18000645F
0x18000645b  add     rcx, 4
0x18000645f  movzx   eax, word ptr [rdi+6]
0x180006463  mov     dl, [rdi+8]
0x180006466  mov     r8d, [rbp+47h+arg_28]
0x18000646a  mov     [rbp+47h+var_80], ax
0x18000646e  mov     [rbp+47h+var_7E], dl
0x180006471  mov     [rbp+47h+var_7C], r8d
0x180006475  mov     [rbp+47h+var_78], r12w
0x18000647a  mov     [rbp+47h+var_70], r9
0x18000647e  mov     [rbp+47h+var_68], r13
0x180006482  test    ax, ax
0x180006485  jnz     short loc_18000648F
0x180006487  movzx   eax, r12w
0x18000648b  add     rax, 2
0x18000648f  cmp     dl, 1
0x180006492  jnz     short loc_18000649A
0x180006494  add     rax, 2
0x180006498  jmp     short loc_1800064A3
0x18000649a  cmp     dl, 2
0x18000649d  jnz     short loc_1800064A3
0x18000649f  add     rax, 4
0x1800064a3  mov     rdx, [rdi+28h]
0x1800064a7  lea     rsi, [rax+rcx]
0x1800064ab  mov     r9, [rdi+20h]
0x1800064af  mov     rcx, rdx
0x1800064b2  sub     rcx, r9
0x1800064b5  cmp     r9, rdx
0x1800064b8  sbb     rax, rax
0x1800064bb  and     rax, rcx
0x1800064be  cmp     rax, rsi
0x1800064c1  jb      loc_18000656E
0x1800064c7  sub     rdx, rsi
0x1800064ca  lea     rcx, [rsi+rbx]; Destination
0x1800064ce  sub     rdx, rbx; DestinationSize
0x1800064d1  sub     r9, rbx; SourceSize
0x1800064d4  mov     r8, rbx; Source
0x1800064d7  call    cs:__imp_memmove_s
0x1800064de  nop     dword ptr [rax+rax+00h]
0x1800064e3  add     [rdi+20h], rsi
0x1800064e7  xor     ebx, ebx
0x1800064e9  cmp     byte ptr [rbp+47h+arg_0], bl
0x1800064ec  jnz     short loc_180006501
0x1800064ee  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800064f2  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800064f6  lea     rcx, [rbp+47h+var_A0]; this
0x1800064fa  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800064ff  jmp     short loc_180006554
0x180006501  mov     cl, [rbp+47h+var_9E]
0x180006504  test    cl, cl
0x180006506  jz      short loc_180006554
0x180006508  mov     eax, [rbp+47h+Source]
0x18000650b  lea     r8d, [rax+1]
0x18000650f  cmp     eax, r8d
0x180006512  jz      short loc_180006554
0x180006514  mov     [rbp+47h+Source], r8d
0x180006518  cmp     cl, 1
0x18000651b  jnz     short loc_180006531
0x18000651d  mov     r9d, 2
0x180006523  mov     [rbp+47h+arg_0], r8w
0x180006528  mov     edx, r9d
0x18000652b  lea     r8, [rbp+47h+arg_0]
0x18000652f  jmp     short loc_180006544
0x180006531  cmp     cl, 2
0x180006534  jnz     short loc_180006554
0x180006536  mov     eax, 4
0x18000653b  lea     r8, [rbp+47h+Source]; Source
0x18000653f  mov     r9d, eax; SourceSize
0x180006542  mov     edx, eax; DestinationSize
0x180006544  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006548  call    cs:__imp_memcpy_s
0x18000654f  nop     dword ptr [rax+rax+00h]
0x180006554  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006558  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000655c  lea     rcx, [rbp+47h+var_80]; this
0x180006560  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006565  mov     byte ptr [rdi+38h], 1
0x180006569  jmp     loc_18000642F
0x18000656e  xor     al, al
0x180006570  add     rsp, 0A8h
0x180006577  pop     r15
0x180006579  pop     r14
0x18000657b  pop     r13
0x18000657d  pop     r12
0x18000657f  pop     rdi
0x180006580  pop     rsi
0x180006581  pop     rbx
0x180006582  pop     rbp
0x180006583  retn
```

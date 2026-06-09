# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1400151e4`
- end: `0x140015564`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140015034`

## callees

- `0x1400138b8`
- `0x140014c1c`
- `0x1400151e4`
- `0x140016a74`
- `0x1400187a6`

## import_xrefs

- `msvcrt!memmove_s` at `0x1400154c3`
- `msvcrt!memmove_s` at `0x1400154c3`
- `msvcrt!memcpy_s` at `0x1400152ef`
- `msvcrt!memcpy_s` at `0x140015388`
- `msvcrt!memcpy_s` at `0x14001552e`
- `msvcrt!memcpy_s` at `0x1400152ef`
- `msvcrt!memcpy_s` at `0x140015388`
- `msvcrt!memcpy_s` at `0x14001552e`

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
0x1400151e4  push    rbp
0x1400151e6  push    rbx
0x1400151e7  push    rsi
0x1400151e8  push    rdi
0x1400151e9  push    r12
0x1400151eb  push    r13
0x1400151ed  push    r14
0x1400151ef  push    r15
0x1400151f1  lea     rbp, [rsp-0Fh]
0x1400151f6  sub     rsp, 0A8h
0x1400151fd  mov     rbx, [rcx+18h]
0x140015201  mov     rdi, rcx
0x140015204  xor     ecx, ecx
0x140015206  mov     r13, r9
0x140015209  mov     r14, r8
0x14001520c  mov     r15, rdx
0x14001520f  test    rbx, rbx
0x140015212  jz      loc_14001554E
0x140015218  movzx   eax, word ptr [rdi+2]
0x14001521c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140015220  mov     r8, [rdi+20h]; unsigned __int8 *
0x140015224  add     rbx, 0Ah
0x140015228  mov     [rbp+47h+var_A0], ax
0x14001522c  xorps   xmm0, xmm0
0x14001522f  mov     al, [rdi+4]
0x140015232  mov     [rbp+47h+Source], ecx
0x140015235  mov     [rbp+47h+var_98], cx
0x140015239  mov     byte ptr [rbp+47h+arg_0], cl
0x14001523c  lea     rcx, [rbp+47h+var_A0]; this
0x140015240  mov     [rbp+47h+var_9E], al
0x140015243  mov     [rbp+47h+var_A8], rbx
0x140015247  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x14001524c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140015251  mov     r12, [rbp+47h+arg_20]
0x140015255  jmp     loc_1400153A3
0x14001525a  movzx   eax, [rbp+47h+var_98]
0x14001525e  cmp     r14, rax
0x140015261  jnz     short loc_140015279
0x140015263  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x140015267  mov     r8, r14; Size
0x14001526a  mov     rcx, r15; Buf1
0x14001526d  call    memcmp_0
0x140015272  mov     ecx, eax
0x140015274  xor     r9d, r9d
0x140015277  jmp     short loc_140015282
0x140015279  movzx   eax, [rbp+47h+var_98]
0x14001527d  mov     ecx, r14d
0x140015280  sub     ecx, eax
0x140015282  test    ecx, ecx
0x140015284  js      loc_140015428
0x14001528a  jz      loc_1400153ED
0x140015290  mov     rbx, [rbp+47h+var_A8]
0x140015294  mov     [rbp+47h+var_A8], rbx
0x140015298  cmp     [rdi+10h], r9
0x14001529c  jbe     short loc_140015307
0x14001529e  mov     rax, [rdi+20h]
0x1400152a2  xor     edx, edx
0x1400152a4  sub     rax, [rdi+18h]
0x1400152a8  mov     rsi, rbx
0x1400152ab  div     qword ptr [rdi+10h]
0x1400152af  mov     edx, [rbp+47h+Source]
0x1400152b2  cmp     rdx, rax
0x1400152b5  jbe     short loc_1400152F8
0x1400152b7  cmp     edx, eax
0x1400152b9  jz      short loc_1400152F8
0x1400152bb  mov     edx, eax
0x1400152bd  mov     [rbp+47h+Source], eax
0x1400152c0  mov     al, [rbp+47h+var_9E]
0x1400152c3  cmp     al, 1
0x1400152c5  jnz     short loc_1400152DA
0x1400152c7  movzx   eax, dx
0x1400152ca  mov     [rbp+47h+var_B0], dx
0x1400152ce  mov     r9d, 2
0x1400152d4  lea     r8, [rbp+47h+var_B0]
0x1400152d8  jmp     short loc_1400152E8
0x1400152da  cmp     al, 2
0x1400152dc  jnz     short loc_1400152F8
0x1400152de  mov     r9d, 4; SourceSize
0x1400152e4  lea     r8, [rbp+47h+Source]; Source
0x1400152e8  mov     rcx, [rbp+47h+Buf2]; Destination
0x1400152ec  mov     rdx, r9; DestinationSize
0x1400152ef  call    cs:__imp_memcpy_s
0x1400152f5  mov     edx, [rbp+47h+Source]
0x1400152f8  mov     ebx, edx
0x1400152fa  imul    rbx, [rdi+10h]
0x1400152ff  add     rbx, rsi
0x140015302  jmp     loc_14001538E
0x140015307  movzx   eax, word ptr [rdi+6]
0x14001530b  xorps   xmm0, xmm0
0x14001530e  mov     [rbp+47h+var_60], ax
0x140015312  mov     esi, r9d
0x140015315  mov     al, [rdi+8]
0x140015318  mov     [rbp+47h+var_5E], al
0x14001531b  mov     eax, [rbp+47h+Source]
0x14001531e  mov     [rbp+47h+var_5C], r9d
0x140015322  mov     [rbp+47h+var_58], r9w
0x140015327  movdqu  [rbp+47h+var_50], xmm0
0x14001532c  test    eax, eax
0x14001532e  jz      short loc_140015352
0x140015330  mov     r8, [rdi+20h]; unsigned __int8 *
0x140015334  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140015338  lea     rcx, [rbp+47h+var_60]; this
0x14001533c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140015341  test    al, al
0x140015343  mov     eax, [rbp+47h+Source]
0x140015346  jz      short loc_14001534E
0x140015348  inc     esi
0x14001534a  cmp     esi, eax
0x14001534c  jb      short loc_140015330
0x14001534e  mov     rbx, [rbp+47h+var_A8]
0x140015352  cmp     eax, esi
0x140015354  jz      short loc_14001538E
0x140015356  mov     al, [rbp+47h+var_9E]
0x140015359  mov     [rbp+47h+Source], esi
0x14001535c  cmp     al, 1
0x14001535e  jnz     short loc_140015374
0x140015360  mov     eax, 2
0x140015365  mov     [rbp+47h+var_B0], si
0x140015369  mov     r9d, eax
0x14001536c  lea     r8, [rbp+47h+var_B0]
0x140015370  mov     edx, eax
0x140015372  jmp     short loc_140015384
0x140015374  cmp     al, 2
0x140015376  jnz     short loc_14001538E
0x140015378  mov     edx, 4; DestinationSize
0x14001537d  lea     r8, [rbp+47h+Source]; Source
0x140015381  mov     r9d, edx; SourceSize
0x140015384  mov     rcx, [rbp+47h+Buf2]; Destination
0x140015388  call    cs:__imp_memcpy_s
0x14001538e  mov     r8, [rdi+20h]; unsigned __int8 *
0x140015392  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140015396  lea     rcx, [rbp+47h+var_A0]; this
0x14001539a  mov     [rbp+47h+var_A8], rbx
0x14001539e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400153a3  xor     r9d, r9d
0x1400153a6  mov     sil, al
0x1400153a9  test    al, al
0x1400153ab  jnz     loc_14001525A
0x1400153b1  mov     rbx, [rbp+47h+var_A8]
0x1400153b5  mov     [rdi+20h], rbx
0x1400153b9  mov     rcx, r9
0x1400153bc  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1400153c0  jnz     loc_14001544B
0x1400153c6  movzx   eax, [rbp+47h+var_A0]
0x1400153ca  mov     [rbp+47h+Source], 1
0x1400153d1  mov     [rbp+47h+var_98], r14w
0x1400153d6  mov     [rbp+47h+Buf2], r9
0x1400153da  mov     [rbp+47h+Buf2+8], r15
0x1400153de  test    ax, ax
0x1400153e1  jnz     short loc_140015433
0x1400153e3  movzx   ecx, r14w
0x1400153e7  add     rcx, 2
0x1400153eb  jmp     short loc_140015436
0x1400153ed  mov     eax, [rbp+47h+arg_28]
0x1400153f0  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x1400153f4  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1400153f8  mov     r9, r13; void *
0x1400153fb  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1400153ff  mov     rcx, rdi; this
0x140015402  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x140015407  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14001540c  xor     r9d, r9d
0x14001540f  mov     [rbp+47h+var_A8], rax
0x140015413  mov     rbx, rax
0x140015416  test    rax, rax
0x140015419  jnz     short loc_140015422
0x14001541b  mov     al, 1
0x14001541d  jmp     loc_140015550
0x140015422  mov     byte ptr [rbp+47h+arg_0], 1
0x140015426  jmp     short loc_14001542C
0x140015428  mov     [rbp+47h+var_A8], rbx
0x14001542c  test    sil, sil
0x14001542f  jnz     short loc_1400153B9
0x140015431  jmp     short loc_1400153B5
0x140015433  mov     rcx, rax
0x140015436  mov     al, [rbp+47h+var_9E]
0x140015439  cmp     al, 1
0x14001543b  jnz     short loc_140015443
0x14001543d  add     rcx, 2
0x140015441  jmp     short loc_14001544B
0x140015443  cmp     al, 2
0x140015445  jnz     short loc_14001544B
0x140015447  add     rcx, 4
0x14001544b  movzx   eax, word ptr [rdi+6]
0x14001544f  mov     dl, [rdi+8]
0x140015452  mov     r8d, [rbp+47h+arg_28]
0x140015456  mov     [rbp+47h+var_80], ax
0x14001545a  mov     [rbp+47h+var_7E], dl
0x14001545d  mov     [rbp+47h+var_7C], r8d
0x140015461  mov     [rbp+47h+var_78], r12w
0x140015466  mov     [rbp+47h+var_70], r9
0x14001546a  mov     [rbp+47h+var_68], r13
0x14001546e  test    ax, ax
0x140015471  jnz     short loc_14001547B
0x140015473  movzx   eax, r12w
0x140015477  add     rax, 2
0x14001547b  cmp     dl, 1
0x14001547e  jnz     short loc_140015486
0x140015480  add     rax, 2
0x140015484  jmp     short loc_14001548F
0x140015486  cmp     dl, 2
0x140015489  jnz     short loc_14001548F
0x14001548b  add     rax, 4
0x14001548f  mov     rdx, [rdi+28h]
0x140015493  lea     rsi, [rax+rcx]
0x140015497  mov     r9, [rdi+20h]
0x14001549b  mov     rcx, rdx
0x14001549e  sub     rcx, r9
0x1400154a1  cmp     r9, rdx
0x1400154a4  sbb     rax, rax
0x1400154a7  and     rax, rcx
0x1400154aa  cmp     rax, rsi
0x1400154ad  jb      loc_14001554E
0x1400154b3  sub     rdx, rsi
0x1400154b6  lea     rcx, [rsi+rbx]; Destination
0x1400154ba  sub     rdx, rbx; DestinationSize
0x1400154bd  sub     r9, rbx; SourceSize
0x1400154c0  mov     r8, rbx; Source
0x1400154c3  call    cs:__imp_memmove_s
0x1400154c9  add     [rdi+20h], rsi
0x1400154cd  xor     ebx, ebx
0x1400154cf  cmp     byte ptr [rbp+47h+arg_0], bl
0x1400154d2  jnz     short loc_1400154E7
0x1400154d4  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400154d8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1400154dc  lea     rcx, [rbp+47h+var_A0]; this
0x1400154e0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1400154e5  jmp     short loc_140015534
0x1400154e7  mov     cl, [rbp+47h+var_9E]
0x1400154ea  test    cl, cl
0x1400154ec  jz      short loc_140015534
0x1400154ee  mov     eax, [rbp+47h+Source]
0x1400154f1  lea     r8d, [rax+1]
0x1400154f5  cmp     eax, r8d
0x1400154f8  jz      short loc_140015534
0x1400154fa  mov     [rbp+47h+Source], r8d
0x1400154fe  cmp     cl, 1
0x140015501  jnz     short loc_140015517
0x140015503  mov     r9d, 2
0x140015509  mov     [rbp+47h+arg_0], r8w
0x14001550e  mov     edx, r9d
0x140015511  lea     r8, [rbp+47h+arg_0]
0x140015515  jmp     short loc_14001552A
0x140015517  cmp     cl, 2
0x14001551a  jnz     short loc_140015534
0x14001551c  mov     eax, 4
0x140015521  lea     r8, [rbp+47h+Source]; Source
0x140015525  mov     r9d, eax; SourceSize
0x140015528  mov     edx, eax; DestinationSize
0x14001552a  mov     rcx, [rbp+47h+Buf2]; Destination
0x14001552e  call    cs:__imp_memcpy_s
0x140015534  mov     r8, [rdi+20h]; unsigned __int8 *
0x140015538  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14001553c  lea     rcx, [rbp+47h+var_80]; this
0x140015540  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140015545  mov     byte ptr [rdi+38h], 1
0x140015549  jmp     loc_14001541B
0x14001554e  xor     al, al
0x140015550  add     rsp, 0A8h
0x140015557  pop     r15
0x140015559  pop     r14
0x14001555b  pop     r13
0x14001555d  pop     r12
0x14001555f  pop     rdi
0x140015560  pop     rsi
0x140015561  pop     rbx
0x140015562  pop     rbp
0x140015563  retn
```

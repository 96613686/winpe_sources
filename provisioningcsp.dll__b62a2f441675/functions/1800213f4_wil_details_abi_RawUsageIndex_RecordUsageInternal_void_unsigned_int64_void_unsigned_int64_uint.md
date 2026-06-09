# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800213f4`
- end: `0x18002178d`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `921`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021220`

## callees

- `0x180016dd4`
- `0x180020dc8`
- `0x1800213f4`
- `0x180022808`
- `0x180035846`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800216df`
- `msvcrt!memmove_s` at `0x1800216df`
- `msvcrt!memcpy_s` at `0x1800214ff`
- `msvcrt!memcpy_s` at `0x18002159e`
- `msvcrt!memcpy_s` at `0x180021750`
- `msvcrt!memcpy_s` at `0x1800214ff`
- `msvcrt!memcpy_s` at `0x18002159e`
- `msvcrt!memcpy_s` at `0x180021750`

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
0x1800213f4  push    rbp
0x1800213f6  push    rbx
0x1800213f7  push    rsi
0x1800213f8  push    rdi
0x1800213f9  push    r12
0x1800213fb  push    r13
0x1800213fd  push    r14
0x1800213ff  push    r15
0x180021401  lea     rbp, [rsp-0Fh]
0x180021406  sub     rsp, 0A8h
0x18002140d  mov     rbx, [rcx+18h]
0x180021411  mov     rdi, rcx
0x180021414  xor     ecx, ecx
0x180021416  mov     r13, r9
0x180021419  mov     r14, r8
0x18002141c  mov     r15, rdx
0x18002141f  test    rbx, rbx
0x180021422  jz      loc_180021776
0x180021428  movzx   eax, word ptr [rdi+2]
0x18002142c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180021430  mov     r8, [rdi+20h]; unsigned __int8 *
0x180021434  add     rbx, 0Ah
0x180021438  mov     [rbp+47h+var_A0], ax
0x18002143c  xorps   xmm0, xmm0
0x18002143f  mov     al, [rdi+4]
0x180021442  mov     [rbp+47h+Source], ecx
0x180021445  mov     [rbp+47h+var_98], cx
0x180021449  mov     byte ptr [rbp+47h+arg_0], cl
0x18002144c  lea     rcx, [rbp+47h+var_A0]; this
0x180021450  mov     [rbp+47h+var_9E], al
0x180021453  mov     [rbp+47h+var_A8], rbx
0x180021457  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18002145c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180021461  mov     r12, [rbp+47h+arg_20]
0x180021465  jmp     loc_1800215BF
0x18002146a  movzx   eax, [rbp+47h+var_98]
0x18002146e  cmp     r14, rax
0x180021471  jnz     short loc_180021489
0x180021473  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180021477  mov     r8, r14; Size
0x18002147a  mov     rcx, r15; Buf1
0x18002147d  call    memcmp_0
0x180021482  mov     ecx, eax
0x180021484  xor     r9d, r9d
0x180021487  jmp     short loc_180021492
0x180021489  movzx   eax, [rbp+47h+var_98]
0x18002148d  mov     ecx, r14d
0x180021490  sub     ecx, eax
0x180021492  test    ecx, ecx
0x180021494  js      loc_180021644
0x18002149a  jz      loc_180021609
0x1800214a0  mov     rbx, [rbp+47h+var_A8]
0x1800214a4  mov     [rbp+47h+var_A8], rbx
0x1800214a8  cmp     [rdi+10h], r9
0x1800214ac  jbe     short loc_18002151D
0x1800214ae  mov     rax, [rdi+20h]
0x1800214b2  xor     edx, edx
0x1800214b4  sub     rax, [rdi+18h]
0x1800214b8  mov     rsi, rbx
0x1800214bb  div     qword ptr [rdi+10h]
0x1800214bf  mov     edx, [rbp+47h+Source]
0x1800214c2  cmp     rdx, rax
0x1800214c5  jbe     short loc_18002150E
0x1800214c7  cmp     edx, eax
0x1800214c9  jz      short loc_18002150E
0x1800214cb  mov     edx, eax
0x1800214cd  mov     [rbp+47h+Source], eax
0x1800214d0  mov     al, [rbp+47h+var_9E]
0x1800214d3  cmp     al, 1
0x1800214d5  jnz     short loc_1800214EA
0x1800214d7  movzx   eax, dx
0x1800214da  mov     [rbp+47h+var_B0], dx
0x1800214de  mov     r9d, 2
0x1800214e4  lea     r8, [rbp+47h+var_B0]
0x1800214e8  jmp     short loc_1800214F8
0x1800214ea  cmp     al, 2
0x1800214ec  jnz     short loc_18002150E
0x1800214ee  mov     r9d, 4; SourceSize
0x1800214f4  lea     r8, [rbp+47h+Source]; Source
0x1800214f8  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800214fc  mov     rdx, r9; DestinationSize
0x1800214ff  call    cs:__imp_memcpy_s
0x180021506  nop     dword ptr [rax+rax+00h]
0x18002150b  mov     edx, [rbp+47h+Source]
0x18002150e  mov     ebx, edx
0x180021510  imul    rbx, [rdi+10h]
0x180021515  add     rbx, rsi
0x180021518  jmp     loc_1800215AA
0x18002151d  movzx   eax, word ptr [rdi+6]
0x180021521  xorps   xmm0, xmm0
0x180021524  mov     [rbp+47h+var_60], ax
0x180021528  mov     esi, r9d
0x18002152b  mov     al, [rdi+8]
0x18002152e  mov     [rbp+47h+var_5E], al
0x180021531  mov     eax, [rbp+47h+Source]
0x180021534  mov     [rbp+47h+var_5C], r9d
0x180021538  mov     [rbp+47h+var_58], r9w
0x18002153d  movdqu  [rbp+47h+var_50], xmm0
0x180021542  test    eax, eax
0x180021544  jz      short loc_180021568
0x180021546  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002154a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18002154e  lea     rcx, [rbp+47h+var_60]; this
0x180021552  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180021557  test    al, al
0x180021559  mov     eax, [rbp+47h+Source]
0x18002155c  jz      short loc_180021564
0x18002155e  inc     esi
0x180021560  cmp     esi, eax
0x180021562  jb      short loc_180021546
0x180021564  mov     rbx, [rbp+47h+var_A8]
0x180021568  cmp     eax, esi
0x18002156a  jz      short loc_1800215AA
0x18002156c  mov     al, [rbp+47h+var_9E]
0x18002156f  mov     [rbp+47h+Source], esi
0x180021572  cmp     al, 1
0x180021574  jnz     short loc_18002158A
0x180021576  mov     eax, 2
0x18002157b  mov     [rbp+47h+var_B0], si
0x18002157f  mov     r9d, eax
0x180021582  lea     r8, [rbp+47h+var_B0]
0x180021586  mov     edx, eax
0x180021588  jmp     short loc_18002159A
0x18002158a  cmp     al, 2
0x18002158c  jnz     short loc_1800215AA
0x18002158e  mov     edx, 4; DestinationSize
0x180021593  lea     r8, [rbp+47h+Source]; Source
0x180021597  mov     r9d, edx; SourceSize
0x18002159a  mov     rcx, [rbp+47h+Buf2]; Destination
0x18002159e  call    cs:__imp_memcpy_s
0x1800215a5  nop     dword ptr [rax+rax+00h]
0x1800215aa  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800215ae  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800215b2  lea     rcx, [rbp+47h+var_A0]; this
0x1800215b6  mov     [rbp+47h+var_A8], rbx
0x1800215ba  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800215bf  xor     r9d, r9d
0x1800215c2  mov     sil, al
0x1800215c5  test    al, al
0x1800215c7  jnz     loc_18002146A
0x1800215cd  mov     rbx, [rbp+47h+var_A8]
0x1800215d1  mov     [rdi+20h], rbx
0x1800215d5  mov     rcx, r9
0x1800215d8  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1800215dc  jnz     loc_180021667
0x1800215e2  movzx   eax, [rbp+47h+var_A0]
0x1800215e6  mov     [rbp+47h+Source], 1
0x1800215ed  mov     [rbp+47h+var_98], r14w
0x1800215f2  mov     [rbp+47h+Buf2], r9
0x1800215f6  mov     [rbp+47h+Buf2+8], r15
0x1800215fa  test    ax, ax
0x1800215fd  jnz     short loc_18002164F
0x1800215ff  movzx   ecx, r14w
0x180021603  add     rcx, 2
0x180021607  jmp     short loc_180021652
0x180021609  mov     eax, [rbp+47h+arg_28]
0x18002160c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180021610  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180021614  mov     r9, r13; void *
0x180021617  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18002161b  mov     rcx, rdi; this
0x18002161e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180021623  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180021628  xor     r9d, r9d
0x18002162b  mov     [rbp+47h+var_A8], rax
0x18002162f  mov     rbx, rax
0x180021632  test    rax, rax
0x180021635  jnz     short loc_18002163E
0x180021637  mov     al, 1
0x180021639  jmp     loc_180021778
0x18002163e  mov     byte ptr [rbp+47h+arg_0], 1
0x180021642  jmp     short loc_180021648
0x180021644  mov     [rbp+47h+var_A8], rbx
0x180021648  test    sil, sil
0x18002164b  jnz     short loc_1800215D5
0x18002164d  jmp     short loc_1800215D1
0x18002164f  mov     rcx, rax
0x180021652  mov     al, [rbp+47h+var_9E]
0x180021655  cmp     al, 1
0x180021657  jnz     short loc_18002165F
0x180021659  add     rcx, 2
0x18002165d  jmp     short loc_180021667
0x18002165f  cmp     al, 2
0x180021661  jnz     short loc_180021667
0x180021663  add     rcx, 4
0x180021667  movzx   eax, word ptr [rdi+6]
0x18002166b  mov     dl, [rdi+8]
0x18002166e  mov     r8d, [rbp+47h+arg_28]
0x180021672  mov     [rbp+47h+var_80], ax
0x180021676  mov     [rbp+47h+var_7E], dl
0x180021679  mov     [rbp+47h+var_7C], r8d
0x18002167d  mov     [rbp+47h+var_78], r12w
0x180021682  mov     [rbp+47h+var_70], r9
0x180021686  mov     [rbp+47h+var_68], r13
0x18002168a  test    ax, ax
0x18002168d  jnz     short loc_180021697
0x18002168f  movzx   eax, r12w
0x180021693  add     rax, 2
0x180021697  cmp     dl, 1
0x18002169a  jnz     short loc_1800216A2
0x18002169c  add     rax, 2
0x1800216a0  jmp     short loc_1800216AB
0x1800216a2  cmp     dl, 2
0x1800216a5  jnz     short loc_1800216AB
0x1800216a7  add     rax, 4
0x1800216ab  mov     rdx, [rdi+28h]
0x1800216af  lea     rsi, [rax+rcx]
0x1800216b3  mov     r9, [rdi+20h]
0x1800216b7  mov     rcx, rdx
0x1800216ba  sub     rcx, r9
0x1800216bd  cmp     r9, rdx
0x1800216c0  sbb     rax, rax
0x1800216c3  and     rax, rcx
0x1800216c6  cmp     rax, rsi
0x1800216c9  jb      loc_180021776
0x1800216cf  sub     rdx, rsi
0x1800216d2  lea     rcx, [rsi+rbx]; Destination
0x1800216d6  sub     rdx, rbx; DestinationSize
0x1800216d9  sub     r9, rbx; SourceSize
0x1800216dc  mov     r8, rbx; Source
0x1800216df  call    cs:__imp_memmove_s
0x1800216e6  nop     dword ptr [rax+rax+00h]
0x1800216eb  add     [rdi+20h], rsi
0x1800216ef  xor     ebx, ebx
0x1800216f1  cmp     byte ptr [rbp+47h+arg_0], bl
0x1800216f4  jnz     short loc_180021709
0x1800216f6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800216fa  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800216fe  lea     rcx, [rbp+47h+var_A0]; this
0x180021702  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180021707  jmp     short loc_18002175C
0x180021709  mov     cl, [rbp+47h+var_9E]
0x18002170c  test    cl, cl
0x18002170e  jz      short loc_18002175C
0x180021710  mov     eax, [rbp+47h+Source]
0x180021713  lea     r8d, [rax+1]
0x180021717  cmp     eax, r8d
0x18002171a  jz      short loc_18002175C
0x18002171c  mov     [rbp+47h+Source], r8d
0x180021720  cmp     cl, 1
0x180021723  jnz     short loc_180021739
0x180021725  mov     r9d, 2
0x18002172b  mov     [rbp+47h+arg_0], r8w
0x180021730  mov     edx, r9d
0x180021733  lea     r8, [rbp+47h+arg_0]
0x180021737  jmp     short loc_18002174C
0x180021739  cmp     cl, 2
0x18002173c  jnz     short loc_18002175C
0x18002173e  mov     eax, 4
0x180021743  lea     r8, [rbp+47h+Source]; Source
0x180021747  mov     r9d, eax; SourceSize
0x18002174a  mov     edx, eax; DestinationSize
0x18002174c  mov     rcx, [rbp+47h+Buf2]; Destination
0x180021750  call    cs:__imp_memcpy_s
0x180021757  nop     dword ptr [rax+rax+00h]
0x18002175c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180021760  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180021764  lea     rcx, [rbp+47h+var_80]; this
0x180021768  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18002176d  mov     byte ptr [rdi+38h], 1
0x180021771  jmp     loc_180021637
0x180021776  xor     al, al
0x180021778  add     rsp, 0A8h
0x18002177f  pop     r15
0x180021781  pop     r14
0x180021783  pop     r13
0x180021785  pop     r12
0x180021787  pop     rdi
0x180021788  pop     rsi
0x180021789  pop     rbx
0x18002178a  pop     rbp
0x18002178b  retn
```

# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800081d0`
- end: `0x180008550`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008014`

## callees

- `0x18000567c`
- `0x1800079a8`
- `0x1800081d0`
- `0x18000b2fc`
- `0x1800184b6`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800084af`
- `msvcrt!memmove_s` at `0x1800084af`
- `msvcrt!memcpy_s` at `0x1800082db`
- `msvcrt!memcpy_s` at `0x180008374`
- `msvcrt!memcpy_s` at `0x18000851a`
- `msvcrt!memcpy_s` at `0x1800082db`
- `msvcrt!memcpy_s` at `0x180008374`
- `msvcrt!memcpy_s` at `0x18000851a`

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
0x1800081d0  push    rbp
0x1800081d2  push    rbx
0x1800081d3  push    rsi
0x1800081d4  push    rdi
0x1800081d5  push    r12
0x1800081d7  push    r13
0x1800081d9  push    r14
0x1800081db  push    r15
0x1800081dd  lea     rbp, [rsp-0Fh]
0x1800081e2  sub     rsp, 0A8h
0x1800081e9  mov     rbx, [rcx+18h]
0x1800081ed  mov     rdi, rcx
0x1800081f0  xor     ecx, ecx
0x1800081f2  mov     r13, r9
0x1800081f5  mov     r14, r8
0x1800081f8  mov     r15, rdx
0x1800081fb  test    rbx, rbx
0x1800081fe  jz      loc_18000853A
0x180008204  movzx   eax, word ptr [rdi+2]
0x180008208  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000820c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008210  add     rbx, 0Ah
0x180008214  mov     [rbp+47h+var_A0], ax
0x180008218  xorps   xmm0, xmm0
0x18000821b  mov     al, [rdi+4]
0x18000821e  mov     [rbp+47h+Source], ecx
0x180008221  mov     [rbp+47h+var_98], cx
0x180008225  mov     byte ptr [rbp+47h+arg_0], cl
0x180008228  lea     rcx, [rbp+47h+var_A0]; this
0x18000822c  mov     [rbp+47h+var_9E], al
0x18000822f  mov     [rbp+47h+var_A8], rbx
0x180008233  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180008238  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000823d  mov     r12, [rbp+47h+arg_20]
0x180008241  jmp     loc_18000838F
0x180008246  movzx   eax, [rbp+47h+var_98]
0x18000824a  cmp     r14, rax
0x18000824d  jnz     short loc_180008265
0x18000824f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180008253  mov     r8, r14; Size
0x180008256  mov     rcx, r15; Buf1
0x180008259  call    memcmp_0
0x18000825e  mov     ecx, eax
0x180008260  xor     r9d, r9d
0x180008263  jmp     short loc_18000826E
0x180008265  movzx   eax, [rbp+47h+var_98]
0x180008269  mov     ecx, r14d
0x18000826c  sub     ecx, eax
0x18000826e  test    ecx, ecx
0x180008270  js      loc_180008414
0x180008276  jz      loc_1800083D9
0x18000827c  mov     rbx, [rbp+47h+var_A8]
0x180008280  mov     [rbp+47h+var_A8], rbx
0x180008284  cmp     [rdi+10h], r9
0x180008288  jbe     short loc_1800082F3
0x18000828a  mov     rax, [rdi+20h]
0x18000828e  xor     edx, edx
0x180008290  sub     rax, [rdi+18h]
0x180008294  mov     rsi, rbx
0x180008297  div     qword ptr [rdi+10h]
0x18000829b  mov     edx, [rbp+47h+Source]
0x18000829e  cmp     rdx, rax
0x1800082a1  jbe     short loc_1800082E4
0x1800082a3  cmp     edx, eax
0x1800082a5  jz      short loc_1800082E4
0x1800082a7  mov     edx, eax
0x1800082a9  mov     [rbp+47h+Source], eax
0x1800082ac  mov     al, [rbp+47h+var_9E]
0x1800082af  cmp     al, 1
0x1800082b1  jnz     short loc_1800082C6
0x1800082b3  movzx   eax, dx
0x1800082b6  mov     [rbp+47h+var_B0], dx
0x1800082ba  mov     r9d, 2
0x1800082c0  lea     r8, [rbp+47h+var_B0]
0x1800082c4  jmp     short loc_1800082D4
0x1800082c6  cmp     al, 2
0x1800082c8  jnz     short loc_1800082E4
0x1800082ca  mov     r9d, 4; SourceSize
0x1800082d0  lea     r8, [rbp+47h+Source]; Source
0x1800082d4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800082d8  mov     rdx, r9; DestinationSize
0x1800082db  call    cs:__imp_memcpy_s
0x1800082e1  mov     edx, [rbp+47h+Source]
0x1800082e4  mov     ebx, edx
0x1800082e6  imul    rbx, [rdi+10h]
0x1800082eb  add     rbx, rsi
0x1800082ee  jmp     loc_18000837A
0x1800082f3  movzx   eax, word ptr [rdi+6]
0x1800082f7  xorps   xmm0, xmm0
0x1800082fa  mov     [rbp+47h+var_60], ax
0x1800082fe  mov     esi, r9d
0x180008301  mov     al, [rdi+8]
0x180008304  mov     [rbp+47h+var_5E], al
0x180008307  mov     eax, [rbp+47h+Source]
0x18000830a  mov     [rbp+47h+var_5C], r9d
0x18000830e  mov     [rbp+47h+var_58], r9w
0x180008313  movdqu  [rbp+47h+var_50], xmm0
0x180008318  test    eax, eax
0x18000831a  jz      short loc_18000833E
0x18000831c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008320  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008324  lea     rcx, [rbp+47h+var_60]; this
0x180008328  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000832d  test    al, al
0x18000832f  mov     eax, [rbp+47h+Source]
0x180008332  jz      short loc_18000833A
0x180008334  inc     esi
0x180008336  cmp     esi, eax
0x180008338  jb      short loc_18000831C
0x18000833a  mov     rbx, [rbp+47h+var_A8]
0x18000833e  cmp     eax, esi
0x180008340  jz      short loc_18000837A
0x180008342  mov     al, [rbp+47h+var_9E]
0x180008345  mov     [rbp+47h+Source], esi
0x180008348  cmp     al, 1
0x18000834a  jnz     short loc_180008360
0x18000834c  mov     eax, 2
0x180008351  mov     [rbp+47h+var_B0], si
0x180008355  mov     r9d, eax
0x180008358  lea     r8, [rbp+47h+var_B0]
0x18000835c  mov     edx, eax
0x18000835e  jmp     short loc_180008370
0x180008360  cmp     al, 2
0x180008362  jnz     short loc_18000837A
0x180008364  mov     edx, 4; DestinationSize
0x180008369  lea     r8, [rbp+47h+Source]; Source
0x18000836d  mov     r9d, edx; SourceSize
0x180008370  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008374  call    cs:__imp_memcpy_s
0x18000837a  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000837e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008382  lea     rcx, [rbp+47h+var_A0]; this
0x180008386  mov     [rbp+47h+var_A8], rbx
0x18000838a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000838f  xor     r9d, r9d
0x180008392  mov     sil, al
0x180008395  test    al, al
0x180008397  jnz     loc_180008246
0x18000839d  mov     rbx, [rbp+47h+var_A8]
0x1800083a1  mov     [rdi+20h], rbx
0x1800083a5  mov     rcx, r9
0x1800083a8  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1800083ac  jnz     loc_180008437
0x1800083b2  movzx   eax, [rbp+47h+var_A0]
0x1800083b6  mov     [rbp+47h+Source], 1
0x1800083bd  mov     [rbp+47h+var_98], r14w
0x1800083c2  mov     [rbp+47h+Buf2], r9
0x1800083c6  mov     [rbp+47h+Buf2+8], r15
0x1800083ca  test    ax, ax
0x1800083cd  jnz     short loc_18000841F
0x1800083cf  movzx   ecx, r14w
0x1800083d3  add     rcx, 2
0x1800083d7  jmp     short loc_180008422
0x1800083d9  mov     eax, [rbp+47h+arg_28]
0x1800083dc  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x1800083e0  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1800083e4  mov     r9, r13; void *
0x1800083e7  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1800083eb  mov     rcx, rdi; this
0x1800083ee  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x1800083f3  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800083f8  xor     r9d, r9d
0x1800083fb  mov     [rbp+47h+var_A8], rax
0x1800083ff  mov     rbx, rax
0x180008402  test    rax, rax
0x180008405  jnz     short loc_18000840E
0x180008407  mov     al, 1
0x180008409  jmp     loc_18000853C
0x18000840e  mov     byte ptr [rbp+47h+arg_0], 1
0x180008412  jmp     short loc_180008418
0x180008414  mov     [rbp+47h+var_A8], rbx
0x180008418  test    sil, sil
0x18000841b  jnz     short loc_1800083A5
0x18000841d  jmp     short loc_1800083A1
0x18000841f  mov     rcx, rax
0x180008422  mov     al, [rbp+47h+var_9E]
0x180008425  cmp     al, 1
0x180008427  jnz     short loc_18000842F
0x180008429  add     rcx, 2
0x18000842d  jmp     short loc_180008437
0x18000842f  cmp     al, 2
0x180008431  jnz     short loc_180008437
0x180008433  add     rcx, 4
0x180008437  movzx   eax, word ptr [rdi+6]
0x18000843b  mov     dl, [rdi+8]
0x18000843e  mov     r8d, [rbp+47h+arg_28]
0x180008442  mov     [rbp+47h+var_80], ax
0x180008446  mov     [rbp+47h+var_7E], dl
0x180008449  mov     [rbp+47h+var_7C], r8d
0x18000844d  mov     [rbp+47h+var_78], r12w
0x180008452  mov     [rbp+47h+var_70], r9
0x180008456  mov     [rbp+47h+var_68], r13
0x18000845a  test    ax, ax
0x18000845d  jnz     short loc_180008467
0x18000845f  movzx   eax, r12w
0x180008463  add     rax, 2
0x180008467  cmp     dl, 1
0x18000846a  jnz     short loc_180008472
0x18000846c  add     rax, 2
0x180008470  jmp     short loc_18000847B
0x180008472  cmp     dl, 2
0x180008475  jnz     short loc_18000847B
0x180008477  add     rax, 4
0x18000847b  mov     rdx, [rdi+28h]
0x18000847f  lea     rsi, [rax+rcx]
0x180008483  mov     r9, [rdi+20h]
0x180008487  mov     rcx, rdx
0x18000848a  sub     rcx, r9
0x18000848d  cmp     r9, rdx
0x180008490  sbb     rax, rax
0x180008493  and     rax, rcx
0x180008496  cmp     rax, rsi
0x180008499  jb      loc_18000853A
0x18000849f  sub     rdx, rsi
0x1800084a2  lea     rcx, [rsi+rbx]; Destination
0x1800084a6  sub     rdx, rbx; DestinationSize
0x1800084a9  sub     r9, rbx; SourceSize
0x1800084ac  mov     r8, rbx; Source
0x1800084af  call    cs:__imp_memmove_s
0x1800084b5  add     [rdi+20h], rsi
0x1800084b9  xor     ebx, ebx
0x1800084bb  cmp     byte ptr [rbp+47h+arg_0], bl
0x1800084be  jnz     short loc_1800084D3
0x1800084c0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800084c4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800084c8  lea     rcx, [rbp+47h+var_A0]; this
0x1800084cc  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800084d1  jmp     short loc_180008520
0x1800084d3  mov     cl, [rbp+47h+var_9E]
0x1800084d6  test    cl, cl
0x1800084d8  jz      short loc_180008520
0x1800084da  mov     eax, [rbp+47h+Source]
0x1800084dd  lea     r8d, [rax+1]
0x1800084e1  cmp     eax, r8d
0x1800084e4  jz      short loc_180008520
0x1800084e6  mov     [rbp+47h+Source], r8d
0x1800084ea  cmp     cl, 1
0x1800084ed  jnz     short loc_180008503
0x1800084ef  mov     r9d, 2
0x1800084f5  mov     [rbp+47h+arg_0], r8w
0x1800084fa  mov     edx, r9d
0x1800084fd  lea     r8, [rbp+47h+arg_0]
0x180008501  jmp     short loc_180008516
0x180008503  cmp     cl, 2
0x180008506  jnz     short loc_180008520
0x180008508  mov     eax, 4
0x18000850d  lea     r8, [rbp+47h+Source]; Source
0x180008511  mov     r9d, eax; SourceSize
0x180008514  mov     edx, eax; DestinationSize
0x180008516  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000851a  call    cs:__imp_memcpy_s
0x180008520  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008524  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008528  lea     rcx, [rbp+47h+var_80]; this
0x18000852c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180008531  mov     byte ptr [rdi+38h], 1
0x180008535  jmp     loc_180008407
0x18000853a  xor     al, al
0x18000853c  add     rsp, 0A8h
0x180008543  pop     r15
0x180008545  pop     r14
0x180008547  pop     r13
0x180008549  pop     r12
0x18000854b  pop     rdi
0x18000854c  pop     rsi
0x18000854d  pop     rbx
0x18000854e  pop     rbp
0x18000854f  retn
```

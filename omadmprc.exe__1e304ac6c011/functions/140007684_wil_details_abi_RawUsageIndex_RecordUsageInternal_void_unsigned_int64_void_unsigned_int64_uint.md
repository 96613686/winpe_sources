# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140007684`
- end: `0x140007a1d`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `921`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007548`

## callees

- `0x140004f44`
- `0x140006e2c`
- `0x140007684`
- `0x140009c18`
- `0x140015666`

## import_xrefs

- `msvcrt!memmove_s` at `0x14000796f`
- `msvcrt!memmove_s` at `0x14000796f`
- `msvcrt!memcpy_s` at `0x14000778f`
- `msvcrt!memcpy_s` at `0x14000782e`
- `msvcrt!memcpy_s` at `0x1400079e0`
- `msvcrt!memcpy_s` at `0x14000778f`
- `msvcrt!memcpy_s` at `0x14000782e`
- `msvcrt!memcpy_s` at `0x1400079e0`

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
0x140007684  push    rbp
0x140007686  push    rbx
0x140007687  push    rsi
0x140007688  push    rdi
0x140007689  push    r12
0x14000768b  push    r13
0x14000768d  push    r14
0x14000768f  push    r15
0x140007691  lea     rbp, [rsp-0Fh]
0x140007696  sub     rsp, 0A8h
0x14000769d  mov     rbx, [rcx+18h]
0x1400076a1  mov     rdi, rcx
0x1400076a4  xor     ecx, ecx
0x1400076a6  mov     r13, r9
0x1400076a9  mov     r14, r8
0x1400076ac  mov     r15, rdx
0x1400076af  test    rbx, rbx
0x1400076b2  jz      loc_140007A06
0x1400076b8  movzx   eax, word ptr [rdi+2]
0x1400076bc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1400076c0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400076c4  add     rbx, 0Ah
0x1400076c8  mov     [rbp+47h+var_A0], ax
0x1400076cc  xorps   xmm0, xmm0
0x1400076cf  mov     al, [rdi+4]
0x1400076d2  mov     [rbp+47h+Source], ecx
0x1400076d5  mov     [rbp+47h+var_98], cx
0x1400076d9  mov     byte ptr [rbp+47h+arg_0], cl
0x1400076dc  lea     rcx, [rbp+47h+var_A0]; this
0x1400076e0  mov     [rbp+47h+var_9E], al
0x1400076e3  mov     [rbp+47h+var_A8], rbx
0x1400076e7  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1400076ec  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400076f1  mov     r12, [rbp+47h+arg_20]
0x1400076f5  jmp     loc_14000784F
0x1400076fa  movzx   eax, [rbp+47h+var_98]
0x1400076fe  cmp     r14, rax
0x140007701  jnz     short loc_140007719
0x140007703  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x140007707  mov     r8, r14; Size
0x14000770a  mov     rcx, r15; Buf1
0x14000770d  call    memcmp_0
0x140007712  mov     ecx, eax
0x140007714  xor     r9d, r9d
0x140007717  jmp     short loc_140007722
0x140007719  movzx   eax, [rbp+47h+var_98]
0x14000771d  mov     ecx, r14d
0x140007720  sub     ecx, eax
0x140007722  test    ecx, ecx
0x140007724  js      loc_1400078D4
0x14000772a  jz      loc_140007899
0x140007730  mov     rbx, [rbp+47h+var_A8]
0x140007734  mov     [rbp+47h+var_A8], rbx
0x140007738  cmp     [rdi+10h], r9
0x14000773c  jbe     short loc_1400077AD
0x14000773e  mov     rax, [rdi+20h]
0x140007742  xor     edx, edx
0x140007744  sub     rax, [rdi+18h]
0x140007748  mov     rsi, rbx
0x14000774b  div     qword ptr [rdi+10h]
0x14000774f  mov     edx, [rbp+47h+Source]
0x140007752  cmp     rdx, rax
0x140007755  jbe     short loc_14000779E
0x140007757  cmp     edx, eax
0x140007759  jz      short loc_14000779E
0x14000775b  mov     edx, eax
0x14000775d  mov     [rbp+47h+Source], eax
0x140007760  mov     al, [rbp+47h+var_9E]
0x140007763  cmp     al, 1
0x140007765  jnz     short loc_14000777A
0x140007767  movzx   eax, dx
0x14000776a  mov     [rbp+47h+var_B0], dx
0x14000776e  mov     r9d, 2
0x140007774  lea     r8, [rbp+47h+var_B0]
0x140007778  jmp     short loc_140007788
0x14000777a  cmp     al, 2
0x14000777c  jnz     short loc_14000779E
0x14000777e  mov     r9d, 4; SourceSize
0x140007784  lea     r8, [rbp+47h+Source]; Source
0x140007788  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000778c  mov     rdx, r9; DestinationSize
0x14000778f  call    cs:__imp_memcpy_s
0x140007796  nop     dword ptr [rax+rax+00h]
0x14000779b  mov     edx, [rbp+47h+Source]
0x14000779e  mov     ebx, edx
0x1400077a0  imul    rbx, [rdi+10h]
0x1400077a5  add     rbx, rsi
0x1400077a8  jmp     loc_14000783A
0x1400077ad  movzx   eax, word ptr [rdi+6]
0x1400077b1  xorps   xmm0, xmm0
0x1400077b4  mov     [rbp+47h+var_60], ax
0x1400077b8  mov     esi, r9d
0x1400077bb  mov     al, [rdi+8]
0x1400077be  mov     [rbp+47h+var_5E], al
0x1400077c1  mov     eax, [rbp+47h+Source]
0x1400077c4  mov     [rbp+47h+var_5C], r9d
0x1400077c8  mov     [rbp+47h+var_58], r9w
0x1400077cd  movdqu  [rbp+47h+var_50], xmm0
0x1400077d2  test    eax, eax
0x1400077d4  jz      short loc_1400077F8
0x1400077d6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400077da  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1400077de  lea     rcx, [rbp+47h+var_60]; this
0x1400077e2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400077e7  test    al, al
0x1400077e9  mov     eax, [rbp+47h+Source]
0x1400077ec  jz      short loc_1400077F4
0x1400077ee  inc     esi
0x1400077f0  cmp     esi, eax
0x1400077f2  jb      short loc_1400077D6
0x1400077f4  mov     rbx, [rbp+47h+var_A8]
0x1400077f8  cmp     eax, esi
0x1400077fa  jz      short loc_14000783A
0x1400077fc  mov     al, [rbp+47h+var_9E]
0x1400077ff  mov     [rbp+47h+Source], esi
0x140007802  cmp     al, 1
0x140007804  jnz     short loc_14000781A
0x140007806  mov     eax, 2
0x14000780b  mov     [rbp+47h+var_B0], si
0x14000780f  mov     r9d, eax
0x140007812  lea     r8, [rbp+47h+var_B0]
0x140007816  mov     edx, eax
0x140007818  jmp     short loc_14000782A
0x14000781a  cmp     al, 2
0x14000781c  jnz     short loc_14000783A
0x14000781e  mov     edx, 4; DestinationSize
0x140007823  lea     r8, [rbp+47h+Source]; Source
0x140007827  mov     r9d, edx; SourceSize
0x14000782a  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000782e  call    cs:__imp_memcpy_s
0x140007835  nop     dword ptr [rax+rax+00h]
0x14000783a  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000783e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140007842  lea     rcx, [rbp+47h+var_A0]; this
0x140007846  mov     [rbp+47h+var_A8], rbx
0x14000784a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000784f  xor     r9d, r9d
0x140007852  mov     sil, al
0x140007855  test    al, al
0x140007857  jnz     loc_1400076FA
0x14000785d  mov     rbx, [rbp+47h+var_A8]
0x140007861  mov     [rdi+20h], rbx
0x140007865  mov     rcx, r9
0x140007868  cmp     byte ptr [rbp+47h+arg_0], r9b
0x14000786c  jnz     loc_1400078F7
0x140007872  movzx   eax, [rbp+47h+var_A0]
0x140007876  mov     [rbp+47h+Source], 1
0x14000787d  mov     [rbp+47h+var_98], r14w
0x140007882  mov     [rbp+47h+Buf2], r9
0x140007886  mov     [rbp+47h+Buf2+8], r15
0x14000788a  test    ax, ax
0x14000788d  jnz     short loc_1400078DF
0x14000788f  movzx   ecx, r14w
0x140007893  add     rcx, 2
0x140007897  jmp     short loc_1400078E2
0x140007899  mov     eax, [rbp+47h+arg_28]
0x14000789c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x1400078a0  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1400078a4  mov     r9, r13; void *
0x1400078a7  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1400078ab  mov     rcx, rdi; this
0x1400078ae  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x1400078b3  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1400078b8  xor     r9d, r9d
0x1400078bb  mov     [rbp+47h+var_A8], rax
0x1400078bf  mov     rbx, rax
0x1400078c2  test    rax, rax
0x1400078c5  jnz     short loc_1400078CE
0x1400078c7  mov     al, 1
0x1400078c9  jmp     loc_140007A08
0x1400078ce  mov     byte ptr [rbp+47h+arg_0], 1
0x1400078d2  jmp     short loc_1400078D8
0x1400078d4  mov     [rbp+47h+var_A8], rbx
0x1400078d8  test    sil, sil
0x1400078db  jnz     short loc_140007865
0x1400078dd  jmp     short loc_140007861
0x1400078df  mov     rcx, rax
0x1400078e2  mov     al, [rbp+47h+var_9E]
0x1400078e5  cmp     al, 1
0x1400078e7  jnz     short loc_1400078EF
0x1400078e9  add     rcx, 2
0x1400078ed  jmp     short loc_1400078F7
0x1400078ef  cmp     al, 2
0x1400078f1  jnz     short loc_1400078F7
0x1400078f3  add     rcx, 4
0x1400078f7  movzx   eax, word ptr [rdi+6]
0x1400078fb  mov     dl, [rdi+8]
0x1400078fe  mov     r8d, [rbp+47h+arg_28]
0x140007902  mov     [rbp+47h+var_80], ax
0x140007906  mov     [rbp+47h+var_7E], dl
0x140007909  mov     [rbp+47h+var_7C], r8d
0x14000790d  mov     [rbp+47h+var_78], r12w
0x140007912  mov     [rbp+47h+var_70], r9
0x140007916  mov     [rbp+47h+var_68], r13
0x14000791a  test    ax, ax
0x14000791d  jnz     short loc_140007927
0x14000791f  movzx   eax, r12w
0x140007923  add     rax, 2
0x140007927  cmp     dl, 1
0x14000792a  jnz     short loc_140007932
0x14000792c  add     rax, 2
0x140007930  jmp     short loc_14000793B
0x140007932  cmp     dl, 2
0x140007935  jnz     short loc_14000793B
0x140007937  add     rax, 4
0x14000793b  mov     rdx, [rdi+28h]
0x14000793f  lea     rsi, [rax+rcx]
0x140007943  mov     r9, [rdi+20h]
0x140007947  mov     rcx, rdx
0x14000794a  sub     rcx, r9
0x14000794d  cmp     r9, rdx
0x140007950  sbb     rax, rax
0x140007953  and     rax, rcx
0x140007956  cmp     rax, rsi
0x140007959  jb      loc_140007A06
0x14000795f  sub     rdx, rsi
0x140007962  lea     rcx, [rsi+rbx]; Destination
0x140007966  sub     rdx, rbx; DestinationSize
0x140007969  sub     r9, rbx; SourceSize
0x14000796c  mov     r8, rbx; Source
0x14000796f  call    cs:__imp_memmove_s
0x140007976  nop     dword ptr [rax+rax+00h]
0x14000797b  add     [rdi+20h], rsi
0x14000797f  xor     ebx, ebx
0x140007981  cmp     byte ptr [rbp+47h+arg_0], bl
0x140007984  jnz     short loc_140007999
0x140007986  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000798a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000798e  lea     rcx, [rbp+47h+var_A0]; this
0x140007992  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140007997  jmp     short loc_1400079EC
0x140007999  mov     cl, [rbp+47h+var_9E]
0x14000799c  test    cl, cl
0x14000799e  jz      short loc_1400079EC
0x1400079a0  mov     eax, [rbp+47h+Source]
0x1400079a3  lea     r8d, [rax+1]
0x1400079a7  cmp     eax, r8d
0x1400079aa  jz      short loc_1400079EC
0x1400079ac  mov     [rbp+47h+Source], r8d
0x1400079b0  cmp     cl, 1
0x1400079b3  jnz     short loc_1400079C9
0x1400079b5  mov     r9d, 2
0x1400079bb  mov     [rbp+47h+arg_0], r8w
0x1400079c0  mov     edx, r9d
0x1400079c3  lea     r8, [rbp+47h+arg_0]
0x1400079c7  jmp     short loc_1400079DC
0x1400079c9  cmp     cl, 2
0x1400079cc  jnz     short loc_1400079EC
0x1400079ce  mov     eax, 4
0x1400079d3  lea     r8, [rbp+47h+Source]; Source
0x1400079d7  mov     r9d, eax; SourceSize
0x1400079da  mov     edx, eax; DestinationSize
0x1400079dc  mov     rcx, [rbp+47h+Buf2]; Destination
0x1400079e0  call    cs:__imp_memcpy_s
0x1400079e7  nop     dword ptr [rax+rax+00h]
0x1400079ec  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400079f0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1400079f4  lea     rcx, [rbp+47h+var_80]; this
0x1400079f8  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1400079fd  mov     byte ptr [rdi+38h], 1
0x140007a01  jmp     loc_1400078C7
0x140007a06  xor     al, al
0x140007a08  add     rsp, 0A8h
0x140007a0f  pop     r15
0x140007a11  pop     r14
0x140007a13  pop     r13
0x140007a15  pop     r12
0x140007a17  pop     rdi
0x140007a18  pop     rsi
0x140007a19  pop     rbx
0x140007a1a  pop     rbp
0x140007a1b  retn
```

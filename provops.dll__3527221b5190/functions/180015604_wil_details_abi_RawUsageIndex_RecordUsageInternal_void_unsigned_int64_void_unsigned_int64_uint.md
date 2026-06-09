# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180015604`
- end: `0x180015984`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015448`

## callees

- `0x18001264c`
- `0x180014e38`
- `0x180015604`
- `0x18001bb3c`
- `0x180033e76`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001570f`
- `msvcrt!memcpy_s` at `0x1800157a8`
- `msvcrt!memcpy_s` at `0x18001594e`
- `msvcrt!memcpy_s` at `0x18001570f`
- `msvcrt!memcpy_s` at `0x1800157a8`
- `msvcrt!memcpy_s` at `0x18001594e`
- `msvcrt!memmove_s` at `0x1800158e3`
- `msvcrt!memmove_s` at `0x1800158e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180015604  push    rbp
0x180015606  push    rbx
0x180015607  push    rsi
0x180015608  push    rdi
0x180015609  push    r12
0x18001560b  push    r13
0x18001560d  push    r14
0x18001560f  push    r15
0x180015611  lea     rbp, [rsp-0Fh]
0x180015616  sub     rsp, 0A8h
0x18001561d  mov     rbx, [rcx+18h]
0x180015621  mov     rdi, rcx
0x180015624  xor     ecx, ecx
0x180015626  mov     r13, r9
0x180015629  mov     r14, r8
0x18001562c  mov     r15, rdx
0x18001562f  test    rbx, rbx
0x180015632  jz      loc_18001596E
0x180015638  movzx   eax, word ptr [rdi+2]
0x18001563c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180015640  mov     r8, [rdi+20h]; unsigned __int8 *
0x180015644  add     rbx, 0Ah
0x180015648  mov     [rbp+47h+var_A0], ax
0x18001564c  xorps   xmm0, xmm0
0x18001564f  mov     al, [rdi+4]
0x180015652  mov     [rbp+47h+Source], ecx
0x180015655  mov     [rbp+47h+var_98], cx
0x180015659  mov     byte ptr [rbp+47h+arg_0], cl
0x18001565c  lea     rcx, [rbp+47h+var_A0]; this
0x180015660  mov     [rbp+47h+var_9E], al
0x180015663  mov     [rbp+47h+var_A8], rbx
0x180015667  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18001566c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180015671  mov     r12, [rbp+47h+arg_20]
0x180015675  jmp     loc_1800157C3
0x18001567a  movzx   eax, [rbp+47h+var_98]
0x18001567e  cmp     r14, rax
0x180015681  jnz     short loc_180015699
0x180015683  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180015687  mov     r8, r14; Size
0x18001568a  mov     rcx, r15; Buf1
0x18001568d  call    memcmp_0
0x180015692  mov     ecx, eax
0x180015694  xor     r9d, r9d
0x180015697  jmp     short loc_1800156A2
0x180015699  movzx   eax, [rbp+47h+var_98]
0x18001569d  mov     ecx, r14d
0x1800156a0  sub     ecx, eax
0x1800156a2  test    ecx, ecx
0x1800156a4  js      loc_180015848
0x1800156aa  jz      loc_18001580D
0x1800156b0  mov     rbx, [rbp+47h+var_A8]
0x1800156b4  mov     [rbp+47h+var_A8], rbx
0x1800156b8  cmp     [rdi+10h], r9
0x1800156bc  jbe     short loc_180015727
0x1800156be  mov     rax, [rdi+20h]
0x1800156c2  xor     edx, edx
0x1800156c4  sub     rax, [rdi+18h]
0x1800156c8  mov     rsi, rbx
0x1800156cb  div     qword ptr [rdi+10h]
0x1800156cf  mov     edx, [rbp+47h+Source]
0x1800156d2  cmp     rdx, rax
0x1800156d5  jbe     short loc_180015718
0x1800156d7  cmp     edx, eax
0x1800156d9  jz      short loc_180015718
0x1800156db  mov     edx, eax
0x1800156dd  mov     [rbp+47h+Source], eax
0x1800156e0  mov     al, [rbp+47h+var_9E]
0x1800156e3  cmp     al, 1
0x1800156e5  jnz     short loc_1800156FA
0x1800156e7  movzx   eax, dx
0x1800156ea  mov     [rbp+47h+var_B0], dx
0x1800156ee  mov     r9d, 2
0x1800156f4  lea     r8, [rbp+47h+var_B0]
0x1800156f8  jmp     short loc_180015708
0x1800156fa  cmp     al, 2
0x1800156fc  jnz     short loc_180015718
0x1800156fe  mov     r9d, 4; SourceSize
0x180015704  lea     r8, [rbp+47h+Source]; Source
0x180015708  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001570c  mov     rdx, r9; DestinationSize
0x18001570f  call    cs:__imp_memcpy_s
0x180015715  mov     edx, [rbp+47h+Source]
0x180015718  mov     ebx, edx
0x18001571a  imul    rbx, [rdi+10h]
0x18001571f  add     rbx, rsi
0x180015722  jmp     loc_1800157AE
0x180015727  movzx   eax, word ptr [rdi+6]
0x18001572b  xorps   xmm0, xmm0
0x18001572e  mov     [rbp+47h+var_60], ax
0x180015732  mov     esi, r9d
0x180015735  mov     al, [rdi+8]
0x180015738  mov     [rbp+47h+var_5E], al
0x18001573b  mov     eax, [rbp+47h+Source]
0x18001573e  mov     [rbp+47h+var_5C], r9d
0x180015742  mov     [rbp+47h+var_58], r9w
0x180015747  movdqu  [rbp+47h+var_50], xmm0
0x18001574c  test    eax, eax
0x18001574e  jz      short loc_180015772
0x180015750  mov     r8, [rdi+20h]; unsigned __int8 *
0x180015754  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180015758  lea     rcx, [rbp+47h+var_60]; this
0x18001575c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180015761  test    al, al
0x180015763  mov     eax, [rbp+47h+Source]
0x180015766  jz      short loc_18001576E
0x180015768  inc     esi
0x18001576a  cmp     esi, eax
0x18001576c  jb      short loc_180015750
0x18001576e  mov     rbx, [rbp+47h+var_A8]
0x180015772  cmp     eax, esi
0x180015774  jz      short loc_1800157AE
0x180015776  mov     al, [rbp+47h+var_9E]
0x180015779  mov     [rbp+47h+Source], esi
0x18001577c  cmp     al, 1
0x18001577e  jnz     short loc_180015794
0x180015780  mov     eax, 2
0x180015785  mov     [rbp+47h+var_B0], si
0x180015789  mov     r9d, eax
0x18001578c  lea     r8, [rbp+47h+var_B0]
0x180015790  mov     edx, eax
0x180015792  jmp     short loc_1800157A4
0x180015794  cmp     al, 2
0x180015796  jnz     short loc_1800157AE
0x180015798  mov     edx, 4; DestinationSize
0x18001579d  lea     r8, [rbp+47h+Source]; Source
0x1800157a1  mov     r9d, edx; SourceSize
0x1800157a4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800157a8  call    cs:__imp_memcpy_s
0x1800157ae  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800157b2  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800157b6  lea     rcx, [rbp+47h+var_A0]; this
0x1800157ba  mov     [rbp+47h+var_A8], rbx
0x1800157be  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800157c3  xor     r9d, r9d
0x1800157c6  mov     sil, al
0x1800157c9  test    al, al
0x1800157cb  jnz     loc_18001567A
0x1800157d1  mov     rbx, [rbp+47h+var_A8]
0x1800157d5  mov     [rdi+20h], rbx
0x1800157d9  mov     rcx, r9
0x1800157dc  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1800157e0  jnz     loc_18001586B
0x1800157e6  movzx   eax, [rbp+47h+var_A0]
0x1800157ea  mov     [rbp+47h+Source], 1
0x1800157f1  mov     [rbp+47h+var_98], r14w
0x1800157f6  mov     [rbp+47h+Buf2], r9
0x1800157fa  mov     [rbp+47h+Buf2+8], r15
0x1800157fe  test    ax, ax
0x180015801  jnz     short loc_180015853
0x180015803  movzx   ecx, r14w
0x180015807  add     rcx, 2
0x18001580b  jmp     short loc_180015856
0x18001580d  mov     eax, [rbp+47h+arg_28]
0x180015810  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180015814  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180015818  mov     r9, r13; void *
0x18001581b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18001581f  mov     rcx, rdi; this
0x180015822  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180015827  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001582c  xor     r9d, r9d
0x18001582f  mov     [rbp+47h+var_A8], rax
0x180015833  mov     rbx, rax
0x180015836  test    rax, rax
0x180015839  jnz     short loc_180015842
0x18001583b  mov     al, 1
0x18001583d  jmp     loc_180015970
0x180015842  mov     byte ptr [rbp+47h+arg_0], 1
0x180015846  jmp     short loc_18001584C
0x180015848  mov     [rbp+47h+var_A8], rbx
0x18001584c  test    sil, sil
0x18001584f  jnz     short loc_1800157D9
0x180015851  jmp     short loc_1800157D5
0x180015853  mov     rcx, rax
0x180015856  mov     al, [rbp+47h+var_9E]
0x180015859  cmp     al, 1
0x18001585b  jnz     short loc_180015863
0x18001585d  add     rcx, 2
0x180015861  jmp     short loc_18001586B
0x180015863  cmp     al, 2
0x180015865  jnz     short loc_18001586B
0x180015867  add     rcx, 4
0x18001586b  movzx   eax, word ptr [rdi+6]
0x18001586f  mov     dl, [rdi+8]
0x180015872  mov     r8d, [rbp+47h+arg_28]
0x180015876  mov     [rbp+47h+var_80], ax
0x18001587a  mov     [rbp+47h+var_7E], dl
0x18001587d  mov     [rbp+47h+var_7C], r8d
0x180015881  mov     [rbp+47h+var_78], r12w
0x180015886  mov     [rbp+47h+var_70], r9
0x18001588a  mov     [rbp+47h+var_68], r13
0x18001588e  test    ax, ax
0x180015891  jnz     short loc_18001589B
0x180015893  movzx   eax, r12w
0x180015897  add     rax, 2
0x18001589b  cmp     dl, 1
0x18001589e  jnz     short loc_1800158A6
0x1800158a0  add     rax, 2
0x1800158a4  jmp     short loc_1800158AF
0x1800158a6  cmp     dl, 2
0x1800158a9  jnz     short loc_1800158AF
0x1800158ab  add     rax, 4
0x1800158af  mov     rdx, [rdi+28h]
0x1800158b3  lea     rsi, [rax+rcx]
0x1800158b7  mov     r9, [rdi+20h]
0x1800158bb  mov     rcx, rdx
0x1800158be  sub     rcx, r9
0x1800158c1  cmp     r9, rdx
0x1800158c4  sbb     rax, rax
0x1800158c7  and     rax, rcx
0x1800158ca  cmp     rax, rsi
0x1800158cd  jb      loc_18001596E
0x1800158d3  sub     rdx, rsi
0x1800158d6  lea     rcx, [rsi+rbx]; Destination
0x1800158da  sub     rdx, rbx; DestinationSize
0x1800158dd  sub     r9, rbx; SourceSize
0x1800158e0  mov     r8, rbx; Source
0x1800158e3  call    cs:__imp_memmove_s
0x1800158e9  add     [rdi+20h], rsi
0x1800158ed  xor     ebx, ebx
0x1800158ef  cmp     byte ptr [rbp+47h+arg_0], bl
0x1800158f2  jnz     short loc_180015907
0x1800158f4  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800158f8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800158fc  lea     rcx, [rbp+47h+var_A0]; this
0x180015900  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180015905  jmp     short loc_180015954
0x180015907  mov     cl, [rbp+47h+var_9E]
0x18001590a  test    cl, cl
0x18001590c  jz      short loc_180015954
0x18001590e  mov     eax, [rbp+47h+Source]
0x180015911  lea     r8d, [rax+1]
0x180015915  cmp     eax, r8d
0x180015918  jz      short loc_180015954
0x18001591a  mov     [rbp+47h+Source], r8d
0x18001591e  cmp     cl, 1
0x180015921  jnz     short loc_180015937
0x180015923  mov     r9d, 2
0x180015929  mov     [rbp+47h+arg_0], r8w
0x18001592e  mov     edx, r9d
0x180015931  lea     r8, [rbp+47h+arg_0]
0x180015935  jmp     short loc_18001594A
0x180015937  cmp     cl, 2
0x18001593a  jnz     short loc_180015954
0x18001593c  mov     eax, 4
0x180015941  lea     r8, [rbp+47h+Source]; Source
0x180015945  mov     r9d, eax; SourceSize
0x180015948  mov     edx, eax; DestinationSize
0x18001594a  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001594e  call    cs:__imp_memcpy_s
0x180015954  mov     r8, [rdi+20h]; unsigned __int8 *
0x180015958  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001595c  lea     rcx, [rbp+47h+var_80]; this
0x180015960  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180015965  mov     byte ptr [rdi+38h], 1
0x180015969  jmp     loc_18001583B
0x18001596e  xor     al, al
0x180015970  add     rsp, 0A8h
0x180015977  pop     r15
0x180015979  pop     r14
0x18001597b  pop     r13
0x18001597d  pop     r12
0x18001597f  pop     rdi
0x180015980  pop     rsi
0x180015981  pop     rbx
0x180015982  pop     rbp
0x180015983  retn
```

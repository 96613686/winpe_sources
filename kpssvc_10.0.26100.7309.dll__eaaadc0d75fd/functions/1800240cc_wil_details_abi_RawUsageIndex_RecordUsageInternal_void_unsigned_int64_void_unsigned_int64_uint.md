# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800240cc`
- end: `0x18002447d`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `945`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, size_t, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180023f54`

## callees

- `0x18001d2fc`
- `0x180023864`
- `0x1800240cc`
- `0x180026278`
- `0x180030ff6`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800243be`
- `msvcrt!memmove_s` at `0x1800243be`
- `msvcrt!memcpy_s` at `0x1800241de`
- `msvcrt!memcpy_s` at `0x18002427d`
- `msvcrt!memcpy_s` at `0x180024433`
- `msvcrt!memcpy_s` at `0x1800241de`
- `msvcrt!memcpy_s` at `0x18002427d`
- `msvcrt!memcpy_s` at `0x180024433`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        size_t a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v11; // r8
  unsigned __int8 *v12; // rdi
  char v13; // al
  bool v14; // al
  size_t v15; // r12
  int v16; // ecx
  unsigned __int64 v17; // rax
  unsigned int v18; // edx
  rsize_t v19; // r9
  unsigned int *p_Source; // r8
  unsigned int v21; // esi
  unsigned int v22; // eax
  bool v23; // zf
  rsize_t v24; // r9
  unsigned int *v25; // r8
  rsize_t v26; // rdx
  unsigned __int8 *v27; // r8
  bool v28; // si
  __int64 v29; // rcx
  __int64 v31; // rax
  char v32; // dl
  unsigned __int64 v33; // rdx
  __int64 v34; // rsi
  unsigned __int64 v35; // r9
  unsigned __int8 *v36; // r8
  __int16 v37; // r8
  rsize_t v38; // r9
  rsize_t v39; // rdx
  unsigned int *v40; // r8
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int16 v42; // [rsp+40h] [rbp-41h] BYREF
  char v43; // [rsp+42h] [rbp-3Fh]
  unsigned int Source; // [rsp+44h] [rbp-3Dh] BYREF
  unsigned __int16 v45; // [rsp+48h] [rbp-39h]
  void *Buf2[2]; // [rsp+50h] [rbp-31h]
  __int16 v47; // [rsp+60h] [rbp-21h] BYREF
  __int16 v48; // [rsp+64h] [rbp-1Dh] BYREF
  __int16 v49; // [rsp+68h] [rbp-19h] BYREF
  char v50; // [rsp+6Ah] [rbp-17h]
  unsigned int v51; // [rsp+6Ch] [rbp-15h]
  __int16 v52; // [rsp+70h] [rbp-11h]
  __int64 v53; // [rsp+78h] [rbp-9h]
  void *v54; // [rsp+80h] [rbp-1h]
  __int16 v55; // [rsp+88h] [rbp+7h] BYREF
  char v56; // [rsp+8Ah] [rbp+9h]
  int v57; // [rsp+8Ch] [rbp+Bh]
  __int16 v58; // [rsp+90h] [rbp+Fh]
  __int128 v59; // [rsp+98h] [rbp+17h]
  __int16 v60; // [rsp+D8h] [rbp+57h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v11 = (unsigned __int8 *)*((_QWORD *)this + 4);
  v12 = (unsigned __int8 *)(v6 + 10);
  v42 = *((_WORD *)this + 1);
  v13 = *((_BYTE *)this + 4);
  Source = 0;
  v45 = 0;
  LOBYTE(v60) = 0;
  v43 = v13;
  InsertionPointOrIncrement = v12;
  *(_OWORD *)Buf2 = 0;
  v14 = wil::details_abi::UsageIndexProperty::Read(
          (wil::details_abi::UsageIndexProperty *)&v42,
          &InsertionPointOrIncrement,
          v11);
  v15 = a5;
  while ( 1 )
  {
    v28 = v14;
    if ( !v14 )
    {
      v12 = InsertionPointOrIncrement;
      goto LABEL_30;
    }
    v16 = Size == v45 ? memcmp_0(Buf1, Buf2[1], Size) : Size - v45;
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v42,
                                    InsertionPointOrIncrement,
                                    a4,
                                    v15,
                                    a6);
      v12 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        LOBYTE(v60) = 1;
        goto LABEL_38;
      }
      return 1;
    }
    v12 = InsertionPointOrIncrement;
    if ( *((_QWORD *)this + 2) )
    {
      v17 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
      v18 = Source;
      if ( Source > v17 && Source != (_DWORD)v17 )
      {
        v18 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
        Source = v18;
        if ( v43 == 1 )
        {
          v47 = v17;
          v19 = 2;
          p_Source = (unsigned int *)&v47;
          goto LABEL_15;
        }
        if ( v43 == 2 )
        {
          v19 = 4;
          p_Source = &Source;
LABEL_15:
          memcpy_s(Buf2[0], v19, p_Source, v19);
          v18 = Source;
        }
      }
      v12 += *((_QWORD *)this + 2) * v18;
      goto LABEL_27;
    }
    v55 = *((_WORD *)this + 3);
    v21 = 0;
    v56 = *((_BYTE *)this + 8);
    v22 = Source;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    if ( Source )
    {
      do
      {
        v23 = !wil::details_abi::UsageIndexProperty::Read(
                 (wil::details_abi::UsageIndexProperty *)&v55,
                 &InsertionPointOrIncrement,
                 *((unsigned __int8 **)this + 4));
        v22 = Source;
        if ( v23 )
          break;
        ++v21;
      }
      while ( v21 < Source );
      v12 = InsertionPointOrIncrement;
    }
    if ( v22 != v21 )
    {
      Source = v21;
      if ( v43 == 1 )
      {
        v48 = v21;
        v24 = 2;
        v25 = (unsigned int *)&v48;
        v26 = 2;
      }
      else
      {
        if ( v43 != 2 )
          goto LABEL_27;
        v26 = 4;
        v25 = &Source;
        v24 = 4;
      }
      memcpy_s(Buf2[0], v26, v25, v24);
    }
LABEL_27:
    v27 = (unsigned __int8 *)*((_QWORD *)this + 4);
    InsertionPointOrIncrement = v12;
    v14 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v42,
            &InsertionPointOrIncrement,
            v27);
  }
  InsertionPointOrIncrement = v12;
LABEL_38:
  if ( !v28 )
LABEL_30:
    *((_QWORD *)this + 4) = v12;
  v29 = 0;
  if ( !(_BYTE)v60 )
  {
    Source = 1;
    v45 = Size;
    Buf2[0] = 0;
    Buf2[1] = Buf1;
    if ( v42 )
      v29 = v42;
    else
      v29 = (unsigned __int16)Size + 2LL;
    if ( v43 == 1 )
    {
      v29 += 2;
    }
    else if ( v43 == 2 )
    {
      v29 += 4;
    }
  }
  v31 = *((unsigned __int16 *)this + 3);
  v32 = *((_BYTE *)this + 8);
  v49 = v31;
  v50 = v32;
  v51 = a6;
  v52 = v15;
  v53 = 0;
  v54 = a4;
  if ( !(_WORD)v31 )
    v31 = (unsigned __int16)v15 + 2LL;
  if ( v32 == 1 )
  {
    v31 += 2;
  }
  else if ( v32 == 2 )
  {
    v31 += 4;
  }
  v33 = *((_QWORD *)this + 5);
  v34 = v31 + v29;
  v35 = *((_QWORD *)this + 4);
  if ( ((v33 - v35) & -(__int64)(v35 < v33)) >= v31 + v29 )
  {
    memmove_s(&v12[v34], v33 - v34 - (_QWORD)v12, v12, v35 - (_QWORD)v12);
    v36 = (unsigned __int8 *)(v34 + *((_QWORD *)this + 4));
    *((_QWORD *)this + 4) = v36;
    if ( !(_BYTE)v60 )
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v42,
        &InsertionPointOrIncrement,
        v36);
LABEL_61:
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v49,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
    if ( !v43 )
      goto LABEL_61;
    v37 = Source + 1;
    if ( Source == Source + 1 )
      goto LABEL_61;
    ++Source;
    if ( v43 == 1 )
    {
      v38 = 2;
      v60 = v37;
      v39 = 2;
      v40 = (unsigned int *)&v60;
    }
    else
    {
      if ( v43 != 2 )
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
0x1800240cc  mov     rax, rsp
0x1800240cf  mov     [rax+10h], rbx
0x1800240d3  mov     [rax+18h], rsi
0x1800240d7  mov     [rax+20h], rdi
0x1800240db  push    rbp
0x1800240dc  push    r12
0x1800240de  push    r13
0x1800240e0  push    r14
0x1800240e2  push    r15
0x1800240e4  lea     rbp, [rax-4Fh]
0x1800240e8  sub     rsp, 0A0h
0x1800240ef  mov     rdi, [rcx+18h]
0x1800240f3  mov     rbx, rcx
0x1800240f6  xor     ecx, ecx
0x1800240f8  mov     r13, r9
0x1800240fb  mov     r14, r8
0x1800240fe  mov     r15, rdx
0x180024101  test    rdi, rdi
0x180024104  jz      loc_180024459
0x18002410a  movzx   eax, word ptr [rbx+2]
0x18002410e  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x180024112  mov     r8, [rbx+20h]; unsigned __int8 *
0x180024116  add     rdi, 0Ah
0x18002411a  mov     [rbp+47h+var_88], ax
0x18002411e  xorps   xmm0, xmm0
0x180024121  mov     al, [rbx+4]
0x180024124  mov     [rbp+47h+Source], ecx
0x180024127  mov     [rbp+47h+var_80], cx
0x18002412b  mov     byte ptr [rbp+47h+arg_0], cl
0x18002412e  lea     rcx, [rbp+47h+var_88]; this
0x180024132  mov     [rbp+47h+var_86], al
0x180024135  mov     [rbp+47h+var_90], rdi
0x180024139  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18002413e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180024143  mov     r12, [rbp+47h+arg_20]
0x180024147  jmp     loc_18002429E
0x18002414c  movzx   ecx, [rbp+47h+var_80]
0x180024150  cmp     r14, rcx
0x180024153  jnz     short loc_18002416B
0x180024155  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180024159  mov     r8, r14; Size
0x18002415c  mov     rcx, r15; Buf1
0x18002415f  call    memcmp_0
0x180024164  mov     ecx, eax
0x180024166  xor     r9d, r9d
0x180024169  jmp     short loc_180024174
0x18002416b  movzx   eax, [rbp+47h+var_80]
0x18002416f  mov     ecx, r14d
0x180024172  sub     ecx, eax
0x180024174  test    ecx, ecx
0x180024176  js      loc_180024323
0x18002417c  jz      loc_1800242E8
0x180024182  mov     rdi, [rbp+47h+var_90]
0x180024186  mov     [rbp+47h+var_90], rdi
0x18002418a  cmp     [rbx+10h], r9
0x18002418e  jbe     short loc_1800241FC
0x180024190  mov     rax, [rbx+20h]
0x180024194  xor     edx, edx
0x180024196  sub     rax, [rbx+18h]
0x18002419a  div     qword ptr [rbx+10h]
0x18002419e  mov     edx, [rbp+47h+Source]
0x1800241a1  cmp     rdx, rax
0x1800241a4  jbe     short loc_1800241ED
0x1800241a6  cmp     edx, eax
0x1800241a8  jz      short loc_1800241ED
0x1800241aa  mov     edx, eax
0x1800241ac  mov     [rbp+47h+Source], eax
0x1800241af  mov     al, [rbp+47h+var_86]
0x1800241b2  cmp     al, 1
0x1800241b4  jnz     short loc_1800241C9
0x1800241b6  movzx   eax, dx
0x1800241b9  mov     [rbp+47h+var_68], dx
0x1800241bd  mov     r9d, 2
0x1800241c3  lea     r8, [rbp+47h+var_68]
0x1800241c7  jmp     short loc_1800241D7
0x1800241c9  cmp     al, 2
0x1800241cb  jnz     short loc_1800241ED
0x1800241cd  mov     r9d, 4; SourceSize
0x1800241d3  lea     r8, [rbp+47h+Source]; Source
0x1800241d7  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800241db  mov     rdx, r9; DestinationSize
0x1800241de  call    cs:__imp_memcpy_s
0x1800241e5  nop     dword ptr [rax+rax+00h]
0x1800241ea  mov     edx, [rbp+47h+Source]
0x1800241ed  mov     eax, edx
0x1800241ef  imul    rax, [rbx+10h]
0x1800241f4  add     rdi, rax
0x1800241f7  jmp     loc_180024289
0x1800241fc  movzx   eax, word ptr [rbx+6]
0x180024200  xorps   xmm0, xmm0
0x180024203  mov     [rbp+47h+var_40], ax
0x180024207  mov     esi, r9d
0x18002420a  mov     al, [rbx+8]
0x18002420d  mov     [rbp+47h+var_3E], al
0x180024210  mov     eax, [rbp+47h+Source]
0x180024213  mov     [rbp+47h+var_3C], r9d
0x180024217  mov     [rbp+47h+var_38], r9w
0x18002421c  movdqu  [rbp+47h+var_30], xmm0
0x180024221  test    eax, eax
0x180024223  jz      short loc_180024247
0x180024225  mov     r8, [rbx+20h]; unsigned __int8 *
0x180024229  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18002422d  lea     rcx, [rbp+47h+var_40]; this
0x180024231  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180024236  test    al, al
0x180024238  mov     eax, [rbp+47h+Source]
0x18002423b  jz      short loc_180024243
0x18002423d  inc     esi
0x18002423f  cmp     esi, eax
0x180024241  jb      short loc_180024225
0x180024243  mov     rdi, [rbp+47h+var_90]
0x180024247  cmp     eax, esi
0x180024249  jz      short loc_180024289
0x18002424b  mov     al, [rbp+47h+var_86]
0x18002424e  mov     [rbp+47h+Source], esi
0x180024251  cmp     al, 1
0x180024253  jnz     short loc_180024269
0x180024255  mov     eax, 2
0x18002425a  mov     [rbp+47h+var_64], si
0x18002425e  mov     r9d, eax
0x180024261  lea     r8, [rbp+47h+var_64]
0x180024265  mov     edx, eax
0x180024267  jmp     short loc_180024279
0x180024269  cmp     al, 2
0x18002426b  jnz     short loc_180024289
0x18002426d  mov     edx, 4; DestinationSize
0x180024272  lea     r8, [rbp+47h+Source]; Source
0x180024276  mov     r9d, edx; SourceSize
0x180024279  mov     rcx, [rbp+47h+Buf2]; Destination
0x18002427d  call    cs:__imp_memcpy_s
0x180024284  nop     dword ptr [rax+rax+00h]
0x180024289  mov     r8, [rbx+20h]; unsigned __int8 *
0x18002428d  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x180024291  lea     rcx, [rbp+47h+var_88]; this
0x180024295  mov     [rbp+47h+var_90], rdi
0x180024299  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002429e  xor     r9d, r9d
0x1800242a1  mov     sil, al
0x1800242a4  test    al, al
0x1800242a6  jnz     loc_18002414C
0x1800242ac  mov     rdi, [rbp+47h+var_90]
0x1800242b0  mov     [rbx+20h], rdi
0x1800242b4  mov     rcx, r9
0x1800242b7  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1800242bb  jnz     loc_180024346
0x1800242c1  movzx   eax, [rbp+47h+var_88]
0x1800242c5  mov     [rbp+47h+Source], 1
0x1800242cc  mov     [rbp+47h+var_80], r14w
0x1800242d1  mov     [rbp+47h+Buf2], r9
0x1800242d5  mov     [rbp+47h+Buf2+8], r15
0x1800242d9  test    ax, ax
0x1800242dc  jnz     short loc_18002432E
0x1800242de  movzx   ecx, r14w
0x1800242e2  add     rcx, 2
0x1800242e6  jmp     short loc_180024331
0x1800242e8  mov     eax, [rbp+47h+arg_28]
0x1800242eb  lea     rdx, [rbp+47h+var_88]; struct wil::details_abi::UsageIndexProperty *
0x1800242ef  mov     r8, [rbp+47h+var_90]; unsigned __int8 *
0x1800242f3  mov     r9, r13; void *
0x1800242f6  mov     [rsp+0C0h+var_98], eax; unsigned int
0x1800242fa  mov     rcx, rbx; this
0x1800242fd  mov     [rsp+0C0h+Size], r12; Size
0x180024302  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180024307  xor     r9d, r9d
0x18002430a  mov     [rbp+47h+var_90], rax
0x18002430e  mov     rdi, rax
0x180024311  test    rax, rax
0x180024314  jnz     short loc_18002431D
0x180024316  mov     al, 1
0x180024318  jmp     loc_18002445B
0x18002431d  mov     byte ptr [rbp+47h+arg_0], 1
0x180024321  jmp     short loc_180024327
0x180024323  mov     [rbp+47h+var_90], rdi
0x180024327  test    sil, sil
0x18002432a  jnz     short loc_1800242B4
0x18002432c  jmp     short loc_1800242B0
0x18002432e  mov     rcx, rax
0x180024331  mov     al, [rbp+47h+var_86]
0x180024334  cmp     al, 1
0x180024336  jnz     short loc_18002433E
0x180024338  add     rcx, 2
0x18002433c  jmp     short loc_180024346
0x18002433e  cmp     al, 2
0x180024340  jnz     short loc_180024346
0x180024342  add     rcx, 4
0x180024346  movzx   eax, word ptr [rbx+6]
0x18002434a  mov     dl, [rbx+8]
0x18002434d  mov     r8d, [rbp+47h+arg_28]
0x180024351  mov     [rbp+47h+var_60], ax
0x180024355  mov     [rbp+47h+var_5E], dl
0x180024358  mov     [rbp+47h+var_5C], r8d
0x18002435c  mov     [rbp+47h+var_58], r12w
0x180024361  mov     [rbp+47h+var_50], r9
0x180024365  mov     [rbp+47h+var_48], r13
0x180024369  test    ax, ax
0x18002436c  jnz     short loc_180024376
0x18002436e  movzx   eax, r12w
0x180024372  add     rax, 2
0x180024376  cmp     dl, 1
0x180024379  jnz     short loc_180024381
0x18002437b  add     rax, 2
0x18002437f  jmp     short loc_18002438A
0x180024381  cmp     dl, 2
0x180024384  jnz     short loc_18002438A
0x180024386  add     rax, 4
0x18002438a  mov     rdx, [rbx+28h]
0x18002438e  lea     rsi, [rax+rcx]
0x180024392  mov     r9, [rbx+20h]
0x180024396  mov     rcx, rdx
0x180024399  sub     rcx, r9
0x18002439c  cmp     r9, rdx
0x18002439f  sbb     rax, rax
0x1800243a2  and     rax, rcx
0x1800243a5  cmp     rax, rsi
0x1800243a8  jb      loc_180024459
0x1800243ae  sub     rdx, rsi
0x1800243b1  lea     rcx, [rsi+rdi]; Destination
0x1800243b5  sub     rdx, rdi; DestinationSize
0x1800243b8  sub     r9, rdi; SourceSize
0x1800243bb  mov     r8, rdi; Source
0x1800243be  call    cs:__imp_memmove_s
0x1800243c5  nop     dword ptr [rax+rax+00h]
0x1800243ca  mov     r8, [rbx+20h]
0x1800243ce  xor     edi, edi
0x1800243d0  add     r8, rsi; unsigned __int8 *
0x1800243d3  mov     [rbx+20h], r8
0x1800243d7  cmp     byte ptr [rbp+47h+arg_0], dil
0x1800243db  jnz     short loc_1800243EC
0x1800243dd  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x1800243e1  lea     rcx, [rbp+47h+var_88]; this
0x1800243e5  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800243ea  jmp     short loc_18002443F
0x1800243ec  mov     cl, [rbp+47h+var_86]
0x1800243ef  test    cl, cl
0x1800243f1  jz      short loc_18002443F
0x1800243f3  mov     eax, [rbp+47h+Source]
0x1800243f6  lea     r8d, [rax+1]
0x1800243fa  cmp     eax, r8d
0x1800243fd  jz      short loc_18002443F
0x1800243ff  mov     [rbp+47h+Source], r8d
0x180024403  cmp     cl, 1
0x180024406  jnz     short loc_18002441C
0x180024408  mov     r9d, 2
0x18002440e  mov     [rbp+47h+arg_0], r8w
0x180024413  mov     edx, r9d
0x180024416  lea     r8, [rbp+47h+arg_0]
0x18002441a  jmp     short loc_18002442F
0x18002441c  cmp     cl, 2
0x18002441f  jnz     short loc_18002443F
0x180024421  mov     eax, 4
0x180024426  lea     r8, [rbp+47h+Source]; Source
0x18002442a  mov     r9d, eax; SourceSize
0x18002442d  mov     edx, eax; DestinationSize
0x18002442f  mov     rcx, [rbp+47h+Buf2]; Destination
0x180024433  call    cs:__imp_memcpy_s
0x18002443a  nop     dword ptr [rax+rax+00h]
0x18002443f  mov     r8, [rbx+20h]; unsigned __int8 *
0x180024443  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x180024447  lea     rcx, [rbp+47h+var_60]; this
0x18002444b  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180024450  mov     byte ptr [rbx+38h], 1
0x180024454  jmp     loc_180024316
0x180024459  xor     al, al
0x18002445b  lea     r11, [rsp+0C0h+var_20]
0x180024463  mov     rbx, [r11+38h]
0x180024467  mov     rsi, [r11+40h]
0x18002446b  mov     rdi, [r11+48h]
0x18002446f  mov     rsp, r11
0x180024472  pop     r15
0x180024474  pop     r14
0x180024476  pop     r13
0x180024478  pop     r12
0x18002447a  pop     rbp
0x18002447b  retn
```

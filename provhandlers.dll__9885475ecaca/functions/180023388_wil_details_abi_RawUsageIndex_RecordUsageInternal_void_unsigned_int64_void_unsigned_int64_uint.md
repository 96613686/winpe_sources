# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180023388`
- end: `0x180023708`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800231d8`

## callees

- `0x1800177b8`
- `0x180022bc8`
- `0x180023388`
- `0x18002477c`
- `0x18003b946`

## import_xrefs

- `msvcrt!memmove_s` at `0x180023667`
- `msvcrt!memmove_s` at `0x180023667`
- `msvcrt!memcpy_s` at `0x180023493`
- `msvcrt!memcpy_s` at `0x18002352c`
- `msvcrt!memcpy_s` at `0x1800236d2`
- `msvcrt!memcpy_s` at `0x180023493`
- `msvcrt!memcpy_s` at `0x18002352c`
- `msvcrt!memcpy_s` at `0x1800236d2`

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
0x180023388  push    rbp
0x18002338a  push    rbx
0x18002338b  push    rsi
0x18002338c  push    rdi
0x18002338d  push    r12
0x18002338f  push    r13
0x180023391  push    r14
0x180023393  push    r15
0x180023395  lea     rbp, [rsp-0Fh]
0x18002339a  sub     rsp, 0A8h
0x1800233a1  mov     rbx, [rcx+18h]
0x1800233a5  mov     rdi, rcx
0x1800233a8  xor     ecx, ecx
0x1800233aa  mov     r13, r9
0x1800233ad  mov     r14, r8
0x1800233b0  mov     r15, rdx
0x1800233b3  test    rbx, rbx
0x1800233b6  jz      loc_1800236F2
0x1800233bc  movzx   eax, word ptr [rdi+2]
0x1800233c0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800233c4  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800233c8  add     rbx, 0Ah
0x1800233cc  mov     [rbp+47h+var_A0], ax
0x1800233d0  xorps   xmm0, xmm0
0x1800233d3  mov     al, [rdi+4]
0x1800233d6  mov     [rbp+47h+Source], ecx
0x1800233d9  mov     [rbp+47h+var_98], cx
0x1800233dd  mov     byte ptr [rbp+47h+arg_0], cl
0x1800233e0  lea     rcx, [rbp+47h+var_A0]; this
0x1800233e4  mov     [rbp+47h+var_9E], al
0x1800233e7  mov     [rbp+47h+var_A8], rbx
0x1800233eb  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1800233f0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800233f5  mov     r12, [rbp+47h+arg_20]
0x1800233f9  jmp     loc_180023547
0x1800233fe  movzx   eax, [rbp+47h+var_98]
0x180023402  cmp     r14, rax
0x180023405  jnz     short loc_18002341D
0x180023407  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18002340b  mov     r8, r14; Size
0x18002340e  mov     rcx, r15; Buf1
0x180023411  call    memcmp_0
0x180023416  mov     ecx, eax
0x180023418  xor     r9d, r9d
0x18002341b  jmp     short loc_180023426
0x18002341d  movzx   eax, [rbp+47h+var_98]
0x180023421  mov     ecx, r14d
0x180023424  sub     ecx, eax
0x180023426  test    ecx, ecx
0x180023428  js      loc_1800235CC
0x18002342e  jz      loc_180023591
0x180023434  mov     rbx, [rbp+47h+var_A8]
0x180023438  mov     [rbp+47h+var_A8], rbx
0x18002343c  cmp     [rdi+10h], r9
0x180023440  jbe     short loc_1800234AB
0x180023442  mov     rax, [rdi+20h]
0x180023446  xor     edx, edx
0x180023448  sub     rax, [rdi+18h]
0x18002344c  mov     rsi, rbx
0x18002344f  div     qword ptr [rdi+10h]
0x180023453  mov     edx, [rbp+47h+Source]
0x180023456  cmp     rdx, rax
0x180023459  jbe     short loc_18002349C
0x18002345b  cmp     edx, eax
0x18002345d  jz      short loc_18002349C
0x18002345f  mov     edx, eax
0x180023461  mov     [rbp+47h+Source], eax
0x180023464  mov     al, [rbp+47h+var_9E]
0x180023467  cmp     al, 1
0x180023469  jnz     short loc_18002347E
0x18002346b  movzx   eax, dx
0x18002346e  mov     [rbp+47h+var_B0], dx
0x180023472  mov     r9d, 2
0x180023478  lea     r8, [rbp+47h+var_B0]
0x18002347c  jmp     short loc_18002348C
0x18002347e  cmp     al, 2
0x180023480  jnz     short loc_18002349C
0x180023482  mov     r9d, 4; SourceSize
0x180023488  lea     r8, [rbp+47h+Source]; Source
0x18002348c  mov     rcx, [rbp+47h+Buf2]; Destination
0x180023490  mov     rdx, r9; DestinationSize
0x180023493  call    cs:__imp_memcpy_s
0x180023499  mov     edx, [rbp+47h+Source]
0x18002349c  mov     ebx, edx
0x18002349e  imul    rbx, [rdi+10h]
0x1800234a3  add     rbx, rsi
0x1800234a6  jmp     loc_180023532
0x1800234ab  movzx   eax, word ptr [rdi+6]
0x1800234af  xorps   xmm0, xmm0
0x1800234b2  mov     [rbp+47h+var_60], ax
0x1800234b6  mov     esi, r9d
0x1800234b9  mov     al, [rdi+8]
0x1800234bc  mov     [rbp+47h+var_5E], al
0x1800234bf  mov     eax, [rbp+47h+Source]
0x1800234c2  mov     [rbp+47h+var_5C], r9d
0x1800234c6  mov     [rbp+47h+var_58], r9w
0x1800234cb  movdqu  [rbp+47h+var_50], xmm0
0x1800234d0  test    eax, eax
0x1800234d2  jz      short loc_1800234F6
0x1800234d4  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800234d8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800234dc  lea     rcx, [rbp+47h+var_60]; this
0x1800234e0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800234e5  test    al, al
0x1800234e7  mov     eax, [rbp+47h+Source]
0x1800234ea  jz      short loc_1800234F2
0x1800234ec  inc     esi
0x1800234ee  cmp     esi, eax
0x1800234f0  jb      short loc_1800234D4
0x1800234f2  mov     rbx, [rbp+47h+var_A8]
0x1800234f6  cmp     eax, esi
0x1800234f8  jz      short loc_180023532
0x1800234fa  mov     al, [rbp+47h+var_9E]
0x1800234fd  mov     [rbp+47h+Source], esi
0x180023500  cmp     al, 1
0x180023502  jnz     short loc_180023518
0x180023504  mov     eax, 2
0x180023509  mov     [rbp+47h+var_B0], si
0x18002350d  mov     r9d, eax
0x180023510  lea     r8, [rbp+47h+var_B0]
0x180023514  mov     edx, eax
0x180023516  jmp     short loc_180023528
0x180023518  cmp     al, 2
0x18002351a  jnz     short loc_180023532
0x18002351c  mov     edx, 4; DestinationSize
0x180023521  lea     r8, [rbp+47h+Source]; Source
0x180023525  mov     r9d, edx; SourceSize
0x180023528  mov     rcx, [rbp+47h+Buf2]; Destination
0x18002352c  call    cs:__imp_memcpy_s
0x180023532  mov     r8, [rdi+20h]; unsigned __int8 *
0x180023536  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18002353a  lea     rcx, [rbp+47h+var_A0]; this
0x18002353e  mov     [rbp+47h+var_A8], rbx
0x180023542  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180023547  xor     r9d, r9d
0x18002354a  mov     sil, al
0x18002354d  test    al, al
0x18002354f  jnz     loc_1800233FE
0x180023555  mov     rbx, [rbp+47h+var_A8]
0x180023559  mov     [rdi+20h], rbx
0x18002355d  mov     rcx, r9
0x180023560  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180023564  jnz     loc_1800235EF
0x18002356a  movzx   eax, [rbp+47h+var_A0]
0x18002356e  mov     [rbp+47h+Source], 1
0x180023575  mov     [rbp+47h+var_98], r14w
0x18002357a  mov     [rbp+47h+Buf2], r9
0x18002357e  mov     [rbp+47h+Buf2+8], r15
0x180023582  test    ax, ax
0x180023585  jnz     short loc_1800235D7
0x180023587  movzx   ecx, r14w
0x18002358b  add     rcx, 2
0x18002358f  jmp     short loc_1800235DA
0x180023591  mov     eax, [rbp+47h+arg_28]
0x180023594  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180023598  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18002359c  mov     r9, r13; void *
0x18002359f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1800235a3  mov     rcx, rdi; this
0x1800235a6  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x1800235ab  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800235b0  xor     r9d, r9d
0x1800235b3  mov     [rbp+47h+var_A8], rax
0x1800235b7  mov     rbx, rax
0x1800235ba  test    rax, rax
0x1800235bd  jnz     short loc_1800235C6
0x1800235bf  mov     al, 1
0x1800235c1  jmp     loc_1800236F4
0x1800235c6  mov     byte ptr [rbp+47h+arg_0], 1
0x1800235ca  jmp     short loc_1800235D0
0x1800235cc  mov     [rbp+47h+var_A8], rbx
0x1800235d0  test    sil, sil
0x1800235d3  jnz     short loc_18002355D
0x1800235d5  jmp     short loc_180023559
0x1800235d7  mov     rcx, rax
0x1800235da  mov     al, [rbp+47h+var_9E]
0x1800235dd  cmp     al, 1
0x1800235df  jnz     short loc_1800235E7
0x1800235e1  add     rcx, 2
0x1800235e5  jmp     short loc_1800235EF
0x1800235e7  cmp     al, 2
0x1800235e9  jnz     short loc_1800235EF
0x1800235eb  add     rcx, 4
0x1800235ef  movzx   eax, word ptr [rdi+6]
0x1800235f3  mov     dl, [rdi+8]
0x1800235f6  mov     r8d, [rbp+47h+arg_28]
0x1800235fa  mov     [rbp+47h+var_80], ax
0x1800235fe  mov     [rbp+47h+var_7E], dl
0x180023601  mov     [rbp+47h+var_7C], r8d
0x180023605  mov     [rbp+47h+var_78], r12w
0x18002360a  mov     [rbp+47h+var_70], r9
0x18002360e  mov     [rbp+47h+var_68], r13
0x180023612  test    ax, ax
0x180023615  jnz     short loc_18002361F
0x180023617  movzx   eax, r12w
0x18002361b  add     rax, 2
0x18002361f  cmp     dl, 1
0x180023622  jnz     short loc_18002362A
0x180023624  add     rax, 2
0x180023628  jmp     short loc_180023633
0x18002362a  cmp     dl, 2
0x18002362d  jnz     short loc_180023633
0x18002362f  add     rax, 4
0x180023633  mov     rdx, [rdi+28h]
0x180023637  lea     rsi, [rax+rcx]
0x18002363b  mov     r9, [rdi+20h]
0x18002363f  mov     rcx, rdx
0x180023642  sub     rcx, r9
0x180023645  cmp     r9, rdx
0x180023648  sbb     rax, rax
0x18002364b  and     rax, rcx
0x18002364e  cmp     rax, rsi
0x180023651  jb      loc_1800236F2
0x180023657  sub     rdx, rsi
0x18002365a  lea     rcx, [rsi+rbx]; Destination
0x18002365e  sub     rdx, rbx; DestinationSize
0x180023661  sub     r9, rbx; SourceSize
0x180023664  mov     r8, rbx; Source
0x180023667  call    cs:__imp_memmove_s
0x18002366d  add     [rdi+20h], rsi
0x180023671  xor     ebx, ebx
0x180023673  cmp     byte ptr [rbp+47h+arg_0], bl
0x180023676  jnz     short loc_18002368B
0x180023678  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002367c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180023680  lea     rcx, [rbp+47h+var_A0]; this
0x180023684  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180023689  jmp     short loc_1800236D8
0x18002368b  mov     cl, [rbp+47h+var_9E]
0x18002368e  test    cl, cl
0x180023690  jz      short loc_1800236D8
0x180023692  mov     eax, [rbp+47h+Source]
0x180023695  lea     r8d, [rax+1]
0x180023699  cmp     eax, r8d
0x18002369c  jz      short loc_1800236D8
0x18002369e  mov     [rbp+47h+Source], r8d
0x1800236a2  cmp     cl, 1
0x1800236a5  jnz     short loc_1800236BB
0x1800236a7  mov     r9d, 2
0x1800236ad  mov     [rbp+47h+arg_0], r8w
0x1800236b2  mov     edx, r9d
0x1800236b5  lea     r8, [rbp+47h+arg_0]
0x1800236b9  jmp     short loc_1800236CE
0x1800236bb  cmp     cl, 2
0x1800236be  jnz     short loc_1800236D8
0x1800236c0  mov     eax, 4
0x1800236c5  lea     r8, [rbp+47h+Source]; Source
0x1800236c9  mov     r9d, eax; SourceSize
0x1800236cc  mov     edx, eax; DestinationSize
0x1800236ce  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800236d2  call    cs:__imp_memcpy_s
0x1800236d8  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800236dc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800236e0  lea     rcx, [rbp+47h+var_80]; this
0x1800236e4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800236e9  mov     byte ptr [rdi+38h], 1
0x1800236ed  jmp     loc_1800235BF
0x1800236f2  xor     al, al
0x1800236f4  add     rsp, 0A8h
0x1800236fb  pop     r15
0x1800236fd  pop     r14
0x1800236ff  pop     r13
0x180023701  pop     r12
0x180023703  pop     rdi
0x180023704  pop     rsi
0x180023705  pop     rbx
0x180023706  pop     rbp
0x180023707  retn
```

# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000fa28`
- end: `0x18000fda8`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f878`

## callees

- `0x180008654`
- `0x18000f268`
- `0x18000fa28`
- `0x180011b1c`
- `0x1800133d6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000fb33`
- `msvcrt!memcpy_s` at `0x18000fbcc`
- `msvcrt!memcpy_s` at `0x18000fd72`
- `msvcrt!memcpy_s` at `0x18000fb33`
- `msvcrt!memcpy_s` at `0x18000fbcc`
- `msvcrt!memcpy_s` at `0x18000fd72`
- `msvcrt!memmove_s` at `0x18000fd07`
- `msvcrt!memmove_s` at `0x18000fd07`

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
0x18000fa28  push    rbp
0x18000fa2a  push    rbx
0x18000fa2b  push    rsi
0x18000fa2c  push    rdi
0x18000fa2d  push    r12
0x18000fa2f  push    r13
0x18000fa31  push    r14
0x18000fa33  push    r15
0x18000fa35  lea     rbp, [rsp-0Fh]
0x18000fa3a  sub     rsp, 0A8h
0x18000fa41  mov     rbx, [rcx+18h]
0x18000fa45  mov     rdi, rcx
0x18000fa48  xor     ecx, ecx
0x18000fa4a  mov     r13, r9
0x18000fa4d  mov     r14, r8
0x18000fa50  mov     r15, rdx
0x18000fa53  test    rbx, rbx
0x18000fa56  jz      loc_18000FD92
0x18000fa5c  movzx   eax, word ptr [rdi+2]
0x18000fa60  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000fa64  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000fa68  add     rbx, 0Ah
0x18000fa6c  mov     [rbp+47h+var_A0], ax
0x18000fa70  xorps   xmm0, xmm0
0x18000fa73  mov     al, [rdi+4]
0x18000fa76  mov     [rbp+47h+Source], ecx
0x18000fa79  mov     [rbp+47h+var_98], cx
0x18000fa7d  mov     byte ptr [rbp+47h+arg_0], cl
0x18000fa80  lea     rcx, [rbp+47h+var_A0]; this
0x18000fa84  mov     [rbp+47h+var_9E], al
0x18000fa87  mov     [rbp+47h+var_A8], rbx
0x18000fa8b  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000fa90  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000fa95  mov     r12, [rbp+47h+arg_20]
0x18000fa99  jmp     loc_18000FBE7
0x18000fa9e  movzx   eax, [rbp+47h+var_98]
0x18000faa2  cmp     r14, rax
0x18000faa5  jnz     short loc_18000FABD
0x18000faa7  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000faab  mov     r8, r14; Size
0x18000faae  mov     rcx, r15; Buf1
0x18000fab1  call    memcmp_0
0x18000fab6  mov     ecx, eax
0x18000fab8  xor     r9d, r9d
0x18000fabb  jmp     short loc_18000FAC6
0x18000fabd  movzx   eax, [rbp+47h+var_98]
0x18000fac1  mov     ecx, r14d
0x18000fac4  sub     ecx, eax
0x18000fac6  test    ecx, ecx
0x18000fac8  js      loc_18000FC6C
0x18000face  jz      loc_18000FC31
0x18000fad4  mov     rbx, [rbp+47h+var_A8]
0x18000fad8  mov     [rbp+47h+var_A8], rbx
0x18000fadc  cmp     [rdi+10h], r9
0x18000fae0  jbe     short loc_18000FB4B
0x18000fae2  mov     rax, [rdi+20h]
0x18000fae6  xor     edx, edx
0x18000fae8  sub     rax, [rdi+18h]
0x18000faec  mov     rsi, rbx
0x18000faef  div     qword ptr [rdi+10h]
0x18000faf3  mov     edx, [rbp+47h+Source]
0x18000faf6  cmp     rdx, rax
0x18000faf9  jbe     short loc_18000FB3C
0x18000fafb  cmp     edx, eax
0x18000fafd  jz      short loc_18000FB3C
0x18000faff  mov     edx, eax
0x18000fb01  mov     [rbp+47h+Source], eax
0x18000fb04  mov     al, [rbp+47h+var_9E]
0x18000fb07  cmp     al, 1
0x18000fb09  jnz     short loc_18000FB1E
0x18000fb0b  movzx   eax, dx
0x18000fb0e  mov     [rbp+47h+var_B0], dx
0x18000fb12  mov     r9d, 2
0x18000fb18  lea     r8, [rbp+47h+var_B0]
0x18000fb1c  jmp     short loc_18000FB2C
0x18000fb1e  cmp     al, 2
0x18000fb20  jnz     short loc_18000FB3C
0x18000fb22  mov     r9d, 4; SourceSize
0x18000fb28  lea     r8, [rbp+47h+Source]; Source
0x18000fb2c  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000fb30  mov     rdx, r9; DestinationSize
0x18000fb33  call    cs:__imp_memcpy_s
0x18000fb39  mov     edx, [rbp+47h+Source]
0x18000fb3c  mov     ebx, edx
0x18000fb3e  imul    rbx, [rdi+10h]
0x18000fb43  add     rbx, rsi
0x18000fb46  jmp     loc_18000FBD2
0x18000fb4b  movzx   eax, word ptr [rdi+6]
0x18000fb4f  xorps   xmm0, xmm0
0x18000fb52  mov     [rbp+47h+var_60], ax
0x18000fb56  mov     esi, r9d
0x18000fb59  mov     al, [rdi+8]
0x18000fb5c  mov     [rbp+47h+var_5E], al
0x18000fb5f  mov     eax, [rbp+47h+Source]
0x18000fb62  mov     [rbp+47h+var_5C], r9d
0x18000fb66  mov     [rbp+47h+var_58], r9w
0x18000fb6b  movdqu  [rbp+47h+var_50], xmm0
0x18000fb70  test    eax, eax
0x18000fb72  jz      short loc_18000FB96
0x18000fb74  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000fb78  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000fb7c  lea     rcx, [rbp+47h+var_60]; this
0x18000fb80  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000fb85  test    al, al
0x18000fb87  mov     eax, [rbp+47h+Source]
0x18000fb8a  jz      short loc_18000FB92
0x18000fb8c  inc     esi
0x18000fb8e  cmp     esi, eax
0x18000fb90  jb      short loc_18000FB74
0x18000fb92  mov     rbx, [rbp+47h+var_A8]
0x18000fb96  cmp     eax, esi
0x18000fb98  jz      short loc_18000FBD2
0x18000fb9a  mov     al, [rbp+47h+var_9E]
0x18000fb9d  mov     [rbp+47h+Source], esi
0x18000fba0  cmp     al, 1
0x18000fba2  jnz     short loc_18000FBB8
0x18000fba4  mov     eax, 2
0x18000fba9  mov     [rbp+47h+var_B0], si
0x18000fbad  mov     r9d, eax
0x18000fbb0  lea     r8, [rbp+47h+var_B0]
0x18000fbb4  mov     edx, eax
0x18000fbb6  jmp     short loc_18000FBC8
0x18000fbb8  cmp     al, 2
0x18000fbba  jnz     short loc_18000FBD2
0x18000fbbc  mov     edx, 4; DestinationSize
0x18000fbc1  lea     r8, [rbp+47h+Source]; Source
0x18000fbc5  mov     r9d, edx; SourceSize
0x18000fbc8  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000fbcc  call    cs:__imp_memcpy_s
0x18000fbd2  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000fbd6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000fbda  lea     rcx, [rbp+47h+var_A0]; this
0x18000fbde  mov     [rbp+47h+var_A8], rbx
0x18000fbe2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000fbe7  xor     r9d, r9d
0x18000fbea  mov     sil, al
0x18000fbed  test    al, al
0x18000fbef  jnz     loc_18000FA9E
0x18000fbf5  mov     rbx, [rbp+47h+var_A8]
0x18000fbf9  mov     [rdi+20h], rbx
0x18000fbfd  mov     rcx, r9
0x18000fc00  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000fc04  jnz     loc_18000FC8F
0x18000fc0a  movzx   eax, [rbp+47h+var_A0]
0x18000fc0e  mov     [rbp+47h+Source], 1
0x18000fc15  mov     [rbp+47h+var_98], r14w
0x18000fc1a  mov     [rbp+47h+Buf2], r9
0x18000fc1e  mov     [rbp+47h+Buf2+8], r15
0x18000fc22  test    ax, ax
0x18000fc25  jnz     short loc_18000FC77
0x18000fc27  movzx   ecx, r14w
0x18000fc2b  add     rcx, 2
0x18000fc2f  jmp     short loc_18000FC7A
0x18000fc31  mov     eax, [rbp+47h+arg_28]
0x18000fc34  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18000fc38  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000fc3c  mov     r9, r13; void *
0x18000fc3f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000fc43  mov     rcx, rdi; this
0x18000fc46  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000fc4b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000fc50  xor     r9d, r9d
0x18000fc53  mov     [rbp+47h+var_A8], rax
0x18000fc57  mov     rbx, rax
0x18000fc5a  test    rax, rax
0x18000fc5d  jnz     short loc_18000FC66
0x18000fc5f  mov     al, 1
0x18000fc61  jmp     loc_18000FD94
0x18000fc66  mov     byte ptr [rbp+47h+arg_0], 1
0x18000fc6a  jmp     short loc_18000FC70
0x18000fc6c  mov     [rbp+47h+var_A8], rbx
0x18000fc70  test    sil, sil
0x18000fc73  jnz     short loc_18000FBFD
0x18000fc75  jmp     short loc_18000FBF9
0x18000fc77  mov     rcx, rax
0x18000fc7a  mov     al, [rbp+47h+var_9E]
0x18000fc7d  cmp     al, 1
0x18000fc7f  jnz     short loc_18000FC87
0x18000fc81  add     rcx, 2
0x18000fc85  jmp     short loc_18000FC8F
0x18000fc87  cmp     al, 2
0x18000fc89  jnz     short loc_18000FC8F
0x18000fc8b  add     rcx, 4
0x18000fc8f  movzx   eax, word ptr [rdi+6]
0x18000fc93  mov     dl, [rdi+8]
0x18000fc96  mov     r8d, [rbp+47h+arg_28]
0x18000fc9a  mov     [rbp+47h+var_80], ax
0x18000fc9e  mov     [rbp+47h+var_7E], dl
0x18000fca1  mov     [rbp+47h+var_7C], r8d
0x18000fca5  mov     [rbp+47h+var_78], r12w
0x18000fcaa  mov     [rbp+47h+var_70], r9
0x18000fcae  mov     [rbp+47h+var_68], r13
0x18000fcb2  test    ax, ax
0x18000fcb5  jnz     short loc_18000FCBF
0x18000fcb7  movzx   eax, r12w
0x18000fcbb  add     rax, 2
0x18000fcbf  cmp     dl, 1
0x18000fcc2  jnz     short loc_18000FCCA
0x18000fcc4  add     rax, 2
0x18000fcc8  jmp     short loc_18000FCD3
0x18000fcca  cmp     dl, 2
0x18000fccd  jnz     short loc_18000FCD3
0x18000fccf  add     rax, 4
0x18000fcd3  mov     rdx, [rdi+28h]
0x18000fcd7  lea     rsi, [rax+rcx]
0x18000fcdb  mov     r9, [rdi+20h]
0x18000fcdf  mov     rcx, rdx
0x18000fce2  sub     rcx, r9
0x18000fce5  cmp     r9, rdx
0x18000fce8  sbb     rax, rax
0x18000fceb  and     rax, rcx
0x18000fcee  cmp     rax, rsi
0x18000fcf1  jb      loc_18000FD92
0x18000fcf7  sub     rdx, rsi
0x18000fcfa  lea     rcx, [rsi+rbx]; Destination
0x18000fcfe  sub     rdx, rbx; DestinationSize
0x18000fd01  sub     r9, rbx; SourceSize
0x18000fd04  mov     r8, rbx; Source
0x18000fd07  call    cs:__imp_memmove_s
0x18000fd0d  add     [rdi+20h], rsi
0x18000fd11  xor     ebx, ebx
0x18000fd13  cmp     byte ptr [rbp+47h+arg_0], bl
0x18000fd16  jnz     short loc_18000FD2B
0x18000fd18  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000fd1c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000fd20  lea     rcx, [rbp+47h+var_A0]; this
0x18000fd24  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000fd29  jmp     short loc_18000FD78
0x18000fd2b  mov     cl, [rbp+47h+var_9E]
0x18000fd2e  test    cl, cl
0x18000fd30  jz      short loc_18000FD78
0x18000fd32  mov     eax, [rbp+47h+Source]
0x18000fd35  lea     r8d, [rax+1]
0x18000fd39  cmp     eax, r8d
0x18000fd3c  jz      short loc_18000FD78
0x18000fd3e  mov     [rbp+47h+Source], r8d
0x18000fd42  cmp     cl, 1
0x18000fd45  jnz     short loc_18000FD5B
0x18000fd47  mov     r9d, 2
0x18000fd4d  mov     [rbp+47h+arg_0], r8w
0x18000fd52  mov     edx, r9d
0x18000fd55  lea     r8, [rbp+47h+arg_0]
0x18000fd59  jmp     short loc_18000FD6E
0x18000fd5b  cmp     cl, 2
0x18000fd5e  jnz     short loc_18000FD78
0x18000fd60  mov     eax, 4
0x18000fd65  lea     r8, [rbp+47h+Source]; Source
0x18000fd69  mov     r9d, eax; SourceSize
0x18000fd6c  mov     edx, eax; DestinationSize
0x18000fd6e  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000fd72  call    cs:__imp_memcpy_s
0x18000fd78  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000fd7c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000fd80  lea     rcx, [rbp+47h+var_80]; this
0x18000fd84  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000fd89  mov     byte ptr [rdi+38h], 1
0x18000fd8d  jmp     loc_18000FC5F
0x18000fd92  xor     al, al
0x18000fd94  add     rsp, 0A8h
0x18000fd9b  pop     r15
0x18000fd9d  pop     r14
0x18000fd9f  pop     r13
0x18000fda1  pop     r12
0x18000fda3  pop     rdi
0x18000fda4  pop     rsi
0x18000fda5  pop     rbx
0x18000fda6  pop     rbp
0x18000fda7  retn
```

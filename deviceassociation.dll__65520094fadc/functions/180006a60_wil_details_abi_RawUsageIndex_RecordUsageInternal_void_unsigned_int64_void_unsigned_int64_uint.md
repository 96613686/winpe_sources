# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006a60`
- end: `0x180006de0`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800068b0`

## callees

- `0x180004d0c`
- `0x18000642c`
- `0x180006a60`
- `0x18000835c`
- `0x18000bbb6`

## import_xrefs

- `msvcrt!memmove_s` at `0x180006d3f`
- `msvcrt!memmove_s` at `0x180006d3f`
- `msvcrt!memcpy_s` at `0x180006b6b`
- `msvcrt!memcpy_s` at `0x180006c04`
- `msvcrt!memcpy_s` at `0x180006daa`
- `msvcrt!memcpy_s` at `0x180006b6b`
- `msvcrt!memcpy_s` at `0x180006c04`
- `msvcrt!memcpy_s` at `0x180006daa`

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
0x180006a60  push    rbp
0x180006a62  push    rbx
0x180006a63  push    rsi
0x180006a64  push    rdi
0x180006a65  push    r12
0x180006a67  push    r13
0x180006a69  push    r14
0x180006a6b  push    r15
0x180006a6d  lea     rbp, [rsp-0Fh]
0x180006a72  sub     rsp, 0A8h
0x180006a79  mov     rbx, [rcx+18h]
0x180006a7d  mov     rdi, rcx
0x180006a80  xor     ecx, ecx
0x180006a82  mov     r13, r9
0x180006a85  mov     r14, r8
0x180006a88  mov     r15, rdx
0x180006a8b  test    rbx, rbx
0x180006a8e  jz      loc_180006DCA
0x180006a94  movzx   eax, word ptr [rdi+2]
0x180006a98  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006a9c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006aa0  add     rbx, 0Ah
0x180006aa4  mov     [rbp+47h+var_A0], ax
0x180006aa8  xorps   xmm0, xmm0
0x180006aab  mov     al, [rdi+4]
0x180006aae  mov     [rbp+47h+Source], ecx
0x180006ab1  mov     [rbp+47h+var_98], cx
0x180006ab5  mov     byte ptr [rbp+47h+arg_0], cl
0x180006ab8  lea     rcx, [rbp+47h+var_A0]; this
0x180006abc  mov     [rbp+47h+var_9E], al
0x180006abf  mov     [rbp+47h+var_A8], rbx
0x180006ac3  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180006ac8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006acd  mov     r12, [rbp+47h+arg_20]
0x180006ad1  jmp     loc_180006C1F
0x180006ad6  movzx   eax, [rbp+47h+var_98]
0x180006ada  cmp     r14, rax
0x180006add  jnz     short loc_180006AF5
0x180006adf  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180006ae3  mov     r8, r14; Size
0x180006ae6  mov     rcx, r15; Buf1
0x180006ae9  call    memcmp_0
0x180006aee  mov     ecx, eax
0x180006af0  xor     r9d, r9d
0x180006af3  jmp     short loc_180006AFE
0x180006af5  movzx   eax, [rbp+47h+var_98]
0x180006af9  mov     ecx, r14d
0x180006afc  sub     ecx, eax
0x180006afe  test    ecx, ecx
0x180006b00  js      loc_180006CA4
0x180006b06  jz      loc_180006C69
0x180006b0c  mov     rbx, [rbp+47h+var_A8]
0x180006b10  mov     [rbp+47h+var_A8], rbx
0x180006b14  cmp     [rdi+10h], r9
0x180006b18  jbe     short loc_180006B83
0x180006b1a  mov     rax, [rdi+20h]
0x180006b1e  xor     edx, edx
0x180006b20  sub     rax, [rdi+18h]
0x180006b24  mov     rsi, rbx
0x180006b27  div     qword ptr [rdi+10h]
0x180006b2b  mov     edx, [rbp+47h+Source]
0x180006b2e  cmp     rdx, rax
0x180006b31  jbe     short loc_180006B74
0x180006b33  cmp     edx, eax
0x180006b35  jz      short loc_180006B74
0x180006b37  mov     edx, eax
0x180006b39  mov     [rbp+47h+Source], eax
0x180006b3c  mov     al, [rbp+47h+var_9E]
0x180006b3f  cmp     al, 1
0x180006b41  jnz     short loc_180006B56
0x180006b43  movzx   eax, dx
0x180006b46  mov     [rbp+47h+var_B0], dx
0x180006b4a  mov     r9d, 2
0x180006b50  lea     r8, [rbp+47h+var_B0]
0x180006b54  jmp     short loc_180006B64
0x180006b56  cmp     al, 2
0x180006b58  jnz     short loc_180006B74
0x180006b5a  mov     r9d, 4; SourceSize
0x180006b60  lea     r8, [rbp+47h+Source]; Source
0x180006b64  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006b68  mov     rdx, r9; DestinationSize
0x180006b6b  call    cs:__imp_memcpy_s
0x180006b71  mov     edx, [rbp+47h+Source]
0x180006b74  mov     ebx, edx
0x180006b76  imul    rbx, [rdi+10h]
0x180006b7b  add     rbx, rsi
0x180006b7e  jmp     loc_180006C0A
0x180006b83  movzx   eax, word ptr [rdi+6]
0x180006b87  xorps   xmm0, xmm0
0x180006b8a  mov     [rbp+47h+var_60], ax
0x180006b8e  mov     esi, r9d
0x180006b91  mov     al, [rdi+8]
0x180006b94  mov     [rbp+47h+var_5E], al
0x180006b97  mov     eax, [rbp+47h+Source]
0x180006b9a  mov     [rbp+47h+var_5C], r9d
0x180006b9e  mov     [rbp+47h+var_58], r9w
0x180006ba3  movdqu  [rbp+47h+var_50], xmm0
0x180006ba8  test    eax, eax
0x180006baa  jz      short loc_180006BCE
0x180006bac  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006bb0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006bb4  lea     rcx, [rbp+47h+var_60]; this
0x180006bb8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006bbd  test    al, al
0x180006bbf  mov     eax, [rbp+47h+Source]
0x180006bc2  jz      short loc_180006BCA
0x180006bc4  inc     esi
0x180006bc6  cmp     esi, eax
0x180006bc8  jb      short loc_180006BAC
0x180006bca  mov     rbx, [rbp+47h+var_A8]
0x180006bce  cmp     eax, esi
0x180006bd0  jz      short loc_180006C0A
0x180006bd2  mov     al, [rbp+47h+var_9E]
0x180006bd5  mov     [rbp+47h+Source], esi
0x180006bd8  cmp     al, 1
0x180006bda  jnz     short loc_180006BF0
0x180006bdc  mov     eax, 2
0x180006be1  mov     [rbp+47h+var_B0], si
0x180006be5  mov     r9d, eax
0x180006be8  lea     r8, [rbp+47h+var_B0]
0x180006bec  mov     edx, eax
0x180006bee  jmp     short loc_180006C00
0x180006bf0  cmp     al, 2
0x180006bf2  jnz     short loc_180006C0A
0x180006bf4  mov     edx, 4; DestinationSize
0x180006bf9  lea     r8, [rbp+47h+Source]; Source
0x180006bfd  mov     r9d, edx; SourceSize
0x180006c00  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006c04  call    cs:__imp_memcpy_s
0x180006c0a  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006c0e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006c12  lea     rcx, [rbp+47h+var_A0]; this
0x180006c16  mov     [rbp+47h+var_A8], rbx
0x180006c1a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006c1f  xor     r9d, r9d
0x180006c22  mov     sil, al
0x180006c25  test    al, al
0x180006c27  jnz     loc_180006AD6
0x180006c2d  mov     rbx, [rbp+47h+var_A8]
0x180006c31  mov     [rdi+20h], rbx
0x180006c35  mov     rcx, r9
0x180006c38  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180006c3c  jnz     loc_180006CC7
0x180006c42  movzx   eax, [rbp+47h+var_A0]
0x180006c46  mov     [rbp+47h+Source], 1
0x180006c4d  mov     [rbp+47h+var_98], r14w
0x180006c52  mov     [rbp+47h+Buf2], r9
0x180006c56  mov     [rbp+47h+Buf2+8], r15
0x180006c5a  test    ax, ax
0x180006c5d  jnz     short loc_180006CAF
0x180006c5f  movzx   ecx, r14w
0x180006c63  add     rcx, 2
0x180006c67  jmp     short loc_180006CB2
0x180006c69  mov     eax, [rbp+47h+arg_28]
0x180006c6c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180006c70  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180006c74  mov     r9, r13; void *
0x180006c77  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180006c7b  mov     rcx, rdi; this
0x180006c7e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180006c83  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180006c88  xor     r9d, r9d
0x180006c8b  mov     [rbp+47h+var_A8], rax
0x180006c8f  mov     rbx, rax
0x180006c92  test    rax, rax
0x180006c95  jnz     short loc_180006C9E
0x180006c97  mov     al, 1
0x180006c99  jmp     loc_180006DCC
0x180006c9e  mov     byte ptr [rbp+47h+arg_0], 1
0x180006ca2  jmp     short loc_180006CA8
0x180006ca4  mov     [rbp+47h+var_A8], rbx
0x180006ca8  test    sil, sil
0x180006cab  jnz     short loc_180006C35
0x180006cad  jmp     short loc_180006C31
0x180006caf  mov     rcx, rax
0x180006cb2  mov     al, [rbp+47h+var_9E]
0x180006cb5  cmp     al, 1
0x180006cb7  jnz     short loc_180006CBF
0x180006cb9  add     rcx, 2
0x180006cbd  jmp     short loc_180006CC7
0x180006cbf  cmp     al, 2
0x180006cc1  jnz     short loc_180006CC7
0x180006cc3  add     rcx, 4
0x180006cc7  movzx   eax, word ptr [rdi+6]
0x180006ccb  mov     dl, [rdi+8]
0x180006cce  mov     r8d, [rbp+47h+arg_28]
0x180006cd2  mov     [rbp+47h+var_80], ax
0x180006cd6  mov     [rbp+47h+var_7E], dl
0x180006cd9  mov     [rbp+47h+var_7C], r8d
0x180006cdd  mov     [rbp+47h+var_78], r12w
0x180006ce2  mov     [rbp+47h+var_70], r9
0x180006ce6  mov     [rbp+47h+var_68], r13
0x180006cea  test    ax, ax
0x180006ced  jnz     short loc_180006CF7
0x180006cef  movzx   eax, r12w
0x180006cf3  add     rax, 2
0x180006cf7  cmp     dl, 1
0x180006cfa  jnz     short loc_180006D02
0x180006cfc  add     rax, 2
0x180006d00  jmp     short loc_180006D0B
0x180006d02  cmp     dl, 2
0x180006d05  jnz     short loc_180006D0B
0x180006d07  add     rax, 4
0x180006d0b  mov     rdx, [rdi+28h]
0x180006d0f  lea     rsi, [rax+rcx]
0x180006d13  mov     r9, [rdi+20h]
0x180006d17  mov     rcx, rdx
0x180006d1a  sub     rcx, r9
0x180006d1d  cmp     r9, rdx
0x180006d20  sbb     rax, rax
0x180006d23  and     rax, rcx
0x180006d26  cmp     rax, rsi
0x180006d29  jb      loc_180006DCA
0x180006d2f  sub     rdx, rsi
0x180006d32  lea     rcx, [rsi+rbx]; Destination
0x180006d36  sub     rdx, rbx; DestinationSize
0x180006d39  sub     r9, rbx; SourceSize
0x180006d3c  mov     r8, rbx; Source
0x180006d3f  call    cs:__imp_memmove_s
0x180006d45  add     [rdi+20h], rsi
0x180006d49  xor     ebx, ebx
0x180006d4b  cmp     byte ptr [rbp+47h+arg_0], bl
0x180006d4e  jnz     short loc_180006D63
0x180006d50  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006d54  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006d58  lea     rcx, [rbp+47h+var_A0]; this
0x180006d5c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006d61  jmp     short loc_180006DB0
0x180006d63  mov     cl, [rbp+47h+var_9E]
0x180006d66  test    cl, cl
0x180006d68  jz      short loc_180006DB0
0x180006d6a  mov     eax, [rbp+47h+Source]
0x180006d6d  lea     r8d, [rax+1]
0x180006d71  cmp     eax, r8d
0x180006d74  jz      short loc_180006DB0
0x180006d76  mov     [rbp+47h+Source], r8d
0x180006d7a  cmp     cl, 1
0x180006d7d  jnz     short loc_180006D93
0x180006d7f  mov     r9d, 2
0x180006d85  mov     [rbp+47h+arg_0], r8w
0x180006d8a  mov     edx, r9d
0x180006d8d  lea     r8, [rbp+47h+arg_0]
0x180006d91  jmp     short loc_180006DA6
0x180006d93  cmp     cl, 2
0x180006d96  jnz     short loc_180006DB0
0x180006d98  mov     eax, 4
0x180006d9d  lea     r8, [rbp+47h+Source]; Source
0x180006da1  mov     r9d, eax; SourceSize
0x180006da4  mov     edx, eax; DestinationSize
0x180006da6  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006daa  call    cs:__imp_memcpy_s
0x180006db0  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006db4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006db8  lea     rcx, [rbp+47h+var_80]; this
0x180006dbc  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006dc1  mov     byte ptr [rdi+38h], 1
0x180006dc5  jmp     loc_180006C97
0x180006dca  xor     al, al
0x180006dcc  add     rsp, 0A8h
0x180006dd3  pop     r15
0x180006dd5  pop     r14
0x180006dd7  pop     r13
0x180006dd9  pop     r12
0x180006ddb  pop     rdi
0x180006ddc  pop     rsi
0x180006ddd  pop     rbx
0x180006dde  pop     rbp
0x180006ddf  retn
```

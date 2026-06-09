# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140006bfc`
- end: `0x140006f95`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `921`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140006a28`

## callees

- `0x1400049cc`
- `0x140006358`
- `0x140006bfc`
- `0x140008e38`
- `0x14004ad46`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140006d07`
- `msvcrt!memcpy_s` at `0x140006da6`
- `msvcrt!memcpy_s` at `0x140006f58`
- `msvcrt!memcpy_s` at `0x140006d07`
- `msvcrt!memcpy_s` at `0x140006da6`
- `msvcrt!memcpy_s` at `0x140006f58`
- `msvcrt!memmove_s` at `0x140006ee7`
- `msvcrt!memmove_s` at `0x140006ee7`

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
0x140006bfc  push    rbp
0x140006bfe  push    rbx
0x140006bff  push    rsi
0x140006c00  push    rdi
0x140006c01  push    r12
0x140006c03  push    r13
0x140006c05  push    r14
0x140006c07  push    r15
0x140006c09  lea     rbp, [rsp-0Fh]
0x140006c0e  sub     rsp, 0A8h
0x140006c15  mov     rbx, [rcx+18h]
0x140006c19  mov     rdi, rcx
0x140006c1c  xor     ecx, ecx
0x140006c1e  mov     r13, r9
0x140006c21  mov     r14, r8
0x140006c24  mov     r15, rdx
0x140006c27  test    rbx, rbx
0x140006c2a  jz      loc_140006F7E
0x140006c30  movzx   eax, word ptr [rdi+2]
0x140006c34  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140006c38  mov     r8, [rdi+20h]; unsigned __int8 *
0x140006c3c  add     rbx, 0Ah
0x140006c40  mov     [rbp+47h+var_A0], ax
0x140006c44  xorps   xmm0, xmm0
0x140006c47  mov     al, [rdi+4]
0x140006c4a  mov     [rbp+47h+Source], ecx
0x140006c4d  mov     [rbp+47h+var_98], cx
0x140006c51  mov     byte ptr [rbp+47h+arg_0], cl
0x140006c54  lea     rcx, [rbp+47h+var_A0]; this
0x140006c58  mov     [rbp+47h+var_9E], al
0x140006c5b  mov     [rbp+47h+var_A8], rbx
0x140006c5f  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x140006c64  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140006c69  mov     r12, [rbp+47h+arg_20]
0x140006c6d  jmp     loc_140006DC7
0x140006c72  movzx   eax, [rbp+47h+var_98]
0x140006c76  cmp     r14, rax
0x140006c79  jnz     short loc_140006C91
0x140006c7b  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x140006c7f  mov     r8, r14; Size
0x140006c82  mov     rcx, r15; Buf1
0x140006c85  call    memcmp_0
0x140006c8a  mov     ecx, eax
0x140006c8c  xor     r9d, r9d
0x140006c8f  jmp     short loc_140006C9A
0x140006c91  movzx   eax, [rbp+47h+var_98]
0x140006c95  mov     ecx, r14d
0x140006c98  sub     ecx, eax
0x140006c9a  test    ecx, ecx
0x140006c9c  js      loc_140006E4C
0x140006ca2  jz      loc_140006E11
0x140006ca8  mov     rbx, [rbp+47h+var_A8]
0x140006cac  mov     [rbp+47h+var_A8], rbx
0x140006cb0  cmp     [rdi+10h], r9
0x140006cb4  jbe     short loc_140006D25
0x140006cb6  mov     rax, [rdi+20h]
0x140006cba  xor     edx, edx
0x140006cbc  sub     rax, [rdi+18h]
0x140006cc0  mov     rsi, rbx
0x140006cc3  div     qword ptr [rdi+10h]
0x140006cc7  mov     edx, [rbp+47h+Source]
0x140006cca  cmp     rdx, rax
0x140006ccd  jbe     short loc_140006D16
0x140006ccf  cmp     edx, eax
0x140006cd1  jz      short loc_140006D16
0x140006cd3  mov     edx, eax
0x140006cd5  mov     [rbp+47h+Source], eax
0x140006cd8  mov     al, [rbp+47h+var_9E]
0x140006cdb  cmp     al, 1
0x140006cdd  jnz     short loc_140006CF2
0x140006cdf  movzx   eax, dx
0x140006ce2  mov     [rbp+47h+var_B0], dx
0x140006ce6  mov     r9d, 2
0x140006cec  lea     r8, [rbp+47h+var_B0]
0x140006cf0  jmp     short loc_140006D00
0x140006cf2  cmp     al, 2
0x140006cf4  jnz     short loc_140006D16
0x140006cf6  mov     r9d, 4; SourceSize
0x140006cfc  lea     r8, [rbp+47h+Source]; Source
0x140006d00  mov     rcx, [rbp+47h+Buf2]; Destination
0x140006d04  mov     rdx, r9; DestinationSize
0x140006d07  call    cs:__imp_memcpy_s
0x140006d0e  nop     dword ptr [rax+rax+00h]
0x140006d13  mov     edx, [rbp+47h+Source]
0x140006d16  mov     ebx, edx
0x140006d18  imul    rbx, [rdi+10h]
0x140006d1d  add     rbx, rsi
0x140006d20  jmp     loc_140006DB2
0x140006d25  movzx   eax, word ptr [rdi+6]
0x140006d29  xorps   xmm0, xmm0
0x140006d2c  mov     [rbp+47h+var_60], ax
0x140006d30  mov     esi, r9d
0x140006d33  mov     al, [rdi+8]
0x140006d36  mov     [rbp+47h+var_5E], al
0x140006d39  mov     eax, [rbp+47h+Source]
0x140006d3c  mov     [rbp+47h+var_5C], r9d
0x140006d40  mov     [rbp+47h+var_58], r9w
0x140006d45  movdqu  [rbp+47h+var_50], xmm0
0x140006d4a  test    eax, eax
0x140006d4c  jz      short loc_140006D70
0x140006d4e  mov     r8, [rdi+20h]; unsigned __int8 *
0x140006d52  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140006d56  lea     rcx, [rbp+47h+var_60]; this
0x140006d5a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140006d5f  test    al, al
0x140006d61  mov     eax, [rbp+47h+Source]
0x140006d64  jz      short loc_140006D6C
0x140006d66  inc     esi
0x140006d68  cmp     esi, eax
0x140006d6a  jb      short loc_140006D4E
0x140006d6c  mov     rbx, [rbp+47h+var_A8]
0x140006d70  cmp     eax, esi
0x140006d72  jz      short loc_140006DB2
0x140006d74  mov     al, [rbp+47h+var_9E]
0x140006d77  mov     [rbp+47h+Source], esi
0x140006d7a  cmp     al, 1
0x140006d7c  jnz     short loc_140006D92
0x140006d7e  mov     eax, 2
0x140006d83  mov     [rbp+47h+var_B0], si
0x140006d87  mov     r9d, eax
0x140006d8a  lea     r8, [rbp+47h+var_B0]
0x140006d8e  mov     edx, eax
0x140006d90  jmp     short loc_140006DA2
0x140006d92  cmp     al, 2
0x140006d94  jnz     short loc_140006DB2
0x140006d96  mov     edx, 4; DestinationSize
0x140006d9b  lea     r8, [rbp+47h+Source]; Source
0x140006d9f  mov     r9d, edx; SourceSize
0x140006da2  mov     rcx, [rbp+47h+Buf2]; Destination
0x140006da6  call    cs:__imp_memcpy_s
0x140006dad  nop     dword ptr [rax+rax+00h]
0x140006db2  mov     r8, [rdi+20h]; unsigned __int8 *
0x140006db6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140006dba  lea     rcx, [rbp+47h+var_A0]; this
0x140006dbe  mov     [rbp+47h+var_A8], rbx
0x140006dc2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140006dc7  xor     r9d, r9d
0x140006dca  mov     sil, al
0x140006dcd  test    al, al
0x140006dcf  jnz     loc_140006C72
0x140006dd5  mov     rbx, [rbp+47h+var_A8]
0x140006dd9  mov     [rdi+20h], rbx
0x140006ddd  mov     rcx, r9
0x140006de0  cmp     byte ptr [rbp+47h+arg_0], r9b
0x140006de4  jnz     loc_140006E6F
0x140006dea  movzx   eax, [rbp+47h+var_A0]
0x140006dee  mov     [rbp+47h+Source], 1
0x140006df5  mov     [rbp+47h+var_98], r14w
0x140006dfa  mov     [rbp+47h+Buf2], r9
0x140006dfe  mov     [rbp+47h+Buf2+8], r15
0x140006e02  test    ax, ax
0x140006e05  jnz     short loc_140006E57
0x140006e07  movzx   ecx, r14w
0x140006e0b  add     rcx, 2
0x140006e0f  jmp     short loc_140006E5A
0x140006e11  mov     eax, [rbp+47h+arg_28]
0x140006e14  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x140006e18  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x140006e1c  mov     r9, r13; void *
0x140006e1f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x140006e23  mov     rcx, rdi; this
0x140006e26  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x140006e2b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x140006e30  xor     r9d, r9d
0x140006e33  mov     [rbp+47h+var_A8], rax
0x140006e37  mov     rbx, rax
0x140006e3a  test    rax, rax
0x140006e3d  jnz     short loc_140006E46
0x140006e3f  mov     al, 1
0x140006e41  jmp     loc_140006F80
0x140006e46  mov     byte ptr [rbp+47h+arg_0], 1
0x140006e4a  jmp     short loc_140006E50
0x140006e4c  mov     [rbp+47h+var_A8], rbx
0x140006e50  test    sil, sil
0x140006e53  jnz     short loc_140006DDD
0x140006e55  jmp     short loc_140006DD9
0x140006e57  mov     rcx, rax
0x140006e5a  mov     al, [rbp+47h+var_9E]
0x140006e5d  cmp     al, 1
0x140006e5f  jnz     short loc_140006E67
0x140006e61  add     rcx, 2
0x140006e65  jmp     short loc_140006E6F
0x140006e67  cmp     al, 2
0x140006e69  jnz     short loc_140006E6F
0x140006e6b  add     rcx, 4
0x140006e6f  movzx   eax, word ptr [rdi+6]
0x140006e73  mov     dl, [rdi+8]
0x140006e76  mov     r8d, [rbp+47h+arg_28]
0x140006e7a  mov     [rbp+47h+var_80], ax
0x140006e7e  mov     [rbp+47h+var_7E], dl
0x140006e81  mov     [rbp+47h+var_7C], r8d
0x140006e85  mov     [rbp+47h+var_78], r12w
0x140006e8a  mov     [rbp+47h+var_70], r9
0x140006e8e  mov     [rbp+47h+var_68], r13
0x140006e92  test    ax, ax
0x140006e95  jnz     short loc_140006E9F
0x140006e97  movzx   eax, r12w
0x140006e9b  add     rax, 2
0x140006e9f  cmp     dl, 1
0x140006ea2  jnz     short loc_140006EAA
0x140006ea4  add     rax, 2
0x140006ea8  jmp     short loc_140006EB3
0x140006eaa  cmp     dl, 2
0x140006ead  jnz     short loc_140006EB3
0x140006eaf  add     rax, 4
0x140006eb3  mov     rdx, [rdi+28h]
0x140006eb7  lea     rsi, [rax+rcx]
0x140006ebb  mov     r9, [rdi+20h]
0x140006ebf  mov     rcx, rdx
0x140006ec2  sub     rcx, r9
0x140006ec5  cmp     r9, rdx
0x140006ec8  sbb     rax, rax
0x140006ecb  and     rax, rcx
0x140006ece  cmp     rax, rsi
0x140006ed1  jb      loc_140006F7E
0x140006ed7  sub     rdx, rsi
0x140006eda  lea     rcx, [rsi+rbx]; Destination
0x140006ede  sub     rdx, rbx; DestinationSize
0x140006ee1  sub     r9, rbx; SourceSize
0x140006ee4  mov     r8, rbx; Source
0x140006ee7  call    cs:__imp_memmove_s
0x140006eee  nop     dword ptr [rax+rax+00h]
0x140006ef3  add     [rdi+20h], rsi
0x140006ef7  xor     ebx, ebx
0x140006ef9  cmp     byte ptr [rbp+47h+arg_0], bl
0x140006efc  jnz     short loc_140006F11
0x140006efe  mov     r8, [rdi+20h]; unsigned __int8 *
0x140006f02  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140006f06  lea     rcx, [rbp+47h+var_A0]; this
0x140006f0a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140006f0f  jmp     short loc_140006F64
0x140006f11  mov     cl, [rbp+47h+var_9E]
0x140006f14  test    cl, cl
0x140006f16  jz      short loc_140006F64
0x140006f18  mov     eax, [rbp+47h+Source]
0x140006f1b  lea     r8d, [rax+1]
0x140006f1f  cmp     eax, r8d
0x140006f22  jz      short loc_140006F64
0x140006f24  mov     [rbp+47h+Source], r8d
0x140006f28  cmp     cl, 1
0x140006f2b  jnz     short loc_140006F41
0x140006f2d  mov     r9d, 2
0x140006f33  mov     [rbp+47h+arg_0], r8w
0x140006f38  mov     edx, r9d
0x140006f3b  lea     r8, [rbp+47h+arg_0]
0x140006f3f  jmp     short loc_140006F54
0x140006f41  cmp     cl, 2
0x140006f44  jnz     short loc_140006F64
0x140006f46  mov     eax, 4
0x140006f4b  lea     r8, [rbp+47h+Source]; Source
0x140006f4f  mov     r9d, eax; SourceSize
0x140006f52  mov     edx, eax; DestinationSize
0x140006f54  mov     rcx, [rbp+47h+Buf2]; Destination
0x140006f58  call    cs:__imp_memcpy_s
0x140006f5f  nop     dword ptr [rax+rax+00h]
0x140006f64  mov     r8, [rdi+20h]; unsigned __int8 *
0x140006f68  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140006f6c  lea     rcx, [rbp+47h+var_80]; this
0x140006f70  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140006f75  mov     byte ptr [rdi+38h], 1
0x140006f79  jmp     loc_140006E3F
0x140006f7e  xor     al, al
0x140006f80  add     rsp, 0A8h
0x140006f87  pop     r15
0x140006f89  pop     r14
0x140006f8b  pop     r13
0x140006f8d  pop     r12
0x140006f8f  pop     rdi
0x140006f90  pop     rsi
0x140006f91  pop     rbx
0x140006f92  pop     rbp
0x140006f93  retn
```

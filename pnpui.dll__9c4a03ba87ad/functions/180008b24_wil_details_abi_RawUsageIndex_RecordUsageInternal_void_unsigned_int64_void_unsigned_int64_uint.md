# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180008b24`
- end: `0x180008ea4`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008974`

## callees

- `0x180005c58`
- `0x180008308`
- `0x180008b24`
- `0x18000a48c`
- `0x18000ccc6`

## import_xrefs

- `msvcrt!memmove_s` at `0x180008e03`
- `msvcrt!memmove_s` at `0x180008e03`
- `msvcrt!memcpy_s` at `0x180008c2f`
- `msvcrt!memcpy_s` at `0x180008cc8`
- `msvcrt!memcpy_s` at `0x180008e6e`
- `msvcrt!memcpy_s` at `0x180008c2f`
- `msvcrt!memcpy_s` at `0x180008cc8`
- `msvcrt!memcpy_s` at `0x180008e6e`

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
0x180008b24  push    rbp
0x180008b26  push    rbx
0x180008b27  push    rsi
0x180008b28  push    rdi
0x180008b29  push    r12
0x180008b2b  push    r13
0x180008b2d  push    r14
0x180008b2f  push    r15
0x180008b31  lea     rbp, [rsp-0Fh]
0x180008b36  sub     rsp, 0A8h
0x180008b3d  mov     rbx, [rcx+18h]
0x180008b41  mov     rdi, rcx
0x180008b44  xor     ecx, ecx
0x180008b46  mov     r13, r9
0x180008b49  mov     r14, r8
0x180008b4c  mov     r15, rdx
0x180008b4f  test    rbx, rbx
0x180008b52  jz      loc_180008E8E
0x180008b58  movzx   eax, word ptr [rdi+2]
0x180008b5c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008b60  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008b64  add     rbx, 0Ah
0x180008b68  mov     [rbp+47h+var_A0], ax
0x180008b6c  xorps   xmm0, xmm0
0x180008b6f  mov     al, [rdi+4]
0x180008b72  mov     [rbp+47h+Source], ecx
0x180008b75  mov     [rbp+47h+var_98], cx
0x180008b79  mov     byte ptr [rbp+47h+arg_0], cl
0x180008b7c  lea     rcx, [rbp+47h+var_A0]; this
0x180008b80  mov     [rbp+47h+var_9E], al
0x180008b83  mov     [rbp+47h+var_A8], rbx
0x180008b87  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180008b8c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008b91  mov     r12, [rbp+47h+arg_20]
0x180008b95  jmp     loc_180008CE3
0x180008b9a  movzx   eax, [rbp+47h+var_98]
0x180008b9e  cmp     r14, rax
0x180008ba1  jnz     short loc_180008BB9
0x180008ba3  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180008ba7  mov     r8, r14; Size
0x180008baa  mov     rcx, r15; Buf1
0x180008bad  call    memcmp_0
0x180008bb2  mov     ecx, eax
0x180008bb4  xor     r9d, r9d
0x180008bb7  jmp     short loc_180008BC2
0x180008bb9  movzx   eax, [rbp+47h+var_98]
0x180008bbd  mov     ecx, r14d
0x180008bc0  sub     ecx, eax
0x180008bc2  test    ecx, ecx
0x180008bc4  js      loc_180008D68
0x180008bca  jz      loc_180008D2D
0x180008bd0  mov     rbx, [rbp+47h+var_A8]
0x180008bd4  mov     [rbp+47h+var_A8], rbx
0x180008bd8  cmp     [rdi+10h], r9
0x180008bdc  jbe     short loc_180008C47
0x180008bde  mov     rax, [rdi+20h]
0x180008be2  xor     edx, edx
0x180008be4  sub     rax, [rdi+18h]
0x180008be8  mov     rsi, rbx
0x180008beb  div     qword ptr [rdi+10h]
0x180008bef  mov     edx, [rbp+47h+Source]
0x180008bf2  cmp     rdx, rax
0x180008bf5  jbe     short loc_180008C38
0x180008bf7  cmp     edx, eax
0x180008bf9  jz      short loc_180008C38
0x180008bfb  mov     edx, eax
0x180008bfd  mov     [rbp+47h+Source], eax
0x180008c00  mov     al, [rbp+47h+var_9E]
0x180008c03  cmp     al, 1
0x180008c05  jnz     short loc_180008C1A
0x180008c07  movzx   eax, dx
0x180008c0a  mov     [rbp+47h+var_B0], dx
0x180008c0e  mov     r9d, 2
0x180008c14  lea     r8, [rbp+47h+var_B0]
0x180008c18  jmp     short loc_180008C28
0x180008c1a  cmp     al, 2
0x180008c1c  jnz     short loc_180008C38
0x180008c1e  mov     r9d, 4; SourceSize
0x180008c24  lea     r8, [rbp+47h+Source]; Source
0x180008c28  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008c2c  mov     rdx, r9; DestinationSize
0x180008c2f  call    cs:__imp_memcpy_s
0x180008c35  mov     edx, [rbp+47h+Source]
0x180008c38  mov     ebx, edx
0x180008c3a  imul    rbx, [rdi+10h]
0x180008c3f  add     rbx, rsi
0x180008c42  jmp     loc_180008CCE
0x180008c47  movzx   eax, word ptr [rdi+6]
0x180008c4b  xorps   xmm0, xmm0
0x180008c4e  mov     [rbp+47h+var_60], ax
0x180008c52  mov     esi, r9d
0x180008c55  mov     al, [rdi+8]
0x180008c58  mov     [rbp+47h+var_5E], al
0x180008c5b  mov     eax, [rbp+47h+Source]
0x180008c5e  mov     [rbp+47h+var_5C], r9d
0x180008c62  mov     [rbp+47h+var_58], r9w
0x180008c67  movdqu  [rbp+47h+var_50], xmm0
0x180008c6c  test    eax, eax
0x180008c6e  jz      short loc_180008C92
0x180008c70  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008c74  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008c78  lea     rcx, [rbp+47h+var_60]; this
0x180008c7c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008c81  test    al, al
0x180008c83  mov     eax, [rbp+47h+Source]
0x180008c86  jz      short loc_180008C8E
0x180008c88  inc     esi
0x180008c8a  cmp     esi, eax
0x180008c8c  jb      short loc_180008C70
0x180008c8e  mov     rbx, [rbp+47h+var_A8]
0x180008c92  cmp     eax, esi
0x180008c94  jz      short loc_180008CCE
0x180008c96  mov     al, [rbp+47h+var_9E]
0x180008c99  mov     [rbp+47h+Source], esi
0x180008c9c  cmp     al, 1
0x180008c9e  jnz     short loc_180008CB4
0x180008ca0  mov     eax, 2
0x180008ca5  mov     [rbp+47h+var_B0], si
0x180008ca9  mov     r9d, eax
0x180008cac  lea     r8, [rbp+47h+var_B0]
0x180008cb0  mov     edx, eax
0x180008cb2  jmp     short loc_180008CC4
0x180008cb4  cmp     al, 2
0x180008cb6  jnz     short loc_180008CCE
0x180008cb8  mov     edx, 4; DestinationSize
0x180008cbd  lea     r8, [rbp+47h+Source]; Source
0x180008cc1  mov     r9d, edx; SourceSize
0x180008cc4  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008cc8  call    cs:__imp_memcpy_s
0x180008cce  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008cd2  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008cd6  lea     rcx, [rbp+47h+var_A0]; this
0x180008cda  mov     [rbp+47h+var_A8], rbx
0x180008cde  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008ce3  xor     r9d, r9d
0x180008ce6  mov     sil, al
0x180008ce9  test    al, al
0x180008ceb  jnz     loc_180008B9A
0x180008cf1  mov     rbx, [rbp+47h+var_A8]
0x180008cf5  mov     [rdi+20h], rbx
0x180008cf9  mov     rcx, r9
0x180008cfc  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180008d00  jnz     loc_180008D8B
0x180008d06  movzx   eax, [rbp+47h+var_A0]
0x180008d0a  mov     [rbp+47h+Source], 1
0x180008d11  mov     [rbp+47h+var_98], r14w
0x180008d16  mov     [rbp+47h+Buf2], r9
0x180008d1a  mov     [rbp+47h+Buf2+8], r15
0x180008d1e  test    ax, ax
0x180008d21  jnz     short loc_180008D73
0x180008d23  movzx   ecx, r14w
0x180008d27  add     rcx, 2
0x180008d2b  jmp     short loc_180008D76
0x180008d2d  mov     eax, [rbp+47h+arg_28]
0x180008d30  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180008d34  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180008d38  mov     r9, r13; void *
0x180008d3b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180008d3f  mov     rcx, rdi; this
0x180008d42  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180008d47  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180008d4c  xor     r9d, r9d
0x180008d4f  mov     [rbp+47h+var_A8], rax
0x180008d53  mov     rbx, rax
0x180008d56  test    rax, rax
0x180008d59  jnz     short loc_180008D62
0x180008d5b  mov     al, 1
0x180008d5d  jmp     loc_180008E90
0x180008d62  mov     byte ptr [rbp+47h+arg_0], 1
0x180008d66  jmp     short loc_180008D6C
0x180008d68  mov     [rbp+47h+var_A8], rbx
0x180008d6c  test    sil, sil
0x180008d6f  jnz     short loc_180008CF9
0x180008d71  jmp     short loc_180008CF5
0x180008d73  mov     rcx, rax
0x180008d76  mov     al, [rbp+47h+var_9E]
0x180008d79  cmp     al, 1
0x180008d7b  jnz     short loc_180008D83
0x180008d7d  add     rcx, 2
0x180008d81  jmp     short loc_180008D8B
0x180008d83  cmp     al, 2
0x180008d85  jnz     short loc_180008D8B
0x180008d87  add     rcx, 4
0x180008d8b  movzx   eax, word ptr [rdi+6]
0x180008d8f  mov     dl, [rdi+8]
0x180008d92  mov     r8d, [rbp+47h+arg_28]
0x180008d96  mov     [rbp+47h+var_80], ax
0x180008d9a  mov     [rbp+47h+var_7E], dl
0x180008d9d  mov     [rbp+47h+var_7C], r8d
0x180008da1  mov     [rbp+47h+var_78], r12w
0x180008da6  mov     [rbp+47h+var_70], r9
0x180008daa  mov     [rbp+47h+var_68], r13
0x180008dae  test    ax, ax
0x180008db1  jnz     short loc_180008DBB
0x180008db3  movzx   eax, r12w
0x180008db7  add     rax, 2
0x180008dbb  cmp     dl, 1
0x180008dbe  jnz     short loc_180008DC6
0x180008dc0  add     rax, 2
0x180008dc4  jmp     short loc_180008DCF
0x180008dc6  cmp     dl, 2
0x180008dc9  jnz     short loc_180008DCF
0x180008dcb  add     rax, 4
0x180008dcf  mov     rdx, [rdi+28h]
0x180008dd3  lea     rsi, [rax+rcx]
0x180008dd7  mov     r9, [rdi+20h]
0x180008ddb  mov     rcx, rdx
0x180008dde  sub     rcx, r9
0x180008de1  cmp     r9, rdx
0x180008de4  sbb     rax, rax
0x180008de7  and     rax, rcx
0x180008dea  cmp     rax, rsi
0x180008ded  jb      loc_180008E8E
0x180008df3  sub     rdx, rsi
0x180008df6  lea     rcx, [rsi+rbx]; Destination
0x180008dfa  sub     rdx, rbx; DestinationSize
0x180008dfd  sub     r9, rbx; SourceSize
0x180008e00  mov     r8, rbx; Source
0x180008e03  call    cs:__imp_memmove_s
0x180008e09  add     [rdi+20h], rsi
0x180008e0d  xor     ebx, ebx
0x180008e0f  cmp     byte ptr [rbp+47h+arg_0], bl
0x180008e12  jnz     short loc_180008E27
0x180008e14  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008e18  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008e1c  lea     rcx, [rbp+47h+var_A0]; this
0x180008e20  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180008e25  jmp     short loc_180008E74
0x180008e27  mov     cl, [rbp+47h+var_9E]
0x180008e2a  test    cl, cl
0x180008e2c  jz      short loc_180008E74
0x180008e2e  mov     eax, [rbp+47h+Source]
0x180008e31  lea     r8d, [rax+1]
0x180008e35  cmp     eax, r8d
0x180008e38  jz      short loc_180008E74
0x180008e3a  mov     [rbp+47h+Source], r8d
0x180008e3e  cmp     cl, 1
0x180008e41  jnz     short loc_180008E57
0x180008e43  mov     r9d, 2
0x180008e49  mov     [rbp+47h+arg_0], r8w
0x180008e4e  mov     edx, r9d
0x180008e51  lea     r8, [rbp+47h+arg_0]
0x180008e55  jmp     short loc_180008E6A
0x180008e57  cmp     cl, 2
0x180008e5a  jnz     short loc_180008E74
0x180008e5c  mov     eax, 4
0x180008e61  lea     r8, [rbp+47h+Source]; Source
0x180008e65  mov     r9d, eax; SourceSize
0x180008e68  mov     edx, eax; DestinationSize
0x180008e6a  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008e6e  call    cs:__imp_memcpy_s
0x180008e74  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008e78  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180008e7c  lea     rcx, [rbp+47h+var_80]; this
0x180008e80  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180008e85  mov     byte ptr [rdi+38h], 1
0x180008e89  jmp     loc_180008D5B
0x180008e8e  xor     al, al
0x180008e90  add     rsp, 0A8h
0x180008e97  pop     r15
0x180008e99  pop     r14
0x180008e9b  pop     r13
0x180008e9d  pop     r12
0x180008e9f  pop     rdi
0x180008ea0  pop     rsi
0x180008ea1  pop     rbx
0x180008ea2  pop     rbp
0x180008ea3  retn
```

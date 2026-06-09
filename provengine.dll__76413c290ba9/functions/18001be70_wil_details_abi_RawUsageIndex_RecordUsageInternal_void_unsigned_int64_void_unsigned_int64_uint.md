# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001be70`
- end: `0x18001c1f0`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001bcc0`

## callees

- `0x1800136d4`
- `0x18001b608`
- `0x18001be70`
- `0x180020a14`
- `0x1800436f6`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001c14f`
- `msvcrt!memmove_s` at `0x18001c14f`
- `msvcrt!memcpy_s` at `0x18001bf7b`
- `msvcrt!memcpy_s` at `0x18001c014`
- `msvcrt!memcpy_s` at `0x18001c1ba`
- `msvcrt!memcpy_s` at `0x18001bf7b`
- `msvcrt!memcpy_s` at `0x18001c014`
- `msvcrt!memcpy_s` at `0x18001c1ba`

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
0x18001be70  push    rbp
0x18001be72  push    rbx
0x18001be73  push    rsi
0x18001be74  push    rdi
0x18001be75  push    r12
0x18001be77  push    r13
0x18001be79  push    r14
0x18001be7b  push    r15
0x18001be7d  lea     rbp, [rsp-0Fh]
0x18001be82  sub     rsp, 0A8h
0x18001be89  mov     rbx, [rcx+18h]
0x18001be8d  mov     rdi, rcx
0x18001be90  xor     ecx, ecx
0x18001be92  mov     r13, r9
0x18001be95  mov     r14, r8
0x18001be98  mov     r15, rdx
0x18001be9b  test    rbx, rbx
0x18001be9e  jz      loc_18001C1DA
0x18001bea4  movzx   eax, word ptr [rdi+2]
0x18001bea8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001beac  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001beb0  add     rbx, 0Ah
0x18001beb4  mov     [rbp+47h+var_A0], ax
0x18001beb8  xorps   xmm0, xmm0
0x18001bebb  mov     al, [rdi+4]
0x18001bebe  mov     [rbp+47h+Source], ecx
0x18001bec1  mov     [rbp+47h+var_98], cx
0x18001bec5  mov     byte ptr [rbp+47h+arg_0], cl
0x18001bec8  lea     rcx, [rbp+47h+var_A0]; this
0x18001becc  mov     [rbp+47h+var_9E], al
0x18001becf  mov     [rbp+47h+var_A8], rbx
0x18001bed3  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18001bed8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001bedd  mov     r12, [rbp+47h+arg_20]
0x18001bee1  jmp     loc_18001C02F
0x18001bee6  movzx   eax, [rbp+47h+var_98]
0x18001beea  cmp     r14, rax
0x18001beed  jnz     short loc_18001BF05
0x18001beef  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18001bef3  mov     r8, r14; Size
0x18001bef6  mov     rcx, r15; Buf1
0x18001bef9  call    memcmp_0
0x18001befe  mov     ecx, eax
0x18001bf00  xor     r9d, r9d
0x18001bf03  jmp     short loc_18001BF0E
0x18001bf05  movzx   eax, [rbp+47h+var_98]
0x18001bf09  mov     ecx, r14d
0x18001bf0c  sub     ecx, eax
0x18001bf0e  test    ecx, ecx
0x18001bf10  js      loc_18001C0B4
0x18001bf16  jz      loc_18001C079
0x18001bf1c  mov     rbx, [rbp+47h+var_A8]
0x18001bf20  mov     [rbp+47h+var_A8], rbx
0x18001bf24  cmp     [rdi+10h], r9
0x18001bf28  jbe     short loc_18001BF93
0x18001bf2a  mov     rax, [rdi+20h]
0x18001bf2e  xor     edx, edx
0x18001bf30  sub     rax, [rdi+18h]
0x18001bf34  mov     rsi, rbx
0x18001bf37  div     qword ptr [rdi+10h]
0x18001bf3b  mov     edx, [rbp+47h+Source]
0x18001bf3e  cmp     rdx, rax
0x18001bf41  jbe     short loc_18001BF84
0x18001bf43  cmp     edx, eax
0x18001bf45  jz      short loc_18001BF84
0x18001bf47  mov     edx, eax
0x18001bf49  mov     [rbp+47h+Source], eax
0x18001bf4c  mov     al, [rbp+47h+var_9E]
0x18001bf4f  cmp     al, 1
0x18001bf51  jnz     short loc_18001BF66
0x18001bf53  movzx   eax, dx
0x18001bf56  mov     [rbp+47h+var_B0], dx
0x18001bf5a  mov     r9d, 2
0x18001bf60  lea     r8, [rbp+47h+var_B0]
0x18001bf64  jmp     short loc_18001BF74
0x18001bf66  cmp     al, 2
0x18001bf68  jnz     short loc_18001BF84
0x18001bf6a  mov     r9d, 4; SourceSize
0x18001bf70  lea     r8, [rbp+47h+Source]; Source
0x18001bf74  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001bf78  mov     rdx, r9; DestinationSize
0x18001bf7b  call    cs:__imp_memcpy_s
0x18001bf81  mov     edx, [rbp+47h+Source]
0x18001bf84  mov     ebx, edx
0x18001bf86  imul    rbx, [rdi+10h]
0x18001bf8b  add     rbx, rsi
0x18001bf8e  jmp     loc_18001C01A
0x18001bf93  movzx   eax, word ptr [rdi+6]
0x18001bf97  xorps   xmm0, xmm0
0x18001bf9a  mov     [rbp+47h+var_60], ax
0x18001bf9e  mov     esi, r9d
0x18001bfa1  mov     al, [rdi+8]
0x18001bfa4  mov     [rbp+47h+var_5E], al
0x18001bfa7  mov     eax, [rbp+47h+Source]
0x18001bfaa  mov     [rbp+47h+var_5C], r9d
0x18001bfae  mov     [rbp+47h+var_58], r9w
0x18001bfb3  movdqu  [rbp+47h+var_50], xmm0
0x18001bfb8  test    eax, eax
0x18001bfba  jz      short loc_18001BFDE
0x18001bfbc  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001bfc0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001bfc4  lea     rcx, [rbp+47h+var_60]; this
0x18001bfc8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001bfcd  test    al, al
0x18001bfcf  mov     eax, [rbp+47h+Source]
0x18001bfd2  jz      short loc_18001BFDA
0x18001bfd4  inc     esi
0x18001bfd6  cmp     esi, eax
0x18001bfd8  jb      short loc_18001BFBC
0x18001bfda  mov     rbx, [rbp+47h+var_A8]
0x18001bfde  cmp     eax, esi
0x18001bfe0  jz      short loc_18001C01A
0x18001bfe2  mov     al, [rbp+47h+var_9E]
0x18001bfe5  mov     [rbp+47h+Source], esi
0x18001bfe8  cmp     al, 1
0x18001bfea  jnz     short loc_18001C000
0x18001bfec  mov     eax, 2
0x18001bff1  mov     [rbp+47h+var_B0], si
0x18001bff5  mov     r9d, eax
0x18001bff8  lea     r8, [rbp+47h+var_B0]
0x18001bffc  mov     edx, eax
0x18001bffe  jmp     short loc_18001C010
0x18001c000  cmp     al, 2
0x18001c002  jnz     short loc_18001C01A
0x18001c004  mov     edx, 4; DestinationSize
0x18001c009  lea     r8, [rbp+47h+Source]; Source
0x18001c00d  mov     r9d, edx; SourceSize
0x18001c010  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001c014  call    cs:__imp_memcpy_s
0x18001c01a  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001c01e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001c022  lea     rcx, [rbp+47h+var_A0]; this
0x18001c026  mov     [rbp+47h+var_A8], rbx
0x18001c02a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001c02f  xor     r9d, r9d
0x18001c032  mov     sil, al
0x18001c035  test    al, al
0x18001c037  jnz     loc_18001BEE6
0x18001c03d  mov     rbx, [rbp+47h+var_A8]
0x18001c041  mov     [rdi+20h], rbx
0x18001c045  mov     rcx, r9
0x18001c048  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18001c04c  jnz     loc_18001C0D7
0x18001c052  movzx   eax, [rbp+47h+var_A0]
0x18001c056  mov     [rbp+47h+Source], 1
0x18001c05d  mov     [rbp+47h+var_98], r14w
0x18001c062  mov     [rbp+47h+Buf2], r9
0x18001c066  mov     [rbp+47h+Buf2+8], r15
0x18001c06a  test    ax, ax
0x18001c06d  jnz     short loc_18001C0BF
0x18001c06f  movzx   ecx, r14w
0x18001c073  add     rcx, 2
0x18001c077  jmp     short loc_18001C0C2
0x18001c079  mov     eax, [rbp+47h+arg_28]
0x18001c07c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18001c080  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18001c084  mov     r9, r13; void *
0x18001c087  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18001c08b  mov     rcx, rdi; this
0x18001c08e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18001c093  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001c098  xor     r9d, r9d
0x18001c09b  mov     [rbp+47h+var_A8], rax
0x18001c09f  mov     rbx, rax
0x18001c0a2  test    rax, rax
0x18001c0a5  jnz     short loc_18001C0AE
0x18001c0a7  mov     al, 1
0x18001c0a9  jmp     loc_18001C1DC
0x18001c0ae  mov     byte ptr [rbp+47h+arg_0], 1
0x18001c0b2  jmp     short loc_18001C0B8
0x18001c0b4  mov     [rbp+47h+var_A8], rbx
0x18001c0b8  test    sil, sil
0x18001c0bb  jnz     short loc_18001C045
0x18001c0bd  jmp     short loc_18001C041
0x18001c0bf  mov     rcx, rax
0x18001c0c2  mov     al, [rbp+47h+var_9E]
0x18001c0c5  cmp     al, 1
0x18001c0c7  jnz     short loc_18001C0CF
0x18001c0c9  add     rcx, 2
0x18001c0cd  jmp     short loc_18001C0D7
0x18001c0cf  cmp     al, 2
0x18001c0d1  jnz     short loc_18001C0D7
0x18001c0d3  add     rcx, 4
0x18001c0d7  movzx   eax, word ptr [rdi+6]
0x18001c0db  mov     dl, [rdi+8]
0x18001c0de  mov     r8d, [rbp+47h+arg_28]
0x18001c0e2  mov     [rbp+47h+var_80], ax
0x18001c0e6  mov     [rbp+47h+var_7E], dl
0x18001c0e9  mov     [rbp+47h+var_7C], r8d
0x18001c0ed  mov     [rbp+47h+var_78], r12w
0x18001c0f2  mov     [rbp+47h+var_70], r9
0x18001c0f6  mov     [rbp+47h+var_68], r13
0x18001c0fa  test    ax, ax
0x18001c0fd  jnz     short loc_18001C107
0x18001c0ff  movzx   eax, r12w
0x18001c103  add     rax, 2
0x18001c107  cmp     dl, 1
0x18001c10a  jnz     short loc_18001C112
0x18001c10c  add     rax, 2
0x18001c110  jmp     short loc_18001C11B
0x18001c112  cmp     dl, 2
0x18001c115  jnz     short loc_18001C11B
0x18001c117  add     rax, 4
0x18001c11b  mov     rdx, [rdi+28h]
0x18001c11f  lea     rsi, [rax+rcx]
0x18001c123  mov     r9, [rdi+20h]
0x18001c127  mov     rcx, rdx
0x18001c12a  sub     rcx, r9
0x18001c12d  cmp     r9, rdx
0x18001c130  sbb     rax, rax
0x18001c133  and     rax, rcx
0x18001c136  cmp     rax, rsi
0x18001c139  jb      loc_18001C1DA
0x18001c13f  sub     rdx, rsi
0x18001c142  lea     rcx, [rsi+rbx]; Destination
0x18001c146  sub     rdx, rbx; DestinationSize
0x18001c149  sub     r9, rbx; SourceSize
0x18001c14c  mov     r8, rbx; Source
0x18001c14f  call    cs:__imp_memmove_s
0x18001c155  add     [rdi+20h], rsi
0x18001c159  xor     ebx, ebx
0x18001c15b  cmp     byte ptr [rbp+47h+arg_0], bl
0x18001c15e  jnz     short loc_18001C173
0x18001c160  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001c164  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001c168  lea     rcx, [rbp+47h+var_A0]; this
0x18001c16c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001c171  jmp     short loc_18001C1C0
0x18001c173  mov     cl, [rbp+47h+var_9E]
0x18001c176  test    cl, cl
0x18001c178  jz      short loc_18001C1C0
0x18001c17a  mov     eax, [rbp+47h+Source]
0x18001c17d  lea     r8d, [rax+1]
0x18001c181  cmp     eax, r8d
0x18001c184  jz      short loc_18001C1C0
0x18001c186  mov     [rbp+47h+Source], r8d
0x18001c18a  cmp     cl, 1
0x18001c18d  jnz     short loc_18001C1A3
0x18001c18f  mov     r9d, 2
0x18001c195  mov     [rbp+47h+arg_0], r8w
0x18001c19a  mov     edx, r9d
0x18001c19d  lea     r8, [rbp+47h+arg_0]
0x18001c1a1  jmp     short loc_18001C1B6
0x18001c1a3  cmp     cl, 2
0x18001c1a6  jnz     short loc_18001C1C0
0x18001c1a8  mov     eax, 4
0x18001c1ad  lea     r8, [rbp+47h+Source]; Source
0x18001c1b1  mov     r9d, eax; SourceSize
0x18001c1b4  mov     edx, eax; DestinationSize
0x18001c1b6  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001c1ba  call    cs:__imp_memcpy_s
0x18001c1c0  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001c1c4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001c1c8  lea     rcx, [rbp+47h+var_80]; this
0x18001c1cc  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001c1d1  mov     byte ptr [rdi+38h], 1
0x18001c1d5  jmp     loc_18001C0A7
0x18001c1da  xor     al, al
0x18001c1dc  add     rsp, 0A8h
0x18001c1e3  pop     r15
0x18001c1e5  pop     r14
0x18001c1e7  pop     r13
0x18001c1e9  pop     r12
0x18001c1eb  pop     rdi
0x18001c1ec  pop     rsi
0x18001c1ed  pop     rbx
0x18001c1ee  pop     rbp
0x18001c1ef  retn
```

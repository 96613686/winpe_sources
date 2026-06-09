# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000b060`
- end: `0x18000b3e0`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000aeb0`

## callees

- `0x18000930c`
- `0x18000aa2c`
- `0x18000b060`
- `0x18000c95c`
- `0x18000d886`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b16b`
- `msvcrt!memcpy_s` at `0x18000b204`
- `msvcrt!memcpy_s` at `0x18000b3aa`
- `msvcrt!memcpy_s` at `0x18000b16b`
- `msvcrt!memcpy_s` at `0x18000b204`
- `msvcrt!memcpy_s` at `0x18000b3aa`
- `msvcrt!memmove_s` at `0x18000b33f`
- `msvcrt!memmove_s` at `0x18000b33f`

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
0x18000b060  push    rbp
0x18000b062  push    rbx
0x18000b063  push    rsi
0x18000b064  push    rdi
0x18000b065  push    r12
0x18000b067  push    r13
0x18000b069  push    r14
0x18000b06b  push    r15
0x18000b06d  lea     rbp, [rsp-0Fh]
0x18000b072  sub     rsp, 0A8h
0x18000b079  mov     rbx, [rcx+18h]
0x18000b07d  mov     rdi, rcx
0x18000b080  xor     ecx, ecx
0x18000b082  mov     r13, r9
0x18000b085  mov     r14, r8
0x18000b088  mov     r15, rdx
0x18000b08b  test    rbx, rbx
0x18000b08e  jz      loc_18000B3CA
0x18000b094  movzx   eax, word ptr [rdi+2]
0x18000b098  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b09c  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b0a0  add     rbx, 0Ah
0x18000b0a4  mov     [rbp+47h+var_A0], ax
0x18000b0a8  xorps   xmm0, xmm0
0x18000b0ab  mov     al, [rdi+4]
0x18000b0ae  mov     [rbp+47h+Source], ecx
0x18000b0b1  mov     [rbp+47h+var_98], cx
0x18000b0b5  mov     byte ptr [rbp+47h+arg_0], cl
0x18000b0b8  lea     rcx, [rbp+47h+var_A0]; this
0x18000b0bc  mov     [rbp+47h+var_9E], al
0x18000b0bf  mov     [rbp+47h+var_A8], rbx
0x18000b0c3  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000b0c8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b0cd  mov     r12, [rbp+47h+arg_20]
0x18000b0d1  jmp     loc_18000B21F
0x18000b0d6  movzx   eax, [rbp+47h+var_98]
0x18000b0da  cmp     r14, rax
0x18000b0dd  jnz     short loc_18000B0F5
0x18000b0df  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000b0e3  mov     r8, r14; Size
0x18000b0e6  mov     rcx, r15; Buf1
0x18000b0e9  call    memcmp_0
0x18000b0ee  mov     ecx, eax
0x18000b0f0  xor     r9d, r9d
0x18000b0f3  jmp     short loc_18000B0FE
0x18000b0f5  movzx   eax, [rbp+47h+var_98]
0x18000b0f9  mov     ecx, r14d
0x18000b0fc  sub     ecx, eax
0x18000b0fe  test    ecx, ecx
0x18000b100  js      loc_18000B2A4
0x18000b106  jz      loc_18000B269
0x18000b10c  mov     rbx, [rbp+47h+var_A8]
0x18000b110  mov     [rbp+47h+var_A8], rbx
0x18000b114  cmp     [rdi+10h], r9
0x18000b118  jbe     short loc_18000B183
0x18000b11a  mov     rax, [rdi+20h]
0x18000b11e  xor     edx, edx
0x18000b120  sub     rax, [rdi+18h]
0x18000b124  mov     rsi, rbx
0x18000b127  div     qword ptr [rdi+10h]
0x18000b12b  mov     edx, [rbp+47h+Source]
0x18000b12e  cmp     rdx, rax
0x18000b131  jbe     short loc_18000B174
0x18000b133  cmp     edx, eax
0x18000b135  jz      short loc_18000B174
0x18000b137  mov     edx, eax
0x18000b139  mov     [rbp+47h+Source], eax
0x18000b13c  mov     al, [rbp+47h+var_9E]
0x18000b13f  cmp     al, 1
0x18000b141  jnz     short loc_18000B156
0x18000b143  movzx   eax, dx
0x18000b146  mov     [rbp+47h+var_B0], dx
0x18000b14a  mov     r9d, 2
0x18000b150  lea     r8, [rbp+47h+var_B0]
0x18000b154  jmp     short loc_18000B164
0x18000b156  cmp     al, 2
0x18000b158  jnz     short loc_18000B174
0x18000b15a  mov     r9d, 4; SourceSize
0x18000b160  lea     r8, [rbp+47h+Source]; Source
0x18000b164  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b168  mov     rdx, r9; DestinationSize
0x18000b16b  call    cs:__imp_memcpy_s
0x18000b171  mov     edx, [rbp+47h+Source]
0x18000b174  mov     ebx, edx
0x18000b176  imul    rbx, [rdi+10h]
0x18000b17b  add     rbx, rsi
0x18000b17e  jmp     loc_18000B20A
0x18000b183  movzx   eax, word ptr [rdi+6]
0x18000b187  xorps   xmm0, xmm0
0x18000b18a  mov     [rbp+47h+var_60], ax
0x18000b18e  mov     esi, r9d
0x18000b191  mov     al, [rdi+8]
0x18000b194  mov     [rbp+47h+var_5E], al
0x18000b197  mov     eax, [rbp+47h+Source]
0x18000b19a  mov     [rbp+47h+var_5C], r9d
0x18000b19e  mov     [rbp+47h+var_58], r9w
0x18000b1a3  movdqu  [rbp+47h+var_50], xmm0
0x18000b1a8  test    eax, eax
0x18000b1aa  jz      short loc_18000B1CE
0x18000b1ac  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b1b0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b1b4  lea     rcx, [rbp+47h+var_60]; this
0x18000b1b8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b1bd  test    al, al
0x18000b1bf  mov     eax, [rbp+47h+Source]
0x18000b1c2  jz      short loc_18000B1CA
0x18000b1c4  inc     esi
0x18000b1c6  cmp     esi, eax
0x18000b1c8  jb      short loc_18000B1AC
0x18000b1ca  mov     rbx, [rbp+47h+var_A8]
0x18000b1ce  cmp     eax, esi
0x18000b1d0  jz      short loc_18000B20A
0x18000b1d2  mov     al, [rbp+47h+var_9E]
0x18000b1d5  mov     [rbp+47h+Source], esi
0x18000b1d8  cmp     al, 1
0x18000b1da  jnz     short loc_18000B1F0
0x18000b1dc  mov     eax, 2
0x18000b1e1  mov     [rbp+47h+var_B0], si
0x18000b1e5  mov     r9d, eax
0x18000b1e8  lea     r8, [rbp+47h+var_B0]
0x18000b1ec  mov     edx, eax
0x18000b1ee  jmp     short loc_18000B200
0x18000b1f0  cmp     al, 2
0x18000b1f2  jnz     short loc_18000B20A
0x18000b1f4  mov     edx, 4; DestinationSize
0x18000b1f9  lea     r8, [rbp+47h+Source]; Source
0x18000b1fd  mov     r9d, edx; SourceSize
0x18000b200  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b204  call    cs:__imp_memcpy_s
0x18000b20a  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b20e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b212  lea     rcx, [rbp+47h+var_A0]; this
0x18000b216  mov     [rbp+47h+var_A8], rbx
0x18000b21a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b21f  xor     r9d, r9d
0x18000b222  mov     sil, al
0x18000b225  test    al, al
0x18000b227  jnz     loc_18000B0D6
0x18000b22d  mov     rbx, [rbp+47h+var_A8]
0x18000b231  mov     [rdi+20h], rbx
0x18000b235  mov     rcx, r9
0x18000b238  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000b23c  jnz     loc_18000B2C7
0x18000b242  movzx   eax, [rbp+47h+var_A0]
0x18000b246  mov     [rbp+47h+Source], 1
0x18000b24d  mov     [rbp+47h+var_98], r14w
0x18000b252  mov     [rbp+47h+Buf2], r9
0x18000b256  mov     [rbp+47h+Buf2+8], r15
0x18000b25a  test    ax, ax
0x18000b25d  jnz     short loc_18000B2AF
0x18000b25f  movzx   ecx, r14w
0x18000b263  add     rcx, 2
0x18000b267  jmp     short loc_18000B2B2
0x18000b269  mov     eax, [rbp+47h+arg_28]
0x18000b26c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18000b270  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000b274  mov     r9, r13; void *
0x18000b277  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000b27b  mov     rcx, rdi; this
0x18000b27e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000b283  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000b288  xor     r9d, r9d
0x18000b28b  mov     [rbp+47h+var_A8], rax
0x18000b28f  mov     rbx, rax
0x18000b292  test    rax, rax
0x18000b295  jnz     short loc_18000B29E
0x18000b297  mov     al, 1
0x18000b299  jmp     loc_18000B3CC
0x18000b29e  mov     byte ptr [rbp+47h+arg_0], 1
0x18000b2a2  jmp     short loc_18000B2A8
0x18000b2a4  mov     [rbp+47h+var_A8], rbx
0x18000b2a8  test    sil, sil
0x18000b2ab  jnz     short loc_18000B235
0x18000b2ad  jmp     short loc_18000B231
0x18000b2af  mov     rcx, rax
0x18000b2b2  mov     al, [rbp+47h+var_9E]
0x18000b2b5  cmp     al, 1
0x18000b2b7  jnz     short loc_18000B2BF
0x18000b2b9  add     rcx, 2
0x18000b2bd  jmp     short loc_18000B2C7
0x18000b2bf  cmp     al, 2
0x18000b2c1  jnz     short loc_18000B2C7
0x18000b2c3  add     rcx, 4
0x18000b2c7  movzx   eax, word ptr [rdi+6]
0x18000b2cb  mov     dl, [rdi+8]
0x18000b2ce  mov     r8d, [rbp+47h+arg_28]
0x18000b2d2  mov     [rbp+47h+var_80], ax
0x18000b2d6  mov     [rbp+47h+var_7E], dl
0x18000b2d9  mov     [rbp+47h+var_7C], r8d
0x18000b2dd  mov     [rbp+47h+var_78], r12w
0x18000b2e2  mov     [rbp+47h+var_70], r9
0x18000b2e6  mov     [rbp+47h+var_68], r13
0x18000b2ea  test    ax, ax
0x18000b2ed  jnz     short loc_18000B2F7
0x18000b2ef  movzx   eax, r12w
0x18000b2f3  add     rax, 2
0x18000b2f7  cmp     dl, 1
0x18000b2fa  jnz     short loc_18000B302
0x18000b2fc  add     rax, 2
0x18000b300  jmp     short loc_18000B30B
0x18000b302  cmp     dl, 2
0x18000b305  jnz     short loc_18000B30B
0x18000b307  add     rax, 4
0x18000b30b  mov     rdx, [rdi+28h]
0x18000b30f  lea     rsi, [rax+rcx]
0x18000b313  mov     r9, [rdi+20h]
0x18000b317  mov     rcx, rdx
0x18000b31a  sub     rcx, r9
0x18000b31d  cmp     r9, rdx
0x18000b320  sbb     rax, rax
0x18000b323  and     rax, rcx
0x18000b326  cmp     rax, rsi
0x18000b329  jb      loc_18000B3CA
0x18000b32f  sub     rdx, rsi
0x18000b332  lea     rcx, [rsi+rbx]; Destination
0x18000b336  sub     rdx, rbx; DestinationSize
0x18000b339  sub     r9, rbx; SourceSize
0x18000b33c  mov     r8, rbx; Source
0x18000b33f  call    cs:__imp_memmove_s
0x18000b345  add     [rdi+20h], rsi
0x18000b349  xor     ebx, ebx
0x18000b34b  cmp     byte ptr [rbp+47h+arg_0], bl
0x18000b34e  jnz     short loc_18000B363
0x18000b350  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b354  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b358  lea     rcx, [rbp+47h+var_A0]; this
0x18000b35c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000b361  jmp     short loc_18000B3B0
0x18000b363  mov     cl, [rbp+47h+var_9E]
0x18000b366  test    cl, cl
0x18000b368  jz      short loc_18000B3B0
0x18000b36a  mov     eax, [rbp+47h+Source]
0x18000b36d  lea     r8d, [rax+1]
0x18000b371  cmp     eax, r8d
0x18000b374  jz      short loc_18000B3B0
0x18000b376  mov     [rbp+47h+Source], r8d
0x18000b37a  cmp     cl, 1
0x18000b37d  jnz     short loc_18000B393
0x18000b37f  mov     r9d, 2
0x18000b385  mov     [rbp+47h+arg_0], r8w
0x18000b38a  mov     edx, r9d
0x18000b38d  lea     r8, [rbp+47h+arg_0]
0x18000b391  jmp     short loc_18000B3A6
0x18000b393  cmp     cl, 2
0x18000b396  jnz     short loc_18000B3B0
0x18000b398  mov     eax, 4
0x18000b39d  lea     r8, [rbp+47h+Source]; Source
0x18000b3a1  mov     r9d, eax; SourceSize
0x18000b3a4  mov     edx, eax; DestinationSize
0x18000b3a6  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b3aa  call    cs:__imp_memcpy_s
0x18000b3b0  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b3b4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b3b8  lea     rcx, [rbp+47h+var_80]; this
0x18000b3bc  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000b3c1  mov     byte ptr [rdi+38h], 1
0x18000b3c5  jmp     loc_18000B297
0x18000b3ca  xor     al, al
0x18000b3cc  add     rsp, 0A8h
0x18000b3d3  pop     r15
0x18000b3d5  pop     r14
0x18000b3d7  pop     r13
0x18000b3d9  pop     r12
0x18000b3db  pop     rdi
0x18000b3dc  pop     rsi
0x18000b3dd  pop     rbx
0x18000b3de  pop     rbp
0x18000b3df  retn
```

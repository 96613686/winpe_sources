# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000b178`
- end: `0x18000b4f8`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000afc8`

## callees

- `0x1800094cc`
- `0x18000ab3c`
- `0x18000b178`
- `0x18000cdfc`
- `0x180015ca6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b283`
- `msvcrt!memcpy_s` at `0x18000b31c`
- `msvcrt!memcpy_s` at `0x18000b4c2`
- `msvcrt!memcpy_s` at `0x18000b283`
- `msvcrt!memcpy_s` at `0x18000b31c`
- `msvcrt!memcpy_s` at `0x18000b4c2`
- `msvcrt!memmove_s` at `0x18000b457`
- `msvcrt!memmove_s` at `0x18000b457`

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
0x18000b178  push    rbp
0x18000b17a  push    rbx
0x18000b17b  push    rsi
0x18000b17c  push    rdi
0x18000b17d  push    r12
0x18000b17f  push    r13
0x18000b181  push    r14
0x18000b183  push    r15
0x18000b185  lea     rbp, [rsp-0Fh]
0x18000b18a  sub     rsp, 0A8h
0x18000b191  mov     rbx, [rcx+18h]
0x18000b195  mov     rdi, rcx
0x18000b198  xor     ecx, ecx
0x18000b19a  mov     r13, r9
0x18000b19d  mov     r14, r8
0x18000b1a0  mov     r15, rdx
0x18000b1a3  test    rbx, rbx
0x18000b1a6  jz      loc_18000B4E2
0x18000b1ac  movzx   eax, word ptr [rdi+2]
0x18000b1b0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b1b4  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b1b8  add     rbx, 0Ah
0x18000b1bc  mov     [rbp+47h+var_A0], ax
0x18000b1c0  xorps   xmm0, xmm0
0x18000b1c3  mov     al, [rdi+4]
0x18000b1c6  mov     [rbp+47h+Source], ecx
0x18000b1c9  mov     [rbp+47h+var_98], cx
0x18000b1cd  mov     byte ptr [rbp+47h+arg_0], cl
0x18000b1d0  lea     rcx, [rbp+47h+var_A0]; this
0x18000b1d4  mov     [rbp+47h+var_9E], al
0x18000b1d7  mov     [rbp+47h+var_A8], rbx
0x18000b1db  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000b1e0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b1e5  mov     r12, [rbp+47h+arg_20]
0x18000b1e9  jmp     loc_18000B337
0x18000b1ee  movzx   eax, [rbp+47h+var_98]
0x18000b1f2  cmp     r14, rax
0x18000b1f5  jnz     short loc_18000B20D
0x18000b1f7  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000b1fb  mov     r8, r14; Size
0x18000b1fe  mov     rcx, r15; Buf1
0x18000b201  call    memcmp_0
0x18000b206  mov     ecx, eax
0x18000b208  xor     r9d, r9d
0x18000b20b  jmp     short loc_18000B216
0x18000b20d  movzx   eax, [rbp+47h+var_98]
0x18000b211  mov     ecx, r14d
0x18000b214  sub     ecx, eax
0x18000b216  test    ecx, ecx
0x18000b218  js      loc_18000B3BC
0x18000b21e  jz      loc_18000B381
0x18000b224  mov     rbx, [rbp+47h+var_A8]
0x18000b228  mov     [rbp+47h+var_A8], rbx
0x18000b22c  cmp     [rdi+10h], r9
0x18000b230  jbe     short loc_18000B29B
0x18000b232  mov     rax, [rdi+20h]
0x18000b236  xor     edx, edx
0x18000b238  sub     rax, [rdi+18h]
0x18000b23c  mov     rsi, rbx
0x18000b23f  div     qword ptr [rdi+10h]
0x18000b243  mov     edx, [rbp+47h+Source]
0x18000b246  cmp     rdx, rax
0x18000b249  jbe     short loc_18000B28C
0x18000b24b  cmp     edx, eax
0x18000b24d  jz      short loc_18000B28C
0x18000b24f  mov     edx, eax
0x18000b251  mov     [rbp+47h+Source], eax
0x18000b254  mov     al, [rbp+47h+var_9E]
0x18000b257  cmp     al, 1
0x18000b259  jnz     short loc_18000B26E
0x18000b25b  movzx   eax, dx
0x18000b25e  mov     [rbp+47h+var_B0], dx
0x18000b262  mov     r9d, 2
0x18000b268  lea     r8, [rbp+47h+var_B0]
0x18000b26c  jmp     short loc_18000B27C
0x18000b26e  cmp     al, 2
0x18000b270  jnz     short loc_18000B28C
0x18000b272  mov     r9d, 4; SourceSize
0x18000b278  lea     r8, [rbp+47h+Source]; Source
0x18000b27c  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b280  mov     rdx, r9; DestinationSize
0x18000b283  call    cs:__imp_memcpy_s
0x18000b289  mov     edx, [rbp+47h+Source]
0x18000b28c  mov     ebx, edx
0x18000b28e  imul    rbx, [rdi+10h]
0x18000b293  add     rbx, rsi
0x18000b296  jmp     loc_18000B322
0x18000b29b  movzx   eax, word ptr [rdi+6]
0x18000b29f  xorps   xmm0, xmm0
0x18000b2a2  mov     [rbp+47h+var_60], ax
0x18000b2a6  mov     esi, r9d
0x18000b2a9  mov     al, [rdi+8]
0x18000b2ac  mov     [rbp+47h+var_5E], al
0x18000b2af  mov     eax, [rbp+47h+Source]
0x18000b2b2  mov     [rbp+47h+var_5C], r9d
0x18000b2b6  mov     [rbp+47h+var_58], r9w
0x18000b2bb  movdqu  [rbp+47h+var_50], xmm0
0x18000b2c0  test    eax, eax
0x18000b2c2  jz      short loc_18000B2E6
0x18000b2c4  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b2c8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b2cc  lea     rcx, [rbp+47h+var_60]; this
0x18000b2d0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b2d5  test    al, al
0x18000b2d7  mov     eax, [rbp+47h+Source]
0x18000b2da  jz      short loc_18000B2E2
0x18000b2dc  inc     esi
0x18000b2de  cmp     esi, eax
0x18000b2e0  jb      short loc_18000B2C4
0x18000b2e2  mov     rbx, [rbp+47h+var_A8]
0x18000b2e6  cmp     eax, esi
0x18000b2e8  jz      short loc_18000B322
0x18000b2ea  mov     al, [rbp+47h+var_9E]
0x18000b2ed  mov     [rbp+47h+Source], esi
0x18000b2f0  cmp     al, 1
0x18000b2f2  jnz     short loc_18000B308
0x18000b2f4  mov     eax, 2
0x18000b2f9  mov     [rbp+47h+var_B0], si
0x18000b2fd  mov     r9d, eax
0x18000b300  lea     r8, [rbp+47h+var_B0]
0x18000b304  mov     edx, eax
0x18000b306  jmp     short loc_18000B318
0x18000b308  cmp     al, 2
0x18000b30a  jnz     short loc_18000B322
0x18000b30c  mov     edx, 4; DestinationSize
0x18000b311  lea     r8, [rbp+47h+Source]; Source
0x18000b315  mov     r9d, edx; SourceSize
0x18000b318  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b31c  call    cs:__imp_memcpy_s
0x18000b322  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b326  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b32a  lea     rcx, [rbp+47h+var_A0]; this
0x18000b32e  mov     [rbp+47h+var_A8], rbx
0x18000b332  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b337  xor     r9d, r9d
0x18000b33a  mov     sil, al
0x18000b33d  test    al, al
0x18000b33f  jnz     loc_18000B1EE
0x18000b345  mov     rbx, [rbp+47h+var_A8]
0x18000b349  mov     [rdi+20h], rbx
0x18000b34d  mov     rcx, r9
0x18000b350  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000b354  jnz     loc_18000B3DF
0x18000b35a  movzx   eax, [rbp+47h+var_A0]
0x18000b35e  mov     [rbp+47h+Source], 1
0x18000b365  mov     [rbp+47h+var_98], r14w
0x18000b36a  mov     [rbp+47h+Buf2], r9
0x18000b36e  mov     [rbp+47h+Buf2+8], r15
0x18000b372  test    ax, ax
0x18000b375  jnz     short loc_18000B3C7
0x18000b377  movzx   ecx, r14w
0x18000b37b  add     rcx, 2
0x18000b37f  jmp     short loc_18000B3CA
0x18000b381  mov     eax, [rbp+47h+arg_28]
0x18000b384  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18000b388  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000b38c  mov     r9, r13; void *
0x18000b38f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000b393  mov     rcx, rdi; this
0x18000b396  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000b39b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000b3a0  xor     r9d, r9d
0x18000b3a3  mov     [rbp+47h+var_A8], rax
0x18000b3a7  mov     rbx, rax
0x18000b3aa  test    rax, rax
0x18000b3ad  jnz     short loc_18000B3B6
0x18000b3af  mov     al, 1
0x18000b3b1  jmp     loc_18000B4E4
0x18000b3b6  mov     byte ptr [rbp+47h+arg_0], 1
0x18000b3ba  jmp     short loc_18000B3C0
0x18000b3bc  mov     [rbp+47h+var_A8], rbx
0x18000b3c0  test    sil, sil
0x18000b3c3  jnz     short loc_18000B34D
0x18000b3c5  jmp     short loc_18000B349
0x18000b3c7  mov     rcx, rax
0x18000b3ca  mov     al, [rbp+47h+var_9E]
0x18000b3cd  cmp     al, 1
0x18000b3cf  jnz     short loc_18000B3D7
0x18000b3d1  add     rcx, 2
0x18000b3d5  jmp     short loc_18000B3DF
0x18000b3d7  cmp     al, 2
0x18000b3d9  jnz     short loc_18000B3DF
0x18000b3db  add     rcx, 4
0x18000b3df  movzx   eax, word ptr [rdi+6]
0x18000b3e3  mov     dl, [rdi+8]
0x18000b3e6  mov     r8d, [rbp+47h+arg_28]
0x18000b3ea  mov     [rbp+47h+var_80], ax
0x18000b3ee  mov     [rbp+47h+var_7E], dl
0x18000b3f1  mov     [rbp+47h+var_7C], r8d
0x18000b3f5  mov     [rbp+47h+var_78], r12w
0x18000b3fa  mov     [rbp+47h+var_70], r9
0x18000b3fe  mov     [rbp+47h+var_68], r13
0x18000b402  test    ax, ax
0x18000b405  jnz     short loc_18000B40F
0x18000b407  movzx   eax, r12w
0x18000b40b  add     rax, 2
0x18000b40f  cmp     dl, 1
0x18000b412  jnz     short loc_18000B41A
0x18000b414  add     rax, 2
0x18000b418  jmp     short loc_18000B423
0x18000b41a  cmp     dl, 2
0x18000b41d  jnz     short loc_18000B423
0x18000b41f  add     rax, 4
0x18000b423  mov     rdx, [rdi+28h]
0x18000b427  lea     rsi, [rax+rcx]
0x18000b42b  mov     r9, [rdi+20h]
0x18000b42f  mov     rcx, rdx
0x18000b432  sub     rcx, r9
0x18000b435  cmp     r9, rdx
0x18000b438  sbb     rax, rax
0x18000b43b  and     rax, rcx
0x18000b43e  cmp     rax, rsi
0x18000b441  jb      loc_18000B4E2
0x18000b447  sub     rdx, rsi
0x18000b44a  lea     rcx, [rsi+rbx]; Destination
0x18000b44e  sub     rdx, rbx; DestinationSize
0x18000b451  sub     r9, rbx; SourceSize
0x18000b454  mov     r8, rbx; Source
0x18000b457  call    cs:__imp_memmove_s
0x18000b45d  add     [rdi+20h], rsi
0x18000b461  xor     ebx, ebx
0x18000b463  cmp     byte ptr [rbp+47h+arg_0], bl
0x18000b466  jnz     short loc_18000B47B
0x18000b468  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b46c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b470  lea     rcx, [rbp+47h+var_A0]; this
0x18000b474  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000b479  jmp     short loc_18000B4C8
0x18000b47b  mov     cl, [rbp+47h+var_9E]
0x18000b47e  test    cl, cl
0x18000b480  jz      short loc_18000B4C8
0x18000b482  mov     eax, [rbp+47h+Source]
0x18000b485  lea     r8d, [rax+1]
0x18000b489  cmp     eax, r8d
0x18000b48c  jz      short loc_18000B4C8
0x18000b48e  mov     [rbp+47h+Source], r8d
0x18000b492  cmp     cl, 1
0x18000b495  jnz     short loc_18000B4AB
0x18000b497  mov     r9d, 2
0x18000b49d  mov     [rbp+47h+arg_0], r8w
0x18000b4a2  mov     edx, r9d
0x18000b4a5  lea     r8, [rbp+47h+arg_0]
0x18000b4a9  jmp     short loc_18000B4BE
0x18000b4ab  cmp     cl, 2
0x18000b4ae  jnz     short loc_18000B4C8
0x18000b4b0  mov     eax, 4
0x18000b4b5  lea     r8, [rbp+47h+Source]; Source
0x18000b4b9  mov     r9d, eax; SourceSize
0x18000b4bc  mov     edx, eax; DestinationSize
0x18000b4be  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000b4c2  call    cs:__imp_memcpy_s
0x18000b4c8  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b4cc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000b4d0  lea     rcx, [rbp+47h+var_80]; this
0x18000b4d4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000b4d9  mov     byte ptr [rdi+38h], 1
0x18000b4dd  jmp     loc_18000B3AF
0x18000b4e2  xor     al, al
0x18000b4e4  add     rsp, 0A8h
0x18000b4eb  pop     r15
0x18000b4ed  pop     r14
0x18000b4ef  pop     r13
0x18000b4f1  pop     r12
0x18000b4f3  pop     rdi
0x18000b4f4  pop     rsi
0x18000b4f5  pop     rbx
0x18000b4f6  pop     rbp
0x18000b4f7  retn
```

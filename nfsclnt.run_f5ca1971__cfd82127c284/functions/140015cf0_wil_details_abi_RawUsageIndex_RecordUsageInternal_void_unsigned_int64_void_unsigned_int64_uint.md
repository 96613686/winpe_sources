# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140015cf0`
- end: `0x140016070`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140015b40`

## callees

- `0x140013f9c`
- `0x1400156bc`
- `0x140015cf0`
- `0x1400175ec`
- `0x1400182f6`

## import_xrefs

- `msvcrt!memmove_s` at `0x140015fcf`
- `msvcrt!memmove_s` at `0x140015fcf`
- `msvcrt!memcpy_s` at `0x140015dfb`
- `msvcrt!memcpy_s` at `0x140015e94`
- `msvcrt!memcpy_s` at `0x14001603a`
- `msvcrt!memcpy_s` at `0x140015dfb`
- `msvcrt!memcpy_s` at `0x140015e94`
- `msvcrt!memcpy_s` at `0x14001603a`

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
0x140015cf0  push    rbp
0x140015cf2  push    rbx
0x140015cf3  push    rsi
0x140015cf4  push    rdi
0x140015cf5  push    r12
0x140015cf7  push    r13
0x140015cf9  push    r14
0x140015cfb  push    r15
0x140015cfd  lea     rbp, [rsp-0Fh]
0x140015d02  sub     rsp, 0A8h
0x140015d09  mov     rbx, [rcx+18h]
0x140015d0d  mov     rdi, rcx
0x140015d10  xor     ecx, ecx
0x140015d12  mov     r13, r9
0x140015d15  mov     r14, r8
0x140015d18  mov     r15, rdx
0x140015d1b  test    rbx, rbx
0x140015d1e  jz      loc_14001605A
0x140015d24  movzx   eax, word ptr [rdi+2]
0x140015d28  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140015d2c  mov     r8, [rdi+20h]; unsigned __int8 *
0x140015d30  add     rbx, 0Ah
0x140015d34  mov     [rbp+47h+var_A0], ax
0x140015d38  xorps   xmm0, xmm0
0x140015d3b  mov     al, [rdi+4]
0x140015d3e  mov     [rbp+47h+Source], ecx
0x140015d41  mov     [rbp+47h+var_98], cx
0x140015d45  mov     byte ptr [rbp+47h+arg_0], cl
0x140015d48  lea     rcx, [rbp+47h+var_A0]; this
0x140015d4c  mov     [rbp+47h+var_9E], al
0x140015d4f  mov     [rbp+47h+var_A8], rbx
0x140015d53  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x140015d58  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140015d5d  mov     r12, [rbp+47h+arg_20]
0x140015d61  jmp     loc_140015EAF
0x140015d66  movzx   eax, [rbp+47h+var_98]
0x140015d6a  cmp     r14, rax
0x140015d6d  jnz     short loc_140015D85
0x140015d6f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x140015d73  mov     r8, r14; Size
0x140015d76  mov     rcx, r15; Buf1
0x140015d79  call    memcmp_0
0x140015d7e  mov     ecx, eax
0x140015d80  xor     r9d, r9d
0x140015d83  jmp     short loc_140015D8E
0x140015d85  movzx   eax, [rbp+47h+var_98]
0x140015d89  mov     ecx, r14d
0x140015d8c  sub     ecx, eax
0x140015d8e  test    ecx, ecx
0x140015d90  js      loc_140015F34
0x140015d96  jz      loc_140015EF9
0x140015d9c  mov     rbx, [rbp+47h+var_A8]
0x140015da0  mov     [rbp+47h+var_A8], rbx
0x140015da4  cmp     [rdi+10h], r9
0x140015da8  jbe     short loc_140015E13
0x140015daa  mov     rax, [rdi+20h]
0x140015dae  xor     edx, edx
0x140015db0  sub     rax, [rdi+18h]
0x140015db4  mov     rsi, rbx
0x140015db7  div     qword ptr [rdi+10h]
0x140015dbb  mov     edx, [rbp+47h+Source]
0x140015dbe  cmp     rdx, rax
0x140015dc1  jbe     short loc_140015E04
0x140015dc3  cmp     edx, eax
0x140015dc5  jz      short loc_140015E04
0x140015dc7  mov     edx, eax
0x140015dc9  mov     [rbp+47h+Source], eax
0x140015dcc  mov     al, [rbp+47h+var_9E]
0x140015dcf  cmp     al, 1
0x140015dd1  jnz     short loc_140015DE6
0x140015dd3  movzx   eax, dx
0x140015dd6  mov     [rbp+47h+var_B0], dx
0x140015dda  mov     r9d, 2
0x140015de0  lea     r8, [rbp+47h+var_B0]
0x140015de4  jmp     short loc_140015DF4
0x140015de6  cmp     al, 2
0x140015de8  jnz     short loc_140015E04
0x140015dea  mov     r9d, 4; SourceSize
0x140015df0  lea     r8, [rbp+47h+Source]; Source
0x140015df4  mov     rcx, [rbp+47h+Buf2]; Destination
0x140015df8  mov     rdx, r9; DestinationSize
0x140015dfb  call    cs:__imp_memcpy_s
0x140015e01  mov     edx, [rbp+47h+Source]
0x140015e04  mov     ebx, edx
0x140015e06  imul    rbx, [rdi+10h]
0x140015e0b  add     rbx, rsi
0x140015e0e  jmp     loc_140015E9A
0x140015e13  movzx   eax, word ptr [rdi+6]
0x140015e17  xorps   xmm0, xmm0
0x140015e1a  mov     [rbp+47h+var_60], ax
0x140015e1e  mov     esi, r9d
0x140015e21  mov     al, [rdi+8]
0x140015e24  mov     [rbp+47h+var_5E], al
0x140015e27  mov     eax, [rbp+47h+Source]
0x140015e2a  mov     [rbp+47h+var_5C], r9d
0x140015e2e  mov     [rbp+47h+var_58], r9w
0x140015e33  movdqu  [rbp+47h+var_50], xmm0
0x140015e38  test    eax, eax
0x140015e3a  jz      short loc_140015E5E
0x140015e3c  mov     r8, [rdi+20h]; unsigned __int8 *
0x140015e40  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140015e44  lea     rcx, [rbp+47h+var_60]; this
0x140015e48  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140015e4d  test    al, al
0x140015e4f  mov     eax, [rbp+47h+Source]
0x140015e52  jz      short loc_140015E5A
0x140015e54  inc     esi
0x140015e56  cmp     esi, eax
0x140015e58  jb      short loc_140015E3C
0x140015e5a  mov     rbx, [rbp+47h+var_A8]
0x140015e5e  cmp     eax, esi
0x140015e60  jz      short loc_140015E9A
0x140015e62  mov     al, [rbp+47h+var_9E]
0x140015e65  mov     [rbp+47h+Source], esi
0x140015e68  cmp     al, 1
0x140015e6a  jnz     short loc_140015E80
0x140015e6c  mov     eax, 2
0x140015e71  mov     [rbp+47h+var_B0], si
0x140015e75  mov     r9d, eax
0x140015e78  lea     r8, [rbp+47h+var_B0]
0x140015e7c  mov     edx, eax
0x140015e7e  jmp     short loc_140015E90
0x140015e80  cmp     al, 2
0x140015e82  jnz     short loc_140015E9A
0x140015e84  mov     edx, 4; DestinationSize
0x140015e89  lea     r8, [rbp+47h+Source]; Source
0x140015e8d  mov     r9d, edx; SourceSize
0x140015e90  mov     rcx, [rbp+47h+Buf2]; Destination
0x140015e94  call    cs:__imp_memcpy_s
0x140015e9a  mov     r8, [rdi+20h]; unsigned __int8 *
0x140015e9e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140015ea2  lea     rcx, [rbp+47h+var_A0]; this
0x140015ea6  mov     [rbp+47h+var_A8], rbx
0x140015eaa  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140015eaf  xor     r9d, r9d
0x140015eb2  mov     sil, al
0x140015eb5  test    al, al
0x140015eb7  jnz     loc_140015D66
0x140015ebd  mov     rbx, [rbp+47h+var_A8]
0x140015ec1  mov     [rdi+20h], rbx
0x140015ec5  mov     rcx, r9
0x140015ec8  cmp     byte ptr [rbp+47h+arg_0], r9b
0x140015ecc  jnz     loc_140015F57
0x140015ed2  movzx   eax, [rbp+47h+var_A0]
0x140015ed6  mov     [rbp+47h+Source], 1
0x140015edd  mov     [rbp+47h+var_98], r14w
0x140015ee2  mov     [rbp+47h+Buf2], r9
0x140015ee6  mov     [rbp+47h+Buf2+8], r15
0x140015eea  test    ax, ax
0x140015eed  jnz     short loc_140015F3F
0x140015eef  movzx   ecx, r14w
0x140015ef3  add     rcx, 2
0x140015ef7  jmp     short loc_140015F42
0x140015ef9  mov     eax, [rbp+47h+arg_28]
0x140015efc  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x140015f00  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x140015f04  mov     r9, r13; void *
0x140015f07  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x140015f0b  mov     rcx, rdi; this
0x140015f0e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x140015f13  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x140015f18  xor     r9d, r9d
0x140015f1b  mov     [rbp+47h+var_A8], rax
0x140015f1f  mov     rbx, rax
0x140015f22  test    rax, rax
0x140015f25  jnz     short loc_140015F2E
0x140015f27  mov     al, 1
0x140015f29  jmp     loc_14001605C
0x140015f2e  mov     byte ptr [rbp+47h+arg_0], 1
0x140015f32  jmp     short loc_140015F38
0x140015f34  mov     [rbp+47h+var_A8], rbx
0x140015f38  test    sil, sil
0x140015f3b  jnz     short loc_140015EC5
0x140015f3d  jmp     short loc_140015EC1
0x140015f3f  mov     rcx, rax
0x140015f42  mov     al, [rbp+47h+var_9E]
0x140015f45  cmp     al, 1
0x140015f47  jnz     short loc_140015F4F
0x140015f49  add     rcx, 2
0x140015f4d  jmp     short loc_140015F57
0x140015f4f  cmp     al, 2
0x140015f51  jnz     short loc_140015F57
0x140015f53  add     rcx, 4
0x140015f57  movzx   eax, word ptr [rdi+6]
0x140015f5b  mov     dl, [rdi+8]
0x140015f5e  mov     r8d, [rbp+47h+arg_28]
0x140015f62  mov     [rbp+47h+var_80], ax
0x140015f66  mov     [rbp+47h+var_7E], dl
0x140015f69  mov     [rbp+47h+var_7C], r8d
0x140015f6d  mov     [rbp+47h+var_78], r12w
0x140015f72  mov     [rbp+47h+var_70], r9
0x140015f76  mov     [rbp+47h+var_68], r13
0x140015f7a  test    ax, ax
0x140015f7d  jnz     short loc_140015F87
0x140015f7f  movzx   eax, r12w
0x140015f83  add     rax, 2
0x140015f87  cmp     dl, 1
0x140015f8a  jnz     short loc_140015F92
0x140015f8c  add     rax, 2
0x140015f90  jmp     short loc_140015F9B
0x140015f92  cmp     dl, 2
0x140015f95  jnz     short loc_140015F9B
0x140015f97  add     rax, 4
0x140015f9b  mov     rdx, [rdi+28h]
0x140015f9f  lea     rsi, [rax+rcx]
0x140015fa3  mov     r9, [rdi+20h]
0x140015fa7  mov     rcx, rdx
0x140015faa  sub     rcx, r9
0x140015fad  cmp     r9, rdx
0x140015fb0  sbb     rax, rax
0x140015fb3  and     rax, rcx
0x140015fb6  cmp     rax, rsi
0x140015fb9  jb      loc_14001605A
0x140015fbf  sub     rdx, rsi
0x140015fc2  lea     rcx, [rsi+rbx]; Destination
0x140015fc6  sub     rdx, rbx; DestinationSize
0x140015fc9  sub     r9, rbx; SourceSize
0x140015fcc  mov     r8, rbx; Source
0x140015fcf  call    cs:__imp_memmove_s
0x140015fd5  add     [rdi+20h], rsi
0x140015fd9  xor     ebx, ebx
0x140015fdb  cmp     byte ptr [rbp+47h+arg_0], bl
0x140015fde  jnz     short loc_140015FF3
0x140015fe0  mov     r8, [rdi+20h]; unsigned __int8 *
0x140015fe4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140015fe8  lea     rcx, [rbp+47h+var_A0]; this
0x140015fec  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140015ff1  jmp     short loc_140016040
0x140015ff3  mov     cl, [rbp+47h+var_9E]
0x140015ff6  test    cl, cl
0x140015ff8  jz      short loc_140016040
0x140015ffa  mov     eax, [rbp+47h+Source]
0x140015ffd  lea     r8d, [rax+1]
0x140016001  cmp     eax, r8d
0x140016004  jz      short loc_140016040
0x140016006  mov     [rbp+47h+Source], r8d
0x14001600a  cmp     cl, 1
0x14001600d  jnz     short loc_140016023
0x14001600f  mov     r9d, 2
0x140016015  mov     [rbp+47h+arg_0], r8w
0x14001601a  mov     edx, r9d
0x14001601d  lea     r8, [rbp+47h+arg_0]
0x140016021  jmp     short loc_140016036
0x140016023  cmp     cl, 2
0x140016026  jnz     short loc_140016040
0x140016028  mov     eax, 4
0x14001602d  lea     r8, [rbp+47h+Source]; Source
0x140016031  mov     r9d, eax; SourceSize
0x140016034  mov     edx, eax; DestinationSize
0x140016036  mov     rcx, [rbp+47h+Buf2]; Destination
0x14001603a  call    cs:__imp_memcpy_s
0x140016040  mov     r8, [rdi+20h]; unsigned __int8 *
0x140016044  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140016048  lea     rcx, [rbp+47h+var_80]; this
0x14001604c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140016051  mov     byte ptr [rdi+38h], 1
0x140016055  jmp     loc_140015F27
0x14001605a  xor     al, al
0x14001605c  add     rsp, 0A8h
0x140016063  pop     r15
0x140016065  pop     r14
0x140016067  pop     r13
0x140016069  pop     r12
0x14001606b  pop     rdi
0x14001606c  pop     rsi
0x14001606d  pop     rbx
0x14001606e  pop     rbp
0x14001606f  retn
```

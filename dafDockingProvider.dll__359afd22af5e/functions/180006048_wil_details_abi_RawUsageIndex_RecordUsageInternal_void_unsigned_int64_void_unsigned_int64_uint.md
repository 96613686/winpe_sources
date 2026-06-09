# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006048`
- end: `0x1800063c8`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005e98`

## callees

- `0x18000439c`
- `0x180005a0c`
- `0x180006048`
- `0x180007dfc`
- `0x18001ca26`

## import_xrefs

- `msvcrt!memmove_s` at `0x180006327`
- `msvcrt!memmove_s` at `0x180006327`
- `msvcrt!memcpy_s` at `0x180006153`
- `msvcrt!memcpy_s` at `0x1800061ec`
- `msvcrt!memcpy_s` at `0x180006392`
- `msvcrt!memcpy_s` at `0x180006153`
- `msvcrt!memcpy_s` at `0x1800061ec`
- `msvcrt!memcpy_s` at `0x180006392`

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
0x180006048  push    rbp
0x18000604a  push    rbx
0x18000604b  push    rsi
0x18000604c  push    rdi
0x18000604d  push    r12
0x18000604f  push    r13
0x180006051  push    r14
0x180006053  push    r15
0x180006055  lea     rbp, [rsp-0Fh]
0x18000605a  sub     rsp, 0A8h
0x180006061  mov     rbx, [rcx+18h]
0x180006065  mov     rdi, rcx
0x180006068  xor     ecx, ecx
0x18000606a  mov     r13, r9
0x18000606d  mov     r14, r8
0x180006070  mov     r15, rdx
0x180006073  test    rbx, rbx
0x180006076  jz      loc_1800063B2
0x18000607c  movzx   eax, word ptr [rdi+2]
0x180006080  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006084  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006088  add     rbx, 0Ah
0x18000608c  mov     [rbp+47h+var_A0], ax
0x180006090  xorps   xmm0, xmm0
0x180006093  mov     al, [rdi+4]
0x180006096  mov     [rbp+47h+Source], ecx
0x180006099  mov     [rbp+47h+var_98], cx
0x18000609d  mov     byte ptr [rbp+47h+arg_0], cl
0x1800060a0  lea     rcx, [rbp+47h+var_A0]; this
0x1800060a4  mov     [rbp+47h+var_9E], al
0x1800060a7  mov     [rbp+47h+var_A8], rbx
0x1800060ab  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1800060b0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800060b5  mov     r12, [rbp+47h+arg_20]
0x1800060b9  jmp     loc_180006207
0x1800060be  movzx   eax, [rbp+47h+var_98]
0x1800060c2  cmp     r14, rax
0x1800060c5  jnz     short loc_1800060DD
0x1800060c7  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x1800060cb  mov     r8, r14; Size
0x1800060ce  mov     rcx, r15; Buf1
0x1800060d1  call    memcmp_0
0x1800060d6  mov     ecx, eax
0x1800060d8  xor     r9d, r9d
0x1800060db  jmp     short loc_1800060E6
0x1800060dd  movzx   eax, [rbp+47h+var_98]
0x1800060e1  mov     ecx, r14d
0x1800060e4  sub     ecx, eax
0x1800060e6  test    ecx, ecx
0x1800060e8  js      loc_18000628C
0x1800060ee  jz      loc_180006251
0x1800060f4  mov     rbx, [rbp+47h+var_A8]
0x1800060f8  mov     [rbp+47h+var_A8], rbx
0x1800060fc  cmp     [rdi+10h], r9
0x180006100  jbe     short loc_18000616B
0x180006102  mov     rax, [rdi+20h]
0x180006106  xor     edx, edx
0x180006108  sub     rax, [rdi+18h]
0x18000610c  mov     rsi, rbx
0x18000610f  div     qword ptr [rdi+10h]
0x180006113  mov     edx, [rbp+47h+Source]
0x180006116  cmp     rdx, rax
0x180006119  jbe     short loc_18000615C
0x18000611b  cmp     edx, eax
0x18000611d  jz      short loc_18000615C
0x18000611f  mov     edx, eax
0x180006121  mov     [rbp+47h+Source], eax
0x180006124  mov     al, [rbp+47h+var_9E]
0x180006127  cmp     al, 1
0x180006129  jnz     short loc_18000613E
0x18000612b  movzx   eax, dx
0x18000612e  mov     [rbp+47h+var_B0], dx
0x180006132  mov     r9d, 2
0x180006138  lea     r8, [rbp+47h+var_B0]
0x18000613c  jmp     short loc_18000614C
0x18000613e  cmp     al, 2
0x180006140  jnz     short loc_18000615C
0x180006142  mov     r9d, 4; SourceSize
0x180006148  lea     r8, [rbp+47h+Source]; Source
0x18000614c  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006150  mov     rdx, r9; DestinationSize
0x180006153  call    cs:__imp_memcpy_s
0x180006159  mov     edx, [rbp+47h+Source]
0x18000615c  mov     ebx, edx
0x18000615e  imul    rbx, [rdi+10h]
0x180006163  add     rbx, rsi
0x180006166  jmp     loc_1800061F2
0x18000616b  movzx   eax, word ptr [rdi+6]
0x18000616f  xorps   xmm0, xmm0
0x180006172  mov     [rbp+47h+var_60], ax
0x180006176  mov     esi, r9d
0x180006179  mov     al, [rdi+8]
0x18000617c  mov     [rbp+47h+var_5E], al
0x18000617f  mov     eax, [rbp+47h+Source]
0x180006182  mov     [rbp+47h+var_5C], r9d
0x180006186  mov     [rbp+47h+var_58], r9w
0x18000618b  movdqu  [rbp+47h+var_50], xmm0
0x180006190  test    eax, eax
0x180006192  jz      short loc_1800061B6
0x180006194  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006198  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000619c  lea     rcx, [rbp+47h+var_60]; this
0x1800061a0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800061a5  test    al, al
0x1800061a7  mov     eax, [rbp+47h+Source]
0x1800061aa  jz      short loc_1800061B2
0x1800061ac  inc     esi
0x1800061ae  cmp     esi, eax
0x1800061b0  jb      short loc_180006194
0x1800061b2  mov     rbx, [rbp+47h+var_A8]
0x1800061b6  cmp     eax, esi
0x1800061b8  jz      short loc_1800061F2
0x1800061ba  mov     al, [rbp+47h+var_9E]
0x1800061bd  mov     [rbp+47h+Source], esi
0x1800061c0  cmp     al, 1
0x1800061c2  jnz     short loc_1800061D8
0x1800061c4  mov     eax, 2
0x1800061c9  mov     [rbp+47h+var_B0], si
0x1800061cd  mov     r9d, eax
0x1800061d0  lea     r8, [rbp+47h+var_B0]
0x1800061d4  mov     edx, eax
0x1800061d6  jmp     short loc_1800061E8
0x1800061d8  cmp     al, 2
0x1800061da  jnz     short loc_1800061F2
0x1800061dc  mov     edx, 4; DestinationSize
0x1800061e1  lea     r8, [rbp+47h+Source]; Source
0x1800061e5  mov     r9d, edx; SourceSize
0x1800061e8  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800061ec  call    cs:__imp_memcpy_s
0x1800061f2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800061f6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800061fa  lea     rcx, [rbp+47h+var_A0]; this
0x1800061fe  mov     [rbp+47h+var_A8], rbx
0x180006202  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006207  xor     r9d, r9d
0x18000620a  mov     sil, al
0x18000620d  test    al, al
0x18000620f  jnz     loc_1800060BE
0x180006215  mov     rbx, [rbp+47h+var_A8]
0x180006219  mov     [rdi+20h], rbx
0x18000621d  mov     rcx, r9
0x180006220  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180006224  jnz     loc_1800062AF
0x18000622a  movzx   eax, [rbp+47h+var_A0]
0x18000622e  mov     [rbp+47h+Source], 1
0x180006235  mov     [rbp+47h+var_98], r14w
0x18000623a  mov     [rbp+47h+Buf2], r9
0x18000623e  mov     [rbp+47h+Buf2+8], r15
0x180006242  test    ax, ax
0x180006245  jnz     short loc_180006297
0x180006247  movzx   ecx, r14w
0x18000624b  add     rcx, 2
0x18000624f  jmp     short loc_18000629A
0x180006251  mov     eax, [rbp+47h+arg_28]
0x180006254  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180006258  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000625c  mov     r9, r13; void *
0x18000625f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180006263  mov     rcx, rdi; this
0x180006266  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000626b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180006270  xor     r9d, r9d
0x180006273  mov     [rbp+47h+var_A8], rax
0x180006277  mov     rbx, rax
0x18000627a  test    rax, rax
0x18000627d  jnz     short loc_180006286
0x18000627f  mov     al, 1
0x180006281  jmp     loc_1800063B4
0x180006286  mov     byte ptr [rbp+47h+arg_0], 1
0x18000628a  jmp     short loc_180006290
0x18000628c  mov     [rbp+47h+var_A8], rbx
0x180006290  test    sil, sil
0x180006293  jnz     short loc_18000621D
0x180006295  jmp     short loc_180006219
0x180006297  mov     rcx, rax
0x18000629a  mov     al, [rbp+47h+var_9E]
0x18000629d  cmp     al, 1
0x18000629f  jnz     short loc_1800062A7
0x1800062a1  add     rcx, 2
0x1800062a5  jmp     short loc_1800062AF
0x1800062a7  cmp     al, 2
0x1800062a9  jnz     short loc_1800062AF
0x1800062ab  add     rcx, 4
0x1800062af  movzx   eax, word ptr [rdi+6]
0x1800062b3  mov     dl, [rdi+8]
0x1800062b6  mov     r8d, [rbp+47h+arg_28]
0x1800062ba  mov     [rbp+47h+var_80], ax
0x1800062be  mov     [rbp+47h+var_7E], dl
0x1800062c1  mov     [rbp+47h+var_7C], r8d
0x1800062c5  mov     [rbp+47h+var_78], r12w
0x1800062ca  mov     [rbp+47h+var_70], r9
0x1800062ce  mov     [rbp+47h+var_68], r13
0x1800062d2  test    ax, ax
0x1800062d5  jnz     short loc_1800062DF
0x1800062d7  movzx   eax, r12w
0x1800062db  add     rax, 2
0x1800062df  cmp     dl, 1
0x1800062e2  jnz     short loc_1800062EA
0x1800062e4  add     rax, 2
0x1800062e8  jmp     short loc_1800062F3
0x1800062ea  cmp     dl, 2
0x1800062ed  jnz     short loc_1800062F3
0x1800062ef  add     rax, 4
0x1800062f3  mov     rdx, [rdi+28h]
0x1800062f7  lea     rsi, [rax+rcx]
0x1800062fb  mov     r9, [rdi+20h]
0x1800062ff  mov     rcx, rdx
0x180006302  sub     rcx, r9
0x180006305  cmp     r9, rdx
0x180006308  sbb     rax, rax
0x18000630b  and     rax, rcx
0x18000630e  cmp     rax, rsi
0x180006311  jb      loc_1800063B2
0x180006317  sub     rdx, rsi
0x18000631a  lea     rcx, [rsi+rbx]; Destination
0x18000631e  sub     rdx, rbx; DestinationSize
0x180006321  sub     r9, rbx; SourceSize
0x180006324  mov     r8, rbx; Source
0x180006327  call    cs:__imp_memmove_s
0x18000632d  add     [rdi+20h], rsi
0x180006331  xor     ebx, ebx
0x180006333  cmp     byte ptr [rbp+47h+arg_0], bl
0x180006336  jnz     short loc_18000634B
0x180006338  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000633c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006340  lea     rcx, [rbp+47h+var_A0]; this
0x180006344  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006349  jmp     short loc_180006398
0x18000634b  mov     cl, [rbp+47h+var_9E]
0x18000634e  test    cl, cl
0x180006350  jz      short loc_180006398
0x180006352  mov     eax, [rbp+47h+Source]
0x180006355  lea     r8d, [rax+1]
0x180006359  cmp     eax, r8d
0x18000635c  jz      short loc_180006398
0x18000635e  mov     [rbp+47h+Source], r8d
0x180006362  cmp     cl, 1
0x180006365  jnz     short loc_18000637B
0x180006367  mov     r9d, 2
0x18000636d  mov     [rbp+47h+arg_0], r8w
0x180006372  mov     edx, r9d
0x180006375  lea     r8, [rbp+47h+arg_0]
0x180006379  jmp     short loc_18000638E
0x18000637b  cmp     cl, 2
0x18000637e  jnz     short loc_180006398
0x180006380  mov     eax, 4
0x180006385  lea     r8, [rbp+47h+Source]; Source
0x180006389  mov     r9d, eax; SourceSize
0x18000638c  mov     edx, eax; DestinationSize
0x18000638e  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006392  call    cs:__imp_memcpy_s
0x180006398  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000639c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800063a0  lea     rcx, [rbp+47h+var_80]; this
0x1800063a4  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800063a9  mov     byte ptr [rdi+38h], 1
0x1800063ad  jmp     loc_18000627F
0x1800063b2  xor     al, al
0x1800063b4  add     rsp, 0A8h
0x1800063bb  pop     r15
0x1800063bd  pop     r14
0x1800063bf  pop     r13
0x1800063c1  pop     r12
0x1800063c3  pop     rdi
0x1800063c4  pop     rsi
0x1800063c5  pop     rbx
0x1800063c6  pop     rbp
0x1800063c7  retn
```

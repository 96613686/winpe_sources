# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180010454`
- end: `0x1800107d4`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800102a4`

## callees

- `0x18000e3dc`
- `0x18000fe94`
- `0x180010454`
- `0x180011484`
- `0x180011ff6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001055f`
- `msvcrt!memcpy_s` at `0x1800105f8`
- `msvcrt!memcpy_s` at `0x18001079e`
- `msvcrt!memcpy_s` at `0x18001055f`
- `msvcrt!memcpy_s` at `0x1800105f8`
- `msvcrt!memcpy_s` at `0x18001079e`
- `msvcrt!memmove_s` at `0x180010733`
- `msvcrt!memmove_s` at `0x180010733`

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
0x180010454  push    rbp
0x180010456  push    rbx
0x180010457  push    rsi
0x180010458  push    rdi
0x180010459  push    r12
0x18001045b  push    r13
0x18001045d  push    r14
0x18001045f  push    r15
0x180010461  lea     rbp, [rsp-0Fh]
0x180010466  sub     rsp, 0A8h
0x18001046d  mov     rbx, [rcx+18h]
0x180010471  mov     rdi, rcx
0x180010474  xor     ecx, ecx
0x180010476  mov     r13, r9
0x180010479  mov     r14, r8
0x18001047c  mov     r15, rdx
0x18001047f  test    rbx, rbx
0x180010482  jz      loc_1800107BE
0x180010488  movzx   eax, word ptr [rdi+2]
0x18001048c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180010490  mov     r8, [rdi+20h]; unsigned __int8 *
0x180010494  add     rbx, 0Ah
0x180010498  mov     [rbp+47h+var_A0], ax
0x18001049c  xorps   xmm0, xmm0
0x18001049f  mov     al, [rdi+4]
0x1800104a2  mov     [rbp+47h+Source], ecx
0x1800104a5  mov     [rbp+47h+var_98], cx
0x1800104a9  mov     byte ptr [rbp+47h+arg_0], cl
0x1800104ac  lea     rcx, [rbp+47h+var_A0]; this
0x1800104b0  mov     [rbp+47h+var_9E], al
0x1800104b3  mov     [rbp+47h+var_A8], rbx
0x1800104b7  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1800104bc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800104c1  mov     r12, [rbp+47h+arg_20]
0x1800104c5  jmp     loc_180010613
0x1800104ca  movzx   eax, [rbp+47h+var_98]
0x1800104ce  cmp     r14, rax
0x1800104d1  jnz     short loc_1800104E9
0x1800104d3  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x1800104d7  mov     r8, r14; Size
0x1800104da  mov     rcx, r15; Buf1
0x1800104dd  call    memcmp_0
0x1800104e2  mov     ecx, eax
0x1800104e4  xor     r9d, r9d
0x1800104e7  jmp     short loc_1800104F2
0x1800104e9  movzx   eax, [rbp+47h+var_98]
0x1800104ed  mov     ecx, r14d
0x1800104f0  sub     ecx, eax
0x1800104f2  test    ecx, ecx
0x1800104f4  js      loc_180010698
0x1800104fa  jz      loc_18001065D
0x180010500  mov     rbx, [rbp+47h+var_A8]
0x180010504  mov     [rbp+47h+var_A8], rbx
0x180010508  cmp     [rdi+10h], r9
0x18001050c  jbe     short loc_180010577
0x18001050e  mov     rax, [rdi+20h]
0x180010512  xor     edx, edx
0x180010514  sub     rax, [rdi+18h]
0x180010518  mov     rsi, rbx
0x18001051b  div     qword ptr [rdi+10h]
0x18001051f  mov     edx, [rbp+47h+Source]
0x180010522  cmp     rdx, rax
0x180010525  jbe     short loc_180010568
0x180010527  cmp     edx, eax
0x180010529  jz      short loc_180010568
0x18001052b  mov     edx, eax
0x18001052d  mov     [rbp+47h+Source], eax
0x180010530  mov     al, [rbp+47h+var_9E]
0x180010533  cmp     al, 1
0x180010535  jnz     short loc_18001054A
0x180010537  movzx   eax, dx
0x18001053a  mov     [rbp+47h+var_B0], dx
0x18001053e  mov     r9d, 2
0x180010544  lea     r8, [rbp+47h+var_B0]
0x180010548  jmp     short loc_180010558
0x18001054a  cmp     al, 2
0x18001054c  jnz     short loc_180010568
0x18001054e  mov     r9d, 4; SourceSize
0x180010554  lea     r8, [rbp+47h+Source]; Source
0x180010558  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001055c  mov     rdx, r9; DestinationSize
0x18001055f  call    cs:__imp_memcpy_s
0x180010565  mov     edx, [rbp+47h+Source]
0x180010568  mov     ebx, edx
0x18001056a  imul    rbx, [rdi+10h]
0x18001056f  add     rbx, rsi
0x180010572  jmp     loc_1800105FE
0x180010577  movzx   eax, word ptr [rdi+6]
0x18001057b  xorps   xmm0, xmm0
0x18001057e  mov     [rbp+47h+var_60], ax
0x180010582  mov     esi, r9d
0x180010585  mov     al, [rdi+8]
0x180010588  mov     [rbp+47h+var_5E], al
0x18001058b  mov     eax, [rbp+47h+Source]
0x18001058e  mov     [rbp+47h+var_5C], r9d
0x180010592  mov     [rbp+47h+var_58], r9w
0x180010597  movdqu  [rbp+47h+var_50], xmm0
0x18001059c  test    eax, eax
0x18001059e  jz      short loc_1800105C2
0x1800105a0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800105a4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800105a8  lea     rcx, [rbp+47h+var_60]; this
0x1800105ac  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800105b1  test    al, al
0x1800105b3  mov     eax, [rbp+47h+Source]
0x1800105b6  jz      short loc_1800105BE
0x1800105b8  inc     esi
0x1800105ba  cmp     esi, eax
0x1800105bc  jb      short loc_1800105A0
0x1800105be  mov     rbx, [rbp+47h+var_A8]
0x1800105c2  cmp     eax, esi
0x1800105c4  jz      short loc_1800105FE
0x1800105c6  mov     al, [rbp+47h+var_9E]
0x1800105c9  mov     [rbp+47h+Source], esi
0x1800105cc  cmp     al, 1
0x1800105ce  jnz     short loc_1800105E4
0x1800105d0  mov     eax, 2
0x1800105d5  mov     [rbp+47h+var_B0], si
0x1800105d9  mov     r9d, eax
0x1800105dc  lea     r8, [rbp+47h+var_B0]
0x1800105e0  mov     edx, eax
0x1800105e2  jmp     short loc_1800105F4
0x1800105e4  cmp     al, 2
0x1800105e6  jnz     short loc_1800105FE
0x1800105e8  mov     edx, 4; DestinationSize
0x1800105ed  lea     r8, [rbp+47h+Source]; Source
0x1800105f1  mov     r9d, edx; SourceSize
0x1800105f4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800105f8  call    cs:__imp_memcpy_s
0x1800105fe  mov     r8, [rdi+20h]; unsigned __int8 *
0x180010602  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180010606  lea     rcx, [rbp+47h+var_A0]; this
0x18001060a  mov     [rbp+47h+var_A8], rbx
0x18001060e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180010613  xor     r9d, r9d
0x180010616  mov     sil, al
0x180010619  test    al, al
0x18001061b  jnz     loc_1800104CA
0x180010621  mov     rbx, [rbp+47h+var_A8]
0x180010625  mov     [rdi+20h], rbx
0x180010629  mov     rcx, r9
0x18001062c  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180010630  jnz     loc_1800106BB
0x180010636  movzx   eax, [rbp+47h+var_A0]
0x18001063a  mov     [rbp+47h+Source], 1
0x180010641  mov     [rbp+47h+var_98], r14w
0x180010646  mov     [rbp+47h+Buf2], r9
0x18001064a  mov     [rbp+47h+Buf2+8], r15
0x18001064e  test    ax, ax
0x180010651  jnz     short loc_1800106A3
0x180010653  movzx   ecx, r14w
0x180010657  add     rcx, 2
0x18001065b  jmp     short loc_1800106A6
0x18001065d  mov     eax, [rbp+47h+arg_28]
0x180010660  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180010664  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180010668  mov     r9, r13; void *
0x18001066b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18001066f  mov     rcx, rdi; this
0x180010672  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180010677  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001067c  xor     r9d, r9d
0x18001067f  mov     [rbp+47h+var_A8], rax
0x180010683  mov     rbx, rax
0x180010686  test    rax, rax
0x180010689  jnz     short loc_180010692
0x18001068b  mov     al, 1
0x18001068d  jmp     loc_1800107C0
0x180010692  mov     byte ptr [rbp+47h+arg_0], 1
0x180010696  jmp     short loc_18001069C
0x180010698  mov     [rbp+47h+var_A8], rbx
0x18001069c  test    sil, sil
0x18001069f  jnz     short loc_180010629
0x1800106a1  jmp     short loc_180010625
0x1800106a3  mov     rcx, rax
0x1800106a6  mov     al, [rbp+47h+var_9E]
0x1800106a9  cmp     al, 1
0x1800106ab  jnz     short loc_1800106B3
0x1800106ad  add     rcx, 2
0x1800106b1  jmp     short loc_1800106BB
0x1800106b3  cmp     al, 2
0x1800106b5  jnz     short loc_1800106BB
0x1800106b7  add     rcx, 4
0x1800106bb  movzx   eax, word ptr [rdi+6]
0x1800106bf  mov     dl, [rdi+8]
0x1800106c2  mov     r8d, [rbp+47h+arg_28]
0x1800106c6  mov     [rbp+47h+var_80], ax
0x1800106ca  mov     [rbp+47h+var_7E], dl
0x1800106cd  mov     [rbp+47h+var_7C], r8d
0x1800106d1  mov     [rbp+47h+var_78], r12w
0x1800106d6  mov     [rbp+47h+var_70], r9
0x1800106da  mov     [rbp+47h+var_68], r13
0x1800106de  test    ax, ax
0x1800106e1  jnz     short loc_1800106EB
0x1800106e3  movzx   eax, r12w
0x1800106e7  add     rax, 2
0x1800106eb  cmp     dl, 1
0x1800106ee  jnz     short loc_1800106F6
0x1800106f0  add     rax, 2
0x1800106f4  jmp     short loc_1800106FF
0x1800106f6  cmp     dl, 2
0x1800106f9  jnz     short loc_1800106FF
0x1800106fb  add     rax, 4
0x1800106ff  mov     rdx, [rdi+28h]
0x180010703  lea     rsi, [rax+rcx]
0x180010707  mov     r9, [rdi+20h]
0x18001070b  mov     rcx, rdx
0x18001070e  sub     rcx, r9
0x180010711  cmp     r9, rdx
0x180010714  sbb     rax, rax
0x180010717  and     rax, rcx
0x18001071a  cmp     rax, rsi
0x18001071d  jb      loc_1800107BE
0x180010723  sub     rdx, rsi
0x180010726  lea     rcx, [rsi+rbx]; Destination
0x18001072a  sub     rdx, rbx; DestinationSize
0x18001072d  sub     r9, rbx; SourceSize
0x180010730  mov     r8, rbx; Source
0x180010733  call    cs:__imp_memmove_s
0x180010739  add     [rdi+20h], rsi
0x18001073d  xor     ebx, ebx
0x18001073f  cmp     byte ptr [rbp+47h+arg_0], bl
0x180010742  jnz     short loc_180010757
0x180010744  mov     r8, [rdi+20h]; unsigned __int8 *
0x180010748  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001074c  lea     rcx, [rbp+47h+var_A0]; this
0x180010750  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180010755  jmp     short loc_1800107A4
0x180010757  mov     cl, [rbp+47h+var_9E]
0x18001075a  test    cl, cl
0x18001075c  jz      short loc_1800107A4
0x18001075e  mov     eax, [rbp+47h+Source]
0x180010761  lea     r8d, [rax+1]
0x180010765  cmp     eax, r8d
0x180010768  jz      short loc_1800107A4
0x18001076a  mov     [rbp+47h+Source], r8d
0x18001076e  cmp     cl, 1
0x180010771  jnz     short loc_180010787
0x180010773  mov     r9d, 2
0x180010779  mov     [rbp+47h+arg_0], r8w
0x18001077e  mov     edx, r9d
0x180010781  lea     r8, [rbp+47h+arg_0]
0x180010785  jmp     short loc_18001079A
0x180010787  cmp     cl, 2
0x18001078a  jnz     short loc_1800107A4
0x18001078c  mov     eax, 4
0x180010791  lea     r8, [rbp+47h+Source]; Source
0x180010795  mov     r9d, eax; SourceSize
0x180010798  mov     edx, eax; DestinationSize
0x18001079a  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001079e  call    cs:__imp_memcpy_s
0x1800107a4  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800107a8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800107ac  lea     rcx, [rbp+47h+var_80]; this
0x1800107b0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800107b5  mov     byte ptr [rdi+38h], 1
0x1800107b9  jmp     loc_18001068B
0x1800107be  xor     al, al
0x1800107c0  add     rsp, 0A8h
0x1800107c7  pop     r15
0x1800107c9  pop     r14
0x1800107cb  pop     r13
0x1800107cd  pop     r12
0x1800107cf  pop     rdi
0x1800107d0  pop     rsi
0x1800107d1  pop     rbx
0x1800107d2  pop     rbp
0x1800107d3  retn
```

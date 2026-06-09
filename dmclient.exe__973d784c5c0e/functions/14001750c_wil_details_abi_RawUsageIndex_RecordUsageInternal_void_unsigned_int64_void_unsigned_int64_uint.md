# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14001750c`
- end: `0x1400178a5`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `921`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140017338`

## callees

- `0x140016538`
- `0x140016ee0`
- `0x14001750c`
- `0x140018608`
- `0x1400195d6`

## import_xrefs

- `msvcrt!memmove_s` at `0x1400177f7`
- `msvcrt!memmove_s` at `0x1400177f7`
- `msvcrt!memcpy_s` at `0x140017617`
- `msvcrt!memcpy_s` at `0x1400176b6`
- `msvcrt!memcpy_s` at `0x140017868`
- `msvcrt!memcpy_s` at `0x140017617`
- `msvcrt!memcpy_s` at `0x1400176b6`
- `msvcrt!memcpy_s` at `0x140017868`

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
0x14001750c  push    rbp
0x14001750e  push    rbx
0x14001750f  push    rsi
0x140017510  push    rdi
0x140017511  push    r12
0x140017513  push    r13
0x140017515  push    r14
0x140017517  push    r15
0x140017519  lea     rbp, [rsp-0Fh]
0x14001751e  sub     rsp, 0A8h
0x140017525  mov     rbx, [rcx+18h]
0x140017529  mov     rdi, rcx
0x14001752c  xor     ecx, ecx
0x14001752e  mov     r13, r9
0x140017531  mov     r14, r8
0x140017534  mov     r15, rdx
0x140017537  test    rbx, rbx
0x14001753a  jz      loc_14001788E
0x140017540  movzx   eax, word ptr [rdi+2]
0x140017544  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140017548  mov     r8, [rdi+20h]; unsigned __int8 *
0x14001754c  add     rbx, 0Ah
0x140017550  mov     [rbp+47h+var_A0], ax
0x140017554  xorps   xmm0, xmm0
0x140017557  mov     al, [rdi+4]
0x14001755a  mov     [rbp+47h+Source], ecx
0x14001755d  mov     [rbp+47h+var_98], cx
0x140017561  mov     byte ptr [rbp+47h+arg_0], cl
0x140017564  lea     rcx, [rbp+47h+var_A0]; this
0x140017568  mov     [rbp+47h+var_9E], al
0x14001756b  mov     [rbp+47h+var_A8], rbx
0x14001756f  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x140017574  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140017579  mov     r12, [rbp+47h+arg_20]
0x14001757d  jmp     loc_1400176D7
0x140017582  movzx   eax, [rbp+47h+var_98]
0x140017586  cmp     r14, rax
0x140017589  jnz     short loc_1400175A1
0x14001758b  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x14001758f  mov     r8, r14; Size
0x140017592  mov     rcx, r15; Buf1
0x140017595  call    memcmp_0
0x14001759a  mov     ecx, eax
0x14001759c  xor     r9d, r9d
0x14001759f  jmp     short loc_1400175AA
0x1400175a1  movzx   eax, [rbp+47h+var_98]
0x1400175a5  mov     ecx, r14d
0x1400175a8  sub     ecx, eax
0x1400175aa  test    ecx, ecx
0x1400175ac  js      loc_14001775C
0x1400175b2  jz      loc_140017721
0x1400175b8  mov     rbx, [rbp+47h+var_A8]
0x1400175bc  mov     [rbp+47h+var_A8], rbx
0x1400175c0  cmp     [rdi+10h], r9
0x1400175c4  jbe     short loc_140017635
0x1400175c6  mov     rax, [rdi+20h]
0x1400175ca  xor     edx, edx
0x1400175cc  sub     rax, [rdi+18h]
0x1400175d0  mov     rsi, rbx
0x1400175d3  div     qword ptr [rdi+10h]
0x1400175d7  mov     edx, [rbp+47h+Source]
0x1400175da  cmp     rdx, rax
0x1400175dd  jbe     short loc_140017626
0x1400175df  cmp     edx, eax
0x1400175e1  jz      short loc_140017626
0x1400175e3  mov     edx, eax
0x1400175e5  mov     [rbp+47h+Source], eax
0x1400175e8  mov     al, [rbp+47h+var_9E]
0x1400175eb  cmp     al, 1
0x1400175ed  jnz     short loc_140017602
0x1400175ef  movzx   eax, dx
0x1400175f2  mov     [rbp+47h+var_B0], dx
0x1400175f6  mov     r9d, 2
0x1400175fc  lea     r8, [rbp+47h+var_B0]
0x140017600  jmp     short loc_140017610
0x140017602  cmp     al, 2
0x140017604  jnz     short loc_140017626
0x140017606  mov     r9d, 4; SourceSize
0x14001760c  lea     r8, [rbp+47h+Source]; Source
0x140017610  mov     rcx, [rbp+47h+Buf2]; Destination
0x140017614  mov     rdx, r9; DestinationSize
0x140017617  call    cs:__imp_memcpy_s
0x14001761e  nop     dword ptr [rax+rax+00h]
0x140017623  mov     edx, [rbp+47h+Source]
0x140017626  mov     ebx, edx
0x140017628  imul    rbx, [rdi+10h]
0x14001762d  add     rbx, rsi
0x140017630  jmp     loc_1400176C2
0x140017635  movzx   eax, word ptr [rdi+6]
0x140017639  xorps   xmm0, xmm0
0x14001763c  mov     [rbp+47h+var_60], ax
0x140017640  mov     esi, r9d
0x140017643  mov     al, [rdi+8]
0x140017646  mov     [rbp+47h+var_5E], al
0x140017649  mov     eax, [rbp+47h+Source]
0x14001764c  mov     [rbp+47h+var_5C], r9d
0x140017650  mov     [rbp+47h+var_58], r9w
0x140017655  movdqu  [rbp+47h+var_50], xmm0
0x14001765a  test    eax, eax
0x14001765c  jz      short loc_140017680
0x14001765e  mov     r8, [rdi+20h]; unsigned __int8 *
0x140017662  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140017666  lea     rcx, [rbp+47h+var_60]; this
0x14001766a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14001766f  test    al, al
0x140017671  mov     eax, [rbp+47h+Source]
0x140017674  jz      short loc_14001767C
0x140017676  inc     esi
0x140017678  cmp     esi, eax
0x14001767a  jb      short loc_14001765E
0x14001767c  mov     rbx, [rbp+47h+var_A8]
0x140017680  cmp     eax, esi
0x140017682  jz      short loc_1400176C2
0x140017684  mov     al, [rbp+47h+var_9E]
0x140017687  mov     [rbp+47h+Source], esi
0x14001768a  cmp     al, 1
0x14001768c  jnz     short loc_1400176A2
0x14001768e  mov     eax, 2
0x140017693  mov     [rbp+47h+var_B0], si
0x140017697  mov     r9d, eax
0x14001769a  lea     r8, [rbp+47h+var_B0]
0x14001769e  mov     edx, eax
0x1400176a0  jmp     short loc_1400176B2
0x1400176a2  cmp     al, 2
0x1400176a4  jnz     short loc_1400176C2
0x1400176a6  mov     edx, 4; DestinationSize
0x1400176ab  lea     r8, [rbp+47h+Source]; Source
0x1400176af  mov     r9d, edx; SourceSize
0x1400176b2  mov     rcx, [rbp+47h+Buf2]; Destination
0x1400176b6  call    cs:__imp_memcpy_s
0x1400176bd  nop     dword ptr [rax+rax+00h]
0x1400176c2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400176c6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1400176ca  lea     rcx, [rbp+47h+var_A0]; this
0x1400176ce  mov     [rbp+47h+var_A8], rbx
0x1400176d2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400176d7  xor     r9d, r9d
0x1400176da  mov     sil, al
0x1400176dd  test    al, al
0x1400176df  jnz     loc_140017582
0x1400176e5  mov     rbx, [rbp+47h+var_A8]
0x1400176e9  mov     [rdi+20h], rbx
0x1400176ed  mov     rcx, r9
0x1400176f0  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1400176f4  jnz     loc_14001777F
0x1400176fa  movzx   eax, [rbp+47h+var_A0]
0x1400176fe  mov     [rbp+47h+Source], 1
0x140017705  mov     [rbp+47h+var_98], r14w
0x14001770a  mov     [rbp+47h+Buf2], r9
0x14001770e  mov     [rbp+47h+Buf2+8], r15
0x140017712  test    ax, ax
0x140017715  jnz     short loc_140017767
0x140017717  movzx   ecx, r14w
0x14001771b  add     rcx, 2
0x14001771f  jmp     short loc_14001776A
0x140017721  mov     eax, [rbp+47h+arg_28]
0x140017724  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x140017728  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x14001772c  mov     r9, r13; void *
0x14001772f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x140017733  mov     rcx, rdi; this
0x140017736  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x14001773b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x140017740  xor     r9d, r9d
0x140017743  mov     [rbp+47h+var_A8], rax
0x140017747  mov     rbx, rax
0x14001774a  test    rax, rax
0x14001774d  jnz     short loc_140017756
0x14001774f  mov     al, 1
0x140017751  jmp     loc_140017890
0x140017756  mov     byte ptr [rbp+47h+arg_0], 1
0x14001775a  jmp     short loc_140017760
0x14001775c  mov     [rbp+47h+var_A8], rbx
0x140017760  test    sil, sil
0x140017763  jnz     short loc_1400176ED
0x140017765  jmp     short loc_1400176E9
0x140017767  mov     rcx, rax
0x14001776a  mov     al, [rbp+47h+var_9E]
0x14001776d  cmp     al, 1
0x14001776f  jnz     short loc_140017777
0x140017771  add     rcx, 2
0x140017775  jmp     short loc_14001777F
0x140017777  cmp     al, 2
0x140017779  jnz     short loc_14001777F
0x14001777b  add     rcx, 4
0x14001777f  movzx   eax, word ptr [rdi+6]
0x140017783  mov     dl, [rdi+8]
0x140017786  mov     r8d, [rbp+47h+arg_28]
0x14001778a  mov     [rbp+47h+var_80], ax
0x14001778e  mov     [rbp+47h+var_7E], dl
0x140017791  mov     [rbp+47h+var_7C], r8d
0x140017795  mov     [rbp+47h+var_78], r12w
0x14001779a  mov     [rbp+47h+var_70], r9
0x14001779e  mov     [rbp+47h+var_68], r13
0x1400177a2  test    ax, ax
0x1400177a5  jnz     short loc_1400177AF
0x1400177a7  movzx   eax, r12w
0x1400177ab  add     rax, 2
0x1400177af  cmp     dl, 1
0x1400177b2  jnz     short loc_1400177BA
0x1400177b4  add     rax, 2
0x1400177b8  jmp     short loc_1400177C3
0x1400177ba  cmp     dl, 2
0x1400177bd  jnz     short loc_1400177C3
0x1400177bf  add     rax, 4
0x1400177c3  mov     rdx, [rdi+28h]
0x1400177c7  lea     rsi, [rax+rcx]
0x1400177cb  mov     r9, [rdi+20h]
0x1400177cf  mov     rcx, rdx
0x1400177d2  sub     rcx, r9
0x1400177d5  cmp     r9, rdx
0x1400177d8  sbb     rax, rax
0x1400177db  and     rax, rcx
0x1400177de  cmp     rax, rsi
0x1400177e1  jb      loc_14001788E
0x1400177e7  sub     rdx, rsi
0x1400177ea  lea     rcx, [rsi+rbx]; Destination
0x1400177ee  sub     rdx, rbx; DestinationSize
0x1400177f1  sub     r9, rbx; SourceSize
0x1400177f4  mov     r8, rbx; Source
0x1400177f7  call    cs:__imp_memmove_s
0x1400177fe  nop     dword ptr [rax+rax+00h]
0x140017803  add     [rdi+20h], rsi
0x140017807  xor     ebx, ebx
0x140017809  cmp     byte ptr [rbp+47h+arg_0], bl
0x14001780c  jnz     short loc_140017821
0x14001780e  mov     r8, [rdi+20h]; unsigned __int8 *
0x140017812  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140017816  lea     rcx, [rbp+47h+var_A0]; this
0x14001781a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14001781f  jmp     short loc_140017874
0x140017821  mov     cl, [rbp+47h+var_9E]
0x140017824  test    cl, cl
0x140017826  jz      short loc_140017874
0x140017828  mov     eax, [rbp+47h+Source]
0x14001782b  lea     r8d, [rax+1]
0x14001782f  cmp     eax, r8d
0x140017832  jz      short loc_140017874
0x140017834  mov     [rbp+47h+Source], r8d
0x140017838  cmp     cl, 1
0x14001783b  jnz     short loc_140017851
0x14001783d  mov     r9d, 2
0x140017843  mov     [rbp+47h+arg_0], r8w
0x140017848  mov     edx, r9d
0x14001784b  lea     r8, [rbp+47h+arg_0]
0x14001784f  jmp     short loc_140017864
0x140017851  cmp     cl, 2
0x140017854  jnz     short loc_140017874
0x140017856  mov     eax, 4
0x14001785b  lea     r8, [rbp+47h+Source]; Source
0x14001785f  mov     r9d, eax; SourceSize
0x140017862  mov     edx, eax; DestinationSize
0x140017864  mov     rcx, [rbp+47h+Buf2]; Destination
0x140017868  call    cs:__imp_memcpy_s
0x14001786f  nop     dword ptr [rax+rax+00h]
0x140017874  mov     r8, [rdi+20h]; unsigned __int8 *
0x140017878  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14001787c  lea     rcx, [rbp+47h+var_80]; this
0x140017880  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140017885  mov     byte ptr [rdi+38h], 1
0x140017889  jmp     loc_14001774F
0x14001788e  xor     al, al
0x140017890  add     rsp, 0A8h
0x140017897  pop     r15
0x140017899  pop     r14
0x14001789b  pop     r13
0x14001789d  pop     r12
0x14001789f  pop     rdi
0x1400178a0  pop     rsi
0x1400178a1  pop     rbx
0x1400178a2  pop     rbp
0x1400178a3  retn
```

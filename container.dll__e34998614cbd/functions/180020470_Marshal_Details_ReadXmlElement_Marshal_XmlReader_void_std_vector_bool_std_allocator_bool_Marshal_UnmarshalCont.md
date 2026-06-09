# Marshal::Details::ReadXmlElement(Marshal::XmlReader &,void *,std::vector<bool,std::allocator<bool>> &,Marshal::UnmarshalContext const &,Marshal::ClassData const &,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)

- ea: `0x180020470`
- end: `0x180020842`
- name: `?ReadXmlElement@Details@Marshal@@YA_NAEAUXmlReader@2@PEAXAEAV?$vector@_NV?$allocator@_N@std@@@std@@AEBVUnmarshalContext@2@AEBUClassData@2@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z`
- size: `978`
- prototype: `__int64 __usercall@<rax>(Marshal::Details *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ff3c`

## callees

- `0x180020470`
- `0x1800208b8`
- `0x180020b18`
- `0x180021058`
- `0x180022094`
- `0x180034010`

## pseudocode

```c
bool __fastcall Marshal::Details::ReadXmlElement(
        Marshal::Details *this,
        wchar_t *a2,
        _QWORD *a3,
        __int64 a4,
        __int64 *a5,
        _QWORD *a6)
{
  char *v6; // rbx
  __int64 v7; // rsi
  bool v8; // cc
  Marshal::Details *v9; // r15
  __int64 v10; // r14
  size_t v11; // r8
  __int64 v12; // r13
  __int64 v13; // rdi
  unsigned int *v14; // r12
  unsigned int *v15; // rax
  __int64 v16; // rbx
  size_t v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rcx
  const wchar_t *v20; // rdi
  int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // rax
  size_t v24; // r8
  int v25; // eax
  __int64 v26; // r11
  __int64 v27; // r10
  __int64 v28; // r9
  __int64 v29; // r12
  char v30; // di
  unsigned __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rdx
  char *v35; // r8
  unsigned __int8 (__fastcall *v36)(Marshal::Details *, char *, void ***); // r10
  struct Marshal::XmlReader *v37; // rdx
  wchar_t *S1; // [rsp+28h] [rbp-79h]
  void **v39; // [rsp+30h] [rbp-71h] BYREF
  __int64 v40; // [rsp+38h] [rbp-69h]
  __int64 v41; // [rsp+40h] [rbp-61h]
  char *v42; // [rsp+48h] [rbp-59h]
  __int64 v43; // [rsp+50h] [rbp-51h]
  void *v44; // [rsp+58h] [rbp-49h] BYREF
  size_t v45; // [rsp+60h] [rbp-41h]
  __int64 v46; // [rsp+68h] [rbp-39h] BYREF
  size_t v47; // [rsp+70h] [rbp-31h]
  size_t N; // [rsp+78h] [rbp-29h]
  __int64 *v49; // [rsp+80h] [rbp-21h]
  unsigned int *v50; // [rsp+88h] [rbp-19h]
  char *v51; // [rsp+90h] [rbp-11h]
  unsigned int *v52; // [rsp+98h] [rbp-9h]
  wchar_t *v54; // [rsp+100h] [rbp+5Fh]

  v54 = a2;
  v6 = (char *)this + 8;
  v7 = a4;
  v8 = *((_QWORD *)this + 4) <= 7u;
  v9 = this;
  v51 = (char *)this + 8;
  if ( v8 )
    S1 = (wchar_t *)((char *)this + 8);
  else
    S1 = *(wchar_t **)v6;
  v10 = (__int64)a5;
  v11 = *((_QWORD *)this + 3);
  v12 = -1;
  v49 = (__int64 *)((char *)this + 24);
  N = v11;
  v13 = *((unsigned int *)a5 + 4);
  v14 = (unsigned int *)a5[1];
  v15 = &v14[v13];
  v52 = v15;
  if ( v13 )
  {
    v16 = *a5;
    v17 = v11;
    do
    {
      v50 = &v14[v13 / 2];
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(*(_QWORD *)(32LL * *v50 + v16) + 2 * v18) );
      v46 = *(_QWORD *)(32LL * *v50 + v16);
      v44 = S1;
      v45 = v17;
      v47 = v18;
      if ( (int)Marshal::Details::StringCompareCaseInsensitive(&v46, &v44) >= 0 )
      {
        v13 /= 2;
      }
      else
      {
        v14 = v50 + 1;
        v13 += -1 - v13 / 2;
      }
    }
    while ( v13 > 0 );
    v6 = v51;
    v7 = a4;
    v9 = this;
    v10 = (__int64)a5;
    v15 = v52;
    v11 = N;
  }
  if ( v14 == v15 )
    goto LABEL_22;
  a2 = *(wchar_t **)(32LL * *v14 + *(_QWORD *)v10);
  v19 = -1;
  do
    ++v19;
  while ( a2[v19] );
  if ( v11 != v19 )
  {
LABEL_22:
    v20 = S1;
  }
  else
  {
    v20 = S1;
    if ( (*(_BYTE *)(*(_QWORD *)(v7 + 8) + 24LL) & 2) != 0 )
    {
      v46 = *(_QWORD *)(32LL * *v14 + *(_QWORD *)v10);
      v47 = v19;
      v44 = S1;
      v45 = v11;
      v21 = Marshal::Details::StringCompareCaseInsensitive(&v44, &v46);
    }
    else
    {
      v21 = wmemcmp(S1, a2, v11);
    }
    if ( !v21 )
    {
      v22 = *v14;
      goto LABEL_33;
    }
  }
  if ( v14 == *(unsigned int **)(v10 + 8) )
    goto LABEL_50;
  v23 = 32LL * *(v14 - 1);
  if ( (*(_BYTE *)(v23 + *(_QWORD *)v10 + 12) & 0x10) == 0 )
    goto LABEL_50;
  a2 = *(wchar_t **)(v23 + *(_QWORD *)v10);
  v24 = -1;
  do
    ++v24;
  while ( a2[v24] );
  if ( N < v24 )
    goto LABEL_50;
  if ( (*(_BYTE *)(*(_QWORD *)(v7 + 8) + 24LL) & 2) != 0 )
  {
    v46 = *(_QWORD *)(v23 + *(_QWORD *)v10);
    v47 = v24;
    v44 = (void *)v20;
    v45 = v24;
    v25 = Marshal::Details::StringCompareCaseInsensitive(&v44, &v46);
  }
  else
  {
    v25 = wmemcmp(v20, a2, v24);
  }
  if ( v25 )
    goto LABEL_50;
  v22 = *(v14 - 1);
LABEL_33:
  if ( v22 >= *(_DWORD *)(v10 + 16)
    || (v26 = *(_QWORD *)v10,
        v27 = v22,
        v28 = 32LL * v22,
        ((*(_DWORD *)(v28 + *(_QWORD *)v10 + 12) & 4) != 0) != *((_BYTE *)v9 + 48)) )
  {
LABEL_50:
    if ( (*(_BYTE *)(*(_QWORD *)(v7 + 8) + 24LL) & 4) != 0 )
    {
      if ( *((_QWORD *)v6 + 3) > 7u )
        v6 = *(char **)v6;
      v40 = *(_QWORD *)(v7 + 8);
      v41 = v7;
      v39 = &Marshal::Details::UnmarshalFieldContext::`vftable';
      v42 = v6;
      v43 = *v49;
      Marshal::UnmarshalContext::ReportError(&v39, 17);
      if ( !*((_BYTE *)v9 + 48) )
        Marshal::Details::SkipElement(v9, v37);
      return 0;
    }
    if ( *((_BYTE *)v9 + 48) || Marshal::Details::SkipElement(v9, (struct Marshal::XmlReader *)a2) )
      return 1;
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(char **)v6;
    v33 = 15;
    goto LABEL_44;
  }
  v29 = *(unsigned int *)(v28 + v26 + 8);
  v30 = v22 & 0x1F;
  v31 = 4 * ((unsigned __int64)v22 >> 5);
  if ( (*(_BYTE *)(v28 + v26 + 12) & 0x10) != 0 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)(*(_QWORD *)(v28 + v26) + 2 * v32) );
    *((_QWORD *)v9 + 5) = v32;
    goto LABEL_46;
  }
  if ( ((1 << v30) & *(_DWORD *)(v31 + *a3)) != 0 && !*(_QWORD *)(*(_QWORD *)(*a6 + 8LL * v22) + 16LL) )
  {
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(char **)v6;
    v33 = 16;
LABEL_44:
    v40 = *(_QWORD *)(v7 + 8);
    v39 = &Marshal::Details::UnmarshalFieldContext::`vftable';
    v42 = v6;
    v41 = v7;
    v43 = *v49;
    Marshal::UnmarshalContext::ReportError(&v39, v33);
    return 0;
  }
LABEL_46:
  *(_DWORD *)(*a3 + v31) |= 1 << v30;
  v35 = *(char **)(v28 + v26);
  v36 = *(unsigned __int8 (__fastcall **)(Marshal::Details *, char *, void ***))(*(_QWORD *)(*a6 + 8 * v27) + 8LL);
  do
    ++v12;
  while ( *(_WORD *)&v35[2 * v12] );
  v40 = *(_QWORD *)(v7 + 8);
  v39 = &Marshal::Details::UnmarshalFieldContext::`vftable';
  v42 = v35;
  v41 = v7;
  v43 = v12;
  return v36(v9, (char *)v54 + v29, &v39) != 0;
}

```

## disassembly

```asm
0x180020470  mov     rax, rsp
0x180020473  mov     [rax+20h], r9
0x180020477  mov     [rax+18h], r8
0x18002047b  mov     [rax+10h], rdx
0x18002047f  mov     [rax+8], rcx
0x180020483  push    rbp
0x180020484  push    rbx
0x180020485  push    rsi
0x180020486  push    rdi
0x180020487  push    r12
0x180020489  push    r13
0x18002048b  push    r14
0x18002048d  push    r15
0x18002048f  lea     rbp, [rax-4Fh]
0x180020493  sub     rsp, 0A8h
0x18002049a  lea     rbx, [rcx+8]
0x18002049e  mov     rsi, r9
0x1800204a1  cmp     qword ptr [rbx+18h], 7
0x1800204a6  mov     r15, rcx
0x1800204a9  mov     [rbp+47h+var_58], rbx
0x1800204ad  jbe     short loc_1800204B8
0x1800204af  mov     rax, [rbx]
0x1800204b2  mov     [rbp+47h+S1], rax
0x1800204b6  jmp     short loc_1800204BC
0x1800204b8  mov     [rbp+47h+S1], rbx
0x1800204bc  mov     r14, [rbp+47h+arg_20]
0x1800204c0  lea     rax, [rbx+10h]
0x1800204c4  mov     r8, [rax]
0x1800204c7  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800204cb  mov     [rbp+47h+var_68], rax
0x1800204cf  xor     r9d, r9d
0x1800204d2  mov     [rbp+47h+N], r8
0x1800204d6  mov     edi, [r14+10h]
0x1800204da  mov     r12, [r14+8]
0x1800204de  lea     rax, [r12+rdi*4]
0x1800204e2  mov     [rbp+47h+var_50], rax
0x1800204e6  test    rdi, rdi
0x1800204e9  jz      loc_18002057E
0x1800204ef  mov     rbx, [r14]
0x1800204f2  mov     rsi, r8
0x1800204f5  mov     r15, [rbp+47h+S1]
0x1800204f9  mov     r14, rdi
0x1800204fc  test    rdi, rdi
0x1800204ff  jns     short loc_180020505
0x180020501  lea     r14, [rdi+1]
0x180020505  sar     r14, 1
0x180020508  lea     rax, [r12+r14*4]
0x18002050c  mov     [rbp+47h+var_60], rax
0x180020510  mov     eax, [rax]
0x180020512  shl     rax, 5
0x180020516  mov     rcx, [rax+rbx]
0x18002051a  mov     rax, r13
0x18002051d  inc     rax
0x180020520  cmp     [rcx+rax*2], r9w
0x180020525  jnz     short loc_18002051D
0x180020527  mov     [rbp+47h+var_80], rcx
0x18002052b  lea     rdx, [rbp+47h+var_90]
0x18002052f  lea     rcx, [rbp+47h+var_80]
0x180020533  mov     [rbp+47h+var_90], r15
0x180020537  mov     [rbp+47h+var_88], rsi
0x18002053b  mov     [rbp+47h+var_78], rax
0x18002053f  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x180020544  xor     r9d, r9d
0x180020547  test    eax, eax
0x180020549  jns     short loc_18002055E
0x18002054b  mov     r12, [rbp+47h+var_60]
0x18002054f  mov     rax, r13
0x180020552  add     r12, 4
0x180020556  sub     rax, r14
0x180020559  add     rdi, rax
0x18002055c  jmp     short loc_180020561
0x18002055e  mov     rdi, r14
0x180020561  test    rdi, rdi
0x180020564  jg      short loc_1800204F9
0x180020566  mov     rbx, [rbp+47h+var_58]
0x18002056a  mov     rsi, [rbp+47h+arg_18]
0x18002056e  mov     r15, [rbp+47h+arg_0]
0x180020572  mov     r14, [rbp+47h+arg_20]
0x180020576  mov     rax, [rbp+47h+var_50]
0x18002057a  mov     r8, [rbp+47h+N]; N
0x18002057e  cmp     r12, rax
0x180020581  jz      short loc_1800205E9
0x180020583  mov     ecx, [r12]
0x180020587  mov     rax, [r14]
0x18002058a  shl     rcx, 5
0x18002058e  mov     rdx, [rcx+rax]; S2
0x180020592  mov     rcx, r13
0x180020595  inc     rcx
0x180020598  cmp     [rdx+rcx*2], r9w
0x18002059d  jnz     short loc_180020595
0x18002059f  cmp     r8, rcx
0x1800205a2  jnz     short loc_1800205E9
0x1800205a4  mov     rax, [rsi+8]
0x1800205a8  mov     rdi, [rbp+47h+S1]
0x1800205ac  test    byte ptr [rax+18h], 2
0x1800205b0  jz      short loc_1800205D1
0x1800205b2  mov     [rbp+47h+var_80], rdx
0x1800205b6  lea     rdx, [rbp+47h+var_80]
0x1800205ba  mov     [rbp+47h+var_78], rcx
0x1800205be  lea     rcx, [rbp+47h+var_90]
0x1800205c2  mov     [rbp+47h+var_90], rdi
0x1800205c6  mov     [rbp+47h+var_88], r8
0x1800205ca  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800205cf  jmp     short loc_1800205D9
0x1800205d1  mov     rcx, rdi; S1
0x1800205d4  call    wmemcmp
0x1800205d9  xor     r9d, r9d
0x1800205dc  test    eax, eax
0x1800205de  jnz     short loc_1800205ED
0x1800205e0  mov     eax, [r12]
0x1800205e4  jmp     loc_18002066C
0x1800205e9  mov     rdi, [rbp+47h+S1]
0x1800205ed  cmp     r12, [r14+8]
0x1800205f1  jz      loc_1800207BA
0x1800205f7  mov     eax, [r12-4]
0x1800205fc  mov     rcx, [r14]
0x1800205ff  shl     rax, 5
0x180020603  test    byte ptr [rax+rcx+0Ch], 10h
0x180020608  jz      loc_1800207BA
0x18002060e  mov     rdx, [rax+rcx]; S2
0x180020612  mov     r8, r13
0x180020615  inc     r8; N
0x180020618  cmp     [rdx+r8*2], r9w
0x18002061d  jnz     short loc_180020615
0x18002061f  cmp     [rbp+47h+N], r8
0x180020623  jb      loc_1800207BA
0x180020629  mov     rax, [rsi+8]
0x18002062d  test    byte ptr [rax+18h], 2
0x180020631  jz      short loc_180020652
0x180020633  mov     [rbp+47h+var_80], rdx
0x180020637  lea     rcx, [rbp+47h+var_90]
0x18002063b  lea     rdx, [rbp+47h+var_80]
0x18002063f  mov     [rbp+47h+var_78], r8
0x180020643  mov     [rbp+47h+var_90], rdi
0x180020647  mov     [rbp+47h+var_88], r8
0x18002064b  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x180020650  jmp     short loc_18002065A
0x180020652  mov     rcx, rdi; S1
0x180020655  call    wmemcmp
0x18002065a  test    eax, eax
0x18002065c  setz    al
0x18002065f  test    al, al
0x180020661  jz      loc_1800207BA
0x180020667  mov     eax, [r12-4]
0x18002066c  cmp     eax, [r14+10h]
0x180020670  jnb     loc_1800207BA
0x180020676  mov     r11, [r14]
0x180020679  mov     r9d, eax
0x18002067c  mov     r10d, eax
0x18002067f  shl     r9, 5
0x180020683  mov     eax, [r9+r11+0Ch]
0x180020688  shr     eax, 2
0x18002068b  and     eax, 1
0x18002068e  cmp     al, [r15+30h]
0x180020692  jnz     loc_1800207BA
0x180020698  mov     r12d, [r9+r11+8]
0x18002069d  mov     eax, r10d
0x1800206a0  mov     r14, [rbp+47h+arg_28]
0x1800206a4  mov     edi, r10d
0x1800206a7  shr     rax, 5
0x1800206ab  and     edi, 1Fh
0x1800206ae  test    byte ptr [r9+r11+0Ch], 10h
0x1800206b4  lea     r8, ds:0[rax*4]
0x1800206bc  jz      short loc_1800206D6
0x1800206be  mov     rcx, [r9+r11]
0x1800206c2  mov     rax, r13
0x1800206c5  xor     ebx, ebx
0x1800206c7  inc     rax
0x1800206ca  cmp     [rcx+rax*2], bx
0x1800206ce  jnz     short loc_1800206C7
0x1800206d0  mov     [r15+28h], rax
0x1800206d4  jmp     short loc_18002073F
0x1800206d6  mov     rdx, [rbp+47h+arg_10]
0x1800206da  mov     rcx, rdi
0x1800206dd  mov     eax, 1
0x1800206e2  shl     eax, cl
0x1800206e4  mov     rdx, [rdx]
0x1800206e7  test    [r8+rdx], eax
0x1800206eb  jz      short loc_18002073D
0x1800206ed  mov     rax, [r14]
0x1800206f0  mov     rcx, [rax+r10*8]
0x1800206f4  cmp     qword ptr [rcx+10h], 0
0x1800206f9  jnz     short loc_18002073D
0x1800206fb  cmp     qword ptr [rbx+18h], 7
0x180020700  jbe     short loc_180020705
0x180020702  mov     rbx, [rbx]
0x180020705  mov     edx, 10h
0x18002070a  mov     rax, [rsi+8]
0x18002070e  lea     rcx, [rbp+47h+var_B8]
0x180020712  mov     [rbp+47h+var_B0], rax
0x180020716  lea     rax, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x18002071d  mov     [rbp+47h+var_B8], rax
0x180020721  mov     rax, [rbp+47h+var_68]
0x180020725  mov     [rbp+47h+var_A0], rbx
0x180020729  mov     [rbp+47h+var_A8], rsi
0x18002072d  mov     rax, [rax]
0x180020730  mov     [rbp+47h+var_98], rax
0x180020734  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x180020739  xor     al, al
0x18002073b  jmp     short loc_1800207A5
0x18002073d  xor     ebx, ebx
0x18002073f  mov     rax, [rbp+47h+arg_10]
0x180020743  mov     rdx, r12
0x180020746  add     rdx, [rbp+47h+arg_8]
0x18002074a  mov     rcx, [rax]
0x18002074d  mov     eax, [rcx+r8]
0x180020751  bts     eax, edi
0x180020754  mov     [rcx+r8], eax
0x180020758  mov     rax, [r14]
0x18002075b  mov     r8, [r9+r11]
0x18002075f  mov     rcx, [rax+r10*8]
0x180020763  mov     r10, [rcx+8]
0x180020767  inc     r13
0x18002076a  cmp     [r8+r13*2], bx
0x18002076f  jnz     short loc_180020767
0x180020771  mov     rcx, [rsi+8]
0x180020775  lea     rax, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x18002077c  mov     [rbp+47h+var_B0], rcx
0x180020780  mov     rcx, r15
0x180020783  mov     [rbp+47h+var_B8], rax
0x180020787  mov     rax, r10
0x18002078a  mov     [rbp+47h+var_A0], r8
0x18002078e  lea     r8, [rbp+47h+var_B8]
0x180020792  mov     [rbp+47h+var_A8], rsi
0x180020796  mov     [rbp+47h+var_98], r13
0x18002079a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002079f  test    al, al
0x1800207a1  jz      short loc_180020739
0x1800207a3  mov     al, 1
0x1800207a5  add     rsp, 0A8h
0x1800207ac  pop     r15
0x1800207ae  pop     r14
0x1800207b0  pop     r13
0x1800207b2  pop     r12
0x1800207b4  pop     rdi
0x1800207b5  pop     rsi
0x1800207b6  pop     rbx
0x1800207b7  pop     rbp
0x1800207b8  retn
0x1800207ba  mov     rax, [rsi+8]
0x1800207be  test    byte ptr [rax+18h], 4
0x1800207c2  jz      short loc_180020816
0x1800207c4  cmp     qword ptr [rbx+18h], 7
0x1800207c9  jbe     short loc_1800207CE
0x1800207cb  mov     rbx, [rbx]
0x1800207ce  mov     [rbp+47h+var_B0], rax
0x1800207d2  lea     rcx, [rbp+47h+var_B8]
0x1800207d6  lea     rax, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x1800207dd  mov     [rbp+47h+var_A8], rsi
0x1800207e1  mov     [rbp+47h+var_B8], rax
0x1800207e5  mov     edx, 11h
0x1800207ea  mov     rax, [rbp+47h+var_68]
0x1800207ee  mov     [rbp+47h+var_A0], rbx
0x1800207f2  mov     rax, [rax]
0x1800207f5  mov     [rbp+47h+var_98], rax
0x1800207f9  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x1800207fe  cmp     byte ptr [r15+30h], 0
0x180020803  jnz     loc_180020739
0x180020809  mov     rcx, r15; this
0x18002080c  call    ?SkipElement@Details@Marshal@@YA_NAEAUXmlReader@2@@Z; Marshal::Details::SkipElement(Marshal::XmlReader &)
0x180020811  jmp     loc_180020739
0x180020816  xor     edi, edi
0x180020818  cmp     [r15+30h], dil
0x18002081c  jnz     short loc_1800207A3
0x18002081e  mov     rcx, r15; this
0x180020821  call    ?SkipElement@Details@Marshal@@YA_NAEAUXmlReader@2@@Z; Marshal::Details::SkipElement(Marshal::XmlReader &)
0x180020826  test    al, al
0x180020828  jnz     loc_1800207A3
0x18002082e  cmp     qword ptr [rbx+18h], 7
0x180020833  jbe     short loc_180020838
0x180020835  mov     rbx, [rbx]
0x180020838  mov     edx, 0Fh
0x18002083d  jmp     loc_18002070A
```

# RtlCreateProcessParametersInternal

- ea: `0x1800980b0`
- end: `0x1800985e0`
- name: `RtlCreateProcessParametersInternal`
- size: `1328`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *Src, __int64, __int64, __int64, __int64, __int64, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `reparse_path, loader_planting`

## callers

- `0x180097e60`
- `0x180097fa0`
- `0x18015c790`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18006ffa0`
- `0x180070490`
- `0x1800980b0`
- `0x1800985e8`
- `0x1800985fc`
- `0x18009867c`
- `0x1800986c0`
- `0x180121cd0`
- `0x180164280`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlCreateProcessParametersInternal(
        _QWORD *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        void *Src,
        __int64 *a7,
        __int64 *a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        int a12)
{
  __int64 v14; // r8
  __int64 v15; // rdx
  unsigned __int64 v16; // r15
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int16 *v19; // r9
  __int64 *v20; // r10
  __int64 *v21; // r11
  __int64 v22; // rdx
  unsigned __int16 *v23; // r14
  __int64 *v24; // r9
  __int64 *v25; // rax
  __int64 *v26; // rdi
  __int64 *v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // r10
  __int64 v30; // rax
  unsigned __int64 v31; // r10
  unsigned __int64 v32; // rdi
  size_t BlockSize; // rsi
  unsigned __int64 i; // r14
  __int64 Heap_0; // rax
  _DWORD *v36; // rbx
  char *v37; // rsi
  __int64 v38; // rsi
  int v39; // eax
  __int64 v40; // r9
  size_t v42; // r8
  __int16 v43; // r9
  char v44; // [rsp+20h] [rbp-40h]
  unsigned __int64 v45; // [rsp+28h] [rbp-38h] BYREF
  __int64 v46; // [rsp+30h] [rbp-30h]
  unsigned __int16 *v47; // [rsp+38h] [rbp-28h]
  __int64 *v48; // [rsp+40h] [rbp-20h]
  __int64 *v49; // [rsp+48h] [rbp-18h]
  __int64 *v50; // [rsp+50h] [rbp-10h]
  __int64 *v51; // [rsp+58h] [rbp-8h]

  if ( (a12 & 0xFFFFFFFE) != 0
    || (int)ValidateStringParameter(a2, NtCurrentPeb()) < 0
    || (int)ValidateOptionalString(v14) < 0 )
  {
    return 3221225485LL;
  }
  v44 = 0;
  v16 = 0;
  if ( a4 )
  {
    if ( (int)ValidateStringParameter(a4, v15) < 0 )
      return 3221225485LL;
    v16 = (unsigned __int64)*a4 >> 1;
    if ( !v16 )
      return 3221225485LL;
    if ( *(_WORD *)(*((_QWORD *)a4 + 1) + 2 * v16 - 2) != v43 )
    {
      if ( v16 > 0x103 )
        return 3221225485LL;
      v44 = 1;
    }
  }
  if ( (int)ValidateOptionalString(a5) < 0
    || (int)ValidateOptionalString(a7) < 0
    || (int)ValidateOptionalString(a8) < 0
    || (int)ValidateOptionalString(a9) < 0
    || (int)ValidateOptionalString(a10) < 0
    || (int)ValidateOptionalString(a11) < 0 )
  {
    return 3221225485LL;
  }
  v22 = *(_QWORD *)(v17 + 32);
  v23 = a2;
  v46 = v22;
  if ( v19 )
    v23 = v19;
  v24 = &RtlpNullString;
  v47 = v23;
  v25 = &RtlpNullString;
  if ( a7 )
    v25 = a7;
  v48 = v25;
  v26 = &RtlpNullString;
  if ( a8 )
    v26 = a8;
  v27 = &RtlpNullString;
  v49 = v26;
  v28 = *((unsigned __int16 *)v25 + 1);
  if ( v21 )
    v27 = v21;
  v50 = v27;
  if ( v20 )
    v24 = v20;
  v29 = *a2 + 9LL;
  v30 = *((unsigned __int16 *)v27 + 1) + 7LL;
  v51 = v24;
  v31 = ((*((unsigned __int16 *)v26 + 1) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
      + ((*v23 + 9LL) & 0xFFFFFFFFFFFFFFF8uLL)
      + (v30 & 0xFFFFFFFFFFFFFFF8uLL)
      + ((v28 + 7) & 0xFFFFFFFFFFFFFFF8uLL)
      + (v29 & 0xFFFFFFFFFFFFFFF8uLL)
      + 1616;
  if ( *(_WORD *)v24 )
    v32 = v31 + ((*((unsigned __int16 *)v24 + 1) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
  else
    v32 = v31;
  if ( v18 )
    v32 += (*(unsigned __int16 *)(v18 + 2) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( a11 )
    v32 += (*(unsigned __int16 *)(a11 + 2) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( Src )
    BlockSize = RtlpGetBlockSizeEx(Src, 1);
  else
    BlockSize = *(_QWORD *)(v22 + 1008);
  for ( i = (BlockSize + 7) & 0xFFFFFFFFFFFFFFF8uLL; ; i = v45 )
  {
    if ( i < BlockSize || i + v32 < v32 )
      return 3221225621LL;
    Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, i + v32);
    v36 = (_DWORD *)Heap_0;
    if ( !Heap_0 )
      return 3221225626LL;
    if ( Src )
    {
      memmove((void *)(v32 + Heap_0), Src, BlockSize);
      v37 = (char *)v36 + v32;
      goto LABEL_35;
    }
    RtlEnterCriticalSection(&FastPebLock);
    BlockSize = *(_QWORD *)(v46 + 1008);
    v45 = (BlockSize + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( BlockSize <= i )
      break;
    RtlLeaveCriticalSection(&FastPebLock);
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v36);
  }
  v42 = BlockSize;
  v37 = (char *)v36 + v32;
  memmove((char *)v36 + v32, *(const void **)(v46 + 128), v42);
  RtlLeaveCriticalSection(&FastPebLock);
  i = v45;
LABEL_35:
  memset_thunk_772440563353939046(v36, 0, 0x448u);
  *((_QWORD *)v36 + 16) = v37;
  v38 = v46;
  *v36 = v32;
  v36[1] = v32;
  *((_QWORD *)v36 + 126) = i;
  v45 = (unsigned __int64)(v36 + 274);
  v36[2] = 1;
  v36[6] = *(_DWORD *)(v38 + 24) & 1;
  if ( a4 )
  {
    RtlpCopyProcString(&v45, v36 + 14, a4, 520);
    if ( v44 )
    {
      *(_WORD *)(*((_QWORD *)v36 + 8) + 2 * v16) = 92;
      *((_WORD *)v36 + 28) += 2;
    }
  }
  else
  {
    RtlEnterCriticalSection(&FastPebLock);
    RtlpCopyProcString(&v45, v36 + 14, v38 + 56, 520);
    RtlLeaveCriticalSection(&FastPebLock);
  }
  if ( a3 )
    RtlpCopyProcString(&v45, v36 + 20, a3, *(unsigned __int16 *)(a3 + 2));
  if ( a11 )
    RtlpCopyProcString(&v45, v36 + 260, a11, *(unsigned __int16 *)(a11 + 2));
  RtlpCopyProcString(&v45, v36 + 24, a2, (unsigned int)*a2 + 2);
  v39 = *v47;
  if ( (_WORD)v39 == v47[1] )
    v40 = v47[1];
  else
    v40 = (unsigned int)(v39 + 2);
  RtlpCopyProcString(&v45, v36 + 28, v47, v40);
  RtlpCopyProcString(&v45, v36 + 44, v48, *((unsigned __int16 *)v48 + 1));
  RtlpCopyProcString(&v45, v36 + 48, v49, *((unsigned __int16 *)v49 + 1));
  RtlpCopyProcString(&v45, v36 + 52, v50, *((unsigned __int16 *)v50 + 1));
  if ( *(_WORD *)v51 )
    RtlpCopyProcString(&v45, v36 + 56, v51, *((unsigned __int16 *)v51 + 1));
  if ( (a12 & 1) == 0 )
    v36 = (_DWORD *)RtlDeNormalizeProcessParams(v36);
  *a1 = v36;
  return 0;
}

```

## disassembly

```asm
0x1800980b0  mov     rax, rsp
0x1800980b3  mov     [rax+20h], rbx
0x1800980b7  mov     [rax+18h], r8
0x1800980bb  mov     [rax+10h], rdx
0x1800980bf  mov     [rax+8], rcx
0x1800980c3  push    rbp
0x1800980c4  push    rsi
0x1800980c5  push    rdi
0x1800980c6  push    r12
0x1800980c8  push    r13
0x1800980ca  push    r14
0x1800980cc  push    r15
0x1800980ce  mov     rbp, rsp
0x1800980d1  sub     rsp, 60h
0x1800980d5  test    [rbp+arg_58], 0FFFFFFFEh
0x1800980df  mov     r13, r9
0x1800980e2  mov     rsi, rdx
0x1800980e5  jnz     loc_18009853D
0x1800980eb  mov     rdx, gs:60h
0x1800980f4  mov     rcx, rsi
0x1800980f7  call    ValidateStringParameter
0x1800980fc  xor     r14d, r14d
0x1800980ff  test    eax, eax
0x180098101  js      loc_18009853D
0x180098107  mov     rcx, r8
0x18009810a  call    ValidateOptionalString
0x18009810f  test    eax, eax
0x180098111  js      loc_18009853D
0x180098117  mov     [rbp+var_40], r14b
0x18009811b  mov     r15d, r14d
0x18009811e  lea     r9d, [r14+5Ch]
0x180098122  test    r13, r13
0x180098125  jnz     loc_180098505
0x18009812b  mov     r9, [rbp+arg_20]
0x18009812f  mov     rcx, r9
0x180098132  call    ValidateOptionalString
0x180098137  test    eax, eax
0x180098139  js      loc_18009853D
0x18009813f  mov     rdi, [rbp+arg_30]
0x180098143  mov     rcx, rdi
0x180098146  call    ValidateOptionalString
0x18009814b  test    eax, eax
0x18009814d  js      loc_18009853D
0x180098153  mov     rbx, [rbp+arg_38]
0x180098157  mov     rcx, rbx
0x18009815a  call    ValidateOptionalString
0x18009815f  test    eax, eax
0x180098161  js      loc_18009853D
0x180098167  mov     r11, [rbp+arg_40]
0x18009816e  mov     rcx, r11
0x180098171  call    ValidateOptionalString
0x180098176  test    eax, eax
0x180098178  js      loc_18009853D
0x18009817e  mov     r10, [rbp+arg_48]
0x180098185  mov     rcx, r10
0x180098188  call    ValidateOptionalString
0x18009818d  test    eax, eax
0x18009818f  js      loc_18009853D
0x180098195  mov     r12, [rbp+arg_50]
0x18009819c  mov     rcx, r12
0x18009819f  call    ValidateOptionalString
0x1800981a4  test    eax, eax
0x1800981a6  js      loc_18009853D
0x1800981ac  mov     rdx, [rdx+20h]
0x1800981b0  test    r9, r9
0x1800981b3  mov     r14, rsi
0x1800981b6  mov     [rbp+var_30], rdx
0x1800981ba  cmovnz  r14, r9
0x1800981be  test    rdi, rdi
0x1800981c1  lea     r9, RtlpNullString
0x1800981c8  mov     [rbp+var_28], r14
0x1800981cc  mov     rax, r9
0x1800981cf  cmovnz  rax, rdi
0x1800981d3  test    rbx, rbx
0x1800981d6  mov     [rbp+var_20], rax
0x1800981da  mov     rdi, r9
0x1800981dd  cmovnz  rdi, rbx
0x1800981e1  mov     rbx, r9
0x1800981e4  test    r11, r11
0x1800981e7  mov     [rbp+var_18], rdi
0x1800981eb  movzx   ecx, word ptr [rax+2]
0x1800981ef  cmovnz  rbx, r11
0x1800981f3  test    r10, r10
0x1800981f6  mov     [rbp+var_10], rbx
0x1800981fa  cmovnz  r9, r10
0x1800981fe  add     rcx, 7
0x180098202  movzx   r10d, word ptr [rsi]
0x180098206  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18009820a  movzx   eax, word ptr [rbx+2]
0x18009820e  add     r10, 9
0x180098212  add     rax, 7
0x180098216  mov     [rbp+var_8], r9
0x18009821a  and     rax, 0FFFFFFFFFFFFFFF8h
0x18009821e  and     r10, 0FFFFFFFFFFFFFFF8h
0x180098222  add     rcx, rax
0x180098225  add     r10, 650h
0x18009822c  movzx   eax, word ptr [r14]
0x180098230  add     rax, 9
0x180098234  and     rax, 0FFFFFFFFFFFFFFF8h
0x180098238  add     rcx, rax
0x18009823b  movzx   eax, word ptr [rdi+2]
0x18009823f  add     rax, 7
0x180098243  and     rax, 0FFFFFFFFFFFFFFF8h
0x180098247  add     rcx, rax
0x18009824a  add     r10, rcx
0x18009824d  xor     ecx, ecx
0x18009824f  cmp     [r9], cx
0x180098253  jz      loc_1800985D8
0x180098259  movzx   edi, word ptr [r9+2]
0x18009825e  add     rdi, 7
0x180098262  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180098266  add     rdi, r10
0x180098269  test    r8, r8
0x18009826c  jz      short loc_18009827E
0x18009826e  movzx   eax, word ptr [r8+2]
0x180098273  add     rax, 7
0x180098277  and     rax, 0FFFFFFFFFFFFFFF8h
0x18009827b  add     rdi, rax
0x18009827e  test    r12, r12
0x180098281  jz      short loc_180098294
0x180098283  movzx   eax, word ptr [r12+2]
0x180098289  add     rax, 7
0x18009828d  and     rax, 0FFFFFFFFFFFFFFF8h
0x180098291  add     rdi, rax
0x180098294  mov     rax, [rbp+Src]
0x180098298  test    rax, rax
0x18009829b  jnz     loc_180098499
0x1800982a1  mov     rsi, [rdx+3F0h]
0x1800982a8  lea     r14, [rsi+7]
0x1800982ac  and     r14, 0FFFFFFFFFFFFFFF8h
0x1800982b0  cmp     r14, rsi
0x1800982b3  jb      loc_180098547
0x1800982b9  lea     r8, [r14+rdi]
0x1800982bd  cmp     r8, rdi
0x1800982c0  jb      loc_180098547
0x1800982c6  mov     rcx, gs:60h
0x1800982cf  xor     edx, edx
0x1800982d1  mov     rcx, [rcx+30h]
0x1800982d5  call    RtlAllocateHeap_0
0x1800982da  mov     rbx, rax
0x1800982dd  test    rax, rax
0x1800982e0  jz      loc_1800985A2
0x1800982e6  lea     rcx, [rdi+rax]; void *
0x1800982ea  mov     rax, [rbp+Src]
0x1800982ee  test    rax, rax
0x1800982f1  jz      loc_1800984AE
0x1800982f7  mov     r8, rsi; Size
0x1800982fa  mov     rdx, rax; Src
0x1800982fd  call    memmove
0x180098302  lea     rsi, [rdi+rbx]
0x180098306  xor     edx, edx; Val
0x180098308  mov     r8d, 448h; Size
0x18009830e  mov     rcx, rbx; void *
0x180098311  call    memset$thunk$772440563353939046
0x180098316  mov     [rbx+80h], rsi
0x18009831d  lea     rax, [rbx+448h]
0x180098324  mov     rsi, [rbp+var_30]
0x180098328  mov     [rbx], edi
0x18009832a  mov     [rbx+4], edi
0x18009832d  lea     rdi, [rbx+38h]
0x180098331  mov     [rbx+3F0h], r14
0x180098338  xor     r14d, r14d
0x18009833b  mov     [rbp+var_38], rax
0x18009833f  mov     dword ptr [rbx+8], 1
0x180098346  mov     eax, [rsi+18h]
0x180098349  and     eax, 1
0x18009834c  mov     [rbx+18h], eax
0x18009834f  test    r13, r13
0x180098352  jnz     loc_180098551
0x180098358  lea     rcx, FastPebLock
0x18009835f  call    RtlEnterCriticalSection
0x180098364  lea     r8, [rsi+38h]
0x180098368  mov     r9d, 208h
0x18009836e  mov     rdx, rdi
0x180098371  lea     rcx, [rbp+var_38]
0x180098375  call    RtlpCopyProcString
0x18009837a  lea     rcx, FastPebLock
0x180098381  call    RtlLeaveCriticalSection
0x180098386  mov     esi, 2
0x18009838b  mov     r8, [rbp+arg_10]
0x18009838f  test    r8, r8
0x180098392  jz      short loc_1800983A6
0x180098394  movzx   r9d, word ptr [r8+2]
0x180098399  lea     rdx, [rbx+50h]
0x18009839d  lea     rcx, [rbp+var_38]
0x1800983a1  call    RtlpCopyProcString
0x1800983a6  test    r12, r12
0x1800983a9  jz      short loc_1800983C4
0x1800983ab  movzx   r9d, word ptr [r12+2]
0x1800983b1  lea     rdx, [rbx+410h]
0x1800983b8  mov     r8, r12
0x1800983bb  lea     rcx, [rbp+var_38]
0x1800983bf  call    RtlpCopyProcString
0x1800983c4  mov     r8, [rbp+arg_8]
0x1800983c8  lea     rdx, [rbx+60h]
0x1800983cc  lea     rcx, [rbp+var_38]
0x1800983d0  movzx   r9d, word ptr [r8]
0x1800983d4  add     r9d, esi
0x1800983d7  call    RtlpCopyProcString
0x1800983dc  mov     r8, [rbp+var_28]
0x1800983e0  lea     rdx, [rbx+70h]
0x1800983e4  movzx   eax, word ptr [r8]
0x1800983e8  cmp     ax, [r8+2]
0x1800983ed  jz      loc_180098598
0x1800983f3  lea     r9d, [rsi+rax]
0x1800983f7  lea     rcx, [rbp+var_38]
0x1800983fb  call    RtlpCopyProcString
0x180098400  mov     r8, [rbp+var_20]
0x180098404  lea     rdx, [rbx+0B0h]
0x18009840b  lea     rcx, [rbp+var_38]
0x18009840f  movzx   r9d, word ptr [r8+2]
0x180098414  call    RtlpCopyProcString
0x180098419  mov     r8, [rbp+var_18]
0x18009841d  lea     rdx, [rbx+0C0h]
0x180098424  lea     rcx, [rbp+var_38]
0x180098428  movzx   r9d, word ptr [r8+2]
0x18009842d  call    RtlpCopyProcString
0x180098432  mov     r8, [rbp+var_10]
0x180098436  lea     rdx, [rbx+0D0h]
0x18009843d  lea     rcx, [rbp+var_38]
0x180098441  movzx   r9d, word ptr [r8+2]
0x180098446  call    RtlpCopyProcString
0x18009844b  mov     r8, [rbp+var_8]
0x18009844f  cmp     [r8], r14w
0x180098453  jz      short loc_18009846A
0x180098455  movzx   r9d, word ptr [r8+2]
0x18009845a  lea     rdx, [rbx+0E0h]
0x180098461  lea     rcx, [rbp+var_38]
0x180098465  call    RtlpCopyProcString
0x18009846a  test    byte ptr [rbp+arg_58], 1
0x180098471  jz      loc_180098588
0x180098477  mov     rax, [rbp+arg_0]
0x18009847b  mov     [rax], rbx
0x18009847e  xor     eax, eax
0x180098480  mov     rbx, [rsp+60h+arg_18]
0x180098488  add     rsp, 60h
0x18009848c  pop     r15
0x18009848e  pop     r14
0x180098490  pop     r13
0x180098492  pop     r12
0x180098494  pop     rdi
0x180098495  pop     rsi
0x180098496  pop     rbp
0x180098497  retn
0x180098499  mov     edx, 1
0x18009849e  mov     rcx, rax
0x1800984a1  call    RtlpGetBlockSizeEx
0x1800984a6  mov     rsi, rax
0x1800984a9  jmp     loc_1800982A8
0x1800984ae  lea     rcx, FastPebLock
0x1800984b5  call    RtlEnterCriticalSection
0x1800984ba  mov     rcx, [rbp+var_30]
0x1800984be  mov     rsi, [rcx+3F0h]
0x1800984c5  lea     rax, [rsi+7]
0x1800984c9  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800984cd  mov     [rbp+var_38], rax
0x1800984d1  cmp     rsi, r14
0x1800984d4  ja      loc_1800985AC
0x1800984da  mov     rdx, [rcx+80h]; Src
0x1800984e1  mov     r8, rsi; Size
0x1800984e4  lea     rsi, [rdi+rbx]
0x1800984e8  mov     rcx, rsi; void *
0x1800984eb  call    memmove
0x1800984f0  lea     rcx, FastPebLock
0x1800984f7  call    RtlLeaveCriticalSection
0x1800984fc  mov     r14, [rbp+var_38]
0x180098500  jmp     loc_180098306
0x180098505  mov     rcx, r13
0x180098508  call    ValidateStringParameter
0x18009850d  test    eax, eax
0x18009850f  js      short loc_18009853D
0x180098511  movzx   r15d, word ptr [r13+0]
0x180098516  shr     r15, 1
0x180098519  jz      short loc_18009853D
0x18009851b  mov     rax, [r13+8]
0x18009851f  cmp     [rax+r15*2-2], r9w
0x180098525  jz      loc_18009812B
0x18009852b  cmp     r15, 103h
0x180098532  ja      short loc_18009853D
0x180098534  mov     [rbp+var_40], 1
0x180098538  jmp     loc_18009812B
0x18009853d  mov     eax, 0C000000Dh
0x180098542  jmp     loc_180098480
0x180098547  mov     eax, 0C0000095h
0x18009854c  jmp     loc_180098480
0x180098551  mov     r9d, 208h
0x180098557  lea     rcx, [rbp+var_38]
0x18009855b  mov     r8, r13
0x18009855e  mov     rdx, rdi
0x180098561  call    RtlpCopyProcString
0x180098566  cmp     [rbp+var_40], r14b
0x18009856a  jz      loc_180098386
0x180098570  mov     rax, [rbx+40h]
0x180098574  mov     esi, 2
0x180098579  mov     word ptr [rax+r15*2], 5Ch ; '\'
0x180098580  add     [rdi], si
0x180098583  jmp     loc_18009838B
0x180098588  mov     rcx, rbx
0x18009858b  call    RtlDeNormalizeProcessParams
0x180098590  mov     rbx, rax
  ... truncated ...
```

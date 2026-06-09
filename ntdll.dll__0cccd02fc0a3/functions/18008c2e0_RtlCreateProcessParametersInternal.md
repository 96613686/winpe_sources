# RtlCreateProcessParametersInternal

- ea: `0x18008c2e0`
- end: `0x18008c810`
- name: `RtlCreateProcessParametersInternal`
- size: `1328`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *Src, __int64, __int64, __int64, __int64, __int64, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `reparse_path, loader_planting`

## callers

- `0x18008c090`
- `0x18008c1d0`
- `0x18015bf80`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x1800535c0`
- `0x180053ab0`
- `0x18008c2e0`
- `0x18008c818`
- `0x18008c82c`
- `0x18008c8ac`
- `0x18008c8f0`
- `0x1801211e0`
- `0x180163a80`
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
      + 1624;
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
  memset_thunk_772440563353939046(v36, 0, 0x450u);
  *((_QWORD *)v36 + 16) = v37;
  v38 = v46;
  *v36 = v32;
  v36[1] = v32;
  *((_QWORD *)v36 + 126) = i;
  v45 = (unsigned __int64)(v36 + 276);
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
0x18008c2e0  mov     rax, rsp
0x18008c2e3  mov     [rax+20h], rbx
0x18008c2e7  mov     [rax+18h], r8
0x18008c2eb  mov     [rax+10h], rdx
0x18008c2ef  mov     [rax+8], rcx
0x18008c2f3  push    rbp
0x18008c2f4  push    rsi
0x18008c2f5  push    rdi
0x18008c2f6  push    r12
0x18008c2f8  push    r13
0x18008c2fa  push    r14
0x18008c2fc  push    r15
0x18008c2fe  mov     rbp, rsp
0x18008c301  sub     rsp, 60h
0x18008c305  test    [rbp+arg_58], 0FFFFFFFEh
0x18008c30f  mov     r13, r9
0x18008c312  mov     rsi, rdx
0x18008c315  jnz     loc_18008C76D
0x18008c31b  mov     rdx, gs:60h
0x18008c324  mov     rcx, rsi
0x18008c327  call    ValidateStringParameter
0x18008c32c  xor     r14d, r14d
0x18008c32f  test    eax, eax
0x18008c331  js      loc_18008C76D
0x18008c337  mov     rcx, r8
0x18008c33a  call    ValidateOptionalString
0x18008c33f  test    eax, eax
0x18008c341  js      loc_18008C76D
0x18008c347  mov     [rbp+var_40], r14b
0x18008c34b  mov     r15d, r14d
0x18008c34e  lea     r9d, [r14+5Ch]
0x18008c352  test    r13, r13
0x18008c355  jnz     loc_18008C735
0x18008c35b  mov     r9, [rbp+arg_20]
0x18008c35f  mov     rcx, r9
0x18008c362  call    ValidateOptionalString
0x18008c367  test    eax, eax
0x18008c369  js      loc_18008C76D
0x18008c36f  mov     rdi, [rbp+arg_30]
0x18008c373  mov     rcx, rdi
0x18008c376  call    ValidateOptionalString
0x18008c37b  test    eax, eax
0x18008c37d  js      loc_18008C76D
0x18008c383  mov     rbx, [rbp+arg_38]
0x18008c387  mov     rcx, rbx
0x18008c38a  call    ValidateOptionalString
0x18008c38f  test    eax, eax
0x18008c391  js      loc_18008C76D
0x18008c397  mov     r11, [rbp+arg_40]
0x18008c39e  mov     rcx, r11
0x18008c3a1  call    ValidateOptionalString
0x18008c3a6  test    eax, eax
0x18008c3a8  js      loc_18008C76D
0x18008c3ae  mov     r10, [rbp+arg_48]
0x18008c3b5  mov     rcx, r10
0x18008c3b8  call    ValidateOptionalString
0x18008c3bd  test    eax, eax
0x18008c3bf  js      loc_18008C76D
0x18008c3c5  mov     r12, [rbp+arg_50]
0x18008c3cc  mov     rcx, r12
0x18008c3cf  call    ValidateOptionalString
0x18008c3d4  test    eax, eax
0x18008c3d6  js      loc_18008C76D
0x18008c3dc  mov     rdx, [rdx+20h]
0x18008c3e0  test    r9, r9
0x18008c3e3  mov     r14, rsi
0x18008c3e6  mov     [rbp+var_30], rdx
0x18008c3ea  cmovnz  r14, r9
0x18008c3ee  test    rdi, rdi
0x18008c3f1  lea     r9, RtlpNullString
0x18008c3f8  mov     [rbp+var_28], r14
0x18008c3fc  mov     rax, r9
0x18008c3ff  cmovnz  rax, rdi
0x18008c403  test    rbx, rbx
0x18008c406  mov     [rbp+var_20], rax
0x18008c40a  mov     rdi, r9
0x18008c40d  cmovnz  rdi, rbx
0x18008c411  mov     rbx, r9
0x18008c414  test    r11, r11
0x18008c417  mov     [rbp+var_18], rdi
0x18008c41b  movzx   ecx, word ptr [rax+2]
0x18008c41f  cmovnz  rbx, r11
0x18008c423  test    r10, r10
0x18008c426  mov     [rbp+var_10], rbx
0x18008c42a  cmovnz  r9, r10
0x18008c42e  add     rcx, 7
0x18008c432  movzx   r10d, word ptr [rsi]
0x18008c436  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18008c43a  movzx   eax, word ptr [rbx+2]
0x18008c43e  add     r10, 9
0x18008c442  add     rax, 7
0x18008c446  mov     [rbp+var_8], r9
0x18008c44a  and     rax, 0FFFFFFFFFFFFFFF8h
0x18008c44e  and     r10, 0FFFFFFFFFFFFFFF8h
0x18008c452  add     rcx, rax
0x18008c455  add     r10, 658h
0x18008c45c  movzx   eax, word ptr [r14]
0x18008c460  add     rax, 9
0x18008c464  and     rax, 0FFFFFFFFFFFFFFF8h
0x18008c468  add     rcx, rax
0x18008c46b  movzx   eax, word ptr [rdi+2]
0x18008c46f  add     rax, 7
0x18008c473  and     rax, 0FFFFFFFFFFFFFFF8h
0x18008c477  add     rcx, rax
0x18008c47a  add     r10, rcx
0x18008c47d  xor     ecx, ecx
0x18008c47f  cmp     [r9], cx
0x18008c483  jz      loc_18008C808
0x18008c489  movzx   edi, word ptr [r9+2]
0x18008c48e  add     rdi, 7
0x18008c492  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18008c496  add     rdi, r10
0x18008c499  test    r8, r8
0x18008c49c  jz      short loc_18008C4AE
0x18008c49e  movzx   eax, word ptr [r8+2]
0x18008c4a3  add     rax, 7
0x18008c4a7  and     rax, 0FFFFFFFFFFFFFFF8h
0x18008c4ab  add     rdi, rax
0x18008c4ae  test    r12, r12
0x18008c4b1  jz      short loc_18008C4C4
0x18008c4b3  movzx   eax, word ptr [r12+2]
0x18008c4b9  add     rax, 7
0x18008c4bd  and     rax, 0FFFFFFFFFFFFFFF8h
0x18008c4c1  add     rdi, rax
0x18008c4c4  mov     rax, [rbp+Src]
0x18008c4c8  test    rax, rax
0x18008c4cb  jnz     loc_18008C6C9
0x18008c4d1  mov     rsi, [rdx+3F0h]
0x18008c4d8  lea     r14, [rsi+7]
0x18008c4dc  and     r14, 0FFFFFFFFFFFFFFF8h
0x18008c4e0  cmp     r14, rsi
0x18008c4e3  jb      loc_18008C777
0x18008c4e9  lea     r8, [r14+rdi]
0x18008c4ed  cmp     r8, rdi
0x18008c4f0  jb      loc_18008C777
0x18008c4f6  mov     rcx, gs:60h
0x18008c4ff  xor     edx, edx
0x18008c501  mov     rcx, [rcx+30h]
0x18008c505  call    RtlAllocateHeap_0
0x18008c50a  mov     rbx, rax
0x18008c50d  test    rax, rax
0x18008c510  jz      loc_18008C7D2
0x18008c516  lea     rcx, [rdi+rax]; void *
0x18008c51a  mov     rax, [rbp+Src]
0x18008c51e  test    rax, rax
0x18008c521  jz      loc_18008C6DE
0x18008c527  mov     r8, rsi; Size
0x18008c52a  mov     rdx, rax; Src
0x18008c52d  call    memmove
0x18008c532  lea     rsi, [rdi+rbx]
0x18008c536  xor     edx, edx; Val
0x18008c538  mov     r8d, 450h; Size
0x18008c53e  mov     rcx, rbx; void *
0x18008c541  call    memset$thunk$772440563353939046
0x18008c546  mov     [rbx+80h], rsi
0x18008c54d  lea     rax, [rbx+450h]
0x18008c554  mov     rsi, [rbp+var_30]
0x18008c558  mov     [rbx], edi
0x18008c55a  mov     [rbx+4], edi
0x18008c55d  lea     rdi, [rbx+38h]
0x18008c561  mov     [rbx+3F0h], r14
0x18008c568  xor     r14d, r14d
0x18008c56b  mov     [rbp+var_38], rax
0x18008c56f  mov     dword ptr [rbx+8], 1
0x18008c576  mov     eax, [rsi+18h]
0x18008c579  and     eax, 1
0x18008c57c  mov     [rbx+18h], eax
0x18008c57f  test    r13, r13
0x18008c582  jnz     loc_18008C781
0x18008c588  lea     rcx, FastPebLock
0x18008c58f  call    RtlEnterCriticalSection
0x18008c594  lea     r8, [rsi+38h]
0x18008c598  mov     r9d, 208h
0x18008c59e  mov     rdx, rdi
0x18008c5a1  lea     rcx, [rbp+var_38]
0x18008c5a5  call    RtlpCopyProcString
0x18008c5aa  lea     rcx, FastPebLock
0x18008c5b1  call    RtlLeaveCriticalSection
0x18008c5b6  mov     esi, 2
0x18008c5bb  mov     r8, [rbp+arg_10]
0x18008c5bf  test    r8, r8
0x18008c5c2  jz      short loc_18008C5D6
0x18008c5c4  movzx   r9d, word ptr [r8+2]
0x18008c5c9  lea     rdx, [rbx+50h]
0x18008c5cd  lea     rcx, [rbp+var_38]
0x18008c5d1  call    RtlpCopyProcString
0x18008c5d6  test    r12, r12
0x18008c5d9  jz      short loc_18008C5F4
0x18008c5db  movzx   r9d, word ptr [r12+2]
0x18008c5e1  lea     rdx, [rbx+410h]
0x18008c5e8  mov     r8, r12
0x18008c5eb  lea     rcx, [rbp+var_38]
0x18008c5ef  call    RtlpCopyProcString
0x18008c5f4  mov     r8, [rbp+arg_8]
0x18008c5f8  lea     rdx, [rbx+60h]
0x18008c5fc  lea     rcx, [rbp+var_38]
0x18008c600  movzx   r9d, word ptr [r8]
0x18008c604  add     r9d, esi
0x18008c607  call    RtlpCopyProcString
0x18008c60c  mov     r8, [rbp+var_28]
0x18008c610  lea     rdx, [rbx+70h]
0x18008c614  movzx   eax, word ptr [r8]
0x18008c618  cmp     ax, [r8+2]
0x18008c61d  jz      loc_18008C7C8
0x18008c623  lea     r9d, [rsi+rax]
0x18008c627  lea     rcx, [rbp+var_38]
0x18008c62b  call    RtlpCopyProcString
0x18008c630  mov     r8, [rbp+var_20]
0x18008c634  lea     rdx, [rbx+0B0h]
0x18008c63b  lea     rcx, [rbp+var_38]
0x18008c63f  movzx   r9d, word ptr [r8+2]
0x18008c644  call    RtlpCopyProcString
0x18008c649  mov     r8, [rbp+var_18]
0x18008c64d  lea     rdx, [rbx+0C0h]
0x18008c654  lea     rcx, [rbp+var_38]
0x18008c658  movzx   r9d, word ptr [r8+2]
0x18008c65d  call    RtlpCopyProcString
0x18008c662  mov     r8, [rbp+var_10]
0x18008c666  lea     rdx, [rbx+0D0h]
0x18008c66d  lea     rcx, [rbp+var_38]
0x18008c671  movzx   r9d, word ptr [r8+2]
0x18008c676  call    RtlpCopyProcString
0x18008c67b  mov     r8, [rbp+var_8]
0x18008c67f  cmp     [r8], r14w
0x18008c683  jz      short loc_18008C69A
0x18008c685  movzx   r9d, word ptr [r8+2]
0x18008c68a  lea     rdx, [rbx+0E0h]
0x18008c691  lea     rcx, [rbp+var_38]
0x18008c695  call    RtlpCopyProcString
0x18008c69a  test    byte ptr [rbp+arg_58], 1
0x18008c6a1  jz      loc_18008C7B8
0x18008c6a7  mov     rax, [rbp+arg_0]
0x18008c6ab  mov     [rax], rbx
0x18008c6ae  xor     eax, eax
0x18008c6b0  mov     rbx, [rsp+60h+arg_18]
0x18008c6b8  add     rsp, 60h
0x18008c6bc  pop     r15
0x18008c6be  pop     r14
0x18008c6c0  pop     r13
0x18008c6c2  pop     r12
0x18008c6c4  pop     rdi
0x18008c6c5  pop     rsi
0x18008c6c6  pop     rbp
0x18008c6c7  retn
0x18008c6c9  mov     edx, 1
0x18008c6ce  mov     rcx, rax
0x18008c6d1  call    RtlpGetBlockSizeEx
0x18008c6d6  mov     rsi, rax
0x18008c6d9  jmp     loc_18008C4D8
0x18008c6de  lea     rcx, FastPebLock
0x18008c6e5  call    RtlEnterCriticalSection
0x18008c6ea  mov     rcx, [rbp+var_30]
0x18008c6ee  mov     rsi, [rcx+3F0h]
0x18008c6f5  lea     rax, [rsi+7]
0x18008c6f9  and     rax, 0FFFFFFFFFFFFFFF8h
0x18008c6fd  mov     [rbp+var_38], rax
0x18008c701  cmp     rsi, r14
0x18008c704  ja      loc_18008C7DC
0x18008c70a  mov     rdx, [rcx+80h]; Src
0x18008c711  mov     r8, rsi; Size
0x18008c714  lea     rsi, [rdi+rbx]
0x18008c718  mov     rcx, rsi; void *
0x18008c71b  call    memmove
0x18008c720  lea     rcx, FastPebLock
0x18008c727  call    RtlLeaveCriticalSection
0x18008c72c  mov     r14, [rbp+var_38]
0x18008c730  jmp     loc_18008C536
0x18008c735  mov     rcx, r13
0x18008c738  call    ValidateStringParameter
0x18008c73d  test    eax, eax
0x18008c73f  js      short loc_18008C76D
0x18008c741  movzx   r15d, word ptr [r13+0]
0x18008c746  shr     r15, 1
0x18008c749  jz      short loc_18008C76D
0x18008c74b  mov     rax, [r13+8]
0x18008c74f  cmp     [rax+r15*2-2], r9w
0x18008c755  jz      loc_18008C35B
0x18008c75b  cmp     r15, 103h
0x18008c762  ja      short loc_18008C76D
0x18008c764  mov     [rbp+var_40], 1
0x18008c768  jmp     loc_18008C35B
0x18008c76d  mov     eax, 0C000000Dh
0x18008c772  jmp     loc_18008C6B0
0x18008c777  mov     eax, 0C0000095h
0x18008c77c  jmp     loc_18008C6B0
0x18008c781  mov     r9d, 208h
0x18008c787  lea     rcx, [rbp+var_38]
0x18008c78b  mov     r8, r13
0x18008c78e  mov     rdx, rdi
0x18008c791  call    RtlpCopyProcString
0x18008c796  cmp     [rbp+var_40], r14b
0x18008c79a  jz      loc_18008C5B6
0x18008c7a0  mov     rax, [rbx+40h]
0x18008c7a4  mov     esi, 2
0x18008c7a9  mov     word ptr [rax+r15*2], 5Ch ; '\'
0x18008c7b0  add     [rdi], si
0x18008c7b3  jmp     loc_18008C5BB
0x18008c7b8  mov     rcx, rbx
0x18008c7bb  call    RtlDeNormalizeProcessParams
0x18008c7c0  mov     rbx, rax
  ... truncated ...
```

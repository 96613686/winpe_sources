# RtlpDosPathNameToRelativeNtPathName

- ea: `0x18001c520`
- end: `0x18001cd26`
- name: `RtlpDosPathNameToRelativeNtPathName`
- size: `2054`
- prototype: ``
- caller_count: `19`
- callee_count: `11`
- tags: `reparse_path, registry_config`

## callers

- `0x18001b870`
- `0x18001b900`
- `0x18001cd30`
- `0x180027ef0`
- `0x180035a70`
- `0x18005b4b0`
- `0x18005c960`
- `0x18005d730`
- `0x18005f450`
- `0x1800a2430`
- `0x1800c5d40`
- `0x1800cbe40`
- `0x1800cee30`
- `0x1800cfa84`
- `0x1800d1a90`
- `0x1800fa8f8`
- `0x1800ffee8`
- `0x1801014d0`
- `0x180111c74`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18001c520`
- `0x18001faf0`
- `0x1800535c0`
- `0x18005d660`
- `0x18005ec80`
- `0x18005f150`
- `0x18015e4b0`
- `0x180162000`
- `0x180163a80`

## pseudocode

```c
__int64 __fastcall RtlpDosPathNameToRelativeNtPathName(
        int a1,
        __m128i *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 a7)
{
  char v8; // dl
  unsigned int v10; // ecx
  unsigned __int16 *v11; // rbx
  _WORD *v12; // rax
  _WORD *v13; // rax
  unsigned int v14; // ebp
  int v15; // ecx
  _WORD *v16; // r12
  unsigned __int16 v17; // ax
  unsigned int v18; // esi
  __int16 v19; // ax
  int v20; // r8d
  __int64 *v21; // r13
  unsigned int v22; // edi
  __int64 v23; // rax
  unsigned int v24; // ebp
  unsigned int v25; // edi
  const void *v26; // rdx
  size_t v27; // r8
  unsigned __int16 v28; // bp
  __int64 v29; // r12
  _QWORD *v30; // rcx
  bool v31; // zf
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // rbp
  _WORD *v35; // rax
  __int16 v36; // si
  unsigned int FullPathName_Ustr; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int16 v42; // dx
  unsigned int v43; // esi
  __int64 Heap_0; // rax
  unsigned __int16 v45; // dx
  unsigned __int64 v46; // rdx
  unsigned __int16 v47; // si
  void *v48; // r15
  __int16 v49; // ax
  __int16 v50; // ax
  __int16 v51; // ax
  unsigned __int64 v52; // rdx
  _WORD *v53; // rcx
  _WORD *v54; // rax
  _BYTE v55[4]; // [rsp+30h] [rbp-2A8h] BYREF
  int v56; // [rsp+34h] [rbp-2A4h]
  int v57; // [rsp+38h] [rbp-2A0h]
  __int64 v58; // [rsp+40h] [rbp-298h]
  _BYTE *v59; // [rsp+48h] [rbp-290h]
  __int64 v60; // [rsp+50h] [rbp-288h] BYREF
  void *v61; // [rsp+58h] [rbp-280h]
  __m128i v62; // [rsp+60h] [rbp-278h] BYREF
  _QWORD *v63; // [rsp+70h] [rbp-268h]
  _QWORD *v64; // [rsp+78h] [rbp-260h]
  _BYTE v65[528]; // [rsp+80h] [rbp-258h] BYREF

  v8 = a1;
  v56 = a1;
  v63 = a5;
  v10 = a2->m128i_u16[0];
  v11 = a3;
  v64 = a6;
  v60 = 0;
  v55[0] = 0;
  v62 = 0;
  if ( v10 > 8 )
  {
    v12 = (_WORD *)a2->m128i_i64[1];
    if ( *v12 == 92 )
    {
      v42 = v12[1];
      if ( v42 != 92 && v42 != 63 || v12[2] != 63 || v12[3] != 92 )
      {
        v8 = v56;
        goto LABEL_3;
      }
      v43 = v10 + 2;
      if ( v10 + 2 <= 0xFFFE )
      {
        if ( !a3 )
        {
          if ( !a4 )
            return (unsigned int)-1073741811;
          goto LABEL_61;
        }
        if ( v43 <= a3[1] )
        {
          v45 = *a3;
LABEL_63:
          if ( (unsigned int)v45 + 8 <= v11[1] )
          {
            v46 = *((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)v45 >> 1);
            *(_QWORD *)v46 = *(_QWORD *)L"\\??\\";
            *v11 += 8;
            if ( (unsigned int)*v11 + 1 < v11[1] )
              *(_WORD *)(v46 + 8) = 0;
          }
          v47 = a2->m128i_i16[0] - 8;
          if ( a2->m128i_i16[0] != 8 && *v11 + (unsigned int)v47 <= v11[1] )
          {
            v48 = (void *)(*((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)*v11 >> 1));
            memmove(v48, (const void *)(a2->m128i_i64[1] + 8), v47);
            *v11 += v47;
            if ( (unsigned int)*v11 + 1 < v11[1] )
              *((_WORD *)v48 + ((unsigned __int64)v47 >> 1)) = 0;
          }
          if ( a5 )
            *a5 = v11;
          *(_WORD *)(*((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)*v11 >> 1)) = 0;
          if ( a6 )
          {
            v52 = *((_QWORD *)v11 + 1);
            v53 = (_WORD *)(v52 + 2 * ((unsigned __int64)*v11 >> 1));
            while ( 1 )
            {
              v54 = v53--;
              if ( (unsigned __int64)v53 < v52 )
                break;
              if ( *v53 == 92 )
              {
                if ( v54 && *v54 )
                {
                  *a6 = v54;
                  goto LABEL_73;
                }
                break;
              }
            }
            *a6 = 0;
          }
LABEL_73:
          if ( a7 )
          {
            *(_DWORD *)a7 = 0;
            *(_QWORD *)(a7 + 8) = 0;
            *(_QWORD *)(a7 + 16) = 0;
            *(_QWORD *)(a7 + 24) = 0;
          }
          return 0;
        }
        if ( a4 )
        {
LABEL_61:
          Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v43);
          *((_QWORD *)a4 + 1) = Heap_0;
          if ( Heap_0 )
          {
            *a4 = 0;
            v11 = a4;
            a4[1] = v43;
            v45 = 0;
            goto LABEL_63;
          }
          return (unsigned int)-1073741801;
        }
      }
      return (unsigned int)-1073741562;
    }
  }
LABEL_3:
  if ( a6 )
    *a6 = 0;
  v13 = v65;
  v59 = v65;
  v14 = 520;
  v58 = 4;
  v15 = 2;
  if ( (v8 & 1) != 0 )
  {
    v16 = (_WORD *)a2->m128i_i64[1];
    v17 = _mm_cvtsi128_si32(*a2);
    v62 = *a2;
    LOWORD(v18) = v17;
    if ( v17 >= 2u && (*v16 == 92 || *v16 == 47) )
    {
      if ( v17 >= 4u && ((v49 = v16[1], v49 == 92) || v49 == 47) )
      {
        if ( (unsigned __int16)v18 >= 6u && ((v50 = v16[2], v50 == 46) || v50 == 63) )
        {
          if ( (unsigned __int16)v18 >= 8u && ((v51 = v16[3], v51 == 92) || v51 == 47) )
          {
            v20 = 6;
          }
          else
          {
            v20 = 1;
            if ( (_WORD)v18 == 6 )
              v20 = 7;
          }
        }
        else
        {
          v20 = 1;
        }
      }
      else
      {
        v20 = 4;
      }
    }
    else if ( v17 >= 4u && *v16 && v16[1] == 58 )
    {
      if ( v17 >= 6u && ((v19 = v16[2], v19 == 92) || v19 == 47) )
        v20 = 2;
      else
        v20 = 3;
    }
    else
    {
      v20 = 5;
    }
    LODWORD(v60) = v20;
LABEL_16:
    if ( v20 == 5 )
      goto LABEL_17;
    if ( v20 == 1 )
    {
      v21 = &RtlpDosDevicesUncPrefix;
      v57 = 4;
      v15 = 14;
LABEL_19:
      v22 = v15 + (unsigned __int16)v18;
      if ( v22 > 0xFFFE )
      {
LABEL_117:
        v25 = -1073741562;
      }
      else
      {
        if ( v11 )
        {
          if ( v22 <= v11[1] )
          {
LABEL_24:
            v24 = *(unsigned __int16 *)v21;
            v25 = 0;
            if ( (_WORD)v24 )
            {
              if ( *v11 + v24 <= v11[1] )
              {
                v26 = (const void *)v21[1];
                v27 = *(unsigned __int16 *)v21;
                v61 = (void *)(*((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)*v11 >> 1));
                memmove(v61, v26, v27);
                *v11 += v24;
                if ( (unsigned int)*v11 + 1 < v11[1] )
                  *((_WORD *)v61 + ((unsigned __int64)v24 >> 1)) = 0;
              }
            }
            v28 = v18 - v57;
            if ( (_WORD)v18 != (_WORD)v57 && *v11 + (unsigned int)v28 <= v11[1] )
            {
              v61 = (void *)(*((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)*v11 >> 1));
              memmove(v61, &v16[(unsigned __int64)v58 / 2], v28);
              *v11 += v28;
              if ( (unsigned int)*v11 + 1 < v11[1] )
                *((_WORD *)v61 + ((unsigned __int64)v28 >> 1)) = 0;
            }
            if ( v63 )
              *v63 = v11;
            v29 = v58;
            *(_WORD *)(*((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)*v11 >> 1)) = 0;
            v30 = v64;
            if ( v64 && *v64 )
              *v64 += *((_QWORD *)v11 + 1) + *(unsigned __int16 *)v21 - v29 - (_QWORD)v59;
            if ( a7 )
            {
              v31 = (_DWORD)v60 == 5;
              *(_DWORD *)a7 = 0;
              *(_QWORD *)(a7 + 8) = 0;
              *(_QWORD *)(a7 + 16) = 0;
              *(_QWORD *)(a7 + 24) = 0;
              if ( v31 )
              {
                LOBYTE(v30) = 1;
                v32 = RtlpReferenceCurrentDirectory(v30);
                v34 = v32;
                if ( v32 )
                {
                  LOBYTE(v33) = 1;
                  if ( !(unsigned __int8)RtlPrefixUnicodeString(v32 + 24, &v62, v33) )
                    goto LABEL_109;
                  v35 = (_WORD *)(*(unsigned __int16 *)(v34 + 24) + *(unsigned __int16 *)v21 - v29 + *((_QWORD *)v11 + 1));
                  *(_QWORD *)(a7 + 8) = v35;
                  v36 = v18 - *(_WORD *)(v34 + 24);
                  *(_WORD *)a7 = v36;
                  if ( *v35 == 92 )
                  {
                    v36 -= 2;
                    *(_WORD *)a7 = v36;
                    *(_QWORD *)(a7 + 8) = v35 + 1;
                  }
                  v31 = (v56 & 2) == 0;
                  *(_WORD *)(a7 + 2) = v36;
                  if ( v31 )
                  {
LABEL_109:
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v34, 0xFFFFFFFF) == 1 )
                    {
                      NtClose(*(HANDLE *)(v34 + 8));
                      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v34);
                    }
                  }
                  else
                  {
                    *(_QWORD *)(a7 + 24) = v34;
                    *(_QWORD *)(a7 + 16) = *(_QWORD *)(v34 + 8);
                  }
                }
                else
                {
                  RtlLeaveCriticalSection(&FastPebLock);
                }
              }
            }
            goto LABEL_50;
          }
          if ( !a4 )
          {
            v25 = -1073741562;
            goto LABEL_50;
          }
        }
        else if ( !a4 )
        {
          v25 = -1073741811;
          goto LABEL_50;
        }
        v23 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v22);
        *((_QWORD *)a4 + 1) = v23;
        if ( v23 )
        {
          a4[1] = v22;
          *a4 = 0;
          v11 = a4;
          goto LABEL_24;
        }
        v25 = -1073741801;
      }
LABEL_50:
      if ( v59 != v65 )
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v59);
      return v25;
    }
    if ( v20 != 6 )
    {
LABEL_17:
      v58 = 0;
      LOWORD(v57) = 0;
      v15 = 10;
    }
    else
    {
      v58 = 8;
      LOWORD(v57) = 8;
    }
    v21 = (__int64 *)L"\b\n";
    goto LABEL_19;
  }
  while ( 1 )
  {
    FullPathName_Ustr = RtlGetFullPathName_Ustr((unsigned __int16 *)a2, v14, v13, a6, v55, (int *)&v60);
    v18 = FullPathName_Ustr;
    if ( !FullPathName_Ustr || v55[0] )
    {
      v25 = -1073741773;
      goto LABEL_50;
    }
    if ( FullPathName_Ustr <= v14 )
    {
      v16 = v59;
      v62.m128i_i64[1] = (__int64)v59;
      v62.m128i_i16[0] = FullPathName_Ustr;
      v62.m128i_i16[1] = v14;
      v20 = RtlDetermineDosPathNameType_Ustr(&v62, v38, v39, v40);
      v15 = 2;
      goto LABEL_16;
    }
    if ( (v56 & 4) == 0 && ((v56 & 8) != 0 || (NtCurrentPeb()->BitField & 0x80u) == 0) )
      goto LABEL_117;
    v13 = (_WORD *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, FullPathName_Ustr);
    v59 = v13;
    if ( !v13 )
      return 3221225495LL;
    v14 = v18;
  }
}

```

## disassembly

```asm
0x18001c520  mov     [rsp+arg_0], rbx
0x18001c525  push    rbp
0x18001c526  push    rsi
0x18001c527  push    rdi
0x18001c528  push    r12
0x18001c52a  push    r13
0x18001c52c  push    r14
0x18001c52e  push    r15
0x18001c530  sub     rsp, 2A0h
0x18001c537  mov     rax, cs:__security_cookie
0x18001c53e  xor     rax, rsp
0x18001c541  mov     [rsp+2D8h+var_48], rax
0x18001c549  mov     r13, [rsp+2D8h+arg_20]
0x18001c551  xor     ebp, ebp
0x18001c553  mov     r12, [rsp+2D8h+arg_28]
0x18001c55b  mov     rdi, rdx
0x18001c55e  mov     r14, [rsp+2D8h+arg_30]
0x18001c566  mov     edx, ecx
0x18001c568  mov     [rsp+2D8h+var_2A4], ecx
0x18001c56c  xorps   xmm0, xmm0
0x18001c56f  mov     r15, r9
0x18001c572  mov     [rsp+2D8h+var_268], r13
0x18001c577  movzx   ecx, word ptr [rdi]
0x18001c57a  mov     rbx, r8
0x18001c57d  mov     [rsp+2D8h+var_260], r12
0x18001c582  mov     [rsp+2D8h+var_288], rbp
0x18001c587  mov     [rsp+2D8h+var_2A8], bpl
0x18001c58c  movups  [rsp+2D8h+var_278], xmm0
0x18001c591  cmp     ecx, 8
0x18001c594  jbe     short loc_18001C5A4
0x18001c596  mov     rax, [rdi+8]
0x18001c59a  cmp     word ptr [rax], 5Ch ; '\'
0x18001c59e  jz      loc_18001C94A
0x18001c5a4  test    r12, r12
0x18001c5a7  jz      short loc_18001C5AD
0x18001c5a9  mov     [r12], rbp
0x18001c5ad  lea     rax, [rsp+2D8h+var_258]
0x18001c5b5  mov     r9d, 4
0x18001c5bb  mov     [rsp+2D8h+var_290], rax
0x18001c5c0  mov     ebp, 208h
0x18001c5c5  mov     [rsp+2D8h+var_298], r9
0x18001c5ca  mov     ecx, 2
0x18001c5cf  test    dl, 1
0x18001c5d2  jz      loc_18001C860
0x18001c5d8  movups  xmm1, xmmword ptr [rdi]
0x18001c5db  mov     r12, [rdi+8]
0x18001c5df  movd    eax, xmm1
0x18001c5e3  movups  [rsp+2D8h+var_278], xmm1
0x18001c5e8  movzx   esi, ax
0x18001c5eb  cmp     ax, cx
0x18001c5ee  jb      short loc_18001C609
0x18001c5f0  movzx   eax, word ptr [r12]
0x18001c5f5  cmp     ax, 5Ch ; '\'
0x18001c5f9  jz      loc_18001CB18
0x18001c5ff  cmp     ax, 2Fh ; '/'
0x18001c603  jz      loc_18001CB18
0x18001c609  cmp     si, r9w
0x18001c60d  jb      loc_18001CB03
0x18001c613  cmp     word ptr [r12], 0
0x18001c619  jz      loc_18001CB03
0x18001c61f  cmp     word ptr [r12+2], 3Ah ; ':'
0x18001c626  jnz     loc_18001CB03
0x18001c62c  cmp     si, 6
0x18001c630  jb      loc_18001CC45
0x18001c636  movzx   eax, word ptr [r12+4]
0x18001c63c  cmp     ax, 5Ch ; '\'
0x18001c640  jnz     loc_18001CC3B
0x18001c646  mov     r8d, ecx
0x18001c649  mov     dword ptr [rsp+2D8h+var_288], r8d
0x18001c64e  cmp     r8d, 5
0x18001c652  jnz     loc_18001C92A
0x18001c658  xor     eax, eax
0x18001c65a  mov     [rsp+2D8h+var_298], 0
0x18001c663  mov     word ptr [rsp+2D8h+var_2A0], ax
0x18001c668  mov     ecx, 0Ah
0x18001c66d  lea     r13, RtlpDosDevicesPrefix; "\b\n"
0x18001c674  movzx   edi, si
0x18001c677  add     edi, ecx
0x18001c679  cmp     edi, 0FFFEh
0x18001c67f  ja      loc_18001CCCC
0x18001c685  test    rbx, rbx
0x18001c688  jnz     loc_18001CB98
0x18001c68e  test    r15, r15
0x18001c691  jz      loc_18001CBDF
0x18001c697  mov     rcx, gs:60h
0x18001c6a0  xor     edx, edx
0x18001c6a2  mov     r8d, edi
0x18001c6a5  mov     rcx, [rcx+30h]
0x18001c6a9  call    RtlAllocateHeap_0
0x18001c6ae  mov     [r15+8], rax
0x18001c6b2  test    rax, rax
0x18001c6b5  jz      loc_18001CB8E
0x18001c6bb  xor     eax, eax
0x18001c6bd  mov     [r15+2], di
0x18001c6c2  mov     [r15], ax
0x18001c6c6  mov     rbx, r15
0x18001c6c9  movzx   ebp, word ptr [r13+0]
0x18001c6ce  xor     edi, edi
0x18001c6d0  test    bp, bp
0x18001c6d3  jz      short loc_18001C726
0x18001c6d5  movzx   edx, word ptr [rbx]
0x18001c6d8  movzx   eax, word ptr [rbx+2]
0x18001c6dc  lea     ecx, [rdx+rbp]
0x18001c6df  cmp     ecx, eax
0x18001c6e1  ja      short loc_18001C726
0x18001c6e3  mov     rax, [rbx+8]
0x18001c6e7  mov     ecx, edx
0x18001c6e9  mov     rdx, [r13+8]; Src
0x18001c6ed  mov     r8d, ebp; Size
0x18001c6f0  shr     rcx, 1
0x18001c6f3  mov     r15d, ebp
0x18001c6f6  lea     rax, [rax+rcx*2]
0x18001c6fa  mov     rcx, rax; void *
0x18001c6fd  mov     [rsp+2D8h+var_280], rax
0x18001c702  call    memmove
0x18001c707  add     [rbx], bp
0x18001c70a  movzx   ecx, word ptr [rbx]
0x18001c70d  movzx   eax, word ptr [rbx+2]
0x18001c711  inc     ecx
0x18001c713  cmp     ecx, eax
0x18001c715  jnb     short loc_18001C726
0x18001c717  mov     rcx, [rsp+2D8h+var_280]
0x18001c71c  shr     r15, 1
0x18001c71f  xor     eax, eax
0x18001c721  mov     [rcx+r15*2], ax
0x18001c726  movzx   ebp, si
0x18001c729  sub     bp, word ptr [rsp+2D8h+var_2A0]
0x18001c72e  jz      short loc_18001C788
0x18001c730  movzx   edx, word ptr [rbx]
0x18001c733  movzx   eax, word ptr [rbx+2]
0x18001c737  movzx   ecx, bp
0x18001c73a  add     ecx, edx
0x18001c73c  cmp     ecx, eax
0x18001c73e  ja      short loc_18001C788
0x18001c740  mov     rax, [rbx+8]
0x18001c744  mov     ecx, edx
0x18001c746  mov     rdx, [rsp+2D8h+var_298]
0x18001c74b  shr     rcx, 1
0x18001c74e  add     rdx, r12; Src
0x18001c751  movzx   r15d, bp
0x18001c755  mov     r8d, r15d; Size
0x18001c758  lea     rax, [rax+rcx*2]
0x18001c75c  mov     rcx, rax; void *
0x18001c75f  mov     [rsp+2D8h+var_280], rax
0x18001c764  call    memmove
0x18001c769  add     [rbx], bp
0x18001c76c  movzx   ecx, word ptr [rbx]
0x18001c76f  movzx   eax, word ptr [rbx+2]
0x18001c773  inc     ecx
0x18001c775  cmp     ecx, eax
0x18001c777  jnb     short loc_18001C788
0x18001c779  mov     rcx, [rsp+2D8h+var_280]
0x18001c77e  shr     r15, 1
0x18001c781  xor     eax, eax
0x18001c783  mov     [rcx+r15*2], ax
0x18001c788  mov     rax, [rsp+2D8h+var_268]
0x18001c78d  test    rax, rax
0x18001c790  jz      short loc_18001C795
0x18001c792  mov     [rax], rbx
0x18001c795  movzx   edx, word ptr [rbx]
0x18001c798  xor     eax, eax
0x18001c79a  mov     rcx, [rbx+8]
0x18001c79e  mov     r12, [rsp+2D8h+var_298]
0x18001c7a3  shr     rdx, 1
0x18001c7a6  mov     [rcx+rdx*2], ax
0x18001c7aa  mov     rcx, [rsp+2D8h+var_260]
0x18001c7af  test    rcx, rcx
0x18001c7b2  jnz     loc_18001CBB7
0x18001c7b8  test    r14, r14
0x18001c7bb  jz      loc_18001C8D3
0x18001c7c1  xor     eax, eax
0x18001c7c3  cmp     dword ptr [rsp+2D8h+var_288], 5
0x18001c7c8  mov     [r14], eax
0x18001c7cb  mov     [r14+8], rax
0x18001c7cf  mov     [r14+10h], rax
0x18001c7d3  mov     [r14+18h], rax
0x18001c7d7  jnz     loc_18001C8D3
0x18001c7dd  mov     cl, 1
0x18001c7df  call    RtlpReferenceCurrentDirectory
0x18001c7e4  mov     rbp, rax
0x18001c7e7  test    rax, rax
0x18001c7ea  jz      loc_18001CCF8
0x18001c7f0  mov     r8b, 1
0x18001c7f3  lea     rdx, [rsp+2D8h+var_278]
0x18001c7f8  lea     rcx, [rax+18h]
0x18001c7fc  call    RtlPrefixUnicodeString
0x18001c801  test    al, al
0x18001c803  jz      loc_18001CC59
0x18001c809  movzx   eax, word ptr [rbp+18h]
0x18001c80d  movzx   ecx, word ptr [r13+0]
0x18001c812  sub     rcx, r12
0x18001c815  add     rcx, rax
0x18001c818  mov     rax, [rbx+8]
0x18001c81c  add     rax, rcx
0x18001c81f  mov     [r14+8], rax
0x18001c823  sub     si, [rbp+18h]
0x18001c827  mov     [r14], si
0x18001c82b  cmp     word ptr [rax], 5Ch ; '\'
0x18001c82f  jnz     short loc_18001C841
0x18001c831  sub     si, 2
0x18001c835  add     rax, 2
0x18001c839  mov     [r14], si
0x18001c83d  mov     [r14+8], rax
0x18001c841  test    byte ptr [rsp+2D8h+var_2A4], 2
0x18001c846  mov     [r14+2], si
0x18001c84b  jz      loc_18001CC59
0x18001c851  mov     [r14+18h], rbp
0x18001c855  mov     rax, [rbp+8]
0x18001c859  mov     [r14+10h], rax
0x18001c85d  jmp     short loc_18001C8D3
0x18001c860  lea     rcx, [rsp+2D8h+var_288]
0x18001c865  mov     r9, r12
0x18001c868  mov     [rsp+2D8h+var_2B0], rcx
0x18001c86d  mov     r8, rax
0x18001c870  lea     rcx, [rsp+2D8h+var_2A8]
0x18001c875  mov     edx, ebp
0x18001c877  mov     [rsp+2D8h+var_2B8], rcx
0x18001c87c  mov     rcx, rdi
0x18001c87f  call    RtlGetFullPathName_Ustr
0x18001c884  mov     esi, eax
0x18001c886  test    eax, eax
0x18001c888  jz      short loc_18001C8CE
0x18001c88a  cmp     [rsp+2D8h+var_2A8], 0
0x18001c88f  jnz     short loc_18001C8CE
0x18001c891  cmp     esi, ebp
0x18001c893  jbe     loc_18001CA96
0x18001c899  mov     eax, [rsp+2D8h+var_2A4]
0x18001c89d  test    al, 4
0x18001c89f  jz      loc_18001CCB5
0x18001c8a5  mov     rcx, gs:60h
0x18001c8ae  mov     r8, rsi
0x18001c8b1  xor     edx, edx
0x18001c8b3  mov     rcx, [rcx+30h]
0x18001c8b7  call    RtlAllocateHeap_0
0x18001c8bc  mov     [rsp+2D8h+var_290], rax
0x18001c8c1  test    rax, rax
0x18001c8c4  jz      loc_18001CB0E
0x18001c8ca  mov     ebp, esi
0x18001c8cc  jmp     short loc_18001C860
0x18001c8ce  mov     edi, 0C0000033h
0x18001c8d3  mov     rax, [rsp+2D8h+var_290]
0x18001c8d8  lea     rcx, [rsp+2D8h+var_258]
0x18001c8e0  cmp     rax, rcx
0x18001c8e3  jz      short loc_18001C8FC
0x18001c8e5  mov     rcx, gs:60h
0x18001c8ee  mov     r8, rax
0x18001c8f1  xor     edx, edx
0x18001c8f3  mov     rcx, [rcx+30h]
0x18001c8f7  call    RtlFreeHeap_0
0x18001c8fc  mov     eax, edi
0x18001c8fe  mov     rcx, [rsp+2D8h+var_48]
0x18001c906  xor     rcx, rsp; StackCookie
0x18001c909  call    __security_check_cookie
0x18001c90e  mov     rbx, [rsp+2D8h+arg_0]
0x18001c916  add     rsp, 2A0h
0x18001c91d  pop     r15
0x18001c91f  pop     r14
0x18001c921  pop     r13
0x18001c923  pop     r12
0x18001c925  pop     rdi
0x18001c926  pop     rsi
0x18001c927  pop     rbp
0x18001c928  retn
0x18001c92a  cmp     r8d, 1
0x18001c92e  jnz     loc_18001CAC7
0x18001c934  lea     r13, RtlpDosDevicesUncPrefix
0x18001c93b  mov     [rsp+2D8h+var_2A0], r9d
0x18001c940  mov     ecx, 0Eh
0x18001c945  jmp     loc_18001C674
0x18001c94a  movzx   edx, word ptr [rax+2]
0x18001c94e  cmp     dx, 5Ch ; '\'
0x18001c952  jnz     loc_18001CB7B
0x18001c958  cmp     word ptr [rax+4], 3Fh ; '?'
0x18001c95d  jnz     loc_18001CB85
0x18001c963  cmp     word ptr [rax+6], 5Ch ; '\'
0x18001c968  jnz     loc_18001CB85
0x18001c96e  lea     esi, [rcx+2]
0x18001c971  cmp     esi, 0FFFEh
0x18001c977  ja      loc_18001CD12
0x18001c97d  test    rbx, rbx
0x18001c980  jnz     loc_18001CCA3
0x18001c986  test    r15, r15
0x18001c989  jz      loc_18001CD1C
0x18001c98f  mov     rcx, gs:60h
0x18001c998  xor     edx, edx
0x18001c99a  mov     r8d, esi
0x18001c99d  mov     rcx, [rcx+30h]
0x18001c9a1  call    RtlAllocateHeap_0
0x18001c9a6  mov     [r15+8], rax
0x18001c9aa  test    rax, rax
0x18001c9ad  jz      loc_18001CB71
0x18001c9b3  mov     [r15], bp
0x18001c9b7  mov     rbx, r15
0x18001c9ba  mov     [r15+2], si
0x18001c9bf  mov     edx, ebp
0x18001c9c1  movzx   eax, word ptr [rbx+2]
0x18001c9c5  movzx   ecx, dx
0x18001c9c8  add     ecx, 8
0x18001c9cb  cmp     ecx, eax
0x18001c9cd  ja      short loc_18001C9FF
  ... truncated ...
```

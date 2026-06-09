# LsapLookupReallocateTranslations(_LSAPR_REFERENCED_DOMAIN_LIST * *,ulong,_LSAPR_TRANSLATED_NAME_EX * *,_LSAPR_TRANSLATED_SID_EX2 * *)

- ea: `0x18001c150`
- end: `0x18001c5c7`
- name: `?LsapLookupReallocateTranslations@@YAJPEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@KPEAPEAU_LSAPR_TRANSLATED_NAME_EX@@PEAPEAU_LSAPR_TRANSLATED_SID_EX2@@@Z`
- size: `1143`
- prototype: `__int64 __fastcall(struct _LSAPR_REFERENCED_DOMAIN_LIST **, unsigned int, struct _LSAPR_TRANSLATED_NAME_EX **, struct _LSAPR_TRANSLATED_SID_EX2 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001daa0`
- `0x18001f060`

## callees

- `0x180001fb8`
- `0x18001c150`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c185`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c1aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c216`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c297`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c2f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c378`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c3e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c463`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c185`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c1aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c216`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c297`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c2f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c378`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c3e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c4b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c4cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c4e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c515`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c529`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c53b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c544`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c565`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c574`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c593`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c5a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c4b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c4cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c4e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c515`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c529`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c53b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c544`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c565`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c574`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c593`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c5a2`
- `ntdll!RtlInitUnicodeString` at `0x18001c34d`
- `ntdll!RtlInitUnicodeString` at `0x18001c34d`
- `ntdll!RtlLengthSid` at `0x18001c283`
- `ntdll!RtlLengthSid` at `0x18001c44f`
- `ntdll!RtlLengthSid` at `0x18001c283`
- `ntdll!RtlLengthSid` at `0x18001c44f`

## pseudocode

```c
__int64 __fastcall LsapLookupReallocateTranslations(HLOCAL *a1, unsigned int a2, HLOCAL *a3, HLOCAL *a4)
{
  HLOCAL v4; // rbx
  struct _LSAPR_TRANSLATED_NAME_EX *v5; // rsi
  struct _LSAPR_TRANSLATED_SID_EX2 *v6; // rbp
  unsigned int v11; // r13d
  HLOCAL v12; // rax
  __int64 v13; // r13
  int v14; // ecx
  __int64 v15; // rcx
  HLOCAL v16; // rax
  void *v17; // rax
  HLOCAL v18; // rax
  struct _LSAPR_TRANSLATED_NAME_EX *v19; // rax
  unsigned int i; // r13d
  char *v21; // rax
  __int64 v22; // r14
  HLOCAL v23; // rax
  struct _LSAPR_TRANSLATED_SID_EX2 *v24; // rax
  __int64 j; // r14
  _QWORD *v26; // rax
  __int64 v27; // r13
  void *v28; // rax
  HLOCAL v29; // rax
  unsigned int v30; // r13d
  __int64 k; // r14
  void *v32; // rcx
  void *v33; // rcx
  unsigned int m; // ebx
  void *v35; // rcx
  __int64 n; // rbx
  void *v37; // rcx
  SIZE_T Size; // [rsp+20h] [rbp-68h]
  size_t Sizea; // [rsp+20h] [rbp-68h]
  SIZE_T Sizeb; // [rsp+20h] [rbp-68h]
  size_t Sizec; // [rsp+20h] [rbp-68h]
  void *Src; // [rsp+28h] [rbp-60h]
  void *Srca; // [rsp+28h] [rbp-60h]
  void *Srcb; // [rsp+28h] [rbp-60h]
  void *Srcc; // [rsp+28h] [rbp-60h]
  size_t v47; // [rsp+30h] [rbp-58h]
  SIZE_T v48; // [rsp+30h] [rbp-58h]
  const void *v49; // [rsp+30h] [rbp-58h]
  SIZE_T v50; // [rsp+30h] [rbp-58h]

  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( *a1 )
  {
    v4 = LocalAlloc(0x40u, 0x18u);
    if ( !v4 )
      goto LABEL_59;
    v11 = 24 * *(_DWORD *)*a1;
    v12 = LocalAlloc(0x40u, v11);
    *((_QWORD *)v4 + 1) = v12;
    if ( !v12 )
      goto LABEL_59;
    memset_0(v12, 0, v11);
    v13 = 0;
    v14 = *(_DWORD *)*a1;
    *(_DWORD *)v4 = v14;
    if ( v14 )
    {
      do
      {
        v15 = *((_QWORD *)*a1 + 1);
        Src = *(void **)(v15 + 24 * v13 + 8);
        if ( Src )
        {
          Size = *(unsigned __int16 *)(v15 + 24 * v13);
          v16 = LocalAlloc(0x40u, Size);
          v47 = (size_t)v16;
          if ( !v16 )
            goto LABEL_59;
          memcpy_0(v16, Src, Size);
          *(_WORD *)(*((_QWORD *)v4 + 1) + 24 * v13) = Size;
          *(_WORD *)(*((_QWORD *)v4 + 1) + 24 * v13 + 2) = Size;
          *(_QWORD *)(*((_QWORD *)v4 + 1) + 24 * v13 + 8) = v47;
        }
        v17 = *(void **)(*((_QWORD *)*a1 + 1) + 24 * v13 + 16);
        Srca = v17;
        if ( v17 )
        {
          v48 = RtlLengthSid(v17);
          v18 = LocalAlloc(0x40u, v48);
          Sizea = (size_t)v18;
          if ( !v18 )
            goto LABEL_59;
          memcpy_0(v18, Srca, v48);
          *(_QWORD *)(*((_QWORD *)v4 + 1) + 24 * v13 + 16) = Sizea;
        }
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < *(_DWORD *)v4 );
    }
  }
  if ( a3 && *a3 )
  {
    v19 = (struct _LSAPR_TRANSLATED_NAME_EX *)LocalAlloc(0x40u, 32 * a2);
    v5 = v19;
    if ( !v19 )
      goto LABEL_59;
    memset_0(v19, 0, 32 * a2);
    for ( i = 0; i < a2; ++i )
    {
      v21 = (char *)*a3;
      v22 = 32LL * i;
      *(_OWORD *)((char *)v5 + v22) = *(_OWORD *)((char *)*a3 + v22);
      *(_OWORD *)((char *)v5 + v22 + 16) = *(_OWORD *)&v21[v22 + 16];
      RtlInitUnicodeString((PUNICODE_STRING)((char *)v5 + v22 + 8), 0);
      v49 = *(const void **)((char *)*a3 + v22 + 16);
      if ( v49 )
      {
        Sizeb = *(unsigned __int16 *)((char *)*a3 + v22 + 8);
        v23 = LocalAlloc(0x40u, Sizeb);
        Srcb = v23;
        if ( !v23 )
          goto LABEL_59;
        memcpy_0(v23, v49, Sizeb);
        *(_WORD *)((char *)v5 + v22 + 8) = Sizeb;
        *(_WORD *)((char *)v5 + v22 + 10) = Sizeb;
        *(_QWORD *)((char *)v5 + v22 + 16) = Srcb;
      }
    }
  }
  if ( a4 && *a4 )
  {
    v24 = (struct _LSAPR_TRANSLATED_SID_EX2 *)LocalAlloc(0x40u, 24 * a2);
    v6 = v24;
    if ( v24 )
    {
      memset_0(v24, 0, 24 * a2);
      for ( j = 0; (unsigned int)j < a2; j = (unsigned int)(j + 1) )
      {
        v26 = *a4;
        v27 = 3 * j;
        *(_OWORD *)((char *)v6 + 8 * v27) = *(_OWORD *)((char *)*a4 + 24 * j);
        *((_QWORD *)v6 + v27 + 2) = v26[3 * j + 2];
        *((_QWORD *)v6 + v27 + 1) = 0;
        v28 = (void *)*((_QWORD *)*a4 + 3 * j + 1);
        Srcc = v28;
        if ( v28 )
        {
          v50 = RtlLengthSid(v28);
          v29 = LocalAlloc(0x40u, v50);
          Sizec = (size_t)v29;
          if ( !v29 )
            goto LABEL_59;
          memcpy_0(v29, Srcc, v50);
          *((_QWORD *)v6 + 3 * j + 1) = Sizec;
        }
      }
      goto LABEL_28;
    }
LABEL_59:
    v30 = -1073741801;
    goto LABEL_36;
  }
LABEL_28:
  v30 = 0;
  if ( *a1 )
  {
    LocalFree(*a1);
    *a1 = v4;
    v4 = 0;
  }
  if ( a3 && *a3 )
  {
    LocalFree(*a3);
    *a3 = v5;
    v5 = 0;
  }
  if ( a4 && *a4 )
  {
    LocalFree(*a4);
    *a4 = v6;
    v6 = 0;
  }
LABEL_36:
  if ( v4 )
  {
    if ( *((_QWORD *)v4 + 1) )
    {
      for ( k = 0; (unsigned int)k < *(_DWORD *)v4; k = (unsigned int)(k + 1) )
      {
        v32 = *(void **)(*((_QWORD *)v4 + 1) + 24 * k + 8);
        if ( v32 )
          LocalFree(v32);
        v33 = *(void **)(*((_QWORD *)v4 + 1) + 24 * k + 16);
        if ( v33 )
          LocalFree(v33);
      }
      LocalFree(*((HLOCAL *)v4 + 1));
    }
    LocalFree(v4);
  }
  if ( v5 )
  {
    for ( m = 0; m < a2; ++m )
    {
      v35 = (void *)*((_QWORD *)v5 + 4 * m + 2);
      if ( v35 )
        LocalFree(v35);
    }
    LocalFree(v5);
  }
  if ( v6 )
  {
    for ( n = 0; (unsigned int)n < a2; n = (unsigned int)(n + 1) )
    {
      v37 = (void *)*((_QWORD *)v6 + 3 * n + 1);
      if ( v37 )
        LocalFree(v37);
    }
    LocalFree(v6);
  }
  return v30;
}

```

## disassembly

```asm
0x18001c150  mov     [rsp+arg_0], rcx
0x18001c155  push    rbx
0x18001c156  push    rbp
0x18001c157  push    rsi
0x18001c158  push    rdi
0x18001c159  push    r12
0x18001c15b  push    r13
0x18001c15d  push    r14
0x18001c15f  push    r15
0x18001c161  sub     rsp, 48h
0x18001c165  xor     ebx, ebx
0x18001c167  xor     esi, esi
0x18001c169  xor     ebp, ebp
0x18001c16b  mov     r15, r9
0x18001c16e  mov     r12, r8
0x18001c171  mov     edi, edx
0x18001c173  mov     r14, rcx
0x18001c176  cmp     [rcx], rbx
0x18001c179  jz      loc_18001C2D7
0x18001c17f  lea     edx, [rbx+18h]; uBytes
0x18001c182  lea     ecx, [rbx+40h]; uFlags
0x18001c185  call    cs:__imp_LocalAlloc
0x18001c18b  mov     rbx, rax
0x18001c18e  test    rax, rax
0x18001c191  jz      loc_18001C5BC
0x18001c197  mov     rax, [r14]
0x18001c19a  mov     ecx, [rax]
0x18001c19c  lea     eax, [rcx+rcx*2]
0x18001c19f  shl     eax, 3
0x18001c1a2  lea     ecx, [rsi+40h]; uFlags
0x18001c1a5  mov     edx, eax; uBytes
0x18001c1a7  mov     r13d, eax
0x18001c1aa  call    cs:__imp_LocalAlloc
0x18001c1b0  mov     [rbx+8], rax
0x18001c1b4  test    rax, rax
0x18001c1b7  jz      loc_18001C5BC
0x18001c1bd  mov     r8d, r13d; Size
0x18001c1c0  xor     edx, edx; Val
0x18001c1c2  mov     rcx, rax; void *
0x18001c1c5  call    memset_0
0x18001c1ca  mov     rax, [r14]
0x18001c1cd  xor     r13d, r13d
0x18001c1d0  mov     ecx, [rax]
0x18001c1d2  mov     [rbx], ecx
0x18001c1d4  test    ecx, ecx
0x18001c1d6  jz      loc_18001C2D7
0x18001c1dc  mov     rax, [rsp+88h+arg_0]
0x18001c1e4  lea     r14, ds:0[r13*2]
0x18001c1ec  add     r14, r13
0x18001c1ef  mov     rax, [rax]
0x18001c1f2  mov     rcx, [rax+8]
0x18001c1f6  mov     rax, [rcx+r14*8+8]
0x18001c1fb  mov     [rsp+88h+Src], rax
0x18001c200  test    rax, rax
0x18001c203  jz      short loc_18001C262
0x18001c205  movzx   eax, word ptr [rcx+r14*8]
0x18001c20a  mov     ecx, 40h ; '@'; uFlags
0x18001c20f  mov     edx, eax; uBytes
0x18001c211  mov     [rsp+88h+Size], rax
0x18001c216  call    cs:__imp_LocalAlloc
0x18001c21c  mov     [rsp+88h+var_58], rax
0x18001c221  test    rax, rax
0x18001c224  jz      loc_18001C5BC
0x18001c22a  mov     r8, [rsp+88h+Size]; Size
0x18001c22f  mov     rcx, rax; void *
0x18001c232  mov     rdx, [rsp+88h+Src]; Src
0x18001c237  call    memcpy_0
0x18001c23c  mov     rax, [rbx+8]
0x18001c240  mov     rcx, [rsp+88h+Size]
0x18001c245  mov     [rax+r14*8], cx
0x18001c24a  mov     rax, [rbx+8]
0x18001c24e  mov     [rax+r14*8+2], cx
0x18001c254  mov     rax, [rbx+8]
0x18001c258  mov     rcx, [rsp+88h+var_58]
0x18001c25d  mov     [rax+r14*8+8], rcx
0x18001c262  mov     rax, [rsp+88h+arg_0]
0x18001c26a  mov     rax, [rax]
0x18001c26d  mov     rcx, [rax+8]
0x18001c271  mov     rax, [rcx+r14*8+10h]
0x18001c276  mov     [rsp+88h+Src], rax
0x18001c27b  test    rax, rax
0x18001c27e  jz      short loc_18001C2CB
0x18001c280  mov     rcx, rax; Sid
0x18001c283  call    cs:__imp_RtlLengthSid
0x18001c289  mov     eax, eax
0x18001c28b  mov     ecx, 40h ; '@'; uFlags
0x18001c290  mov     edx, eax; uBytes
0x18001c292  mov     [rsp+88h+var_58], rax
0x18001c297  call    cs:__imp_LocalAlloc
0x18001c29d  mov     [rsp+88h+Size], rax
0x18001c2a2  test    rax, rax
0x18001c2a5  jz      loc_18001C5BC
0x18001c2ab  mov     r8, [rsp+88h+var_58]; Size
0x18001c2b0  mov     rcx, rax; void *
0x18001c2b3  mov     rdx, [rsp+88h+Src]; Src
0x18001c2b8  call    memcpy_0
0x18001c2bd  mov     rax, [rbx+8]
0x18001c2c1  mov     rcx, [rsp+88h+Size]
0x18001c2c6  mov     [rax+r14*8+10h], rcx
0x18001c2cb  inc     r13d
0x18001c2ce  cmp     r13d, [rbx]
0x18001c2d1  jb      loc_18001C1DC
0x18001c2d7  test    r12, r12
0x18001c2da  jz      loc_18001C3C5
0x18001c2e0  cmp     [r12], rsi
0x18001c2e4  jz      loc_18001C3C5
0x18001c2ea  mov     eax, edi
0x18001c2ec  mov     ecx, 40h ; '@'; uFlags
0x18001c2f1  shl     eax, 5
0x18001c2f4  mov     edx, eax; uBytes
0x18001c2f6  mov     r14d, eax
0x18001c2f9  call    cs:__imp_LocalAlloc
0x18001c2ff  mov     rsi, rax
0x18001c302  test    rax, rax
0x18001c305  jz      loc_18001C5BC
0x18001c30b  mov     r8d, r14d; Size
0x18001c30e  xor     edx, edx; Val
0x18001c310  mov     rcx, rax; void *
0x18001c313  call    memset_0
0x18001c318  xor     r13d, r13d
0x18001c31b  test    edi, edi
0x18001c31d  jz      loc_18001C3C5
0x18001c323  mov     rax, [r12]
0x18001c327  lea     rcx, [rsi+8]
0x18001c32b  mov     r14d, r13d
0x18001c32e  xor     edx, edx; SourceString
0x18001c330  shl     r14, 5
0x18001c334  add     rcx, r14; DestinationString
0x18001c337  movups  xmm0, xmmword ptr [r14+rax]
0x18001c33c  movups  xmmword ptr [r14+rsi], xmm0
0x18001c341  movups  xmm1, xmmword ptr [r14+rax+10h]
0x18001c347  movups  xmmword ptr [r14+rsi+10h], xmm1
0x18001c34d  call    cs:__imp_RtlInitUnicodeString
0x18001c353  mov     rax, [r12]
0x18001c357  mov     rcx, [r14+rax+10h]
0x18001c35c  mov     [rsp+88h+var_58], rcx
0x18001c361  test    rcx, rcx
0x18001c364  jz      short loc_18001C3B9
0x18001c366  movzx   eax, word ptr [r14+rax+8]
0x18001c36c  mov     ecx, 40h ; '@'; uFlags
0x18001c371  mov     edx, eax; uBytes
0x18001c373  mov     [rsp+88h+Size], rax
0x18001c378  call    cs:__imp_LocalAlloc
0x18001c37e  mov     [rsp+88h+Src], rax
0x18001c383  test    rax, rax
0x18001c386  jz      loc_18001C5BC
0x18001c38c  mov     r8, [rsp+88h+Size]; Size
0x18001c391  mov     rcx, rax; void *
0x18001c394  mov     rdx, [rsp+88h+var_58]; Src
0x18001c399  call    memcpy_0
0x18001c39e  mov     rax, [rsp+88h+Size]
0x18001c3a3  mov     [r14+rsi+8], ax
0x18001c3a9  mov     [r14+rsi+0Ah], ax
0x18001c3af  mov     rax, [rsp+88h+Src]
0x18001c3b4  mov     [r14+rsi+10h], rax
0x18001c3b9  inc     r13d
0x18001c3bc  cmp     r13d, edi
0x18001c3bf  jb      loc_18001C323
0x18001c3c5  test    r15, r15
0x18001c3c8  jz      loc_18001C49F
0x18001c3ce  cmp     [r15], rbp
0x18001c3d1  jz      loc_18001C49F
0x18001c3d7  lea     eax, [rdi+rdi*2]
0x18001c3da  mov     ecx, 40h ; '@'; uFlags
0x18001c3df  shl     eax, 3
0x18001c3e2  mov     edx, eax; uBytes
0x18001c3e4  mov     r14d, eax
0x18001c3e7  call    cs:__imp_LocalAlloc
0x18001c3ed  mov     rbp, rax
0x18001c3f0  test    rax, rax
0x18001c3f3  jz      loc_18001C5BC
0x18001c3f9  mov     r8d, r14d; Size
0x18001c3fc  xor     edx, edx; Val
0x18001c3fe  mov     rcx, rax; void *
0x18001c401  call    memset_0
0x18001c406  xor     r14d, r14d
0x18001c409  test    edi, edi
0x18001c40b  jz      loc_18001C49F
0x18001c411  mov     rax, [r15]
0x18001c414  lea     r13, [r14+r14*2]
0x18001c418  movups  xmm0, xmmword ptr [rax+r13*8]
0x18001c41d  movups  xmmword ptr [rbp+r13*8+0], xmm0
0x18001c423  movsd   xmm1, qword ptr [rax+r13*8+10h]
0x18001c42a  movsd   qword ptr [rbp+r13*8+10h], xmm1
0x18001c431  mov     qword ptr [rbp+r13*8+8], 0
0x18001c43a  mov     rax, [r15]
0x18001c43d  mov     rax, [rax+r13*8+8]
0x18001c442  mov     [rsp+88h+Src], rax
0x18001c447  test    rax, rax
0x18001c44a  jz      short loc_18001C493
0x18001c44c  mov     rcx, rax; Sid
0x18001c44f  call    cs:__imp_RtlLengthSid
0x18001c455  mov     eax, eax
0x18001c457  mov     ecx, 40h ; '@'; uFlags
0x18001c45c  mov     edx, eax; uBytes
0x18001c45e  mov     [rsp+88h+var_58], rax
0x18001c463  call    cs:__imp_LocalAlloc
0x18001c469  mov     [rsp+88h+Size], rax
0x18001c46e  test    rax, rax
0x18001c471  jz      loc_18001C5BC
0x18001c477  mov     r8, [rsp+88h+var_58]; Size
0x18001c47c  mov     rcx, rax; void *
0x18001c47f  mov     rdx, [rsp+88h+Src]; Src
0x18001c484  call    memcpy_0
0x18001c489  mov     rax, [rsp+88h+Size]
0x18001c48e  mov     [rbp+r13*8+8], rax
0x18001c493  inc     r14d
0x18001c496  cmp     r14d, edi
0x18001c499  jb      loc_18001C411
0x18001c49f  mov     r14, [rsp+88h+arg_0]
0x18001c4a7  xor     r13d, r13d
0x18001c4aa  mov     rcx, [r14]; hMem
0x18001c4ad  test    rcx, rcx
0x18001c4b0  jz      short loc_18001C4BD
0x18001c4b2  call    cs:__imp_LocalFree
0x18001c4b8  mov     [r14], rbx
0x18001c4bb  xor     ebx, ebx
0x18001c4bd  test    r12, r12
0x18001c4c0  jz      short loc_18001C4D7
0x18001c4c2  mov     rcx, [r12]; hMem
0x18001c4c6  test    rcx, rcx
0x18001c4c9  jz      short loc_18001C4D7
0x18001c4cb  call    cs:__imp_LocalFree
0x18001c4d1  mov     [r12], rsi
0x18001c4d5  xor     esi, esi
0x18001c4d7  test    r15, r15
0x18001c4da  jz      short loc_18001C4EF
0x18001c4dc  mov     rcx, [r15]; hMem
0x18001c4df  test    rcx, rcx
0x18001c4e2  jz      short loc_18001C4EF
0x18001c4e4  call    cs:__imp_LocalFree
0x18001c4ea  mov     [r15], rbp
0x18001c4ed  xor     ebp, ebp
0x18001c4ef  test    rbx, rbx
0x18001c4f2  jz      short loc_18001C54A
0x18001c4f4  cmp     qword ptr [rbx+8], 0
0x18001c4f9  jz      short loc_18001C541
0x18001c4fb  xor     r14d, r14d
0x18001c4fe  cmp     [rbx], r14d
0x18001c501  jbe     short loc_18001C537
0x18001c503  mov     rax, [rbx+8]
0x18001c507  lea     r15, [r14+r14*2]
0x18001c50b  mov     rcx, [rax+r15*8+8]; hMem
0x18001c510  test    rcx, rcx
0x18001c513  jz      short loc_18001C51B
0x18001c515  call    cs:__imp_LocalFree
0x18001c51b  mov     rax, [rbx+8]
0x18001c51f  mov     rcx, [rax+r15*8+10h]; hMem
0x18001c524  test    rcx, rcx
0x18001c527  jz      short loc_18001C52F
0x18001c529  call    cs:__imp_LocalFree
0x18001c52f  inc     r14d
0x18001c532  cmp     r14d, [rbx]
0x18001c535  jb      short loc_18001C503
0x18001c537  mov     rcx, [rbx+8]; hMem
0x18001c53b  call    cs:__imp_LocalFree
0x18001c541  mov     rcx, rbx; hMem
0x18001c544  call    cs:__imp_LocalFree
0x18001c54a  test    rsi, rsi
0x18001c54d  jz      short loc_18001C57A
0x18001c54f  xor     ebx, ebx
0x18001c551  test    edi, edi
0x18001c553  jz      short loc_18001C571
0x18001c555  mov     eax, ebx
0x18001c557  shl     rax, 5
0x18001c55b  mov     rcx, [rax+rsi+10h]; hMem
0x18001c560  test    rcx, rcx
0x18001c563  jz      short loc_18001C56B
0x18001c565  call    cs:__imp_LocalFree
0x18001c56b  inc     ebx
0x18001c56d  cmp     ebx, edi
0x18001c56f  jb      short loc_18001C555
0x18001c571  mov     rcx, rsi; hMem
0x18001c574  call    cs:__imp_LocalFree
0x18001c57a  test    rbp, rbp
0x18001c57d  jz      short loc_18001C5A8
0x18001c57f  xor     ebx, ebx
0x18001c581  test    edi, edi
0x18001c583  jz      short loc_18001C59F
0x18001c585  lea     rcx, [rbx+rbx*2]
0x18001c589  mov     rcx, [rbp+rcx*8+8]; hMem
0x18001c58e  test    rcx, rcx
0x18001c591  jz      short loc_18001C599
0x18001c593  call    cs:__imp_LocalFree
0x18001c599  inc     ebx
0x18001c59b  cmp     ebx, edi
0x18001c59d  jb      short loc_18001C585
0x18001c59f  mov     rcx, rbp; hMem
0x18001c5a2  call    cs:__imp_LocalFree
0x18001c5a8  mov     eax, r13d
0x18001c5ab  add     rsp, 48h
0x18001c5af  pop     r15
0x18001c5b1  pop     r14
0x18001c5b3  pop     r13
0x18001c5b5  pop     r12
0x18001c5b7  pop     rdi
0x18001c5b8  pop     rsi
0x18001c5b9  pop     rbp
0x18001c5ba  pop     rbx
0x18001c5bb  retn
  ... truncated ...
```

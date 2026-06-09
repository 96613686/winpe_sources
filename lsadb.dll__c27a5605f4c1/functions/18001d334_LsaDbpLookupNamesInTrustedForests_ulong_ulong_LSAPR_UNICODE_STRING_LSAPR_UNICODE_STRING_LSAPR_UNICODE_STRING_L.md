# LsaDbpLookupNamesInTrustedForests(ulong,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *,long *)

- ea: `0x18001d334`
- end: `0x18001d7eb`
- name: `?LsaDbpLookupNamesInTrustedForests@@YAJKKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK3PEAJ@Z`
- size: `1207`
- prototype: `__int64 __fastcall(int, unsigned int, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001c670`

## callees

- `0x18001d334`
- `0x18001d7f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d3f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d41c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d435`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d44e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d3f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d41c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d435`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d44e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d668`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d68a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d702`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d71d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d735`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d742`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d757`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d796`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d668`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d68a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d702`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d71d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d735`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d742`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d757`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d796`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7c8`
- `LSASRV!LsapDbUpdateCountCompUnmappedNames` at `0x18001d6c8`
- `LSASRV!LsapDbUpdateCountCompUnmappedNames` at `0x18001d6c8`
- `LSASRV!LsapDbLookupMergeDisjointReferencedDomains` at `0x18001d5a0`
- `LSASRV!LsapDbLookupMergeDisjointReferencedDomains` at `0x18001d5a0`
- `LSASRV!LsapRpcCopySid` at `0x18001d61a`
- `LSASRV!LsapRpcCopySid` at `0x18001d61a`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupNamesInTrustedForests(
        int a1,
        unsigned int a2,
        struct _LSAPR_UNICODE_STRING *a3,
        struct _LSAPR_UNICODE_STRING *a4,
        struct _LSAPR_UNICODE_STRING *a5,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a6,
        struct _LSAPR_TRANSLATED_SIDS_EX2 *a7,
        unsigned int *a8,
        unsigned int *a9,
        int *a10)
{
  int v13; // ebx
  HLOCAL v14; // r10
  _QWORD *v15; // r12
  unsigned int v16; // r15d
  unsigned int v17; // edx
  SIZE_T v18; // rbx
  struct _LSAPR_UNICODE_STRING *v19; // rax
  unsigned int v20; // r9d
  struct _LSAPR_UNICODE_STRING *v21; // r10
  struct _LSAPR_UNICODE_STRING *v22; // r11
  unsigned int v23; // r8d
  struct _LSAPR_UNICODE_STRING *v24; // rsi
  struct _LSAPR_UNICODE_STRING *v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rcx
  _DWORD *v28; // r12
  struct _LSAPR_UNICODE_STRING *v29; // r13
  HLOCAL v30; // r14
  int v31; // eax
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v32; // rdi
  unsigned int v33; // esi
  struct _LSAPR_TRANSLATED_SIDS_EX2 *v34; // rcx
  __int64 v35; // r13
  __int64 v36; // rax
  _QWORD *v37; // rcx
  unsigned int i; // edi
  void *v39; // rcx
  void *v40; // rcx
  unsigned int j; // edi
  void *v42; // rcx
  unsigned int v44; // [rsp+40h] [rbp-69h]
  HLOCAL v45; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v46; // [rsp+58h] [rbp-51h] BYREF
  HLOCAL v47; // [rsp+60h] [rbp-49h]
  struct _LSAPR_UNICODE_STRING *v48; // [rsp+68h] [rbp-41h]
  int v49; // [rsp+70h] [rbp-39h] BYREF
  HLOCAL v50; // [rsp+78h] [rbp-31h]
  HLOCAL hMem; // [rsp+80h] [rbp-29h] BYREF
  HLOCAL v52; // [rsp+88h] [rbp-21h]
  __int128 v53; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int8 v54; // [rsp+F8h] [rbp+4Fh] BYREF
  struct _LSAPR_UNICODE_STRING *v55; // [rsp+100h] [rbp+57h]

  v55 = a3;
  v49 = 0;
  v46 = 0;
  *a10 = 0;
  v13 = 0;
  v45 = 0;
  v14 = 0;
  hMem = 0;
  v15 = 0;
  v47 = 0;
  v16 = 0;
  v50 = 0;
  v52 = 0;
  v48 = 0;
  v54 = 0;
  v53 = 0;
  if ( a2 )
  {
    v17 = 0;
    do
    {
      if ( (a1 >= 0 || *((_WORD *)a4 + 8 * v17)) && (*(_BYTE *)(*((_QWORD *)a7 + 1) + 24LL * v17 + 20) & 2) != 0 )
        ++v16;
      ++v17;
    }
    while ( v17 < a2 );
    if ( v16 )
    {
      v50 = LocalAlloc(0x40u, 4LL * v16);
      if ( v50 )
      {
        v18 = 16LL * v16;
        v47 = LocalAlloc(0x40u, v18);
        if ( v47 )
        {
          v52 = LocalAlloc(0x40u, v18);
          if ( v52 )
          {
            v19 = (struct _LSAPR_UNICODE_STRING *)LocalAlloc(0x40u, v18);
            v20 = 0;
            v48 = v19;
            if ( v19 )
            {
              v21 = a5;
              v22 = (struct _LSAPR_UNICODE_STRING *)v47;
              v23 = 0;
              v24 = (struct _LSAPR_UNICODE_STRING *)v52;
              v25 = v19;
              do
              {
                if ( v20 >= v16 )
                  break;
                if ( (a1 >= 0 || *((_WORD *)a4 + 8 * v23))
                  && (*(_BYTE *)(*((_QWORD *)a7 + 1) + 24LL * v23 + 20) & 2) != 0 )
                {
                  v26 = 2LL * v20;
                  v27 = v20++;
                  v28 = v50;
                  *(_OWORD *)((char *)v22 + 8 * v26) = *((_OWORD *)v55 + v23);
                  *(_OWORD *)((char *)v24 + 8 * v26) = *((_OWORD *)a4 + v23);
                  *(_OWORD *)((char *)v25 + 8 * v26) = *((_OWORD *)v21 + v23);
                  v28[v27] = v23;
                }
                ++v23;
              }
              while ( v23 < a2 );
              v46 = 0;
              LODWORD(v53) = 0;
              *((_QWORD *)&v53 + 1) = 0;
              v29 = v25;
              v30 = v22;
              v31 = LsaDbpLookupNamesInTrustedForestsWorker(
                      v16,
                      v22,
                      v24,
                      v25,
                      (struct _LSAPR_REFERENCED_DOMAIN_LIST **)&v45,
                      (struct _LSAPR_TRANSLATED_SIDS_EX2 *)&v53,
                      &v54,
                      &v46,
                      v44,
                      &v49);
              v13 = v31;
              v15 = 0;
              if ( *((_QWORD *)&v53 + 1) )
              {
                v15 = (_QWORD *)*((_QWORD *)&v53 + 1);
                *((_QWORD *)&v53 + 1) = 0;
                LODWORD(v53) = 0;
              }
              if ( v31 >= 0 )
              {
                v31 = v49;
                if ( v49 >= 0 )
                  goto LABEL_31;
              }
              else
              {
                if ( (unsigned int)(v31 + 1073741428) > 1 && v31 != -1073741136 )
                {
                  if ( v31 == -1073741709 )
                  {
LABEL_31:
                    v32 = a6;
                    v13 = LsapDbLookupMergeDisjointReferencedDomains(a6, v45, &hMem, 1);
                    if ( v13 >= 0 )
                    {
                      v33 = 0;
                      LODWORD(a10) = *(_DWORD *)v32;
                      do
                      {
                        if ( LODWORD(v15[3 * v33 + 2]) != -1 || LODWORD(v15[3 * v33]) != 8 )
                        {
                          v34 = a7;
                          v35 = 3LL * *((unsigned int *)v50 + v33);
                          v36 = *((_QWORD *)a7 + 1);
                          *(_OWORD *)(v36 + 8 * v35) = *(_OWORD *)&v15[3 * v33];
                          *(_QWORD *)(v36 + 8 * v35 + 16) = v15[3 * v33 + 2];
                          v13 = LsapRpcCopySid(0, *((_QWORD *)v34 + 1) + 8LL + 8 * v35, v15[3 * v33 + 1], 0);
                          if ( v13 < 0 )
                            goto LABEL_43;
                          *(_DWORD *)(*((_QWORD *)a7 + 1) + 8 * v35 + 16) = LODWORD(v15[3 * v33 + 2]) + (_DWORD)a10;
                          --*a9;
                        }
                        ++v33;
                      }
                      while ( v33 < v16 );
                      v37 = hMem;
                      if ( hMem )
                      {
                        if ( *((_QWORD *)v32 + 1) )
                        {
                          LocalFree(*((HLOCAL *)v32 + 1));
                          v37 = hMem;
                          *((_QWORD *)v32 + 1) = 0;
                        }
                        *(_OWORD *)v32 = *(_OWORD *)v37;
                        *((_QWORD *)v32 + 2) = v37[2];
                        LocalFree(v37);
                        hMem = 0;
                      }
                      *a8 += v46;
                    }
                  }
LABEL_43:
                  v14 = v45;
                  v30 = v47;
                  v29 = v48;
                  goto LABEL_45;
                }
                v13 = 0;
              }
              v14 = v45;
              *a10 = v31;
              goto LABEL_45;
            }
          }
        }
      }
      v13 = -1073741670;
      goto LABEL_43;
    }
  }
  v29 = 0;
  v30 = 0;
LABEL_45:
  if ( *a9 )
  {
    LsapDbUpdateCountCompUnmappedNames(a7, a9);
    v14 = v45;
  }
  if ( v14 )
  {
    if ( !v54 && *((_QWORD *)v14 + 1) )
    {
      for ( i = 0; i < *(_DWORD *)v14; ++i )
      {
        v39 = *(void **)(*((_QWORD *)v14 + 1) + 24LL * i + 8);
        if ( v39 )
        {
          LocalFree(v39);
          v14 = v45;
        }
        v40 = *(void **)(*((_QWORD *)v14 + 1) + 24LL * i + 16);
        if ( v40 )
        {
          LocalFree(v40);
          v14 = v45;
        }
      }
      LocalFree(*((HLOCAL *)v14 + 1));
      v14 = v45;
    }
    LocalFree(v14);
    v45 = 0;
  }
  if ( v30 )
    LocalFree(v30);
  if ( v15 )
  {
    if ( !v54 )
    {
      for ( j = 0; j < v16; ++j )
      {
        v42 = (void *)v15[3 * j + 1];
        if ( v42 )
          LocalFree(v42);
      }
    }
    LocalFree(v15);
  }
  if ( v52 )
    LocalFree(v52);
  if ( v29 )
    LocalFree(v29);
  if ( v50 )
    LocalFree(v50);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001d334  mov     [rsp-8+arg_0], rbx
0x18001d339  mov     [rsp-8+arg_10], r8
0x18001d33e  push    rbp
0x18001d33f  push    rsi
0x18001d340  push    rdi
0x18001d341  push    r12
0x18001d343  push    r13
0x18001d345  push    r14
0x18001d347  push    r15
0x18001d349  lea     rbp, [rsp-7]
0x18001d34e  sub     rsp, 0B0h
0x18001d355  mov     rsi, [rbp+37h+arg_48]
0x18001d35c  mov     r14, r9
0x18001d35f  xor     r9d, r9d
0x18001d362  xorps   xmm0, xmm0
0x18001d365  mov     [rbp+37h+var_70], r9d
0x18001d369  mov     edi, edx
0x18001d36b  mov     [rbp+37h+var_88], r9d
0x18001d36f  mov     r13d, ecx
0x18001d372  mov     [rsi], r9d
0x18001d375  mov     ebx, r9d
0x18001d378  mov     [rbp+37h+var_90], r9
0x18001d37c  mov     r10d, r9d
0x18001d37f  mov     [rbp+37h+hMem], r9
0x18001d383  mov     r12d, r9d
0x18001d386  mov     [rbp+37h+var_80], r9
0x18001d38a  mov     r15d, r9d
0x18001d38d  mov     [rbp+37h+var_68], r9
0x18001d391  mov     [rbp+37h+var_58], r9
0x18001d395  mov     [rbp+37h+var_78], r9
0x18001d399  mov     [rbp+37h+arg_8], r9b
0x18001d39d  movups  [rbp+37h+var_50], xmm0
0x18001d3a1  test    edx, edx
0x18001d3a3  jz      loc_18001D6AF
0x18001d3a9  mov     r8, [rbp+37h+arg_30]
0x18001d3ad  mov     edx, r9d
0x18001d3b0  mov     ecx, edx
0x18001d3b2  test    r13d, r13d
0x18001d3b5  jns     short loc_18001D3C3
0x18001d3b7  mov     eax, ecx
0x18001d3b9  add     rax, rax
0x18001d3bc  cmp     [r14+rax*8], r9w
0x18001d3c1  jz      short loc_18001D3D5
0x18001d3c3  mov     rax, [r8+8]
0x18001d3c7  lea     rcx, [rcx+rcx*2]
0x18001d3cb  test    byte ptr [rax+rcx*8+14h], 2
0x18001d3d0  jz      short loc_18001D3D5
0x18001d3d2  inc     r15d
0x18001d3d5  inc     edx
0x18001d3d7  cmp     edx, edi
0x18001d3d9  jb      short loc_18001D3B0
0x18001d3db  test    r15d, r15d
0x18001d3de  jz      loc_18001D6AF
0x18001d3e4  mov     ebx, r15d
0x18001d3e7  mov     ecx, 40h ; '@'; uFlags
0x18001d3ec  lea     rdx, ds:0[rbx*4]; uBytes
0x18001d3f4  call    cs:__imp_LocalAlloc
0x18001d3fa  xor     r9d, r9d
0x18001d3fd  mov     [rbp+37h+var_68], rax
0x18001d401  test    rax, rax
0x18001d404  jnz     short loc_18001D410
0x18001d406  mov     ebx, 0C000009Ah
0x18001d40b  jmp     loc_18001D6A1
0x18001d410  shl     rbx, 4
0x18001d414  mov     ecx, 40h ; '@'; uFlags
0x18001d419  mov     rdx, rbx; uBytes
0x18001d41c  call    cs:__imp_LocalAlloc
0x18001d422  xor     r9d, r9d
0x18001d425  mov     [rbp+37h+var_80], rax
0x18001d429  test    rax, rax
0x18001d42c  jz      short loc_18001D406
0x18001d42e  mov     rdx, rbx; uBytes
0x18001d431  lea     ecx, [r9+40h]; uFlags
0x18001d435  call    cs:__imp_LocalAlloc
0x18001d43b  xor     r9d, r9d
0x18001d43e  mov     [rbp+37h+var_58], rax
0x18001d442  test    rax, rax
0x18001d445  jz      short loc_18001D406
0x18001d447  mov     rdx, rbx; uBytes
0x18001d44a  lea     ecx, [r9+40h]; uFlags
0x18001d44e  call    cs:__imp_LocalAlloc
0x18001d454  xor     r9d, r9d
0x18001d457  mov     [rbp+37h+var_78], rax
0x18001d45b  test    rax, rax
0x18001d45e  jz      short loc_18001D406
0x18001d460  mov     r10, [rbp+37h+arg_20]
0x18001d464  xor     ecx, ecx
0x18001d466  mov     r11, [rbp+37h+var_80]
0x18001d46a  mov     r8d, ecx
0x18001d46d  mov     rsi, [rbp+37h+var_58]
0x18001d471  mov     rbx, rax
0x18001d474  cmp     r9d, r15d
0x18001d477  jnb     short loc_18001D4E2
0x18001d479  mov     edx, r8d
0x18001d47c  add     rdx, rdx
0x18001d47f  mov     eax, r8d
0x18001d482  test    r13d, r13d
0x18001d485  jns     short loc_18001D48E
0x18001d487  cmp     [r14+rdx*8], cx
0x18001d48c  jz      short loc_18001D4DA
0x18001d48e  lea     rcx, [rax+rax*2]
0x18001d492  mov     rax, [rbp+37h+arg_30]
0x18001d496  mov     rax, [rax+8]
0x18001d49a  test    byte ptr [rax+rcx*8+14h], 2
0x18001d49f  jz      short loc_18001D4D8
0x18001d4a1  mov     r12, [rbp+37h+arg_10]
0x18001d4a5  mov     eax, r9d
0x18001d4a8  add     rax, rax
0x18001d4ab  mov     ecx, r9d
0x18001d4ae  inc     r9d
0x18001d4b1  movups  xmm0, xmmword ptr [r12+rdx*8]
0x18001d4b6  mov     r12, [rbp+37h+var_68]
0x18001d4ba  movdqu  xmmword ptr [r11+rax*8], xmm0
0x18001d4c0  movups  xmm1, xmmword ptr [r14+rdx*8]
0x18001d4c5  movdqu  xmmword ptr [rsi+rax*8], xmm1
0x18001d4ca  movups  xmm0, xmmword ptr [r10+rdx*8]
0x18001d4cf  movdqu  xmmword ptr [rbx+rax*8], xmm0
0x18001d4d4  mov     [r12+rcx*4], r8d
0x18001d4d8  xor     ecx, ecx
0x18001d4da  inc     r8d
0x18001d4dd  cmp     r8d, edi
0x18001d4e0  jb      short loc_18001D474
0x18001d4e2  lea     rax, [rbp+37h+var_70]
0x18001d4e6  mov     [rbp+37h+var_88], ecx
0x18001d4e9  mov     [rsp+0E0h+var_98], rax; int *
0x18001d4ee  mov     r9, rbx; struct _LSAPR_UNICODE_STRING *
0x18001d4f1  lea     rax, [rbp+37h+var_88]
0x18001d4f5  mov     dword ptr [rbp+37h+var_50], ecx
0x18001d4f8  mov     [rsp+0E0h+var_A8], rax; unsigned int *
0x18001d4fd  mov     r8, rsi; struct _LSAPR_UNICODE_STRING *
0x18001d500  lea     rax, [rbp+37h+arg_8]
0x18001d504  mov     qword ptr [rbp+37h+var_50+8], rcx
0x18001d508  mov     [rsp+0E0h+var_B0], rax; unsigned __int8 *
0x18001d50d  mov     rdx, r11; struct _LSAPR_UNICODE_STRING *
0x18001d510  lea     rax, [rbp+37h+var_50]
0x18001d514  mov     ecx, r15d; unsigned int
0x18001d517  mov     [rsp+0E0h+var_B8], rax; struct _LSAPR_TRANSLATED_SIDS_EX2 *
0x18001d51c  mov     r13, rbx
0x18001d51f  lea     rax, [rbp+37h+var_90]
0x18001d523  mov     r14, r11
0x18001d526  mov     [rsp+0E0h+var_C0], rax; struct _LSAPR_REFERENCED_DOMAIN_LIST **
0x18001d52b  call    ?LsaDbpLookupNamesInTrustedForestsWorker@@YAJKPEAU_LSAPR_UNICODE_STRING@@00PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAEPEAKKPEAJ@Z; LsaDbpLookupNamesInTrustedForestsWorker(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_SIDS_EX2 *,uchar *,ulong *,ulong,long *)
0x18001d530  mov     rcx, qword ptr [rbp+37h+var_50+8]
0x18001d534  xor     r9d, r9d
0x18001d537  mov     rsi, [rbp+37h+arg_48]
0x18001d53e  mov     ebx, eax
0x18001d540  mov     r12d, r9d
0x18001d543  test    rcx, rcx
0x18001d546  jz      short loc_18001D553
0x18001d548  mov     r12, rcx
0x18001d54b  mov     qword ptr [rbp+37h+var_50+8], r9
0x18001d54f  mov     dword ptr [rbp+37h+var_50], r9d
0x18001d553  test    eax, eax
0x18001d555  jns     short loc_18001D584
0x18001d557  lea     ecx, [rax+3FFFFE74h]
0x18001d55d  cmp     ecx, 1
0x18001d560  jbe     short loc_18001D576
0x18001d562  cmp     eax, 0C00002B0h
0x18001d567  jz      short loc_18001D576
0x18001d569  cmp     eax, 0C0000073h
0x18001d56e  jnz     loc_18001D6A1
0x18001d574  jmp     short loc_18001D58B
0x18001d576  mov     ebx, r9d
0x18001d579  mov     r10, [rbp+37h+var_90]
0x18001d57d  mov     [rsi], eax
0x18001d57f  jmp     loc_18001D6B5
0x18001d584  mov     eax, [rbp+37h+var_70]
0x18001d587  test    eax, eax
0x18001d589  js      short loc_18001D579
0x18001d58b  mov     rdi, [rbp+37h+arg_28]
0x18001d58f  lea     r8, [rbp+37h+hMem]
0x18001d593  mov     rdx, [rbp+37h+var_90]
0x18001d597  mov     rcx, rdi
0x18001d59a  mov     r9d, 1
0x18001d5a0  call    cs:__imp_LsapDbLookupMergeDisjointReferencedDomains
0x18001d5a6  xor     r9d, r9d
0x18001d5a9  mov     ebx, eax
0x18001d5ab  test    eax, eax
0x18001d5ad  js      loc_18001D6A1
0x18001d5b3  mov     eax, [rdi]
0x18001d5b5  mov     esi, r9d
0x18001d5b8  mov     dword ptr [rbp+37h+arg_48], eax
0x18001d5be  test    r15d, r15d
0x18001d5c1  jz      loc_18001D655
0x18001d5c7  mov     eax, esi
0x18001d5c9  lea     r14, [rax+rax*2]
0x18001d5cd  cmp     dword ptr [r12+r14*8+10h], 0FFFFFFFFh
0x18001d5d3  jnz     short loc_18001D5DC
0x18001d5d5  cmp     dword ptr [r12+r14*8], 8
0x18001d5da  jz      short loc_18001D64A
0x18001d5dc  movups  xmm0, xmmword ptr [r12+r14*8]
0x18001d5e1  mov     rcx, [rbp+37h+var_68]
0x18001d5e5  mov     eax, [rcx+rax*4]
0x18001d5e8  mov     rcx, [rbp+37h+arg_30]
0x18001d5ec  lea     r13, [rax+rax*2]
0x18001d5f0  mov     rax, [rcx+8]
0x18001d5f4  movups  xmmword ptr [rax+r13*8], xmm0
0x18001d5f9  movsd   xmm1, qword ptr [r12+r14*8+10h]
0x18001d600  movsd   qword ptr [rax+r13*8+10h], xmm1
0x18001d607  mov     rdx, [rcx+8]
0x18001d60b  xor     ecx, ecx
0x18001d60d  mov     r8, [r12+r14*8+8]
0x18001d612  add     rdx, 8
0x18001d616  lea     rdx, [rdx+r13*8]
0x18001d61a  call    cs:__imp_LsapRpcCopySid
0x18001d620  xor     r9d, r9d
0x18001d623  mov     ebx, eax
0x18001d625  test    eax, eax
0x18001d627  js      short loc_18001D6A1
0x18001d629  mov     rax, [rbp+37h+arg_30]
0x18001d62d  mov     ecx, dword ptr [rbp+37h+arg_48]
0x18001d633  add     ecx, [r12+r14*8+10h]
0x18001d638  mov     rax, [rax+8]
0x18001d63c  mov     [rax+r13*8+10h], ecx
0x18001d641  mov     rax, [rbp+37h+arg_40]
0x18001d648  dec     dword ptr [rax]
0x18001d64a  inc     esi
0x18001d64c  cmp     esi, r15d
0x18001d64f  jb      loc_18001D5C7
0x18001d655  mov     rcx, [rbp+37h+hMem]
0x18001d659  test    rcx, rcx
0x18001d65c  jz      short loc_18001D697
0x18001d65e  cmp     [rdi+8], r9
0x18001d662  jz      short loc_18001D67A
0x18001d664  mov     rcx, [rdi+8]; hMem
0x18001d668  call    cs:__imp_LocalFree
0x18001d66e  mov     rcx, [rbp+37h+hMem]; hMem
0x18001d672  mov     qword ptr [rdi+8], 0
0x18001d67a  movups  xmm0, xmmword ptr [rcx]
0x18001d67d  movups  xmmword ptr [rdi], xmm0
0x18001d680  movsd   xmm1, qword ptr [rcx+10h]
0x18001d685  movsd   qword ptr [rdi+10h], xmm1
0x18001d68a  call    cs:__imp_LocalFree
0x18001d690  xor     r9d, r9d
0x18001d693  mov     [rbp+37h+hMem], r9
0x18001d697  mov     r8, [rbp+37h+arg_38]
0x18001d69b  mov     eax, [rbp+37h+var_88]
0x18001d69e  add     [r8], eax
0x18001d6a1  mov     r10, [rbp+37h+var_90]
0x18001d6a5  mov     r14, [rbp+37h+var_80]
0x18001d6a9  mov     r13, [rbp+37h+var_78]
0x18001d6ad  jmp     short loc_18001D6B5
0x18001d6af  mov     r13, rbx
0x18001d6b2  mov     r14, rbx
0x18001d6b5  mov     rax, [rbp+37h+arg_40]
0x18001d6bc  cmp     [rax], r9d
0x18001d6bf  jbe     short loc_18001D6D5
0x18001d6c1  mov     rcx, [rbp+37h+arg_30]
0x18001d6c5  mov     rdx, rax
0x18001d6c8  call    cs:__imp_LsapDbUpdateCountCompUnmappedNames
0x18001d6ce  mov     r10, [rbp+37h+var_90]
0x18001d6d2  xor     r9d, r9d
0x18001d6d5  test    r10, r10
0x18001d6d8  jz      short loc_18001D74F
0x18001d6da  cmp     [rbp+37h+arg_8], r9b
0x18001d6de  jnz     short loc_18001D73F
0x18001d6e0  cmp     [r10+8], r9
0x18001d6e4  jz      short loc_18001D73F
0x18001d6e6  mov     edi, r9d
0x18001d6e9  cmp     [r10], r9d
0x18001d6ec  jbe     short loc_18001D731
0x18001d6ee  mov     eax, edi
0x18001d6f0  lea     rsi, [rax+rax*2]
0x18001d6f4  mov     rax, [r10+8]
0x18001d6f8  mov     rcx, [rax+rsi*8+8]; hMem
0x18001d6fd  test    rcx, rcx
0x18001d700  jz      short loc_18001D70F
0x18001d702  call    cs:__imp_LocalFree
0x18001d708  mov     r10, [rbp+37h+var_90]
0x18001d70c  xor     r9d, r9d
0x18001d70f  mov     rax, [r10+8]
0x18001d713  mov     rcx, [rax+rsi*8+10h]; hMem
0x18001d718  test    rcx, rcx
0x18001d71b  jz      short loc_18001D72A
0x18001d71d  call    cs:__imp_LocalFree
0x18001d723  mov     r10, [rbp+37h+var_90]
0x18001d727  xor     r9d, r9d
0x18001d72a  inc     edi
0x18001d72c  cmp     edi, [r10]
0x18001d72f  jb      short loc_18001D6EE
0x18001d731  mov     rcx, [r10+8]; hMem
0x18001d735  call    cs:__imp_LocalFree
0x18001d73b  mov     r10, [rbp+37h+var_90]
0x18001d73f  mov     rcx, r10; hMem
0x18001d742  call    cs:__imp_LocalFree
0x18001d748  xor     r9d, r9d
0x18001d74b  mov     [rbp+37h+var_90], r9
0x18001d74f  test    r14, r14
0x18001d752  jz      short loc_18001D760
0x18001d754  mov     rcx, r14; hMem
0x18001d757  call    cs:__imp_LocalFree
0x18001d75d  xor     r9d, r9d
0x18001d760  test    r12, r12
0x18001d763  jz      short loc_18001D79C
0x18001d765  cmp     [rbp+37h+arg_8], r9b
0x18001d769  jnz     short loc_18001D793
0x18001d76b  mov     edi, r9d
0x18001d76e  test    r15d, r15d
0x18001d771  jz      short loc_18001D793
0x18001d773  mov     eax, edi
  ... truncated ...
```
